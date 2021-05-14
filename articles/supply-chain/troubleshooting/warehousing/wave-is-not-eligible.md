---
title: O ciclo não está qualificado para limpeza
description: O ciclo não está qualificado para limpeza
author: perlynne
ms.date: 04/15/2021
ms.topic: troubleshooting
ms.search.form: WHSWaveTable_WHSWaveProcessingDataCleanup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-05-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 3e5142cf40a6c0d308e8e952bbe17e85b498826d
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924318"
---
# <a name="wave-isnt-eligible-for-cleanup"></a><span data-ttu-id="8543f-103">O ciclo não está qualificado para limpeza</span><span class="sxs-lookup"><span data-stu-id="8543f-103">Wave isn't eligible for cleanup</span></span>

<span data-ttu-id="8543f-104">Código de erro: WaveNotEligibleForCleanup</span><span class="sxs-lookup"><span data-stu-id="8543f-104">Error code: WaveNotEligibleForCleanup</span></span>

## <a name="symptoms"></a><span data-ttu-id="8543f-105">Sintomas</span><span class="sxs-lookup"><span data-stu-id="8543f-105">Symptoms</span></span>

<span data-ttu-id="8543f-106">O sistema mostra a seguinte mensagem de erro:</span><span class="sxs-lookup"><span data-stu-id="8543f-106">The system shows the following error message:</span></span>

> <span data-ttu-id="8543f-107">A onda %1 não está inteligível para a limpeza.</span><span class="sxs-lookup"><span data-stu-id="8543f-107">Wave %1 is not eligible for cleanup.</span></span>

<span data-ttu-id="8543f-108">Os dados do ciclo não podem ser limpos.</span><span class="sxs-lookup"><span data-stu-id="8543f-108">The wave data can't be cleaned up.</span></span>  

## <a name="cause"></a><span data-ttu-id="8543f-109">Causa</span><span class="sxs-lookup"><span data-stu-id="8543f-109">Cause</span></span>

<span data-ttu-id="8543f-110">No momento, o ciclo está sendo processado, como indicado por uma das seguintes condições:</span><span class="sxs-lookup"><span data-stu-id="8543f-110">The wave is currently being processed, as indicated by one of the following conditions:</span></span>

- <span data-ttu-id="8543f-111">O campo **Status do ciclo** está definido como *Executando*.</span><span class="sxs-lookup"><span data-stu-id="8543f-111">The **Wave status** field is set to *Executing*.</span></span>
- <span data-ttu-id="8543f-112">Ao selecionar **Trabalho em lotes** no grupo **Ciclo**, na guia **Ciclo** do Painel de Ações, o campo **Status** não é definido como *Concluído*, *Erro* ou *Cancelado*.</span><span class="sxs-lookup"><span data-stu-id="8543f-112">When you select **Batch job** in the **Wave** group on the **Wave** tab of the Action Pane, the **Status** field isn't set to *Ended*, *Error*, or *Canceled*.</span></span> <span data-ttu-id="8543f-113">Portanto, um trabalho em lotes está em execução no momento.</span><span class="sxs-lookup"><span data-stu-id="8543f-113">Therefore, a batch job is currently running.</span></span>

## <a name="resolution"></a><span data-ttu-id="8543f-114">Resolução</span><span class="sxs-lookup"><span data-stu-id="8543f-114">Resolution</span></span>

<span data-ttu-id="8543f-115">No Painel de Ações, na guia **Ciclo**, no grupo **Ciclo**, selecione **Trabalho em lotes** e siga uma destas etapas:</span><span class="sxs-lookup"><span data-stu-id="8543f-115">On the Action Pane, on the **Wave** tab, in the **Wave** group, select **Batch job**, and then follow one of these steps:</span></span>

- <span data-ttu-id="8543f-116">Se o campo **Status** estiver definido como *Executando*: no Painel de Ações, na guia **Trabalho em lotes**, no grupo **Trabalho em lotes**, selecione **Exibir tarefas**.</span><span class="sxs-lookup"><span data-stu-id="8543f-116">If the **Status** field is set to *Executing*: On the Action Pane, on the **Batch job** tab, in the **Batch job** group, select **View tasks**.</span></span> <span data-ttu-id="8543f-117">Você pode acompanhar o progresso atualizando a página **Tarefas em lote**.</span><span class="sxs-lookup"><span data-stu-id="8543f-117">You can follow the progress by refreshing the **Batch tasks** page.</span></span>
- <span data-ttu-id="8543f-118">Se o campo **Status** não estiver definido como *Executando*: no Painel de Ações, na guia **Trabalho em lotes**, no grupo **Funções**, selecione **Alterar status**.</span><span class="sxs-lookup"><span data-stu-id="8543f-118">If the **Status** field isn't set to *Executing*: On the Action Pane, on the **Batch job** tab, in the **Functions** group, select **Change status**.</span></span> <span data-ttu-id="8543f-119">No campo **Selecionar novo status**, selecione *Aguardando*.</span><span class="sxs-lookup"><span data-stu-id="8543f-119">In the **Select new status** field, select *Waiting*.</span></span> <span data-ttu-id="8543f-120">Em seguida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="8543f-120">Then select **OK**.</span></span>
