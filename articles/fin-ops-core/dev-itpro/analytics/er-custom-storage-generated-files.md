---
title: Especificar locais de armazenamento personalizado para os documentos gerados
description: Este tópico explica como estender a lista de locais de armazenamento para documentos gerados pelos formatos de Relatório eletrônico (ER).
author: NickSelin
ms.date: 10/29/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-3-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 83b2d3c35e3e68aaad22bc03a46b17abc1526073895057717fd055dacdfbee5c
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6718468"
---
# <a name="specify-custom-storage-locations-for-generated-documents"></a>Especificar locais de armazenamento personalizado para os documentos gerados

[!include[banner](../includes/banner.md)]

A interface de programação de aplicativos (API) da estrutura de relatórios eletrônicos (ER) permite estender a lista de locais de armazenamento para documentos gerados pelos formatos ER. Este tópico explica como adicionar um local de armazenamento personalizado para documentos gerados delegando a tarefa de criar destinos de ER ao alocador de destino padrão e, em seguida, implementando uma classe personalizada que tem sua própria lógica de destino.

## <a name="prerequisites"></a>Pré-requisitos

Implante uma topologia que dê suporte à compilação contínua. Para obter mais informações, consulte [Implantar topologias que dão suporte à contínua automação de compilações e testes](/dynamics365/unified-operations/dev-itpro/perf-test/continuous-build-test-automation). Você também deve ter acesso a essa topologia para uma das seguintes funções:

- Desenvolvedor de relatório eletrônico
- Consultor funcional de relatório eletrônico
- Administrador do sistema

Você também deve ter acesso ao ambiente de desenvolvimento para essa topologia.

Todas as tarefas deste tópico podem ser concluídas na empresa **USMF**.

## <a name="import-the-fixed-asset-roll-forward-er-format"></a>Importar o formato de ER de roll forward de ativo fixo

Para gerar os documentos aos quais você quer adicionar um local de armazenamento personalizado, [importe](er-download-configurations-global-repo.md) a **configuração do formato de ER de roll forward de ativo fixo** para a topologia atual.

![Página do repositório de configuração.](./media/er-custom-storage-generated-files-import-format.png)

## <a name="run-the-fixed-asset-roll-forward-report"></a>Gerar o Relatório de roll forward de ativo fixo

1. Acesse **Ativos fixos** \> **Consultas e relatórios** \> **Relatórios de transações** \> **Roll forward de ativo fixo**.
2. No campo **Data inicial**, insira **1/1/2017** (1º de janeiro de 2017).
3. No campo **Data final**, insira **1/31/2017** (31 de janeiro de 2017).
4. No **campo Moeda**, selecione a **Moeda contábil**.
5. No campo **Mapeamento de formato**, selecione **Roll forward de ativo fixo**.
6. Selecione **OK**.

![Caixa de diálogo de runtime do Relatório de roll forward de ativo fixo.](./media/er-custom-storage-generated-files-runtime-dialog.png)

Em Microsoft Excel, revise o documento de saída gerado disponível para download. Esse comportamento é o [comportamento padrão ](electronic-reporting-destinations.md#default-behavior)para um formato de ER em que nenhum [destino](electronic-reporting-destinations.md) está configurado e que está sendo executado no modo interativo.

## <a name="review-the-source-code"></a>Revisar o código-fonte

Revise o código do método `generateReportByGER()` da classe `AssetRollForwardService`. Observe que o método `Run()` é usado para chamar a estrutura de ER e gerar o **Relatório de roll forward de ativo fixo**.

```xpp
class AssetRollForwardService extends SysOperationServiceBase
{
    public const str ERFormatModelName = 'Fixed assets';
    public const str ERModelDataSourceName = 'model';
    public const str DefaultExportedFileName = 'AssetRollForward';

    /// <summary>
    /// Generates report by general electronic reporting
    /// </summary>
    /// <param name = "_contract">The Asset Period Statement contract</param>
    public void generateReportByGER(AssetRollForwardContract _contract)
    {
        ERFormatMappingId   formatMappingId;
        AssetRollForwardDP  dataProvider;
        AssetRollForwardTmp assetRollForwardTmp;
        Query               query;

        query = new Query(SysOperationHelper::base64Decode(_contract.parmQuery()));
        dataProvider = AssetRollForwardDP::construct();
        formatMappingId = _contract.parmFormatMapping();
        assetRollForwardTmp = dataProvider.getAssetRollForwardTmp(_contract, query);

        if (assetRollForwardTmp)
        {
            try
            {
                ERIModelDefinitionParamsAction parameters = new ERModelDefinitionParamsUIActionComposite()
                    .add(new ERModelDefinitionDatabaseContext().addTemporaryTable(assetRollForwardTmp))
                    .add(new ERModelDefinitionObjectParameterAction(ERModelDataSourceName, 'MyParameters', _contract, true));

                // Call ER to generate the report.
                ERObjectsFactory::createFormatMappingRunByFormatMappingId(formatMappingId, DefaultExportedFileName)
                    .withParameter(parameters)
                    .withFileDestination(_contract.getFileDestination())
                    .run();
            }
            catch
            {
                // An error occurred while exporting data.
                error("@SYP4861341");
            }
        }
        else
        {
            // There is no data available.
            info("@SYS300117");
        }
    }
}
```

## <a name="modify-the-source-code"></a>Modificar o código-fonte

1. No seu projeto Visual Studio, adicione uma nova classe (`AssetRollForwardDestination` neste exemplo) e escreva o código para implementar seu destino personalizado para os **Relatórios de roll forward de ativo fixo** gerados.

    - O método `new()` foi projetado para obter o objeto de destino de ER original e o parâmetro baseado na lógica do aplicativo que especifica o local personalizado onde os relatórios gerados devem ser armazenados. Neste exemplo, o local personalizado é o nome de uma pasta do sistema de arquivos local do servidor que executa o serviço de AOS (Servidor de Objetos de Aplicativo).
    - O método `saveFile()` foi projetado para salvar um documento gerado em uma pasta do sistema de arquivos local do servidor que executa o serviço de AOS.

    ```xpp
    using Microsoft.Dynamics365.LocalizationFramework;

    /// <summary>
    /// Destination class for <c>AssetRollForwardDestinationFactory</c> that stores a generated report.
    /// </summary>
    public class AssetRollForwardDestination implements ERIFileDestination
    {
        private ERIFileDestination originDestination;
        private str TargetFolder;

        /// <summary>
        /// Creates a stream for new file.
        /// </summary>
        /// <param name = "_fileName">Name of a new file.</param>
        /// <returns>Stream for new file.</returns>
        public System.IO.Stream newFileStream(System.String _fileName)
        {
            return originDestination.newFileStream(_fileName);
        }

        /// <summary>
        /// Saves file in destination.
        /// </summary>
        /// <param name = "_stream">A stream to save.</param>
        /// <param name = "_fileName">A file name.</param>
        /// <returns>Saved stream.</returns>
        public System.IO.Stream saveFile(System.IO.Stream _stream, System.String _fileName)
        {
            _stream.Seek(0, System.IO.SeekOrigin::Begin);
            using (var localStream = System.IO.File::OpenWrite(TargetFolder + _fileName))
            {
                _stream.CopyTo(localStream);
            }
            return _stream;
        }

        /// <summary>
        /// Constructs destination for fixed asset roll forward report.
        /// </summary>
        /// <param name = "_originDestination">The original destination.</param>
        /// <param name = "_TargetFoder">The folder to store a report that's being created.</param>
        /// <returns>The fixed asset roll forward destination.</returns>
        public static AssetRollForwardDestination construct(ERIFileDestination _originDestination, str _TargetFoder)
        {
            return new AssetRollForwardDestination(_originDestination, _TargetFoder);
        }

        protected void new(ERIFileDestination _originDestination, str _TargetFoder)
        {
            originDestination = _originDestination;
            TargetFolder = _TargetFoder;
        }
    }
    ```

2. No seu projeto Visual Studio, adicione uma nova classe (`AssetRollForwardDestinationFactory` no exemplo) e escreva o código para configurar um alocador de destino personalizado que delega a criação de um destino ao alocador padrão e para empacotar um destino de arquivo com seu próprio destino.

    ```xpp
    using Microsoft.Dynamics365.LocalizationFramework;
    using Microsoft.Dynamics365.LocalizationFramework.Format.FileGeneration;

    /// <summary>
    /// Destination factory for using <c>AssetRollForwardDestinationFactory</c>.
    /// </summary>
    public class AssetRollForwardDestinationFactory implements ERIFileDestinationFactory, ERIFileDestinationFactoryPostProcessor
    {
        private ERIFileDestinationFactory originDestinationFactory;
        private str TargetFolder;

        /// <summary>
        /// Creates file destination for print management.
        /// </summary>
        /// <param name = "_fileDestination">A default file destination.</param>
        /// <param name = "_identification">An identification strategy.</param>
        /// <param name = "_rootContext">A root context.</param>
        /// <param name = "_root">A root element.</param>
        /// <returns>A file destination.</returns>
        public ERIDataDrivenFileDestination createPrintMgmtDestination(
            ERIFileDestination _fileDestination,
            ERIObjectIdentificationStrategy _identification,
            ERTextFormatDataContext _rootContext,
            ERTextFormatIFileComponent _root)
        {
            ERIDataDrivenFileDestination dataDrivenDestination = originDestinationFactory.createPrintMgmtDestination(
                _fileDestination,
                _identification,
                _rootContext,
                _root);

            IFileDestinationHost fileDestinationHost = dataDrivenDestination as IFileDestinationHost;
            if (fileDestinationHost)
            {
                fileDestinationHost.FileDestination = AssetRollForwardDestination::construct(
                    fileDestinationHost.get_FileDestination(),
                    TargetFolder);
            }

            return dataDrivenDestination;
        }

        /// <summary>
        /// Constructs the fixed asset roll forward destination factory.
        /// </summary>
        /// <param name = "_originDestinationFactory">The original destination.</param>
        /// <param name = "_TargetFolder">The string containing a folder name that corresponds to the report, that's being created.</param>
        /// <returns>The destination factory for the fixed asset roll forward report.</returns>
        public static AssetRollForwardDestinationFactory construct(ERIFileDestinationFactory _originDestinationFactory, str _TargetFolder)
        {
            AssetRollForwardDestinationFactory destinationFactory = new AssetRollForwardDestinationFactory(_originDestinationFactory, _TargetFolder);

            ERIFileDestinationFactoryPostProcessorsHost factoryPostProcessing = ERCast::asObject(destinationFactory.originDestinationFactory) as ERIFileDestinationFactoryPostProcessorsHost;

            if (factoryPostProcessing)
            {
                factoryPostProcessing.addDestinationPostProcessor(destinationFactory);
            }
            return destinationFactory;
        }

        public ERIFileDestination processDestinationAfterCreation(ERIFileDestination _sourceDestination)
        {
            return AssetRollForwardDestination::construct(_sourceDestination, TargetFolder);
        }

        protected void new(ERIFileDestinationFactory _originDestinationFactory, str _TargetFolder)
        {
            originDestinationFactory = _originDestinationFactory;
            TargetFolder = _TargetFolder;
        }
    }
    ```

3. Modifique a classe `AssetRollForwardService` existente e escreva o código para configurar um alocador de destino personalizado para o executor de relatórios. Observe que, quando um alocador de destino personalizado é criado, o parâmetro baseado em aplicativo que especifica uma pasta de destino é enviado. Dessa forma, essa pasta de destino é usada para armazenar os arquivos gerados.

    > [!NOTE] 
    > Verifique se a pasta especificada (**c:\\0** neste exemplo) está presente no sistema de arquivos local do servidor que executa o serviço de AOS. Caso contrário, um erro [DirectoryNotFoundException](/dotnet/api/system.io.directorynotfoundexception?view=netcore-3.1) será exibido no runtime.

    ```xpp
    using Microsoft.Dynamics365.LocalizationFramework;
    /// <summary>
    /// The electronic reporting service class for fixed asset roll forward report
    /// </summary>
    class AssetRollForwardService extends SysOperationServiceBase
    {
        public const str ERFormatModelName = 'Fixed assets';
        public const str ERModelDataSourceName = 'model';
        public const str DefaultExportedFileName = 'AssetRollForward';

        /// <summary>
        /// Generates report by general electronic reporting
        /// </summary>
        /// <param name = "_contract">The Asset Period Statement contract</param>
        public void generateReportByGER(AssetRollForwardContract _contract)
        {
            ERFormatMappingId   formatMappingId;
            AssetRollForwardDP  dataProvider;
            AssetRollForwardTmp assetRollForwardTmp;
            Query               query;

            query = new Query(SysOperationHelper::base64Decode(_contract.parmQuery()));
            dataProvider = AssetRollForwardDP::construct();
            formatMappingId = _contract.parmFormatMapping();
            assetRollForwardTmp = dataProvider.getAssetRollForwardTmp(_contract, query);

            if (assetRollForwardTmp)
            {
                try
                {
                    ERIModelDefinitionParamsAction parameters = new ERModelDefinitionParamsUIActionComposite()
                        .add(new ERModelDefinitionDatabaseContext().addTemporaryTable(assetRollForwardTmp))
                        .add(new ERModelDefinitionObjectParameterAction(ERModelDataSourceName, 'MyParameters', _contract, true));

                    // Call ER to generate the report.
                    ERIFormatMappingRun formatMappingRun = ERObjectsFactory::createFormatMappingRunByFormatMappingId(formatMappingId, DefaultExportedFileName);
                    formatMappingRun.withParameter(parameters);
                    formatMappingRun.withFileDestination(_contract.getFileDestination());

                    ERIFileDestinationFactoryHost factoryHost = ERCast::asObject(formatMappingRun) as ERIFileDestinationFactoryHost;
                    if (factoryHost)
                    {
                        ERIFileDestinationFactory fileDestinationFactory = factoryHost.getFileDestinationFactory();
                        factoryHost.setFileDestinationFactory(AssetRollForwardDestinationFactory::construct(fileDestinationFactory, @'c:\0\'));
                        formatMappingRun.run();
                    }
                }
                catch
                {
                    // An error occurred while exporting data.
                    error("@SYP4861341");
                }
            }
            else
            {
                // There is no data available.
                info("@SYS300117");
            }
        }
    }
    ```

4. Reconstrua seu projeto.

## <a name="re-run-the-fixed-asset-roll-forward-report"></a>Gerar novamente o Relatório de roll forward de ativo fixo

1. Acesse **Ativos fixos** \> **Consultas e relatórios** \> **Relatórios de transações** \> **Roll forward de ativo fixo**.
2. No campo **Data inicial**, insira **1/1/2017**.
3. No campo **Data final**, insira **1/31/2017**.
4. No **campo Moeda**, selecione a **Moeda contábil**.
5. No campo **Mapeamento de formato**, selecione **Roll forward de ativo fixo**.
6. Selecione **OK**.
7. Explore a pasta local **C:\\0** para encontrar o mesmo arquivo gerado.

> [!NOTE]
> Como o objeto `originDestination` não é usado no objeto `AssetRollForwardDestination` neste exemplo, as configurações para os [destinos](electronic-reporting-destinations.md) do formato de ER serão ignoradas no runtime.

## <a name="additional-resources"></a>Recursos adicionais

- [Destinos de Relatório eletrônico (ER)](electronic-reporting-destinations.md)
- [Home page da extensibilidade](../extensibility/extensibility-home-page.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]