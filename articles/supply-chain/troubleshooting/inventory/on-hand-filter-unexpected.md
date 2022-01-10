---
title: O painel de filtros na página Lista disponível não funciona como esperado
description: Os filtros no painel de filtros na página "Lista disponível" não filtram os resultados conforme o esperado.
author: sherry-zheng
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: 2b2b233e22378c8710a63dce83d168bfd89eba7f
ms.sourcegitcommit: 008779c530798f563fe216810d34b2d56f2c8d3c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/14/2021
ms.locfileid: "7920489"
---
# <a name="the-filter-pane-on-the-on-hand-list-page-doesnt-work-as-expected"></a>O painel de filtros na página Lista disponível não funciona como esperado

## <a name="symptoms"></a>Sintomas

Os filtros no painel de filtros na página **Lista disponível** não filtram os resultados conforme o esperado.

## <a name="resolution"></a>Resolução

A página **Listagem disponível** é montada em uma tabela de estoque disponível detalhada que inclui todas as dimensões disponíveis. No entanto, a lista nesta página é um resumo. Portanto, é possível combinar linhas da tabela de origem, agregando valores de acordo com as dimensões que são mostradas.

Os filtros configurados no painel de filtros se aplicam à tabela de origem, não à lista agregada. Às vezes, esse comportamento pode produzir resultados inesperados, como mostrado [nestes exemplos](/dynamics365/supply-chain/inventory/inventory-on-hand-list.md#examples).

No entanto, os [filtros fornecidos na grade](/dynamics365/supply-chain/inventory/inventory-on-hand-list.md#grid-filters) *se* aplicam à lista agregada. Esses filtros incluem filtro rápido na parte superior da grade e o filtro para cada título de coluna.
