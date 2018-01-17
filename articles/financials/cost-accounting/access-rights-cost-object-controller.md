---
title: Definir direitos de acesso para controladores do objeto de custo
description: "Este tópico fornece informações sobre direitos de acesso para controladores do objeto de custo."
author: AndersGirke
manager: AnnBe
ms.date: 06/24/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CAMCostControlWorkspace, CAMParameters
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations, Core
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 029511634e56aec7fdd91bad9441cd12951fbd8d
ms.openlocfilehash: d3489e4cc5c9cbf1f3ac89350a811fd99c7d8ce3
ms.contentlocale: pt-br
ms.lasthandoff: 01/17/2018

---

# <a name="access-rights-of-a-cost-object-controller"></a><span data-ttu-id="27691-103">Direitos de acesso de um controlador de objeto de custo</span><span class="sxs-lookup"><span data-stu-id="27691-103">Access rights of a cost object controller</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="27691-104">O espaço trabalho **Controle de custos** é uma empresa central onde os gerentes podem exibir o desempenho de seus objetos de custo.</span><span class="sxs-lookup"><span data-stu-id="27691-104">The **Cost control** workspace is a central point where managers can view the performance of their cost objects.</span></span> <span data-ttu-id="27691-105">Este espaço de trabalho permite que os gerentes consumam dados da contabilidade de custo mesmo que não sejam contadores.</span><span class="sxs-lookup"><span data-stu-id="27691-105">This workspace lets managers consume Cost accounting data even though they aren't cost accountants.</span></span> <span data-ttu-id="27691-106">Por motivo de segurança, gerentes somente podem consultar os dados da contabilidade de custo relacionados a objetos específicos de custo pelos quais eles são responsáveis.</span><span class="sxs-lookup"><span data-stu-id="27691-106">For security reasons, managers should be allowed to see only the Cost accounting data that is related to the specific cost objects that they are responsible for.</span></span>

<span data-ttu-id="27691-107">Existem quatro funções exclusivas na contabilização de custos.</span><span class="sxs-lookup"><span data-stu-id="27691-107">There are four unique roles in Cost accounting.</span></span>

| <span data-ttu-id="27691-108">Nome da função</span><span class="sxs-lookup"><span data-stu-id="27691-108">Role name</span></span>               | <span data-ttu-id="27691-109">Licença</span><span class="sxs-lookup"><span data-stu-id="27691-109">License</span></span>      |
|-------------------------|--------------|
| <span data-ttu-id="27691-110">Gerenciador de contabilização de custos</span><span class="sxs-lookup"><span data-stu-id="27691-110">Cost accounting manager</span></span> | <span data-ttu-id="27691-111">Atividade</span><span class="sxs-lookup"><span data-stu-id="27691-111">Activity</span></span>     |
| <span data-ttu-id="27691-112">Contador de custos</span><span class="sxs-lookup"><span data-stu-id="27691-112">Cost accountant</span></span>         | <span data-ttu-id="27691-113">Operations</span><span class="sxs-lookup"><span data-stu-id="27691-113">Operations</span></span>   |
| <span data-ttu-id="27691-114">Contador de custos</span><span class="sxs-lookup"><span data-stu-id="27691-114">Cost accountant clerk</span></span>   | <span data-ttu-id="27691-115">Operations</span><span class="sxs-lookup"><span data-stu-id="27691-115">Operations</span></span>   |
| <span data-ttu-id="27691-116">Controlador do objeto de custo</span><span class="sxs-lookup"><span data-stu-id="27691-116">Cost object controller</span></span>  | <span data-ttu-id="27691-117">Membros da equipe</span><span class="sxs-lookup"><span data-stu-id="27691-117">Team members</span></span> |

<span data-ttu-id="27691-118">Este tópico explica como atribuir a função **Controlador do objeto de custo** a um gerente.</span><span class="sxs-lookup"><span data-stu-id="27691-118">This topic explains how to assign the **Cost object controller** role to a manager.</span></span>

<span data-ttu-id="27691-119">Quando a função **Controlador do objeto de custo** for designada a um gerente, ele poderá executar as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="27691-119">When the **Cost object controller** role is assigned to a manager, the manager can perform the following tasks:</span></span>

- <span data-ttu-id="27691-120">Acessar o espaço de trabalho **Controle de custo** (no cliente).</span><span class="sxs-lookup"><span data-stu-id="27691-120">Access the **Cost control** workspace (in the client).</span></span>

    - <span data-ttu-id="27691-121">Detalhar e ter acesso de exibição às páginas que suportam a experiência detalhada.</span><span class="sxs-lookup"><span data-stu-id="27691-121">Drill through and have view access to the pages that support the drill-through experience.</span></span>

- <span data-ttu-id="27691-122">Acessar o espaço de trabalho **Controle de custo** (no aplicativo móvel).</span><span class="sxs-lookup"><span data-stu-id="27691-122">Access the **Cost control** workspace (in the mobile application).</span></span>

> [!NOTE]
> <span data-ttu-id="27691-123">A função **Controlador do objeto de custo** não controla os objetos de custo pelo qual o usuário pode acessar e exibir dados.</span><span class="sxs-lookup"><span data-stu-id="27691-123">The **Cost object controller** role doesn't control which cost objects the user can access and view data for.</span></span> <span data-ttu-id="27691-124">A segurança em nível de linha é fornecida por meio das hierarquias de dimensões e de hierarquia de lista de acesso.</span><span class="sxs-lookup"><span data-stu-id="27691-124">Row-level security is provided via dimension hierarchies and the Access list hierarchy.</span></span>

## <a name="grant-access-rights"></a><span data-ttu-id="27691-125">Conceder direitos de acesso</span><span class="sxs-lookup"><span data-stu-id="27691-125">Grant access rights</span></span>
<span data-ttu-id="27691-126">O exemplo a seguir mostra como pode ser uma hierarquia de dimensões.</span><span class="sxs-lookup"><span data-stu-id="27691-126">The following example shows what a dimension hierarchy can look like.</span></span>

<span data-ttu-id="27691-127">**Detalhes de hierarquias de dimensão**</span><span class="sxs-lookup"><span data-stu-id="27691-127">**Dimension hierarchy details**</span></span>

| <span data-ttu-id="27691-128">Nome de hierarquia de dimensões</span><span class="sxs-lookup"><span data-stu-id="27691-128">Dimension hierarchy name</span></span> | <span data-ttu-id="27691-129">Dimensão</span><span class="sxs-lookup"><span data-stu-id="27691-129">Dimension</span></span>    | <span data-ttu-id="27691-130">Nome do tipo de hierarquia de dimensões</span><span class="sxs-lookup"><span data-stu-id="27691-130">Dimension hierarchy type name</span></span>      | <span data-ttu-id="27691-131">Acessar hierarquia de lista</span><span class="sxs-lookup"><span data-stu-id="27691-131">Access list hierarchy</span></span> |
|--------------------------|--------------|------------------------------------|-----------------------|
| <span data-ttu-id="27691-132">Organização</span><span class="sxs-lookup"><span data-stu-id="27691-132">Organization</span></span>             | <span data-ttu-id="27691-133">Centros de custos</span><span class="sxs-lookup"><span data-stu-id="27691-133">Cost centers</span></span> | <span data-ttu-id="27691-134">Hierarquia de classificação de dimensões</span><span class="sxs-lookup"><span data-stu-id="27691-134">Dimension classification hierarchy</span></span> | <span data-ttu-id="27691-135">**Sim**</span><span class="sxs-lookup"><span data-stu-id="27691-135">**Yes**</span></span>               |

<span data-ttu-id="27691-136">Você pode usar a Guia Rápida **Usuários** no designer de hierarquia para inserir uma ou várias ids de usuário em cada nó.</span><span class="sxs-lookup"><span data-stu-id="27691-136">You can use the **Users** FastTab in the hierarchy designer to insert one or more user IDs on each node.</span></span>

|                                   | <span data-ttu-id="27691-137">Usuários</span><span class="sxs-lookup"><span data-stu-id="27691-137">Users</span></span>            | <span data-ttu-id="27691-138">Intervalos de membros de dimensão</span><span class="sxs-lookup"><span data-stu-id="27691-138">Dimension member ranges</span></span>   |                         |
|-----------------------------------|------------------|---------------------------|-------------------------|
| <span data-ttu-id="27691-139">**Nós**</span><span class="sxs-lookup"><span data-stu-id="27691-139">**Nodes**</span></span>                         | <span data-ttu-id="27691-140">**ID do Usuário**</span><span class="sxs-lookup"><span data-stu-id="27691-140">**User ID**</span></span>      | <span data-ttu-id="27691-141">**Membro da dimensão de origem**</span><span class="sxs-lookup"><span data-stu-id="27691-141">**From dimension member**</span></span> | <span data-ttu-id="27691-142">**Membro da dimensão de destino**</span><span class="sxs-lookup"><span data-stu-id="27691-142">**To dimension member**</span></span> |
| <span data-ttu-id="27691-143">Organização</span><span class="sxs-lookup"><span data-stu-id="27691-143">Organization</span></span>                      | <span data-ttu-id="27691-144">Benjamin, Claire</span><span class="sxs-lookup"><span data-stu-id="27691-144">Benjamin, Claire</span></span> |                           |                         |
| <span data-ttu-id="27691-145">&nbsp;&nbsp;Administrador</span><span class="sxs-lookup"><span data-stu-id="27691-145">&nbsp;&nbsp;Admin</span></span>                 | <span data-ttu-id="27691-146">Abril</span><span class="sxs-lookup"><span data-stu-id="27691-146">April</span></span>            |                           |                         |
| <span data-ttu-id="27691-147">&nbsp;&nbsp;&nbsp;&nbsp;Finanças</span><span class="sxs-lookup"><span data-stu-id="27691-147">&nbsp;&nbsp;&nbsp;&nbsp;Finance</span></span>   | <span data-ttu-id="27691-148">Alicia</span><span class="sxs-lookup"><span data-stu-id="27691-148">Alicia</span></span>           | <span data-ttu-id="27691-149">CC002</span><span class="sxs-lookup"><span data-stu-id="27691-149">CC002</span></span>                     | <span data-ttu-id="27691-150">CC003</span><span class="sxs-lookup"><span data-stu-id="27691-150">CC003</span></span>                   |
|                                   |                  | <span data-ttu-id="27691-151">CC007</span><span class="sxs-lookup"><span data-stu-id="27691-151">CC007</span></span>                     | <span data-ttu-id="27691-152">CC007</span><span class="sxs-lookup"><span data-stu-id="27691-152">CC007</span></span>                   |
| <span data-ttu-id="27691-153">&nbsp;&nbsp;&nbsp;&nbsp;RH</span><span class="sxs-lookup"><span data-stu-id="27691-153">&nbsp;&nbsp;&nbsp;&nbsp;HR</span></span>        | <span data-ttu-id="27691-154">Arnie</span><span class="sxs-lookup"><span data-stu-id="27691-154">Arnie</span></span>            | <span data-ttu-id="27691-155">CC001</span><span class="sxs-lookup"><span data-stu-id="27691-155">CC001</span></span>                     | <span data-ttu-id="27691-156">CC001</span><span class="sxs-lookup"><span data-stu-id="27691-156">CC001</span></span>                   |
| <span data-ttu-id="27691-157">&nbsp;&nbsp;Produção</span><span class="sxs-lookup"><span data-stu-id="27691-157">&nbsp;&nbsp;Production</span></span>            | <span data-ttu-id="27691-158">David</span><span class="sxs-lookup"><span data-stu-id="27691-158">David</span></span>            |                           |                         |
| <span data-ttu-id="27691-159">&nbsp;&nbsp;&nbsp;&nbsp;Embalagem</span><span class="sxs-lookup"><span data-stu-id="27691-159">&nbsp;&nbsp;&nbsp;&nbsp;Packaging</span></span> | <span data-ttu-id="27691-160">Ellen</span><span class="sxs-lookup"><span data-stu-id="27691-160">Ellen</span></span>            | <span data-ttu-id="27691-161">CC005</span><span class="sxs-lookup"><span data-stu-id="27691-161">CC005</span></span>                     | <span data-ttu-id="27691-162">CC005</span><span class="sxs-lookup"><span data-stu-id="27691-162">CC005</span></span>                   |
| <span data-ttu-id="27691-163">&nbsp;&nbsp;&nbsp;&nbsp;Montagem</span><span class="sxs-lookup"><span data-stu-id="27691-163">&nbsp;&nbsp;&nbsp;&nbsp;Assembly</span></span>  | <span data-ttu-id="27691-164">Chris</span><span class="sxs-lookup"><span data-stu-id="27691-164">Chris</span></span>            | <span data-ttu-id="27691-165">CC006</span><span class="sxs-lookup"><span data-stu-id="27691-165">CC006</span></span>                     | <span data-ttu-id="27691-166">CC006</span><span class="sxs-lookup"><span data-stu-id="27691-166">CC006</span></span>                   |

> [!NOTE]
> <span data-ttu-id="27691-167">Os contadores devem ser atribuídos ao nível de hierarquia superior para que possam consultar todas as entradas na contabilização de custo.</span><span class="sxs-lookup"><span data-stu-id="27691-167">Cost accountants should be assigned to the top level of the hierarchy, so that they can see all entries in Cost accounting.</span></span>

<span data-ttu-id="27691-168">Antes da hierarquia da lista de acesso e de suas configurações de segurança serem aplicadas, a opção **Habilitar acesso de visualização para membros de dimensão de objeto de custo** deve ser definida como **Sim** na guia **Geral** da página **Parâmetros de contabilização de custos** (**Contabilização de custo** > **Configuração** > **Parâmetros**).</span><span class="sxs-lookup"><span data-stu-id="27691-168">Before the Access list hierarchy and its security settings can be applied, the **Enable view access for cost object dimension members** option must be set to **Yes** on the **General** tab of the **Cost accounting parameters** page (**Cost accounting** > **Setup** > **Parameters**).</span></span>

<span data-ttu-id="27691-169">As configurações da hierarquia da lista de acesso são usadas para controlar os dados que são mostrados nas seguintes áreas:</span><span class="sxs-lookup"><span data-stu-id="27691-169">The settings for the Access list hierarchy are used to control the data that is shown in following areas:</span></span>

- <span data-ttu-id="27691-170">Espaço de trabalho **Controle de custo** (no cliente):</span><span class="sxs-lookup"><span data-stu-id="27691-170">**Cost control** workspace (in the client):</span></span>

    - <span data-ttu-id="27691-171">Dados nas páginas usadas para o detalhamento</span><span class="sxs-lookup"><span data-stu-id="27691-171">Data on the pages that are used for drill-through</span></span>

- <span data-ttu-id="27691-172">Espaço de trabalho **Controle de custo** (no aplicativo móvel):</span><span class="sxs-lookup"><span data-stu-id="27691-172">**Cost control** workspace (in the mobile application):</span></span>

    - <span data-ttu-id="27691-173">Saldos em cartões</span><span class="sxs-lookup"><span data-stu-id="27691-173">Balances in cards</span></span>

- <span data-ttu-id="27691-174">Microsoft Power BI:</span><span class="sxs-lookup"><span data-stu-id="27691-174">Microsoft Power BI:</span></span>

    - <span data-ttu-id="27691-175">Dados mostrados nas visualizações do Power BI</span><span class="sxs-lookup"><span data-stu-id="27691-175">Data that is shown in Power BI visualizations</span></span>
    - <span data-ttu-id="27691-176">Visualizações de dados do Power BI incorporadas no cliente Microsoft Dynamics 365 for Finance and Operations, Enterprise edition</span><span class="sxs-lookup"><span data-stu-id="27691-176">Data Power BI visualizations that are embedded in the Microsoft Dynamics 365 for Finance and Operations, Enterprise edition, client</span></span>

> [!IMPORTANT]
> - <span data-ttu-id="27691-177">Antes que a hierarquia da lista de acesso possa afetar os dados no Power BI, a hierarquia da lista de acesso e a segurança em nível de linha no Power BI devem ser emparelhadas.</span><span class="sxs-lookup"><span data-stu-id="27691-177">Before the Access list hierarchy can affect data in Power BI, the Access list hierarchy and row-level security in Power BI must be paired.</span></span> <span data-ttu-id="27691-178">Para obter mais informações, consulte [Configurar segurança para o pacote de conteúdo de contabilização de custo](../../dev-itpro/analytics/setup-security-cost-accounting-content-pack.md).</span><span class="sxs-lookup"><span data-stu-id="27691-178">For more information, see [Set up security for Cost accounting content pack](../../dev-itpro/analytics/setup-security-cost-accounting-content-pack.md).</span></span>
> - <span data-ttu-id="27691-179">Esta seção mostra os pré-requisitos que devem estar em vigor para usar o espaço de trabalho **Controle de custos**.</span><span class="sxs-lookup"><span data-stu-id="27691-179">This topic shows the prerequisites that must be in place before you can use the **Cost control** workspace.</span></span>

<span data-ttu-id="27691-180">Consulte também</span><span class="sxs-lookup"><span data-stu-id="27691-180">See also</span></span>

- [<span data-ttu-id="27691-181">Espaço de trabalho de controle de custos</span><span class="sxs-lookup"><span data-stu-id="27691-181">Cost control workspace</span></span>](cost-control-workspace.md)
- [<span data-ttu-id="27691-182">Hierarquia de dimensões</span><span class="sxs-lookup"><span data-stu-id="27691-182">Dimension hierarchy</span></span>](dimension-hierarchy.md)
- [<span data-ttu-id="27691-183">Configurar segurança para o pacote de conteúdo de contabilização de custo</span><span class="sxs-lookup"><span data-stu-id="27691-183">Set up security for Cost accounting content pack</span></span>](../../dev-itpro/analytics/setup-security-cost-accounting-content-pack.md)

