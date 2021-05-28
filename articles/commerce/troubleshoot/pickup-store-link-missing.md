---
title: A opção Retirar este item não aparece nas páginas de detalhes do carrinho ou do produto
description: Este tópico fornece orientações de solução de problemas que podem ajudar quando a opção de retirada na loja não aparece na página do carrinho ou nas páginas de detalhes do produto.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: f692d73bf1755422e9bfc8314c1156e043ccf761
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6020795"
---
# <a name="pick-this-up-option-doesnt-appear-on-cart-or-product-details-pages"></a><span data-ttu-id="caf12-103">A opção "Retirar este item" não aparece nas páginas de detalhes do carrinho ou do produto</span><span class="sxs-lookup"><span data-stu-id="caf12-103">"Pick this up" option doesn't appear on cart or product details pages</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="caf12-104">Este tópico fornece orientações de solução de problemas que podem ajudar quando a opção de retirada na loja não aparece na página do carrinho ou nas páginas de detalhes do produto.</span><span class="sxs-lookup"><span data-stu-id="caf12-104">This topic provides troubleshooting guidance that can help when the option for in-store pickup doesn't appear on the cart page or product details pages.</span></span>

## <a name="description"></a><span data-ttu-id="caf12-105">descrição</span><span class="sxs-lookup"><span data-stu-id="caf12-105">Description</span></span>

<span data-ttu-id="caf12-106">O botão **Retirar este item** não aparece nas páginas de detalhes do carrinho ou do produto.</span><span class="sxs-lookup"><span data-stu-id="caf12-106">The **Pick this up** button doesn't appear on the cart page or product details pages.</span></span>

<span data-ttu-id="caf12-107">A ilustração a seguir mostra um exemplo de uma página que inclui o botão **Retirar este item**.</span><span class="sxs-lookup"><span data-stu-id="caf12-107">The following illustration shows an example of a page that includes the **Pick this up** button.</span></span>

![Botão Retirar este item](media/pickup-button-missing.jpg)

## <a name="resolution"></a><span data-ttu-id="caf12-109">Resolução</span><span class="sxs-lookup"><span data-stu-id="caf12-109">Resolution</span></span>

### <a name="enable-the-bopis-extension-in-commerce-site-builder"></a><span data-ttu-id="caf12-110">Habilitar a extensão de BOPIS no criador de sites do Commerce</span><span class="sxs-lookup"><span data-stu-id="caf12-110">Enable the BOPIS extension in Commerce site builder</span></span>

<span data-ttu-id="caf12-111">Para habilitar a extensão "comprar online, retirar na Store" (BOPIS) no criador de sites do Commerce, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="caf12-111">To enable the "buy online, pick up in store" (BOPIS) extension in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="caf12-112">Selecione seu site.</span><span class="sxs-lookup"><span data-stu-id="caf12-112">Select your site.</span></span>
1. <span data-ttu-id="caf12-113">Selecione **Configurações do site** e, em seguida, selecione **Extensões**.</span><span class="sxs-lookup"><span data-stu-id="caf12-113">Select **Site settings**, and then select **Extensions**.</span></span>
1. <span data-ttu-id="caf12-114">Verifique se a opção **Desativar BOPIS** está desmarcada.</span><span class="sxs-lookup"><span data-stu-id="caf12-114">Make sure that the **Disable BOPIS** option is cleared.</span></span>

### <a name="configure-modes-of-delivery-in-commerce-headquarters"></a><span data-ttu-id="caf12-115">Configurar modos de entrega na matriz do Commerce</span><span class="sxs-lookup"><span data-stu-id="caf12-115">Configure modes of delivery in Commerce headquarters</span></span>

<span data-ttu-id="caf12-116">Para configurar modos de entrega na matriz do Commerce, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="caf12-116">To configure modes of delivery in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="caf12-117">Vá para **Compras e fornecimento \> Configuração \> Modos de entrega**.</span><span class="sxs-lookup"><span data-stu-id="caf12-117">Go to **Procurement and sourcing \> Setup \> Modes of delivery**.</span></span>
1. <span data-ttu-id="caf12-118">Verifique se o modo de entrega **Retirada do cliente** foi criado e se os produtos e endereços estão atribuídos a ele.</span><span class="sxs-lookup"><span data-stu-id="caf12-118">Make sure that a **Customer pickup** mode of delivery has been created, and that products and addresses are assigned to it.</span></span>
1. <span data-ttu-id="caf12-119">Vá para **Varejo e Comércio \> Configuração da sede \> Parâmetros**.</span><span class="sxs-lookup"><span data-stu-id="caf12-119">Go to **Retail and Commerce \> Headquarters setup \> Parameters**.</span></span>
1. <span data-ttu-id="caf12-120">No painel de navegação à esquerda, selecione **Ordens do cliente**.</span><span class="sxs-lookup"><span data-stu-id="caf12-120">In the left navigation, select **Customer orders**.</span></span>
1. <span data-ttu-id="caf12-121">Verifique se o **Modo de entrega de retirada** está configurado corretamente.</span><span class="sxs-lookup"><span data-stu-id="caf12-121">Make sure that **Pickup mode of delivery** is correctly configured.</span></span>

### <a name="configure-customer-orders-payments"></a><span data-ttu-id="caf12-122">Configurar pagamentos de ordens de cliente</span><span class="sxs-lookup"><span data-stu-id="caf12-122">Configure customer orders payments</span></span>

<span data-ttu-id="caf12-123">Para configurar pagamentos de ordens do cliente na matriz do Commerce, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="caf12-123">To configure customer orders payments in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="caf12-124">Vá para **Varejo e Comércio \> Configuração da sede \> Parâmetros**.</span><span class="sxs-lookup"><span data-stu-id="caf12-124">Go to **Retail and Commerce \> Headquarters setup \> Parameters**.</span></span>
1. <span data-ttu-id="caf12-125">No painel de navegação à esquerda, selecione **Ordens do cliente**.</span><span class="sxs-lookup"><span data-stu-id="caf12-125">In the left navigation, select **Customer orders**.</span></span>
1. <span data-ttu-id="caf12-126">Na guia rápida **Pagamentos**, verifique se os campos **Condições de pagamento** e **Método de pagamento** estão definidos corretamente.</span><span class="sxs-lookup"><span data-stu-id="caf12-126">On the **Payments** FastTab, make sure that the **Terms of payment** and **Method of payment** fields are correctly set.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="caf12-127">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="caf12-127">Additional resources</span></span>

[<span data-ttu-id="caf12-128">Configurar BOPIS</span><span class="sxs-lookup"><span data-stu-id="caf12-128">Configure BOPIS</span></span>](../cpe-bopis.md)

[<span data-ttu-id="caf12-129">Habilitar vários modos de entrega de retirada para ordens de cliente</span><span class="sxs-lookup"><span data-stu-id="caf12-129">Enable multiple pickup delivery modes for customer orders</span></span>](../multiple-pickup-modes.md)

[<span data-ttu-id="caf12-130">Pagamentos de ordens de omnicanal do Commerce</span><span class="sxs-lookup"><span data-stu-id="caf12-130">Omni-channel Commerce order payments</span></span>](../dev-itpro/commerce-payments.md)

[<span data-ttu-id="caf12-131">Módulo de seletor de loja</span><span class="sxs-lookup"><span data-stu-id="caf12-131">Store selector module</span></span>](../store-selector.md)
