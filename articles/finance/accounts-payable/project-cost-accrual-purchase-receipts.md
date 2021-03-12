---
title: Despesas de custo de projeto sobre recebimentos de compra
description: Este tópico descreve como os custos de projeto acumulados de recibos de compra podem ser rastreados no Microsoft Dynamics 365 Finance.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CostControlCommittedCost
audience: Application User
ms.reviewer: roschlom
ms.custom: 266984
ms.assetid: 61e7d2a3-5aab-4113-bccc-213f932885d2
ms.search.region: Global
ms.author: sigitac
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: d27fba816ca289e6a84e8684f7f90686864fb0b6
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4972072"
---
# <a name="project-cost-accrual-on-purchase-receipts"></a><span data-ttu-id="97f72-103">Despesas de custo de projeto sobre recebimentos de compra</span><span class="sxs-lookup"><span data-stu-id="97f72-103">Project cost accrual on purchase receipts</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="97f72-104">Este tópico descreve como os custos de projeto acumulados de recibos de compra podem ser rastreados no Microsoft Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="97f72-104">This topic describes how accrued project costs from purchase receipts can be tracked in Microsoft Dynamics 365 Finance.</span></span> 

<span data-ttu-id="97f72-105">As notas fiscais de um projeto geralmente chegam após as mercadorias e os serviços serem entregues, podendo ter um impacto significativo nos indicadores de desempenho principais do projeto (KPIs).</span><span class="sxs-lookup"><span data-stu-id="97f72-105">Invoices for a project often arrive later than the goods and services are delivered, which might have a significant impact on project key performance indicators (KPIs).</span></span> <span data-ttu-id="97f72-106">É importante poder acompanhar essas transações em relatórios financeiros e de projeto.</span><span class="sxs-lookup"><span data-stu-id="97f72-106">It important to be able to track these transactions in both financial and project reports.</span></span>

<span data-ttu-id="97f72-107">O cenário de exemplo a seguir ilustra isto.</span><span class="sxs-lookup"><span data-stu-id="97f72-107">The following example scenario illustrates this.</span></span> 

<span data-ttu-id="97f72-108">A Consultoria da Contoso iniciou um novo projeto de implantação de nuvem.</span><span class="sxs-lookup"><span data-stu-id="97f72-108">Contoso Consulting has started a new cloud deployment project.</span></span> <span data-ttu-id="97f72-109">Uma ordem de compra é criada para comprar um computador para o projeto.</span><span class="sxs-lookup"><span data-stu-id="97f72-109">A purchase order is created to buy a computer for the project.</span></span> <span data-ttu-id="97f72-110">O computador custará US$ 1.500 e os serviços de instalação custarão US$ 150.</span><span class="sxs-lookup"><span data-stu-id="97f72-110">The computer will cost $1500 and installation services will cost $150.</span></span> <span data-ttu-id="97f72-111">O fornecedor entregou e instalou o computador, mas as faturas ainda não chegaram à Consultoria da Contoso.</span><span class="sxs-lookup"><span data-stu-id="97f72-111">The vendor has delivered and installed the computer, but the invoice has not yet reached Contoso Consulting.</span></span> <span data-ttu-id="97f72-112">O gerente de projeto gostaria de ver as despesas de custo de projeto de US$ 1.650 antes da fatura ser entregue.</span><span class="sxs-lookup"><span data-stu-id="97f72-112">The project manager would like to see project cost accrual of $1650 before the invoice gets delivered.</span></span> <span data-ttu-id="97f72-113">Esse custo também deve ser refletido nos demonstrativos financeiros finais do mês da empresa.</span><span class="sxs-lookup"><span data-stu-id="97f72-113">This cost should also be reflected in the company's month end financial statements.</span></span> 

<span data-ttu-id="97f72-114">Os custos acumulados precisam ser registradas em nível financeiro e em nível de projeto para fins de relatório.</span><span class="sxs-lookup"><span data-stu-id="97f72-114">The accrued cost needs to be recorded on both the financial level and project level for reporting purposes.</span></span> <span data-ttu-id="97f72-115">A atualização financeira do recibo do produto pode ser rastreada para categorias de item e compra.</span><span class="sxs-lookup"><span data-stu-id="97f72-115">The financial update of the product receipt can be tracked for the item and procurement categories.</span></span> 

<span data-ttu-id="97f72-116">Para itens, na página **Parâmetros de contas a pagar**, selecione a opção **Lançar recibos de produto ao razão**.</span><span class="sxs-lookup"><span data-stu-id="97f72-116">For items, on the **Accounts payable parameters** page, select the **Post product receipts to ledger** option.</span></span>
<span data-ttu-id="97f72-117">[![Página Parâmetros de contas a pagar](./media/accruals1-1024x409.png)](./media/accruals1.png)</span><span class="sxs-lookup"><span data-stu-id="97f72-117">[![Accounts payable parameters page](./media/accruals1-1024x409.png)](./media/accruals1.png)</span></span> 

<span data-ttu-id="97f72-118">Para categorias de compras, na página **Regra de política de categoria**, selecione políticas de **Compras** e depois selecione **Despesas de compras acumuladas no recebimento** para cada categoria de compra.</span><span class="sxs-lookup"><span data-stu-id="97f72-118">For procurement categories, on the **Category policy rule** page, select **Purchasing** policies, and then select **Accrue purchase expense on receipt** for each procurement category.</span></span>
<span data-ttu-id="97f72-119">[![Página Regra de política de categoria](./media/accruals2-1024x569.png)](./media/accruals2.png)</span><span class="sxs-lookup"><span data-stu-id="97f72-119">[![Category policy rule page](./media/accruals2-1024x569.png)](./media/accruals2.png)</span></span> 

<span data-ttu-id="97f72-120">As contas **Despesa de compra não faturada** e **Despesa de compra** na **Configuração de lançamento** serão usadas quando os comprovantes relacionados ao recibo do produto forem lançados.</span><span class="sxs-lookup"><span data-stu-id="97f72-120">The **Purchase expenditure un-invoiced** and **Purchase accrual** accounts in **Posting setup** will be used when vouchers that are related to the product receipt are posted.</span></span>

<span data-ttu-id="97f72-121">Com esse mesmo cenário, vejamos como o lançamento de recibo de produto impactará as informações de contabilidade e projeto.</span><span class="sxs-lookup"><span data-stu-id="97f72-121">Using this same scenario, let's see how posting a product receipt will impact General ledger and Project information.</span></span> 

<span data-ttu-id="97f72-122">**Etapa 1:** Criar e confirmar uma nova ordem de compra do projeto para registrar a compra de um computador por US$ 1.500 e serviços de instalação por US$ 150.</span><span class="sxs-lookup"><span data-stu-id="97f72-122">**Step 1:** Create and confirm a new purchase order for the project to record the purchase of a computer for $1500 and installation services for $150.</span></span>
<span data-ttu-id="97f72-123">[![Criar nova ordem de compra](./media/accruals4-1024x497.png)](./media/accruals4.png)</span><span class="sxs-lookup"><span data-stu-id="97f72-123">[![Create new purchase order](./media/accruals4-1024x497.png)](./media/accruals4.png)</span></span> 

<span data-ttu-id="97f72-124">Quando a ordem de compra for confirmada, as transações do custo comprometido são criadas para o projeto.</span><span class="sxs-lookup"><span data-stu-id="97f72-124">When the purchase order is confirmed, transactions for the committed cost are created for the project.</span></span> 
<span data-ttu-id="97f72-125">[![Transações criadas](./media/accruals5-1024x219.png)](./media/accruals5.png)</span><span class="sxs-lookup"><span data-stu-id="97f72-125">[![Transactions created](./media/accruals5-1024x219.png)](./media/accruals5.png)</span></span> 

> [!NOTE]
> <span data-ttu-id="97f72-126">As transações do custo comprometido terão o campo **Origem da transação** definido para **Ordem de compra**.</span><span class="sxs-lookup"><span data-stu-id="97f72-126">The transactions for the committed cost will have the **Transaction Origin** field set to **Purchase Order**.</span></span> <span data-ttu-id="97f72-127">Criar e confirmar uma ordem de compra não cria transações para um projeto.</span><span class="sxs-lookup"><span data-stu-id="97f72-127">Creating and confirming a purchase order does not create transactions for a project.</span></span> 

<span data-ttu-id="97f72-128">**Etapa 2:** Mercadorias e serviços são entregues e um recibo de produto é registrado.</span><span class="sxs-lookup"><span data-stu-id="97f72-128">**Step 2:** Goods and services get delivered and a product receipt is registered.</span></span> 

<span data-ttu-id="97f72-129">Lançar um recebimento de produtos gerará e lançará um comprovante no razão.</span><span class="sxs-lookup"><span data-stu-id="97f72-129">Posting a product receipt will generate and post a voucher to the ledger.</span></span> <span data-ttu-id="97f72-130">O comprovante debitará as despesas de compra, conta não faturada e conta de despesas de compra em crédito.</span><span class="sxs-lookup"><span data-stu-id="97f72-130">The voucher will debit the purchase expenditure, un-invoiced account, and credit purchase accrual account.</span></span> 
<span data-ttu-id="97f72-131">[![Comprovantes de transações](./media/accruals6-1024x214.png)](./media/accruals6.png)</span><span class="sxs-lookup"><span data-stu-id="97f72-131">[![Voucher transactions](./media/accruals6-1024x214.png)](./media/accruals6.png)</span></span>

> [!NOTE]
> <span data-ttu-id="97f72-132">Lançar um recibo de produtos usará a configuração de lançamento de categorias de compra e produtos, e não a configuração de lançamento das categorias de projeto.</span><span class="sxs-lookup"><span data-stu-id="97f72-132">Posting a product receipt will use the posting setup for procurement categories and products, and not the posting setup for the project categories.</span></span> <span data-ttu-id="97f72-133">Para refletir corretamente o impacto financeiro das despesas de compra, essa configuração precisar estar alinhada.</span><span class="sxs-lookup"><span data-stu-id="97f72-133">In order to correctly reflect financial impact of purchase accruals, this setup needs to be aligned.</span></span> 

<span data-ttu-id="97f72-134">É possível mapear categorias de compras para projetar categorias na página **Categoria de compra**.</span><span class="sxs-lookup"><span data-stu-id="97f72-134">It is possible to map procurement categories to project categories on the **Procurement category** page.</span></span>
<span data-ttu-id="97f72-135">[![Página Categoria de compras](./media/accruals7-1024x390.png)](./media/accruals7.png)</span><span class="sxs-lookup"><span data-stu-id="97f72-135">[![Procurement category page](./media/accruals7-1024x390.png)](./media/accruals7.png)</span></span>

<span data-ttu-id="97f72-136">**Etapa 3:** Criar um rascunho da fatura de fornecedor.</span><span class="sxs-lookup"><span data-stu-id="97f72-136">**Step 3:** Create a draft vendor invoice.</span></span> 

<span data-ttu-id="97f72-137">Lançar um recibo de produto não afetará as informações de projeto.</span><span class="sxs-lookup"><span data-stu-id="97f72-137">Posting a product receipt does not impact project information.</span></span> <span data-ttu-id="97f72-138">Como uma solução alternativa, você pode gerar um rascunho de fatura de fornecedor logo após o lançamento do recebimento de compra.</span><span class="sxs-lookup"><span data-stu-id="97f72-138">As a workaround, you could generate a draft vendor invoice right after posting the purchase receipt.</span></span> <span data-ttu-id="97f72-139">Vá para a página **Ordem de compra** &gt; **Guia de fatura** &gt; **Gerar** &gt; **Fatura**.</span><span class="sxs-lookup"><span data-stu-id="97f72-139">Go to the **Purchase Order** page &gt; **Invoice tab** &gt; **Generate** &gt; **Invoice**.</span></span> <span data-ttu-id="97f72-140">Essa ação cria um documento de fatura pendente que atualiza as informações do projeto.</span><span class="sxs-lookup"><span data-stu-id="97f72-140">This creates a pending invoice document that updates project information.</span></span> 

<span data-ttu-id="97f72-141">Criar um rascunho da fatura de fornecedor gerará transações de projeto pendentes.</span><span class="sxs-lookup"><span data-stu-id="97f72-141">Creating a draft vendor invoice will generate pending project transactions.</span></span> 
<span data-ttu-id="97f72-142">[![Minhas transações de projeto pendentes](./media/accruals8-1024x225.png)](./media/accruals8.png)</span><span class="sxs-lookup"><span data-stu-id="97f72-142">[![Pending project transactions](./media/accruals8-1024x225.png)](./media/accruals8.png)</span></span> 

<span data-ttu-id="97f72-143">Na página **Custo comprometido**, registros criados na etapa 1 serão fechados e novos registros serão criados para refletir o custo comprometido proveniente de fatura de fornecedor pendente.</span><span class="sxs-lookup"><span data-stu-id="97f72-143">In the **Committed cost** page, records created in step 1 will be closed and new records will be created to reflect cost commitment coming from the pending vendor invoice.</span></span> <span data-ttu-id="97f72-144">O campo **Origem da transação** do custo comprometido será definido como **Fatura de fornecedor**.</span><span class="sxs-lookup"><span data-stu-id="97f72-144">The **Transaction origin** field for the committed cost will be set to **Vendor invoice**.</span></span>
<span data-ttu-id="97f72-145">[![Página Custos comprometidos](./media/accruals9-1024x200.png)](./media/accruals9.png)</span><span class="sxs-lookup"><span data-stu-id="97f72-145">[![Commited costs page](./media/accruals9-1024x200.png)](./media/accruals9.png)</span></span>

<span data-ttu-id="97f72-146">A fatura do fornecedor permanecerá em um estado pendente até que a fatura de fornecedor real chegue.</span><span class="sxs-lookup"><span data-stu-id="97f72-146">The vendor invoice will remain in a pending state until the actual vendor invoice arrives.</span></span>



