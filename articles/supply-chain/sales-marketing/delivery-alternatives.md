---
title: Alternativas de entrega
description: "Os tomadores de ordem de venda podem usar a página de Alternativas de entrega para descobrir opções alternativos de preenchimento da ordem."
author: ChristianRytt
manager: AnnBe
ms.date: 04/10/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SalesLineDeliveryDetails
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 271623
ms.assetid: 527f6084-44fe-41bb-924f-4386e926358a
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: crytt
ms.dyn365.ops.intro: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: cbfbdf5f79ef557ea934505285b57562b0b289ba
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---

# <a name="delivery-alternatives"></a><span data-ttu-id="bbc49-103">Alternativas de entrega</span><span class="sxs-lookup"><span data-stu-id="bbc49-103">Delivery alternatives</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="bbc49-104">Os tomadores de ordem de venda podem usar a página de Alternativas de entrega para descobrir opções alternativos de preenchimento da ordem.</span><span class="sxs-lookup"><span data-stu-id="bbc49-104">Sales order takers can use the Delivery alternatives page to discover alternative order fulfillment options.</span></span>

<span data-ttu-id="bbc49-105">Na versão 1611 (novembro de 2016) do Microsoft Dynamics 365 for Operations, os tomadores de ordem de venda podem usar a página **Alternativas de entrega** para descobrir opções alternativas de preenchimento da ordem.</span><span class="sxs-lookup"><span data-stu-id="bbc49-105">In Microsoft Dynamics 365 for Operations version 1611 (November 2016), sales order takers can use the **Delivery alternatives** page to discover alternative order fulfillment options.</span></span> <span data-ttu-id="bbc49-106">O layout da página reprojetado apresenta uma visão geral melhor de todas as opções alternativas.</span><span class="sxs-lookup"><span data-stu-id="bbc49-106">The redesigned page layout gives a better overview of all alternative options.</span></span> <span data-ttu-id="bbc49-107">Também permite que os tomadores de ordem olhe além da empresa atual para obter oportunidades de atendimento.</span><span class="sxs-lookup"><span data-stu-id="bbc49-107">It also lets order takers look beyond the current company for fulfillment opportunities.</span></span> <span data-ttu-id="bbc49-108">Eles agora podem exibir as oportunidades intercompanhia e as oportunidades dos fornecedores externos.</span><span class="sxs-lookup"><span data-stu-id="bbc49-108">They can now view both intercompany opportunities and opportunities from external vendors.</span></span> <span data-ttu-id="bbc49-109">Classificando as opções por data de entrega, os tomadores de ordem de venda podem exibir uma lista inteligente de alternativas de entrega.</span><span class="sxs-lookup"><span data-stu-id="bbc49-109">By sorting the options by delivery date, sales order takers can view an intelligent list of delivery alternatives.</span></span> <span data-ttu-id="bbc49-110">Além disso, os parâmetros nos ajudam a gerenciar melhor as entregas sugeridas.</span><span class="sxs-lookup"><span data-stu-id="bbc49-110">In addition, parameters help them better manage the suggested deliveries.</span></span> <span data-ttu-id="bbc49-111">Como o tempo de transporte pode afetar datas de entrega, os tomadores de ordem de venda podem explorar várias opções de transporte que as transportadoras oferecem.</span><span class="sxs-lookup"><span data-stu-id="bbc49-111">Because transport time can affect delivery dates, sales order takers can explore the various transportation choices that carriers offer.</span></span> <span data-ttu-id="bbc49-112">Como as informações detalhadas são mostradas para cada sugestão, os tomadores de ordem podem tomar decisões diretamente da página **Alternativas de entrega**.</span><span class="sxs-lookup"><span data-stu-id="bbc49-112">Because detailed information is shown for each suggestion, order takers can make informed decisions directly from the **Delivery alternatives** page.</span></span>

## <a name="open-the-delivery-alternatives-page"></a><span data-ttu-id="bbc49-113">Abra a página Alternativas de entrega</span><span class="sxs-lookup"><span data-stu-id="bbc49-113">Open the Delivery alternatives page</span></span>
<span data-ttu-id="bbc49-114">Você pode abrir a página **Alternativas** **de entrega** da linha de ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="bbc49-114">You can open the **Delivery** **alternatives** page from the sales order line.</span></span>

1.  <span data-ttu-id="bbc49-115">Clique em **Produtos e fornecimento** &gt; **Alternativas de entrega**.</span><span class="sxs-lookup"><span data-stu-id="bbc49-115">Click **Products and supply** &gt; **Delivery alternatives**.</span></span>
2.  <span data-ttu-id="bbc49-116">Clique em **Detalhes da linha** &gt; **Entrega** &gt; **Alternativas de entrega.**</span><span class="sxs-lookup"><span data-stu-id="bbc49-116">Click **Line details** &gt; **Delivery** &gt; **Delivery alternatives.**</span></span>

<span data-ttu-id="bbc49-117">Você também pode abrir a página **Alternativas de entrega** abrindo o espaço de trabalho **Processamento e consulta de ordem de venda** e, em seguida, clicando em &gt; **Ordens e favoritos** **Linhas de ordem atrasadas** &gt; **Alternativas de entrega** **Observação:** você pode abrir as **Alternativas de entrega** somente se as seguintes condições forem atendidas:</span><span class="sxs-lookup"><span data-stu-id="bbc49-117">You can also open the **Delivery alternatives** page by opening the **Sales order processing and inquiry** workspace, and then clicking **Orders and favorites** &gt; **Delayed order lines** &gt; **Delivery alternatives** **Note:** You can open the **Delivery alternatives** page only if both the following conditions are met:</span></span>

-   <span data-ttu-id="bbc49-118">Todas as informações da linha de venda obrigatórias são preenchidas.</span><span class="sxs-lookup"><span data-stu-id="bbc49-118">All mandatory sales line information is filled in.</span></span>
-   <span data-ttu-id="bbc49-119">O campo **Controle da data de entrega** é definido para um valor diferente de **Nenhum**.</span><span class="sxs-lookup"><span data-stu-id="bbc49-119">The **Delivery date control** field is set to a value other than **None**.</span></span>

## <a name="delivery-date-control-methods"></a><span data-ttu-id="bbc49-120">Métodos de controle da data de entrega</span><span class="sxs-lookup"><span data-stu-id="bbc49-120">Delivery date control methods</span></span>
<span data-ttu-id="bbc49-121">O método de controle de data de entrega determina como o sistema estabelece as datas de entrega, como as alternativas de entrega são calculadas e quais informações são mostradas.</span><span class="sxs-lookup"><span data-stu-id="bbc49-121">The delivery date control method determines how the system establishes delivery dates, how delivery alternatives are calculated, and what information is shown.</span></span> <span data-ttu-id="bbc49-122">Observe que o controle de dados de entrega leva em consideração os calendários.</span><span class="sxs-lookup"><span data-stu-id="bbc49-122">Note that delivery data control takes calendars into consideration.</span></span> <span data-ttu-id="bbc49-123">Portanto, os seguintes calendários podem afetar a data sugerida de recibo: calendário de depósito, calendário de transporte, calendário do fornecedor e calendário do cliente.</span><span class="sxs-lookup"><span data-stu-id="bbc49-123">Therefore, the following calendars can affect the suggested receipt date: Warehouse calendar, Transport calendar, Vendor calendar, and Customer calendar.</span></span> <span data-ttu-id="bbc49-124">A tabela a seguir descreve cada método de controle de data de entrega.</span><span class="sxs-lookup"><span data-stu-id="bbc49-124">The following table describes each method for delivery date control.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><span data-ttu-id="bbc49-125"><strong>Método</strong></span><span class="sxs-lookup"><span data-stu-id="bbc49-125"><strong>Method</strong></span></span></td>
<td><span data-ttu-id="bbc49-126"><strong>Descrição</strong></span><span class="sxs-lookup"><span data-stu-id="bbc49-126"><strong>Description</strong></span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="bbc49-127"><strong>Nenhum</strong></span><span class="sxs-lookup"><span data-stu-id="bbc49-127"><strong>None</strong></span></span></td>
<td><ul>
<li><span data-ttu-id="bbc49-128">As alternativas de entrega de linhas de venda não são suportadas.</span><span class="sxs-lookup"><span data-stu-id="bbc49-128">Delivery alternatives for sales lines aren't supported.</span></span> <span data-ttu-id="bbc49-129">Esta opção desativa o controle de dados da entrega.</span><span class="sxs-lookup"><span data-stu-id="bbc49-129">This option turns off delivery data control.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="bbc49-130"><strong>Prazo de entrega das vendas</strong></span><span class="sxs-lookup"><span data-stu-id="bbc49-130"><strong>Sales lead time</strong></span></span></td>
<td><ul>
<li><span data-ttu-id="bbc49-131">As alternativas de entrega são calculadas com base no prazo de entrega das vendas predefinido.</span><span class="sxs-lookup"><span data-stu-id="bbc49-131">Delivery alternatives are calculated based on the predefined sales lead time.</span></span> <span data-ttu-id="bbc49-132">Os dias de transporte são calculados com base no modo de entrega.</span><span class="sxs-lookup"><span data-stu-id="bbc49-132">The transport days are calculated based on the mode of delivery.</span></span></li>
<li><span data-ttu-id="bbc49-133">As alternativas de entrega incluem depósitos que têm estoque disponível e ordens de suprimento/demanda.</span><span class="sxs-lookup"><span data-stu-id="bbc49-133">Delivery alternatives include warehouses that have on-hand inventory, and supply/demand orders.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="bbc49-134"><strong>ATP</strong></span><span class="sxs-lookup"><span data-stu-id="bbc49-134"><strong>ATP</strong></span></span></td>
<td><ul>
<li><span data-ttu-id="bbc49-135">As alternativas de entrega são calculadas com base na lógica ATP - disponível para promessa.</span><span class="sxs-lookup"><span data-stu-id="bbc49-135">Delivery alternatives are calculated based on available to promise (ATP) logic.</span></span> <span data-ttu-id="bbc49-136">A disponibilidade atual e a disponibilidade futura prevista são consideradas.</span><span class="sxs-lookup"><span data-stu-id="bbc49-136">The current availability and expected future availability are considered.</span></span> <span data-ttu-id="bbc49-137">Os dias de transporte são calculados com base no modo de entrega.</span><span class="sxs-lookup"><span data-stu-id="bbc49-137">The transport days are calculated based on the mode of delivery.</span></span></li>
<li><span data-ttu-id="bbc49-138">As alternativas de entrega incluem depósitos que têm estoque disponível e ordens de suprimento/demanda.</span><span class="sxs-lookup"><span data-stu-id="bbc49-138">Delivery alternatives include warehouses that have on-hand inventory, and supply/demand orders.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="bbc49-139"><strong>ATP + Margem de saída</strong></span><span class="sxs-lookup"><span data-stu-id="bbc49-139"><strong>ATP + Issue margin</strong></span></span></td>
<td><ul>
<li><span data-ttu-id="bbc49-140">As alternativas de entrega são calculadas para o método ATP, mas a margem de saída é incluída no cálculo.</span><span class="sxs-lookup"><span data-stu-id="bbc49-140">Delivery alternatives are calculated as for the ATP method, but the issue margin is included in the calculation.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="bbc49-141"><strong>CTP</strong></span><span class="sxs-lookup"><span data-stu-id="bbc49-141"><strong>CTP</strong></span></span></td>
<td><ul>
<li><span data-ttu-id="bbc49-142">As alternativas de entrega são calculadas com base na lógica CTP (capacidade de comprometimento).</span><span class="sxs-lookup"><span data-stu-id="bbc49-142">Delivery alternatives are calculated based on the capable to promise (CTP) logic.</span></span> <span data-ttu-id="bbc49-143">A explosão de MRP é usada para determinar a disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="bbc49-143">MRP explosion is used to determine availability.</span></span> <span data-ttu-id="bbc49-144">Observe que, pelo menos, o CTP compensa datas de entrega ao prazo de entrega de vendas.</span><span class="sxs-lookup"><span data-stu-id="bbc49-144">Note that, at a minimum, CTP offsets delivery dates to the sales lead time.</span></span> <span data-ttu-id="bbc49-145">Os dias de transporte são calculados com base no modo de entrega.</span><span class="sxs-lookup"><span data-stu-id="bbc49-145">The transport days are calculated based on the mode of delivery.</span></span></li>
<li><span data-ttu-id="bbc49-146">As alternativas de entrega são sugestões para os seguintes depósitos:</span><span class="sxs-lookup"><span data-stu-id="bbc49-146">Delivery alternatives include suggestions for the following warehouses:</span></span>
<ul>
<li><span data-ttu-id="bbc49-147">Depósito atual</span><span class="sxs-lookup"><span data-stu-id="bbc49-147">Current warehouse</span></span></li>
<li><span data-ttu-id="bbc49-148">Depósito padrão</span><span class="sxs-lookup"><span data-stu-id="bbc49-148">Default warehouse</span></span></li>
<li><span data-ttu-id="bbc49-149">Todos os depósitos que têm estoque disponível</span><span class="sxs-lookup"><span data-stu-id="bbc49-149">All warehouses that have available on-hand inventory</span></span></li>
<li><span data-ttu-id="bbc49-150">Todos os depósitos que têm ordens de suprimento</span><span class="sxs-lookup"><span data-stu-id="bbc49-150">All warehouses that have supply orders</span></span></li>
<li><span data-ttu-id="bbc49-151">Todos os depósitos que têm versões da BOM (lista de materiais) ativa</span><span class="sxs-lookup"><span data-stu-id="bbc49-151">All warehouses that have active bill of materials (BOM) versions</span></span></li>
</ul></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="view-information-about-delivery-alternatives"></a><span data-ttu-id="bbc49-152">Exibir informações sobre alternativas de entrega</span><span class="sxs-lookup"><span data-stu-id="bbc49-152">View information about delivery alternatives</span></span>
<span data-ttu-id="bbc49-153">Esta seção descreve as informações sobre alternativas de entrega que estão disponíveis em cada guia da página **Alternativas de entrega**.</span><span class="sxs-lookup"><span data-stu-id="bbc49-153">This section describes the information about delivery alternatives that is available on each tab of the **Delivery alternatives** page.</span></span>

### <a name="products"></a><span data-ttu-id="bbc49-154">Produtos</span><span class="sxs-lookup"><span data-stu-id="bbc49-154">Products</span></span>

<span data-ttu-id="bbc49-155">Esta guia mostra um resumo dos produtos e os detalhes da linha de venda atual.</span><span class="sxs-lookup"><span data-stu-id="bbc49-155">This tab shows a summary of the product and details of the current sales line.</span></span>

### <a name="delivery-alternatives"></a><span data-ttu-id="bbc49-156">Alternativas de entrega</span><span class="sxs-lookup"><span data-stu-id="bbc49-156">Delivery alternatives</span></span>

<span data-ttu-id="bbc49-157">Esta guia mostra uma lista de alternativas de entrega classificada por dados do recibo.</span><span class="sxs-lookup"><span data-stu-id="bbc49-157">This tab shows a list of delivery alternatives that is sorted by receipt data.</span></span> <span data-ttu-id="bbc49-158">Acima da lista, é possível selecionar em quais opções se baseiam as sugestões.</span><span class="sxs-lookup"><span data-stu-id="bbc49-158">Above the list, you can select which options to base the suggestions on.</span></span> <span data-ttu-id="bbc49-159">Você também pode selecionar o modo de entrega, que determina os dias de transporte.</span><span class="sxs-lookup"><span data-stu-id="bbc49-159">You can also select the mode of delivery, which determines the transport days.</span></span> <span data-ttu-id="bbc49-160">As opções a seguir estão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="bbc49-160">The following options are available:</span></span>

-   <span data-ttu-id="bbc49-161">**Incluir outras variantes de produto** - Esta opção está disponível para produtos que têm variantes do produto.</span><span class="sxs-lookup"><span data-stu-id="bbc49-161">**Include other product variants** - This option is available for products that have product variants.</span></span> <span data-ttu-id="bbc49-162">Incluirá alternativas de entrega para outras variantes do produto.</span><span class="sxs-lookup"><span data-stu-id="bbc49-162">It will include delivery alternatives for other variants of the product.</span></span> <span data-ttu-id="bbc49-163">Esta opção não está disponível para o CTP.</span><span class="sxs-lookup"><span data-stu-id="bbc49-163">This option isn't available for CTP.</span></span>
-   <span data-ttu-id="bbc49-164">**Incluir quantidade parcial** - Por padrão, somente as sugestões que atendem a quantidade total das linhas de venda são incluídas.</span><span class="sxs-lookup"><span data-stu-id="bbc49-164">**Include partial quantity** - By default, only suggestions that fulfill the full quantity of the sales line are included.</span></span> <span data-ttu-id="bbc49-165">Selecione esta opção para incluir as que atendem apenas parcialmente a linha de ordem.</span><span class="sxs-lookup"><span data-stu-id="bbc49-165">Select this option to include suggestions that only partially fulfill the order line.</span></span> <span data-ttu-id="bbc49-166">Essa opção é útil quando o cliente solicita uma data de entrega anterior e aceita a entrega parcial.</span><span class="sxs-lookup"><span data-stu-id="bbc49-166">This option is useful when the customer requests an earlier delivery date and accepts partial delivery.</span></span>
-   <span data-ttu-id="bbc49-167">**Incluir datas posteriores** - Por padrão, somente são mostradas as sugestões melhores (anteriores) que as datas atuais na linha de venda.</span><span class="sxs-lookup"><span data-stu-id="bbc49-167">**Include later dates** - By default, only suggestions that are better (earlier) than the current dates on the sales line are shown.</span></span> <span data-ttu-id="bbc49-168">Selecione esta opção para incluir as datas posteriores.</span><span class="sxs-lookup"><span data-stu-id="bbc49-168">Select this option to include later dates.</span></span> <span data-ttu-id="bbc49-169">Essa opção pode ser útil em situações onde os parâmetros diferente da data têm prioridade.</span><span class="sxs-lookup"><span data-stu-id="bbc49-169">This option can be useful in situations where parameters other than the date have priority.</span></span> <span data-ttu-id="bbc49-170">Por exemplo, um fornecedor ou depósito específico podem ser preferenciais.</span><span class="sxs-lookup"><span data-stu-id="bbc49-170">For example, a specific vendor or warehouse might be preferred.</span></span>
-   <span data-ttu-id="bbc49-171">**Modo de entrega** - Selecione o modo de entrega preferido para otimizar tempo e custo de transporte.</span><span class="sxs-lookup"><span data-stu-id="bbc49-171">**Mode of delivery** - Select the preferred mode of delivery to optimize transport time and cost.</span></span> <span data-ttu-id="bbc49-172">Você verá imediatamente o efeito nas alternativas de entrega sugeridas.</span><span class="sxs-lookup"><span data-stu-id="bbc49-172">You will immediately see the effect on the suggested delivery alternatives.</span></span> <span data-ttu-id="bbc49-173">Portanto, é fácil comparar as alternativas.</span><span class="sxs-lookup"><span data-stu-id="bbc49-173">Therefore, it's easy to compare the alternatives.</span></span>
-   <span data-ttu-id="bbc49-174">**Incluir compras** - Quanto compras for selecionada, as alternativas de entrega sugeridas incluirão opções para comprar de fornecedores externos e de outras companhias da empresa (intercompanhias).</span><span class="sxs-lookup"><span data-stu-id="bbc49-174">**Include procurement** - When procurement is selected, the suggested delivery alternatives include options to procure from both external vendors and other companies in the enterprise (intercompany).</span></span> <span data-ttu-id="bbc49-175">A opção **Incluir compras** é suportada para ATP e ATP + controle de data de entrega da margem de saída</span><span class="sxs-lookup"><span data-stu-id="bbc49-175">The **Include procurement** option is supported for ATP and ATP + Issue margin delivery date control.</span></span> <span data-ttu-id="bbc49-176">Estão inclusas as opções de compras do fornecedor de compra padrão do produto e de todos os fornecedores aprovados para o produto.</span><span class="sxs-lookup"><span data-stu-id="bbc49-176">Procurement options from the default purchase vendor for the product and all approved vendors for the product are included.</span></span>
-   <span data-ttu-id="bbc49-177">Para fornecedores externos, o cálculo baseia-se no prazo de entrega da compra.</span><span class="sxs-lookup"><span data-stu-id="bbc49-177">For external vendors, the calculation is based on the purchase lead time.</span></span>
-   <span data-ttu-id="bbc49-178">Para intercompanhia, o cálculo considera o que está disponível na empresa de fornecimento, com base no controle de data de entrega na empresa de fornecimento.</span><span class="sxs-lookup"><span data-stu-id="bbc49-178">For intercompany, the calculation considers what is available from the sourcing company, based on delivery date control in the sourcing company.</span></span>
-   <span data-ttu-id="bbc49-179">**Tipo de entrega** (Relevante para compras)</span><span class="sxs-lookup"><span data-stu-id="bbc49-179">**Delivery type** (Relevant for procurement)</span></span>
    -   <span data-ttu-id="bbc49-180">**Estoque** - Os produtos são enviados do depósito de fornecimento para o local/depósito na linha de venda.</span><span class="sxs-lookup"><span data-stu-id="bbc49-180">**Stock** - Products are shipped from the sourcing warehouse to the site/warehouse on the sales line.</span></span> <span data-ttu-id="bbc49-181">Em seguida, são enviados do depósito para o cliente.</span><span class="sxs-lookup"><span data-stu-id="bbc49-181">They are then shipped from that warehouse to the customer.</span></span>
    -   <span data-ttu-id="bbc49-182">**Entrega direta** - os produtos são enviados diretamente do depósito de fornecimento para o cliente.</span><span class="sxs-lookup"><span data-stu-id="bbc49-182">**Direct delivery** - Products are shipped directly from the sourcing warehouse to the customer.</span></span>

### <a name="availability-information"></a><span data-ttu-id="bbc49-183">Informações de disponibilidade</span><span class="sxs-lookup"><span data-stu-id="bbc49-183">Availability information</span></span>

<span data-ttu-id="bbc49-184">As informações desta guia estão relacionadas à linha de entrega alternativa selecionada.</span><span class="sxs-lookup"><span data-stu-id="bbc49-184">Information on this tab is related to the delivery alternative line that is selected.</span></span> <span data-ttu-id="bbc49-185">As informações a seguir são mostradas, dependendo do controle da data de entrega da linha de venda:</span><span class="sxs-lookup"><span data-stu-id="bbc49-185">The following information is shown, depending on the delivery date control for the sales line:</span></span>

-   <span data-ttu-id="bbc49-186">**Prazo de entrega das vendas**</span><span class="sxs-lookup"><span data-stu-id="bbc49-186">**Sales lead time**</span></span>
    -   <span data-ttu-id="bbc49-187">**Disponível hoje** - mostra o estoque físico disponível atual, físico reservado e físico disponível.</span><span class="sxs-lookup"><span data-stu-id="bbc49-187">**Available today** - Show the current physical on-hand, physical reserved, and available physical inventory.</span></span>
    -   <span data-ttu-id="bbc49-188">**Parâmetros** Mostra a unidade de estoque e o prazo de entrega de venda.</span><span class="sxs-lookup"><span data-stu-id="bbc49-188">**Parameters** - Show the inventory unit and sales lead time.</span></span>

-   <span data-ttu-id="bbc49-189">**ATP e ATP + margem de saída**</span><span class="sxs-lookup"><span data-stu-id="bbc49-189">**ATP and ATP + Issue margin**</span></span>
    -   <span data-ttu-id="bbc49-190">**Disponível hoje** - mostra o estoque físico disponível atual, físico reservado e físico disponível.</span><span class="sxs-lookup"><span data-stu-id="bbc49-190">**Available today** - Show the current physical on-hand, physical reserved, and available physical inventory.</span></span>
    -   <span data-ttu-id="bbc49-191">**Parâmetros** Mostra a unidade de estoque e o prazo de entrega de venda.</span><span class="sxs-lookup"><span data-stu-id="bbc49-191">**Parameters** - Show the inventory unit and sales lead time.</span></span>
    -   <span data-ttu-id="bbc49-192">**Disponibilidade futura** - mostra uma representação gráfica da disponibilidade atual e futura para o local e depósito selecionados em **Alternativas de entrega**.</span><span class="sxs-lookup"><span data-stu-id="bbc49-192">**Future availability** - Show a graphical representation of current and future availability for the selected site and warehouse under **Delivery alternatives**.</span></span> <span data-ttu-id="bbc49-193">Você pode clicar nas colunas do gráfico para ver mais informações detalhadas sobre a futura disponibilidade do produto.</span><span class="sxs-lookup"><span data-stu-id="bbc49-193">You can click the chart columns to see more detailed information about the future availability of the product.</span></span> <span data-ttu-id="bbc49-194">O controle deslizante mostra uma lista das ordens de suprimento e demanda relevantes dentro do limite de tempo de ATP.</span><span class="sxs-lookup"><span data-stu-id="bbc49-194">The slider shows a list of relevant demand and supply orders within the ATP time fence.</span></span>

-   <span data-ttu-id="bbc49-195">**CTP**</span><span class="sxs-lookup"><span data-stu-id="bbc49-195">**CTP**</span></span>
    -   <span data-ttu-id="bbc49-196">**Disponível hoje** - mostra o estoque físico disponível atual, físico reservado e físico disponível.</span><span class="sxs-lookup"><span data-stu-id="bbc49-196">**Available today** - Show the current physical on-hand, physical reserved, and available physical inventory.</span></span>
    -   <span data-ttu-id="bbc49-197">**Parâmetros** Mostra a unidade de estoque e o prazo de entrega de venda.</span><span class="sxs-lookup"><span data-stu-id="bbc49-197">**Parameters** - Show the inventory unit and sales lead time.</span></span>
    -   <span data-ttu-id="bbc49-198">**Detalhamento** - mostra um detalhamento do suprimento da alternativa de entrega selecionada.</span><span class="sxs-lookup"><span data-stu-id="bbc49-198">**Explosion** - Show a supply explosion of the selected delivery alternative.</span></span> <span data-ttu-id="bbc49-199">É possível usar **Configuração** para alterar os campos e as dimensões de estoque mostradas no detalhamento.</span><span class="sxs-lookup"><span data-stu-id="bbc49-199">You can use **Setup** to change the fields and inventory dimensions that are shown in the explosion.</span></span>

### <a name="impact-of-selected-alternative"></a><span data-ttu-id="bbc49-200">Impacto da alternativa selecionada</span><span class="sxs-lookup"><span data-stu-id="bbc49-200">Impact of selected alternative</span></span>

<span data-ttu-id="bbc49-201">Esta guia destaca o impacto da alternativa de entrega selecionada.</span><span class="sxs-lookup"><span data-stu-id="bbc49-201">This tab highlights the impact of the selected delivery alternative.</span></span> <span data-ttu-id="bbc49-202">Se você clicar em **OK**, a linha de venda será atualizada com valores destacados nas colunas SELECIONADAS.</span><span class="sxs-lookup"><span data-stu-id="bbc49-202">If you click **OK**, the sales line is updated with the highlighted values in the SELECTED columns.</span></span> <span data-ttu-id="bbc49-203">Observe que, se a quantidade na alternativa de entrega selecionada for menor que a quantidade na linha de vendas, uma agenda de entrega será criada, e a linha da ordem será dividida em duas linhas: uma linha para a quantidade selecionada e uma linha para a quantidade pendente.</span><span class="sxs-lookup"><span data-stu-id="bbc49-203">Note that, if the quantity on the selected delivery alternative is less than quantity on the sales line, a delivery schedule is created, and the order line is split into two lines: one line for the selected quantity and one line for the remaining quantity.</span></span> <span data-ttu-id="bbc49-204">Você também pode atualizar a linha comercial, de forma que ela corresponda às linhas da agenda e afete o preço.</span><span class="sxs-lookup"><span data-stu-id="bbc49-204">You can also update the commercial line so that it matches the schedule lines and affects the pricing.</span></span>

<a name="see-also"></a><span data-ttu-id="bbc49-205">Consulte também</span><span class="sxs-lookup"><span data-stu-id="bbc49-205">See also</span></span>
--------

[<span data-ttu-id="bbc49-206">Promessa de ordem</span><span class="sxs-lookup"><span data-stu-id="bbc49-206">Order promising</span></span>](delivery-dates-available-promise-calculations.md)




