---
title: Solucionar problemas de preços, descontos, contratos e descontos
description: Este tópico descreve como corrigir problemas que podem ocorrer ao trabalhar com preços, descontos, contratos e descontos.
author: SmithaNataraj
manager: tfehr
ms.date: 09/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart, PurchRFQTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-9-16
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 5d17f2ec594901404fcd251e463f293258af051c
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5237146"
---
# <a name="troubleshoot-prices-discounts-agreements-and-rebates"></a><span data-ttu-id="7a6a4-103">Solucionar problemas de preços, descontos, contratos e descontos</span><span class="sxs-lookup"><span data-stu-id="7a6a4-103">Troubleshoot prices, discounts, agreements, and rebates</span></span>

<span data-ttu-id="7a6a4-104">Este tópico descreve como corrigir problemas que podem ocorrer ao trabalhar com preços, descontos, contratos e descontos.</span><span class="sxs-lookup"><span data-stu-id="7a6a4-104">This topic describes how to fix issues that you might encounter while you work with prices, discounts, agreements, and rebates.</span></span>

## <a name="i-cant-link-a-purchase-agreement-to-a-purchase-order-line-after-the-purchase-order-is-created"></a><span data-ttu-id="7a6a4-105">Não consigo vincular um contrato de compra a uma linha da ordem de compra após a criação da ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="7a6a4-105">I can't link a purchase agreement to a purchase order line after the purchase order is created.</span></span>

<span data-ttu-id="7a6a4-106">Um contrato de compra deve ser associado a uma ordem de compra quando a ordem de compra for criada.</span><span class="sxs-lookup"><span data-stu-id="7a6a4-106">A purchase agreement must be associated with a purchase order when the purchase order is created.</span></span> <span data-ttu-id="7a6a4-107">Caso contrário, as linhas da ordem de compra não podem ser associadas a linhas do contrato de compra.</span><span class="sxs-lookup"><span data-stu-id="7a6a4-107">Otherwise, purchase order lines can't be associated with purchase agreement lines.</span></span>

## <a name="what-check-triggers-the-update-prices-and-discounts-entered-manually-or-external-document-message"></a><span data-ttu-id="7a6a4-108">Que verificação dispara a mensagem "Atualizar preços e descontos inseridos manualmente ou documento externo"?</span><span class="sxs-lookup"><span data-stu-id="7a6a4-108">What check triggers the "Update prices and discounts entered manually or external document" message?</span></span>

<span data-ttu-id="7a6a4-109">Ao alterar a data de remessa, você pode receber uma mensagem que declara, "Atualizar preços e descontos inseridos manualmente ou documento externo."</span><span class="sxs-lookup"><span data-stu-id="7a6a4-109">When you change the shipping date, you might receive a message that states, "Update prices and discounts entered manually or external document."</span></span> <span data-ttu-id="7a6a4-110">Você recebe esta mensagem porque, se a data de remessa for alterada, um contrato comercial ou de venda diferente poderá ser disparado e provocar uma alteração de preço.</span><span class="sxs-lookup"><span data-stu-id="7a6a4-110">You receive this message because, if the shipping date is changed, a different trade or sales agreement might be triggered and cause a price change.</span></span> <span data-ttu-id="7a6a4-111">Uma alteração na data de remessa também pode afetar agendas de depósito e outras informações relacionadas.</span><span class="sxs-lookup"><span data-stu-id="7a6a4-111">A change to the shipping date can also affect warehouse schedules and other related information.</span></span>

<span data-ttu-id="7a6a4-112">A mensagem é disparada sempre que qualquer uma das datas ou outros parâmetros são alterados.</span><span class="sxs-lookup"><span data-stu-id="7a6a4-112">The message is triggered whenever any of the dates or some other parameters are changed.</span></span> <span data-ttu-id="7a6a4-113">A finalidade da mensagem é verificar se você está ciente de alterações de preço que podem ocorrer devido a essas alterações.</span><span class="sxs-lookup"><span data-stu-id="7a6a4-113">The purpose of the message is to make sure that you're aware of price changes that can occur because of those changes.</span></span>

<span data-ttu-id="7a6a4-114">A mensagem é o prompt de avaliação do contrato comercial (TAE).</span><span class="sxs-lookup"><span data-stu-id="7a6a4-114">The message is the trade agreement evaluation (TAE) prompt.</span></span> <span data-ttu-id="7a6a4-115">Para obter uma descrição completa, consulte [Políticas de avaliação de contrato comercial](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/trade-agreement-evaluation-policies-white-paper).</span><span class="sxs-lookup"><span data-stu-id="7a6a4-115">For a full description, see [Trade agreement evaluation policies](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/trade-agreement-evaluation-policies-white-paper).</span></span>

## <a name="a-purchase-order-receipt-doesnt-include-all-charges"></a><span data-ttu-id="7a6a4-116">Um recibo de ordem de compra não inclui todos os encargos.</span><span class="sxs-lookup"><span data-stu-id="7a6a4-116">A purchase order receipt doesn't include all charges.</span></span>

### <a name="reproduce-the-issue"></a><span data-ttu-id="7a6a4-117">Reproduzir o problema</span><span class="sxs-lookup"><span data-stu-id="7a6a4-117">Reproduce the issue</span></span>

<span data-ttu-id="7a6a4-118">O seguinte procedimento mostra uma forma de reproduzir o problema.</span><span class="sxs-lookup"><span data-stu-id="7a6a4-118">The following procedure shows one way to reproduce the issue.</span></span>

1. <span data-ttu-id="7a6a4-119">Na página **Parâmetros de compras**, na guia **Entrega**, certifique-se de que a opção **Gerar encargos no recibo do produto** está definida como *Sim*.</span><span class="sxs-lookup"><span data-stu-id="7a6a4-119">On the **Procurement and sourcing parameters** page, on the **Delivery** tab, make sure that the **Generate charges on product receipt** option is set to *Yes*.</span></span>
1. <span data-ttu-id="7a6a4-120">Crie uma ordem de compra que inclui encargos.</span><span class="sxs-lookup"><span data-stu-id="7a6a4-120">Create a purchase order that includes charges.</span></span>
1. <span data-ttu-id="7a6a4-121">Confirme uma ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="7a6a4-121">Confirm the purchase order.</span></span>
1. <span data-ttu-id="7a6a4-122">Receba a ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="7a6a4-122">Receive the purchase order.</span></span>
1. <span data-ttu-id="7a6a4-123">Examine o total do recibo e compare-o com o total esperado.</span><span class="sxs-lookup"><span data-stu-id="7a6a4-123">Look at the receipt total, and compare it to the expected total.</span></span>
1. <span data-ttu-id="7a6a4-124">Observe que nem todos os encargos estão incluídos no recebimento da ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="7a6a4-124">Notice that not all the charges are included on the purchase order receipt.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="7a6a4-125">Resolução do problema</span><span class="sxs-lookup"><span data-stu-id="7a6a4-125">Issue resolution</span></span>

<span data-ttu-id="7a6a4-126">A resolução depende da forma como os encargos diversos foram configurados.</span><span class="sxs-lookup"><span data-stu-id="7a6a4-126">The resolution depends on the way that the miscellaneous charges have been set up.</span></span> <span data-ttu-id="7a6a4-127">Para obter informações sobre como configurar encargos diversos de acordo com suas necessidades, consulte a seguinte postagem de blog: [Lançar encargos diversos no momento do recebimento do produto](https://cloudblogs.microsoft.com/dynamics365/no-audience/2014/11/11/post-misc-charges-at-time-of-product-receipt/).</span><span class="sxs-lookup"><span data-stu-id="7a6a4-127">For information about how to set up miscellaneous charges to meet your requirements, see the following blog post: [Post misc. charges at time of product receipt](https://cloudblogs.microsoft.com/dynamics365/no-audience/2014/11/11/post-misc-charges-at-time-of-product-receipt/).</span></span>

## <a name="trade-agreement-prices-and-discounts-arent-applied-on-sales-or-purchase-order-lines-that-are-imported-through-data-management"></a><span data-ttu-id="7a6a4-128">Os preços e descontos do contrato comercial não são aplicados a linhas de ordem de compra ou de venda que são importadas por meio do gerenciamento de dados.</span><span class="sxs-lookup"><span data-stu-id="7a6a4-128">Trade agreement prices and discounts aren't applied on sales or purchase order lines that are imported through data management.</span></span>

### <a name="issue-description"></a><span data-ttu-id="7a6a4-129">Descrição do problema</span><span class="sxs-lookup"><span data-stu-id="7a6a4-129">Issue description</span></span>

<span data-ttu-id="7a6a4-130">Os contratos comerciais que não são aplicados a linhas de ordem de compra ou de venda não são aplicados a linhas que são importadas por meio do gerenciamento de dados.</span><span class="sxs-lookup"><span data-stu-id="7a6a4-130">Trade agreements that are applicable to sales or purchase order lines aren't applied on lines that are imported through data management.</span></span> <span data-ttu-id="7a6a4-131">No entanto, os mesmos contratos comerciais são aplicados a linhas de ordem de compra ou de venda que são criadas manualmente.</span><span class="sxs-lookup"><span data-stu-id="7a6a4-131">However, the same trade agreements are applied on sales or purchase order lines that are manually created.</span></span>

### <a name="reason-for-the-issue"></a><span data-ttu-id="7a6a4-132">Motivo do problema</span><span class="sxs-lookup"><span data-stu-id="7a6a4-132">Reason for the issue</span></span>

<span data-ttu-id="7a6a4-133">Se as linhas da ordem de compra que são importadas por meio do gerenciamento de dados já incluírem informações de preço, o contrato comercial não será reavaliado para essas linhas.</span><span class="sxs-lookup"><span data-stu-id="7a6a4-133">If purchase order lines that are imported via data management already include price information, the trade agreement won't be reevaluated for those lines.</span></span> <span data-ttu-id="7a6a4-134">Por exemplo, se **Porcentagem de desconto de linha** ou qualquer um dos valores de preço e desconto for definido para uma linha, os contratos comerciais não serão pesquisados para essa linha.</span><span class="sxs-lookup"><span data-stu-id="7a6a4-134">For example, if **Line discount percentage** or any of the price and discount values is set for a line, then trade agreements will not be looked up for that line.</span></span>

### <a name="issue-workaround"></a><span data-ttu-id="7a6a4-135">Solução alternativa do problema</span><span class="sxs-lookup"><span data-stu-id="7a6a4-135">Issue workaround</span></span>

<span data-ttu-id="7a6a4-136">Esse comportamento é esperado e é semelhante para ordens de venda e ordens de compra.</span><span class="sxs-lookup"><span data-stu-id="7a6a4-136">This behavior is expected, and is similar for both sales orders and purchase orders.</span></span>

<span data-ttu-id="7a6a4-137">Para solucionar o problema, importe as linhas da ordem de compra sem definir as informações de preço.</span><span class="sxs-lookup"><span data-stu-id="7a6a4-137">As a workaround, import the purchase order lines without setting any price information.</span></span> <span data-ttu-id="7a6a4-138">Os contratos comerciais serão aplicados, e as linhas da ordem de compra serão atualizadas com base nos contratos comerciais definidos.</span><span class="sxs-lookup"><span data-stu-id="7a6a4-138">The trade agreements will then be applied, and the purchase order lines will be updated based on the defined trade agreements.</span></span>

## <a name="a-vendor-rebate-isnt-cumulated-based-on-invoices"></a><span data-ttu-id="7a6a4-139">Um desconto de fornecedor não é acumulado com base em faturas.</span><span class="sxs-lookup"><span data-stu-id="7a6a4-139">A vendor rebate isn't cumulated based on invoices.</span></span>

### <a name="issue-description"></a><span data-ttu-id="7a6a4-140">Descrição do problema</span><span class="sxs-lookup"><span data-stu-id="7a6a4-140">Issue description</span></span>

<span data-ttu-id="7a6a4-141">Se as faturas lançadas tiverem datas de conclusão diferentes, essas faturas serão refletidas em descontos de fornecedor que são gerados a partir delas.</span><span class="sxs-lookup"><span data-stu-id="7a6a4-141">If invoices that are posted have different due dates, those invoices aren't reflected in vendor rebates that are generated from them.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="7a6a4-142">Resolução do problema</span><span class="sxs-lookup"><span data-stu-id="7a6a4-142">Issue resolution</span></span>

<span data-ttu-id="7a6a4-143">Por design, a data de conclusão não é considerada quando o desconto do fornecedor é calculado.</span><span class="sxs-lookup"><span data-stu-id="7a6a4-143">By design, the due date isn't considered when the vendor rebate is calculated.</span></span> <span data-ttu-id="7a6a4-144">Considere a personalização do sistema para que a data de conclusão e a relação com a fatura sejam mais aparentes em relação ao desconto real do fornecedor.</span><span class="sxs-lookup"><span data-stu-id="7a6a4-144">Consider customizing the system so that the due date and the relation to the invoice are more apparent with respect to the actual vendor rebate.</span></span>

## <a name="unit-prices-on-purchase-orders-arent-calculated-based-on-the-unit-conversion"></a><span data-ttu-id="7a6a4-145">Os preços unitários das ordens de compra não são calculados com base na conversão de unidades.</span><span class="sxs-lookup"><span data-stu-id="7a6a4-145">Unit prices on purchase orders aren't calculated based on the unit conversion.</span></span>

### <a name="issue-description"></a><span data-ttu-id="7a6a4-146">Descrição do problema</span><span class="sxs-lookup"><span data-stu-id="7a6a4-146">Issue description</span></span>

<span data-ttu-id="7a6a4-147">Quando uma unidade é alterada em uma ordem de compra, os preços do contrato comercial não são recalculados de acordo com as definições de conversão de unidades.</span><span class="sxs-lookup"><span data-stu-id="7a6a4-147">When a unit is changed on a purchase order, trade agreement prices aren't recalculated according to unit conversion definitions.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="7a6a4-148">Resolução do problema</span><span class="sxs-lookup"><span data-stu-id="7a6a4-148">Issue resolution</span></span>

<span data-ttu-id="7a6a4-149">Os preços sempre obtidos de contratos comerciais (ou outras configurações de preço no sistema, como contratos de venda ou preços de item), e são definidos para uma unidade.</span><span class="sxs-lookup"><span data-stu-id="7a6a4-149">Prices are always obtained from trade agreements (or other price settings in the system, such as sales agreements or item prices), and they are set for a unit.</span></span>

<span data-ttu-id="7a6a4-150">Se a unidade for alterada em uma linha da ordem, o sistema procurará um preço para a nova unidade e aplicará esse preço.</span><span class="sxs-lookup"><span data-stu-id="7a6a4-150">If the unit is changed on an order line, the system looks for a price for the new unit and applies that price.</span></span> <span data-ttu-id="7a6a4-151">Se nenhum preço for encontrado para a unidade, o sistema não aplicará um preço.</span><span class="sxs-lookup"><span data-stu-id="7a6a4-151">If no price is found for the unit, the system doesn't apply a price.</span></span> <span data-ttu-id="7a6a4-152">A conversão de unidades não pode ser usada para recalcular o preço em outra unidade.</span><span class="sxs-lookup"><span data-stu-id="7a6a4-152">The unit conversion can't be used to recalculate the price into another unit.</span></span> <span data-ttu-id="7a6a4-153">Teoricamente, o preço de uma caixa de dez pode não ser igual a dez vezes o preço de uma caixa.</span><span class="sxs-lookup"><span data-stu-id="7a6a4-153">Theoretically, the price for one box of ten might not equal ten times the price of one box.</span></span>

### <a name="issue-workaround"></a><span data-ttu-id="7a6a4-154">Solução alternativa do problema</span><span class="sxs-lookup"><span data-stu-id="7a6a4-154">Issue workaround</span></span>

<span data-ttu-id="7a6a4-155">Uma forma de solucionar esse problema é verificar se há contratos comerciais para as unidades esperadas que serão usadas nas linhas da ordem para o item.</span><span class="sxs-lookup"><span data-stu-id="7a6a4-155">One way to work around this issue is to make sure that there are trade agreements for the units that you expect will be used on order lines for the item.</span></span>

## <a name="currency-conversion-issues-occur-with-trade-agreements"></a><span data-ttu-id="7a6a4-156">Os problemas de conversão de moeda ocorrem com os contratos comerciais.</span><span class="sxs-lookup"><span data-stu-id="7a6a4-156">Currency conversion issues occur with trade agreements.</span></span>

<span data-ttu-id="7a6a4-157">Os preços do contrato comercial não são recalculados, de acordo com a moeda, quando a moeda é diferente em uma ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="7a6a4-157">Trade agreement prices aren't recalculated according to the currency when the currency differs on a purchase order.</span></span>

<span data-ttu-id="7a6a4-158">O recurso *Moeda genérica* permite definir preços e descontos em apenas uma moeda.</span><span class="sxs-lookup"><span data-stu-id="7a6a4-158">The *Generic currency* feature lets you define prices and discounts in only one currency.</span></span> <span data-ttu-id="7a6a4-159">Em seguida, você pode converter para outras moedas, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="7a6a4-159">You can then convert to other currencies as you require.</span></span> <span data-ttu-id="7a6a4-160">Além disso, após a conversão ser concluída, o recurso pode aplicar o arredondamento inteligente automaticamente.</span><span class="sxs-lookup"><span data-stu-id="7a6a4-160">Furthermore, after the conversion is done, the feature can automatically apply smart rounding.</span></span>

## <a name="when-i-open-the-purchase-agreement-page-in-a-line-view-mode-i-cant-personalize-the-page-by-adding-the-price-unit-field-in-the-overview-of-the-line"></a><span data-ttu-id="7a6a4-161">Quando abro a página de Contrato de compra em um modo de exibição de linha, não consigo personalizar a página adicionando o campo Unidade de preço na visão geral da linha.</span><span class="sxs-lookup"><span data-stu-id="7a6a4-161">When I open the Purchase agreement page in a line view mode, I can't personalize the page by adding the Price unit field in the overview of the line.</span></span>

<span data-ttu-id="7a6a4-162">Alguns campos compartilhados na estrutura do contrato não podem ser incluídos nas personalizações.</span><span class="sxs-lookup"><span data-stu-id="7a6a4-162">Some shared fields in the agreement framework can't be included in personalizations.</span></span> <span data-ttu-id="7a6a4-163">Essa limitação ocorre por causa do modelo de dados implementado.</span><span class="sxs-lookup"><span data-stu-id="7a6a4-163">This limitation occurs because of the data model that is implemented.</span></span> <span data-ttu-id="7a6a4-164">Portanto, não é possível personalizar o campo **Unidade de preço**.</span><span class="sxs-lookup"><span data-stu-id="7a6a4-164">Therefore, you can't personalize the **Price unit** field.</span></span>

## <a name="the-maximum-limit-from-a-purchase-agreement-isnt-effective-on-a-purchase-requisition"></a><span data-ttu-id="7a6a4-165">O limite máximo de um contrato de compra não é efetivo em uma requisição de compra.</span><span class="sxs-lookup"><span data-stu-id="7a6a4-165">The maximum limit from a purchase agreement isn't effective on a purchase requisition.</span></span>

### <a name="issue-description"></a><span data-ttu-id="7a6a4-166">Descrição do problema</span><span class="sxs-lookup"><span data-stu-id="7a6a4-166">Issue description</span></span>

<span data-ttu-id="7a6a4-167">Quando uma requisição de compra estiver vinculada a um contrato de compra, o limite máximo do contrato de compra não será efetivo na requisição de compra.</span><span class="sxs-lookup"><span data-stu-id="7a6a4-167">When a purchase requisition is linked to a purchase agreement, the maximum limit from the purchase agreement isn't effective on the purchase requisition.</span></span> <span data-ttu-id="7a6a4-168">As informações de preço padrão são inseridas corretamente, mas mais do que o limite máximo do contrato de compra pode ser solicitado na requisição de compra.</span><span class="sxs-lookup"><span data-stu-id="7a6a4-168">The default price information is correctly entered, but more than the maximum limit from the purchase agreement can be ordered in the purchase requisition.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="7a6a4-169">Resolução do problema</span><span class="sxs-lookup"><span data-stu-id="7a6a4-169">Issue resolution</span></span>

<span data-ttu-id="7a6a4-170">Esse comportamento é esperado.</span><span class="sxs-lookup"><span data-stu-id="7a6a4-170">This behavior is expected.</span></span> <span data-ttu-id="7a6a4-171">Como as requisições nem sempre são aprovadas, uma quantidade ou um valor não deve ser reservado no contrato de compra.</span><span class="sxs-lookup"><span data-stu-id="7a6a4-171">Because requisitions aren't always approved, a quantity or amount should not be reserved on the purchase agreement.</span></span> <span data-ttu-id="7a6a4-172">Portanto, você não atenderá ao limite máximo do contrato de compra.</span><span class="sxs-lookup"><span data-stu-id="7a6a4-172">Therefore, you won't meet the maximum limit from the purchase agreement.</span></span>

## <a name="trade-agreements-can-be-created-from-rejected-rfqs-therefore-the-system-doesnt-prevent-trade-agreement-journals-from-being-created-if-the-rfq-line-hasnt-been-accepted"></a><span data-ttu-id="7a6a4-173">Os contratos comerciais podem ser criados a partir de RFQs rejeitadas.</span><span class="sxs-lookup"><span data-stu-id="7a6a4-173">Trade agreements can be created from rejected RFQs.</span></span> <span data-ttu-id="7a6a4-174">Portanto, o sistema não impede que os diários de contratos comerciais sejam criados se a linha da RFQ não tiver sido aceita.</span><span class="sxs-lookup"><span data-stu-id="7a6a4-174">Therefore, the system doesn't prevent trade agreement journals from being created if the RFQ line hasn't been accepted.</span></span>

<span data-ttu-id="7a6a4-175">Você pode criar contratos comerciais para qualquer resposta para uma solicitação de cotação (RFQ), independentemente de elas terem sido aceitas ou rejeitadas.</span><span class="sxs-lookup"><span data-stu-id="7a6a4-175">You can create trade agreements for any replies for a request for quotation (RFQ), regardless of whether they were accepted or rejected.</span></span> <span data-ttu-id="7a6a4-176">Para obter informações, consulte [Visão geral de solicitações de cotação (RFQs)](request-quotations.md).</span><span class="sxs-lookup"><span data-stu-id="7a6a4-176">For more information, see [Requests for quotation (RFQs) overview](request-quotations.md).</span></span>



[!INCLUDE[footer-include](../../includes/footer-banner.md)]