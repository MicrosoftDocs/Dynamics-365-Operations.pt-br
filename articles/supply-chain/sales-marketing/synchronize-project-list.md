---
title: Sincronizar lista de projetos do Finance and Operations no Field Service
description: Este tópico discute os modelos e as tarefas subjacentes usadas para sincronizar projetos do Microsoft Dynamics 365 for Finance and Operations com o Microsoft Dynamics 365 for Field Service.
author: ChristianRytt
manager: AnnBe
ms.date: 01/14/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: 8.1.3
ms.search.validFrom: 2018-12-01
ms.openlocfilehash: b5aeb4c3925994d7488e8e113e88b9d06ee6b350
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "312499"
---
# <a name="synchronize-project-list-from-finance-and-operations-to-field-service"></a><span data-ttu-id="6984f-103">Sincronizar lista de projetos do Finance and Operations no Field Service</span><span class="sxs-lookup"><span data-stu-id="6984f-103">Synchronize project list from Finance and Operations to Field Service</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="6984f-104">Este tópico discute os modelos e as tarefas subjacentes usadas para sincronizar projetos do Microsoft Dynamics 365 for Finance and Operations com o Microsoft Dynamics 365 for Field Service.</span><span class="sxs-lookup"><span data-stu-id="6984f-104">This topic discusses the templates and underlying tasks that are used to synchronize projects from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="6984f-105">[![Sincronização de processos empresariais entre o Finance and Operations e o Field Service](./media/FSProjectOW.png)](./media/FSProjectOW.png)</span><span class="sxs-lookup"><span data-stu-id="6984f-105">[![Synchronization of business processes between Finance and Operations and Field Service](./media/FSProjectOW.png)](./media/FSProjectOW.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="6984f-106">Modelos e tarefas</span><span class="sxs-lookup"><span data-stu-id="6984f-106">Templates and tasks</span></span>
<span data-ttu-id="6984f-107">O modelo a seguir e as tarefas subjacentes são usados para executar a sincronização de projetos do Microsoft Dynamics 365 for Finance and Operations com o Microsoft Dynamics 365 for Field Service.</span><span class="sxs-lookup"><span data-stu-id="6984f-107">The following template and underlying tasks are used to run synchronization of projects from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="6984f-108">**Modelo na integração de dados**</span><span class="sxs-lookup"><span data-stu-id="6984f-108">**Template in Data integration**</span></span>
- <span data-ttu-id="6984f-109">Projetos (Finance and Operations para Field Service)</span><span class="sxs-lookup"><span data-stu-id="6984f-109">Projects (Finance and Operations to Field Service)</span></span>

<span data-ttu-id="6984f-110">**Tarefas no projeto de integração de dados**</span><span class="sxs-lookup"><span data-stu-id="6984f-110">**Task in the Data integration project**</span></span>
- <span data-ttu-id="6984f-111">Projetos</span><span class="sxs-lookup"><span data-stu-id="6984f-111">Projects</span></span>

<span data-ttu-id="6984f-112">As seguintes tarefas de sincronização necessárias antes da sincronização a lista de projetos:</span><span class="sxs-lookup"><span data-stu-id="6984f-112">The following synchronization tasks are required before synchronization of project list can occur:</span></span>
- <span data-ttu-id="6984f-113">Contas (Sales para o Finance and Operations)</span><span class="sxs-lookup"><span data-stu-id="6984f-113">Accounts (Sales to Finance and Operations)</span></span> 

## <a name="entity-set"></a><span data-ttu-id="6984f-114">Conjunto de entidades</span><span class="sxs-lookup"><span data-stu-id="6984f-114">Entity set</span></span>
| <span data-ttu-id="6984f-115">Field Service</span><span class="sxs-lookup"><span data-stu-id="6984f-115">Field Service</span></span>           | <span data-ttu-id="6984f-116">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="6984f-116">Finance and Operations</span></span>  |
|-------------------------|-------------------------|
|<span data-ttu-id="6984f-117">msdynce_externalprojects</span><span class="sxs-lookup"><span data-stu-id="6984f-117">msdynce_externalprojects</span></span> | <span data-ttu-id="6984f-118">Projetos</span><span class="sxs-lookup"><span data-stu-id="6984f-118">Projects</span></span>                |

## <a name="entity-flow"></a><span data-ttu-id="6984f-119">Fluxo de entidades</span><span class="sxs-lookup"><span data-stu-id="6984f-119">Entity flow</span></span>
<span data-ttu-id="6984f-120">Os projetos são criados no Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="6984f-120">Projects are created in Finance and Operations.</span></span> <span data-ttu-id="6984f-121">Os projetos com **Tipo de projeto** definido como **Tempo e material** e **Estágio de projeto** definido como **Em andamento** serão sincronizados com a entidade **Projeto Externo** no Field Service, incluindo número do projeto, nome do projeto, estágio do projeto e informações da conta do cliente.</span><span class="sxs-lookup"><span data-stu-id="6984f-121">Projects with **Project type** set to **Time and material** and **Project stage** set to **In process** will synchronize to the **External Project** entity in Field Service, including Project number, Project name, Project stage, and Customer account information.</span></span> <span data-ttu-id="6984f-122">A lista **Projeto externo** é usada para emparelhar ordens de trabalho do Field Service com projetos do Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="6984f-122">The **External Project** list is used to pair Field service work orders with Finance and Operations projects.</span></span>

## <a name="field-service-crm-solution"></a><span data-ttu-id="6984f-123">Solução Field Service CRM</span><span class="sxs-lookup"><span data-stu-id="6984f-123">Field Service CRM solution</span></span>
<span data-ttu-id="6984f-124">A entidade **Projeto externo** obtém todos os projetos do Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="6984f-124">The **External Project** entity gets all the projects from Finance and Operations.</span></span> <span data-ttu-id="6984f-125">O campo **Projeto externo** foi adicionado à entidade **Ordem de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="6984f-125">The **External Project** field has been added to the **Work Order** entity.</span></span> <span data-ttu-id="6984f-126">Este é um campo de pesquisa, assim, marcando sua ordem de trabalho com um projeto, a ordem de venda será conectada a um projeto no Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="6984f-126">This is a lookup field, so by tagging your work order with a project, the sales order will be connected to a project within Finance and Operations.</span></span> <span data-ttu-id="6984f-127">Depois que o **Status do sistema** mudar de **Aberto - Em Andamento (690.970.000)** para a um status superior, o campo **Projeto externo** será bloqueado e você não poderá mais adicionar, remover ou alterar o valor.</span><span class="sxs-lookup"><span data-stu-id="6984f-127">After the **System Status** changes **Open – In Progress(690,970,000)** to a higher status, the **External Project** field will be locked and you can no longer add, remove, or change the value.</span></span>

## <a name="prerequisites-and-mapping-setup"></a><span data-ttu-id="6984f-128">Pré-requisitos e configuração de mapeamento</span><span class="sxs-lookup"><span data-stu-id="6984f-128">Prerequisites and mapping setup</span></span>
### <a name="finance-and-operations"></a><span data-ttu-id="6984f-129">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="6984f-129">Finance and Operations</span></span>
<span data-ttu-id="6984f-130">Habilitar o controle de alterações para projetos da entidade Dados.</span><span class="sxs-lookup"><span data-stu-id="6984f-130">Enable change tracking for Data entity projects.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="6984f-131">Mapeamento de modelo na Integração de dados</span><span class="sxs-lookup"><span data-stu-id="6984f-131">Template mapping in Data integration</span></span>


### <a name="projects-finance-and-operations-to-field-service-projects"></a><span data-ttu-id="6984f-132">Projetos (Finance and Operations para Field Service): Projetos</span><span class="sxs-lookup"><span data-stu-id="6984f-132">Projects (Finance and Operations to Field Service): Projects</span></span>

<span data-ttu-id="6984f-133">[![Mapeamento de modelo na Integração de dados](./media/FSProject1.png)](./media/FSProject1.png)</span><span class="sxs-lookup"><span data-stu-id="6984f-133">[![Template mapping in Data integration](./media/FSProject1.png)](./media/FSProject1.png)</span></span>
