---
title: Não é possível mover a placa de licença se Saída em branco e Recebimento em branco forem permitidos
description: Não é possível mover uma placa de licença se o número de série tiver Saída em branco e Recebimento em branco permitidos. Isso será corrigido ao tornar opcional o campo de número de série.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 0047f79aa417c8fc910447505f07963d014f54e7
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7475572"
---
# <a name="cant-move-license-plate-if-serial-number-has-blank-issue-and-blank-receipt-allowed"></a>Não é possível mover a placa de licença se o número de série tiver Saída em branco e Recebimento em branco permitidos

## <a name="symptoms"></a>Sintomas

Não é possível mover uma placa de licença usando um item de menu **Movimento** se o número de série tiver configurações de *Saída em branco permitida* e *Recebimento em branco permitido* no grupo de dimensão de rastreamento e se houver várias placas no mesmo local, algumas das quais com números de série e outras sem.

## <a name="resolution"></a>Resolução

Esse problema será corrigido por mudanças que são implantadas no [KB 4571546](https://fix.lcs.dynamics.com/Issue/Details?kb=4571546&bugId=467880&dbType=3&qc=5b46d7faa9cc326cebfe9854cb30be8ea30b21ef33d3572c325fbb21202de687). Essas alterações tornarão o campo **Número de série** opcional quando Saída em branco e Recebimento em branco forem permitidos.
