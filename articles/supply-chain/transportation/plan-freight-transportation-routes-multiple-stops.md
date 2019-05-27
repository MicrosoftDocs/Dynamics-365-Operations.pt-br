---
title: Planejar rotas de transporte de frete com várias paradas
description: Este artigo descreve os vários elementos que você usa para planejar rotas de transporte no Dynamics 365 for Finance and Operations.
author: MarkusFogelberg
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TMSHubMaster, TMSLoadBuildTemplates, TMSRateRouteWorkbench, TMSRouteGuide, TMSRoutePlan, TMSRouteWorkbench, WHSLoadTemplate
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 90013
ms.assetid: 50d6f58c-f1c8-4321-9e83-8445cec57a85
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 36cb454477c0d296246c061d2573954a81c9efd7
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1553967"
---
# <a name="plan-freight-transportation-routes-with-multiple-stops"></a>Planejar rotas de transporte de frete com várias paradas

[!include [banner](../includes/banner.md)]

Este artigo descreve os vários elementos que você usa para planejar rotas de transporte no Microsoft Dynamics 365 for Finance and Operations.

Você pode usar guias de rota e planos de rota para rotas de transporte complexos que têm várias paradas. Se o mesmo roteiro for usado regularmente, você pode configurar uma rota programada.

## <a name="route-plans"></a>Planos do roteiro
Um plano de rota contém segmentos de rota que fornecem informações sobre as paradas visitadas no roteiro e transportadoras que são usadas para cada segmento. Você deve definir as paradas na rota como hubs. Um hub pode ser um fornecedor, um depósito, um cliente ou até mesmo um lugar recarregando onde você altera a transportadora. Para cada segmento, você pode definir "taxas especiais" para encargos diversos. Eis alguns exemplos:

-   Despesas de viagens de negócios para os segmentos determinados
-   Encargos para uma separação acima das mercadorias
-   Encargos de descarte das mercadorias

Cada plano de rota deve ser associado a um guia de rota.

## <a name="route-guides"></a>Guias de roteiros
Um guia de rota define os critérios de correspondência de uma carga a um plano de rota específico. Por exemplo, você pode especificar um hub de origem e um hub de destino, os limites para o volume do recipiente ou peso e uma transportadora, serviço ou grupo. Guias de rota estão disponíveis na página **Bancada do roteiro de taxa**, onde onde cargas podem ser adequadas às rotas manual ou automaticamente. Se a guia roteiro for para um roteiro agendado, também está disponível na página **Bancada de criação de carga**.

## <a name="scheduled-routes"></a>Roteiros agendados
Uma rota programada é um plano de rota predefinida que tem uma agenda para as datas de remessa. Roteiros agendados e rotas não agendadas são diferentes da forma que os carregamentos são atribuídos a eles. Se você atribuir uma rota não programada usando a Bancada de trabalho de roteiro de taxa, apenas a carga e o guia de rota são validados. Se você atribuir uma rota agendada, as datas e os endereços de pedidos e os hubs e a data no plano de rota também são considerados. Você não precisa usar a página de Bancada de trabalho de roteiro de taxa para atribuir manualmente as cargas a um roteiro agendado. Em vez disso, você pode usar a Bancada de criação de carga para sugerir que as cargas sejam criadas com base nos endereços de clientes e datas de entrega de ordens de venda para uma determinada rota programada. Para rotas agendadas, o plano de rota irá ter corrigido hubs de origem e de destino. Normalmente, o serviço de transportadora será o mesmo para todos os segmentos, mas eles podem ser diferentes. Os hubs de destino são criados usando os códigos postais dos clientes que visitaram no roteiro. Várias agendas de rota podem ser definidas para o plano de uma rota. O plano de rota deve ser associado a um guia de rota. No entanto, para rotas agendadas, o plano pode ser associado com apenas um guia de rota. O agendamento de rota é usado somente para criar rotas reais na página **Agenda de rota**. Você pode usar o modelo padrão de carga ao propor cargas sobre a Bancada de trabalho de criação de carga.

## <a name="load-building-workbench"></a>Bancada de criação de carga
A Bancada de trabalho de criação de carga utiliza os endereços de clientes e datas de entrega de ordens de venda e as rotas agendadas que estão disponíveis para propor uma carga. Por padrão, os valores do roteiro são inseridos sobre a bancada de trabalho. No entanto, você pode selecionar uma data "de" que é anterior à data "de" no roteiro. Quando uma carga é proposta, o endereço de entrega e a data de entrega de todas as ordens de venda são verificadas. Se o código postal do endereço de entrega corresponde ao código postal de um hub no plano de rota e a data de entrega está dentro do intervalo selecionado nos critérios, a ordem de venda é proposta para o carregamento. A capacidade de carregar modelo também é considerada. Apenas uma carga é proposta ao mesmo tempo. Se você tiver uma ordem de venda que não será incluída, você terá que usar um modelo de carga diferente (por exemplo, um modelo de carga de um caminhão ou contêiner) ou planejar uma entrega extra.



