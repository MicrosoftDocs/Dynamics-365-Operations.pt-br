---
title: Restringir métodos de pagamento para devoluções sem recibos
description: Este tópico descreve como determinados tipos de pagamento podem ser restritos para o reembolso se as devoluções forem feitas sem recebimento.
author: rapraj
manager: AnnBe
ms.date: 03/05/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailTenderTypeTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 15831
ms.assetid: 465893a5-6b4f-4c5f-b305-db071df2d33f
ms.search.region: global
ms.search.industry: Retail
ms.author: yabinl
ms.search.validFrom: 2019-02-01
ms.dyn365.ops.version: AX 10.0.0, Retail Feb 2019 update
ms.openlocfilehash: 22e675fd9b7ee33c89f52ac4c8c15807580b86a7
ms.sourcegitcommit: b806f0c94d703bec39680fead827733361d47045
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/07/2020
ms.locfileid: "2935843"
---
# <a name="restrict-payment-methods-for-returns-without-a-receipt"></a><span data-ttu-id="f2303-103">Restringir métodos de pagamento para devoluções sem recibos</span><span class="sxs-lookup"><span data-stu-id="f2303-103">Restrict payment methods for returns without a receipt</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="f2303-104">Cada tipo de pagamento que o varejista aceita deve ser configurado quando o sistema for configurado.</span><span class="sxs-lookup"><span data-stu-id="f2303-104">Each payment type that a retailer accepts must be configured when the system is set up.</span></span> <span data-ttu-id="f2303-105">Este tópico descreve como determinados tipos de pagamento podem ser restritos para o reembolso se as devoluções forem feitas sem recebimento.</span><span class="sxs-lookup"><span data-stu-id="f2303-105">This topic describes how certain payment types can be restricted for refund if the returns are made without a receipt.</span></span>

## <a name="set-up-payment-methods"></a><span data-ttu-id="f2303-106">Configurar métodos de pagamento</span><span class="sxs-lookup"><span data-stu-id="f2303-106">Set up payment methods</span></span>

<span data-ttu-id="f2303-107">Para configurar métodos de pagamento, as seguintes tarefas devem ser concluídas.</span><span class="sxs-lookup"><span data-stu-id="f2303-107">To set up payment methods, the following tasks must be completed.</span></span>
1. <span data-ttu-id="f2303-108">Criar os métodos de pagamento aceitos pela organização inteira.</span><span class="sxs-lookup"><span data-stu-id="f2303-108">Create the payment methods that are accepted by the entire organization.</span></span>
2. <span data-ttu-id="f2303-109">Criar tipos e números de cartão no nível da organização.</span><span class="sxs-lookup"><span data-stu-id="f2303-109">Create organization-wide card types and card numbers.</span></span> <span data-ttu-id="f2303-110">Se cartões de crédito ou de débito forem aceitos, você deve criar um tipo de método de pagamento com cartões e os tipos e números de cartão no nível da organização.</span><span class="sxs-lookup"><span data-stu-id="f2303-110">If credit cards or debit cards are accepted, you must create one payment method for cards, and then create the organization-wide card types and card numbers.</span></span>
3. <span data-ttu-id="f2303-111">Configurar métodos de pagamento da loja.</span><span class="sxs-lookup"><span data-stu-id="f2303-111">Set up store payment methods.</span></span> <span data-ttu-id="f2303-112">Associe métodos de pagamento a cada loja e insira as configurações específicas da loja para cada método de pagamento.</span><span class="sxs-lookup"><span data-stu-id="f2303-112">Associate payment methods with each store, and then enter the store-specific settings for each payment method.</span></span>
4. <span data-ttu-id="f2303-113">Configurar métodos de pagamento de cartão para lojas.</span><span class="sxs-lookup"><span data-stu-id="f2303-113">Set up card payment methods for stores.</span></span> <span data-ttu-id="f2303-114">Para todos os métodos de pagamento de cartão que a loja aceita, conclua a configuração do cartão.</span><span class="sxs-lookup"><span data-stu-id="f2303-114">For any card payment methods that the store accepts, complete the card setup.</span></span>

<span data-ttu-id="f2303-115">![Configuração de Loja de Varejo](media/NoReceiptReturns1.png "Configuração de Loja de Varejo")</span><span class="sxs-lookup"><span data-stu-id="f2303-115">![Retail Store Setup](media/NoReceiptReturns1.png "Retail Store Setup")</span></span> 


## <a name="restrict-payment-methods-for-returns-without-a-receipt"></a><span data-ttu-id="f2303-116">Restringir métodos de pagamento para devoluções sem recibos</span><span class="sxs-lookup"><span data-stu-id="f2303-116">Restrict payment methods for returns without a receipt</span></span>

<span data-ttu-id="f2303-117">Para cada método de pagamento da loja, na página **Gerenciamento de loja de Varejo** , em **Devoluções sem recibos**, defina **Restringir métodos de pagamento para devoluções sem recibos** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="f2303-117">For each store payment method, on the **Retail store management** page, under **Non receipt returns**, set **Restrict for refunds without receipt** to **Yes**.</span></span> 

<span data-ttu-id="f2303-118">O valor padrão de alternância é **Não**, o que garante que o método de pagamento seja permitido para reembolsos.</span><span class="sxs-lookup"><span data-stu-id="f2303-118">The default value of the toggle is **No**, which ensures that the payment method is allowed for refunds.</span></span> 

<span data-ttu-id="f2303-119">Quando **Restringir para reembolsos sem recibo** for definido como **Sim**, o método de pagamento selecionado não será permitido para reembolsos.</span><span class="sxs-lookup"><span data-stu-id="f2303-119">When **Restrict for refunds without receipt** is set to **Yes**, the selected payment method will not be allowed for refunds.</span></span> 

<span data-ttu-id="f2303-120">![Método de pagamento da Loja de Varejo](media/NoReceiptReturns3.png "Método de Pagamento da Loja de Varejo")</span><span class="sxs-lookup"><span data-stu-id="f2303-120">![Retail Store payment method](media/NoReceiptReturns3.png "Retail Store Payment Method")</span></span> 

> [!NOTE]
> <span data-ttu-id="f2303-121">Quando um caixa seleciona um método de pagamento que é restrito para o reembolso sem um recibo, será exibida uma mensagem para verificar os métodos de pagamento aceitáveis.</span><span class="sxs-lookup"><span data-stu-id="f2303-121">When a cashier selects a payment method that is restricted for refund without a receipt, a message displays to verify the acceptable payment methods.</span></span>

<span data-ttu-id="f2303-122">![Métodos de pagamento aceitáveis](media/NoReceiptReturns4.png "Métodos de pagamento aceitáveis")</span><span class="sxs-lookup"><span data-stu-id="f2303-122">![Acceptable payment methods](media/NoReceiptReturns4.png "Acceptable payment methods")</span></span> 

<span data-ttu-id="f2303-123">Se uma transação tiver uma devolução com recibo e uma sem recibo, as condições de restrição não serão impostas porque a transação será um fluxo de trabalho de devolução com um recibo.</span><span class="sxs-lookup"><span data-stu-id="f2303-123">If a transaction has both a receipted return and a return without a receipt, the restriction conditions will not be enforced because the transaction will be a return workflow with a receipt.</span></span> 

