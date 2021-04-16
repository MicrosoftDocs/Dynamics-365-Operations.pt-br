---
title: Otimizar o desempenho agendando trabalhos em lotes após o expediente
description: Este tópico explica como resolver problemas de desempenho com o Microsoft Dynamics 365 Human Resources agendando para depois do expediente os trabalhos em lotes de execução demorada.
author: andreabichsel
ms.date: 06/23/2020
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
ms.search.validFrom: 2020-06-23
ms.dyn365.ops.version: Platform update 24
ms.openlocfilehash: 92dd281ed718be5c7ebd843d015c108ee121f30a
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5794916"
---
# <a name="optimize-performance-by-scheduling-batch-jobs-after-hours"></a><span data-ttu-id="ad171-103">Otimizar o desempenho agendando trabalhos em lotes após o expediente</span><span class="sxs-lookup"><span data-stu-id="ad171-103">Optimize performance by scheduling batch jobs after hours</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

## <a name="issue"></a><span data-ttu-id="ad171-104">Emitir</span><span class="sxs-lookup"><span data-stu-id="ad171-104">Issue</span></span>

<span data-ttu-id="ad171-105">O Microsoft Dynamics 365 Human Resources poderá ter problemas de desempenho se os trabalhos em lotes demorados forem executados no horário comercial normal.</span><span class="sxs-lookup"><span data-stu-id="ad171-105">Microsoft Dynamics 365 Human Resources can experience performance issues if long-running batch jobs run during typical business hours.</span></span>

## <a name="resolution"></a><span data-ttu-id="ad171-106">Resolução</span><span class="sxs-lookup"><span data-stu-id="ad171-106">Resolution</span></span>

<span data-ttu-id="ad171-107">Agende os trabalhos em lotes a seguir fora do horário comercial.</span><span class="sxs-lookup"><span data-stu-id="ad171-107">Schedule the following batch jobs during off hours.</span></span> <span data-ttu-id="ad171-108">Também é recomendável rever a frequência de trabalhos em lotes executados habitualmente.</span><span class="sxs-lookup"><span data-stu-id="ad171-108">We also recommend reviewing the frequency of batch jobs that run frequently.</span></span> <span data-ttu-id="ad171-109">Se possível, reduza a recorrência do trabalho em lotes.</span><span class="sxs-lookup"><span data-stu-id="ad171-109">If possible, reduce the recurrence of the batch job.</span></span> <span data-ttu-id="ad171-110">Em muitos casos, a frequência padrão é suficiente.</span><span class="sxs-lookup"><span data-stu-id="ad171-110">In many cases, the default frequency is sufficient.</span></span>

<span data-ttu-id="ad171-111">Os trabalhos em lotes a seguir devem ser executados à noite ou depois do expediente.</span><span class="sxs-lookup"><span data-stu-id="ad171-111">The following batch jobs should run at night or after hours.</span></span> <span data-ttu-id="ad171-112">Verifique o fuso horário desses trabalhos em lotes recorrentes.</span><span class="sxs-lookup"><span data-stu-id="ad171-112">Be sure to check the time zone for these recurring batch jobs.</span></span> <span data-ttu-id="ad171-113">Alguns trabalhos em lotes podem usar o Horário Padrão do Pacífico (PST).</span><span class="sxs-lookup"><span data-stu-id="ad171-113">Some batch jobs might use Pacific Standard Time (PST).</span></span>

| <span data-ttu-id="ad171-114">Trabalho em Lotes</span><span class="sxs-lookup"><span data-stu-id="ad171-114">Batch job</span></span> | <span data-ttu-id="ad171-115">Ocorrência padrão</span><span class="sxs-lookup"><span data-stu-id="ad171-115">Default occurrence</span></span> |
| --- | --- |
| <span data-ttu-id="ad171-116">Limpeza do histórico de trabalhos em lotes</span><span class="sxs-lookup"><span data-stu-id="ad171-116">Batch job history cleanup</span></span> | <span data-ttu-id="ad171-117">1 vez por mês</span><span class="sxs-lookup"><span data-stu-id="ad171-117">1 time per month</span></span> |
| <span data-ttu-id="ad171-118">Limpeza de preparo de exportação</span><span class="sxs-lookup"><span data-stu-id="ad171-118">Export staging cleanup</span></span> | <span data-ttu-id="ad171-119">1 vez por dia</span><span class="sxs-lookup"><span data-stu-id="ad171-119">1 time per day</span></span> |
| <span data-ttu-id="ad171-120">Sincronização de solicitação perdida da integração do Common Data Service</span><span class="sxs-lookup"><span data-stu-id="ad171-120">Common Data Service integration missed request sync</span></span> | <span data-ttu-id="ad171-121">1 vez por dia</span><span class="sxs-lookup"><span data-stu-id="ad171-121">1 time per day</span></span> |
| <span data-ttu-id="ad171-122">Trabalho do sistema de compactação de banco de dados que precisa ser executado regularmente fora do horário comercial</span><span class="sxs-lookup"><span data-stu-id="ad171-122">Database compression system job that needs to run regularly during off hours</span></span> | <span data-ttu-id="ad171-123">1 vez por dia</span><span class="sxs-lookup"><span data-stu-id="ad171-123">1 time per day</span></span> |
| <span data-ttu-id="ad171-124">Trabalho do sistema de recriação de índice de banco de dados que precisa ser executado regularmente fora do horário comercial</span><span class="sxs-lookup"><span data-stu-id="ad171-124">Database index rebuild system job that needs to run regularly during off hours</span></span> | <span data-ttu-id="ad171-125">1 vez por dia</span><span class="sxs-lookup"><span data-stu-id="ad171-125">1 time per day</span></span> |

1. <span data-ttu-id="ad171-126">No Human Resources, selecione **Administração do sistema**.</span><span class="sxs-lookup"><span data-stu-id="ad171-126">In Human Resources, select **System administration**.</span></span>

2. <span data-ttu-id="ad171-127">Na barra **Pesquisa**, procure um dos trabalhos em lotes acima.</span><span class="sxs-lookup"><span data-stu-id="ad171-127">In the **Search** bar, search for one of the above batch jobs.</span></span>

3. <span data-ttu-id="ad171-128">Selecione **Executar em segundo plano** e, depois, **Recorrência**.</span><span class="sxs-lookup"><span data-stu-id="ad171-128">Select **Run in the background**, and then select **Recurrence**.</span></span>

   ![Definir a recorrência](media/talent-batch-history-cleanup-recurrence.png)

4. <span data-ttu-id="ad171-130">Em **Definir a recorrência**, defina a **Data inicial** e a **Hora inicial** para ocorrer fora do horário comercial ou no final de semana.</span><span class="sxs-lookup"><span data-stu-id="ad171-130">Under **Define recurrence**, set the **Start date** and **Start time** to occur during off hours or the weekend.</span></span> <span data-ttu-id="ad171-131">Selecione **Sem data de término**.</span><span class="sxs-lookup"><span data-stu-id="ad171-131">Select **No end date**.</span></span> 

   ![Definir a data e a hora de início da recorrência](media/talent-batch-history-cleanup-define-recurrence.png)

5. <span data-ttu-id="ad171-133">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="ad171-133">Select **OK**.</span></span>

6. <span data-ttu-id="ad171-134">Se necessário, altere quaisquer outros parâmetros em **Executar em segundo plano** e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="ad171-134">If needed, change any other parameters under **Run in the background**, and then select **OK**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ad171-135">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="ad171-135">Additional resources</span></span>

[<span data-ttu-id="ad171-136">Otimizar o desempenho com tarefas de limpeza automática</span><span class="sxs-lookup"><span data-stu-id="ad171-136">Optimize performance with auto cleanup tasks</span></span>](hr-admin-troubleshooting-batch-history.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]