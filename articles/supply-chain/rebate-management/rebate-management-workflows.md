---
title: Fluxos de trabalho de acordos de gerenciamento de reembolso
description: Este artigo explica como configurar um fluxo de trabalho de Acordo de gerenciamento de reembolso para aprovar e ativar acordos.
author: sherry-zheng
ms.date: 02/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WorkflowTableListPageRnr
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-02-19
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 2b1611ff7877efc4a2f98b8f84a1ef91971902ab
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8869507"
---
# <a name="rebate-management-deal-workflows"></a>Fluxos de trabalho de acordos de gerenciamento de reembolso

[!include [banner](../includes/banner.md)]

Para aprovar acordos de reembolso, o Gerenciamento de reembolso usa a mesma plataforma de fluxo de trabalho que outros aplicativos de finanças e operações. Dois processos de trabalho estão associados a cada fluxo de trabalho:

- Um elemento do fluxo de trabalho aprova o acordo.
- Um elemento do fluxo de trabalho ativa o acordo para que o usuário ou processo de fluxo de trabalho possa aprovar as transações.

Para poder usar um acordo de reembolso, ele deve estar ativo no módulo **Gerenciamento de reembolso**. Para ativar um acordo, você deve primeiro criar e configurar um *Fluxo de trabalho de acordo de gerenciamento de reembolso*.

Os usuários não podem aprovar negociações manualmente. O fluxo de trabalho deve sempre ser utilizado.

## <a name="create-and-manage-rebate-management-deal-workflows"></a>Criar e gerenciar fluxos de trabalho de Acordo de gerenciamento de reembolso

Para trabalhar com fluxos de trabalho de Acordo de gerenciamento de reembolso, acesse **Gerenciamento de reembolso \> Configuração \> Fluxos de trabalho de gerenciamento de reembolso**. Aqui você pode exibir, criar e atualizar fluxos de trabalho, conforme necessário. Só é possível ativar um fluxo de trabalho deste tipo de cada vez. Para obter mais informações sobre fluxos de trabalho, como trabalhar com a página **Fluxos de trabalho de gerenciamento de reembolso** e como criar fluxos de trabalho, consulte [Visão geral do sistema de fluxo de trabalho](../../fin-ops-core/fin-ops/organization-administration/overview-workflow-system.md) e os artigos relacionados.

## <a name="use-a-workflow-to-activate-a-deal"></a>Use um fluxo de trabalho para ativar um acordo

Para ativar um acordo por meio de um fluxo de trabalho, abra o acordo (por exemplo, na página **Todos os acordos de gerenciamento de reembolso**). No Painel de Ações, selecione **Fluxo de trabalho \> Enviar**. Após o processamento e a aprovação do novo acordo pelo fluxo de trabalho, ele ficará ativo e pronto para ser usado.

Depois que uma negociação for ativada, você não poderá alterar a maior parte de sua configuração. Se for necessário alterar um acordo ativo, primeiro, desative-o e crie um novo acordo. Se o novo acordo for parecido com o antigo, você poderá criá-lo copiando o acordo antigo.

Você pode alterar as seguintes configurações de uma negociação depois de ativada:

- Reconciliar por
- Garantia cumulativa
- Perfil de lançamento
- Perfil de lançamento para garantia
- Notas do documento
- Moeda
- Data Inicial
- Data final

Além disso, as linhas de reembolso podem ser removidas.
