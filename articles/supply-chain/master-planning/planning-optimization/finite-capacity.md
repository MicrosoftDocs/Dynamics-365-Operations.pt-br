---
title: Planejamento e agendamento de capacidade finita
description: O planejamento e agendamento de capacidade finita ajudam você a entender quanto trabalho pode ser produzido durante um período específico quando as limitações de diferentes recursos são levadas em consideração.
author: t-benebo
ms.date: 09/19/2022
ms.topic: article
ms.search.form: ReqParameters, ReqPlanSched, WrkCtrTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2022-09-19
ms.dyn365.ops.version: 10.0.29
ms.openlocfilehash: c5eebe9ef6258b43daa7c7007ee28b0278fe5b09
ms.sourcegitcommit: 1a7729a6ce4f3fcf68bdc4cfdad746a5553da3c5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/22/2022
ms.locfileid: "9573128"
---
# <a name="finite-capacity-planning-and-scheduling"></a>Planejamento e agendamento de capacidade finita

[!include [banner](../../includes/banner.md)]

A capacidade finita é uma abordagem que ajuda você a entender quanto trabalho pode ser produzido durante um período específico quando as limitações de diferentes recursos são levadas em consideração. O objetivo do agendamento de capacidade finita é garantir que o trabalho prossiga em um ritmo uniforme e eficiente em toda a planta.

O planejamento e o agendamento de capacidade finita criam uma programação mais realista para os processos de produção do que a abordagem de carregamento infinito cria. Se não houver capacidade suficiente nos recursos, a data de entrega será adiada e o trabalho será agendado quando houver capacidade suficiente.

## <a name="planning-optimization-support-for-finite-capacity-planning"></a>Suporte à Otimização de Planejamento para planejamento de capacidade finita

O planejamento e o agendamento de capacidade finita funcionam quase da mesma maneira, independentemente de você usar a Otimização de Planejamento ou o mecanismo de planejamento integrado. Contudo, a Otimização de Planejamento não usa o parâmetro de limite **Tempo de gargalo**. Quando você usa a Otimização de Planejamento, os recursos de gargalo são sempre planejados usando o mesmo limite de tempo que os recursos sem gargalo (conforme indicado pelo limite de tempo de capacidade finita).

## <a name="set-up-finite-capacity-functionality"></a>Configurar a funcionalidade de capacidade finita

Para usar a funcionalidade de capacidade finita, você deve habilitar o planejamento de capacidade globalmente e deve habilitar o planejamento de capacidade finita tanto para o plano mestre em que deseja usá-lo quanto para cada recurso em que ele se aplica. Para planos e recursos em que a capacidade finita está habilitada, o agendamento de ordens de produção planejadas considerará a capacidade que já foi reservada. As ordens de produção planejadas são programadas retroativamente a partir da data da necessidade. Se a capacidade não estiver disponível para atender à agenda ideal, o sistema tentará exigir os itens do componente em uma data anterior. Se sua capacidade pode mudar conforme os requisitos mudam (por exemplo, quando você está trabalhando com turnos), você não deve usar a funcionalidade de capacidade finita, porque os tempos de processamento calculados não estarão corretos. O agendamento só levará em conta a capacidade que já está reservada para recursos em que a capacidade finita está habilitada. Ao habilitar a capacidade finita para um recurso, você torna possível modificar o limite de tempo de capacidade finita.

### <a name="activate-master-planning-parameters"></a>Ativar parâmetros de planejamento mestre

Para usar a funcionalidade de capacidade finita, você deve habilitar o planejamento de capacidade na página **Parâmetros do planejamento mestre**.

1. Acesse **Planejamento mestre \> Configurar \> Parâmetros de planejamento mestre**.
1. Na guia **Ordens planejadas**, na seção **Planejamento de capacidade**, defina a opção **Produção** como *Sim*.

### <a name="activate-a-master-plan"></a>Ativar um plano mestre

Você deve habilitar o planejamento e o agendamento de capacidade finita para cada plano mestre em que deseja usá-lo.

1. Acesse **Planejamento mestre \> Configuração \> Planos \> Planos mestres**.
1. No painel de lista, selecione um plano mestre que você deseja configurar para usar planejamento e agendamento de capacidade finita.
1. Na Guia Rápida **Geral**, na seção **Ordens de produção planejadas**, defina a opção **Capacidade finita** como *Sim*.
1. Repita as etapas 2 e 3 para cada plano mestre adicional que você deseja configurar.

### <a name="activate-resources"></a>Ativar recursos

Você deve habilitar o planejamento e o agendamento de capacidade finita para cada recurso onde você deseja usá-lo.

1. Acesse **Controle de produção \> Configuração \> Recursos \> Recursos**.
1. No painel de lista, selecione um recurso que você deseja configurar para usar planejamento e agendamento de capacidade finita.
1. Na Guia Rápida **Operação**, na seção **Botão de capacidade**, defina a opção **Capacidade finita** como *Sim*.
1. Repita as etapas 2 e 3 para cada recurso adicional que você deseja configurar.

## <a name="examples"></a>Exemplos

Esta seção fornece os seguintes exemplos que mostram como trabalhar com planejamento e agendamento de capacidade infinita e finita:

- Exemplo 1 – Planejamento de capacidade infinita
- Exemplo 2 – Planejamento de capacidade finita com um limite de tempo de um dia
- Exemplo 3 – Planejamento de capacidade finita com um limite de dois dias

### <a name="preconditions"></a>Precondições

Todos os três exemplos assumem as precondições descritas nesta seção.

Produto *Product1* tem um roteiro que contém as seguintes operações.

| Nº de operação | Nome da operação | Recurso        | Tempo de execução | Processar qtd. | Próximo |
|---------------|----------------|-----------------|----------|--------------|------|
| 10            | Solda        | Linha de soldagem    | 1        | 2            | 20   |
| 20            | Montagem     | Linha de montagem | 1        | 4            |      |

Os funcionários da sua empresa trabalham em um turno por oito horas (8:00–16:00).

Existe uma ordem de produção agendada para *24 pcs* de *Product1*. Tem uma data de entrega de *Hoje + 3 dias*.

Como resultado do planejamento, o sistema carregará os recursos da seguinte forma:

- **Linha de soldagem:** este recurso é carregado de *Hoje às 8:00* até *Hoje + 1 às 12:00*.
- **Linha de montagem:** este recurso é carregado de *Hoje + 1 às 12:00* até *Hoje + 2 às 10:00*.

A ilustração a seguir mostra o gráfico de Gantt resultante (selecione-o para uma exibição maior).

[![Gráfico de Gantt mostrando precondições.](media/finite-examples-conditions-small.png "Gráfico de Gantt mostrando precondições")](media/finite-examples-conditions.png)

### <a name="example-1--infinite-capacity-planning"></a>Exemplo 1 – Planejamento de capacidade infinita

Este exemplo mostra os resultados do planejamento quando você usa o planejamento de capacidade infinita em vez do planejamento de capacidade finita.

O plano mestre tem a seguinte configuração relevante, que desativa o planejamento de capacidade finita para o plano:

- **Capacidade finita:** *Não*

A opção **Capacidade finita** também está definida como *Não* para ambos os recursos relevantes para desabilitar o planejamento de capacidade finita para eles:

- Linha de soldagem
- Linha de montagem

Agora você adiciona uma nova ordem de venda para *8 pcs*  de *Product1* e executa o plano. Como resultado, o sistema carregará a linha de soldagem de *Hoje às 8:00* até *Hoje às 12:00*. Após a conclusão das operações na linha de soldagem, o sistema carregará a linha de montagem de *Hoje às 12:00* até *Hoje às 14:00*.

A ilustração a seguir mostra o gráfico de Gantt resultante (selecione-o para uma exibição maior).

[![Gráfico de Gantt mostrando um exemplo de planejamento de capacidade infinita.](media/finite-examples-example1-small.png "Gráfico de Gantt mostrando um exemplo de planejamento de capacidade infinita")](media/finite-examples-example1.png)

### <a name="example-2--finite-capacity-planning-with-a-time-fence-of-one-day"></a>Exemplo 2 – Planejamento de capacidade finita com um limite de tempo de um dia

Este exemplo mostra os resultados do planejamento quando você usa o planejamento de capacidade finita e um horizonte firme de um dia.

O plano mestre tem as seguintes configurações relevantes, que permitem o planejamento de capacidade finita e definem um limite de tempo para o plano:

- **Capacidade finita:** *Sim*
- **Limite de tempo de capacidade finita:** *1*

A opção **Capacidade finita** também está definida como *Sim* para ambos os recursos relevantes para habilitar o planejamento de capacidade finita para eles:

- Linha de soldagem
- Linha de montagem

Agora você adiciona uma nova ordem de venda para *8 pcs*  de *Product1* e executa o plano. Como resultado, o sistema carregará a linha de soldagem de *Hoje + 1 às 8:00* até *Hoje + 1 às 12:00*. Após a conclusão das operações na linha de soldagem, o sistema carregará a linha de montagem de *Hoje + 1 às 12:00* até *Hoje + 1 às 14:00*. O sistema considerará a capacidade finita para apenas um dia.

A ilustração a seguir mostra o gráfico de Gantt resultante (selecione-o para uma exibição maior).

[![Gráfico de Gantt mostrando o planejamento de capacidade finita com um limite de tempo de um dia.](media/finite-examples-example2-small.png "Gráfico de Gantt mostrando o planejamento de capacidade finita com um limite de tempo de um dia")](media/finite-examples-example2.png)

### <a name="example-3--finite-capacity-planning-with-a-time-fence-of-two-days"></a>Exemplo 3 – Planejamento de capacidade finita com um limite de dois dias

Este exemplo mostra os resultados do planejamento quando você usa o planejamento de capacidade finita e um horizonte firme de dois dias.

O plano mestre tem as seguintes configurações relevantes, que permitem o planejamento de capacidade finita e definem um limite de tempo para o plano:

- **Capacidade finita:** *Sim*
- **Limite de tempo de capacidade finita:** *2*

A opção **Capacidade finita** também está definida como *Sim* para ambos os recursos relevantes para habilitar o planejamento de capacidade finita para eles:

- Linha de soldagem
- Linha de montagem

Agora você adiciona uma nova ordem de venda para *8 pcs*  de *Product1* e executa o plano. Como resultado, o sistema carregará a linha de soldagem de *Hoje + 1 às 12:00* até *Hoje + 1 às 16:00*. Após a conclusão das operações na linha de soldagem, o sistema carregará a linha de montagem de *Hoje + 2 às 8:00* até *Hoje + 2 às 10:00*. O sistema considerará a capacidade finita para apenas dois dias.

A ilustração a seguir mostra o gráfico de Gantt resultante (selecione-o para uma exibição maior).

[![Gráfico de Gantt mostrando o planejamento de capacidade finita com um limite de tempo de dois dias.](media/finite-examples-example3-small.png "Gráfico de Gantt mostrando o planejamento de capacidade finita com um limite de tempo de dois dias")](media/finite-examples-example3.png)

> [!IMPORTANT]
> Você deve sempre definir o limite de tempo de capacidade finita conforme necessário para atender às suas necessidades de negócios. Os exemplos fornecidos neste artigo apenas ilustram a funcionalidade. Na realidade, um limite de tempo de um dia provavelmente é muito baixo para a maioria dos fabricantes que usam planejamento de capacidade finita.
