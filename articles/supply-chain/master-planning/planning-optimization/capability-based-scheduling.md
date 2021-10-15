---
title: Agendamento com seleção de recursos com base na capacidade
description: Este tópico descreve a seleção de recursos durante o agendamento de capacidade infinita quando você especifica capacidades como requisitos de recursos para uma operação.
author: ChristianRytt
ms.date: 9/3/2021
ms.topic: article
ms.search.form: RouteInventProd, WrkCtrTable, WrkCtrCapability
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-09-03
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 1fcea155f330fa1eced8035f11f7cf204d3b2de8
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7575694"
---
# <a name="scheduling-with-resource-selection-based-on-capability"></a>Agendamento com seleção de recursos com base na capacidade

[!include [banner](../../includes/banner.md)]
[!INCLUDE [preview-banner](../../includes/preview-banner.md)]

Ao especificar os requisitos de recursos para uma operação de um roteiro de produção, você define o que é necessário para executar essa operação. Por exemplo, uma operação pode exigir um recurso específico ou um grupo de recursos ou uma combinação de habilidades ou capacidades. Este tópico descreve a seleção de recursos durante o agendamento de capacidade infinita quando você especifica capacidades como requisitos de recursos para uma operação.

## <a name="turn-on-the-capability-based-scheduling-feature"></a>Ativar o recurso de agendamento com base em recursos

Antes de poder usar esse recurso, você deve habilitá-lo no seu sistema. Os administradores podem usar as configurações de [gerenciamento de recursos](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar o status do recurso e ativá-lo. No espaço de trabalho **Gerenciamento de recursos**, o recurso está listado da seguinte forma:

- **Módulo:** *Planejamento mestre*
- **Nome do recurso:** *agendamento da capacidade infinita para a Otimização do Planejamento*

Para obter mais informações sobre este recurso, consulte [Agendamento com capacidade infinita](infinite-capacity-planning.md).

## <a name="capability-based-scheduling"></a>Agendamento com base em recursos

Um recurso é a capacidade de um recurso de operações de executar uma atividade específica. Mais de uma capacidade pode ser atribuída a um único recurso de operação e uma única capacidade pode ser atribuída a mais de um recurso. As capacidades podem ser atribuídas a todos os tipos de recursos, como ferramentas, fornecedores, máquinas, locais, instalações e recursos humanos.

Ao especificar capacidades como requisitos de recursos, você pode adiar a alocação de recursos até que as ordens sejam agendadas. Em vez de atribuir recursos específicos ou grupos de recursos a uma operação de roteiro, você pode definir os recursos necessários para cada operação de roteiro. Em seguida, durante o planejamento, o sistema compara as capacidades necessárias com as capacidades definidas para os recursos. O sistema seleciona somente os recursos que atendem aos requisitos.

Para atribuir capacidades a um recurso de operação, use a Guia Rápida **Capacidades** da página **Recursos**. Para atribuir recursos a uma capacidade, use a Guia Rápida **Recursos** da página **Capacidades do recurso**. As duas páginas são acessíveis em **Controle de produção \> Configuração \> Recursos** no painel de navegação. Ambas as Guia Rápidas incluem uma grade que lista os recursos associados a um recurso ou capacidade selecionado. As duas guias rápidas também incluem uma barra de ferramentas que pode ser usada para adicionar, remover e editar linhas na grade. A grade inclui as seguintes colunas:

- **Recurso** ou **Capacidade** – selecione o recurso ou capacidade que está sendo atribuído pela linha.
- **Descrição** – informe uma descrição curta do recursos ou capacidade.
- **Efetivo** – especifique a primeira data em que se aplica a atribuição de recurso ou capacidade. Durante o planejamento, o sistema não usará um recurso ou capacidade que tenha uma atribuição de capacidade expirada, mesmo que o recurso não atenda aos requisitos.
- **Expiração** – especifique a última data em que se aplica a atribuição de recurso ou capacidade. Durante o planejamento, o sistema não usará um recurso ou capacidade que tenha uma atribuição de capacidade expirada, mesmo que o recurso não atenda aos requisitos.
- **Nível** – especifique o nível de proficiência que o recurso deve ter para a capacidade. Em seguida, se você especificar um **Nível mínimo necessário** para o recurso ou requisito de capacidade, o mecanismo de planejamento considera o nível de proficiência durante a seleção do recurso. O sistema seleciona apenas os recursos com a capacidade necessária em um nível que é igual ou excede o nível mínimo especificado na requisição de recurso.
- **Prioridade** – este campo ainda não tem suporte na Otimização de Planejamento. No entanto, se você estiver usando o mecanismo de planejamento interno, poderá usar o campo **Prioridade** na atribuição de recurso ou capacidade para definir a prioridade do recurso. Em seguida, se *Prioridade* estiver selecionado no campo **Seleção de recurso primário** na página **Agendamento de parâmetros**, o sistema primeiro seleciona o recurso que tem a prioridade mais alta (ou seja, o valor numérico mais baixo no campo **Prioridade**) durante o agendamento.

## <a name="example"></a>Exemplo

Este exemplo mostra como o mecanismo de agendamento seleciona recursos, com base na capacidade.

Um roteiro de produção tem cinco operações: *10*, *20*, *30*, *40* e *50*. Cada operação de roteiro requer um recurso com capacidades diferentes. Por exemplo, a operação *10* do roteiro requer um recurso que tenha a capacidade de montar um alto-falante (*0050 Montagem de alto-falante*) e o recurso de marcenaria (*1010 recursos de madeira*). A operação de roteiro *50* requer um recurso que tenha a capacidade de empacotar um produto (*0070 Recurso de embalagem*).

![Capacidade usada para agendamento.](media/capability-based-scheduling.png "Capacidade usada para agendamento.")

Durante o agendamento, o mecanismo procura recursos que satisfaçam aos requisitos de operação. Por exemplo, o mecanismo de agendamento seleciona o recurso *00101* para executar a operação *10* porque esse recurso é o primeiro recurso encontrado que tem ambas as capacidades obrigatórias. O mecanismo de agendamento seleciona o recurso *00301* para executar a operação *50* porque esse recurso é somente o primeiro recurso encontrado que tem ambas as capacidades de empacotamento.

Em seguida, considere como este exemplo é afetado quando níveis de proficiência são usados:

- A operação *10* requer um nível mínimo de proficiência de *7* para a capacidade *0059 Montagem*.
- O recurso *00101* tem um nível de proficiência de *5* para a capacidade *0059 Montagem*.
- O recurso *00102* tem um nível de proficiência de *10* para a capacidade *0059 Montagem*.

Nesse caso, durante o planejamento de capacidade infinito, o mecanismo de agendamento seleciona o recurso *00102* para executar a operação *10*, porque esse recurso, diferentemente do recurso *00101*, tem o nível de proficiência necessário para a capacidade.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
