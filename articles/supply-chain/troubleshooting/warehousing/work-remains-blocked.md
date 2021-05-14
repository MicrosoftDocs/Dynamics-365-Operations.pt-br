---
title: O trabalho permanece bloqueado
description: O trabalho permanece bloqueado
author: perlynne
ms.date: 04/15/2021
ms.topic: troubleshooting
ms.search.form: WHSWorkTableListPage_WHSWorkUnblocking
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-05-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: f85364d1ecfadc36b26c3395ab4402d3cb3b1603
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924121"
---
# <a name="work-remains-blocked"></a><span data-ttu-id="04e00-103">O trabalho permanece bloqueado</span><span class="sxs-lookup"><span data-stu-id="04e00-103">Work remains blocked</span></span>

<span data-ttu-id="04e00-104">Código de erro: WHSWorkBlockingExecutingWaveReason_ErrorMessage</span><span class="sxs-lookup"><span data-stu-id="04e00-104">Error code: WHSWorkBlockingExecutingWaveReason_ErrorMessage</span></span>

## <a name="symptoms"></a><span data-ttu-id="04e00-105">Sintomas</span><span class="sxs-lookup"><span data-stu-id="04e00-105">Symptoms</span></span>

<span data-ttu-id="04e00-106">O sistema mostra a seguinte mensagem de erro:</span><span class="sxs-lookup"><span data-stu-id="04e00-106">The system shows the following error message:</span></span>

> <span data-ttu-id="04e00-107">O trabalho %1 permanece bloqueado porque o ciclo relacionado %2 tem o status %3.</span><span class="sxs-lookup"><span data-stu-id="04e00-107">Work %1 remains blocked because the related wave %2 has status %3.</span></span>

## <a name="cause"></a><span data-ttu-id="04e00-108">Causa</span><span class="sxs-lookup"><span data-stu-id="04e00-108">Cause</span></span>

<span data-ttu-id="04e00-109">No momento, o trabalho está sendo processado em um ciclo e não pode ser desbloqueado, como indicado por uma das seguintes condições:</span><span class="sxs-lookup"><span data-stu-id="04e00-109">The work is currently being processed on a wave and can't be unblocked, as indicated by one of the following conditions:</span></span>

- <span data-ttu-id="04e00-110">Na guia **Motivos do bloqueio**, o campo **Motivo do bloqueio do trabalho** de uma ou mais linhas está definido como *Ciclo de processamento*.</span><span class="sxs-lookup"><span data-stu-id="04e00-110">On the **Blocking reasons** tab, the **Work blocking reason** field for one or more lines is set to *Processing wave*.</span></span>
- <span data-ttu-id="04e00-111">Ao selecionar **Ciclo** no grupo **Informações relacionadas**, na guia **Informações relacionadas** do Painel de Ações, o campo **Status do ciclo** é definido como *Processando*.</span><span class="sxs-lookup"><span data-stu-id="04e00-111">When you select **Wave** in the **Related information** group on the **Related information** tab of the Action Pane, the **Wave status** field is set to *Processing*.</span></span>

## <a name="resolution"></a><span data-ttu-id="04e00-112">Resolução</span><span class="sxs-lookup"><span data-stu-id="04e00-112">Resolution</span></span>

<span data-ttu-id="04e00-113">No Painel de Ações, na guia **Informações relacionadas**, no grupo **Informações relacionadas**, selecione **Ciclo**.</span><span class="sxs-lookup"><span data-stu-id="04e00-113">On the Action Pane, on the **Related information** tab, in the **Related information** group, select **Wave**.</span></span> <span data-ttu-id="04e00-114">Em seguida, na página **Ciclos**, no Painel de Ações, na guia **Ciclo**, no grupo **Ciclo**, selecione **Limpar dados do ciclo**.</span><span class="sxs-lookup"><span data-stu-id="04e00-114">Then, on the **Waves** page, on the Action Pane, on the **Wave** tab, in the **Wave** group, select **Cleanup wave data**.</span></span>

## <a name="workaround"></a><span data-ttu-id="04e00-115">Solução alternativa</span><span class="sxs-lookup"><span data-stu-id="04e00-115">Workaround</span></span>

<span data-ttu-id="04e00-116">Se as etapas anteriores não corrigiram o problema, você pode cancelar o trabalho seguindo estas etapas.</span><span class="sxs-lookup"><span data-stu-id="04e00-116">If the previous steps didn't fix the issue, you can cancel the work by following these steps.</span></span>

1. <span data-ttu-id="04e00-117">Vá para **Gerenciamento de depósito \> Tarefas periódicas \> Limpar \> Cancelar trabalho**.</span><span class="sxs-lookup"><span data-stu-id="04e00-117">Go to **Warehouse management \> Periodic tasks \> Clean up \> Cancel work**.</span></span>
1. <span data-ttu-id="04e00-118">No campo **ID do trabalho**, especifique a ID do trabalho que deseja cancelar e que, atualmente, tem um valor **Status do trabalho** de *Aberto*, *Em andamento*, *Cancelado*, *Combinado* ou *Fechado*.</span><span class="sxs-lookup"><span data-stu-id="04e00-118">In the **Work ID** field, specify the ID of the work that you want to cancel, and that currently has a **Work status** value of *Open*, *In progress*, *Canceled*, *Combined*, or *Closed*.</span></span>
1. <span data-ttu-id="04e00-119">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="04e00-119">Select **OK**.</span></span>
1. <span data-ttu-id="04e00-120">Selecione **Sim** para confirmar que você deseja cancelar o trabalho.</span><span class="sxs-lookup"><span data-stu-id="04e00-120">Select **Yes** to confirm that you want to cancel the work.</span></span>

<span data-ttu-id="04e00-121">Para obter mais informações, consulte [Cancelar trabalho de depósito para tratamento de exceções](../../warehousing/cancel-warehouse-work.md).</span><span class="sxs-lookup"><span data-stu-id="04e00-121">For more information, see [Cancel warehouse work for exception handling](../../warehousing/cancel-warehouse-work.md).</span></span>
