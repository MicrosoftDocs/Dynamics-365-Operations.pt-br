---
title: Configurar perfil de notificação por email
description: Este tópico descreve como criar um perfil de notificação de email no Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 03/31/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: c0ab56c15a37313d0a88b1174d5bcf51d391dcec
ms.sourcegitcommit: 17ffdcbf4b1801bd6ee9c9ddc18622d5d04b8a98
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2020
ms.locfileid: "3180186"
---
# <a name="set-up-an-email-notification-profile"></a><span data-ttu-id="2f3a1-103">Configurar perfil de notificação por email</span><span class="sxs-lookup"><span data-stu-id="2f3a1-103">Set up an email notification profile</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="2f3a1-104">Este tópico descreve como criar um perfil de notificação de email no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="2f3a1-104">This topic describes how to create an email notification profile in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="2f3a1-105">Visão geral</span><span class="sxs-lookup"><span data-stu-id="2f3a1-105">Overview</span></span>

<span data-ttu-id="2f3a1-106">Antes de criar canais, configure um perfil para garantir que as notificações de email possam ser enviadas para vários eventos, como criação da ordem, status da remessa da ordem e falha do pagamento.</span><span class="sxs-lookup"><span data-stu-id="2f3a1-106">Before creating channels, you'll want to set up a profile to ensure that email notifications can be sent out for various events, such as order creation, order shipping status, and payment failure.</span></span>

<span data-ttu-id="2f3a1-107">Para obter informações adicionais sobre como configurar o email, consulte [Configurar e enviar email](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json).</span><span class="sxs-lookup"><span data-stu-id="2f3a1-107">For additional email configuration information, see [Configure and send email](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json).</span></span>

## <a name="create-an-email-notification-profile"></a><span data-ttu-id="2f3a1-108">Criar perfil de notificação por email</span><span class="sxs-lookup"><span data-stu-id="2f3a1-108">Create an email notification profile</span></span>

<span data-ttu-id="2f3a1-109">Para criar um perfil de notificação por email, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="2f3a1-109">To create an email notification profile, follow these steps.</span></span>

1. <span data-ttu-id="2f3a1-110">No painel de navegação, vá para **Módulos \> Retail e Commerce \> Configuração do Headquarters \> Perfil de notificação por email do Commerce**.</span><span class="sxs-lookup"><span data-stu-id="2f3a1-110">In the navigation pane, go to **Modules \> Retail and commerce \> Headquarters setup \> Commerce email notification profile**.</span></span>
1. <span data-ttu-id="2f3a1-111">No painel de ações, clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="2f3a1-111">On the action pane, click **New**.</span></span>
1. <span data-ttu-id="2f3a1-112">No campo **Perfil de notificação por email**, insira um nome para identificar o perfil.</span><span class="sxs-lookup"><span data-stu-id="2f3a1-112">In the **Email notification profile** field, enter a name to identify the profile.</span></span>
1. <span data-ttu-id="2f3a1-113">No campo **Descrição**, insira uma descrição relevante.</span><span class="sxs-lookup"><span data-stu-id="2f3a1-113">In the **Description** field, enter a relevant description.</span></span>
1. <span data-ttu-id="2f3a1-114">Defina a alternância **Ativo** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="2f3a1-114">Set the **Active** switch to **Yes**.</span></span>

### <a name="create-an-email-template"></a><span data-ttu-id="2f3a1-115">Criar um modelo de email</span><span class="sxs-lookup"><span data-stu-id="2f3a1-115">Create an email template</span></span>

<span data-ttu-id="2f3a1-116">Antes que uma notificação por email possa ser criada, é necessário criar um modelo de email da organização contendo as informações de email dos remetentes e o modelo de email.</span><span class="sxs-lookup"><span data-stu-id="2f3a1-116">Before an email notification can be created, you must create an organization email template which contains the senders email information and the email template.</span></span>

<span data-ttu-id="2f3a1-117">Para criar um modelo de email, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="2f3a1-117">To create an email template, follow these steps.</span></span>

1. <span data-ttu-id="2f3a1-118">No painel de navegação, vá para **Módulos \> Retail e Commerce \> Configuração do Headquarters \> Parâmetros \> Modelos de email da organização**.</span><span class="sxs-lookup"><span data-stu-id="2f3a1-118">In the navigation pane, go to **Modules \> Retail and commerce \> Headquarters setup \> Parameters \> Organization email templates**.</span></span>
1. <span data-ttu-id="2f3a1-119">No painel de ação, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="2f3a1-119">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="2f3a1-120">No campo **ID do email**, insira uma ID para ajudar a identificar este modelo.</span><span class="sxs-lookup"><span data-stu-id="2f3a1-120">In the **Email ID** field, enter an ID to help identify this template.</span></span>
1. <span data-ttu-id="2f3a1-121">No campo **Nome do remetente**, digite o nome do remetente.</span><span class="sxs-lookup"><span data-stu-id="2f3a1-121">In the **Sends name** field, enter the senders name.</span></span>
1. <span data-ttu-id="2f3a1-122">No campo **Descrição do Email**, insira uma descrição significativa.</span><span class="sxs-lookup"><span data-stu-id="2f3a1-122">In the **Email Description**, enter a meaningful description.</span></span>
1. <span data-ttu-id="2f3a1-123">No campo **Email do remetente**, insira o endereço de email do remetente.</span><span class="sxs-lookup"><span data-stu-id="2f3a1-123">In the **Sender email**, enter the senders email address.</span></span>
1. <span data-ttu-id="2f3a1-124">Na seção **Geral**, preencha todas as informações opcionais necessárias (como a prioridade de email).</span><span class="sxs-lookup"><span data-stu-id="2f3a1-124">In the **General** section, fill out any optional information needed (such as the email priority).</span></span>
1. <span data-ttu-id="2f3a1-125">Expanda a seção **Conteúdo da mensagem de email** e selecione **Novo** para criar o conteúdo do modelo.</span><span class="sxs-lookup"><span data-stu-id="2f3a1-125">Expand the **Email message content** section and select **New** to create the template content.</span></span> <span data-ttu-id="2f3a1-126">Para cada item de conteúdo, selecione o idioma e forneça a linha de assunto do email.</span><span class="sxs-lookup"><span data-stu-id="2f3a1-126">For each content item, select the language and provide the email subject line.</span></span> <span data-ttu-id="2f3a1-127">Se o email tiver um corpo, certifique-se de que a caixa **Tem corpo** esteja selecionada.</span><span class="sxs-lookup"><span data-stu-id="2f3a1-127">If the email will have a body, ensure that the **Has body** box is checked.</span></span>
1. <span data-ttu-id="2f3a1-128">No painel de ações, selecione **Mensagem do email** para fornecer um modelo de corpo de email.</span><span class="sxs-lookup"><span data-stu-id="2f3a1-128">On the action pane, select **Email message** to provide an email body template.</span></span>

<span data-ttu-id="2f3a1-129">A imagem a seguir mostra alguns exemplos de configurações de modelo de email.</span><span class="sxs-lookup"><span data-stu-id="2f3a1-129">The following image shows some example email template settings.</span></span>

![Configurações de modelo de email](media/email-template.png)

### <a name="create-an-email-event"></a><span data-ttu-id="2f3a1-131">Criar um evento de email</span><span class="sxs-lookup"><span data-stu-id="2f3a1-131">Create an email event</span></span>

<span data-ttu-id="2f3a1-132">Para criar um evento de email, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="2f3a1-132">To create an email event, follow these steps.</span></span>

1. <span data-ttu-id="2f3a1-133">No painel de navegação, vá para **Módulos \> Retail e Commerce \> Configuração do Headquarters \> Perfil de notificação por email do Commerce**.</span><span class="sxs-lookup"><span data-stu-id="2f3a1-133">In the navigation pane, go to **Modules \> Retail and commerce \> Headquarters setup \> Commerce email notification profile**.</span></span>
1. <span data-ttu-id="2f3a1-134">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="2f3a1-134">In the list, find and select the desired record.</span></span> 
1. <span data-ttu-id="2f3a1-135">Selecione o modelo de email na lista suspensa **ID do Email**.</span><span class="sxs-lookup"><span data-stu-id="2f3a1-135">Select the email template from the **Email ID** drop-down list.</span></span>
1. <span data-ttu-id="2f3a1-136">Selecione o **Tipo de notificação por email** apropriado na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="2f3a1-136">Select the appropriate **Email notification type** from the drop-down list.</span></span>
1. <span data-ttu-id="2f3a1-137">Marque a caixa de seleção **Ativo**.</span><span class="sxs-lookup"><span data-stu-id="2f3a1-137">Select the **Active** check box.</span></span>
1. <span data-ttu-id="2f3a1-138">No painel de ação, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="2f3a1-138">On the action pane, select **Save**.</span></span>

<span data-ttu-id="2f3a1-139">A imagem a seguir mostra alguns exemplos de configurações de notificação de evento.</span><span class="sxs-lookup"><span data-stu-id="2f3a1-139">The following image shows some example event notification settings.</span></span>

![Configurações de notificação de evento](media/email-notification-profile.png)

### <a name="next-steps"></a><span data-ttu-id="2f3a1-141">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="2f3a1-141">Next steps</span></span>

<span data-ttu-id="2f3a1-142">Para poder enviar emails, você deve configurar seu serviço de email de saída e configurar um trabalho em lotes.</span><span class="sxs-lookup"><span data-stu-id="2f3a1-142">Before you can send mails, you must configure your outgoing mail service and set up a batch job.</span></span> <span data-ttu-id="2f3a1-143">Para obter mais informações, consulte [Configurar e enviar email](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json).</span><span class="sxs-lookup"><span data-stu-id="2f3a1-143">For more information, see [Configure and send email](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json).</span></span>


## <a name="additional-resources"></a><span data-ttu-id="2f3a1-144">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="2f3a1-144">Additional resources</span></span>

[<span data-ttu-id="2f3a1-145">Configurar e enviar email</span><span class="sxs-lookup"><span data-stu-id="2f3a1-145">Configure and send email</span></span>](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json)

[<span data-ttu-id="2f3a1-146">Visão geral de canais</span><span class="sxs-lookup"><span data-stu-id="2f3a1-146">Channels overview</span></span>](channels-overview.md)

[<span data-ttu-id="2f3a1-147">Pré-requisitos de configuração de canal</span><span class="sxs-lookup"><span data-stu-id="2f3a1-147">Channel setup prerequisites</span></span>](channels-prerequisites.md)

[<span data-ttu-id="2f3a1-148">Visão geral de organizações e hierarquias organizacionais</span><span class="sxs-lookup"><span data-stu-id="2f3a1-148">Organizations and organizational hierarchies overview</span></span>](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)
