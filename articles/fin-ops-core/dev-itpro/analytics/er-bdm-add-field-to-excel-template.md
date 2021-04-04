---
title: Adicionar novos campos a um modelo de documento comercial no Microsoft Excel
description: Este tópico fornece informações sobre como adicionar novos campos a um modelo de documento comercial no Microsoft Excel usando o recurso de gerenciamento de documentos comerciais.
author: NickSelin
manager: AnnBe
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
ms.openlocfilehash: 6368d763f44c015a6e85652b1880cfd86ff5ba09
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5569012"
---
# <a name="add-new-fields-to-a-business-document-template-in-microsoft-excel"></a><span data-ttu-id="0b26e-103">Adicionar novos campos a um modelo de documento comercial no Microsoft Excel</span><span class="sxs-lookup"><span data-stu-id="0b26e-103">Add new fields to a business document template in Microsoft Excel</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="0b26e-104">Você pode adicionar novos campos a um modelo usado para gerar documentos comerciais no formato do Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="0b26e-104">You can add new fields to a template that is used to generate business documents in Microsoft Excel format.</span></span> <span data-ttu-id="0b26e-105">Esses campos podem ser adicionados como espaços reservados que são utilizados para preencher os documentos gerados com as informações necessárias ao aplicativo.</span><span class="sxs-lookup"><span data-stu-id="0b26e-105">These fields can be added as placeholders that are used to fill generated documents with required information from the application.</span></span> <span data-ttu-id="0b26e-106">Para cada campo adicionado, você também pode especificar uma associação às fontes de dados para especificar quais dados do aplicativo serão inseridos no campo quando o modelo é usado para gerar documentos comerciais.</span><span class="sxs-lookup"><span data-stu-id="0b26e-106">For every field that you add, you can also specify a binding to the data sources, to specify what application data will be entered in the field when the template is used to generate business documents.</span></span>

<span data-ttu-id="0b26e-107">Para saber mais sobre este recurso, conclua o exemplo neste tópico.</span><span class="sxs-lookup"><span data-stu-id="0b26e-107">To learn more about this feature, complete the example in this topic.</span></span> <span data-ttu-id="0b26e-108">Esse exemplo mostra como atualizar um modelo para preencher os campos nos formulários de fatura de texto livre que são gerados.</span><span class="sxs-lookup"><span data-stu-id="0b26e-108">This example shows how to update a template to fill in the fields in free text invoice forms that are generated.</span></span>

## <a name="configure-business-document-management-to-edit-templates"></a><span data-ttu-id="0b26e-109">Configurar o Gerenciamento de documentos comerciais para editar modelos</span><span class="sxs-lookup"><span data-stu-id="0b26e-109">Configure Business document management to edit templates</span></span>

<span data-ttu-id="0b26e-110">Como o BDM (Gerenciamento de documentos comerciais) foi criado com base na estrutura [Visão geral de ER (Relatórios eletrônicos)](general-electronic-reporting.md), você deve configurar os parâmetros necessários de ER e BDM antes de poder iniciar o trabalho com o BDM.</span><span class="sxs-lookup"><span data-stu-id="0b26e-110">Because Business document management (BDM) is built on top of the [Electronic reporting (ER) overview](general-electronic-reporting.md) framework, you must configure the required ER and BDM parameters before you can start to work with BDM.</span></span>

1.  <span data-ttu-id="0b26e-111">Entre na instância do Microsoft Dynamics 365 Finance como o administrador de sistema.</span><span class="sxs-lookup"><span data-stu-id="0b26e-111">Sign in to the instance of Microsoft Dynamics 365 Finance as the system administrator.</span></span>
2.  <span data-ttu-id="0b26e-112">Conclua as etapas a seguir do exemplo no tópico [Visão geral do Gerenciamento de documentos comerciais](er-business-document-management.md):</span><span class="sxs-lookup"><span data-stu-id="0b26e-112">Complete the following steps of the example in the [Business document management overview](er-business-document-management.md) topic:</span></span>

    1.  <span data-ttu-id="0b26e-113">Configure os parâmetros de ER.</span><span class="sxs-lookup"><span data-stu-id="0b26e-113">Configure ER parameters.</span></span>
    2.  <span data-ttu-id="0b26e-114">Ative o BDM.</span><span class="sxs-lookup"><span data-stu-id="0b26e-114">Turn on BDM.</span></span>

<span data-ttu-id="0b26e-115">Agora você pode começar a usar o BDM para editar modelos de documento comercial.</span><span class="sxs-lookup"><span data-stu-id="0b26e-115">You can now start to use BDM to edit business document templates.</span></span>

## <a name="import-er-solutions-that-contain-a-template"></a><span data-ttu-id="0b26e-116">Importar soluções de ER que contêm um modelo</span><span class="sxs-lookup"><span data-stu-id="0b26e-116">Import ER solutions that contain a template</span></span>

<span data-ttu-id="0b26e-117">O exemplo neste procedimento usa a solução de ER oficialmente publicada.</span><span class="sxs-lookup"><span data-stu-id="0b26e-117">The example in this procedure uses the officially published ER solution.</span></span> <span data-ttu-id="0b26e-118">Você deve importar as configurações de ER dessa solução na sua instância atual do Finance.</span><span class="sxs-lookup"><span data-stu-id="0b26e-118">You must import the ER configurations of this solution into your current instance of Finance.</span></span>

<span data-ttu-id="0b26e-119">A configuração de formato de ER **Fatura de texto livre (Excel)** dessa solução contém o modelo de documento comercial no formato do Excel que pode ser editado usando o BDM.</span><span class="sxs-lookup"><span data-stu-id="0b26e-119">The **Free text invoice (Excel)** ER format configuration of this solution contains the business document template in Excel format that can be edited by using BDM.</span></span> <span data-ttu-id="0b26e-120">Importe a versão mais recente dessa configuração de formato de ER do Microsoft Dynamics Lifecycle Service (LCS).</span><span class="sxs-lookup"><span data-stu-id="0b26e-120">Import the latest version of this ER format configuration from Microsoft Dynamics Lifecycle Service (LCS).</span></span> <span data-ttu-id="0b26e-121">As configurações do modelo de dados de ER e do mapeamento do modelo de ER correspondentes serão importadas automaticamente.</span><span class="sxs-lookup"><span data-stu-id="0b26e-121">The corresponding ER data model and ER model mapping configurations will be imported automatically.</span></span>

<span data-ttu-id="0b26e-122">Para obter mais informações sobre como importar configurações de ER, consulte [Gerenciar o ciclo de vida da configuração de ER](general-electronic-reporting-manage-configuration-lifecycle.md).</span><span class="sxs-lookup"><span data-stu-id="0b26e-122">For more information about how to import ER configurations, see [Manage the ER configuration lifecycle](general-electronic-reporting-manage-configuration-lifecycle.md).</span></span>

![LCS Página Biblioteca de ativos compartilhados](./media/BDM-AddFldExcel-LCS.png)

### <a name="edit-the-er-solution-template"></a><span data-ttu-id="0b26e-124">Editar o modelo de solução de ER</span><span class="sxs-lookup"><span data-stu-id="0b26e-124">Edit the ER solution template</span></span>

1.  <span data-ttu-id="0b26e-125">Entre como um usuário com acesso ao espaço de trabalho **Gerenciamento de documentos comerciais**.</span><span class="sxs-lookup"><span data-stu-id="0b26e-125">Sign in as a user who has access to the **Business document management** workspace.</span></span>
2.  <span data-ttu-id="0b26e-126">Abra o espaço de trabalho **Gerenciamento de documentos comerciais**.</span><span class="sxs-lookup"><span data-stu-id="0b26e-126">Open the **Business document management** workspace.</span></span>

    ![Espaço de trabalho Gerenciamento de documentos comerciais](./media/BDM-AddFldExcel-Workspace.png)

3.  <span data-ttu-id="0b26e-128">Na grade, selecione o modelo **Fatura de texto livre (Excel)**.</span><span class="sxs-lookup"><span data-stu-id="0b26e-128">In the grid, select the **Free text invoice (Excel)** template.</span></span>
4.  <span data-ttu-id="0b26e-129">No painel direito, selecione **Novo modelo** para criar um novo modelo baseado no modelo selecionado.</span><span class="sxs-lookup"><span data-stu-id="0b26e-129">In the right pane, select **New template** to create a new template that is based on the selected template.</span></span>
5.  <span data-ttu-id="0b26e-130">No campo **Título** , insira **Fatura de texto livre (Excel) Contoso** como o título do novo modelo.</span><span class="sxs-lookup"><span data-stu-id="0b26e-130">In the **Title** field, enter **Free text invoice (Excel) Contoso** as the title of the new template.</span></span>
6.  <span data-ttu-id="0b26e-131">Selecione **OK** para confirmar o início do processo de edição.</span><span class="sxs-lookup"><span data-stu-id="0b26e-131">Select **OK** to confirm the start of the editing process.</span></span>

<span data-ttu-id="0b26e-132">A página do editor de modelo de BDM aparece.</span><span class="sxs-lookup"><span data-stu-id="0b26e-132">The BDM template editor page appears.</span></span> <span data-ttu-id="0b26e-133">Você pode usar o Microsoft 365 para editar o modelo online selecionado no controle inserido.</span><span class="sxs-lookup"><span data-stu-id="0b26e-133">You can use Microsoft 365 to edit the selected template online in the embedded control.</span></span>

![Página do editor de modelo de BDM](./media/BDM-AddFldExcel-EditableTemplate.png)

### <a name="add-the-label-for-a-new-field-to-the-template"></a><span data-ttu-id="0b26e-135">Adicionar o rótulo para um novo campo ao modelo</span><span class="sxs-lookup"><span data-stu-id="0b26e-135">Add the label for a new field to the template</span></span>

1.  <span data-ttu-id="0b26e-136">Na página do editor de modelo de BDM, na faixa de opções do Excel, na guia **Exibir** , marque as caixas de seleção **Cabeçalhos e Linhas de Grade** para o modelo editável do Excel.</span><span class="sxs-lookup"><span data-stu-id="0b26e-136">On the BDM template editor page, on the Excel ribbon, on the **View** tab, select the **Headings and Gridlines** check boxes for the editable Excel template.</span></span>

    ![Caixas de seleção Cabeçalhos e Linhas de Grade marcadas](./media/BDM-AddFldExcel-EditableTemplate2.png)

2.  <span data-ttu-id="0b26e-138">Selecione as células **E8:F8**.</span><span class="sxs-lookup"><span data-stu-id="0b26e-138">Select cells **E8:F8**.</span></span>
3.  <span data-ttu-id="0b26e-139">Na faixa de opções do Excel, na guia **Início**, selecione **Mesclar e Centralizar** para mesclar as células selecionadas em uma nova célula mesclada **E8:F8**.</span><span class="sxs-lookup"><span data-stu-id="0b26e-139">On the Excel ribbon, on the **Home** tab, select **Merge & Center** to merge the selected cells into a new merged **E8:F8** cell.</span></span>
4.  <span data-ttu-id="0b26e-140">Na célula mesclada **E8:F8**, insira **URL**.</span><span class="sxs-lookup"><span data-stu-id="0b26e-140">In the merged cell **E8:F8**, enter **URL**.</span></span>
5.  <span data-ttu-id="0b26e-141">Selecione a célula mesclada **E7:F7**, selecione **Pintor de formato** e depois selecione a célula mesclada **E8:F8** para formatá-la da mesma forma do que a célula mesclada **E7:F7**.</span><span class="sxs-lookup"><span data-stu-id="0b26e-141">Select merged cell **E7:F7**, select **Format painter**, and then select merged cell **E8:F8** to format it in the same way as merged cell **E7:F7**.</span></span>

    ![Novo rótulo de campo adicionado ao modelo](./media/BDM-AddFldExcel-EditableTemplate3.png)

### <a name="format-the-template-to-reserve-space-for-a-new-field"></a><span data-ttu-id="0b26e-143">Formatar o modelo para reservar o espaço para um novo campo</span><span class="sxs-lookup"><span data-stu-id="0b26e-143">Format the template to reserve space for a new field</span></span>

1.  <span data-ttu-id="0b26e-144">Na página do editor de modelo de BDM, selecione a célula mesclada **G8:H8**.</span><span class="sxs-lookup"><span data-stu-id="0b26e-144">On the BDM template editor page, select merged cell **G8:H8**.</span></span>
2.  <span data-ttu-id="0b26e-145">Na faixa de opções do Excel, na guia **Início**, selecione **Mesclar e Centralizar** para mesclar as células selecionadas em uma nova célula mesclada **G8:H8**.</span><span class="sxs-lookup"><span data-stu-id="0b26e-145">On the Excel ribbon, on the **Home** tab, select **Merge & Center** to merge the selected cells into a new merged **G8:H8** cell.</span></span>
3.  <span data-ttu-id="0b26e-146">Selecione a célula mesclada **G7:H7**, selecione **Pintor de formato** e depois selecione a célula mesclada **G8:H8** para formatá-la da mesma forma do que a célula mesclada **G7:H7**.</span><span class="sxs-lookup"><span data-stu-id="0b26e-146">Select merged cell **G7:H7**, select **Format painter**, and then select merged cell **G8:H8** to format it in the same way as merged cell **G7:H7**.</span></span>

    ![Espaço reservado para o novo campo](./media/BDM-AddFldExcel-EditableTemplate4.png)

4.  <span data-ttu-id="0b26e-148">No campo da caixa **Nome** , selecione **CompanyInfo**.</span><span class="sxs-lookup"><span data-stu-id="0b26e-148">In the **Name** box field, select **CompanyInfo**.</span></span>

    <span data-ttu-id="0b26e-149">O intervalo **CompanyInfo** do modelo atual do Excel contém todos os campos usados para preencher o cabeçalho de um relatório gerado com os detalhes da empresa atual como um participante de vendedor.</span><span class="sxs-lookup"><span data-stu-id="0b26e-149">The **CompanyInfo** range of the current Excel template holds all the fields that are used to fill the header of a generated report with the details of the current company as a seller party.</span></span>

    ![Intervalo de CompanyInfo selecionado](./media/BDM-AddFldExcel-SelectCompanyInfoRange.png)

### <a name="add-a-new-field-to-the-template"></a><span data-ttu-id="0b26e-151">Adicionar um novo campo ao modelo</span><span class="sxs-lookup"><span data-stu-id="0b26e-151">Add a new field to the template</span></span>

1.  <span data-ttu-id="0b26e-152">Na página **Editor de modelo de BDM**, no Painel de Ação, selecione **Mostrar formato**.</span><span class="sxs-lookup"><span data-stu-id="0b26e-152">On the **BDM template editor** page, on the Action Pane, select **Show format**.</span></span>
2.  <span data-ttu-id="0b26e-153">No painel **Estrutura do modelo** , selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="0b26e-153">In the **Template structure** pane, select **Add**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0b26e-154">Você deverá ajustar a seção do modelo que você deseja usar como um novo campo.</span><span class="sxs-lookup"><span data-stu-id="0b26e-154">You must adjust the section of the template that you want to use as a new field.</span></span> <span data-ttu-id="0b26e-155">Você já fez esse ajuste ao formatar a célula mesclada **G8:H8**.</span><span class="sxs-lookup"><span data-stu-id="0b26e-155">You already made this adjustment by formatting merged cell **G8:H8**.</span></span>

    ![Adição de um novo campo ao modelo](./media/BDM-AddFldExcel-AddCell.png)

3.  <span data-ttu-id="0b26e-157">Selecione **Excel\Célula** para adicionar um novo campo como uma célula no modelo.</span><span class="sxs-lookup"><span data-stu-id="0b26e-157">Select **Excel\Cell** to add a new field as a cell in the template.</span></span>

    <span data-ttu-id="0b26e-158">Você pode selecionar **Excel\Intervalo** se desejar adicionar um novo intervalo ao modelo.</span><span class="sxs-lookup"><span data-stu-id="0b26e-158">You can select **Excel\Range** if you want to add a new range to the template.</span></span> <span data-ttu-id="0b26e-159">O intervalo inserido pode conter várias células.</span><span class="sxs-lookup"><span data-stu-id="0b26e-159">The range that is entered can contain multiple cells.</span></span> <span data-ttu-id="0b26e-160">Você pode adicionar essas células posteriormente.</span><span class="sxs-lookup"><span data-stu-id="0b26e-160">You can add these cells later.</span></span>
    
    <span data-ttu-id="0b26e-161">Observe que o componente do modelo **CompanyInfo** está selecionado automaticamente no painel **Estrutura do modelo** já que é o componente principal mais apropriado na estrutura do modelo atual para o campo que você está adicionando.</span><span class="sxs-lookup"><span data-stu-id="0b26e-161">Notice that the **CompanyInfo** template component, is automatically selected in the **Template structure** pane, because it's the most suitable parent component in the current template structure for the field that you're adding.</span></span>
    
4.  <span data-ttu-id="0b26e-162">No campo **Intervalo do Excel**, insira **CompanyURL_Value**.</span><span class="sxs-lookup"><span data-stu-id="0b26e-162">In the **Excel range** field, enter **CompanyURL_Value**.</span></span>
5.  <span data-ttu-id="0b26e-163">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="0b26e-163">Select **OK**.</span></span>

    ![Campo CompanyURL_Value adicionado à estrutura do modelo](./media/BDM-AddFldExcel-EditableTemplate5.png)

6.  <span data-ttu-id="0b26e-165">No painel **Estrutura do modelo**, selecione o botão de reticências (...) e depois selecione **Mostrar associações**.</span><span class="sxs-lookup"><span data-stu-id="0b26e-165">In the **Template structure** pane, select the ellipsis button (...), and then select **Show bindings**.</span></span>

    ![Mostrar associações selecionadas](./media/BDM-AddFldExcel-ShowBindings.png)

    <span data-ttu-id="0b26e-167">O painel **Estrutura do modelo** agora mostra as fontes de dados disponíveis no formato de ER subjacente.</span><span class="sxs-lookup"><span data-stu-id="0b26e-167">The **Template structure** pane now shows the data sources that are available in the underlying ER format.</span></span>

7.  <span data-ttu-id="0b26e-168">Selecione **CompanyInfo_Value** como o campo que você planeja associar a uma fonte de dados do formato de ER subjacente.</span><span class="sxs-lookup"><span data-stu-id="0b26e-168">Select **CompanyInfo_Value** as the field that you plan to bind to a data source of the underlying ER format.</span></span>
8.  <span data-ttu-id="0b26e-169">Na seção **Fontes de dados** do painel **Estrutura do modelo**, expanda **Modelo \> InvoiceBase \> CompanyInfo**.</span><span class="sxs-lookup"><span data-stu-id="0b26e-169">In the **Data sources** section of the **Template structure** pane, expand **Model \> InvoiceBase \> CompanyInfo**.</span></span>
9.  <span data-ttu-id="0b26e-170">Em **CompanyInfo**, selecione o item **WebsiteURI**.</span><span class="sxs-lookup"><span data-stu-id="0b26e-170">Under **CompanyInfo**, select the **WebsiteURI** item.</span></span>

    ![Item WebsiteURI selecionado](./media/BDM-AddFldExcel-BindURL.png)

10. <span data-ttu-id="0b26e-172">Selecione **Associar**.</span><span class="sxs-lookup"><span data-stu-id="0b26e-172">Select **Bind**.</span></span>
11. <span data-ttu-id="0b26e-173">No painel **Estrutura do modelo**, selecione **Salvar** e depois feche a página do editor de modelo de BDM.</span><span class="sxs-lookup"><span data-stu-id="0b26e-173">In the **Template structure** pane, select **Save**, and then close the BDM template editor page.</span></span>

<span data-ttu-id="0b26e-174">No espaço de trabalho **Gerenciamento de documentos comerciais**, a guia **Modelo** no painel direito mostra o modelo atualizado.</span><span class="sxs-lookup"><span data-stu-id="0b26e-174">In the **Business document management** workspace, the **Template** tab in the right pane shows the updated template.</span></span> <span data-ttu-id="0b26e-175">Na grade, observe que o campo **Status** do modelo editado foi alterado para **Rascunho** e o campo **Revisão** não estará mais em branco.</span><span class="sxs-lookup"><span data-stu-id="0b26e-175">In the grid, notice that the **Status** field for the edited template has been changed to **Draft**, and the **Revision** field is no longer blank.</span></span> <span data-ttu-id="0b26e-176">Essas alterações indicam que o processo de edição desse modelo foi iniciado.</span><span class="sxs-lookup"><span data-stu-id="0b26e-176">These changes indicate that the process of editing this template has been started.</span></span>

![Modelo editado no espaço de trabalho Gerenciamento de documentos comerciais](./media/BDM-AddFldExcel-Workspace2.png)

## <a name="review-company-settings"></a><span data-ttu-id="0b26e-178">Revisar configurações da empresa</span><span class="sxs-lookup"><span data-stu-id="0b26e-178">Review company settings</span></span>

1.  <span data-ttu-id="0b26e-179">Vá para **Administração da organização \> Organizações \> Entidades legais**.</span><span class="sxs-lookup"><span data-stu-id="0b26e-179">Go to **Organization administration \> Organizations \> Legal entities**.</span></span>
2.  <span data-ttu-id="0b26e-180">Na Guia Rápida **Informações de contato**, verifique se a URL da empresa foi inserida.</span><span class="sxs-lookup"><span data-stu-id="0b26e-180">On the **Contact information** FastTab, verify that the company URL is entered.</span></span>

![URL da empresa inserida na página Entidades legais](./media/BDM-AddFldExcel-CompanyInfo.png)

## <a name="generate-business-documents-to-test-the-updated-template"></a><span data-ttu-id="0b26e-182">Gerar documentos comerciais para testar o modelo atualizado</span><span class="sxs-lookup"><span data-stu-id="0b26e-182">Generate business documents to test the updated template</span></span>

1.  <span data-ttu-id="0b26e-183">No aplicativo, altere a empresa para **USMF** e vá para **Contas a receber \> Faturas \> Todas as faturas de texto livre**.</span><span class="sxs-lookup"><span data-stu-id="0b26e-183">In the application, change the company to **USMF**, and go to **Accounts receivable \> Invoices \> All free text invoices**.</span></span>
2.  <span data-ttu-id="0b26e-184">Selecione a fatura **FTI-00000002** e depois **Gerenciamento de impressão**.</span><span class="sxs-lookup"><span data-stu-id="0b26e-184">Select invoice **FTI-00000002**, and then select **Print management**.</span></span>
3.  <span data-ttu-id="0b26e-185">No painel esquerdo, expanda **Módulo - contas a receber \> Documentos \> Fatura de texto livre**.</span><span class="sxs-lookup"><span data-stu-id="0b26e-185">In the left pane, expand **Module - accounts receivable \> Documents \> Free text invoice**.</span></span>
4.  <span data-ttu-id="0b26e-186">Em **Fatura de texto livre**, selecione o nível **Documento original** para especificar o escopo de faturas para processamento.</span><span class="sxs-lookup"><span data-stu-id="0b26e-186">Under **Free text invoice**, select the **Original document** level to specify the scope of invoices for processing.</span></span>
5.  <span data-ttu-id="0b26e-187">No painel direito, no campo **Formato de relatório**, selecione o modelo **Fatura de texto livre (Excel) Contoso** para o nível de documento especificado.</span><span class="sxs-lookup"><span data-stu-id="0b26e-187">In the right pane, in the **Report format** field, select the **Free text invoice (Excel) Contoso** template for the specified document level.</span></span>

    ![Modelo Fatura de texto livre (Excel) Contoso selecionado](./media/BDM-AddFldExcel-PrintMngtSetting.png)

6.  <span data-ttu-id="0b26e-189">Pressione **Esc** para fechar a página atual.</span><span class="sxs-lookup"><span data-stu-id="0b26e-189">Press **Esc** to close the current page.</span></span>
7.  <span data-ttu-id="0b26e-190">Selecione **Imprimir \> Selecionado**.</span><span class="sxs-lookup"><span data-stu-id="0b26e-190">Select **Print \> Selected**.</span></span>
8.  <span data-ttu-id="0b26e-191">Baixe o documento gerado e abra-o no Excel.</span><span class="sxs-lookup"><span data-stu-id="0b26e-191">Download the generated document, and open it in Excel.</span></span>

    ![Fatura de texto livre no Excel](./media/BDM-AddFldExcel-PreviewReport.png)

<span data-ttu-id="0b26e-193">O modelo modificado é usado para gerar o relatório de fatura de texto livre para o item selecionado.</span><span class="sxs-lookup"><span data-stu-id="0b26e-193">The modified template is used to generate the free text invoice report for the selected item.</span></span> <span data-ttu-id="0b26e-194">Para analisar como esse relatório é afetado pelas alterações feitas no modelo, execute o relatório em uma sessão de aplicativo imediatamente depois de alterar o modelo em outra sessão de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="0b26e-194">To analyze how this report is affected by changes that you make to the template, run the report in one application session immediately after you change the template in another application session.</span></span>

## <a name="related-links"></a><span data-ttu-id="0b26e-195">Links relacionados</span><span class="sxs-lookup"><span data-stu-id="0b26e-195">Related links</span></span>

[<span data-ttu-id="0b26e-196">Visão geral de Relatório eletrônico (ER)</span><span class="sxs-lookup"><span data-stu-id="0b26e-196">Electronic reporting (ER) overview</span></span>](general-electronic-reporting.md)

[<span data-ttu-id="0b26e-197">Visão geral de gerenciamento de documentos comerciais</span><span class="sxs-lookup"><span data-stu-id="0b26e-197">Business document management overview</span></span>](er-business-document-management.md)

[<span data-ttu-id="0b26e-198">Criar uma configuração para gerar relatórios no formato OPENXML</span><span class="sxs-lookup"><span data-stu-id="0b26e-198">Design a configuration for generating reports in OPENXML format</span></span>](tasks/er-design-reports-openxml-2016-11.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]