---
title: Agendamento de manutenção
description: Este tópico explica o agendamento de manutenção no Gerenciamento de Ativos.
author: josaw1
manager: tfehr
ms.date: 08/27/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetObjectCalendarCreateWO, EntAssetObjectCalendarListPagePoolsOpen, EntAssetObjectCalendarListPage, EntAssetObjectCalendarListPagePreviewPart, EntAssetObjectCalendarEdit, EntAssetObjectCalendarAdjust, EntAssetObjectCalendarDiscard, EntAssetObjectCalendarInfoPart
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 351e088ece0512fee1bb5f9dad020f32f7728fe4
ms.sourcegitcommit: c986d5234b81d31cc6d054298be6f6ec92c1754c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/25/2020
ms.locfileid: "3888992"
---
# <a name="maintenance-schedule"></a>Agendamento de manutenção

[!include [banner](../../includes/banner.md)]

 

O agendamento de manutenção contém uma lista de todos os planos de manutenção preventiva esperados, solicitações de manutenção e rounds de manutenção a serem executados. Algumas linhas de agendamento podem ter sido convertidas em ordens de serviço.

As quatro exibições do agendamento de manutenção são um pouco diferentes, dependendo de quais linhas de agendamento de manutenção você quer ver.

| Item de menu                  | Descrição do conteúdo                                                                                                                                             |
|----------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Todos os agendamentos de manutenção       | Todas as linhas de agendamento de manutenção são mostradas.     |
| Minha agenda de ativos        | Todas as linhas de agendamento de manutenção que contêm ativos instalados nos locais funcionais para os quais você está relacionado como trabalhador (configurar em [Trabalhadores de manutenção e grupos de trabalhadores](../setup-for-objects/workers-and-worker-groups.md)) são mostrados nesta lista. |
| Abrir linhas do agendamento de manutenção | As linhas de agendamento de manutenção com status "Criado" - que significa que eles não foram convertidos para uma ordem de serviço ou descartados - são mostradas nesta lista.                                            |
| Abrir grupos de agendamentos de manutenção | As linhas de agendamento de manutenção relacionadas ao pool da ordem de serviço são mostradas nesta lista.                                                                                                                  |

>[!NOTE]
>Se uma linha do agendamento de manutenção for incluída em vários pools da ordem de serviço (consulte [Pools da ordem de serviço](../work-orders/work-order-pools.md)), um registro será mostrado para cada pool em **Abrir grupos de agendamento de manutenção**. Isso é feito para otimizar opções de filtragem em grupos de ordens de serviço.

Para abrir um agendamento de manutenção:

1. Clique em **Gerenciamento de ativos** > **Comum** > **Agendamento de manutenção** > **Todo agendamento de manutenção** ou **Abrir linhas de agendamento de manutenção** ou **Abrir grupos de agendamento de manutenção**.

2. Para atualizar o agendamento de manutenção, clique em **Plano de manutenção** ou em **Rounds de manutenção**. 

3. Você pode editar uma linha do plano da manutenção, selecionando-a e clicando em **Editar**. Por exemplo, você pode atualizar rapidamente o nível de serviço ou o trabalhador responsável pelo trabalho. Você só poderá editar as linhas de agendamento de manutenção que ainda não foram associadas a uma ordem de serviço.

4. Você pode excluir uma linha do plano de agendamento selecionando-a na página de listagem e clicando em **Excluir**.

5. Você pode descartar uma linha do agendamento de manutenção selecionando-a na página de listagem e clicando em **Descartar**. Esta função é útil, por exemplo, se um ativo tiver um plano de manutenção de 2.000 km e um plano hora de manutenção de 10.000 km. Depois, talvez você queira descartar a linha criada do plano de manutenção de 2.000 km quando ele coincidir com 10.000 km, 20.000 km, 30.000 km e assim por diante. Se você descartar uma linha do agendamento de manutenção relacionada a um plano de manutenção, essa linha nunca aparecerá novamente quando o plano de manutenção for agendado.

6. Você pode selecionar várias linhas de agendamento de manutenção em **Todo agendamento de manutenção** e clicar em **Grupo de ordens de serviço**, se quiser que todas as linhas sejam incluídas no mesmo grupo de ordens de serviço.

7. Você pode selecionar várias linhas de agendamento de manutenção em **Todo agendamento de manutenção** ou **Abrir linhas de agendamento de manutenção** ou **Abrir grupos de agendamento de manutenção** e clicar em **Ajustar agendamento** se quiser fazer os mesmos ajustes em várias linhas. Você pode alterar as datas inicial e final esperadas, nível de serviço e o grupo do funcionário de manutenção ou o funcionário de manutenção responsável relacionado às linhas de agendamento de manutenção selecionadas.

- Quando uma linha do agendamento de manutenção estiver relacionada a uma ordem de serviço, o ID da ordem de serviço será exibido no campo **Ordem de serviço**.  
- Na guia **Todos os ativos** exibição de detalhes > **Planos de manutenção do ativo**, você pode selecionar os planos de manutenção do ativo. Posteriormente, se você excluir uma linha do plano de manutenção relacionada a um ativo em **Todos os ativos**, você também excluirá todas as linhas de agendamento de manutenção com status "Criado" que foram criadas com base nesse plano de manutenção. Consulte também [Criar um ativo](../objects/create-an-object.md).

A ilustração a seguir mostra a página da lista **Todos os agendamentos de manutenção**.

![Figura 1](media/16-preventive-maintenance.png)

