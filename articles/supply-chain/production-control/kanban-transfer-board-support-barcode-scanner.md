---
title: "Suporte do quadro de transferência kanban para os scanners de código de barras"
description: "O Quadro de transferência do kanban oferece suporte à entrada de scanner de um scanner de código de barras de widget para Selecionar, Iniciar, Concluir e Esvaziar um trabalho kanban."
author: ChristianRytt
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: KanbanBoardTransferJob
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 19391
ms.assetid: a426f645-d59b-4c98-8d78-eba8d64a562e
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 0696580dcf50139639dace641169d041021cf1b8
ms.contentlocale: pt-br
ms.lasthandoff: 04/13/2018

---

# <a name="kanban-transfer-board-support-for-barcode-scanners"></a><span data-ttu-id="99754-103">Suporte do quadro de transferência kanban para os scanners de código de barras</span><span class="sxs-lookup"><span data-stu-id="99754-103">Kanban transfer board support for barcode scanners</span></span>

[!INCLUDE [banner](../includes/banner.md)]

<span data-ttu-id="99754-104">O Quadro de transferência do kanban oferece suporte à entrada de scanner de um scanner de código de barras de widget para Selecionar, Iniciar, Concluir e Esvaziar um trabalho kanban.</span><span class="sxs-lookup"><span data-stu-id="99754-104">The Kanban transfer board supports scanner input from a widget barcode scanner to Select, Start, Complete, and Empty a kanban job.</span></span>

<a name="registration-modes"></a><span data-ttu-id="99754-105">Modos de registro</span><span class="sxs-lookup"><span data-stu-id="99754-105">Registration modes</span></span>
------------------

<span data-ttu-id="99754-106">Na Guia Rápida **Registro do scanner** você pode selecionar o modo do registro, que controla a ação quando você pesquisa um número de cartão kanban ou digita manualmente o número no campo Número do cartão kanban.</span><span class="sxs-lookup"><span data-stu-id="99754-106">On the **Scanner registration** FastTab you can select the registration mode, which controls the action when you scan a kanban card number or manually type the number in the Kanban card number field.</span></span>

| <span data-ttu-id="99754-107">Definir o modo de registro</span><span class="sxs-lookup"><span data-stu-id="99754-107">Set registration mode</span></span> | <span data-ttu-id="99754-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="99754-108">Description</span></span>                                                                                     |
|-----------------------|-------------------------------------------------------------------------------------------------|
| <span data-ttu-id="99754-109">Inicial</span><span class="sxs-lookup"><span data-stu-id="99754-109">Start</span></span>                 | <span data-ttu-id="99754-110">Registra um trabalho de transferência kanban como em andamento.</span><span class="sxs-lookup"><span data-stu-id="99754-110">Registers a Kanban transfer job as in progress.</span></span>                                                 |
| <span data-ttu-id="99754-111">Concluída</span><span class="sxs-lookup"><span data-stu-id="99754-111">Complete</span></span>              | <span data-ttu-id="99754-112">Registra um trabalho de transferência kanban como concluído.</span><span class="sxs-lookup"><span data-stu-id="99754-112">Registers a Kanban transfer job as completed.</span></span>                                                   |
| <span data-ttu-id="99754-113">Vazio</span><span class="sxs-lookup"><span data-stu-id="99754-113">Empty</span></span>                 | <span data-ttu-id="99754-114">Registra a unidade de manuseio de material referenciada por um cartão kanban como vazia.</span><span class="sxs-lookup"><span data-stu-id="99754-114">Registers the material handling unit that is referenced by a Kanban card as empty.</span></span>              |
| <span data-ttu-id="99754-115">Selecionar</span><span class="sxs-lookup"><span data-stu-id="99754-115">Select</span></span>                | <span data-ttu-id="99754-116">Registra um número de cartão kanban e seleciona automaticamente o trabalho referenciado na lista Kanban.</span><span class="sxs-lookup"><span data-stu-id="99754-116">Registers a Kanban card number and automatically selects the referenced job in the Kanban list.</span></span> |

 
<a name="registration-mode-select"></a><span data-ttu-id="99754-117">Seleção do Modo de registro</span><span class="sxs-lookup"><span data-stu-id="99754-117">Registration mode Select</span></span>
------------------------

<span data-ttu-id="99754-118">Quando você usa um leitor de código de barras para selecionar um trabalho, o modo de exibição do quadro kanban é alterado.</span><span class="sxs-lookup"><span data-stu-id="99754-118">When you use a bar code reader to select a job, the display mode of the kanban board changes.</span></span> <span data-ttu-id="99754-119">Desse modo, as seguintes condições se aplicam:</span><span class="sxs-lookup"><span data-stu-id="99754-119">In this mode, the following conditions apply:</span></span>

-   <span data-ttu-id="99754-120">Somente o trabalho kanban verificado é exibido.</span><span class="sxs-lookup"><span data-stu-id="99754-120">Only the scanned kanban job is displayed.</span></span>
-   <span data-ttu-id="99754-121">Os detalhes do trabalho selecionado são exibidos na Guia Rápida **Detalhes**.</span><span class="sxs-lookup"><span data-stu-id="99754-121">The details of the selected job are displayed in the **Details** FastTab.</span></span>
-   <span data-ttu-id="99754-122">A Guia Rápida **Mensagens** exibe mensagens somente do trabalho selecionado.</span><span class="sxs-lookup"><span data-stu-id="99754-122">The **Messages** FastTab displays messages only for the selected job.</span></span>
-   <span data-ttu-id="99754-123">Você pode alterar o status do trabalho usando as funções disponíveis no Painel de Ações.</span><span class="sxs-lookup"><span data-stu-id="99754-123">You can change the status of the job by using the functions that are available on the Action Pane.</span></span> <span data-ttu-id="99754-124">O quadro de transferência kanban continuará a exibir somente um único trabalho durante esse tempo.</span><span class="sxs-lookup"><span data-stu-id="99754-124">The Kanban transfer board continues to display only a single job during this time.</span></span>
-   <span data-ttu-id="99754-125">Você pode atualizar as informações da lista de trabalhos manualmente, clicando em **Atualizar** (Shift+F5) no Painel de Ação.</span><span class="sxs-lookup"><span data-stu-id="99754-125">You can update the information in the list of jobs manually by clicking **Refresh** (Shift+F5) on the Action Pane.</span></span> <span data-ttu-id="99754-126">Depois de atualizar as informações, os resultados completos sobre o filtro de trabalho serão exibidos mais uma vez.</span><span class="sxs-lookup"><span data-stu-id="99754-126">After you refresh the information, the full results for the job filter are displayed again.</span></span>

## <a name="job-status-and-possible-actions"></a><span data-ttu-id="99754-127">Status do trabalho e ações possíveis</span><span class="sxs-lookup"><span data-stu-id="99754-127">Job status and possible actions</span></span>
<span data-ttu-id="99754-128">O status do trabalho selecionado e o status de todos os trabalhos vinculados para kanbans de eventos, determinam se você pode processar o trabalho ainda mais.</span><span class="sxs-lookup"><span data-stu-id="99754-128">The status of the selected job and the status of any pegged jobs for event kanbans, determine whether you can process the job further.</span></span> <span data-ttu-id="99754-129">A tabela a seguir exibe informações sobre esses status e tarefas:</span><span class="sxs-lookup"><span data-stu-id="99754-129">The following table displays information about these statuses and tasks:</span></span>
-   <span data-ttu-id="99754-130">Os status disponíveis para trabalhos, ou para as unidades de manuseio de material referenciadas pelos trabalhos.</span><span class="sxs-lookup"><span data-stu-id="99754-130">The statuses that are available for jobs, or for the handling units that are referenced by the jobs.</span></span>
-   <span data-ttu-id="99754-131">Cada tarefa que você pode executar para o trabalho.</span><span class="sxs-lookup"><span data-stu-id="99754-131">Each task that you can perform for the job.</span></span>

<table>
<colgroup>
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="99754-132">Tipo de trabalho</span><span class="sxs-lookup"><span data-stu-id="99754-132">Job type</span></span></th>
<th><span data-ttu-id="99754-133">Status do trabalho ou status da unidade de manuseio de material</span><span class="sxs-lookup"><span data-stu-id="99754-133">Job status or handling unit status</span></span></th>
<th><span data-ttu-id="99754-134">Atualizar lista de separação</span><span class="sxs-lookup"><span data-stu-id="99754-134">Update picking list</span></span></th>
<th><span data-ttu-id="99754-135">Inicial</span><span class="sxs-lookup"><span data-stu-id="99754-135">Start</span></span></th>
<th><span data-ttu-id="99754-136">Atualizar registro</span><span class="sxs-lookup"><span data-stu-id="99754-136">Update registration</span></span></th>
<th><span data-ttu-id="99754-137">Concluída</span><span class="sxs-lookup"><span data-stu-id="99754-137">Complete</span></span></th>
<th><span data-ttu-id="99754-138">Vazio</span><span class="sxs-lookup"><span data-stu-id="99754-138">Empty</span></span></th>
<th><span data-ttu-id="99754-139">Criar kanbans de evento</span><span class="sxs-lookup"><span data-stu-id="99754-139">Create event kanbans</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="99754-140">Transferência</span><span class="sxs-lookup"><span data-stu-id="99754-140">Transfer</span></span></td>
<td><ul>
<li><span data-ttu-id="99754-141">Não planejados</span><span class="sxs-lookup"><span data-stu-id="99754-141">Not planned</span></span></li>
<li><span data-ttu-id="99754-142">Nenhum trabalho vinculado ou os trabalhos vinculados estão Concluídos</span><span class="sxs-lookup"><span data-stu-id="99754-142">No pegged jobs, or pegged jobs are Completed</span></span></li>
</ul></td>
<td><span data-ttu-id="99754-143">Sim</span><span class="sxs-lookup"><span data-stu-id="99754-143">Yes</span></span></td>
<td><span data-ttu-id="99754-144">Sim</span><span class="sxs-lookup"><span data-stu-id="99754-144">Yes</span></span></td>
<td><span data-ttu-id="99754-145">Sim</span><span class="sxs-lookup"><span data-stu-id="99754-145">Yes</span></span></td>
<td><span data-ttu-id="99754-146">Sim</span><span class="sxs-lookup"><span data-stu-id="99754-146">Yes</span></span></td>
<td><span data-ttu-id="99754-147">Não</span><span class="sxs-lookup"><span data-stu-id="99754-147">No</span></span></td>
<td><span data-ttu-id="99754-148">Sim</span><span class="sxs-lookup"><span data-stu-id="99754-148">Yes</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="99754-149">Transferência</span><span class="sxs-lookup"><span data-stu-id="99754-149">Transfer</span></span></td>
<td><ul>
<li><span data-ttu-id="99754-150">Não planejados</span><span class="sxs-lookup"><span data-stu-id="99754-150">Not planned</span></span></li>
<li><span data-ttu-id="99754-151">O trabalho vinculado não está Concluído</span><span class="sxs-lookup"><span data-stu-id="99754-151">The pegged job is not Completed</span></span></li>
</ul></td>
<td><span data-ttu-id="99754-152">Sim</span><span class="sxs-lookup"><span data-stu-id="99754-152">Yes</span></span></td>
<td><span data-ttu-id="99754-153">Não</span><span class="sxs-lookup"><span data-stu-id="99754-153">No</span></span></td>
<td><span data-ttu-id="99754-154">Sim</span><span class="sxs-lookup"><span data-stu-id="99754-154">Yes</span></span></td>
<td><span data-ttu-id="99754-155">Não</span><span class="sxs-lookup"><span data-stu-id="99754-155">No</span></span></td>
<td><span data-ttu-id="99754-156">Não</span><span class="sxs-lookup"><span data-stu-id="99754-156">No</span></span></td>
<td><span data-ttu-id="99754-157">Não</span><span class="sxs-lookup"><span data-stu-id="99754-157">No</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="99754-158">Transferência</span><span class="sxs-lookup"><span data-stu-id="99754-158">Transfer</span></span></td>
<td><span data-ttu-id="99754-159">Em andamento</span><span class="sxs-lookup"><span data-stu-id="99754-159">In progress</span></span></td>
<td><span data-ttu-id="99754-160">Sim</span><span class="sxs-lookup"><span data-stu-id="99754-160">Yes</span></span></td>
<td><span data-ttu-id="99754-161">Não</span><span class="sxs-lookup"><span data-stu-id="99754-161">No</span></span></td>
<td><span data-ttu-id="99754-162">Sim</span><span class="sxs-lookup"><span data-stu-id="99754-162">Yes</span></span></td>
<td><span data-ttu-id="99754-163">Sim</span><span class="sxs-lookup"><span data-stu-id="99754-163">Yes</span></span></td>
<td><span data-ttu-id="99754-164">Não</span><span class="sxs-lookup"><span data-stu-id="99754-164">No</span></span></td>
<td><span data-ttu-id="99754-165">Não</span><span class="sxs-lookup"><span data-stu-id="99754-165">No</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="99754-166">Transferência</span><span class="sxs-lookup"><span data-stu-id="99754-166">Transfer</span></span></td>
<td><span data-ttu-id="99754-167">Concluídas</span><span class="sxs-lookup"><span data-stu-id="99754-167">Completed</span></span></td>
<td><span data-ttu-id="99754-168">Não</span><span class="sxs-lookup"><span data-stu-id="99754-168">No</span></span></td>
<td><span data-ttu-id="99754-169">Não</span><span class="sxs-lookup"><span data-stu-id="99754-169">No</span></span></td>
<td><span data-ttu-id="99754-170">Não</span><span class="sxs-lookup"><span data-stu-id="99754-170">No</span></span></td>
<td><span data-ttu-id="99754-171">Não</span><span class="sxs-lookup"><span data-stu-id="99754-171">No</span></span></td>
<td><span data-ttu-id="99754-172">Sim</span><span class="sxs-lookup"><span data-stu-id="99754-172">Yes</span></span></td>
<td><span data-ttu-id="99754-173">Não</span><span class="sxs-lookup"><span data-stu-id="99754-173">No</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="99754-174">Transferência ou processo</span><span class="sxs-lookup"><span data-stu-id="99754-174">Transfer or process</span></span></td>
<td><span data-ttu-id="99754-175">Vazio</span><span class="sxs-lookup"><span data-stu-id="99754-175">Empty</span></span></td>
<td><span data-ttu-id="99754-176">Não</span><span class="sxs-lookup"><span data-stu-id="99754-176">No</span></span></td>
<td><span data-ttu-id="99754-177">Não</span><span class="sxs-lookup"><span data-stu-id="99754-177">No</span></span></td>
<td><span data-ttu-id="99754-178">Não</span><span class="sxs-lookup"><span data-stu-id="99754-178">No</span></span></td>
<td><span data-ttu-id="99754-179">Não</span><span class="sxs-lookup"><span data-stu-id="99754-179">No</span></span></td>
<td><span data-ttu-id="99754-180">Não</span><span class="sxs-lookup"><span data-stu-id="99754-180">No</span></span></td>
<td><span data-ttu-id="99754-181">Não</span><span class="sxs-lookup"><span data-stu-id="99754-181">No</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="99754-182">Transferência ou processo</span><span class="sxs-lookup"><span data-stu-id="99754-182">Transfer or process</span></span></td>
<td><span data-ttu-id="99754-183">Um cartão kanban não foi encontrado</span><span class="sxs-lookup"><span data-stu-id="99754-183">A kanban card is not found</span></span></td>
<td><span data-ttu-id="99754-184">Não</span><span class="sxs-lookup"><span data-stu-id="99754-184">No</span></span></td>
<td><span data-ttu-id="99754-185">Não</span><span class="sxs-lookup"><span data-stu-id="99754-185">No</span></span></td>
<td><span data-ttu-id="99754-186">Não</span><span class="sxs-lookup"><span data-stu-id="99754-186">No</span></span></td>
<td><span data-ttu-id="99754-187">Não</span><span class="sxs-lookup"><span data-stu-id="99754-187">No</span></span></td>
<td><span data-ttu-id="99754-188">Não</span><span class="sxs-lookup"><span data-stu-id="99754-188">No</span></span></td>
<td><span data-ttu-id="99754-189">Não</span><span class="sxs-lookup"><span data-stu-id="99754-189">No</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="99754-190">Transferência ou processo</span><span class="sxs-lookup"><span data-stu-id="99754-190">Transfer or process</span></span></td>
<td><span data-ttu-id="99754-191">Um cartão kanban foi encontrado, mas não foi atribuído a um kanban</span><span class="sxs-lookup"><span data-stu-id="99754-191">A kanban card is found, but it is not assigned to a kanban</span></span></td>
<td><span data-ttu-id="99754-192">Não</span><span class="sxs-lookup"><span data-stu-id="99754-192">No</span></span></td>
<td><span data-ttu-id="99754-193">Não</span><span class="sxs-lookup"><span data-stu-id="99754-193">No</span></span></td>
<td><span data-ttu-id="99754-194">Não</span><span class="sxs-lookup"><span data-stu-id="99754-194">No</span></span></td>
<td><span data-ttu-id="99754-195">Não</span><span class="sxs-lookup"><span data-stu-id="99754-195">No</span></span></td>
<td><span data-ttu-id="99754-196">Não</span><span class="sxs-lookup"><span data-stu-id="99754-196">No</span></span></td>
<td><span data-ttu-id="99754-197">Não</span><span class="sxs-lookup"><span data-stu-id="99754-197">No</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="99754-198">Processo</span><span class="sxs-lookup"><span data-stu-id="99754-198">Process</span></span></td>
<td><ul>
<li><span data-ttu-id="99754-199">Não planejados</span><span class="sxs-lookup"><span data-stu-id="99754-199">Not planned</span></span></li>
<li><span data-ttu-id="99754-200">Preparados</span><span class="sxs-lookup"><span data-stu-id="99754-200">Prepared</span></span></li>
<li><span data-ttu-id="99754-201">Em andamento</span><span class="sxs-lookup"><span data-stu-id="99754-201">In progress</span></span></li>
</ul></td>
<td><span data-ttu-id="99754-202">Não</span><span class="sxs-lookup"><span data-stu-id="99754-202">No</span></span></td>
<td><span data-ttu-id="99754-203">Não</span><span class="sxs-lookup"><span data-stu-id="99754-203">No</span></span></td>
<td><span data-ttu-id="99754-204">Não</span><span class="sxs-lookup"><span data-stu-id="99754-204">No</span></span></td>
<td><span data-ttu-id="99754-205">Não</span><span class="sxs-lookup"><span data-stu-id="99754-205">No</span></span></td>
<td><span data-ttu-id="99754-206">Não</span><span class="sxs-lookup"><span data-stu-id="99754-206">No</span></span></td>
<td><span data-ttu-id="99754-207">Não</span><span class="sxs-lookup"><span data-stu-id="99754-207">No</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="99754-208">Processo</span><span class="sxs-lookup"><span data-stu-id="99754-208">Process</span></span></td>
<td><span data-ttu-id="99754-209">Concluídas</span><span class="sxs-lookup"><span data-stu-id="99754-209">Completed</span></span></td>
<td><span data-ttu-id="99754-210">Não</span><span class="sxs-lookup"><span data-stu-id="99754-210">No</span></span></td>
<td><span data-ttu-id="99754-211">Não</span><span class="sxs-lookup"><span data-stu-id="99754-211">No</span></span></td>
<td><span data-ttu-id="99754-212">Não</span><span class="sxs-lookup"><span data-stu-id="99754-212">No</span></span></td>
<td><span data-ttu-id="99754-213">Não</span><span class="sxs-lookup"><span data-stu-id="99754-213">No</span></span></td>
<td><span data-ttu-id="99754-214">Não</span><span class="sxs-lookup"><span data-stu-id="99754-214">No</span></span></td>
<td><span data-ttu-id="99754-215">Não</span><span class="sxs-lookup"><span data-stu-id="99754-215">No</span></span></td>
</tr>
</tbody>
</table>






