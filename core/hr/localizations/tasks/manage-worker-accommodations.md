--- 
title: "Gerenciar acomodações do trabalhador"
description: "Este procedimento apresenta as etapas para configurar os tipos de acomodação do ambiente de trabalho, como cadeiras ergonômicas ou intervalos periódicos."
author: ShielaSogge
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Operations
ms.search.region: Global
ms.author: shielas
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 10d34d0b2eca95034d1f67931ff72a035be9a6b8
ms.contentlocale: pt-br
ms.lasthandoff: 08/29/2017

---
# <a name="manage-worker-accommodations"></a><span data-ttu-id="9dc48-103">Gerenciar acomodações do trabalhador</span><span class="sxs-lookup"><span data-stu-id="9dc48-103">Manage worker accommodations</span></span>

[!include[task guide banner](../../../includes/task-guide-banner.md)]

<span data-ttu-id="9dc48-104">Este procedimento apresenta as etapas para configurar os tipos de acomodação do ambiente de trabalho, como cadeiras ergonômicas ou intervalos periódicos.</span><span class="sxs-lookup"><span data-stu-id="9dc48-104">This procedure walks through the steps for setting up work environment accommodation types, such as ergonomic chairs or periodic breaks.</span></span> <span data-ttu-id="9dc48-105">Mostra também como atribuir esses tipos de acomodação a um funcionário, e tanto aprovar como negar o tipo de acomodação.</span><span class="sxs-lookup"><span data-stu-id="9dc48-105">It also shows how to assign these accommodation types to a worker, and either approve or deny the accommodation type.</span></span> <span data-ttu-id="9dc48-106">A empresa de dados demo usada para criar este procedimento é USMF.</span><span class="sxs-lookup"><span data-stu-id="9dc48-106">The demo data company used to create this procedure is USMF.</span></span>


## <a name="setup-accommodations"></a><span data-ttu-id="9dc48-107">Instalar acomodações</span><span class="sxs-lookup"><span data-stu-id="9dc48-107">Setup accommodations</span></span>
1. <span data-ttu-id="9dc48-108">Vá para Recursos humanos > Configurar > Tipos de acomodação.</span><span class="sxs-lookup"><span data-stu-id="9dc48-108">Go to Human resources > Setup > Accommodation types.</span></span>
2. <span data-ttu-id="9dc48-109">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="9dc48-109">Click New.</span></span>
3. <span data-ttu-id="9dc48-110">No campo Tipo de acomodação, insira um nome para a acomodação.</span><span class="sxs-lookup"><span data-stu-id="9dc48-110">In the Accommodation type field, enter a name for the accommodation.</span></span> <span data-ttu-id="9dc48-111">Exemplo: Teclado.</span><span class="sxs-lookup"><span data-stu-id="9dc48-111">Example: Keyboard.</span></span>
4. <span data-ttu-id="9dc48-112">No campo Descrição, insira uma descrição para a acomodação.</span><span class="sxs-lookup"><span data-stu-id="9dc48-112">In the Description field, enter a description for the accommodation.</span></span> <span data-ttu-id="9dc48-113">Exemplo: Teclado ergonômico.</span><span class="sxs-lookup"><span data-stu-id="9dc48-113">Example: Ergonomic Keyboard.</span></span>
5. <span data-ttu-id="9dc48-114">No campo Nota, insira qualquer informação que ajude a esclarecer a acomodação.</span><span class="sxs-lookup"><span data-stu-id="9dc48-114">In the Note field, enter any information that helps to clarify the accommodation.</span></span>
6. <span data-ttu-id="9dc48-115">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="9dc48-115">Click Save.</span></span>
7. <span data-ttu-id="9dc48-116">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="9dc48-116">Close the page.</span></span>

## <a name="assign-accommodations"></a><span data-ttu-id="9dc48-117">Atribuir acomodações</span><span class="sxs-lookup"><span data-stu-id="9dc48-117">Assign accommodations</span></span>
1. <span data-ttu-id="9dc48-118">Vá para Recursos humanos > Trabalhadores > Funcionários.</span><span class="sxs-lookup"><span data-stu-id="9dc48-118">Go to Human resources > Workers > Employees.</span></span>
2. <span data-ttu-id="9dc48-119">Da lista, selecione um funcionário.</span><span class="sxs-lookup"><span data-stu-id="9dc48-119">From the list, select an employee.</span></span>
3. <span data-ttu-id="9dc48-120">Clique no nome do funcionário para exibir detalhes sobre o funcionário que está solicitando a acomodação.</span><span class="sxs-lookup"><span data-stu-id="9dc48-120">Click the employee's name to view details about the employee who is requesting the accommodation.</span></span>
4. <span data-ttu-id="9dc48-121">Expanda a aba rápida Informações pessoais.</span><span class="sxs-lookup"><span data-stu-id="9dc48-121">Expand the Personal information FastTab.</span></span>
5. <span data-ttu-id="9dc48-122">Clique em Acomodações.</span><span class="sxs-lookup"><span data-stu-id="9dc48-122">Click Accommodations.</span></span>
6. <span data-ttu-id="9dc48-123">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="9dc48-123">Click New.</span></span>
7. <span data-ttu-id="9dc48-124">No campo Tipo de acomodação, selecione a acomodação apropriada.</span><span class="sxs-lookup"><span data-stu-id="9dc48-124">In the Accommodation type field, select the appropriate accommodation.</span></span> <span data-ttu-id="9dc48-125">Exemplo: Teclado</span><span class="sxs-lookup"><span data-stu-id="9dc48-125">Example: Keyboard</span></span>
8. <span data-ttu-id="9dc48-126">No campo Tarefa de trabalho, insira a tarefa de trabalho que exige a acomodação.</span><span class="sxs-lookup"><span data-stu-id="9dc48-126">In the Job task field, enter the work task that requires the accommodation.</span></span>
9. <span data-ttu-id="9dc48-127">No campo Status, insira o status apropriado.</span><span class="sxs-lookup"><span data-stu-id="9dc48-127">In the Status field, enter the appropriate status.</span></span> <span data-ttu-id="9dc48-128">Exemplo: Razoável</span><span class="sxs-lookup"><span data-stu-id="9dc48-128">Example: Reasonable</span></span>
    * <span data-ttu-id="9dc48-129">Os seguintes status estão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="9dc48-129">The following statuses are available.</span></span> <span data-ttu-id="9dc48-130">Solicitada indica que a acomodação foi criada mas ainda não foi revisada.</span><span class="sxs-lookup"><span data-stu-id="9dc48-130">Requested indicates that the accommodation has been created but not yet reviewed.</span></span> <span data-ttu-id="9dc48-131">Razoável indica que a acomodação é razoável e será concedida.</span><span class="sxs-lookup"><span data-stu-id="9dc48-131">Reasonable indicates that the accommodation is reasonable and will be granted.</span></span> <span data-ttu-id="9dc48-132">Dificuldades inaceitáveis indica que a acomodação colocará uma carga excessiva sobre o empregado, e foi negada.</span><span class="sxs-lookup"><span data-stu-id="9dc48-132">Undue hardship indicates that the accommodation will place an unreasonable burden on the employer, and has been denied.</span></span> <span data-ttu-id="9dc48-133">Neste exemplo, a solicitação foi aprovada imediatamente porque a solicitação de acomodação foi mínima.</span><span class="sxs-lookup"><span data-stu-id="9dc48-133">In this example, the request was approved immediately because the accommodation request was minimal.</span></span>  
10. <span data-ttu-id="9dc48-134">No campo Aceito, selecione a pessoa que aceitou a solicitação de acomodação.</span><span class="sxs-lookup"><span data-stu-id="9dc48-134">In the Accepted field, select the person who accepted the accommodation request.</span></span>
11. <span data-ttu-id="9dc48-135">Clique em Selecionar.</span><span class="sxs-lookup"><span data-stu-id="9dc48-135">Click Select.</span></span>
12. <span data-ttu-id="9dc48-136">No campo Data de aceite, insira a data e hora em que a solicitação de acomodação foi aceitada.</span><span class="sxs-lookup"><span data-stu-id="9dc48-136">In the Accepted date field, enter the date and time when the accommodation request was accepted.</span></span>
13. <span data-ttu-id="9dc48-137">Expanda a seção Nota.</span><span class="sxs-lookup"><span data-stu-id="9dc48-137">Expand the Note section.</span></span>
14. <span data-ttu-id="9dc48-138">No campo Financeiro, insira qualquer informação ou custos de recurso que ajudem a esclarecer o impacto da acomodação.</span><span class="sxs-lookup"><span data-stu-id="9dc48-138">In the Financial field, enter any information or resource costs that helps to clarify the impact of the accommodation.</span></span>
    * <span data-ttu-id="9dc48-139">Se a acomodação foi negada, o campo Responder pode ser usado para indicar o motivo pelo qual a solicitação foi negada.</span><span class="sxs-lookup"><span data-stu-id="9dc48-139">If the accommodation has been denied, the Reply field can be used to indicate why a request was denied.</span></span>  
15. <span data-ttu-id="9dc48-140">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="9dc48-140">Click Save.</span></span>


