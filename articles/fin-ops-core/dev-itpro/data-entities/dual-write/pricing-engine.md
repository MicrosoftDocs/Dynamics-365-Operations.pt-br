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
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-10
ms.openlocfilehash: 740ae20704abd9c59f64c2c7622fa96d65dccb1d
ms.sourcegitcommit: 0a741b131ed71f6345d4219a47cf5f71fec6744b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "3997137"
---
# <a name="sync-with-the-dynamics-365-supply-chain-management-pricing-engine-on-demand"></a><span data-ttu-id="822ac-103">Sincronizar com o mecanismo de preços sob demanda do Dynamics 365 Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="822ac-103">Sync with the Dynamics 365 Supply Chain Management pricing engine on demand</span></span>

[!include [banner](../../includes/banner.md)]



<span data-ttu-id="822ac-104">O Microsoft Dynamics 365 Supply Chain Management inclui um mecanismo de preços que lida com acordos comerciais, listas de preços, programas de fidelidade do cliente, promoções e descontos.</span><span class="sxs-lookup"><span data-stu-id="822ac-104">Microsoft Dynamics 365 Supply Chain Management includes a pricing engine that handles trade agreements, price lists, customer loyalty programs, promotions, and discounts.</span></span> <span data-ttu-id="822ac-105">O mecanismo de preços usa regras complexas para determinar o melhor preço para uma determinada cotação ou ordem.</span><span class="sxs-lookup"><span data-stu-id="822ac-105">The pricing engine uses complex rules to determine the best price for a given quotation or order.</span></span> <span data-ttu-id="822ac-106">Ao usar a gravação dupla, você usa os preços estáticos ou o mecanismo de preços do Dynamics 365 Supply Chain Management nas páginas Cotação e Ordem no Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="822ac-106">When you use dual-write, you use either static pricing or the pricing engine from Dynamics 365 Supply Chain Management on the Quote and Order pages in Dynamics 365 Sales.</span></span>

## <a name="use-the-pricing-engine-from-supply-chain-management-in-sales"></a><span data-ttu-id="822ac-107">Usar o mecanismo de preços do Supply Chain Management no Sales</span><span class="sxs-lookup"><span data-stu-id="822ac-107">Use the pricing engine from Supply Chain Management in Sales</span></span>

1. <span data-ttu-id="822ac-108">No Sales, acesse **Vendas \> Ordens**.</span><span class="sxs-lookup"><span data-stu-id="822ac-108">In Sales, go to **Sales \> Orders**.</span></span>
2. <span data-ttu-id="822ac-109">Selecione **Novo** para criar uma ordem ou selecione uma ordem existente na lista **Minhas ordens**.</span><span class="sxs-lookup"><span data-stu-id="822ac-109">Select **New** to create a new order, or select an existing order in the **My Orders** list.</span></span>
3. <span data-ttu-id="822ac-110">Adicione uma nova linha de ordem.</span><span class="sxs-lookup"><span data-stu-id="822ac-110">Add a new order line.</span></span>
4. <span data-ttu-id="822ac-111">Se você estiver criando uma ordem, selecione **Ordem de preço** no Painel de Ação.</span><span class="sxs-lookup"><span data-stu-id="822ac-111">If you're creating a new order, select **Price Order** on the Action Pane.</span></span> <span data-ttu-id="822ac-112">Se você estiver atualizando uma ordem existente, selecione **Recalcular** no Painel de Ação.</span><span class="sxs-lookup"><span data-stu-id="822ac-112">If you're updating an existing order, select **Recalculate** on the Action Pane.</span></span>

    <span data-ttu-id="822ac-113">Os seguintes campos são preenchidos automaticamente:</span><span class="sxs-lookup"><span data-stu-id="822ac-113">The following fields are automatically filled in:</span></span>

    + <span data-ttu-id="822ac-114">Valor Detalhado</span><span class="sxs-lookup"><span data-stu-id="822ac-114">Detail Amount</span></span>
    + <span data-ttu-id="822ac-115">% de desconto</span><span class="sxs-lookup"><span data-stu-id="822ac-115">Discount %</span></span>
    + <span data-ttu-id="822ac-116">Desconto</span><span class="sxs-lookup"><span data-stu-id="822ac-116">Discount</span></span>
    + <span data-ttu-id="822ac-117">Valor sem Frete</span><span class="sxs-lookup"><span data-stu-id="822ac-117">Pre-Freight Amount</span></span>
    + <span data-ttu-id="822ac-118">Valor do Frete</span><span class="sxs-lookup"><span data-stu-id="822ac-118">Freight Amount</span></span>
    + <span data-ttu-id="822ac-119">Total de Impostos</span><span class="sxs-lookup"><span data-stu-id="822ac-119">Total Tax</span></span>
    + <span data-ttu-id="822ac-120">Valor total do CF -e-SAT</span><span class="sxs-lookup"><span data-stu-id="822ac-120">Total Amount</span></span>
    
5. <span data-ttu-id="822ac-121">Para garantir que o sistema considera os contratos comerciais e de venda para calcular o preço:</span><span class="sxs-lookup"><span data-stu-id="822ac-121">To ensure that the system considers trade and sales agreements to calculate the price:</span></span>
    1. <span data-ttu-id="822ac-122">Navegue até o ambiente Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="822ac-122">Navigate to your Supply Chain Management environment.</span></span>
    2. <span data-ttu-id="822ac-123">Navegue até **Contas a receber \> Configuração \> Parâmetros de contas a receber**.</span><span class="sxs-lookup"><span data-stu-id="822ac-123">Navigate to **Accounts receivable \> Setup \> Accounts receivable parameters**.</span></span>
    3. <span data-ttu-id="822ac-124">Selecione a guia **Preços** na barra de navegação lateral.</span><span class="sxs-lookup"><span data-stu-id="822ac-124">Select the **Prices** tab in the side navigation bar.</span></span>
    4. <span data-ttu-id="822ac-125">Na Guia Rápida **Avaliação de contrato comercial** , desmarque a opção **Entrada manual**.</span><span class="sxs-lookup"><span data-stu-id="822ac-125">Under the **Trade agreement evaluation** fastab, uncheck the **Manual entry** option.</span></span>

## <a name="how-it-works"></a><span data-ttu-id="822ac-126">Como funciona</span><span class="sxs-lookup"><span data-stu-id="822ac-126">How it works</span></span>

<span data-ttu-id="822ac-127">Ao selecionar **Ordem de preço** no Sales, a função **Totais** na guia **Ordem de venda \> Exibir** no Supply Chain Management é chamada para a ordem de venda associada.</span><span class="sxs-lookup"><span data-stu-id="822ac-127">When you select **Price Order** in Sales, the **Totals** function on the **Sales Order \> View** tab in Supply Chain Management is called for the associated sales order.</span></span> <span data-ttu-id="822ac-128">Os valores no total da ordens no Sales são usados para preencher os campos correspondentes no Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="822ac-128">The values in the order total in Sales are used to fill in the corresponding fields in Supply Chain Management.</span></span>

<span data-ttu-id="822ac-129">Quando o total das ordens do cliente é calculado no Supply Chain Management, o cálculo avalia os acordos comerciais e contratos de vendas existentes para o cliente e os produtos listados na ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="822ac-129">When the sales order total is calculated in Supply Chain Management, the calculation evaluates the existing trade agreements and sales agreements for the customer and the products that are listed in the sales order.</span></span> <span data-ttu-id="822ac-130">Essas informações são usadas para calcular os totais.</span><span class="sxs-lookup"><span data-stu-id="822ac-130">This information is used to calculate the totals.</span></span> <span data-ttu-id="822ac-131">Quando a **Ordem de preço** é selecionada, o Sales reflete automaticamente toda a configuração que foi feita no Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="822ac-131">When **Price Order** is selected, Sales automatically reflects all the setup that has been done in Supply Chain Management.</span></span>

## <a name="limitations"></a><span data-ttu-id="822ac-132">Limitações</span><span class="sxs-lookup"><span data-stu-id="822ac-132">Limitations</span></span>

<span data-ttu-id="822ac-133">Quando os campos no Sales são preenchidos, as seguintes limitações se aplicam:</span><span class="sxs-lookup"><span data-stu-id="822ac-133">When the fields in Sales are filled in, the following limitations apply:</span></span>

+ <span data-ttu-id="822ac-134">A configuração de encargos e alocações de encargos no Supply Chain Management não é replicada no Sales.</span><span class="sxs-lookup"><span data-stu-id="822ac-134">The setup of charges and charge allocations in Supply Chain Management isn't replicated in Sales.</span></span>
+ <span data-ttu-id="822ac-135">Os preços não consideram os preços especiais de varejo especificados no campo **Canal de Varejo** na página da linha da ordem do cliente no Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="822ac-135">Pricing doesn't consider special retail pricing that is specified in the **Retail Channel** field on the sales order line page in Supply Chain Management.</span></span>
+ <span data-ttu-id="822ac-136">Os descontos definidos na seção **Gerenciamento de bonificação comercial** do Supply Chain Management não são considerados.</span><span class="sxs-lookup"><span data-stu-id="822ac-136">Discounts that are defined in the **Trade Allowance Management** section of Supply Chain Management aren't considered.</span></span>
