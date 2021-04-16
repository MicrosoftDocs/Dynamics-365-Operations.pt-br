---
title: Fluxos de trabalho de acordos de gerenciamento de reembolso
description: Este tópico explica como configurar um fluxo de trabalho de Acordo de gerenciamento de reembolso para aprovar e ativar acordos.
author: sherry-zheng
ms.date: 02/19/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WorkflowTableListPageRnr
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-02-19
ms.dyn365.ops.version: Release 10.0.18
ms.openlocfilehash: 37b8022633e61c4d98d6f5d129bcf494a9ed92e0
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5831713"
---
# <a name="rebate-management-deal-workflows"></a>Fluxos de trabalho de acordos de gerenciamento de reembolso

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Para aprovar acordos de reembolso, o Gerenciamento de reembolso usa a mesma plataforma de fluxo de trabalho que outros aplicativos Finance and Operations. Dois processos de trabalho estão associados a cada fluxo de trabalho:

- Um elemento do fluxo de trabalho ativa o acordo para que o usuário ou processo de fluxo de trabalho possa aprovar as transações.
- Um elemento do fluxo de trabalho aprova o acordo.

Para poder usar um acordo de reembolso, ele deve estar ativo no módulo **Gerenciamento de reembolso**. Para ativar um acordo, você deve primeiro criar e configurar um *Fluxo de trabalho de acordo de gerenciamento de reembolso*.

Após um fluxo de trabalho ser ativado para Gerenciamento de reembolso, os usuários não podem aprovar acordos manualmente. O fluxo de trabalho deve ser sempre utilizado.

## <a name="create-and-manage-rebate-management-deal-workflows"></a>Criar e gerenciar fluxos de trabalho de Acordo de gerenciamento de reembolso

Para trabalhar com fluxos de trabalho de Acordo de gerenciamento de reembolso, acesse **Gerenciamento de reembolso \> Configuração \> Fluxos de trabalho de gerenciamento de reembolso**. Aqui você pode exibir, criar e atualizar fluxos de trabalho, conforme necessário. Só é possível ativar um fluxo de trabalho deste tipo de cada vez. Para obter mais informações sobre fluxos de trabalho, como trabalhar com a página **Fluxos de trabalho de gerenciamento de reembolso** e como criar fluxos de trabalho, consulte [Visão geral do sistema de fluxo de trabalho](../../fin-ops-core/fin-ops/organization-administration/overview-workflow-system.md) e os tópicos relacionados.

## <a name="use-a-workflow-to-activate-a-deal"></a>Use um fluxo de trabalho para ativar um acordo

Para ativar um acordo por meio de um fluxo de trabalho, abra o acordo (por exemplo, na página **Todos os acordos de gerenciamento de reembolso**). No Painel de Ações, selecione **Fluxo de trabalho \> Enviar**. Após o processamento e a aprovação do novo acordo pelo fluxo de trabalho, ele ficará ativo e pronto para ser usado.

Depois que um acordo for ativado, você não poderá alterar a configuração. Se for necessário alterar um acordo ativo, desative-o e crie um novo acordo. Se o novo acordo for parecido com o antigo, você poderá criá-lo copiando o acordo antigo.
