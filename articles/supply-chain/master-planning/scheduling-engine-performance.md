---
title: Melhorar o desempenho do mecanismo de agendamento
description: Este tópico fornece informações sobre o mecanismo de agendamento e sobre como melhorar o desempenho.
author: ChristianRytt
ms.date: 09/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19311
ms.assetid: 5ffb1486-2e08-4cdc-bd34-b47ae795ef0f
ms.search.region: Global
ms.search.industry: ''
ms.author: kamaybac
ms.search.validFrom: 2020-09-03
ms.dyn365.ops.version: ''
ms.openlocfilehash: d1378ae652ea70cba941316f4667052dcb05f717
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5812898"
---
# <a name="improve-scheduling-engine-performance"></a>Melhorar o desempenho do mecanismo de agendamento

[!include [banner](../includes/banner.md)]

O mecanismo de agendamento de recursos é usado ao agendar roteiros para ordens de produção planejadas e liberadas. O mecanismo foi lançado originalmente como parte do Dynamics AX 2012 e passou por várias melhorias desde seu lançamento.

O [problema no agendamento de trabalhos](https://en.wikipedia.org/wiki/Job_shop_scheduling) é um problema extremamente complexo no qual o tempo da solução aumenta exponencialmente com o número de variáveis de decisão. Muitas vezes, os clientes configuram roteiros de produção e dados relacionados de forma que resulta em um problema de agendamento que não pode ser resolvido em um tempo razoável, mesmo no hardware mais moderno. Este tópico o ajudará a compreender o mecanismo de agendamento e a forma como uma configuração específica pode ter influência sobre o desempenho.

Quando se trata de melhorar o desempenho do agendamento, as orientações gerais recomendam reduzir a complexidade do problema que o mecanismo precisa solucionar. Alguns dos principais fatores que podem afetar o desempenho incluem:

- Roteiros com muitas operações
- Roteiros com operações paralelas
- Operações com quantidade de recursos maior que um
- Operações com vários recursos aplicáveis
- Uso de links rígidos
- Uso de capacidade finita
- O número de diferentes calendários usados
- O número de slots de horário de trabalho por dia no calendário
- Duração total do roteiro
- Executar vários mecanismos de agendamento em paralelo

## <a name="overview-of-basic-scheduling-flow"></a>Visão geral do fluxo de agendamento básico

Para entender como uma determinada configuração pode afetar o desempenho, é importante compreender um pouco sobre como o processo flui, tanto dentro do mecanismo quanto no código X++ que o envolve.

O processo básico de agendamento de uma ordem consiste em três etapas principais:

- **Carregando dados** – Aqui, os modelos de dados X++ são transformados no modelo de dados interno do mecanismo na forma de trabalhos e restrições.
- **Agendamento** – Esta é a principal origem de agendamento que processa o modelo e as restrições específicas e gera um resultado. Durante esse processo, o mecanismo solicita as informações de horários de trabalho e as reservas de capacidade existentes do X++ conforme necessário.
- **Salvar dados** – O resultado do mecanismo na forma de slots de reserva de capacidade de trabalho é processado pelo código X++ para economizar reservas de capacidade e atualizar as horas de início e de término de trabalhos/operação/ordem.

## <a name="load-data-into-the-engine"></a>Carregar dados no mecanismo

O mecanismo de agendamento tem um modelo de dados mais abstrato do que o banco de dados do Supply Chain Management porque foi criado como um mecanismo genérico que pode lidar com diferentes fontes de dados. Os conceitos de roteiro, operações secundárias e tempo de execução precisam ser "traduzidos" para o modelo de trabalho e de restrição genérico que o mecanismo expõe. A lógica para a criação do modelo tem uma quantidade significativa de lógica comercial e é diferente dependendo dos dados de origem. A classe X++ responsável é `WrkCtrScheduler` e tem classes derivadas para ordens de produção planejadas, ordens de produção liberadas e previsões de projeto.

Como exemplo, considere um roteiro mostrado na tabela e imagem a seguir, que parece relativamente simples.

| Oper. Nº | Prioridade | Tempo de preparação | Tempo de execução | Tempo de espera posterior | Quantidade de recursos | Avançar |
| --- | --- | --- | --- | --- | --- | --- |
| 10 | Principal | 1.00 | 2.00 | | 1 | 20 |
| 10 | Secundário&nbsp;1 | | | | 1 | 20 |
| 20 | Principal | | 3.00 | 1.00 | 3 | 0 |

![Exemplo de diagrama de roteiros](media/scheduling-engine-route.png "Exemplo de diagrama de roteiros")

Ao enviá-lo para o mecanismo, ele é dividido em oito trabalhos, conforme mostrado na ilustração a seguir (selecione a imagem para ampliá-la).

[![Trabalhos do mecanismo de agendamento](media/scheduling-engine-jobs.png "Trabalhos do mecanismo de agendamento")](media/scheduling-engine-jobs-large.png)

O link padrão entre dois trabalhos é `FinishStart`, o que significa que a hora de término de um trabalho deve ser anterior à hora de início de outro trabalho. Como a configuração deve ser executada pelo mesmo recurso que posteriormente fará o processo, há restrições `OnSameResource` entre eles. Entre os trabalhos da operação principal e secundária para 10, há links `StartStart` e `FinishFinish`, o que significa que os trabalhos devem ser iniciados e concluídos na mesma hora, e há restrições `NotOnSameResource`, o que impedirá que o mesmo recurso seja principal e secundário.

Para a operação 20, na qual a quantidade de recursos foi definida como 3, o trabalho de processo foi dividido em três trabalhos distintos, nos quais todos os trabalhos devem ser executados na mesma hora.
Nesse caso, o grupo de roteiros foi configurado para não reservar capacidade para fila depois das horas, que é o motivo pelo qual há apenas um único trabalho para a fila depois.

O mecanismo de agendamento só entende os conceitos de trabalho e não tem noção de operações. Isso significa que, ao executar o agendamento de operações, as operações também são divididas em trabalhos, embora não sejam persistentes no banco de dados.

Para cada trabalho, também definiremos o que é o requisito de capacidade do trabalho (o número de segundos necessário). Dependendo de como os requisitos de recursos foram definidos, para cada trabalho, também podemos enviar uma lista de todos os recursos possíveis aplicáveis em que o trabalho pode ser executado e qual é o requisito de capacidade para esse recurso específico. Embora a lista de recursos aplicáveis seja enviada durante a criação do modelo, o mecanismo ainda precisará garantir que a atribuição de recursos seja realmente válida por toda a duração do trabalho.

## <a name="scheduling-engine-internals"></a>Componentes internos do mecanismo de agendamento

### <a name="scheduling-engine-interface"></a>Interface do mecanismo de agendamento

Para ter uma ideia de como o mecanismo funciona internamente, é melhor verificar a funcionalidade que ele expõe externamente. No X ++, a interface principal é `WrkCtrSchedulerEngineInterface`. Ele tem os métodos descritos nas subseções a seguir.

#### <a name="general-engine"></a>Mecanismo geral

| **Método** | **Finalidade** |
| --- | --- |
| `run` | Agenda todos os trabalhos carregados e retorna o código de erro. |
| `getJobSchedulingSequenceResult` | Obtém o resultado do agendamento e o primeiro trabalho de erro para a sequência identificada por um trabalho específico. |
| `validateJobCapacityReservations` | Valida as reservas de capacidade para todos os trabalhos armazenados pelo mecanismo. |
| `setReservationsTimeStamp` | Envia um carimbo de data/hora para o mecanismo definido em todas as novas reservas de capacidade para os trabalhos agendados no cache do mecanismo. |
| `addPropertyToGroupAggregation` | Adiciona um prefixo de propriedade ao conjunto de propriedades usado quando a capacidade é agregada. |
| `addResource` | Adiciona um recurso ao pool de recursos do mecanismo de agendamento. |
| `addResourceGroup` | Adiciona um grupo de recursos ao grupo de recursos do mecanismo de agendamento. |
| `addResourceGroupMembership` | Adiciona um recurso como membro a um grupo de recursos. |
| `addOptimizationGoal` | Adiciona uma meta de otimização de agendamento (duração ou prioridade). |

#### <a name="individual-jobs"></a>Trabalhos individuais

| **Método** | **Finalidade** |
| --- | --- |
| `addJobInfo` | Adiciona um registro de informações do trabalho que informa o mecanismo sobre um trabalho que deve ser agendamento. |
| `addConstraintJobEndsAt` | Adiciona uma restrição que um trabalho deve ser concluído em uma data e hora especificadas. |
| `addConstraintJobStartsAt` | Adiciona uma restrição de que um trabalho deve ser iniciado em uma data e hora especificadas. |
| `addConstraintMaxJobDays` | Define a restrição que um trabalho pode abranger durante um número máximo especificado de dias. |
| `addConstraintResourceRequirement` | Adiciona a restrição de que o trabalho deve ser agendado em um recurso específico. |
| `addJobBindPriority` | Adiciona uma prioridade de associação de trabalho para um par (trabalho, nível de restrição). Um valor de prioridade mais alto significa que as variáveis de trabalho serão associadas antes. O trabalho será processado antes dos trabalhos com valor de prioridade menor na mesma sequência. |
| `addJobCapacity` | Adiciona informações de capacidade máxima de um trabalho (como o tempo de execução necessário para o trabalho), não importa em qual recurso o trabalho é executado. |
| `addJobResourceCapacity` | Adiciona um recurso ao conjunto de recursos que pode ser usado para executar um trabalho e declara a capacidade necessária quando executado no recurso. |
| `addJobGoal` | Adiciona informações de meta de trabalho para um nível de restrição específico (hora de término mais antiga ou hora de início mais recente). |
| `addJobResourcePriority` | Adiciona a prioridade a ser usada quando um trabalho é agendado em um recurso. |
| `addJobResourceRuntime` | Especifica um tempo de trabalho que depende do recurso no qual o trabalho será agendado. |
| `addJobRuntime` | Especifica um tempo de trabalho que não depende do recurso no qual o trabalho será agendado. |
| `scheduleJobOnResourceGroup` | Marca um trabalho para agendamento no nível de grupo de recursos. |
| `setJobResourcePreemptionAllowed` | Define se um resgate é permitido para um trabalho em um recurso (se o mecanismo tiver permissão para agendar o trabalho em slots de capacidade não contínuos). |
| `setRequiredNumberOfResources` | Define o número de recursos necessários para agendar um trabalho (somente para o agendamento de operações). |

#### <a name="constraints-between-jobs"></a>Restrições entre trabalhos

| **Método** | **Finalidade** |
| --- | --- |
| `addJobLink` | Adiciona um link (como término\>início) entre dois trabalhos. |
| `addConstraintEndsDelayed` | Define a restrição de que um trabalho não pode ser concluído antes que outros trabalhos sejam concluídos, além de um tempo de atraso. |
| `addConstraintJobListWorkingTimeIntersect` | Adiciona uma restrição de que os slots de capacidade reservados para os trabalhos devem estar nos horários trabalho em interseção para os dois recursos usados pelos trabalhos. |
| `addConstraintJobOverlap` | Adicionar uma restrição que define como os trabalhos são sequenciados quando uma determinada quantidade de um item pode ser movida entre dois recursos, enquanto o primeiro recurso ainda não terminou de ser processado, de forma que o segundo recurso possa iniciar o processamento. |
| `addConstraintNotOnSameResource` | Adiciona uma restrição de que dois trabalhos não devem ser agendados no mesmo recurso. |
| `addConstraintOnSameResource` | Adiciona uma restrição de que dois trabalhos devem usar o mesmo recurso. |
| `addJobSameReservations` | Adiciona uma restrição de que um trabalho deve ser concluído com reservas de capacidade para os mesmos slots de horário que o trabalho principal. |
| `setPrimaryParallelJob` | Adiciona informações sobre o trabalho que é o principal em um conjunto de trabalhos paralelos. |

### <a name="solver"></a>Agente de resolução

O próprio mecanismo é basicamente um agente especializado de resolução de restrição com heurística personalizada adicionada. O agente de resolução se baseia em dois elementos principais: variáveis e restrições.

#### <a name="variable"></a>Variável

Uma variável representa um domínio de valores possíveis. O mecanismo de agendamento tem dois tipos de variáveis:

- **Variável DateTime** - Tem um domínio de todas as datas e horas, e o domínio pode ser restringido ao mover o limite inferior e superior para a hora da variável mais próxima.
- **Variável Recurso** - Tem um domínio de recursos aplicáveis, e o domínio pode ser restringido ao eliminar recursos da lista.

#### <a name="constraint"></a>Restrição

Uma restrição atua nas variáveis restringindo seus domínios, mas também depende de variáveis, de forma que ela é ativada quando as variáveis são alteradas. O processo de "propagação de restrições" é quando uma restrição executa sua função principal e relata novamente a lógica principal, se for bem-sucedido.

Uma variável é considerada como limitada quando não pode ser restrita ainda mais, o que, para a variável DateTime, significa que o limite superior e inferior é o mesmo e, para a variável Recurso, que ele tem apenas um único recurso aplicável. Quando todas as variáveis são limites, uma solução é encontrada.

### <a name="constraint-levels"></a>Níveis de restrição

Quando o agendamento é executado como parte da fase de cobertura do requisições de materiais (MRP), as ordens serão agendadas para antes da data de requisição. No entanto, se não for possível encontrar um agendamento que é iniciado hoje ou depois e concluído antes da data da requisição, a direção do agendamento mudará para depois de hoje.

Essa principal regra comercial é tratada organizando as restrições em níveis. Se nenhuma solução for encontrada ao usar as restrições no nível mais alto, as restrições desse nível serão todas ignoradas, e o nível mais baixo será tentado. Na prática, isso significa que, para o agendamento regressivo, o modelo terá um nível 1 com metas de trabalho da hora de início mais recente, considerando a restrição de hora de término máxima (a data da requisição) e um nível 0 com metas de trabalho da hora inicial mais antiga e considerando a restrição de hora de início mínima de hoje.

### <a name="algorithm"></a>Algoritmo

As etapas principais do algoritmo do mecanismo são:

1. Localize sequências (cadeias de trabalhos) que podem ser resolvidas separadamente.
1. Tentar encontrar uma solução inicial da sequência para o nível mais alto de restrição.
    1. Classifique os trabalhos na sequência com base na meta e nas prioridades do trabalho, de forma que um trabalho inicial possa ser encontrado.
    1. Execute loops dos trabalhos na seguinte sequência:
        1. Localize todas as restrições que precisam ser propagadas e execute a propagação.
        1. Se todas as variáveis do trabalho foram limitadas, uma solução para esse trabalho foi encontrada.
        1. Se uma das variáveis não pôde ser limitada sem violar as restrições, reverta a associação de variável, tente um valor diferente no domínio (para a variável de recurso) e execute novamente a propagação da restrição.
1. Se nenhuma solução foi encontrada, todas as restrições no nível de restrição atual serão removidas, o nível de restrição será diminuído (se houver níveis inferiores disponíveis) e a pesquisa de solução será repetida com o novo conjunto de restrições.
1. Se uma solução possível foi encontrada, a fase de otimização será iniciada, que tentará encontrar uma solução melhor até que o tempo limite de otimização seja atingido ou que todas as combinações de recursos tenham se esgotado.

O agente de resolução de restrições não está ciente das especificações do algoritmo de agendamento. É na definição e na combinação das várias restrições que a "mágica" acontece.

### <a name="determining-working-times"></a>Determinar horários de trabalho

Uma grande parte das restrições (internas) no mecanismo controla o horário de trabalho e a capacidade de um recurso. Basicamente, a tarefa é percorrer os slots de horário de trabalho para um recurso de um determinado ponto em uma determinada direção e localizar um intervalo longo o suficiente no qual a capacidade necessária de trabalho (tempo) pode ser ajustada.

Para isso, o mecanismo precisa saber os horários de trabalho de um recurso. Ao contrário dos dados do modelo principal, os horários de trabalho são *carregados lentamente*, o que significa que eles são carregados no mecanismo, conforme necessário. O motivo dessa abordagem é que, em geral, há horários de trabalho no Supply Chain Management de um calendário para um período muito longo, e geralmente há muitos calendários, portanto, os dados seriam muito grandes para serem pré-carregados.

As informações do calendário são solicitadas pelo mecanismo em partes, invocando o método da classe X++ `WrkCtrSchedulingInteropDataProvider.getWorkingTimes`. A solicitação é para uma ID de calendário específica em um intervalo de tempo específico. Dependendo do estado do cache do servidor no Supply Chain Management, cada uma dessas solicitações pode resultar em várias chamadas de banco de dados, o que leva muito tempo (em relação ao tempo computacional em si). Além disso, se o calendário contém definições de horário de trabalho muito elaboradas com muitos intervalos de tempo de trabalho por dia, isso aumenta o tempo necessário para o carregamento.

Quando os dados de horário de trabalho são carregados no mecanismo de agendamento, eles são mantidos no seu cache interno para o calendário específico, o que significa que, se algum outro trabalho ou recurso estiver usando o mesmo calendário, as próximas pesquisas poderão ser executadas rapidamente da memória. Uma causa comum de desempenho incorreto é se uma ID de calendário separada for usada para cada recurso, pois os dados precisarão ser solicitados para cada calendário, mesmo que o conteúdo dos calendários possa ser o mesmo.

### <a name="finite-capacity"></a>Capacidade finita

Ao usar a capacidade finita, os slots de horário de trabalho do calendário são divididos e reduzidos com base nas reservas de capacidade existentes. Essas reservas também são buscadas por meio da mesma classe `WrkCtrSchedulingInteropDataProvider` que os calendários, mas, em vez disso, usam o método `getCapacityReservations`. Ao agendar durante o planejamento mestre, as reservas para o plano mestre específico são consideradas e, se habilitadas na página **Parâmetros do planejamento mestre**, as reservas das ordens de produção confirmadas também serão incluídas. Da mesma forma, ao agendar uma ordem de produção, também é uma opção incluir reservas de ordens planejadas existentes, embora isso não seja tão comum quanto o contrário.

O uso da capacidade finita causará demora no agendamento devido a vários motivos:

- A busca de informações sobre capacidade no banco de dados é uma operação lenta, e o cache do servidor de informações sobre capacidade normalmente não é tão bom para horários de trabalho, pois eles não são compartilhados entre os recursos, como calendários normalmente são.
- O número de slots de horário de trabalho aumentam devido às divisões, e os slots para um período maior normalmente devem ser investigados antes que uma solução possa ser encontrada.
- Depois que o agendamento for concluído, uma verificação de reservas conflitantes deverá ser realizada (consulte a seção "Executar mecanismos de agendamento em paralelo" para obter detalhes).

### <a name="examining-the-resource-combinations"></a>Examinar as combinações de recursos

Se a sequência de trabalhos tiver somente os links `FinishStart` padrão, o que significa que ela forma uma cadeia simples sem ramificações, um resultado ideal (visto da ordem única, não várias ordens) poderá ser alcançado ao encontrar a melhor solução para o primeiro trabalho e avançar para encontrar a melhor solução para o próximo trabalho. A melhor solução para um trabalho significa encontrar o recurso que pode obter a data de início e término do trabalho mais próximas da meta do trabalho (no agendamento antecipado, isso significa obter a data de término do trabalho o mais cedo possível), ainda respeitando as restrições.

Quando houver trabalhos paralelos, encontrar uma solução pode envolver a verificação de diferentes combinações de recursos. O número de possíveis combinações de recursos é o produto do número de recursos aplicáveis para os trabalhos paralelos conectados. Principalmente ao agendar uma ordem regressivamente a partir de uma data de requisição, pode demorar muito para a lógica perceber que não há solução para o problema que fará com que os trabalhos paralelos ocorram antes da data de hoje, pois será necessário verificar todas as combinações, já que pode haver alguns recursos que tinham maior eficiência ou um calendário diferente que pode gerar um resultado. Isso significa que, se nenhum limite for definido, ele será executado por muito tempo antes de alterar a direção para depois.

Essa lógica de combinação também significa que adicionar mais recursos aplicáveis pode tornar o mecanismo mais lento. Se ocorrerem problemas de desempenho durante a execução de operações paralelas e agendamento com capacidade infinita, isso poderá ser corrigido parcialmente, fazendo com que o criador de roteiros decida qual recurso deve ser usado e, em seguida, atribuir o recurso diretamente na operação (porque, na maioria dos casos, o mecanismo sempre acabará selecionando o mesmo recurso e, portanto, o resultado final será o mesmo).

### <a name="hard-links"></a>Links rígidos

Definir o tipo de link entre dois trabalhos para rígido garante que não haja intervalo de tempo entre o término de um trabalho e o início do próximo. Isso pode ser muito útil em cenários como quando o metal é aquecido em um trabalho e, em seguida, processado no próximo, no qual não é desejável que o metal esfrie.

Com links flexíveis e agendamento antecipado padrão, se o roteiro formar uma cadeia simples sem ramificações, um resultado poderá ser alcançado ao encontrar uma solução para o primeiro trabalho que atenda às suas próprias restrições e avançar na cadeia, propagando a hora de término do trabalho anterior, para o próximo trabalho. Se o trabalho atual não encontrar nenhuma capacidade, a hora de início dele será atrasada ainda mais, sem consequências para a possível criação de lacunas entre os trabalhos. No entanto, com links rígidos (principalmente em conexão com capacidade finita) para o mesmo cenário, o fato de que um trabalho posterior na cadeia não consegue encontrar capacidade significará que todos os trabalhos agendados anteriores precisarão ser "arrastados" um por um e, portanto, reagendados várias vezes. Principalmente em cenários com alta carga para vários recursos, os links rígidos podem causar uma reação em cadeia, em que os trabalhos afetarão uns aos outros, e várias iterações precisarão ser feitas antes de o resultado se estabilizar em um agendamento viável.

## <a name="running-scheduling-engines-in-parallel"></a>Executar mecanismos de agendamento em paralelo

Ao executar o agendamento como parte de uma execução de planejamento mestre onde são usados auxiliares, cada um dos threads de auxiliares de planejamento mestre também pode selecionar tarefas de agendamento de ordem de produção. Isso significa que vários mecanismos de agendamento podem ser executados ao mesmo tempo. Embora o multithread em geral seja um benefício de desempenho muito significativo, há também algumas desvantagens funcionais quando se trata de agendamento.

No MRP, todas as ordens de produção para um determinado nível da lista de materiais (BOM) são agendadas em sequência de datas de requisições, o que significa que as ordens com a data de requisição mais antiga devem ser agendadas primeiro e, assim, têm a maior probabilidade de obter a capacidade disponível do recurso. No entanto, com vários mecanismos selecionando com base na lista de ordens não agendadas, a sequência não é mais garantida, pois uma pode ser concluída mais rapidamente do que a outra.

Além disso, ao agendar o uso da capacidade finita e quando várias instâncias de mecanismo estão tentando agendar ordens que podem estar usando os mesmos recursos no mesmo intervalo de tempo, pode ocorrer uma condição de concorrência. O número dessas condições de concorrência é registrado no campo **Conflitos de agendamento** na página de histórico de planos mestre. A lógica de resolução de conflitos é a seguinte:

- Agende uma ordem (sem bloqueio) e obtenha reservas de capacidade.
- Faça o bloqueio.
- Verifique se há reservas de capacidade mais recentes para os recursos agendados no intervalo de tempo.
  - Em caso negativo, anote a capacidade e libere o bloqueio.
  - Em caso afirmativo, libere o bloqueio e agende novamente a ordem desde o início.

Portanto, ao agendar com várias instâncias de mecanismo, o resultado não é totalmente determinístico porque dependerá do tempo exato de cada um dos threads.

## <a name="operation-scheduling-performance"></a>Desempenho do agendamento de operações

Embora o agendamento de operações também seja conhecido como planejamento da capacidade de corte, do ponto de vista de um mecanismo, ele poderá ser um problema mais difícil de ser resolvido se a capacidade finita for usada, pois mais dados serão necessários para determinar a viabilidade.

A capacidade de um grupo de recursos depende de quais e quantos recursos são membros do grupo de recursos. Um grupo de recursos em si não tem capacidade alguma; ele só terá capacidade quando os recursos forem membros do grupo. Como a associação do grupo de recursos pode variar ao longo do tempo, a capacidade deve ser avaliada por dia.

No agendamento de operações, o calendário do grupo de recursos é usado para determinar as horas de início e término de cada operação. Isso significa que o calendário do grupo de recursos insere um limite de quanto tempo as operações podem ser agendadas para uma operação em um dia, em um grupo de recursos. Ao contrário do calendário dos recursos específicos, os dados de eficiência do calendário são ignorados para o grupo de recursos, pois eles simplesmente denotam os horários de abertura, e não a capacidade real.

Por exemplo, se o horário de trabalho de um grupo de recursos em uma data específica for das 8:00 às 16:00, uma operação não poderá colocar mais carga no grupo de recursos do que pode ser feito em 8 horas, independentemente do quanto de capacidade o grupo de recursos disponibilizou no total nesse dia. Entretanto, a capacidade disponível pode limitar ainda mais a carga.

A carga do agendamento de trabalhos em todos os recursos incluídos no grupo de recursos em um determinado dia é considerada quando a capacidade disponível do grupo de recursos é calculada no mesmo dia. Para cada data, o cálculo é:

*Capacidade do grupo de recursos disponível = capacidade de recursos no grupo com base no calendário &ndash; Carga de trabalho agendada nos recursos do grupo &ndash; Carga de operações agendada nos recursos no grupo &ndash; Carga de operações agendada no grupo de recursos*

Na guia **Requisitos de recursos** da operação de roteiro, os requisitos de recursos podem ser especificados usando um recurso específico (nesse caso, a operação será agendada com esse recurso), para um grupo de recursos, para um tipo de recurso ou para um ou mais recursos, habilidade, curso ou certificado. Embora o uso de todas essas opções forneça uma grande flexibilidade na criação do roteiro, também complica o agendamento para o mecanismo, pois a capacidade deve ser considerada por "propriedade" (o nome abstrato usado no mecanismo para capacidade, habilidades, etc.).

A capacidade do grupo de recursos para uma capacidade é a soma da capacidade de todos os recursos no grupo de recursos que têm a capacidade em questão. Se um recurso no grupo tiver uma capacidade, ele será considerado independentemente do nível de capacidade necessário.

No agendamento de operações, a capacidade disponível para um determinado recurso de um grupo de recursos será reduzida quando for carregada com uma operação que exige o recurso em questão. Se a operação exigir mais de um recurso, a capacidade será reduzida para todos os recursos necessários.

Para cada data, o cálculo necessário é:

*Capacidade disponível para um recurso = capacidade para o recurso &ndash; Carga de trabalho agendada nos recursos com o recurso específico, incluído no grupo de grupo de recursos &ndash; Carga de operações agendada nos recursos com o recurso específico, incluído no grupo de recursos &ndash; Carga de operações agendada no próprio grupo de recursos, que exige o recurso específico*

Isso significa que, se houver carga em um recurso específico, ela será considerada no cálculo da capacidade disponível do grupo de recursos por capacidade, pois a carga em um recurso específico reduz sua contribuição para a capacidade do grupo de recursos, não importa se a carga do recurso específico for para essa capacidade específica. Se houver carga no nível do grupo de recursos, ela será considerada no cálculo da capacidade disponível do grupo de recursos por capacidade somente se a carga for de uma operação que exija a capacidade específica.

A lógica acima é complicada, pois é a mesma para cada tipo de "propriedade", de forma que o uso do agendamento de operações com capacidade finita exige que um volume significativo de dados seja carregado.

## <a name="viewing-scheduling-engine-input-and-output"></a>Exibir a entrada e a saída do mecanismo de agendamento

Para obter detalhes específicos sobre a entrada e a saída do processo de agendamento, habilite o log acessando **Administração da organização \> Configuração \> Agendamento \> Ferramenta cockpit de rastreamento de agendamento**.

Nesta página, primeiro selecione **Habilitar log** no Painel de ações. Em seguida, execute o agendamento da ordem de produção. Ao concluir, retorne à página **Ferramenta cockpit de rastreamento de agendamento** e selecione **Desabilitar log** no Painel de ações. Atualize a página e uma nova linha será exibida na grade. Selecione a nova linha e selecione **Download** no Painel de ações. Isso gerará uma pasta compactada .zip, contendo os seguintes arquivos:

- **Log.txt** - Este é o arquivo de log que descreve as etapas pelas quais o mecanismo passa. É muito elaborado e pode ser um pouco difícil, mas quando usado como parte do experimento com a configuração de roteiro para resolver problemas de desempenho, a primeira coisa a procurar é a diferença no tempo entre a primeira e a última linha, pois isso lhe dará o tempo exato que o agendador gastou.
- **XmlModel.xml** - Contém o modelo criado em X++ e no qual o mecanismo é operado. O `JobId` usado no arquivo se correlaciona com o `RecId` da tabela de origem que contém os trabalhos (`ReqRouteJob` ou `ProdRouteJob`). O mais comum a se notar neste arquivo é que as datas fornecidas em `ConstraintJobStartsAt` e `ConstraintJobEndsAt` são as esperadas, que a propriedade `JobGoal` está definida corretamente e que os trabalhos estão relacionados entre si por meio das restrições `JobLink`.
- **XmlSlots.xml** - Contém todos os horários de trabalho e as reservas de capacidade que o mecanismo solicitou. Os horários de trabalho e as reservas do calendário só serão solicitadas pelo mecanismo para os períodos em que tenta inserir os trabalhos (e um buffer extra). Portanto, se o arquivo contiver tempos muito distantes no futuro, poderá ser uma indicação de um problema com a configuração. Os nós `ResourceProperty` mostrarão, para cada recurso, a qual grupo de recursos e capacidades ele está associado para quais períodos.
- **Result.xml** - Contém o resultado da execução do agendamento.

Observe que a funcionalidade de rastreamento pode adicionar uma sobrecarga de desempenho significativa, portanto, use-a apenas na investigação do agendamento de ordens específicas de forma controlada. Se ela estiver ativada durante a execução de um planejamento mestre, ela alcançará rapidamente o seu limite de tamanho e parará.

## <a name="troubleshooting-performance"></a>Solucionar problemas de desempenho

Conforme explicado em todas as seções anteriores, há algumas armadilhas no que se refere à configuração e ao uso do mecanismo de agendamento, que podem causar problemas de desempenho. A lista de verificação a seguir pode ser usada para solucionar problemas desse tipo. É importante observar todos os detalhes, pois normalmente é uma combinação de vários fatores que resulta em problemas.

### <a name="performing-scheduling-as-part-of-mrp-when-it-is-not-needed"></a>Executar o agendamento como parte do MRP quando não for necessário

Mesmo que os roteiros sejam usados para fins do controle de produção, como custos e relatórios, talvez não seja necessário considerá-los durante o MRP. Em alguns casos, o prazo de entrega padrão especificado da produção do item será suficiente para o planejamento. Para desativar o agendamento de roteiro, defina o limite de tempo de capacidade como zero. Se o agendamento deve ser feito, o limite de tempo de capacidade deve ser cuidadosamente definido porque talvez não seja necessário considerar os roteiros para a extensão total do limite de tempo de cobertura do MRP.

Observe que, se a ordem não for agendada durante o MRP, ela deverá ser agendada quando a ordem planejada for confirmada. Isso significa que o processo de confirmação levará mais tempo, de forma que, dependendo de quantas ordens planejadas sugeridas forem confirmadas, o ganho de desempenho durante o MRP poderá ser perdido na confirmação.

### <a name="route-with-unnecessary-operations"></a>Roteiro com operações desnecessárias

Ao criar o roteiro, ele tenta modelar o mundo real exatamente com todas as etapas pelas quais a produção passa. Embora isso possa ser útil em alguns casos, não é bom para o desempenho, pois o modelo que o mecanismo precisa para funcionar aumenta (tanto em termos de trabalho e quanto em restrições) e mais instruções SQL serão executadas para inserção e atualização dos trabalhos e das reservas de capacidade. Além disso, há o efeito downstream de ter de relatar o progresso nos trabalhos, que pode ser atenuado com lançamentos automáticos. Se os dados não forem usados para nada, eles criarão uma carga desnecessária.

É recomendável criar somente operações que sejam rigorosamente necessárias para o agendamento (que normalmente são os recursos de afunilamento) e/ou fins de custos. Como alternativa, você deve agrupar várias operações distintas e menores em uma operação maior que representa uma parte maior do processo.

### <a name="many-applicable-resources-for-an-operation"></a>Muitos recursos aplicáveis para uma operação

O número de recursos aplicáveis para uma operação é determinado de acordo com os requisitos de recursos definidos na relação de operação. O requisito pode ser para um recurso específico (individual) ou pode ser baseado na associação do recurso de um grupo de recursos ou uma capacidade.

Se o agendamento não for feito usando a capacidade finita e todos os recursos aplicáveis tiverem o mesmo calendário e a mesma eficiência, o mecanismo de agendamento sempre acabará selecionando o mesmo recurso para uma operação, mas somente depois de testar todos os recursos aplicáveis para verificar se há algum "melhor" do que os outros. Nesse caso, a carga do agendamento pode ser bastante reduzida simplesmente por meio da atribuição de um recurso específico à operação no tempo de criação do roteiro.

### <a name="route-with-parallel-operations"></a>Roteiro com operações paralelas

Enquanto operações paralelas (principais/secundárias) são uma ferramenta poderosa para modelar cenários, como quando um computador e um operador são necessários para executar uma tarefa específica, também é a origem de vários problemas de desempenho. Se um requisito de um recurso individual específico for atribuído à operação principal e secundária, normalmente não será um problema. Mas se houver vários recursos possíveis para cada uma das operações, isso adicionará uma complexidade computacional significativa ao agendamento.

Uma alternativa ao uso de operações paralelas é modelar os pares como recursos "virtuais" (que representarão a equipe que sempre vai para a operação) ou simplesmente não modelar uma das operações se não representar um afunilamento.

### <a name="route-with-quantity-of-resources-higher-than-1"></a>Roteiro com quantidade de recursos maior que 1

Se a configuração da quantidade de recursos necessários para uma operação for superior a um, o resultado será o mesmo que o uso de operações principais/secundárias, pois vários trabalhos paralelos serão enviados para o mecanismo. No entanto, nesse caso, não há uma opção de usar atribuições específicas de recursos, porque uma quantidade superior a um exige que mais de um recurso seja aplicável à operação.

### <a name="excessive-use-of-finite-capacity"></a>Uso excessivo de capacidade finita

O uso da capacidade finita exige que o mecanismo carregue as informações de capacidade de um banco de dados e tenha uma sobrecarga computacional, pois será mais difícil encontrar uma solução principalmente em ambientes nos quais os recursos estão reservados próximos à capacidade máxima. Como resultado, é importante avaliar com cuidado se um recurso realmente precisa usar capacidade finita ou se pode estar excessivamente reservado. Como pode haver uma diferença entre os recursos de capacidade finita sobre a importância de não reservar excessivamente, é recomendável usar a opção de afunilamento em um recurso em combinação com um valor separado no plano em "Limite de tempo de capacidade para recursos de afunilamento". O uso do conceito de afunilamento pode permitir que o limite de tempo de capacidade finita geral possa ser reduzido.

### <a name="setting-hard-links"></a>Configurar links rígidos

O tipo de link padrão do roteiro é *flexível*, o que significa que um intervalo de tempo é permitido entre a hora de término de uma operação e o início da próxima. Isso pode ter o efeito indesejado de que, se os materiais ou a capacidade não estiverem disponíveis para uma das operações por um período muito longo, a produção poderá ficar ociosa por muito tempo, o que significa um possível aumento do trabalho em andamento. Isso não ocorrerá com links rígidos porque o término e o início devem alinhar-se perfeitamente. Mas a definição de links rígidos dificulta o problema de agendamento porque interseções de capacidade e horário de trabalho devem ser calculadas para os dois recursos das operações. Se também houver operações paralelas envolvidas, isso adicionará um período computacional significativo. Se os recursos das duas operações tiverem calendários diferentes que não se sobrepõem, o problema não poderá ser resolvido.

Recomendamos o uso de links rígidos somente quando necessários, e considere com cuidado se é necessário para cada operação do roteiro.

Para reduzir o trabalho em andamento sem aplicar links rígidos, um truque é agendar a ordem duas vezes com a alteração para a direção oposta na segunda passagem. Se o primeiro agendamento tiver sido realizado regressivamente a partir da data de entrega, o segundo deverá ser feito a partir da data de início agendada. Isso resultará na máxima compactação dos trabalhos, de forma que o trabalho em andamento seja minimizado.

### <a name="separate-calendar-for-each-resource"></a>Calendário separado para cada recurso

Uma das principais fontes de dados do mecanismo de agendamento são as informações de calendário, que podem ser caras para carregar do banco de dados. Como os calendários são gerados com base nos modelos, é tentador gerar um calendário para cada recurso e ajustar as informações neste calendário quando o recurso tem tempo de inatividade e outros problemas. No entanto, isso limitará muito a capacidade do mecanismo de armazenar em cache os dados do calendário, pois seria necessário solicitar novos dados para cada recurso e pode ser uma grande fonte de problemas de desempenho. Em vez disso, recomendamos reutilizar os calendários o máximo possível entre os recursos e, em seguida, controlar as alterações de tempo de inatividade atribuindo uma ID de calendário diferente para um período.

### <a name="high-number-of-working-time-slots-per-calendar-day"></a>Alto número de slots de horário de trabalho por dia do calendário

Como o mecanismo funciona examinando os intervalos de tempo individualmente para capacidade, é vantajoso minimizar o número de slots de horário por dia do calendário. Por exemplo, isso pode ser feito considerando se é importante que o agendamento resultante reflita que os funcionários têm um intervalo de 5 minutos a cada hora.

### <a name="large-or-none-scheduling-timeouts"></a>Tempos limite de agendamento longos (ou nenhum)

O desempenho do mecanismo de agendamento pode ser otimizado usando parâmetros encontrados na página **Parâmetros de agendamento**. As configurações **Tempo limite de agendamento habilitado** e **Tempo limite de otimização de agendamento habilitado** sempre devem estar definidas como **Sim**. Se forem definidas como **Não**, o agendamento poderá ser executado infinitamente se um roteiro inviável com muitas opções tiver sido criado.

O valor para **Tempo máximo de agendamento por sequência** controla o número de segundos que podem, no máximo, ser gastos na tentativa de encontrar uma solução para uma única sequência (na maioria dos casos, uma sequência corresponde a uma única ordem). O valor a ser usado aqui depende muito da complexidade do roteiro e das configurações, como a capacidade finita. No máximo, cerca de 30 segundos é um bom ponto de partida.

O valor para **Tempo limite de tentativas de otimização** controla quantos segundos podem, no máximo, ser usados para encontrar uma solução melhor do que aquela encontrada inicialmente. Isso só influenciará os roteiros que estão usando operações paralelas, pois elas tornam necessário testar combinações diferentes.

> [!NOTE]
> Os valores definidos para os tempos limite serão aplicados para o agendamento de ordens de produção liberadas e ordens planejadas como parte do MRP. Como resultado, definir valores muito altos poderia adicionar significativamente ao tempo de execução do MRP durante a execução de um plano com muitas ordens de produção planejadas.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]