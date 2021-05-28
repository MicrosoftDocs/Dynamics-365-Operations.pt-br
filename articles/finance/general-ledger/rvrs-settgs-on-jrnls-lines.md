---
title: Reverter configurações em diários e linhas
description: Este tópico aborda por que uma entrada de estorno que foi inserida em um diário geral pode não ser incluída na transação lançada.
author: kweekley
ms.date: 04/29/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2021-5-05
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 74020f6fc9b0fa8e05a1e2a09fd13dcd60490dc0
ms.sourcegitcommit: 817716c2e96f24af0ef1d7d5323afdeccdc602f3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/13/2021
ms.locfileid: "6028548"
---
# <a name="reverse-settings-on-journals-and-lines"></a><span data-ttu-id="4d54f-103">Reverter configurações em diários e linhas</span><span class="sxs-lookup"><span data-stu-id="4d54f-103">Reverse settings on journals and lines</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4d54f-104">Este tópico aborda por que uma entrada de estorno que foi inserida em um diário geral pode não ser incluída na transação lançada.</span><span class="sxs-lookup"><span data-stu-id="4d54f-104">This topic addresses why a reversing entry that was entered on a general journal might not be included on the posted transaction.</span></span>  

## <a name="symptom"></a><span data-ttu-id="4d54f-105">Sintoma</span><span class="sxs-lookup"><span data-stu-id="4d54f-105">Symptom</span></span>

<span data-ttu-id="4d54f-106">Um diário geral inclui uma entrada de estorno e a data de estorno no diário.</span><span class="sxs-lookup"><span data-stu-id="4d54f-106">A general journal includes a reversing entry and reversing date on the journal.</span></span> <span data-ttu-id="4d54f-107">Quando você lança o diário, nenhum dos comprovantes é revertido.</span><span class="sxs-lookup"><span data-stu-id="4d54f-107">When you post the journal, none of the vouchers are reversed.</span></span> <span data-ttu-id="4d54f-108">Por que isso ocorre?</span><span class="sxs-lookup"><span data-stu-id="4d54f-108">Why does this happen?</span></span>

## <a name="resolution"></a><span data-ttu-id="4d54f-109">Resolução</span><span class="sxs-lookup"><span data-stu-id="4d54f-109">Resolution</span></span>

<span data-ttu-id="4d54f-110">Quando o diário é lançado, o processo de estorno examina apenas as configurações de **Entrada de estorno** e **Data de estorno** na seção **Linhas** do comprovante.</span><span class="sxs-lookup"><span data-stu-id="4d54f-110">When the journal is posted, the reversing process looks only at the **Revering entry** and **Reversing date** settings on the **Lines** section of the voucher.</span></span> <span data-ttu-id="4d54f-111">Essa abordagem permite que um diário inclua alguns comprovantes que estejam marcados para estorno e outros que não estejam.</span><span class="sxs-lookup"><span data-stu-id="4d54f-111">This approach allows a journal to include some vouchers that are marked for reversing, and others that are not.</span></span>

<span data-ttu-id="4d54f-112">Os valores do diário são usados somente como padrões ao adicionar *novas* linhas.</span><span class="sxs-lookup"><span data-stu-id="4d54f-112">The values from the journal are only used as defaults when adding *new* lines.</span></span> <span data-ttu-id="4d54f-113">A alteração dos valores no diário não afeta as linhas existentes.</span><span class="sxs-lookup"><span data-stu-id="4d54f-113">Changing the values on the journal doesn’t affect existing lines.</span></span> <span data-ttu-id="4d54f-114">Neste exemplo, as linhas do comprovante foram inseridas primeiro.</span><span class="sxs-lookup"><span data-stu-id="4d54f-114">In this example, the voucher lines were entered first.</span></span> <span data-ttu-id="4d54f-115">Ao inserir os detalhes da linha antes de designar o diário como estorno, a designação como entrada e data de estorno não será aplicada a nenhuma linha existente.</span><span class="sxs-lookup"><span data-stu-id="4d54f-115">When you enter the line detail before designating the journal as reversing, the designation as a reversing entry and date won't be applied to any existing lines.</span></span>

<span data-ttu-id="4d54f-116">A alteração da entrada de estorno ou da data de estorno em uma linha existente propaga essa alteração para outras linhas no mesmo comprovante.</span><span class="sxs-lookup"><span data-stu-id="4d54f-116">Changing the reversing entry or reversing date on an existing line propagates that change to other lines in the same voucher.</span></span> <span data-ttu-id="4d54f-117">Para otimizar o desempenho, a grade não é atualizada após a propagação de alterações para outras linhas.</span><span class="sxs-lookup"><span data-stu-id="4d54f-117">To optimize performance, the grid is not refreshed after propagating changes to other Lines.</span></span> <span data-ttu-id="4d54f-118">Você pode exibir os valores atualizados atualizando a grade.</span><span class="sxs-lookup"><span data-stu-id="4d54f-118">You can display the updated values by refreshing the grid.</span></span>


