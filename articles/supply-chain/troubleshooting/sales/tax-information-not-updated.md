---
title: As informações de impostos não serão atualizadas se o local da ordem de venda for alterado
description: Se o local, o depósito ou o endereço de entrega for alterado em um cabeçalho da ordem de venda, as informações de imposto do caso não serão atualizadas automaticamente nas linhas. Você deve fazer isso manualmente.
author: SmithaNataraj
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 77a73a787ff8a174c575f3b4f75694ded45d5712
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7475584"
---
# <a name="tax-information-isnt-updated-if-location-on-a-sales-order-header-is-changed"></a>As informações de impostos não são atualizadas se o local em um cabeçalho da ordem de venda for alterado

## <a name="symptoms"></a>Sintomas

Se o local, o depósito ou o endereço de entrega for alterado em um cabeçalho da ordem de venda, as informações de imposto do caso não serão atualizadas automaticamente nas linhas.

## <a name="resolution"></a>Resolução

Esse comportamento é por design. O problema ocorre porque o endereço de entrega, o site e o depósito não são alterados automaticamente no nível da linha. Você deve atualizá-los manualmente.
