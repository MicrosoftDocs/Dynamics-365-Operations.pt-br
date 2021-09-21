---
title: Erro ao reenviar uma ordem de compra para um fluxo de trabalho após uma alteração
description: Erro ao reenviar uma ordem de compra para um fluxo de trabalho após uma alteração
author: kamaybac
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: PurchTable, PurchTablePart
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 4b8465d198c440f27a4b3cc4268445e0aa450f5b
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7475627"
---
# <a name="error-on-resubmitting-a-purchase-order-to-a-workflow-after-a-change"></a>Erro ao reenviar uma ordem de compra para um fluxo de trabalho após uma alteração


## <a name="symptoms"></a>Sintomas

O seguinte erro ocorre no fluxo de trabalho quando uma ordem de compra é reenviada após uma alteração:

> Parado (erro): Exceção X++: Alterações na ordem de compra PO0000569 só são permitidas no estado de rascunho quando o gerenciamento de alterações for ativado em<br>
SysWorkflowParticipantProvider-resolve<br>
SysWorkflowParticipantProvider-resolveParticipants<br>
SysWorkflowServiceProvider-resolveParticipant<br>
SysWorkflowQueue-resume

Esse problema ocorre apenas se a ordem de compra estiver em um estado *Confirmado* antes da solicitação de alterações. Se você solicitar alterações enquanto a ordem de compra estiver em um estado *Aprovado*, o fluxo de trabalho poderá ser processado com êxito.

## <a name="resolution"></a>Resolução

Esse problema pode ocorrer devido a inconsistências nas distribuições da ordem de compra.

Para desbloquear esse problema e redefinir a ordem de compra para um estado *Rascunho*, Acesse **Compras e fornecimento \> Tarefas periódicas \> Limpar \> Redefinição de distribuição da ordem de compra**. Para obter mais informações, consulte a seguinte postagem de blog: [Resolver erros de distribuição de OC no Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).

O problema será corrigido através [deste artigo da Base de Dados de Conhecimento (KB) da Microsoft](https://msdyneng.visualstudio.com/FinOps/_workitems/edit/467138).
