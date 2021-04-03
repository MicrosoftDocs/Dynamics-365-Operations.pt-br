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
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 91c25c52a2c6dc7f096a494577b361ff30406e9c
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5236785"
---
# <a name="create-cost-objects"></a><span data-ttu-id="e9923-103">Criar objetos de custos  </span><span class="sxs-lookup"><span data-stu-id="e9923-103">Create cost objects</span></span> 

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="e9923-104">Este procedimento mostra como criar objetos de custo importando a dimensão financeira do centro de custo para a Contabilidade de custos por meio de um conector de dados.</span><span class="sxs-lookup"><span data-stu-id="e9923-104">This procedure shows how to create cost objects by importing the cost center financial dimension into Cost accounting via a data connector.</span></span> <span data-ttu-id="e9923-105">A empresa de demonstração USMF foi usada para criar este procedimento.</span><span class="sxs-lookup"><span data-stu-id="e9923-105">The USMF demo company was used to create this procedure.</span></span> 


## <a name="create-new-cost-objects"></a><span data-ttu-id="e9923-106">Criar novos objetos de custo</span><span class="sxs-lookup"><span data-stu-id="e9923-106">Create new cost objects</span></span>
1. <span data-ttu-id="e9923-107">Vá para Contabilização de custos > Dimensões > Dimensões do objeto de custo.</span><span class="sxs-lookup"><span data-stu-id="e9923-107">Go to Cost accounting > Dimensions > Cost object dimensions.</span></span>
2. <span data-ttu-id="e9923-108">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="e9923-108">Click New.</span></span>
3. <span data-ttu-id="e9923-109">No campo Nome, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="e9923-109">In the Name field, type a value.</span></span>
4. <span data-ttu-id="e9923-110">No campo Conector de dados para membros de dimensões, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="e9923-110">In the Data connector for dimension members field, enter or select a value.</span></span>
5. <span data-ttu-id="e9923-111">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="e9923-111">In the Description field, type a value.</span></span>
6. <span data-ttu-id="e9923-112">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="e9923-112">Click Save.</span></span>

## <a name="configure-the-data-connector"></a><span data-ttu-id="e9923-113">Configurar o conector de dados</span><span class="sxs-lookup"><span data-stu-id="e9923-113">Configure the data connector</span></span>
1. <span data-ttu-id="e9923-114">Clique em Configurar provedor de membro de dimensão.</span><span class="sxs-lookup"><span data-stu-id="e9923-114">Click Configure dimension member provider.</span></span>
    * <span data-ttu-id="e9923-115">Selecione CostCenter para importar a dimensão do CostCenter para a Contabilização de custos.</span><span class="sxs-lookup"><span data-stu-id="e9923-115">Select CostCenter to import the CostCenter dimension into Cost accounting.</span></span>  
2. <span data-ttu-id="e9923-116">No campo Nome da dimensão, selecione Centro de custo.</span><span class="sxs-lookup"><span data-stu-id="e9923-116">In the Dimension name field, select Cost center.</span></span>
3. <span data-ttu-id="e9923-117">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="e9923-117">Click OK.</span></span>

## <a name="import-cost-centers"></a><span data-ttu-id="e9923-118">Importar centros de custos</span><span class="sxs-lookup"><span data-stu-id="e9923-118">Import cost centers</span></span>
1. <span data-ttu-id="e9923-119">Clique em Importar membros da dimensão.</span><span class="sxs-lookup"><span data-stu-id="e9923-119">Click Import dimension members.</span></span>
2. <span data-ttu-id="e9923-120">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="e9923-120">Click OK.</span></span>

## <a name="view-the-imported-cost-centers"></a><span data-ttu-id="e9923-121">Exibir os centros de custo importados</span><span class="sxs-lookup"><span data-stu-id="e9923-121">View the imported cost centers</span></span>
1. <span data-ttu-id="e9923-122">Clique em Exibir membros da dimensão.</span><span class="sxs-lookup"><span data-stu-id="e9923-122">Click View dimension members.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]