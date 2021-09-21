---
title: Mesmo contrato comercial selecionado ao criar linhas da ordem de venda
description: Se houver mais de um contrato comercial definido para uma determinada data, aquele com o menor preço sempre será selecionado.
author: SmithaNataraj
ms.date: 06/24/2021
ms.topic: troubleshooting
ms.search.form: SalesTable, SalesTableListPage, SalesTableListPage_SalesCancelOrder
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: a586a399fb349965b972191bec1271651bec5fcb
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7475585"
---
# <a name="if-two-trade-agreements-exist-for-overlapping-dates-the-same-one-is-always-selected"></a>Se houver dois contratos comerciais para as datas sobrepostas, o mesmo será sempre selecionado

## <a name="symptoms"></a>Sintomas

Se dois contratos comerciais forem definidos para o mesmo período ou períodos sobrepostos, o mesmo contrato comercial parecerá ser selecionado sempre que você criar linhas de ordem de venda que contenham esses itens.

## <a name="resolution"></a>Resolução

Se houver mais de um contrato comercial para uma determinada data, o contrato comercial com o menor preço será sempre selecionado. Para obter mais informações, baixe o seguinte white paper: [Contratos comerciais no Microsoft Dynamics AX 2012](https://www.axug.com/HigherLogic/System/DownloadDocumentFile.ashx?DocumentFileKey=3396a3a8-1f48-4d85-8cd6-5fa982f62e90).
