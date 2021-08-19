---
title: Planejamento de trabalho
description: Este artigo fornece informações sobre o plano de trabalho, que é um formulário mais detalhado de programação do plano de operações. Você pode usar o agendamento de trabalho para agendar trabalhos individuais ou ordens de fábrica e para controlar o ambiente de manufatura.
author: ChristianRytt
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ProdSchedule
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19431
ms.assetid: aef37341-91d8-4263-80eb-35d9584be156
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: bc782a46f01464f2e0fea7eaf1d05a915bf735c7b4280676e45442af9440ae98
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6717091"
---
# <a name="job-scheduling"></a>Planejamento de trabalho

[!include [banner](../includes/banner.md)]

Este artigo fornece informações sobre o plano de trabalho, que é um formulário mais detalhado de programação do plano de operações. Você pode usar o agendamento de trabalho para agendar trabalhos individuais ou ordens de fábrica e para controlar o ambiente de manufatura.

Você pode usar o agendamento de trabalho para agendar trabalhos individuais ou ordens de fábrica e para controlar o ambiente de manufatura. O agendamento de trabalho divide cada operação em suas tarefas ou trabalhos individuais. Esses trabalhos são então atribuídos aos recursos de operações que vão executá-los. O agendamento de trabalho também permite sincronizar todos os trabalhos que são referenciados pelo trabalho selecionado. Você pode especificar uma data e hora de início ou de término para o trabalho e depois executar o agendamento. A hora especificada pode ser de início ou de término, dependendo da direção do agendamento. Essa funcionalidade é útil quando, por exemplo, um trabalho deve ser executado somente em um computador de cada vez ou quando você quiser otimizar o trabalho executado para cada recurso.

## <a name="tasks-in-the-job-scheduling-process"></a>Tarefas no processo de agendamento de trabalho
O processo de agendamento de trabalho inclui as seguintes tarefas:

-   Dividir as operações em trabalhos.
-   Planejar trabalhos baseados nas datas e horas dos recursos que são especificados para a operação relacionada.
-   Calcular as horas de início e de término de cada trabalho. Você pode usar a capacidade finita para garantir que não haja sobreposição de horas.
-   Determinar quais recursos no grupo de recursos executarão o trabalho. Esta tarefa exige que um grupo de recursos seja especificado para uma operação. O agendamento de trabalho seleciona os recursos ou grupos de recursos com base no prazo de entrega mais curto e também considera qualquer reserva anterior dos recursos.
-   Explorar operações em trabalhos quando você executar o agendamento de trabalho. Os trabalhos são planejados por data e hora de acordo com a ordem especificada pelo roteiro de produção. A configuração da operação determina os trabalhos que serão detalhados durante o processo de agendamento. O grupo de roteiros que é atribuído à operação controla se os trabalhos serão gerados. Um trabalho só é gerado se tem uma duração específica. Por exemplo, um trabalho de tempo de transporte será gerado se o tempo de transporte foi especificado para a operação selecionada.

## <a name="scheduling-direction"></a>Direção do plano
Você pode planejar trabalhos para frente ou para trás.

-   **Adiantar** – use a direção de agendamento antecipado para iniciar a produção o mais cedo possível. Isso também é conhecido como método push, pois a produção está sendo adiantada por meio do processo de produção. A produção é planejada para iniciar e terminar nas datas mais próximas possíveis.
-   **Atrasar** – use a direção de agendamento retroativo para iniciar a produção o mais tarde possível. Isso também é conhecido como método pull, pois ele se baseia na data em que a produção deve ser concluída. O agendamento retroativo é contado de modo regressivo para a data mais longe possível em que a produção pode ser iniciada sem que o prazo final alvo seja comprometido.

## <a name="finite-capacity"></a>Capacidade finita
Você pode planejar trabalhos usando a capacidade finita. Quando você usar a capacidade finita, a capacidade que é planejada não poderá ser maior que a capacidade disponível para o recurso. O tempo disponível é definido como o intervalo de tempo em que o recurso está disponível e no qual não há outras reservas de capacidade. O agendamento que se baseia na capacidade finita garante que as horas de início e término para uma operação em uma data específica não se sobreponham. A capacidade do recurso que já está reservada é considerada e as sobreposições entre as horas de início e término também são consideradas. A capacidade finita determina o valor de capacidade que deve estar disponível para um recurso a fim de obter o uso ideal desse recurso. A determinação é equilibrada em relação ao cálculo do prazo de entrega mais curto possível entre as operações.

## <a name="finite-materials"></a>material finito
O agendamento de trabalho que se baseia nos materiais finitos garante que os materiais necessários estejam disponíveis no início da operação. As regras de cobertura para itens definem esses limites. O agendamento usa o detalhamento de requisitos para determinar quando os itens de componente estarão disponíveis. Se você planejar sem configurar materiais finitos, o sistema presumirá que todos os itens estarão disponíveis quando necessário.

## <a name="finite-properties"></a>Propriedades finitas
O agendamento de trabalho que é baseado em propriedades especiais exige que as propriedades sejam especificadas para as operações no roteiro de produção. Essas propriedades devem ser preenchidas para reservar capacidade.

## <a name="references"></a>Referências
O agendamento de trabalho planeja todas as produções que são referenciadas pela produção atual. Se uma produção tiver uma ou mais subproduções, estas devem ser planejadas ao mesmo tempo que a produção principal, pois a produção principal não pode ser iniciada até que as subproduções relacionadas sejam concluídas.

## <a name="schedule-resources"></a>Programar recursos
O mecanismo de agendamento examina as combinações de recursos para identificar as combinações que podem atender aos requisitos. Você pode especificar critérios de seleção ao selecionar um destes valores no campo **Seleção do recurso principal** da página **Parâmetros de agendamento**:

-   **Duração** – o mecanismo de agendamento seleciona o recurso com o prazo de entrega mais curto. **Observação:** o agendamento por duração pode reduzir o desempenho quando o mesmo grupo de recursos contiver muitos recursos e forem usadas operações secundárias. É possível planejar um máximo de 32 recursos por operação. Se você exceder essa quantidade, uma mensagem do log de informações será exibida e o agendamento de trabalho não encontrará o melhor recurso alternativo.
-   **Prioridade** – o mecanismo de agendamento selecionará o recurso com a prioridade mais alta se dois ou mais recursos tiverem níveis e capacidades idênticos. O recurso com o valor numérico mais baixo nesse campo tem a prioridade mais alta.

Quando o agendamento de trabalho é executado, o sistema planeja os recursos com base nas limitações que são definidas nos parâmetros do recurso. Você pode controlar a capacidade dos recursos usando as configurações de calendário. O sistema calcula cargas para recursos durante o processo de agendamento. **Observação:** para produções que usam a função de plano de operações, você pode executar o plano de trabalho após o plano de operações. Se não estiver usando o plano de operações, você poderá executar o plano de trabalho sozinho.

## <a name="maximum-capacities-for-resources-per-job-order"></a>Capacidades máximas para recursos por ordem de trabalho
Os recursos são atribuídos aos trabalhos por meio do agendamento de trabalho. Você pode estabelecer capacidades máximas para recursos por ordem de trabalho. Por exemplo, você pode configurar o sistema para planejar até 50% da capacidade total para uma ordem de produção. Essa configuração oferece mais controle sobre o agendamento de recursos no nível do plano de trabalho. Portanto, ela pode ajudar a impedir problemas caso não haja capacidade suficiente disponível para executar produções simultâneas.

## <a name="resource-efficiency"></a>Eficiência de recursos
O agendamento de trabalho considera as porcentagens de eficiência que são especificadas para os recursos. As porcentagens de eficiência reduzem ou aumentam o tempo reservado para o recurso. Dessa forma, o prazo de entrega também aumenta ou diminui. A fórmula a seguir é usada usada para o cálculo: Hora de agendamento= Hora × 100 ÷ Porcentagem de eficiência Nesta fórmula, *Hora* inclui o tempo de execução e o tempo de preparação.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]