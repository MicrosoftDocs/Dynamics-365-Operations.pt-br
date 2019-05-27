---
title: 'Criar objetos de custos  '
description: Este procedimento mostra como criar objetos de custo importando a dimensão financeira do centro de custos do Dynamics 365 for Finance and Operations, Enterprise edition para a Contabilização de custos por meio de um conector de dados.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CAMDimension, CAMAXFinancialDimensionMemberProviderConfiguration, CAMDimensionMember
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1e12de1d51658092fb19f652cef7c1cc78b255b5
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1543762"
---
# <a name="create-cost-objects"></a><span data-ttu-id="cf997-103">Criar objetos de custos  </span><span class="sxs-lookup"><span data-stu-id="cf997-103">Create cost objects</span></span> 

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="cf997-104">Este procedimento mostra como criar objetos de custo importando a dimensão financeira do centro de custos do Dynamics 365 for Finance and Operations, Enterprise edition para a Contabilização de custos por meio de um conector de dados.</span><span class="sxs-lookup"><span data-stu-id="cf997-104">This procedure shows how to create cost objects by importing the Dynamics 365 for Finance and Operations, Enterprise edition cost center financial dimension into Cost accounting via a data connector.</span></span> <span data-ttu-id="cf997-105">A empresa de demonstração USMF foi usada para criar este procedimento.</span><span class="sxs-lookup"><span data-stu-id="cf997-105">The USMF demo company was used to create this procedure.</span></span> <span data-ttu-id="cf997-106">Este procedimento é para um recurso de Contabilização de custos que foi adicionado à versão 1611 do Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="cf997-106">This procedure is for a Cost accounting feature that was added in Dynamics 365 for Operations, version 1611.</span></span>


## <a name="create-new-cost-objects"></a><span data-ttu-id="cf997-107">Criar novos objetos de custo</span><span class="sxs-lookup"><span data-stu-id="cf997-107">Create new cost objects</span></span>
1. <span data-ttu-id="cf997-108">Vá para Contabilização de custos > Dimensões > Dimensões do objeto de custo.</span><span class="sxs-lookup"><span data-stu-id="cf997-108">Go to Cost accounting > Dimensions > Cost object dimensions.</span></span>
2. <span data-ttu-id="cf997-109">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="cf997-109">Click New.</span></span>
3. <span data-ttu-id="cf997-110">No campo Nome, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="cf997-110">In the Name field, type a value.</span></span>
4. <span data-ttu-id="cf997-111">No campo Conector de dados para membros de dimensões, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="cf997-111">In the Data connector for dimension members field, enter or select a value.</span></span>
5. <span data-ttu-id="cf997-112">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="cf997-112">In the Description field, type a value.</span></span>
6. <span data-ttu-id="cf997-113">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="cf997-113">Click Save.</span></span>

## <a name="configure-the-data-connector"></a><span data-ttu-id="cf997-114">Configurar o conector de dados</span><span class="sxs-lookup"><span data-stu-id="cf997-114">Configure the data connector</span></span>
1. <span data-ttu-id="cf997-115">Clique em Configurar provedor de membro de dimensão.</span><span class="sxs-lookup"><span data-stu-id="cf997-115">Click Configure dimension member provider.</span></span>
    * <span data-ttu-id="cf997-116">Selecione CostCenter para importar a dimensão do CostCenter para a Contabilização de custos.</span><span class="sxs-lookup"><span data-stu-id="cf997-116">Select CostCenter to import the CostCenter dimension into Cost accounting.</span></span>  
2. <span data-ttu-id="cf997-117">No campo Nome da dimensão, selecione Centro de custo.</span><span class="sxs-lookup"><span data-stu-id="cf997-117">In the Dimension name field, select Cost center.</span></span>
3. <span data-ttu-id="cf997-118">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="cf997-118">Click OK.</span></span>

## <a name="import-cost-centers"></a><span data-ttu-id="cf997-119">Importar centros de custos</span><span class="sxs-lookup"><span data-stu-id="cf997-119">Import cost centers</span></span>
1. <span data-ttu-id="cf997-120">Clique em Importar membros da dimensão.</span><span class="sxs-lookup"><span data-stu-id="cf997-120">Click Import dimension members.</span></span>
2. <span data-ttu-id="cf997-121">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="cf997-121">Click OK.</span></span>

## <a name="view-the-imported-cost-centers"></a><span data-ttu-id="cf997-122">Exibir os centros de custo importados</span><span class="sxs-lookup"><span data-stu-id="cf997-122">View the imported cost centers</span></span>
1. <span data-ttu-id="cf997-123">Clique em Exibir membros da dimensão.</span><span class="sxs-lookup"><span data-stu-id="cf997-123">Click View dimension members.</span></span>

