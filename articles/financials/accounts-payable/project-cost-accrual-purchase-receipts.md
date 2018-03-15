---
title: Despesas de custo de projeto sobre recebimentos de compra
description: "Este tópico descreve como os custos acumulados de projeto a partir de compra podem ser rastreados no Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CostControlCommittedCost
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 266984
ms.assetid: 61e7d2a3-5aab-4113-bccc-213f932885d2
ms.search.region: Global
ms.author: sigitac
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: ea07d8e91c94d9fdad4c2d05533981e254420188
ms.openlocfilehash: f7355dc856d97a19d0f7558061b3e2d9902dab65
ms.contentlocale: pt-br
ms.lasthandoff: 02/07/2018

---

# <a name="project-cost-accrual-on-purchase-receipts"></a><span data-ttu-id="83b4a-103">Despesas de custo de projeto sobre recebimentos de compra</span><span class="sxs-lookup"><span data-stu-id="83b4a-103">Project cost accrual on purchase receipts</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="83b4a-104">Este tópico descreve como os custos acumulados de projeto a partir de compra podem ser rastreados no Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="83b4a-104">This topic describes how accrued project costs from purchase receipts can be tracked in Microsoft Dynamics 365 for Finance and Operations, Enterprise edition.</span></span> 

<span data-ttu-id="83b4a-105">As notas fiscais de um projeto geralmente chegam após as mercadorias e os serviços serem entregues, podendo ter um impacto significativo nos indicadores de desempenho principais do projeto (KPIs).</span><span class="sxs-lookup"><span data-stu-id="83b4a-105">Invoices for a project often arrive later than the goods and services are delivered, which might have a significant impact on project key performance indicators (KPIs).</span></span> <span data-ttu-id="83b4a-106">É importante poder acompanhar essas transações em relatórios financeiros e de projeto.</span><span class="sxs-lookup"><span data-stu-id="83b4a-106">It important to be able to track these transactions in both financial and project reports.</span></span>

<span data-ttu-id="83b4a-107">O cenário de exemplo a seguir ilustra isto.</span><span class="sxs-lookup"><span data-stu-id="83b4a-107">The following example scenario illustrates this.</span></span> 

<span data-ttu-id="83b4a-108">A Consultoria da Contoso iniciou um novo projeto de implantação de nuvem.</span><span class="sxs-lookup"><span data-stu-id="83b4a-108">Contoso Consulting has started a new cloud deployment project.</span></span> <span data-ttu-id="83b4a-109">Uma ordem de compra é criada para comprar um computador para o projeto.</span><span class="sxs-lookup"><span data-stu-id="83b4a-109">A purchase order is created to buy a computer for the project.</span></span> <span data-ttu-id="83b4a-110">O computador custará US$ 1.500 e os serviços de instalação custarão US$ 150.</span><span class="sxs-lookup"><span data-stu-id="83b4a-110">The computer will cost $1500 and installation services will cost $150.</span></span> <span data-ttu-id="83b4a-111">O fornecedor entregou e instalou o computador, mas as faturas ainda não chegaram à Consultoria da Contoso.</span><span class="sxs-lookup"><span data-stu-id="83b4a-111">The vendor has delivered and installed the computer, but the invoice has not yet reached Contoso Consulting.</span></span> <span data-ttu-id="83b4a-112">O gerente de projeto gostaria de ver as despesas de custo de projeto de US$ 1.650 antes da fatura ser entregue.</span><span class="sxs-lookup"><span data-stu-id="83b4a-112">The project manager would like to see project cost accrual of $1650 before the invoice gets delivered.</span></span> <span data-ttu-id="83b4a-113">Esse custo também deve ser refletido nos demonstrativos financeiros finais do mês da empresa.</span><span class="sxs-lookup"><span data-stu-id="83b4a-113">This cost should also be reflected in the company's month end financial statements.</span></span> 

<span data-ttu-id="83b4a-114">Os custos acumulados precisam ser registradas em nível financeiro e em nível de projeto para fins de relatório.</span><span class="sxs-lookup"><span data-stu-id="83b4a-114">The accrued cost needs to be recorded on both the financial level and project level for reporting purposes.</span></span> <span data-ttu-id="83b4a-115">No Finanças e Operações, a atualização financeira do recibo do produto pode ser rastreada para categorias de item e compra.</span><span class="sxs-lookup"><span data-stu-id="83b4a-115">In Finance and Operations, the financial update of the product receipt can be tracked for the item and procurement categories.</span></span> 

<span data-ttu-id="83b4a-116">Para itens, na página **Parâmetros de contas a pagar**, selecione a opção **Lançar recibos de produto ao razão**.</span><span class="sxs-lookup"><span data-stu-id="83b4a-116">For items, on the **Accounts payable parameters** page, select the **Post product receipts to ledger** option.</span></span>
<span data-ttu-id="83b4a-117">[![accruals1](./media/accruals1-1024x409.png)](./media/accruals1.png)</span><span class="sxs-lookup"><span data-stu-id="83b4a-117">[![accruals1](./media/accruals1-1024x409.png)](./media/accruals1.png)</span></span> 

<span data-ttu-id="83b4a-118">Para categorias de compras, na página **Regra de política de categoria**, selecione políticas de **Compras** e depois selecione **Despesas de compras acumuladas no recebimento** para cada categoria de compra.</span><span class="sxs-lookup"><span data-stu-id="83b4a-118">For procurement categories, on the **Category policy rule** page, select **Purchasing** policies, and then select **Accrue purchase expense on receipt** for each procurement category.</span></span>
<span data-ttu-id="83b4a-119">[![accruals2](./media/accruals2-1024x569.png)](./media/accruals2.png)</span><span class="sxs-lookup"><span data-stu-id="83b4a-119">[![accruals2](./media/accruals2-1024x569.png)](./media/accruals2.png)</span></span> 

<span data-ttu-id="83b4a-120">As contas **Despesa de compra não faturada** e **Despesa de compra** na **Configuração de lançamento** serão usadas quando os comprovantes relacionados ao recibo do produto forem lançados.</span><span class="sxs-lookup"><span data-stu-id="83b4a-120">The **Purchase expenditure un-invoiced** and **Purchase accrual** accounts in **Posting setup** will be used when vouchers that are related to the product receipt are posted.</span></span>
<span data-ttu-id="83b4a-121">[![accruals3](./media/accruals3-1024x429.png)](./media/accruals3.png)</span><span class="sxs-lookup"><span data-stu-id="83b4a-121">[![accruals3](./media/accruals3-1024x429.png)](./media/accruals3.png)</span></span> 

<span data-ttu-id="83b4a-122">Com esse mesmo cenário, vejamos como o lançamento de recibo de produto impactará as informações de contabilidade e projeto.</span><span class="sxs-lookup"><span data-stu-id="83b4a-122">Using this same scenario, let's see how posting a product receipt will impact General ledger and Project information.</span></span> 

<span data-ttu-id="83b4a-123">**Etapa 1:** Criar e confirmar uma nova ordem de compra do projeto para registrar a compra de um computador por US$ 1.500 e serviços de instalação por US$ 150.</span><span class="sxs-lookup"><span data-stu-id="83b4a-123">**Step 1:** Create and confirm a new purchase order for the project to record the purchase of a computer for $1500 and installation services for $150.</span></span>
<span data-ttu-id="83b4a-124">[![accruals4](./media/accruals4-1024x497.png)](./media/accruals4.png)</span><span class="sxs-lookup"><span data-stu-id="83b4a-124">[![accruals4](./media/accruals4-1024x497.png)](./media/accruals4.png)</span></span> 

<span data-ttu-id="83b4a-125">Quando a ordem de compra for confirmada, as transações do custo comprometido são criadas para o projeto.</span><span class="sxs-lookup"><span data-stu-id="83b4a-125">When the purchase order is confirmed, transactions for the committed cost are created for the project.</span></span> 
<span data-ttu-id="83b4a-126">[![accruals5](./media/accruals5-1024x219.png)](./media/accruals5.png)</span><span class="sxs-lookup"><span data-stu-id="83b4a-126">[![accruals5](./media/accruals5-1024x219.png)](./media/accruals5.png)</span></span> 

> [!NOTE]
> <span data-ttu-id="83b4a-127">As transações do custo comprometido terão o campo **Origem da transação** definido para **Ordem de compra**.</span><span class="sxs-lookup"><span data-stu-id="83b4a-127">The transactions for the committed cost will have the **Transaction Origin** field set to **Purchase Order**.</span></span> <span data-ttu-id="83b4a-128">Criar e confirmar uma ordem de compra não cria transações para um projeto.</span><span class="sxs-lookup"><span data-stu-id="83b4a-128">Creating and confirming a purchase order does not create transactions for a project.</span></span> 

<span data-ttu-id="83b4a-129">**Etapa 2:** Mercadorias e serviços são entregues e um recibo de produto é registrado.</span><span class="sxs-lookup"><span data-stu-id="83b4a-129">**Step 2:** Goods and services get delivered and a product receipt is registered.</span></span> 

<span data-ttu-id="83b4a-130">Lançar um recebimento de produtos gerará e lançará um comprovante no razão.</span><span class="sxs-lookup"><span data-stu-id="83b4a-130">Posting a product receipt will generate and post a voucher to the ledger.</span></span> <span data-ttu-id="83b4a-131">O comprovante debitará as despesas de compra, conta não faturada e conta de despesas de compra em crédito.</span><span class="sxs-lookup"><span data-stu-id="83b4a-131">The voucher will debit the purchase expenditure, un-invoiced account, and credit purchase accrual account.</span></span> 
<span data-ttu-id="83b4a-132">[![accruals6](./media/accruals6-1024x214.png)](./media/accruals6.png)</span><span class="sxs-lookup"><span data-stu-id="83b4a-132">[![accruals6](./media/accruals6-1024x214.png)](./media/accruals6.png)</span></span>

> [!NOTE]
> <span data-ttu-id="83b4a-133">Lançar um recibo de produtos usará a configuração de lançamento de categorias de compra e produtos, e não a configuração de lançamento das categorias de projeto.</span><span class="sxs-lookup"><span data-stu-id="83b4a-133">Posting a product receipt will use the posting setup for procurement categories and products, and not the posting setup for the project categories.</span></span> <span data-ttu-id="83b4a-134">Para refletir corretamente o impacto financeiro das despesas de compra, essa configuração precisar estar alinhada.</span><span class="sxs-lookup"><span data-stu-id="83b4a-134">In order to correctly reflect financial impact of purchase accruals, this setup needs to be aligned.</span></span> 

<span data-ttu-id="83b4a-135">É possível mapear categorias de compras para projetar categorias na página **Categoria de compra**.</span><span class="sxs-lookup"><span data-stu-id="83b4a-135">It is possible to map procurement categories to project categories on the **Procurement category** page.</span></span>
<span data-ttu-id="83b4a-136">[![accruals7](./media/accruals7-1024x390.png)](./media/accruals7.png)</span><span class="sxs-lookup"><span data-stu-id="83b4a-136">[![accruals7](./media/accruals7-1024x390.png)](./media/accruals7.png)</span></span>

<span data-ttu-id="83b4a-137">**Etapa 3:** Criar um rascunho da fatura de fornecedor.</span><span class="sxs-lookup"><span data-stu-id="83b4a-137">**Step 3:** Create a draft vendor invoice.</span></span> 

<span data-ttu-id="83b4a-138">No Finanças e Operações, lançar um recibo de produto não impactará nas informações de projeto.</span><span class="sxs-lookup"><span data-stu-id="83b4a-138">In Finance and Operations, posting a product receipt does not impact project information.</span></span> <span data-ttu-id="83b4a-139">Como uma solução alternativa, você pode gerar um rascunho de fatura de fornecedor logo após o lançamento do recebimento de compra.</span><span class="sxs-lookup"><span data-stu-id="83b4a-139">As a workaround, you could generate a draft vendor invoice right after posting the purchase receipt.</span></span> <span data-ttu-id="83b4a-140">Vá para a página **Ordem de compra** &gt; **Guia de fatura** &gt; **Gerar** &gt; **Fatura**.</span><span class="sxs-lookup"><span data-stu-id="83b4a-140">Go to the **Purchase Order** page &gt; **Invoice tab** &gt; **Generate** &gt; **Invoice**.</span></span> <span data-ttu-id="83b4a-141">Essa ação cria um documento de fatura pendente que atualiza as informações do projeto.</span><span class="sxs-lookup"><span data-stu-id="83b4a-141">This creates a pending invoice document that updates project information.</span></span> 

<span data-ttu-id="83b4a-142">Criar um rascunho da fatura de fornecedor gerará transações de projeto pendentes.</span><span class="sxs-lookup"><span data-stu-id="83b4a-142">Creating a draft vendor invoice will generate pending project transactions.</span></span> 
<span data-ttu-id="83b4a-143">[![accruals8](./media/accruals8-1024x225.png)](./media/accruals8.png)</span><span class="sxs-lookup"><span data-stu-id="83b4a-143">[![accruals8](./media/accruals8-1024x225.png)](./media/accruals8.png)</span></span> 

<span data-ttu-id="83b4a-144">Na página **Custo comprometido**, registros criados na etapa 1 serão fechados e novos registros serão criados para refletir o custo comprometido proveniente de fatura de fornecedor pendente.</span><span class="sxs-lookup"><span data-stu-id="83b4a-144">In the **Committed cost** page, records created in step 1 will be closed and new records will be created to reflect cost commitment coming from the pending vendor invoice.</span></span> <span data-ttu-id="83b4a-145">O campo **Origem da transação** do custo comprometido será definido como **Fatura de fornecedor**.</span><span class="sxs-lookup"><span data-stu-id="83b4a-145">The **Transaction origin** field for the committed cost will be set to **Vendor invoice**.</span></span>
<span data-ttu-id="83b4a-146">[![accruals9](./media/accruals9-1024x200.png)](./media/accruals9.png)</span><span class="sxs-lookup"><span data-stu-id="83b4a-146">[![accruals9](./media/accruals9-1024x200.png)](./media/accruals9.png)</span></span>

<span data-ttu-id="83b4a-147">A fatura do fornecedor permanecerá em um estado pendente até que a fatura de fornecedor real chegue.</span><span class="sxs-lookup"><span data-stu-id="83b4a-147">The vendor invoice will remain in a pending state until the actual vendor invoice arrives.</span></span>




