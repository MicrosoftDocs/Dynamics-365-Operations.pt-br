--- 
title: "Configurar registros de depreciações"
description: "Esse guia da tarefa criará um novo registro de depreciações e irá associá-lo com um grupo de ativo fixo."
author: saraschi2
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: d2001da7b3487a07a91abd406f74558916ac9f23
ms.contentlocale: pt-br
ms.lasthandoff: 08/29/2017

---
# <a name="set-up-depreciation-books"></a><span data-ttu-id="27fd5-103">Configurar registros de depreciações</span><span class="sxs-lookup"><span data-stu-id="27fd5-103">Set up depreciation books</span></span> 

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="27fd5-104">Esse guia da tarefa criará um novo registro de depreciações e irá associá-lo com um grupo de ativo fixo.</span><span class="sxs-lookup"><span data-stu-id="27fd5-104">This task guide will create a new depreciation book and associate it with a fixed asset group.</span></span>  <span data-ttu-id="27fd5-105">Ela usa a função de contador e os dados de demonstração da entidade legal de USMF.</span><span class="sxs-lookup"><span data-stu-id="27fd5-105">It uses the Accountant role and demo data for the USMF legal entity.</span></span>


## <a name="create-a-depreciation-book"></a><span data-ttu-id="27fd5-106">Crie um registro de depreciação</span><span class="sxs-lookup"><span data-stu-id="27fd5-106">Create a depreciation book</span></span>
1. <span data-ttu-id="27fd5-107">Vá para Ativos fixos > Configuração > Registros de depreciação.</span><span class="sxs-lookup"><span data-stu-id="27fd5-107">Go to Fixed assets > Setup > Depreciation books.</span></span>
2. <span data-ttu-id="27fd5-108">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="27fd5-108">Click New.</span></span>
3. <span data-ttu-id="27fd5-109">No campo de registro de depreciação, insira um valor.</span><span class="sxs-lookup"><span data-stu-id="27fd5-109">In the Depreciation book field, type a value.</span></span>
4. <span data-ttu-id="27fd5-110">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="27fd5-110">In the Description field, type a value.</span></span>
5. <span data-ttu-id="27fd5-111">Marcar ou desmarcar a caixa de seleção Calcular depreciação.</span><span class="sxs-lookup"><span data-stu-id="27fd5-111">Check or uncheck the Calculate depreciation checkbox.</span></span>
6. <span data-ttu-id="27fd5-112">No campo Perfil de depreciação, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="27fd5-112">In the Depreciation profile field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="27fd5-113">Na lista, localize e selecione o perfil de depreciação desejado.</span><span class="sxs-lookup"><span data-stu-id="27fd5-113">In the list, find and select the desired depreciation profile.</span></span>
8. <span data-ttu-id="27fd5-114">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="27fd5-114">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="27fd5-115">No campo Perfil de depreciação alternativa, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="27fd5-115">In the Alternative depreciation profile field, click the drop-down button to open the lookup.</span></span>
10. <span data-ttu-id="27fd5-116">Na lista, selecione o perfil de depreciação desejado.</span><span class="sxs-lookup"><span data-stu-id="27fd5-116">In the list, select the desired depreciation profile.</span></span>
11. <span data-ttu-id="27fd5-117">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="27fd5-117">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="27fd5-118">O perfil de depreciação extraordinário é usado para depreciação adicional para um ativo em condições incomuns.</span><span class="sxs-lookup"><span data-stu-id="27fd5-118">The Extraordinary depreciation profile is used for additional depreciation of an asset in unusual circumstances.</span></span> <span data-ttu-id="27fd5-119">Por exemplo, você pode usá-lo para registrar a depreciação que resulta de acidentes naturais.</span><span class="sxs-lookup"><span data-stu-id="27fd5-119">For example, you might use this to record depreciation that results from a natural disaster.</span></span>  
12. <span data-ttu-id="27fd5-120">Marque ou desmarque a caixa de seleção Criar ajustes de depreciação com ajustes de base.</span><span class="sxs-lookup"><span data-stu-id="27fd5-120">Check or uncheck the Create depreciation adjustments with basis adjustments checkbox.</span></span>
13. <span data-ttu-id="27fd5-121">No campo Calendário, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="27fd5-121">In the Calendar field, click the drop-down button to open the lookup.</span></span>
14. <span data-ttu-id="27fd5-122">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="27fd5-122">In the list, click the link in the selected row.</span></span>

## <a name="associate-the-depreciation-book-with-a-fixed-asset-group"></a><span data-ttu-id="27fd5-123">Associar o registro de depreciação a um grupo de ativo fixo</span><span class="sxs-lookup"><span data-stu-id="27fd5-123">Associate the depreciation book with a fixed asset group</span></span>
1. <span data-ttu-id="27fd5-124">Clique em Grupos de ativos fixos.</span><span class="sxs-lookup"><span data-stu-id="27fd5-124">Click Fixed asset groups.</span></span>
2. <span data-ttu-id="27fd5-125">No campo Grupo de ativo fixo, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="27fd5-125">In the Fixed asset group field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="27fd5-126">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="27fd5-126">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="27fd5-127">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="27fd5-127">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="27fd5-128">No campo Convenção de depreciação, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="27fd5-128">In the Depreciation convention field, select an option.</span></span>
6. <span data-ttu-id="27fd5-129">No campo Vida útil, insira um número.</span><span class="sxs-lookup"><span data-stu-id="27fd5-129">In the Service life field, enter a number.</span></span>
    * <span data-ttu-id="27fd5-130">Observe que o valor do campo de períodos de depreciação será calculado depois de definir a vida útil.</span><span class="sxs-lookup"><span data-stu-id="27fd5-130">Notice the Depreciation periods field value is calculated after setting the Service life.</span></span>  


