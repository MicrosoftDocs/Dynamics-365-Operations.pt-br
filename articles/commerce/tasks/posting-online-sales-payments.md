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
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: fbc85b957e716d07d9073d889c47f157ea0ead01
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4982282"
---
# <a name="posting-of-online-sales-and-payments"></a><span data-ttu-id="80533-103">Lançamento de vendas e pagamentos online</span><span class="sxs-lookup"><span data-stu-id="80533-103">Posting of online sales and payments</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="80533-104">Este procedimento orienta como configurar e executar um trabalho em lotes periódico para criar ordens de venda e pagamentos para transações de lojas online.</span><span class="sxs-lookup"><span data-stu-id="80533-104">This procedure walks through configuring and running a recurrent batch job to create sales orders and payments for online store transactions.</span></span>

<span data-ttu-id="80533-105">Lançar pagamentos e vendas on-line é um processo de dois estágios.</span><span class="sxs-lookup"><span data-stu-id="80533-105">Posting online sales and payments is a two-stage process.</span></span>

- <span data-ttu-id="80533-106">Recebendo os dados de transação online de comércio na matriz.</span><span class="sxs-lookup"><span data-stu-id="80533-106">Pulling the online commerce transaction data in HQ.</span></span>
- <span data-ttu-id="80533-107">Sincronizando ordens criar ordens de venda na matriz.</span><span class="sxs-lookup"><span data-stu-id="80533-107">Synchronizing orders to create sales orders in HQ.</span></span>

<span data-ttu-id="80533-108">Receber os dados de transação online pode ser feito manualmente executando o trabalho P ou criando um trabalho em lotes recorrente.</span><span class="sxs-lookup"><span data-stu-id="80533-108">Pulling the online transaction data can be done either by manually running the P-job or by creating a recurrent batch job.</span></span>

### <a name="manually-running-the-p-job"></a><span data-ttu-id="80533-109">Executando o trabalho P manualmente</span><span class="sxs-lookup"><span data-stu-id="80533-109">Manually running the P-job</span></span>

1. <span data-ttu-id="80533-110">Vá para Todos os espaços de trabalho > TI de Varejo e Comércio.</span><span class="sxs-lookup"><span data-stu-id="80533-110">Go to All workspaces > Retail and Commerce IT.</span></span>
2. <span data-ttu-id="80533-111">Clique em Agenda de distribuição.</span><span class="sxs-lookup"><span data-stu-id="80533-111">Click Distribution schedule.</span></span>
3. <span data-ttu-id="80533-112">Selecione P-0001.</span><span class="sxs-lookup"><span data-stu-id="80533-112">Select P-0001.</span></span>
4. <span data-ttu-id="80533-113">Ajuste os grupos do banco de dados do canal, se necessário.</span><span class="sxs-lookup"><span data-stu-id="80533-113">Adjust channel database groups, if required.</span></span>
5. <span data-ttu-id="80533-114">Clique em Executar agora.</span><span class="sxs-lookup"><span data-stu-id="80533-114">Click Run now.</span></span>
6. <span data-ttu-id="80533-115">Clique em Sim.</span><span class="sxs-lookup"><span data-stu-id="80533-115">Click Yes.</span></span>

### <a name="scheduling-a-recurring-p-job"></a><span data-ttu-id="80533-116">Agendando um trabalho P recorrente</span><span class="sxs-lookup"><span data-stu-id="80533-116">Scheduling a recurring P-job</span></span>

1. <span data-ttu-id="80533-117">Vá para Todos os espaços de trabalho > TI de Varejo e Comércio.</span><span class="sxs-lookup"><span data-stu-id="80533-117">Go to All workspaces > Retail and Commerce IT.</span></span>
2. <span data-ttu-id="80533-118">Clique em Agenda de distribuição.</span><span class="sxs-lookup"><span data-stu-id="80533-118">Click Distribution schedule.</span></span>
3. <span data-ttu-id="80533-119">Selecione P-0001.</span><span class="sxs-lookup"><span data-stu-id="80533-119">Select P-0001.</span></span>
4. <span data-ttu-id="80533-120">Clique em Criar trabalho em lotes.</span><span class="sxs-lookup"><span data-stu-id="80533-120">Click Create batch job.</span></span>
5. <span data-ttu-id="80533-121">Clique em Executar em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="80533-121">Click Run in the background.</span></span>
5. <span data-ttu-id="80533-122">Habilitar Processamento em lotes.</span><span class="sxs-lookup"><span data-stu-id="80533-122">Enable Batch processing.</span></span>
6. <span data-ttu-id="80533-123">Clique em Recorrência.</span><span class="sxs-lookup"><span data-stu-id="80533-123">Click Recurrence..</span></span>
7. <span data-ttu-id="80533-124">Selecione a opção Nenhuma data de término.</span><span class="sxs-lookup"><span data-stu-id="80533-124">Select the No end date option.</span></span>
8. <span data-ttu-id="80533-125">No campo Contagem, insira o intervalo entre as execuções em minutos.</span><span class="sxs-lookup"><span data-stu-id="80533-125">In the Count field, enter interval between the runs in minutes.</span></span> <span data-ttu-id="80533-126">Normalmente isso seria 5-10.</span><span class="sxs-lookup"><span data-stu-id="80533-126">Typically this would be 5-10.</span></span>
9. <span data-ttu-id="80533-127">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="80533-127">Click OK.</span></span>
10. <span data-ttu-id="80533-128">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="80533-128">Click OK.</span></span>

<span data-ttu-id="80533-129">As ordens podem ser sincronizadas manualmente, executando o trabalho "Sincronizar ordens" ou criando um trabalho em lotes recorrente.</span><span class="sxs-lookup"><span data-stu-id="80533-129">Orders can be synchronized either by manually running the "Synchronize orders"-job or by creating a recurring batch job.</span></span>

### <a name="manually-running-order-synchronization"></a><span data-ttu-id="80533-130">Executando a sincronização da ordem manualmente</span><span class="sxs-lookup"><span data-stu-id="80533-130">Manually running order synchronization</span></span> 

<span data-ttu-id="80533-131">Siga estas etapas para executar manualmente o trabalho "Sincronizar ordens" uma vez.</span><span class="sxs-lookup"><span data-stu-id="80533-131">Follow these steps to manually run "Synchronize orders" job once.</span></span>

1. <span data-ttu-id="80533-132">Vá para Todos os espaços de trabalho > Finanças da loja.</span><span class="sxs-lookup"><span data-stu-id="80533-132">Go to All workspaces > Store financials.</span></span>
2. <span data-ttu-id="80533-133">Clique em Sincronizar ordens.</span><span class="sxs-lookup"><span data-stu-id="80533-133">Click Synchronize orders.</span></span>
3. <span data-ttu-id="80533-134">No campo Hierarquia da organização, selecione 'Lojas por região'.</span><span class="sxs-lookup"><span data-stu-id="80533-134">In the Organization hierarchy field, select 'Stores by Region'.</span></span>
    * <span data-ttu-id="80533-135">Selecione uma loja online específica ou selecione um nó se você deseja criar o trabalho em lotes para um grupo de lojas.</span><span class="sxs-lookup"><span data-stu-id="80533-135">Select either a specific online store, or select a node if you want to create the batch job for a group of stores.</span></span>  
    * <span data-ttu-id="80533-136">Clique na seta para adicionar sua seleção.</span><span class="sxs-lookup"><span data-stu-id="80533-136">Click the arrow to add your selection.</span></span>  
4. <span data-ttu-id="80533-137">Clique na guia Executar em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="80533-137">Click the Run in the background tab.</span></span>
5. <span data-ttu-id="80533-138">Desativar processamento em lotes</span><span class="sxs-lookup"><span data-stu-id="80533-138">Disable Batch processing</span></span>
6. <span data-ttu-id="80533-139">Clique em Recorrência.</span><span class="sxs-lookup"><span data-stu-id="80533-139">Click Recurrence.</span></span>
7. <span data-ttu-id="80533-140">Selecione a opção Terminar Após</span><span class="sxs-lookup"><span data-stu-id="80533-140">Select End After option</span></span>
8. <span data-ttu-id="80533-141">No campo Terminar Após, insira 1.</span><span class="sxs-lookup"><span data-stu-id="80533-141">In the End After field, enter 1.</span></span>
9. <span data-ttu-id="80533-142">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="80533-142">Click OK.</span></span>
10. <span data-ttu-id="80533-143">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="80533-143">Click OK.</span></span>

### <a name="scheduling-recurring-order-synchronization"></a><span data-ttu-id="80533-144">Agendando sincronização da ordem recorrente</span><span class="sxs-lookup"><span data-stu-id="80533-144">Scheduling recurring order synchronization</span></span>

<span data-ttu-id="80533-145">Este procedimento orienta como configurar e executar um trabalho em lotes periódico para criar ordens de venda e pagamentos para transações de lojas online.</span><span class="sxs-lookup"><span data-stu-id="80533-145">This procedure walks through configuring and running a recurrent batch job to create sales orders and payments for online store transactions.</span></span> <span data-ttu-id="80533-146">Este procedimento usa a empresa USRT nos dados de demonstração.</span><span class="sxs-lookup"><span data-stu-id="80533-146">This procedure uses the USRT company in demo data.</span></span>

1. <span data-ttu-id="80533-147">Vá para Todos os espaços de trabalho > Finanças da loja.</span><span class="sxs-lookup"><span data-stu-id="80533-147">Go to All workspaces > Store financials.</span></span>
2. <span data-ttu-id="80533-148">Clique em Sincronizar ordens.</span><span class="sxs-lookup"><span data-stu-id="80533-148">Click Synchronize orders.</span></span>
3. <span data-ttu-id="80533-149">No campo Hierarquia da organização, selecione 'Lojas por região'.</span><span class="sxs-lookup"><span data-stu-id="80533-149">In the Organization hierarchy field, select 'Stores by Region'.</span></span>
    * <span data-ttu-id="80533-150">Selecione uma loja online específica ou selecione um nó se você deseja criar o trabalho em lotes para um grupo de lojas.</span><span class="sxs-lookup"><span data-stu-id="80533-150">Select either a specific online store, or select a node if you want to create the batch job for a group of stores.</span></span>  
    * <span data-ttu-id="80533-151">Clique na seta para adicionar sua seleção.</span><span class="sxs-lookup"><span data-stu-id="80533-151">Click the arrow to add your selection.</span></span>  
4. <span data-ttu-id="80533-152">Clique na guia Executar em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="80533-152">Click the Run in the background tab.</span></span>
5. <span data-ttu-id="80533-153">Habilitar processamento em lotes</span><span class="sxs-lookup"><span data-stu-id="80533-153">Enable Batch processing</span></span>
6. <span data-ttu-id="80533-154">Clique em Recorrência.</span><span class="sxs-lookup"><span data-stu-id="80533-154">Click Recurrence.</span></span>
7. <span data-ttu-id="80533-155">Selecione a opção Nenhuma data de término.</span><span class="sxs-lookup"><span data-stu-id="80533-155">Select the No end date option.</span></span>
8. <span data-ttu-id="80533-156">No campo Contagem, insira o intervalo entre as execuções em minutos.</span><span class="sxs-lookup"><span data-stu-id="80533-156">In the Count field, enter interval between the runs in minutes.</span></span> <span data-ttu-id="80533-157">Normalmente isso seria 2-20</span><span class="sxs-lookup"><span data-stu-id="80533-157">Typically this would be 2-20</span></span>
9. <span data-ttu-id="80533-158">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="80533-158">Click OK.</span></span>
10. <span data-ttu-id="80533-159">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="80533-159">Click OK.</span></span>

## <a name="data-entities-involved-in-the-process"></a><span data-ttu-id="80533-160">Entidades de dados envolvidas no processo</span><span class="sxs-lookup"><span data-stu-id="80533-160">Data entities involved in the process</span></span>

- <span data-ttu-id="80533-161">RetailTransactionTable</span><span class="sxs-lookup"><span data-stu-id="80533-161">RetailTransactionTable</span></span>
- <span data-ttu-id="80533-162">RetailTransactionAddressTrans</span><span class="sxs-lookup"><span data-stu-id="80533-162">RetailTransactionAddressTrans</span></span>
- <span data-ttu-id="80533-163">RetailTransactionInfocodeTrans</span><span class="sxs-lookup"><span data-stu-id="80533-163">RetailTransactionInfocodeTrans</span></span>
- <span data-ttu-id="80533-164">RetailTransactionTaxTrans</span><span class="sxs-lookup"><span data-stu-id="80533-164">RetailTransactionTaxTrans</span></span>
- <span data-ttu-id="80533-165">RetailTransactionSalesTrans</span><span class="sxs-lookup"><span data-stu-id="80533-165">RetailTransactionSalesTrans</span></span>
- <span data-ttu-id="80533-166">RetailTransactionTaxMeasure</span><span class="sxs-lookup"><span data-stu-id="80533-166">RetailTransactionTaxMeasure</span></span>
- <span data-ttu-id="80533-167">RetailTransactionDiscountTrans</span><span class="sxs-lookup"><span data-stu-id="80533-167">RetailTransactionDiscountTrans</span></span>
- <span data-ttu-id="80533-168">RetailTransactionTaxTransGTE</span><span class="sxs-lookup"><span data-stu-id="80533-168">RetailTransactionTaxTransGTE</span></span>
- <span data-ttu-id="80533-169">RetailTransactionMarkupTrans</span><span class="sxs-lookup"><span data-stu-id="80533-169">RetailTransactionMarkupTrans</span></span>
- <span data-ttu-id="80533-170">RetailTransactionPaymentTrans</span><span class="sxs-lookup"><span data-stu-id="80533-170">RetailTransactionPaymentTrans</span></span>
- <span data-ttu-id="80533-171">RetailTransactionAttributeTrans</span><span class="sxs-lookup"><span data-stu-id="80533-171">RetailTransactionAttributeTrans</span></span>
