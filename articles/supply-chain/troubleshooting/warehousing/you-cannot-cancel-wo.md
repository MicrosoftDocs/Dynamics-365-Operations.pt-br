---
title: Não é possível cancelar um trabalho que esteja em um usuário
description: Não é possível cancelar um trabalho que esteja em um usuário
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
ms.openlocfilehash: e5f6912cfb1d5be8e46b7989856af99f8a611c11
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924392"
---
# <a name="you-cant-cancel-work-that-is-on-a-user"></a><span data-ttu-id="6c2e9-103">Não é possível cancelar um trabalho que esteja em um usuário</span><span class="sxs-lookup"><span data-stu-id="6c2e9-103">You can't cancel work that is on a user</span></span>

<span data-ttu-id="6c2e9-104">Código de erro: WAX708</span><span class="sxs-lookup"><span data-stu-id="6c2e9-104">Error code: WAX708</span></span>

## <a name="symptoms"></a><span data-ttu-id="6c2e9-105">Sintomas</span><span class="sxs-lookup"><span data-stu-id="6c2e9-105">Symptoms</span></span>

<span data-ttu-id="6c2e9-106">O sistema mostra a seguinte mensagem de erro:</span><span class="sxs-lookup"><span data-stu-id="6c2e9-106">The system shows the following error message:</span></span>

> <span data-ttu-id="6c2e9-107">Você não pode cancelar o trabalho que está em um usuário.</span><span class="sxs-lookup"><span data-stu-id="6c2e9-107">You cannot cancel work that is on a user.</span></span>

## <a name="cause"></a><span data-ttu-id="6c2e9-108">Causa</span><span class="sxs-lookup"><span data-stu-id="6c2e9-108">Cause</span></span>

<span data-ttu-id="6c2e9-109">O trabalho está bloqueado por um usuário e não pode ser cancelado.</span><span class="sxs-lookup"><span data-stu-id="6c2e9-109">The work is locked by a user and can't be canceled.</span></span> <span data-ttu-id="6c2e9-110">Para confirmar isso, abra a ID do trabalho e, em seguida, abra a guia **Geral**. Se o trabalho estiver bloqueado, o campo **Status do trabalho** será definido como *Em andamento*, e o campo **Bloqueado por** será definido como uma ID de usuário.</span><span class="sxs-lookup"><span data-stu-id="6c2e9-110">To confirm this, open the work ID and then open the **General** tab. If the work is locked, the **Work status** field will be set to *In progress*, and the **Locked by** field will be set to a user ID.</span></span>

## <a name="resolution"></a><span data-ttu-id="6c2e9-111">Resolução</span><span class="sxs-lookup"><span data-stu-id="6c2e9-111">Resolution</span></span>

<span data-ttu-id="6c2e9-112">Para cancelar o trabalho, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="6c2e9-112">To cancel the work, follow these steps.</span></span>

1. <span data-ttu-id="6c2e9-113">Vá para **Gerenciamento de depósito \> Tarefas periódicas \> Limpar \> Cancelar trabalho**.</span><span class="sxs-lookup"><span data-stu-id="6c2e9-113">Go to **Warehouse management \> Periodic tasks \> Clean up \> Cancel work**.</span></span>
1. <span data-ttu-id="6c2e9-114">No campo **ID do trabalho**, especifique a ID do trabalho que deseja cancelar.</span><span class="sxs-lookup"><span data-stu-id="6c2e9-114">In the **Work ID** field, specify the ID of the work that you want to cancel.</span></span>
1. <span data-ttu-id="6c2e9-115">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="6c2e9-115">Select **OK**.</span></span>
1. <span data-ttu-id="6c2e9-116">Selecione **Sim** para confirmar que você deseja cancelar o trabalho.</span><span class="sxs-lookup"><span data-stu-id="6c2e9-116">Select **Yes** to confirm that you want to cancel the work.</span></span>

<span data-ttu-id="6c2e9-117">Para obter mais informações, consulte [Cancelar trabalho de depósito para tratamento de exceções](../../warehousing/cancel-warehouse-work.md).</span><span class="sxs-lookup"><span data-stu-id="6c2e9-117">For more information, see [Cancel warehouse work for exception handling](../../warehousing/cancel-warehouse-work.md).</span></span>
