---
title: 'Criar elementos de custo  '
description: Há várias maneiras de criar elementos de custo na Contabilização de custos.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CAMDimension, CAMAXMainAccountDimensionMemberProviderConfiguration, CAMDimensionMember
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 87f93fd7c1c42045274d6b89847b27e93614d9a4
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/10/2020
ms.locfileid: "3976130"
---
# <a name="create-cost-elements"></a><span data-ttu-id="a9ba3-103">Criar elementos de custo  </span><span class="sxs-lookup"><span data-stu-id="a9ba3-103">Create cost elements</span></span> 

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="a9ba3-104">Há várias maneiras de criar elementos de custo na Contabilização de custos.</span><span class="sxs-lookup"><span data-stu-id="a9ba3-104">There are several ways to create cost elements in Cost accounting.</span></span> <span data-ttu-id="a9ba3-105">Este procedimento mostra como criar elementos de custo importando as contas principais por meio de um conector de dados.</span><span class="sxs-lookup"><span data-stu-id="a9ba3-105">This procedure shows how to create cost elements by importing main accounts via a data connector.</span></span> <span data-ttu-id="a9ba3-106">A empresa de demonstração USMF foi usada para criar este procedimento.</span><span class="sxs-lookup"><span data-stu-id="a9ba3-106">The USMF demo company was used to create this procedure.</span></span> <span data-ttu-id="a9ba3-107">Este procedimento é para um recurso de Contabilização de custos que foi adicionado à versão 1611 do Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="a9ba3-107">This procedure is for a Cost accounting feature that was added in Dynamics 365 for Operations, version 1611.</span></span>


## <a name="create-new-cost-elements"></a><span data-ttu-id="a9ba3-108">Criar novos elementos de custo</span><span class="sxs-lookup"><span data-stu-id="a9ba3-108">Create new cost elements</span></span>
1. <span data-ttu-id="a9ba3-109">Vá para Contabilização de custos > Dimensões > Dimensões do elemento de custo.</span><span class="sxs-lookup"><span data-stu-id="a9ba3-109">Go to Cost accounting > Dimensions > Cost element dimensions.</span></span>
2. <span data-ttu-id="a9ba3-110">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="a9ba3-110">Click New.</span></span>
3. <span data-ttu-id="a9ba3-111">No campo Nome, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="a9ba3-111">In the Name field, type a value.</span></span>
4. <span data-ttu-id="a9ba3-112">No campo Conector de dados para membros de dimensões, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="a9ba3-112">In the Data connector for dimension members field, enter or select a value.</span></span>
5. <span data-ttu-id="a9ba3-113">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="a9ba3-113">In the Description field, type a value.</span></span>
6. <span data-ttu-id="a9ba3-114">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="a9ba3-114">Click Save.</span></span>

## <a name="configure-the-data-connector"></a><span data-ttu-id="a9ba3-115">Configurar o conector de dados</span><span class="sxs-lookup"><span data-stu-id="a9ba3-115">Configure the data connector</span></span>
1. <span data-ttu-id="a9ba3-116">Clique em Configurar provedor de membro de dimensão.</span><span class="sxs-lookup"><span data-stu-id="a9ba3-116">Click Configure dimension member provider.</span></span>
2. <span data-ttu-id="a9ba3-117">No campo Plano de contas, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="a9ba3-117">In the Chart of accounts field, enter or select a value.</span></span>
    * <span data-ttu-id="a9ba3-118">Selecione Compartilhado para usar o plano de contas compartilhado.</span><span class="sxs-lookup"><span data-stu-id="a9ba3-118">Select Shared to use the shared chart of accounts.</span></span>  
3. <span data-ttu-id="a9ba3-119">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="a9ba3-119">Click New.</span></span>
4. <span data-ttu-id="a9ba3-120">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="a9ba3-120">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="a9ba3-121">Você pode aplicar filtros às contas para que atendam a seus critérios.</span><span class="sxs-lookup"><span data-stu-id="a9ba3-121">You can apply filters to accounts to meet your criteria.</span></span>  
5. <span data-ttu-id="a9ba3-122">No campo Da conta principal, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="a9ba3-122">In the From main account field, enter or select a value.</span></span>
6. <span data-ttu-id="a9ba3-123">No campo Para conta principal, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="a9ba3-123">In the To main account field, enter or select a value.</span></span>
7. <span data-ttu-id="a9ba3-124">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="a9ba3-124">Click OK.</span></span>

## <a name="import-main-accounts"></a><span data-ttu-id="a9ba3-125">Importar contas principais</span><span class="sxs-lookup"><span data-stu-id="a9ba3-125">Import main accounts</span></span>
1. <span data-ttu-id="a9ba3-126">Clique em Importar membros da dimensão.</span><span class="sxs-lookup"><span data-stu-id="a9ba3-126">Click Import dimension members.</span></span>
    * <span data-ttu-id="a9ba3-127">As contas principais serão importadas para a Contabilização de custos e usadas como elementos de custo.</span><span class="sxs-lookup"><span data-stu-id="a9ba3-127">Main accounts will be imported into Cost accounting and used as cost elements.</span></span>  
2. <span data-ttu-id="a9ba3-128">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="a9ba3-128">Click OK.</span></span>

## <a name="view-the-imported-accounts-as-cost-elements"></a><span data-ttu-id="a9ba3-129">Exibir as contas importadas como elementos de custo</span><span class="sxs-lookup"><span data-stu-id="a9ba3-129">View the imported accounts as cost elements</span></span>
1. <span data-ttu-id="a9ba3-130">Clique em Exibir membros da dimensão.</span><span class="sxs-lookup"><span data-stu-id="a9ba3-130">Click View dimension members.</span></span>
    * <span data-ttu-id="a9ba3-131">Exiba as contas contábeis importadas como elementos de custo na empresa para a qual os custos possam fluir.</span><span class="sxs-lookup"><span data-stu-id="a9ba3-131">View the imported ledger accounts as cost elements in your business that costs can flow to.</span></span>  

