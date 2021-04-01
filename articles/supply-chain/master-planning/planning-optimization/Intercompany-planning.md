---
title: Planejamento intercompanhia
description: Este tópico descreve o planejamento intercompanhia e explica como configurar o planejamento intercompanhia com a Otimização de Planejamento no Microsoft Dynamics 365 Supply Chain Management.
author: ChristianRytt
manager: tfehr
ms.date: 12/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2020-12-02
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: dd498489e18eaba81720757faa14c0bf7b7d67f1
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5263389"
---
# <a name="intercompany-planning"></a><span data-ttu-id="48612-103">Planejamento intercompanhia</span><span class="sxs-lookup"><span data-stu-id="48612-103">Intercompany planning</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="48612-104">Para algumas organizações, as operações de logística dependem de outras entidades legais (empresas) na organização.</span><span class="sxs-lookup"><span data-stu-id="48612-104">For some organizations, logistics operations depend on other legal entities (companies) in the organization.</span></span> <span data-ttu-id="48612-105">Essas operações são tratadas com o uso de vendas e compras intercompanhia, pois cada entidade legal tem um plano de contas separado.</span><span class="sxs-lookup"><span data-stu-id="48612-105">These operations are handled by using intercompany sales and purchases, because each legal entity has a separate chart of accounts.</span></span>

<span data-ttu-id="48612-106">Este tópico descreve o planejamento intercompanhia e explica como configurar o planejamento intercompanhia com a Otimização de Planejamento no Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="48612-106">This topic describes intercompany planning and explains how to configure intercompany planning with Planning Optimization in Microsoft Dynamics 365 Supply Chain Management.</span></span>

<span data-ttu-id="48612-107">Este tópico usa os seguintes termos importantes intercompanhia:</span><span class="sxs-lookup"><span data-stu-id="48612-107">This topic uses the following important intercompany terms:</span></span>

- <span data-ttu-id="48612-108">**Upstream** – uma referência relativa em uma empresa ou cadeia de fornecimento.</span><span class="sxs-lookup"><span data-stu-id="48612-108">**Upstream** – A relative reference in a firm or supply chain.</span></span> <span data-ttu-id="48612-109">Ele indica movimento na direção do fornecedor de matérias-primas.</span><span class="sxs-lookup"><span data-stu-id="48612-109">It indicates movement in the direction of the raw material supplier.</span></span>
- <span data-ttu-id="48612-110">**Downstream** – uma referência relativa em uma empresa ou cadeia de fornecimento.</span><span class="sxs-lookup"><span data-stu-id="48612-110">**Downstream** – A relative reference in a firm or supply chain.</span></span> <span data-ttu-id="48612-111">Ele indica movimento na direção do cliente.</span><span class="sxs-lookup"><span data-stu-id="48612-111">It indicates movement in the direction of the customer.</span></span>
- <span data-ttu-id="48612-112">**Demanda intercompanhia planejada** – demanda planejada para um produto de uma empresa, com base na demanda planejada para o produto de uma empresa downstream.</span><span class="sxs-lookup"><span data-stu-id="48612-112">**Planned intercompany demand** – Planned demand for a product in a company, based on planned demand for the product from a downstream company.</span></span>

<span data-ttu-id="48612-113">No planejamento mestre, um plano em uma empresa pode incluir a demanda intercompanhia planejada relacionada às ordens planejadas de um plano em outra empresa.</span><span class="sxs-lookup"><span data-stu-id="48612-113">In master planning, a plan in one company can include planned intercompany demand that is related to planned orders from a plan in another company.</span></span> <span data-ttu-id="48612-114">Esse recurso é útil, pois oferece visibilidade total das ordens planejadas entre as empresas.</span><span class="sxs-lookup"><span data-stu-id="48612-114">This capability is useful, because it provides full visibility into planned orders across companies.</span></span> <span data-ttu-id="48612-115">Ele também garante que todas as ordens de fornecimento planejadas necessárias sejam criadas, mas sem exigir que as ordens planejadas sejam confirmadas para a demanda intercompanhia.</span><span class="sxs-lookup"><span data-stu-id="48612-115">It also ensures that all required planned supply orders are created, but without requiring that planned orders be firmed for the intercompany demand.</span></span>

<span data-ttu-id="48612-116">Se você executar o planejamento mestre a partir de um plano mestre que inclui a demanda downstream planejada, as ordens de compra planejadas dos fornecedores intercompanhia relacionadas serão incluídas no plano como demanda.</span><span class="sxs-lookup"><span data-stu-id="48612-116">If you run master planning from a master plan that includes planned downstream demand, planned purchase orders from the related intercompany vendors will be included in the plan as demand.</span></span>

## <a name="required-setup"></a><span data-ttu-id="48612-117">Configuração necessária</span><span class="sxs-lookup"><span data-stu-id="48612-117">Required setup</span></span>

<span data-ttu-id="48612-118">Para usar o planejamento intercompanhia, você deve preparar o sistema da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="48612-118">To use intercompany planning, you must prepare your system in the following way:</span></span>

1. <span data-ttu-id="48612-119">Os produtos relevantes devem ser liberados em todas as empresas relevantes.</span><span class="sxs-lookup"><span data-stu-id="48612-119">The relevant products must be released in all the relevant companies.</span></span> <span data-ttu-id="48612-120">Para obter mais informações, consulte [Configurar e usar comércio intercompanhia no Dynamics 365 Supply Chain Management](https://docs.microsoft.com/learn/modules/configure-use-intercompany-trade-dyn365-supply-chain-mgmt/) no Microsoft Learn.</span><span class="sxs-lookup"><span data-stu-id="48612-120">For more information, see [Configure and use intercompany trade in Dynamics 365 Supply Chain Management ](https://docs.microsoft.com/learn/modules/configure-use-intercompany-trade-dyn365-supply-chain-mgmt/) on Microsoft Learn.</span></span>
1. <span data-ttu-id="48612-121">A demanda downstream deve ser coberta pelas compras de um fornecedor que tenha uma relação intercompanhia para a empresa de upstream e as dimensões de estoque padrão relevantes (site e depósito) no cliente.</span><span class="sxs-lookup"><span data-stu-id="48612-121">Downstream demand must be covered by purchases from a vendor that has an intercompany relation to the upstream company and relevant default inventory dimensions (site and warehouse) on the customer.</span></span> <span data-ttu-id="48612-122">Para obter mais informações, consulte [Configurar e usar comércio intercompanhia no Dynamics 365 Supply Chain Management](https://docs.microsoft.com/learn/modules/configure-use-intercompany-trade-dyn365-supply-chain-mgmt/) no Microsoft Learn.</span><span class="sxs-lookup"><span data-stu-id="48612-122">For more information, see [Configure and use intercompany trade in Dynamics 365 Supply Chain Management ](https://docs.microsoft.com/learn/modules/configure-use-intercompany-trade-dyn365-supply-chain-mgmt/) on Microsoft Learn.</span></span>
1. <span data-ttu-id="48612-123">O plano mestre na empresa de upstream deve incluir a demanda de downstream planejada; a empresa e o plano mestre relevantes devem ser especificados nos planos downstream.</span><span class="sxs-lookup"><span data-stu-id="48612-123">The master plan in the upstream company must include planned downstream demand, and the relevant company and master plan must be specified in the downstream plans.</span></span>

## <a name="include-planned-downstream-demand"></a><span data-ttu-id="48612-124">Incluir a demanda downstream planejada</span><span class="sxs-lookup"><span data-stu-id="48612-124">Include planned downstream demand</span></span>

<span data-ttu-id="48612-125">Siga estas etapas para configurar seu plano mestre de forma que inclua a demanda downstream planejada.</span><span class="sxs-lookup"><span data-stu-id="48612-125">Follow these steps to configure your master plan so that it includes planned downstream demand.</span></span>

1. <span data-ttu-id="48612-126">Vá para **Planejamento mestre \> Configuração \> Planos \> Planos mestres**.</span><span class="sxs-lookup"><span data-stu-id="48612-126">Go to **Master planning \> Setup \> Plans \> Master plans**.</span></span>
1. <span data-ttu-id="48612-127">Selecione ou crie um plano mestre.</span><span class="sxs-lookup"><span data-stu-id="48612-127">Select or create a master plan.</span></span>
1. <span data-ttu-id="48612-128">Na FastTab **Planejamento intercompanhia**, defina os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="48612-128">On the **Intercompany planning** FastTab, set the following fields:</span></span>

    - <span data-ttu-id="48612-129">**Incluir a demanda downstream planejada** – defina esta opção como *Sim* para habilitar o planejamento intercompanhia para o plano mestre.</span><span class="sxs-lookup"><span data-stu-id="48612-129">**Include planned downstream demand** – Set this option to *Yes* to enable intercompany planning for the master plan.</span></span>
    - <span data-ttu-id="48612-130">**Planos downstream** – se você definir a opção **Incluir demanda downstream planejada** como *Sim*, use a barra de ferramentas e a grade para adicionar os planos mestre desejados de outras empresas.</span><span class="sxs-lookup"><span data-stu-id="48612-130">**Downstream plans** – If you set the **Include planned downstream demand** option to *Yes*, use the toolbar and grid to add the desired master plans from other companies.</span></span>

## <a name="peg-across-companies-by-using-multilevel-pegging"></a><span data-ttu-id="48612-131">Vincular entre empresas usando vinculação de vários níveis</span><span class="sxs-lookup"><span data-stu-id="48612-131">Peg across companies by using multilevel pegging</span></span>

<span data-ttu-id="48612-132">Na vinculação de vários níveis, você pode exibir a vinculação entre empresas para ver a fonte inicial de demanda que está sendo coberta por um fornecimento.</span><span class="sxs-lookup"><span data-stu-id="48612-132">In multilevel pegging, you can view pegging across companies to see the initial source of demand that is being covered by a supply.</span></span>

<span data-ttu-id="48612-133">Para exibir informações de vinculação de vários níveis, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="48612-133">To view multilevel pegging information, follow these steps.</span></span>

1. <span data-ttu-id="48612-134">Vá para **Planejamento mestre \> Planejamento mestre \> Ordens planejadas**.</span><span class="sxs-lookup"><span data-stu-id="48612-134">Go to **Master planning \> Master planning \> Planned orders**.</span></span>
1. <span data-ttu-id="48612-135">Selecione ou abra uma ordem planejada.</span><span class="sxs-lookup"><span data-stu-id="48612-135">Select or open a planned order.</span></span>
1. <span data-ttu-id="48612-136">No Painel de Ações, na guia **Exibir**, no grupo **Requisitos**, selecione **Vinculação de vários níveis**.</span><span class="sxs-lookup"><span data-stu-id="48612-136">On the Action Pane, on the **View** tab, in the **Requirements** group, select **Multilevel pegging**.</span></span>

### <a name="intercompany-example-that-involves-two-companies"></a><span data-ttu-id="48612-137">Exemplo de intercompanhia que envolve duas empresas</span><span class="sxs-lookup"><span data-stu-id="48612-137">Intercompany example that involves two companies</span></span>

<span data-ttu-id="48612-138">Neste exemplo, uma ordem de produção planejada é criada na empresa USMF para cobrir uma ordem de venda na empresa DEMF.</span><span class="sxs-lookup"><span data-stu-id="48612-138">For this example, a planned production order is created in the USMF company to cover a sales order in the DEMF company.</span></span> <span data-ttu-id="48612-139">No USMF, a demanda direta é a demanda intercompanhia planejada.</span><span class="sxs-lookup"><span data-stu-id="48612-139">In USMF, the direct demand is planned intercompany demand.</span></span> <span data-ttu-id="48612-140">Para fazer com que essa demanda apareça no USMF, o planejamento mestre é executado primeiro no DEMF e, depois, no USMF.</span><span class="sxs-lookup"><span data-stu-id="48612-140">To make this demand appear in USMF, master planning is run first in DEMF and then in USMF.</span></span>

<span data-ttu-id="48612-141">A ilustração a seguir mostra como esse exemplo pode aparecer na página **Vinculação de vários níveis** para a ordem de produção planejada.</span><span class="sxs-lookup"><span data-stu-id="48612-141">The following illustration shows how this example might appear on the **Multilevel pegging** page for the planned production order.</span></span>

![Exemplo de intercompanhia que envolve duas empresas](media/IntercompanyPlanning1.png)

### <a name="intercompany-example-that-involves-three-companies"></a><span data-ttu-id="48612-143">Exemplo de intercompanhia que envolve três empresas</span><span class="sxs-lookup"><span data-stu-id="48612-143">Intercompany example that involves three companies</span></span>

<span data-ttu-id="48612-144">Neste exemplo, uma ordem de compra planejada é criada na empresa USMF para cobrir uma ordem de venda na empresa FRRT.</span><span class="sxs-lookup"><span data-stu-id="48612-144">For this example, a planned purchase order is created in the USMF company to cover a sales order in the FRRT company.</span></span> <span data-ttu-id="48612-145">Nas empresas DEMF e USMF, a demanda direta é a demanda intercompanhia planejada.</span><span class="sxs-lookup"><span data-stu-id="48612-145">In the DEMF and USMF companies, the direct demand is planned intercompany demand.</span></span> <span data-ttu-id="48612-146">Para fazer com que essa demanda apareça no USMF, o planejamento mestre é executado primeiro no FRRT, depois no DEMF e, finalmente, no USMF.</span><span class="sxs-lookup"><span data-stu-id="48612-146">To make this demand appear in USMF, master planning is run first in FRRT, then in DEMF, and finally in USMF.</span></span>

<span data-ttu-id="48612-147">A ilustração a seguir mostra como esse exemplo pode aparecer na página **Vinculação de vários níveis** para a ordem de produção planejada.</span><span class="sxs-lookup"><span data-stu-id="48612-147">The following illustration shows how this example might appear on the **Multilevel pegging** page for the planned production order.</span></span>

![Exemplo de intercompanhia que envolve três empresas](media/IntercompanyPlanning2.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]