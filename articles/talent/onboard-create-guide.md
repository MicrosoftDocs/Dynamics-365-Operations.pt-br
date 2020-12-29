---
title: Criar e enviar um guia de integração usando o Dynamics 365 Talent - Onboard
description: Este tópico explica como usar o aplicativo Microsoft Dynamics 365 Talent - Onboard para criar um guia de integração para suas novas contratações. Esta tarefa é uma etapa inicial essencial em uma estratégia de contratação até a demissão do gerenciamento de capital humano (HCM).
author: andreabichsel
manager: ''
ms.date: 05/02/2019
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
ms.search.validFrom: 2019-05-06
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 2371d86165390503312c2848842acf4745a8ed7a
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4460306"
---
# <a name="create-and-send-an-onboarding-guide"></a><span data-ttu-id="ba090-104">Criar e enviar uma guia de integração</span><span class="sxs-lookup"><span data-stu-id="ba090-104">Create and send an onboarding guide</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="ba090-105">O Microsoft Dynamics 365 Talent: Onboard permite criar guias de integração por meio de modelos que você mesmo criou, de modelos disponíveis em uma galeria ou do zero.</span><span class="sxs-lookup"><span data-stu-id="ba090-105">Microsoft Dynamics 365 Talent: Onboard lets you create onboarding guides from templates that you created yourself, from templates that are available in a gallery, or from scratch.</span></span>

<span data-ttu-id="ba090-106">Após criar um guia de integração, você pode enviá-lo para uma nova contratação.</span><span class="sxs-lookup"><span data-stu-id="ba090-106">After you've created an onboarding guide, you can send it to a new hire.</span></span> <span data-ttu-id="ba090-107">Como alternativa, você pode enviá-lo a várias novas contratações especificadas em um arquivo do Microsoft Excel que você baixa do aplicativo Onboard.</span><span class="sxs-lookup"><span data-stu-id="ba090-107">Alternatively, you can send it to multiple new hires that you specify in a Microsoft Excel file that you download from the Onboard app.</span></span>

## <a name="create-an-onboarding-guide-from-a-template-and-send-it-to-a-single-new-hire"></a><span data-ttu-id="ba090-108">Criar um guia de integração por meio de um modelo e enviá-lo para uma única nova contratação</span><span class="sxs-lookup"><span data-stu-id="ba090-108">Create an onboarding guide from a template and send it to a single new hire</span></span>

1. <span data-ttu-id="ba090-109">No menu esquerdo, selecione **Modelos**.</span><span class="sxs-lookup"><span data-stu-id="ba090-109">On the left menu, select **Templates**.</span></span>
2. <span data-ttu-id="ba090-110">Em **Meus modelos**, selecione o modelo que deseja configurar como um guia de integração para a nova contratação.</span><span class="sxs-lookup"><span data-stu-id="ba090-110">Under **My templates**, select the template that you want to set up as an onboarding guide for the new hire.</span></span>
3. <span data-ttu-id="ba090-111">Edite o modelo como desejar.</span><span class="sxs-lookup"><span data-stu-id="ba090-111">Edit the template as you desire.</span></span> <span data-ttu-id="ba090-112">Lembre-se de salvar seu trabalho conforme progredir.</span><span class="sxs-lookup"><span data-stu-id="ba090-112">Be sure to save your work as you go.</span></span>
4. <span data-ttu-id="ba090-113">Quando concluir a edição do modelo, selecione **Criar guia**.</span><span class="sxs-lookup"><span data-stu-id="ba090-113">When you've finished editing the template, select **Create guide**.</span></span>

    <span data-ttu-id="ba090-114">[![Criar um guia de integração por meio de um modelo](./media/onboard-create-guide.png)](./media/onboard-create-guide.png)</span><span class="sxs-lookup"><span data-stu-id="ba090-114">[![Creating an onboarding guide from a template](./media/onboard-create-guide.png)](./media/onboard-create-guide.png)</span></span>

5. <span data-ttu-id="ba090-115">Na janela **Criar um guia**, em **Quem você está integrando**, insira o nome ou o endereço de email da nova contratação.</span><span class="sxs-lookup"><span data-stu-id="ba090-115">In the **Create a guide** window, under **Who are you onboarding**, enter the new hire's name or email address.</span></span> <span data-ttu-id="ba090-116">Se a nova contratação ainda não estiver no sistema, selecione **Adicionar agora** e insira as informações do funcionário.</span><span class="sxs-lookup"><span data-stu-id="ba090-116">If the new hire isn't in the system yet, select **Add now**, and enter the employee's information.</span></span>

    ![[<span data-ttu-id="ba090-117">Inserindo informações para o guia de integração</span><span class="sxs-lookup"><span data-stu-id="ba090-117">Entering information for the onboarding guide</span></span>](./media/onboard-create-a-guide-window.png)](./media/onboard-create-a-guide-window.png)

6. <span data-ttu-id="ba090-118">Em **Quando elas começam**, selecione uma data inicial.</span><span class="sxs-lookup"><span data-stu-id="ba090-118">Under **When do they start**, select a start date.</span></span>
7. <span data-ttu-id="ba090-119">Caso o guia de integração precise ser enviado automaticamente à nova contratação em uma data específica, certifique-se de ativar a opção **Agendar uma data de envio automático** e selecione a data de envio automático.</span><span class="sxs-lookup"><span data-stu-id="ba090-119">If the onboarding guide should be sent automatically to the new hire on a specific date, make sure that the **Schedule an automatic send date** option is turned on, and then select the automatic send date.</span></span> <span data-ttu-id="ba090-120">Para enviar o guia imediatamente, desative a opção **Agendar uma data de envio automático**.</span><span class="sxs-lookup"><span data-stu-id="ba090-120">To send the guide immediately, turn off the **Schedule an automatic send date** option.</span></span>
8. <span data-ttu-id="ba090-121">Selecione **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="ba090-121">Select **Done**.</span></span>
9. <span data-ttu-id="ba090-122">Quando terminar de editar o guia de integração, selecione **Enviar** no canto superior direito.</span><span class="sxs-lookup"><span data-stu-id="ba090-122">When you've finished editing the onboarding guide, select **Send** in the upper-right corner.</span></span> <span data-ttu-id="ba090-123">E então, siga uma destas etapas:</span><span class="sxs-lookup"><span data-stu-id="ba090-123">Then follow one of these steps:</span></span>

    - <span data-ttu-id="ba090-124">Para enviar um link do guia de integração para a nova contratação, selecione **Copiar link** e então **Copiar**.</span><span class="sxs-lookup"><span data-stu-id="ba090-124">To send the new hire a link to the onboarding guide, select **copy a link**, and then select **Copy**.</span></span>
    - <span data-ttu-id="ba090-125">Para personalizar o email do guia de integração antes de enviar, selecione **Personalizar o email antes de enviar**, selecione **Avançar**, personalize o email como preferir e selecione **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="ba090-125">To customize the email for the onboarding guide before you send it, select **Customize the email before sending**, select **Next**, customize the email as you desire, and then select **Send**.</span></span>
    - <span data-ttu-id="ba090-126">Para enviar o email sem personalização, selecione **Avançar** e **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="ba090-126">To send the email without customizing it, select **Next**, and then select **Send**.</span></span>

## <a name="create-an-onboarding-guide-from-a-template-and-send-it-to-multiple-new-hires"></a><span data-ttu-id="ba090-127">Criar um guia de integração por meio de um modelo e enviá-lo para várias novas contratações</span><span class="sxs-lookup"><span data-stu-id="ba090-127">Create an onboarding guide from a template and send it to multiple new hires</span></span>

<span data-ttu-id="ba090-128">O Onboard permite enviar um guia de integração simultaneamente para várias novas contratações.</span><span class="sxs-lookup"><span data-stu-id="ba090-128">Onboard lets you send an onboarding guide to multiple new hires at the same time.</span></span>

1. <span data-ttu-id="ba090-129">No menu esquerdo, selecione **Modelos**.</span><span class="sxs-lookup"><span data-stu-id="ba090-129">On the left menu, select **Templates**.</span></span>
2. <span data-ttu-id="ba090-130">Em **Meus modelos**, selecione o modelo que deseja configurar como um guia de integração para as novas contratações.</span><span class="sxs-lookup"><span data-stu-id="ba090-130">Under **My templates**, select the template that you want to set up as an onboarding guide for the new hires.</span></span>
3. <span data-ttu-id="ba090-131">Edite o modelo como desejar.</span><span class="sxs-lookup"><span data-stu-id="ba090-131">Edit the template as you desire.</span></span> <span data-ttu-id="ba090-132">Lembre-se de salvar seu trabalho conforme progredir.</span><span class="sxs-lookup"><span data-stu-id="ba090-132">Be sure to save your work as you go.</span></span>
4. <span data-ttu-id="ba090-133">Quando concluir a edição do modelo, selecione **Criar guia**.</span><span class="sxs-lookup"><span data-stu-id="ba090-133">When you've finished editing the template, select **Create guide**.</span></span>
5. <span data-ttu-id="ba090-134">Na janela **Criar guia**, selecione **Precisa fazer a integração de mais de uma pessoa por vez**.</span><span class="sxs-lookup"><span data-stu-id="ba090-134">In the **Create a guide** window, select **Need to onboard multiple people at once**.</span></span>

    <span data-ttu-id="ba090-135">[![Criar um guia de integração para várias novas contratações](./media/onboard-send-guide-multiple-people.png)](./media/onboard-send-guide-multiple-people.png)</span><span class="sxs-lookup"><span data-stu-id="ba090-135">[![Creating an onboarding guide for multiple new hires](./media/onboard-send-guide-multiple-people.png)](./media/onboard-send-guide-multiple-people.png)</span></span>

6. <span data-ttu-id="ba090-136">Selecione **Modelo de nova contratação**.</span><span class="sxs-lookup"><span data-stu-id="ba090-136">Select **new hire template**.</span></span>
7. <span data-ttu-id="ba090-137">Após baixar o arquivo .xlsx, selecione **Abrir**, insira as informações dos funcionários na pasta de trabalho do Excel e salve a pasta de trabalho.</span><span class="sxs-lookup"><span data-stu-id="ba090-137">After the .xlsx file is downloaded, select **Open**, enter the employees' information in the Excel workbook, and save the workbook.</span></span>

    <span data-ttu-id="ba090-138">[![Baixar o modelo do Excel para enviar o guia de integração para várias novas contratações](./media/onboard-send-guide-download-spreadsheet.png)](./media/onboard-send-guide-download-spreadsheet.png)</span><span class="sxs-lookup"><span data-stu-id="ba090-138">[![Downloading the Excel template for sending the onboarding guide to multiple new hires](./media/onboard-send-guide-download-spreadsheet.png)](./media/onboard-send-guide-download-spreadsheet.png)</span></span>

    > [!NOTE]
    > <span data-ttu-id="ba090-139">Para poder editar a pasta de trabalho, é necessário selecionar **Habilitar edição** no Excel.</span><span class="sxs-lookup"><span data-stu-id="ba090-139">Before you can edit the workbook, you must select **Enable editing** in Excel.</span></span>
    > 
    > <span data-ttu-id="ba090-140">[![Habilitar edição](./media/onboard-send-guide-enable-editing.png)](./media/onboard-send-guide-enable-editing.png)</span><span class="sxs-lookup"><span data-stu-id="ba090-140">[![Enabling editing](./media/onboard-send-guide-enable-editing.png)](./media/onboard-send-guide-enable-editing.png)</span></span>

8. <span data-ttu-id="ba090-141">Arraste a pasta de trabalho do Excel para a área designada na janela **Criar vários guias**, ou clique em qualquer lugar nessa área para procurar o arquivo no seu computador.</span><span class="sxs-lookup"><span data-stu-id="ba090-141">Drag the Excel workbook to the designated area in the **Create multiple guides** window, or click anywhere in that area to browse for the file on your computer.</span></span>

    <span data-ttu-id="ba090-142">[![Arrastar a pasta de trabalho editada](./media/onboard-send-guide-drag-spreadsheet.png)](./media/onboard-send-guide-drag-spreadsheet.png)</span><span class="sxs-lookup"><span data-stu-id="ba090-142">[![Dragging the edited workbook](./media/onboard-send-guide-drag-spreadsheet.png)](./media/onboard-send-guide-drag-spreadsheet.png)</span></span>

9. <span data-ttu-id="ba090-143">Quando terminar de editar o guia de integração, selecione **Enviar** no canto superior direito.</span><span class="sxs-lookup"><span data-stu-id="ba090-143">When you've finished editing the onboarding guide, select **Send** in the upper-right corner.</span></span> <span data-ttu-id="ba090-144">E então, siga uma destas etapas:</span><span class="sxs-lookup"><span data-stu-id="ba090-144">Then follow one of these steps:</span></span>

    - <span data-ttu-id="ba090-145">Para enviar um link do guia de integração para as novas contratações, selecione **Copiar link** e então **Copiar**.</span><span class="sxs-lookup"><span data-stu-id="ba090-145">To send the new hires a link to the onboarding guide, select **copy a link**, and then select **Copy**.</span></span>
    - <span data-ttu-id="ba090-146">Para personalizar o email do guia de integração antes de enviar, selecione **Personalizar o email antes de enviar**, selecione **Avançar**, personalize o email como preferir e selecione **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="ba090-146">To customize the email for the onboarding guide before you send it, select **Customize the email before sending**, select **Next**, customize the email as you desire, and then select **Send**.</span></span>
    - <span data-ttu-id="ba090-147">Para enviar o email sem personalização, selecione **Avançar** e **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="ba090-147">To send the email without customizing it, select **Next**, and then select **Send**.</span></span>

## <a name="create-a-guide-without-using-a-template"></a><span data-ttu-id="ba090-148">Criar um guia sem usar um modelo</span><span class="sxs-lookup"><span data-stu-id="ba090-148">Create a guide without using a template</span></span>

<span data-ttu-id="ba090-149">Você não precisa sempre criar um guia por meio de um modelo.</span><span class="sxs-lookup"><span data-stu-id="ba090-149">You don't always have to create a guide from a template.</span></span> <span data-ttu-id="ba090-150">Em vez disso, se preferir, você pode criar um guia do zero.</span><span class="sxs-lookup"><span data-stu-id="ba090-150">If you prefer, you can create a guide from scratch instead.</span></span>

1. <span data-ttu-id="ba090-151">No menu esquerdo, selecione **Guias** e selecione o botão **Adicionar** (o sinal de adição \[**+**\]).</span><span class="sxs-lookup"><span data-stu-id="ba090-151">On the left menu, select **Guides**, and then select the **Add** button (the plus sign \[**+**\]).</span></span>
2. <span data-ttu-id="ba090-152">Na janela **Criar um guia**, em **Quem você está integrando**, insira o nome ou o endereço de email da nova contratação.</span><span class="sxs-lookup"><span data-stu-id="ba090-152">In the **Create a guide** window, under **Who are you onboarding**, enter the new hire's name or email address.</span></span> <span data-ttu-id="ba090-153">Se a nova contratação ainda não estiver no sistema, selecione **Adicionar agora** e insira as informações do funcionário.</span><span class="sxs-lookup"><span data-stu-id="ba090-153">If the new hire isn't in the system yet, select **Add now**, and enter the employee's information.</span></span>

    ![[<span data-ttu-id="ba090-154">Inserindo informações para o guia de integração</span><span class="sxs-lookup"><span data-stu-id="ba090-154">Entering information for the onboarding guide</span></span>](./media/onboard-create-a-guide-window.png)](./media/onboard-create-a-guide-window.png)

3. <span data-ttu-id="ba090-155">Em **Quando elas começam**, selecione uma data inicial.</span><span class="sxs-lookup"><span data-stu-id="ba090-155">Under **When do they start**, select a start date.</span></span>
4. <span data-ttu-id="ba090-156">Caso o guia de integração precise ser enviado automaticamente à nova contratação em uma data específica, certifique-se de ativar a opção **Agendar uma data de envio automático** e selecione a data de envio automático.</span><span class="sxs-lookup"><span data-stu-id="ba090-156">If the onboarding guide should be sent automatically to the new hire on a specific date, make sure that the **Schedule an automatic send date** option is turned on, and then select the automatic send date.</span></span> <span data-ttu-id="ba090-157">Para enviar o guia imediatamente, desative a opção **Agendar uma data de envio automático**.</span><span class="sxs-lookup"><span data-stu-id="ba090-157">To send the guide immediately, turn off the **Schedule an automatic send date** option.</span></span>
5. <span data-ttu-id="ba090-158">Selecione **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="ba090-158">Select **Done**.</span></span>

## <a name="save-a-guide-as-a-template"></a><span data-ttu-id="ba090-159">Salvar um guia como modelo</span><span class="sxs-lookup"><span data-stu-id="ba090-159">Save a guide as a template</span></span>

<span data-ttu-id="ba090-160">Você pode salvar um guia de integração como modelo.</span><span class="sxs-lookup"><span data-stu-id="ba090-160">You can save an onboarding guide as a template.</span></span> <span data-ttu-id="ba090-161">Dessa forma, você poderá poupar tempo quando você precisar criar mais guias de integração posteriormente.</span><span class="sxs-lookup"><span data-stu-id="ba090-161">In this way, you can save time when you must create more onboarding guides later.</span></span>

1. <span data-ttu-id="ba090-162">No menu esquerdo, selecione **Guias**.</span><span class="sxs-lookup"><span data-stu-id="ba090-162">On the left menu, select **Guides**.</span></span>
2. <span data-ttu-id="ba090-163">Selecione o botão **Mais** (as reticências \[**...**\]) no guia que deseja usar para criar um modelo e, em seguida, selecione **Salvar como modelo**.</span><span class="sxs-lookup"><span data-stu-id="ba090-163">Select the **More** button (the ellipsis \[**...**\]) for the guide that you want to create a template from, and then select **Save as template**.</span></span>

    ![[<span data-ttu-id="ba090-164">Salvando um guia de integração como um modelo</span><span class="sxs-lookup"><span data-stu-id="ba090-164">Saving an onboarding guide as a template</span></span>](./media/onboard-save-guide-as-template.png)](./media/onboard-save-guide-as-template.png)

3. <span data-ttu-id="ba090-165">Na janela **Salvar como um novo modelo**, digite um nome para o novo modelo e selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="ba090-165">In the **Save as a new template** window, enter a name for your new template, and then select **Save**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="ba090-166">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="ba090-166">Next steps</span></span>

- [<span data-ttu-id="ba090-167">Editar guias e modelos de integração</span><span class="sxs-lookup"><span data-stu-id="ba090-167">Edit onboarding guides and templates</span></span>](./onboard-edit-guides-templates.md)
- [<span data-ttu-id="ba090-168">Compartilhar conteúdo com outros contribuintes</span><span class="sxs-lookup"><span data-stu-id="ba090-168">Share content with other contributors</span></span>](./onboard-share-template.md)
- [<span data-ttu-id="ba090-169">Exibir o status de tarefas e da integração de funcionários</span><span class="sxs-lookup"><span data-stu-id="ba090-169">View the status of tasks and onboarding employees</span></span>](./onboard-view-status.md)
- [<span data-ttu-id="ba090-170">Criar equipes de contratação no Onboard</span><span class="sxs-lookup"><span data-stu-id="ba090-170">Create hiring teams in Onboard</span></span>](./onboard-create-team.md)

### <a name="see-also"></a><span data-ttu-id="ba090-171">Consulte também</span><span class="sxs-lookup"><span data-stu-id="ba090-171">See also</span></span>

- [<span data-ttu-id="ba090-172">Experimentar ou comprar o Onboard</span><span class="sxs-lookup"><span data-stu-id="ba090-172">Try or buy the Onboard app</span></span>](https://dynamics.microsoft.com/talent/onboard/)
- [<span data-ttu-id="ba090-173">Novidades ou alterações no Dynamics 365 Talent</span><span class="sxs-lookup"><span data-stu-id="ba090-173">What's new or changed in Dynamics 365 Talent</span></span>](./whats-new.md)
- [<span data-ttu-id="ba090-174">Planos de versão</span><span class="sxs-lookup"><span data-stu-id="ba090-174">Release plans</span></span>](https://docs.microsoft.com/business-applications-release-notes/index)
- [<span data-ttu-id="ba090-175">Obter suporte para o Microsoft Dynamics 365 Talent</span><span class="sxs-lookup"><span data-stu-id="ba090-175">Get support for Microsoft Dynamics 365 Talent</span></span>](./talent-support.md)
