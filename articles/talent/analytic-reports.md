---
title: Usar relatórios analíticos no Attract
description: Este tópico descreve os relatórios analíticos para insights do processo de contratação no Microsoft Dynamics 365 Talent - Attract
author: fewatson
manager: AnnBe
ms.date: 04/30/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: fewatson
ms.search.validFrom: 2019-04-30
ms.dyn365.ops.version: Talent April 2019 update
ms.openlocfilehash: 081988e8b8cfe1e2ddb533247b678ba38a07f5f1
ms.sourcegitcommit: f38302b9430f2ab3efe91d0a7beff946bc610e8f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/28/2020
ms.locfileid: "3092214"
---
# <a name="use-analytic-reports-in-attract"></a><span data-ttu-id="b0701-103">Usar relatórios analíticos no Attract</span><span class="sxs-lookup"><span data-stu-id="b0701-103">Use analytic reports in Attract</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="b0701-104">Os relatórios analíticos no Microsoft Dynamics 365 Talent: Attract fornecem uma solução pronta para uso (OOTB) para insights do processo de contratação.</span><span class="sxs-lookup"><span data-stu-id="b0701-104">Analytic reports in Microsoft Dynamics 365 Talent: Attract provide an out-of-the-box (OOTB) solution for hiring process insights.</span></span> <span data-ttu-id="b0701-105">Os recursos disponíveis incluem:</span><span class="sxs-lookup"><span data-stu-id="b0701-105">Availabe features include:</span></span>

- <span data-ttu-id="b0701-106">**Análise de trabalho:** clique na guia **Análise** dentro de um trabalho para métricas sobre os candidatos do trabalho.</span><span class="sxs-lookup"><span data-stu-id="b0701-106">**Job analytics:** Click the **Analytics** tab within a job for metrics on the job's applicants.</span></span>
- <span data-ttu-id="b0701-107">**Hub de análise:** clique em **Análise** na navegação à esquerda, para métricas agregadas nas tarefas.</span><span class="sxs-lookup"><span data-stu-id="b0701-107">**Analytics hub:** Click **Analytics** on the left navigation for aggregated metrics across jobs.</span></span>
- <span data-ttu-id="b0701-108">**Segurança específica do usuário**: o acesso a relatórios é controlado pela [função](security-attract.md) do Attract e a função de participante do trabalho.</span><span class="sxs-lookup"><span data-stu-id="b0701-108">**User-specific security:** Access to reports is controlled by Attract [role](security-attract.md) and job participant role.</span></span>
- <span data-ttu-id="b0701-109">**Filtragem cruzada:** clique nos elementos visuais em um relatório para visualizar outras métricas filtradas pelos dados selecionados.</span><span class="sxs-lookup"><span data-stu-id="b0701-109">**Cross-filtering:** Click visuals within a report to view other metrics filtered by selected data.</span></span>

>[!NOTE] 
>- <span data-ttu-id="b0701-110">Este recurso está atualmente em [visualização](access-preview-feature.md).</span><span class="sxs-lookup"><span data-stu-id="b0701-110">This feature is currently in [preview](access-preview-feature.md).</span></span> <span data-ttu-id="b0701-111">Para experimentá-lo, você deve ter o [**Complemento de Contratação Abrangente**](attract-comprehensive-hiring.md).</span><span class="sxs-lookup"><span data-stu-id="b0701-111">To try it, you must have the [**Comprehensive Hiring Add-On**](attract-comprehensive-hiring.md).</span></span>
>- <span data-ttu-id="b0701-112">Todos os relatórios públicos de visualização são exibidos em inglês.</span><span class="sxs-lookup"><span data-stu-id="b0701-112">All public preview reports are displayed in English.</span></span>
>- <span data-ttu-id="b0701-113">Relatórios são atualizados a cada 3 horas.</span><span class="sxs-lookup"><span data-stu-id="b0701-113">Reports refresh every 3 hours.</span></span> <span data-ttu-id="b0701-114">A hora da última atualização (no fuso horário local) está localizada na parte superior do relatório.</span><span class="sxs-lookup"><span data-stu-id="b0701-114">The last refresh time (in the local timezone) is located at the top of the report.</span></span> <span data-ttu-id="b0701-115">As horas de atualização são uma aproximação e variam com base no volume de dados e na carga de recursos na sua região.</span><span class="sxs-lookup"><span data-stu-id="b0701-115">Refresh times are an approximation and vary based on data volume and resource load in your region.</span></span>

## <a name="job-analytics"></a><span data-ttu-id="b0701-116">Análise de Trabalho</span><span class="sxs-lookup"><span data-stu-id="b0701-116">Job Analytics</span></span>

<span data-ttu-id="b0701-117">Os relatórios Análise de trabalho são um snapshot do processo de contratação de um trabalho.</span><span class="sxs-lookup"><span data-stu-id="b0701-117">Job Analytics reports are a snapshot of the hiring process for a job.</span></span>  <span data-ttu-id="b0701-118">Principais métricas incluem:</span><span class="sxs-lookup"><span data-stu-id="b0701-118">Key metrics include:</span></span>

- <span data-ttu-id="b0701-119">Candidatos ativos por estágio</span><span class="sxs-lookup"><span data-stu-id="b0701-119">Active applicants by stage</span></span>
- <span data-ttu-id="b0701-120">Origem do candidato</span><span class="sxs-lookup"><span data-stu-id="b0701-120">Applicant source</span></span>
- <span data-ttu-id="b0701-121">Tipo do candidato (interna ou externa)</span><span class="sxs-lookup"><span data-stu-id="b0701-121">Applicant type (internal or external)</span></span>

## <a name="analytics-hub"></a><span data-ttu-id="b0701-122">Hub de análise</span><span class="sxs-lookup"><span data-stu-id="b0701-122">Analytics Hub</span></span>

<span data-ttu-id="b0701-123">Os relatórios Hub de análise agregam dados entre tarefas para destacar tendências no processo de contratação.</span><span class="sxs-lookup"><span data-stu-id="b0701-123">Analytics Hub reports aggregate data across jobs to surface trends in the hiring process.</span></span> <span data-ttu-id="b0701-124">O Attract inclui dois relatórios OOTB: Resumo de pipeline e Análise em forma de funil.</span><span class="sxs-lookup"><span data-stu-id="b0701-124">Attract includes two OOTB reports: Pipeline Summary and Funnel Analysis.</span></span>

### <a name="pipeline-summary"></a><span data-ttu-id="b0701-125">Resumo do Pipeline</span><span class="sxs-lookup"><span data-stu-id="b0701-125">Pipeline Summary</span></span>

<span data-ttu-id="b0701-126">O relatório Resumo de pipeline agrega dados para trabalhos abertos.</span><span class="sxs-lookup"><span data-stu-id="b0701-126">The Pipeline Summary report aggregates data for open jobs.</span></span> <span data-ttu-id="b0701-127">Principais métricas incluem:</span><span class="sxs-lookup"><span data-stu-id="b0701-127">Key metrics include:</span></span>

- <span data-ttu-id="b0701-128">Candidatos em todos os trabalhos por estágio</span><span class="sxs-lookup"><span data-stu-id="b0701-128">Applicants across all jobs by stage</span></span>
- <span data-ttu-id="b0701-129">Origem do candidato</span><span class="sxs-lookup"><span data-stu-id="b0701-129">Applicant source</span></span>
- <span data-ttu-id="b0701-130">Posições abertas por nível de tempo de serviço</span><span class="sxs-lookup"><span data-stu-id="b0701-130">Open jobs by seniority level</span></span>

### <a name="funnel-analysis"></a><span data-ttu-id="b0701-131">Análise em forma de funil</span><span class="sxs-lookup"><span data-stu-id="b0701-131">Funnel Analysis</span></span>

<span data-ttu-id="b0701-132">O relatório Análise em forma de funil agrega dados para trabalhos que foram fechados como preenchidos.</span><span class="sxs-lookup"><span data-stu-id="b0701-132">The Funnel Analysis report aggregates data for jobs that have been closed as filled.</span></span> <span data-ttu-id="b0701-133">Principais métricas incluem:</span><span class="sxs-lookup"><span data-stu-id="b0701-133">Key metrics include:</span></span>

- <span data-ttu-id="b0701-134">Tempo para contratar</span><span class="sxs-lookup"><span data-stu-id="b0701-134">Time to hire</span></span>
- <span data-ttu-id="b0701-135">Métricas de conversão (ao passar o mouse)</span><span class="sxs-lookup"><span data-stu-id="b0701-135">Conversion metrics (on hover)</span></span>
- <span data-ttu-id="b0701-136">Taxa de aceitação da oferta</span><span class="sxs-lookup"><span data-stu-id="b0701-136">Offer acceptance rate</span></span>

<span data-ttu-id="b0701-137">Observação: no momento mais preciso para contratação de relatórios, é recomendável que você use [Gerenciamento de ofertas](offer-setup.md), um recurso disponível como parte do Complemento de Contratação Abrangente.</span><span class="sxs-lookup"><span data-stu-id="b0701-137">Note: For the most accurate time to hire reporting, it is recommended that you use [Offer management](offer-setup.md), a feature available as part of the Comprehensive Hiring Add-On.</span></span>

>[!TIP] 
><span data-ttu-id="b0701-138">Tente passar o mouse sobre os recursos visuais para obter informações adicionais.</span><span class="sxs-lookup"><span data-stu-id="b0701-138">Try hovering over visuals for additional information.</span></span> <span data-ttu-id="b0701-139">Por exemplo, passar o mouse sobre os recursos visuais **Candidatos ativos** exibirá os dias médios no estágio.</span><span class="sxs-lookup"><span data-stu-id="b0701-139">For example, hovering over **Active applicants** visuals will display the average days in stage.</span></span> <span data-ttu-id="b0701-140">A análise dessas informações pode fornecer insights essenciais para reduzir o tempo de contratação e permitir que os recrutadores se concentrem em maneiras de reduzir o tempo gasto em cada estágio.</span><span class="sxs-lookup"><span data-stu-id="b0701-140">Analyzing this information can provide insights critical to reducing time to hire and enable recruiters to focus on ways to reduce the time spent in each stage.</span></span>

## <a name="user-specific-security"></a><span data-ttu-id="b0701-141">Segurança específica do usuário</span><span class="sxs-lookup"><span data-stu-id="b0701-141">User-specific security</span></span>

<span data-ttu-id="b0701-142">Os relatórios do Attract podem ser acessados para as [funções](security-attract.md) Administrador, Ler tudo, Recrutador e Gerente de contratação.</span><span class="sxs-lookup"><span data-stu-id="b0701-142">Attract reports are accessible for Admin, Read All, Recruiter, and Hiring Manager [roles](security-attract.md).</span></span> <span data-ttu-id="b0701-143">Os usuários não atribuídos não têm acesso a nenhuma das páginas do relatório analítico (Análise de trabalho ou Hub de análise).</span><span class="sxs-lookup"><span data-stu-id="b0701-143">Unassigned users do not have access to either of the analytic report pages (Job Analytics or Analytics Hub).</span></span>

<span data-ttu-id="b0701-144">Os relatórios Análise de trabalho exibem dados para o trabalho selecionado.</span><span class="sxs-lookup"><span data-stu-id="b0701-144">Job Analytics reports display data for the selected job.</span></span> <span data-ttu-id="b0701-145">O Hub de análise reúne dados agregados em todos os trabalhos que um usuário pode visualizar.</span><span class="sxs-lookup"><span data-stu-id="b0701-145">Analytics Hub reports aggregate data across all jobs a user can view.</span></span> <span data-ttu-id="b0701-146">Os usuários que podem visualizar Meus trabalhos e Todos os trabalhos na página Trabalhos têm as mesmas visualizações disponíveis no Hub de análise.</span><span class="sxs-lookup"><span data-stu-id="b0701-146">Users that can view both My jobs and All jobs on the Jobs page have the same views available in the Analytics Hub.</span></span>

## <a name="cross-filter"></a><span data-ttu-id="b0701-147">Filtro cruzado</span><span class="sxs-lookup"><span data-stu-id="b0701-147">Cross-filter</span></span>

<span data-ttu-id="b0701-148">Um dos grandes recursos do Power BI é a forma como todos os recursos visuais de uma página de relatório são interconectados.</span><span class="sxs-lookup"><span data-stu-id="b0701-148">One of the great features of Power BI is the way all visuals on a report page are interconnected.</span></span> <span data-ttu-id="b0701-149">Se você selecionar um ponto de dados em um dos recursos visuais, todos os outros recursos visuais na página que contêm esses dados serão alterados com base nessa seleção.</span><span class="sxs-lookup"><span data-stu-id="b0701-149">If you select a data point on one of the visuals, all the other visuals on the page that contain that data change, based on that selection.</span></span> <span data-ttu-id="b0701-150">Saiba mais e veja um exemplo em [Como os visuais realizam filtragem cruzada entre si em um relatório do Power BI](https://docs.microsoft.com/power-bi/consumer/end-user-interactions).</span><span class="sxs-lookup"><span data-stu-id="b0701-150">Find out more and see an example in [How visuals cross-filter each other in a Power BI report](https://docs.microsoft.com/power-bi/consumer/end-user-interactions).</span></span>

## <a name="export-to-excel"></a><span data-ttu-id="b0701-151">Exportar para o Excel</span><span class="sxs-lookup"><span data-stu-id="b0701-151">Export to Excel</span></span>

<span data-ttu-id="b0701-152">Para visualizar os dados do relatório no Excel, você pode clicar no menu de opções (três pontos) em um visual e selecionar **Exportar dados subjacentes**.</span><span class="sxs-lookup"><span data-stu-id="b0701-152">To view report data in Excel, you can click the options menu (three dots) on a visual and select **Export underlying data**.</span></span> <span data-ttu-id="b0701-153">Os dados exportados serão exportados como filtrados, respeitando as permissões do usuário no Attract.</span><span class="sxs-lookup"><span data-stu-id="b0701-153">Exported data will export as filtered, respecting user permissions in Attract.</span></span> <span data-ttu-id="b0701-154">Para obter mais informações, consulte [Exportar dados de visualizações](https://docs.microsoft.com/power-bi/visuals/power-bi-visualization-export-data).</span><span class="sxs-lookup"><span data-stu-id="b0701-154">For more information, see [Export data from visualizations](https://docs.microsoft.com/power-bi/visuals/power-bi-visualization-export-data).</span></span>
