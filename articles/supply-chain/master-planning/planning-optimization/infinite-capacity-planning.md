---
title: Agendamento com capacidade infinita
description: Este tópico fornece informações sobre o agendamento de capacidade infinita para a Otimização de Planejamento. Ele também descreve as limitações atuais dos recursos.
author: crytt
ms.date: 6/9/2021
ms.topic: article
ms.search.form: RouteInventProd
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-06-09
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fc40dc2bcf1969e4c566b624a9425638e69ab2a17892f035aeabb74068aadd14
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6718963"
---
# <a name="scheduling-with-infinite-capacity"></a>Agendamento com capacidade infinita

[!include [banner](../../includes/banner.md)]
[!INCLUDE [preview-banner](../../includes/preview-banner.md)]

O recurso *Agendamento de capacidade infinita para Otimização de Planejamento* introduz o agendamento com base nas informações de roteiro. Ele permite que você agende trabalhos com base em uma vasta gama de configurações de roteiro. O Agendamento para Otimização de Planejamento aborda as configurações de roteiro usadas com frequência, incluindo a sequência de operações de roteiro ou os requisitos para recursos de operação de roteiro.

## <a name="turn-on-the-infinite-capacity-scheduling-feature"></a>Ativar o recurso de agendamento de capacidade infinita

Se o sistema ainda não incluir o recurso descrito neste tópico, abra o espaço de trabalho [Gerenciamento de recursos](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) e ative o recurso *Agendamento de capacidade infinita para a Otimização de Planejamento*.

## <a name="added-functionality"></a>Funcionalidade adicionada

O recurso *Agendamento de capacidade infinita para Otimização de Planejamento* permite o agendamento de trabalhos com base nas informações de roteiro. Portanto, uma configuração de roteiro pode ser usada para agendar processos de produção. Embora esse recurso tenha algumas limitações que o planejamento mestre interno não tem, ele oferece suporte à funcionalidade mais comum necessária para cenários de fabricação.

O recurso considera *Roteiros simples* e *Redes de roteiro*. Usando o campo **Avançar** em uma operação de roteiro, você pode configurar roteiros complexos que tenham vários pontos iniciais e várias operações executadas em paralelo. O sistema considera estruturas de roteiros complexos desse tipo durante o agendamento.

Além disso, o recurso oferece suporte a *operações paralelas* em roteiros. Usando as opções *Principal* e *Secundária* no campo **Prioridade** em operações de roteiro, você pode definir uma estrutura de roteiro em que uma operação de roteiro seja a principal operação e outra seja a secundária. Neste caso, o sistema considera a estrutura de roteiro durante o agendamento.

Durante o processo de agendamento, o sistema também considera os *requisitos de recursos* especificados para uma operação. O sistema usa requisitos de recursos para determinar quais recursos são necessários para executar a operação. No momento, o recurso *Agendamento de capacidade infinita para Otimização de Planejamento* oferece suporte aos seguintes tipos de requisitos de recursos:

- Tipo de recurso
- Recurso
- Grupo de recursos
- Capacidade

> [!NOTE]
> Ainda não há suporte para os requisitos relacionados a recursos humanos, como requisitos de habilidades ou certificados.

O recurso também oferece suporte às propriedades operacionais **Tempo de configuração** e **Tempo de execução**. Ao definir essas propriedades em uma operação de roteiro, o processo de agendamento criará os trabalhos de configuração e processo apropriados.

Em resumo, o agendamento para a Otimização de Planejamento oferece suporte aos cenários usados com mais frequência. Você pode criar o roteiro, adicionar operações primárias e secundárias, definir as próximas operações, adicionar requisitos de recursos e adicionar o tempo de configuração e tempo de execução. O sistema considerará essas informações durante o agendamento.

## <a name="limitations"></a>Limitações

As seguintes limitações aplicam-se quando você usa o agendamento para o Planejamento de Otimização:

- O recurso oferece suporte somente ao agendamento de trabalhos. As configurações relacionadas ao agendamento de operações não são consideradas durante o agendamento, independentemente do método de agendamento em planos mestre.
- O recurso oferece suporte apenas à capacidade infinita.
- O recurso não oferece suporte à funcionalidade de carregamento de recursos.
- O recurso não considera a sucata do roteiro.
- O recurso oferece suporte à *Duração* somente como a seleção do recurso principal.

Observe que o recurso *Agendamento de capacidade infinita para Otimização de Planejamento* é constantemente melhorado. A Microsoft espera apresentar suporte para configurações de agendamento adicionais em versões futuras.
