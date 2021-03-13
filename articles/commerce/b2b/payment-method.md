---
title: Configurar o método de pagamento da conta do cliente para sites de comércio eletrônico B2B
description: Este tópico descreve como configurar o método de pagamento da conta do cliente para sites de comércio eletrônico business-to-business (B2B).
author: josaw1
manager: AnnBe
ms.date: 01/20/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailOperations
audience: Application User, IT Pro
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: retail
ms.author: josaw
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 754e2f83d6c8ff5d3698d98062e54bba7ccd9836
ms.sourcegitcommit: f9df202aefef761be52c0360b0e22da88773914c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/21/2021
ms.locfileid: "5035871"
---
# <a name="configure-the-customer-account-payment-method-for-b2b-e-commerce-sites"></a><span data-ttu-id="6e1ad-103">Configurar o método de pagamento da conta do cliente para sites de comércio eletrônico B2B</span><span class="sxs-lookup"><span data-stu-id="6e1ad-103">Configure the customer account payment method for B2B e-commerce sites</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="6e1ad-104">Este tópico descreve como configurar o método de pagamento da conta do cliente para sites de comércio eletrônico business-to-business (B2B).</span><span class="sxs-lookup"><span data-stu-id="6e1ad-104">This topic describes how to configure the customer account payment method for business-to-business (B2B) e-commerce sites.</span></span>

<span data-ttu-id="6e1ad-105">Os varejistas podem aceitar vários tipos de pagamento em troca de produtos e serviços vendidos em um canal de comércio eletrônico.</span><span class="sxs-lookup"><span data-stu-id="6e1ad-105">Retailers can accept various types of payment in exchange for the products and services that they sell in an e-commerce channel.</span></span> <span data-ttu-id="6e1ad-106">Cada tipo de pagamento que um varejista aceita deve ser configurado no Microsoft Dynamics 365 Commerce quando o sistema é configurado.</span><span class="sxs-lookup"><span data-stu-id="6e1ad-106">Each payment type that a retailer accepts must be configured in Microsoft Dynamics 365 Commerce when the system is set up.</span></span> <span data-ttu-id="6e1ad-107">O método de pagamento da conta do cliente (ou "por conta") deve ter suporte em sites de comércio eletrônico B2B.</span><span class="sxs-lookup"><span data-stu-id="6e1ad-107">The customer account (or "on account") payment method must be supported on B2B e-commerce sites.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="6e1ad-108">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="6e1ad-108">Prerequisites</span></span>

1. <span data-ttu-id="6e1ad-109">Adicione o método de pagamento da conta do cliente na sede do Commerce.</span><span class="sxs-lookup"><span data-stu-id="6e1ad-109">Add the customer account payment method in Commerce headquarters.</span></span>
2. <span data-ttu-id="6e1ad-110">Associe o método de pagamento da conta do cliente ao canal de comércio eletrônico.</span><span class="sxs-lookup"><span data-stu-id="6e1ad-110">Associate the customer account payment method with the e-commerce channel.</span></span>
3. <span data-ttu-id="6e1ad-111">Verifique se **Permitir por conta** está habilitado para o cliente em **Varejo e Comércio \> Clientes \> Todos os clientes \> Padrões de pagamentos** na sede do Commerce.</span><span class="sxs-lookup"><span data-stu-id="6e1ad-111">Make sure that **Allow on account** is enabled for the customer at **Retail and Commerce \> Customers \> All customers \> Payment defaults** in Commerce headquarters.</span></span> <span data-ttu-id="6e1ad-112">Verifique também se os parâmetros de **Limite de crédito** estão definidos corretamente para o cliente em **Varejo e Comércio \> Clientes \> Todos os clientes \> Crédito e Coleções** na sede do Commerce.</span><span class="sxs-lookup"><span data-stu-id="6e1ad-112">Also make sure that **Credit limit** parameters are set appropriately for the customer at **Retail and Commerce \> Customers \> All customers \> Credit and Collections** in Commerce headquarters.</span></span> 

## <a name="enable-the-customer-account-payment-method-in-commerce-site-builder"></a><span data-ttu-id="6e1ad-113">Habilitar o método de pagamento da conta do cliente no assistente para criação de sites do Commerce</span><span class="sxs-lookup"><span data-stu-id="6e1ad-113">Enable the customer account payment method in Commerce site builder</span></span> 

<span data-ttu-id="6e1ad-114">Para habilitar o método de pagamento da conta do cliente no assistente para criação de sites do Commerce, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="6e1ad-114">To enable the customer account payment method in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="6e1ad-115">Acesse **Configurações do Site \> Extensões**.</span><span class="sxs-lookup"><span data-stu-id="6e1ad-115">Go to **Site Settings \> Extensions**.</span></span>
1. <span data-ttu-id="6e1ad-116">Defina a propriedade **Habilitar pagamentos de conta do cliente** como **Habilitado para clientes B2B**.</span><span class="sxs-lookup"><span data-stu-id="6e1ad-116">Set the **Enable customer account payments** property to **Enabled for B2B customers**.</span></span> 
1. <span data-ttu-id="6e1ad-117">Selecione **Salvar e publicar**.</span><span class="sxs-lookup"><span data-stu-id="6e1ad-117">Select **Save and Publish**.</span></span>

> [!NOTE]
> <span data-ttu-id="6e1ad-118">As novas configurações de sites terão efeito somente após a atualização do arquivo app.settings.json.</span><span class="sxs-lookup"><span data-stu-id="6e1ad-118">The new site settings take effect only after the app.settings.json file is updated.</span></span> <span data-ttu-id="6e1ad-119">Para obter mais informações, consulte [SDK e atualizações da biblioteca de módulos](../e-commerce-extensibility/sdk-updates.md).</span><span class="sxs-lookup"><span data-stu-id="6e1ad-119">For more information, see [SDK and Module library updates](../e-commerce-extensibility/sdk-updates.md).</span></span>

## <a name="enable-the-customer-account-payment-method-on-the-checkout-page-for-the-b2b-e-commerce-site"></a><span data-ttu-id="6e1ad-120">Habilitar o método de pagamento da conta do cliente na página de finalização de compra para o site de comércio eletrônico B2B</span><span class="sxs-lookup"><span data-stu-id="6e1ad-120">Enable the customer account payment method on the checkout page for the B2B e-commerce site</span></span>

<span data-ttu-id="6e1ad-121">Para habilitar o método de pagamento da conta do cliente na página de finalização de compra para o site de comércio eletrônico B2B, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="6e1ad-121">To enable the customer account payment method on the checkout page for the B2B e-commerce site, follow these steps.</span></span>

1. <span data-ttu-id="6e1ad-122">No assistente para criação de sites do Commerce, encontre e edite a página de finalização de compra ou o fragmento que contenha o módulo de finalização de compra para o site de comércio eletrônico B2B.</span><span class="sxs-lookup"><span data-stu-id="6e1ad-122">In Commerce site builder, find and edit the checkout page or fragment that contains the checkout module for the B2B e-commerce site.</span></span>
1. <span data-ttu-id="6e1ad-123">No slot de **Contêiner da seção de finalização de compra**, selecione **Adicionar Módulo** e, depois, adicione um módulo **Pagamento de conta do cliente**.</span><span class="sxs-lookup"><span data-stu-id="6e1ad-123">In the **Checkout section container** slot, select **Add Module**, and then add a **Customer account payment** module.</span></span>
1. <span data-ttu-id="6e1ad-124">Para posicionar o módulo **Pagamento da conta do cliente**, selecione a elipse (**...**) e, depois, selecione **Mover para cima** ou **Mover para baixo**, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="6e1ad-124">Position the **Customer account payment** module by selecting the ellipsis (**...**), and then selecting **Move Up** or **Move Down** as required.</span></span>
1. <span data-ttu-id="6e1ad-125">Selecione **Salvar**, **Concluir edição** para fazer check-in da página e depois selecione **Publicar** para publicá-lo.</span><span class="sxs-lookup"><span data-stu-id="6e1ad-125">Select **Save**, select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="confirm-that-the-customer-account-payment-method-has-been-enabled-and-published"></a><span data-ttu-id="6e1ad-126">Confirme que o método de pagamento da conta do cliente foi ativado e publicado</span><span class="sxs-lookup"><span data-stu-id="6e1ad-126">Confirm that the customer account payment method has been enabled and published</span></span>

<span data-ttu-id="6e1ad-127">Para confirmar que o método de pagamento da conta do cliente foi ativado e publicado, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="6e1ad-127">To confirm that the customer account payment method has been enabled, follow these steps.</span></span>

1. <span data-ttu-id="6e1ad-128">Entre no site de comércio eletrônico.</span><span class="sxs-lookup"><span data-stu-id="6e1ad-128">Sign in to the e-commerce site.</span></span>
1. <span data-ttu-id="6e1ad-129">Adicione um produto ao carrinho.</span><span class="sxs-lookup"><span data-stu-id="6e1ad-129">Add a product to the cart.</span></span>
1. <span data-ttu-id="6e1ad-130">Acesse a página de finalização de compra.</span><span class="sxs-lookup"><span data-stu-id="6e1ad-130">Go to the checkout page.</span></span> <span data-ttu-id="6e1ad-131">Você deve ver o novo método de pagamento da **Conta do Cliente**.</span><span class="sxs-lookup"><span data-stu-id="6e1ad-131">You should see the new **Customer Account** payment method.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="6e1ad-132">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="6e1ad-132">Additional resources</span></span>

[<span data-ttu-id="6e1ad-133">Configurar um site de comércio eletrônico B2B</span><span class="sxs-lookup"><span data-stu-id="6e1ad-133">Set up a B2B e-commerce site</span></span>](set-up-b2b-site.md)

[<span data-ttu-id="6e1ad-134">Criar hierarquias de modelagem de organização para organizações B2B</span><span class="sxs-lookup"><span data-stu-id="6e1ad-134">Create org modeling hierarchies for B2B organizations</span></span>](org-model.md)

[<span data-ttu-id="6e1ad-135">Gerenciar usuários parceiros comerciais em sites de comércio eletrônico B2B</span><span class="sxs-lookup"><span data-stu-id="6e1ad-135">Manage business partner users on B2B e-commerce sites</span></span>](manage-b2b-users.md)

[<span data-ttu-id="6e1ad-136">Definir limites de quantidade de produto para sites de comércio eletrônico B2B</span><span class="sxs-lookup"><span data-stu-id="6e1ad-136">Set product quantity limits for B2B e-commerce sites</span></span>](quantity-limits.md)

[<span data-ttu-id="6e1ad-137">SDK e atualizações da biblioteca de módulos</span><span class="sxs-lookup"><span data-stu-id="6e1ad-137">SDK and Module library updates</span></span>](../e-commerce-extensibility/sdk-updates.md)
