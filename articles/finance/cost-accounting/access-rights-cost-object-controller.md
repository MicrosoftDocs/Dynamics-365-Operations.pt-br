---
title: Definir direitos de acesso para controladores do objeto de custo
description: Este tópico fornece informações sobre direitos de acesso para controladores do objeto de custo.
author: AndersGirke
manager: AnnBe
ms.date: 06/24/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CAMCostControlWorkspace, CAMParameters
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: shylaw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: e86f087a1df0f133dbaa5491cf5ba9e57b0e12d9
ms.sourcegitcommit: 75db3b75d35d27034f9b56e7119c9d0cb7666830
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/03/2019
ms.locfileid: "2551717"
---
# <a name="define-access-rights-for-cost-object-controllers"></a><span data-ttu-id="2b219-103">Definir direitos de acesso para controladores do objeto de custo</span><span class="sxs-lookup"><span data-stu-id="2b219-103">Define access rights for cost object controllers</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2b219-104">O espaço trabalho **Controle de custos** é uma empresa central onde os gerentes podem exibir o desempenho de seus objetos de custo.</span><span class="sxs-lookup"><span data-stu-id="2b219-104">The **Cost control** workspace is a central point where managers can view the performance of their cost objects.</span></span> <span data-ttu-id="2b219-105">Este espaço de trabalho permite que os gerentes consumam dados da contabilidade de custo mesmo que não sejam contadores.</span><span class="sxs-lookup"><span data-stu-id="2b219-105">This workspace lets managers consume Cost accounting data even though they aren't cost accountants.</span></span> <span data-ttu-id="2b219-106">Por motivo de segurança, gerentes somente podem consultar os dados da contabilidade de custo relacionados a objetos específicos de custo pelos quais eles são responsáveis.</span><span class="sxs-lookup"><span data-stu-id="2b219-106">For security reasons, managers should be allowed to see only the Cost accounting data that is related to the specific cost objects that they are responsible for.</span></span>

<span data-ttu-id="2b219-107">Existem quatro funções exclusivas na contabilização de custos.</span><span class="sxs-lookup"><span data-stu-id="2b219-107">There are four unique roles in Cost accounting.</span></span>

| <span data-ttu-id="2b219-108">Nome da função</span><span class="sxs-lookup"><span data-stu-id="2b219-108">Role name</span></span>               | <span data-ttu-id="2b219-109">Licença</span><span class="sxs-lookup"><span data-stu-id="2b219-109">License</span></span>      |
|-------------------------|--------------|
| <span data-ttu-id="2b219-110">Gerenciador de contabilização de custos</span><span class="sxs-lookup"><span data-stu-id="2b219-110">Cost accounting manager</span></span> | <span data-ttu-id="2b219-111">Atividade</span><span class="sxs-lookup"><span data-stu-id="2b219-111">Activity</span></span>     |
| <span data-ttu-id="2b219-112">Contador de custos</span><span class="sxs-lookup"><span data-stu-id="2b219-112">Cost accountant</span></span>         | <span data-ttu-id="2b219-113">Operations</span><span class="sxs-lookup"><span data-stu-id="2b219-113">Operations</span></span>   |
| <span data-ttu-id="2b219-114">Contador de custos</span><span class="sxs-lookup"><span data-stu-id="2b219-114">Cost accountant clerk</span></span>   | <span data-ttu-id="2b219-115">Operations</span><span class="sxs-lookup"><span data-stu-id="2b219-115">Operations</span></span>   |
| <span data-ttu-id="2b219-116">Controlador do objeto de custo</span><span class="sxs-lookup"><span data-stu-id="2b219-116">Cost object controller</span></span>  | <span data-ttu-id="2b219-117">Membros da equipe</span><span class="sxs-lookup"><span data-stu-id="2b219-117">Team members</span></span> |

<span data-ttu-id="2b219-118">Este tópico explica como atribuir a função **Controlador do objeto de custo** a um gerente.</span><span class="sxs-lookup"><span data-stu-id="2b219-118">This topic explains how to assign the **Cost object controller** role to a manager.</span></span>

<span data-ttu-id="2b219-119">Quando a função **Controlador do objeto de custo** for designada a um gerente, ele poderá executar as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="2b219-119">When the **Cost object controller** role is assigned to a manager, the manager can perform the following tasks:</span></span>

- <span data-ttu-id="2b219-120">Acessar o espaço de trabalho **Controle de custo** (no cliente).</span><span class="sxs-lookup"><span data-stu-id="2b219-120">Access the **Cost control** workspace (in the client).</span></span>

    - <span data-ttu-id="2b219-121">Detalhar e ter acesso de exibição às páginas que suportam a experiência detalhada.</span><span class="sxs-lookup"><span data-stu-id="2b219-121">Drill through and have view access to the pages that support the drill-through experience.</span></span>

- <span data-ttu-id="2b219-122">Acessar o espaço de trabalho **Controle de custo** (no aplicativo móvel).</span><span class="sxs-lookup"><span data-stu-id="2b219-122">Access the **Cost control** workspace (in the mobile application).</span></span>

> [!NOTE]
> <span data-ttu-id="2b219-123">A função **Controlador do objeto de custo** não controla os objetos de custo pelo qual o usuário pode acessar e exibir dados.</span><span class="sxs-lookup"><span data-stu-id="2b219-123">The **Cost object controller** role doesn't control which cost objects the user can access and view data for.</span></span> <span data-ttu-id="2b219-124">A segurança em nível de linha é fornecida por meio das hierarquias de dimensões e de hierarquia de lista de acesso.</span><span class="sxs-lookup"><span data-stu-id="2b219-124">Row-level security is provided via dimension hierarchies and the Access list hierarchy.</span></span>

## <a name="grant-access-rights"></a><span data-ttu-id="2b219-125">Conceder direitos de acesso</span><span class="sxs-lookup"><span data-stu-id="2b219-125">Grant access rights</span></span>
<span data-ttu-id="2b219-126">O exemplo a seguir mostra como pode ser uma hierarquia de dimensões.</span><span class="sxs-lookup"><span data-stu-id="2b219-126">The following example shows what a dimension hierarchy can look like.</span></span>

<span data-ttu-id="2b219-127">**Detalhes de hierarquias de dimensão**</span><span class="sxs-lookup"><span data-stu-id="2b219-127">**Dimension hierarchy details**</span></span>

| <span data-ttu-id="2b219-128">Nome de hierarquia de dimensões</span><span class="sxs-lookup"><span data-stu-id="2b219-128">Dimension hierarchy name</span></span> | <span data-ttu-id="2b219-129">Dimensão</span><span class="sxs-lookup"><span data-stu-id="2b219-129">Dimension</span></span>    | <span data-ttu-id="2b219-130">Nome do tipo de hierarquia de dimensões</span><span class="sxs-lookup"><span data-stu-id="2b219-130">Dimension hierarchy type name</span></span>      | <span data-ttu-id="2b219-131">Acessar hierarquia de lista</span><span class="sxs-lookup"><span data-stu-id="2b219-131">Access list hierarchy</span></span> |
|--------------------------|--------------|------------------------------------|-----------------------|
| <span data-ttu-id="2b219-132">Organização</span><span class="sxs-lookup"><span data-stu-id="2b219-132">Organization</span></span>             | <span data-ttu-id="2b219-133">Centros de custos</span><span class="sxs-lookup"><span data-stu-id="2b219-133">Cost centers</span></span> | <span data-ttu-id="2b219-134">Hierarquia de classificação de dimensões</span><span class="sxs-lookup"><span data-stu-id="2b219-134">Dimension classification hierarchy</span></span> | <span data-ttu-id="2b219-135">**Sim**</span><span class="sxs-lookup"><span data-stu-id="2b219-135">**Yes**</span></span>               |

<span data-ttu-id="2b219-136">Você pode usar a Guia Rápida **Usuários** no designer de hierarquia para inserir uma ou várias ids de usuário em cada nó.</span><span class="sxs-lookup"><span data-stu-id="2b219-136">You can use the **Users** FastTab in the hierarchy designer to insert one or more user IDs on each node.</span></span>

|                                   | <span data-ttu-id="2b219-137">Usuários</span><span class="sxs-lookup"><span data-stu-id="2b219-137">Users</span></span>            | <span data-ttu-id="2b219-138">Intervalos de membros de dimensão</span><span class="sxs-lookup"><span data-stu-id="2b219-138">Dimension member ranges</span></span>   |                         |
|-----------------------------------|------------------|---------------------------|-------------------------|
| <span data-ttu-id="2b219-139">**Nós**</span><span class="sxs-lookup"><span data-stu-id="2b219-139">**Nodes**</span></span>                         | <span data-ttu-id="2b219-140">**ID do Usuário**</span><span class="sxs-lookup"><span data-stu-id="2b219-140">**User ID**</span></span>      | <span data-ttu-id="2b219-141">**Membro da dimensão de origem**</span><span class="sxs-lookup"><span data-stu-id="2b219-141">**From dimension member**</span></span> | <span data-ttu-id="2b219-142">**Membro da dimensão de destino**</span><span class="sxs-lookup"><span data-stu-id="2b219-142">**To dimension member**</span></span> |
| <span data-ttu-id="2b219-143">Organização</span><span class="sxs-lookup"><span data-stu-id="2b219-143">Organization</span></span>                      | <span data-ttu-id="2b219-144">Benjamin, Claire</span><span class="sxs-lookup"><span data-stu-id="2b219-144">Benjamin, Claire</span></span> |                           |                         |
| <span data-ttu-id="2b219-145">&nbsp;&nbsp;Administrador</span><span class="sxs-lookup"><span data-stu-id="2b219-145">&nbsp;&nbsp;Admin</span></span>                 | <span data-ttu-id="2b219-146">Abril</span><span class="sxs-lookup"><span data-stu-id="2b219-146">April</span></span>            |                           |                         |
| <span data-ttu-id="2b219-147">&nbsp;&nbsp;&nbsp;&nbsp;Finanças</span><span class="sxs-lookup"><span data-stu-id="2b219-147">&nbsp;&nbsp;&nbsp;&nbsp;Finance</span></span>   | <span data-ttu-id="2b219-148">Alicia</span><span class="sxs-lookup"><span data-stu-id="2b219-148">Alicia</span></span>           | <span data-ttu-id="2b219-149">CC002</span><span class="sxs-lookup"><span data-stu-id="2b219-149">CC002</span></span>                     | <span data-ttu-id="2b219-150">CC003</span><span class="sxs-lookup"><span data-stu-id="2b219-150">CC003</span></span>                   |
|                                   |                  | <span data-ttu-id="2b219-151">CC007</span><span class="sxs-lookup"><span data-stu-id="2b219-151">CC007</span></span>                     | <span data-ttu-id="2b219-152">CC007</span><span class="sxs-lookup"><span data-stu-id="2b219-152">CC007</span></span>                   |
| <span data-ttu-id="2b219-153">&nbsp;&nbsp;&nbsp;&nbsp;RH</span><span class="sxs-lookup"><span data-stu-id="2b219-153">&nbsp;&nbsp;&nbsp;&nbsp;HR</span></span>        | <span data-ttu-id="2b219-154">Arnie</span><span class="sxs-lookup"><span data-stu-id="2b219-154">Arnie</span></span>            | <span data-ttu-id="2b219-155">CC001</span><span class="sxs-lookup"><span data-stu-id="2b219-155">CC001</span></span>                     | <span data-ttu-id="2b219-156">CC001</span><span class="sxs-lookup"><span data-stu-id="2b219-156">CC001</span></span>                   |
| <span data-ttu-id="2b219-157">&nbsp;&nbsp;Produção</span><span class="sxs-lookup"><span data-stu-id="2b219-157">&nbsp;&nbsp;Production</span></span>            | <span data-ttu-id="2b219-158">David</span><span class="sxs-lookup"><span data-stu-id="2b219-158">David</span></span>            |                           |                         |
| <span data-ttu-id="2b219-159">&nbsp;&nbsp;&nbsp;&nbsp;Embalagem</span><span class="sxs-lookup"><span data-stu-id="2b219-159">&nbsp;&nbsp;&nbsp;&nbsp;Packaging</span></span> | <span data-ttu-id="2b219-160">Ellen</span><span class="sxs-lookup"><span data-stu-id="2b219-160">Ellen</span></span>            | <span data-ttu-id="2b219-161">CC005</span><span class="sxs-lookup"><span data-stu-id="2b219-161">CC005</span></span>                     | <span data-ttu-id="2b219-162">CC005</span><span class="sxs-lookup"><span data-stu-id="2b219-162">CC005</span></span>                   |
| <span data-ttu-id="2b219-163">&nbsp;&nbsp;&nbsp;&nbsp;Montagem</span><span class="sxs-lookup"><span data-stu-id="2b219-163">&nbsp;&nbsp;&nbsp;&nbsp;Assembly</span></span>  | <span data-ttu-id="2b219-164">Chris</span><span class="sxs-lookup"><span data-stu-id="2b219-164">Chris</span></span>            | <span data-ttu-id="2b219-165">CC006</span><span class="sxs-lookup"><span data-stu-id="2b219-165">CC006</span></span>                     | <span data-ttu-id="2b219-166">CC006</span><span class="sxs-lookup"><span data-stu-id="2b219-166">CC006</span></span>                   |

> [!NOTE]
> <span data-ttu-id="2b219-167">Os contadores devem ser atribuídos ao nível de hierarquia superior para que possam consultar todas as entradas na contabilização de custo.</span><span class="sxs-lookup"><span data-stu-id="2b219-167">Cost accountants should be assigned to the top level of the hierarchy, so that they can see all entries in Cost accounting.</span></span>

<span data-ttu-id="2b219-168">Antes da hierarquia da lista de acesso e de suas configurações de segurança serem aplicadas, a opção **Habilitar acesso de visualização para membros de dimensão de objeto de custo** deve ser definida como **Sim** na guia **Geral** da página **Parâmetros de contabilização de custos** (**Contabilização de custo** > **Configuração** > **Parâmetros**).</span><span class="sxs-lookup"><span data-stu-id="2b219-168">Before the Access list hierarchy and its security settings can be applied, the **Enable view access for cost object dimension members** option must be set to **Yes** on the **General** tab of the **Cost accounting parameters** page (**Cost accounting** > **Setup** > **Parameters**).</span></span>

<span data-ttu-id="2b219-169">As configurações da hierarquia da lista de acesso são usadas para controlar os dados que são mostrados nas seguintes áreas:</span><span class="sxs-lookup"><span data-stu-id="2b219-169">The settings for the Access list hierarchy are used to control the data that is shown in following areas:</span></span>

- <span data-ttu-id="2b219-170">Espaço de trabalho **Controle de custo** (no cliente):</span><span class="sxs-lookup"><span data-stu-id="2b219-170">**Cost control** workspace (in the client):</span></span>

    - <span data-ttu-id="2b219-171">Dados nas páginas usadas para o detalhamento</span><span class="sxs-lookup"><span data-stu-id="2b219-171">Data on the pages that are used for drill-through</span></span>

- <span data-ttu-id="2b219-172">Espaço de trabalho **Controle de custo** (no aplicativo móvel):</span><span class="sxs-lookup"><span data-stu-id="2b219-172">**Cost control** workspace (in the mobile application):</span></span>

    - <span data-ttu-id="2b219-173">Saldos em cartões</span><span class="sxs-lookup"><span data-stu-id="2b219-173">Balances in cards</span></span>

- <span data-ttu-id="2b219-174">Microsoft Power BI:</span><span class="sxs-lookup"><span data-stu-id="2b219-174">Microsoft Power BI:</span></span>

    - <span data-ttu-id="2b219-175">Dados mostrados em visualizações do Power BI</span><span class="sxs-lookup"><span data-stu-id="2b219-175">Data that is shown in Power BI visualizations</span></span>
    - <span data-ttu-id="2b219-176">Visualizações de dados do Power BI incorporadas no cliente do Dynamics 365 Finance</span><span class="sxs-lookup"><span data-stu-id="2b219-176">Data Power BI visualizations that are embedded in the Dynamics 365 Finance client</span></span>

> [!IMPORTANT]
> - <span data-ttu-id="2b219-177">Antes que a hierarquia da lista de acesso possa afetar os dados no Power BI, a hierarquia da lista de acesso e a segurança em nível de linha no Power BI devem ser emparelhadas.</span><span class="sxs-lookup"><span data-stu-id="2b219-177">Before the Access list hierarchy can affect data in Power BI, the Access list hierarchy and row-level security in Power BI must be paired.</span></span> <span data-ttu-id="2b219-178">Para obter mais informações, consulte [Configurar segurança para o pacote de conteúdo de contabilização de custo](../../dev-itpro/analytics/setup-security-cost-accounting-content-pack.md).</span><span class="sxs-lookup"><span data-stu-id="2b219-178">For more information, see [Set up security for Cost accounting content pack](../../dev-itpro/analytics/setup-security-cost-accounting-content-pack.md).</span></span>
> - <span data-ttu-id="2b219-179">Esta seção mostra os pré-requisitos que devem estar em vigor para usar o espaço de trabalho **Controle de custos**.</span><span class="sxs-lookup"><span data-stu-id="2b219-179">This topic shows the prerequisites that must be in place before you can use the **Cost control** workspace.</span></span>

<span data-ttu-id="2b219-180">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="2b219-180">Additional resources</span></span>

- [<span data-ttu-id="2b219-181">Espaço de trabalho de controle de custos</span><span class="sxs-lookup"><span data-stu-id="2b219-181">Cost control workspace</span></span>](cost-control-workspace.md)
- [<span data-ttu-id="2b219-182">Hierarquia da dimensão</span><span class="sxs-lookup"><span data-stu-id="2b219-182">Dimension hierarchy</span></span>](dimension-hierarchy.md)
- [<span data-ttu-id="2b219-183">Configurar segurança para o pacote de conteúdo de contabilização de custo</span><span class="sxs-lookup"><span data-stu-id="2b219-183">Set up security for Cost accounting content pack</span></span>](../../dev-itpro/analytics/setup-security-cost-accounting-content-pack.md)