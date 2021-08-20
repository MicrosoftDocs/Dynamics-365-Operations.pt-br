---
title: Não é possível adicionar uma linha a uma requisição de compra após solicitar uma alteração
description: O sistema não permite a você adicionar uma linha a uma requisição de compra após solicitar uma alteração.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: PurchReqTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: jeyao
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: f873a487eb573eca562b3f7cd350ed0977a035ecd77b326c5d179777f559d817
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6753810"
---
# <a name="you-cant-add-a-line-to-a-purchase-requisition-after-you-request-a-change"></a>Não é possível adicionar uma linha a uma requisição de compra após solicitar uma alteração

Número da base de dados de conhecimento: 4611211

## <a name="symptoms"></a>Sintomas

O sistema não permite a você adicionar uma linha a uma requisição de compra após solicitar uma alteração.

## <a name="resolution"></a>Resolução

Você deve chamar o fluxo de trabalho novamente. Quando a requisição de compra estiver no status *Rascunho*, você pode continuar editando ou adicionar uma linha a ela.
