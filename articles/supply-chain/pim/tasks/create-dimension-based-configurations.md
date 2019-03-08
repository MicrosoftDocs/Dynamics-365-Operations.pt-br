---
title: Criar configurações baseadas em dimensão
description: Este procedimento mostra como definir uma configuração para um produto baseado na dimensão.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductMaintainWorkspace, EcoResProductOpenCasesFormPart, EcoResProductDetailsExtended, EcoResDimensionBasedConfiguration, ConfigChooseFromRoute, ConfigChooseFromGroup, ConfigChoiceApprove
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9190d6dfd4b3f6cf0634e86845e7de028631bdd4
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "328576"
---
# <a name="create-dimension-based-configurations"></a><span data-ttu-id="33884-103">Criar configurações baseadas em dimensão</span><span class="sxs-lookup"><span data-stu-id="33884-103">Create dimension-based configurations</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="33884-104">Este procedimento mostra como definir uma configuração para um produto baseado na dimensão.</span><span class="sxs-lookup"><span data-stu-id="33884-104">This procedure shows how to define a configuration for a dimension-based product.</span></span> <span data-ttu-id="33884-105">Este é o último procedimento da série que explica como criar combinações para configuração baseada em dimensão.</span><span class="sxs-lookup"><span data-stu-id="33884-105">This is the last procedure in the series that explains how to build combinations for dimension-based configuration.</span></span> <span data-ttu-id="33884-106">A execução desse procedimento depende dos dados criados nos sete registros anteriores.</span><span class="sxs-lookup"><span data-stu-id="33884-106">The execution of this procedure is dependent on the data created in the previous seven recordings.</span></span> <span data-ttu-id="33884-107">A empresa de dados demo usada para criar este procedimento é USMF.</span><span class="sxs-lookup"><span data-stu-id="33884-107">The demo data company used to create this procedure is USMF.</span></span>


## <a name="find-the-dimension-based-product-master"></a><span data-ttu-id="33884-108">Encontre o produto mestre baseado na dimensão</span><span class="sxs-lookup"><span data-stu-id="33884-108">Find the dimension-based product master</span></span>
1. <span data-ttu-id="33884-109">Clique em Manutenção de produto liberado.</span><span class="sxs-lookup"><span data-stu-id="33884-109">Click Released product maintenance.</span></span>
2. <span data-ttu-id="33884-110">Clique em Produtos liberados.</span><span class="sxs-lookup"><span data-stu-id="33884-110">Click Released products.</span></span>
3. <span data-ttu-id="33884-111">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="33884-111">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="33884-112">Selecione o produto mestre baseado na dimensão que você criou no primeiro registro nesta sequência de 8 registros.</span><span class="sxs-lookup"><span data-stu-id="33884-112">Select the dimension-based product master that you created in the first recording in this sequence of 8 recordings.</span></span>  

## <a name="create-configurations"></a><span data-ttu-id="33884-113">Criar configurações</span><span class="sxs-lookup"><span data-stu-id="33884-113">Create configurations</span></span>
1. <span data-ttu-id="33884-114">No Painel de Ação Engenharia, clique em Manter configurações.</span><span class="sxs-lookup"><span data-stu-id="33884-114">On the Engineering Action Pane, click Maintain configurations.</span></span>
2. <span data-ttu-id="33884-115">Clique em Configurar.</span><span class="sxs-lookup"><span data-stu-id="33884-115">Click Configure.</span></span>
3. <span data-ttu-id="33884-116">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="33884-116">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="33884-117">No campo Número do item, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="33884-117">In the Item number field, enter or select a value.</span></span>
    * <span data-ttu-id="33884-118">Selecione um dos itens no grupo de configuração.</span><span class="sxs-lookup"><span data-stu-id="33884-118">Select any of the items in the first configuration group.</span></span>  
5. <span data-ttu-id="33884-119">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="33884-119">In the list, find and select the desired record.</span></span>
6. <span data-ttu-id="33884-120">No campo Número do item, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="33884-120">In the Item number field, enter or select a value.</span></span>
    * <span data-ttu-id="33884-121">Selecione qualquer item do segundo grupo de configuração.</span><span class="sxs-lookup"><span data-stu-id="33884-121">Select any item from the second configuration group.</span></span>  
7. <span data-ttu-id="33884-122">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="33884-122">Click OK.</span></span>
8. <span data-ttu-id="33884-123">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="33884-123">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="33884-124">No campo Configuração, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="33884-124">In the Configuration field, type a value.</span></span>
    * <span data-ttu-id="33884-125">Insira um nome de configuração que seja de fácil identificação da configuração.</span><span class="sxs-lookup"><span data-stu-id="33884-125">Enter a configuration name that will make it easy to identify the configuration.</span></span>  
10. <span data-ttu-id="33884-126">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="33884-126">In the Description field, type a value.</span></span>
    * <span data-ttu-id="33884-127">Insira uma descrição da configuração para explicar o que ela contém.</span><span class="sxs-lookup"><span data-stu-id="33884-127">Enter a description of the configuration to explain what it contains.</span></span>  
11. <span data-ttu-id="33884-128">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="33884-128">Click OK.</span></span>

