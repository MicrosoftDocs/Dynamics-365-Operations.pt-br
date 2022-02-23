---
title: Configurar a importação de dados do SharePoint
description: Este tópico explica como importar dados do Microsoft SharePoint.
author: NickSelin
manager: AnnBe
ms.date: 11/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2018-04-01
ms.dyn365.ops.version: Release 8.0
ms.openlocfilehash: 1f7754a3e69238ab1760b3f7eb8f5e2c792b451b
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4680893"
---
# <a name="configure-data-import-from-sharepoint"></a>Configurar a importação de dados do SharePoint

[!include[banner](../includes/banner.md)]

Para importar dados de um arquivo de entrada usando a estrutura de relatório eletrônico (ER), é necessário configurar um formato de ER que suporta a importação e, em seguida, executar um mapeamento de modelo para o tipo **Para destino** que usa esse formato como uma origem de dados. Para importar dados, você deve navegar para o arquivo que deseja importar. O arquivo de entrada pode ser selecionado manualmente pelo usuário. Com a nova capacidade de ER de dar suporte à importação de dados do Microsoft SharePoint, este processo pode ser configurado como autônomo. Você pode usar as configurações de ER para executar a importação de dados de arquivos armazenados em pastas do Microsoft SharePoint. Este tópico explica como executar a importação do SharePoint. Os exemplos usam transações de fornecedor como dados comerciais.

## <a name="prerequisites"></a>Pré-requisitos
Para concluir os exemplos neste tópico, você deve ter o seguinte acesso:

- Acesso a uma das seguintes funções:

    - Desenvolvedor de relatório eletrônico
    - Consultor funcional de relatório eletrônico
    - Administrador do sistema

- Acesso à instância do Microsoft SharePoint Server configurado para uso com o aplicativo.
- Configurações de formato e modelo de ER para pagamentos de 1099.

### <a name="create-required-er-configurations"></a>Criar configurações de ER necessárias
Executar os guias de tarefas **ER Importar dados de um arquivo do Microsoft Excel**, que fazem parte do processo de negócios **7.5.4.3 Adquirir/Desenvolver componentes de serviço/solução de TI (10677)**. Esses guias de tarefas contêm orientações para o processo de criação e uso de configurações de ER para importar transações de fornecedores de maneira interativa a partir de arquivos do Microsoft Excel. Para obter mais informações, consulte [Analisar documentos de entrada no formato do Excel](parse-incoming-documents-excel.md). Depois de concluir as guias da tarefa, você terá a configuração a seguir.

#### <a name="er-configurations"></a>Configurações de ER

- Configuração de modelo de ER, **Modelo de pagamento 1099**
- Configuração de formato de ER, **Formatar para importar transações de fornecedores do Excel**

![Configurações de ER para importar dados do SharePoint](./media/GERImportFromSharePoint-01-Configurations.PNG)

#### <a name="sample-of-the-incoming-file-for-data-import"></a>Amostra do arquivo de entrada para importação de dados

- Arquivo do Excel **1099import-data.xlsx** com as transações do fornecedor que devem ser importadas.

![Arquivo do Excel de amostra para importar de SharePoint](./media/GERImportFromSharePoint-02-Excel.PNG)
    
> [!NOTE]
> O formato para importar transações do fornecedor é selecionado como o mapeamento de modelo padrão. Portanto, se você executar um mapeamento de modelo do **Modelo de pagamentos 1099** e esse mapeamento de modelo for do tipo **Para destino**, o mapeamento de modelo executa este formato para importar dados dos arquivos externos. Em seguida, usa esses dados para atualizar tabelas do aplicativo.

## <a name="configure-access-to-sharepoint-for-file-storage"></a>Configurar o acesso ao SharePoint para armazenamento de arquivos
Para armazenar arquivos de relatórios eletrônicos em um local do SharePoint, você deve configurar o acesso à instância do SharePoint Server que será usada pela empresa atual. Neste exemplo, a empresa é USMF. Para obter instruções, consulte [Configurar armazenamento do SharePoint](../../fin-ops/organization-administration/configure-document-management.md#configure-sharepoint-storage).

1. Execute as etapas em [Configurar armazenamento do SharePoint](../../fin-ops/organization-administration/configure-document-management.md#configure-sharepoint-storage).
2. Abra o site configurado do SharePoint.
3. Criar estas pastas onde os arquivos de relatórios eletrônicos de entrada possam ser armazenados:

     - Origem da importação de arquivos (principal) (exemplo mostrado na captura de tela a seguir)
     - Origem da importação de arquivos (alternativa)

    ![Origem da importação de arquivos (pai)](./media/GERImportFromSharePoint-04-SharePointFolder1.png)

4. (Opcional) Criar estas pastas onde os arquivos possam ser armazenados após a importação: 

    - Pasta do arquivo morto de arquivos - esta pasta seria para arquivos importados com êxito.
    - Pasta de avisos de arquivos - essa pasta seria para os arquivos que foram importados com um aviso.
    - Pasta de arquivos com erros - esta pasta seria para os arquivos que não foram importados.

4. Vá para **Administração da organização > Gerenciamento de documentos > Tipos de documento**.
5. Crie os tipos de documento a seguir que serão usados para acessar as pastas do SharePoint recém-criadas. Para obter instruções, consulte [Configurar tipos de documento](../../fin-ops/organization-administration/configure-document-management.md#configure-document-types).

|Tipo de documento       | Agrupar              | Localização      | Pasta do SharePoint      |
|--------------------|--------------------|---------------|------------------------|
|SP principal             |Arquivo                |SharePoint     |Origem da importação de arquivos (pai)|
|SP alternativa             |Arquivo                |SharePoint     |Origem da importação de arquivos (alternativa)|
|Arquivo morto de SP             |Arquivo                |SharePoint     |Pasta do arquivo morto de arquivos|
|Aviso do SP             |Arquivo                |SharePoint     |Pasta de avisos de arquivos|
|Erro do SP             |Arquivo                |SharePoint     |Pasta de arquivos com erros|

![Configuração do SharePoint – novo tipo de documento](./media/GERImportFromSharePoint-06-SharePointDocumentTypesSetup.png)

## <a name="configure-er-sources-for-the-er-format"></a>Configurar fontes de ER para o formato de ER
1. Clique em **Administração da organização** \> **Relatório eletrônico** \> **Origem do relatório eletrônico**.
2. Na página **Origem do relatório eletrônico** , configure os arquivos de origem para a importação de dados usando o formato do ER configurado.
3. Defina uma máscara de nome de arquivo, para que somente os arquivos com a extensão .xlsx sejam importados. A máscara do nome de arquivo é opcional e é usada somente quando for definida. Você pode definir somente uma máscara para cada formato de ER.
4. Altere **Classificar arquivos antes de importar** para **Não classificar** se houver muitos arquivos para importação e a ordem de importação não for importante
5. Selecione todas as pastas do SharePoint que você criou anteriormente.

    [![Configuração de origem dos arquivos ER](./media/GERImportFromSharePoint-07-FormatSourceSetup.PNG)](./media/GERImportFromSharePoint-07-FormatSourceSetup.PNG)

> [!NOTE]
> - A *origem* do ER é definida para cada empresa do aplicativo individualmente. Por outro lado, as *configurações* do ER são compartilhadas entre as empresas.
> - Quando você exclui uma configuração de origem de ER para um formato de ER, todos os estados de arquivos conectados (veja abaixo) também são excluídos por confirmação.

## <a name="review-the-files-states-for-the-er-format"></a>Examinar os estados dos arquivos para o formato de ER
1. Na página **Origem do relatório eletrônico** , selecione **Estados dos arquivos das origens** para examinar o conteúdo de origens do arquivo configurado para o formato de ER atual.
2. Na seção **Arquivos** , examine a lista de arquivos. Esta lista apresentará o seguinte:

    - Arquivos de origem que são aplicáveis, com base na máscara de nome de arquivo (se uma máscara de nome de arquivo for definida) e que estão prontas para a importação de dados. Para esses arquivos, a seção **Logs de origem do formato de importação** estará vazia.
    - Arquivos importados anteriormente. Para cada um desses arquivos, na seção **Logs de origem do formato de importação** , você pode revisar o histórico de importação deste arquivo.

Você também pode abrir a página **Estados dos arquivos das origens** selecionando **Administração da organização** \> **Relatório eletrônico** \> **Estados dos arquivos das origens**. Nesse caso, a página fornece informações sobre fontes de arquivo para todos os formatos de ER nos quais as origens do arquivo foram configuradas na empresa na qual você está conectado.

## <a name="import-data-from-excel-files-that-are-in-a-sharepoint-folder"></a>Importar dados de arquivos do Excel que estão em uma pasta do SharePoint
1. No SharePoint, carregue o arquivo do Microsoft Excel **1099import-data.xlsx** que contém transações do fornecedor para a pasta do SharePoint **Origem de importação dos arquivos (principal)** criada anteriormente.

    [![Conteúdo do SharePoint – arquivo do Microsoft Excel para importação](./media/GERImportFromSharePoint-08-UploadFile.png)](./media/GERImportFromSharePoint-08-UploadFile.png)

2. Na página **Estados dos arquivos das origens**, selecione **Atualizar** para atualizar a página. O arquivo do Excel que foi carregado no SharePoint apareceu nesta página com o status **Pronto**. Os seguintes status são suportados atualmente:

    - **Pronto** – atribuído automaticamente para cada novo arquivo em uma pasta do SharePoint. Este status indica que o arquivo está pronto para a importação.
    - **Importando** – Atribuído automaticamente para um relatório de ER quando o arquivo for bloqueado pelo processo de importação para impedir seu uso por outros processos (se vários deles forem executados simultaneamente.)
    - **Importado** – atribuído automaticamente por um relatório de ER quando a importação do arquivo for concluída com sucesso. Este status indica que o arquivo importado foi excluído da origem de arquivos configurada (pasta do SharePoint).
    - **Com falha** – atribuído automaticamente por um relatório de ER quando a importação do arquivo for concluída com sucesso com erros ou exceções.
    - **Em espera** – Atribuído manualmente pelo usuário nesta página. Este status indica que o arquivo não será importado por enquanto. Este status pode ser usado para adiar a importação de alguns arquivos.

    [![Página dos estados do arquivo de ER atualizados para as fontes selecionadas](./media/GERImportFromSharePoint-09-FileStatesForm.png)](./media/GERImportFromSharePoint-09-FileStatesForm.png)

## <a name="import-data-from-sharepoint-files"></a>Importar dados de arquivos do SharePoint
1. Abra a árvore das configurações de ER, selecione **Modelo de pagamento 1099** e expanda a lista de componentes do modelo de ER.
2. Selecione o nome do mapeamento do modelo para abrir a lista de mapeamentos do modelo da configuração do modelo de ER selecionada.

    [![Página Configuração](./media/GERImportFromSharePoint-10-SelectModelMapping.PNG)](./media/GERImportFromSharePoint-10-SelectModelMapping.PNG)

3. Selecione **Executar** para executar o mapeamento de modelo selecionado. Como você configurou as origens no formato ER, poderá alterar a configuração da opção **Origem do arquivo** se necessário. Se você mantém a configuração desta opção, os arquivos .xslx são importados das origens configuradas (as pastas do SharePoint, neste exemplo).

    Neste exemplo, você está importando somente um arquivo. Porém, se houver vários arquivos, eles serão selecionados para importação na ordem em que foram adicionados à pasta do SharePoint. Cada execução de um formato de ER importa um único arquivo selecionado.

    [![Importar de SharePoint e executar o mapeamento de modelo de ER](./media/GERImportFromSharePoint-11-RunModelMapping.PNG)](./media/GERImportFromSharePoint-11-RunModelMapping.PNG)

4. O mapeamento do modelo pode ser executado [no modo autônomo](#limitations) em lote. Nesse caso, sempre que um lote executar esse formato de ER, um arquivo único é importado de origens do arquivo configurado.

    Quando um arquivo é importado com êxito da pasta do SharePoint, ele é excluído dessa pasta e movido para uma pasta de arquivos importados com êxito ou para a pasta de arquivos importados com avisos. Caso contrário, ele será movido para a pasta de arquivos com falhas ou ficará nessa pasta se a pasta de arquivos com falhas não estiver configurada. 

5. Insira a ID de comprovante, como **V-00001** e depois selecione **OK**.

    [![Executar mapeamento de modelo de ER](./media/GERImportFromSharePoint-12-ModelMappingRunFinished.PNG)](./media/GERImportFromSharePoint-12-ModelMappingRunFinished.PNG)

6. Na página **Estados dos arquivos das origens**, selecione **Atualizar** para atualizar a página.

    [![Página dos estados do arquivo de ER para as fontes](./media/GERImportFromSharePoint-13-FileStatesForm.PNG)](./media/GERImportFromSharePoint-13-FileStatesForm.PNG)

7. Na seção **Arquivos** , examine a lista de arquivos. A seção **Logs de origem do formato de importação** fornece o histórico de importação de arquivo Excel. Como esse arquivo foi importado com êxito, ele é marcado como **Excluído** na pasta do SharePoint.
8. Revise a pasta do SharePoint **Origem de importação dos arquivos (principal)**. Os arquivos do Excel que foram importados com sucesso foram excluídos desta pasta.
9. Selecione **Contas a pagar** \> **Tarefas periódicas** \> **Imposto 1099** \> **Liquidação de fornecedor para impostos 1099**.
10. Nos campos **De** e **Até**, informe os valores apropriados. Em seguida, selecione **Transações 1099 manuais**.

    As transações do fornecedor importadas dos arquivos do Excel no SharePoint para o comprovante **V-00001** são apresentadas na página.

    [![Página transações do fornecedor 1099](./media/GERImportFromSharePoint-14-ImportedTransactions.PNG)](./media/GERImportFromSharePoint-14-ImportedTransactions.PNG)

## <a name="prepare-an-excel-file-for-import"></a>Preparar um arquivo do Excel para importação
1. Abra o arquivo do Excel usado anteriormente. Na linha 3, coluna 1 adicione um código do fornecedor que não existe no aplicativo. Inclua informações adicionais falsas de fornecedor na linha.

    [![Arquivo de exemplo do Microsoft Excel para importar do SharePoint](./media/GERImportFromSharePoint-15-Excel.PNG)](./media/GERImportFromSharePoint-15-Excel.PNG)

2. Carregue o arquivo do Excel atualizado que contém as transações dos fornecedores para a pasta do SharePoint **Origem de importação dos arquivos (principal)**.
3. Abra a árvore das configurações de ER, selecione **Modelo de pagamento 1099** e expanda a lista de componentes do modelo de ER.
4. Selecione o nome do mapeamento de modelo para atualizar o mapeamento de modelo, de forma que o código incorreto do fornecedor seja considerado um erro durante o processo de importação de dados.
5. Selecione **Designer**.
6. Na guia **Validações** , você deverá alterar a ação de pós-validação para a regra de validação que foi configurada para avaliar se a conta de fornecedor importada existe no aplicativo. Atualize o valor do campo **Ação pós-validação** para **Parar execução**, salve suas alterações e feche a página.

    [![ER Página designer de mapeamento do modelo](./media/GERImportFromSharePoint-16-UpdateModelMapping.PNG)](./media/GERImportFromSharePoint-16-UpdateModelMapping.PNG)

7. Salvar suas alterações e feche o designer de mapeamento de modelo do ER.
8. Selecione **Executar** para executar o mapeamento de modelo de ER modificado.
9. Insira a ID de comprovante, como **V-00002** e depois selecione **OK**.

    O log de informações contém um aviso de que há um arquivo na pasta do SharePoint com uma conta de fornecedor incorreta e que, portanto, ele não pode ser importado.

    [![Execução concluída do mapeamento de modelo de ER](./media/GERImportFromSharePoint-17-ModelMappingRunFinished.PNG)](./media/GERImportFromSharePoint-17-ModelMappingRunFinished.PNG)

10. Na página **Estados dos arquivos das origens**, selecione **Atualizar** e, em seguida, na seção **Arquivos**, revise a lista de arquivos.

    [![Página dos estados do arquivo de ER para as origens selecionadas](./media/GERImportFromSharePoint-18-FileStatesForm.PNG)](./media/GERImportFromSharePoint-18-FileStatesForm.PNG)

   A seção **Logs de origem do formato de importação** indica que o processo de importação falhou e que o arquivo está na pasta de arquivos com erros do SharePoint (a caixa de seleção **Excluído** não está marcada). Se você corrigir esse arquivo no SharePoint adicionando o código de fornecedor apropriado e movendo-o para a pasta Origem de importação dos arquivos (principal) do SharePoint, poderá importá-lo novamente.

11. Selecione **Contas a pagar** \> **Tarefas periódicas** \> **Imposto 1099** \> **Liquidação de fornecedor para impostos 1099**, insira os valores apropriados nos campos **De** e **Até** e selecione **Transações 1099 manuais**.

    Somente as transações para o comprovante V-00001 estão disponíveis. Nenhuma transação para o comprovante V-00002 estará disponível, mesmo que o erro da última transação importada seja encontrado no arquivo do Excel.

## <a name=""></a><a name="limitations">Limitações</a>

A estrutura de ER não permite iniciar um novo trabalho em lote de execução de mapeamento de modelo no modo autônomo para a importação de dados. Para isso, você deve desenvolver uma nova lógica de forma que o mapeamento de modelo de ER configurado possa ser chamado na interface do usuário (IU) do aplicativo para importar dados de arquivos de entrada. Portanto, é necessário algum trabalho de engenharia. 

Se você quiser saber mais sobre a API de ER relevante, consulte a seção [Código para executar mapeamento de formato para importação de dados](er-apis-app73.md#code-to-run-a-format-mapping-for-data-import) no tópico [Alterações na API da estrutura de ER para Application update 7.3](er-apis-app73.md).

Analise o código na classe `BankImport_RU` do modelo `Application Suite` para ver como a lógica personalizada pode ser implementada. Essa classe estende a `RunBaseBatch`. Em particular, analise o método `runER()` em que o objeto `ERIModelMappingDestinationRun` é criado como o executor de um mapeamento de modelo de ER.

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral do Relatório Eletrônico](general-electronic-reporting.md)

[Alterações na API da estrutura de ER para Application update 7.3](er-apis-app73.md)

