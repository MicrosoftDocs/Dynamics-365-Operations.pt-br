---
title: Criar critérios de seleção de preço de venda
description: Este procedimento mostra como criar um critério de seleção preço de venda para modelos de preço de vendas baseado em atributo.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCPriceModelSelectionCriteria, SysQueryForm, SysQueryTableLookUp, SysQueryFieldLookUp
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 69d22c3321beaa2667ee20bff00acd746714b993
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/20/2021
ms.locfileid: "5920522"
---
# <a name="create-sales-price-selection-criteria"></a><span data-ttu-id="9b265-103">Criar critérios de seleção de preço de venda</span><span class="sxs-lookup"><span data-stu-id="9b265-103">Create sales price selection criteria</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="9b265-104">Este procedimento mostra como criar um critério de seleção preço de venda para modelos de preço de vendas baseado em atributo.</span><span class="sxs-lookup"><span data-stu-id="9b265-104">This procedure shows how to create a sales price selection criterion for attribute-based sales price models.</span></span> <span data-ttu-id="9b265-105">Este procedimento exige que pelo menos um modelo de preço de vendas esteja disponível.</span><span class="sxs-lookup"><span data-stu-id="9b265-105">This procedure requires that at least one sales price model be available.</span></span> <span data-ttu-id="9b265-106">Este exemplo usa o modelo de preço para o modelo de preço de vendas de solução do Palestrante na empresa de dados demo USMF.</span><span class="sxs-lookup"><span data-stu-id="9b265-106">This example uses the price model for the Speaker solution sales price model in the USMF demo data company.</span></span> <span data-ttu-id="9b265-107">Normalmente, um gerente de produto usa este procedimento.</span><span class="sxs-lookup"><span data-stu-id="9b265-107">Typically, a product manager uses this procedure.</span></span>

## <a name="add-a-new-criterion-for-an-existing-sales-price-model"></a><span data-ttu-id="9b265-108">Adicionar um novo critério para um modelo existente de preço de venda</span><span class="sxs-lookup"><span data-stu-id="9b265-108">Add a new criterion for an existing sales price model</span></span>

1. <span data-ttu-id="9b265-109">Vá para **Gerenciamento de informações do produto \> Produtos \> Modelos de configuração do produto**.</span><span class="sxs-lookup"><span data-stu-id="9b265-109">Go to **Product information management \> Products \> Product configuration models**.</span></span>
1. <span data-ttu-id="9b265-110">Na lista, selecione a linha do modelo de produto de solução do Palestrante, mas não selecione o link para o nome do modelo.</span><span class="sxs-lookup"><span data-stu-id="9b265-110">In the list, select the row for the Speaker solution product model, but don't select the link for the model name.</span></span>
1. <span data-ttu-id="9b265-111">No Painel de Ação, selecione **Modelo**.</span><span class="sxs-lookup"><span data-stu-id="9b265-111">On the Action Pane, select **Model**.</span></span>
1. <span data-ttu-id="9b265-112">Selecione **Critérios de modelo de preço**.</span><span class="sxs-lookup"><span data-stu-id="9b265-112">Select **Price model criteria**.</span></span>
1. <span data-ttu-id="9b265-113">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="9b265-113">Select **New**.</span></span>
1. <span data-ttu-id="9b265-114">No campo **Nome**, digite 'Grupo de clientes 10'.</span><span class="sxs-lookup"><span data-stu-id="9b265-114">In the **Name** field, type 'Customer group 10'.</span></span>
    * <span data-ttu-id="9b265-115">O nome do critério de modelo de preço é usado para ajudar a identificar os critérios de seleção subjacentes.</span><span class="sxs-lookup"><span data-stu-id="9b265-115">The name of the price model criterion is used to help identify the underlying selection criteria.</span></span>  
1. <span data-ttu-id="9b265-116">No campo **Modelo de preço**, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="9b265-116">In the **Price model** field, enter or select a value.</span></span>
1. <span data-ttu-id="9b265-117">No campo **Tipo de ordem**, selecione *Ordem de venda*.</span><span class="sxs-lookup"><span data-stu-id="9b265-117">In the **Order type** field, select *Sales order*.</span></span>
    * <span data-ttu-id="9b265-118">O tipo de ordem determina os campos de base de dados que estão disponíveis para a consulta de seleção.</span><span class="sxs-lookup"><span data-stu-id="9b265-118">The order type determines the database fields that will be available for the selection query.</span></span>  
1. <span data-ttu-id="9b265-119">No campo **Válido a partir de**, informe uma data.</span><span class="sxs-lookup"><span data-stu-id="9b265-119">In the **Valid from** field, enter a date.</span></span>
1. <span data-ttu-id="9b265-120">No campo **Expirar em**, informe uma data.</span><span class="sxs-lookup"><span data-stu-id="9b265-120">In the **Expire by** field, enter a date.</span></span>
1. <span data-ttu-id="9b265-121">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="9b265-121">Select **Save**.</span></span>

## <a name="create-the-query-for-the-selection-criteria"></a><span data-ttu-id="9b265-122">Criar uma consulta para o critério de seleção</span><span class="sxs-lookup"><span data-stu-id="9b265-122">Create the query for the selection criteria</span></span>

1. <span data-ttu-id="9b265-123">Selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="9b265-123">Select **Edit**.</span></span>
2. <span data-ttu-id="9b265-124">No campo **Tabela**, selecione *Clientes*.</span><span class="sxs-lookup"><span data-stu-id="9b265-124">In the **Table** field, select *Customers*.</span></span>
3. <span data-ttu-id="9b265-125">No campo **Campo**, selecione *Grupo de clientes*.</span><span class="sxs-lookup"><span data-stu-id="9b265-125">In the **Field** field, select *Customer group*.</span></span>
    * <span data-ttu-id="9b265-126">Neste exemplo, usaremos um grupo de clientes específico para os critérios de seleção.</span><span class="sxs-lookup"><span data-stu-id="9b265-126">In this example, we will use a specific customer group for the selection criteria.</span></span>  
4. <span data-ttu-id="9b265-127">No campo **Critérios**, selecione *Grupo de clientes 10*.</span><span class="sxs-lookup"><span data-stu-id="9b265-127">In the **Criteria** field, select *Customer group 10*.</span></span>
5. <span data-ttu-id="9b265-128">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="9b265-128">Select **OK**.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]