---
title: Não é possível processar a entrega direta no depósito habilitado para WMS
description: Se o depósito estiver habilitado para o WMS, ele não será compatível com entrega direta. Para usar a entrega direta, você deve selecionar um item e depósito que não sejam WMS.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 090e17091e9fb92c2065679bb9b04637214e2eea
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7475632"
---
# <a name="direct-delivery-not-able-to-process-for-wms-enabled-warehouse"></a>Não é possível processar a entrega direta no depósito habilitado para WMS

## <a name="symptoms"></a>Sintomas

Se um item for adicionado a uma linha de venda para entrega direta a partir de um depósito habilitado para o gerenciamento de depósito (WMS), será exibida a seguinte mensagem de erro quando a linha de venda for atualizada:

> Não é possível processar a entrega direta no depósito 1% porque ele tem o gerenciamento de depósito habilitado. Especifique outro depósito que não esteja habilitado para gerenciamento de depósito.

## <a name="resolution"></a>Resolução

A Microsoft avaliou esse problema e determinou que é uma limitação de recurso. Atualmente, o WMS não oferece suporte para entrega direta. Portanto, para usar a entrega direta, você deve selecionar um item e depósito que não é WMS.
