---
title: Adicionar novos campos a um modelo de documento comercial no Microsoft Excel
description: Este tópico fornece informações sobre como adicionar novos campos a um modelo de documento comercial no Microsoft Excel usando o recurso de gerenciamento de documentos comerciais.
author: NickSelin
ms.date: 11/15/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERBDWorkspace, ERBDParameters, ERBDTemplateEditor
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-10-01
ms.dyn365.ops.version: 10.0.7
ms.openlocfilehash: 57eebdc38fb3f74690b92c03fa60e10c7610db1fe413320a6d167f05b0658bf1
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6767233"
---
# <a name="add-new-fields-to-a-business-document-template-in-microsoft-excel"></a>Adicionar novos campos a um modelo de documento comercial no Microsoft Excel

[!include[banner](../includes/banner.md)]

Você pode adicionar novos campos a um modelo usado para gerar documentos comerciais no formato do Microsoft Excel. Esses campos podem ser adicionados como espaços reservados que são utilizados para preencher os documentos gerados com as informações necessárias ao aplicativo. Para cada campo adicionado, você também pode especificar uma associação às fontes de dados para especificar quais dados do aplicativo serão inseridos no campo quando o modelo é usado para gerar documentos comerciais.

Para saber mais sobre este recurso, conclua o exemplo neste tópico. Esse exemplo mostra como atualizar um modelo para preencher os campos nos formulários de fatura de texto livre que são gerados.

## <a name="configure-business-document-management-to-edit-templates"></a>Configurar o Gerenciamento de documentos comerciais para editar modelos

Como o BDM (Gerenciamento de documentos comerciais) foi criado com base na estrutura [Visão geral de ER (Relatórios eletrônicos)](general-electronic-reporting.md), você deve configurar os parâmetros necessários de ER e BDM antes de poder iniciar o trabalho com o BDM.

1.  Entre na instância do Microsoft Dynamics 365 Finance como o administrador de sistema.
2.  Conclua as etapas a seguir do exemplo no tópico [Visão geral do Gerenciamento de documentos comerciais](er-business-document-management.md):

    1.  Configure os parâmetros de ER.
    2.  Ative o BDM.

Agora você pode começar a usar o BDM para editar modelos de documento comercial.

## <a name="import-er-solutions-that-contain-a-template"></a>Importar soluções de ER que contêm um modelo

O exemplo neste procedimento usa a solução de ER oficialmente publicada. Você deve importar as configurações de ER dessa solução na sua instância atual do Finance.

A configuração de formato de ER **Fatura de texto livre (Excel)** dessa solução contém o modelo de documento comercial no formato do Excel que pode ser editado usando o BDM. Importe a versão mais recente dessa configuração de formato de ER do Microsoft Dynamics Lifecycle Service (LCS). As configurações do modelo de dados de ER e do mapeamento do modelo de ER correspondentes serão importadas automaticamente.

Para obter mais informações sobre como importar configurações de ER, consulte [Gerenciar o ciclo de vida da configuração de ER](general-electronic-reporting-manage-configuration-lifecycle.md).

![LCS Página Biblioteca de ativos compartilhados.](./media/BDM-AddFldExcel-LCS.png)

### <a name="edit-the-er-solution-template"></a>Editar o modelo de solução de ER

1.  Entre como um usuário com acesso ao espaço de trabalho **Gerenciamento de documentos comerciais**.
2.  Abra o espaço de trabalho **Gerenciamento de documentos comerciais**.

    ![Espaço de trabalho Gerenciamento de documentos comerciais.](./media/BDM-AddFldExcel-Workspace.png)

3.  Na grade, selecione o modelo **Fatura de texto livre (Excel)**.
4.  No painel direito, selecione **Novo modelo** para criar um novo modelo baseado no modelo selecionado.
5.  No campo **Título** , digite **Fatura de texto livre (Excel) Contoso** como o título do novo modelo.
6.  Selecione **OK** para confirmar o início do processo de edição.

A página do editor de modelo de BDM aparece. Você pode usar o Microsoft 365 para editar o modelo online selecionado no controle inserido.

![Página do editor de modelo de BDM.](./media/BDM-AddFldExcel-EditableTemplate.png)

### <a name="add-the-label-for-a-new-field-to-the-template"></a>Adicionar o rótulo para um novo campo ao modelo

1.  Na página do editor de modelo de BDM, na faixa de opções do Excel, na guia **Exibir** , marque as caixas de seleção **Cabeçalhos e Linhas de Grade** para o modelo editável do Excel.

    ![Caixas de seleção Cabeçalhos e Linhas de Grade marcadas.](./media/BDM-AddFldExcel-EditableTemplate2.png)

2.  Selecione as células **E8:F8**.
3.  Na faixa de opções do Excel, na guia **Início**, selecione **Mesclar e Centralizar** para mesclar as células selecionadas em uma nova célula mesclada **E8:F8**.
4.  Na célula mesclada **E8:F8**, insira **URL**.
5.  Selecione a célula mesclada **E7:F7**, selecione **Pintor de formato** e depois selecione a célula mesclada **E8:F8** para formatá-la da mesma forma do que a célula mesclada **E7:F7**.

    ![Novo rótulo de campo adicionado ao modelo.](./media/BDM-AddFldExcel-EditableTemplate3.png)

### <a name="format-the-template-to-reserve-space-for-a-new-field"></a>Formatar o modelo para reservar o espaço para um novo campo

1.  Na página do editor de modelo de BDM, selecione a célula mesclada **G8:H8**.
2.  Na faixa de opções do Excel, na guia **Início**, selecione **Mesclar e Centralizar** para mesclar as células selecionadas em uma nova célula mesclada **G8:H8**.
3.  Selecione a célula mesclada **G7:H7**, selecione **Pintor de formato** e depois selecione a célula mesclada **G8:H8** para formatá-la da mesma forma do que a célula mesclada **G7:H7**.

    ![Espaço reservado para o novo campo.](./media/BDM-AddFldExcel-EditableTemplate4.png)

4.  No campo da caixa **Nome** , selecione **CompanyInfo**.

    O intervalo **CompanyInfo** do modelo atual do Excel contém todos os campos usados para preencher o cabeçalho de um relatório gerado com os detalhes da empresa atual como um participante de vendedor.

    ![Intervalo de CompanyInfo selecionado.](./media/BDM-AddFldExcel-SelectCompanyInfoRange.png)

### <a name="add-a-new-field-to-the-template"></a>Adicionar um novo campo ao modelo

1.  Na página **Editor de modelo de BDM**, no Painel de Ação, selecione **Mostrar formato**.
2.  No painel **Estrutura do modelo** , selecione **Adicionar**.

    > [!NOTE]
    > Você deverá ajustar a seção do modelo que você deseja usar como um novo campo. Você já fez esse ajuste ao formatar a célula mesclada **G8:H8**.

    ![Adição de um novo campo ao modelo.](./media/BDM-AddFldExcel-AddCell.png)

3.  Selecione **Excel\Célula** para adicionar um novo campo como uma célula no modelo.

    Você pode selecionar **Excel\Intervalo** se desejar adicionar um novo intervalo ao modelo. O intervalo inserido pode conter várias células. Você pode adicionar essas células posteriormente.
    
    Observe que o componente do modelo **CompanyInfo** está selecionado automaticamente no painel **Estrutura do modelo** já que é o componente principal mais apropriado na estrutura do modelo atual para o campo que você está adicionando.
    
4.  No campo **Intervalo do Excel**, insira **CompanyURL_Value**.
5.  Selecione **OK**.

    ![Campo CompanyURL_Value adicionado à estrutura do modelo.](./media/BDM-AddFldExcel-EditableTemplate5.png)

6.  No painel **Estrutura do modelo**, selecione o botão de reticências (...) e depois selecione **Mostrar associações**.

    ![Mostrar associações selecionadas.](./media/BDM-AddFldExcel-ShowBindings.png)

    O painel **Estrutura do modelo** agora mostra as fontes de dados disponíveis no formato de ER subjacente.

7.  Selecione **CompanyInfo_Value** como o campo que você planeja associar a uma fonte de dados do formato de ER subjacente.
8.  Na seção **Fontes de dados** do painel **Estrutura do modelo**, expanda **Modelo \> InvoiceBase \> CompanyInfo**.
9.  Em **CompanyInfo**, selecione o item **WebsiteURI**.

    ![Item WebsiteURI selecionado.](./media/BDM-AddFldExcel-BindURL.png)

10. Selecione **Associar**.
11. No painel **Estrutura do modelo**, selecione **Salvar** e depois feche a página do editor de modelo de BDM.

No espaço de trabalho **Gerenciamento de documentos comerciais**, a guia **Modelo** no painel direito mostra o modelo atualizado. Na grade, observe que o campo **Status** do modelo editado foi alterado para **Rascunho** e o campo **Revisão** não estará mais em branco. Essas alterações indicam que o processo de edição desse modelo foi iniciado.

![Modelo editado no espaço de trabalho Gerenciamento de documentos comerciais.](./media/BDM-AddFldExcel-Workspace2.png)

## <a name="review-company-settings"></a>Revisar configurações da empresa

1.  Acesse **Administração da organização \> Organizações \> Entidades legais**.
2.  Na Guia Rápida **Informações de contato**, verifique se a URL da empresa foi inserida.

![URL da empresa inserida na página Entidades legais.](./media/BDM-AddFldExcel-CompanyInfo.png)

## <a name="generate-business-documents-to-test-the-updated-template"></a>Gerar documentos comerciais para testar o modelo atualizado

1.  No aplicativo, altere a empresa para **USMF** e Acesse **Contas a receber \> Faturas \> Todas as faturas de texto livre**.
2.  Selecione a fatura **FTI-00000002** e depois **Gerenciamento de impressão**.
3.  No painel esquerdo, expanda **Módulo - contas a receber \> Documentos \> Fatura de texto livre**.
4.  Em **Fatura de texto livre**, selecione o nível **Documento original** para especificar o escopo de faturas para processamento.
5.  No painel direito, no campo **Formato de relatório**, selecione o modelo **Fatura de texto livre (Excel) Contoso** para o nível de documento especificado.

    ![Modelo Fatura de texto livre (Excel) Contoso selecionado.](./media/BDM-AddFldExcel-PrintMngtSetting.png)

6.  Pressione **Esc** para fechar a página atual.
7.  Selecione **Imprimir \> Selecionado**.
8.  Baixe o documento gerado e abra-o no Excel.

    ![Fatura de texto livre no Excel.](./media/BDM-AddFldExcel-PreviewReport.png)

O modelo modificado é usado para gerar o relatório de fatura de texto livre para o item selecionado. Para analisar como esse relatório é afetado pelas alterações feitas no modelo, execute o relatório em uma sessão de aplicativo imediatamente depois de alterar o modelo em outra sessão de aplicativo.

## <a name="related-links"></a>Links relacionados

[Visão geral de Relatório eletrônico (ER)](general-electronic-reporting.md)

[Visão geral de gerenciamento de documentos comerciais](er-business-document-management.md)

[Criar uma configuração para gerar relatórios no formato OPENXML](tasks/er-design-reports-openxml-2016-11.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]