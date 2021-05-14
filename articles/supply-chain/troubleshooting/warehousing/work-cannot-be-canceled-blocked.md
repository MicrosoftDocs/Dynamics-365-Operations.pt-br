---
title: O trabalho não pode ser cancelado porque está bloqueado
description: O trabalho não pode ser cancelado porque está bloqueado
author: perlynne
ms.date: 04/15/2021
ms.topic: troubleshooting
ms.search.form: WHSWorkTable_WHSWorkCancel
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-05-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: a7ab4c7263947767164702fb7dd6da7573175253
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924270"
---
# <a name="work-cant-be-canceled-because-its-blocked"></a><span data-ttu-id="b21d7-103">O trabalho não pode ser cancelado porque está bloqueado</span><span class="sxs-lookup"><span data-stu-id="b21d7-103">Work can't be canceled because it's blocked</span></span>

<span data-ttu-id="b21d7-104">Código de erro: WHSCancellationOfWorkBlockedByExecutingWave_ErrorMessage</span><span class="sxs-lookup"><span data-stu-id="b21d7-104">Error code: WHSCancellationOfWorkBlockedByExecutingWave_ErrorMessage</span></span>

## <a name="symptoms"></a><span data-ttu-id="b21d7-105">Sintomas</span><span class="sxs-lookup"><span data-stu-id="b21d7-105">Symptoms</span></span>

<span data-ttu-id="b21d7-106">O sistema mostra a seguinte mensagem de erro:</span><span class="sxs-lookup"><span data-stu-id="b21d7-106">The system shows the following error message:</span></span>

> <span data-ttu-id="b21d7-107">O trabalho %1 não pode ser cancelado porque está bloqueado pelo tipo de motivo %2.</span><span class="sxs-lookup"><span data-stu-id="b21d7-107">Work %1 cannot be cancelled because it is blocked by reason type %2.</span></span> <span data-ttu-id="b21d7-108">O trabalho deve ser desbloqueado para que possa ser cancelado.</span><span class="sxs-lookup"><span data-stu-id="b21d7-108">The work must be unblocked before it can be cancelled.</span></span>

## <a name="cause"></a><span data-ttu-id="b21d7-109">Causa</span><span class="sxs-lookup"><span data-stu-id="b21d7-109">Cause</span></span>

<span data-ttu-id="b21d7-110">O trabalho está bloqueado e não pode ser cancelado.</span><span class="sxs-lookup"><span data-stu-id="b21d7-110">The work is blocked and can't be canceled.</span></span>

<span data-ttu-id="b21d7-111">Na página **Trabalho**, na guia **Geral**, a opção **Bloqueado** está definida como *Sim*.</span><span class="sxs-lookup"><span data-stu-id="b21d7-111">On the **Work** page, on the **General** tab, the **Blocked** option is set to *Yes*.</span></span> <span data-ttu-id="b21d7-112">Essa configuração indica que o trabalho está bloqueado.</span><span class="sxs-lookup"><span data-stu-id="b21d7-112">This setting indicates that the work is blocked.</span></span> <span data-ttu-id="b21d7-113">A guia **Motivos do bloqueio** mostra por que o trabalho foi bloqueado.</span><span class="sxs-lookup"><span data-stu-id="b21d7-113">The **Blocking reasons** tab shows why the work was blocked.</span></span>

## <a name="resolution"></a><span data-ttu-id="b21d7-114">Resolução</span><span class="sxs-lookup"><span data-stu-id="b21d7-114">Resolution</span></span>

<span data-ttu-id="b21d7-115">Para desbloquear o trabalho, selecione a guia **Motivos do bloqueio** e, em seguida, siga uma destas etapas:</span><span class="sxs-lookup"><span data-stu-id="b21d7-115">To unblock the work, select the **Blocking reasons** tab, and then follow one of these steps:</span></span>

- <span data-ttu-id="b21d7-116">Se o campo **Motivo do bloqueio do trabalho** estiver definido como *Motivo não definido*: no Painel de Ações, na guia **Trabalho**, no grupo **Trabalho**, selecione **Desbloquear trabalho**.</span><span class="sxs-lookup"><span data-stu-id="b21d7-116">If the **Work blocking reason** field is set to *Undefined reason*: On the Action Pane, on the **Work** tab, in the **Work** group, select **Unblock work**.</span></span>
- <span data-ttu-id="b21d7-117">Se o campo **Motivo do bloqueio do trabalho** estiver definido como *Ciclo de processamento*: no Painel de Ações, na guia **Informações relacionadas**, no grupo **Informações relacionadas**, selecione **Ciclo**.</span><span class="sxs-lookup"><span data-stu-id="b21d7-117">If the **Work blocking reason** field is set to *Processing wave*: On the Action Pane, on the **Related information** tab, in the **Related information** group, select **Wave**.</span></span> <span data-ttu-id="b21d7-118">Em seguida, na página **Ciclos**, no Painel de Ações, na guia **Ciclo**, no grupo **Ciclo**, selecione **Limpar dados do ciclo**.</span><span class="sxs-lookup"><span data-stu-id="b21d7-118">Then, on the **Waves** page, on the Action Pane, on the **Wave** tab, in the **Wave** group, select **Cleanup wave data**.</span></span>

## <a name="workaround"></a><span data-ttu-id="b21d7-119">Solução alternativa</span><span class="sxs-lookup"><span data-stu-id="b21d7-119">Workaround</span></span>

<span data-ttu-id="b21d7-120">Se as etapas anteriores não corrigiram o problema, você pode cancelar o trabalho seguindo estas etapas.</span><span class="sxs-lookup"><span data-stu-id="b21d7-120">If the previous steps didn't fix the issue, you can cancel the work by following these steps.</span></span>

1. <span data-ttu-id="b21d7-121">Vá para **Gerenciamento de depósito \> Tarefas periódicas \> Limpar \> Cancelar trabalho**.</span><span class="sxs-lookup"><span data-stu-id="b21d7-121">Go to **Warehouse management \> Periodic tasks \> Clean up \> Cancel work**.</span></span>
1. <span data-ttu-id="b21d7-122">No campo **ID do trabalho**, especifique a ID do trabalho que deseja cancelar e que, atualmente, tem um valor **Status do trabalho** de *Aberto*, *Em andamento*, *Cancelado*, *Combinado* ou *Fechado*.</span><span class="sxs-lookup"><span data-stu-id="b21d7-122">In the **Work ID** field, specify the ID of the work that you want to cancel, and that currently has a **Work status** value of *Open*, *In progress*, *Canceled*, *Combined*, or *Closed*.</span></span>
1. <span data-ttu-id="b21d7-123">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="b21d7-123">Select **OK**.</span></span>
1. <span data-ttu-id="b21d7-124">Selecione **Sim** para confirmar que você deseja cancelar o trabalho.</span><span class="sxs-lookup"><span data-stu-id="b21d7-124">Select **Yes** to confirm that you want to cancel the work.</span></span>

<span data-ttu-id="b21d7-125">Para obter mais informações, consulte [Cancelar trabalho de depósito para tratamento de exceções](../../warehousing/cancel-warehouse-work.md).</span><span class="sxs-lookup"><span data-stu-id="b21d7-125">For more information, see [Cancel warehouse work for exception handling](../../warehousing/cancel-warehouse-work.md).</span></span>
