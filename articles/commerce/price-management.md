---
title: Gerenciamento de preços de vendas para varejo
description: Este tópico descreve os conceitos para criar e gerenciar os preços de venda do Dynamics 365 Commerce.
author: ShalabhjainMSFT
manager: AnnBe
ms.date: 05/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-retail
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.search.region: Global
ms.search.industry: retail
ms.author: shajain
ms.search.validFrom: 2018-03-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a90f5706c87d398f495fae40f42f6c2d408b1c2a
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4410065"
---
# <a name="retail-sales-price-management"></a>Gerenciamento de preços de vendas de varejo

[!include [banner](includes/banner.md)]

Este tópico fornece informações sobre o processo de criação e gerenciamento de preços de venda do Dynamics 365 Commerce. Ele concentra-se nos conceitos que estão envolvidos neste processo e nos efeitos das várias opções de configuração para preços de venda.

## <a name="terminology"></a>Terminologia

Os seguintes termos são usados neste tópico.

| Termo | Definição, uso e observações |
|---|---|
| Preço | O valor de uma única unidade de venda do produto em um cliente do ponto de venda (PDV) ou em uma ordem de venda. Neste tópico, o termo *preço* sempre se refere ao preço de venda, não ao preço do estoque ou ao preço de custo. |
| Preço base | O preço definido no campo **Preço** em um produto liberado. |
| Preço do contrato comercial | O preço definido em um produto ou em uma variante usando um contrato comercial do tipo **Preço (vendas)**. |
| Melhor preço | Quando mais de um preço ou desconto puder ser aplicado a um produto, refere-se ao valor do preço menor e/ou o valor do desconto maior que produz o menor valor líquido possível que o cliente deve pagar. Neste tópico, o conceito de melhor preço é sempre indicado como “o melhor preço.” Este melhor preço é diferente e não deve ser confundido com o valor de enumeração **Melhor preço** para um modo de concorrência de desconto. |

## <a name="price-groups"></a>Grupos de preços

Os grupos de preços estão no centro do gerenciamento de preços e desconto no Commerce. Os grupos de preços são usados para atribuir preços e descontos para entidades de comércio (isto é, canais, catálogos, afiliações e programas de fidelidade). Como os grupos de preços são usados para todos os preços e descontos, é muito importante você planejar como os usará, antes de começar.

Por si só, um grupo de preços é apenas um nome, uma descrição, e, opcionalmente, uma prioridade de preços. O ponto principal sobre os grupos de preços é que eles são usados para gerenciar os relacionamentos muitos para muitos que os descontos e preços têm com as entidades de comércio.

A ilustração a seguir mostra como os grupos de preços são usados. Nesta ilustração, observe que o "Grupo de preços" está literalmente no centro do gerenciamento de preços e desconto. As entidades de comércio que você pode usar para gerenciar diferenciais de preços e descontos ficam à esquerda e os registros de preço e desconto reais ficam à direita.

![Grupos de preços](./media/PriceGroups.png "Grupos de preços")

Ao criar grupos de preços, você não deverá usar um único grupo de preços para vários tipos de entidades de comércio. Caso contrário, poderá ser difícil determinar porque um preço ou desconto específico está sendo aplicado a uma transação.

Como a linha tracejada vermelha na ilustração mostra, o Commerce dá suporte à funcionalidade principal do Microsoft Dynamics 365 de um grupo de preços que é definido diretamente em um cliente. Entretanto, nesse caso, você obtém apenas os contratos comerciais de preço de venda. Se quiser aplicar preços específicos do cliente, recomendamos que você não defina grupos de preços diretamente no cliente. Em vez disso, você deverá usar afiliações. 

Observe que, se o grupo de preços for definido no cliente, então esse grupo de preços será associado ao cabeçalho da ordem de venda das ordens criadas para esse cliente. Se o usuário alterar o grupo de preços no cabeçalho da ordem, o grupo de preços antigo será substituído pelo novo grupo de preços somente para a ordem atual. Por exemplo, o grupo de preços antigo não afetará a ordem atual, mas ainda estará associado ao cliente para ordens futuras.

As seções a seguir fornecem mais informações sobre as entidades de comércio que você pode usar para definir preços distintos quando os grupos de preços forem usados. A configuração de preços e descontos para todas essas entidades é um processo de duas etapas. Essas etapas podem ser feitas em qualquer ordem. Entretanto, a ordem lógica é para definir os grupos de preços nas entidades primeiro, porque essa etapa é provavelmente uma configuração ocasional que é feita durante a implementação. Em seguida, conforme os preços e os descontos são criados, é possível definir grupos de preço nesses preços e descontos individualmente

### <a name="channels"></a>Canais

No setor de comércio, é muito comum ter diferentes preços em diferentes canais. Os dois principais fatores que afetam os preços específicos do canal são custos e condições do mercado local.

- **Custos** – Quanto mais longe estiver um canal do produto de origem, maior o custo para armazenar um produto. Por exemplo, produtos frescos têm uma prateleira limitada e outros requisitos de produção específicos (por exemplo, uma estação de crescimento). Durante o inverno, a alface fresca provavelmente custa mais nos climas do norte do que nos climas do sul. Se estiver definindo preços para canais em uma grande área geográfica, provavelmente você vai querer definir preços diferentes em canais diferentes.
- **Condições do mercado local** – Uma loja que tenha um concorrente direto do outro lado da rua será muito mais sensível ao preço do que uma loja que não tenha um concorrente direto nas proximidades.

### <a name="affiliations"></a>Afiliações

A definição geral de uma afiliação é um link ou associação a um grupo. No Commerce, as afiliações são grupos de clientes. As afiliações são ferramentas muito mais flexíveis para preço e descontos de clientes que o conceito principal de Microsoft Dynamics 365 de grupos de cliente e grupos de descontos. Primeiro, uma afiliação pode ser usada para os preços e descontos, enquanto o preço não de varejo tem um grupo diferente para cada tipo de desconto e de preço. Em seguida, um cliente pode pertencer a várias afiliações, mas pode pertencer somente a um grupo de preços não de varejo de cada tipo. Finalmente, embora as afiliações possam ser definidas de modo que estejam vinculadas a um cliente, elas não precisam ser específicas. Uma afiliação ad hoc pode ser usada para clientes anônimos no PDV. Um exemplo típico de um desconto anônimos de afiliação é um desconto para idosos ou estudantes no qual um cliente pode receber um desconto apenas mostrando um cartão de associação do grupo.

Embora as afiliações sejam mais frequentemente associadas aos descontos, você também pode usá-las para definir o preço diferencial. Por exemplo, quando um varejista vende para um funcionário, ele pode querer alterar o preço de venda, em vez de aplicar um desconto sobre o preço regular. Como outro exemplo, um varejista que vende tanto para clientes do consumidor como para clientes da empresa pode oferecer melhores preços aos clientes da empresa, com base no volume de compra. As afiliações permitem esses dois cenários.

### <a name="loyalty-programs"></a>Programas de fidelidade

Em relação aos preços e descontos, os programas de fidelidade são basicamente uma afiliação que tem um nome especial. Os preços e os descontos podem ser definidos para um programa de fidelidade, assim como podem ser definidos para uma afiliação. Entretanto, a forma que os clientes recebem o preço de fidelidade durante uma transação ou uma ordem difere da forma que eles recebem o preço de afiliação. Os clientes podem obter o preço de fidelidade somente se um cartão de fidelidade for adicionado à uma transação. Quando um cartão de fidelidade é adicionado a uma transação, o programa de fidelidade também é. O programa de fidelidade então habilita preços e descontos especiais.

Os programas de fidelidade pode ter várias camadas, e os descontos podem diferir para níveis diferentes. Assim, os varejistas podem dar recompensas maiores aos clientes frequentes, sem precisar colocar esses clientes manualmente em um grupo especial.

Os programas de fidelidade têm a funcionalidade adicional, além de preços e descontos. Entretanto, da perspectiva de preços e descontos, eles têm as mesmas afiliações.

### <a name="catalogs"></a>Catálogos

Alguns varejistas usam catálogos físicos ou virtuais para comercializar produtos e precificá-los, focados nos grupos de clientes. Como parte do modelo de negócios para marketing de destino através de um catálogo, esses varejistas podem definir preços diferenciais em vários catálogos. O Microsoft Dynamics 365 suporta esse recurso permitindo que você defina descontos e preços específicos do catálogo, exatamente como você define descontos específicos do canal ou da afiliação. Ao editar um catálogo, é possível associar grupos de preços ao catálogo, como você associa-os a um canal, afiliação ou programa de fidelidade.

### <a name="best-practices-for-price-groups"></a>Práticas recomendadas para grupos de preços

Não use um grupo de preços para vários tipos de entidades. Em vez disso, use um conjunto de grupos de preços para os canais, um conjunto diferente de grupos de preços para afiliações ou programas de fidelidade, etc. Você pode usar um prefixo ou sufixo no nome do grupo de preços para agrupar visualmente vários tipos de grupos de preços que você está usando.

Evite definir grupos de preço diretamente em um cliente. Em vez disso, use uma afiliação. Dessa forma, você pode atribuir todos os tipos de preços e descontos para clientes, e não apenas contratos comerciais de preço de venda.

## <a name="pricing-priority"></a>Prioridade de preço

Por si só, prioridade de preços é apenas um número e uma descrição. As prioridades de preços podem ser aplicadas aos grupos de preços, ou podem ser aplicadas diretamente aos descontos. Quando as prioridades de preços são usadas, elas permitem que um varejista substitua o princípio do melhor preço, controlando a ordem na qual os preços e descontos são aplicados aos produtos. Um número de prioridade maior de preços é avaliado antes de um número de prioridade menor. Além disso, se um preço ou desconto for encontrado em qualquer número de prioridade, todos os preços ou descontos que tiverem números de prioridade menores serão ignorados.

O preço e o desconto podem vir de duas prioridades diferentes de preços, pois as prioridades de preços se aplicam a preços e os descontos independentemente.

Para usar a prioridade do preço para preços, é necessário atribuir uma prioridade de preços a um grupo de preços e depois criar um contrato comercial de preço de venda para esse grupo de preços.

O recurso de prioridade de preço foi introduzido para oferecer suporte ao cenário no qual um varejista deseja aplicar preços mais alto em um conjunto específico de lojas. Por exemplo, um varejista definiu preços regionais para a costa leste dos Estados Unidos, mas quer preços mais altos para alguns produtos das lojas de Nova York porque é mais caro vender alguns produtos na cidades e/ou porque o mercado local suporta um preço mais alto.

Conforme descrito na seção "Melhor preço" deste tópico, o mecanismo de precificação geralmente seleciona o menor dos dois preços. Portanto, o varejista geralmente evita usar o maior dos dois preços em uma loja que tem os dois grupos de preços na costa leste e em Nova York. Para resolver esse problema antes de o recurso de prioridade de preço ser introduzido, o varejista teve que definir preços para cada produto duas vezes, e não atribuir os dois grupos de preços. Como alternativa, o varejista teve que criar grupos de preço adicional para isolar produtos com um preço mais alto de produtos com preços usuais, mais baixo.

Entretanto, o recurso de prioridade de preços permite que o varejista crie uma prioridade de preços para preços de loja que seja maior do que a prioridade do preço para preços regionais. Como alternativa, o varejista pode criar uma prioridade de preços apenas para preços de loja e deixar os preços regionais na prioridade padrão de definição de preços, que é 0 (zero). As duas configurações ajudam a garantir que os preços de loja sempre serão usados antes de preços regionais.

### <a name="pricing-priority-example"></a>Exemplo da prioridade de preço

Vamos ver um exemplo no qual os preços da loja substituem outros preços.

Um varejista nacional define a maioria dos preços por região e tem quatro regiões: nordeste, sudeste, meio-oeste e oeste. Isso identificou vários mercados de custo alto que podem suportar preços mais altos. Esses mercados estão na área de Nova York, Chicago e São Francisco.

Por exemplo, vamos nos concentrar na região nordeste. A loja 1 está em Boston e a loja 2 em Manhattan. Para a loja de Boston, dois grupos de preços estão associados ao canal: nordeste de Loja 1. Para a loja de Manhattan, três grupos de preços estão associados ao canal: nordeste, Nova York e Loja 2.

O varejista configura duas prioridades de preços: custo alto tem um número de prioridade de 5 e os preços da Loja tem um número de prioridade de 10. (Lembre-se que, por padrão, a prioridade de preço é 0 \[zero\], e um preço ou desconto que tenha um número de prioridade maior é usado antes de um preço ou desconto que tenha um número de prioridade menor). Para o grupo de preços do nordeste, a prioridade de preços fica com o valor padrão **0** (zero). Para o grupo de preços de Nova York, a prioridade de preços é definida como **5**, pois Nova York tem um mercado de custo alto. Para os grupos de preços da Loja 1 e da Loja 2, a prioridade de preço é definida como **10**.

Dois produtos que o varejista vende são produto 1, uma camiseta e produto 2, calça jeans de uma marca específica.

| Produto | Preço do nordeste | Preço de Nova York | Preço da loja |
|---|---|---|---|
| Camiseta | $15 | Não Definir | Não Definir |
| Calça jeans | $50 | $70 | Não Definir |

A camiseta é vendida pelo mesmo preço (isto é $ 15), tanto nas lojas de Boston como de Manhattan porque somente um preço é definido no grupo de preços do nordeste que está associado aos dois canais. A calça jeans é vendida por $50 na loja de Boston porque esse preço é o único que está disponível nessa loja. Porém, na loja de Manhattan, os dois preços estão disponíveis: $50 e $70. Como a prioridade de preço de 5 para o grupo de preços de Nova York é maior que a prioridade de preço de 0 (zero) para o grupo de preços do nordeste, o preço será aumentado para $ 70 no sistema PDV.

> [!NOTE]
> Para cada prioridade de preço, é necessária uma passagem completa pela lógica do mecanismo de preço de varejo. Entretanto, para manter o desempenho do cálculo de preço e desconto, você deve usar as prioridades de preço com moderação.

## <a name="types-of-prices"></a>Tipos de preços

No Microsoft Dynamics 365, você pode definir o preço de um produto em três locais:

- Diretamente no produto (preço base)
- Em um contrato comercial de preço de venda
- Em um ajuste de preço

O preço base e o preço de contrato comercial fazem parte do Dynamics 365 principal e estão disponíveis, mesmo que você não use o Commerce. A funcionalidade de ajuste de preço ficará disponível somente no Commerce. A próxima seção fornece mais informações sobre cada uma dessas opções para definir preços e explicar como as opções trabalham juntas.

## <a name="setting-prices"></a>Definição de preços

### <a name="base-price"></a>Preço base

O local mais fácil para definir o preço de um produto é diretamente no produto. O valor que você define diretamente em um produto geralmente é mencionado como o preço base do produto. Você define o preço base no campo **Preço** na guia **Vender** da página **Detalhes do produto liberado**. O valor que você inserir é a moeda da empresa. Por padrão, o preço é para uma quantidade 1 da unidade de medida (UDM) definida no campo **Unidade** na guia **Vender**. O preço real por unidade de um produto é baseado na UDM, a quantidade de preço e na moeda.

Se um produto tiver um preço para todos, o preço base oferece a forma mais eficiente de gerenciar o preço desse produto. Mesmo que você use contratos comerciais para definir preços, você também pode definir o preço base de um produto. Depois, se você não usar um contrato comercial **Tudo**, você terá um preço de fallback que é usado quando nenhum contrato comercial é aplicado.

Se uma moeda do canal for diferente da moeda da empresa, o preço base nesse canal é determinado usando a conversão da moeda no preço que é definido no produto.

Embora a unidade de preço não esteja em um cenário comum, o mecanismo de preço a apoia. Se a unidade de preço for definida como um valor diferente de **0** (zero), o preço por unidade é igual a Preço ÷ Unidade de preço. Por exemplo, se o preço o produto for $10,00 e a unidade de preço for 50, o preço de uma quantidade 1 é $ 0,20 (=$10,00 ÷ 50).

### <a name="sales-price-trade-agreement"></a>Contrato comercial do preço de venda

Usando o diário de contrato comercial, você pode criar contratos comerciais de preço de vendas para cada produto. No Microsoft Dynamics 365, há três escopos de contratos comerciais de preço de venda: **Tabela**, **Grupo** e **Tudo**. O escopo do cliente determina os clientes aos quais um contrato comercial do preço de venda é aplicado.

Um contrato comercial do preço de venda de **Tabela** é para um cliente único que é definido diretamente no contrato comercial. Esse cenário não é um cenário típico de business-to-consumer (B2C). Porém, se ocorrer, o mecanismo do preço usa os contratos comerciais da **Tabela** ao determinar o preço.

Um contrato comercial do preço de venda **Grupo** é o tipo que é mais frequentemente usado em conjunto. Fora do Commerce, os contratos comerciais do preço de vendas **Grupo** são para o grupo de clientes simples. Porém, no Commerce, o conceito de um grupo de clientes foi estendido, de forma que é um grupo do preço mais genérico. Um grupo de preço pode ser vinculado a um canal, uma afiliação, a um programa de fidelidade, ou um catálogo. Para informações detalhadas sobre grupos de preços, consulte a seção “Grupos de preços” anteriormente neste tópico.

> [!NOTE]
> Um preço do contrato comercial sempre é usado antes do preço base.

### <a name="price-adjustment"></a>Ajuste de preço

Como o nome implica, um ajuste de preço será usado para modificar o preço que foi definido diretamente no produto ou definido usando um contrato comercial. Um ajuste de preço pode ser usado somente para baixar o preço, não para aumentá-lo. Um ajuste de preço é a forma recomendada para os varejistas criarem, rastrearem e gerenciarem markdowns de preço para seus produtos ao longo do tempo.

Há três tipos de ajustes de preço: percentual de desconto, valor de desconto e preço. Um ajuste de preço do percentual de desconto ou do tipo de valor de desconto é sempre aplicado a uma transação de venda. Porém, um ajuste de preço do tipo de preço é aplicado somente se o preço ajustado for menor que o preço que foi definido usando o preço base ou o preço do contrato comercial. Portanto, se o preço que está definido em um ajuste de preço for maior que o preço não ajustado, o ajuste de preço não será usado.

## <a name="determining-price-for-a-product-in-a-transaction"></a>Determinando preço de um produto em uma transação

O cálculo do preço e do desconto em uma transação usa o princípio de localizar o melhor preço do cliente. De acordo com esse princípio, se mais de um preço for encontrado, o preço mais baixo será usado. Além disso, é usada a combinação de descontos que produz o valor de desconto maior para toda a transação. Em alguns casos, o menor desconto deve ser usado em um único produto, de modo que os descontos adicionais possam ser aplicados a outros produtos na transação.

A única exceção ao princípio de localizar o melhor preço do cliente é uma opção para descontos de menos caros de compra combinada. Esta opção habilita os descontos menos caros que favorecem o varejista quando os produtos são selecionados e agrupados. Portanto, quando uma transação incluir mais produtos que os necessários para qualificar o desconto menos caro, o mecanismo de preço seleciona os produtos que produzem o menos valor de desconto possível para o cliente.

O mecanismo de preço retorna três preços para cada produto: o preço base, o preço do contrato comercial e o preço fixo.

O preço base é apenas a propriedade no produto e é igual para todos em qualquer parte.

No contrato comercial do preço de vendas, se a opção **Localizar próximo** for definida como **Sim**, o preço mais baixo que for encontrado para contratos comerciais do preço de vendas é usado como o preço do contrato comercial. Os contratos comerciais podem ser localizados usando grupos de preço ou o código de conta **TUDO** . Como alternativa, os contratos comerciais podem ser atribuídos diretamente a um cliente. Se a opção **Localizar próximo** for definida como **Não**, será usado o primeiro preço do contrato comercial que for encontrado. Se nenhum contrato comercial de preço de venda for encontrado, então o preço do contrato comercial será definido como igual ao preço base.

O preço ativo será calculado usando o preço do contrato comercial e aplicando o ajuste de preço maior que é aplicado ao produto. Se nenhum ajuste de preço for encontrado, ou se o preço ativo calculado for maior do preço do contrato comercial, o preço ativo será definido como igual ao preço do contrato comercial. Lembre-se de que você não pode aumentar o preço de um produto usando um ajuste de preço. Os ajustes de preço aplicáveis podem ser localizados apenas usando os grupos de preços atribuídos a um canal, a um catálogo, uma afiliação ou um programa de fidelidade.

## <a name="category-price-rules"></a>Regras de preço da categoria

O recurso de regras de preço de categoria no Commerce fornece uma maneira fácil de criar novos contratos comerciais para todos os produtos de uma categoria. Este recurso também permite localizar automaticamente contratos comerciais para os produtos da categoria e expirá-los.

Quando você seleciona a opção expirar contratos comerciais existentes, o sistema cria um novo diário de contrato comercial para os produtos na categoria que tem um contrato comercial ativo. Porém, o diário deve ser lançado manualmente. Além disso, as regras de preços da categoria podem localizar contratos comerciais existentes somente se você estiver usando a mesma regra de preço (isto é, se você criar uma nova regra de preço que usa a mesma categoria de antes). Se não estiver usando a mesma regra de preço, os contratos comerciais existentes não serão expirados.

Os preços podem ser aumentados ou reduzidos usando os campos **Regra de preço** e **Base de preço** das regras de preços da categoria.

- No campo **Regra de preço**, selecione o tipo de alteração de preço a ser usado:

    - **Marcação** – Uma porcentagem da base de preço é usada para calcular o preço de venda. Por exemplo: um produto que custa 10,00 e é vendido por 15,00, tem uma marcação de 50%.
    - **Margem** – uma porcentagem do preço de venda que é usado para calcular o valor do lucro. Por exemplo: um produto que custa 10,00 e é vendido por 15,00, tem uma margem de 33.3%.
    - **Valor fixo** – um valor adicionado à base de preço que é usada para calcular o preço de venda. Por exemplo: um produto que custa 10,00 e é vendido por 15,00, tem um valor fixo de 5,00.

- No campo **Preço base** selecione o tipo de preço a ser modificado:

    - **Custo base** – o valor que o varejista pagou ao varejista..
    - **Preço base** – o preço de venda antes de contratos comerciais e ajustes de preço são aplicados.
    - **Preço atual** – o preço de venda depois que os contratos comerciais e ajustes de preço forem aplicados.

Para atualizar facilmente os preços de vários produtos de categorias diferentes, você pode usar as categorias de produtos complementares juntas com as regras de preço da categoria.

## <a name="best-practices"></a>Práticas Recomendadas

O Microsoft SQL Server Express é usado frequentemente para bancos de dados do canal do custo (grátis). Lembre-se que o SQL Server Express tem limitações de hardware e limites de volume de dados. Se não planejar corretamente, você pode atingir rapidamente os limites de tamanho dos dados do SQL Server Express. Essa conta não se aplica somente à definição de preços, mas também em outras áreas do produto. Aqui estão algumas práticas recomendadas que podem ajudar a reduzir o tamanho de seus dados:

- Se estiver usando os contratos comerciais, e a sua alteração de preços, você deve expirar contratos comerciais definindo uma data final. Com o tempo, esta abordagem ajuda a reduzir o número de contratos comerciais que são mantidos em bancos de dados do canal. Isso também ajuda a reduzir o valor dos dados que o algoritmo de cálculo de preços deve trabalhar.
- Se seus preços variam por grade de produto, considere o preço da base do produto como o preço da grade mais comum. Use os contratos comerciais somente para os preços da grade que são exceções. Esta abordagem ajudar a reduzir o número de registros do contrato comercial. Como é fácil importar dados para o Microsoft Dynamics 365, você pode tentar importar um contrato comercial para cada grade de cada produto. Porém, esta abordagem pode gerar vários contratos comerciais que têm o mesmo valor. Portanto, pode aumentar desnecessariamente o tamanho dos seus dados.
- O Commerce processa preços específicos da grade para do mais específico para o menos específico. Se uma dimensão do produto não afeta o preço, você não precisa definir contratos comerciais para ele. Por exemplo, um produto fica disponível em três cores e quatro tamanhos, mas esse preço varia somente por tamanho. Se definir um contrato comercial para cada grade, você cria 12 registros. Em vez disso, você pode definir um contrato comercial apenas para cada tamanho e deixar a dimensão de Cor em branco. Nesse caso, você gera apenas quatro registros.

    Como alternativa, se todo valor de uma dimensão produzir um preço diferente, você poderá definir um acordo comercial para o produto mestre e deixar todas as dimensões do produto em branco. Depois, defina um contrato comercial separado apenas para cada valor de dimensão que gera um preço diferente. Por exemplo, se o tamanho de XXL possui um preço maior, mas todos tamanhos restantes tiverem o mesmo custo, você exige somente dois contratos comerciais: um para produtos mestre e um para o tamanho de XXL.

## <a name="prices-that-include-tax-vs-prices-that-exclude-tax"></a>Os preços que incluem imposto versus preços que excluem imposto

Quando os preços de vendas forem definidos no Dynamics 365, você não especifica se o valor do preço que você está definindo inclui ou exclui o imposto. O valor é apenas o preço. Porém, a configuração **Preço inclui imposto** nos canais permitem configurar canais, de forma que eles incluam ou excluam imposto de preços. Esta configuração é definida no canal e pode até mesmo mudar em uma única empresa.

Se você trabalhar com tipos inclusivos e exclusivo de impostos, será muito importante que você defina preços corretamente porque a quantidade total que o cliente paga será alterada se a configuração **Preço inclui imposto** no canal for alterada.

## <a name="differences-between-retail-pricing-and-non-retail-pricing"></a>Diferenças entre o preço de varejo e o preço não de varejo

Um mecanismo de única definição de preços é usado para calcular preços em todos os canais: Call center, loja de varejo e lojas online. Isso ajuda a habilitar os cenários unificados de comércio.

O preço é criado para trabalhar com entidades de varejo, em vez das entidades não varejo. Especificamente, é criado para definir preços por loja, não por depósito.

O mecanismo de preços **não suporta** os seguintes recursos de preços:

- Não há suporte para a definição de preços por meio de dimensões de armazenamento do Local e Depósito. Se você especificar somente a dimensão do Site nos contratos comerciais, a definição de preços de mecanismo ignorará o Site e aplicará o contrato comercial a todos os sites. Se você especificar o Local e o Depósito, o comportamento será indefinido/não testado porque espera-se que os varejistas usem os grupos de preços de armazenamento para controlar os preços de cada loja/depósito.
- A definição de preços com base no atributo não é suportada.
- A passagem de desconto do fornecedor não é suportada.
- O mecanismo de preços de Supply Chain Management padrão oferece suporte ao cálculo de preços com base na "Data de remessa solicitada" e na "Data de recebimento solicitada", juntamente com a data atual. No entanto, os preços de varejo não oferecem suporte a esses valores no momento. O motivo é que para os cenários de B2C, os clientes não esperam a data de entrega solicitada afetar o preço do item. Em alguns casos, os varejistas têm operações B2B e B2C. Para operações B2B, é comum alterar os preços com base nas datas de entrega. Esses varejistas podem usar os preços de Supply Chain Management para seus negócios B2B e de varejo para seus negócios B2C. O preço varejo só aparecerá se o usuário do aplicativo for adicionado como um usuário do call center, de forma que os varejistas possam atribuir certos usuários que trabalharão com os preços de Supply Chain Management e atribuir outros que trabalharão com o Preço de varejo, ou seja, esses usuários deverão ser adicionados como usuários do call center. Além disso, a propriedade **Usar a data de hoje para calcular preços** na seção **Parâmetros de comércio > preços e descontos > Diversos** deve estar ativada. Dessa forma, eles podem manter o valor do parâmetro de contas a receber em uso para Data de remessa solicitada ou Data de recebimento solicitada para os preços de Supply Chain Management, mas os preços do varejo continuarão usando a data atual para o cálculo de preços.

Além disso, **somente** o mecanismo de preço suporta os seguintes recursos de preços:

- O preço está baseado em dimensões do produto, na ordem do preço da grade mais específica para o preço da grade menos específico para o preço do produto mestre. Um preço definido com duas dimensões de produtos (por exemplo, cor e tamanho) é usado antes de um preço definido usando somente uma dimensão de produtos (por exemplo, por tamanho.)
- O mesmo grupo de preços pode ser usado para controlar a definição de preços e descontos.

## <a name="pricing-api-enhancements"></a>Aprimoramentos na API de definição de preços

O preço é um dos fatores mais importantes que controla as decisões de compra de muitos clientes. Muitos deles comparam preços em vários sites antes de realizar uma compra. Para ajudar a garantir que ofereçam preços competitivos, os varejistas observam atentamente seus concorrentes e costumam oferecer promoções. Para ajudar esses varejistas a atrair clientes, é muito importante que a pesquisa de produtos, o recurso de navegação, as listas e a página de detalhes dos produtos mostrem os preços mais precisos.

Em uma próxima versão do Commerce, a API (interface de programação de aplicativos) **GetActivePrices** retornará preços que incluem descontos simples (por exemplo, descontos de linha única que não dependem de outros itens no carrinho). Assim, os preços exibidos são próximos do valor real que os clientes pagam pelos itens. Essa API incluirá todos os tipos de descontos simples: descontos baseados em afiliação, em fidelidade, em catálogo e em canal. Além disso, a API retornará os nomes e as informações de validade dos descontos aplicados, para que os varejistas possam fornecer uma descrição mais detalhada do preço e criar um senso de urgência se a validade do desconto expirar em breve.
