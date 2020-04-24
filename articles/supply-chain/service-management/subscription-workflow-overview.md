---
title: Visão geral do fluxo de trabalho de subscrições
description: Este tópico oferece uma visão geral do fluxo de trabalho de subscrições.
author: ShylaThompson
manager: tfehr
ms.date: 05/07/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMASubscriptionGroup, SMASubscriptionCreateDialog
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0cb8b86ef0e2a1bd90590c8cc2a20e18e82ef9c6
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3206579"
---
# <a name="subscription-workflow-overview"></a><span data-ttu-id="d0e4e-103">Visão geral do fluxo de trabalho de subscrições</span><span class="sxs-lookup"><span data-stu-id="d0e4e-103">Subscription workflow overview</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="d0e4e-104">Você é o administrador de subscrições de uma empresa de iluminação que oferece subscrições para a manutenção de equipamentos de luz.</span><span class="sxs-lookup"><span data-stu-id="d0e4e-104">You are the subscriptions administrator for a light company that offers subscriptions for lighting rig maintenance.</span></span> <span data-ttu-id="d0e4e-105">Um cliente entra em contato com a sua empresa para adquirir uma subscrição anual para a manutenção de equipamentos de luz.</span><span class="sxs-lookup"><span data-stu-id="d0e4e-105">A customer contacts your company to purchase a yearly subscription for lighting rig maintenance.</span></span>

## <a name="setting-up-subscriptions"></a><span data-ttu-id="d0e4e-106">Configurando subscrições</span><span class="sxs-lookup"><span data-stu-id="d0e4e-106">Setting up subscriptions</span></span>

<span data-ttu-id="d0e4e-107">Para configurar uma subscrição, você deve primeiro criar um grupo de subscrições para o novo contrato de serviço ou verificar se já existe um grupo de subscrições.</span><span class="sxs-lookup"><span data-stu-id="d0e4e-107">To set up a subscription, you must first create a subscription group for the new service agreement or verify that a subscription group exists.</span></span> <span data-ttu-id="d0e4e-108">Se já existir um grupo, você deverá configurá-lo para faturar o cliente anualmente e acumular a receita de vendas todos os meses do ano.</span><span class="sxs-lookup"><span data-stu-id="d0e4e-108">If a subscription group exists, you must set it up to invoice the customer yearly and to accrue sales revenue every month of the year.</span></span> <span data-ttu-id="d0e4e-109">Para obter mais informações sobre como configurar as subscrições, consulte [Configurar grupos de subscrições](set-up-subscription-groups.md).</span><span class="sxs-lookup"><span data-stu-id="d0e4e-109">For more information about how to set up subscriptions, see [Set up subscription groups](set-up-subscription-groups.md).</span></span>

<span data-ttu-id="d0e4e-110">Uma vez criado o grupo de subscrições, você poderá criar a subscrição.</span><span class="sxs-lookup"><span data-stu-id="d0e4e-110">After the subscription group is created, you can create the subscription.</span></span> <span data-ttu-id="d0e4e-111">Para obter mais informações sobre como criar subscrições de serviço, consulte [Criar subscrições de serviço de um grupo de subscrições](create-service-subscriptions-from-subscription-group.md).</span><span class="sxs-lookup"><span data-stu-id="d0e4e-111">For more information about how to create service subscriptions, see [Create service subscriptions from a subscription group](create-service-subscriptions-from-subscription-group.md).</span></span>

## <a name="create-and-modify-subscription-transactions"></a><span data-ttu-id="d0e4e-112">Criar e modificar transações de subscrição</span><span class="sxs-lookup"><span data-stu-id="d0e4e-112">Create and modify subscription transactions</span></span>

<span data-ttu-id="d0e4e-113">Depois de configurar a subscrição, crie a transação de taxa de subscrição para o primeiro período de faturamento, que é um ano.</span><span class="sxs-lookup"><span data-stu-id="d0e4e-113">After you set up the subscription, you create the subscription fee transaction for the first invoicing period, which is one year.</span></span> <span data-ttu-id="d0e4e-114">As transações são do tipo **Normal**.</span><span class="sxs-lookup"><span data-stu-id="d0e4e-114">The transactions are of the **Regular** type.</span></span> <span data-ttu-id="d0e4e-115">Portanto, você só pode criar transações de subscrição onde as datas inicial e final correspondam aos períodos criados anteriormente no formulário **Tipos de período**.</span><span class="sxs-lookup"><span data-stu-id="d0e4e-115">Therefore, you can only create subscription transactions where the from date and the to date correspond to periods that were previously created in the **Period types** form.</span></span> <span data-ttu-id="d0e4e-116">Para obter mais informações sobre transações de taxa, consulte [Criar transações de taxa de subscrição](create-subscription-fee-transactions.md).</span><span class="sxs-lookup"><span data-stu-id="d0e4e-116">For more information about fee transactions, see [Create subscription fee transactions](create-subscription-fee-transactions.md).</span></span>

<span data-ttu-id="d0e4e-117">Depois de configurar a subscrição para o cliente, você se lembra de que eles negociaram um desconto de 10% sobre todas os preços de lista das ofertas de serviço.</span><span class="sxs-lookup"><span data-stu-id="d0e4e-117">After you set up the subscription for your customer, you remember that they have negotiated a 10 percent discount on all list prices for service offerings.</span></span> <span data-ttu-id="d0e4e-118">Portanto, é preciso reduzir o preço da taxa da transação criada.</span><span class="sxs-lookup"><span data-stu-id="d0e4e-118">Therefore, you must reduce the price of the transaction fee that you created.</span></span>

<span data-ttu-id="d0e4e-119">Mais tarde, o contato do seu contato cliente lhe telefona para dizer que, embora desejem manter o contrato de serviço para o equipamento de luz, eles planejam introduzir um novo equipamento de luz ainda este ano.</span><span class="sxs-lookup"><span data-stu-id="d0e4e-119">Later in the day, your customer contact calls to say that, although they still want the service agreement for the lighting rig, they plan to introduce a new lighting rig later in the year.</span></span> <span data-ttu-id="d0e4e-120">Portanto, eles precisam da cobertura de manutenção somente até outubro de 2013.</span><span class="sxs-lookup"><span data-stu-id="d0e4e-120">Therefore, they only need maintenance coverage until October 2013.</span></span> <span data-ttu-id="d0e4e-121">Para reduzir o número de meses da subscrição do cliente, você cria uma nova transação de taxa de subscrição do tipo **Dias de redução**.</span><span class="sxs-lookup"><span data-stu-id="d0e4e-121">To reduce the number of months for the customer’s subscription, you create a new subscription fee transaction of the **Reduction days** type.</span></span> <span data-ttu-id="d0e4e-122">Para obter mais informações sobre como reduzir dias, consulte [Reduzir os dias para taxas de subscrição](reduce-the-days-on-subscription-fees.md).</span><span class="sxs-lookup"><span data-stu-id="d0e4e-122">For more information about how to reduce days, see [Reduce the days on subscription fees](reduce-the-days-on-subscription-fees.md).</span></span>

## <a name="invoice-and-accrue-subscription-transactions"></a><span data-ttu-id="d0e4e-123">Faturar e acumular transações de subscrição</span><span class="sxs-lookup"><span data-stu-id="d0e4e-123">Invoice and accrue subscription transactions</span></span>

<span data-ttu-id="d0e4e-124">Agora você concluiu a configuração da subscrição e está pronto para faturar o cliente pela subscrição.</span><span class="sxs-lookup"><span data-stu-id="d0e4e-124">You have now finished setting up the subscription, and you are ready to invoice your customer for it.</span></span> <span data-ttu-id="d0e4e-125">Para obter mais informações sobre como faturar as subscrições, consulte [Faturar transações de subscrições](invoice-subscription-transactions.md).</span><span class="sxs-lookup"><span data-stu-id="d0e4e-125">For more information about how to invoice subscriptions, see [Invoice subscription transactions](invoice-subscription-transactions.md).</span></span>

<span data-ttu-id="d0e4e-126">Dois dias depois, o cliente liga para dizer que a subscrição deve ser faturada em dólares norte-americanos, não em euros.</span><span class="sxs-lookup"><span data-stu-id="d0e4e-126">Two days later, your customer calls to say that the subscription should be invoiced in U.S. dollars, not Euros.</span></span> <span data-ttu-id="d0e4e-127">Portanto, você cria uma nota de crédito e também uma nova transação de subscrição na moeda correta.</span><span class="sxs-lookup"><span data-stu-id="d0e4e-127">Therefore, you create a credit note, and you also create a new subscription transaction in the correct currency.</span></span> <span data-ttu-id="d0e4e-128">Para obter mais informações sobre como creditar transações de subscrição de crédito, consulte [Creditar transações de subscrição](credit-subscription-transactions.md).</span><span class="sxs-lookup"><span data-stu-id="d0e4e-128">For more information about how to credit subscription transactions, see [Credit subscription transactions](credit-subscription-transactions.md).</span></span>

<span data-ttu-id="d0e4e-129">No final de cada mês, a receita mensal pode ser acumulada pela subscrição do cliente na conta de lucros e perdas e nas contas WIP.</span><span class="sxs-lookup"><span data-stu-id="d0e4e-129">At the end of each month, one month's revenue can be accrued from the customer's subscription to the profit and loss account and the WIP accounts.</span></span> <span data-ttu-id="d0e4e-130">Para obter mais informações sobre como acumular receita para subscrições, consulte [Acumular receita de subscrição](accrue-subscription-revenue.md).</span><span class="sxs-lookup"><span data-stu-id="d0e4e-130">For more information about how to accrue revenue for subscriptions, see [Accrue subscription revenue](accrue-subscription-revenue.md).</span></span>

  


