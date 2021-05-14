---
title: A última linha de trabalho fechada deve ser de colocação
description: A última linha de trabalho fechada deve ser de colocação
author: perlynne
ms.date: 04/15/2021
ms.topic: troubleshooting
ms.search.form: WHSWorkTable_WHSWorkCancel, WHSWorkTableListPage_WHSWorkCancel
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-05-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: a5b78154b51252b3ac96ba28c254e823caf87019
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924366"
---
# <a name="the-last-closed-work-line-must-be-a-put"></a><span data-ttu-id="383f6-103">A última linha de trabalho fechada deve ser de colocação</span><span class="sxs-lookup"><span data-stu-id="383f6-103">The last closed work line must be a put</span></span>

<span data-ttu-id="383f6-104">Código de erro: WAX1285</span><span class="sxs-lookup"><span data-stu-id="383f6-104">Error code: WAX1285</span></span>

## <a name="symptoms"></a><span data-ttu-id="383f6-105">Sintomas</span><span class="sxs-lookup"><span data-stu-id="383f6-105">Symptoms</span></span>

<span data-ttu-id="383f6-106">O sistema mostra a seguinte mensagem de erro:</span><span class="sxs-lookup"><span data-stu-id="383f6-106">The system shows the following error message:</span></span>

> <span data-ttu-id="383f6-107">A última linha de trabalho fechada deve ser de colocação.</span><span class="sxs-lookup"><span data-stu-id="383f6-107">The last closed work line must be a put.</span></span>

## <a name="cause"></a><span data-ttu-id="383f6-108">Causa</span><span class="sxs-lookup"><span data-stu-id="383f6-108">Cause</span></span>

<span data-ttu-id="383f6-109">O trabalho não pode ser cancelado no estado atual.</span><span class="sxs-lookup"><span data-stu-id="383f6-109">The work can't be canceled in its current state.</span></span>

<span data-ttu-id="383f6-110">Na última linha de trabalho, o campo **Status do trabalho** está definido como *Fechado*, mas o campo **Tipo de trabalho** não está definido como *Colocado*.</span><span class="sxs-lookup"><span data-stu-id="383f6-110">On the last work line, the **Work status** field is set to *Closed*, but the **Work type** field isn't set to *Put*.</span></span>

## <a name="resolution"></a><span data-ttu-id="383f6-111">Resolução</span><span class="sxs-lookup"><span data-stu-id="383f6-111">Resolution</span></span>

<span data-ttu-id="383f6-112">Para cancelar o trabalho, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="383f6-112">To cancel the work, follow these steps.</span></span>

1. <span data-ttu-id="383f6-113">Vá para **Gerenciamento de depósito \> Tarefas periódicas \> Limpar \> Cancelar trabalho**.</span><span class="sxs-lookup"><span data-stu-id="383f6-113">Go to **Warehouse management \> Periodic tasks \> Clean up \> Cancel work**.</span></span>
1. <span data-ttu-id="383f6-114">No campo **ID do trabalho**, especifique a ID do trabalho que deseja cancelar.</span><span class="sxs-lookup"><span data-stu-id="383f6-114">In the **Work ID** field, specify the ID of the work that you want to cancel.</span></span>
1. <span data-ttu-id="383f6-115">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="383f6-115">Select **OK**.</span></span>
1. <span data-ttu-id="383f6-116">Selecione **Sim** para confirmar que você deseja cancelar o trabalho.</span><span class="sxs-lookup"><span data-stu-id="383f6-116">Select **Yes** to confirm that you want to cancel the work.</span></span>

<span data-ttu-id="383f6-117">Para obter mais informações, consulte [Cancelar trabalho de depósito para tratamento de exceções](../../warehousing/cancel-warehouse-work.md).</span><span class="sxs-lookup"><span data-stu-id="383f6-117">For more information, see [Cancel warehouse work for exception handling](../../warehousing/cancel-warehouse-work.md).</span></span>
