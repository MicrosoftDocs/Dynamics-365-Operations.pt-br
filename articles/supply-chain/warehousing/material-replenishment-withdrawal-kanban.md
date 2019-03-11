---
title: Reabastecimento com kanbans de retirada
description: Este tópico descreve como o kanban de retirada é usado para o reabastecimento de material para atividades de fabricação.
author: johanhoffmann
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanBoardTransferJob, KanbanFlow, KanbanRules
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7fe3ebe3c27c380d95cbc12b864264e9538d433f
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "320917"
---
# <a name="replenishment-with-withdrawal-kanbans"></a>Reabastecimento com kanbans de retirada

[!include [banner](../includes/banner.md)]

Este tópico descreve como o kanban de retirada é usado para o reabastecimento de material para atividades de fabricação.

## <a name="workflow-for-material-replenishment-that-uses-the-withdrawal-kanban"></a>Fluxo de trabalho para o reabastecimento de material que usa o kanban de retirada
-------------------------------------------------------------------

O kanban de retirada pode ser usado para mover um kanban de um único item entre depósitos e locais de produção nos quais o material é consumido. O kanban de retirada oferece suporte a uma solução baseada em pull para reabastecimento de material, no qual um sinal pull é necessário para acionar o fornecimento para uma demanda específica. 

O cenário a seguir mostra um sistema de reabastecimento baseado em pull, no qual um sinal pull aciona a criação de um kanban para reabastecer o material para um processo de produção. 

[![O sinal pull aciona a criação de um kanban para reabastecer o material para um processo de produção](./media/material-replenishment-with-withdrawal-kanban.png)](./media/material-replenishment-with-withdrawal-kanban.png)

1.  Kanban de retirada
2.  Local de "origem" e local de colocação Kanban para trabalhos de depósito
3.  Local de "destino" e local de entrada de produção Kanban
4.  Processo de fabricação
5.  Trabalho de depósito para a separação kanban
6.  Locais de depósito de matéria-prima
7.  Depósito de material
8.  Depósito de fabricação

Neste cenário, um processo de fabricação (4) consome material de um local de entrada de produção (3) no depósito de fabricação (8). Quando uma unidade de manuseio do material (kanban) é consumida, é registrada como vazio. Um sinal de reabastecimento é criado para a origem do item, e um novo kanban (1) é criado. Nesse caso, a origem do item consiste em localizações no depósito de material (7). O material para o kanban é separado e atrelado a um local (2) no mesmo depósito. Quando o material é separado, está pronto para ser transferido do local 2 para o local de entrada de produção (3) no depósito de fabricação (8).

## <a name="configure-warehouse-work-for-kanban-picking-for-the-withdrawal-kanban"></a>Configurar trabalhos de depósito para a separação kanban do kanban de retirada

Para habilitar a separação de matéria-prima para o kanban de retirada, configure os modelos de onda, os modelos de trabalho e as diretivas de localização para o tipo de ordem de trabalho **Separação kanban**. Este tipo de ordem de trabalho não oferece suporte somente ao processo de separação do kanban de retirada. Também oferece suporte ao processo de separação do kanban de fabricação. Entretanto, você pode configurar um processo de separação para cada tipo de kanban separando os modelos de onda, os modelos de trabalho e as diretivas da localização. Para separar os modelos de onda, os modelos de trabalho e as diretivas da localização, defina critérios no tipo de atividade (**Processar** ou **Transferir**) nas consultas para essas entidades.

## <a name="configure-the-withdrawal-kanban"></a>Configurar o kanban de retirada

A atividade de transferência que é usada para o kanban de retirada é configurada como parte de um plano de atividades ativado no fluxo de produção de lean manufacturing. Como parte da configuração da atividade de transferência, você especifica os locais de "origem" e "destino" para a transferência. Após configurar a atividade de transferência, você pode atribuí-la a uma regra kanban do tipo **Retirada**. A regra kanban define as diretivas e as configurações para o kanban de retirada. A quantidade do kanban define quantas unidades da unidade de manuseio de material o kanban transporta durante o processo de transferência. A quantidade fixa de kanbans será usada quando a estratégia fixa de reabastecimento estiver selecionada. Essa quantidade define quantos kanbans são necessários para impedir o esgotamento do estoque ou a criação de estoque na origem de demanda. A quantidade fixa pode ser calculada com base na demanda real, no histórico de demanda ou em níveis de serviço. Os dois cenários a seguir descrevem como você pode gerenciar o reabastecimento de material que usa o kanban de retirada.

## <a name="scenario-1-replenish-a-production-input-location-by-using-a-fixed-withdrawal-kanban"></a>Cenário 1: Reabastecer um local de entrada de produção usando um kanban de retirada fixo

Um processo de fabricação consome matéria-prima comprada de um local de entrada de produção que está no depósito de fabricação. Quando a matéria-prima é recebida do fornecedor, ela é armazenada em locais do depósito de material. Por ser considerada estável durante um período, a demanda de material é configurada de modo a fornecer a produção em uma quantidade fixa de fluxo kanban. Quando um kanban é consumido em um local de entrada de produção, um sinal vazio é registrado, e um novo kanban do mesmo tipo é adicionado ao fluxo. 

O sinal vazio pode ser configurado para ocorrer automaticamente quando um kanban é concluído. Como alternativa, o sinal vazio pode ser configurado como interação manual fornecida do quadro de transferência Kanban ou de um menu do dispositivo portátil. O quadro de transferência Kanban é o espaço de trabalho onde todas as atividades no ciclo de vida do kanban são gerenciadas. 

Quando o kanban é criado, uma linha de onda para a matéria-prima é adicionada a uma onda kanban para o depósito de material. Na seção da lista de separação do quadro de transferência Kanban, o status do material e os processos de depósito relacionados podem ser monitorados da criação da onda à criação do trabalho, até que o material esteja disponível no local ”transferir de" e esteja pronto para ser transferido para os locais de entrada de produção. O kanban pode ser concluído do quadro de transferência Kanban ou de um menu no dispositivo portátil. 

Nesse cenário, o trabalho de separação no depósito de material é processado como uma atividade. A atividade de transferência entre o depósito de material e o depósito de produção é processada como uma atividade separada. Essa abordagem pode ser útil se, por exemplo, há uma grande distância física entre os dois depósitos. Nesse caso, a atividade de transferência do kanban pode representar uma carga de caminhão. 

Se a distância entre as localizações de depósito e o local de entrada de produção é pequena, pode ser mais eficiente incluir a atividade de transferência no processo de separação. Assim, após a separação do material, ele pode ser atrelado diretamente ao local de entrada de produção. Para dar suporte a esse processo, você configura a atividade de transferência para que ela seja concluída automaticamente quando o trabalho de separação do kanban de retirada for processado.

## <a name="scenario-2-automatically-complete-the-transfer-activity-when-kanban-picking-work-is-processed"></a>Cenário 2: Concluir automaticamente a atividade de transferência quando o trabalho de separação kanban for processado

No cenário a seguir, a atividade de transferência do kanban de retirada é configurada para transferência entre dois locais do mesmo depósito. A atividade de transferência do kanban de retirada é configurada para que seja concluída automaticamente. 

[![A atividade de transferência é concluída automaticamente quando o trabalho de separação kanban é processado](./media/transfer-activities-when-processing-kanban-picking.png)](./media/transfer-activities-when-processing-kanban-picking.png)

1.  Depósitos compartilhados de matérias-primas e produção
2.  Locais de depósito de matérias-primas
3.  Local de "origem" e local de colocação Kanban para trabalhos de depósito
4.  Kanban de retirada
5.  Local de entrada de produção
6.  Processo de fabricação

Depois de consumido em um local de entrada de produção, o kanban é relatado como vazio, e um novo kanban é adicionado ao fluxo. Quando o kanban é criado, uma linha de onda é adicionada a uma onda kanban. Quando a onda kanban é processada, o trabalho de depósito para a separação kanban é criado. O trabalhador do depósito processa o trabalho para a separação kanban e é direcionado pelo trabalho a separar o material para o kanban em um local de depósito. Na medida em que esse trabalhador do depósito confirma a separação, o kanban é concluído automaticamente, e o trabalhador do depósito é orientado a atrelar o material ao local de entrada de produção.

