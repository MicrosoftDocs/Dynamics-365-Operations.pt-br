---
title: Redefinir trabalhos em lote presos
description: Este tópico explica como resolver problemas de trabalhos em lote que estão presos.
author: andreabichsel
ms.date: 03/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2021-03-19
ms.dyn365.ops.version: Platform update 42
ms.openlocfilehash: 906a391b3c28d15445f6ddf0fc547ebcf842ba19
ms.sourcegitcommit: d18d9cdb175c9d42eafbed66352c24b2aa94258b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/13/2021
ms.locfileid: "5881751"
---
# <a name="reset-stuck-batch-jobs"></a><span data-ttu-id="7162f-103">Redefinir trabalhos em lote presos</span><span class="sxs-lookup"><span data-stu-id="7162f-103">Reset stuck batch jobs</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

## <a name="issue"></a><span data-ttu-id="7162f-104">Problema</span><span class="sxs-lookup"><span data-stu-id="7162f-104">Issue</span></span>

<span data-ttu-id="7162f-105">O Microsoft Dynamics 365 Human Resources pode enfrentar problemas com trabalhos em lotes que estão presos em um estado **Executando** ou **Cancelando** e não são concluídos.</span><span class="sxs-lookup"><span data-stu-id="7162f-105">Microsoft Dynamics 365 Human Resources can experience issues with batch jobs that are stuck in either an **Executing** or **Canceling** state and don't complete.</span></span>

## <a name="resolution"></a><span data-ttu-id="7162f-106">Resolução</span><span class="sxs-lookup"><span data-stu-id="7162f-106">Resolution</span></span>

<span data-ttu-id="7162f-107">Quando um trabalho em lotes está preso em um estado **Executando** ou **Cancelando**, é possível redefinir o status ao forçar o cancelamento do trabalho.</span><span class="sxs-lookup"><span data-stu-id="7162f-107">When a batch job is stuck in an **Executing** or **Canceling** state, you can reset the status by forcing the cancellation of the job.</span></span> <span data-ttu-id="7162f-108">Após cancelá-lo, você pode redefinir o trabalho em lotes ao defini-lo com um status **Aguardando**.</span><span class="sxs-lookup"><span data-stu-id="7162f-108">After you cancel it, you can reset the batch job by setting it to a **Waiting** status.</span></span> <span data-ttu-id="7162f-109">Em seguida, ele será selecionado novamente para execução na próxima execução de lote agendada.</span><span class="sxs-lookup"><span data-stu-id="7162f-109">It will then be picked up again for execution in the next scheduled batch run.</span></span>

1. <span data-ttu-id="7162f-110">No espaço de trabalho **Administração do sistema**, selecione a página **Links** e selecione **Trabalhos em lote**.</span><span class="sxs-lookup"><span data-stu-id="7162f-110">In the **System administration** workspace, select the **Links** page, and select **Batch jobs**.</span></span>

2. <span data-ttu-id="7162f-111">Na página de lista **Trabalho em lotes**, selecione o trabalho que deve ser redefinido.</span><span class="sxs-lookup"><span data-stu-id="7162f-111">On the **Batch job** list page, select the job that needs to be reset.</span></span>

3. <span data-ttu-id="7162f-112">Na faixa de opções de ação, selecione **Forçar cancelamento** e confirme a ação.</span><span class="sxs-lookup"><span data-stu-id="7162f-112">On the action ribbon, select **Force cancel**, and confirm the action.</span></span>

   > [!NOTE]
   > <span data-ttu-id="7162f-113">A ação **Forçar cancelamento** está disponível somente quando o trabalho em lotes tem um status **Executando** ou **Cancelando** e não houver execução em lotes ou processos de cancelamento do trabalho em andamento.</span><span class="sxs-lookup"><span data-stu-id="7162f-113">The **Force cancel** action is only available when the selected batch job has a status of either **Executing** or **Canceling**, and no batch execution or cancellation processes are running for the job.</span></span>

4. <span data-ttu-id="7162f-114">Na faixa de opções de ação, selecione **Alterar status**.</span><span class="sxs-lookup"><span data-stu-id="7162f-114">On the action ribbon, select **Change status**.</span></span>

5. <span data-ttu-id="7162f-115">Na página **Selecionar novo status**, selecione **Aguardando** e depois **OK**.</span><span class="sxs-lookup"><span data-stu-id="7162f-115">On the **Select new status** page, select **Waiting**, and then select **OK**.</span></span>

   ![Selecionar um novo status de trabalho em lotes](./media/hr-admin-reset-batch-job-status.png)

## <a name="see-also"></a><span data-ttu-id="7162f-117">Consulte também</span><span class="sxs-lookup"><span data-stu-id="7162f-117">See also</span></span>

[<span data-ttu-id="7162f-118">Otimizar o desempenho ao agendar trabalhos em lotes após o expediente</span><span class="sxs-lookup"><span data-stu-id="7162f-118">Optimize performance by scheduling batch jobs after hours</span></span>](hr-admin-troubleshooting-batch-jobs.md)<br>
[<span data-ttu-id="7162f-119">Otimizar o desempenho com tarefas de limpeza automática</span><span class="sxs-lookup"><span data-stu-id="7162f-119">Optimize performance with auto cleanup tasks</span></span>](hr-admin-troubleshooting-batch-history.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
