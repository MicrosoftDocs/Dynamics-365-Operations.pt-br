---
title: Custos de fluxo inverso
description: Este tópico apresenta o conceito de custo de fluxo inverso usado para Lean manufacturing.
author: cvocph
manager: tfehr
ms.date: 04/10/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LeanCosting, LeanCostingTimeBucket
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 272063
ms.assetid: 62a2a7da-ff79-49bf-a6e8-29460ba5252f
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: 0c8ef901afacd4ae191f2d01114bbf4bac38b9cd
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4422388"
---
# <a name="backflush-costing"></a>Custos de fluxo inverso

[!include [banner](../includes/banner.md)]

Este tópico apresenta o conceito de custo de fluxo inverso usado para Lean manufacturing. 

O custo de Lean manufacturing permite ao fluxo de produção usar o método de acumulação de custos conhecido como custos de fluxo inverso. No método de acumulação de custos, os materiais diretos consumidos são acumulados na conta de custo do trabalho em andamento (WIP) do fluxo de produção. O grupo de modelos de estoque de custo padrão é usado. Os produtos recebidos do fluxo de produção são deduzidos do WIP no seu custo padrão. A principal diferença entre custos de fluxo inverso e custo padrão é que, nos custos de fluxo inverso, as variações não são calculadas por kanban ou produto finalizado. Em vez disso, as variações são calculadas por fluxo de produção durante um período. Esse método apresenta um conceito que é realmente de lean manufacturing para relatar consumo de materiais. Quantidades separadas dedicadas de materiais não são relatadas para um kanban ou uma ordem de produção. Em vez disso, os lotes ou as unidades de manuseio de material completos são preparados para o fluxo de produção. Depois que os lotes ou as unidades de manuseio de material são registrados como vazios, eles são declarados como consumidos. O consumo avançado pode ser usado, dependendo da [configuração do fluxo de produção](../production-control/lean-manufacturing-modeling-lean-organization.md). Para que o consumo avançado possa ser usado, as organizações precisam fazer com que os materiais desapareçam no WIP do fluxo de produção. Os custos de fluxo inverso periódicos determinam o valor efetivo do WIP ao final do período. Essa determinação é baseada nas unidades de manuseio de material kanban e no status dos trabalhos kanban. Os desvios entre os valores efetivos e os valores reais do WIP por grupo e item de custos são explicados e exibidos como variações.

## <a name="configuring-backflush-costing"></a>Configuração de custos de fluxo inverso
Para habilitar custos, é preciso completar a seguinte configuração:

-   **Configure as contas do WIP para o grupo e o fluxo de produção.** As contas do WIP para fluxo de produção são especificadas no grupo produção. O fluxo de produção de custos de fluxo inverso calcula variações como a diferença no valor de WIP antes e depois de os custos de fluxo inverso serem executados para cada fluxo de produção. Portanto, recomendamos que você crie uma conta WIP para cada fluxo de produção.
-   **Atribua uma categoria de custo ao grupo de recursos.** Você precisa atribuir uma categoria de custo à categoria de tempo de execução da célula de trabalho. Para determinar variações por atividade, você deve criar uma categoria de custo para cada célula de trabalho. As categorias de custo para configuração e quantidade não são consideradas em custos para lean manufacturing. As contas WIP por grupo de recursos serão ignoradas nos custos de fluxo inverso. Para atividades subcontratadas, nenhuma categoria de custo é necessária. Em vez disso, o grupo de custo atribuído ao serviço será utilizado.
-   **Atribua grupos de custos.** Para habilitar a segmentação da contribuição de custo em um fluxo de produção, é preciso atribuir grupos de custo por tipo de grupo de custo:
    -   **Grupo de custo de material direto** - O material direto requer um grupo de custo que identifica a categoria do material para avaliação de custo. Esse grupo de custo permite uma exibição agregada de custo, WIP e variações por materiais diretos.
    -   **Grupo de custo de fabricação direta** - O grupo de custo de fabricação direta captura a contribuição de custo direto de recursos operacionais ao fluxo de produção. Esse grupo de custo permite uma exibição agregada de custo, WIP e variações por custo de fabricação direta.
    -   **Grupo de custo indireto** - O grupo de custo indireto é necessário para calcular a contribuição de custo indireto ao fluxo de produção. Esse grupo de custo permite uma exibição agregada de custo, WIP e variações por custo indireto.
    -   **Grupo de custo de terceirização direta** - O grupo de custo por serviços permite uma exibição agregada de custo atribuído e WIP e determina as variações de custo dos serviços subcontratados.
    -   **Grupo de custo para um produto finalizado** - Produtos finalizados requerem um grupo de custo que identifique a categoria do produto para avaliação de custo. Esse grupo de custo permite uma exibição agregada de custo, WIP e variações por categoria de produto. O custo padrão dos produtos é calculado por meio do cálculo de custo baseado na lista de materiais (BOM) e por meio do fluxo de produção e das regras kanban ou do roteiro.

### <a name="costing-sheet"></a>Folha de custos

A folha de custos molda a estrutura de custos da empresa e é criada pelos grupos de custo para classificar o custo. A folha de custos tem vários formulários. Mostra informações de custo de acordo com a estrutura que é criada nela. Na folha de custos, você também define a fórmula usada para calcular o custo indireto. A fórmula de cálculo pode ser baseada em quantidades, peso, massa ou valor.

-   **Defina uma versão de avaliação de custo.** Na versão de avaliação de custo, a empresa define como os custos devem ser mantidos. Uma versão de avaliação de custo pode conter um conjunto de registros de custo padrão ou um conjunto de registros de custo planejado, dependendo do tipo de custo atribuído à versão de avaliação de custo. A versão de avaliação de custo usada para determinar a avaliação de custo para Lean manufacturing deve se basear em custos padrão.
-   **Atribua um grupo de modelo de estoque para os produtos liberados.** Todos os produtos relacionados ao fluxo de produção devem ser atribuídos a um grupo de modelos de estoque que usa o grupo de modelos de estoque **Custo padrão**. Os custos padrão são mantidos por site e data de ativação. Para produto mestre, o grupo de modelos de estoque pode ser selecionado se os custos forem mantidos por grade ou produto mestre.
-   **Por definição, serviços subcontratados são serviços não inventariados.** Atividades subcontratadas não apresentam qualquer grupo de modelos de estoque. Para contabilizar corretamente uma atividade subcontratada, é necessário garantir que a atividade de serviço pertença a um grupo de modelos de estoque no qual a política de estoque seja definida como **Produto em estoque = Falso**.

Para produtos de saída, o cálculo de custo baseado no fluxo de produção requer que um custo padrão seja mantido pelos serviços relacionados a atividades subcontratadas. O grupo de custo atribuído aos serviços é usado para determinar as variações de custo da atividade subcontratada.

## <a name="cost-calculation-for-lean-manufacturing"></a>Cálculo do custo para Lean manufacturing
Para produtos fornecidos fora de um fluxo de produção, o cálculo da BOM deve ser baseado em uma versão de roteiro ou um fluxo de produção. O cálculo da BOM estima o custo de um produto e a divisão relacionada aos recursos e ao material necessários para criar o produto. A dedução da conta WIP para o fluxo de produção é realizada por meio da divisão de um produto por grupo de itens e de custo.

### <a name="calculation-that-is-based-on-the-production-flow"></a>Cálculo baseado no fluxo de produção

Lean manufacturing para Dynamics 365 Supply Chain Management não depende de roteiros. O cálculo de custo para produtos fornecidos em um fluxo de produção pode ser baseado no próprio fluxo de produção. Antes que o cálculo possa ser feito, deve ser criada uma regra kanban que forneça o produto fora do fluxo de produção. Se for possível fornecer um produto de vários fluxos de produção no mesmo site na data de cálculo, você pode selecionar o fluxo de produção para o cálculo da BOM. Na página **Fluxo de produção padrão**, você pode configurar um fluxo de produção padrão de cada item. Se houver várias regras kanban para o mesmo produto no mesmo fluxo de produção ativo na data de cálculo, o cálculo selecionará a primeira regra kanban ativa para o cálculo.

### <a name="calculation-that-is-based-on-the-route"></a>Cálculo baseado no roteiro

O cálculo baseado no roteiro é tão válido quanto aquele baseado em um fluxo de produção. No entanto, o cálculo baseado em um roteiro não usa a avaliação de custo para a funcionalidade de Lean manufacturing. O roteiro deve usar requisições de origem para grupos de recursos. Para evitar variações sistemáticas, ele também deve usar as mesmas células de trabalho ou, pelo menos, as mesmas categorias de custo. Além disso, você deve evitar categorias de custo para configuração e quantidade. Elas não ajudam a calcular o custo em uma divisão mais granular que os custos de fluxo inverso de Lean manufacturing. Para determinar qual opção (fluxo de produção ou roteiro) deve ser usada para calcular custos, considere os resultados da divisão de custo. A versão que mais se aproxima da realidade e que produz menos variações de modo geral é a melhor opção. Em um ambiente de lean manufacturing no qual um produto é fornecido por um único fluxo de produção e por uma regra kanban, o cálculo baseado no fluxo de produção é provavelmente mais preciso. No caso de produtos que podem ser fornecidos por Lean manufacturing e ordens de produção no mesmo site ou que podem apresentar vários fluxos de produção ou várias regras kanban no mesmo fluxo, um cálculo pode ser mais preciso se for baseado em uma versão de roteiro criada especificamente para o cálculo de custo, não para a produção. O cálculo do fluxo de produção deve ser usado para calcular os produtos que envolvem subcontratação. Os modelos de custo para subcontratação por meio de ordens de produção e subcontratação em Lean manufacturing estão usando duas abordagens diferentes. O lean manufacturing apresenta um novo tipo de grupo de custo, **Terceirização direta**, para calcular serviços subcontratados.

## <a name="material-consumption"></a>Consumo de materiais
Quando o material é consumido do estoque para o WIP, o custo de materiais é adicionado ao WIP no seu custo padrão real para um grupo de custo. Essa operação ocorre nas seguintes condições:

-   Os problemas do kanban são lançados para linhas de separação do kanban que atualizam o estoque.
-   São concluídos os trabalhos de transferência que atualizam o estoque na separação mas não no recebimento (transferência de materiais do estoque para o WIP).

## <a name="receiving-products-from-the-production-flow"></a>Recebimento de produtos do fluxo de produção
Os produtos são recebidos do fluxo de produção nas seguintes condições:

-   São concluídos os trabalhos de processo que apresentam **Atualizar estoque no recebimento** definido como **Sim**.
-   São concluídos os trabalhos de transferência que atualizam o estoque no recebimento, mas que apresentam **Atualizar estoque na separação** definido como **Não** (transferência de WIP para estoque). Esta opção permite receber todos os produtos fora de um fluxo de produção independentemente da BOM e da configuração de roteiro. O processo apenas segue os fluxos físicos. Esta opção é especialmente adequada para o recebimento de subprodutos, coprodutos ou sucata fora de um fluxo de produção e para a correção apropriada do saldo de custo do WIP do fluxo de produção.

Produtos recebidos do fluxo de produção são deduzidos do WIP.

## <a name="products-in-wip"></a>Produtos no WIP
O modelo de WIP de Lean manufacturing permite usar o status da unidade de manuseio de material kanban para gerenciar o material, produtos semiacabados e produtos acabados que fazem parte do WIP.

-   **Atribuído** - O kanban pode apresentar material consumido que é contabilizado no WIP.
-   **Recebido** - Se o kanban se referir a uma última atividade na qual **Atualizar estoque no recebimento** está definido como **Não**, isso representa uma unidade de manuseio de material completa de um produto ou um produto semifinalizado não registrado no estoque.

Observe que o material no WIP não é visível em visões gerais do estoque disponível. Entretanto, é visível em visões gerais da quantidade de kanbans.

## <a name="consuming-products-in-wip"></a>Consumo de produtos no WIP
Os produtos em WIP são consumidos quando as unidades de manuseio de material kanban correspondentes são esvaziadas. Um sinal vazio do kanban não gera uma transação de custo ativa, mas ele terá efeito quando os próximos custos de fluxo inverso forem executados. As unidades de manuseio de material kanban esvaziadas não são mais contabilizadas como disponíveis e, portanto, calculadas como consumidas no período.

### <a name="automatic-empty-registration"></a>Registro vazio automático

Kanbans programados ou de evento podem ser definidos como registro vazio automático na regra kanban:

-   **Quando as unidades de manuseio de material forem recebidas** - Por padrão, no caso do kanban programado, o material é declarado como consumido quando o último trabalho do kanban é concluído. Em caso de kanbans de quantidade fixa, essa opção só é recomendada para kanbans de compartimento único, pois ela retorna o cartão à origem da demanda sempre que um kanban é recebido no destino final.
-   **Quando a requisição da origem for registrada** - Esta opção está disponível apenas para kanbans de evento e é a opção padrão para eles. Em conexão com o WIP, esta opção é útil para mantê-lo limpo, porque os kanbans de componentes em WIP são esvaziados automaticamente e, portanto, consumidos no WIP, quando o kanban principal é preparado.

Em conclusão, unidades de manuseio de material kanban podem ser atribuídas (= em processo), recebidas (= completas) ou esvaziadas. Não há esvaziamento parcial. Portanto, para habilitar um registro de consumo preciso, é importante que você delimite as quantidades de produto de um kanban para que sejam menores que o consumo por período. Produtos movidos para o chão da fábrica em grandes lotes envolvendo dias ou semanas de demanda não devem ser consumidos para WIP. Em vez disso, esses produtos devem ser mantidos em estoque.

## <a name="backflush-costing"></a>Custos de fluxo inverso
Você deve executar custos de fluxo inverso para avaliar o WIP periodicamente e gerar um status de fechamento de período que calcula as variações de material, mão de obra e custos indiretos. As variações calculadas são lançadas nas contas de variação. No processo de custos de fluxo inverso, os fluxos de produção a a entidade legal são usados na mesma execução de lote. Quando os custos de fluxo inverso são executados em um lote, o processamento pode ser de vários threads por fluxo de produção. O período de fluxo inverso é definido por uma data final. Você não poderá lançar novas transações para uma data quando o cálculo de custos de fluxo inverso foi executado. Você jamais deve executar custos de fluxo inverso para a data atual antes que o dia chegue realmente ao fim. Os custos de fluxo inverso realizam as seguintes etapas:

1.  Determine as quantidades não usadas no fluxo de produção a partir da data final do período. Após a execução dos custos de fluxo inverso, é possível exibir as quantidades não usadas na data da avaliação de custo executada na caixa de diálogo **Quantidades não usadas**.
2.  Calcule a utilização líquida realizada do fluxo de produção durante o período.
3.  Limpe o WIP dos produtos e consumo de recursos realizado.
4.  Calcule as variações de produção para custo padrão do período. **Para componentes consumidos no período:**
    -   Atualize financeiramente as quantidades líquidas realizadas de materiais que o fluxo de produção consumiu durante o período. O sistema processa ordens PEPS (primeiro a entrar, primeiro a sair) nas transações de estoque individual para atualizar financeiramente transações atualizadas fisicamente em relação ao fluxo de produção, até que as quantidades líquidas realizadas do período sejam atingidas.
    -   As transações são divididas financeiramente para mapear as quantidades consumidas exatas.
    -   Quantidades não usadas no WIP do fluxo de produção permanecem em status de atualizadas fisicamente.

    **Para quantidades de produção concluídas do período:**
    -   Atualize financeiramente as transações de estoque em relação às quantidades do período concluídas.

    **Para os custos de conversão:**
    -   As transações de custo de conversão aplicadas (transações de roteiro) que foram registradas para o período são atualizadas financeiramente.
    -   Todo custo de fabricação direta é atualizado financeiramente. Todos os trabalhos de processo do kanban concluídos durante o período são acumulados.
    -   Todos os custos indiretos calculados para o material consumido no período são calculados e deduzidos do WIP. Os custos indiretos restantes são lançados como variação.

5.  Calcule as variações de produção para custo padrão. A variação é calculada por grupo de custo.







[!INCLUDE[footer-include](../../includes/footer-banner.md)]