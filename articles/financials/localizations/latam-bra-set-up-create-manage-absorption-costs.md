---
title: Configurar, criar e gerenciar custos de absorção
description: Este tópico fornece informações sobre como configurar, criar e gerenciar custos de absorção para o Brasil.
author: ShylaThompson
manager: AnnBe
ms.date: 09/13/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Brazil
ms.author: shylaw
ms.search.validFrom: 2017-12-31
ms.dyn365.ops.version: 7.2999999999999998
ms.openlocfilehash: 8a0fad9ad1bca82758aaebcd474438105c097b6c
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "371654"
---
# <a name="set-up-create-and-manage-absorption-costs"></a><span data-ttu-id="87dfe-103">Configurar, criar e gerenciar custos de absorção</span><span class="sxs-lookup"><span data-stu-id="87dfe-103">Set up, create, and manage absorption costs</span></span> 

[!include [banner](../includes/banner.md)]

<span data-ttu-id="87dfe-104">Você pode calcular e lançar os custos diretos e indiretos incorridos nas ordens de produção de um período fiscal.</span><span class="sxs-lookup"><span data-stu-id="87dfe-104">You can calculate and post the direct and indirect costs that are incurred in the production orders for a fiscal period.</span></span> <span data-ttu-id="87dfe-105">Os custos finais da fabricação são registrados no razão no final do período fiscal.</span><span class="sxs-lookup"><span data-stu-id="87dfe-105">The final manufacturing costs are registered in the ledger at the end of the fiscal period.</span></span> <span data-ttu-id="87dfe-106">Você pode calcular os custos de absorção alocando os custos totais de fabricação para os produtos fabricados durante um período fiscal.</span><span class="sxs-lookup"><span data-stu-id="87dfe-106">You can calculate the absorption costs by allocating the total manufacturing costs to the products that are manufactured during a fiscal period.</span></span>

## <a name="set-up-a-number-sequence-for-absorption-costs"></a><span data-ttu-id="87dfe-107">Configurar uma sequência numérica para custos de absorção</span><span class="sxs-lookup"><span data-stu-id="87dfe-107">Set up a number sequence for absorption costs</span></span>

<span data-ttu-id="87dfe-108">Use este procedimento para configurar o código da sequência numérica para diários de absorção de custos.</span><span class="sxs-lookup"><span data-stu-id="87dfe-108">Use this procedure to set up the number sequence code for cost absorption journals.</span></span>

1.  <span data-ttu-id="87dfe-109">Clique em **Controle de produção** \> **Configuração** \> **Custos de absorção** \> **Parâmetros**.</span><span class="sxs-lookup"><span data-stu-id="87dfe-109">Click **Production control** \> **Setup** \> **Absorption costs** \> **Parameters**.</span></span>

2.  <span data-ttu-id="87dfe-110">No campo **Código da sequência numérica**, selecione o código de sequência numérica a ser usado para o diário de absorção de custo.</span><span class="sxs-lookup"><span data-stu-id="87dfe-110">In the **Number sequence code** field, select the number sequence code to use for the cost absorption journal.</span></span>

## <a name="set-up-a-cost-center-for-absorption-costs"></a><span data-ttu-id="87dfe-111">Configurar um centro de custo para custos de absorção</span><span class="sxs-lookup"><span data-stu-id="87dfe-111">Set up a cost center for absorption costs</span></span>

<span data-ttu-id="87dfe-112">Use este procedimento para configurar um tipo de custo para um centro de custo.</span><span class="sxs-lookup"><span data-stu-id="87dfe-112">Use this procedure to set up a cost type for a cost center.</span></span> <span data-ttu-id="87dfe-113">Você pode usar a página **Centro de custo** para configurar centros de custos para custos de absorção.</span><span class="sxs-lookup"><span data-stu-id="87dfe-113">You can use the **Cost center** page to set up cost centers for absorption costs.</span></span> 

1.  <span data-ttu-id="87dfe-114">Clique em **Controle de produção** \> **Configuração** \> **Custos de absorção** \> **Centros de custo**.</span><span class="sxs-lookup"><span data-stu-id="87dfe-114">Click **Production control** \> **Setup** \> **Absorption costs** \> **Cost centers**.</span></span>

2.  <span data-ttu-id="87dfe-115">Selecione o centro de custo a ser usado para lançar custos de absorção.</span><span class="sxs-lookup"><span data-stu-id="87dfe-115">Select the cost center to use to post absorption costs.</span></span>

3.  <span data-ttu-id="87dfe-116">No campo **Tipo de custo**, selecione o tipo de custo do centro de custo.</span><span class="sxs-lookup"><span data-stu-id="87dfe-116">In the **Cost type** field, select the type of cost for the cost center.</span></span>

## <a name="set-up-journal-names-for-absorption-costs"></a><span data-ttu-id="87dfe-117">Configurar nomes de diário para custos de absorção</span><span class="sxs-lookup"><span data-stu-id="87dfe-117">Set up journal names for absorption costs</span></span>

<span data-ttu-id="87dfe-118">Use este procedimento para configurar nomes de diários para custos de absorção.</span><span class="sxs-lookup"><span data-stu-id="87dfe-118">Use this procedure to set up journal names for absorption costs.</span></span>

1.  <span data-ttu-id="87dfe-119">Clique em **Controle de produção** \> **Configuração** \> **Custos de absorção** \> **Nomes de diário**.</span><span class="sxs-lookup"><span data-stu-id="87dfe-119">Click **Production control** \> **Setup** \> **Absorption costs** \> **Journal names**.</span></span>

2.  <span data-ttu-id="87dfe-120">Pressione CTRL+N para criar um registro.</span><span class="sxs-lookup"><span data-stu-id="87dfe-120">Press CTRL+N to create a record.</span></span>

3.  <span data-ttu-id="87dfe-121">No campo **Nome**, digite um nome para o diário.</span><span class="sxs-lookup"><span data-stu-id="87dfe-121">In the **Name** field, enter a name for the journal.</span></span>  

    > [!NOTE]
    > <span data-ttu-id="87dfe-122">O campo <STRONG>Tipo de diário</STRONG> é atualizado com o tipo de diário padrão que é usado para custos de absorção.</span><span class="sxs-lookup"><span data-stu-id="87dfe-122">The <STRONG>Journal type</STRONG> field is updated with the default journal type that is used for absorption costs.</span></span> <span data-ttu-id="87dfe-123">O tipo de diário padrão é <STRONG>Custos indiretos</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="87dfe-123">The default journal type is <STRONG>Indirect costs</STRONG>.</span></span>

4.  <span data-ttu-id="87dfe-124">No campo **Descrição** informe uma breve descrição do diário.</span><span class="sxs-lookup"><span data-stu-id="87dfe-124">In the **Description** field, enter a brief description for the journal.</span></span>

5.  <span data-ttu-id="87dfe-125">No campo **Série de comprovante**, selecione o código de sequência numérica a ser usado para o diário.</span><span class="sxs-lookup"><span data-stu-id="87dfe-125">In the **Voucher series** field, select the number sequence code to use for the journal.</span></span>

6.  <span data-ttu-id="87dfe-126">No campo **Seleção por**, indique se um novo comprovante será selecionado durante a entrada ou após o lançamento.</span><span class="sxs-lookup"><span data-stu-id="87dfe-126">In the **Selection by** field, indicate whether a new voucher is selected during entry or after posting.</span></span>

7.  <span data-ttu-id="87dfe-127">No campo **Nível de detalhe**, selecione o método a ser usado para resumir os detalhes do diário.</span><span class="sxs-lookup"><span data-stu-id="87dfe-127">In the **Detail level** field, select the method to use to summarize the details of the journal.</span></span>

## <a name="create-the-cost-absorption-journal"></a><span data-ttu-id="87dfe-128">Criar o diário de absorção de custos</span><span class="sxs-lookup"><span data-stu-id="87dfe-128">Create the cost absorption journal</span></span>

<span data-ttu-id="87dfe-129">Use este procedimento para criar e lançar um diário de absorção de custos.</span><span class="sxs-lookup"><span data-stu-id="87dfe-129">Use this procedure to create and post a cost absorption journal.</span></span>

1.  <span data-ttu-id="87dfe-130">Clique em **Controle de produção** \> **Periódico** \> **Custos de absorção** \> **Diário de absorção de custo**.</span><span class="sxs-lookup"><span data-stu-id="87dfe-130">Click **Production control** \> **Periodic** \> **Absorption costs** \> **Cost absorption journal**.</span></span>

2.  <span data-ttu-id="87dfe-131">Para criar um diário, pressione CTRL+N.</span><span class="sxs-lookup"><span data-stu-id="87dfe-131">Press CTRL+N to create a journal.</span></span>

3.  <span data-ttu-id="87dfe-132">Na guia **Visão geral**, no campo **Nome**, selecione o nome do diário de absorção de custo.</span><span class="sxs-lookup"><span data-stu-id="87dfe-132">On the **Overview** tab, in the **Name** field, select the name of the cost absorption journal.</span></span>

4.  <span data-ttu-id="87dfe-133">No campo **Mês/ano de fechamento**, selecione o mês e ano nos quais os custos são lançados.</span><span class="sxs-lookup"><span data-stu-id="87dfe-133">In the **Month/Year to close** field, select the month and year that the costs are posted for.</span></span>

5.  <span data-ttu-id="87dfe-134">Clique em **Linhas** para abrir a página **Linhas do diário** e especifique valores nos seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="87dfe-134">Click **Lines** to open the **Journal lines** page, and then specify values in the following fields:</span></span>
    
      - <span data-ttu-id="87dfe-135">**Data** – a data na qual a linha do diário será lançada.</span><span class="sxs-lookup"><span data-stu-id="87dfe-135">**Date** – The date on which to post the journal line.</span></span>
      - <span data-ttu-id="87dfe-136">**Conta contábil** – o número da conta contábil na qual a linha do diário será lançada.</span><span class="sxs-lookup"><span data-stu-id="87dfe-136">**Ledger account** – The ledger account number to post the journal line to.</span></span>
      - <span data-ttu-id="87dfe-137">**Centro de custo** – O número do centro de custo a ser usado para lançar a linha do diário.</span><span class="sxs-lookup"><span data-stu-id="87dfe-137">**Cost center** – The cost center number to use to post the journal line.</span></span>
      - <span data-ttu-id="87dfe-138">**Valor do custo** – O valor do custo da linha do diário.</span><span class="sxs-lookup"><span data-stu-id="87dfe-138">**Cost amount** – The cost amount for the journal line.</span></span>

6.  <span data-ttu-id="87dfe-139">Clique em **Lançar** \> **OK** para lançar a linha do diário.</span><span class="sxs-lookup"><span data-stu-id="87dfe-139">Click **Post** \> **OK** to post the journal line.</span></span>

    > [!NOTE]
    > <span data-ttu-id="87dfe-140">Você pode visualizar o tipo de custo absorvido lançado em um centro de trabalho, o centro de custo correspondente ao qual o centro de trabalho está associado, a taxa por hora e a capacidade planejada para os detalhes do centro de trabalho na página <STRONG>Custos absorvidos</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="87dfe-140">You can view the type of absorbed cost that is posted to a work center, the corresponding cost center that the work center is associated with, the hourly rate, and the planned capacity for the work center details on the <STRONG>Absorbed costs</STRONG> page.</span></span>

## <a name="close-absorption-costs"></a><span data-ttu-id="87dfe-141">Fechar custos de absorção</span><span class="sxs-lookup"><span data-stu-id="87dfe-141">Close absorption costs</span></span>

<span data-ttu-id="87dfe-142">Você pode lançar os custos de absorção para um mês e um ano específicos no razão.</span><span class="sxs-lookup"><span data-stu-id="87dfe-142">You can post the absorption costs for a specific month and year to the ledger.</span></span> <span data-ttu-id="87dfe-143">Você pode especificar a conta de transferência e a contrapartida de transferência nos campos **Contas - WIP** e **Contas - custos** na página **Recursos** .</span><span class="sxs-lookup"><span data-stu-id="87dfe-143">You can specify the transfer account and transfer offset account in the **Accounts - WIP** and **Accounts - costing** fields on the **Resources** page.</span></span> 

1.  <span data-ttu-id="87dfe-144">Clique em **Controle de produção** \> **Periódico** \> **Custos de absorção** \> **Custos por absorção - Fechamento mensal**.</span><span class="sxs-lookup"><span data-stu-id="87dfe-144">Click **Production control** \> **Periodic** \> **Absorption costs** \> **Absorption costs - monthly closing**.</span></span>

2.  <span data-ttu-id="87dfe-145">No campo **Mês/ano de fechamento**, selecione o mês e ano nos quais os custos absorvidos são lançados.</span><span class="sxs-lookup"><span data-stu-id="87dfe-145">In the **Month/Year to close** field, select the month and year to post the absorbed costs for.</span></span>

3.  <span data-ttu-id="87dfe-146">Clique em **OK** para lançar os custos de absorção para o mês e o ano selecionados.</span><span class="sxs-lookup"><span data-stu-id="87dfe-146">Click **OK** to post the absorption costs for the selected month and year.</span></span>

## <a name="cancel-absorbed-costs"></a><span data-ttu-id="87dfe-147">Cancelar custos absorvidos</span><span class="sxs-lookup"><span data-stu-id="87dfe-147">Cancel absorbed costs</span></span>

<span data-ttu-id="87dfe-148">Use este procedimento para cancelar os custos absorvidos que não são lançados no razão para um mês e um ano específicos.</span><span class="sxs-lookup"><span data-stu-id="87dfe-148">Use this procedure to cancel the absorbed costs that are not posted to the ledger for a specific month and year.</span></span> <span data-ttu-id="87dfe-149">Não será possível cancelar os custos absorvidos depois que o fechamento mensal for concluído.</span><span class="sxs-lookup"><span data-stu-id="87dfe-149">You cannot cancel the absorbed costs after the monthly closing is completed.</span></span>

1.  <span data-ttu-id="87dfe-150">Clique em **Controle de produção** \> **Periódico** \> **Custos de absorção** \> **Cancelamento dos custos de absorção**.</span><span class="sxs-lookup"><span data-stu-id="87dfe-150">Click **Production control** \> **Periodic** \> **Absorption costs** \> **Absorbed costs cancellation**.</span></span>

2.  <span data-ttu-id="87dfe-151">No campo **Mês/ano para cancelar**, selecione o mês e ano nos quais os custos absorvidos serão cancelados.</span><span class="sxs-lookup"><span data-stu-id="87dfe-151">In the **Month/Year to cancel** field, select the month and year to cancel the absorbed costs for.</span></span>

3.  <span data-ttu-id="87dfe-152">Clique em **OK** para cancelar os custos absorvidos para o mês e o ano selecionados.</span><span class="sxs-lookup"><span data-stu-id="87dfe-152">Click **OK** to cancel the absorbed costs for the selected month and year.</span></span>
