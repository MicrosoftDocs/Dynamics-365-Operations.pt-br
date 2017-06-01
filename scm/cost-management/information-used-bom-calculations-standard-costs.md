---
title: "Cálculos de BOM com custos padrão"
description: 
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BOMCalcDialog, BOMCalcGroup, BOMCalcTable, ProdParmBOMCalc
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 65571
ms.assetid: ca17e6dd-b16a-4bbc-8682-b16345ab9906
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 0f539e286b9f16aec3c73934403ba41f2641e6e0
ms.contentlocale: pt-br
ms.lasthandoff: 05/25/2017


---

# <a name="bom-calculations-with-standard-costs"></a>Cálculos de BOM com custos padrão

[!include[banner](../includes/banner.md)]




As informações sobre o item comprado usado no cálculo de BOM de custo padrão incluem as seguintes:
-   Custo − os custos de um item comprado são mantidos como registros de custo específicos ao site em uma versão de avaliação de custo para os custos padrão. Cada registro de custo tem uma data efetiva e a data do cálculo de BOM determina qual registro de custo será usado. Por exemplo, um cálculo de BOM com uma data de cálculo futura pode usar um registro de custo com um status pendente e uma data efetiva no futuro.
-   Grupo de custos − o grupo de custos atribuído a um item comprado fornece a base para a segmentação do custo nos custos calculados de um item fabricado.
-   As condições de aviso incorporadas no grupo de cálculo de BOM do item permitem que o cálculo de BOM identifique problemas potenciais. Isso pode acontecer quando o item comprado tem um custo zero, uma quantidade zero em uma BOM ou um registro de custo vencido. As condições de aviso aplicáveis podem ser substituídas quando se inicia um cálculo de BOM.

As informações sobre o item fabricado usado no cálculo de BOM de custo padrão incluem as seguintes:
-   Quantidade de ordem padrão para estoque − a quantidade de ordem padrão do item para estoque age como o tamanho de lote contábil padrão para amortizar custos constantes em um cálculo de BOM. O tamanho de lote contábil também reflete o múltiplo da quantidade de ordem, se especificado.
-   As condições de aviso incorporadas no grupo de cálculo de BOM do item permitem que o cálculo de BOM identifique problemas potenciais. Por exemplo, quando o item fabricado não tem uma BOM ou um roteiro. As condições de aviso aplicáveis podem ser substituídas quando se inicia um cálculo de BOM.

As informações sobre a lista de materiais usada no cálculo de BOM de custo padrão incluem as seguintes:
-   Versão da BOM − a versão da BOM atribuída ao item fabricado tem datas iniciais e finais efetivas, e um status para aprovada e ativa. A versão da lista pode ser para toda a empresa ou específica a um site e, opcionalmente, pode refletir pontos de quebra de quantidade.
-   Quantidade de item de linha de BOM − em geral, um componente tem uma quantidade variável necessárias, mas ela pode ser uma constante. A quantidade do componente costuma ser expressa para a produção de um item pai, mas pode ser expressa por centenas ou por milhares para lidar com problemas de precisão decimal. A quantidade do componente também pode ser calculada com base em medidas.
-   Sucata de item de linha de BOM − um componente pode ter uma quantidade variável ou constante para sucata planejada.
-   Datas de validade de item de linha de BOM − um componente pode ter datas de validade iniciais e finais.
-   Tipo de produção de item de linha de BOM − o tamanho do lote de custos para amortizar custos constantes refletirá a quantidade de cálculo de BOM e um modo detalhado de execução por encomenda, porque o cálculo de BOM supõe que o componente fabricado será produzido na quantidade exata e não na quantidade de ordem padrão.
-   Sub-BOM para um componente fabricado − opcionalmente, um componente fabricado pode ter uma versão de BOM especificada, que pode ser usada em vez da versão de BOM ativa atual do item em um cálculo de BOM.
-   Sub-roteiro para um componente fabricado − opcionalmente, um componente fabricado pode ter uma versão de roteiro especificada, que pode ser usada em vez da versão de roteiro ativa atual do item em um cálculo de BOM.
-   Número de operação e o impacto de porcentagens de sucata de operação − o número de operação vincula um componente a uma operação específica, e as operações podem ter uma porcentagem de sucata. A vinculação permite que os cálculos de BOM considerem as porcentagens de sucata e as porcentagens de sucata cumulativa em várias operações na quantidade necessária do componente.
-   Ignorar item de linha de BOM em cálculos de custo − um componente pode ser ignorado para fins de cálculo de BOM.

As informações do recurso de operações usadas em um cálculo de BOM de custo padrão incluem:
-   Custos por hora − os custos por hora associados a um recurso de operações são expressos em termos de categorias de custo atribuídas ao tempo de preparação e ao tempo de execução. Essas categorias de custo devem ser identificadas para grupos de recursos e recursos de operações. Os custos por hora associados a uma categoria de custo podem ser específicos a um site ou para toda a empresa.
-   Custos unitários − alguns ambientes de fabricação atribuem custos de recurso de operações por unidade produzida, que é expressa como uma categoria de custo diferente para quantidade. Por exemplo, os custos relativos à quantidade podem refletir preços de peça para mão-de-obra ou um fabricante de tintas pode atribuir os custos de recurso de operações por litro produzido.
-   Substituição de informações de recurso de operações em operações de roteiro − as informações de recursos sobre categorias de custo são herdadas pelas operações, nas quais elas podem ser substituídas. Os cálculos de BOM usam as informações de categoria de custo especificadas nas operações de roteiro.
-   Grupo de custos para uma categoria de custo − o grupo de custos atribuído a uma categoria de custo fornece a segmentação do custo nos custos calculados de um item fabricado. Por exemplo, grupos de custos diferentes podem ser usados para segmentar os custos calculados associados a máquinas e a mão-de-obra ou ao tempo de preparação e execução.

As informações do roteiro usado em um cálculo de BOM de custo padrão incluem:
-   Versão do roteiro - a versão do roteiro atribuída ao item fabricado tem datas iniciais e finais efetivas, e um status para aprovada e ativa. A versão do roteiro deve ser específica a um site e, opcionalmente, pode refletir pontos de quebra de quantidade.
-   Tempo de operação de roteiro − o tempo pode ser especificado para o tempo de preparação e de execução. O tempo em horas costuma ser expresso para a produção de um item pai, mas pode ser expresso por centenas ou por milhares para lidar com problemas de precisão decimal.
-   Tempo de operação de roteiro para recursos secundários − um recurso secundário tem o mesmo número de operação que o principal e o mesmo tempo de operação de roteiro. Por exemplo, uma operação pode exigir uma máquina como o recurso principal e mão-de-obra e ferramentas como recursos secundários.
-   Porcentagem de sucata de operação de roteiro - os cálculos de BOM incluirão porcentagens de sucata e porcentagens de sucata cumulativa em várias operações. Isso se aplica ao tempo necessário para operações de roteiro e à quantidade necessária dos componentes vinculados a números de operação.
-   Categorias de custo para uma operação de roteiro − as informações de recurso de operações sobre categorias de custo são herdadas pelas operações, nas quais elas podem ser substituídas. Os cálculos de BOM usam as informações de categoria de custo especificadas nas operações de roteiro.

As informações de custos gerais indiretos de fabricação usadas em um cálculo de BOM de custo padrão incluem:
-   Sobretaxa − uma fórmula de cálculo de sobretaxa reflete uma porcentagem de valor, como 100 por cento, associada a um grupo de custos específico, como mão-de-obra.
-   Taxa − uma fórmula de cálculo de taxa reflete uma quantidade unitária, como BRL 10,00 por hora, associada a um grupo de custos específico, como mão-de-obra.
-   Custos gerais indiretos baseados em tempo versus baseado em material − os custos gerais indiretos de fabricação podem ser associados a operações de roteiro ou componentes de materiais.

As informações da versão de custo usadas em um cálculo de BOM de custo padrão incluem:
-   Tipo de custos − a versão de custo deve conter custos padrão. Várias restrições se aplicam a cálculos de BOM que usam custos padrão. Por exemplo, essas restrições especificam que os encargos diversos devem ser incluídos em custos unitários e que o modo de detalhamento do cálculo de BOM deve ser de nível único.
-   Princípio de fallback obrigatório − a versão de custo pode obrigar o uso de um princípio de fallback, como o uso de uma versão de custo especificada ou os registros de custo ativo. O princípio de fallback obrigatório em geral se aplica a uma versão de custo que representa as atualizações incrementais em uma abordagem de duas versões para atualizações de custo.
-   Sinalizador de bloqueio para custos pendentes − um sinalizador de bloqueio pode impedir os cálculos de BOM do custo pendente para itens fabricados.
-   Data inicial especificada − a data inicial especificada age como a data de cálculo padrão para todos os cálculos de BOM que envolvem a versão de custo.
-   Site especificado − um site especificado limita os cálculos de BOM ao próprio site.
-   Conteúdo da versão de custo deve incluir custos − o conteúdo deve incluir custos. Opcionalmente, ele pode incluir preços de venda a fim de calcular os preços de venda sugeridos para itens fabricados.

Várias fontes de informações podem ser especificadas ao iniciar um cálculo de BOM. Isso inclui o site, a data do cálculo e a versão de custo.






