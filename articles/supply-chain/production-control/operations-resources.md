---
title: Recursos de operações
description: Os recursos de operações executam as atividades de um projeto ou um processo de produção. Podem ser de diferentes tipos e podem ter diferentes recursos.
author: sorenva
manager: tfehr
ms.date: 11/03/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: OpResLifecycleManagementWorkspace, WrkCtrCapability, WrkCtrResourceGroup, WrkCtrResourceAbilityMap, OpResCapacityPlanningWorkspace, WrkCtrCapResGraph, WrkCtrResourceRequirementPart, WrkCtrCapResGraphDialog, WrkCtrResourceCopy, WrkCtrCapResStatistic
audience: Application User
ms.reviewer: kamaybac
ms.custom: 61943
ms.assetid: a3847f07-fca4-4140-a26f-d83c6ac68dde
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: sorenand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 890645e28830d9d53296c4a2530ed1072f9d47e3
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5260422"
---
# <a name="operations-resources"></a>Recursos de operações

[!include [banner](../includes/banner.md)]

Os recursos de operações executam as atividades de um projeto ou um processo de produção. Podem ser de diferentes tipos e podem ter diferentes recursos. 

<a name="operations-resources"></a>Recursos de operações
--------------------

Os recursos de operações são as máquinas, as ferramentas, os trabalhadores, as instalações, as áreas físicas ou fornecedores que executam as atividades de um projeto ou um processo de produção. Podem ser de diferentes tipos e podem ter diferentes recursos.

-   **Fornecedor** – Um recurso externo que executa as atividades do projeto ou operações de produção. Um exemplo é um subcontratado. Vinculando recursos de fornecedor para uma conta de fornecedor, você pode gerar compras para subcontratados, com base nas linhas da lista de materiais (BOM) ou nas linhas de produção.
-   **Recursos humanos** – Um projeto ou trabalhador de produção que execute uma atividade, independentemente ou como um operador de uma ferramenta ou de uma máquina. Se você estiver usando a funcionalidade Recursos humanos, você pode vincular recursos humanos a um trabalhador. O mecanismo de planejamento pode alocar os recursos, com base nas competências que são definidas para o trabalhador correspondente.
-   **Máquina** – Uma máquina ou outro equipamento de produção necessário na produção.
-   **Ferramenta** – Um instrumento ou um dispositivo que normalmente é usado junto com outro recurso para executar uma atividade em um projeto ou na produção.
-   **Local** – Uma localização física de um tamanho específico que é necessária para executar uma atividade. Um exemplo é uma área de montagem.
-   **Instalação** – Um prédio ou uma estrutura fixa que é obrigatória para realizar uma atividade.

## <a name="calendars"></a>Calendários
Um calendário pode ser atribuído a um recurso de operações e descreve a capacidade (horas) desse recurso. Os horários de trabalho do recurso de operações são determinados pelo calendário atribuído ao grupo de recursos ao qual o recurso de operações pertence. Você pode definir uma data efetiva e uma data de vencimento para o calendário atribuído. Você pode atribuir mais de um calendário para um recurso de operações. No entanto, as datas de calendários atribuídos não serão sobrepostos, e o recurso de operações pode ser atribuído apenas um calendário de cada vez. **Observação:** Se não houver um calendário de trabalho em vigor para um grupo de recursos (por exemplo, se o último ou o único calendário atribuído expirar), você não poderá mais acessar os recursos de operações atribuídos ao grupo de recursos para o planejamento da produção e o agendamento de operações. Você também pode atribuir um calendário para um grupo de recursos para especificar os horários de trabalho do grupo de itens e de todos os recursos de operações que são atribuídos ao grupo de recursos. A capacidade do grupo de recursos é calculada como a soma das capacidades de cada recurso de operações que é atribuído a esse grupo de recursos. O calendário que é atribuído a um grupo de recursos pode ser alterado ao longo do tempo.

## <a name="resource-capabilities"></a>Capacidades do recurso
Um recurso é a capacidade de um recurso de operações de executar uma atividade específica. Você pode atribuir um ou mais recursos a um recurso de operações. O mecanismo de planejamento alocará recursos correspondendo as requisições de recursos de cada atividade às capacidades dos recursos de operações disponíveis. As capacidades podem ser atribuídas a todos os tipos de recursos: (**Ferramenta**, **Fornecedor**, **Máquina**, **Recursos humanos**, **Local** ou **Instalação**). Para atribuir capacidades a recursos de operações para um tempo limitado, defina uma data de início e uma data de vencimento na atribuição de capacidade. Para obter mais informações, consulte [Capacidades do recurso](resource-capabilities.md).

## <a name="resource-groups"></a>Grupos de recursos
Um grupo de recursos é um conjunto de recursos de operações que representa a granularidade em que você deseja planejar recursos quando usa o método de planejamento de operações. No entanto, grupos de recursos geralmente correspondem à organização física das células de trabalho, demarcadas pelas linhas amarelas no chão da fábrica de produção. O grupo de recursos define o site, a unidade de produção e o contexto de depósito para recursos de operações atribuídos ao grupo. Quando você atribuir um recurso de operações a um grupo de recursos, o recurso pode ser agendado no local no qual o grupo de recursos está localizado. Você não precisa atribuir os recursos de operações que você cria a um grupo de recursos. No entanto, um recurso de operações deve ser atribuído a um grupo de recursos antes de ser programado para executar o trabalho. Um recurso de operações pode ser atribuídos a um grupo de recursos por tempo limitado. Você também pode atribuir recurso de operações para vários grupos de recursos, de forma que possa, em seguida, compartilhar o recurso em locais. No entanto, as datas efetivas e as datas de vencimento não serão sobrepostas. Em outras palavras, não é possível atribuir um recurso de operações a dois grupos de recursos ao mesmo tempo. As alterações nas atribuições de grupo de recursos só entram em vigor para novas alocações de recursos. As reservas de capacidade para trabalhos, operações e previsões de horas do projeto que são agendadas não serão afetadas. **Observação:** Quando você atribui recursos de operações do tipo **Fornecedor** a um grupo de recursos, todos os recursos de operações que são atribuídos a esse grupo de recursos devem ser do tipo **Fornecedor** e devem estar vinculados à mesma conta de fornecedor.

## <a name="production-units"></a>Unidades de Produção
Unidade de produção é uma unidade administrativa formada por um conjunto de grupos de recursos. Uma unidade de produção pode conter vários grupos de recursos, mas um grupo de recursos pode ser atribuído somente a uma unidade de produção. Uma unidade de produção reflete o layout físico dos recursos de produção e não tem efeito sobre as transações ou o modo como são processadas. Você deve associar uma unidade de produção a um local. Você também pode atribuir um depósito de separação e outro de armazenamento a uma unidade de produção. Você pode usar uma unidade de produção para consolidar e filtrar dados relacionados à produção. Por exemplo, um gerente de chão de fábrica pode ver uma visão geral da carga de trabalho pendente e a capacidade disponível para determinada unidade de produção. Você pode alterar a unidade de produção atribuída a um grupo de recursos. Também é possível excluir uma unidade de produção. Porém, essas alterações na unidade de produção só entram em vigor para novas ordens criadas após a execução do planejamento mestre. Se quiser aplicar a alteração da unidade de produção às ordens existentes, você deve fazer esta alteração manualmente.

## <a name="resource-scheduling"></a>Agendamento do recurso
Os recursos de operações são atribuídos às atividades quando um projeto ou uma produção é programada. Dois métodos de planejamento estão disponíveis: plano de operações e plano de trabalho. Quando você usa o plano de operações, cada operação ou atividade do projeto é planejada no grupo de recursos que contém os recursos de operações que correspondem aos requisitos de capacidade especificados para a operação. Se um recurso específico de operações for necessário para a operação, o plano reserva a capacidade somente em um recurso específico de operações no grupo. O agendamento de trabalho é um formulário de agendamento mais detalhado do que o agendamento de operações. Ele divide cada operação em seus trabalhos e tarefas individuais. Esses trabalhos são então atribuídos aos recursos de operações que vão executá-los. O agendamento reserva a capacidade nos grupos de recursos com base nos tempos de operação definidos no roteiro de produção ou em atividades do projeto. Se você estiver trabalhando com capacidade finita, o plano dependerá da disponibilidade dos recursos de operações necessários para concluir a atividade. Para o plano de operações, a capacidade do grupo de recursos é a soma da capacidade disponível dos recursos de operações que fazem parte desse grupo. As reservas de capacidade que já existem para os recursos de operações são consideradas como a capacidade não disponível. Se não houver capacidade disponível suficiente para a produção, as ordens de produção podem ser atrasadas ou até mesmo interrompidas. Na página **Recursos**, você pode definir várias propriedades que controlam como as reservas de capacidade são feitas:

-   **Capacidade** – Especifique a capacidade do recurso de operações por hora em termos da unidade de medida de capacidade.
-   **Capacidade de lote** – Especifique o número máximo de unidades que o recurso de operações pode processar por execução.
-   **Porcentagem de eficiência** – Especifique a eficiência que você espera do recurso de operações. A porcentagem de eficiência ajusta a produtividade do recurso de operações e afeta o tempo que é reservado para o recurso. Os prazos de entrega para as operações que usam o recurso de operações também serão ajustados adequadamente. Esta é a fórmula usada para o cálculo: Hora do plano = Hora × 100 ÷ porcentagem de eficiência. *Hora* inclui o tempo de execução e o tempo de preparação.
-   **Porcentagem do plano de operações** – Especifique a porcentagem máxima de capacidade do recurso de operações que você deseja usar no plano de operações. Para permitir flexibilidade na capacidade durante o agendamento do trabalho, você deve definir esta porcentagem para menor que 100%.
-   **Capacidade finita** – Defina esta opção como **Sim** se o recurso de operações for planejado com base na capacidade real disponível e se as reservas de capacidade existentes forem consideradas. Se essa opção estiver definida como **Não**, o recurso de operações é considerado para que a capacidade infinita e o recurso possam ser reservados.
-   **Propriedade finita** – Defina esta opção como **Sim** se quiser que o recurso de operações seja planejado com base na capacidade real que está disponível em relação às propriedades de programação de horário de trabalho necessárias.
-   **Exclusivo** – Defina esta opção como **Sim** se não quiser que o recurso de operações esteja disponível para outro trabalho ou outra operação até a produção atual ser concluída. Neste caso, o recurso de operações não poderá ser usado, se houver intervalos no momento da execução do recurso.
-   **Recurso de afunilamento** – Defina o recurso de operações como um recurso de afunilamento. Um recurso de afunilamento é planejado por meio do uso de capacidade finita, quando o campo **Capacidade finita** e o campo **Planejamento de afunilamento** na página **Planejamentos mestres** forem selecionados.

Para agendar vários recursos de operações ao mesmo tempo para executar, por exemplo, uma operação na produção, você terá de especificar os requisitos de vários recursos com operações principais e secundárias. Você também poderá reservar os vários recursos de operações com capacidade diferente. O recurso de operações que está programado para a operação principal determina a duração da atividade.

## <a name="lean-work-cells"></a>Células de trabalho de lean manufacturing
Você pode especificar se um grupo de recursos é uma célula de trabalho de lean manufacturing. O grupo de recursos poderá fazer parte de um fluxo de produção. Especificando um grupo de recursos como uma célula de trabalho de lean manufacturing, você também evita que o grupo de recursos e os recursos de operações atribuídos sejam alocados entre as operações de uma ordem de produção ou de uma previsão de horas do projeto. Para cada grupo de recursos que atua como uma célula de trabalho de lean manufacturing, você deve especificar as seguintes informações:

-   **Calendário** – O calendário de trabalho da célula de trabalho, que deve ter a propriedade de um dia útil padrão.
-   **Depósito e a localização de entrada** – O local padrão que é usado para separar o material para uma atividade.
-   **Depósito e a localização de saída** – A localização padrão na qual todas as saídas da célula de trabalho são colocadas.
-   **Categoria de custo do tempo de execução** – Essa categoria deve ser definida para a célula de trabalho, se o trabalho for rastreado direto na previsão de custo.

Quando um grupo de recursos é usado como uma célula de trabalho de lean manufacturing, a capacidade de célula de trabalho é especificada diretamente no grupo de recursos. No entanto, você não precisa atribuir os recursos de operações ao grupo de recursos. Somente quando a célula de trabalho é gerenciada por um subcontratado, um recurso de operações do tipo de **Fornecedor** deverá ser atribuído à célula de trabalho. Se você atribuir um recurso de operações a um grupo de recursos que esteja marcado como uma célula de trabalho, a capacidade da célula de trabalho não será afetada.

## <a name="costing-resources"></a>Recursos de avaliação de custo
Ao definir uma atividade, como uma operação de roteiro ou uma previsão de horas do projeto, você pode especificar o requisito para um recurso de operações ou um grupo de recursos específicos. No entanto, você também pode especificar o requisito para um recurso de operações de um tipo específico, ou um recurso de operações com um recurso específico ou uma competência. Por esse motivo, a atribuição de recursos real não será feita até que a atividade esteja agendada e houver capacidade reservada. Consequentemente, em uma operação de roteiro, você pode especificar se a previsão e o cálculo de BOM devem se basear em um recurso específico de operações. Este recurso de operações é referido como o recurso de avaliação de custo. Também é possível transferir categorias de custo e tempo de operação do recurso de avaliação de custo à atividade. Quando a operação for agendada, a previsão e o cálculo de BOM são feitos usando o recurso de operações que é programado realmente.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]