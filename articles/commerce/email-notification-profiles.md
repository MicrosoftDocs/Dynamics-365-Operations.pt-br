---
title: Configurar perfil de notificação por email
description: Este tópico descreve como criar um perfil de notificação de email no Microsoft Dynamics 365 Commerce.
author: bicyclingfool
manager: annbe
ms.date: 03/01/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: stuharg
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: d82a1abe68ff6e162acb75c6fdc1e207af11c279
ms.sourcegitcommit: 88babb2fffe97e93bbde543633fc492120f2a4fc
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/06/2021
ms.locfileid: "5555298"
---
# <a name="set-up-an-email-notification-profile"></a><span data-ttu-id="f7ab3-103">Configurar perfil de notificação por email</span><span class="sxs-lookup"><span data-stu-id="f7ab3-103">Set up an email notification profile</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="f7ab3-104">Este tópico descreve como criar um perfil de notificação de email no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="f7ab3-104">This topic describes how to create an email notification profile in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="f7ab3-105">Ao criar canais, você pode configurar um perfil de notificação por email.</span><span class="sxs-lookup"><span data-stu-id="f7ab3-105">When you create channels, you can set up an email notification profile.</span></span> <span data-ttu-id="f7ab3-106">Dessa forma, os emails podem ser enviados para os clientes por vários eventos transacionais, como a criação da ordem, o status de remessa da ordem e a falha de pagamento.</span><span class="sxs-lookup"><span data-stu-id="f7ab3-106">In that way, emails can be sent to customers for various transactional events, such as order creation, order shipping status, and payment failure.</span></span>

<span data-ttu-id="f7ab3-107">Para obter informações adicionais sobre como configurar o email, consulte [Configurar e enviar email](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json).</span><span class="sxs-lookup"><span data-stu-id="f7ab3-107">For additional email configuration information, see [Configure and send email](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json).</span></span>

## <a name="create-an-email-notification-profile"></a><span data-ttu-id="f7ab3-108">Criar perfil de notificação por email</span><span class="sxs-lookup"><span data-stu-id="f7ab3-108">Create an email notification profile</span></span>

<span data-ttu-id="f7ab3-109">Para criar um perfil de notificação por email, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="f7ab3-109">To create an email notification profile, follow these steps.</span></span>

1. <span data-ttu-id="f7ab3-110">No painel de navegação, vá para **Módulos \> Retail e Commerce \> Configuração do Headquarters \> Perfil de notificação por email do Commerce**.</span><span class="sxs-lookup"><span data-stu-id="f7ab3-110">In the navigation pane, go to **Modules \> Retail and commerce \> Headquarters setup \> Commerce email notification profile**.</span></span>
1. <span data-ttu-id="f7ab3-111">No painel de ações, clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="f7ab3-111">On the action pane, click **New**.</span></span>
1. <span data-ttu-id="f7ab3-112">No campo **Perfil de notificação por email**, insira um nome para identificar o perfil.</span><span class="sxs-lookup"><span data-stu-id="f7ab3-112">In the **Email notification profile** field, enter a name to identify the profile.</span></span>
1. <span data-ttu-id="f7ab3-113">No campo **Descrição**, insira uma descrição relevante.</span><span class="sxs-lookup"><span data-stu-id="f7ab3-113">In the **Description** field, enter a relevant description.</span></span>
1. <span data-ttu-id="f7ab3-114">Defina a alternância **Ativo** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="f7ab3-114">Set the **Active** switch to **Yes**.</span></span>

### <a name="create-an-email-template"></a><span data-ttu-id="f7ab3-115">Criar um modelo de email</span><span class="sxs-lookup"><span data-stu-id="f7ab3-115">Create an email template</span></span>

<span data-ttu-id="f7ab3-116">Antes que um tipo de notificação por email possa ser habilitado, você deve criar um modelo de email de organização no Commerce Headquarters.</span><span class="sxs-lookup"><span data-stu-id="f7ab3-116">Before an email notification type can be enabled, you must create an organization email template in Commerce headquarters.</span></span> <span data-ttu-id="f7ab3-117">Este modelo define o assunto do email, o remetente, o idioma padrão e o corpo do email para cada idioma para o qual você deseja oferecer suporte.</span><span class="sxs-lookup"><span data-stu-id="f7ab3-117">This template defines the email subject, sender, default language, and email body for each language that you want to support.</span></span>

<span data-ttu-id="f7ab3-118">Para criar um modelo de email, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="f7ab3-118">To create an email template, follow these steps.</span></span>

1. <span data-ttu-id="f7ab3-119">No painel de navegação, vá para **Módulos \> Retail e Commerce \> Configuração do Headquarters \> Parâmetros \> Modelos de email da organização**.</span><span class="sxs-lookup"><span data-stu-id="f7ab3-119">In the navigation pane, go to **Modules \> Retail and commerce \> Headquarters setup \> Parameters \> Organization email templates**.</span></span>
1. <span data-ttu-id="f7ab3-120">No painel de ação, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="f7ab3-120">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="f7ab3-121">No campo **ID do email**, insira uma ID para ajudar a identificar este modelo.</span><span class="sxs-lookup"><span data-stu-id="f7ab3-121">In the **Email ID** field, enter an ID to help identify this template.</span></span>
1. <span data-ttu-id="f7ab3-122">No campo **Nome do remetente**, digite o nome do remetente.</span><span class="sxs-lookup"><span data-stu-id="f7ab3-122">In the **Sends name** field, enter the senders name.</span></span>
1. <span data-ttu-id="f7ab3-123">No campo **Descrição do Email**, insira uma descrição significativa.</span><span class="sxs-lookup"><span data-stu-id="f7ab3-123">In the **Email Description**, enter a meaningful description.</span></span>
1. <span data-ttu-id="f7ab3-124">No campo **Email do remetente**, insira o endereço de email do remetente.</span><span class="sxs-lookup"><span data-stu-id="f7ab3-124">In the **Sender email**, enter the senders email address.</span></span>
1. <span data-ttu-id="f7ab3-125">Na seção **Geral**, selecione um idioma padrão para o modelo de email.</span><span class="sxs-lookup"><span data-stu-id="f7ab3-125">In the **General** section, select a default language for the email template.</span></span> <span data-ttu-id="f7ab3-126">O idioma padrão será usado quando não existir nenhum modelo localizado para o idioma especificado.</span><span class="sxs-lookup"><span data-stu-id="f7ab3-126">The default language will be used when no localized template exists for the specified language.</span></span>
1. <span data-ttu-id="f7ab3-127">Expanda a seção **Conteúdo da mensagem de email** e selecione **Novo** para criar o conteúdo do modelo.</span><span class="sxs-lookup"><span data-stu-id="f7ab3-127">Expand the **Email message content** section and select **New** to create the template content.</span></span> <span data-ttu-id="f7ab3-128">Para cada item de conteúdo, selecione o idioma e forneça a linha de assunto do email.</span><span class="sxs-lookup"><span data-stu-id="f7ab3-128">For each content item, select the language and provide the email subject line.</span></span> <span data-ttu-id="f7ab3-129">Se o email tiver um corpo, certifique-se de que a caixa **Tem corpo** esteja selecionada.</span><span class="sxs-lookup"><span data-stu-id="f7ab3-129">If the email will have a body, ensure that the **Has body** box is checked.</span></span>
1. <span data-ttu-id="f7ab3-130">No painel de ações, selecione **Mensagem do email** para fornecer um modelo de corpo de email.</span><span class="sxs-lookup"><span data-stu-id="f7ab3-130">On the action pane, select **Email message** to provide an email body template.</span></span>

<span data-ttu-id="f7ab3-131">A imagem a seguir mostra alguns exemplos de configurações de modelo de email.</span><span class="sxs-lookup"><span data-stu-id="f7ab3-131">The following image shows some example email template settings.</span></span>

![Configurações de modelo de email](media/email-template.png)

### <a name="create-an-email-event"></a><span data-ttu-id="f7ab3-133">Criar um evento de email</span><span class="sxs-lookup"><span data-stu-id="f7ab3-133">Create an email event</span></span>

<span data-ttu-id="f7ab3-134">Para criar um evento de email, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="f7ab3-134">To create an email event, follow these steps.</span></span>

1. <span data-ttu-id="f7ab3-135">No painel de navegação, vá para **Módulos \> Retail e Commerce \> Configuração do Headquarters \> Perfil de notificação por email do Commerce**.</span><span class="sxs-lookup"><span data-stu-id="f7ab3-135">In the navigation pane, go to **Modules \> Retail and commerce \> Headquarters setup \> Commerce email notification profile**.</span></span>
1. <span data-ttu-id="f7ab3-136">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="f7ab3-136">In the list, find and select the desired record.</span></span> 
1. <span data-ttu-id="f7ab3-137">Selecione o modelo de email na lista suspensa **ID do Email**.</span><span class="sxs-lookup"><span data-stu-id="f7ab3-137">Select the email template from the **Email ID** drop-down list.</span></span>
1. <span data-ttu-id="f7ab3-138">Selecione o **Tipo de notificação por email** apropriado na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="f7ab3-138">Select the appropriate **Email notification type** from the drop-down list.</span></span>
1. <span data-ttu-id="f7ab3-139">Marque a caixa de seleção **Ativo**.</span><span class="sxs-lookup"><span data-stu-id="f7ab3-139">Select the **Active** check box.</span></span>
1. <span data-ttu-id="f7ab3-140">No painel de ação, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="f7ab3-140">On the action pane, select **Save**.</span></span>

<span data-ttu-id="f7ab3-141">A imagem a seguir mostra alguns exemplos de configurações de notificação de evento.</span><span class="sxs-lookup"><span data-stu-id="f7ab3-141">The following image shows some example event notification settings.</span></span>

![Configurações de notificação de evento](media/email-notification-profile.png)

### <a name="next-steps"></a><span data-ttu-id="f7ab3-143">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="f7ab3-143">Next steps</span></span>

<span data-ttu-id="f7ab3-144">Para poder enviar emails, você deve configurar seu serviço de email de saída e configurar um trabalho em lotes.</span><span class="sxs-lookup"><span data-stu-id="f7ab3-144">Before you can send mails, you must configure your outgoing mail service and set up a batch job.</span></span> <span data-ttu-id="f7ab3-145">Para obter mais informações, consulte [Configurar e enviar email](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json).</span><span class="sxs-lookup"><span data-stu-id="f7ab3-145">For more information, see [Configure and send email](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json).</span></span>


## <a name="additional-resources"></a><span data-ttu-id="f7ab3-146">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="f7ab3-146">Additional resources</span></span>

[<span data-ttu-id="f7ab3-147">Configurar e enviar email</span><span class="sxs-lookup"><span data-stu-id="f7ab3-147">Configure and send email</span></span>](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json)

[<span data-ttu-id="f7ab3-148">Visão geral de canais</span><span class="sxs-lookup"><span data-stu-id="f7ab3-148">Channels overview</span></span>](channels-overview.md)

[<span data-ttu-id="f7ab3-149">Pré-requisitos de configuração de canal</span><span class="sxs-lookup"><span data-stu-id="f7ab3-149">Channel setup prerequisites</span></span>](channels-prerequisites.md)

[<span data-ttu-id="f7ab3-150">Visão geral de organizações e hierarquias organizacionais</span><span class="sxs-lookup"><span data-stu-id="f7ab3-150">Organizations and organizational hierarchies overview</span></span>](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
