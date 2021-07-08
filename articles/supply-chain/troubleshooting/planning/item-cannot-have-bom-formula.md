---
title: O item não pode ter uma lista de materiais ou fórmula
description: Ao tentar firmar uma ordem, você recebe uma mensagem de erro durante a validação do item. Ela afirma que o item não pode ter uma lista de materiais (BOM) ou fórmula.
author: ankubik
ms.date: 06/10/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPO
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ankubik
ms.search.validFrom: 2021-06-10
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 6739b8b1e4d080055a2a0501427eac1c2e8a96c5
ms.sourcegitcommit: 18ca2df785e9656fdd4e8c0734eca2b2624fda10
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/22/2021
ms.locfileid: "6294011"
---
# <a name="item-cant-have-a-bom-or-formula"></a><span data-ttu-id="360f9-104">O item não pode ter uma lista de materiais ou fórmula</span><span class="sxs-lookup"><span data-stu-id="360f9-104">Item can't have a BOM or formula</span></span>

<span data-ttu-id="360f9-105">Código de erro: PRO2614</span><span class="sxs-lookup"><span data-stu-id="360f9-105">Error code: PRO2614</span></span>

## <a name="symptoms"></a><span data-ttu-id="360f9-106">Sintomas</span><span class="sxs-lookup"><span data-stu-id="360f9-106">Symptoms</span></span>

<span data-ttu-id="360f9-107">Ao tentar firmar uma ordem, você recebe a seguinte mensagem de erro durante a validação do item:</span><span class="sxs-lookup"><span data-stu-id="360f9-107">When you try to firm an order, you receive the following error message during item validation:</span></span>

> <span data-ttu-id="360f9-108">O item não pode ter uma BOM ou uma fórmula</span><span class="sxs-lookup"><span data-stu-id="360f9-108">Item cannot have a BOM or formula</span></span>

## <a name="resolution"></a><span data-ttu-id="360f9-109">Resolução</span><span class="sxs-lookup"><span data-stu-id="360f9-109">Resolution</span></span>

<span data-ttu-id="360f9-110">Os itens que possuem uma lista de materiais (BOM) ou fórmula devem ser do tipo *Item de planejamento*, *BOM* ou *fórmula*.</span><span class="sxs-lookup"><span data-stu-id="360f9-110">Items that have a bill of materials (BOM) or formula must be of the *Planning item*, *BOM*, or *formula* type.</span></span> <span data-ttu-id="360f9-111">Para alterar o tipo de um item, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="360f9-111">To change the type of an item, follow these steps.</span></span>

1. <span data-ttu-id="360f9-112">Vá para **Gerenciamento de informações do produto \> Produtos \> Produtos liberados**.</span><span class="sxs-lookup"><span data-stu-id="360f9-112">Go to **Product information management \> Products \> Released products**.</span></span>
1. <span data-ttu-id="360f9-113">Abra o produto relevante.</span><span class="sxs-lookup"><span data-stu-id="360f9-113">Open the relevant product.</span></span>
1. <span data-ttu-id="360f9-114">Na FastTab **Engenharia**, definida o campo **Tipo de produção** como *Item de planejamento*, *BOM* ou *Fórmula*.</span><span class="sxs-lookup"><span data-stu-id="360f9-114">On the **Engineer** FastTab, set the **Production type** field to *Planning item*, *BOM*, or *formula*.</span></span>
