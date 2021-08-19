---
title: Não há um valor no campo "Data inicial" na guia "Preços ativos" da página "Preço do item"
description: Não há um valor no campo "Data inicial" na guia "Preços ativos" da página "Preço do item".
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: InventItemPrice
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: dc0071bc508fc1b2fcfa5071f0756434641b7e6f872308ed4febb0cb34d37840
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6730121"
---
# <a name="there-is-no-from-date-value-on-the-active-prices-tab-of-the-item-price-page"></a>Não há um valor no campo "Data inicial" na guia "Preços ativos" da página "Preço do item"

Número de KB: 4613548

## <a name="symptoms"></a>Sintomas

Não há um valor no campo **Data inicial** na guia **Preços ativos** da página **Preço do item**.

## <a name="resolution"></a>Resolução

O valor da **Data inicial** (data de efetivação) definido sobre o preço pendente não é transferido para o preço ativo.

Quando um registro de custo de item é inserido pela primeira vez, ele tem um status *Pendente* e uma data de efetivação pretendida. Quando você ativa o registro de custo do item, o status é atualizado para *Ativo* e a data de efetivação é atualizada para a data de ativação. Portanto, a data de ativação do preço ativo é sempre a data real da ativação.

Para obter mais informações, consulte [Visão geral das versões de avaliação de custo](../../cost-management/costing-versions.md).
