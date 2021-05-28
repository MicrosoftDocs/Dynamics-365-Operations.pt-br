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
ms.openlocfilehash: 3dd13f6a3e5ce3c894e96f420358d337f2e43dba
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026284"
---
# <a name="there-is-no-from-date-value-on-the-active-prices-tab-of-the-item-price-page"></a><span data-ttu-id="02a83-103">Não há um valor no campo "Data inicial" na guia "Preços ativos" da página "Preço do item"</span><span class="sxs-lookup"><span data-stu-id="02a83-103">There is no From date value on the Active prices tab of the Item price page</span></span>

<span data-ttu-id="02a83-104">Número de KB: 4613548</span><span class="sxs-lookup"><span data-stu-id="02a83-104">KB number: 4613548</span></span>

## <a name="symptoms"></a><span data-ttu-id="02a83-105">Sintomas</span><span class="sxs-lookup"><span data-stu-id="02a83-105">Symptoms</span></span>

<span data-ttu-id="02a83-106">Não há um valor no campo **Data inicial** na guia **Preços ativos** da página **Preço do item**.</span><span class="sxs-lookup"><span data-stu-id="02a83-106">There is no **From date** value on the **Active prices** tab of the **Item price** page.</span></span>

## <a name="resolution"></a><span data-ttu-id="02a83-107">Resolução</span><span class="sxs-lookup"><span data-stu-id="02a83-107">Resolution</span></span>

<span data-ttu-id="02a83-108">O valor da **Data inicial** (data de efetivação) definido sobre o preço pendente não é transferido para o preço ativo.</span><span class="sxs-lookup"><span data-stu-id="02a83-108">The **From date** value (effective date) that is set on the pending price isn't transferred to the active price.</span></span>

<span data-ttu-id="02a83-109">Quando um registro de custo de item é inserido pela primeira vez, ele tem um status *Pendente* e uma data de efetivação pretendida.</span><span class="sxs-lookup"><span data-stu-id="02a83-109">When an item cost record is first entered, it has a status of *Pending* and an intended effective date.</span></span> <span data-ttu-id="02a83-110">Quando você ativa o registro de custo do item, o status é atualizado para *Ativo* e a data de efetivação é atualizada para a data de ativação.</span><span class="sxs-lookup"><span data-stu-id="02a83-110">When you activate the item cost record, the status is updated to *Active*, and the effective date is updated to the activation date.</span></span> <span data-ttu-id="02a83-111">Portanto, a data de ativação do preço ativo é sempre a data real da ativação.</span><span class="sxs-lookup"><span data-stu-id="02a83-111">Therefore, the active price's activation date is always the actual date of the activation.</span></span>

<span data-ttu-id="02a83-112">Para obter mais informações, consulte [Visão geral das versões de avaliação de custo](../../cost-management/costing-versions.md).</span><span class="sxs-lookup"><span data-stu-id="02a83-112">For more information, see [Costing versions overview](../../cost-management/costing-versions.md).</span></span>
