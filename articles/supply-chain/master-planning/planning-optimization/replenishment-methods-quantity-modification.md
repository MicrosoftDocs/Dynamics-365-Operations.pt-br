---
title: Métodos de reabastecimento e modificação de quantidade
description: Este tópico fornece informações sobre os métodos de reabastecimento na Otimização de Planejamento. Também explica como a quantidade múltipla de ordens de um produto afeta o resultado.
author: crytt
ms.date: 6/1/2021
ms.topic: article
ms.search.form: ReqGroup, ReqItemTable, InventItemOrderSetup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-06-01
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d5e0e671e624de2646a47647ef08d3567599b884
ms.sourcegitcommit: 4cbd83e21a78459e4711a2dedba0f5a7acc3c841
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/15/2021
ms.locfileid: "6261687"
---
# <a name="replenishment-methods-and-quantity-modification"></a><span data-ttu-id="fc02a-104">Métodos de reabastecimento e modificação de quantidade</span><span class="sxs-lookup"><span data-stu-id="fc02a-104">Replenishment methods and quantity modification</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="fc02a-105">Este tópico fornece informações sobre os métodos de reabastecimento na Otimização de Planejamento.</span><span class="sxs-lookup"><span data-stu-id="fc02a-105">This topic provides information about replenishment methods in Planning Optimization.</span></span> <span data-ttu-id="fc02a-106">Também explica como a quantidade múltipla de ordens de um produto afeta o resultado.</span><span class="sxs-lookup"><span data-stu-id="fc02a-106">It also explains how the multiple order quantity for a product affects the result.</span></span>

<span data-ttu-id="fc02a-107">Os métodos de reabastecimento também são conhecidos como métodos de cobertura e métodos de dimensionamento de lotes.</span><span class="sxs-lookup"><span data-stu-id="fc02a-107">Replenishment methods are also known as coverage methods and lot-sizing methods.</span></span>

## <a name="coverage-codes"></a><span data-ttu-id="fc02a-108">Códigos de cobertura</span><span class="sxs-lookup"><span data-stu-id="fc02a-108">Coverage codes</span></span>

<span data-ttu-id="fc02a-109">A Otimização de Planejamento pode ser configurada para usar diversos métodos de reabastecimento.</span><span class="sxs-lookup"><span data-stu-id="fc02a-109">Planning Optimization can be configured to use different replenishment methods.</span></span> <span data-ttu-id="fc02a-110">Os métodos de reabastecimento são as técnicas que o sistema usa para calcular os requisitos de um produto.</span><span class="sxs-lookup"><span data-stu-id="fc02a-110">The replenishment methods are the techniques that the system uses to calculate requirements for a product.</span></span> <span data-ttu-id="fc02a-111">Os métodos de reabastecimento são definidos por códigos de cobertura que você pode configurar no grupo de cobertura ou no produto.</span><span class="sxs-lookup"><span data-stu-id="fc02a-111">Replenishment methods are defined by coverage codes that you can set up on either the coverage group or the product.</span></span>

<span data-ttu-id="fc02a-112">Os seguintes códigos de cobertura podem ser usados na Otimização de Planejamento:</span><span class="sxs-lookup"><span data-stu-id="fc02a-112">The following coverage codes can be used in Planning Optimization:</span></span>

- <span data-ttu-id="fc02a-113">**Período** - O método de reabastecimento combina toda a demanda de um período em uma ordem para o produto.</span><span class="sxs-lookup"><span data-stu-id="fc02a-113">**Period** – The replenishment method combines all the demand for a period into one order for the product.</span></span> <span data-ttu-id="fc02a-114">A ordem será planejada para o primeiro dia do período e sua quantidade preencherá as requisições líquidas durante o período estabelecido.</span><span class="sxs-lookup"><span data-stu-id="fc02a-114">The order will be planned for the first day of the period, and its quantity will fulfill the net requirements during the established period.</span></span> <span data-ttu-id="fc02a-115">O período começa com a primeira a demanda do produto e abrange o tempo definido.</span><span class="sxs-lookup"><span data-stu-id="fc02a-115">The period starts with the first demand of the product and covers the defined length of time.</span></span> <span data-ttu-id="fc02a-116">O período seguinte começará com as requisições seguintes do produto.</span><span class="sxs-lookup"><span data-stu-id="fc02a-116">The next period will start with the next requirements of the product.</span></span> <span data-ttu-id="fc02a-117">O código de cobertura *Período* é usado frequentemente para emissão de inventário não previsível, produtos sazonais ou produtos de alto custo.</span><span class="sxs-lookup"><span data-stu-id="fc02a-117">The *Period* coverage code is often used for non-predictable inventory draw, season-influenced products, or high-cost products.</span></span> <span data-ttu-id="fc02a-118">A ilustração a seguir mostra um exemplo.</span><span class="sxs-lookup"><span data-stu-id="fc02a-118">The following illustration shows an example.</span></span>

    <span data-ttu-id="fc02a-119">![Exemplo de uso do Código de cobertura de período](./media/coverage-code-period.png "Exemplo de uso do Código de cobertura de período")</span><span class="sxs-lookup"><span data-stu-id="fc02a-119">![Example of Period coverage code use](./media/coverage-code-period.png "Example of Period coverage code use")</span></span>

- <span data-ttu-id="fc02a-120">**Requisito** - No método de reabastecimento, o sistema cria uma ordem de compra, transferência ou produção planejada por requisição do produto.</span><span class="sxs-lookup"><span data-stu-id="fc02a-120">**Requirement** – In the replenishment method, the system creates a planned purchase, transfer, or production order per requirement for the product.</span></span> <span data-ttu-id="fc02a-121">Este método é usado para produtos caros que têm demanda intermitente.</span><span class="sxs-lookup"><span data-stu-id="fc02a-121">This method is used for expensive products that have intermittent demand.</span></span> <span data-ttu-id="fc02a-122">O código de cobertura *Requisito* é usado frequentemente para produtos configuráveis ou cenários de produção por ordem.</span><span class="sxs-lookup"><span data-stu-id="fc02a-122">The *Requirement* coverage code is often used for configurable products or make-to-order scenarios.</span></span> <span data-ttu-id="fc02a-123">A ilustração a seguir mostra um exemplo.</span><span class="sxs-lookup"><span data-stu-id="fc02a-123">The following illustration shows an example.</span></span>

    <span data-ttu-id="fc02a-124">![Exemplo de uso do Código de cobertura de requisito](./media/coverage-code-requirement.png "Exemplo de uso do Código de cobertura de requisito")</span><span class="sxs-lookup"><span data-stu-id="fc02a-124">![Example of Requirement coverage code use](./media/coverage-code-requirement.png "Example of Requirement coverage code use")</span></span>

- <span data-ttu-id="fc02a-125">**Mín./Máx.**</span><span class="sxs-lookup"><span data-stu-id="fc02a-125">**Min./Max.**</span></span> <span data-ttu-id="fc02a-126">– O método de reabastecimento baseia-se no nível de inventário.</span><span class="sxs-lookup"><span data-stu-id="fc02a-126">– The replenishment method is based on the inventory level.</span></span> <span data-ttu-id="fc02a-127">Ele define o reabastecimento do inventário até um nível específico quando o nível previsto disponível estiver abaixo de um limite específico.</span><span class="sxs-lookup"><span data-stu-id="fc02a-127">It defines the replenishment of inventory up to a specific level when the predicted on-hand level is below a specific threshold.</span></span> <span data-ttu-id="fc02a-128">A quantidade do reabastecimento será a diferença entre o nível máximo e o nível disponível previsto.</span><span class="sxs-lookup"><span data-stu-id="fc02a-128">The replenishment quantity will be the difference between the maximum level and the predicted on-hand level.</span></span> <span data-ttu-id="fc02a-129">O código de cobertura *Mín./Máx.*</span><span class="sxs-lookup"><span data-stu-id="fc02a-129">The *Min./Max.*</span></span> <span data-ttu-id="fc02a-130">é frequentemente usado para sorteio de inventário previsível, corredores altos ou produtos mais baratos.</span><span class="sxs-lookup"><span data-stu-id="fc02a-130">coverage code is often used for predictable inventory draw, high runners, or less expensive products.</span></span> <span data-ttu-id="fc02a-131">A ilustração a seguir mostra um exemplo.</span><span class="sxs-lookup"><span data-stu-id="fc02a-131">The following illustration shows an example.</span></span>

    <span data-ttu-id="fc02a-132">![Exemplo de uso do Código de cobertura Mín./Máx.](./media/coverage-code-min-max.png "Exemplo de uso do Código de cobertura Mín./Máx.")</span><span class="sxs-lookup"><span data-stu-id="fc02a-132">![Example of Min./Max. coverage code use](./media/coverage-code-min-max.png "Example of Min./Max. coverage code use")</span></span>

- <span data-ttu-id="fc02a-133">**Manual** - No método de reabastecimento, o sistema não sugere ordens de compra, transferência ou produção para o produto.</span><span class="sxs-lookup"><span data-stu-id="fc02a-133">**Manual** – In the replenishment method, the system doesn't suggest purchase, transfer, or production orders for the product.</span></span> <span data-ttu-id="fc02a-134">Em vez disso, o planejador do produto é responsável pela criação dos pedidos necessários para a reposição do produto.</span><span class="sxs-lookup"><span data-stu-id="fc02a-134">Instead, the planner for the product is responsible for creating the required orders for the replenishment of the product.</span></span> <span data-ttu-id="fc02a-135">O código de cobertura *Manual* é usado frequentemente para produtos para os quais as ordens planejadas geradas pelo sistema não são desejadas.</span><span class="sxs-lookup"><span data-stu-id="fc02a-135">The *Manual* coverage code is often used for products that system-generated planned orders aren't wanted for.</span></span>

## <a name="impact-of-the-order-quantity-from-default-order-settings"></a><span data-ttu-id="fc02a-136">Impacto da quantidade de pedidos das configurações padrão do pedido</span><span class="sxs-lookup"><span data-stu-id="fc02a-136">Impact of the order quantity from default order settings</span></span>

<span data-ttu-id="fc02a-137">Na página **Configuração de ordem padrão** para um produto liberado, você pode especificar cada uma das seguintes configurações de quantidade nas FastTabs **Ordem de compra**, **Inventário** e **Ordem de vendas**.</span><span class="sxs-lookup"><span data-stu-id="fc02a-137">On the **Default order setting** page for a released product, you can specify each of following quantity settings on the **Purchase order**, **Inventory**, and **Sales order** FastTabs.</span></span> <span data-ttu-id="fc02a-138">(A FastTab **Inventário** é usada tanto para ordens de transferência quanto para ordens de produção.)</span><span class="sxs-lookup"><span data-stu-id="fc02a-138">(The **Inventory** FastTab is used for both transfer orders and production orders.)</span></span>

- <span data-ttu-id="fc02a-139">**Múltiplo** – As ordens planejadas serão múltiplos dessa quantidade.</span><span class="sxs-lookup"><span data-stu-id="fc02a-139">**Multiple** – Planned orders will be a multiple of this quantity.</span></span>

    <span data-ttu-id="fc02a-140">Por exemplo, se o campo **Múltiplo** for definido como *5*, uma ordem pode ser para uma quantidade de 5, 10, 15, 20, e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="fc02a-140">For example, if the **Multiple** field is set to *5*, an order can be for a quantity of 5, 10, 15, 20, and so on.</span></span>

- <span data-ttu-id="fc02a-141">**Quantidade mínima da ordem** – As ordens planejadas não serão inferiores ao valor especificado.</span><span class="sxs-lookup"><span data-stu-id="fc02a-141">**Min. order quantity** – Planned orders won't be less than the specified value.</span></span>

    <span data-ttu-id="fc02a-142">Por exemplo, se o campo **Quantidade mínima da ordem** for definido como *10*, uma ordem planejada para uma quantidade de 10 itens será criada, mesmo que apenas quatro sejam necessários para atender à demanda.</span><span class="sxs-lookup"><span data-stu-id="fc02a-142">For example, if the **Min. order quantity** field is set to *10*, a planned order for a quantity of 10 will be created, even if only four are required to fulfill the demand.</span></span>

- <span data-ttu-id="fc02a-143">**Quantidade máxima da ordem** – As ordens planejadas não serão superiores ao valor especificado.</span><span class="sxs-lookup"><span data-stu-id="fc02a-143">**Max. order quantity** – Planned orders won't exceed the specified value.</span></span> <span data-ttu-id="fc02a-144">Se a demanda for maior do que o valor **Quantidade máx. da ordem**, ordens planejadas de múltiplo serão criadas para atender essa demanda.</span><span class="sxs-lookup"><span data-stu-id="fc02a-144">If the demand is more than the **Max. order quantity** value, multiple planned orders will be created to cover it.</span></span>

    <span data-ttu-id="fc02a-145">Por exemplo, se o campo **Quantidade máx. da ordem** for definido como *100*, e a demanda for 450, quatro ordens planejadas para uma quantidade de 100 e uma ordem planejada para a quantidade de 50 serão criadas.</span><span class="sxs-lookup"><span data-stu-id="fc02a-145">For example, if the **Max. order quantity** field is set to *100*, and the demand is 450, four planned orders for a quantity of 100 and one planned order for a quantity of 50 will be created.</span></span>

## <a name="examples-of-replenishment-that-use-the-minmax-coverage-code"></a><span data-ttu-id="fc02a-146">Exemplos de reabastecimentos que usam o código de cobertura</span><span class="sxs-lookup"><span data-stu-id="fc02a-146">Examples of replenishment that use the Min./Max.</span></span> <span data-ttu-id="fc02a-147">Mín./Máx.</span><span class="sxs-lookup"><span data-stu-id="fc02a-147">coverage code</span></span>

<span data-ttu-id="fc02a-148">Se você não especificar um valor no campo **Múltiplo** para um produto na página de **Configuração de ordem padrão** e se você estiver usando o método de reabastecimento *Mín./Máx.*,</span><span class="sxs-lookup"><span data-stu-id="fc02a-148">If you don't specify a value in the **Multiple** field for a product on the **Default order setting** page, and if you're using the *Min./Max.*</span></span> <span data-ttu-id="fc02a-149">a Otimização de Planejamento reabastecerá o inventário até um nível específico quando o nível disponível previsto estiver abaixo de um limite específico.</span><span class="sxs-lookup"><span data-stu-id="fc02a-149">replenishment method, Planning Optimization will replenish the inventory up to a specific level when the predicted on-hand level is below a specific threshold.</span></span>

<span data-ttu-id="fc02a-150">Se você definir uma quantidade múltipla para um produto, o método de reabastecimento *Mín./Máx.*</span><span class="sxs-lookup"><span data-stu-id="fc02a-150">If you define a multiple quantity for a product, the *Min./Max.*</span></span> <span data-ttu-id="fc02a-151">mudará seu comportamento e considerará o valor **Múltiplo**.</span><span class="sxs-lookup"><span data-stu-id="fc02a-151">replenishment method changes its behavior and considers the **Multiple** value.</span></span>

<span data-ttu-id="fc02a-152">Em outras palavras, a Otimização de Planejamento ainda reabastecerá o inventário até o nível máximo definido quando o nível previsto disponível for inferior ao nível mínimo definido.</span><span class="sxs-lookup"><span data-stu-id="fc02a-152">In other words, Planning Optimization will still replenish the inventory up to the defined maximum level when the predicted on-hand level is less than the defined minimum level.</span></span> <span data-ttu-id="fc02a-153">No entanto, a quantidade de reabastecimento deve ser um múltiplo do valor de **Múltiplo**.</span><span class="sxs-lookup"><span data-stu-id="fc02a-153">However, the replenishment quantity must be a multiple of the **Multiple** value.</span></span>

<span data-ttu-id="fc02a-154">Se a quantidade de reabastecimento (a diferença entre o nível máximo e o nível previsto disponível) não for um múltiplo da quantidade múltipla definida, a Otimização de Planejamento usará o primeiro valor possível que, juntamente com o nível previsto disponível, esteja abaixo do nível máximo.</span><span class="sxs-lookup"><span data-stu-id="fc02a-154">If the replenishment quantity (the difference between the maximum level and the predicted on-hand level) isn't a multiple of the defined multiple quantity, Planning Optimization uses the first possible value that, together with predicted on-hand level, will be below the maximum level.</span></span> <span data-ttu-id="fc02a-155">Se a soma for inferior ao nível mínimo, a Otimização de Planejamento utilizará o primeiro valor que, juntamente com o previsto disponível, estiver acima do nível máximo.</span><span class="sxs-lookup"><span data-stu-id="fc02a-155">If the sum is less than the minimum level, Planning Optimization uses the first value that, together with predicted on-hand, will be above the maximum level.</span></span>

<span data-ttu-id="fc02a-156">As seguintes subseções fornecem alguns exemplos que mostram como o resultado do método de reabastecimento *Mín./Máx.* é afetada pela quantidade múltipla da ordem</span><span class="sxs-lookup"><span data-stu-id="fc02a-156">The following subsections provide some examples that show how the multiple order quantity for a product affects the result of the *Min./Max.*</span></span> <span data-ttu-id="fc02a-157">para um produto.</span><span class="sxs-lookup"><span data-stu-id="fc02a-157">replenishment method.</span></span>

### <a name="example-1"></a><span data-ttu-id="fc02a-158">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="fc02a-158">Example 1</span></span>

<span data-ttu-id="fc02a-159">Um produto tem a seguinte configuração:</span><span class="sxs-lookup"><span data-stu-id="fc02a-159">A product has the following configuration:</span></span>

- <span data-ttu-id="fc02a-160">**Código de cobertura:** *Mín./Máx.*</span><span class="sxs-lookup"><span data-stu-id="fc02a-160">**Coverage code:** *Min./Max.*</span></span>
- <span data-ttu-id="fc02a-161">**Mínimo:** *15*</span><span class="sxs-lookup"><span data-stu-id="fc02a-161">**Minimum:** *15*</span></span>
- <span data-ttu-id="fc02a-162">**Máximo:** *22*</span><span class="sxs-lookup"><span data-stu-id="fc02a-162">**Maximum:** *22*</span></span>
- <span data-ttu-id="fc02a-163">**Múltiplo:** *0*</span><span class="sxs-lookup"><span data-stu-id="fc02a-163">**Multiple:** *0*</span></span>

<span data-ttu-id="fc02a-164">Há 10 itens de inventário disponível para o produto, e não há outra demanda ou oferta.</span><span class="sxs-lookup"><span data-stu-id="fc02a-164">There are 10 pieces of on-hand inventory for the product, and there is no other demand or supply.</span></span>

<span data-ttu-id="fc02a-165">Quando o planejamento mestre é executado, uma ordem planejada para 12 itens é criada para reabastecer o inventário até a quantidade máxima.</span><span class="sxs-lookup"><span data-stu-id="fc02a-165">When master planning runs, a planned order for 12 pieces is created to replenish inventory to the maximum quantity.</span></span>

### <a name="example-2"></a><span data-ttu-id="fc02a-166">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="fc02a-166">Example 2</span></span>

<span data-ttu-id="fc02a-167">Um produto tem a seguinte configuração:</span><span class="sxs-lookup"><span data-stu-id="fc02a-167">A product has the following configuration:</span></span>

- <span data-ttu-id="fc02a-168">**Código de cobertura:** *Mín./Máx.*</span><span class="sxs-lookup"><span data-stu-id="fc02a-168">**Coverage code:** *Min./Max.*</span></span>
- <span data-ttu-id="fc02a-169">**Mínimo:** *15*</span><span class="sxs-lookup"><span data-stu-id="fc02a-169">**Minimum:** *15*</span></span>
- <span data-ttu-id="fc02a-170">**Máximo:** *22*</span><span class="sxs-lookup"><span data-stu-id="fc02a-170">**Maximum:** *22*</span></span>
- <span data-ttu-id="fc02a-171">**Múltiplo:** *5*</span><span class="sxs-lookup"><span data-stu-id="fc02a-171">**Multiple:** *5*</span></span>

<span data-ttu-id="fc02a-172">Há 10 itens de inventário disponível para o produto, e não há outra demanda ou oferta.</span><span class="sxs-lookup"><span data-stu-id="fc02a-172">There are 10 pieces of on-hand inventory for the product, and there is no other demand or supply.</span></span>

<span data-ttu-id="fc02a-173">Quando o planejamento mestre é executado, uma ordem planejada para 10 itens é criada (porque 15 itens de reabastecimento mais 10 itens de inventário manual excederão a quantidade máxima).</span><span class="sxs-lookup"><span data-stu-id="fc02a-173">When master planning runs, a planned order for 10 pieces is created (because 15 pieces of replenishment plus 10 pieces of on-hand inventory will exceed the maximum quantity).</span></span>

### <a name="example-3"></a><span data-ttu-id="fc02a-174">Exemplo 3</span><span class="sxs-lookup"><span data-stu-id="fc02a-174">Example 3</span></span>

<span data-ttu-id="fc02a-175">Um produto tem a seguinte configuração:</span><span class="sxs-lookup"><span data-stu-id="fc02a-175">A product has the following configuration:</span></span>

- <span data-ttu-id="fc02a-176">**Código de cobertura:** *Mín./Máx.*</span><span class="sxs-lookup"><span data-stu-id="fc02a-176">**Coverage code:** *Min./Max.*</span></span>
- <span data-ttu-id="fc02a-177">**Mínimo:** *21*</span><span class="sxs-lookup"><span data-stu-id="fc02a-177">**Minimum:** *21*</span></span>
- <span data-ttu-id="fc02a-178">**Máximo:** *24*</span><span class="sxs-lookup"><span data-stu-id="fc02a-178">**Maximum:** *24*</span></span>
- <span data-ttu-id="fc02a-179">**Múltiplo:** *5*</span><span class="sxs-lookup"><span data-stu-id="fc02a-179">**Multiple:** *5*</span></span>

<span data-ttu-id="fc02a-180">Há 10 itens de inventário disponível para o produto, e não há outra demanda ou oferta.</span><span class="sxs-lookup"><span data-stu-id="fc02a-180">There are 10 pieces of on-hand inventory for the product, and there is no other demand or supply.</span></span>

<span data-ttu-id="fc02a-181">Quando o planejamento mestre é executado, a ordem planejada para 15 itens é criada (porque 10 itens de reabastecimento mais 10 itens de inventário manual serão inferiores que a quantidade mínima).</span><span class="sxs-lookup"><span data-stu-id="fc02a-181">When master planning runs, the planned order for 15 pieces is created (because 10 pieces of replenishment plus 10 pieces of on-hand inventory will be less than the minimum quantity).</span></span>

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
