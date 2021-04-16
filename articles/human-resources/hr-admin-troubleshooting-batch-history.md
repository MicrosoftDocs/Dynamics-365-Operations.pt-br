---
title: Otimizar o desempenho com tarefas de limpeza automática
description: Este artigo explica como resolver alguns problemas de desempenho com o Microsoft Dynamics 365 Human Resources limpando o histórico de trabalhos em lotes.
author: andreabichsel
ms.date: 02/03/2020
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
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Platform update 24
ms.openlocfilehash: 0372833c11e0919fa03d57ea258e81a89ab9ff31
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5803936"
---
# <a name="optimize-performance-with-auto-cleanup-tasks"></a><span data-ttu-id="4c5fa-103">Otimizar o desempenho com tarefas automáticas de limpeza</span><span class="sxs-lookup"><span data-stu-id="4c5fa-103">Optimize performance with auto cleanup tasks</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="4c5fa-104">**Emissão**</span><span class="sxs-lookup"><span data-stu-id="4c5fa-104">**Issue**</span></span>

<span data-ttu-id="4c5fa-105">O Microsoft Dynamics 365 Human Resources pode apresentar problemas de desempenho se o histórico de trabalhos em lotes se tornar muito grande.</span><span class="sxs-lookup"><span data-stu-id="4c5fa-105">Microsoft Dynamics 365 Human Resources can experience performance issues if the batch job history grows too large.</span></span>

<span data-ttu-id="4c5fa-106">**Causa**</span><span class="sxs-lookup"><span data-stu-id="4c5fa-106">**Cause**</span></span>

<span data-ttu-id="4c5fa-107">Os trabalhos em lote que são executados com frequência geralmente podem levar ao crescimento insustentável do histórico de trabalhos em lotes.</span><span class="sxs-lookup"><span data-stu-id="4c5fa-107">Batch jobs that run frequently can lead to unsustainable growth of the batch job history.</span></span> <span data-ttu-id="4c5fa-108">Isso pode causar problemas de desempenho.</span><span class="sxs-lookup"><span data-stu-id="4c5fa-108">This can cause performance issues.</span></span> 

<span data-ttu-id="4c5fa-109">**Resolução**</span><span class="sxs-lookup"><span data-stu-id="4c5fa-109">**Resolution**</span></span>

<span data-ttu-id="4c5fa-110">Agende uma tarefa automática limpar o histórico de trabalhos em lotes.</span><span class="sxs-lookup"><span data-stu-id="4c5fa-110">Schedule an automatic task to clean up your batch job history.</span></span> <span data-ttu-id="4c5fa-111">Recomendamos configurar a tarefa para ser executada semanalmente, mas pode ser necessário executar a limpeza com mais ou menos frequência, dependendo do seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="4c5fa-111">We recommend setting up the task to run weekly, but you might need to run the cleanup more or less frequently, depending on your environment.</span></span> <span data-ttu-id="4c5fa-112">O procedimento a seguir contém nossas configurações recomendadas, mas você pode modificá-las de acordo com suas necessidades.</span><span class="sxs-lookup"><span data-stu-id="4c5fa-112">The following procedure contains our recommended settings, but you can change these according to your needs.</span></span>

1. <span data-ttu-id="4c5fa-113">No Human Resources, selecione **Administração do sistema**.</span><span class="sxs-lookup"><span data-stu-id="4c5fa-113">In Human Resources, select **System administration**.</span></span>

2. <span data-ttu-id="4c5fa-114">Na barra **Pesquisa** , insira **Limpeza de histórico de trabalhos em lote**.</span><span class="sxs-lookup"><span data-stu-id="4c5fa-114">In the **Search** bar, enter **Batch job history clean-up**.</span></span>

   ![Pesquisar limpeza de histórico de trabalhos em lotes](media/talent-batch-history-cleanup-search-bar.png)

3. <span data-ttu-id="4c5fa-116">No **Limite de histórico (dias)**, insira **30**.</span><span class="sxs-lookup"><span data-stu-id="4c5fa-116">In **History limit (days)**, enter **30**.</span></span>

   ![Defina o limite de histórico como 30](media/talent-batch-history-cleanup-history-limit.png)

4. <span data-ttu-id="4c5fa-118">Selecione **Executar em segundo plano** e **Recorrência**.</span><span class="sxs-lookup"><span data-stu-id="4c5fa-118">Select **Run in the background** and then select **Recurrence**.</span></span>

   ![Definir a recorrência](media/talent-batch-history-cleanup-recurrence.png)

5. <span data-ttu-id="4c5fa-120">Em **Definir a recorrência**, defina a **Data inicial** e a **Hora inicial** para ocorrer fora do horário comercial ou no final de semana e selecione **NENHUMA DATA DE TÉRMINO**.</span><span class="sxs-lookup"><span data-stu-id="4c5fa-120">Under **Define recurrence**, set the **Start date** and **Start time** to occur during off-hours or the weekend, and then select **NO END DATE**.</span></span> 

   ![Definir a data e a hora de início da recorrência](media/talent-batch-history-cleanup-define-recurrence.png)

6. <span data-ttu-id="4c5fa-122">Em **PADRÃO DE RECORRÊNCIA**, selecione **Dias** e **REPETIR APÓS O INTERVALO ESPECIFICADO** como **7**.</span><span class="sxs-lookup"><span data-stu-id="4c5fa-122">Under **RECURRENCE PATTERN**, select **Days** and set **REPEAT AFTER SPECIFIED INTERVAL** to **7**.</span></span>

   ![Definir limpeza para ser repetida semanalmente](media/talent-batch-history-cleanup-recurrence-pattern.png)

7. <span data-ttu-id="4c5fa-124">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="4c5fa-124">Select **OK**.</span></span>

8. <span data-ttu-id="4c5fa-125">Altere quaisquer outros parâmetros em **Executar em segundo plano** conforme necessário e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="4c5fa-125">Change any other parameters under **Run in the background** as necessary, and then select **OK**.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]