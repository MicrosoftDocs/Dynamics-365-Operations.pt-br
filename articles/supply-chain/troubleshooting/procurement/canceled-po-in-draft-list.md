---
title: As ordens de compra canceladas aparecem na lista de rascunhos no espaço de trabalho
description: As ordens de compra canceladas aparecem na lista de rascunhos no espaço de trabalho de preparação da Ordem de compra
author: kamaybac
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: PurchTable, PurchTablePart
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: f1dc23cd7e5b4b99cb7a9440d7d4666d8396511f
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7475602"
---
# <a name="canceled-purchase-orders-appear-in-the-draft-list-in-the-workspace"></a>As ordens de compra canceladas aparecem na lista de rascunhos no espaço de trabalho

## <a name="symptoms"></a>Sintomas

Depois de cancelar as ordens de compra que estavam em um estado *Confirmado*, as ordens de compra canceladas ainda aparecem na lista de ordens de compra de rascunho no espaço de trabalho **Preparação da ordem de compra**.

## <a name="resolution"></a>Resolução

Esse problema ocorre apenas para ordens de compra sujeitas ao gerenciamento de alterações. Ele ocorre porque o cancelamento é considerado uma alteração que deve ser aprovada. A aprovação pode ser feita automaticamente pelo sistema. Portanto, o processo é enviar a ordem de compra cancelada para o fluxo de trabalho de aprovação, de forma que possa ir para um estado *Aprovado*. Nesse ponto, a ordem de compra não será mais exibida na lista de ordens de compra de rascunho no espaço de trabalho **Preparação da ordem de compra**.
