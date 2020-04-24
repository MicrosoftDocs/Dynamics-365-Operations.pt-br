---
title: Sincronizar lista de projetos do Supply Chain Management com o Field Service
description: Este tópico discute os modelos e as tarefas subjacentes usadas para sincronizar projetos do Dynamics 365 Supply Chain Management com o Dynamics 365 Field Service.
author: ChristianRytt
manager: tfehr
ms.date: 03/13/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: 8.1.3
ms.search.validFrom: 2018-12-01
ms.openlocfilehash: d80fce409ee92973a6134d96ce839b9722980918
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3215921"
---
# <a name="synchronize-project-list-from-supply-chain-management-to-field-service"></a><span data-ttu-id="39545-103">Sincronizar lista de projetos do Supply Chain Management com o Field Service</span><span class="sxs-lookup"><span data-stu-id="39545-103">Synchronize project list from Supply Chain Management to Field Service</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="39545-104">Este tópico discute os modelos e as tarefas subjacentes usadas para sincronizar projetos do Dynamics 365 Supply Chain Management com o Dynamics 365 Field Service.</span><span class="sxs-lookup"><span data-stu-id="39545-104">This topic discusses the templates and underlying tasks that are used to synchronize projects from Dynamics 365 Supply Chain Management to Dynamics 365 Field Service.</span></span>

<span data-ttu-id="39545-105">[![Sincronização de processos empresariais entre o Supply Chain Management e o Field Service](./media/FSProjectOW.png)](./media/FSProjectOW.png)</span><span class="sxs-lookup"><span data-stu-id="39545-105">[![Synchronization of business processes between Supply Chain Management and Field Service](./media/FSProjectOW.png)](./media/FSProjectOW.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="39545-106">Modelos e tarefas</span><span class="sxs-lookup"><span data-stu-id="39545-106">Templates and tasks</span></span>
<span data-ttu-id="39545-107">O modelo a seguir e as tarefas subjacentes são usados para executar a sincronização de projetos do Supply Chain Management com o Field Service.</span><span class="sxs-lookup"><span data-stu-id="39545-107">The following template and underlying tasks are used to run synchronization of projects from Supply Chain Management to Field Service.</span></span>

<span data-ttu-id="39545-108">**Modelo na integração de dados**</span><span class="sxs-lookup"><span data-stu-id="39545-108">**Template in Data integration**</span></span>
- <span data-ttu-id="39545-109">Projetos (Supply Chain Management para Field Service)</span><span class="sxs-lookup"><span data-stu-id="39545-109">Projects (Supply Chain Management to Field Service)</span></span>

<span data-ttu-id="39545-110">**Tarefas no projeto de integração de dados**</span><span class="sxs-lookup"><span data-stu-id="39545-110">**Task in the Data integration project**</span></span>
- <span data-ttu-id="39545-111">Projetos</span><span class="sxs-lookup"><span data-stu-id="39545-111">Projects</span></span>

<span data-ttu-id="39545-112">As seguintes tarefas de sincronização necessárias antes da sincronização a lista de projetos:</span><span class="sxs-lookup"><span data-stu-id="39545-112">The following synchronization tasks are required before synchronization of project list can occur:</span></span>
- <span data-ttu-id="39545-113">Contas (Sales para Supply Chain Management)</span><span class="sxs-lookup"><span data-stu-id="39545-113">Accounts (Sales to Supply Chain Management)</span></span> 

## <a name="entity-set"></a><span data-ttu-id="39545-114">Conjunto de entidades</span><span class="sxs-lookup"><span data-stu-id="39545-114">Entity set</span></span>
| <span data-ttu-id="39545-115">Field Service</span><span class="sxs-lookup"><span data-stu-id="39545-115">Field Service</span></span>           | <span data-ttu-id="39545-116">Gerenciamento da Cadeia de Fornecedores</span><span class="sxs-lookup"><span data-stu-id="39545-116">Supply Chain Management</span></span>  |
|-------------------------|-------------------------|
|<span data-ttu-id="39545-117">msdynce_externalprojects</span><span class="sxs-lookup"><span data-stu-id="39545-117">msdynce_externalprojects</span></span> | <span data-ttu-id="39545-118">Projetos</span><span class="sxs-lookup"><span data-stu-id="39545-118">Projects</span></span>                |

## <a name="entity-flow"></a><span data-ttu-id="39545-119">Fluxo de entidades</span><span class="sxs-lookup"><span data-stu-id="39545-119">Entity flow</span></span>
<span data-ttu-id="39545-120">Os projetos são criados no Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="39545-120">Projects are created in Supply Chain Management.</span></span> <span data-ttu-id="39545-121">Os projetos com **Tipo de projeto** definido como **Tempo e material** e **Estágio de projeto** definido como **Em andamento** serão sincronizados com a entidade **Projeto Externo** no Field Service, incluindo número do projeto, nome do projeto, estágio do projeto e informações da conta do cliente.</span><span class="sxs-lookup"><span data-stu-id="39545-121">Projects with **Project type** set to **Time and material** and **Project stage** set to **In process** will synchronize to the **External Project** entity in Field Service, including Project number, Project name, Project stage, and Customer account information.</span></span> <span data-ttu-id="39545-122">A lista **Projeto Externo** é usada para emparelhar ordens de serviço do Field Service com projetos do Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="39545-122">The **External Project** list is used to pair Field service work orders with Supply Chain Management projects.</span></span>

## <a name="field-service-crm-solution"></a><span data-ttu-id="39545-123">Solução Field Service CRM</span><span class="sxs-lookup"><span data-stu-id="39545-123">Field Service CRM solution</span></span>
<span data-ttu-id="39545-124">A entidade **Projeto Externo** obtém todos os projetos do Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="39545-124">The **External Project** entity gets all the projects from Supply Chain Management.</span></span> <span data-ttu-id="39545-125">O campo **Projeto externo** foi adicionado à entidade **Ordem de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="39545-125">The **External Project** field has been added to the **Work Order** entity.</span></span> <span data-ttu-id="39545-126">Este campo é uma pesquisa, portanto, ao marcar sua ordem de serviço com um projeto, a ordem de venda será conectada a um projeto no Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="39545-126">This is a lookup field, so by tagging your work order with a project, the sales order will be connected to a project within Supply Chain Management.</span></span> <span data-ttu-id="39545-127">Depois que o **Status do sistema** mudar de **Aberto - Em Andamento (690.970.000)** para a um status superior, o campo **Projeto externo** será bloqueado e você não poderá mais adicionar, remover ou alterar o valor.</span><span class="sxs-lookup"><span data-stu-id="39545-127">After the **System Status** changes **Open – In Progress(690,970,000)** to a higher status, the **External Project** field will be locked and you can no longer add, remove, or change the value.</span></span>

## <a name="prerequisites-and-mapping-setup"></a><span data-ttu-id="39545-128">Pré-requisitos e configuração de mapeamento</span><span class="sxs-lookup"><span data-stu-id="39545-128">Prerequisites and mapping setup</span></span>
### <a name="supply-chain-management"></a><span data-ttu-id="39545-129">Gerenciamento da Cadeia de Fornecedores</span><span class="sxs-lookup"><span data-stu-id="39545-129">Supply Chain Management</span></span>
<span data-ttu-id="39545-130">Habilitar o controle de alterações para projetos da entidade Dados.</span><span class="sxs-lookup"><span data-stu-id="39545-130">Enable change tracking for Data entity projects.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="39545-131">Mapeamento de modelo na Integração de dados</span><span class="sxs-lookup"><span data-stu-id="39545-131">Template mapping in Data integration</span></span>


### <a name="projects-supply-chain-management-to-field-service-projects"></a><span data-ttu-id="39545-132">Projetos (Supply Chain Management para Field Service): Projetos</span><span class="sxs-lookup"><span data-stu-id="39545-132">Projects (Supply Chain Management to Field Service): Projects</span></span>

<span data-ttu-id="39545-133">[![Mapeamento de modelo na Integração de dados](./media/FSProject1.png)](./media/FSProject1.png)</span><span class="sxs-lookup"><span data-stu-id="39545-133">[![Template mapping in Data integration](./media/FSProject1.png)](./media/FSProject1.png)</span></span>
