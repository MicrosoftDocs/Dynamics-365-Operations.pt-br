---
title: Agendamento com capacidade infinita
description: Este artigo fornece informações sobre agendamento de capacidade infinita. Ele também descreve as limitações atuais dos recursos.
author: t-benebo
ms.date: 08/09/2022
ms.topic: article
ms.search.form: RouteInventProd
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-06-09
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 7249734e5d2644145a36276dbc818a40b5962805
ms.sourcegitcommit: 491ab9ae2b6ed991b4eb0317e396fef542d3a21b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2022
ms.locfileid: "9739996"
---
# <a name="scheduling-with-infinite-capacity"></a>Agendamento com capacidade infinita

[!include [banner](../../includes/banner.md)]

O recurso *Agendamento de capacidade infinita para Otimização de Planejamento* introduz o agendamento com base nas informações de roteiro. Ele permite que você agende trabalhos com base em uma vasta gama de configurações de roteiro. O agendamento aborda as configurações de roteiro usadas com frequência, incluindo a sequência de operações de roteiro ou os requisitos para recursos de operação de roteiro.

## <a name="turn-the-infinite-capacity-scheduling-feature-on-or-off"></a>Ativar ou desativar o recurso de agendamento de capacidade infinita

Para usar esse recurso, você deve habilitá-lo no seu sistema. A partir da versão 10.0.29 do Supply Chain Management, o recurso está ativado por padrão. Os administradores podem ativar ou desativar essa funcionalidade pesquisando o recurso *Agendamento da capacidade infinita para a Otimização do Planejamento* no espaço de trabalho [Gerenciamento de recursos](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

Para obter mais informações sobre esse recurso, consulte [Agendamento com a seleção de recursos com base na capacidade](capability-based-scheduling.md).

## <a name="added-functionality"></a>Funcionalidade adicionada

O recurso *Agendamento de capacidade infinita para Otimização de Planejamento* permite o agendamento de trabalhos com base nas informações de roteiro. Portanto, uma configuração de roteiro pode ser usada para agendar processos de produção. Embora esse recurso tenha algumas limitações que o mecanismo de planejamento mestre preterido não tem, ele oferece suporte à funcionalidade mais comum necessária para cenários de fabricação.

O recurso considera *Roteiros simples* e *Redes de roteiro*. Usando o campo **Avançar** em uma operação de roteiro, você pode configurar roteiros complexos que tenham vários pontos iniciais e várias operações executadas em paralelo. O sistema considera estruturas de roteiros complexos desse tipo durante o agendamento.

Além disso, o recurso oferece suporte a *operações paralelas* em roteiros. Usando as opções *Principal* e *Secundária* no campo **Prioridade** em operações de roteiro, você pode definir uma estrutura de roteiro em que uma operação de roteiro seja a principal operação e outra seja a secundária. Neste caso, o sistema considera a estrutura de roteiro durante o agendamento.

Durante o processo de agendamento, o sistema também considera os *requisitos de recursos* especificados para uma operação. O sistema usa requisitos de recursos para determinar quais recursos são necessários para executar a operação. No momento, o recurso *Agendamento de capacidade infinita para Otimização de Planejamento* oferece suporte aos seguintes tipos de requisitos de recursos:

- Tipo de recurso
- Recurso
- Grupo de recursos
- Capacidade (Para obter mais informações, consulte [Agendamento com a seleção de recursos com base na capacidade](capability-based-scheduling.md).)

> [!NOTE]
>
> - Se o recurso e/ou o grupo de recursos estiver definido como capacidade infinita, o planejamento mestre irá considerá-lo como capacidade infinita.
> - Ainda não há suporte para os requisitos relacionados a recursos humanos, como requisitos de habilidades ou certificados.

O recurso também oferece suporte às propriedades operacionais **Tempo de configuração** e **Tempo de execução**. Ao definir essas propriedades em uma operação de roteiro, o processo de agendamento criará os trabalhos de configuração e processo apropriados.

Em resumo, o agendamento oferece suporte aos cenários usados com mais frequência. Você pode criar o roteiro, adicionar operações primárias e secundárias, definir as próximas operações, adicionar requisitos de recursos e adicionar o tempo de configuração e tempo de execução. O sistema considerará essas informações durante o agendamento.

## <a name="limitations"></a>Limitações

As limitações a seguir se aplicam quando você usa o recurso *Agendamento da capacidade infinita para a Otimização do Planejamento*:

- O recurso oferece suporte apenas à capacidade infinita.
- O recurso não oferece suporte à funcionalidade de carregamento de recursos.
- O recurso não considera a sucata do roteiro.
- O recurso oferece suporte à *Duração* somente como a seleção do recurso principal.
