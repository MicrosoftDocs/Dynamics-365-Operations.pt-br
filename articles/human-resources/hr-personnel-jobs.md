---
title: Configurar os componentes de um trabalho
description: Este artigo descreve os elementos conceituais que um trabalho pode incluir e fornece exemplos de como você pode usar esses elementos na sua organização.
author: andreabichsel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
ms.search.form: HcmJob, HcmJobFunction, HcmJobTask, HcmTitle
audience: Application User
ms.author: anbichse
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Human Resources, Retail
ms.custom: 269054
ms.assetid: 889a8fab-0eef-45c2-91fc-ff2f4d44d54f
ms.search.region: Global
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 02475cdc23565c1d49c9f1bb6901101b16acf3a5
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "3008123"
---
# <a name="set-up-the-components-of-a-job"></a><span data-ttu-id="0f077-103">Configurar os componentes de um trabalho</span><span class="sxs-lookup"><span data-stu-id="0f077-103">Set up the components of a job</span></span>

<span data-ttu-id="0f077-104">Este artigo descreve os elementos conceituais que um trabalho pode incluir e fornece exemplos de como você pode usar esses elementos na sua organização.</span><span class="sxs-lookup"><span data-stu-id="0f077-104">This article describes the conceptual elements that a job can include and provides examples of how you can use those elements in your organization.</span></span> 

<span data-ttu-id="0f077-105">Antes de você poder criar trabalhos, você deve configurar algumas informações de referência.</span><span class="sxs-lookup"><span data-stu-id="0f077-105">Before you can create jobs, you must set up some reference information.</span></span> <span data-ttu-id="0f077-106">Você pode criar um trabalho com apenas um nome.</span><span class="sxs-lookup"><span data-stu-id="0f077-106">You can create a job that has only a name.</span></span> <span data-ttu-id="0f077-107">No entanto, ao incluir informações adicionais, como título do trabalho, você fornece valores padrão para as posições atribuídas ao trabalho.</span><span class="sxs-lookup"><span data-stu-id="0f077-107">However, by including additional information, such as a job title, you provide default values for the positions that are assigned to the job.</span></span> <span data-ttu-id="0f077-108">Além disso, algumas das informações inseridas por você podem ser usadas para filtrar planos de remuneração para trabalhos específicos.</span><span class="sxs-lookup"><span data-stu-id="0f077-108">Additionally, some of the information that you enter can be used to filter compensation plans to specific jobs.</span></span> <span data-ttu-id="0f077-109">Se deseja configurar a qualificação que pode ser usada para filtrar planos de remuneração para um trabalho específico, você deve configurar funções e tipos de trabalho antes de configurar os trabalhos.</span><span class="sxs-lookup"><span data-stu-id="0f077-109">If you want to set up eligibility that you can use to filter compensation plans to a specific job, you should set up job functions and job types before you set up jobs.</span></span> <span data-ttu-id="0f077-110">Com esses valores padrão disponíveis, você economizará tempo ao adicionar posições ao trabalho.</span><span class="sxs-lookup"><span data-stu-id="0f077-110">By having these default values available, you will save time when you add positions to the job.</span></span> 

<span data-ttu-id="0f077-111">Alguns detalhes de trabalho, como o título, tipo e função do trabalho, são de data efetiva.</span><span class="sxs-lookup"><span data-stu-id="0f077-111">Some job details, such as the job title, type, and function, are date-effective.</span></span> <span data-ttu-id="0f077-112">Se você criar um trabalho hoje mas não adicionar esses detalhes posteriormente e verificar o trabalho a partir da data de criação, esses detalhes não aparecerão.</span><span class="sxs-lookup"><span data-stu-id="0f077-112">If you create a job today but don't add these details until later, and you then look at the job as of the creation date, these details won't appear.</span></span> <span data-ttu-id="0f077-113">Portanto, você deve criar algumas dessas informações de referência antes de solicitá-las.</span><span class="sxs-lookup"><span data-stu-id="0f077-113">Therefore, you should create some of this reference information before you require it.</span></span> <span data-ttu-id="0f077-114">Dessa forma, você pode adicionar as informações a novos trabalhos ao criá-los.</span><span class="sxs-lookup"><span data-stu-id="0f077-114">That way, you can add the information to new jobs when you create them.</span></span>

## <a name="job-titles"></a><span data-ttu-id="0f077-115">Títulos de trabalho</span><span class="sxs-lookup"><span data-stu-id="0f077-115">Job titles</span></span>
<span data-ttu-id="0f077-116">Antes de criar trabalhos, você deve configurar cargos para esses trabalhos.</span><span class="sxs-lookup"><span data-stu-id="0f077-116">Before you create jobs, you must set up titles for those jobs.</span></span> <span data-ttu-id="0f077-117">As posições herdam cargos dos trabalhos com os quais essas posições estão associadas.</span><span class="sxs-lookup"><span data-stu-id="0f077-117">Positions inherit job titles from the jobs that the positions are associated with.</span></span> 

<span data-ttu-id="0f077-118">Manter títulos de trabalho usando a página **Títulos**, que você pode abrir por meio da função Pesquisar.</span><span class="sxs-lookup"><span data-stu-id="0f077-118">Maintain job titles using the **Titles** page, which you can open by using the Search function.</span></span> <span data-ttu-id="0f077-119">Na página **Títulos**, insira os títulos que você planeja usar em seus trabalhos.</span><span class="sxs-lookup"><span data-stu-id="0f077-119">On the \*\*Titles \*\*page, enter the titles that you plan to use for your jobs.</span></span>

## <a name="job-types"></a><span data-ttu-id="0f077-120">Tipos de trabalho</span><span class="sxs-lookup"><span data-stu-id="0f077-120">Job types</span></span>
<span data-ttu-id="0f077-121">Você usa tipos de trabalho para agrupar trabalhos semelhantes em categorias.</span><span class="sxs-lookup"><span data-stu-id="0f077-121">You use job types to group similar jobs into categories.</span></span> <span data-ttu-id="0f077-122">Tipos de trabalhos não são necessários.</span><span class="sxs-lookup"><span data-stu-id="0f077-122">Job types aren't required.</span></span> <span data-ttu-id="0f077-123">Entretanto, se planeja usar tipos de trabalho ao configurar regras de qualificação para o gerenciamento de remuneração, você deve configurar tipos de trabalho antes de configurar os trabalhos.</span><span class="sxs-lookup"><span data-stu-id="0f077-123">However, if you plan to use job types when you set up eligibility rules for compensation management, you should set up job types before you set up jobs.</span></span> <span data-ttu-id="0f077-124">Alguns exemplos de tipos de trabalho são horário integral e meio período ou salário e pagamento por hora.</span><span class="sxs-lookup"><span data-stu-id="0f077-124">Some examples of job types are full-time and part-time, or salary and hourly pay.</span></span> <span data-ttu-id="0f077-125">Você mantém tipos de trabalho usando a página **Tipos de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="0f077-125">You maintain job types by using the **Job types** page.</span></span> <span data-ttu-id="0f077-126">Na página **Tipos de trabalho**, insira um nome e uma breve descrição para o tipo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="0f077-126">On the **Job types** page, enter a name and a brief description for the job type.</span></span> <span data-ttu-id="0f077-127">No campo **Status de isenção**, selecione uma das seguintes opções para indicar o status de isenção de trabalhos FLSA (Lei de Padrões Justos de Trabalho) que tem esse tipo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="0f077-127">In the **Exempt status** field, select one of the following options to indicate the Fair Labor Standards Act (FLSA) exempt status of jobs that have this job type:</span></span>

-   <span data-ttu-id="0f077-128">**Isenção** – Os trabalhos estão isentos de horas extras de acordo com a FLSA.</span><span class="sxs-lookup"><span data-stu-id="0f077-128">**Exempt** – Jobs are exempt from overtime under the FLSA.</span></span>
-   <span data-ttu-id="0f077-129">**Não isento** – Os trabalhos não estão isentos de horas extras de acordo com a FLSA.</span><span class="sxs-lookup"><span data-stu-id="0f077-129">**Non-exempt** – Jobs aren't exempt from overtime under the FLSA.</span></span>
-   <span data-ttu-id="0f077-130">**Não se aplica** – A cobertura da FLSA não é aplicável.</span><span class="sxs-lookup"><span data-stu-id="0f077-130">**Does not apply** – FLSA coverage isn't applicable.</span></span>

## <a name="job-functions"></a><span data-ttu-id="0f077-131">Funções de trabalho</span><span class="sxs-lookup"><span data-stu-id="0f077-131">Job functions</span></span>
<span data-ttu-id="0f077-132">Junções de trabalho descrevem categorias funcionais de alto nível e direitos de alto nível relacionados.</span><span class="sxs-lookup"><span data-stu-id="0f077-132">Job junctions describe high-level functional categories and relate high-level duties.</span></span> <span data-ttu-id="0f077-133">Junções de trabalho não são necessárias.</span><span class="sxs-lookup"><span data-stu-id="0f077-133">Job functions aren't required.</span></span> <span data-ttu-id="0f077-134">Você pode usar essas funções, juntamente com tipos de trabalho, a fim de filtrar planos de remuneração para trabalhos específicos.</span><span class="sxs-lookup"><span data-stu-id="0f077-134">You can use job functions, together with job types, to filter compensation plans to specific jobs.</span></span> <span data-ttu-id="0f077-135">Para associar funções e tipos de trabalho a planos de remuneração, configure regras de qualificação na página **Regras de qualificação**.</span><span class="sxs-lookup"><span data-stu-id="0f077-135">You associate job functions and job types with compensation plans by setting up eligibility rules on the **Eligibility rules** page.</span></span> <span data-ttu-id="0f077-136">Você então pode associar ao plano de remuneração um conjunto de níveis aplicáveis à combinação específica de tipo/função de trabalho definida por meio de uma regra de qualificação.</span><span class="sxs-lookup"><span data-stu-id="0f077-136">You can then attach a set of levels to a compensation plan that apply to the specific combination of a job type and job function that you've defined through an eligibility rule.</span></span> <span data-ttu-id="0f077-137">(Esses recursos se aplicam aos planos de remuneração fixos e variáveis.) No entanto, se planeja usar funções de trabalho ao configurar regras de qualificação para o gerenciamento de remuneração, você deve configurar funções de trabalho antes de configurar os trabalhos.</span><span class="sxs-lookup"><span data-stu-id="0f077-137">(These features apply to both fixed compensation plans and variable compensation plans.) However, if you plan to use job functions when you set up eligibility rules for compensation management, you should set up job functions before you set up jobs.</span></span> <span data-ttu-id="0f077-138">A tabela a seguir mostra alguns exemplos de funções de trabalho.</span><span class="sxs-lookup"><span data-stu-id="0f077-138">The following table shows some examples of job functions.</span></span>

| <span data-ttu-id="0f077-139">Trabalho</span><span class="sxs-lookup"><span data-stu-id="0f077-139">Job</span></span>           | <span data-ttu-id="0f077-140">Função de trabalho</span><span class="sxs-lookup"><span data-stu-id="0f077-140">Job function</span></span>         |
|---------------|----------------------|
| <span data-ttu-id="0f077-141">Gerente de vendas</span><span class="sxs-lookup"><span data-stu-id="0f077-141">Sales manager</span></span> | <span data-ttu-id="0f077-142">Gerente de nível médio</span><span class="sxs-lookup"><span data-stu-id="0f077-142">Mid-level Manager</span></span>    |
| <span data-ttu-id="0f077-143">Contador</span><span class="sxs-lookup"><span data-stu-id="0f077-143">Accountant</span></span>    | <span data-ttu-id="0f077-144">Profissionais</span><span class="sxs-lookup"><span data-stu-id="0f077-144">Professionals</span></span>        |

<span data-ttu-id="0f077-145">Você mantém funções de trabalho usando a página **Funções de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="0f077-145">You maintain job functions by using the **Job functions** page.</span></span> <span data-ttu-id="0f077-146">Na página **Funções de trabalho**, insira um código de identificação e uma breve descrição para a função de trabalho.</span><span class="sxs-lookup"><span data-stu-id="0f077-146">On the **Job functions** page, enter an identification code and a brief description for the job function.</span></span>

## <a name="job-tasks"></a><span data-ttu-id="0f077-147">Tarefas do trabalho</span><span class="sxs-lookup"><span data-stu-id="0f077-147">Job tasks</span></span>
<span data-ttu-id="0f077-148">Tarefas de trabalho descrevem as tarefas básicas que devem ser realizadas por um trabalhador em um cargo desse trabalho.</span><span class="sxs-lookup"><span data-stu-id="0f077-148">Job tasks describe the basic tasks that a worker who is in a position for a job must complete.</span></span> <span data-ttu-id="0f077-149">A mesma tarefa de trabalho pode ser adicionada a vários trabalhos e posições para os trabalhos que usam essas tarefas de trabalho.</span><span class="sxs-lookup"><span data-stu-id="0f077-149">The same job task can be added to multiple jobs, and to positions for the jobs that use those job tasks.</span></span> <span data-ttu-id="0f077-150">A tabela a seguir mostra alguns exemplos de tarefas de trabalho.</span><span class="sxs-lookup"><span data-stu-id="0f077-150">The following table shows some examples of job tasks.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="0f077-151">Trabalho</span><span class="sxs-lookup"><span data-stu-id="0f077-151">Job</span></span></th>
<th><span data-ttu-id="0f077-152">Tarefa do trabalho</span><span class="sxs-lookup"><span data-stu-id="0f077-152">Job task</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="0f077-153">Gerente de vendas</span><span class="sxs-lookup"><span data-stu-id="0f077-153">Sales manager</span></span></td>
<td><ul>
<li><span data-ttu-id="0f077-154"><strong>Avaliação de desempenho</strong> – avaliar o desempenho profissional de cada vendedor.</span><span class="sxs-lookup"><span data-stu-id="0f077-154"><strong>Perf-review</strong> – Review each salesperson&#39;s job performance.</span></span></li>
<li><span data-ttu-id="0f077-155"><strong>Avaliação de ausências</strong> – aprovar ou rejeitar solicitações ou registros de ausência de cada vendedor.</span><span class="sxs-lookup"><span data-stu-id="0f077-155"><strong>Abs-review</strong> – Approve or reject each salesperson&#39;s absence requests or registrations.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="0f077-156">Contador</span><span class="sxs-lookup"><span data-stu-id="0f077-156">Accountant</span></span></td>
<td><span data-ttu-id="0f077-157"><strong>Relatório financeiro</strong> – Apresentar relatórios financeiros semanais para o diretor financeiro.</span><span class="sxs-lookup"><span data-stu-id="0f077-157"><strong>FIN-Report</strong> – Present weekly financial reports to the chief financial officer.</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="0f077-158">Você mantém tarefas de trabalho usando a página **Tarefas de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="0f077-158">You maintain job tasks by using the **Job tasks** page.</span></span> <span data-ttu-id="0f077-159">Na página **Tarefas de trabalho**, insira um nome e uma descrição para a tarefa de trabalho.</span><span class="sxs-lookup"><span data-stu-id="0f077-159">On the **Job tasks** page, enter a name and description for the job task.</span></span> <span data-ttu-id="0f077-160">No campo **Observação**, você tem a opção de inserir informações adicionais.</span><span class="sxs-lookup"><span data-stu-id="0f077-160">In the **Note** field, you can optionally enter additional information.</span></span> <span data-ttu-id="0f077-161">As observações podem ser atualizadas para um trabalho específico sem a necessidade de alteração das observações que você inseriu aqui.</span><span class="sxs-lookup"><span data-stu-id="0f077-161">The notes can be updated for a specific job without changing the notes that you entered here.</span></span>

## <a name="areas-of-responsibility"></a><span data-ttu-id="0f077-162">Áreas de responsabilidade</span><span class="sxs-lookup"><span data-stu-id="0f077-162">Areas of responsibility</span></span>
<span data-ttu-id="0f077-163">Use as áreas de responsabilidade para indicar as funções de trabalho, os processos e os produtos pelos quais um trabalhador é responsável em um cargo do trabalho.</span><span class="sxs-lookup"><span data-stu-id="0f077-163">You use areas of responsibility to indicate the work roles, processes, and products that a worker who is in a position for a job is responsible for.</span></span> <span data-ttu-id="0f077-164">Por exemplo, para um trabalho denominado "Contador", uma área de responsabilidade pode ser "Relatório financeiro do produto A".</span><span class="sxs-lookup"><span data-stu-id="0f077-164">For example, for a job that is named "Accountant," one area of responsibility might be "Financial reporting for product A."</span></span> <span data-ttu-id="0f077-165">Você mantém áreas de responsabilidade usando a página **Áreas de responsabilidade**, que você pode encontrar por meio da função Pesquisar.</span><span class="sxs-lookup"><span data-stu-id="0f077-165">You maintain areas of responsibility by using the **Areas of responsibility** page, which you can find by using the Search function.</span></span> <span data-ttu-id="0f077-166">Na página **Áreas de responsabilidade**, insira um nome e uma descrição para a responsabilidade.</span><span class="sxs-lookup"><span data-stu-id="0f077-166">On the **Areas of responsibility** page, enter a name and description for the responsibility.</span></span> <span data-ttu-id="0f077-167">No campo **Observação**, você tem a opção de inserir informações adicionais.</span><span class="sxs-lookup"><span data-stu-id="0f077-167">In the **Note** field, you can optionally enter additional information.</span></span> <span data-ttu-id="0f077-168">As observações podem ser atualizadas para um trabalho específico sem a necessidade de alteração das observações que você inseriu aqui.</span><span class="sxs-lookup"><span data-stu-id="0f077-168">The notes can be updated for a specific job without changing the notes that you entered here.</span></span>

## <a name="steps-for-creating-a-job"></a><span data-ttu-id="0f077-169">Etapas para criar um trabalho</span><span class="sxs-lookup"><span data-stu-id="0f077-169">Steps for creating a job</span></span>
<span data-ttu-id="0f077-170">Consulte o artigo [Definir novos trabalhos](../fin-and-ops/hr/tasks/define-new-jobs.md) para obter o procedimento passo a passo para criar um novo trabalho.</span><span class="sxs-lookup"><span data-stu-id="0f077-170">Refer to the [Define new jobs](../fin-and-ops/hr/tasks/define-new-jobs.md) article for the step-by-step procedure for creating a new job.</span></span> 