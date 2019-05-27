---
title: Requisitos da configuração da produção
description: Este artigo fornece informações sobre os requisitos de instalação antes que você possa trabalhar com controle de produção.
author: johanhoffmann
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProdParameters, RouteOpr, RouteOprTable, WorkCalendarTable, WorkTimeTable, WrkCtrTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 55561
ms.assetid: 1953059f-478d-4706-b461-25b89ace5fc3
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b811c11271097f4bb7910c34f7775955abba526d
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1559108"
---
# <a name="production-setup-requirements"></a><span data-ttu-id="60318-103">Requisitos da configuração da produção</span><span class="sxs-lookup"><span data-stu-id="60318-103">Production setup requirements</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="60318-104">Este artigo fornece informações sobre os requisitos de instalação antes que você possa trabalhar com controle de produção.</span><span class="sxs-lookup"><span data-stu-id="60318-104">This article provides information about setup requirements before you can work with Production control.</span></span> 

<span data-ttu-id="60318-105">O controle de produção é integrado a recursos em outros módulos.</span><span class="sxs-lookup"><span data-stu-id="60318-105">Production control is integrated with features in other modules.</span></span> <span data-ttu-id="60318-106">Esta interconectividade permite que você altere as ordens de produção e garante que sejam atualizadas automaticamente em todos os outros processos e cálculos relacionados no sistema.</span><span class="sxs-lookup"><span data-stu-id="60318-106">This interconnectivity lets you change production orders and make sure that they are automatically updated in all other related processes and calculations in the system.</span></span> <span data-ttu-id="60318-107">Os processos de configuração a seguir são listados na ordem em que devem ser concluídos.</span><span class="sxs-lookup"><span data-stu-id="60318-107">The following setup processes are listed in the order that you should complete them in.</span></span>

## <a name="required-baseline-setup-in-other-modules"></a><span data-ttu-id="60318-108">Configuração de linha de base necessária em outros módulos</span><span class="sxs-lookup"><span data-stu-id="60318-108">Required baseline setup in other modules</span></span>
<span data-ttu-id="60318-109">As informações em outros módulos devem ser configuradas antes que você possa trabalhar com Controle de produção.</span><span class="sxs-lookup"><span data-stu-id="60318-109">Information in other modules must be set up before you can work with Production control.</span></span> <span data-ttu-id="60318-110">Esta configuração inclui as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="60318-110">This setup includes the following tasks:</span></span>

-   <span data-ttu-id="60318-111">Configurar as informações gerais sobre a empresa.</span><span class="sxs-lookup"><span data-stu-id="60318-111">Set up general company information.</span></span>
-   <span data-ttu-id="60318-112">Configurar a contabilidade.</span><span class="sxs-lookup"><span data-stu-id="60318-112">Set up the general ledger.</span></span>
-   <span data-ttu-id="60318-113">Definir grupos de itens.</span><span class="sxs-lookup"><span data-stu-id="60318-113">Define item groups.</span></span>
-   <span data-ttu-id="60318-114">Configurar contas contábeis de grupos de itens.</span><span class="sxs-lookup"><span data-stu-id="60318-114">Set up ledger accounts for item groups.</span></span>
-   <span data-ttu-id="60318-115">Configurar a tabela de item de estoque em Gerenciamento de estoque.</span><span class="sxs-lookup"><span data-stu-id="60318-115">Set up the inventory item table in Inventory management.</span></span>
-   <span data-ttu-id="60318-116">Criar listas de materiais (BOMs) e versões de BOM em Gerenciamento de estoque.</span><span class="sxs-lookup"><span data-stu-id="60318-116">Create bills of materials (BOMs) and BOM versions in Inventory management.</span></span>

## <a name="required-calendar-and-resource-setup"></a><span data-ttu-id="60318-117">Configuração necessária de calendário e do recurso</span><span class="sxs-lookup"><span data-stu-id="60318-117">Required calendar and resource setup</span></span>
<span data-ttu-id="60318-118">Antes de usar Controle de produção, abra Administração da organização e crie e defina o calendário e os recursos de operações na seguinte ordem:</span><span class="sxs-lookup"><span data-stu-id="60318-118">Before you use Production control, open Organization administration, and create and define the calendar and operations resources in the following order:</span></span>

1.  <span data-ttu-id="60318-119">**Modelos de horário de trabalho** - configure modelos de horário de trabalho para definir os horários disponíveis para o planejamento da produção.</span><span class="sxs-lookup"><span data-stu-id="60318-119">**Working time templates** – Set up working time templates to define the times that are available for production scheduling.</span></span>
2.  <span data-ttu-id="60318-120">**Calendários** - configure calendários de horário de trabalho para definir os dias do ano que estão disponíveis para o agendamento da produção.</span><span class="sxs-lookup"><span data-stu-id="60318-120">**Calendars** – Set up working time calendars to define the days of the year that are available for production scheduling.</span></span>
3.  <span data-ttu-id="60318-121">**Grupos de recursos** – configure grupos de recursos para agrupar os recursos de operações para obter uma visão geral das habilidades livres quando você executa o agendamento.</span><span class="sxs-lookup"><span data-stu-id="60318-121">**Resource groups** – Set up resource groups to group the operations resources, so that you can get an overview of any free capacity when you run scheduling.</span></span> <span data-ttu-id="60318-122">Você não precisa configurar grupos de recursos antes de configurar recursos de operações.</span><span class="sxs-lookup"><span data-stu-id="60318-122">You don't have to set up resource groups before you set up operations resources.</span></span> <span data-ttu-id="60318-123">No entanto, é recomendável que você compreenda como agrupar recursos ao configurar o Controle de produção.</span><span class="sxs-lookup"><span data-stu-id="60318-123">However, we recommend that you understand how to group resources when you set up Production control.</span></span>
4.  <span data-ttu-id="60318-124">**Recursos** – configure os recursos de operações para definir os recursos usados para completar o processo de produção e para planejar a capacidade.</span><span class="sxs-lookup"><span data-stu-id="60318-124">**Resources** – Set up operations resources to define the resources that are used to complete the production process and plan for capacity.</span></span>

## <a name="required-production-parameters-setup"></a><span data-ttu-id="60318-125">Configuração dos parâmetros de produção necessários</span><span class="sxs-lookup"><span data-stu-id="60318-125">Required production parameters setup</span></span>
<span data-ttu-id="60318-126">**Parâmetros de controle de produção** - configure parâmetros de produção básicos para definir como o sistema processa e lida com as ordens de produção.</span><span class="sxs-lookup"><span data-stu-id="60318-126">**Production control parameters** – Set up basic production parameters to define how the system handles and processes production orders.</span></span> <span data-ttu-id="60318-127">Defina como as ordens de produção são criadas, estimadas, agendadas e consumidas.</span><span class="sxs-lookup"><span data-stu-id="60318-127">Define how production orders are created, estimated, scheduled, and consumed.</span></span> <span data-ttu-id="60318-128">Você também pode selecionar que tipo de comentário você deseja e como a contabilização de custos é concluída.</span><span class="sxs-lookup"><span data-stu-id="60318-128">You can also select what kind of feedback you want and how cost accounting is done.</span></span>

## <a name="required-journal-name-identification"></a><span data-ttu-id="60318-129">Identificação de nome do diário necessário</span><span class="sxs-lookup"><span data-stu-id="60318-129">Required journal name identification</span></span>
<span data-ttu-id="60318-130">**Nomes de diários de produção** – especifique os nomes de diário de produção usados para registrar e lançar transações.</span><span class="sxs-lookup"><span data-stu-id="60318-130">**Production journal names** – Specify the production journal names that are used to record and post transactions.</span></span>

## <a name="setup-if-you-use-operations"></a><span data-ttu-id="60318-131">Configurar se você usa operações</span><span class="sxs-lookup"><span data-stu-id="60318-131">Setup if you use operations</span></span>
<span data-ttu-id="60318-132">As operações representam as atividades específicas que são concluídas para produzir o produto acabado.</span><span class="sxs-lookup"><span data-stu-id="60318-132">Operations represent the specific activities that are completed to produce the finished product.</span></span> <span data-ttu-id="60318-133">**Observação:** você deve conhecer os tipos de atividades necessárias para produzir o item e a ordem e as prioridades dessas atividades.</span><span class="sxs-lookup"><span data-stu-id="60318-133">**Note:** You must know the types of activities that are required in order to produce your item, and the order and priorities of those activities.</span></span> <span data-ttu-id="60318-134">Você também deve saber quais recursos estão envolvidos, e quantos.</span><span class="sxs-lookup"><span data-stu-id="60318-134">You must also know which resources are involved, and how many.</span></span>

1.  <span data-ttu-id="60318-135">**Operações** - configure operações para representar as tarefas que devem ser concluídas para produzir o item concluído.</span><span class="sxs-lookup"><span data-stu-id="60318-135">**Operations** – Set up operations to represent the tasks that must be completed to produce the finished item.</span></span>
2.  <span data-ttu-id="60318-136">**Relações** - configure relações de operação para estabelecer propriedades detalhadas.</span><span class="sxs-lookup"><span data-stu-id="60318-136">**Relations** – Set up operation relations to establish detailed properties.</span></span> <span data-ttu-id="60318-137">Para definir relações de operação, clique em **Relações** na página **Operações**.</span><span class="sxs-lookup"><span data-stu-id="60318-137">To define operation relations, click **Relations** on the **Operations** page.</span></span>

## <a name="setup-if-you-use-routes"></a><span data-ttu-id="60318-138">Configurar se você usa roteiros</span><span class="sxs-lookup"><span data-stu-id="60318-138">Setup if you use routes</span></span>
<span data-ttu-id="60318-139">Se você estiver trabalhando com roteiros, as operações deverão ser definidas para todos os roteiros de produção configurados.</span><span class="sxs-lookup"><span data-stu-id="60318-139">If you're working with routes, operations must be defined for every production route that you set up.</span></span> <span data-ttu-id="60318-140">O roteiro representa o caminho traçado pelo item de operação em operação, do início ao fim do processo de produção.</span><span class="sxs-lookup"><span data-stu-id="60318-140">The route represents the path that the item takes from operation to operation, from the start of the production process to the end.</span></span>

1.  <span data-ttu-id="60318-141">**Categorias de custo** - configure categorias de custo para definir o custo por hora dos processos especificados e o tempo de configuração.</span><span class="sxs-lookup"><span data-stu-id="60318-141">**Cost categories** – Set up cost categories to define the cost per hour of specified processes and setup times.</span></span>
2.  <span data-ttu-id="60318-142">**Grupos de custo** - configure grupos de custos para criar e manter tipos diferentes de avaliações de custo.</span><span class="sxs-lookup"><span data-stu-id="60318-142">**Cost groups** – Set up cost groups to create and maintain different types of costing.</span></span>
3.  <span data-ttu-id="60318-143">**Grupos de roteiros** - configure grupos de roteiros para definir parâmetros relacionados a grupos de roteiros.</span><span class="sxs-lookup"><span data-stu-id="60318-143">**Route groups** – Set up route groups to define parameters that are related to groups of routes.</span></span> <span data-ttu-id="60318-144">Você deverá configurar grupos de roteiros antes de criar roteiros de produção.</span><span class="sxs-lookup"><span data-stu-id="60318-144">You must set up route groups before you can create production routes.</span></span>
4.  <span data-ttu-id="60318-145">**Roteiros** - configure roteiros de produção e defina as configurações padrão para controlar o planejamento, os custos e a definição de preços de operações de roteiro, assim como o relatório de progresso.</span><span class="sxs-lookup"><span data-stu-id="60318-145">**Routes** – Set up production routes, and define default settings to control scheduling, costing, and pricing of route operations, and to control progress reporting.</span></span>
5.  <span data-ttu-id="60318-146">**Roteiros** - configure versões de roteiro para habilitar variações de item na produção.</span><span class="sxs-lookup"><span data-stu-id="60318-146">**Routes** – Set up route versions to enable item variations in production.</span></span>

## <a name="optional-advanced-settings"></a><span data-ttu-id="60318-147">Configurações avançadas opcionais</span><span class="sxs-lookup"><span data-stu-id="60318-147">Optional advanced settings</span></span>
1.  <span data-ttu-id="60318-148">**Grupos de produção** - configure grupos de produção para estabelecer relações entre a ordem de produção e as contas contábeis.</span><span class="sxs-lookup"><span data-stu-id="60318-148">**Production groups** – Set up production groups to establish relationships between the production order and ledger accounts.</span></span> <span data-ttu-id="60318-149">As contas contábeis são usadas para lançar ou para agrupar ordens para relatório.</span><span class="sxs-lookup"><span data-stu-id="60318-149">The ledger accounts are used to post or group orders for reporting.</span></span>
2.  <span data-ttu-id="60318-150">**Pools de produção** - crie pools de produção para agrupar ordens de produção para processar ordens de produção urgentes ou para excluir e lançar grupos de ordens.</span><span class="sxs-lookup"><span data-stu-id="60318-150">**Production pools** – Create production pools to group production orders so that you can process urgent production orders, or delete and post groups of orders.</span></span>
3.  <span data-ttu-id="60318-151">**Propriedades** – defina as propriedades para criar atributos especiais que podem ser atribuídos aos recursos para controlar a ordem das produções.</span><span class="sxs-lookup"><span data-stu-id="60318-151">**Properties** – Define properties to create special attributes that you can assign to your resources to control the order of productions.</span></span> <span data-ttu-id="60318-152">Esses atributos estão conectados ao modelo de horário de trabalho.</span><span class="sxs-lookup"><span data-stu-id="60318-152">These attributes are connected to the working time template.</span></span>




