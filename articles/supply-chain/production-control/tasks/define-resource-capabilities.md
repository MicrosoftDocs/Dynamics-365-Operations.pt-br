--- 
title: Definir capacidades do recurso
description: "As funcionalidade do recurso descrevem qual recursos de operações podem ser feitos."
author: sorenva
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WrkCtrCapability
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: sorenand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 0940883d0e9edf56e61b5ecd817062aac5e0f8a6
ms.contentlocale: pt-br
ms.lasthandoff: 09/14/2018

---
# <a name="define-resource-capabilities"></a><span data-ttu-id="f4261-103">Definir capacidades do recurso</span><span class="sxs-lookup"><span data-stu-id="f4261-103">Define resource capabilities</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="f4261-104">As funcionalidade do recurso descrevem qual recursos de operações podem ser feitos.</span><span class="sxs-lookup"><span data-stu-id="f4261-104">Resource capabilities describe what operations resources can do.</span></span> <span data-ttu-id="f4261-105">Durante a programação, os requisitos de cada trabalho e a operação são correspondentes em relação às funcionalidades de recursos disponíveis.</span><span class="sxs-lookup"><span data-stu-id="f4261-105">During scheduling, the requirements of each job and operation are matched against the capabilities of the available resources.</span></span> <span data-ttu-id="f4261-106">Essa guia da tarefa irá ajudá-lo a criar uma funcionalidade de recursos e a atribui a um recurso.</span><span class="sxs-lookup"><span data-stu-id="f4261-106">This task guide will help you create a resource capability and assign it to a resource.</span></span> <span data-ttu-id="f4261-107">A empresa de dados demo usada para criar esta tarefa é USMF.</span><span class="sxs-lookup"><span data-stu-id="f4261-107">The demo data company used to create this task is USMF.</span></span>


## <a name="create-a-resource-capability"></a><span data-ttu-id="f4261-108">Criar uma nova capacidade de recurso</span><span class="sxs-lookup"><span data-stu-id="f4261-108">Create a resource capability</span></span>
1. <span data-ttu-id="f4261-109">Ir para Capacidades do recurso.</span><span class="sxs-lookup"><span data-stu-id="f4261-109">Go to Resource capabilities.</span></span>
2. <span data-ttu-id="f4261-110">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="f4261-110">Click New.</span></span>
3. <span data-ttu-id="f4261-111">No campo Capacidade, digite a ID de capacidade do recurso.</span><span class="sxs-lookup"><span data-stu-id="f4261-111">In the Capability field, type the ID of the resource capability.</span></span>
    * <span data-ttu-id="f4261-112">Para uma operação específica, use a ID do recurso para especificar quais recursos devem ter esse recurso para executar a operação.</span><span class="sxs-lookup"><span data-stu-id="f4261-112">For a given operation, you use the capability ID to specify that resources must have this capability to perform the operation.</span></span>  
4. <span data-ttu-id="f4261-113">No campo Descrição, insira uma descrição da capacidade.</span><span class="sxs-lookup"><span data-stu-id="f4261-113">In the Description field, enter a description of the capability.</span></span>

## <a name="assign-capability-to-a-resource"></a><span data-ttu-id="f4261-114">Atribuir a capacidade a um recurso</span><span class="sxs-lookup"><span data-stu-id="f4261-114">Assign capability to a resource</span></span>
1. <span data-ttu-id="f4261-115">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="f4261-115">Click Add.</span></span>
2. <span data-ttu-id="f4261-116">No campo Recurso, digite a ID do recurso.</span><span class="sxs-lookup"><span data-stu-id="f4261-116">In the Resource field, type the ID of the resource.</span></span>
    * <span data-ttu-id="f4261-117">Uma funcionalidade do recurso pode ser atribuída a um ou vários recursos.</span><span class="sxs-lookup"><span data-stu-id="f4261-117">A resource capability can be assigned to one or more resources.</span></span>  
3. <span data-ttu-id="f4261-118">No campo Vencimento, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="f4261-118">In the Expiration field, enter a date.</span></span>
    * <span data-ttu-id="f4261-119">É possível usar este campo para especificar uma funcionalidade do recurso somente por um tempo limitado.</span><span class="sxs-lookup"><span data-stu-id="f4261-119">You can use this field to specify that a resource has the capability for only a limited time.</span></span>  
4. <span data-ttu-id="f4261-120">No campo Prioridade, insira um número.</span><span class="sxs-lookup"><span data-stu-id="f4261-120">In the Priority field, enter a number.</span></span>
    * <span data-ttu-id="f4261-121">Quando você planejar o trabalho e operações, você pode especificar se deseja selecionar recursos prioridade.</span><span class="sxs-lookup"><span data-stu-id="f4261-121">When you schedule jobs and operations, you can specify whether to select resources by priority.</span></span> <span data-ttu-id="f4261-122">Se você optar por fazer isso, é possível definir mais de um recurso para executar o trabalho ou a operação na data de solicitação, o recurso com a menor prioridade em relação ao recurso necessário está selecionado.</span><span class="sxs-lookup"><span data-stu-id="f4261-122">If you choose to do this, and more than one resource can perform the job or operation by the requested date, the resource that has the lowest priority with respect to the required capability is selected.</span></span>  
5. <span data-ttu-id="f4261-123">No campo Nível, insira um número.</span><span class="sxs-lookup"><span data-stu-id="f4261-123">In the Level field, enter a number.</span></span>
    * <span data-ttu-id="f4261-124">Quando você especifica que um trabalho ou uma operação requer um recurso específico, você também pode especificar o nível mínimo necessário.</span><span class="sxs-lookup"><span data-stu-id="f4261-124">When you specify that a job or operation requires a particular capability, you can also specify the minimum level that is required.</span></span> <span data-ttu-id="f4261-125">Use o recurso em nível para diferenciar os recursos que podem realizar o mesmo trabalho, velocidades diferentes, pontos fortes, tamanho, e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="f4261-125">Use the capability level to differentiate resources that can perform the same job, but at different speeds, strengths, sizes, and so on.</span></span>  


