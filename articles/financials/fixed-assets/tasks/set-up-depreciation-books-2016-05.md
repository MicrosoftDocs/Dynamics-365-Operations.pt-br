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
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 3e2c3bfdde6fd06bfe9e22f215f691e0c92fa8ee
ms.contentlocale: pt-br
ms.lasthandoff: 05/08/2018

---

# <a name="set-up-depreciation-books"></a><span data-ttu-id="c80e9-103">Configurar registros de depreciações</span><span class="sxs-lookup"><span data-stu-id="c80e9-103">Set up depreciation books</span></span> 

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="c80e9-104">Esse guia da tarefa criará um novo registro de depreciações e irá associá-lo com um grupo de ativo fixo.</span><span class="sxs-lookup"><span data-stu-id="c80e9-104">This task guide will create a new depreciation book and associate it with a fixed asset group.</span></span>  <span data-ttu-id="c80e9-105">Ela usa a função de contador e os dados de demonstração da entidade legal de USMF.</span><span class="sxs-lookup"><span data-stu-id="c80e9-105">It uses the Accountant role and demo data for the USMF legal entity.</span></span>


## <a name="create-a-depreciation-book"></a><span data-ttu-id="c80e9-106">Crie um registro de depreciação</span><span class="sxs-lookup"><span data-stu-id="c80e9-106">Create a depreciation book</span></span>
1. <span data-ttu-id="c80e9-107">Vá para Ativos fixos > Configuração > Registros de depreciação.</span><span class="sxs-lookup"><span data-stu-id="c80e9-107">Go to Fixed assets > Setup > Depreciation books.</span></span>
2. <span data-ttu-id="c80e9-108">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="c80e9-108">Click New.</span></span>
3. <span data-ttu-id="c80e9-109">No campo de registro de depreciação, insira um valor.</span><span class="sxs-lookup"><span data-stu-id="c80e9-109">In the Depreciation book field, type a value.</span></span>
4. <span data-ttu-id="c80e9-110">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="c80e9-110">In the Description field, type a value.</span></span>
5. <span data-ttu-id="c80e9-111">Marcar ou desmarcar a caixa de seleção Calcular depreciação.</span><span class="sxs-lookup"><span data-stu-id="c80e9-111">Check or uncheck the Calculate depreciation checkbox.</span></span>
6. <span data-ttu-id="c80e9-112">No campo Perfil de depreciação, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="c80e9-112">In the Depreciation profile field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="c80e9-113">Na lista, localize e selecione o perfil de depreciação desejado.</span><span class="sxs-lookup"><span data-stu-id="c80e9-113">In the list, find and select the desired depreciation profile.</span></span>
8. <span data-ttu-id="c80e9-114">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="c80e9-114">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="c80e9-115">No campo Perfil de depreciação alternativa, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="c80e9-115">In the Alternative depreciation profile field, click the drop-down button to open the lookup.</span></span>
10. <span data-ttu-id="c80e9-116">Na lista, selecione o perfil de depreciação desejado.</span><span class="sxs-lookup"><span data-stu-id="c80e9-116">In the list, select the desired depreciation profile.</span></span>
11. <span data-ttu-id="c80e9-117">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="c80e9-117">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="c80e9-118">O perfil de depreciação extraordinário é usado para depreciação adicional para um ativo em condições incomuns.</span><span class="sxs-lookup"><span data-stu-id="c80e9-118">The Extraordinary depreciation profile is used for additional depreciation of an asset in unusual circumstances.</span></span> <span data-ttu-id="c80e9-119">Por exemplo, você pode usá-lo para registrar a depreciação que resulta de acidentes naturais.</span><span class="sxs-lookup"><span data-stu-id="c80e9-119">For example, you might use this to record depreciation that results from a natural disaster.</span></span>  
12. <span data-ttu-id="c80e9-120">Marque ou desmarque a caixa de seleção Criar ajustes de depreciação com ajustes de base.</span><span class="sxs-lookup"><span data-stu-id="c80e9-120">Check or uncheck the Create depreciation adjustments with basis adjustments checkbox.</span></span>
13. <span data-ttu-id="c80e9-121">No campo Calendário, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="c80e9-121">In the Calendar field, click the drop-down button to open the lookup.</span></span>
14. <span data-ttu-id="c80e9-122">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="c80e9-122">In the list, click the link in the selected row.</span></span>

## <a name="associate-the-depreciation-book-with-a-fixed-asset-group"></a><span data-ttu-id="c80e9-123">Associar o registro de depreciação a um grupo de ativo fixo</span><span class="sxs-lookup"><span data-stu-id="c80e9-123">Associate the depreciation book with a fixed asset group</span></span>
1. <span data-ttu-id="c80e9-124">Clique em Grupos de ativos fixos.</span><span class="sxs-lookup"><span data-stu-id="c80e9-124">Click Fixed asset groups.</span></span>
2. <span data-ttu-id="c80e9-125">No campo Grupo de ativo fixo, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="c80e9-125">In the Fixed asset group field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="c80e9-126">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="c80e9-126">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="c80e9-127">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="c80e9-127">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="c80e9-128">No campo Convenção de depreciação, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="c80e9-128">In the Depreciation convention field, select an option.</span></span>
6. <span data-ttu-id="c80e9-129">No campo Vida útil, insira um número.</span><span class="sxs-lookup"><span data-stu-id="c80e9-129">In the Service life field, enter a number.</span></span>
    * <span data-ttu-id="c80e9-130">Observe que o valor do campo de períodos de depreciação será calculado depois de definir a vida útil.</span><span class="sxs-lookup"><span data-stu-id="c80e9-130">Notice the Depreciation periods field value is calculated after setting the Service life.</span></span>  


