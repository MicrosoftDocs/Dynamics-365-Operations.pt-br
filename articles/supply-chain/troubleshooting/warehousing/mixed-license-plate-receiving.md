---
title: O recebimento de placas de licença mistas não funciona para todos os código de disposição
description: Quando o campo Ação para um código de disposição é definido como Crédito ou Sucata, você pode usar somente o item de menu Recebimento de placa de licença mista para processar itens devolvidos.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: b762255bc5ef6a1e15688a9c635940e92e67db3c
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7475605"
---
# <a name="mixed-license-plate-receiving-doesnt-work-for-any-disposition-code-but-credit"></a>O recebimento de placas de licença mistas não funciona para nenhum código de disposição, exceto Crédito

## <a name="symptoms"></a>Sintomas

Quando o campo **Ação** para um código de disposição é definido como *Crédito* ou *Sucata*, você pode usar somente o item de menu [Recebimento de placa de licença mista](/dynamics365/supply-chain/warehousing/mixed-license-plate-receiving) para processar itens devolvidos.

## <a name="resolution"></a>Resolução

A Microsoft avaliou esse problema e determinou que é uma limitação de recurso. Atualmente, somente [códigos de disposição](/dynamics365/supply-chain/service-management/set-up-disposition-codes) em que o campo **Ação** é definido como *Crédito* ou *Sucata* são compatíveis para recebimento de placa de licença mista.
