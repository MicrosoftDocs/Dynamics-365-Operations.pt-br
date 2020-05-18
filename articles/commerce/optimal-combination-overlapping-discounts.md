---
title: Determinar a combinação ideal de sobreposição de descontos
description: Quando os descontos se sobrepõem, você deve determinar a combinação dos descontos que produzirão a transação total inferior ou o desconto total maior. Quando o valor de desconto varia de acordo com o preço dos produtos que estão sendo comprados, como no desconto de varejo comum 'Compre 1, leve 1 X por cento de desconto' (BOGO), este processo se torna um problema de otimização combinatória.
author: kfend
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailParameters, RetailPeriodicDiscount,
audience: Application User, IT Pro
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 89643
ms.assetid: 09843c9a-3e19-4e4a-a8ce-80650f2095f9
ms.search.region: global
ms.search.industry: Retail
ms.author: kfend
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 565722da65cbb711acedb5acf7de4edfbd615314
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/01/2020
ms.locfileid: "3021670"
---
# <a name="determine-the-optimal-combination-of-overlapping-discounts"></a><span data-ttu-id="f188c-104">Determinar a combinação ideal de sobreposição de descontos</span><span class="sxs-lookup"><span data-stu-id="f188c-104">Determine the optimal combination of overlapping discounts</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="f188c-105">Quando os descontos se sobrepõem, você deve determinar a combinação dos descontos que produzirão a transação total inferior ou o desconto total maior.</span><span class="sxs-lookup"><span data-stu-id="f188c-105">When discounts overlap, you must determine the combination of overlapping discounts that will produce the lowest transaction total or the highest total discount.</span></span> <span data-ttu-id="f188c-106">Quando o valor de desconto varia de acordo com o preço dos produtos que são comprados, como no desconto de varejo comum "Compre 1, leve 1 X com percentual de desconto" (BOGO), este processo torna-se um problema de otimização combinatória.</span><span class="sxs-lookup"><span data-stu-id="f188c-106">When the discount amount varies according to the price of the products that are purchased, such as in the common "Buy 1, get 1 X percent off" (BOGO) retail discount, this process becomes an issue of combinatorial optimization.</span></span>

<span data-ttu-id="f188c-107">Este artigo aplica-se ao Microsoft Dynamics AX 2012 R3 com KB 3105973 (versão de 2 de novembro de 2015) ou posterior e ao Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="f188c-107">This article applies to Microsoft Dynamics AX 2012 R3 with KB 3105973 (released November 2, 2015) or later, and to Dynamics 365 Commerce.</span></span> <span data-ttu-id="f188c-108">Para determinar a combinação de sobreposição de descontos a ser aplicada tempestivamente, nós introduzimos um método de aplicação de sobreposição de descontos.</span><span class="sxs-lookup"><span data-stu-id="f188c-108">To determine the combination overlapping discounts to apply in a timely manner, we have introduced a method for applying overlapping discounts.</span></span> <span data-ttu-id="f188c-109">Chamamos este novo método de **classificação de valor marginal**.</span><span class="sxs-lookup"><span data-stu-id="f188c-109">We call this new method **marginal value ranking**.</span></span> <span data-ttu-id="f188c-110">A classificação de valor marginal é usada quando o tempo necessário para avaliar as combinações possíveis de sobreposição de descontos excede o limite configurável na página **Parâmetros do Commerce**.</span><span class="sxs-lookup"><span data-stu-id="f188c-110">Marginal value ranking is used when the time that is required in order to evaluate the possible combinations of overlapping discounts exceeds a threshold that is configurable on the **Commerce parameters** page.</span></span> <span data-ttu-id="f188c-111">No método de classificação de valor marginal, um valor é calculado para cada desconto de sobreposição usando o valor de desconto nos produtos compartilhados.</span><span class="sxs-lookup"><span data-stu-id="f188c-111">In the marginal value ranking method, a value is calculated for each overlapping discount by using the discount's value on the shared products.</span></span> <span data-ttu-id="f188c-112">Os descontos sobrepostos são então aplicados a partir do valor relativo mais alto ao valor relativo mais baixo.</span><span class="sxs-lookup"><span data-stu-id="f188c-112">The overlapped discounts are then applied from the highest relative value to the lowest relative value.</span></span> <span data-ttu-id="f188c-113">Para obter detalhes sobre o novo método, consulte a seção "Valor marginal", mais adiante neste artigo.</span><span class="sxs-lookup"><span data-stu-id="f188c-113">For details about the new method, see the "Marginal value" section, later in this article.</span></span> <span data-ttu-id="f188c-114">A classificação de valor marginal não é usada quando valores de desconto para um produto não são afetados por outros produtos na transação.</span><span class="sxs-lookup"><span data-stu-id="f188c-114">Marginal value ranking isn't used when the discount amounts for a product aren't affected by another product in the transaction.</span></span> <span data-ttu-id="f188c-115">Por exemplo, este método não é usado para os dois descontos simples ou para um desconto simples e um único desconto por quantidade de produto.</span><span class="sxs-lookup"><span data-stu-id="f188c-115">For example, this method isn't used for two simple discounts, or for a simple discount and a single product quantity discount.</span></span>

## <a name="discount-examples"></a><span data-ttu-id="f188c-116">Exemplos de desconto</span><span class="sxs-lookup"><span data-stu-id="f188c-116">Discount examples</span></span>

<span data-ttu-id="f188c-117">Você pode criar um número ilimitado de descontos em um conjunto comum de produtos.</span><span class="sxs-lookup"><span data-stu-id="f188c-117">You can create an unlimited number of discounts on a common set of products.</span></span> <span data-ttu-id="f188c-118">Entretanto, como não há limites, problemas de desempenho podem ocorrer ao tentar calcular descontos que devem ser usados em vários produtos.</span><span class="sxs-lookup"><span data-stu-id="f188c-118">However, because there is no limit, performance issues can occur when you try to calculate the discounts that should be used on the various products.</span></span> <span data-ttu-id="f188c-119">Os exemplos a seguir ilustram esse problema mais detalhadamente.</span><span class="sxs-lookup"><span data-stu-id="f188c-119">The following examples illustrate this issue in more detail.</span></span> <span data-ttu-id="f188c-120">No exemplo 1, nós começamos com dois produtos e os dois descontos se sobrepuserem.</span><span class="sxs-lookup"><span data-stu-id="f188c-120">In example 1, we start with two products and two overlapping discounts.</span></span> <span data-ttu-id="f188c-121">Em seguida, no exemplo 2, mostramos como o problema evolui conforme mais produtos são adicionados.</span><span class="sxs-lookup"><span data-stu-id="f188c-121">Then, in example 2, we show how the issue evolves as more products are added.</span></span>

### <a name="example-1-two-products-and-two-discounts"></a><span data-ttu-id="f188c-122">Exemplo 1: Dois produtos e os dois descontos</span><span class="sxs-lookup"><span data-stu-id="f188c-122">Example 1: Two products and two discounts</span></span>

<span data-ttu-id="f188c-123">Neste exemplo, dois produtos são necessários para qualificar-se para cada desconto e os descontos não podem ser combinados.</span><span class="sxs-lookup"><span data-stu-id="f188c-123">In this example, two products are required in order to qualify for each discount, and the discounts can't be combined.</span></span> <span data-ttu-id="f188c-124">Os descontos no exemplo são descontos **Melhor preço**.</span><span class="sxs-lookup"><span data-stu-id="f188c-124">The discounts in this example are **Best price** discounts.</span></span> <span data-ttu-id="f188c-125">Os produtos se qualificam para os dois descontos.</span><span class="sxs-lookup"><span data-stu-id="f188c-125">Both products qualify for both discounts.</span></span> <span data-ttu-id="f188c-126">Veja os dois descontos.</span><span class="sxs-lookup"><span data-stu-id="f188c-126">Here are the two discounts.</span></span>

![Exemplo de dois descontos Melhor preço](./media/overlapping-discount-combo-01.jpg)

<span data-ttu-id="f188c-128">Para dois produtos quaisquer, o melhor desses dois descontos depende do preço dos dois produtos.</span><span class="sxs-lookup"><span data-stu-id="f188c-128">For any two products, the better of these two discounts depends on the prices of the two products.</span></span> <span data-ttu-id="f188c-129">Quando o preço dos produtos é igual ou quase igual, desconto 1 é melhor.</span><span class="sxs-lookup"><span data-stu-id="f188c-129">When the price of both products is equal or almost equal, discount 1 is better.</span></span> <span data-ttu-id="f188c-130">Quando o preço de um produto é significativamente menor que o preço de outros produtos, desconto 2 é melhor.</span><span class="sxs-lookup"><span data-stu-id="f188c-130">When the price of one product is significantly less than the price of the other product, discount 2 is better.</span></span> <span data-ttu-id="f188c-131">Esta é a regra matemática para avaliar esses dois descontos entre si.</span><span class="sxs-lookup"><span data-stu-id="f188c-131">Here is the mathematical rule for evaluating these two discounts against each other.</span></span>

![Regra de avaliação dos descontos](./media/overlapping-discount-combo-02.jpg)

> [!NOTE]
> <span data-ttu-id="f188c-133">Quando o preço do produto 1 é igual a dois terços do preço do produto 2, os dois descontos são iguais.</span><span class="sxs-lookup"><span data-stu-id="f188c-133">When the price of product 1 is equal to two-thirds of the price of product 2, the two discounts are equal.</span></span> <span data-ttu-id="f188c-134">Neste exemplo, a porcentagem de desconto em vigor para desconto 1 varia de uma porcentagem menor (quando os preços dos produtos forem afastados) a um máximo de 25% (quando os dois projetos tiverem o mesmo preço).</span><span class="sxs-lookup"><span data-stu-id="f188c-134">In this example, the effective discount percentage for discount 1 varies from a few percent (when the prices of the two products are far apart) to a maximum of 25 percent (when the two products have the same price).</span></span> <span data-ttu-id="f188c-135">A porcentagem de desconto em vigor para desconto 2 é fixa.</span><span class="sxs-lookup"><span data-stu-id="f188c-135">The effective discount percentage for discount 2 is fixed.</span></span> <span data-ttu-id="f188c-136">É sempre 20%.</span><span class="sxs-lookup"><span data-stu-id="f188c-136">It's always 20 percent.</span></span> <span data-ttu-id="f188c-137">Como a porcentagem de desconto em vigor para desconto 1 tem um intervalo que pode ser maior ou menor do que de desconto 2, o melhor desconto depende de preços dos produtos a serem descontados.</span><span class="sxs-lookup"><span data-stu-id="f188c-137">Because the effective discount percentage for discount 1 has a range that can be more than or less than discount 2, the best discount depends on the prices of the two products that must be discounted.</span></span> <span data-ttu-id="f188c-138">Neste exemplo, o cálculo é concluído rapidamente, pois apenas dois descontos são aplicados em apenas dois produtos.</span><span class="sxs-lookup"><span data-stu-id="f188c-138">In this example, the calculation is completed quickly, because only two discounts are applied on only two products.</span></span> <span data-ttu-id="f188c-139">Há somente duas combinações possíveis: uma aplicação de desconto 1 ou uma aplicação de desconto 2.</span><span class="sxs-lookup"><span data-stu-id="f188c-139">There are only two possible combinations: one application of discount 1 or one application of discount 2.</span></span> <span data-ttu-id="f188c-140">Não há permutações para cálculo.</span><span class="sxs-lookup"><span data-stu-id="f188c-140">There are no permutations to calculate.</span></span> <span data-ttu-id="f188c-141">O valor da cada desconto é calculado usando ambos produtos e o melhor desconto é usado.</span><span class="sxs-lookup"><span data-stu-id="f188c-141">The value of each discount is calculated by using both products, and the best discount is used.</span></span>

### <a name="example-2-four-products-and-two-discounts"></a><span data-ttu-id="f188c-142">Exemplo 2: Quatro produtos e dois descontos</span><span class="sxs-lookup"><span data-stu-id="f188c-142">Example 2: Four products and two discounts</span></span>

<span data-ttu-id="f188c-143">Em seguida, usaremos quatro produtos e os mesmos dois descontos.</span><span class="sxs-lookup"><span data-stu-id="f188c-143">Next, we will use four products and the same two discounts.</span></span> <span data-ttu-id="f188c-144">Todos os quatro produtos se qualificam para os dois descontos.</span><span class="sxs-lookup"><span data-stu-id="f188c-144">All four products qualify for both discounts.</span></span> <span data-ttu-id="f188c-145">Há doze combinações possíveis.</span><span class="sxs-lookup"><span data-stu-id="f188c-145">There are twelve possible combinations.</span></span> <span data-ttu-id="f188c-146">No final, dois descontos serão aplicados à transação em uma das três combinações: duas aplicações de desconto 1, duas aplicações de desconto 2 ou uma aplicação de desconto 1 e uma de desconto 2.</span><span class="sxs-lookup"><span data-stu-id="f188c-146">In the end, two discounts will be applied to the transaction in one of three combinations: two applications of discount 1, two applications of discount 2, or one application of discount 1 and one application of discount 2.</span></span> <span data-ttu-id="f188c-147">Para ilustrar as possíveis combinações, olharemos dois conjuntos diferentes dos quatro produtos com preços diferentes:</span><span class="sxs-lookup"><span data-stu-id="f188c-147">To illustrate the possible combinations, we will look at two different sets of four products that have different prices:</span></span>

- <span data-ttu-id="f188c-148">Todos os quatro produtos têm o mesmo preço, US$ 15,00.</span><span class="sxs-lookup"><span data-stu-id="f188c-148">All four products have the same price, $15.00.</span></span> <span data-ttu-id="f188c-149">Nesse caso, a melhor combinação de desconto é duas aplicações de desconto 1.</span><span class="sxs-lookup"><span data-stu-id="f188c-149">In this case, the best discount combination is two applications of discount 1.</span></span> <span data-ttu-id="f188c-150">Dois produto terão preço completo e dois terão 50% de desconto.</span><span class="sxs-lookup"><span data-stu-id="f188c-150">Two products will be full price, and two will be 50 percent off.</span></span> <span data-ttu-id="f188c-151">O total descontado da transação é de US$ 45 (15 + 15 + 7,50 + 7,50), que é US$ 15 (25%) de desconto do total descontado de US$ 60.</span><span class="sxs-lookup"><span data-stu-id="f188c-151">The discounted total for the transaction is $45 (15 + 15 + 7.50 + 7.50), which is $15 (25 percent) off the undiscounted total of $60.</span></span> <span data-ttu-id="f188c-152">O desconto 2 é de apenas US$ 12 (20%).</span><span class="sxs-lookup"><span data-stu-id="f188c-152">Discount 2 is only $12 (20 percent).</span></span>
- <span data-ttu-id="f188c-153">Dois produtos são US$ 20 cada, um produto é US$ 15 e o outro US$ 5.</span><span class="sxs-lookup"><span data-stu-id="f188c-153">Two products are $20 each, one product is $15, and one product is $5.</span></span> <span data-ttu-id="f188c-154">Nesse caso, a melhor combinação de desconto é uma aplicação do desconto 2 e uma aplicação do desconto 1.</span><span class="sxs-lookup"><span data-stu-id="f188c-154">In this case, the best discount combination is one application of discount 2 and one application of discount 1.</span></span> <span data-ttu-id="f188c-155">As tabelas a seguir ilustram os descontos.</span><span class="sxs-lookup"><span data-stu-id="f188c-155">The following tables illustrates the discounts.</span></span>

<span data-ttu-id="f188c-156">Para ler as tabelas, use um produto de uma linha e um produto de uma coluna.</span><span class="sxs-lookup"><span data-stu-id="f188c-156">To read the tables, use one product from a row and one product from a column.</span></span> <span data-ttu-id="f188c-157">Por exemplo, na tabela do desconto 1, quando você combina os dois produtos de US$ 20, você receberá US$ 10 de desconto.</span><span class="sxs-lookup"><span data-stu-id="f188c-157">For example, in the table for discount 1, when you combine the two $20 products, you get $10 off.</span></span> <span data-ttu-id="f188c-158">Na tabela do desconto 2, quando você combina o produto de US$ 15 e o de US$ 5, você receberá US$ 4 de desconto.</span><span class="sxs-lookup"><span data-stu-id="f188c-158">In the table for discount 2, when you combine the $15 product and the $5 product, you get $4 off.</span></span>

![Exemplo que usa quatro produtos para os mesmos dois descontos](./media/overlapping-discount-combo-03.jpg)

<span data-ttu-id="f188c-160">Primeiro, encontramos o maior desconto disponível de quaisquer dois produtos usando qualquer desconto.</span><span class="sxs-lookup"><span data-stu-id="f188c-160">First, we find the largest discount that is available from any two products by using either discount.</span></span> <span data-ttu-id="f188c-161">As duas tabelas mostram o valor de desconto de todas as combinações dos produtos.</span><span class="sxs-lookup"><span data-stu-id="f188c-161">The two tables show the discount amount for all combinations of the two products.</span></span> <span data-ttu-id="f188c-162">As partes protegidas das tabelas representam um dos casos em que um produto é emparelhado com ele mesmo, o que não podemos fazer, ou um emparelhamento reverso de dois produtos que produz o mesmo valor de desconto e pode ser ignorado.</span><span class="sxs-lookup"><span data-stu-id="f188c-162">The shaded portions of the tables represent either cases where a product is paired with itself, which we can't do, or a reverse pairing of two products that produces the same discount amount and can be ignored.</span></span> <span data-ttu-id="f188c-163">Olhando as tabelas, é possível ver que o desconto 1 para os dois itens de US$ 20 é o maior desconto disponível dos dois descontos em todos os quatro produtos.</span><span class="sxs-lookup"><span data-stu-id="f188c-163">By looking at the tables, you can see that discount 1 for the two $20 items is the largest discount that is available for either discount on all four products.</span></span> <span data-ttu-id="f188c-164">(Esse desconto é realçado em verde na primeira tabela.) Isso deixa apenas o produto de US$ 15 e o de US$ 5.</span><span class="sxs-lookup"><span data-stu-id="f188c-164">(This discount is highlighted in green in the first table.) That leaves only the $15 product and the $5 product.</span></span> <span data-ttu-id="f188c-165">Olhando as duas tabelas novamente, você pode ver que, para esses dois produtos, o desconto 1 oferece um desconto de US$ 2,50, enquanto o desconto 2 oferece um desconto de US$ 4.</span><span class="sxs-lookup"><span data-stu-id="f188c-165">By looking at the two tables again, you can see that, for these two products, discount 1 gives a $2.50 discount, whereas discount 2 gives a $4 discount.</span></span> <span data-ttu-id="f188c-166">Portanto, selecionamos o desconto 2.</span><span class="sxs-lookup"><span data-stu-id="f188c-166">Therefore, we select discount 2.</span></span> <span data-ttu-id="f188c-167">O desconto total é de US$ 14.</span><span class="sxs-lookup"><span data-stu-id="f188c-167">The total discount is $14.</span></span> <span data-ttu-id="f188c-168">Para facilitar a visualização dessa discrepância, veja duas tabelas adicionais que mostram o a porcentagem de desconto em vigor para todas as combinações de dois produtos possíveis para os descontos 1 e 2.</span><span class="sxs-lookup"><span data-stu-id="f188c-168">To make this discussion easier to visualize, here are two additional tables that show the effective discount percentage for all possible two-product combinations for both discount 1 and discount 2.</span></span> <span data-ttu-id="f188c-169">Somente metade da lista de combinações é incluída, pois, para esses dois descontos, a ordem na qual os dois produtos são colocados no desconto não importa.</span><span class="sxs-lookup"><span data-stu-id="f188c-169">Only half the list of combinations is included, because, for these two discounts, the order in which the two products are put into the discount doesn't matter.</span></span> <span data-ttu-id="f188c-170">O desconto mais alto em vigor (25%) é destacado em verde, e o desconto em vigor inferior (10%) é destacado em vermelho.</span><span class="sxs-lookup"><span data-stu-id="f188c-170">The highest effective discount (25 percent) is highlighted in green, and the lowest effective discount (10 percent) is highlighted in red.</span></span>

![Percentual de desconto em vigor para todas as combinações de dois produtos para ambos os descontos](./media/overlapping-discount-combo-04.jpg)

> [!NOTE]
> <span data-ttu-id="f188c-172">Quando os preços variam e dois ou mais descontos competem, a única maneira de garantir a melhor combinação de descontos é avaliar os dois descontos e compará-los.</span><span class="sxs-lookup"><span data-stu-id="f188c-172">When prices vary, and two or more discount compete, the only way to guarantee the best combination of discounts is to evaluate both discounts and compare them.</span></span>

## <a name="total-possible-combinations"></a><span data-ttu-id="f188c-173">Combinações totais possíveis</span><span class="sxs-lookup"><span data-stu-id="f188c-173">Total possible combinations</span></span>

<span data-ttu-id="f188c-174">Esta seção continua o exemplo da seção anterior.</span><span class="sxs-lookup"><span data-stu-id="f188c-174">This section continues the example from the previous section.</span></span> <span data-ttu-id="f188c-175">Nós adicionaremos mais produtos e outro desconto, e veremos quantas combinações devem ser calculadas e comparadas.</span><span class="sxs-lookup"><span data-stu-id="f188c-175">We will add more products and another discount, and see how many combinations must be calculated and compared.</span></span> <span data-ttu-id="f188c-176">A tabela a seguir mostra o número de combinações de desconto possíveis conforme a quantidade de produto aumenta.</span><span class="sxs-lookup"><span data-stu-id="f188c-176">The following table shows the number of possible discount combinations as the product quantity increases.</span></span> <span data-ttu-id="f188c-177">A tabela mostra o que acontece em ambos quando houver dois descontos se sobrepondo, como no exemplo anterior, e quando há três descontos se sobrepondo.</span><span class="sxs-lookup"><span data-stu-id="f188c-177">The table shows what happens both when there are two overlapping discounts, as in the previous example, and when there are three overlapping discounts.</span></span> <span data-ttu-id="f188c-178">O número de combinações possíveis de descontos que devem ser avaliados logo excede o que até um computador rápido pode calcular e compara rápido o suficiente aceitável para transações de varejo.</span><span class="sxs-lookup"><span data-stu-id="f188c-178">The number of possible discount combinations that must be evaluated soon exceeds what even a fast computer can calculate and compare quickly enough to be acceptable for retail transactions.</span></span>

![Número de combinações de desconto possíveis conforme a quantidade de produto aumenta.](./media/overlapping-discount-combo-05.jpg)

<span data-ttu-id="f188c-180">Quando quantidades ainda maiores ou descontos mais sobrepostos são aplicados, o número total de combinações de desconto possível rapidamente entra na casa dos milhões, e o tempo necessário para avaliar e selecionar a melhor combinação possível rapidamente torna-se notória.</span><span class="sxs-lookup"><span data-stu-id="f188c-180">When even larger quantities or more overlapping discounts are applied, the total number of possible discount combinations quickly goes into the millions, and the time that is required in order to evaluate and select the best possible combination quickly becomes noticeable.</span></span> <span data-ttu-id="f188c-181">Algumas otimizações foram feitas no mecanismo de preço para reduzir o número total de combinações que devem ser avaliadas.</span><span class="sxs-lookup"><span data-stu-id="f188c-181">Some optimizations have been done in the price engine to reduce the total number of combinations that must be evaluated.</span></span> <span data-ttu-id="f188c-182">Porém, como o número de descontos sobrepostos e as quantidades em uma transação não são limitados, um número maior de combinações sempre precisará ser avaliado toda vez que houver descontos sobrepostos.</span><span class="sxs-lookup"><span data-stu-id="f188c-182">However, because the number overlapping discounts and the quantities in a transaction aren't limited, a large number of combinations will always have to be evaluated whenever there are overlapping discounts.</span></span> <span data-ttu-id="f188c-183">Esse problema é o problema que o método de avaliação de valor marginal aborda.</span><span class="sxs-lookup"><span data-stu-id="f188c-183">This issue is the issue that the marginal value ranking method addresses.</span></span>

## <a name="marginal-value-method"></a><span data-ttu-id="f188c-184">Método de valor marginal</span><span class="sxs-lookup"><span data-stu-id="f188c-184">Marginal value method</span></span>

<span data-ttu-id="f188c-185">Para resolver o problema de um número exponencialmente elevado de combinações que devem ser avaliadas, uma otimização existe, que calcula o valor por produto compartilhado de cada desconto no grupo de produtos que dois ou mais descontos pode ser aplicado.</span><span class="sxs-lookup"><span data-stu-id="f188c-185">To resolve the issue of an exponentially increasing number of combinations that must be evaluated, an optimization exists that calculates the value per shared product of each discount on the set of products that two or more discounts can be applied to.</span></span> <span data-ttu-id="f188c-186">Nos referimos a este valor como **valor marginal** do desconto para os produtos compartilhados.</span><span class="sxs-lookup"><span data-stu-id="f188c-186">We refer to this value as the **marginal value** of the discount for the shared products.</span></span> <span data-ttu-id="f188c-187">O valor marginal é o aumento médio por produto no valor de desconto total quando os produtos compartilhados são incluídos em cada desconto.</span><span class="sxs-lookup"><span data-stu-id="f188c-187">The marginal value is the average per product increase in the total discount amount when the shared products are included in each discount.</span></span> <span data-ttu-id="f188c-188">O valor marginal é calculado pegando o valor de desconto total (DTotal), subtraindo o valor de desconto sem os produtos compartilhados (DMenos\\ Compartilhado) e dividindo a diferença pelo número de produtos compartilhados (ProductsShared).</span><span class="sxs-lookup"><span data-stu-id="f188c-188">The marginal value is calculated by taking the total discount amount (DTotal), subtracting the discount amount without the shared products (DMinus\\ Shared), and dividing that difference by the number of shared products (ProductsShared).</span></span>

![Fórmula para calcular o valor marginal](./media/overlapping-discount-combo-06.jpg)

<span data-ttu-id="f188c-190">Após o valor marginal de cada desconto em um grupo compartilhado de produtos ser calculado, os descontos são aplicados aos produtos compartilhados na ordem do valor marginal maior para o menor.</span><span class="sxs-lookup"><span data-stu-id="f188c-190">After the marginal value of each discount on a shared set of products is calculated, the discounts are applied to the shared products in order, exhaustively, from highest marginal value to lowest marginal value.</span></span> <span data-ttu-id="f188c-191">Para este método, todas as possibilidades restantes de desconto não são comparadas sempre depois que uma única instância de um desconto é aplicada.</span><span class="sxs-lookup"><span data-stu-id="f188c-191">For this method, all remaining discount possibilities aren't compared every time after a single instance of a discount is applied.</span></span> <span data-ttu-id="f188c-192">Em vez disso, os descontos sobrepostos são comparados uma vez e depois aplicados em ordem.</span><span class="sxs-lookup"><span data-stu-id="f188c-192">Instead, the overlapping discounts are compared one time and then applied in order.</span></span> <span data-ttu-id="f188c-193">Nenhuma comparação adicional é feita.</span><span class="sxs-lookup"><span data-stu-id="f188c-193">No additional comparisons are done.</span></span> <span data-ttu-id="f188c-194">Você pode configurar o limite para trocar para o método de valor marginal na guia **Desconto** da página **Parâmetros do Commerce**.</span><span class="sxs-lookup"><span data-stu-id="f188c-194">You can configure the threshold to switch to the marginal value method on the **Discount** tab of the **Commerce parameters** page.</span></span> <span data-ttu-id="f188c-195">O tempo aceitável para calcular o desconto total varia entre as indústrias de varejo.</span><span class="sxs-lookup"><span data-stu-id="f188c-195">The acceptable time to calculate the total discount varies across retail industries.</span></span> <span data-ttu-id="f188c-196">Porém, esse tempo geralmente cai na variação de diversos milissegundos a um segundo.</span><span class="sxs-lookup"><span data-stu-id="f188c-196">However, this time generally falls in the range of tens of milliseconds to one second.</span></span>