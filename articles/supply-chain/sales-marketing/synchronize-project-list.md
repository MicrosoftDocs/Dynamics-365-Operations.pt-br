---
title: Sincronizar lista de projetos do Finance and Operations no Field Service
description: Este tópico discute os modelos e as tarefas subjacentes usadas para sincronizar projetos do Microsoft Dynamics 365 for Finance and Operations com o Microsoft Dynamics 365 for Field Service.
author: ChristianRytt
manager: AnnBe
ms.date: 03/13/2019
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
ms.openlocfilehash: ea5c188891bb97ba73d2d022e86bbff50897381b
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2019
ms.locfileid: "1525868"
---
# <a name="synchronize-project-list-from-finance-and-operations-to-field-service"></a><span data-ttu-id="a9227-103">Sincronizar lista de projetos do Finance and Operations no Field Service</span><span class="sxs-lookup"><span data-stu-id="a9227-103">Synchronize project list from Finance and Operations to Field Service</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="a9227-104">Este tópico discute os modelos e as tarefas subjacentes usadas para sincronizar projetos do Microsoft Dynamics 365 for Finance and Operations com o Microsoft Dynamics 365 for Field Service.</span><span class="sxs-lookup"><span data-stu-id="a9227-104">This topic discusses the templates and underlying tasks that are used to synchronize projects from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="a9227-105">[![Sincronização de processos empresariais entre o Finance and Operations e o Field Service](./media/FSProjectOW.png)](./media/FSProjectOW.png)</span><span class="sxs-lookup"><span data-stu-id="a9227-105">[![Synchronization of business processes between Finance and Operations and Field Service](./media/FSProjectOW.png)](./media/FSProjectOW.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="a9227-106">Modelos e tarefas</span><span class="sxs-lookup"><span data-stu-id="a9227-106">Templates and tasks</span></span>
<span data-ttu-id="a9227-107">O modelo a seguir e as tarefas subjacentes são usados para executar a sincronização de projetos do Microsoft Dynamics 365 for Finance and Operations com o Microsoft Dynamics 365 for Field Service.</span><span class="sxs-lookup"><span data-stu-id="a9227-107">The following template and underlying tasks are used to run synchronization of projects from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="a9227-108">**Modelo na integração de dados**</span><span class="sxs-lookup"><span data-stu-id="a9227-108">**Template in Data integration**</span></span>
- <span data-ttu-id="a9227-109">Projetos (Fin and Ops com o Field Service)</span><span class="sxs-lookup"><span data-stu-id="a9227-109">Projects (Fin and Ops to Field Service)</span></span>

<span data-ttu-id="a9227-110">**Tarefas no projeto de integração de dados**</span><span class="sxs-lookup"><span data-stu-id="a9227-110">**Task in the Data integration project**</span></span>
- <span data-ttu-id="a9227-111">Projetos</span><span class="sxs-lookup"><span data-stu-id="a9227-111">Projects</span></span>

<span data-ttu-id="a9227-112">As seguintes tarefas de sincronização necessárias antes da sincronização a lista de projetos:</span><span class="sxs-lookup"><span data-stu-id="a9227-112">The following synchronization tasks are required before synchronization of project list can occur:</span></span>
- <span data-ttu-id="a9227-113">Contas (Sales com o Fin and Ops)</span><span class="sxs-lookup"><span data-stu-id="a9227-113">Accounts (Sales to Fin and Ops)</span></span> 

## <a name="entity-set"></a><span data-ttu-id="a9227-114">Conjunto de entidades</span><span class="sxs-lookup"><span data-stu-id="a9227-114">Entity set</span></span>
| <span data-ttu-id="a9227-115">Field Service</span><span class="sxs-lookup"><span data-stu-id="a9227-115">Field Service</span></span>           | <span data-ttu-id="a9227-116">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="a9227-116">Finance and Operations</span></span>  |
|-------------------------|-------------------------|
|<span data-ttu-id="a9227-117">msdynce_externalprojects</span><span class="sxs-lookup"><span data-stu-id="a9227-117">msdynce_externalprojects</span></span> | <span data-ttu-id="a9227-118">Projetos</span><span class="sxs-lookup"><span data-stu-id="a9227-118">Projects</span></span>                |

## <a name="entity-flow"></a><span data-ttu-id="a9227-119">Fluxo de entidades</span><span class="sxs-lookup"><span data-stu-id="a9227-119">Entity flow</span></span>
<span data-ttu-id="a9227-120">Os projetos são criados no Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="a9227-120">Projects are created in Finance and Operations.</span></span> <span data-ttu-id="a9227-121">Os projetos com **Tipo de projeto** definido como **Tempo e material** e **Estágio de projeto** definido como **Em andamento** serão sincronizados com a entidade **Projeto Externo** no Field Service, incluindo número do projeto, nome do projeto, estágio do projeto e informações da conta do cliente.</span><span class="sxs-lookup"><span data-stu-id="a9227-121">Projects with **Project type** set to **Time and material** and **Project stage** set to **In process** will synchronize to the **External Project** entity in Field Service, including Project number, Project name, Project stage, and Customer account information.</span></span> <span data-ttu-id="a9227-122">A lista **Projeto externo** é usada para emparelhar ordens de trabalho do Field Service com projetos do Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="a9227-122">The **External Project** list is used to pair Field service work orders with Finance and Operations projects.</span></span>

## <a name="field-service-crm-solution"></a><span data-ttu-id="a9227-123">Solução Field Service CRM</span><span class="sxs-lookup"><span data-stu-id="a9227-123">Field Service CRM solution</span></span>
<span data-ttu-id="a9227-124">A entidade **Projeto externo** obtém todos os projetos do Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="a9227-124">The **External Project** entity gets all the projects from Finance and Operations.</span></span> <span data-ttu-id="a9227-125">O campo **Projeto externo** foi adicionado à entidade **Ordem de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="a9227-125">The **External Project** field has been added to the **Work Order** entity.</span></span> <span data-ttu-id="a9227-126">Este é um campo de pesquisa, assim, marcando sua ordem de trabalho com um projeto, a ordem de venda será conectada a um projeto no Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="a9227-126">This is a lookup field, so by tagging your work order with a project, the sales order will be connected to a project within Finance and Operations.</span></span> <span data-ttu-id="a9227-127">Depois que o **Status do sistema** mudar de **Aberto - Em Andamento (690.970.000)** para a um status superior, o campo **Projeto externo** será bloqueado e você não poderá mais adicionar, remover ou alterar o valor.</span><span class="sxs-lookup"><span data-stu-id="a9227-127">After the **System Status** changes **Open – In Progress(690,970,000)** to a higher status, the **External Project** field will be locked and you can no longer add, remove, or change the value.</span></span>

## <a name="prerequisites-and-mapping-setup"></a><span data-ttu-id="a9227-128">Pré-requisitos e configuração de mapeamento</span><span class="sxs-lookup"><span data-stu-id="a9227-128">Prerequisites and mapping setup</span></span>
### <a name="finance-and-operations"></a><span data-ttu-id="a9227-129">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="a9227-129">Finance and Operations</span></span>
<span data-ttu-id="a9227-130">Habilitar o controle de alterações para projetos da entidade Dados.</span><span class="sxs-lookup"><span data-stu-id="a9227-130">Enable change tracking for Data entity projects.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="a9227-131">Mapeamento de modelo na Integração de dados</span><span class="sxs-lookup"><span data-stu-id="a9227-131">Template mapping in Data integration</span></span>


### <a name="projects-fin-and-ops-to-field-service-projects"></a><span data-ttu-id="a9227-132">Projetos (Fin and Ops com o Field Service): Projetos</span><span class="sxs-lookup"><span data-stu-id="a9227-132">Projects (Fin and Ops to Field Service): Projects</span></span>

<span data-ttu-id="a9227-133">[![Mapeamento de modelo na Integração de dados](./media/FSProject1.png)](./media/FSProject1.png)</span><span class="sxs-lookup"><span data-stu-id="a9227-133">[![Template mapping in Data integration](./media/FSProject1.png)](./media/FSProject1.png)</span></span>
