---
title: A estação de embalagem não mostra observações do produto
description: A estação de embalagem não mostra observações do produto.
author: perlynne
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: WHSPack
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: bf64de3e67c1000dad9d5b37fffe622ae0e300b3
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026266"
---
# <a name="packing-station-doesnt-show-product-notes"></a>A estação de embalagem não mostra observações do produto

Número da base de dados de conhecimento: 4614615

## <a name="symptoms"></a>Sintomas

As observações de embalagem não são exibidas no formulário de embalagem quando as instruções de embalagem são adicionadas como anexo a um produto principal ou variante do produto.

## <a name="resolution"></a>Resolução

O sistema está agindo como esperado.

A lógica atual para exibir observações de embalagem no formulário de embalagem exige que as observações sejam associadas aos envios.
