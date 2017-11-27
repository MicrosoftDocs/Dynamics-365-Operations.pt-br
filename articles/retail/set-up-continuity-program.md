---
title: Configurar um programa da continuidade para um call center
description: Este artigo descreve como configurar um programa de continuidade para um call center.
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 16081
ms.assetid: 426a9be7-a931-4780-b372-e06f6083dd60
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 0fa2c5aaf6953eed75729017cca8cf3c2220e80d
ms.contentlocale: pt-br
ms.lasthandoff: 11/03/2017

---

# <a name="set-up-a-continuity-program-for-a-call-center"></a><span data-ttu-id="eb8e6-103">Configurar um programa da continuidade para um call center</span><span class="sxs-lookup"><span data-stu-id="eb8e6-103">Set up a continuity program for a call center</span></span>

[!include[banner](includes/banner.md)]


<span data-ttu-id="eb8e6-104">Este artigo descreve como configurar um programa de continuidade para um call center.</span><span class="sxs-lookup"><span data-stu-id="eb8e6-104">This article describes how to set up a continuity program for a call center.</span></span>

<span data-ttu-id="eb8e6-105">Em um programa de continuidade, que também é conhecido como um programa de ordem recorrente, os clientes recebem remessas regulares de produtos de acordo com uma agenda predefinida.</span><span class="sxs-lookup"><span data-stu-id="eb8e6-105">In a continuity program, which is also known as a recurring order program, customers receive regular product shipments according to a predefined schedule.</span></span> <span data-ttu-id="eb8e6-106">Cada remessa pode conter um produto diferente, como no caso de um clube de livro do mês, ou o mesmo produto pode ser enviado repetidamente.</span><span class="sxs-lookup"><span data-stu-id="eb8e6-106">Each shipment can contain a different product, as in the case of a book-of-the-month club, or the same product can be sent repeatedly.</span></span> <span data-ttu-id="eb8e6-107">Para configurar um programa de continuidade, deve concluir as seguintes tarefas.</span><span class="sxs-lookup"><span data-stu-id="eb8e6-107">To set up a continuity program, you must complete the following tasks.</span></span>

1.  <span data-ttu-id="eb8e6-108">Defina os parâmetros de continuidade na página **Parâmetros do call center**.</span><span class="sxs-lookup"><span data-stu-id="eb8e6-108">Set the continuity parameters on the **Call center parameters** page.</span></span>
2.  <span data-ttu-id="eb8e6-109">Crie um programa de continuidade que especifica detalhes como o plano de pagamento, a hora das remessas e se o faturamento será adiantado.</span><span class="sxs-lookup"><span data-stu-id="eb8e6-109">Create a continuity program that specifies details such as the payment schedule, the timing of the shipments, and whether billing is up front.</span></span> <span data-ttu-id="eb8e6-110">Você também deve adicionar uma lista de produtos que estejam incluídos no programa de continuidade.</span><span class="sxs-lookup"><span data-stu-id="eb8e6-110">You must also add a list of products that are included in the continuity program.</span></span> <span data-ttu-id="eb8e6-111">Cada produto recebe um número de identificação de evento que é atribuído sequencialmente, começando com 1.</span><span class="sxs-lookup"><span data-stu-id="eb8e6-111">Each product receives an event ID number that is assigned sequentially, beginning with 1.</span></span> <span data-ttu-id="eb8e6-112">As identificações de evento determinam a ordem em que os produtos são enviados.</span><span class="sxs-lookup"><span data-stu-id="eb8e6-112">The event IDs determine the order that products are sent in.</span></span>
    -   <span data-ttu-id="eb8e6-113">Se os clientes receberem um produto diferente em cada remessa, os produtos são enviados na ordem sequencial, com base nas IDs de evento, e começando com o evento atual.</span><span class="sxs-lookup"><span data-stu-id="eb8e6-113">If customers receive a different product in each shipment, the products are sent in sequential order, based on their event IDs and beginning with the current event.</span></span>
    -   <span data-ttu-id="eb8e6-114">Se clientes receberem o mesmo produto em cada remessa, a lista conterá apenas um produto com uma ID do evento.</span><span class="sxs-lookup"><span data-stu-id="eb8e6-114">If customers receive the same product in each shipment, the list contains only one product that has one event ID.</span></span> <span data-ttu-id="eb8e6-115">O mesmo evento ocorre repetidamente.</span><span class="sxs-lookup"><span data-stu-id="eb8e6-115">The same event occurs repeatedly.</span></span> <span data-ttu-id="eb8e6-116">Você pode especificar quantas vezes cada evento será repetido.</span><span class="sxs-lookup"><span data-stu-id="eb8e6-116">You can specify how many times each event is repeated.</span></span>

3.  <span data-ttu-id="eb8e6-117">Crie um produto pai que representa o programa de continuidade que você criou na tarefa 2.</span><span class="sxs-lookup"><span data-stu-id="eb8e6-117">Create a parent product that represents the continuity program that you created in task 2.</span></span> <span data-ttu-id="eb8e6-118">Se você adicionar este produto a uma ordem de venda, a página **Continuidade** abrirá.</span><span class="sxs-lookup"><span data-stu-id="eb8e6-118">If you add this product to a sales order, the **Continuity** page opens.</span></span> <span data-ttu-id="eb8e6-119">Em seguida, você poderá usar essa página para criar a ordem de continuidade.</span><span class="sxs-lookup"><span data-stu-id="eb8e6-119">You can then use that page to create the actual continuity order.</span></span> <span data-ttu-id="eb8e6-120">O produto pai não especifica os produtos individuais que o cliente recebe em cada remessa.</span><span class="sxs-lookup"><span data-stu-id="eb8e6-120">The parent product doesn't specify the individual products that the customer receives in each shipment.</span></span>

<span data-ttu-id="eb8e6-121">Depois de configurar um programa de continuidade conforme descrito acima, você poderá criar uma ordem de continuidade para um cliente.</span><span class="sxs-lookup"><span data-stu-id="eb8e6-121">After you've set up a continuity program as described above, you can create a continuity order for a customer.</span></span> <span data-ttu-id="eb8e6-122">Talvez também seja necessário realizar as tarefas de manutenção adicionais.</span><span class="sxs-lookup"><span data-stu-id="eb8e6-122">You might also have to perform the following additional maintenance tasks.</span></span>

-   <span data-ttu-id="eb8e6-123">**Atualizar o período de evento atual de continuidade** – Configure um trabalho em lotes que avisa o sistema qual é o período do evento atual.</span><span class="sxs-lookup"><span data-stu-id="eb8e6-123">**Update the current continuity event period** – Set up a batch job that tells the system what the current event period is.</span></span>
-   <span data-ttu-id="eb8e6-124">**Criar ordens filhas de continuidade** – Crie ordens filhas a partir da ordem de continuidade pai.</span><span class="sxs-lookup"><span data-stu-id="eb8e6-124">**Create continuity child orders** – Create child orders from the parent continuity order.</span></span>
-   <span data-ttu-id="eb8e6-125">**Processar pagamentos de continuidade** – Processar cobrança e notificações para pagamentos associados a ordens de venda de continuidade.</span><span class="sxs-lookup"><span data-stu-id="eb8e6-125">**Process continuity payments** – Process billing and notifications for payments that are associated with continuity sales orders.</span></span>
-   <span data-ttu-id="eb8e6-126">**Estender linhas da continuidade** (se necessário) – Estenda o número de vezes em que um evento de continuidade possa ser repetido.</span><span class="sxs-lookup"><span data-stu-id="eb8e6-126">**Extend continuity lines** (if required) – Extend the number of times that a continuity event can be repeated.</span></span> <span data-ttu-id="eb8e6-127">A repetição de remessas poderá se estender além de limite foi definido no campo **Limite da repetição de continuidade** nos parâmetros de call center.</span><span class="sxs-lookup"><span data-stu-id="eb8e6-127">The repetition of shipments can then extend beyond the limit that was set in the **Continuity repeat threshold** field in the call center parameters.</span></span>
-   <span data-ttu-id="eb8e6-128">**Executar uma atualização de continuidade** (se necessário) – Sincronize alterações entre o programa de continuidade e as ordens de venda pai de continuidade.</span><span class="sxs-lookup"><span data-stu-id="eb8e6-128">**Perform a continuity update** (if required) – Synchronize changes between the continuity program and the continuity parent sales orders.</span></span>
-   <span data-ttu-id="eb8e6-129">**Fechar linhas e ordens pai de continuidade** – Fecha as ordens de continuidade.</span><span class="sxs-lookup"><span data-stu-id="eb8e6-129">**Close continuity parent lines and orders** – Close continuity orders.</span></span>





