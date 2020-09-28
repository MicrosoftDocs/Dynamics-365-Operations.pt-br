---
title: Sincronizar capacidade de recursos
description: Este tópico fornece informações sobre como sincronizar a capacidade de um recurso em calendários e projetos.
author: Yowelle
manager: AnnBe
ms.date: 09/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjProjectsListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 82022
ms.assetid: bd2fb375-84c6-428a-8e54-f0f719045898
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 27b6fde91a72e37bb2712daba765032322cbd4e9
ms.sourcegitcommit: 241ada0945c72d769eaa70ae35aedbb6a3233fdf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/02/2020
ms.locfileid: "3760472"
---
# <a name="synchronize-resource-capacity"></a>Sincronizar capacidade de recursos

[!include [banner](../includes/banner.md)]

Os processos para ajudar a sincronização de recurso ajudam a garantir que as informações do calendário e do calendário base passem para o agendamento de recurso de projeto. Se o calendário for alterado, os processos farão as atualizações necessárias no agendamento dos recursos de projeto. Os processos também ajudam a melhorar o desempenho, pois as informações de recurso de calendário são previamente sincronizadas. Portanto, as atualizações para informações de recurso ocorrem mais rapidamente. Recomendamos que você agende os processos em lotes em vez de um de cada vez. Caso contrário, há o risco de que alguém se esqueça das datas inclusivas quando as informações foram sincronizadas pela última vez. Se as datas inclusivas não forem usadas, poderão ocorrer lacunas durante a sincronização de datas.

![Sincronização de calendário](./media/projectresourcing04-1024x471.jpg)

## <a name="synchronize-resource-capacity-roll-ups"></a>Sincronizar acúmulos de capacidade de recurso

O processo de sincronização é projetado para sincronizar todas as informações do calendário do recurso. Essas informações incluem informações do calendário base sobre todas as alterações na tabela de capacidade do calendário do recurso do projeto. Se novos recursos forem adicionados ao projeto, a sincronização ajuda a garantir que as informações atualizadas de calendário estejam disponíveis. Essa sincronização pode ser feita a qualquer momento.

É recomendável usar um lote. As opções estarão disponíveis durante a sincronização de reservas de capacidade.

1. Selecione **Gerenciamento e contabilidade de projeto** &gt; **Atividades periódicas** &gt; **Sincronização de capacidade** &gt; **Sincronizar acúmulos de capacidade de recursos**.
2. Defina as opções na seguinte tabela.

    | Opção      | descrição |
    |-------------|-------------|
    | Código de período | Se preferir, selecione o código de intervalo de datas da contabilidade para definir as datas inicial e final para o processo de sincronização para acúmulos de capacidade de recurso. |
    | Data de início  | Insira a data inicial para o processo de sincronização para acúmulos de capacidade de recurso. |
    | Data de término    | Insira a data final para o processo de sincronização para acúmulos de capacidade de recurso. |

[![Processo de sincronização](./media/projectresourcing09.jpg)](./media/projectresourcing09.jpg)
