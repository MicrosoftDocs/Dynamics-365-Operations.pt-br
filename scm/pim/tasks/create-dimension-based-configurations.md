--- 
title: "Criar configurações baseadas em dimensão"
description: "Este procedimento mostra como definir uma configuração para um produto baseado na dimensão."
author: YuyuScheller
manager: AnnBe
ms.date: 06/21/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Operations
ms.search.region: Global
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 6dd2aa1ebc713287120106a9d1ec7dc15c24def9
ms.openlocfilehash: d6ea85cedbb96266f82e0a4ec1ad17f3ba829322
ms.contentlocale: pt-br
ms.lasthandoff: 09/14/2017

---
# <a name="create-dimension-based-configurations"></a><span data-ttu-id="7e6cc-103">Criar configurações baseadas em dimensão</span><span class="sxs-lookup"><span data-stu-id="7e6cc-103">Create dimension-based configurations</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="7e6cc-104">Este procedimento mostra como definir uma configuração para um produto baseado na dimensão.</span><span class="sxs-lookup"><span data-stu-id="7e6cc-104">This procedure shows how to define a configuration for a dimension-based product.</span></span> <span data-ttu-id="7e6cc-105">Este é o último procedimento da série que explica como criar combinações para configuração baseada em dimensão.</span><span class="sxs-lookup"><span data-stu-id="7e6cc-105">This is the last procedure in the series that explains how to build combinations for dimension-based configuration.</span></span> <span data-ttu-id="7e6cc-106">A execução desse procedimento depende dos dados criados nos sete registros anteriores.</span><span class="sxs-lookup"><span data-stu-id="7e6cc-106">The execution of this procedure is dependent on the data created in the previous seven recordings.</span></span> <span data-ttu-id="7e6cc-107">A empresa de dados demo usada para criar este procedimento é USMF.</span><span class="sxs-lookup"><span data-stu-id="7e6cc-107">The demo data company used to create this procedure is USMF.</span></span>


## <a name="find-the-dimension-based-product-master"></a><span data-ttu-id="7e6cc-108">Encontre o produto mestre baseado na dimensão</span><span class="sxs-lookup"><span data-stu-id="7e6cc-108">Find the dimension-based product master</span></span>
1. <span data-ttu-id="7e6cc-109">Clique em Manutenção de produto liberado.</span><span class="sxs-lookup"><span data-stu-id="7e6cc-109">Click Released product maintenance.</span></span>
2. <span data-ttu-id="7e6cc-110">Clique em Produtos liberados.</span><span class="sxs-lookup"><span data-stu-id="7e6cc-110">Click Released products.</span></span>
3. <span data-ttu-id="7e6cc-111">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="7e6cc-111">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="7e6cc-112">Selecione o produto mestre baseado na dimensão que você criou no primeiro registro nesta sequência de 8 registros.</span><span class="sxs-lookup"><span data-stu-id="7e6cc-112">Select the dimension-based product master that you created in the first recording in this sequence of 8 recordings.</span></span>  

## <a name="create-configurations"></a><span data-ttu-id="7e6cc-113">Criar configurações</span><span class="sxs-lookup"><span data-stu-id="7e6cc-113">Create configurations</span></span>
1. <span data-ttu-id="7e6cc-114">No Painel de Ação Engenharia, clique em Manter configurações.</span><span class="sxs-lookup"><span data-stu-id="7e6cc-114">On the Engineering Action Pane, click Maintain configurations.</span></span>
2. <span data-ttu-id="7e6cc-115">Clique em Configurar.</span><span class="sxs-lookup"><span data-stu-id="7e6cc-115">Click Configure.</span></span>
3. <span data-ttu-id="7e6cc-116">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="7e6cc-116">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="7e6cc-117">No campo Número do item, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="7e6cc-117">In the Item number field, enter or select a value.</span></span>
    * <span data-ttu-id="7e6cc-118">Selecione um dos itens no grupo de configuração.</span><span class="sxs-lookup"><span data-stu-id="7e6cc-118">Select any of the items in the first configuration group.</span></span>  
5. <span data-ttu-id="7e6cc-119">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="7e6cc-119">In the list, find and select the desired record.</span></span>
6. <span data-ttu-id="7e6cc-120">No campo Número do item, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="7e6cc-120">In the Item number field, enter or select a value.</span></span>
    * <span data-ttu-id="7e6cc-121">Selecione qualquer item do segundo grupo de configuração.</span><span class="sxs-lookup"><span data-stu-id="7e6cc-121">Select any item from the second configuration group.</span></span>  
7. <span data-ttu-id="7e6cc-122">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="7e6cc-122">Click OK.</span></span>
8. <span data-ttu-id="7e6cc-123">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="7e6cc-123">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="7e6cc-124">No campo Configuração, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="7e6cc-124">In the Configuration field, type a value.</span></span>
    * <span data-ttu-id="7e6cc-125">Insira um nome de configuração que seja de fácil identificação da configuração.</span><span class="sxs-lookup"><span data-stu-id="7e6cc-125">Enter a configuration name that will make it easy to identify the configuration.</span></span>  
10. <span data-ttu-id="7e6cc-126">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="7e6cc-126">In the Description field, type a value.</span></span>
    * <span data-ttu-id="7e6cc-127">Insira uma descrição da configuração para explicar o que ela contém.</span><span class="sxs-lookup"><span data-stu-id="7e6cc-127">Enter a description of the configuration to explain what it contains.</span></span>  
11. <span data-ttu-id="7e6cc-128">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="7e6cc-128">Click OK.</span></span>


