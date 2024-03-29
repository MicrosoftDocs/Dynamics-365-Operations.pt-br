---
title: Substituir o princípio de reserva padrão por materiais em produção
description: Este artigo descreve como configurar um princípio de reserva padrão para cada grupo de modelo de item, para que diferentes princípios de reserva possam ser automaticamente aplicados a cada item que faz parte da lista de materiais (BOM) ou fórmula de ordem de lote.
author: johanhoffmann
ms.date: 08/05/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventModelGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-12-10
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 87f10efd7eebdc034af3f7c9081d2674a6190b38
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/23/2022
ms.locfileid: "9334585"
---
# <a name="override-the-default-reservation-principle-for-materials-in-production"></a>Substituir o princípio de reserva padrão por materiais em produção

[!include [banner](../includes/banner.md)]

O recurso *Substituir reserva de produção padrão* permite definir um princípio de reserva padrão para cada grupo de modelos de item. Portanto, diferentes princípios de reserva podem automaticamente ser aplicados em cada item que faz parte de uma lista de materiais (BOM) ou fórmula de ordem de lote. Você pode selecionar se cada grupo de modelos de item deve substituir o princípio de reserva padrão definido para uma ordem e qual princípio de reserva deve ser usado (*manual*, *estimativa*, *agendamento*, *liberação* ou *início*).

Ao criar uma ordem de produção ou ordem de lote, você será solicitado a selecionar o princípio de reserva que deve ser aplicado a essa ordem e todas as linhas da BOM ou linhas da fórmula. Quando o recurso *Substituir reserva de produção padrão* é usado, algumas ou todas as linhas da BOM ou da fórmula podem substituir esse princípio de reserva e usar o princípio de reserva definido para o grupo de modelos de itens relevantes.

Por exemplo, se você tem matérias-primas ou componentes que exigem trabalho de separação, as linhas da BOM ou fórmula que são criadas para esses produtos exigem uma reserva física, pois ela é um pré-requisito para a geração de trabalho de depósito. Normalmente, se quiser que a reserva ocorra automaticamente, selecione um dos seguintes princípios de reserva: *estimativa*, *agendamento*, *liberação* ou *início*. Por outro lado, se você tem materiais ou ingredientes que não exigem trabalho de separação, pois são consumidos diretamente de um local, você normalmente seleciona o princípio de reserva *manual*, que não faz reservas físicas nem gera trabalho de separação.

## <a name="turn-the-override-default-production-reservation-feature-on-or-off"></a>Ativar ou desativar o recurso Substituir reserva de produção padrão

Para usar esse recurso, você deve habilitá-lo no seu sistema. A partir do Supply Chain Management versão 10.0.25, o recurso está ativado por padrão. A partir do Supply Chain Management versão 10.0.29, o recurso é obrigatório e não pode ser desativado. Se você estiver executando uma versão anterior à 10.0.29, os administradores poderão habilitar ou desabilitar essa funcionalidade pesquisando o recurso *Substituir reserva de produção padrão* no espaço de trabalho [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="assign-a-production-reservation-policy-to-an-item-model-group"></a>Atribuir uma política de reserva de produção a um grupo de modelos de item

1. Acesse **Gerenciamento de custos \> Configuração das políticas contábeis de estoque \> Grupos de modelos de item**.
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