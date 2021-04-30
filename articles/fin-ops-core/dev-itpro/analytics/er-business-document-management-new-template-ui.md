---
title: Interface do usuário no estilo do Microsoft Office no Gerenciamento de documentos comerciais
description: Este tópico explica como usar a nova interface de usuário no recurso Gerenciamento de documentos comerciais da estrutura do relatório eletrônico (ER).
author: v-anamir
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERBDWorkspace, ERBDParameters
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: v-anamir
ms.search.validFrom: 2019-08-01
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: e6c5081f71a18dfac83b7aea950395436b42f50e
ms.sourcegitcommit: d18d9cdb175c9d42eafbed66352c24b2aa94258b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/13/2021
ms.locfileid: "5881027"
---
# <a name="microsoft-office-style-user-interface-in-business-document-management"></a><span data-ttu-id="226df-103">Interface do usuário no estilo do Microsoft Office no Gerenciamento de documentos comerciais</span><span class="sxs-lookup"><span data-stu-id="226df-103">Microsoft Office-style user interface in Business document management</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="226df-104">O Gerenciamento de documentos comerciais permite que os usuários empresariais editem modelos de documento comercial usando um serviço do Microsoft 365 ou o aplicativo da área de trabalho apropriado do Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="226df-104">Business document management lets business users edit business document templates by using a Microsoft 365 service or the appropriate Microsoft Office desktop application.</span></span> <span data-ttu-id="226df-105">As edições podem incluir alterações de design ou novas implantações, ou os usuários podem adicionar espaços reservados para incluir dados adicionais sem precisar alterar o código-fonte.</span><span class="sxs-lookup"><span data-stu-id="226df-105">Edits might include design changes or new deployments, or users might add placeholders to include additional data without having to change the source code.</span></span> <span data-ttu-id="226df-106">Para obter mais informações sobre como trabalhar com o Gerenciamento de documentos comerciais, consulte [Visão geral do Gerenciamento de documentos comerciais](er-business-document-management.md).</span><span class="sxs-lookup"><span data-stu-id="226df-106">For more information about how to work with Business document management, see [Business document management overview](er-business-document-management.md).</span></span>

<span data-ttu-id="226df-107">A nova interface de usuário (IU) está mais clara e mais confortável para uso.</span><span class="sxs-lookup"><span data-stu-id="226df-107">The new user interface (UI) is clearer and more comfortable to use.</span></span> <span data-ttu-id="226df-108">A área **Documento comercial** mostra apenas os modelos disponíveis para o provedor atual.</span><span class="sxs-lookup"><span data-stu-id="226df-108">The **Business document** area shows only the templates that are available for the current provider.</span></span> <span data-ttu-id="226df-109">Na interface do usuário anterior, a guia **Modelo** listava todos os modelos disponíveis para qualquer fornecedor.</span><span class="sxs-lookup"><span data-stu-id="226df-109">In the previous UI, the **Template** tab listed all the templates that were available for any providers.</span></span> <span data-ttu-id="226df-110">Ela também mostrava todos os modelos criados e editados por qualquer usuário com a mesma função.</span><span class="sxs-lookup"><span data-stu-id="226df-110">It also showed all the templates that were created and edited by any user who had the same role.</span></span>

<span data-ttu-id="226df-111">Você pode usar o botão **Novo documento** para criar e editar um modelo em uma configuração de formato do ER (Relatório Eletrônico) que é fornecido por outro provedor.</span><span class="sxs-lookup"><span data-stu-id="226df-111">You can use the **New document** button to create and edit a template in an Electronic reporting (ER) format configuration that is provided by another provider.</span></span> <span data-ttu-id="226df-112">No exemplo deste tópico, o provedor é a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="226df-112">In the example in this topic, the provider is Microsoft.</span></span> <span data-ttu-id="226df-113">Outra opção é criar um modelo carregando seu próprio modelo no formato Excel.</span><span class="sxs-lookup"><span data-stu-id="226df-113">Alternatively, you can create a template by uploading your own template in Excel format.</span></span>


> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWAVQg]

<span data-ttu-id="226df-114">O vídeo [Criar um novo documento comercial usando o Gerenciamento de documentos comerciais](https://youtu.be/gAIYl-mM_pw) (mostrado acima) está incluído na [playlist do Finance and Operations](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) disponível no YouTube.</span><span class="sxs-lookup"><span data-stu-id="226df-114">The [Create a new business document using Business document management](https://youtu.be/gAIYl-mM_pw) video (shown above) is included in the [Finance and Operations playlist](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) available on YouTube.</span></span>

## <a name="make-the-new-document-ui-in-business-document-management-available"></a><span data-ttu-id="226df-115">Disponibilizar a nova interface de usuário de documento no Gerenciamento de documentos comerciais</span><span class="sxs-lookup"><span data-stu-id="226df-115">Make the new document UI in Business document management available</span></span>

<span data-ttu-id="226df-116">Para começar a usar a nova interface de usuário de documento no Gerenciamento de documentos comerciais, você deve executar o recurso **Experiência de interface de usuário semelhante à do Office para o Gerenciamento de documentos comerciais** no espaço de trabalho **Gerenciamento de recursos**.</span><span class="sxs-lookup"><span data-stu-id="226df-116">To start to use the new document UI in Business document management, you must turn on the **Office-like UI experience for Business document management** feature in the **Feature management** workspace.</span></span>

<span data-ttu-id="226df-117">Siga estas etapas a fim de ativar esse recurso para todas as entidades legais.</span><span class="sxs-lookup"><span data-stu-id="226df-117">Follow these steps to turn on this feature for all legal entities.</span></span>

1. <span data-ttu-id="226df-118">No espaço de trabalho **Gerenciamento de recursos**, na guia **Tudo**, selecione na lista o recurso **Experiência de interface de usuário semelhante à do Office para o Gerenciamento de documentos comerciais**.</span><span class="sxs-lookup"><span data-stu-id="226df-118">In the **Feature management** workspace, on the **All** tab, select the **Office-like UI experience for Business document management** feature in the list.</span></span>
2. <span data-ttu-id="226df-119">Selecione **Habilitar agora** para ativar o recurso selecionado.</span><span class="sxs-lookup"><span data-stu-id="226df-119">Select **Enable now** to turn on the selected feature.</span></span>
3. <span data-ttu-id="226df-120">Atualize a página para acessar o novo recurso.</span><span class="sxs-lookup"><span data-stu-id="226df-120">Refresh the page to access the new feature.</span></span>

## <a name="edit-templates-that-are-owned-by-other-providers"></a><span data-ttu-id="226df-121">Editar modelos que são de propriedade de outros provedores</span><span class="sxs-lookup"><span data-stu-id="226df-121">Edit templates that are owned by other providers</span></span>

1. <span data-ttu-id="226df-122">No espaço de trabalho **Gerenciamento de documentos comerciais**, selecione **Novo documento**.</span><span class="sxs-lookup"><span data-stu-id="226df-122">In the **Business document management** workspace, select **New document**.</span></span>

    ![Espaço de trabalho Gerenciamento de documentos comerciais](./media/BDM_overview_new_template1.png)

2. <span data-ttu-id="226df-124">Na guia **Selecionar**, selecione o documento a ser usado como um modelo e, depois, **Criar documento**.</span><span class="sxs-lookup"><span data-stu-id="226df-124">On the **Select** tab, select the document to use as a template, and then select **Create document**.</span></span>

    ![Caixa de diálogo Documentos comerciais](./media/BDM_overview_new_template2.png)

3. <span data-ttu-id="226df-126">Na nova caixa de diálogo, no campo **Título**, altere o título conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="226df-126">In the new dialog box, in the **Title** field, change the title as you require.</span></span> <span data-ttu-id="226df-127">O texto do título é usado para nomear a nova configuração de formato do ER criada automaticamente.</span><span class="sxs-lookup"><span data-stu-id="226df-127">The title text is used to name the new ER format configuration that is automatically created.</span></span> <span data-ttu-id="226df-128">A versão de rascunho dessa configuração (**Cópia do relatório de FTI do cliente (GER)**) conterá o modelo editado e será usada para executar esse formato de ER para o usuário atual.</span><span class="sxs-lookup"><span data-stu-id="226df-128">The draft version of this configuration (**Customer FTI report (GER) Copy**) will contain the edited template and will be used to run this ER format for the current user.</span></span> <span data-ttu-id="226df-129">O modelo original da configuração base do formato de ER será usado para executar esse formato de ER para qualquer outro usuário.</span><span class="sxs-lookup"><span data-stu-id="226df-129">The original template from the base ER format configuration will be used to run this ER format for every other user.</span></span>
4. <span data-ttu-id="226df-130">No campo **Nome**, altere o nome da primeira revisão do modelo editável que será automaticamente criado.</span><span class="sxs-lookup"><span data-stu-id="226df-130">In the **Name** field, change the name of the first revision of the editable template that will be automatically created.</span></span>
5. <span data-ttu-id="226df-131">No campo **Comentário**, atualize os comentários para a revisão do modelo editável que será automaticamente criado.</span><span class="sxs-lookup"><span data-stu-id="226df-131">In the **Comment** field, update the remarks for the revision of the editable template that will be automatically created.</span></span>
6. <span data-ttu-id="226df-132">Selecione **OK** para confirmar o início do processo de edição.</span><span class="sxs-lookup"><span data-stu-id="226df-132">Select **OK** to confirm the start of the editing process.</span></span>

    ![Caixa de diálogo Criação de documento](./media/BDM_overview_new_template3.png)

<span data-ttu-id="226df-134">O botão **Novo documento** é usado para criar e editar um modelo em uma configuração de formato do ER que é fornecido por outro provedor.</span><span class="sxs-lookup"><span data-stu-id="226df-134">The **New document** button is used to create and edit a template in an ER format configuration that is provided by another provider.</span></span> <span data-ttu-id="226df-135">Neste exemplo, o provedor é a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="226df-135">In this example, the provider is Microsoft.</span></span> <span data-ttu-id="226df-136">Ao selecionar **Novo documento**, você pode ver todos os modelos que pertencem ao provedor atual e a outros.</span><span class="sxs-lookup"><span data-stu-id="226df-136">When you select **New document**, you can view all the templates that are owned by current and other providers.</span></span> <span data-ttu-id="226df-137">Depois que você seleciona o modelo, ele é aberto para edição.</span><span class="sxs-lookup"><span data-stu-id="226df-137">After you select the template, it's opened for editing.</span></span> <span data-ttu-id="226df-138">O modelo editado será armazenado em uma nova configuração de formato de ER que é gerada automaticamente.</span><span class="sxs-lookup"><span data-stu-id="226df-138">The edited template will then be stored in a new ER format configuration that is automatically generated.</span></span>

## <a name="upload-a-template-that-uses-an-existing-excel-format"></a><span data-ttu-id="226df-139">Carregar um modelo que usa um formato Excel existente</span><span class="sxs-lookup"><span data-stu-id="226df-139">Upload a template that uses an existing Excel format</span></span>
<span data-ttu-id="226df-140">Siga estas etapas para fornecer as informações necessárias antes de carregar um modelo.</span><span class="sxs-lookup"><span data-stu-id="226df-140">Follow these steps to provide required information before you upload a template.</span></span>

1. <span data-ttu-id="226df-141">No espaço de trabalho **Gerenciamento de documentos comerciais**, selecione **Novo documento**.</span><span class="sxs-lookup"><span data-stu-id="226df-141">In the **Business document management** workspace, select **New document**.</span></span>

    ![Espaço de trabalho Gerenciamento de documentos comerciais](./media/BDM_overview_new_template1.png)
    
2. <span data-ttu-id="226df-143">Na página **Criar um novo modelo**, na guia **Carregar**, na guia **Modelo**, selecione **Procurar** para localizar e selecionar o arquivo Excel a ser usado como modelo.</span><span class="sxs-lookup"><span data-stu-id="226df-143">On the **Create a new template** page, on the **Upload** tab, on the **Template** tab, select **Browse** to find and select the Excel file that you want to use as a template.</span></span> <span data-ttu-id="226df-144">Na seção **Modelo**, os campos **Título** e **Descrição** são preenchidos automaticamente.</span><span class="sxs-lookup"><span data-stu-id="226df-144">In the **Template** section, the **Title** and **Description** fields are automatically filled in.</span></span> <span data-ttu-id="226df-145">Eles especificam o nome e a descrição da nova configuração de formato ER que é criada automaticamente.</span><span class="sxs-lookup"><span data-stu-id="226df-145">They specify the name and description of the new ER format configuration that is automatically created.</span></span> <span data-ttu-id="226df-146">Você pode editar esses campos, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="226df-146">You can edit these fields as you require.</span></span>
3. <span data-ttu-id="226df-147">Na seção **Tipo de Documento**, no campo **Nome**, especifique o tipo de documento comercial.</span><span class="sxs-lookup"><span data-stu-id="226df-147">In the **Document Type** section, in the **Name** field, specify the type of business document.</span></span> <span data-ttu-id="226df-148">Esse valor será usado para pesquisar a fonte de dados correta (ou seja, a configuração do modelo de ER).</span><span class="sxs-lookup"><span data-stu-id="226df-148">This value will be used to search the correct data source (that is, the ER model configuration).</span></span>

    ![Guia Modelo](./media/BDM_overview_new_UI_import_21.jpg)

4. <span data-ttu-id="226df-150">Na guia **Fonte de dados**, na FastTab **Filtro**, selecione **Aplicar filtro**.</span><span class="sxs-lookup"><span data-stu-id="226df-150">On the **Data source** tab, on the **Filter** FastTab, select **Apply filter**.</span></span> <span data-ttu-id="226df-151">Na seção **Fonte de dados**, o campo **Nome** é preenchido automaticamente ou você pode selecionar um valor manualmente.</span><span class="sxs-lookup"><span data-stu-id="226df-151">In the **Data source** section, the **Name** field is automatically filled in, or you can manually select a value.</span></span> <span data-ttu-id="226df-152">Você pode usar o filtro para procurar o nome da fonte de dados apropriada por nome, descrição, código do país/região e tipo de documento comercial.</span><span class="sxs-lookup"><span data-stu-id="226df-152">You can use the filter to search for the appropriate data source name by name, description, country/region code, and business document type.</span></span>

    ![Guia Fonte de dados](./media/BDM_overview_new_UI_import_31.jpg)
    
    > [!NOTE]
    > <span data-ttu-id="226df-154">A FastTab **Filtro** é usada para pesquisar a fonte de dados correta (ou seja, a configuração do modelo de ER).</span><span class="sxs-lookup"><span data-stu-id="226df-154">The **Filter** FastTab is used to search the correct data source (that is, the ER model configuration).</span></span> <span data-ttu-id="226df-155">Você pode editar todos os campos de filtro para localizar a fonte de dados mais apropriada para o documento carregado.</span><span class="sxs-lookup"><span data-stu-id="226df-155">You can edit all filter fields to find the most appropriate data source for the document that you're uploading.</span></span>
    > 
    > <span data-ttu-id="226df-156">As condições na FastTab **Filtro** são usadas como condições **OR**.</span><span class="sxs-lookup"><span data-stu-id="226df-156">The conditions on the **Filter** FastTab are used as **OR** conditions.</span></span>
    
5. <span data-ttu-id="226df-157">Na guia **Mapeamento**, selecione **Detecção automática**.</span><span class="sxs-lookup"><span data-stu-id="226df-157">On the **Mapping** tab, select **Auto detect**.</span></span> <span data-ttu-id="226df-158">O campo **Definição raiz** é preenchido automaticamente ou você pode selecionar um valor manualmente.</span><span class="sxs-lookup"><span data-stu-id="226df-158">The **Root definition** field is automatically filled in, or you can manually select a value.</span></span> <span data-ttu-id="226df-159">Esta guia mostra o mapeamento final dos elementos do modelo e o modelo.</span><span class="sxs-lookup"><span data-stu-id="226df-159">This tab shows the end mapping for the elements from the template and the model.</span></span>

    ![Guia Mapeamento](./media/BDM_overview_new_UI_import_41.jpg)
    
   > [!NOTE]
   > <span data-ttu-id="226df-161">O mapeamento na seção **Estrutura de modelos** usa a correspondência total das etiquetas ou descrições da fonte de dados no idioma do usuário e no nome da célula no modelo.</span><span class="sxs-lookup"><span data-stu-id="226df-161">The mapping in the **Template structure** section uses the full match of the labels or descriptions in the data source in the user's language, and in the cell name in the template.</span></span>

6. <span data-ttu-id="226df-162">Selecione **Criar documento** para confirmar se deseja criar um modelo e iniciar o processo de edição.</span><span class="sxs-lookup"><span data-stu-id="226df-162">Select **Create document** to confirm that you want to create a template and start the editing process.</span></span>

<span data-ttu-id="226df-163">Para obter mais informações, consulte [Visão geral do Gerenciamento de documentos comerciais](er-business-document-management.md).</span><span class="sxs-lookup"><span data-stu-id="226df-163">For more information, see [Business document management overview](er-business-document-management.md).</span></span>

<span data-ttu-id="226df-164">Se não houver um provedor de relatórios eletrônicos, você poderá criar um.</span><span class="sxs-lookup"><span data-stu-id="226df-164">If there isn't a provider in Electronic reporting, you can create one.</span></span> <span data-ttu-id="226df-165">Se não houver um provedor ativo, você poderá optar por ativar um.</span><span class="sxs-lookup"><span data-stu-id="226df-165">If there's no active provider, you can select to activate one.</span></span>

- <span data-ttu-id="226df-166">Para criar um provedor, altere o nome do provedor no campo **Nome**, atualize o endereço na Internet do novo provedor no campo **Endereço na Internet** e selecione **OK** para confirmar.</span><span class="sxs-lookup"><span data-stu-id="226df-166">To create a provider, change the name of the provider in the **Name** field, update the internet address of the new provider in the **Internet address** field, and select **OK** to confirm.</span></span>

    ![Criar novo provedor em BDM](./media/bdm_create_provider.png)
    
- <span data-ttu-id="226df-168">Para ativar o provedor existente, escolha o nome do provedor no campo **Provedor de configuração** e selecione **OK** para definir o provedor como ativo.</span><span class="sxs-lookup"><span data-stu-id="226df-168">To activate existing provider, choose the name of the provider in the **Configuration provider** field, and select **OK** to set provider as active.</span></span>

    ![Ativar provedor em BDM](./media/bdm_choose_provider.png)

> [!NOTE]
> <span data-ttu-id="226df-170">Cada modelo de BDM se refere ao fornecedor como o autor da configuração.</span><span class="sxs-lookup"><span data-stu-id="226df-170">Each BDM template refers to the provider as the author of the configuration.</span></span> <span data-ttu-id="226df-171">É por isso que um provedor ativo é necessário para o modelo.</span><span class="sxs-lookup"><span data-stu-id="226df-171">This is why an active provider is required for the template.</span></span>

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
