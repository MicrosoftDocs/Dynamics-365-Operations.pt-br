---
title: Atualizar a estrutura de um modelo de documento comercial
description: Este tópico explica como atualizar a estrutura de um modelo de documento comercial usando o recurso de gerenciamento de documentos comerciais.
author: NickSelin
manager: AnnBe
ms.date: 11/19/2020
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
ms.search.validFrom: 2019-12-01
ms.dyn365.ops.version: 10.0.9
ms.openlocfilehash: 09813115544701ea3fffb6be06114bcdd63c0ba0
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5570439"
---
# <a name="update-the-structure-of-a-business-document-template"></a><span data-ttu-id="b5afe-103">Atualizar a estrutura de um modelo de documento comercial</span><span class="sxs-lookup"><span data-stu-id="b5afe-103">Update the structure of a business document template</span></span> 

[!include[banner](../includes/banner.md)]

<span data-ttu-id="b5afe-104">No painel **Estrutura de modelos** do editor de modelos de [gerenciamento de documentos comerciais](er-business-document-management.md), você pode modificar um modelo de documento comercial [adicionando novos campos ](er-bdm-add-field-to-excel-template.md)a um modelo no Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="b5afe-104">In the **Template structure** pane of the [Business document management](er-business-document-management.md) template editor, you can modify a business document template by [adding new fields](er-bdm-add-field-to-excel-template.md) to a template in Microsoft Excel.</span></span> <span data-ttu-id="b5afe-105">Depois, a estrutura do modelo é atualizada automaticamente no Dynamics 365 Finance para refletir as alterações feitas no painel **Estrutura de modelos**.</span><span class="sxs-lookup"><span data-stu-id="b5afe-105">The structure of the template is then automatically updated in Dynamics 365 Finance, so that it reflects the changes that you made in the **Template structure** pane.</span></span>

<span data-ttu-id="b5afe-106">Você também pode modificar um modelo usando a funcionalidade online do Office 365.</span><span class="sxs-lookup"><span data-stu-id="b5afe-106">You can also modify a template by using Office 365 online functionality.</span></span> <span data-ttu-id="b5afe-107">Por exemplo, é possível adicionar um novo item nomeado, como uma imagem ou forma, à planilha editável.</span><span class="sxs-lookup"><span data-stu-id="b5afe-107">For example, you can add a new named item, such as a picture or shape, to the editable worksheet.</span></span> <span data-ttu-id="b5afe-108">Nesse caso, a estrutura do modelo não é atualizada automaticamente no Finance, e o item incluído não aparece no painel **Estrutura de modelos**.</span><span class="sxs-lookup"><span data-stu-id="b5afe-108">In this case, the structure of the template isn't automatically updated in Finance, and the item that you added doesn't appear in the **Template structure** pane.</span></span> <span data-ttu-id="b5afe-109">Atualize manualmente a estrutura de modelos no Finance selecionando **Atualizar estrutura** na página Editor de modelos.</span><span class="sxs-lookup"><span data-stu-id="b5afe-109">Manually update the template structure in Finance by selecting **Update structure** on the template editor page.</span></span>

<span data-ttu-id="b5afe-110">Para obter mais informações sobre esse recurso, conclua o exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="b5afe-110">For more information about this feature, complete the following example.</span></span>

## <a name="example-update-the-structure-of-a-business-document-template"></a><span data-ttu-id="b5afe-111">Exemplo: Atualizar a estrutura de um modelo de documento comercial</span><span class="sxs-lookup"><span data-stu-id="b5afe-111">Example: Update the structure of a business document template</span></span>

<span data-ttu-id="b5afe-112">Este exemplo mostra como um administrador do sistema pode atualizar a estrutura de um modelo de documento comercial no Finance após a modificação do modelo no Office Online.</span><span class="sxs-lookup"><span data-stu-id="b5afe-112">This example shows how a system administrator can update the structure of a business document template in Finance after the template is modified in Office Online.</span></span> <span data-ttu-id="b5afe-113">Veja nas seções a seguir as etapas envolvidas.</span><span class="sxs-lookup"><span data-stu-id="b5afe-113">The following sections explain the steps that are involved.</span></span>

### <a name="prepare-a-business-document-template-for-editing"></a><span data-ttu-id="b5afe-114">Preparar um modelo de documento comercial para edição</span><span class="sxs-lookup"><span data-stu-id="b5afe-114">Prepare a business document template for editing</span></span>

<span data-ttu-id="b5afe-115">Conclua os seguintes procedimentos na [visão geral de gerenciamento de documentos comerciais](er-business-document-management.md).</span><span class="sxs-lookup"><span data-stu-id="b5afe-115">Complete the following procedures in [Business document management overview](er-business-document-management.md).</span></span>

1. [<span data-ttu-id="b5afe-116">Configurar parâmetros de ER</span><span class="sxs-lookup"><span data-stu-id="b5afe-116">Configure ER parameters</span></span>](er-business-document-management.md#configure-er-parameters)
2. [<span data-ttu-id="b5afe-117">Importar soluções de ER</span><span class="sxs-lookup"><span data-stu-id="b5afe-117">Import ER solutions</span></span>](er-business-document-management.md#import-er-solutions)
3. [<span data-ttu-id="b5afe-118">Habilitar gerenciamento de documentos comerciais</span><span class="sxs-lookup"><span data-stu-id="b5afe-118">Enable Business document management</span></span>](er-business-document-management.md#enable-business-document-management)
4. [<span data-ttu-id="b5afe-119">Configurar parâmetros</span><span class="sxs-lookup"><span data-stu-id="b5afe-119">Configure parameters</span></span>](er-business-document-management.md#configure-parameters)

### <a name="edit-a-business-document-template"></a><span data-ttu-id="b5afe-120">Editar um modelo de documento comercial</span><span class="sxs-lookup"><span data-stu-id="b5afe-120">Edit a business document template</span></span>

1. <span data-ttu-id="b5afe-121">No espaço de trabalho **Gerenciamento de documentos comerciais**, selecione **Novo documento**.</span><span class="sxs-lookup"><span data-stu-id="b5afe-121">In the **Business document management** workspace, select **New document**.</span></span>
2. <span data-ttu-id="b5afe-122">Na página **Criar um novo modelo**, selecione o modelo **Fatura de texto livre (exemplo de ER) (Excel)**.</span><span class="sxs-lookup"><span data-stu-id="b5afe-122">On the **Create a new template** page, select the **Free text invoice (ER sample)(Excel)** template.</span></span>
3. <span data-ttu-id="b5afe-123">Selecione **Criar documento**.</span><span class="sxs-lookup"><span data-stu-id="b5afe-123">Select **Create document**.</span></span>
4. <span data-ttu-id="b5afe-124">No campo **Título**, insira **FTI sample Litware**.</span><span class="sxs-lookup"><span data-stu-id="b5afe-124">In the **Title** field, enter **FTI sample Litware**.</span></span>
5. <span data-ttu-id="b5afe-125">Selecione **OK** para criar o novo modelo.</span><span class="sxs-lookup"><span data-stu-id="b5afe-125">Select **OK** to create the new template.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b5afe-126">Se ainda não tiver feito login no Office Online, você será [direcionado para a página de entrada do Office 365](er-business-document-management.md#frequently-asked-questions).</span><span class="sxs-lookup"><span data-stu-id="b5afe-126">If you haven't yet signed in to Office Online, you're [directed to the Office 365 sign-in page](er-business-document-management.md#frequently-asked-questions).</span></span> <span data-ttu-id="b5afe-127">Para retornar ao seu ambiente do Finance, selecione o botão **Voltar** no navegador.</span><span class="sxs-lookup"><span data-stu-id="b5afe-127">To return to your Finance environment, select the **Back** button in your browser.</span></span>

    <span data-ttu-id="b5afe-128">O novo modelo é aberto para edição no controle incorporado do Excel Online na página Editor de modelos.</span><span class="sxs-lookup"><span data-stu-id="b5afe-128">The new template is opened for editing in the Excel Online embedded control on the template editor page.</span></span>

<span data-ttu-id="b5afe-129">[![Usando o espaço de trabalho de gerenciamento de documentos comerciais para iniciar a edição de um modelo de documento comercial](./media/er-bdm-update-structure1.gif)](./media/er-bdm-update-structure1.gif)</span><span class="sxs-lookup"><span data-stu-id="b5afe-129">[![Using the Business document management workspace to start to edit a business document template](./media/er-bdm-update-structure1.gif)](./media/er-bdm-update-structure1.gif)</span></span>

### <a name="review-the-current-structure-of-the-editable-template"></a><span data-ttu-id="b5afe-130">Analisar a estrutura atual do modelo editável</span><span class="sxs-lookup"><span data-stu-id="b5afe-130">Review the current structure of the editable template</span></span>

1. <span data-ttu-id="b5afe-131">No Excel Online, na guia **Exibição** da faixa de opções, grupo **Mostrar**, selecione **Linhas de grade**.</span><span class="sxs-lookup"><span data-stu-id="b5afe-131">In Excel Online, on the ribbon, on the **View** tab, in the **Show** group, select **Gridlines**.</span></span>
2. <span data-ttu-id="b5afe-132">No modelo editável, selecione o retângulo acima do título do modelo.</span><span class="sxs-lookup"><span data-stu-id="b5afe-132">In the editable template, select the rectangle above the template title.</span></span> <span data-ttu-id="b5afe-133">Esse retângulo é uma imagem chamada **rptHeaderCompLogo**.</span><span class="sxs-lookup"><span data-stu-id="b5afe-133">This rectangle is a picture that is named **rptHeaderCompLogo**.</span></span>
3. <span data-ttu-id="b5afe-134">Se o painel **Estrutura de modelos** estiver oculto, selecione **Mostrar estrutura**.</span><span class="sxs-lookup"><span data-stu-id="b5afe-134">If the **Template structure** pane is hidden, select **Show structure**.</span></span>
4. <span data-ttu-id="b5afe-135">No painel **Estrutura de modelos**, expanda **Relatório \> Fatura \> rptHeader \> rptHeaderPart1**.</span><span class="sxs-lookup"><span data-stu-id="b5afe-135">In the **Template structure** pane, expand **Report \> Invoice \> rptHeader \> rptHeaderPart1**.</span></span>
5. <span data-ttu-id="b5afe-136">Observe que, na estrutura de modelos no Finance, o item **rptHeaderCompLogo** tem um item filho de **Relatório \> Fatura \> rptHeader \> rptHeaderPart1**.</span><span class="sxs-lookup"><span data-stu-id="b5afe-136">Notice that, in the template structure in Finance, the **rptHeaderCompLogo** item is presented as a child item of **Report \> Invoice \> rptHeader \> rptHeaderPart1**.</span></span>

<span data-ttu-id="b5afe-137">[![Usando o espaço de trabalho de gerenciamento de documentos comerciais para analisar a estrutura atual de um modelo editável](./media/er-bdm-update-structure2.gif)](./media/er-bdm-update-structure2.gif)</span><span class="sxs-lookup"><span data-stu-id="b5afe-137">[![Using the Business document management workspace to review the current structure of an editable template](./media/er-bdm-update-structure2.gif)](./media/er-bdm-update-structure2.gif)</span></span>

### <a name="update-the-structure-of-a-business-document-template-by-deleting-a-picture"></a><span data-ttu-id="b5afe-138">Atualizar a estrutura de um modelo de documento comercial excluindo uma imagem</span><span class="sxs-lookup"><span data-stu-id="b5afe-138">Update the structure of a business document template by deleting a picture</span></span>

1. <span data-ttu-id="b5afe-139">No modelo editável do Excel Online, selecione a imagem **rptHeaderCompLogo**.</span><span class="sxs-lookup"><span data-stu-id="b5afe-139">In Excel Online, in the editable template, select the **rptHeaderCompLogo** picture.</span></span>
2. <span data-ttu-id="b5afe-140">Siga uma destas etapas para excluir a imagem selecionada do modelo editável:</span><span class="sxs-lookup"><span data-stu-id="b5afe-140">Follow one of these steps to delete the selected picture from the editable template:</span></span>

    - <span data-ttu-id="b5afe-141">Pressione a tecla **Delete** no seu teclado.</span><span class="sxs-lookup"><span data-stu-id="b5afe-141">Select the **Delete** key on your keyboard.</span></span>
    - <span data-ttu-id="b5afe-142">Selecione e segure (ou clique com o botão direito do mouse) na imagem e selecione **Recortar**.</span><span class="sxs-lookup"><span data-stu-id="b5afe-142">Select and hold (or right-click) the picture, and then select **Cut**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b5afe-143">Embora a imagem não seja mais incluída no modelo do Excel, o item **rptHeaderCompLogo** ainda é exibido na estrutura de modelos no Finance.</span><span class="sxs-lookup"><span data-stu-id="b5afe-143">The **rptHeaderCompLogo** item is currently still present in the template structure in Finance, even though the picture is no longer included in the Excel template.</span></span>

3. <span data-ttu-id="b5afe-144">Selecione **Atualizar estrutura** para sincronizar a estrutura do modelo editável no Excel e no Finance.</span><span class="sxs-lookup"><span data-stu-id="b5afe-144">Select **Update structure** to sync the structure of the editable template in Excel and Finance.</span></span>
4. <span data-ttu-id="b5afe-145">No painel **Estrutura de modelos**, expanda **Relatório \> Fatura \> rptHeader \> rptHeaderPart1**.</span><span class="sxs-lookup"><span data-stu-id="b5afe-145">In the **Template structure** pane, expand **Report \> Invoice \> rptHeader \> rptHeaderPart1**.</span></span>
5. <span data-ttu-id="b5afe-146">Observe que o item **rptHeaderCompLogo** não está mais incluído na estrutura de modelos no Finance.</span><span class="sxs-lookup"><span data-stu-id="b5afe-146">Notice that the **rptHeaderCompLogo** item is no longer included in the template structure in Finance.</span></span>

<span data-ttu-id="b5afe-147">[![Usando o espaço de trabalho de gerenciamento de documentos comerciais para excluir uma imagem de um modelo de documento comercial](./media/er-bdm-update-structure3.gif)](./media/er-bdm-update-structure3.gif)</span><span class="sxs-lookup"><span data-stu-id="b5afe-147">[![Using the Business document management workspace to delete a picture from a business document template](./media/er-bdm-update-structure3.gif)](./media/er-bdm-update-structure3.gif)</span></span>

### <a name="update-the-structure-of-a-business-document-template-by-adding-a-picture"></a><span data-ttu-id="b5afe-148">Atualizar a estrutura de um modelo de documento comercial adicionando uma imagem</span><span class="sxs-lookup"><span data-stu-id="b5afe-148">Update the structure of a business document template by adding a picture</span></span>

1. <span data-ttu-id="b5afe-149">No Excel Online, na guia **Inserir** da faixa de opções, grupo **Ilustrações**, selecione **Imagem**.</span><span class="sxs-lookup"><span data-stu-id="b5afe-149">In Excel Online, on the ribbon, on the **Insert** tab, in the **Illustrations** group, select **Picture**.</span></span>
2. <span data-ttu-id="b5afe-150">Selecione **Escolher arquivo**, procure a imagem que deseja adicionar, selecione-a e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="b5afe-150">Select **Choose file**, browse to the image that you want to add, select it, and then select **OK**.</span></span>
3. <span data-ttu-id="b5afe-151">Selecione **Inserir**.</span><span class="sxs-lookup"><span data-stu-id="b5afe-151">Select **Insert**.</span></span>
4. <span data-ttu-id="b5afe-152">Mova a nova imagem até que ela esteja no local correto.</span><span class="sxs-lookup"><span data-stu-id="b5afe-152">Move the new picture until it's in the correct place.</span></span> <span data-ttu-id="b5afe-153">O Excel nomeia a imagem por padrão.</span><span class="sxs-lookup"><span data-stu-id="b5afe-153">By default, Excel names the picture.</span></span> <span data-ttu-id="b5afe-154">Por exemplo, ele pode nomear a imagem como **Imagem 2**.</span><span class="sxs-lookup"><span data-stu-id="b5afe-154">For example, it might name the picture **Picture 2**.</span></span>
5. <span data-ttu-id="b5afe-155">Selecione **Atualizar estrutura** para sincronizar a estrutura do modelo editável no Excel e no Finance.</span><span class="sxs-lookup"><span data-stu-id="b5afe-155">Select **Update structure** to sync the structure of the editable template in Excel and Finance.</span></span>
6. <span data-ttu-id="b5afe-156">No painel **Estrutura de modelos**, expanda **Relatório \> Fatura \> rptHeader \> rptHeaderPart1**.</span><span class="sxs-lookup"><span data-stu-id="b5afe-156">In the **Template structure** pane, expand **Report \> Invoice \> rptHeader \> rptHeaderPart1**.</span></span>
7. <span data-ttu-id="b5afe-157">Observe que a nova imagem agora está incluída como um item na estrutura de modelos no Finance.</span><span class="sxs-lookup"><span data-stu-id="b5afe-157">Notice that the new picture is now included as an item in the template structure in Finance.</span></span>

<span data-ttu-id="b5afe-158">[![Usando o espaço de trabalho de gerenciamento de documentos comerciais para adicionar uma imagem a um modelo de documento comercial](./media/er-bdm-update-structure4.gif)](./media/er-bdm-update-structure4.gif)</span><span class="sxs-lookup"><span data-stu-id="b5afe-158">[![Using the Business document management workspace to add a picture to a business document template](./media/er-bdm-update-structure4.gif)](./media/er-bdm-update-structure4.gif)</span></span>

## <a name="related-links"></a><span data-ttu-id="b5afe-159">Links relacionados</span><span class="sxs-lookup"><span data-stu-id="b5afe-159">Related links</span></span>

[<span data-ttu-id="b5afe-160">Visão geral de Relatório eletrônico (ER)</span><span class="sxs-lookup"><span data-stu-id="b5afe-160">Electronic reporting (ER) overview</span></span>](general-electronic-reporting.md)

[<span data-ttu-id="b5afe-161">Visão geral de gerenciamento de documentos comerciais</span><span class="sxs-lookup"><span data-stu-id="b5afe-161">Business document management overview</span></span>](er-business-document-management.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]