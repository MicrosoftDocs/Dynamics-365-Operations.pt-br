---
title: Ajuste de estoque do depósito
description: Este tópico fornece informações sobre o diário de ajuste de estoque de depósito e o processamento quando você está usando unidades de escala.
author: perlynne
manager: tfehr
ms.date: 04/22/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSInventoryAdjustmentJournal, InventJournalCount
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: SCM
ms.author: perlynne
ms.search.validFrom: 2021-04-21
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: be386539ea7addf20256ac2b1f8a2a72736fcbec
ms.sourcegitcommit: cd9016e9787169cb800889d335b9c5919ddbe4af
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2021
ms.locfileid: "5938217"
---
# <a name="warehouse-inventory-adjustment"></a>Ajuste de estoque do depósito

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

O recurso de ajuste de estoque de depósito é usado na execução de unidades de escala de nuvem e de borda para [cargas de trabalho de fabricação](cloud-edge-workload-manufacturing.md) e de gerenciamento de [depósito](cloud-edge-workload-warehousing.md).

Quando um trabalhador faz um ajuste de estoque usando o aplicativo de depósito em uma carga de trabalho de gerenciamento de depósito da unidade de escala, a atualização física disponível deve ser processada pelo trabalho em lotes do **diário de ajuste de estoque de depósito**, que você executa e agenda acessando o **Gerenciamento de depósito > Tarefas periódicas > Diário de ajuste de estoque de depósito**.

Os seguintes processos de trabalho do aplicativo de depósito no momento estão usando o **Diário de ajuste de estoque de depósito** nas cargas da unidade de escala:

- Ajuste de entrada/saída
- Contagem cíclica
- Carregamento da placa de licença:

Várias transações de estoque são criadas como parte da nuvem e borda no processo de ajuste de estoque porque as implantações de unidade de escala e de hub compartilham os registros de estoque.

## <a name="inventory-adjustment-example"></a>Exemplo de ajuste do estoque

Neste exemplo, um trabalhador de depósito usou o aplicativo de depósito para registrar a inclusão de estoque disponível.

Primeiro, a carga de trabalho da unidade de escala cria uma transação de ajuste de estoque de depósito para o ajuste físico positivo, que, em seguida, é sincronizado com o hub e resulta em um aumento do estoque disponível no hub.

| Tipo                                    | Unidade de escala | Direção | Hub |
|-----------------------------------------|------------|-----------|-----|
| Ajuste de estoque do depósito          | +1         | ->        | +1  |

O hub processa um lançamento de diário de contagem, que é recebido por [mensagens de processador de mensagens](cloud-edge-message-processor-messages.md). Isso atualiza o estoque disponível adicional. Para evitar um estoque duplo disponível, o hub cria uma transação de compensação como parte desse processo e remove o estoque disponível gravado anteriormente que está relacionado ao ajuste de estoque de depósito.

| Tipo                                    | Unidade de escala | Direção | Hub |
|-----------------------------------------|------------|-----------|-----|
| Contagem                                | +1         | <-        | +1  |
| Ajuste de estoque de depósito (compensação) | -1         | <-        | -1  |

Depois que uma unidade de escala cria um **Diário de ajuste de estoque de depósito** no hub, você pode revisar o **Diário de contagem** e o **Diário de compensação**, que são criados pelo hub como parte do processo de ajuste.

Você pode revisar cada uma dessas entradas de diário e transações no Supply Chain Management seguindo estas etapas:

1. Entre na unidade de escala.
1. Vá para **Gerenciamento de depósito \> Tarefas periódicas \> Diário de ajuste de estoque de depósito**.
1. Na página **Diário de ajuste de estoque de depósito**, localize e abra o diário que gravou a alteração de estoque disponível. A seção **Linhas do diário** mostra cada ajuste registrado pelo diário.
1. Entre no Hub.
1. Vá para **Gerenciamento de depósito \> Tarefas periódicas \> Diário de ajuste de estoque de depósito**.
1. Na página **Diário de ajustes de estoque de depósito**, você deve ver o mesmo diário listado, se a unidade de escala e o hub foram sincronizados.
1. Abrir o diário. Se as [mensagens do processador de mensagens](cloud-edge-message-processor-messages.md) tiverem sido processadas, você verá links para o **Diário de contagem** e o **Diário de compensação** no cabeçalho.
    - O **Diário de contagem** deve mostrar os mesmos valores de dimensão que as linhas do diário.
    - O **Diário de compensação** deve mostrar a compensação, que remove o ajuste de estoque duplo.
    > [!NOTE]
    > Quando toda sincronização e processamento são concluídos, o **Diário de contagem** e o **Diário de compensação** são sincronizados novamente para a unidade de escala. Eles também podem ser exibidos na página **Diário de ajuste de estoque de depósito** relevante.
