---
title: O número de fórmula selecionado não é aprovado para um pedido de lote
description: Ao tentar firmar uma ordem planejada, você recebe uma mensagem de erro que afirma que o número da fórmula selecionado não é aprovado para uma ordem de lote.
author: ankubik
ms.date: 06/10/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPo
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ankubik
ms.search.validFrom: 2021-06-10
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 4f993c92ca0a2f8f79e4b0e0eda43904529163f8
ms.sourcegitcommit: 18ca2df785e9656fdd4e8c0734eca2b2624fda10
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/22/2021
ms.locfileid: "6294007"
---
# <a name="selected-formula-number-isnt-approved-for-a-batch-order"></a><span data-ttu-id="8c007-103">O número de fórmula selecionado não é aprovado para um pedido de lote</span><span class="sxs-lookup"><span data-stu-id="8c007-103">Selected formula number isn't approved for a batch order</span></span>

<span data-ttu-id="8c007-104">Código de erro: PRO2614</span><span class="sxs-lookup"><span data-stu-id="8c007-104">Error code: PRO2614</span></span>

## <a name="symptoms"></a><span data-ttu-id="8c007-105">Sintomas</span><span class="sxs-lookup"><span data-stu-id="8c007-105">Symptoms</span></span>

<span data-ttu-id="8c007-106">Ao tentar firmar uma ordem planejada, você recebe a seguinte mensagem de erro:</span><span class="sxs-lookup"><span data-stu-id="8c007-106">When you try to firm a planned order, you receive the following error message:</span></span>

> <span data-ttu-id="8c007-107">O número de fórmula selecionado não é aprovado para uma ordem de lote.</span><span class="sxs-lookup"><span data-stu-id="8c007-107">The selected formula number is not approved for a batch order.</span></span>

## <a name="cause"></a><span data-ttu-id="8c007-108">Causa</span><span class="sxs-lookup"><span data-stu-id="8c007-108">Cause</span></span>

<span data-ttu-id="8c007-109">O sistema valida a operação de firmamento para garantir que uma fórmula aprovada esteja disponível para o item ativo.</span><span class="sxs-lookup"><span data-stu-id="8c007-109">The system validates the firming operation to make sure that an approved formula is available for the active item.</span></span> <span data-ttu-id="8c007-110">Você provavelmente deve aprovar a fórmula.</span><span class="sxs-lookup"><span data-stu-id="8c007-110">You must probably approve the formula.</span></span>

## <a name="resolution"></a><span data-ttu-id="8c007-111">Resolução</span><span class="sxs-lookup"><span data-stu-id="8c007-111">Resolution</span></span>

<span data-ttu-id="8c007-112">Para aprovar uma fórmula, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="8c007-112">To approve a formula, follow these steps.</span></span>

1. <span data-ttu-id="8c007-113">Vá para **Gerenciamento de informações sobre produtos \> Lista de materiais e fórmulas \> Fórmulas**.</span><span class="sxs-lookup"><span data-stu-id="8c007-113">Go to **Product information management \> Bills of materials and formulas \> Formulas**.</span></span>
1. <span data-ttu-id="8c007-114">Selecione a fórmula relevante.</span><span class="sxs-lookup"><span data-stu-id="8c007-114">Select the relevant formula.</span></span>
1. <span data-ttu-id="8c007-115">No Painel de Ação, na guia **Fórmula**, no grupo **Manter**, selecione **Aprovar fórmula**.</span><span class="sxs-lookup"><span data-stu-id="8c007-115">On the Action Pane, on the **Formula** tab, in the **Maintain** group, select **Approve formula**.</span></span>
1. <span data-ttu-id="8c007-116">Na caixa de diálogo **Aprovar lista de materiais ou fórmula**, selecione um aprovador e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="8c007-116">In the **Approve BOM or formula** dialog box, select an approver, and then select **OK**.</span></span>
