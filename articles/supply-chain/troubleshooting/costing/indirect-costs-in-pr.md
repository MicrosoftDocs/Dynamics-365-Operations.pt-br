---
title: O relatório Custos indiretos no processo inclui pedidos de produção excluídos
description: O relatório Custos indiretos no processo apresenta informações sobre pedidos de produção que foram processados parcialmente e depois excluídos.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ProdIndirectCostInProgress
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 707fa9bb30129c3656e10c6756dee770a7712e65
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026270"
---
# <a name="the-indirect-costs-in-process-report-includes-deleted-production-orders"></a>O relatório Custos indiretos no processo inclui pedidos de produção excluídos

Número da base de dados de conhecimento: 4612748

## <a name="symptoms"></a>Sintomas

O relatório **Custos indiretos no processo** apresenta informações sobre pedidos de produção que foram processados parcialmente e depois excluídos.

## <a name="resolution"></a>Resolução

Quando você reverte um pedido de produção, você também reverte todas as transações desse pedido de produção. Ao excluir o pedido de produção, as tabelas do razão auxiliar e do razão geral persistem em todas as transações relacionadas a ele. Os relatórios mostrarão as transações nas tabelas do razão auxiliar. Para o pedido de produção específico, o valor líquido deve ser 0,00.
