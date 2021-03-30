---
title: Personalizar emails transacionais por modo de entrega
description: Este tópico descreve como configurar modelos de email personalizados para tipos específicos de notificação e modos de entrega no Microsoft Dynamics 365 Commerce.
author: stuharg
manager: annbe
ms.date: 11/16/2020
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
ms.search.validFrom: 2020-10-26
ms.dyn365.ops.version: Release 10.0.16
ms.openlocfilehash: d0d96ddb20b2b09751d8c0c0bf8af713de35279a
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5222624"
---
# <a name="customize-transactional-emails-by-mode-of-delivery"></a><span data-ttu-id="5cbfd-103">Personalizar emails transacionais por modo de entrega</span><span class="sxs-lookup"><span data-stu-id="5cbfd-103">Customize transactional emails by mode of delivery</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="5cbfd-104">Este tópico descreve como configurar modelos de email personalizados para tipos específicos de notificação e modos de entrega no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="5cbfd-104">This topic describes how to set up custom email templates for specific notification types and modes of delivery in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="5cbfd-105">Agora, os emails transacionais podem ser personalizados para uma combinação de um tipo de notificação (por exemplo, **Ordem criada**, **Ordem embalada** ou **Ordem faturada**) e um modo de entrega (por exemplo, à noite, retirada na loja ou retirada em frente à loja).</span><span class="sxs-lookup"><span data-stu-id="5cbfd-105">Transactional emails can now be customized for a combination of a notification type (for example, **Order created**, **Order packed**, or **Order invoiced**) and a mode of delivery (for example, overnight, in-store pickup, or curbside pickup).</span></span> <span data-ttu-id="5cbfd-106">Os emails transacionais personalizados permitem que os varejistas forneçam aos clientes experiências de atendimento personalizadas para o modo de entrega da ordem.</span><span class="sxs-lookup"><span data-stu-id="5cbfd-106">Custom transactional emails let retailers provide their customers order with fulfillment experiences that are tailored to the order's mode of delivery.</span></span> <span data-ttu-id="5cbfd-107">Por exemplo, o evento "ordem embalada" pode ser personalizado de forma que forneça instruções de retirada em frente à loja para clientes que optam por retirada em frente à loja.</span><span class="sxs-lookup"><span data-stu-id="5cbfd-107">For example, the "order packed" event can be customized so that it provides curbside pickup instructions for customers who choose curbside pickup.</span></span> <span data-ttu-id="5cbfd-108">Como alternativa, ele pode fornecer informações da operadora de remessa e de entrega para clientes que optam por ordem enviada.</span><span class="sxs-lookup"><span data-stu-id="5cbfd-108">Alternatively, it can provide shipping carrier and delivery information for customers who choose to have their order shipped.</span></span>

> [!NOTE]
> <span data-ttu-id="5cbfd-109">Para usar a funcionalidade para emails transacionais personalizados, primeiro você deve ativar o recurso **Personalizar modelos de email transacional por modo de entrega**, acessando **Espaços de trabalho \> Gerenciamento de recursos** na sede do Commerce.</span><span class="sxs-lookup"><span data-stu-id="5cbfd-109">To use the functionality for customized transactional emails, you first must turn on the **Customize transactional email templates by mode of delivery** feature by going to **Workspaces \> Feature management** in Commerce headquarters.</span></span>

<span data-ttu-id="5cbfd-110">Os emails podem ser personalizados por modo de entrega para os seguintes tipos de notificação:</span><span class="sxs-lookup"><span data-stu-id="5cbfd-110">Emails can be customized by mode of delivery for the following notification types:</span></span>

- <span data-ttu-id="5cbfd-111">**Cancelamento da ordem** – este tipo de notificação por email é novo.</span><span class="sxs-lookup"><span data-stu-id="5cbfd-111">**Order cancellation** – This email notification type is new.</span></span>
- <span data-ttu-id="5cbfd-112">**Ordem criada**</span><span class="sxs-lookup"><span data-stu-id="5cbfd-112">**Order created**</span></span>
- <span data-ttu-id="5cbfd-113">**Ordem confirmada**</span><span class="sxs-lookup"><span data-stu-id="5cbfd-113">**Order confirmed**</span></span>
- <span data-ttu-id="5cbfd-114">**Ordem faturada** – este tipo de notificação por email é novo.</span><span class="sxs-lookup"><span data-stu-id="5cbfd-114">**Order invoiced** – This email notification type is new.</span></span> <span data-ttu-id="5cbfd-115">Ele pode ser usado em vez do tipo de notificação **Ordem enviada** que enviará uma notificação para qualquer evento de fatura que tenha um modo de entrega enviado (não um modo de entrega por retirada, execução ou eletrônica).</span><span class="sxs-lookup"><span data-stu-id="5cbfd-115">It can be used instead of the **Order shipped** notification type that will send a notification for any invoice event that has a shipped mode of delivery (not a pickup, carry out, or electronic mode of delivery).</span></span>
- <span data-ttu-id="5cbfd-116">**Ordem separada**</span><span class="sxs-lookup"><span data-stu-id="5cbfd-116">**Order picked**</span></span>
- <span data-ttu-id="5cbfd-117">**Ordem embalada**</span><span class="sxs-lookup"><span data-stu-id="5cbfd-117">**Order packed**</span></span>
- <span data-ttu-id="5cbfd-118">**Ordem pronta para retirada** – este tipo de notificação só poderá ser personalizado por modo de entrega somente se o recurso **Suporte a vários modos de entrega de retirada** estiver ativado.</span><span class="sxs-lookup"><span data-stu-id="5cbfd-118">**Order ready for pickup** – This notification type can be customized by mode of delivery only if the **Support for multiple pickup delivery modes** feature is turned on.</span></span> <span data-ttu-id="5cbfd-119">Nesse caso, esse tipo de notificação é funcionalmente equivalente ao tipo de notificação **Ordem embalada**.</span><span class="sxs-lookup"><span data-stu-id="5cbfd-119">In that case, this notification type is functionally equivalent to the **Order packed** notification type.</span></span>
- <span data-ttu-id="5cbfd-120">**Falha no pagamento**</span><span class="sxs-lookup"><span data-stu-id="5cbfd-120">**Payment failed**</span></span>
- <span data-ttu-id="5cbfd-121">**Ordem de substituição criada**</span><span class="sxs-lookup"><span data-stu-id="5cbfd-121">**Replacement order created**</span></span>

## <a name="configure-email-templates-for-specific-modes-of-delivery"></a><span data-ttu-id="5cbfd-122">Configurar modelos de email para modos de entrega específicos</span><span class="sxs-lookup"><span data-stu-id="5cbfd-122">Configure email templates for specific modes of delivery</span></span>

<span data-ttu-id="5cbfd-123">Para esse procedimento, a suposição é que você já tenha criado novos modelos de email personalizados e os adicionou à página **Modelos de email da organização**.</span><span class="sxs-lookup"><span data-stu-id="5cbfd-123">For this procedure, the assumption is that you've already created your new, custom email templates and added them to the **Organization email templates** page.</span></span> <span data-ttu-id="5cbfd-124">Para obter informações sobre como criar e carregar modelos de email, consulte [Criar modelos de email para eventos transacionais](email-templates-transactions.md).</span><span class="sxs-lookup"><span data-stu-id="5cbfd-124">For information about how to create and upload email templates, see [Create email templates for transactional events](email-templates-transactions.md).</span></span>

<span data-ttu-id="5cbfd-125">Para configurar modelos de email para modos de entrega específicos na sede do Commerce, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="5cbfd-125">To configure email templates for specific modes of delivery in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="5cbfd-126">Vá para **Perfil de notificação por email do Commerce**.</span><span class="sxs-lookup"><span data-stu-id="5cbfd-126">Go to **Commerce email notification profile**.</span></span>
1. <span data-ttu-id="5cbfd-127">Em **Configurações de notificação de eventos de varejo**, selecione um tipo de notificação existente.</span><span class="sxs-lookup"><span data-stu-id="5cbfd-127">Under **Retail event notification settings**, select an existing notification type.</span></span>
1. <span data-ttu-id="5cbfd-128">Enquanto o tipo de notificação ainda estiver selecionado, selecione **Configurar modos de entrega**.</span><span class="sxs-lookup"><span data-stu-id="5cbfd-128">While the notification type is still selected, select **Configure modes of delivery**.</span></span>
1. <span data-ttu-id="5cbfd-129">Na caixa de diálogo **Modos de entrega**, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="5cbfd-129">In the **Modes of delivery** dialog box, select **New**.</span></span>
1. <span data-ttu-id="5cbfd-130">Na nova linha, no campo **Modo de entrega**, selecione um modo de entrega.</span><span class="sxs-lookup"><span data-stu-id="5cbfd-130">In the new row, in the **Mode of delivery** field, select a mode of delivery.</span></span>
1. <span data-ttu-id="5cbfd-131">No campo **ID de email**, selecione o modelo de email a ser mapeado para o modo de entrega.</span><span class="sxs-lookup"><span data-stu-id="5cbfd-131">In the **Email ID** field, select the email template to map to the mode of delivery.</span></span>
1. <span data-ttu-id="5cbfd-132">Marque a caixa de seleção **Ativo**.</span><span class="sxs-lookup"><span data-stu-id="5cbfd-132">Select the **Active** check box.</span></span>
1. <span data-ttu-id="5cbfd-133">Repita as etapas 4 a 7 para adicionar mais modos de entrega.</span><span class="sxs-lookup"><span data-stu-id="5cbfd-133">Repeat steps 4 through 7 to add more modes of delivery.</span></span>
1. <span data-ttu-id="5cbfd-134">Quando terminar, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="5cbfd-134">When you've finished, select **OK**.</span></span>

> [!NOTE]
> - <span data-ttu-id="5cbfd-135">Quando mais de um modo de entrega estiver presente em linhas de uma ordem de venda, o modelo padrão será usado.</span><span class="sxs-lookup"><span data-stu-id="5cbfd-135">When more than one mode of delivery is present across lines in a sales order, the default template will be used.</span></span> <span data-ttu-id="5cbfd-136">O modelo padrão é o modelo mapeado para o tipo de notificação na página **Perfil de notificação de email no Commerce**.</span><span class="sxs-lookup"><span data-stu-id="5cbfd-136">The default template is the template that is mapped to the notification type on the **Commerce email notification profile** page.</span></span>
> - <span data-ttu-id="5cbfd-137">Se uma ordem de venda tiver um modo de entrega ainda não configurado para um modelo de email personalizado, o modelo de email padrão será usado.</span><span class="sxs-lookup"><span data-stu-id="5cbfd-137">If a sales order has a mode of delivery that hasn't been configured for a custom email template, the default email template will be used.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="5cbfd-138">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="5cbfd-138">Additional resources</span></span>

[<span data-ttu-id="5cbfd-139">Criar ordens de call center</span><span class="sxs-lookup"><span data-stu-id="5cbfd-139">Create call center orders</span></span>](tasks/create-call-center-orders.md)

[<span data-ttu-id="5cbfd-140">Alterar modo de entrega no PDV</span><span class="sxs-lookup"><span data-stu-id="5cbfd-140">Change mode of delivery in POS</span></span>](pos-change-delivery-mode.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]