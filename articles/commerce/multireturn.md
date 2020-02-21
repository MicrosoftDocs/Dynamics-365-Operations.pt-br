---
title: Devolver itens em várias ordens e faturas de clientes
description: Este tópico descreve a funcionalidade que habilita as devoluções em várias ordens e faturas de clientes no Dynamics 365 Commerce.
author: josaw1
manager: AnnBe
ms.date: 03/05/2019
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-01-15
ms.dyn365.ops.version: 10
ms.openlocfilehash: c5f17424f0837344030f9ce2d2d037cde08c4e49
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/01/2020
ms.locfileid: "3004449"
---
# <a name="return-items-across-multiple-customer-orders-and-invoices"></a><span data-ttu-id="9f959-103">Devolver itens em várias ordens e faturas de clientes</span><span class="sxs-lookup"><span data-stu-id="9f959-103">Return items across multiple customer orders and invoices</span></span>

[!include [banner](includes/banner.md)]


<span data-ttu-id="9f959-104">É possível fazer devoluções em várias ordens e faturas de clientes.</span><span class="sxs-lookup"><span data-stu-id="9f959-104">Returns can be made across multiple orders and invoices.</span></span> 

## <a name="configure-commerce-to-support-returns-across-multiple-customer-order-and-invoices"></a><span data-ttu-id="9f959-105">Configurar o Commerce para oferecer suporte a devoluções em várias ordens e faturas de clientes</span><span class="sxs-lookup"><span data-stu-id="9f959-105">Configure Commerce to support returns across multiple customer order and invoices</span></span>

1. <span data-ttu-id="9f959-106">Acesse **Parâmetros de comércio \> Ordens de cliente**.</span><span class="sxs-lookup"><span data-stu-id="9f959-106">Go to **Commerce parameters \> Customer orders**.</span></span>
1. <span data-ttu-id="9f959-107">Ative o parâmetro **Habilitar devoluções para várias ordens**.</span><span class="sxs-lookup"><span data-stu-id="9f959-107">Turn on the **Enable returns for multiple orders** parameter.</span></span> 

## <a name="process-returns"></a><span data-ttu-id="9f959-108">Processar devoluções</span><span class="sxs-lookup"><span data-stu-id="9f959-108">Process returns</span></span>

<span data-ttu-id="9f959-109">Depois que o parâmetro for ativado e as alterações forem sincronizadas com as lojas, o operador de caixa da loja poderá selecionar várias ordens de venda de um cliente para sua devolução.</span><span class="sxs-lookup"><span data-stu-id="9f959-109">After the parameter is turned on and the changes are synchronized to the stores, the cashier in the store can select multiple sales orders for a customer for their return.</span></span>

<span data-ttu-id="9f959-110">Quando as ordens estiverem selecionadas, uma lista de todos os produtos retornáveis em todas as faturas das ordens será exibida.</span><span class="sxs-lookup"><span data-stu-id="9f959-110">When the orders are selected, a list of all the returnable products across all the invoices for the orders will display.</span></span> <span data-ttu-id="9f959-111">O operador de caixa poderá então selecionar os produtos para devolução.</span><span class="sxs-lookup"><span data-stu-id="9f959-111">The cashier can then select the products to return.</span></span> <span data-ttu-id="9f959-112">Uma única ordem de devolução será criada para todos os produtos selecionados.</span><span class="sxs-lookup"><span data-stu-id="9f959-112">A single return order will be created for all the selected products.</span></span>
