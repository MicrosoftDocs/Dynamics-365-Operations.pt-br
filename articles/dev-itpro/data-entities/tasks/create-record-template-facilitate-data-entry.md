---
title: Criar um modelo de registro para facilitar a entrada de dados
description: Este procedimento demonstra como criar um modelo de registro para que os valores de campo usados frequentemente não tenham que ser inseridos explicitamente para cada novo registro.
author: margoc
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetTable, SysRecordInfo, SysRecordTemplatePromptOnCreate
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: margoc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3b2ba56b6146f2495fb6a53c3cef9f549b1ad837
ms.sourcegitcommit: 16bfa0fd08feec1647829630401ce62ce2ffa1a4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/02/2019
ms.locfileid: "1848198"
---
# <a name="create-a-record-template-to-facilitate-data-entry"></a><span data-ttu-id="7dd42-103">Criar um modelo de registro para facilitar a entrada de dados</span><span class="sxs-lookup"><span data-stu-id="7dd42-103">Create a record template to facilitate data entry</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="7dd42-104">Este procedimento demonstra como criar um modelo de registro para que os valores de campo usados frequentemente não tenham que ser inseridos explicitamente para cada novo registro.</span><span class="sxs-lookup"><span data-stu-id="7dd42-104">This procedure demonstrates how to create a record template so that field values that are used often do not have to be entered explicitly for each new record.</span></span> <span data-ttu-id="7dd42-105">Neste procedimento, você criará um novo registro para novos laptops que devem ser adicionados aos ativos fixos.</span><span class="sxs-lookup"><span data-stu-id="7dd42-105">In this procedure, you’ll create a new record for new laptops that should be added to your fixed assets.</span></span> <span data-ttu-id="7dd42-106">Este procedimento usa a empresa exemplo USMF.</span><span class="sxs-lookup"><span data-stu-id="7dd42-106">This procedure uses the USMF sample company.</span></span>

1. <span data-ttu-id="7dd42-107">Vá para Ativos fixos > Ativos fixos > Ativos fixos.</span><span class="sxs-lookup"><span data-stu-id="7dd42-107">Go to Fixed assets > Fixed assets > Fixed assets.</span></span>
2. <span data-ttu-id="7dd42-108">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="7dd42-108">Click New.</span></span>
3. <span data-ttu-id="7dd42-109">No campo Grupo de ativo fixo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="7dd42-109">In the Fixed asset group field, enter or select a value.</span></span>
4. <span data-ttu-id="7dd42-110">No campo Nome, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="7dd42-110">In the Name field, type a value.</span></span>
    * <span data-ttu-id="7dd42-111">Por exemplo, insira "Laptop corporativo do cliente potencial".</span><span class="sxs-lookup"><span data-stu-id="7dd42-111">For example, enter 'Corporate lead laptop'.</span></span>  
5. <span data-ttu-id="7dd42-112">No campo Nome da pesquisa, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="7dd42-112">In the Search name field, type a value.</span></span>
    * <span data-ttu-id="7dd42-113">Por exemplo, insira "laptop".</span><span class="sxs-lookup"><span data-stu-id="7dd42-113">For example, enter 'laptop.'</span></span>  
6. <span data-ttu-id="7dd42-114">Expanda a seção Informações técnicas.</span><span class="sxs-lookup"><span data-stu-id="7dd42-114">Expand the Technical information section.</span></span>
7. <span data-ttu-id="7dd42-115">No campo Marca, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="7dd42-115">In the Make field, type a value.</span></span>
8. <span data-ttu-id="7dd42-116">No campo Modelo, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="7dd42-116">In the Model field, type a value.</span></span>
9. <span data-ttu-id="7dd42-117">No campo Ano do modelo, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="7dd42-117">In the Model year field, type a value.</span></span>
10. <span data-ttu-id="7dd42-118">No Painel de Ação, clique em Opções.</span><span class="sxs-lookup"><span data-stu-id="7dd42-118">On the Action Pane, click Options.</span></span>
11. <span data-ttu-id="7dd42-119">Clique em Informações sobre registro.</span><span class="sxs-lookup"><span data-stu-id="7dd42-119">Click Record info.</span></span>
12. <span data-ttu-id="7dd42-120">Clique em Modelo de usuário.</span><span class="sxs-lookup"><span data-stu-id="7dd42-120">Click User template.</span></span>
13. <span data-ttu-id="7dd42-121">No campo Nome, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="7dd42-121">In the Name field, type a value.</span></span>
    * <span data-ttu-id="7dd42-122">Por exemplo, insira "Laptop corporativo".</span><span class="sxs-lookup"><span data-stu-id="7dd42-122">For example, enter 'Corporate laptop.'</span></span>  
14. <span data-ttu-id="7dd42-123">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="7dd42-123">In the Description field, type a value.</span></span>
    * <span data-ttu-id="7dd42-124">Por exemplo, insira "Laptop corporativo".</span><span class="sxs-lookup"><span data-stu-id="7dd42-124">For example, enter 'Corporate laptop'.</span></span>  
15. <span data-ttu-id="7dd42-125">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="7dd42-125">Click OK.</span></span>
16. <span data-ttu-id="7dd42-126">Clique em Fechar.</span><span class="sxs-lookup"><span data-stu-id="7dd42-126">Click Close.</span></span>

