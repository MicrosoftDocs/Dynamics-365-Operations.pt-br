---
title: Suporte do quadro de transferência kanban para os scanners de código de barras
description: O Quadro de transferência do kanban oferece suporte à entrada de scanner de um scanner de código de barras de widget para Selecionar, Iniciar, Concluir e Esvaziar um trabalho kanban.
author: ChristianRytt
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: KanbanBoardTransferJob
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19391
ms.assetid: a426f645-d59b-4c98-8d78-eba8d64a562e
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2a7073fb5d77e2d11569e86b92433864371f0e1d
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5825858"
---
# <a name="kanban-transfer-board-support-for-barcode-scanners"></a><span data-ttu-id="7bc41-103">Suporte do quadro de transferência kanban para os scanners de código de barras</span><span class="sxs-lookup"><span data-stu-id="7bc41-103">Kanban transfer board support for barcode scanners</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7bc41-104">O Quadro de transferência do kanban oferece suporte à entrada de scanner de um scanner de código de barras de widget para Selecionar, Iniciar, Concluir e Esvaziar um trabalho kanban.</span><span class="sxs-lookup"><span data-stu-id="7bc41-104">The Kanban transfer board supports scanner input from a widget barcode scanner to Select, Start, Complete, and Empty a kanban job.</span></span>

<a name="registration-modes"></a><span data-ttu-id="7bc41-105">Modos de registro</span><span class="sxs-lookup"><span data-stu-id="7bc41-105">Registration modes</span></span>
------------------

<span data-ttu-id="7bc41-106">Na Guia Rápida **Registro do scanner** você pode selecionar o modo do registro, que controla a ação quando você pesquisa um número de cartão kanban ou digita manualmente o número no campo Número do cartão kanban.</span><span class="sxs-lookup"><span data-stu-id="7bc41-106">On the **Scanner registration** FastTab you can select the registration mode, which controls the action when you scan a kanban card number or manually type the number in the Kanban card number field.</span></span>

| <span data-ttu-id="7bc41-107">Definir o modo de registro</span><span class="sxs-lookup"><span data-stu-id="7bc41-107">Set registration mode</span></span> | <span data-ttu-id="7bc41-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="7bc41-108">Description</span></span>                                                                                     |
|-----------------------|-------------------------------------------------------------------------------------------------|
| <span data-ttu-id="7bc41-109">Inicial</span><span class="sxs-lookup"><span data-stu-id="7bc41-109">Start</span></span>                 | <span data-ttu-id="7bc41-110">Registra um trabalho de transferência kanban como em andamento.</span><span class="sxs-lookup"><span data-stu-id="7bc41-110">Registers a Kanban transfer job as in progress.</span></span>                                                 |
| <span data-ttu-id="7bc41-111">Concluída</span><span class="sxs-lookup"><span data-stu-id="7bc41-111">Complete</span></span>              | <span data-ttu-id="7bc41-112">Registra um trabalho de transferência kanban como concluído.</span><span class="sxs-lookup"><span data-stu-id="7bc41-112">Registers a Kanban transfer job as completed.</span></span>                                                   |
| <span data-ttu-id="7bc41-113">Vazio</span><span class="sxs-lookup"><span data-stu-id="7bc41-113">Empty</span></span>                 | <span data-ttu-id="7bc41-114">Registra a unidade de manuseio de material referenciada por um cartão kanban como vazia.</span><span class="sxs-lookup"><span data-stu-id="7bc41-114">Registers the material handling unit that is referenced by a Kanban card as empty.</span></span>              |
| <span data-ttu-id="7bc41-115">Selecionar</span><span class="sxs-lookup"><span data-stu-id="7bc41-115">Select</span></span>                | <span data-ttu-id="7bc41-116">Registra um número de cartão kanban e seleciona automaticamente o trabalho referenciado na lista Kanban.</span><span class="sxs-lookup"><span data-stu-id="7bc41-116">Registers a Kanban card number and automatically selects the referenced job in the Kanban list.</span></span> |

 
<a name="registration-mode-select"></a><span data-ttu-id="7bc41-117">Seleção do Modo de registro</span><span class="sxs-lookup"><span data-stu-id="7bc41-117">Registration mode Select</span></span>
------------------------

<span data-ttu-id="7bc41-118">Quando você usa um leitor de código de barras para selecionar um trabalho, o modo de exibição do quadro kanban é alterado.</span><span class="sxs-lookup"><span data-stu-id="7bc41-118">When you use a bar code reader to select a job, the display mode of the kanban board changes.</span></span> <span data-ttu-id="7bc41-119">Nesse modo, as seguintes condições se aplicam:</span><span class="sxs-lookup"><span data-stu-id="7bc41-119">In this mode, the following conditions apply:</span></span>

-   <span data-ttu-id="7bc41-120">Somente o trabalho kanban verificado é exibido.</span><span class="sxs-lookup"><span data-stu-id="7bc41-120">Only the scanned kanban job is displayed.</span></span>
-   <span data-ttu-id="7bc41-121">Os detalhes do trabalho selecionado são exibidos na Guia Rápida **Detalhes**.</span><span class="sxs-lookup"><span data-stu-id="7bc41-121">The details of the selected job are displayed in the **Details** FastTab.</span></span>
-   <span data-ttu-id="7bc41-122">A Guia Rápida **Mensagens** exibe mensagens somente do trabalho selecionado.</span><span class="sxs-lookup"><span data-stu-id="7bc41-122">The **Messages** FastTab displays messages only for the selected job.</span></span>
-   <span data-ttu-id="7bc41-123">Você pode alterar o status do trabalho usando as funções disponíveis no Painel de Ações.</span><span class="sxs-lookup"><span data-stu-id="7bc41-123">You can change the status of the job by using the functions that are available on the Action Pane.</span></span> <span data-ttu-id="7bc41-124">O quadro de transferência kanban continuará a exibir somente um único trabalho durante esse tempo.</span><span class="sxs-lookup"><span data-stu-id="7bc41-124">The Kanban transfer board continues to display only a single job during this time.</span></span>
-   <span data-ttu-id="7bc41-125">Você pode atualizar as informações da lista de trabalhos manualmente, clicando em **Atualizar** (Shift+F5) no Painel de Ação.</span><span class="sxs-lookup"><span data-stu-id="7bc41-125">You can update the information in the list of jobs manually by clicking **Refresh** (Shift+F5) on the Action Pane.</span></span> <span data-ttu-id="7bc41-126">Depois de atualizar as informações, os resultados completos sobre o filtro de trabalho serão exibidos mais uma vez.</span><span class="sxs-lookup"><span data-stu-id="7bc41-126">After you refresh the information, the full results for the job filter are displayed again.</span></span>

## <a name="job-status-and-possible-actions"></a><span data-ttu-id="7bc41-127">Status do trabalho e ações possíveis</span><span class="sxs-lookup"><span data-stu-id="7bc41-127">Job status and possible actions</span></span>
<span data-ttu-id="7bc41-128">O status do trabalho selecionado e o status de todos os trabalhos vinculados para kanbans de eventos, determinam se você pode processar o trabalho ainda mais.</span><span class="sxs-lookup"><span data-stu-id="7bc41-128">The status of the selected job and the status of any pegged jobs for event kanbans, determine whether you can process the job further.</span></span> <span data-ttu-id="7bc41-129">A tabela a seguir exibe informações sobre esses status e tarefas:</span><span class="sxs-lookup"><span data-stu-id="7bc41-129">The following table displays information about these statuses and tasks:</span></span>
-   <span data-ttu-id="7bc41-130">Os status disponíveis para trabalhos, ou para as unidades de manuseio de material referenciadas pelos trabalhos.</span><span class="sxs-lookup"><span data-stu-id="7bc41-130">The statuses that are available for jobs, or for the handling units that are referenced by the jobs.</span></span>
-   <span data-ttu-id="7bc41-131">Cada tarefa que você pode executar para o trabalho.</span><span class="sxs-lookup"><span data-stu-id="7bc41-131">Each task that you can perform for the job.</span></span>

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
<th><span data-ttu-id="7bc41-132">Tipo de trabalho</span><span class="sxs-lookup"><span data-stu-id="7bc41-132">Job type</span></span></th>
<th><span data-ttu-id="7bc41-133">Status do trabalho ou status da unidade de manuseio de material</span><span class="sxs-lookup"><span data-stu-id="7bc41-133">Job status or handling unit status</span></span></th>
<th><span data-ttu-id="7bc41-134">Atualizar lista de separação</span><span class="sxs-lookup"><span data-stu-id="7bc41-134">Update picking list</span></span></th>
<th><span data-ttu-id="7bc41-135">Inicial</span><span class="sxs-lookup"><span data-stu-id="7bc41-135">Start</span></span></th>
<th><span data-ttu-id="7bc41-136">Atualizar registro</span><span class="sxs-lookup"><span data-stu-id="7bc41-136">Update registration</span></span></th>
<th><span data-ttu-id="7bc41-137">Concluída</span><span class="sxs-lookup"><span data-stu-id="7bc41-137">Complete</span></span></th>
<th><span data-ttu-id="7bc41-138">Vazio</span><span class="sxs-lookup"><span data-stu-id="7bc41-138">Empty</span></span></th>
<th><span data-ttu-id="7bc41-139">Criar kanbans de evento</span><span class="sxs-lookup"><span data-stu-id="7bc41-139">Create event kanbans</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="7bc41-140">Transferência</span><span class="sxs-lookup"><span data-stu-id="7bc41-140">Transfer</span></span></td>
<td><ul>
<li><span data-ttu-id="7bc41-141">Não planejados</span><span class="sxs-lookup"><span data-stu-id="7bc41-141">Not planned</span></span></li>
<li><span data-ttu-id="7bc41-142">Nenhum trabalho vinculado ou os trabalhos vinculados estão Concluídos</span><span class="sxs-lookup"><span data-stu-id="7bc41-142">No pegged jobs, or pegged jobs are Completed</span></span></li>
</ul></td>
<td><span data-ttu-id="7bc41-143">Sim</span><span class="sxs-lookup"><span data-stu-id="7bc41-143">Yes</span></span></td>
<td><span data-ttu-id="7bc41-144">Sim</span><span class="sxs-lookup"><span data-stu-id="7bc41-144">Yes</span></span></td>
<td><span data-ttu-id="7bc41-145">Sim</span><span class="sxs-lookup"><span data-stu-id="7bc41-145">Yes</span></span></td>
<td><span data-ttu-id="7bc41-146">Sim</span><span class="sxs-lookup"><span data-stu-id="7bc41-146">Yes</span></span></td>
<td><span data-ttu-id="7bc41-147">Não</span><span class="sxs-lookup"><span data-stu-id="7bc41-147">No</span></span></td>
<td><span data-ttu-id="7bc41-148">Sim</span><span class="sxs-lookup"><span data-stu-id="7bc41-148">Yes</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="7bc41-149">Transferência</span><span class="sxs-lookup"><span data-stu-id="7bc41-149">Transfer</span></span></td>
<td><ul>
<li><span data-ttu-id="7bc41-150">Não planejados</span><span class="sxs-lookup"><span data-stu-id="7bc41-150">Not planned</span></span></li>
<li><span data-ttu-id="7bc41-151">O trabalho vinculado não está Concluído</span><span class="sxs-lookup"><span data-stu-id="7bc41-151">The pegged job is not Completed</span></span></li>
</ul></td>
<td><span data-ttu-id="7bc41-152">Sim</span><span class="sxs-lookup"><span data-stu-id="7bc41-152">Yes</span></span></td>
<td><span data-ttu-id="7bc41-153">Não</span><span class="sxs-lookup"><span data-stu-id="7bc41-153">No</span></span></td>
<td><span data-ttu-id="7bc41-154">Sim</span><span class="sxs-lookup"><span data-stu-id="7bc41-154">Yes</span></span></td>
<td><span data-ttu-id="7bc41-155">Não</span><span class="sxs-lookup"><span data-stu-id="7bc41-155">No</span></span></td>
<td><span data-ttu-id="7bc41-156">Não</span><span class="sxs-lookup"><span data-stu-id="7bc41-156">No</span></span></td>
<td><span data-ttu-id="7bc41-157">Não</span><span class="sxs-lookup"><span data-stu-id="7bc41-157">No</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="7bc41-158">Transferência</span><span class="sxs-lookup"><span data-stu-id="7bc41-158">Transfer</span></span></td>
<td><span data-ttu-id="7bc41-159">Em andamento</span><span class="sxs-lookup"><span data-stu-id="7bc41-159">In progress</span></span></td>
<td><span data-ttu-id="7bc41-160">Sim</span><span class="sxs-lookup"><span data-stu-id="7bc41-160">Yes</span></span></td>
<td><span data-ttu-id="7bc41-161">Não</span><span class="sxs-lookup"><span data-stu-id="7bc41-161">No</span></span></td>
<td><span data-ttu-id="7bc41-162">Sim</span><span class="sxs-lookup"><span data-stu-id="7bc41-162">Yes</span></span></td>
<td><span data-ttu-id="7bc41-163">Sim</span><span class="sxs-lookup"><span data-stu-id="7bc41-163">Yes</span></span></td>
<td><span data-ttu-id="7bc41-164">Não</span><span class="sxs-lookup"><span data-stu-id="7bc41-164">No</span></span></td>
<td><span data-ttu-id="7bc41-165">Não</span><span class="sxs-lookup"><span data-stu-id="7bc41-165">No</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="7bc41-166">Transferência</span><span class="sxs-lookup"><span data-stu-id="7bc41-166">Transfer</span></span></td>
<td><span data-ttu-id="7bc41-167">Concluídas</span><span class="sxs-lookup"><span data-stu-id="7bc41-167">Completed</span></span></td>
<td><span data-ttu-id="7bc41-168">Não</span><span class="sxs-lookup"><span data-stu-id="7bc41-168">No</span></span></td>
<td><span data-ttu-id="7bc41-169">Não</span><span class="sxs-lookup"><span data-stu-id="7bc41-169">No</span></span></td>
<td><span data-ttu-id="7bc41-170">Não</span><span class="sxs-lookup"><span data-stu-id="7bc41-170">No</span></span></td>
<td><span data-ttu-id="7bc41-171">Não</span><span class="sxs-lookup"><span data-stu-id="7bc41-171">No</span></span></td>
<td><span data-ttu-id="7bc41-172">Sim</span><span class="sxs-lookup"><span data-stu-id="7bc41-172">Yes</span></span></td>
<td><span data-ttu-id="7bc41-173">Não</span><span class="sxs-lookup"><span data-stu-id="7bc41-173">No</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="7bc41-174">Transferência ou processo</span><span class="sxs-lookup"><span data-stu-id="7bc41-174">Transfer or process</span></span></td>
<td><span data-ttu-id="7bc41-175">Vazio</span><span class="sxs-lookup"><span data-stu-id="7bc41-175">Empty</span></span></td>
<td><span data-ttu-id="7bc41-176">Não</span><span class="sxs-lookup"><span data-stu-id="7bc41-176">No</span></span></td>
<td><span data-ttu-id="7bc41-177">Não</span><span class="sxs-lookup"><span data-stu-id="7bc41-177">No</span></span></td>
<td><span data-ttu-id="7bc41-178">Não</span><span class="sxs-lookup"><span data-stu-id="7bc41-178">No</span></span></td>
<td><span data-ttu-id="7bc41-179">Não</span><span class="sxs-lookup"><span data-stu-id="7bc41-179">No</span></span></td>
<td><span data-ttu-id="7bc41-180">Não</span><span class="sxs-lookup"><span data-stu-id="7bc41-180">No</span></span></td>
<td><span data-ttu-id="7bc41-181">Não</span><span class="sxs-lookup"><span data-stu-id="7bc41-181">No</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="7bc41-182">Transferência ou processo</span><span class="sxs-lookup"><span data-stu-id="7bc41-182">Transfer or process</span></span></td>
<td><span data-ttu-id="7bc41-183">Um cartão kanban não foi encontrado</span><span class="sxs-lookup"><span data-stu-id="7bc41-183">A kanban card is not found</span></span></td>
<td><span data-ttu-id="7bc41-184">Não</span><span class="sxs-lookup"><span data-stu-id="7bc41-184">No</span></span></td>
<td><span data-ttu-id="7bc41-185">Não</span><span class="sxs-lookup"><span data-stu-id="7bc41-185">No</span></span></td>
<td><span data-ttu-id="7bc41-186">Não</span><span class="sxs-lookup"><span data-stu-id="7bc41-186">No</span></span></td>
<td><span data-ttu-id="7bc41-187">Não</span><span class="sxs-lookup"><span data-stu-id="7bc41-187">No</span></span></td>
<td><span data-ttu-id="7bc41-188">Não</span><span class="sxs-lookup"><span data-stu-id="7bc41-188">No</span></span></td>
<td><span data-ttu-id="7bc41-189">Não</span><span class="sxs-lookup"><span data-stu-id="7bc41-189">No</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="7bc41-190">Transferência ou processo</span><span class="sxs-lookup"><span data-stu-id="7bc41-190">Transfer or process</span></span></td>
<td><span data-ttu-id="7bc41-191">Um cartão kanban foi encontrado, mas não foi atribuído a um kanban</span><span class="sxs-lookup"><span data-stu-id="7bc41-191">A kanban card is found, but it is not assigned to a kanban</span></span></td>
<td><span data-ttu-id="7bc41-192">Não</span><span class="sxs-lookup"><span data-stu-id="7bc41-192">No</span></span></td>
<td><span data-ttu-id="7bc41-193">Não</span><span class="sxs-lookup"><span data-stu-id="7bc41-193">No</span></span></td>
<td><span data-ttu-id="7bc41-194">Não</span><span class="sxs-lookup"><span data-stu-id="7bc41-194">No</span></span></td>
<td><span data-ttu-id="7bc41-195">Não</span><span class="sxs-lookup"><span data-stu-id="7bc41-195">No</span></span></td>
<td><span data-ttu-id="7bc41-196">Não</span><span class="sxs-lookup"><span data-stu-id="7bc41-196">No</span></span></td>
<td><span data-ttu-id="7bc41-197">Não</span><span class="sxs-lookup"><span data-stu-id="7bc41-197">No</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="7bc41-198">Processo</span><span class="sxs-lookup"><span data-stu-id="7bc41-198">Process</span></span></td>
<td><ul>
<li><span data-ttu-id="7bc41-199">Não planejados</span><span class="sxs-lookup"><span data-stu-id="7bc41-199">Not planned</span></span></li>
<li><span data-ttu-id="7bc41-200">Preparados</span><span class="sxs-lookup"><span data-stu-id="7bc41-200">Prepared</span></span></li>
<li><span data-ttu-id="7bc41-201">Em andamento</span><span class="sxs-lookup"><span data-stu-id="7bc41-201">In progress</span></span></li>
</ul></td>
<td><span data-ttu-id="7bc41-202">Não</span><span class="sxs-lookup"><span data-stu-id="7bc41-202">No</span></span></td>
<td><span data-ttu-id="7bc41-203">Não</span><span class="sxs-lookup"><span data-stu-id="7bc41-203">No</span></span></td>
<td><span data-ttu-id="7bc41-204">Não</span><span class="sxs-lookup"><span data-stu-id="7bc41-204">No</span></span></td>
<td><span data-ttu-id="7bc41-205">Não</span><span class="sxs-lookup"><span data-stu-id="7bc41-205">No</span></span></td>
<td><span data-ttu-id="7bc41-206">Não</span><span class="sxs-lookup"><span data-stu-id="7bc41-206">No</span></span></td>
<td><span data-ttu-id="7bc41-207">Não</span><span class="sxs-lookup"><span data-stu-id="7bc41-207">No</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="7bc41-208">Processo</span><span class="sxs-lookup"><span data-stu-id="7bc41-208">Process</span></span></td>
<td><span data-ttu-id="7bc41-209">Concluídas</span><span class="sxs-lookup"><span data-stu-id="7bc41-209">Completed</span></span></td>
<td><span data-ttu-id="7bc41-210">Não</span><span class="sxs-lookup"><span data-stu-id="7bc41-210">No</span></span></td>
<td><span data-ttu-id="7bc41-211">Não</span><span class="sxs-lookup"><span data-stu-id="7bc41-211">No</span></span></td>
<td><span data-ttu-id="7bc41-212">Não</span><span class="sxs-lookup"><span data-stu-id="7bc41-212">No</span></span></td>
<td><span data-ttu-id="7bc41-213">Não</span><span class="sxs-lookup"><span data-stu-id="7bc41-213">No</span></span></td>
<td><span data-ttu-id="7bc41-214">Não</span><span class="sxs-lookup"><span data-stu-id="7bc41-214">No</span></span></td>
<td><span data-ttu-id="7bc41-215">Não</span><span class="sxs-lookup"><span data-stu-id="7bc41-215">No</span></span></td>
</tr>
</tbody>
</table>







[!INCLUDE[footer-include](../../includes/footer-banner.md)]