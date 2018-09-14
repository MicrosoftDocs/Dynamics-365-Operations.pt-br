--- 
title: "Configurar depreciação extra"
description: "Este procedimento mostra como criar uma provisão para depreciação especial e associá-la a um registro de ativos fixos."
author: saraschi2
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetBonus, AssetGroup, AssetGroupBookSetup, AssetGroupSetupBonus
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 6bbd6b78d05fcc9d95f6e6409db2619a210ad760
ms.contentlocale: pt-br
ms.lasthandoff: 09/14/2018

---
# <a name="set-up-bonus-depreciation"></a><span data-ttu-id="7027d-103">Configurar depreciação extra</span><span class="sxs-lookup"><span data-stu-id="7027d-103">Set up bonus depreciation</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="7027d-104">Este procedimento mostra como criar uma provisão para depreciação especial e associá-la a um registro de ativos fixos.</span><span class="sxs-lookup"><span data-stu-id="7027d-104">This procedure shows how to create a special depreciation allowance and associate it with a fixed asset book.</span></span> <span data-ttu-id="7027d-105">Ela usa a função de contador e os dados de demonstração da entidade legal de USMF.</span><span class="sxs-lookup"><span data-stu-id="7027d-105">It uses the accountant role and demo data for the USMF legal entity.</span></span>


## <a name="create-a-special-depreciation-allowance"></a><span data-ttu-id="7027d-106">Criar uma provisão para depreciação especial</span><span class="sxs-lookup"><span data-stu-id="7027d-106">Create a special depreciation allowance</span></span>
1. <span data-ttu-id="7027d-107">Vá para Ativos fixos > Configuração > Provisão para depreciação especial.</span><span class="sxs-lookup"><span data-stu-id="7027d-107">Go to Fixed assets > Setup > Special depreciation allowance.</span></span>
2. <span data-ttu-id="7027d-108">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="7027d-108">Click New.</span></span>
3. <span data-ttu-id="7027d-109">No campo Provisão para depreciação especial, insira um valor.</span><span class="sxs-lookup"><span data-stu-id="7027d-109">In the Special depreciation allowance field, type a value.</span></span>
4. <span data-ttu-id="7027d-110">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="7027d-110">In the Description field, type a value.</span></span>
5. <span data-ttu-id="7027d-111">No campo Porcentagem, insira um número.</span><span class="sxs-lookup"><span data-stu-id="7027d-111">In the Percentage field, enter a number.</span></span>
    * <span data-ttu-id="7027d-112">Se uma porcentagem não foi indicada, defina um valor.</span><span class="sxs-lookup"><span data-stu-id="7027d-112">If a percentage was not indicated, set an amount.</span></span>  

## <a name="associate-a-special-depreciation-allowance-with-a-fixed-asset-group-book"></a><span data-ttu-id="7027d-113">Associar uma provisão para depreciação especial a um registro de grupo de ativos fixos</span><span class="sxs-lookup"><span data-stu-id="7027d-113">Associate a special depreciation allowance with a fixed asset group book</span></span>
1. <span data-ttu-id="7027d-114">Vá para Ativos fixos > Configuração > Grupos de ativo fixo.</span><span class="sxs-lookup"><span data-stu-id="7027d-114">Go to Fixed assets > Setup > Fixed asset groups.</span></span>
2. <span data-ttu-id="7027d-115">Na lista, selecione o grupo de ativos fixos a ser associado à provisão para depreciação especial.</span><span class="sxs-lookup"><span data-stu-id="7027d-115">In the list, select the fixed asset group associated with the special depreciation allowance.</span></span>
3. <span data-ttu-id="7027d-116">Clique em Registros.</span><span class="sxs-lookup"><span data-stu-id="7027d-116">Click Books.</span></span>
4. <span data-ttu-id="7027d-117">Na lista, selecione o registro associado à provisão para depreciação especial.</span><span class="sxs-lookup"><span data-stu-id="7027d-117">In the list, select the book that is associated with the special depreciation allowance.</span></span>
5. <span data-ttu-id="7027d-118">Clique em Provisão para depreciação especial.</span><span class="sxs-lookup"><span data-stu-id="7027d-118">Click Special depreciation allowance.</span></span>
6. <span data-ttu-id="7027d-119">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="7027d-119">Click New.</span></span>
7. <span data-ttu-id="7027d-120">No campo Provisão para depreciação especial, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="7027d-120">In the Special depreciation allowance field, enter or select a value.</span></span>
    * <span data-ttu-id="7027d-121">O padrão para a porcentagem ou o valor vem da configuração de provisão para depreciação especial.</span><span class="sxs-lookup"><span data-stu-id="7027d-121">The default for Percentage or Amount comes from the special depreciation allowance setup.</span></span>  
8. <span data-ttu-id="7027d-122">No campo Prioridade, insira um número.</span><span class="sxs-lookup"><span data-stu-id="7027d-122">In the Priority field, enter a number.</span></span>


