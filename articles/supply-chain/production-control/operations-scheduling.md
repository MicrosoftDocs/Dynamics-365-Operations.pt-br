---
title: Plano de operações
description: Este tópico fornece informações sobre agendamento de operações. Você pode usar o plano de operações para fornecer uma estimativa geral do processo de produção ao longo do tempo.
author: ChristianRytt
manager: tfehr
ms.date: 06/20/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProdSchedule
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 198073
ms.assetid: 12c28b11-80aa-4668-b15b-724cb24890bd
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e95374e0aebca825f589f13eda389d6612737181
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3211344"
---
# <a name="operations-scheduling"></a>Plano de operações

[!include [banner](../includes/banner.md)]

Este tópico fornece informações sobre agendamento de operações. Você pode usar o plano de operações para fornecer uma estimativa geral do processo de produção ao longo do tempo.

Você pode planejar a produção no nível de operação e o nível do profissional. Diferente do agendamento de trabalho, o agendamento de operações não expande as operações para a rota de produção em trabalhos. Se desejar incluir mais detalhes no agendamento, como informações sobre a capacidade atual, você pode executar o agendamento de trabalho após a execução de agendamento de operações. Você também pode executar um agendamento de trabalho apenas. O agendamento de trabalho é o plano de trabalhos individuais no chão de fábrica e normalmente ocorre em uma prazo imediato ou a curto prazo.

## <a name="components-of-operations-scheduling"></a>Componentes principais do agendamento de operações
Os principais componentes do agendamento de operações são o método de agendamento, a capacidade dos centros de trabalho e a otimização do material. Usando o agendamento de projeto, é possível alcançar os seguintes objetivos:

-   Controlar o método de planejamento (por exemplo, agendamento progressivo ou regressivo a partir de uma data)
-   Otimizar o uso de recursos de agendamento produções com base na capacidade de recursos. Essa abordagem também ajuda a identificar quando devem ser usados os recursos alternativos.
-   Otimizar o uso de materiais de agendamento produções com base na disponibilidade dos materiais necessários.
-   Programar e sincronizar produções de referência. As datas das produções de referência são ajustadas quando são feitas alterações no plano da ordem de produção.

Você deve estimar o custo de uma ordem de produção para que você possa executar o agendamento de operações. Se você não executar uma estimativa, ela será executada automaticamente antes do início do processo de agendamento de operações. Um plano de operações especificar as seguintes informações:

-   os produtos que são planejados para a produção
-   A configuração do item
-   As quantidades envolvidas na produção
-   As datas de início e término da produção
-   As reservas de capacidade para os recursos que executam as atividades de produção

O tempo de preparação, tempo de processamento, e o tempo de execução são definidos para as operações na produção. Depois que você executa o agendamento de operações, o status da ordem de produção é **Agendado**, e todas as operações são planejadas na ordem que é especificado pelo roteiro de produção. No entanto, apenas a duração da operação será considerada. A hora inicial e a hora final não são programadas.

## <a name="scheduling-direction-and-date"></a>Direção e data do plano
A direção do plano é fundamental para o processo de planejamento. A produção pode ser planejada para frente ou para trás a partir de qualquer data, dependendo das necessidades de tempo e agendamento.

-   **Avançar a partir da data do agendamento** – Você pode agendar a produção do plano para iniciar o mais rápido. A produção pode ser iniciada hoje, amanhã ou em qualquer data futura. A produção é planejada para frente no tempo até a primeira data possível.
-   **Avançar a partir da data do agendamento** – Você pode agendar a produção do plano para iniciar o mais rápido. O agendamento regressivo é com base na data em que a produção deve ser concluída. O plano conta a partir de essa data até a data mais posterior possível em que a produção pode ser iniciada e ainda ser concluída por tempo.

## <a name="resource-scheduling"></a>Agendamento do recurso
Quando você executa um plano de operações, cada operação no roteiro de produção será programada para o recurso especificado para a operação. Além disso, a duração de cada operação é especificada no roteiro de produção. Se um grupo de recursos estiver especificado para uma operação, o agendamento reserva a capacidade no grupo. No entanto, diferentemente do agendamento de trabalho, o agendamento de operações não selecionar os recursos específicos do grupo. Se você estiver trabalhando com capacidade finita, o plano depende da disponibilidade dos recursos necessários para concluir a produção. O agendamento de operações segue a sequência de operações que é especificada no roteiro de produção. O agendamento de operações reserva a capacidade nos grupos de recursos com base nos tempos de operação definidos no roteiro de produção. A soma da capacidade disponível em recursos envolvidos determina a capacidade do grupo de recursos. as reservas de capacidade que já existem para os recursos são consideradas como a capacidade não disponível. Se não houver capacidade disponível suficiente para a produção, as ordens de produção podem ser atrasadas ou até mesmo interrompidas. Você também pode especificar a eficiência que você espera de recursos que estão envolvidos na produção. Você especifica a eficiência como uma porcentagem do recurso. A porcentagem de eficiência ajusta a produção do recurso. Esses ajustes afetam o tempo reservado para o recurso. Os prazos de entrega para as operações que usam o recurso também serão ajustados de acordo.

## <a name="operations-scheduling-and-master-planning"></a>Agendamento de operações e planejamento mestre
O plano de operações também norteia o planejamento mestre, que determina todos os cálculos de requisito de material. O agendamento de operações considera as seguintes informações:

-   **Produções em registros anteriores** – Produtos que são planejados, liberados ou iniciados.
-   **Disponibilidade de material** – Estoque, subprodução, provedores e fornecedores
-   **Disponibilidade de capacidade** – recursos necessários para a produção

> [!NOTE]
> Se estiver usando o planejamento mestre de vários threads e o plano de operações, a capacidade finita não será considerada. 

## <a name="cancellations"></a>Cancelamento
Quando você executa o agendamento de operações, você pode cancelar algumas partes do roteiro. Essas partes incluem o tempo de espera, o tempo de preparação, tempo de processamento, o tempo de sobreposição, e o tempo de transporte.

## <a name="finite-materials"></a>material finito
Se você estiver trabalhando com material finitos, o agendamento também depende da disponibilidade dos materiais necessários para a produção. se os componentes disponíveis não são suficientes para a produção, a produção pode ser atrasada. Você pode usar o agendamento em uso de materiais especificando o material que devem estar disponíveis para a produção. Quando você otimiza na capacidade do recurso e da disponibilidade de materiais, a produção será calculada de acordo com essas restrições. Uma ordem de produção não pode ser programadas para iniciar até a capacidade e o material está disponível ao mesmo tempo e as quantidades necessárias.

<a name="additional-resources"></a>Recursos adicionais
--------

[Opções de agendamento de operações](operation-scheduling-options.md)



