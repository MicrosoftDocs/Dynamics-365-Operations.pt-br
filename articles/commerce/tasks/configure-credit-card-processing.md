---
title: Configurar processamento do cartão de crédito
description: Este procedimento orienta como exibir a lista de provedores de serviço de pagamento e como configurar uma conta de pagamento para contas a receber.
author: jashanno
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2cfec44bc1c767dff1109c4ecd4e2862443fb1d0
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3141490"
---
# <a name="configure-credit-card-processing"></a><span data-ttu-id="a1c34-103">Configurar processamento do cartão de crédito</span><span class="sxs-lookup"><span data-stu-id="a1c34-103">Configure credit card processing</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a1c34-104">Este procedimento orienta como exibir a lista de provedores de serviço de pagamento e como configurar uma conta de pagamento para contas a receber.</span><span class="sxs-lookup"><span data-stu-id="a1c34-104">This procedure walks through how to view the list of payment providers and how to configure a payment account for accounts receivable.</span></span> <span data-ttu-id="a1c34-105">Este procedimento usa a empresa USRT nos dados de demonstração e destina-se aos administradores e profissionais de TI.</span><span class="sxs-lookup"><span data-stu-id="a1c34-105">This procedure uses the USRT company in demo data and is intended for Administrators and IT Professionals.</span></span>


## <a name="view-a-list-of-payment-providers"></a><span data-ttu-id="a1c34-106">Exibir uma lista de provedores de serviço de pagamento</span><span class="sxs-lookup"><span data-stu-id="a1c34-106">View a list of payment providers</span></span>
1. <span data-ttu-id="a1c34-107">Vá para Contas a receber > Configurar pagamentos > Serviços de pagamento.</span><span class="sxs-lookup"><span data-stu-id="a1c34-107">Go to Accounts receivable > Payments setup > Payment services.</span></span>
2. <span data-ttu-id="a1c34-108">Clique em Exibir provedores disponíveis.</span><span class="sxs-lookup"><span data-stu-id="a1c34-108">Click View available providers.</span></span>

## <a name="configure-payment-account"></a><span data-ttu-id="a1c34-109">Configurar conta de pagamento</span><span class="sxs-lookup"><span data-stu-id="a1c34-109">Configure payment account</span></span>
1. <span data-ttu-id="a1c34-110">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="a1c34-110">Click New.</span></span>
2. <span data-ttu-id="a1c34-111">No campo Serviço de pagamento, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="a1c34-111">In the Payment service field, type a value.</span></span>
3. <span data-ttu-id="a1c34-112">No campo Conector de pagamento, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="a1c34-112">In the Payment connector field, select an option.</span></span>
4. <span data-ttu-id="a1c34-113">Ative/desative a expansão da seção Conta de serviço de pagamento.</span><span class="sxs-lookup"><span data-stu-id="a1c34-113">Toggle the expansion of the Payment service account section.</span></span>
5. <span data-ttu-id="a1c34-114">No campo Ambiente, digite 'PROD'.</span><span class="sxs-lookup"><span data-stu-id="a1c34-114">In the Environment: field, type 'PROD'.</span></span>
6. <span data-ttu-id="a1c34-115">Clique em Tipos de cartão de crédito.</span><span class="sxs-lookup"><span data-stu-id="a1c34-115">Click Credit card types.</span></span>
7. <span data-ttu-id="a1c34-116">No campo Diário de pagamentos, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="a1c34-116">In the Payment journal field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="a1c34-117">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="a1c34-117">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="a1c34-118">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="a1c34-118">Click Add.</span></span>
10. <span data-ttu-id="a1c34-119">No campo Moeda, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="a1c34-119">In the Currency field, type a value.</span></span>
11. <span data-ttu-id="a1c34-120">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="a1c34-120">In the list, find and select the desired record.</span></span>
12. <span data-ttu-id="a1c34-121">No campo Diário de pagamentos, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="a1c34-121">In the Payment journal field, click the drop-down button to open the lookup.</span></span>
13. <span data-ttu-id="a1c34-122">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="a1c34-122">In the list, click the link in the selected row.</span></span>
14. <span data-ttu-id="a1c34-123">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="a1c34-123">Click Add.</span></span>
15. <span data-ttu-id="a1c34-124">No campo Moeda, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="a1c34-124">In the Currency field, type a value.</span></span>
16. <span data-ttu-id="a1c34-125">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="a1c34-125">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="a1c34-126">Você pode repetir essas etapas para quantos tipos de cartão for necessário.</span><span class="sxs-lookup"><span data-stu-id="a1c34-126">You can repeat these steps for as many card types as you need.</span></span>  
17. <span data-ttu-id="a1c34-127">No campo Diário de pagamentos, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="a1c34-127">In the Payment journal field, click the drop-down button to open the lookup.</span></span>
18. <span data-ttu-id="a1c34-128">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="a1c34-128">In the list, click the link in the selected row.</span></span>
19. <span data-ttu-id="a1c34-129">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="a1c34-129">Click Add.</span></span>
20. <span data-ttu-id="a1c34-130">No campo Moeda, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="a1c34-130">In the Currency field, type a value.</span></span>
21. <span data-ttu-id="a1c34-131">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="a1c34-131">Click Save.</span></span>
22. <span data-ttu-id="a1c34-132">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="a1c34-132">Close the page.</span></span>
23. <span data-ttu-id="a1c34-133">Clique em Validar.</span><span class="sxs-lookup"><span data-stu-id="a1c34-133">Click Validate.</span></span>
24. <span data-ttu-id="a1c34-134">Clique na caixa de seleção Processador padrão para novos cartões de crédito.</span><span class="sxs-lookup"><span data-stu-id="a1c34-134">Click the Default processor for new credit cards checkbox.</span></span>
25. <span data-ttu-id="a1c34-135">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="a1c34-135">Click Save.</span></span>
