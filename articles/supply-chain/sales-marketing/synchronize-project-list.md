---
title: Sincronizar lista de projetos do Finance and Operations no Field Service
description: "Este tópico discute os modelos e as tarefas subjacente usados para sincronizar projetos do Microsoft Dynamics 365 for Finance and Operations com o Microsoft Dynamics 365 for Field Service."
author: ChristianRytt
manager: AnnBe
ms.date: 12/20/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User, IT Pro
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: crytt
ms.dyn365.ops.version: 8.1.3
ms.search.validFrom: 2018-12-01
ms.translationtype: HT
ms.sourcegitcommit: 8c6cb481f1a3fe48d329c5936118d8df88a4175b
ms.openlocfilehash: adcb1c1b241ce2b073cd26cf2a8a8d64931c8b0f
ms.contentlocale: pt-br
ms.lasthandoff: 12/20/2018

---

# <a name="synchronize-project-list-from-finance-and-operations-to-field-service"></a><span data-ttu-id="25400-103">Sincronizar lista de projetos do Finance and Operations no Field Service</span><span class="sxs-lookup"><span data-stu-id="25400-103">Synchronize project list from Finance and Operations to Field Service</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="25400-104">Este tópico discute os modelos e as tarefas subjacente usados para sincronizar projetos do Microsoft Dynamics 365 for Finance and Operations com o Microsoft Dynamics 365 for Field Service.</span><span class="sxs-lookup"><span data-stu-id="25400-104">This topic discusses the templates and underlying tasks that are used to synchronize projects from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="25400-105">[![Sincronização de processos empresariais entre o Finance and Operations e o Field Service](./media/FSProjectOW.png)](./media/FSProjectOW.png)</span><span class="sxs-lookup"><span data-stu-id="25400-105">[![Synchronization of business processes between Finance and Operations and Field Service](./media/FSProjectOW.png)](./media/FSProjectOW.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="25400-106">Modelos e tarefas</span><span class="sxs-lookup"><span data-stu-id="25400-106">Templates and tasks</span></span>
<span data-ttu-id="25400-107">O modelo e as tarefas subjacentes a seguir são usados para executar a sincronização de projetos do Microsoft Dynamics 365 for Finance and Operations para o Microsoft Dynamics 365 for Field Service.</span><span class="sxs-lookup"><span data-stu-id="25400-107">The following template and underlying tasks are used to run synchronization of projects from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="25400-108">**Nome do modelo na Integração de dados:**</span><span class="sxs-lookup"><span data-stu-id="25400-108">**Name of the template in Data integration:**</span></span>
- <span data-ttu-id="25400-109">Projetos (Finance and Operations para Field Service)</span><span class="sxs-lookup"><span data-stu-id="25400-109">Projects (Finance and Operations to Field Service)</span></span>

<span data-ttu-id="25400-110">**Nomes das tarefas no projeto de Integração de dados:**</span><span class="sxs-lookup"><span data-stu-id="25400-110">**Names of the tasks in the Data integration project:**</span></span>
- <span data-ttu-id="25400-111">Projetos</span><span class="sxs-lookup"><span data-stu-id="25400-111">Projects</span></span>

<span data-ttu-id="25400-112">As seguintes tarefas de sincronização necessárias antes da sincronização a lista de projetos:</span><span class="sxs-lookup"><span data-stu-id="25400-112">The following synchronization tasks are required before synchronization of project list can occur:</span></span>
- <span data-ttu-id="25400-113">Contas (Sales para o Finance and Operations)</span><span class="sxs-lookup"><span data-stu-id="25400-113">Accounts (Sales to Finance and Operations)</span></span> 

## <a name="entity-set"></a><span data-ttu-id="25400-114">Conjunto de entidades</span><span class="sxs-lookup"><span data-stu-id="25400-114">Entity set</span></span>
<span data-ttu-id="25400-115">Field Service   Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="25400-115">Field Service   Finance and Operations</span></span>

| <span data-ttu-id="25400-116">Field Service</span><span class="sxs-lookup"><span data-stu-id="25400-116">Field Service</span></span>           | <span data-ttu-id="25400-117">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="25400-117">Finance and Operations</span></span>  |
|-------------------------|-------------------------|
|<span data-ttu-id="25400-118">msdynce_externalprojects</span><span class="sxs-lookup"><span data-stu-id="25400-118">msdynce_externalprojects</span></span> | <span data-ttu-id="25400-119">Projetos</span><span class="sxs-lookup"><span data-stu-id="25400-119">Projects</span></span>                |

## <a name="entity-flow"></a><span data-ttu-id="25400-120">Fluxo de entidades</span><span class="sxs-lookup"><span data-stu-id="25400-120">Entity flow</span></span>
<span data-ttu-id="25400-121">Os projetos são criados no Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="25400-121">Projects are created in Finance and Operations.</span></span> <span data-ttu-id="25400-122">Os projetos de tempo e material **Tipo de projeto** e **Estágio de projeto** em andamento serão sincronizados para a entidade **Projeto Externo** no Field Service, incluindo número do projeto, nome do projeto, estágio do projeto e informações da conta do cliente.</span><span class="sxs-lookup"><span data-stu-id="25400-122">Projects with **Project type** Time and material and **Project stage** In process will synchronize to the **External Project** entity in Field Service, including Project number, Project name, Project stage and Customer account information.</span></span> <span data-ttu-id="25400-123">A lista **Projeto Externo** é usada para emparelhar ordens de trabalho do Field Service com projetos do Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="25400-123">The list of **External Project** is used to pair Field service Work orders with Finance and Operations projects.</span></span>
<span data-ttu-id="25400-124">A solução CRM do Field Service: o projeto externo é uma nova entidade que obtém todos os projetos de operações.</span><span class="sxs-lookup"><span data-stu-id="25400-124">Field Service CRM solution The External Project is a new entity that gets all the Projects from Operations.</span></span>
<span data-ttu-id="25400-125">O campo Projeto Externo foi adicionado à entidade de Ordem de Trabalho.</span><span class="sxs-lookup"><span data-stu-id="25400-125">The External Project field has been added to the Work Order entity.</span></span> <span data-ttu-id="25400-126">Este campo é uma pesquisa e compra que marca sua ordem de trabalho com um projeto. A ordem de venda será conectada a um projeto em operações.</span><span class="sxs-lookup"><span data-stu-id="25400-126">This field is a lookup and buy tagging your Work Order with a project the Sales Order will then be connected to a Project within Operations.</span></span> <span data-ttu-id="25400-127">Quando o status do sistema mudar de Aberto - Em Andamento (690,970,000) para a um status superior, o campo Projeto Externo será bloqueado e você não poderá adicionar, remover ou alterar o valor.</span><span class="sxs-lookup"><span data-stu-id="25400-127">Ones the System Status changes Open – In Progress(690,970,000) to a higher status the External Project field will be locked and you can't add, remove or change the value.</span></span>

## <a name="prerequisites-and-mapping-setup"></a><span data-ttu-id="25400-128">Pré-requisitos e configuração de mapeamento</span><span class="sxs-lookup"><span data-stu-id="25400-128">Prerequisites and mapping setup</span></span>
### <a name="in-finance-and-operations"></a><span data-ttu-id="25400-129">No Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="25400-129">In Finance and Operations</span></span>
<span data-ttu-id="25400-130">Habilitar o controle de alterações para projetos da entidade Dados</span><span class="sxs-lookup"><span data-stu-id="25400-130">Enable change tracking for Data entity Projects</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="25400-131">Mapeamento de modelo na Integração de dados</span><span class="sxs-lookup"><span data-stu-id="25400-131">Template mapping in Data integration</span></span>


### <a name="projects-finance-and-operations-to-field-service-projects"></a><span data-ttu-id="25400-132">Projetos (Finance and Operations para Field Service): Projetos</span><span class="sxs-lookup"><span data-stu-id="25400-132">Projects (Finance and Operations to Field Service): Projects</span></span>

<span data-ttu-id="25400-133">[![Mapeamento de modelo na Integração de dados](./media/FSProject1.png)](./media/FSProject1.png)</span><span class="sxs-lookup"><span data-stu-id="25400-133">[![Template mapping in Data integration](./media/FSProject1.png)](./media/FSProject1.png)</span></span>

