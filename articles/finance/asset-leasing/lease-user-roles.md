---
title: Atribuir funções de usuário de arrendamento
description: Este tópico descreve as funções de segurança usadas no Arrendamento de ativos. Também explica como atribuir usuários a essas funções.
author: moaamer
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 16719576dde73f096c0102a89c43cbc75594cc80
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5819833"
---
# <a name="assign-lease-user-roles"></a>Atribuir funções de usuário de arrendamento

[!include [banner](../includes/banner.md)]

Este tópico descreve as funções de segurança usadas no Arrendamento de ativos. Também explica como atribuir usuários a essas funções.

Três funções de usuário diferenciam o acesso no Arrendamento de ativos. Uma função é apropriada para manter arrendamentos, uma é apropriada para exibir arrendamentos e uma é apropriada para realizar as obrigações de um auxiliar de arrendamento. Cada função tem permissões específicas para todas as páginas de arrendamento e permite que os usuários exibam, criem, editem ou excluam arrendamentos de acordo com suas tarefas.

| Função           | descrição |
|----------------|-------------|
| Manter Arrendamento | Os usuários nessa função podem adicionar, editar, excluir e exibir arrendamentos. Essa função foi criada para usuários diários cujas tarefas incluem a criação e o lançamento de entradas de diário mensal e a adição de novos arrendamentos. Essa função dá acesso a toda a funcionalidade de Arrendamento de ativos. |
| Exibir Arrendamento     | Os usuários nessa função só podem exibir registros de arrendamento, agendas e executar relatórios. Eles não podem criar novos arrendamentos, editar arrendamentos existentes ou criar entradas de diário em arrendamentos. A função foi criada para usuários que só precisam exibir arrendamentos, agendas de arrendamento e transações que ocorrem nesses arrendamentos. |
| Auxiliar de Arrendamento    | Os usuários nessa função só podem criar novos arrendamentos. Eles não podem editar ou excluir arrendamentos existentes, exibir agendas de arrendamento ou lançar entradas de diário de arrendamento. Essa função foi criada para usuários que trabalham em uma capacidade de entrada de dados. |

Siga estas etapas para atribuir aos usuários as funções usadas em Arrendamento de ativos.

1. Vá para **Administração do sistema \> Segurança \> Atribuir usuários a funções**.
2. Selecione a função **Manter arrendamento**, **Auxiliar de arrendamento** ou **Exibir arrendamento** e depois selecione **Atribuir/excluir usuários manualmente**.
3. Selecione o usuário a ser atribuído à função e selecione **Atribuir à função**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]