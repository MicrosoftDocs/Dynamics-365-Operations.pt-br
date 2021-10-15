---
title: Agendamento com capacidade infinita
description: Este tópico fornece informações sobre o agendamento de capacidade infinita para a Otimização de Planejamento. Ele também descreve as limitações atuais dos recursos.
author: ChristianRytt
ms.date: 09/21/2021
ms.topic: article
ms.search.form: RouteInventProd
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-06-09
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 9c1eef91bcf7d1ce6379e87417be5a8b3be069e5
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7575623"
---
# <a name="scheduling-with-infinite-capacity"></a>Agendamento com capacidade infinita

[!include [banner](../../includes/banner.md)]
[!INCLUDE [preview-banner](../../includes/preview-banner.md)]

O recurso *Agendamento de capacidade infinita para Otimização de Planejamento* introduz o agendamento com base nas informações de roteiro. Ele permite que você agende trabalhos com base em uma vasta gama de configurações de roteiro. O Agendamento para Otimização de Planejamento aborda as configurações de roteiro usadas com frequência, incluindo a sequência de operações de roteiro ou os requisitos para recursos de operação de roteiro.

## <a name="turn-on-the-infinite-capacity-scheduling-feature"></a>Ativar o recurso de agendamento de capacidade infinita

Antes de poder usar esse recurso, você deve habilitá-lo no seu sistema. Os administradores podem usar as configurações de [gerenciamento de recursos](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar o status do recurso e ativá-lo. No espaço de trabalho **Gerenciamento de recursos**, o recurso está listado da seguinte forma:

- **Módulo:** *Planejamento mestre*
- **Nome do recurso:** *agendamento da capacidade infinita para a Otimização do Planejamento*

Para obter mais informações sobre esse recurso, consulte [Agendamento com a seleção de recursos com base na capacidade](capability-based-scheduling.md).

## <a name="added-functionality"></a>Funcionalidade adicionada

O recurso *Agendamento de capacidade infinita para Otimização de Planejamento* permite o agendamento de trabalhos com base nas informações de roteiro. Portanto, uma configuração de roteiro pode ser usada para agendar processos de produção. Embora esse recurso tenha algumas limitações que o planejamento mestre interno não tem, ele oferece suporte à funcionalidade mais comum necessária para cenários de fabricação.

O recurso considera *Roteiros simples* e *Redes de roteiro*. Usando o campo **Avançar** em uma operação de roteiro, você pode configurar roteiros complexos que tenham vários pontos iniciais e várias operações executadas em paralelo. O sistema considera estruturas de roteiros complexos desse tipo durante o agendamento.

Além disso, o recurso oferece suporte a *operações paralelas* em roteiros. Usando as opções *Principal* e *Secundária* no campo **Prioridade** em operações de roteiro, você pode definir uma estrutura de roteiro em que uma operação de roteiro seja a principal operação e outra seja a secundária. Neste caso, o sistema considera a estrutura de roteiro durante o agendamento.

Durante o processo de agendamento, o sistema também considera os *requisitos de recursos* especificados para uma operação. O sistema usa requisitos de recursos para determinar quais recursos são necessários para executar a operação. No momento, o recurso *Agendamento de capacidade infinita para Otimização de Planejamento* oferece suporte aos seguintes tipos de requisitos de recursos:

- Tipo de recurso
- Recurso
- Grupo de recursos
- Capacidade (Para obter mais informações, consulte [Agendamento com a seleção de recursos com base na capacidade](capability-based-scheduling.md).)

> [!NOTE]
> Ainda não há suporte para os requisitos relacionados a recursos humanos, como requisitos de habilidades ou certificados.

O recurso também oferece suporte às propriedades operacionais **Tempo de configuração** e **Tempo de execução**. Ao definir essas propriedades em uma operação de roteiro, o processo de agendamento criará os trabalhos de configuração e processo apropriados.

Em resumo, o agendamento para a Otimização de Planejamento oferece suporte aos cenários usados com mais frequência. Você pode criar o roteiro, adicionar operações primárias e secundárias, definir as próximas operações, adicionar requisitos de recursos e adicionar o tempo de configuração e tempo de execução. O sistema considerará essas informações durante o agendamento.

## <a name="limitations"></a>Limitações

As seguintes limitações aplicam-se quando você usa o agendamento para o Planejamento de Otimização:

- O recurso oferece suporte apenas à capacidade infinita.
- O recurso não oferece suporte à funcionalidade de carregamento de recursos.
- O recurso não considera a sucata do roteiro.
- O recurso oferece suporte à *Duração* somente como a seleção do recurso principal.

Observe que o recurso *Agendamento de capacidade infinita para Otimização de Planejamento* é constantemente melhorado. A Microsoft espera apresentar suporte para configurações de agendamento adicionais em versões futuras.
