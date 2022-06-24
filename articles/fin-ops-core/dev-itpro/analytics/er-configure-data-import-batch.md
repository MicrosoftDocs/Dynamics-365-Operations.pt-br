---
title: Importar dados de arquivos selecionados manualmente em modo de lotes
description: Este artigo explica como importar dados de arquivos selecionados manualmente no modo de lotes.
author: NickSelin
ms.date: 01/07/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERImportFormatSourceTable, ERWorkspace
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2022-01-01
ms.dyn365.ops.version: Release 10.0.25
ms.openlocfilehash: 2dec838439876fd8e57ea4a7078d97267e5ea1a2
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8890173"
---
# <a name="import-data-from-manually-selected-files-in-batch-mode"></a>Importar dados de arquivos selecionados manualmente em modo de lotes

[!include[banner](../includes/banner.md)]
[!include[banner](../includes/preview-banner.md)]

Para usar a estrutura de [Relatório eletrônico (ER)](general-electronic-reporting.md) para importar dados de arquivos de entrada manualmente selecionados no modo de lotes, configure um [formato](er-overview-components.md#format-component) ER compatível com a importação. Em seguida, execute um [mapeamento de modelo](er-overview-components.md#model-mapping-component) do tipo **Para destino** para usar esse formato como uma fonte de dados. Para importar dados, navegue para o arquivo a ser importado e selecione-o manualmente. 

A nova capacidade de ER que dá suporte à importação de dados no modo de lotes permite que esse processo seja configurado como autônomo. Você pode usar as configurações de ER para executar a importação de dados, programando um novo trabalho em lotes a partir da interface do usuário (IU) ER.

Este artigo explica como concluir a importação de dados de um arquivo selecionado manualmente no modo de lotes. Os exemplos usam transações de fornecedor como dados comerciais. As etapas desses exemplos podem ser concluídas na empresa **USMF**. Nenhum código é necessário.

## <a name="prerequisites"></a>Pré-requisitos

Para concluir os exemplos neste artigo, você deve ter o seguinte acesso:

- Uma das seguintes funções:

    - Desenvolvedor de relatório eletrônico
    - Consultor funcional de relatório eletrônico
    - Administrador do sistema

- Configurações de formato e modelo de ER para pagamentos de 1099

### <a name="create-the-required-er-configurations"></a>Criar as configurações de ER necessárias

Para criar as configurações de ER necessárias e obter outros pré-requisitos, siga uma destas etapas:

- Executar os guias de tarefas **ER Importar dados de um arquivo do Microsoft Excel**, que fazem parte do processo de negócios **7.5.4.3 Adquirir/Desenvolver componentes de serviço/solução de TI (10677)**. Esses guias de tarefas contêm orientações para o processo de criação e uso de configurações de ER que importam transações de fornecedores de maneira interativa a partir de arquivos do Microsoft Excel. Para obter mais informações, consulte [Analisar documentos de entrada no formato do Excel](parse-incoming-documents-excel.md).
- Preencha os exemplos em [Configurar importação de dados de SharePoint](er-configure-data-import-sharepoint.md). Esses exemplos contêm orientações para o processo de criação e uso de configurações de ER que importam transações de fornecedores de maneira interativa a partir de arquivos do Excel armazenados em uma pasta do SharePoint.

### <a name="download-the-required-er-configurations"></a>Baixe as configurações de ER necessárias

1. Baixe as configurações de ER a seguir e salve-as localmente.

    | Descrição do conteúdo | Arquivo |
    |---------------------|------|
    | Configuração do modelo de dados de ER do **Modelo de pagamentos 1099** | [1099model.xml](https://download.microsoft.com/download/b/d/9/bd9e8373-d558-4ab8-aa9b-31981adc97ea/1099model.xml) |
    | Configuração de formato de ER **Para importar as transações de fornecedores (Excel)** | [1099format-Import-from-Excel. xml](https://download.microsoft.com/download/b/3/8/b38faf0a-fbaf-4e9e-84c2-dedae7464880/1099format-import-from-excel.xml) |

2. Use a opção de ER [Carregar do arquivo XML](er-defer-sequence-element.md#import-the-sample-er-configurations) para importar as configurações de ER baixadas na instância do Dynamics 365 Finance na seguinte ordem:

    1. Configuração do modelo de dados de ER
    2. Configuração de formato ER

### <a name="download-the-required-excel-files"></a>Baixar os arquivos necessários do Excel

- Baixe o conjunto de dados de exemplo a seguir e salve-o localmente.

    | Descrição do conteúdo | Arquivo |
    |---------------------|------|
    | Arquivo de entrada **1099import-Data. xlsx** que contém dados de exemplo para importação | [1099import-data.xlsx](https://download.microsoft.com/download/f/f/4/ff4dbce9-8364-4391-adee-877945ff01f7/1099import-data.xlsx) |

### <a name="review-the-prerequisites"></a>Revisar os pré-requisitos

1. Acesse **Administração da organização** \> **Relatório eletrônico** \> **Configurações**.
2. Na página **Configurações**, revise a solução ER preparada para importação de dados no modo de lotes.
3. Reveja a configuração de formato **Para importar transações de fornecedores (Excel)**.

    - O componente de formato dessa configuração foi projetado para analisar um arquivo do Excel de entrada.
    - O componente de mapeamento de modelo dessa configuração é usado para preencher o modelo de dados básico usando dados do arquivo do Excel analisado.

    ![Configuração de formato de ER para importar dados no modo de lotes da interface de usuário de ER.](./media/er-configure-data-import-batch-configurations-1.png)

4. Revise a configuração do modelo de dados **Modelo de pagamentos 1099**.

    - O componente de modelo desta configuração representa a estrutura do modelo de dados que é usado para passar dados entre componentes ER em execução.
    - O componente de mapeamento de modelos dessa configuração é usado para obter dados do componente de formato executado e atualizar as tabelas de aplicativos.

    ![Configuração de modelo de dados de ER para importar dados no modo de lotes da interface de usuário de ER.](./media/er-configure-data-import-batch-configurations-2.png)

5. Abra o arquivo **1099import-Data. xlsx** no Excel.

    ![Exemplo de arquivo do Excel com dados para importação no modo de lotes.](./media/er-configure-data-import-batch-excel-content.png)

## <a name="enable-batch-data-import-for-er-from-the-ui"></a>Habilitar importação de dados em lote para ER a partir da interface do usuário

1. Acesse **Administrador do sistema** \> **Espaços de trabalho** \> **Gerenciamento de recursos**.
2. No espaço de trabalho **Gerenciamento de recursos**, selecione o recurso **Executar importação de ER de documentos carregados manualmente em lote** e selecione **Habilitar agora**.

## <a name="import-data-from-manually-selected-excel-files"></a>Importar dados de arquivos Excel selecionados manualmente

1. Acesse **Administração da organização** \> **Relatório eletrônico** \> **Configurações**.
2. Na página **Configurações**, selecione a configuração de modelo de dados **Modelo de pagamentos 1099**.
3. Na FastTab **Componentes de configuração**, selecione o link **Para importação de transações manuais 1099**.
4. Na página **Modelo para mapeamento de fonte de dados**, o mapeamento de modelos **Para importação de transações manuais 1099** é pré-selecionado. Selecione **Executar**.
5. Na guia **Parâmetros**, selecione **Navegar**. Localize e selecione o arquivo **1099import-data.xlsx** e, depois, selecione **OK**.
6. No campo **Inserir id de comprovante**, digite **V-00001**.
7. Na guia **Executar em segundo plano**, defina a opção **Processamento em lotes** como **Sim**.

    Observe que o campo **Descrição da tarefa** está definido como **Executar o mapeamento do modelo 'Para importação de transações manuais 1099, configuração 'Modelo de pagamentos 1099**. Esse valor indica que a execução do mapeamento de modelos selecionado será agendada como um novo trabalho em lotes.

    ![Especificar detalhes da importação de dados no modo de lotes na caixa de diálogo Parâmetros do relatório eletrônico.](./media/er-configure-data-import-batch-execution-parameters.png)

8. Selecione **OK**. Uma mensagem o notifica de que um novo trabalho em lotes foi agendado.

    ![Mensagem sobre um novo trabalho em lotes agendado na página Modelo para mapeamento de fonte de dados.](./media/er-configure-data-import-batch-scheduled-job-info.png)

## <a name="review-the-data-import-results-on-the-batch-job-page"></a>Revisar os resultados da importação de dados na página Trabalho em lotes

1. Acesse **Comum** \> **Consultas** \> **Trabalhos em lotes** \> **Meus trabalhos em lotes**.
2. Na página **Trabalho em lotes**, filtre a lista de trabalhos em lotes para localizar o lote agendado e, depois, selecione-o.
3. Selecione o link de **ID do trabalho** para analisar detalhes do trabalho.
4. Na FastTab **Tarefas em lotes**, selecione **Registrar**.

    ![Botão Registrar na página Trabalho em lotes.](./media/er-configure-data-import-batch-scheduled-job-record.png)

5. Revise detalhes da execução.

    ![Log de execução do trabalho em lotes agendado na página Trabalho em lotes.](./media/er-configure-data-import-batch-scheduled-job-log.png)

## <a name="change-the-data-import-parameters"></a>Alterar os parâmetros de importação de dados

Depois que o lote for agendado e ainda não tiver sido executado, você poderá alterar os parâmetros da importação de dados agendada.

1. Acesse **Comum** \> **Consultas** \> **Trabalhos em lotes** \> **Meus trabalhos em lotes**.
2. Na página **Trabalho em lotes**, filtre a lista de trabalhos em lotes para localizar o lote agendado e, depois, selecione-o.
3. Selecione **Alterar status**.
4. Na caixa de diálogo **Selecionar novo status**, selecione **Reter** e, depois, **OK**.
5. Selecione o link de **ID do trabalho** para acessar os detalhes do trabalho.
6. Na FastTab **Tarefas em lotes**, selecione **Parâmetros**.
7. Na caixa de diálogo **Parâmetros de relatório eletrônico**, siga estas etapas:

    1. Selecione **Procurar** para selecionar o arquivo alternativo para importação de dados.
    2. Selecione **Inserir id de comprovante** para alterar o número do comprovante para importar transações do fornecedor.

        ![Alterar os parâmetros da importação de dados para o trabalho em lotes agendado na caixa de diálogo Parâmetros do relatório eletrônico.](./media/er-configure-data-import-batch-scheduled-job-parameters.png)

    3. Selecione **OK**.

8. Verifique se o lote ainda está selecionado e, depois, selecione novamente **Alterar status**.
9. Na caixa de diálogo **Selecionar novo status**, selecione **Aguardando** e, depois, **OK**.

## <a name="review-the-data-import-results-on-the-er-source-page"></a>Revisar os resultados da importação de dados na página Fonte de ER

1. Vá para **Administração da organização** \> **Relatório eletrônico** \> **Origem do relatório eletrônico**.
2. Selecione o registro **Para importar as transações de fornecedores (Excel)** criado automaticamente durante a importação de dados.

    ![Registro da configuração de Para importar as transações de fornecedores (Excel) na página Fonte de relatório eletrônico.](./media/er-configure-data-import-batch-files-source-1.png)

3. Selecione **Estados dos arquivos das origens**.
4. Nas FastTabs **Arquivos** e **Logs de origem para o formato de importação**, revise os detalhes da importação.
5. Na FastTab **Arquivos**, selecione o registro. Observe que o arquivo importado está anexado a esse registro.

    ![Arquivo importado anexado ao registro na página Estados dos arquivos das origens.](./media/er-configure-data-import-batch-files-source-2.png)

6. Selecione **Anexos** para revisar o arquivo importado.

    ![Arquivo importado na página Exibição de documento.](./media/er-configure-data-import-batch-files-source-3.png)

    > [!TIP]
    > Para manter esses anexos, a estrutura de ER usa um tipo de documento [definido](electronic-reporting-er-configure-parameters.md#parameters-to-manage-documents) para a empresa atual no campo **Outros** dos parâmetros de ER.

## <a name="review-the-data-import-results-on-the-vendor-settlement-for-1099s-page"></a>Revisar os resultados da importação de dados na página Liquidação de fornecedor para impostos 1099

1. Vá para **Contas a pagar** \> **Tarefas periódicas** \> **Imposto 1099** \> **Liquidação de fornecedor para impostos 1099**.
2. No campo **Data inicial**, insira **31/12/2017** (31 de dezembro de 2017).
3. Selecione **Transações 1099 manuais**.

    ![Transações de fornecedor importadas na página Transações do imposto 1099.](./media/er-configure-data-import-batch-imported-data.png)

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral do Relatório Eletrônico](general-electronic-reporting.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
