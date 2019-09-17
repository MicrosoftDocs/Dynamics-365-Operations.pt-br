---
title: Editar guias e modelos de integração no Dynamics 365 for Talent - Onboard
description: Este tópico explica como adicionar atividades e outras informações para guias e modelos de integração no Microsoft Dynamics 365 for Talent - Onboard.
author: andreabichsel
manager: ''
ms.date: 06/19/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: HcmCourseType, HcmCourseTypeGroup, HRMCourseTable
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Talent
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2019-06-19
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 68afc5d789d1f4af67cd2ec73eb0e073efad0761
ms.sourcegitcommit: 4ff8c2c2f3705d8045df66f2c4393253e05b49ed
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/06/2019
ms.locfileid: "1864384"
---
# <a name="edit-onboarding-guides-and-templates-in-dynamics-365-for-talent-onboard"></a><span data-ttu-id="2fdfa-103">Editar guias e modelos de integração no Dynamics 365 for Talent: Onboard</span><span class="sxs-lookup"><span data-stu-id="2fdfa-103">Edit onboarding guides and templates in Dynamics 365 for Talent: Onboard</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="2fdfa-104">Depois de criar um guia ou modelo de integração no Microsoft Dynamics 365 for Talent: Onboard, você deve adicionar uma introdução, atividades, contatos e recursos.</span><span class="sxs-lookup"><span data-stu-id="2fdfa-104">After you create an onboarding guide or template in Microsoft Dynamics 365 for Talent: Onboard, you must add an introduction, activities, contacts, and resources.</span></span> <span data-ttu-id="2fdfa-105">O Onboard permite que você inclua conteúdo avançado nos seus guias de integração, incluindo:</span><span class="sxs-lookup"><span data-stu-id="2fdfa-105">Onboard lets you include rich content in your onboarding guides, including:</span></span>

- <span data-ttu-id="2fdfa-106">Vídeos do YouTube</span><span class="sxs-lookup"><span data-stu-id="2fdfa-106">YouTube videos</span></span>
- <span data-ttu-id="2fdfa-107">Apresentações do Microsoft Sway</span><span class="sxs-lookup"><span data-stu-id="2fdfa-107">Microsoft Sway presentations</span></span>
- <span data-ttu-id="2fdfa-108">Aplicativos Microsoft PowerApps</span><span class="sxs-lookup"><span data-stu-id="2fdfa-108">Microsoft PowerApps apps</span></span>
- <span data-ttu-id="2fdfa-109">Vídeos do Microsoft Stream</span><span class="sxs-lookup"><span data-stu-id="2fdfa-109">Microsoft Stream videos</span></span>
- <span data-ttu-id="2fdfa-110">Formulários do Microsoft Forms</span><span class="sxs-lookup"><span data-stu-id="2fdfa-110">Microsoft Forms forms</span></span>
- <span data-ttu-id="2fdfa-111">Iframes que contém o conteúdo da Web</span><span class="sxs-lookup"><span data-stu-id="2fdfa-111">Iframes that contains web content</span></span>

## <a name="edit-introductions-or-activities-imported-from-a-template"></a><span data-ttu-id="2fdfa-112">Editar introduções ou atividades importados de um modelo</span><span class="sxs-lookup"><span data-stu-id="2fdfa-112">Edit introductions or activities imported from a template</span></span>

<span data-ttu-id="2fdfa-113">Se criar um guia de integração de um modelo ou importar atividades de um modelo para outro, você verá um botão **Bloquear** nas atividades importadas.</span><span class="sxs-lookup"><span data-stu-id="2fdfa-113">If you create an onboarding guide from a template, or if you import activities from one template into another, you'll notice a **Lock** button on the imported activities.</span></span> <span data-ttu-id="2fdfa-114">Elas são chamadas *atividades gerenciadas*.</span><span class="sxs-lookup"><span data-stu-id="2fdfa-114">These are called *managed activities*.</span></span>

<span data-ttu-id="2fdfa-115">[![Atividades gerenciadas](./media/onboard-edit-guide-managed-activities.png)](./media/onboard-edit-guide-managed-activities.png)</span><span class="sxs-lookup"><span data-stu-id="2fdfa-115">[![Managed activities](./media/onboard-edit-guide-managed-activities.png)](./media/onboard-edit-guide-managed-activities.png)</span></span>

<span data-ttu-id="2fdfa-116">Ao selecionar uma atividade gerenciada, você poderá ver o modelo de origem na parte superior da atividade.</span><span class="sxs-lookup"><span data-stu-id="2fdfa-116">When you select a managed activity, you can see the source template at the top of the activity.</span></span>

<span data-ttu-id="2fdfa-117">[![Origem da atividade gerenciada](./media/onboard-edit-guide-managed-activity-source.png)](./media/onboard-edit-guide-managed-activity-source.png)</span><span class="sxs-lookup"><span data-stu-id="2fdfa-117">[![Managed activity source](./media/onboard-edit-guide-managed-activity-source.png)](./media/onboard-edit-guide-managed-activity-source.png)</span></span>

<span data-ttu-id="2fdfa-118">Se você editar uma atividade em um modelo, o Onboard enviará as alterações para todos os modelos e guias não enviados que são baseados nesse modelo.</span><span class="sxs-lookup"><span data-stu-id="2fdfa-118">If you edit an activity in a template, Onboard will push the changes to all templates and unsent guides that are based on that template.</span></span> <span data-ttu-id="2fdfa-119">Se você selecionar um guia não enviado com base em um modelo editado e depois selecionar a guia **Atividades**, será exibido um aviso informando que seu guia foi alterado.</span><span class="sxs-lookup"><span data-stu-id="2fdfa-119">If you select an unsent guide based on a template you edited and then select the **Activities** tab in the guide, you will see a notice that your guide has changed.</span></span> <span data-ttu-id="2fdfa-120">Para ignorar a notificação, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="2fdfa-120">To dismiss the notification, select **OK**.</span></span> 

<span data-ttu-id="2fdfa-121">[![Alterar notificação](./media/onboard-edit-guide-change-notification.png)](./media/onboard-edit-guide-change-notification.png)</span><span class="sxs-lookup"><span data-stu-id="2fdfa-121">[![Change notification](./media/onboard-edit-guide-change-notification.png)](./media/onboard-edit-guide-change-notification.png)</span></span>

<span data-ttu-id="2fdfa-122">Você verá um ponto preto próximo às atividades atualizadas.</span><span class="sxs-lookup"><span data-stu-id="2fdfa-122">You'll see a black dot next to the updated activities.</span></span>

<span data-ttu-id="2fdfa-123">[![Atividade alterada](./media/onboard-edit-guide-changed-activity.png)](./media/onboard-edit-guide-changed-activity.png)</span><span class="sxs-lookup"><span data-stu-id="2fdfa-123">[![Changed activity](./media/onboard-edit-guide-changed-activity.png)](./media/onboard-edit-guide-changed-activity.png)</span></span>

<span data-ttu-id="2fdfa-124">Você não pode editar atividades gerenciadas fora do modelo original, exceto para adicionar um destinatário, data de vencimento ou outras informações na seção direita da atividade.</span><span class="sxs-lookup"><span data-stu-id="2fdfa-124">You can't edit managed activities outside of the original template, except to add an assignee, due date, or other information in the right-hand section of the activity.</span></span>

<span data-ttu-id="2fdfa-125">Se quiser editar uma atividade gerenciada ou se não quiser que uma atividade receba atualizações do modelo de origem, selecione o botão **Bloquear** dessa atividade.</span><span class="sxs-lookup"><span data-stu-id="2fdfa-125">If you want to edit a managed activity, or if you don't want an activity to receive updates from the template it came from, select the **Lock** button for that activity.</span></span> <span data-ttu-id="2fdfa-126">O botão **Bloquear** desaparecerá.</span><span class="sxs-lookup"><span data-stu-id="2fdfa-126">The **Lock** button will disappear.</span></span> <span data-ttu-id="2fdfa-127">A atividade não será gerenciada por método original, e não receberá mais atualizações desse modelo.</span><span class="sxs-lookup"><span data-stu-id="2fdfa-127">The activity will no longer be managed by the original template, and it will no longer receive updates from that template.</span></span> <span data-ttu-id="2fdfa-128">As atualizações feitas a uma atividade não afetarão o modelo original.</span><span class="sxs-lookup"><span data-stu-id="2fdfa-128">Updates you make to an activity do not affect the original template.</span></span>

<span data-ttu-id="2fdfa-129">Se você excluir uma atividade de um guia e enviar alterações do modelo desse guia, a atividade permanecerá excluída no guia.</span><span class="sxs-lookup"><span data-stu-id="2fdfa-129">If you delete an activity from a guide and push changes from that guide's template, the activity will remain deleted in the guide.</span></span>

> [!NOTE]
> <span data-ttu-id="2fdfa-130">Os contatos e recursos não são gerenciados por modelos.</span><span class="sxs-lookup"><span data-stu-id="2fdfa-130">Contacts and resources aren't managed by templates.</span></span> <span data-ttu-id="2fdfa-131">Além disso, as seções não são gerenciadas; portanto, se você adicionar ou editar uma seção em um modelo, as alterações não serão enviadas a nenhum guia ou modelo que use esse modelo.</span><span class="sxs-lookup"><span data-stu-id="2fdfa-131">In addition, sections aren't managed, so if you add or edit a section in a template, the changes won't be pushed to any guides or templates that use that template.</span></span>
> 
> <span data-ttu-id="2fdfa-132">Se você adicionar novas atividades a um modelo, as novas atividades serão enviadas aos guias e aos modelos baseados nesse modelo, e as novas atividades serão exibidas na parte superior.</span><span class="sxs-lookup"><span data-stu-id="2fdfa-132">If you add new activities to a template, the new activities are pushed to guides and templates based on that template, and the new activities display at the top.</span></span>

## <a name="import-activities-from-another-template"></a><span data-ttu-id="2fdfa-133">Importar atividades de outro modelo</span><span class="sxs-lookup"><span data-stu-id="2fdfa-133">Import activities from another template</span></span>

<span data-ttu-id="2fdfa-134">Você pode importar atividades de um ou mais modelos em um guia ou em um modelo.</span><span class="sxs-lookup"><span data-stu-id="2fdfa-134">You can import activities from one or more templates into a guide or template.</span></span>

1. <span data-ttu-id="2fdfa-135">Selecionar o guia ou modelo que deseja editar.</span><span class="sxs-lookup"><span data-stu-id="2fdfa-135">Select the guide or template you want to edit.</span></span>

2. <span data-ttu-id="2fdfa-136">Selecione a guia **Atividades**.</span><span class="sxs-lookup"><span data-stu-id="2fdfa-136">Select the **Activities** tab.</span></span>

3. <span data-ttu-id="2fdfa-137">Selecione a guia **Importar** na seção à direita.</span><span class="sxs-lookup"><span data-stu-id="2fdfa-137">Select the **Import** tab in the section on the right.</span></span>

   <span data-ttu-id="2fdfa-138">[![Importar atividades](./media/onboard-edit-guide-import-activities.png)](./media/onboard-edit-guide-import-activities.png)</span><span class="sxs-lookup"><span data-stu-id="2fdfa-138">[![Import activities](./media/onboard-edit-guide-import-activities.png)](./media/onboard-edit-guide-import-activities.png)</span></span>

4. <span data-ttu-id="2fdfa-139">Para visualizar as tarefas em uma nova guia de seu navegador, selecione o botão **Abrir em nova guia** em qualquer modelo.</span><span class="sxs-lookup"><span data-stu-id="2fdfa-139">To preview the tasks in a new tab in your browser, select the **Open in new tab** button on any template.</span></span>

   <span data-ttu-id="2fdfa-140">[![Importar atividades](./media/onboard-edit-guide-preview-activities.png)](./media/onboard-edit-guide-preview-activities.png)</span><span class="sxs-lookup"><span data-stu-id="2fdfa-140">[![Import activities](./media/onboard-edit-guide-preview-activities.png)](./media/onboard-edit-guide-preview-activities.png)</span></span>

5. <span data-ttu-id="2fdfa-141">Arraste e solte o modelo desejado para o local do modelo de guia em que deseja que as atividades apareçam.</span><span class="sxs-lookup"><span data-stu-id="2fdfa-141">Drag and drop the desired template to the place in your guide template where you want the activities to appear.</span></span> <span data-ttu-id="2fdfa-142">Continue editando seu guia ou modelo.</span><span class="sxs-lookup"><span data-stu-id="2fdfa-142">Continue editing your guide or template.</span></span>

<span data-ttu-id="2fdfa-143">Atividades importadas conterão um botão **Bloquear** , que indica que as atividades são gerenciadas pelo modelo que você importou.</span><span class="sxs-lookup"><span data-stu-id="2fdfa-143">The imported activities will contain a **Lock** button, which indicates those activities are managed by the template you imported from.</span></span> <span data-ttu-id="2fdfa-144">Quando você fizer alterações no modelo importado, essas atividades serão atualizadas no modelo para o qual você importou.</span><span class="sxs-lookup"><span data-stu-id="2fdfa-144">When you make changes to the template you imported, those activities will update in the template you imported them to.</span></span> <span data-ttu-id="2fdfa-145">Contudo, as alterações não serão enviadas automaticamente a nenhum guia criado do modelo importado.</span><span class="sxs-lookup"><span data-stu-id="2fdfa-145">However, the changes will not be pushed automatically to any guides created from the template you imported to.</span></span>

## <a name="push-changes-from-a-template-to-other-templates-or-guides"></a><span data-ttu-id="2fdfa-146">Enviar alterações de um modelo para outros modelos ou guias</span><span class="sxs-lookup"><span data-stu-id="2fdfa-146">Push changes from a template to other templates or guides</span></span>

<span data-ttu-id="2fdfa-147">Se você editar um modelo que contém as atividades que são usadas em outros modelos ou guias, você deve enviar as alterações, se quiser que elas apareçam em outros guias ou modelos.</span><span class="sxs-lookup"><span data-stu-id="2fdfa-147">If you edit a template that contains activities that are used in other templates or guides, you must push the changes if you want them to appear in the other templates or guides.</span></span>

<span data-ttu-id="2fdfa-148">Se você não tiver certeza se as atividades do seu modelo são usadas em outros modelos ou guias, selecione a guia **Usado em** para exibir onde as atividades serão exibidas.</span><span class="sxs-lookup"><span data-stu-id="2fdfa-148">If you're not sure whether your template's activities are used in other templates or guides, select the **Used in** tab to view where those activities appear.</span></span>

   <span data-ttu-id="2fdfa-149">[![Exibir atividades de guias e modelos usados em](./media/onboard-edit-guide-view-used-in.png)](./media/onboard-edit-guide-view-used-in.png)</span><span class="sxs-lookup"><span data-stu-id="2fdfa-149">[![View guides and templates activities are used in](./media/onboard-edit-guide-view-used-in.png)](./media/onboard-edit-guide-view-used-in.png)</span></span>

<span data-ttu-id="2fdfa-150">Para enviar as alterações:</span><span class="sxs-lookup"><span data-stu-id="2fdfa-150">To push your changes:</span></span>

1. <span data-ttu-id="2fdfa-151">Salve suas alterações selecionando o botão **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="2fdfa-151">Save your changes by selecting the **Save** button.</span></span> <span data-ttu-id="2fdfa-152">Se você não fizer isso, será solicitado que você salve as alterações na próxima etapa.</span><span class="sxs-lookup"><span data-stu-id="2fdfa-152">If you don't do this, you'll be prompted to save your changes in the next step.</span></span>

2. <span data-ttu-id="2fdfa-153">Selecione **Enviar estas alterações**.</span><span class="sxs-lookup"><span data-stu-id="2fdfa-153">Select **Push these changes**.</span></span>

   
## <a name="add-or-edit-an-introduction"></a><span data-ttu-id="2fdfa-154">Adicionar ou editar uma introdução</span><span class="sxs-lookup"><span data-stu-id="2fdfa-154">Add or edit an introduction</span></span>

1. <span data-ttu-id="2fdfa-155">Na guia **Introdução** , digite um título para o guia e uma mensagem de abertura.</span><span class="sxs-lookup"><span data-stu-id="2fdfa-155">On the **Introduction** tab, enter a title for your guide and an opening message.</span></span> <span data-ttu-id="2fdfa-156">Para usar o texto de exemplo, selecione **Usar esta mensagem**.</span><span class="sxs-lookup"><span data-stu-id="2fdfa-156">To use the sample text, select **Use this message**.</span></span>

    <span data-ttu-id="2fdfa-157">[![Guia Introdução em um modelo do Onboard](./media/onboard-template-introduction.png)](./media/onboard-template-introduction.png)</span><span class="sxs-lookup"><span data-stu-id="2fdfa-157">[![Introduction tab in an Onboard template](./media/onboard-template-introduction.png)](./media/onboard-template-introduction.png)</span></span>

2. <span data-ttu-id="2fdfa-158">Use os botões de formatação para chamar o texto, conforme necessário, ou para adicionar links ou imagens.</span><span class="sxs-lookup"><span data-stu-id="2fdfa-158">Use the formatting buttons to call out text as you require, or to add images or links.</span></span>
3. <span data-ttu-id="2fdfa-159">Selecione **Salvar** para salvar seu trabalho.</span><span class="sxs-lookup"><span data-stu-id="2fdfa-159">Select **Save** to save your work.</span></span>

## <a name="add-or-edit-activities"></a><span data-ttu-id="2fdfa-160">Adicionar ou editar atividades</span><span class="sxs-lookup"><span data-stu-id="2fdfa-160">Add or edit activities</span></span>

1. <span data-ttu-id="2fdfa-161">Na guia **Atividades** , arraste os itens da direita para a área de edição.</span><span class="sxs-lookup"><span data-stu-id="2fdfa-161">On the **Activities** tab, drag items from the right to the editing area.</span></span>
2. <span data-ttu-id="2fdfa-162">Para organizar seu guia em seções, arraste o item **Nova seção** para a área de edição e informe um nome e uma descrição opcional para a seção.</span><span class="sxs-lookup"><span data-stu-id="2fdfa-162">To organize your guide into sections, drag the **New section** item to the editing area, and enter a name and an optional description for the section.</span></span>

    ![[<span data-ttu-id="2fdfa-163">Adicionando uma nova seção a um guia ou modelo de integração</span><span class="sxs-lookup"><span data-stu-id="2fdfa-163">Adding a new section to an onboarding guide or template</span></span>](./media/onboard-edit-add-section.png)](./media/onboard-edit-add-section.png)

3. <span data-ttu-id="2fdfa-164">Para adicionar atividades para sua nova contratação concluir, arraste o item **Nova atividade** para a área de edição e insira um nome e descrição para a atividade.</span><span class="sxs-lookup"><span data-stu-id="2fdfa-164">To add activities for your new hire to complete, drag the **New activity** item to the editing area, and enter a name and description for the activity.</span></span>

    ![[<span data-ttu-id="2fdfa-165">Adicionando uma nova atividade a um guia ou modelo de integração</span><span class="sxs-lookup"><span data-stu-id="2fdfa-165">Adding a new activity to an onboarding guide or template</span></span>](./media/onboard-edit-add-activity.png)](./media/onboard-edit-add-activity.png)

4. <span data-ttu-id="2fdfa-166">Adicionar o conteúdo avançado ao seu guia de integração:</span><span class="sxs-lookup"><span data-stu-id="2fdfa-166">Add rich content to your onboarding guide:</span></span>

    - <span data-ttu-id="2fdfa-167">Para adicionar um vídeo do YouTube, arraste o item do **YouTube** para a área de edição, informe um nome e descrição para a atividade e insira o URL do vídeo do YouTube.</span><span class="sxs-lookup"><span data-stu-id="2fdfa-167">To add a YouTube video, drag the **YouTube** item to the editing area, enter a name and description for the activity, and enter the URL for the YouTube video.</span></span>
    - <span data-ttu-id="2fdfa-168">Para adicionar uma apresentação ou boletim, arraste o item **Sway** para a área de edição, informe um nome e descrição da atividade e informe o URL incorporado para a apresentação ou boletim Sway.</span><span class="sxs-lookup"><span data-stu-id="2fdfa-168">To add a Sway presentation or newsletter, drag the **Sway** item to the editing area, enter a name and description for the activity, and enter the embedded URL for the Sway presentation or newsletter.</span></span>
    - <span data-ttu-id="2fdfa-169">Para adicionar um aplicativo PowerApps, arraste o item do **PowerApps** para a área de edição, informe um nome e descrição para a atividade e selecione o aplicativo PowerApps ou informe o ID do aplicativo PowerApps.</span><span class="sxs-lookup"><span data-stu-id="2fdfa-169">To add a PowerApps app, drag the **PowerApps** item to the editing area, enter a name and description for the activity, and either select the PowerApps app or enter the PowerApps app ID.</span></span>
    - <span data-ttu-id="2fdfa-170">Para adicionar um vídeo do Microsoft Stream, arraste o item do **Microsoft Stream** para a área de edição, informe um nome e descrição para a atividade e insira o URL do vídeo do Microsoft Stream.</span><span class="sxs-lookup"><span data-stu-id="2fdfa-170">To add a Microsoft Stream video, drag the **Microsoft Stream** item to the editing area, enter a name and description for the activity, and enter the URL for the Microsoft Stream video.</span></span>
    - <span data-ttu-id="2fdfa-171">Para adicionar um form do Microsoft Forms, arraste o item do **Microsoft Forms** para a área de edição, informe um nome e uma descrição da atividade, informe o URL do formulário do Microsoft Forms e especifique o tamanho da área da tela.</span><span class="sxs-lookup"><span data-stu-id="2fdfa-171">To add a Microsoft Forms form, drag the **Microsoft Forms** item to the editing area, enter a name and description for the activity, enter the URL for the Microsoft Forms form, and specify the size of the screen area.</span></span>
    - <span data-ttu-id="2fdfa-172">Para adicionar um iframe que contém conteúdo da Web, arraste o item de **Conteúdo da Web (iframe)** para a área de edição, informe um nome e uma descrição para a atividade, informe o URL do conteúdo da Web e especifique o tamanho da área da tela.</span><span class="sxs-lookup"><span data-stu-id="2fdfa-172">To add an iframe that contains web content, drag the **Web Content (iframe)** item to the editing area, enter a name and description for the activity, enter the URL for the web content, and specify the size of the screen area.</span></span>

    ![[<span data-ttu-id="2fdfa-173">Adicionando conteúdo avançado a um guia ou modelo de integração</span><span class="sxs-lookup"><span data-stu-id="2fdfa-173">Adding rich content to an onboarding guide or template</span></span>](./media/onboard-edit-add-rich-content.png)](./media/onboard-edit-add-rich-content.png)

2. <span data-ttu-id="2fdfa-174">Opcional: na área à direita de cada atividade, atribua a atividade a uma pessoa ou função específica, adicione uma data de vencimento e pessoa de contato e atribua uma cor de categoria.</span><span class="sxs-lookup"><span data-stu-id="2fdfa-174">Optional: In the area on the right of each activity, assign the activity to a specific person or role, add a due date and contact person, and assign a category color.</span></span> <span data-ttu-id="2fdfa-175">Ao atribuir uma atividade a uma pessoa ou função, uma tarefa será criada para cada pessoa.</span><span class="sxs-lookup"><span data-stu-id="2fdfa-175">When you assign an activity to a person or role, a task is created for each individual.</span></span> <span data-ttu-id="2fdfa-176">Esta tarefa aparece no menu **Tarefas** no Onboard.</span><span class="sxs-lookup"><span data-stu-id="2fdfa-176">This task appears on the **Tasks** menu in Onboard.</span></span>

    <span data-ttu-id="2fdfa-177">[![Atribuindo uma atividade a um guia ou modelo de integração](./media/onboard-assign-activity.png)](./media/onboard-assign-activity.png)</span><span class="sxs-lookup"><span data-stu-id="2fdfa-177">[![Assigning an activity in an onboarding guide or template](./media/onboard-assign-activity.png)](./media/onboard-assign-activity.png)</span></span>

3. <span data-ttu-id="2fdfa-178">Selecione **Salvar** para salvar seu trabalho.</span><span class="sxs-lookup"><span data-stu-id="2fdfa-178">Select **Save** to save your work.</span></span>

<span data-ttu-id="2fdfa-179">Para excluir uma atividade ou seção, selecione o botão **Excluir** (o símbolo de lixeira) no canto superior direito da atividade ou da seção.</span><span class="sxs-lookup"><span data-stu-id="2fdfa-179">To delete an activity or section, select the **Delete** button (the trash can symbol) in the upper-right corner of the activity or section.</span></span>

<span data-ttu-id="2fdfa-180">Para reorganizar atividades e seções, arraste-as para um novo local.</span><span class="sxs-lookup"><span data-stu-id="2fdfa-180">To rearrange activities and sections, drag them to a new location.</span></span>

## <a name="add-or-edit-contacts"></a><span data-ttu-id="2fdfa-181">Adicionar ou editar contatos</span><span class="sxs-lookup"><span data-stu-id="2fdfa-181">Add or edit contacts</span></span>

<span data-ttu-id="2fdfa-182">Você pode adicionar pessoas de contato que podem ajudar sua nova contratação a ter sucesso desde o primeiro dia.</span><span class="sxs-lookup"><span data-stu-id="2fdfa-182">You can add contact people who can help your new hire succeed from day one.</span></span> <span data-ttu-id="2fdfa-183">Esses contatos podem ser recrutadores, colegas de equipe, companheiros de integração, mentores, administradores e equipe de suporte de TI.</span><span class="sxs-lookup"><span data-stu-id="2fdfa-183">These contacts can be recruiters, teammates, onboarding buddies, mentors, admins, and IT support staff.</span></span>

1. <span data-ttu-id="2fdfa-184">Na guia **Contatos**, selecione **Novo contato**.</span><span class="sxs-lookup"><span data-stu-id="2fdfa-184">On the **Contacts** tab, select **New contact**.</span></span>
2. <span data-ttu-id="2fdfa-185">Na caixa de diálogo **Adicionar membro da equipe**, informe o nome da pessoa de contato ou o endereço de email, informe uma descrição curta que explica como a pessoa de contato pode ajudar a nova contratação e selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="2fdfa-185">In the **Add team member** dialog box, enter the contact person's name or email address, enter a short description that explains how the contact person can help the new hire, and then select **Add**.</span></span> 

    ![[<span data-ttu-id="2fdfa-186">Adicionando contatos a um guia ou modelo de integração</span><span class="sxs-lookup"><span data-stu-id="2fdfa-186">Adding contacts to an onboarding guide or template</span></span>](./media/onboard-edit-add-contact.png)](./media/onboard-edit-add-contact.png)

    <span data-ttu-id="2fdfa-187">Se preferir, você pode selecionar um ou mais contatos em **Sugestões**.</span><span class="sxs-lookup"><span data-stu-id="2fdfa-187">Alternately, you can select one or more contacts under **Suggestions**.</span></span>

3. <span data-ttu-id="2fdfa-188">Selecione **Salvar** para salvar seu trabalho.</span><span class="sxs-lookup"><span data-stu-id="2fdfa-188">Select **Save** to save your work.</span></span>

<span data-ttu-id="2fdfa-189">Para excluir um contato, selecione o botão **Excluir** (o símbolo de lixeira) à direita do contato.</span><span class="sxs-lookup"><span data-stu-id="2fdfa-189">To delete a contact, select the **Delete** button (the trash can symbol) to the right of the contact.</span></span>

<span data-ttu-id="2fdfa-190">Para editar um contato, selecione o botão **Editar** (o símbolo de lápis) à direita do contato.</span><span class="sxs-lookup"><span data-stu-id="2fdfa-190">To edit a contact, select the **Edit** button (the pencil symbol) to the right of the contact.</span></span>

## <a name="add-or-edit-resources"></a><span data-ttu-id="2fdfa-191">Adicionar ou editar recursos</span><span class="sxs-lookup"><span data-stu-id="2fdfa-191">Add or edit resources</span></span>

<span data-ttu-id="2fdfa-192">Você pode adicionar arquivos, mapas e links úteis à seção **Recursos** de seu guia de integração.</span><span class="sxs-lookup"><span data-stu-id="2fdfa-192">You can add useful files, maps, and links to the **Resources** section of your onboarding guide.</span></span>

1. <span data-ttu-id="2fdfa-193">Na guia **Recursos**, selecione **Novo recurso**.</span><span class="sxs-lookup"><span data-stu-id="2fdfa-193">On the **Resources** tab, select **New resource**.</span></span>
2. <span data-ttu-id="2fdfa-194">Siga uma destas etapas:</span><span class="sxs-lookup"><span data-stu-id="2fdfa-194">Follow one of these steps:</span></span>

    - <span data-ttu-id="2fdfa-195">Para adicionar um arquivo, selecione a guia **Arquivo** e arraste o arquivo para a área designada.</span><span class="sxs-lookup"><span data-stu-id="2fdfa-195">To add a file, select the **File** tab, and drag the file into the designated area.</span></span> <span data-ttu-id="2fdfa-196">(Se preferir, clique em qualquer lugar nessa área para procurar o arquivo em seu computador ou selecione **Procurar OneDrive**). Informe um nome para o arquivo e selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="2fdfa-196">(Alternatively, click anywhere in that area to browse for the file on your computer, or select **Browse OneDrive**.) Enter a name for the file, and then select **Add**.</span></span>
    - <span data-ttu-id="2fdfa-197">Para adicionar um link, selecione a guia **Link**, informe um nome e endereço para o link e selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="2fdfa-197">To add a link, select the **Link** tab, enter a name and address for the link, and then select **Add**.</span></span>
    - <span data-ttu-id="2fdfa-198">Para adicionar um mapa, seleciona a guia **Mapa**, informe o nome e endereço do mapa e selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="2fdfa-198">To add a map, select the **Map** tab, enter a name and address for the map, and then select **Add**.</span></span> <span data-ttu-id="2fdfa-199">O Onboard incluirá um mapa do endereço que você especificar.</span><span class="sxs-lookup"><span data-stu-id="2fdfa-199">Onboard will include a map of the address that you specify.</span></span>

    ![[<span data-ttu-id="2fdfa-200">Adicionando um recurso a um guia ou modelo de integração</span><span class="sxs-lookup"><span data-stu-id="2fdfa-200">Adding a resource to an onboarding guide or template</span></span>](./media/onboard-edit-add-resource.png)](./media/onboard-edit-add-resource.png)

3. <span data-ttu-id="2fdfa-201">Selecione **Salvar** para salvar seu trabalho.</span><span class="sxs-lookup"><span data-stu-id="2fdfa-201">Select **Save** to save your work.</span></span>

<span data-ttu-id="2fdfa-202">Para excluir um recurso, selecione o botão **Excluir** (o símbolo de lixeira) à direita do recurso.</span><span class="sxs-lookup"><span data-stu-id="2fdfa-202">To delete a resource, select the **Delete** button (the trash can symbol) to the right of the resource.</span></span>

<span data-ttu-id="2fdfa-203">Para editar um contato, selecione o botão **Editar** (o símbolo de lápis) à direita do recurso.</span><span class="sxs-lookup"><span data-stu-id="2fdfa-203">To edit a contact, select the **Edit** button (the pencil symbol) to the right of the resource.</span></span>

## <a name="next-steps"></a><span data-ttu-id="2fdfa-204">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="2fdfa-204">Next steps</span></span>

- [<span data-ttu-id="2fdfa-205">Compartilhar conteúdo com outros contribuintes</span><span class="sxs-lookup"><span data-stu-id="2fdfa-205">Share content with other contributors</span></span>](./onboard-share-template.md)
- [<span data-ttu-id="2fdfa-206">Exibir o status de tarefas e da integração de funcionários</span><span class="sxs-lookup"><span data-stu-id="2fdfa-206">View the status of tasks and onboarding employees</span></span>](./onboard-view-status.md)
- [<span data-ttu-id="2fdfa-207">Criar equipes de contratação no Onboard</span><span class="sxs-lookup"><span data-stu-id="2fdfa-207">Create hiring teams in Onboard</span></span>](./onboard-create-team.md)

### <a name="see-also"></a><span data-ttu-id="2fdfa-208">Consulte também</span><span class="sxs-lookup"><span data-stu-id="2fdfa-208">See also</span></span>

- [<span data-ttu-id="2fdfa-209">Experimentar ou comprar o Onboard</span><span class="sxs-lookup"><span data-stu-id="2fdfa-209">Try or buy the Onboard app</span></span>](https://dynamics.microsoft.com/talent/onboard/)
- [<span data-ttu-id="2fdfa-210">Novidades</span><span class="sxs-lookup"><span data-stu-id="2fdfa-210">What's new</span></span>](./whats-new.md)
- [<span data-ttu-id="2fdfa-211">Notas de versão</span><span class="sxs-lookup"><span data-stu-id="2fdfa-211">Release notes</span></span>](https://docs.microsoft.com/business-applications-release-notes/index)
- [<span data-ttu-id="2fdfa-212">Obter suporte</span><span class="sxs-lookup"><span data-stu-id="2fdfa-212">Get support</span></span>](./talent-support.md)
