---
title: Configurar registros de depreciação
description: Este procedimento explica o processo de criação de um registro de depreciações e o associa a um grupo de ativos fixos.
author: saraschi2
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: AssetDepBookTable, AssetGroupDepBookSetup
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b0ab7f9332e3224c3dadd62aae532ccffb05c82a
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5815587"
---
# <a name="set-up-depreciation-books"></a><span data-ttu-id="7c475-103">Configurar registros de depreciação</span><span class="sxs-lookup"><span data-stu-id="7c475-103">Set up depreciation books</span></span> 

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="7c475-104">Este procedimento explica o processo de criação de um registro de depreciações e o associa a um grupo de ativos fixos.</span><span class="sxs-lookup"><span data-stu-id="7c475-104">This procedure walks through the process of creating a new depreciation book and associate it with a fixed asset group.</span></span> 

## <a name="create-a-depreciation-book"></a><span data-ttu-id="7c475-105">Crie um registro de depreciação</span><span class="sxs-lookup"><span data-stu-id="7c475-105">Create a depreciation book</span></span>
1. <span data-ttu-id="7c475-106">Vá para Ativos fixos > Configuração > Registros de depreciação.</span><span class="sxs-lookup"><span data-stu-id="7c475-106">Go to Fixed assets > Setup > Depreciation books.</span></span>
2. <span data-ttu-id="7c475-107">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="7c475-107">Click New.</span></span>
3. <span data-ttu-id="7c475-108">No campo de registro de depreciação, insira um valor.</span><span class="sxs-lookup"><span data-stu-id="7c475-108">In the Depreciation book field, type a value.</span></span>
4. <span data-ttu-id="7c475-109">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="7c475-109">In the Description field, type a value.</span></span>
5. <span data-ttu-id="7c475-110">Marcar ou desmarcar a caixa de seleção Calcular depreciação.</span><span class="sxs-lookup"><span data-stu-id="7c475-110">Check or uncheck the Calculate depreciation checkbox.</span></span>
6. <span data-ttu-id="7c475-111">No campo Perfil de depreciação, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="7c475-111">In the Depreciation profile field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="7c475-112">Na lista, localize e selecione o perfil de depreciação desejado.</span><span class="sxs-lookup"><span data-stu-id="7c475-112">In the list, find and select the desired depreciation profile.</span></span>
8. <span data-ttu-id="7c475-113">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="7c475-113">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="7c475-114">No campo Perfil de depreciação alternativa, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="7c475-114">In the Alternative depreciation profile field, click the drop-down button to open the lookup.</span></span>
10. <span data-ttu-id="7c475-115">Na lista, selecione o perfil de depreciação desejado.</span><span class="sxs-lookup"><span data-stu-id="7c475-115">In the list, select the desired depreciation profile.</span></span>
11. <span data-ttu-id="7c475-116">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="7c475-116">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="7c475-117">O perfil de depreciação extraordinário é usado para depreciação adicional para um ativo em condições incomuns.</span><span class="sxs-lookup"><span data-stu-id="7c475-117">The Extraordinary depreciation profile is used for additional depreciation of an asset in unusual circumstances.</span></span> <span data-ttu-id="7c475-118">Por exemplo, você pode usá-lo para registrar a depreciação que resulta de acidentes naturais.</span><span class="sxs-lookup"><span data-stu-id="7c475-118">For example, you might use this to record depreciation that results from a natural disaster.</span></span>  
12. <span data-ttu-id="7c475-119">Marque ou desmarque a caixa de seleção Criar ajustes de depreciação com ajustes de base.</span><span class="sxs-lookup"><span data-stu-id="7c475-119">Check or uncheck the Create depreciation adjustments with basis adjustments checkbox.</span></span>
13. <span data-ttu-id="7c475-120">No campo Calendário, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="7c475-120">In the Calendar field, click the drop-down button to open the lookup.</span></span>
14. <span data-ttu-id="7c475-121">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="7c475-121">In the list, click the link in the selected row.</span></span>

## <a name="associate-the-depreciation-book-with-a-fixed-asset-group"></a><span data-ttu-id="7c475-122">Associar o registro de depreciação a um grupo de ativo fixo</span><span class="sxs-lookup"><span data-stu-id="7c475-122">Associate the depreciation book with a fixed asset group</span></span>
1. <span data-ttu-id="7c475-123">Clique em Grupos de ativos fixos.</span><span class="sxs-lookup"><span data-stu-id="7c475-123">Click Fixed asset groups.</span></span>
2. <span data-ttu-id="7c475-124">No campo Grupo de ativo fixo, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="7c475-124">In the Fixed asset group field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="7c475-125">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="7c475-125">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="7c475-126">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="7c475-126">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="7c475-127">No campo Convenção de depreciação, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="7c475-127">In the Depreciation convention field, select an option.</span></span>
6. <span data-ttu-id="7c475-128">No campo Vida útil, insira um número.</span><span class="sxs-lookup"><span data-stu-id="7c475-128">In the Service life field, enter a number.</span></span>
    * <span data-ttu-id="7c475-129">Observe que o valor do campo de períodos de depreciação será calculado depois de definir a vida útil.</span><span class="sxs-lookup"><span data-stu-id="7c475-129">Notice the Depreciation periods field value is calculated after setting the Service life.</span></span>  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]