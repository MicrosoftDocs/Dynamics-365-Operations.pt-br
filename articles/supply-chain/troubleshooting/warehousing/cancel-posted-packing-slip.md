---
title: Não é possível cancelar uma guia de remessa depois de lançada de uma ordem
description: Quando os processos de separação e remessa são habilitados para WMS, você não consegue cancelar uma guia de remessa depois de lançada em uma ordem de venda. Esta página oferece uma solução alternativa.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: d20e66e2721560b8409eb63c3546a79adc188c7c
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7475633"
---
# <a name="cant-cancel-a-packing-slip-after-its-posted-from-a-sales-order"></a>Não é possível cancelar uma guia de remessa depois de lançada em uma ordem de venda

## <a name="symptoms"></a>Sintomas

Quando os processos de separação e remessa são habilitados para gerenciamento de depósito avançado (WMS), não é possível cancelar uma guia de remessa depois de lançada em uma ordem de venda.

## <a name="resolution"></a>Resolução

Para corrigir guias de remessa lançadas para itens habilitados para WMS, o lançamento deve ocorrer a partir da carga, não a partir da ordem. A Microsoft avaliou esse problema e determinou que é uma limitação de recurso.  

Em geral, uma ordem de venda que foi separada e enviada por meio de processos de gerenciamento de depósito pode ter a guia de remessa atualizada a partir da carga ou remessa e do próprio documento de ordem de venda. Contudo, se você atualizar a guia de remessa a partir do documento de ordem de venda, a reversão da guia de remessa ainda não poderá ser feita a partir da carga ou da ordem de venda. Portanto, recomendamos que você use a guia de remessa a partir da carga. Nesse caso, será habilitada a reversão que deve ser feita a partir da carga.
