---
title: Visão geral de crédito e cobranças
description: Este tópico apresenta uma visão geral da funcionalidade de crédito e cobranças.
author: mikefalkner
manager: AnnBe
ms.date: 09/04/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschloma
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mfalkner
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 2fdfe05483d577819d64bdf7a4ebfe5d37cd414c
ms.sourcegitcommit: 6a70f9ac296158edd065d52a12703b3ce85ce5ee
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "3015107"
---
# <a name="credit-and-collections-overview"></a><span data-ttu-id="f2cfa-103">Visão geral de crédito e cobranças</span><span class="sxs-lookup"><span data-stu-id="f2cfa-103">Credit and collections overview</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="f2cfa-104">Você pode gerenciar os limites de crédito de seus clientes e realizar atividades de cobrança quando forem necessárias.</span><span class="sxs-lookup"><span data-stu-id="f2cfa-104">You can manage credit limits for your customers and perform collection activities when they become necessary.</span></span>

## <a name="credit-management"></a><span data-ttu-id="f2cfa-105">Gerenciamento de crédito</span><span class="sxs-lookup"><span data-stu-id="f2cfa-105">Credit management</span></span>

<span data-ttu-id="f2cfa-106">O gerenciamento de crédito de cliente permite gerenciar limites de crédito e controlar o fluxo de ordens de venda por meio do processo de lançamento, com base nas regras de crédito criadas.</span><span class="sxs-lookup"><span data-stu-id="f2cfa-106">Customer credit management lets you manage credit limits and control the flow of sales orders through the posting process, based on credit rules that you create.</span></span>

<span data-ttu-id="f2cfa-107">O processo de gerenciamento de crédito pode incluir qualquer uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="f2cfa-107">The credit management process can include any of the following steps:</span></span>

- <span data-ttu-id="f2cfa-108">Atualizar os atributos de crédito para que os clientes forneçam informações adicionais sobre confiabilidade de crédito.</span><span class="sxs-lookup"><span data-stu-id="f2cfa-108">Update credit attributes for customers to provide additional information about their credit worthiness.</span></span>
- <span data-ttu-id="f2cfa-109">Criar limites de crédito para os clientes usando ajustes de limite de crédito.</span><span class="sxs-lookup"><span data-stu-id="f2cfa-109">Create credit limits for customers by using credit limit adjustments.</span></span>
- <span data-ttu-id="f2cfa-110">Criar limites de crédito temporários para os clientes usando ajustes de limite de crédito.</span><span class="sxs-lookup"><span data-stu-id="f2cfa-110">Create temporary credit limits for customers by using credit limit adjustments.</span></span> <span data-ttu-id="f2cfa-111">Dessa forma, você pode aumentar ou diminuir temporariamente os limites de crédito dos clientes com base nas requisições de negócios.</span><span class="sxs-lookup"><span data-stu-id="f2cfa-111">In this way, you can temporarily increase or decrease customer credit limits, based on business requirements.</span></span>
- <span data-ttu-id="f2cfa-112">Adicionar informações que podem afetar o limite de crédito, como informações sobre seguro e garantias.</span><span class="sxs-lookup"><span data-stu-id="f2cfa-112">Add information that can affect the credit limit, such as information about insurance and guarantees.</span></span>
- <span data-ttu-id="f2cfa-113">Criar grupos de crédito de cliente que vinculem os clientes para que eles compartilhem um único limite de crédito.</span><span class="sxs-lookup"><span data-stu-id="f2cfa-113">Create customer credit groups that link customers together so that they share a single credit limit.</span></span>
- <span data-ttu-id="f2cfa-114">Atribuir pontuações de risco aos clientes e usar as pontuações para gerar automaticamente limites de crédito para esses clientes por meio de ajustes de limite de crédito.</span><span class="sxs-lookup"><span data-stu-id="f2cfa-114">Assign risk scores to customers, and then use the scores to automatically generate credit limits for those customers through credit limit adjustments.</span></span>
- <span data-ttu-id="f2cfa-115">Criar regras de bloqueio que coloquem uma ordem em espera durante um ou mais processos de lançamento com base em fatores como risco, condições de pagamento, limites de crédito, valores vencidos e a porcentagem do limite de crédito que foi usado.</span><span class="sxs-lookup"><span data-stu-id="f2cfa-115">Create blocking rules that put an order on hold during one or more posting processes, based on factors such as risk, payment terms, credit limits, overdue amounts, and the percentage of the credit limit that has been used.</span></span>
- <span data-ttu-id="f2cfa-116">Gerenciar uma lista de ordens de venda em espera, revisar os motivos do bloqueio e mitigar problemas.</span><span class="sxs-lookup"><span data-stu-id="f2cfa-116">Manage a list of sales orders that are on hold, review the reasons for the hold, and mitigate issues.</span></span>
- <span data-ttu-id="f2cfa-117">Liberar ordens de venda para dar andamento a elas no processo de lançamento.</span><span class="sxs-lookup"><span data-stu-id="f2cfa-117">Release sales orders so that they continue through the posting process.</span></span>
- <span data-ttu-id="f2cfa-118">Configurar um fluxo de trabalho para gerenciar a aprovação de alterações no limite de crédito e liberações de ordens de venda.</span><span class="sxs-lookup"><span data-stu-id="f2cfa-118">Set up a workflow to manage the approval of credit limit changes and sales order releases.</span></span>

## <a name="collections-management"></a><span data-ttu-id="f2cfa-119">Gerenciamento de cobranças</span><span class="sxs-lookup"><span data-stu-id="f2cfa-119">Collections management</span></span>

<span data-ttu-id="f2cfa-120">A página **Cobranças** mostra uma exibição centralizada onde são gerenciadas as informações sobre cobranças de contas a receber.</span><span class="sxs-lookup"><span data-stu-id="f2cfa-120">The **Collections** page provides a centralized view where accounts receivable collections information is managed.</span></span> <span data-ttu-id="f2cfa-121">Os gerentes de cobranças podem usar essa exibição centralizada para gerenciar cobranças.</span><span class="sxs-lookup"><span data-stu-id="f2cfa-121">Collections managers can use this centralized view to manage collections.</span></span> <span data-ttu-id="f2cfa-122">Os agentes de cobranças podem iniciar o processo de cobranças em listas de clientes que são geradas com o uso de critérios de cobrança predefinidos ou na página **Clientes**.</span><span class="sxs-lookup"><span data-stu-id="f2cfa-122">Collections agents can begin the collections process either from customer lists that are generated by using predefined collection criteria or from the **Customers** page.</span></span>

<span data-ttu-id="f2cfa-123">Antes de começar a configurar ou trabalhar com cobranças, você deve entender os seguintes conceitos:</span><span class="sxs-lookup"><span data-stu-id="f2cfa-123">Before you start to set up or work with collections, you should understand the following concepts:</span></span>

- <span data-ttu-id="f2cfa-124">Os instantâneos de classificação por vencimento de clientes contêm informações de saldo antigo em um determinado ponto no tempo.</span><span class="sxs-lookup"><span data-stu-id="f2cfa-124">Customer aging snapshots contain aged balance information at a specific point in time.</span></span>
- <span data-ttu-id="f2cfa-125">Os grupos de clientes de cobranças ajudam você a organizar seu trabalho.</span><span class="sxs-lookup"><span data-stu-id="f2cfa-125">Collections customer pools help you organize your work.</span></span>
- <span data-ttu-id="f2cfa-126">Os agentes de cobranças podem ter seus próprios grupos de clientes.</span><span class="sxs-lookup"><span data-stu-id="f2cfa-126">Collections agents can have their own customer pools.</span></span>
- <span data-ttu-id="f2cfa-127">As páginas de lista organizam clientes, atividades e casos de cobranças.</span><span class="sxs-lookup"><span data-stu-id="f2cfa-127">List pages organize collections customers, activities, and cases.</span></span>
- <span data-ttu-id="f2cfa-128">Todas as informações de cobranças de um cliente estão em uma página e você pode agir com base nessa página.</span><span class="sxs-lookup"><span data-stu-id="f2cfa-128">All collections information for a customer is on one page, and you can take action from that page.</span></span>
- <span data-ttu-id="f2cfa-129">Juros e taxas podem ser cancelados, restabelecidos ou revertidos em uma única etapa.</span><span class="sxs-lookup"><span data-stu-id="f2cfa-129">Interest and fees can be waived, reinstated, or reversed in one step.</span></span>
- <span data-ttu-id="f2cfa-130">Transações de baixa podem ser criadas em uma única etapa.</span><span class="sxs-lookup"><span data-stu-id="f2cfa-130">Write-off transactions can be created in one step.</span></span>
- <span data-ttu-id="f2cfa-131">Pagamentos NSF (insuficiência de fundos) podem ser processados em uma única etapa.</span><span class="sxs-lookup"><span data-stu-id="f2cfa-131">Not sufficient funds (NSF) payments can be processed in one step.</span></span>

<span data-ttu-id="f2cfa-132">Para obter descrições desses conceitos, consulte [Principais conceitos de gerenciamento de cobranças](./cm-collections-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="f2cfa-132">For descriptions of these concepts, see [Collections management key concepts](./cm-collections-concepts.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f2cfa-133">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="f2cfa-133">Additional resources</span></span>

[<span data-ttu-id="f2cfa-134">Configuração de parâmetros de gerenciamento de crédito de cliente</span><span class="sxs-lookup"><span data-stu-id="f2cfa-134">Customer credit management parameters setup</span></span>](./cm-credit-mgmt-setup.md)

[<span data-ttu-id="f2cfa-135">Informações de configuração de gerenciamento de crédito de cliente</span><span class="sxs-lookup"><span data-stu-id="f2cfa-135">Customer credit management setup information</span></span>](./cm-setup-information.md)

[<span data-ttu-id="f2cfa-136">Adicionar informações de gerenciamento de crédito de um cliente</span><span class="sxs-lookup"><span data-stu-id="f2cfa-136">Add credit management information for a customer</span></span>](./cm-add-credit-mgmt-information-customer.md)

[<span data-ttu-id="f2cfa-137">Grupos de crédito de cliente</span><span class="sxs-lookup"><span data-stu-id="f2cfa-137">Customer credit groups</span></span>](./cm-customer-credit-groups.md)

[<span data-ttu-id="f2cfa-138">Ajustes de limite de crédito de cliente</span><span class="sxs-lookup"><span data-stu-id="f2cfa-138">Customer credit limit adjustments</span></span>](./cm-credit-limit-adjustments.md)

[<span data-ttu-id="f2cfa-139">Bloqueios de crédito para ordens de venda</span><span class="sxs-lookup"><span data-stu-id="f2cfa-139">Credit holds for sales orders</span></span>](./cm-sales-order-credit-holds.md)

[<span data-ttu-id="f2cfa-140">Tarefas periódicas de gerenciamento de crédito de cliente</span><span class="sxs-lookup"><span data-stu-id="f2cfa-140">Customer credit management periodic tasks</span></span>](./cm-periodic-tasks.md)
