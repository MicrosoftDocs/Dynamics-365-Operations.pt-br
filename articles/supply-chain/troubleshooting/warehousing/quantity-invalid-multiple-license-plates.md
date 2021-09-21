---
title: A quantidade não é válida para o trabalho de separação com vários LPs
description: Quando há trabalhos de separação com várias placas de licença em um local, a quantidade não é válida para a unidade ea. Verifique se os campos a seguir estão corretos.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 5b245f71e80339fee3e42cfffa0396078a56926e
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7475539"
---
# <a name="quantity-not-valid-when-theres-picking-work-with-multiple-lps-in-one-location"></a>A quantidade não é válida quando há trabalho de separação com vários LPs em um local

## <a name="symptoms"></a>Sintomas

Quando há trabalhos de separação com várias placas de licença em um local, a quantidade não é válida para a unidade *ea* e você recebe a seguinte mensagem de erro:

> A quantidade não é válida para a unidade 1%.

## <a name="resolution"></a>Resolução

Verifique se os campos **ID do grupo de sequências de unidade** e **Conversões de unidades** no produto lançado ou na variante do produto estão definidos corretamente.

Observe que a mensagem de erro foi melhorada na versão 10.0.15 para mostrar a quantidade esperada (consulte [KB 4581627](https://fix.lcs.dynamics.com/Issue/Details/?bugId=486531)). A nova mensagem de erro é:

> A quantidade é inválida. Espera-se %1 %2.
