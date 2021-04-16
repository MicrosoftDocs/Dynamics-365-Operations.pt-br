---
title: Suprimir controles de conteúdo do Word em relatórios gerados
description: Este tópico explica como configurar um formato de Relatório eletrônico (ER) para gerar relatórios como arquivos do Microsoft Word nos quais os controles de conteúdo são suprimidos.
author: NickSelin
ms.date: 02/11/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, EROperationDesigner,  LedgerJournalTable, LedgerJournalTransVendPaym
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-01-01
ms.dyn365.ops.version: Version 10.0.6
ms.openlocfilehash: 8c99203110cfdc7f8123c30488611d55f48e8f67
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5753591"
---
# <a name="suppress-word-content-controls-in-generated-reports"></a>Suprimir controles de conteúdo do Word em relatórios gerados

[!include [banner](../includes/banner.md)]

Para gerar relatórios como documentos do Microsoft Word, você deverá criar um modelo para os relatórios como um documento do Word. Esse modelo deve conter controles de conteúdo do Word como espaços reservados para os dados que serão preenchidos no runtime. Para usar um documento do Word criado como um modelo para seus relatórios, você poderá [configurar](er-design-configuration-word.md) uma nova [solução](er-quick-start1-new-solution.md) de [Relatório eletrônico (ER)](general-electronic-reporting.md). A solução deve incluir uma [configuração](general-electronic-reporting.md#Configuration) ER que contenha um componente de [formato](general-electronic-reporting.md#FormatComponentOutbound) ER. Esse formato ER deve ser configurado para usar o modelo projetado para a geração de relatórios.

Na versão 10.0.6 e posterior do Dynamics 365 Finance, você pode configurar fórmulas no formato ER para suprimir alguns controles de conteúdo do Word em documentos gerados.

As etapas a seguir explicam como um usuário atribuído à função Administrador do sistema ou Consultor funcional de Relatório eletrônico pode configurar um formato ER que gera relatórios como arquivos do Word e suprime alguns dos controles de conteúdo nos relatórios gerados que foram configurados usando um modelo do Word.

Estas etapas podem ser concluídas na empresa GBSI.

## <a name="prerequisites"></a>Pré-requisitos

Para concluir estas etapas, primeiro você deverá concluir as etapas nas seguintes guias de tarefas:

- [Criar uma configuração para gerar relatórios no formato OPENXML](./tasks/er-design-reports-openxml-2016-11.md)
- [Reutilizar configurações de ER com modelos do Excel para gerar relatórios no formato do Word](./tasks/er-design-configuration-word-2016-11.md)

Quando você concluir as etapas desses guias de tarefas, os seguintes itens serão preparados:

- Um formato ER de **Relatório de planilha de exemplo** que está configurado para gerar um documento no formato do Word
- Uma versão de [rascunho](general-electronic-reporting.md#component-versioning) do formato ER de **Relatório de planilha de exemplo** marcado como **Executável**
- Um método de pagamentos **Eletrônico** configurado para usar o formato ER de **Relatório de planilha de exemplo** para processamento de pagamento de fornecedor

Você também precisa baixar e salvar o seguinte modelo para o relatório de exemplo:

- [Modelo limitado 2 de relatório de pagamento (SampleVendPaymDocReportBounded2.docx)](https://download.microsoft.com/download/a/1/2/a126cb43-6281-4f7b-bde0-25e03ff9bc1e/SampleVendPaymDocReportBounded2.docx)

## <a name="review-the-downloaded-word-template"></a><a id="tag-control"></a>Analisar o modelo do Word baixado

1. No aplicativo da área de trabalho de Word, abra o arquivo de modelo **SampleVendPaymDocReportBounded2.docx** baixado anteriormente.
2. Verifique se o arquivo de modelo contém uma seção de resumo que mostra os valores de pagamento total para todos os códigos de moeda que foram atendidos nos pagamentos processados.

    - A seção de resumo reside em uma tabela separada do documento do Word.
    - A primeira linha desta tabela mantém os títulos das colunas da tabela como o cabeçalho da seção.
    - A segunda linha desta tabela mantém o controle de conteúdo repetitivo como os detalhes da seção.
    - Esse controle de conteúdo é mapeado para o campo **SummaryLines** da parte XML personalizada do **Relatório**.
    - Com base nesse mapeamento, o controle de conteúdo é associado ao elemento **SummaryLines** do formato ER editável.

    > [!NOTE]
    > O controle de conteúdo repetitivo é marcado pela chave **SummaryLines** que corresponde ao campo da parte XML personalizada para a qual foi mapeado.

    ![Layout de modelo do Word](./media/er-design-configuration-word-suppress-controls-image1.gif)

## <a name="select-the-existing-er-report-configuration"></a>Selecionar a configuração de relatório de ER existente

Para as etapas a seguir, você reusará a configuração de ER existente que você definiu ao concluir as etapas nos guias de tarefas mencionadas anteriormente.

1. Vá para **Administração da organização** \> **Espaços de trabalho** \> **Relatório eletrônico**.
2. Selecione **Configurações de relatórios**.
3. Na página **Configurações**, na árvore de configuração, expanda **Modelo de pagamento** e selecione **Relatório de planilha de exemplo**.
4. Selecione **Designer** para editar a versão de rascunho do formato ER selecionado.

## <a name="replace-the-current-template-with-the-new-template"></a>Substituir o modelo atual pelo novo modelo

Atualmente, o arquivo SampleVendPaymDocReportBounded.docx é usado como um modelo para gerar a saída no formato do Word. Nas etapas a seguir, você substituirá esse modelo do Word pelo novo modelo do Word, SampleVendPaymDocReportBounded2.docx, que você baixou anteriormente.

1. Na página **Designer de formatos**, selecione **Anexos**.
2. Na página **Anexos**, selecione **Excluir** para remover o modelo existente.
3. Selecione **Sim** para confirmar a exclusão.
4. Selecione **Novo** \> **Arquivo**.
5. Selecione **Procurar** e procure e selecione o arquivo **SampleVendPaymDocReportBounded2.docx** baixado anteriormente.
6. Selecione **OK**.
7. Feche a página **Anexos**.
8. Na página **Designer de formatos**, no campo **Modelo**, insira ou selecione o arquivo **SampleVendPaymDocReportBounded2.docx**.

## <a name="run-the-format-to-create-word-output"></a>Executar o formato para criar a saída do Word

1. Acesse **Contas a pagar** \> **Pagamentos** \> **Diário de pagamento**.
2. Na página **Pagamentos do fornecedor**, na guia **Lista**, selecione todos os pagamentos.
3. Selecione o **Status do pagamento** \> **Nenhum**.
4. Selecione **Gerar pagamentos**.
5. No campo **Método de pagamento**, selecione **Eletrônico**.
6. No campo **Conta bancária**, selecione **GBSI OPER**.
7. Selecione **OK**.
8. Na caixa de diálogo **Parâmetros de relatório eletrônico**, selecione **OK** e analise a saída gerada.

    ![Pagamentos para processar na página Pagamentos do fornecedor](./media/er-design-configuration-word-suppress-controls-image2.gif)

    A saída é apresentada no formato do Word e contém a seção de resumo.

## <a name="configure-the-editable-format-to-suppress-the-summary-section"></a><a id="configure-to-suppress-control"></a>Configurar o formato editável para suprimir a seção de resumo

Se desejar suprimir a seção de resumo em um documento gerado, com base na solicitação de um usuário que executa esse formato ER, você deverá modificar o formato ER editável.

1. Acesse **Administração da organização** \> **Espaços de trabalho** \> **Relatório eletrônico** e abra a versão de rascunho do formato ER para edição.
2. Selecione **Configurações de relatórios**. 
3. Na página **Configurações**, na árvore de configuração, expanda **Modelo de pagamento** \> **Relatório de planilha de exemplo**.
4. Selecione **Designer**.
5. Na página **Designer de formatos**, expanda **Word** e selecione **SummaryLines**.
6. Na guia **Mapeamento**, adicione uma nova fonte de dados para perguntar ao usuário, no runtime, se a seção de resumo deve ser suprimida:

    1. Selecione **Adicionar raiz**.
    2. Na caixa de diálogo **Adicionar fonte de dados**, selecione **Geral\Parâmetro de entrada de usuário** para abrir a caixa de diálogo **Propriedades da fonte de dados "Parâmetro de entrada do usuário"**.
    3. No campo **Nome**, insira **uipSuppress**.
    4. No campo **Rótulo**, insira a **seção Resumo de supressão**.
    5. No campo **Nome do tipo de dados de operações**, selecione ou insira **NoYes**.
    6. Selecione **OK**.

7. Adicione uma nova fonte de dados do tipo de enumeração de aplicativo **NoYes**:

    1. Selecione **Adicionar raiz**.
    2. Na caixa de diálogo **Adicionar fonte de dados**, selecione **Dynamics 365 for Operations\Enumeração** para abrir a caixa de diálogo **Propriedades da fonte de dados "Enumeração"**.
    3. No campo **Nome**, insira **enumNoYes**.
    4. No campo **Rótulo**, insira **Opções de supressão**.
    5. No campo **Nome do tipo de dados de operações**, selecione ou insira **NoYes**.
    6. Selecione **OK**.

8. Para o elemento de formato **SummaryLines** selecionado, configure a fórmula para especificar quando o controle de conteúdo do Word associado ao elemento de formato selecionado deve ser suprimido:

    1. Na guia **Mapeamento**, na seção **Removido**, selecione **Editar** para abrir a página **[Designer de fórmulas](general-electronic-reporting-formula-designer.md)**.
    2. No campo **Fórmula**, insira a fórmula `uipSuppress = enumNoYes.Yes`.
    3. Selecione **Salvar** e feche a página **Designer de fórmulas**.

        > [!NOTE]
        > Essa fórmula será aplicada a um documento gerado **depois que todos os outros elementos de formato são executados**. Para aplicar essa fórmula, um controle de conteúdo do Word marcado como um elemento de formato para o qual a fórmula está configurada (**SummaryLines**, nesse caso) é encontrado em um documento gerado. Esse controle de conteúdo é, então, completamente removido, juntamente com a linha da tabela do Word que o contém. A linha de detalhes da seção de resumo é removida do documento gerado.
        >
        > Em tempo de design, você pode configurar a fórmula **Removida** para um elemento de formato, mesmo que nenhum controle de conteúdo no modelo do Word que você está usando tenha uma marca que corresponda ao nome de um elemento de formato para o qual a propriedade **Removida** está configurada. Ao validar o formato no tempo de design, você receberá um [aviso](er-components-inspections.md#i14) sobre essa inconsistência.
        >
        > No runtime, uma exceção será lançada se nenhum controle de conteúdo no modelo do Word que você está usando tiver uma marca que corresponda ao nome de um elemento de formato para o qual a propriedade **Removida** está configurada.

    4. Na guia **Mapeamento**, na seção **Removido**, defina a opção **Com pai** como **Sim**.

        > [!NOTE]
        > Você deve definir esta opção como **Sim** para remover a tabela inteira do Word como o objeto pai da linha que contém os detalhes da seção de resumo. Se você definir essa opção como **Não**, a linha de cabeçalho da seção permanecerá no documento gerado.

9. Selecione **Salvar** para salvar as alterações no formato editável.

    ![A saída gerada no formato do Word](./media/er-design-configuration-word-suppress-controls-image3.gif)

## <a name="run-the-modified-format-to-create-word-output"></a>Executar o formato modificado para criar a saída do Word

1. Acesse **Contas a pagar** \> **Pagamentos** \> **Diário de pagamento**.
2. Selecione o diário de pagamento que você criou e, em seguida, selecione **Linhas**.
3. Na página **Pagamentos do fornecedor**, selecione todas as linhas e, em seguida, selecione **Status do pagamento** \> **Nenhum**.
4. Selecione **Gerar pagamentos**.
5. No campo **Método de pagamento**, selecione **Eletrônico**.
6. No campo **Conta bancária**, selecione **GBSI OPER**.
7. Selecione **OK**.
8. Na caixa de diálogo **Parâmetros do relatório eletrônico** , no campo **Seção Resumo de supressão**, selecione **Sim**.
9. Selecione **OK** e analise a saída gerada.

    ![Saída gerada no formato Word](./media/er-design-configuration-word-suppress-controls-image4.gif)

    Observe que a saída não contém a seção de resumo, pois ela foi suprimida.

## <a name="additional-resources"></a>Recursos adicionais

- [Criar uma configuração para gerar relatórios no formato OPENXML](./tasks/er-design-reports-openxml-2016-11.md)
- [Criar uma configuração ER para gerar relatórios no formato Word](er-design-configuration-word.md)
- [Reutilizar configurações de ER com modelos do Excel para gerar relatórios no formato do Word](./tasks/er-design-configuration-word-2016-11.md)
- [Inspecionar o componente de ER configurado para evitar problemas de runtime](er-components-inspections.md#i14)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]