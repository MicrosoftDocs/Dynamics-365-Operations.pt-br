---
title: As ordens planejadas são geradas para em estoque com ordens de produção
description: As ordens planejadas são geradas mesmo que você tenha itens em estoque e já existam ordens de produção para eles
author: ChristianRytt
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: aa803bcd7d43aa36675596050ccbe06831f1724d
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7475629"
---
# <a name="planned-orders-are-generated-for-in-stock-with-production-orders"></a>As ordens planejadas são geradas para em estoque com ordens de produção

## <a name="symptoms"></a>Sintomas

As ordens planejadas são geradas mesmo que você tenha itens em estoque e já existam ordens de produção para eles.

## <a name="resolution"></a>Resolução

É possível consertar esse problema aumentando o valor de **Dias positivos** para os grupos relevantes na página **Grupo de cobertura**. Essa alteração fará com que o sistema determine se o estoque disponível pode ser usado para a demanda. Depois, uma nova ordem planejada não será gerada para os itens que estão em estoque.
