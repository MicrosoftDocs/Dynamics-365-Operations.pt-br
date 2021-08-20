---
title: Solucionar problemas de fluxos de trabalho de compras e fornecimento
description: Este tópico descreve como corrigir problemas que podem ocorrer ao trabalhar com fluxos de trabalho de compras e fornecimento.
author: SmithaNataraj
ms.date: 09/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-9-16
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: cda9da1a084bf3c04aef6911516ebee0facf1be61e94bfc1abab95e9dee75475
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6729450"
---
# <a name="troubleshoot-procurement-and-sourcing-workflows"></a>Solucionar problemas de fluxos de trabalho de compras e fornecimento

Este tópico descreve como corrigir problemas que podem ocorrer ao trabalhar com fluxos de trabalho de compras e fornecimento.

## <a name="error-when-re-submitting-a-purchase-order-to-the-workflow-after-a-change-changes-to-purchase-order-x-are-allowed-only-in-a-draft-state-when-change-management-is-activated"></a>Erro ao enviar novamente uma ordem de compra para o fluxo de trabalho após uma alteração: "As alterações na ordem de compra X são permitidas somente em um estado de rascunho quando o gerenciamento de alterações é ativado"

Esse problema ocorre apenas se a ordem de compra estiver em um estado *Confirmado* antes da solicitação de alterações. Se você solicitar alterações enquanto a ordem de compra estiver em um estado *Aprovado*, o fluxo de trabalho poderá ser processado com êxito.

### <a name="error-description"></a>Descrição do erro

O seguinte erro ocorre no fluxo de trabalho quando uma ordem de compra é reenviada após uma alteração:

> Parado (erro): Exceção X++: Alterações na ordem de compra PO0000569 só são permitidas no estado de rascunho quando o gerenciamento de alterações for ativado em<br>
SysWorkflowParticipantProvider-resolve<br>
SysWorkflowParticipantProvider-resolveParticipants<br>
SysWorkflowServiceProvider-resolveParticipant<br>
SysWorkflowQueue-resume

### <a name="issue-resolution"></a>Resolução do problema

Esse problema pode ocorrer devido a inconsistências nas distribuições da ordem de compra.

Para desbloquear esse problema e redefinir a ordem de compra para um estado *Rascunho*, Acesse **Compras e fornecimento \> Tarefas periódicas \> Limpar \> Redefinição de distribuição da ordem de compra**. Para obter mais informações, consulte a seguinte postagem de blog: [Resolver erros de distribuição de OC no Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).

O problema será corrigido através [deste artigo da Base de Dados de Conhecimento (KB) da Microsoft](https://msdyneng.visualstudio.com/FinOps/_workitems/edit/467138).

## <a name="one-or-more-accounting-distributions-are-either-over-distributed-or-under-distributed"></a>Uma ou mais distribuições contábeis são superdistribuídas ou subdistribuídas.

Esse problema pode ocorrer devido a inconsistências nas distribuições da ordem de compra.

Para desbloquear esse problema e redefinir a ordem de compra para um estado *Rascunho*, Acesse **Compras e fornecimento \> Tarefas periódicas \> Limpar \> Redefinição de distribuição da ordem de compra**. Para obter mais informações, consulte a seguinte postagem de blog: [Resolver erros de distribuição de OC no Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).

## <a name="if-a-delivery-remainder-is-canceled-on-a-purchase-order-where-change-management-is-turned-on-the-purchase-order-goes-to-a-confirmed-state"></a>Se um resto da entrega for cancelado em uma ordem de compra na qual o gerenciamento de alterações está ativado, a ordem de compra vai para um estado Confirmado.

### <a name="issue-description"></a>Descrição do problema

Para uma ordem de compra sujeita ao gerenciamento de alterações, se a única alteração solicitada for o cancelamento de uma entrega pendente em uma ou mais linhas, a ordem de compra irá diretamente para um estado *Confirmado* quando for aprovada e nenhum diário será criado.

### <a name="issue-resolution"></a>Resolução do problema

O cancelamento de uma pendência de entrega não afeta o conteúdo do diário de confirmação. Essa funcionalidade deve ser usada quando a linha foi parcialmente recebida e a qualidade final deve ser cancelada na etapa do processo após a confirmação da ordem de compra com o fornecedor.

Se isso deve ser refletido na confirmação da ordem de compra, a quantidade deve ser ajustada na linha da ordem de compra para que a confirmação seja obrigatória. Como alternativa, se nada foi recebido na linha, a quantidade pode ser removida. Nesse caso, será necessário reconfirmar.

## <a name="canceled-purchase-orders-appear-in-the-draft-list-in-the-purchase-order-preparation-workspace"></a>As ordens de compra canceladas aparecem na lista de rascunhos no espaço de trabalho de preparação da Ordem de Compra.

### <a name="issue-description"></a>Descrição do problema

Depois de cancelar as ordens de compra que estavam em um estado *Confirmado*, as ordens de compra canceladas ainda aparecem na lista de ordens de compra de rascunho no espaço de trabalho **Preparação da ordem de compra**.

### <a name="issue-resolution"></a>Resolução do problema

Esse problema ocorre apenas para ordens de compra sujeitas ao gerenciamento de alterações. Ele ocorre porque o cancelamento é considerado uma alteração que deve ser aprovada. A aprovação pode ser feita automaticamente pelo sistema. Portanto, o processo é enviar a ordem de compra cancelada para o fluxo de trabalho de aprovação, de forma que possa ir para um estado *Aprovado*. Nesse ponto, a ordem de compra não será mais exibida na lista de ordens de compra de rascunho no espaço de trabalho **Preparação da ordem de compra**.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]