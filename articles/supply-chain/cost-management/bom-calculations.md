---
title: "Cálculos de BOM"
description: "Os cálculos de preço de venda e de acúmulo de custo são conhecidos como cálculos de lista de materiais (BOM), e você os inicia na página Cálculos. Este tópico fornece informações sobre cálculos de BOM."
author: AndersGirke
manager: AnnBe
ms.date: 04/10/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BOMCalcDialog, BOMCalcTable, CostingVersion, InventItemPrice, SalesQuotationTable, SalesTable, SMAServiceOrderTable
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 273763
ms.assetid: c6fa3348-eafa-4847-9132-e65c5f55cbf4
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.dyn365.ops.version: AX 7.0.0
ms.search.validFrom: 2016-02-28
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: ad00a3b5e41892aaa705fd8eafa52cc199e1d806
ms.contentlocale: pt-br
ms.lasthandoff: 11/03/2017

---

# <a name="bom-calculations"></a>Cálculos de BOM

[!include[banner](../includes/banner.md)]


Os cálculos de preço de venda e de acúmulo de custo são conhecidos como cálculos de lista de materiais (BOM), e você os inicia na página Cálculos. Este tópico fornece informações sobre cálculos de BOM.

Os cálculos de preço de venda e de acúmulo de custo são conhecidos como cálculos de lista de materiais (BOM), e você os inicia na página **Cálculos**. Você pode usar a página **Cálculos** para executar as seguintes tarefas:

-   Calcular o custo de um item fabricado e gerar um registro de custo de item associado em uma versão de avaliação de custo.
-   Calcular o preço de venda de um item fabricado e gerar o registro de preço de venda de um item associado em uma versão de avaliação de custo.

A forma como você usa a página **Cálculos** varia levemente, dependendo da forma como você inicia os cálculos de BOM. A forma como você usa a página **Cálculos** também varia quando os cálculos de BOM envolvem uma versão de avaliação de custo para custos padrão ou custos planejados e depende de várias políticas definidas na versão do custo em uso nos cálculos de BOM. **Observação:** uma variação da página **Cálculos** é usada no contexto de um item de linha de ordem de venda, de cotação de venda ou de ordem de serviço. Esses cálculos são conhecidos como cálculos de BOM específicos para uma ordem. Um cálculo de BOM específico para uma ordem não gera um registro de custo de item em uma versão de avaliação de custo. Em vez disso, gera um registro de cálculo que aparece na página **Detalhes do cálculo da BOM**. O registro de cálculo inclui um custo calculado e um preço de venda calculado. A página **Cálculos** pode ser aberta para um único item fabricado ou para uma versão de avaliação de custo:

-   Para calcular os custos de um único item fabricado, inicie os cálculos de BOM na página **Preço de item**. A página **Cálculos** herda o identificador do item. A versão de avaliação de custo, a versão de BOM, a versão de roteiro, a quantidade de cálculo, a data de cálculo e o site devem ser especificados.
    -   Por padrão, a versão de BOM e a versão de roteiro são definidas como versões ativas para o item, o site, a data e a quantidade de cálculo. Contudo, você pode substituir os valores padrão por versões aprovadas.
    -   Por padrão, a quantidade de cálculo é definida como a quantidade de ordem padrão do item. No entanto, você pode substituir o valor padrão.
    -   A data de cálculo ou o site pode ser obrigatório pela versão do custo ou os valores especificados pelo usuário podem ser definidos quando a data ou o site não é obrigatório na versão de avaliação de custo. Uma data de cálculo futura determina como registros de custo pendente são usados. Os cálculos de BOM usam um registro de custo pendente com a data inicial mais próxima da data de cálculo, mas não posterior a ela.
-   Para calcular custos para todos os itens fabricados ou para itens selecionados ou atualizar itens quando usados, inicie os cálculos de BOM na página **Configuração de versão de avaliação de custo** ou na página **Manutenção de versão de avaliação de custo**. A página **Cálculos** herda a versão de avaliação de custo.
    -   Em relação aos cálculos, supõem-se o uso da versão da BOM ativa e a versão do roteiro para um item fabricado (e para o site, a data e a quantidade relacionados), a menos que um componente fabricado tenha uma sub-BOM ou um sub-roteiro especificado.
    -   Em relação aos cálculos, supõem-se que a quantidade de ordens padrão seja usada para itens fabricados. A quantidade de ordem padrão fornece a base para calcular quantidades de componente, determinar as versões da BOM e as versões de roteiro relevantes (quando você usa BOMs e roteiros sensíveis à quantidade) e amortizar os custos constantes. No entanto, quando um componente fabricado tem uma linha de BOM do tipo **Produção** ou **Fornecedor**, ou quando você usa um modo de detalhamento de execução por encomenda para os cálculos de BOM, essa suposição não se aplica, pois as quantidades refletem a quantidade de cálculo especificada.
    -   A data de cálculo ou o site pode ser obrigatório pela versão do custo ou os valores especificados pelo usuário podem ser definidos quando a data ou o site não é obrigatório na versão de avaliação de custo.

Outras variações nos cálculos de BOM refletem o tipo de custo e as restrições da versão de avaliação de custo:

-   Os cálculos de BOM que usam custos padrão devem ser restringidos por diretivas de versão do custo porque as restrições ajudam a garantir princípios de custo padrão. Esses princípios exigem a aplicação de restrições sobre o uso de custos padrão para itens comprados, um modo de detalhamento de nível único e a inclusão de encargos diversos nos custos unitários.
-   Os cálculos de BOM que usam custos planejados não precisam seguir princípios de custo padrão. Esses cálculos podem usar modos de detalhamento diferentes, fontes alternativas de dados de custo para itens comprados e a aplicação opcional de restrições na versão do custo.

### <a name="bom-calculations-that-use-standard-costs"></a>Cálculos de BOM que usam custos padrão

As diretivas na versão do custo (para custos padrão) podem obrigar a aplicação de cinco diretivas de cálculo de BOM. A opção **Registrando restrição** na versão do custo obriga a aplicação de uma dessas políticas, na qual os encargos diversos devem ser incluídos no preço unitário. Os encargos diversos para itens comprados podem ser digitados manualmente, ao passo que para os itens fabricados eles refletem a amortização calculada dos custos constantes. A opção **Restrição de cálculo** na versão do custo obriga a aplicação de outras quatro diretivas de cálculo de BOM:

-   A fonte das contribuições de custo dos itens comprados deve ser baseada nos custos padrão. Em outras palavras, os cálculos de BOM devem usar os registros de custo de item na versão do custo especificada ou no fallback que contém os custos padrão.
-   Para ajudar a garantir o cálculo exato e consistente dos custos padrão, o modo de detalhamento deve ser de nível único.
-   Para ajudar a garantir resultados consistentes ao calcular o preço de venda dos itens, a configuração de lucro deve ser obrigatória. A configuração de lucro pode ser usada, e os registros de preço de venda do item podem ser gerados se a versão de avaliação de custo permitir conteúdo de preços de venda.
-   O princípio de fallback deve ser obrigatório e pode ser definido como **Nenhum**, **Ativo** (para registros de custo ativos) ou **Versão de avaliação de custo** (para uma versão do custo especificada).

### <a name="bom-calculations-that-use-planned-costs"></a>Cálculos de BOM que usam custos planejados

As diretivas na versão do custo (para custos planejados) podem, opcionalmente, obrigar a aplicação de cinco políticas de cálculo de BOM. Como alternativa, as políticas só podem fornecer valores padrão. A opção **Registrando restrição** na versão do custo determina se a diretiva de cálculo de BOM sobre encargos diversos será obrigatória ou será usada como um valor padrão. Os encargos diversos podem ser incluídos opcionalmente no preço unitário. A opção **Restrição de cálculo** na versão do custo determina se as outras quatro políticas de cálculo de BOM serão obrigatórias ou usadas como valores padrão.

-   A fonte das contribuições de custo de um item comprado pode ser os registros de custo de item em uma versão de avaliação de custo. Como alternativa, a fonte pode ser definida por um grupo de cálculo de BOM atribuído ao item. Por exemplo, o grupo de cálculos de BOM pode definir contratos comerciais de preço de compra como a fonte dos dados de contribuição de custo.
-   O modo de detalhamento pode ser de nível único, vários níveis, fazer por encomenda ou ser baseado no item de linha de BOM. O modo de detalhamento para o tipo de linha de BOM replica a lógica de cálculo de custo para previsões de ordem de produção.
-   A configuração de lucro pode ser obrigatório ou ser um valor padrão. A configuração de lucro pode ser usada, e os registros de preço de venda do item podem ser gerados se a versão de avaliação de custo permitir conteúdo de preços de venda.
-   O princípio de fallback pode ser obrigatório ou ser um valor padrão. O princípio de fallback pode ser definido como **Nenhum**, **Ativo** (para registros de custo ativos) ou **Versão de avaliação de custo** (para uma versão do custo especificada).

Os cálculos de BOM geram mensagens de aviso e outros tipos de mensagens. Várias diretivas de cálculo de BOM determinam os tipos de mensagens. As condições de aviso aplicáveis são definidas no grupo de cálculo de BOM atribuído aos itens. No entanto, você pode substituir essas condições de aviso ao iniciar um cálculo de BOM. Ao usar o princípio de fallback, geralmente é útil exibir as informações de fallback como mensagens de informações. Ao tentar atualizar custos calculados para itens com registros de custo ausentes, também é útil se a mensagem de informações identificar itens que não foram atualizados.

## <a name="bom-calculations-that-use-the-fallback-principle"></a>Cálculos de BOM que usam o princípio de fallback
As situações a seguir ilustram dois usos do princípio de fallback:

-   **Abordagem de duas versões para atualizações de custo padrão** - Uma versão de avaliação de custo pode conter alterações incrementais nos custos padrão, como registros de custo pendentes que representam novos itens ou alterações de custo. Nessa situação, o princípio de fallback pode identificar o uso dos custos padrão ativos contidos em outras versões de avaliação de custo.
-   **Simulação do efeito das alterações de custo usando custos planejados** - Uma versão de custos para custos planejados pode conter alterações incrementais para fins de simulação. Essa versão de avaliação de custo incluirá registros de custo pendentes que representam as alterações de custo simuladas para itens, categorias de custo e fórmulas de cálculo de custo indireto. Nessa situação, o princípio de fallback pode identificar o uso dos custos padrão ativos contidos em outras versões de avaliação de custo.

## <a name="bom-calculation-of-a-suggested-sales-price"></a>Cálculos de BOM de um preço de vendas sugerido
Ao usar uma abordagem de custo mais marcação, o preço de vendas calculado do item reflete o conjunto de porcentagens de definição de lucro especificado para o cálculo de BOM e os custos que são associados com os itens componentes do item, operações de roteiro e custos gerais indiretos de fabricação aplicáveis. A marcação reflete as porcentagens de definição de lucro atribuídas a grupos de custo e os grupos de custo que são atribuídos para itens, categorias de custo para operações de roteiro as fórmulas de cálculo de custo indireto para custos gerais indiretos de fabricação. Os conjuntos de porcentagens de definição de lucro são **Padrão**, **Lucro 1**, **Lucro 2** e **Lucro 3**. No conjunto Lucro 1, por exemplo, uma porcentagem de definição de lucro de 50% pode ser definida para um grupo de custo atribuído a material comprado e uma porcentagem de definição de lucro de 80% pode ser definida para um grupo de custo atribuído a categorias de custo para operações de roteiro. O contexto do cálculo de BOM determina como os resultados de um preço de vendas calculado serão tratados.

-   **Cálculo de BOM para um item e versão de avaliação de custo especificada** - O cálculo de BOM gera um registro de preço de vendas pendente na versão de custo. Esse registro de preço de vendas fornece o ponto de partida para exibir os detalhes de cálculo (por exemplo, na página **Calcular custo do item**). O registro de preço de compras age principalmente como informação de referência e não é usado como base para um preço de vendas em ordens de venda.
-   **Cálculo de BOM específico a uma ordem** - Uma variação da página **Cálculo de BOM** é usado no contexto da ordem de venda, cotação de vendas ou item de linha de ordem de serviço. Um cálculo de BOM específico de uma ordem não gera um registro em uma versão do custo. Em vez disso, gera um registro de cálculo que aparece na página **Resultados de cálculo de BOM**. Esse registro de cálculo fornece o ponto de partida para exibir os detalhes de cálculo (por exemplo, na página **Calcular custo do item**). Informações sobre um registro de cálculo selecionado podem ser transferidas para o item de linha que o originou. Por exemplo, o preço de venda calculado pode ser transferido para um item de linha de ordem de venda.

## <a name="order-specific-bom-calculations"></a>Cálculos de BOM específicos a uma ordem
Um cálculo de BOM específico a uma ordem representa uma variação de um cálculo de BOM para um item fabricado. O cálculo de BOM específico para uma ordem é realizado no contexto de um item de linha de uma ordem de venda, uma cotação de venda ou uma ordem de serviço. Um cálculo de BOM específico para uma ordem gera um registro de cálculo que aparece na página **Resultados de cálculo de BOM**. O registro de cálculo inclui um peso calculado, um custo calculado baseado nos registros de custo ativo e um preço de venda calculado. O registro de cálculo que cada cálculo de BOM específico para uma ordem gera na página **Resultados de cálculo de BOM** é identificado de forma única, por um número de cálculo. Opcionalmente, os resultados de um registro de cálculo podem ser transferidos para o item de linha de origem. Um cálculo de BOM específico para uma ordem não é o mesmo que um cálculo de BOM para um item fabricado de duas maneiras:

-   Um cálculo de BOM específico para uma ordem não gera um registro de custo de item em uma versão de avaliação de custo. Portanto, as políticas de cálculo de BOM não se aplicam quando um registro de custo de item é criado ou quando um registro de custo é substituído.
-   Um cálculo de BOM específico a uma ordem sempre usa os registros de custo ativo para componentes, categorias de custo e fórmulas de cálculo de custo indireto.






