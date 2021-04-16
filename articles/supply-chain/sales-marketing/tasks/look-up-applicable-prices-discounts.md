---
title: Pesquisar preços e descontos aplicáveis
description: Este procedimento mostra como encontrar o preço e/ou desconto para um produto que é válido no momento para um cliente específico, sem criar uma ordem de venda.
author: omulvad
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 50d7cf7b765c27db5aa9ea50c8593132c68c850a
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5824837"
---
# <a name="look-up-applicable-prices-and-discounts"></a><span data-ttu-id="e3b45-103">Pesquisar preços e descontos aplicáveis</span><span class="sxs-lookup"><span data-stu-id="e3b45-103">Look up applicable prices and discounts</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="e3b45-104">Este procedimento mostra como encontrar o preço e/ou desconto para um produto que é válido no momento para um cliente específico, sem criar uma ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="e3b45-104">This procedure shows how to find the price and/or discount for a product which is currently valid for a specific customer, without creating a sales order.</span></span> <span data-ttu-id="e3b45-105">O procedimento aborda um exemplo específico, e você precisa seguir o exemplo utilizando a empresa de demonstração USMF para selecionar os valores necessários.</span><span class="sxs-lookup"><span data-stu-id="e3b45-105">The procedure walks through a specific example, and you need follow the example using the USMF demo company in order to select the necessary values.</span></span>


## <a name="find-the-applicable-price"></a><span data-ttu-id="e3b45-106">Localizar o preço aplicável</span><span class="sxs-lookup"><span data-stu-id="e3b45-106">Find the applicable price</span></span>
1. <span data-ttu-id="e3b45-107">Vá para Vendas e marketing > Preços e descontos > Encontrar preços.</span><span class="sxs-lookup"><span data-stu-id="e3b45-107">Go to Sales and marketing > Prices and discounts > Find prices.</span></span>
2. <span data-ttu-id="e3b45-108">No campo Conta do cliente, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="e3b45-108">In the Customer account field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="e3b45-109">Na lista, localize e selecione o cliente US-001.</span><span class="sxs-lookup"><span data-stu-id="e3b45-109">In the list, find and select customer US-001.</span></span>
4. <span data-ttu-id="e3b45-110">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="e3b45-110">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="e3b45-111">No campo Número do item, digite 'T0004'.</span><span class="sxs-lookup"><span data-stu-id="e3b45-111">In the Item number field, type 'T0004'.</span></span>
    * <span data-ttu-id="e3b45-112">Por padrão, o campo Quantidade está definido como 1.</span><span class="sxs-lookup"><span data-stu-id="e3b45-112">By default, the Quantity field is set to 1.</span></span> <span data-ttu-id="e3b45-113">No entanto, se você souber o tamanho da ordem que o cliente pretende realizar para o produto em questão, insira este valor no lugar.</span><span class="sxs-lookup"><span data-stu-id="e3b45-113">However, if you know the size of the order that the customer intends to place for the product in question, then enter this value instead.</span></span> <span data-ttu-id="e3b45-114">Essa informação é relevante se os contratos comerciais com o cliente tem divisões de quantidade, ou seja, o preço do produto depende da quantidade mínima comprada.</span><span class="sxs-lookup"><span data-stu-id="e3b45-114">This information is relevant if the trade agreements with the customer have quantity breaks, that is, the product's price depends on the minimum quantity purchased.</span></span>  
6. <span data-ttu-id="e3b45-115">No campo Data, insira uma data para quando o cliente espera fazer um pedido.</span><span class="sxs-lookup"><span data-stu-id="e3b45-115">In the Date field, enter a date for when the customer expects to place an order.</span></span> 
    * <span data-ttu-id="e3b45-116">A data pode ser a data de hoje ou qualquer data futura.</span><span class="sxs-lookup"><span data-stu-id="e3b45-116">The date can be today's date or any date in the future.</span></span>  
    * <span data-ttu-id="e3b45-117">O sistema agora retorna o preço que é válido para o produto selecionado quando comprado pelo cliente selecionado na data selecionada com uma quantidade especificada.</span><span class="sxs-lookup"><span data-stu-id="e3b45-117">The system now returns the price that is valid for the selected product when bought by the selected customer on the selected date with a specified quantity.</span></span> <span data-ttu-id="e3b45-118">Neste exemplo, se o cliente US-001 comprou 1 unidade do produto T0004 hoje, seria cobrado do cliente 350 CAD por unidade</span><span class="sxs-lookup"><span data-stu-id="e3b45-118">In this example, if the customer US-001 bought 1 unit of product T0004 today, they would be charged 350 CAD a unit.</span></span> <span data-ttu-id="e3b45-119">Esse preço é obtido de um contrato comercial existente e ativo com o cliente.</span><span class="sxs-lookup"><span data-stu-id="e3b45-119">This price comes from an existing and active trade agreement with the customer.</span></span>      <span data-ttu-id="e3b45-120">Outros campos na página fornecem mais detalhes sobre o preço e o custo do produto (se configurado no produto mestre), e a lucratividade calculada.</span><span class="sxs-lookup"><span data-stu-id="e3b45-120">Other fields on the page provide more details about the product price and product cost (if set up on the product master), and calculated profitability.</span></span>  
    * <span data-ttu-id="e3b45-121">Se a opção Exibir variantes do produto relacionadas estiver selecionada, significa que existem contratos comerciais adicionais para variantes do produto.</span><span class="sxs-lookup"><span data-stu-id="e3b45-121">If the Show related product variants option is selected, it means that there are additional trade agreements for product's variants.</span></span>  
7. <span data-ttu-id="e3b45-122">Clique na caixa de seleção Exibir variantes do produto relacionadas.</span><span class="sxs-lookup"><span data-stu-id="e3b45-122">Click the Show related product variants checkbox.</span></span>
    * <span data-ttu-id="e3b45-123">Uma lista das variantes do produto é exibida, com informação sobre suas dimensões.</span><span class="sxs-lookup"><span data-stu-id="e3b45-123">A list of the product variants is shown, with information about their dimensions.</span></span>  
8. <span data-ttu-id="e3b45-124">Na lista, marque a linha que representa a cor Branca.</span><span class="sxs-lookup"><span data-stu-id="e3b45-124">In the list, mark the line representing color White.</span></span>
    * <span data-ttu-id="e3b45-125">Note que o preço do produto agora é diferente daquele exibido anteriormente quando não era especificado por dimensão.</span><span class="sxs-lookup"><span data-stu-id="e3b45-125">Notice, that the product price is now different from the one displayed previously when it was not specified per dimension.</span></span>  
9. <span data-ttu-id="e3b45-126">Clique em Exibir preços de venda.</span><span class="sxs-lookup"><span data-stu-id="e3b45-126">Click View sales prices.</span></span>
    * <span data-ttu-id="e3b45-127">A página Preços (venda) exibe todos os contratos comerciais aplicáveis ao produto, incluindo suas variantes.</span><span class="sxs-lookup"><span data-stu-id="e3b45-127">The Price (sales) page displays all the trade agreements applicable to the product, including its variants.</span></span>  
10. <span data-ttu-id="e3b45-128">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="e3b45-128">Close the page.</span></span>

## <a name="find-the-applicable-discount"></a><span data-ttu-id="e3b45-129">Localizar o desconto aplicável</span><span class="sxs-lookup"><span data-stu-id="e3b45-129">Find the applicable discount</span></span>
<span data-ttu-id="e3b45-130">Verifique se o campo Conta de cliente contém o número de cliente US-001 </span><span class="sxs-lookup"><span data-stu-id="e3b45-130">Make sure the Customer account field contains customer number US-001</span></span>   
1. <span data-ttu-id="e3b45-131">No campo Número do item, digite 'T0012'.</span><span class="sxs-lookup"><span data-stu-id="e3b45-131">In the Item number field, type 'T0012'.</span></span>
    * <span data-ttu-id="e3b45-132">Verifique se o campo Quantidade está definido como 1.</span><span class="sxs-lookup"><span data-stu-id="e3b45-132">Make sure the Quantity field is set to 1.</span></span>  
    * <span data-ttu-id="e3b45-133">Os seguintes detalhes de definição de preços mostrados para o produto T0012 vêm de um ou mais contratos comerciais: O preço unitário é 1.000 CAD e a porcentagem de desconto é 5.</span><span class="sxs-lookup"><span data-stu-id="e3b45-133">The following pricing details shown for product T0012 come from one or more trade agreements: The unit price is 1,000 CAD and the discount percentage is 5.</span></span>  
2. <span data-ttu-id="e3b45-134">Defina a quantidade como '20'.</span><span class="sxs-lookup"><span data-stu-id="e3b45-134">Set Quantity to '20'.</span></span>
    * <span data-ttu-id="e3b45-135">A quantidade da ordem aumentada faz com que o desconto de linha que será oferecido ao cliente mude de 5 para 7 por cento.</span><span class="sxs-lookup"><span data-stu-id="e3b45-135">The increased order quantity causes the line discount that will be offered to the customer to change from 5 to 7 percent.</span></span>  
    * <span data-ttu-id="e3b45-136">O Valor líquido é calculado com base no preço unitário, desconto e na quantidade total.</span><span class="sxs-lookup"><span data-stu-id="e3b45-136">The Net amount is calculated based on the unit price, discount and the total quantity.</span></span>  
3. <span data-ttu-id="e3b45-137">Clique em Exibir desconto de linha.</span><span class="sxs-lookup"><span data-stu-id="e3b45-137">Click View line discount.</span></span>
    * <span data-ttu-id="e3b45-138">Existem dois contratos de linha de desconto para o produto T0012, especificando um desconto de 5 por cento para uma quantidade de linha de ordem de 1 a 10, e 7 por cento para quantidades de ordem acima de 10.</span><span class="sxs-lookup"><span data-stu-id="e3b45-138">There are two line discount agreements for product T0012, specifying a 5 percent discount for an order line quantity from 1 to 10, and 7 percent discount for order quantities above 10.</span></span> <span data-ttu-id="e3b45-139">Observe que os descontos estão aplicados a um grupo de produtos, neste exemplo, Grupo código 01, do qual o produto T0012 é membro.</span><span class="sxs-lookup"><span data-stu-id="e3b45-139">Note that the discounts are applied to a group of products, in this example, Group code 01, of which product T0012 is a member.</span></span>  
4. <span data-ttu-id="e3b45-140">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="e3b45-140">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]