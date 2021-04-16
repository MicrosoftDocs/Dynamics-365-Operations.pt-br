---
title: Substituir o princípio de reserva padrão por materiais em produção
description: Este tópico descreve como configurar um princípio de reserva padrão para cada grupo de modelo de item, para que diferentes princípios de reserva possam ser automaticamente aplicados a cada item que faz parte da lista de materiais (BOM) ou fórmula de ordem de lote.
author: johanhoffmann
ms.date: 12/10/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventModelGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-12-10
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: a1b2dd204c9a507dba387b0295f3021253e02dc4
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5814793"
---
# <a name="override-the-default-reservation-principle-for-materials-in-production"></a>Substituir o princípio de reserva padrão por materiais em produção

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]

O recurso *Substituir reserva de produção padrão* permite definir um princípio de reserva padrão para cada grupo de modelos de item. Portanto, diferentes princípios de reserva podem automaticamente ser aplicados em cada item que faz parte de uma lista de materiais (BOM) ou fórmula de ordem de lote. Você pode selecionar se cada grupo de modelos de item deve substituir o princípio de reserva padrão definido para uma ordem e qual princípio de reserva deve ser usado (*manual*, *estimativa*, *agendamento*, *liberação* ou *início*).

Ao criar uma ordem de produção ou ordem de lote, você será solicitado a selecionar o princípio de reserva que deve ser aplicado a essa ordem e todas as linhas da BOM ou linhas da fórmula. Quando o recurso *Substituir reserva de produção padrão* é usado, algumas ou todas as linhas da BOM ou da fórmula podem substituir esse princípio de reserva e usar o princípio de reserva definido para o grupo de modelos de itens relevantes.

Por exemplo, se você tem matérias-primas ou componentes que exigem trabalho de separação, as linhas da BOM ou fórmula que são criadas para esses produtos exigem uma reserva física, pois ela é um pré-requisito para a geração de trabalho de depósito. Normalmente, se quiser que a reserva ocorra automaticamente, selecione um dos seguintes princípios de reserva: *estimativa*, *agendamento*, *liberação* ou *início*. Por outro lado, se você tem materiais ou ingredientes que não exigem trabalho de separação, pois são consumidos diretamente de um local, você normalmente seleciona o princípio de reserva *manual*, que não faz reservas físicas nem gera trabalho de separação.

## <a name="turn-on-the-feature"></a>Ativar o recurso

Para que você possa usar o recurso, ele deve estar ativado no sistema. Os administradores podem usar as configurações de [gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar o status do recurso e ativá-lo. No espaço de trabalho **Gerenciamento de recursos**, o recurso está listado da seguinte forma:

- **Módulo:** *Controle de produção*
- **Nome do recurso:** *(Versão Preliminar) Substituir reserva de produção padrão*

## <a name="assign-a-production-reservation-policy-to-an-item-model-group"></a>Atribuir uma política de reserva de produção a um grupo de modelos de item

1. Vá para **Gerenciamento de custos \> Configuração das políticas contábeis de estoque \> Grupos de modelos de item**.
1. Crie ou selecione um grupo de modelos de item.
1. Na FastTab **Políticas de estoque**, marque a caixa de seleção **Substituir reserva de produção de item**.
1. No campo **Reserva**, selecione o princípio de reserva de itens que pertencem ao grupo de modelos selecionado. (Esses itens incluem itens que estão em uma linha da BOM ou da fórmula.)

    - **Manual** – os itens no grupo de modelos não serão automaticamente reservados fisicamente para a produção. No entanto, ainda podem ser reservados manualmente, conforme necessário.
    - **Estimativa** – os itens no grupo de modelos serão fisicamente reservados durante a estimativa da ordem de produção.
    - **Agendamento** – os itens no grupo de modelos serão fisicamente reservados durante o agendamento da ordem de produção.
    - **Liberação** – os itens no grupo de modelos serão fisicamente reservados quando a ordem de produção for liberada.
    - **Início** – os itens no grupo de modelos serão fisicamente reservados no início da ordem de produção.

## <a name="example-using-reservation-principles-in-a-bulkpack-scenario"></a>Exemplo: usando princípios de reserva em um cenário a granel/de embalagem

Um material lubrificante a granel é produzido em um misturador de 1.000 litros. Depois que o material a granel estiver pronto, ele é bombeado para várias estações de abastecimento, nas quais garrafas de tamanhos diferentes são abastecidas. Depois que o abastecimento é concluído, as garrafas são embaladas em caixas. Essas caixas são colocadas em paletes.

Nesse cenário, uma ordem de lote para preparar 1.000 litros de material a granel é criada. (Essa ordem é a ordem em massa.) Quando essa ordem de lote for concluída, ela será relatada como finalizada para o local de entrada de material das estações de abastecimento. Uma ordem de lote para abastecer e embalar cada tamanho de garrafa será criada. (Essas ordens são as ordens em pacote.) As ordens em pacote têm uma fórmula que consiste no material a granel, uma garrafa vazia, um rótulo e outros materiais de embalagem. Como o material a granel flui diretamente do tanque do misturador para as estações de abastecimento, não é necessário realizar trabalho de depósito para separar esse ingrediente e o material a granel é consumido diretamente no local de entrada. Portanto, o princípio da reserva é definido como *manual*. Os outros materiais são preparados para a estação de abastecimento por trabalho de separação. Portanto, o princípio de reserva para essas linhas é definido como *liberação*, por exemplo, para que a reserva ocorra automaticamente quando a ordem em pacote for liberada.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]