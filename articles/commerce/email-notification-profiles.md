---
title: Configurar perfil de notificação por email
description: Este tópico descreve como criar um perfil de notificação de email no Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 01/27/2020
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
ms.openlocfilehash: 9e5d90eaf1815bbe54b0bea40d92a0a993a23b75
ms.sourcegitcommit: 141e0239b6310ab4a6a775bc0997120c31634f79
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/10/2020
ms.locfileid: "3113796"
---
# <a name="set-up-an-email-notification-profile"></a><span data-ttu-id="c1b73-103">Configurar perfil de notificação por email</span><span class="sxs-lookup"><span data-stu-id="c1b73-103">Set up an email notification profile</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="c1b73-104">Este tópico descreve como criar um perfil de notificação de email no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="c1b73-104">This topic describes how to create an email notification profile in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="c1b73-105">Visão geral</span><span class="sxs-lookup"><span data-stu-id="c1b73-105">Overview</span></span>

<span data-ttu-id="c1b73-106">Antes de criar canais, configure um perfil para garantir que as notificações de email possam ser enviadas para vários eventos, como criação da ordem, status da remessa da ordem e falha do pagamento.</span><span class="sxs-lookup"><span data-stu-id="c1b73-106">Before creating channels, you'll want to set up a profile to ensure that email notifications can be sent out for various events, such as order creation, order shipping status, and payment failure.</span></span>

<span data-ttu-id="c1b73-107">Para obter informações adicionais sobre como configurar o email, consulte [Configurar e enviar email](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json).</span><span class="sxs-lookup"><span data-stu-id="c1b73-107">For additional email configuration information, see [Configure and send email](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json).</span></span>

## <a name="create-an-email-notification-profile"></a><span data-ttu-id="c1b73-108">Criar perfil de notificação por email</span><span class="sxs-lookup"><span data-stu-id="c1b73-108">Create an email notification profile</span></span>

<span data-ttu-id="c1b73-109">Para criar um perfil de notificação por email, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="c1b73-109">To create an email notification profile, follow these steps.</span></span>

1. <span data-ttu-id="c1b73-110">No painel de navegação, vá para **Módulos \> Retail e Commerce \> Configuração do Headquarters \> Perfil de notificação por email do Commerce**.</span><span class="sxs-lookup"><span data-stu-id="c1b73-110">In the navigation pane, go to **Modules \> Retail and commerce \> Headquarters setup \> Commerce email notification profile**.</span></span>
1. <span data-ttu-id="c1b73-111">No painel de ações, clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="c1b73-111">On the action pane, click **New**.</span></span>
1. <span data-ttu-id="c1b73-112">No campo **Perfil de notificação por email**, insira um nome para identificar o perfil.</span><span class="sxs-lookup"><span data-stu-id="c1b73-112">In the **Email notification profile** field, enter a name to identify the profile.</span></span>
1. <span data-ttu-id="c1b73-113">No campo **Descrição**, insira uma descrição relevante.</span><span class="sxs-lookup"><span data-stu-id="c1b73-113">In the **Description** field, enter a relevant description.</span></span>
1. <span data-ttu-id="c1b73-114">Defina a alternância **Ativo** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="c1b73-114">Set the **Active** switch to **Yes**.</span></span>

### <a name="create-an-email-template"></a><span data-ttu-id="c1b73-115">Criar um modelo de email</span><span class="sxs-lookup"><span data-stu-id="c1b73-115">Create an email template</span></span>

<span data-ttu-id="c1b73-116">Antes que uma notificação por email possa ser criada, é necessário criar um modelo de email da organização contendo as informações de email dos remetentes e o modelo de email.</span><span class="sxs-lookup"><span data-stu-id="c1b73-116">Before an email notification can be created, you must create an organization email template which contains the senders email information and the email template.</span></span>

<span data-ttu-id="c1b73-117">Para criar um modelo de email, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="c1b73-117">To create an email template, follow these steps.</span></span>

1. <span data-ttu-id="c1b73-118">No painel de navegação, vá para **Módulos \> Retail e Commerce \> Configuração do Headquarters \> Parâmetros \> Modelos de email da organização**.</span><span class="sxs-lookup"><span data-stu-id="c1b73-118">In the navigation pane, go to **Modules \> Retail and commerce \> Headquarters setup \> Parameters \> Organization email templates**.</span></span>
1. <span data-ttu-id="c1b73-119">No painel de ação, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="c1b73-119">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="c1b73-120">No campo **ID do email**, insira uma ID para ajudar a identificar este modelo.</span><span class="sxs-lookup"><span data-stu-id="c1b73-120">In the **Email ID** field, enter an ID to help identify this template.</span></span>
1. <span data-ttu-id="c1b73-121">No campo **Nome do remetente**, digite o nome do remetente.</span><span class="sxs-lookup"><span data-stu-id="c1b73-121">In the **Sends name** field, enter the senders name.</span></span>
1. <span data-ttu-id="c1b73-122">No campo **Descrição do Email**, insira uma descrição significativa.</span><span class="sxs-lookup"><span data-stu-id="c1b73-122">In the **Email Description**, enter a meaningful description.</span></span>
1. <span data-ttu-id="c1b73-123">No campo **Email do remetente**, insira o endereço de email do remetente.</span><span class="sxs-lookup"><span data-stu-id="c1b73-123">In the **Sender email**, enter the senders email address.</span></span>
1. <span data-ttu-id="c1b73-124">Na seção **Geral**, preencha todas as informações opcionais necessárias (como a prioridade de email).</span><span class="sxs-lookup"><span data-stu-id="c1b73-124">In the **General** section, fill out any optional information needed (such as the email priority).</span></span>
1. <span data-ttu-id="c1b73-125">Expanda a seção **Conteúdo da mensagem de email** e selecione **Novo** para criar o conteúdo do modelo.</span><span class="sxs-lookup"><span data-stu-id="c1b73-125">Expand the **Email message content** section and select **New** to create the template content.</span></span> <span data-ttu-id="c1b73-126">Para cada item de conteúdo, selecione o idioma e forneça a linha de assunto do email.</span><span class="sxs-lookup"><span data-stu-id="c1b73-126">For each content item, select the language and provide the email subject line.</span></span> <span data-ttu-id="c1b73-127">Se o email tiver um corpo, certifique-se de que a caixa **Tem corpo** esteja selecionada.</span><span class="sxs-lookup"><span data-stu-id="c1b73-127">If the email will have a body, ensure that the **Has body** box is checked.</span></span>
1. <span data-ttu-id="c1b73-128">No painel de ações, selecione **Mensagem do email** para fornecer um modelo de corpo de email.</span><span class="sxs-lookup"><span data-stu-id="c1b73-128">On the action pane, select **Email message** to provide an email body template.</span></span>

<span data-ttu-id="c1b73-129">A imagem a seguir mostra alguns exemplos de configurações de modelo de email.</span><span class="sxs-lookup"><span data-stu-id="c1b73-129">The following image shows some example email template settings.</span></span>

![Configurações de modelo de email](media/email-template.png)

### <a name="create-an-email-event"></a><span data-ttu-id="c1b73-131">Criar um evento de email</span><span class="sxs-lookup"><span data-stu-id="c1b73-131">Create an email event</span></span>

<span data-ttu-id="c1b73-132">Para criar um evento de email, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="c1b73-132">To create an email event, follow these steps.</span></span>

1. <span data-ttu-id="c1b73-133">No painel de navegação, vá para **Módulos \> Retail e Commerce \> Configuração do Headquarters \> Perfil de notificação por email do Commerce**.</span><span class="sxs-lookup"><span data-stu-id="c1b73-133">In the navigation pane, go to **Modules \> Retail and commerce \> Headquarters setup \> Commerce email notification profile**.</span></span>
1. <span data-ttu-id="c1b73-134">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="c1b73-134">In the list, find and select the desired record.</span></span> 
1. <span data-ttu-id="c1b73-135">Selecione o modelo de email na lista suspensa **ID do Email**.</span><span class="sxs-lookup"><span data-stu-id="c1b73-135">Select the email template from the **Email ID** drop-down list.</span></span>
1. <span data-ttu-id="c1b73-136">Selecione o **Tipo de notificação por email** apropriado na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="c1b73-136">Select the appropriate **Email notification type** from the drop-down list.</span></span>
1. <span data-ttu-id="c1b73-137">Marque a caixa de seleção **Ativo**.</span><span class="sxs-lookup"><span data-stu-id="c1b73-137">Select the **Active** check box.</span></span>
1. <span data-ttu-id="c1b73-138">No painel de ação, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="c1b73-138">On the action pane, select **Save**.</span></span>

<span data-ttu-id="c1b73-139">A imagem a seguir mostra alguns exemplos de configurações de notificação de evento.</span><span class="sxs-lookup"><span data-stu-id="c1b73-139">The following image shows some example event notification settings.</span></span>

![Configurações de notificação de evento](media/email-notification-profile.png)

## <a name="additional-resources"></a><span data-ttu-id="c1b73-141">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="c1b73-141">Additional resources</span></span>

[<span data-ttu-id="c1b73-142">Configurar e enviar email</span><span class="sxs-lookup"><span data-stu-id="c1b73-142">Configure and send email</span></span>](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json)

[<span data-ttu-id="c1b73-143">Visão geral de canais</span><span class="sxs-lookup"><span data-stu-id="c1b73-143">Channels overview</span></span>](channels-overview.md)

[<span data-ttu-id="c1b73-144">Pré-requisitos de configuração de canal</span><span class="sxs-lookup"><span data-stu-id="c1b73-144">Channel setup prerequisites</span></span>](channels-prerequisites.md)

[<span data-ttu-id="c1b73-145">Visão geral de organizações e hierarquias organizacionais</span><span class="sxs-lookup"><span data-stu-id="c1b73-145">Organizations and organizational hierarchies overview</span></span>](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)
