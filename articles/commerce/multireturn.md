---
title: Devolver itens em várias ordens e faturas de clientes
description: Este tópico descreve a funcionalidade que habilita as devoluções em várias ordens e faturas de clientes no Dynamics 365 Commerce.
author: josaw1
ms.date: 08/27/2020
ms.topic: index-page
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-01-15
ms.dyn365.ops.version: 10
ms.openlocfilehash: 4a64794a0e04516441fab628d441640e4d154b8d
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5796874"
---
# <a name="return-items-across-multiple-customer-orders-and-invoices"></a><span data-ttu-id="01fa4-103">Devolver itens em várias ordens e faturas de clientes</span><span class="sxs-lookup"><span data-stu-id="01fa4-103">Return items across multiple customer orders and invoices</span></span>

[!include [banner](includes/banner.md)]


<span data-ttu-id="01fa4-104">Este artigo descreve dois recursos que otimizam a devolução de ordens de clientes em várias faturas.</span><span class="sxs-lookup"><span data-stu-id="01fa4-104">This article describes two features that optimize customer order returns over multiple invoices.</span></span> 

## <a name="enable-refunds-over-multiple-captures"></a><span data-ttu-id="01fa4-105">Habilitar reembolsos em várias capturas</span><span class="sxs-lookup"><span data-stu-id="01fa4-105">Enable refunds over multiple captures</span></span>

<span data-ttu-id="01fa4-106">Este recurso permite vários reembolsos vinculados em relação à mesma ordem do cliente.</span><span class="sxs-lookup"><span data-stu-id="01fa4-106">This feature enables multiple linked refunds against the same customer order.</span></span> 

1. <span data-ttu-id="01fa4-107">Acesse o espaço de trabalho **Gerenciamento de recursos** e procure **Habilitar reembolsos em várias capturas**.</span><span class="sxs-lookup"><span data-stu-id="01fa4-107">Go to the **Feature management** workspace and search for **Enable refunds over multiple captures**.</span></span>
2. <span data-ttu-id="01fa4-108">Selecione **Habilitar reembolsos em várias ordens** e clique em **Habilitar**.</span><span class="sxs-lookup"><span data-stu-id="01fa4-108">Select **Enable refunds over multiple orders** and then click **Enable**.</span></span> 

## <a name="enable-proper-tax-calculation-for-returns-with-partial-quantity"></a><span data-ttu-id="01fa4-109">Habilitar o cálculo de imposto apropriado para devoluções com quantidade parcial</span><span class="sxs-lookup"><span data-stu-id="01fa4-109">Enable proper tax calculation for returns with partial quantity</span></span>

<span data-ttu-id="01fa4-110">Esse recurso garante que, quando uma ordem é devolvida com várias faturas, os impostos serão basicamente iguais ao valor do imposto cobrado originalmente.</span><span class="sxs-lookup"><span data-stu-id="01fa4-110">This feature ensures that when an order is returned using multiple invoices, the taxes will ultimately be equal to the tax amount originally charged.</span></span> 

1. <span data-ttu-id="01fa4-111">Acesse o espaço de trabalho **Gerenciamento de recursos** e procure **Habilitar o cálculo de imposto apropriado para devoluções com quantidade parcial**.</span><span class="sxs-lookup"><span data-stu-id="01fa4-111">Go to the **Feature management** workspace and search for **Enable proper tax calculation for returns with partial quantity**.</span></span>
2. <span data-ttu-id="01fa4-112">Selecione **Habilitar o cálculo de imposto apropriado para devoluções com quantidade parcial** e clique em **Habilitar**.</span><span class="sxs-lookup"><span data-stu-id="01fa4-112">Select **Enable proper tax calculation for returns with partial quantity** and then click **Enable**.</span></span> 


## <a name="process-returns"></a><span data-ttu-id="01fa4-113">Processar devoluções</span><span class="sxs-lookup"><span data-stu-id="01fa4-113">Process returns</span></span>

<span data-ttu-id="01fa4-114">Depois que recursos forem ativados e as alterações forem sincronizadas com as lojas, o operador de caixa da loja poderá selecionar várias ordens de venda de um cliente para a devolução.</span><span class="sxs-lookup"><span data-stu-id="01fa4-114">After these features are turned on and the changes are synchronized to the stores, the cashier in the store can select multiple sales orders for a customer for their return.</span></span>

<span data-ttu-id="01fa4-115">Quando as ordens estiverem selecionadas, uma lista de todos os produtos retornáveis em todas as faturas das ordens será exibida.</span><span class="sxs-lookup"><span data-stu-id="01fa4-115">When the orders are selected, a list of all the returnable products across all the invoices for the orders will display.</span></span> <span data-ttu-id="01fa4-116">O operador de caixa poderá então selecionar os produtos para devolução.</span><span class="sxs-lookup"><span data-stu-id="01fa4-116">The cashier can then select the products to return.</span></span> <span data-ttu-id="01fa4-117">Uma única ordem de devolução será criada para todos os produtos selecionados.</span><span class="sxs-lookup"><span data-stu-id="01fa4-117">A single return order will be created for all the selected products.</span></span>

<span data-ttu-id="01fa4-118">Se a ordem for totalmente devolvida, o valor dos impostos devolvidos ao cliente será igual ao valor do imposto cobrado originalmente.</span><span class="sxs-lookup"><span data-stu-id="01fa4-118">If the order is fully returned, the amount of taxes returned to the customer will be equal to the amount of tax originally charged.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]