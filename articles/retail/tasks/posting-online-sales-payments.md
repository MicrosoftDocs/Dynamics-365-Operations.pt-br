---
title: Lançamento de vendas e pagamentos online
description: Este procedimento orienta como configurar e executar um trabalho em lotes periódico para criar ordens de venda e pagamentos para transações de lojas online.
author: psimolin
manager: AnnBe
ms.date: 08/06/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailChannelOperationsWorkspace, RetailOperatingUnitPicker, SysRecurrence
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1d42b585a61214628980cd45a859215443ed55b5
ms.sourcegitcommit: c461758290d7ddc19f0b60701368937c35ef78b0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/06/2019
ms.locfileid: "1864144"
---
# <a name="posting-of-online-sales-and-payments"></a><span data-ttu-id="a2ab5-103">Lançamento de vendas e pagamentos online</span><span class="sxs-lookup"><span data-stu-id="a2ab5-103">Posting of online sales and payments</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="a2ab5-104">Este procedimento orienta como configurar e executar um trabalho em lotes periódico para criar ordens de venda e pagamentos para transações de lojas online.</span><span class="sxs-lookup"><span data-stu-id="a2ab5-104">This procedure walks through configuring and running a recurrent batch job to create sales orders and payments for online store transactions.</span></span>

<span data-ttu-id="a2ab5-105">Lançar pagamentos e vendas on-line é um processo de dois estágios.</span><span class="sxs-lookup"><span data-stu-id="a2ab5-105">Posting online sales and payments is a two-stage process.</span></span>

- <span data-ttu-id="a2ab5-106">Recebendo os dados de transação online de varejo na matriz.</span><span class="sxs-lookup"><span data-stu-id="a2ab5-106">Pulling the online retail transaction data in HQ.</span></span>
- <span data-ttu-id="a2ab5-107">Sincronizando ordens criar ordens de venda na matriz.</span><span class="sxs-lookup"><span data-stu-id="a2ab5-107">Synchronizing orders to create sales orders in HQ.</span></span>

<span data-ttu-id="a2ab5-108">Receber os dados de transação online de varejo pode ser feito manualmente executando o trabalho P ou criando um trabalho em lotes recorrente.</span><span class="sxs-lookup"><span data-stu-id="a2ab5-108">Pulling the online retail transaction data can be done either by manually running the P-job or by creating a recurrent batch job.</span></span>

### <a name="manually-running-the-p-job"></a><span data-ttu-id="a2ab5-109">Executando o trabalho P manualmente</span><span class="sxs-lookup"><span data-stu-id="a2ab5-109">Manually running the P-job</span></span>

1. <span data-ttu-id="a2ab5-110">Vá para Todos os espaços de trabalho > TI de Varejo.</span><span class="sxs-lookup"><span data-stu-id="a2ab5-110">Go to All workspaces > Retail IT.</span></span>
2. <span data-ttu-id="a2ab5-111">Clique em Agenda de distribuição.</span><span class="sxs-lookup"><span data-stu-id="a2ab5-111">Click Distribution schedule.</span></span>
3. <span data-ttu-id="a2ab5-112">Selecione P-0001.</span><span class="sxs-lookup"><span data-stu-id="a2ab5-112">Select P-0001.</span></span>
4. <span data-ttu-id="a2ab5-113">Ajuste os grupos do banco de dados do canal, se necessário.</span><span class="sxs-lookup"><span data-stu-id="a2ab5-113">Adjust channel database groups, if required.</span></span>
5. <span data-ttu-id="a2ab5-114">Clique em Executar agora.</span><span class="sxs-lookup"><span data-stu-id="a2ab5-114">Click Run now.</span></span>
6. <span data-ttu-id="a2ab5-115">Clique em Sim.</span><span class="sxs-lookup"><span data-stu-id="a2ab5-115">Click Yes.</span></span>

### <a name="scheduling-a-recurring-p-job"></a><span data-ttu-id="a2ab5-116">Agendando um trabalho P recorrente</span><span class="sxs-lookup"><span data-stu-id="a2ab5-116">Scheduling a recurring P-job</span></span>

1. <span data-ttu-id="a2ab5-117">Vá para Todos os espaços de trabalho > TI de Varejo.</span><span class="sxs-lookup"><span data-stu-id="a2ab5-117">Go to All workspaces > Retail IT.</span></span>
2. <span data-ttu-id="a2ab5-118">Clique em Agenda de distribuição.</span><span class="sxs-lookup"><span data-stu-id="a2ab5-118">Click Distribution schedule.</span></span>
3. <span data-ttu-id="a2ab5-119">Selecione P-0001.</span><span class="sxs-lookup"><span data-stu-id="a2ab5-119">Select P-0001.</span></span>
4. <span data-ttu-id="a2ab5-120">Clique em Criar trabalho em lotes.</span><span class="sxs-lookup"><span data-stu-id="a2ab5-120">Click Create batch job.</span></span>
5. <span data-ttu-id="a2ab5-121">Clique em Executar em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="a2ab5-121">Click Run in the background.</span></span>
5. <span data-ttu-id="a2ab5-122">Habilitar Processamento em lotes.</span><span class="sxs-lookup"><span data-stu-id="a2ab5-122">Enable Batch processing.</span></span>
6. <span data-ttu-id="a2ab5-123">Clique em Recorrência.</span><span class="sxs-lookup"><span data-stu-id="a2ab5-123">Click Recurrence..</span></span>
7. <span data-ttu-id="a2ab5-124">Selecione a opção Nenhuma data de término.</span><span class="sxs-lookup"><span data-stu-id="a2ab5-124">Select the No end date option.</span></span>
8. <span data-ttu-id="a2ab5-125">No campo Contagem, insira o intervalo entre as execuções em minutos.</span><span class="sxs-lookup"><span data-stu-id="a2ab5-125">In the Count field, enter interval between the runs in minutes.</span></span> <span data-ttu-id="a2ab5-126">Normalmente isso seria 5-10.</span><span class="sxs-lookup"><span data-stu-id="a2ab5-126">Typically this would be 5-10.</span></span>
9. <span data-ttu-id="a2ab5-127">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="a2ab5-127">Click OK.</span></span>
10. <span data-ttu-id="a2ab5-128">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="a2ab5-128">Click OK.</span></span>

<span data-ttu-id="a2ab5-129">As ordens podem ser sincronizadas manualmente, executando o trabalho "Sincronizar ordens" ou criando um trabalho em lotes recorrente.</span><span class="sxs-lookup"><span data-stu-id="a2ab5-129">Orders can be synchronized either by manually running the "Synchronize orders"-job or by creating a recurring batch job.</span></span>

### <a name="manually-running-order-synchronization"></a><span data-ttu-id="a2ab5-130">Executando a sincronização da ordem manualmente</span><span class="sxs-lookup"><span data-stu-id="a2ab5-130">Manually running order synchronization</span></span> 

<span data-ttu-id="a2ab5-131">Siga estas etapas para executar manualmente o trabalho "Sincronizar ordens" uma vez.</span><span class="sxs-lookup"><span data-stu-id="a2ab5-131">Follow these steps to manually run "Synchronize orders" job once.</span></span>

1. <span data-ttu-id="a2ab5-132">Vá para Todos os espaços de trabalho > Finanças da loja de varejo.</span><span class="sxs-lookup"><span data-stu-id="a2ab5-132">Go to All workspaces > Retail store financials.</span></span>
2. <span data-ttu-id="a2ab5-133">Clique em Sincronizar ordens.</span><span class="sxs-lookup"><span data-stu-id="a2ab5-133">Click Synchronize orders.</span></span>
3. <span data-ttu-id="a2ab5-134">No campo Hierarquia da organização, selecione 'Lojas de varejo por região'.</span><span class="sxs-lookup"><span data-stu-id="a2ab5-134">In the Organization hierarchy field, select 'Retail Stores by Region'.</span></span>
    * <span data-ttu-id="a2ab5-135">Selecione uma loja online específica ou selecione um nó se você deseja criar o trabalho em lotes para um grupo de lojas.</span><span class="sxs-lookup"><span data-stu-id="a2ab5-135">Select either a specific online store, or select a node if you want to create the batch job for a group of stores.</span></span>  
    * <span data-ttu-id="a2ab5-136">Clique na seta para adicionar sua seleção.</span><span class="sxs-lookup"><span data-stu-id="a2ab5-136">Click the arrow to add your selection.</span></span>  
4. <span data-ttu-id="a2ab5-137">Clique na guia Executar em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="a2ab5-137">Click the Run in the background tab.</span></span>
5. <span data-ttu-id="a2ab5-138">Desativar processamento em lotes</span><span class="sxs-lookup"><span data-stu-id="a2ab5-138">Disable Batch processing</span></span>
6. <span data-ttu-id="a2ab5-139">Clique em Recorrência.</span><span class="sxs-lookup"><span data-stu-id="a2ab5-139">Click Recurrence.</span></span>
7. <span data-ttu-id="a2ab5-140">Selecione a opção Terminar Após</span><span class="sxs-lookup"><span data-stu-id="a2ab5-140">Select End After option</span></span>
8. <span data-ttu-id="a2ab5-141">No campo Terminar Após, insira 1.</span><span class="sxs-lookup"><span data-stu-id="a2ab5-141">In the End After field, enter 1.</span></span>
9. <span data-ttu-id="a2ab5-142">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="a2ab5-142">Click OK.</span></span>
10. <span data-ttu-id="a2ab5-143">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="a2ab5-143">Click OK.</span></span>

### <a name="scheduling-recurring-order-synchronization"></a><span data-ttu-id="a2ab5-144">Agendando sincronização da ordem recorrente</span><span class="sxs-lookup"><span data-stu-id="a2ab5-144">Scheduling recurring order synchronization</span></span>

<span data-ttu-id="a2ab5-145">Este procedimento orienta como configurar e executar um trabalho em lotes periódico para criar ordens de venda e pagamentos para transações de lojas online.</span><span class="sxs-lookup"><span data-stu-id="a2ab5-145">This procedure walks through configuring and running a recurrent batch job to create sales orders and payments for online store transactions.</span></span> <span data-ttu-id="a2ab5-146">Este procedimento usa a empresa USRT nos dados de demonstração.</span><span class="sxs-lookup"><span data-stu-id="a2ab5-146">This procedure uses the USRT company in demo data.</span></span>

1. <span data-ttu-id="a2ab5-147">Vá para Todos os espaços de trabalho > Finanças da loja de varejo.</span><span class="sxs-lookup"><span data-stu-id="a2ab5-147">Go to All workspaces > Retail store financials.</span></span>
2. <span data-ttu-id="a2ab5-148">Clique em Sincronizar ordens.</span><span class="sxs-lookup"><span data-stu-id="a2ab5-148">Click Synchronize orders.</span></span>
3. <span data-ttu-id="a2ab5-149">No campo Hierarquia da organização, selecione 'Lojas de varejo por região'.</span><span class="sxs-lookup"><span data-stu-id="a2ab5-149">In the Organization hierarchy field, select 'Retail Stores by Region'.</span></span>
    * <span data-ttu-id="a2ab5-150">Selecione uma loja online específica ou selecione um nó se você deseja criar o trabalho em lotes para um grupo de lojas.</span><span class="sxs-lookup"><span data-stu-id="a2ab5-150">Select either a specific online store, or select a node if you want to create the batch job for a group of stores.</span></span>  
    * <span data-ttu-id="a2ab5-151">Clique na seta para adicionar sua seleção.</span><span class="sxs-lookup"><span data-stu-id="a2ab5-151">Click the arrow to add your selection.</span></span>  
4. <span data-ttu-id="a2ab5-152">Clique na guia Executar em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="a2ab5-152">Click the Run in the background tab.</span></span>
5. <span data-ttu-id="a2ab5-153">Habilitar processamento em lotes</span><span class="sxs-lookup"><span data-stu-id="a2ab5-153">Enable Batch processing</span></span>
6. <span data-ttu-id="a2ab5-154">Clique em Recorrência.</span><span class="sxs-lookup"><span data-stu-id="a2ab5-154">Click Recurrence.</span></span>
7. <span data-ttu-id="a2ab5-155">Selecione a opção Nenhuma data de término.</span><span class="sxs-lookup"><span data-stu-id="a2ab5-155">Select the No end date option.</span></span>
8. <span data-ttu-id="a2ab5-156">No campo Contagem, insira o intervalo entre as execuções em minutos.</span><span class="sxs-lookup"><span data-stu-id="a2ab5-156">In the Count field, enter interval between the runs in minutes.</span></span> <span data-ttu-id="a2ab5-157">Normalmente isso seria 2-20</span><span class="sxs-lookup"><span data-stu-id="a2ab5-157">Typically this would be 2-20</span></span>
9. <span data-ttu-id="a2ab5-158">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="a2ab5-158">Click OK.</span></span>
10. <span data-ttu-id="a2ab5-159">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="a2ab5-159">Click OK.</span></span>

## <a name="data-entities-involved-in-the-process"></a><span data-ttu-id="a2ab5-160">Entidades de dados envolvidas no processo</span><span class="sxs-lookup"><span data-stu-id="a2ab5-160">Data entities involved in the process</span></span>

- <span data-ttu-id="a2ab5-161">RetailTransactionTable</span><span class="sxs-lookup"><span data-stu-id="a2ab5-161">RetailTransactionTable</span></span>
- <span data-ttu-id="a2ab5-162">RetailTransactionAddressTrans</span><span class="sxs-lookup"><span data-stu-id="a2ab5-162">RetailTransactionAddressTrans</span></span>
- <span data-ttu-id="a2ab5-163">RetailTransactionInfocodeTrans</span><span class="sxs-lookup"><span data-stu-id="a2ab5-163">RetailTransactionInfocodeTrans</span></span>
- <span data-ttu-id="a2ab5-164">RetailTransactionTaxTrans</span><span class="sxs-lookup"><span data-stu-id="a2ab5-164">RetailTransactionTaxTrans</span></span>
- <span data-ttu-id="a2ab5-165">RetailTransactionSalesTrans</span><span class="sxs-lookup"><span data-stu-id="a2ab5-165">RetailTransactionSalesTrans</span></span>
- <span data-ttu-id="a2ab5-166">RetailTransactionTaxMeasure</span><span class="sxs-lookup"><span data-stu-id="a2ab5-166">RetailTransactionTaxMeasure</span></span>
- <span data-ttu-id="a2ab5-167">RetailTransactionDiscountTrans</span><span class="sxs-lookup"><span data-stu-id="a2ab5-167">RetailTransactionDiscountTrans</span></span>
- <span data-ttu-id="a2ab5-168">RetailTransactionTaxTransGTE</span><span class="sxs-lookup"><span data-stu-id="a2ab5-168">RetailTransactionTaxTransGTE</span></span>
- <span data-ttu-id="a2ab5-169">RetailTransactionMarkupTrans</span><span class="sxs-lookup"><span data-stu-id="a2ab5-169">RetailTransactionMarkupTrans</span></span>
- <span data-ttu-id="a2ab5-170">RetailTransactionPaymentTrans</span><span class="sxs-lookup"><span data-stu-id="a2ab5-170">RetailTransactionPaymentTrans</span></span>
- <span data-ttu-id="a2ab5-171">RetailTransactionAttributeTrans</span><span class="sxs-lookup"><span data-stu-id="a2ab5-171">RetailTransactionAttributeTrans</span></span>
