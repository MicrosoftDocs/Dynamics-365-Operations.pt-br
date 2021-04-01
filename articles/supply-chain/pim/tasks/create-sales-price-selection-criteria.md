---
title: Criar critérios de seleção de preço de venda
description: Este procedimento mostra como criar um critério de seleção preço de venda para modelos de preço de vendas baseado em atributo.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCPriceModelSelectionCriteria, SysQueryForm, SysQueryTableLookUp, SysQueryFieldLookUp
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 84cef2cbf6f9783f0629fe068a4779a99dca9711
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5258581"
---
# <a name="create-sales-price-selection-criteria"></a><span data-ttu-id="f3076-103">Criar critérios de seleção de preço de venda</span><span class="sxs-lookup"><span data-stu-id="f3076-103">Create sales price selection criteria</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="f3076-104">Este procedimento mostra como criar um critério de seleção preço de venda para modelos de preço de vendas baseado em atributo.</span><span class="sxs-lookup"><span data-stu-id="f3076-104">This procedure shows how to create a sales price selection criterion for attribute-based sales price models.</span></span> <span data-ttu-id="f3076-105">Este procedimento exige que pelo menos um modelo de preço de vendas esteja disponível.</span><span class="sxs-lookup"><span data-stu-id="f3076-105">This procedure requires that at least one sales price model be available.</span></span> <span data-ttu-id="f3076-106">Este exemplo usa o modelo de preço para o modelo de preço de vendas de solução do Palestrante na empresa de dados demo USMF.</span><span class="sxs-lookup"><span data-stu-id="f3076-106">This example uses the price model for the Speaker solution sales price model in the USMF demo data company.</span></span> <span data-ttu-id="f3076-107">Normalmente, um gerente de produto usa este procedimento.</span><span class="sxs-lookup"><span data-stu-id="f3076-107">Typically, a product manager uses this procedure.</span></span>


## <a name="add-a-new-criterion-for-an-existing-sales-price-model"></a><span data-ttu-id="f3076-108">Adicionar um novo critério para um modelo existente de preço de venda</span><span class="sxs-lookup"><span data-stu-id="f3076-108">Add a new criterion for an existing sales price model</span></span>
1. <span data-ttu-id="f3076-109">Clique em Definição de modelo de variante de produto.</span><span class="sxs-lookup"><span data-stu-id="f3076-109">Click Product variant model definition.</span></span>
2. <span data-ttu-id="f3076-110">Clique em Modelos de configuração do produto.</span><span class="sxs-lookup"><span data-stu-id="f3076-110">Click Product configuration models.</span></span>
3. <span data-ttu-id="f3076-111">Na lista, selecione a linha do modelo de produto de solução do Palestrante, mas não clique no link para o nome do modelo.</span><span class="sxs-lookup"><span data-stu-id="f3076-111">In the list, select the row for the Speaker solution product model, but don't click the link for the model name.</span></span>
4. <span data-ttu-id="f3076-112">No Painel de Ação, clique em Modelo.</span><span class="sxs-lookup"><span data-stu-id="f3076-112">On the Action Pane, click Model.</span></span>
5. <span data-ttu-id="f3076-113">Clique em Critério de modelo de preço.</span><span class="sxs-lookup"><span data-stu-id="f3076-113">Click Price model criteria.</span></span>
6. <span data-ttu-id="f3076-114">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="f3076-114">Click New.</span></span>
7. <span data-ttu-id="f3076-115">No campo Nome, digite "Grupo de clientes 10".</span><span class="sxs-lookup"><span data-stu-id="f3076-115">In the Name field, type 'Customer group 10'.</span></span>
    * <span data-ttu-id="f3076-116">O nome do critério de modelo de preço é usado para ajudar a identificar os critérios de seleção subjacentes.</span><span class="sxs-lookup"><span data-stu-id="f3076-116">The name of the price model criterion is used to help identify the underlying selection criteria.</span></span>  
8. <span data-ttu-id="f3076-117">No campo Modelo de preço, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="f3076-117">In the Price model field, enter or select a value.</span></span>
9. <span data-ttu-id="f3076-118">No campo Tipo de ordem, selecione Ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="f3076-118">In the Order type field, select Sales order.</span></span>
    * <span data-ttu-id="f3076-119">O tipo de ordem determina os campos de base de dados que estão disponíveis para a consulta de seleção.</span><span class="sxs-lookup"><span data-stu-id="f3076-119">The order type determines the database fields that will be available for the selection query.</span></span>  
10. <span data-ttu-id="f3076-120">No campo Validar de, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="f3076-120">In the Valid from field, enter a date.</span></span>
11. <span data-ttu-id="f3076-121">No campo Expirar em, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="f3076-121">In the Expire by field, enter a date.</span></span>
12. <span data-ttu-id="f3076-122">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="f3076-122">Click Save.</span></span>

## <a name="create-the-query-for-the-selection-criteria"></a><span data-ttu-id="f3076-123">Criar uma consulta para o critério de seleção</span><span class="sxs-lookup"><span data-stu-id="f3076-123">Create the query for the selection criteria</span></span>
1. <span data-ttu-id="f3076-124">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="f3076-124">Click Edit.</span></span>
2. <span data-ttu-id="f3076-125">No campo Tabela, selecione Clientes.</span><span class="sxs-lookup"><span data-stu-id="f3076-125">In the Table field, select Customers.</span></span> 
3. <span data-ttu-id="f3076-126">No campo Campo, selecione Grupo de cliente.</span><span class="sxs-lookup"><span data-stu-id="f3076-126">In the Field field, select Customer group.</span></span>
    * <span data-ttu-id="f3076-127">Neste exemplo, usaremos um grupo de clientes específico para os critérios de seleção.</span><span class="sxs-lookup"><span data-stu-id="f3076-127">In this example, we will use a specific customer group for the selection criteria.</span></span>  
4. <span data-ttu-id="f3076-128">No campo Critérios, selecione Grupo de cliente 10.</span><span class="sxs-lookup"><span data-stu-id="f3076-128">In the Criteria field, select Customer group 10.</span></span> 
5. <span data-ttu-id="f3076-129">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="f3076-129">Click OK.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]