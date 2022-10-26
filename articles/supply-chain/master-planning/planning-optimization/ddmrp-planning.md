---
title: Planejamento orientado por demanda
description: O artigo descreve como gerar ordens planejadas para itens configurados como pontos de separação.
author: t-benebo
ms.date: 06/30/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2022-06-30
ms.dyn365.ops.version: 10.0.28
ms.openlocfilehash: f1e2cfca47d507c8de7f9323bb8e4262a0e90949
ms.sourcegitcommit: 3e04f7e4bc0c29c936dc177d5fa11761a58e9a02
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2022
ms.locfileid: "9689149"
---
# <a name="demand-driven-planning"></a>Planejamento orientado por demanda

[!include [banner](../../includes/banner.md)]
[!INCLUDE [preview-banner](../../includes/preview-banner.md)]
<!-- KFM: Preview until further notice -->

O artigo descreve como gerar ordens planejadas para itens configurados como pontos de separação.

## <a name="net-flow-and-qualified-demand"></a>Fluxo líquido e demanda qualificada

Durante o planejamento mestre, o sistema aplica o conceito de *fluxo líquido* para estabelecer a quantidade disponível efetiva com base no estoque disponível real, além do estoque que está na ordem (ordens de fornecimento existentes que ainda não foram recebidas), menos o que é referido como *demanda qualificada* (vendas futuras qualificadas), conforme mostrado na ilustração a seguir. Quando o sistema está determinando a qual zona de buffer pertence um item e qual deve ser a quantidade encomendada, ele avalia o fluxo líquido, não o estoque disponível real.

![Exemplo de um gráfico de cálculo de fluxo líquido.](media/ddmrp-net-flow-example.png "Exemplo de um gráfico de cálculo de fluxo líquido")

Quando uma ordem planejada for disparada durante uma execução de planejamento, a quantidade encomendada será o nível máximo menos o fluxo líquido. Para atribuir uma prioridade de ordem, o sistema usa a funcionalidade de [planejamento baseado em prioridade](priority-based-planning.md) em vez das datas de requisito. O DDMRP (Planejamento de Requisitos de Material Orientado por Demanda) atribui a prioridade de uma ordem planejada com base na quantidade encomendada como uma porcentagem do estoque máximo. Na ilustração anterior, a quantidade encomendada é 53% da quantidade máxima. Portanto, a prioridade da ordem para o reabastecimento será 53. (Para o contexto, 0 é a prioridade mais alta, e 100 é a prioridade mais baixa.)

A *demanda qualificada* é a demanda em atraso, além da demanda de hoje, mais picos de ordem qualificados no futuro. A ilustração a seguir mostra um exemplo de níveis de demanda para hoje (12 de junho) e os próximos três dias. O DDMRP permite definir um limite de picos de ordem para identificar a demanda que exceda as expectativas normais. Se o limite for definido como 25 peças, duas das datas futuras que serão mostradas na ilustração serão qualificadas como picos de ordem. Você deve atribuir um limite de pico de ordem para cada produto individualmente usando a respectiva página **Cobertura do item**, conforme descrito em [Configurar buffers para um item do ponto de separação](ddmrp-buffer-profile-and-levels.md#set-up-buffers).

![Exemplo de um gráfico de cálculo de demanda qualificado.](media/ddmrp-net-qualified-demand-example.png "Exemplo de um gráfico de cálculo de demanda qualificado")

Desde que não haja nenhuma demanda em atraso, agora você pode adicionar a demanda de hoje (18) às quantidades dos dois picos da ordem (29 e 26) para obter uma demanda qualificada de 73. Mesmo que haja demanda para 23 de junho, observe que ela não está incluída no cálculo do fluxo líquido porque o DDMRP dispara ordens planejadas de forma diferente dos tradicionais grupos de cobertura de planejamento.

## <a name="generating-planned-orders-with-ddmrp"></a>Gerando ordens planejadas com o DDMRP

Durante uma execução de planejamento, o sistema criará uma nova ordem planejada se o fluxo líquido para um item ficar abaixo do ponto de reabastecimento. Ao usar o DDMRP, você geralmente fará uma execução de planejamento todos os dias. Portanto, a verificação dos níveis de estoque é feita basicamente uma vez ao dia para determinar quais itens devem ser reabastecidos.

A ilustração a seguir mostra o exemplo de uma situação em que você tem uma ordem de 18 peças em 20 de junho, 29 peças em 21 de junho, 26 peças em 22 de junho e 20 peças em 23 de junho. Como o limite de pico é definido como 25 peças, duas dessas ordens são sinalizadas como picos. Há 220 peças desse item disponíveis.

![Exemplo de planejamento 1.](media/ddmrp-planning-example-1.png "Exemplo de planejamento 1")

Se você executar o planejamento mestre agora, uma ordem planejada será gerada se o fluxo líquido for ficar abaixo do ponto de reabastecimento (219 peças neste exemplo).

![Exemplo de planejamento 2.](media/ddmrp-planning-example-2.png "Exemplo de planejamento 2")

Este exemplo produz uma ordem de compra planejada para uma quantidade de 130, que é igual ao nível máximo menos o fluxo líquido. A ordem planejada recebe uma prioridade de 53,07, com base na sua porcentagem de quantidade máxima. Como esses valores foram encontrados em 20 de junho, o sistema cria uma ordem planejada com data de 20 de junho mais o prazo de entrega separado para o item (cinco dias úteis neste exemplo). Portanto, como cinco dias úteis são uma semana a partir de hoje, a ordem planejada é datada de 27 de junho.

> [!NOTE]
> A Otimização de Planejamento calcula somente itens separados usando o DDMRP. Todos os outros itens são calculados usando MRP (Planejamento de Requisitos de Material) padrão.
