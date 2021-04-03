---
title: Especificar locais de armazenamento personalizado para os documentos gerados
description: Este tópico explica como estender a lista de locais de armazenamento para documentos gerados pelos formatos de Relatório eletrônico (ER).
author: NickSelin
manager: AnnBe
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
ms.openlocfilehash: 146e7fb5fefbecabc99c2978b52eb0e782da0322
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5562205"
---
# <a name="specify-custom-storage-locations-for-generated-documents"></a><span data-ttu-id="cb9be-103">Especificar locais de armazenamento personalizado para os documentos gerados</span><span class="sxs-lookup"><span data-stu-id="cb9be-103">Specify custom storage locations for generated documents</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="cb9be-104">A interface de programação de aplicativos (API) da estrutura de relatórios eletrônicos (ER) permite estender a lista de locais de armazenamento para documentos gerados pelos formatos ER.</span><span class="sxs-lookup"><span data-stu-id="cb9be-104">The application programming interface (API) of the Electronic reporting (ER) framework lets you extend the list of storage locations for documents that ER formats generate.</span></span> <span data-ttu-id="cb9be-105">Este tópico explica como adicionar um local de armazenamento personalizado para documentos gerados delegando a tarefa de criar destinos de ER ao alocador de destino padrão e, em seguida, implementando uma classe personalizada que tem sua própria lógica de destino.</span><span class="sxs-lookup"><span data-stu-id="cb9be-105">This topic explains how to add a custom storage location for generated documents by delegating the task of creating ER destinations to the default destination factory and then implementing a custom class that has its own destination logic.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="cb9be-106">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="cb9be-106">Prerequisites</span></span>

<span data-ttu-id="cb9be-107">Implante uma topologia que dê suporte à compilação contínua.</span><span class="sxs-lookup"><span data-stu-id="cb9be-107">Deploy a topology that supports continuous build.</span></span> <span data-ttu-id="cb9be-108">Para obter mais informações, consulte [Implantar topologias que dão suporte à contínua automação de compilações e testes](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/perf-test/continuous-build-test-automation).</span><span class="sxs-lookup"><span data-stu-id="cb9be-108">For more information, see [Deploy topologies that support continuous build and test automation](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/perf-test/continuous-build-test-automation).</span></span> <span data-ttu-id="cb9be-109">Você também deve ter acesso a essa topologia para uma das seguintes funções:</span><span class="sxs-lookup"><span data-stu-id="cb9be-109">You must have access to this topology for one of the following roles:</span></span>

- <span data-ttu-id="cb9be-110">Desenvolvedor de relatório eletrônico</span><span class="sxs-lookup"><span data-stu-id="cb9be-110">Electronic reporting developer</span></span>
- <span data-ttu-id="cb9be-111">Consultor funcional de relatório eletrônico</span><span class="sxs-lookup"><span data-stu-id="cb9be-111">Electronic reporting functional consultant</span></span>
- <span data-ttu-id="cb9be-112">Administrador do sistema</span><span class="sxs-lookup"><span data-stu-id="cb9be-112">System administrator</span></span>

<span data-ttu-id="cb9be-113">Você também deve ter acesso ao ambiente de desenvolvimento para essa topologia.</span><span class="sxs-lookup"><span data-stu-id="cb9be-113">You must also have access to the development environment for this topology.</span></span>

<span data-ttu-id="cb9be-114">Todas as tarefas deste tópico podem ser concluídas na empresa **USMF**.</span><span class="sxs-lookup"><span data-stu-id="cb9be-114">All the tasks in this topic can be completed in the **USMF** company.</span></span>

## <a name="import-the-fixed-asset-roll-forward-er-format"></a><span data-ttu-id="cb9be-115">Importar o formato de ER de roll forward de ativo fixo</span><span class="sxs-lookup"><span data-stu-id="cb9be-115">Import the Fixed asset roll forward ER format</span></span>

<span data-ttu-id="cb9be-116">Para gerar os documentos aos quais você quer adicionar um local de armazenamento personalizado, [importe](er-download-configurations-global-repo.md) a **configuração do formato de ER de roll forward de ativo fixo** para a topologia atual.</span><span class="sxs-lookup"><span data-stu-id="cb9be-116">To generate the documents that you plan to add a custom storage location for, [import](er-download-configurations-global-repo.md) the **Fixed asset roll forward** ER format configuration into the current topology.</span></span>

![Página do repositório de configuração](./media/er-custom-storage-generated-files-import-format.png)

## <a name="run-the-fixed-asset-roll-forward-report"></a><span data-ttu-id="cb9be-118">Gerar o Relatório de roll forward de ativo fixo</span><span class="sxs-lookup"><span data-stu-id="cb9be-118">Run the Fixed asset roll forward report</span></span>

1. <span data-ttu-id="cb9be-119">Vá para **Ativos fixos** \> **Consultas e relatórios** \> **Relatórios de transações** \> **Roll forward de ativo fixo**.</span><span class="sxs-lookup"><span data-stu-id="cb9be-119">Go to **Fixed assets** \> **Inquiries and reports** \> **Transaction reports** \> **Fixed asset roll forward**.</span></span>
2. <span data-ttu-id="cb9be-120">No campo **Data inicial**, insira **1/1/2017** (1º de janeiro de 2017).</span><span class="sxs-lookup"><span data-stu-id="cb9be-120">In the **From date** field, enter **1/1/2017** (January 1, 2017).</span></span>
3. <span data-ttu-id="cb9be-121">No campo **Data final**, insira **1/31/2017** (31 de janeiro de 2017).</span><span class="sxs-lookup"><span data-stu-id="cb9be-121">In the **To date** field, enter **1/31/2017** (January 31, 2017).</span></span>
4. <span data-ttu-id="cb9be-122">No **campo Moeda**, selecione a **Moeda contábil**.</span><span class="sxs-lookup"><span data-stu-id="cb9be-122">In the **Currency field**, select **Accounting currency**.</span></span>
5. <span data-ttu-id="cb9be-123">No campo **Mapeamento de formato**, selecione **Roll forward de ativo fixo**.</span><span class="sxs-lookup"><span data-stu-id="cb9be-123">In the **Format mapping** field, select **Fixed asset roll forward**.</span></span>
6. <span data-ttu-id="cb9be-124">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="cb9be-124">Select **OK**.</span></span>

![Caixa de diálogo de runtime do Relatório de roll forward de ativo fixo](./media/er-custom-storage-generated-files-runtime-dialog.png)

<span data-ttu-id="cb9be-126">Em Microsoft Excel, revise o documento de saída gerado disponível para download.</span><span class="sxs-lookup"><span data-stu-id="cb9be-126">In Microsoft Excel, review the outbound document that is generated and available for download.</span></span> <span data-ttu-id="cb9be-127">Esse comportamento é o [comportamento padrão ](electronic-reporting-destinations.md#default-behavior)para um formato de ER em que nenhum [destino](electronic-reporting-destinations.md) está configurado e que está sendo executado no modo interativo.</span><span class="sxs-lookup"><span data-stu-id="cb9be-127">This behavior is the [default behavior](electronic-reporting-destinations.md#default-behavior) for an ER format that no [destinations](electronic-reporting-destinations.md) are configured for, and that is running in interactive mode.</span></span>

## <a name="review-the-source-code"></a><span data-ttu-id="cb9be-128">Revisar o código-fonte</span><span class="sxs-lookup"><span data-stu-id="cb9be-128">Review the source code</span></span>

<span data-ttu-id="cb9be-129">Revise o código do método `generateReportByGER()` da classe `AssetRollForwardService`.</span><span class="sxs-lookup"><span data-stu-id="cb9be-129">Review the code of the `generateReportByGER()` method of the `AssetRollForwardService` class.</span></span> <span data-ttu-id="cb9be-130">Observe que o método `Run()` é usado para chamar a estrutura de ER e gerar o **Relatório de roll forward de ativo fixo**.</span><span class="sxs-lookup"><span data-stu-id="cb9be-130">Notice that the `Run()` method is used to call the ER framework and generate the **Fixed asset roll forward** report.</span></span>

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

## <a name="modify-the-source-code"></a><span data-ttu-id="cb9be-131">Modificar o código-fonte</span><span class="sxs-lookup"><span data-stu-id="cb9be-131">Modify the source code</span></span>

1. <span data-ttu-id="cb9be-132">No seu projeto Visual Studio, adicione uma nova classe (`AssetRollForwardDestination` neste exemplo) e escreva o código para implementar seu destino personalizado para os **Relatórios de roll forward de ativo fixo** gerados.</span><span class="sxs-lookup"><span data-stu-id="cb9be-132">In your Visual Studio project, add a new class (`AssetRollForwardDestination` in this example), and write code to implement your custom destination for **Fixed asset roll forward** reports that are generated.</span></span>

    - <span data-ttu-id="cb9be-133">O método `new()` foi projetado para obter o objeto de destino de ER original e o parâmetro baseado na lógica do aplicativo que especifica o local personalizado onde os relatórios gerados devem ser armazenados.</span><span class="sxs-lookup"><span data-stu-id="cb9be-133">The `new()` method is designed to get the original ER destination object and the application logic–driven parameter that specifies the custom location where generated reports should be stored.</span></span> <span data-ttu-id="cb9be-134">Neste exemplo, o local personalizado é o nome de uma pasta do sistema de arquivos local do servidor que executa o serviço de AOS (Servidor de Objetos de Aplicativo).</span><span class="sxs-lookup"><span data-stu-id="cb9be-134">In this example, the custom location is the name of a folder of the local file system of the server that runs the Application Object Server (AOS) service.</span></span>
    - <span data-ttu-id="cb9be-135">O método `saveFile()` foi projetado para salvar um documento gerado em uma pasta do sistema de arquivos local do servidor que executa o serviço de AOS.</span><span class="sxs-lookup"><span data-stu-id="cb9be-135">The `saveFile()` method is designed to save a generated document to a folder of the local file system of the server that runs the AOS service.</span></span>

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

2. <span data-ttu-id="cb9be-136">No seu projeto Visual Studio, adicione uma nova classe (`AssetRollForwardDestinationFactory` no exemplo) e escreva o código para configurar um alocador de destino personalizado que delega a criação de um destino ao alocador padrão e para empacotar um destino de arquivo com seu próprio destino.</span><span class="sxs-lookup"><span data-stu-id="cb9be-136">In your Visual Studio project, add a new class (`AssetRollForwardDestinationFactory` in this example), and write code to set up a custom destination factory that delegates the creation of a destination to the default destination factory, and to wrap a file destination with your own destination.</span></span>

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

3. <span data-ttu-id="cb9be-137">Modifique a classe `AssetRollForwardService` existente e escreva o código para configurar um alocador de destino personalizado para o executor de relatórios.</span><span class="sxs-lookup"><span data-stu-id="cb9be-137">Modify the existing `AssetRollForwardService` class, and write code to set up a custom destination factory for the report runner.</span></span> <span data-ttu-id="cb9be-138">Observe que, quando um alocador de destino personalizado é criado, o parâmetro baseado em aplicativo que especifica uma pasta de destino é enviado.</span><span class="sxs-lookup"><span data-stu-id="cb9be-138">Notice that when a custom destination factory is constructed, the application-driven parameter that specifies a target folder is passed.</span></span> <span data-ttu-id="cb9be-139">Dessa forma, essa pasta de destino é usada para armazenar os arquivos gerados.</span><span class="sxs-lookup"><span data-stu-id="cb9be-139">In this way, that target folder is used to store generated files.</span></span>

    > [!NOTE] 
    > <span data-ttu-id="cb9be-140">Verifique se a pasta especificada (**c:\\0** neste exemplo) está presente no sistema de arquivos local do servidor que executa o serviço de AOS.</span><span class="sxs-lookup"><span data-stu-id="cb9be-140">Make sure that the specified folder (**c:\\0** in this example) is present in the local file system of the server that runs the AOS service.</span></span> <span data-ttu-id="cb9be-141">Caso contrário, um erro [DirectoryNotFoundException](https://docs.microsoft.com/dotnet/api/system.io.directorynotfoundexception?view=netcore-3.1) será exibido no runtime.</span><span class="sxs-lookup"><span data-stu-id="cb9be-141">Otherwise, a [DirectoryNotFoundException](https://docs.microsoft.com/dotnet/api/system.io.directorynotfoundexception?view=netcore-3.1) exception will be thrown at runtime.</span></span>

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

4. <span data-ttu-id="cb9be-142">Reconstrua seu projeto.</span><span class="sxs-lookup"><span data-stu-id="cb9be-142">Rebuild your project.</span></span>

## <a name="re-run-the-fixed-asset-roll-forward-report"></a><span data-ttu-id="cb9be-143">Gerar novamente o Relatório de roll forward de ativo fixo</span><span class="sxs-lookup"><span data-stu-id="cb9be-143">Re-run the Fixed asset roll forward report</span></span>

1. <span data-ttu-id="cb9be-144">Vá para **Ativos fixos** \> **Consultas e relatórios** \> **Relatórios de transações** \> **Roll forward de ativo fixo**.</span><span class="sxs-lookup"><span data-stu-id="cb9be-144">Go to **Fixed assets** \> **Inquiries and reports** \> **Transaction reports** \> **Fixed asset roll forward**.</span></span>
2. <span data-ttu-id="cb9be-145">No campo **Data inicial**, insira **1/1/2017**.</span><span class="sxs-lookup"><span data-stu-id="cb9be-145">In the **From date** field, enter **1/1/2017**.</span></span>
3. <span data-ttu-id="cb9be-146">No campo **Data final**, insira **1/31/2017**.</span><span class="sxs-lookup"><span data-stu-id="cb9be-146">In the **To date** field, enter **1/31/2017**.</span></span>
4. <span data-ttu-id="cb9be-147">No **campo Moeda**, selecione a **Moeda contábil**.</span><span class="sxs-lookup"><span data-stu-id="cb9be-147">In the **Currency field**, select **Accounting currency**.</span></span>
5. <span data-ttu-id="cb9be-148">No campo **Mapeamento de formato**, selecione **Roll forward de ativo fixo**.</span><span class="sxs-lookup"><span data-stu-id="cb9be-148">In the **Format mapping** field, select **Fixed asset roll forward**.</span></span>
6. <span data-ttu-id="cb9be-149">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="cb9be-149">Select **OK**.</span></span>
7. <span data-ttu-id="cb9be-150">Explore a pasta local **C:\\0** para encontrar o mesmo arquivo gerado.</span><span class="sxs-lookup"><span data-stu-id="cb9be-150">Browse the local **C:\\0** folder to find the generated file.</span></span>

> [!NOTE]
> <span data-ttu-id="cb9be-151">Como o objeto `originDestination` não é usado no objeto `AssetRollForwardDestination` neste exemplo, as configurações para os [destinos](electronic-reporting-destinations.md) do formato de ER serão ignoradas no runtime.</span><span class="sxs-lookup"><span data-stu-id="cb9be-151">Because the `originDestination` object isn't used in the `AssetRollForwardDestination` object in this example, the configurations for the ER format [destinations](electronic-reporting-destinations.md) will be ignored at runtime.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="cb9be-152">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="cb9be-152">Additional resources</span></span>

- [<span data-ttu-id="cb9be-153">Destinos de Relatório eletrônico (ER)</span><span class="sxs-lookup"><span data-stu-id="cb9be-153">Electronic reporting (ER) destinations</span></span>](electronic-reporting-destinations.md)
- [<span data-ttu-id="cb9be-154">Home page da extensibilidade</span><span class="sxs-lookup"><span data-stu-id="cb9be-154">Extensibility home page</span></span>](../extensibility/extensibility-home-page.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]