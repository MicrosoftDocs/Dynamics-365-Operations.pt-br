---
title: 'Criar objetos de custos  '
description: Este procedimento mostra como criar objetos de custo importando a dimensão financeira do centro de custo para a Contabilidade de custos por meio de um conector de dados.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CAMDimension, CAMAXFinancialDimensionMemberProviderConfiguration, CAMDimensionMember
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ed020348e50158362fda7b6b36dcdb17c48b4532
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3142308"
---
# <a name="create-cost-objects"></a><span data-ttu-id="25b44-103">Criar objetos de custos  </span><span class="sxs-lookup"><span data-stu-id="25b44-103">Create cost objects</span></span> 

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="25b44-104">Este procedimento mostra como criar objetos de custo importando a dimensão financeira do centro de custo para a Contabilidade de custos por meio de um conector de dados.</span><span class="sxs-lookup"><span data-stu-id="25b44-104">This procedure shows how to create cost objects by importing the cost center financial dimension into Cost accounting via a data connector.</span></span> <span data-ttu-id="25b44-105">A empresa de demonstração USMF foi usada para criar este procedimento.</span><span class="sxs-lookup"><span data-stu-id="25b44-105">The USMF demo company was used to create this procedure.</span></span> 


## <a name="create-new-cost-objects"></a><span data-ttu-id="25b44-106">Criar novos objetos de custo</span><span class="sxs-lookup"><span data-stu-id="25b44-106">Create new cost objects</span></span>
1. <span data-ttu-id="25b44-107">Vá para Contabilização de custos > Dimensões > Dimensões do objeto de custo.</span><span class="sxs-lookup"><span data-stu-id="25b44-107">Go to Cost accounting > Dimensions > Cost object dimensions.</span></span>
2. <span data-ttu-id="25b44-108">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="25b44-108">Click New.</span></span>
3. <span data-ttu-id="25b44-109">No campo Nome, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="25b44-109">In the Name field, type a value.</span></span>
4. <span data-ttu-id="25b44-110">No campo Conector de dados para membros de dimensões, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="25b44-110">In the Data connector for dimension members field, enter or select a value.</span></span>
5. <span data-ttu-id="25b44-111">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="25b44-111">In the Description field, type a value.</span></span>
6. <span data-ttu-id="25b44-112">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="25b44-112">Click Save.</span></span>

## <a name="configure-the-data-connector"></a><span data-ttu-id="25b44-113">Configurar o conector de dados</span><span class="sxs-lookup"><span data-stu-id="25b44-113">Configure the data connector</span></span>
1. <span data-ttu-id="25b44-114">Clique em Configurar provedor de membro de dimensão.</span><span class="sxs-lookup"><span data-stu-id="25b44-114">Click Configure dimension member provider.</span></span>
    * <span data-ttu-id="25b44-115">Selecione CostCenter para importar a dimensão do CostCenter para a Contabilização de custos.</span><span class="sxs-lookup"><span data-stu-id="25b44-115">Select CostCenter to import the CostCenter dimension into Cost accounting.</span></span>  
2. <span data-ttu-id="25b44-116">No campo Nome da dimensão, selecione Centro de custo.</span><span class="sxs-lookup"><span data-stu-id="25b44-116">In the Dimension name field, select Cost center.</span></span>
3. <span data-ttu-id="25b44-117">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="25b44-117">Click OK.</span></span>

## <a name="import-cost-centers"></a><span data-ttu-id="25b44-118">Importar centros de custos</span><span class="sxs-lookup"><span data-stu-id="25b44-118">Import cost centers</span></span>
1. <span data-ttu-id="25b44-119">Clique em Importar membros da dimensão.</span><span class="sxs-lookup"><span data-stu-id="25b44-119">Click Import dimension members.</span></span>
2. <span data-ttu-id="25b44-120">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="25b44-120">Click OK.</span></span>

## <a name="view-the-imported-cost-centers"></a><span data-ttu-id="25b44-121">Exibir os centros de custo importados</span><span class="sxs-lookup"><span data-stu-id="25b44-121">View the imported cost centers</span></span>
1. <span data-ttu-id="25b44-122">Clique em Exibir membros da dimensão.</span><span class="sxs-lookup"><span data-stu-id="25b44-122">Click View dimension members.</span></span>

