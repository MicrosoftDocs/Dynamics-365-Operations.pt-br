---
title: Reutilizar configurações de ER com modelos do Excel para gerar relatórios no formatos Word
description: Este artigo descreve como os formatos de relatório criados para gerar relatórios como pastas de trabalho do Excel podem ser configurados para gerar relatórios como documentos do Word.
author: kfend
ms.date: 04/23/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.search.form: ERWorkspace, ERSolutionTable, EROperationDesigner, LedgerJournalTable, LedgerJournalTransVendPaym
ms.openlocfilehash: eea037751bc7ae4cb5e45fcaa0166d1f2f0b8292
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9291164"
---
# <a name="reuse-er-configurations-with-excel-templates-to-generate-reports-in-word-format"></a>Reutilizar configurações de ER com modelos do Excel para gerar relatórios no formatos Word

[!include [banner](../../includes/banner.md)]

Para gerar relatórios como documentos do Microsoft Word, você pode [configurar](../er-design-configuration-word.md) um novo formato de [Relatório Eletrônico (ER)](../general-electronic-reporting.md). Como alternativa, você pode reutilizar um formato de ER que foi originalmente projetado para gerar relatórios como pastas de trabalho do Excel. Nesse caso, você deve substituir o modelo do Excel por um modelo do Word.

Os procedimentos a seguir mostram como um usuário na função Administrador do sistema ou no desenvolvedor de relatório eletrônico pode configurar um formato de ER para gerar relatórios como arquivos do Word reutilizando um formato de ER que foi criado para gerar relatórios como arquivos do Excel.

Esses procedimentos podem ser concluídos na empresa GBSI.

## <a name="prerequisites"></a>Pré-requisitos

Para completar esses procedimentos, primeiro você deve seguir as etapas no guia de tarefa [Criar uma configuração para gerar relatórios no formato OPENXML](er-design-reports-openxml-2016-11.md).

Você também precisa baixar e salvar localmente os seguintes modelos para o modelo de relatório:

- [Modelo de relatório de pagamento (SampleVendPaymDocReport.docx)](https://download.microsoft.com/download/0/d/e/0de5a87c-95fc-4dfa-958f-285cb28b5b2b/SampleVendPaymDocReport.docx)
- [Modelo limitado de relatório de pagamento (SampleVendPaymDocReportBounded.docx)](https://download.microsoft.com/download/a/1/2/a126cb43-6281-4f7b-bde0-25e03ff9bc1e/SampleVendPaymDocReportBounded.docx)

Esses procedimentos são para um recurso que foi adicionado no Dynamics 365 for Operations versão 1611 (novembro de 2016).

## <a name="select-the-existing-er-report-configuration"></a>Selecionar a configuração de relatório de ER existente

1. No Dynamics 365 Finance, acesse **Administração da organização** \> **Espaços de trabalho** \> **Relatório eletrônico**.
2. Verifique se o provedor de configuração **Litware, Inc.** está selecionado como **Ativo**. Se não estiver, siga as etapas no guia de tarefas [Criar provedores de configuração e marcá-los como ativos](er-configuration-provider-mark-it-active-2016-11.md).
3. Selecione **Configurações de relatórios**. Você reutilizará a configuração de ER existente que foi criada para gerar a saída de relatório no formato OPENXML.
4. Na página **Configurações**, na árvore de configuração no painel esquerdo, expanda **Modelo de pagamento** e selecione **Exemplo de relatório de planilha**.

    > [!NOTE]
    > A versão de rascunho selecionada do formato de ER pode ser editada na guia rápida **Versões**.

5. Selecione **Designer**.
6. Na página **Designer de formato**, observe que o título do elemento de formato raiz indica que um modelo do Excel está sendo usado no momento.

![Selecionar a configuração existente.](../media/er-design-configuration-word-2016-11-image01.gif)

## <a name="review-the-downloaded-word-template"></a>Analisar o modelo do Word baixado

1. No aplicativo da área de trabalho Word, abra o arquivo de modelo **SampleVendPaymDocReport.docx** baixado anteriormente.
2. Observe que esse modelo contém apenas o layout do documento que desejamos gerar como saída de ER.

![O layout de modelo do Word no aplicativo da área de trabalho.](../media/er-design-configuration-word-2016-11-image02.png)

## <a name="replace-the-excel-template-with-the-word-template-and-add-a-custom-xml-part"></a>Substituir o modelo do Excel pelo modelo do Word e adicionar uma parte XML personalizada

Atualmente, o documento do Excel é usado como modelo para gerar a saída no formato OPENXML. Você substituirá este modelo com o arquivo de modelo do Word SampleVendPaymDocReport.docx baixado anteriormente. Você também estenderá o modelo do Word adicionando uma parte XML personalizada.

1. No Finance, na página **Designer de formato**, na guia **Formatar**, selecione **Anexos**.
2. Na página **Anexos**, selecione **Excluir** para remover o modelo do Excel existente. Selecione **Sim** para confirmar a alteração.
3. Selecione **Novo** \> **Arquivo**.

    > [!NOTE]
    > É necessário selecionar um tipo de documento [configurado](../electronic-reporting-er-configure-parameters.md#parameters-to-manage-documents) nos parâmetros de ER para armazenar modelos de formato de ER.

4. Selecione **Pesquisar**, pesquise e selecione o arquivo **SampleVendPaymDocReport.docx** baixado anteriormente.
5. Selecione **OK**.
6. Feche a página **Anexos**.
7. Na página **Designer de formato**, no campo **Modelo**, insira ou selecione o arquivo **SampleVendPaymDocReport.docx** para usar esse modelo do Word em vez do modelo do Excel que foi usado anteriormente.
8. Selecione **Salvar**.

    Além de armazenar alterações de configuração, a ação **Salvar** também atualiza o modelo do Word anexo. A estrutura hierárquica do formato criado é adicionada ao documento do Word anexo como nova parte XML personalizada chamada **Relatório**. O modelo do Word anexo contém não só o layout do documento que será gerado como saída de ER, mas também a estrutura dos dados que o ER preencherá nesse modelo no runtime.

9. Observe que o título do elemento de formato raiz indica que um modelo do Word está sendo usado no momento.

    ![Substituir o modelo do Excel pelo modelo do Word e adicionar uma parte XML personalizada.](../media/er-design-configuration-word-2016-11-image03.gif)

10. Na guia **Formato**, selecione **Anexos**.

Agora você pode mapear os elementos da parte XML personalizada **Relatório** selecionada para os controles de conteúdo do documento do Word.

Se estiver familiarizado com o processo de criar documentos do Word como formulários com [controles de conteúdo](/office/client-developer/word/content-controls-in-word) mapeados a elementos das [partes XML personalizadas](/visualstudio/vsto/custom-xml-parts-overview), siga todas as etapas do próximo procedimento para criar o documento. Para obter mais informações, consulte [Criar formulários preenchidos ou impressos pelos usuários no Word](https://support.office.com/article/Create-forms-that-users-complete-or-print-in-Word-040c5cc1-e309-445b-94ac-542f732c8c8b). Caso contrário, ignore o próximo procedimento.

## <a name="get-a-word-document-that-has-a-custom-xml-part-and-do-data-mapping"></a><a id='get-word-doc'></a>Obter um documento do Word que tenha uma parte XML personalizada e fazer mapeamento de dados

1. No Finance, na página **Anexos**, selecione **Abrir** para baixar o modelo selecionado do Finance e armazená-lo localmente como um documento do Word.
3. No aplicativo da área de trabalho Word, abra o documento que você acabou de baixar.
4. Na guia **Desenvolvedor**, selecione **Painel de mapeamento XML**.

    > [!NOTE]
    > Se a guia **Desenvolvedor** não aparecer na faixa de opções, personalize a faixa para adicioná-la.

5. No painel **Mapeamento XML**, no campo **Parte XML personalizada**, selecione a parte XML personalizada do **Relatório**.
6. Mapeie os elementos da parte XML personalizada **Relatório** selecionada e os controles de conteúdo do documento do Word.
7. Salve o documento atualizado do Word localmente como **SampleVendPaymDocReportBounded.docx**.

## <a name="review-the-word-template-where-the-custom-xml-part-is-mapped-to-content-controls"></a>Revisar o modelo do Word em que a parte XML personalizada é mapeada para controles de conteúdo

1. No aplicativo da área de trabalho Word, abra o arquivo de modelo **SampleVendPaymDocReport.docx** baixado anteriormente.
2. Observe que esse modelo contém o layout do documento que desejamos gerar como saída de ER. Os controles de conteúdo usados como espaços reservados para dados que o ER insere neste modelo no tempo de execução são baseados nos mapeamentos que são configurados entre os elementos da parte XML personalizada **Relatório** e os controles de conteúdo do documento do Word.

![Versão prévia de modelo do Word no aplicativo da área de trabalho.](../media/er-design-configuration-word-2016-11-image04.png)

## <a name="upload-the-word-template-where-the-custom-xml-part-is-mapped-to-content-controls"></a>Carregar o modelo do Word em que a parte XML personalizada é mapeada para controles de conteúdo

1. No Finance, na página **Anexos**, selecione **Excluir** para remover o modelo do Word que não tem mapeamentos entre elementos da parte XML personalizada **Relatório** e controles de conteúdo. Selecione **Sim** para confirmar a alteração.
2. Selecione **Novo** \> **Arquivo** para adicionar um novo arquivo de modelo que contém mapeamentos entre elementos da parte XML personalizada **Relatório** e controles de conteúdo.

    > [!NOTE]
    > É necessário selecionar um tipo de documento [configurado](../electronic-reporting-er-configure-parameters.md#parameters-to-manage-documents) nos parâmetros de ER para armazenar modelos de formato de ER.

3. Selecione **Pesquisar**, pesquise e selecione o arquivo **SampleVendPaymDocReportBounded.docx** que você baixou ou preparou concluindo o procedimento na seção [Obter um documento do Word que tenha uma parte XML personalizada para fazer mapeamento de dados](#get-word-doc).
4. Selecione **OK**.
5. Feche a página **Anexos**.
6. Na página **Designer de formato**, no campo **Modelo**, selecione o documento que você acabou de baixar.
7. Selecione **Salvar**.
8. Feche a página **Designer de formato**.

## <a name="mark-the-configured-format-as-runnable"></a>Marcar o formato configurado como executável

Para executar a versão de rascunho do formato editável, você deve torná-la [executável](../er-quick-start2-customize-report.md#MarkFormatRunnable).

1. No Finance, na página **Configurações**, no Painel Ação, na guia **Configurações**, no grupo **Configurações avançadas**, selecione **Parâmetros de usuário**.
2. Na caixa de diálogo **Parâmetros de usuário**, defina a opção **Executar configurações** como **Sim** e selecione **OK**.
3. Selecione **Editar** para tornar a página atual editável, conforme necessário.
4. Para a configuração **Exemplo de relatório de planilha** selecionada no momento, defina a opção **Executar rascunho** como **Sim**.
5. Selecione **Salvar**.

## <a name="run-the-format-to-create-output-in-word-format"></a>Executar o formato para criar saída no formato do Word

1. No Finance, Acesse **Contas a pagar** \> **Pagamentos** \> **Diário de pagamentos**.
2. Em um diário de pagamentos inserido anteriormente, selecione **Linhas**.
3. Na página **Pagamentos do fornecedor**, selecione todas as linhas na grade.
4. Selecione o **Status do pagamento** \> **Nenhum**.

    ![Pagamentos para processar na página Pagamentos do fornecedor.](../media/er-design-configuration-word-2016-11-image05.png)

5. No Painel de Ações, selecione **Gerar pagamentos**.
6. Na caixa de diálogo que aparece, siga estas etapas:

    1. No campo **Método de pagamento**, selecione **Eletrônico**.
    2. No campo **Conta bancária**, selecione **GBSI OPER**.
    3. Selecione **OK**.

7. Na caixa de diálogo **Parâmetros de relatório eletrônico**, selecione **OK**.
8. A saída criada é apresentada no formato Word e contém os detalhes dos pagamentos processados. Analise a saída gerada.

    ![Saída gerada no formato Word.](../media/er-design-configuration-word-2016-11-image06.png)

## <a name="additional-resources"></a>Recursos adicionais

- [Criar uma configuração ER para gerar relatórios no formato Word](../er-design-configuration-word.md)
- [Inserir imagens e formas em documentos que você gerar usando ER](../electronic-reporting-embed-images-shapes.md#embed-an-image-in-a-word-document)


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
