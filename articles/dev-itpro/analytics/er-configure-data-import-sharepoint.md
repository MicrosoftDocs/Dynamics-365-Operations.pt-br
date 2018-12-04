---
title: "Configurar importação de dados do SharePoint"
description: "Este tópico explica como importar dados do Microsoft SharePoint."
author: NickSelin
manager: AnnBe
ms.date: 05/21/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2018-04-01
ms.dyn365.ops.version: Release 8.0
ms.translationtype: HT
ms.sourcegitcommit: 821d8927211d7ac3e479848c7e7bef9f650d4340
ms.openlocfilehash: 9f23f73e9a98fc50c622255bf6ed027c41ec8010
ms.contentlocale: pt-br
ms.lasthandoff: 08/13/2018

---
# <a name="configure-data-import-from-sharepoint"></a>Configurar importação de dados do SharePoint

[!include[banner](../includes/banner.md)]

Para importar dados de um arquivo de entrada usando a estrutura de relatório eletrônico (ER), é necessário configurar um formato de ER que suporta a importação e, em seguida, executar um mapeamento de modelo para o tipo **Para destino** que usa esse formato como uma origem de dados. Para importar dados, você deve navegar para o arquivo que deseja importar. O arquivo de entrada pode ser selecionado manualmente pelo usuário. Com a nova capacidade de ER de suportar importação de dados do Microsoft SharePoint, este processo pode ser configurado como autônomo. Você pode usar as configurações de ER para executar a importação de dados de arquivos armazenados em pastas do Microsoft SharePoint. Este tópico explica como concluir a importação do SharePoint para Microsoft Dynamics 365 for Finance and Operations. Os exemplos usam transações de fornecedor como dados comerciais.

## <a name="prerequisites"></a>Pré-requisitos
Para concluir os exemplos neste tópico, você deve ter o seguinte acesso:

- Acesso ao Finance and Operations para uma das seguintes funções:

    - Desenvolvedor de relatório eletrônico
    - Consultor funcional de relatório eletrônico
    - Administrador do sistema

- Acesso à instância do Microsoft SharePoint Server configurado para uso com o Finance and Operations
- Configurações de formato e modelo de ER para pagamentos de 1099

### <a name="create-required-er-configurations"></a>Criar configurações de ER necessárias
Executar os guias de tarefa **ER Importar dados de um arquivo do Microsoft Excel**, que fazem parte do processo de negócios **7.5.4.3 Adquirir/Desenvolver componentes de serviço/solução de TI (10677)**. Esses guias de tarefas o orientam no processo de criação e uso de configurações de ER para importar interativamente transações de fornecedores a partir de arquivos externos do Microsoft Excel. Para obter mais informações, consulte [Analisar documentos de entrada no Microsoft Excel](parse-incoming-documents-excel.md). Finalmente, você terá:

- Configurações de ER:

    - Configuração de modelo de ER, **Modelo de pagamento 1099**
    - Configuração de formato de ER, **Formatar para importar transações de fornecedores do Excel**

    [![Configurações de ER para importar dados do SharePoint](./media/GERImportFromSharePoint-01-Configurations.PNG)](./media/GERImportFromSharePoint-01-Configurations.PNG)

- Exemplo de arquivo de entrada para importação de dados:

    - Arquivo Excel **1099import-data.xlsx**, com transações do fornecedor que devem ser importadas para Finance and Operations

    [![Arquivo do Microsoft Excel de amostra para importação do Sharepoint](./media/GERImportFromSharePoint-02-Excel.PNG)](./media/GERImportFromSharePoint-02-Excel.PNG)

> [!NOTE]
> O formato para importar transações do fornecedor é selecionado como o mapeamento de modelo padrão. Portanto, se você executar um mapeamento de modelo do **Modelo de pagamentos 1099** e esse mapeamento de modelo for do tipo **Para destino**, o mapeamento de modelo executa este formato para importar dados dos arquivos externos. Em seguida, usa esses dados para atualizar tabelas do aplicativo.

## <a name="configure-document-management-parameters"></a>Configurar parâmetros de gerenciamento do documento
1. Na página **Parâmetros de gerenciamento de documentos**, configure o acesso à instância do SharePoint Server que será usado pela empresa à qual você está conectado. Neste exemplo, a empresa é USMF.
2. Teste a conexão com a instância do SharePoint Server para certificar-se de que você tem acesso.

    [![Configuração de gerenciamento de documentos - servidor SharePoint](./media/GERImportFromSharePoint-03-SharePointSetup.png)](./media/GERImportFromSharePoint-03-SharePointSetup.png)

3. Abra o site do SharePoint configurado e crie as seguintes pastas onde os arquivos de entrada podem ser estocados:

    - Origem da importação de arquivos (pai)
    - Origem da importação de arquivos (alternativa)

    [![Configuração de gerenciamento de documentos - servidor SharePoint](./media/GERImportFromSharePoint-04-SharePointFolder1.png)](./media/GERImportFromSharePoint-04-SharePointFolder1.png)

    [![Configuração de gerenciamento de documentos - servidor SharePoint](./media/GERImportFromSharePoint-05-SharePointFolder2.png)](./media/GERImportFromSharePoint-05-SharePointFolder2.png)

4. No Finance and Operations, na página **Tipos de documento**, crie os seguintes tipos de documentos que serão usados para acessar as pasta do SharePoint que você acabou de criar:

    - SP principal
    - SP alternativa

5. Para tipos de documento criados, no campo **Grupo**, insira **Arquivo** e no campo **Local**, insira **SharePoint**. Em seguida, insira o endereço da pasta do SharePoint:

    - Do tipo de documento **SP principal**: Origem de importação dos arquivos (principal)
    - Do tipo de documento **SP alternativa**: Origem de importação de arquivos (alternativa)

    [![Definição de SharePoint – novo tipo de documento](./media/GERImportFromSharePoint-06-SharePointDocumentTypesSetup.png)](./media/GERImportFromSharePoint-06-SharePointDocumentTypesSetup.png)

## <a name="configure-er-sources-for-the-er-format"></a>Configurar fontes de ER para o formato de ER
1. Clique em **Administração da organização** \> **Relatório eletrônico** \> **Origem do relatório eletrônico**.
2. Na página **Origem do relatório eletrônico** , configure os arquivos de origem para a importação de dados usando o formato do ER configurado.
3. Defina uma máscara de nome de arquivo, para que somente os arquivos com a extensão .xlsx sejam importados. A máscara do nome de arquivo é opcional e é usada somente quando for definida. Você pode definir somente uma máscara para cada formato de ER.
4. Selecione duas pastas do SharePoint que você criou anteriormente.

    [![Configuração de origem dos arquivos ER](./media/GERImportFromSharePoint-07-FormatSourceSetup.PNG)](./media/GERImportFromSharePoint-07-FormatSourceSetup.PNG)

> [!NOTE]
> - A *origem* do ER é definida para cada empresa do aplicativo individualmente. Por outro lado, as *configurações* do ER são compartilhadas entre as empresas.
> - Quando você exclui uma configuração de origem de ER para um formato de ER, todos os estados de arquivos conectados (veja abaixo) também são excluídos.

## <a name="review-the-files-states-for-the-er-format"></a>Examinar os estados dos arquivos para o formato de ER
1. Na página **Origem do relatório eletrônico** , selecione **Estados dos arquivos das origens** para examinar o conteúdo de origens do arquivo configurado para o formato de ER atual.
2. Na seção **Arquivos** , examine a lista de arquivos. Esta lista apresentará o seguinte:

    - Arquivos de origem que são aplicáveis, com base na máscara de nome de arquivo (se uma máscara de nome de arquivo for definida) e que estão prontas para a importação de dados. Para esses arquivos, a seção **Logs de origem do formato de importação** estará vazia.
    - Arquivos importados anteriormente. Para cada um desses arquivos, na seção **Logs de origem do formato de importação** , você pode revisar o histórico de importação deste arquivo.

Você também pode abrir a página **Estados dos arquivos das origens** selecionando **Administração da organização** \> **Relatório eletrônico** \> **Estados dos arquivos das origens**. Nesse caso, a página fornece informações sobre fontes de arquivo para todos os formatos de ER nos quais as origens do arquivo foram configuradas na empresa na qual você está conectado.

## <a name="import-data-from-excel-files-that-are-in-a-sharepoint-folder"></a>Importar dados dos arquivos do Excel que estão na pasta do SharePoint
1. No SharePoint, carregue o arquivo do Microsoft Excel **1099import-data.xlsx** que contém transações do fornecedor para a pasta do Sharepoint **Origem de importação dos arquivos (principal)** que você criou anteriormente.

    [![Conteúdo do SharePoint – arquivo do Microsoft Excel para importação](./media/GERImportFromSharePoint-08-UploadFile.png)](./media/GERImportFromSharePoint-08-UploadFile.png)

2. No Finance and Operations, na página **Estados dos arquivos das origens**, selecione **Atualizar** para atualizar a página. Observe que o arquivo Excel que foi carregado para o SharePoint apareceu neste formulário com o status **Pronto**. Os seguintes status são suportados atualmente:

    - **Pronto** – Atribuído automaticamente para cada novo arquivo em uma pasta do SharePoint. Este status indica que o arquivo está pronto para a importação.
    - **Importando** – Atribuído automaticamente para um relatório de ER quando o arquivo for bloqueado pelo processo de importação para impedir seu uso por outros processos (se vários deles forem executados simultaneamente.)
    - **Importado** – atribuído automaticamente por um relatório de ER quando a importação do arquivo for concluída com sucesso. Este status indica que o arquivo importado foi excluído da origem de arquivos configurados (pasta do SharePoint).
    - **Com falha** – atribuído automaticamente por um relatório de ER quando a importação do arquivo for concluída com sucesso com erros ou exceções.
    - **Em espera** – Atribuído manualmente pelo usuário neste formulário. Este status indica que o arquivo não será importado por enquanto. Este status pode ser usado para adiar a importação de alguns arquivos.

    [![Página dos estados do arquivo de ER para as origens selecionadas](./media/GERImportFromSharePoint-09-FileStatesForm.png)](./media/GERImportFromSharePoint-09-FileStatesForm.png)

## <a name="import-data-from-sharepoint-files"></a>Importar dados de arquivos do SharePoint
1. Abra a árvore das configurações de ER, selecione **Modelo de pagamento 1099** e expanda a lista de componentes do modelo de ER.
2. Selecione o nome do mapeamento do modelo para abrir a lista de mapeamentos do modelo da configuração do modelo de ER selecionada.

    [![Página dos estados do arquivo de ER para as origens selecionadas](./media/GERImportFromSharePoint-10-SelectModelMapping.PNG)](./media/GERImportFromSharePoint-10-SelectModelMapping.PNG)

3. Selecione **Executar** para executar o mapeamento de modelo selecionado. Como você configurou as origens do arquivo configurado para o formato de ER, você poderá alterar a configuração da opção **Origem de Arquivo**, conforme necessário. Se você mantiver a configuração desta opção, os arquivos .xslx são importados das origens configuradas (as pastas do Sharepoint, neste exemplo).

    Neste exemplo, você está importando somente um arquivo. Porém, se houver vários arquivos, eles serão selecionados para importação na ordem em que foram adicionados à pasta do SharePoint. Cada execução de um formato de ER importa um único arquivo selecionado.

    [![Executar mapeamento de modelo de ER](./media/GERImportFromSharePoint-11-RunModelMapping.PNG)](./media/GERImportFromSharePoint-11-RunModelMapping.PNG)

4. O mapeamento do modelo pode ser executado no modo automático no lote. Nesse caso, sempre que um lote executar esse formato de ER, um arquivo único é importado de origens do arquivo configurado. Use o código a seguir para implementar esta execução de lote.

    ```
    ERObjectsFactory::createMappingDestinationRunByImportFormatMappingId().run()
    ```

    Quando um arquivo é importado com êxito da pasta do SharePoint, ele é excluído dessa pasta.

5. Insira a ID de comprovante, como **V-00001** e depois selecione **OK**.

    [![Executar mapeamento de modelo de ER](./media/GERImportFromSharePoint-12-ModelMappingRunFinished.PNG)](./media/GERImportFromSharePoint-12-ModelMappingRunFinished.PNG)

6. Na página **Estados dos arquivos das origens**, selecione **Atualizar** para atualizar a página.

    [![Página dos estados do arquivo de ER para as origens selecionadas](./media/GERImportFromSharePoint-13-FileStatesForm.PNG)](./media/GERImportFromSharePoint-13-FileStatesForm.PNG)

7. Na seção **Arquivos** , examine a lista de arquivos. A seção **Logs de origem do formato de importação** fornece o histórico de importação de arquivo Excel. Como esse arquivo foi importado com êxito, ele é marcado como **Excluído** na pasta do SharePoint.
8. Revise a pasta do SharePoint **Origem da importação de arquivos (pai)**. Os arquivos do Excel que foram importados com sucesso foram excluídos desta pasta.
9. No Finance and Operations, selecione **Contas a pagar** \> **Tarefas periódicas** \> **Imposto 1099** \> **Liquidação de fornecedor para impostos 1099**.
10. Nos campos **De** e **Até**, informe os valores apropriados. Em seguida, selecione **Transações 1099 manuais**.

    As transações do fornecedor que foram importadas dos arquivos do Excel no SharePoint para o comprovante **V-00001**, são apresentadas na página.

    [![Página transações do fornecedor 1099](./media/GERImportFromSharePoint-14-ImportedTransactions.PNG)](./media/GERImportFromSharePoint-14-ImportedTransactions.PNG)

## <a name="prepare-an-excel-file-for-import"></a>Preparar um arquivo do Excel para importação
1. Abra o arquivo do Excel usado anteriormente. Na linha 3, coluna 1 adicione um código do fornecedor que não existe no aplicativo. Inclua informações adicionais falsas de fornecedor na linha.

    [![Arquivo do Microsoft Excel de amostra para importação do Sharepoint](./media/GERImportFromSharePoint-15-Excel.PNG)](./media/GERImportFromSharePoint-15-Excel.PNG)

2. Carregue o arquivo do Excel atualizado que contém as transações dos fornecedores para a pasta do SharePoint **Origem da importação de arquivos (pai)**.
3. No Finance and Operations, abra a árvore de configurações de ER, selecione o **Modelo de pagamento 1099** e expanda a lista de componentes do modelo de ER.
4. Selecione o nome do mapeamento de modelo para atualizar o mapeamento de modelo, de forma que o código incorreto do fornecedor seja considerado um erro durante o processo de importação de dados.
5. Selecione **Designer**.
6. Na guia **Validações** , você deverá alterar a ação de pós-validação para a regra de validação que foi configurada para avaliar se a conta de fornecedor importada existe no aplicativo. Atualize o valor do campo **Ação pós-validação** para **Parar execução**, salve suas alterações e feche a página.

    [![ER Página designer de mapeamento do modelo](./media/GERImportFromSharePoint-16-UpdateModelMapping.PNG)](./media/GERImportFromSharePoint-16-UpdateModelMapping.PNG)

7. Salvar suas alterações e feche o designer de mapeamento de modelo do ER.
8. Selecione **Executar** para executar o mapeamento de modelo de ER modificado.
9. Insira a ID de comprovante, como **V-00002** e depois selecione **OK**.

    Observe que o log de informações contém a notificação informando que residindo no arquivo da pasta do Sharepoint contém conta de fornecedor incorreta e não pode ser importada.

    [![Executar mapeamento de modelo de ER](./media/GERImportFromSharePoint-17-ModelMappingRunFinished.PNG)](./media/GERImportFromSharePoint-17-ModelMappingRunFinished.PNG)

10. Na página **Estados dos arquivos das origens**, selecione **Atualizar** e, em seguida, na seção **Arquivos**, revise a lista de arquivos.

    [![Página dos estados do arquivo de ER para as origens selecionadas](./media/GERImportFromSharePoint-18-FileStatesForm.PNG)](./media/GERImportFromSharePoint-18-FileStatesForm.PNG)

    A seção **Logs de origem do formato de importação** indica que o processo de importação falhou e que o arquivo ainda está na pasta do SharePoint (a caixa de seleção **Excluído** não foi selecionada). Se você corrigir este arquivo no SharePoint adicionando o código do fornecedor adequado e, em seguida, alterar o status do arquivo de **Com Falha** para **Pronto** na seção **Logs de origem do formato de importação**, você pode importar o arquivo novamente.

11. Revise a pasta do SharePoint **Origem da importação de arquivos (pai)**. Observe que o arquivo do Excel que não foi importado ainda está nesta pasta.
12. Em Finance and Operations, selecione **Contas a pagar** \> **Tarefas periódicas** \> **Imposto 1099** \> **Liquidação de fornecedor para impostos 1099**, insira os valores apropriados nos campos **De** e **Até** e selecione **Transações 1099 manuais**.

    Somente as transações para o comprovante V-00001 estão disponíveis. Nenhuma transação para o comprovante V-00002 estará disponível, mesmo que o erro da última transação importada seja encontrado no arquivo do Excel.

