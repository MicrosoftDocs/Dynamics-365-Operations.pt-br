---
title: Sincronizar com o mecanismo de preços sob demanda do Dynamics 365 Supply Chain Management
description: Este tópico descreve como usar o mecanismo de preços no Microsoft Dynamics 365 Supply Chain Management do Dynamics 365 Sales.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 03/10/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-10
ms.openlocfilehash: ef4465144155130087b078f9f96911df38b62c41
ms.sourcegitcommit: 68f1485de7d64a6c9eba1088af63bd07992d972d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2020
ms.locfileid: "3173168"
---
# <a name="sync-with-the-dynamics-365-supply-chain-management-pricing-engine-on-demand"></a><span data-ttu-id="3fb8d-103">Sincronizar com o mecanismo de preços sob demanda do Dynamics 365 Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="3fb8d-103">Sync with the Dynamics 365 Supply Chain Management pricing engine on demand</span></span>

[!include [banner](../../includes/banner.md)]



<span data-ttu-id="3fb8d-104">O Microsoft Dynamics 365 Supply Chain Management inclui um mecanismo de preços que lida com acordos comerciais, listas de preços, programas de fidelidade do cliente, promoções e descontos.</span><span class="sxs-lookup"><span data-stu-id="3fb8d-104">Microsoft Dynamics 365 Supply Chain Management includes a pricing engine that handles trade agreements, price lists, customer loyalty programs, promotions, and discounts.</span></span> <span data-ttu-id="3fb8d-105">O mecanismo de preços usa regras complexas para determinar o melhor preço para uma determinada cotação ou ordem.</span><span class="sxs-lookup"><span data-stu-id="3fb8d-105">The pricing engine uses complex rules to determine the best price for a given quotation or order.</span></span> <span data-ttu-id="3fb8d-106">Ao usar a gravação dupla, você usa os preços estáticos ou o mecanismo de preços do Dynamics 365 Supply Chain Management nas páginas Cotação e Ordem no Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="3fb8d-106">When you use dual-write, you use either static pricing or the pricing engine from Dynamics 365 Supply Chain Management on the Quote and Order pages in Dynamics 365 Sales.</span></span>

## <a name="use-the-pricing-engine-from-supply-chain-management-in-sales"></a><span data-ttu-id="3fb8d-107">Usar o mecanismo de preços do Supply Chain Management no Sales</span><span class="sxs-lookup"><span data-stu-id="3fb8d-107">Use the pricing engine from Supply Chain Management in Sales</span></span>

1. <span data-ttu-id="3fb8d-108">No Sales, acesse **Vendas \> Ordens**.</span><span class="sxs-lookup"><span data-stu-id="3fb8d-108">In Sales, go to **Sales \> Orders**.</span></span>
2. <span data-ttu-id="3fb8d-109">Selecione **Novo** para criar uma ordem ou selecione uma ordem existente na lista **Minhas ordens**.</span><span class="sxs-lookup"><span data-stu-id="3fb8d-109">Select **New** to create a new order, or select an existing order in the **My Orders** list.</span></span>
3. <span data-ttu-id="3fb8d-110">Adicione uma nova linha de ordem.</span><span class="sxs-lookup"><span data-stu-id="3fb8d-110">Add a new order line.</span></span>
4. <span data-ttu-id="3fb8d-111">Se você estiver criando uma ordem, selecione **Ordem de preço** no Painel de Ação.</span><span class="sxs-lookup"><span data-stu-id="3fb8d-111">If you're creating a new order, select **Price Order** on the Action Pane.</span></span> <span data-ttu-id="3fb8d-112">Se você estiver atualizando uma ordem existente, selecione **Recalcular** no Painel de Ação.</span><span class="sxs-lookup"><span data-stu-id="3fb8d-112">If you're updating an existing order, select **Recalculate** on the Action Pane.</span></span>

    <span data-ttu-id="3fb8d-113">Os seguintes campos são preenchidos automaticamente:</span><span class="sxs-lookup"><span data-stu-id="3fb8d-113">The following fields are automatically filled in:</span></span>

    + <span data-ttu-id="3fb8d-114">Valor Detalhado</span><span class="sxs-lookup"><span data-stu-id="3fb8d-114">Detail Amount</span></span>
    + <span data-ttu-id="3fb8d-115">% de desconto</span><span class="sxs-lookup"><span data-stu-id="3fb8d-115">Discount %</span></span>
    + <span data-ttu-id="3fb8d-116">Desconto</span><span class="sxs-lookup"><span data-stu-id="3fb8d-116">Discount</span></span>
    + <span data-ttu-id="3fb8d-117">Valor sem Frete</span><span class="sxs-lookup"><span data-stu-id="3fb8d-117">Pre-Freight Amount</span></span>
    + <span data-ttu-id="3fb8d-118">Valor do Frete</span><span class="sxs-lookup"><span data-stu-id="3fb8d-118">Freight Amount</span></span>
    + <span data-ttu-id="3fb8d-119">Total de Impostos</span><span class="sxs-lookup"><span data-stu-id="3fb8d-119">Total Tax</span></span>
    + <span data-ttu-id="3fb8d-120">Valor total do CF -e-SAT</span><span class="sxs-lookup"><span data-stu-id="3fb8d-120">Total Amount</span></span>

## <a name="how-it-works"></a><span data-ttu-id="3fb8d-121">Como funciona</span><span class="sxs-lookup"><span data-stu-id="3fb8d-121">How it works</span></span>

<span data-ttu-id="3fb8d-122">Ao selecionar **Ordem de preço** no Sales, a função **Totais** na guia **Ordem de venda \> Exibir** no Supply Chain Management é chamada para a ordem de venda associada.</span><span class="sxs-lookup"><span data-stu-id="3fb8d-122">When you select **Price Order** in Sales, the **Totals** function on the **Sales Order \> View** tab in Supply Chain Management is called for the associated sales order.</span></span> <span data-ttu-id="3fb8d-123">Os valores no total da ordens no Sales são usados para preencher os campos correspondentes no Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="3fb8d-123">The values in the order total in Sales are used to fill in the corresponding fields in Supply Chain Management.</span></span>

<span data-ttu-id="3fb8d-124">Quando o total das ordens do cliente é calculado no Supply Chain Management, o cálculo avalia os acordos comerciais e contratos de vendas existentes para o cliente e os produtos listados na ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="3fb8d-124">When the sales order total is calculated in Supply Chain Management, the calculation evaluates the existing trade agreements and sales agreements for the customer and the products that are listed in the sales order.</span></span> <span data-ttu-id="3fb8d-125">Essas informações são usadas para calcular os totais.</span><span class="sxs-lookup"><span data-stu-id="3fb8d-125">This information is used to calculate the totals.</span></span> <span data-ttu-id="3fb8d-126">Quando a **Ordem de preço** é selecionada, o Sales reflete automaticamente toda a configuração que foi feita no Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="3fb8d-126">When **Price Order** is selected, Sales automatically reflects all the setup that has been done in Supply Chain Management.</span></span>

## <a name="limitations"></a><span data-ttu-id="3fb8d-127">Limitações</span><span class="sxs-lookup"><span data-stu-id="3fb8d-127">Limitations</span></span>

<span data-ttu-id="3fb8d-128">Quando os campos no Sales são preenchidos, as seguintes limitações se aplicam:</span><span class="sxs-lookup"><span data-stu-id="3fb8d-128">When the fields in Sales are filled in, the following limitations apply:</span></span>

+ <span data-ttu-id="3fb8d-129">A configuração de encargos e alocações de encargos no Supply Chain Management não é replicada no Sales.</span><span class="sxs-lookup"><span data-stu-id="3fb8d-129">The setup of charges and charge allocations in Supply Chain Management isn't replicated in Sales.</span></span>
+ <span data-ttu-id="3fb8d-130">Os preços não consideram os preços especiais de varejo especificados no campo **Canal de Varejo** na página da linha da ordem do cliente no Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="3fb8d-130">Pricing doesn't consider special retail pricing that is specified in the **Retail Channel** field on the sales order line page in Supply Chain Management.</span></span>
+ <span data-ttu-id="3fb8d-131">Os descontos definidos na seção **Gerenciamento de bonificação comercial** do Supply Chain Management não são considerados.</span><span class="sxs-lookup"><span data-stu-id="3fb8d-131">Discounts that are defined in the **Trade Allowance Management** section of Supply Chain Management aren't considered.</span></span>
