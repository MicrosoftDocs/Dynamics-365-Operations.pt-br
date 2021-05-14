---
title: O trabalho não pode ser cancelado por causa de seu status
description: O trabalho não pode ser cancelado por causa de seu status
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
ms.openlocfilehash: 60b4da44ca5e6790302e0797640317cef8493db7
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924246"
---
# <a name="work-cant-be-canceled-because-of-its-status"></a><span data-ttu-id="84505-103">O trabalho não pode ser cancelado por causa de seu status</span><span class="sxs-lookup"><span data-stu-id="84505-103">Work can't be canceled because of its status</span></span>

<span data-ttu-id="84505-104">Código de erro: WAX2190</span><span class="sxs-lookup"><span data-stu-id="84505-104">Error code: WAX2190</span></span>

## <a name="symptoms"></a><span data-ttu-id="84505-105">Sintomas</span><span class="sxs-lookup"><span data-stu-id="84505-105">Symptoms</span></span>

<span data-ttu-id="84505-106">O sistema mostra a seguinte mensagem de erro:</span><span class="sxs-lookup"><span data-stu-id="84505-106">The system shows the following error message:</span></span>

> <span data-ttu-id="84505-107">Você não pode cancelar o trabalho %1 porque ele tem o status %2.</span><span class="sxs-lookup"><span data-stu-id="84505-107">You cannot cancel work %1 because it has a status of %2.</span></span>

## <a name="cause"></a><span data-ttu-id="84505-108">Causa</span><span class="sxs-lookup"><span data-stu-id="84505-108">Cause</span></span>

<span data-ttu-id="84505-109">O trabalho não pode ser cancelado no estado atual.</span><span class="sxs-lookup"><span data-stu-id="84505-109">The work can't be canceled in its current state.</span></span>

<span data-ttu-id="84505-110">O cabeçalho ou as linhas do trabalho não têm o valor **Status do trabalho** esperado.</span><span class="sxs-lookup"><span data-stu-id="84505-110">The work header or work lines don't have the expected **Work status** value.</span></span> <span data-ttu-id="84505-111">O campo **Status do trabalho** no cabeçalho do trabalho não está definido como *Aberto* ou *Em andamento*.</span><span class="sxs-lookup"><span data-stu-id="84505-111">The **Work status** field on the work header isn't set to *Open* or *In progress*.</span></span>

## <a name="resolution"></a><span data-ttu-id="84505-112">Resolução</span><span class="sxs-lookup"><span data-stu-id="84505-112">Resolution</span></span>

<span data-ttu-id="84505-113">Para cancelar o trabalho, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="84505-113">To cancel the work, follow these steps.</span></span>

1. <span data-ttu-id="84505-114">Vá para **Gerenciamento de depósito \> Tarefas periódicas \> Limpar \> Cancelar trabalho**.</span><span class="sxs-lookup"><span data-stu-id="84505-114">Go to **Warehouse management \> Periodic tasks \> Clean up \> Cancel work**.</span></span>
1. <span data-ttu-id="84505-115">No campo **ID do trabalho**, especifique a ID do trabalho que deseja cancelar.</span><span class="sxs-lookup"><span data-stu-id="84505-115">In the **Work ID** field, specify the ID of the work that you want to cancel.</span></span>
1. <span data-ttu-id="84505-116">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="84505-116">Select **OK**.</span></span>
1. <span data-ttu-id="84505-117">Selecione **Sim** para confirmar que você deseja cancelar o trabalho.</span><span class="sxs-lookup"><span data-stu-id="84505-117">Select **Yes** to confirm that you want to cancel the work.</span></span>

<span data-ttu-id="84505-118">Para obter mais informações, consulte [Cancelar trabalho de depósito para tratamento de exceções](../../warehousing/cancel-warehouse-work.md).</span><span class="sxs-lookup"><span data-stu-id="84505-118">For more information, see [Cancel warehouse work for exception handling](../../warehousing/cancel-warehouse-work.md).</span></span>
