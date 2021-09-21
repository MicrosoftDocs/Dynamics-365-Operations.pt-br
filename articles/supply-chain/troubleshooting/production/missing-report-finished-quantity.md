---
title: Falha na atualização do Relatório de Conclusão com erro de quantidade ausente
description: Se você tentar encerrar uma ordem de produção enquanto relata a quantidade de erros, mas não o tempo ou a quantidade de material, a atualização do relatório de conclusão falhará.
author: SmithaNataraj
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 7785549c47063727f2749749940c1a96a351e70f
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7475551"
---
# <a name="report-as-finished-update-fails-with-a-missing-quantity-error"></a>Falha na atualização do Relatório de Conclusão com um erro de quantidade ausente

## <a name="symptoms"></a>Sintomas

Você tenta relatar uma ordem de produção como concluída enquanto relata a quantidade de erros, mas não enquanto relata o tempo ou a quantidade de material. A atualização do relatório de conclusão falhará quando você tentar encerrar a ordem de produção. Além disso, você receberá a seguinte mensagem de erro:

> Quantidade de relatório de conclusão ausente.

## <a name="resolution"></a>Resolução

Se relatar a quantidade de erros em uma ordem de produção, você também deverá relatar a quantidade total.
