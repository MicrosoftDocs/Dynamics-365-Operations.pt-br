---
title: Solucionar problemas de liberações e remessas parciais
description: Este tópico descreve como corrigir problemas comuns que você pode encontrar ao trabalhar com liberações parciais e remessas parciais no Microsoft Dynamics 365 Supply Chain Management.
author: perlynne
manager: tfehr
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: e89a430f90374733b23fadaf53f5bab598d67d62
ms.sourcegitcommit: deb711c92251ed48cdf20ea514d03461c26a2262
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/25/2020
ms.locfileid: "4645939"
---
# <a name="troubleshoot-partial-releases-and-partial-shipments"></a>Solucionar problemas de liberações e remessas parciais

[!include [banner](../includes/banner.md)]

Este tópico descreve como corrigir problemas comuns que você pode encontrar ao trabalhar com liberações parciais e remessas parciais no Microsoft Dynamics 365 Supply Chain Management.

## <a name="the-release-status-of-a-sales-order-remains-partially-released-even-after-the-sales-order-is-invoiced"></a>O status de liberação de uma ordem de venda permanece Parcialmente liberada, mesmo depois que a ordem de venda é faturada.

### <a name="issue-description"></a>Descrição do problema

Uma ordem de venda é uma ordem de entrega, mas um ou mais itens contidos nela possuem um modo de entrega diferente. Depois que a ordem é faturada, ela ainda tem um status de liberação de *Parcialmente liberada*.

Por exemplo, uma ordem de venda tem dois itens: um para entrega e outro para retirada. A entrega e a retirada foram realizadas. Portanto, ambas as linhas foram faturadas. No entanto, o status de liberação ainda é mostrado como *Parcialmente liberada*, o que é enganoso.

### <a name="issue-resolution"></a>Resolução do problema

O status de liberação se aplica apenas a linhas de ordem em que os itens estão habilitados para gerenciamento de depósito. Portanto, o status de liberação permanece *Parcialmente liberada* neste cenário. A Microsoft avaliou esse problema e determinou que é uma limitação de recurso. Uma extensão pode ser adicionada como parte da guia de remessa e do processo de faturamento para atualizar o status de liberação.
