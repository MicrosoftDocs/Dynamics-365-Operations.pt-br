---
title: Determinar a combinação ideal de sobreposição de descontos
description: Quando os descontos se sobrepõem, você deve determinar a combinação dos descontos que produzirão a transação total inferior ou o desconto total maior. Quando o valor de desconto varia de acordo com o preço dos produtos que estão sendo comprados, como no desconto de varejo comum 'Compre 1, leve 1 X por cento de desconto' (BOGO), este processo se torna um problema de otimização combinatória.
author: kfend
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailParameters, RetailPeriodicDiscount,
audience: Application User, IT Pro
ms.reviewer: josaw
ms.custom: 89643
ms.assetid: 09843c9a-3e19-4e4a-a8ce-80650f2095f9
ms.search.region: global
ms.search.industry: Retail
ms.author: kfend
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 51526c8409e0a04cf35e2dbd63cb4a3bd7d121e0
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/06/2021
ms.locfileid: "6352953"
---
# <a name="determine-the-optimal-combination-of-overlapping-discounts"></a>Determinar a combinação ideal de sobreposição de descontos

[!include [banner](includes/banner.md)]

Quando os descontos se sobrepõem, você deve determinar a combinação dos descontos que produzirão a transação total inferior ou o desconto total maior. Quando o valor de desconto varia de acordo com o preço dos produtos que são comprados, como no desconto de varejo comum "Compre 1, leve 1 X com percentual de desconto" (BOGO), este processo torna-se um problema de otimização combinatória.

Este artigo aplica-se ao Microsoft Dynamics AX 2012 R3 com KB 3105973 (versão de 2 de novembro de 2015) ou posterior e ao Dynamics 365 Commerce. Para determinar a combinação de sobreposição de descontos a ser aplicada tempestivamente, nós introduzimos um método de aplicação de sobreposição de descontos. Chamamos este novo método de **classificação de valor marginal**. A classificação de valor marginal é usada quando o tempo necessário para avaliar as combinações possíveis de sobreposição de descontos excede o limite configurável na página **Parâmetros do Commerce**. No método de classificação de valor marginal, um valor é calculado para cada desconto de sobreposição usando o valor de desconto nos produtos compartilhados. Os descontos sobrepostos são então aplicados a partir do valor relativo mais alto ao valor relativo mais baixo. Para obter detalhes sobre o novo método, consulte a seção "Valor marginal", mais adiante neste artigo. A classificação de valor marginal não é usada quando valores de desconto para um produto não são afetados por outros produtos na transação. Por exemplo, este método não é usado para os dois descontos simples ou para um desconto simples e um único desconto por quantidade de produto.

## <a name="discount-examples"></a>Exemplos de desconto

Você pode criar um número ilimitado de descontos em um conjunto comum de produtos. Entretanto, como não há limites, problemas de desempenho podem ocorrer ao tentar calcular descontos que devem ser usados em vários produtos. Os exemplos a seguir ilustram esse problema mais detalhadamente. No exemplo 1, nós começamos com dois produtos e os dois descontos se sobrepuserem. Em seguida, no exemplo 2, mostramos como o problema evolui conforme mais produtos são adicionados.

### <a name="example-1-two-products-and-two-discounts"></a>Exemplo 1: Dois produtos e os dois descontos

Neste exemplo, dois produtos são necessários para qualificar-se para cada desconto e os descontos não podem ser combinados. Os descontos no exemplo são descontos **Melhor preço**. Os produtos se qualificam para os dois descontos. Veja os dois descontos.

![Exemplo de dois descontos Melhor preço.](./media/overlapping-discount-combo-01.jpg)

Para dois produtos quaisquer, o melhor desses dois descontos depende do preço dos dois produtos. Quando o preço dos produtos é igual ou quase igual, desconto 1 é melhor. Quando o preço de um produto é significativamente menor que o preço de outros produtos, desconto 2 é melhor. Esta é a regra matemática para avaliar esses dois descontos entre si.

![Regra de avaliação dos descontos.](./media/overlapping-discount-combo-02.jpg)

> [!NOTE]
> Quando o preço do produto 1 é igual a dois terços do preço do produto 2, os dois descontos são iguais. Neste exemplo, a porcentagem de desconto em vigor para desconto 1 varia de uma porcentagem menor (quando os preços dos produtos forem afastados) a um máximo de 25% (quando os dois projetos tiverem o mesmo preço). A porcentagem de desconto em vigor para desconto 2 é fixa. É sempre 20%. Como a porcentagem de desconto em vigor para desconto 1 tem um intervalo que pode ser maior ou menor do que de desconto 2, o melhor desconto depende de preços dos produtos a serem descontados. Neste exemplo, o cálculo é concluído rapidamente, pois apenas dois descontos são aplicados em apenas dois produtos. Há somente duas combinações possíveis: uma aplicação de desconto 1 ou uma aplicação de desconto 2. Não há permutações para cálculo. O valor da cada desconto é calculado usando ambos produtos e o melhor desconto é usado.

### <a name="example-2-four-products-and-two-discounts"></a>Exemplo 2: Quatro produtos e dois descontos

Em seguida, usaremos quatro produtos e os mesmos dois descontos. Todos os quatro produtos se qualificam para os dois descontos. Há doze combinações possíveis. No final, dois descontos serão aplicados à transação em uma das três combinações: duas aplicações de desconto 1, duas aplicações de desconto 2 ou uma aplicação de desconto 1 e uma de desconto 2. Para ilustrar as possíveis combinações, olharemos dois conjuntos diferentes dos quatro produtos com preços diferentes:

- Todos os quatro produtos têm o mesmo preço, US$ 15,00. Nesse caso, a melhor combinação de desconto é duas aplicações de desconto 1. Dois produto terão preço completo e dois terão 50% de desconto. O total descontado da transação é de US$ 45 (15 + 15 + 7,50 + 7,50), que é US$ 15 (25%) de desconto do total descontado de US$ 60. O desconto 2 é de apenas US$ 12 (20%).
- Dois produtos são US$ 20 cada, um produto é US$ 15 e o outro US$ 5. Nesse caso, a melhor combinação de desconto é uma aplicação do desconto 2 e uma aplicação do desconto 1. As tabelas a seguir ilustram os descontos.

Para ler as tabelas, use um produto de uma linha e um produto de uma coluna. Por exemplo, na tabela do desconto 1, quando você combina os dois produtos de US$ 20, você receberá US$ 10 de desconto. Na tabela do desconto 2, quando você combina o produto de US$ 15 e o de US$ 5, você receberá US$ 4 de desconto.

![Exemplo que usa quatro produtos para os mesmos dois descontos.](./media/overlapping-discount-combo-03.jpg)

Primeiro, encontramos o maior desconto disponível de quaisquer dois produtos usando qualquer desconto. As duas tabelas mostram o valor de desconto de todas as combinações dos produtos. As partes protegidas das tabelas representam um dos casos em que um produto é emparelhado com ele mesmo, o que não podemos fazer, ou um emparelhamento reverso de dois produtos que produz o mesmo valor de desconto e pode ser ignorado. Olhando as tabelas, é possível ver que o desconto 1 para os dois itens de US$ 20 é o maior desconto disponível dos dois descontos em todos os quatro produtos. (Esse desconto é realçado em verde na primeira tabela.) Isso deixa apenas o produto de US$ 15 e o de US$ 5. Olhando as duas tabelas novamente, você pode ver que, para esses dois produtos, o desconto 1 oferece um desconto de US$ 2,50, enquanto o desconto 2 oferece um desconto de US$ 4. Portanto, selecionamos o desconto 2. O desconto total é de US$ 14. Para facilitar a visualização dessa discrepância, veja duas tabelas adicionais que mostram o a porcentagem de desconto em vigor para todas as combinações de dois produtos possíveis para os descontos 1 e 2. Somente metade da lista de combinações é incluída, pois, para esses dois descontos, a ordem na qual os dois produtos são colocados no desconto não importa. O desconto mais alto em vigor (25%) é destacado em verde, e o desconto em vigor inferior (10%) é destacado em vermelho.

![Percentual de desconto em vigor para todas as combinações de dois produtos para ambos os descontos.](./media/overlapping-discount-combo-04.jpg)

> [!NOTE]
> Quando os preços variam e dois ou mais descontos competem, a única maneira de garantir a melhor combinação de descontos é avaliar os dois descontos e compará-los.

## <a name="total-possible-combinations"></a>Combinações totais possíveis

Esta seção continua o exemplo da seção anterior. Nós adicionaremos mais produtos e outro desconto, e veremos quantas combinações devem ser calculadas e comparadas. A tabela a seguir mostra o número de combinações de desconto possíveis conforme a quantidade de produto aumenta. A tabela mostra o que acontece em ambos quando houver dois descontos se sobrepondo, como no exemplo anterior, e quando há três descontos se sobrepondo. O número de combinações possíveis de descontos que devem ser avaliados logo excede o que até um computador rápido pode calcular e compara rápido o suficiente aceitável para transações de varejo.

![Número de combinações de desconto possíveis conforme a quantidade de produto aumenta.](./media/overlapping-discount-combo-05.jpg)

Quando quantidades ainda maiores ou descontos mais sobrepostos são aplicados, o número total de combinações de desconto possível rapidamente entra na casa dos milhões, e o tempo necessário para avaliar e selecionar a melhor combinação possível rapidamente torna-se notória. Algumas otimizações foram feitas no mecanismo de preço para reduzir o número total de combinações que devem ser avaliadas. Porém, como o número de descontos sobrepostos e as quantidades em uma transação não são limitados, um número maior de combinações sempre precisará ser avaliado toda vez que houver descontos sobrepostos. Esse problema é o problema que o método de avaliação de valor marginal aborda.

## <a name="marginal-value-method"></a>Método de valor marginal

Para resolver o problema de um número exponencialmente elevado de combinações que devem ser avaliadas, uma otimização existe, que calcula o valor por produto compartilhado de cada desconto no grupo de produtos que dois ou mais descontos pode ser aplicado. Nos referimos a este valor como **valor marginal** do desconto para os produtos compartilhados. O valor marginal é o aumento médio por produto no valor de desconto total quando os produtos compartilhados são incluídos em cada desconto. O valor marginal é calculado pegando o valor de desconto total (DTotal), subtraindo o valor de desconto sem os produtos compartilhados (DMenos\\ Compartilhado) e dividindo a diferença pelo número de produtos compartilhados (ProductsShared).

![Fórmula para calcular o valor marginal.](./media/overlapping-discount-combo-06.jpg)

Após o valor marginal de cada desconto em um grupo compartilhado de produtos ser calculado, os descontos são aplicados aos produtos compartilhados na ordem do valor marginal maior para o menor. Para este método, todas as possibilidades restantes de desconto não são comparadas sempre depois que uma única instância de um desconto é aplicada. Em vez disso, os descontos sobrepostos são comparados uma vez e depois aplicados em ordem. Nenhuma comparação adicional é feita. Você pode configurar o limite para trocar para o método de valor marginal na guia **Desconto** da página **Parâmetros do Commerce**. O tempo aceitável para calcular o desconto total varia entre as indústrias de varejo. Porém, esse tempo geralmente cai na variação de diversos milissegundos a um segundo.


[!INCLUDE[footer-include](../includes/footer-banner.md)]