---
title: Manter BOM para um modelo de configuração de produtos
description: Executar este procedimento exige um modelo de configuração de produto existente.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails, PCBOMLineDetails, InventItemIdLookupSimple
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 49aa17aa376f8536e9d2290292f877d314c2c078
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5818004"
---
# <a name="maintain-bom-for-a-product-configuration-model"></a><span data-ttu-id="40463-103">Manter BOM para um modelo de configuração de produtos</span><span class="sxs-lookup"><span data-stu-id="40463-103">Maintain BOM for a product configuration model</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="40463-104">Executar este procedimento exige um modelo de configuração de produto existente.</span><span class="sxs-lookup"><span data-stu-id="40463-104">Running this procedure requires an existing product configuration model.</span></span> <span data-ttu-id="40463-105">O modelo de alto-falante avançado na empresa de demonstração USMF é usado para criar este procedimento.</span><span class="sxs-lookup"><span data-stu-id="40463-105">The High end speaker model in the demo company USMF is used to create this procedure.</span></span>


## <a name="add-a-bom-line"></a><span data-ttu-id="40463-106">Adicione uma linha da BOM</span><span class="sxs-lookup"><span data-stu-id="40463-106">Add a BOM line</span></span>
1. <span data-ttu-id="40463-107">Clique em Definição de modelo de variante de produto.</span><span class="sxs-lookup"><span data-stu-id="40463-107">Click Product variant model definition.</span></span>
2. <span data-ttu-id="40463-108">Clique em Modelos de configuração do produto.</span><span class="sxs-lookup"><span data-stu-id="40463-108">Click Product configuration models.</span></span>
3. <span data-ttu-id="40463-109">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="40463-109">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="40463-110">Selecione o alto-falante avançado para este procedimento.</span><span class="sxs-lookup"><span data-stu-id="40463-110">Select the High end speaker for this procedure.</span></span>  
4. <span data-ttu-id="40463-111">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="40463-111">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="40463-112">Expandir a seção Linhas de BOM.</span><span class="sxs-lookup"><span data-stu-id="40463-112">Expand the BOM lines section.</span></span>
6. <span data-ttu-id="40463-113">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="40463-113">Click Add.</span></span>
7. <span data-ttu-id="40463-114">No campo Nome, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="40463-114">In the Name field, type a value.</span></span>
8. <span data-ttu-id="40463-115">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="40463-115">In the Description field, type a value.</span></span>
9. <span data-ttu-id="40463-116">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="40463-116">Click Save.</span></span>

## <a name="add-bom-line-details"></a><span data-ttu-id="40463-117">Adicione Detalhes da linha de BOM</span><span class="sxs-lookup"><span data-stu-id="40463-117">Add BOM line details</span></span>
1. <span data-ttu-id="40463-118">Clique em Detalhes da linha de BOM.</span><span class="sxs-lookup"><span data-stu-id="40463-118">Click BOM line details.</span></span>
2. <span data-ttu-id="40463-119">No campo Número do item, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="40463-119">In the Item number field, enter or select a value.</span></span>
    * <span data-ttu-id="40463-120">Por exemplo, você pode selecionar o item M0055.</span><span class="sxs-lookup"><span data-stu-id="40463-120">For example, you can select the item M0055.</span></span>  
    * <span data-ttu-id="40463-121">Para cada propriedade da linha da BOM, você pode selecionar se ela tem um valor fixo ou está mapeada a um atributo.</span><span class="sxs-lookup"><span data-stu-id="40463-121">For each BOM line property, you can select if it takes a fixed value or is mapped to an attribute.</span></span>  
3. <span data-ttu-id="40463-122">Marque a caixa de seleção Definir.</span><span class="sxs-lookup"><span data-stu-id="40463-122">Select the Set check box.</span></span>
4. <span data-ttu-id="40463-123">Selecione Sim no campo Cálculo.</span><span class="sxs-lookup"><span data-stu-id="40463-123">Select Yes in the Calculation field.</span></span>
    * <span data-ttu-id="40463-124">Definindo a propriedade Cálculo como Sim garante que a linha da BOM seja incluída em cálculos de custo.</span><span class="sxs-lookup"><span data-stu-id="40463-124">Setting the Calculation property to Yes ensures that the BOM line is included in cost calculations.</span></span>  
5. <span data-ttu-id="40463-125">Clique na guia Configuração.</span><span class="sxs-lookup"><span data-stu-id="40463-125">Click the Setup tab.</span></span>
6. <span data-ttu-id="40463-126">Marque a caixa de seleção Definir.</span><span class="sxs-lookup"><span data-stu-id="40463-126">Select the Set check box.</span></span>
7. <span data-ttu-id="40463-127">No campo Quantidade, insira um número.</span><span class="sxs-lookup"><span data-stu-id="40463-127">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="40463-128">O campo Quantidade determina a quantidade do item que será incluída na BOM.</span><span class="sxs-lookup"><span data-stu-id="40463-128">The quantity field determines how much of the item that will be included in the BOM.</span></span> <span data-ttu-id="40463-129">Pode ser um candidato óbvio para um mapeamento de atributos.</span><span class="sxs-lookup"><span data-stu-id="40463-129">This could be an obvious candidate for an attribute mapping.</span></span>  
8. <span data-ttu-id="40463-130">Clique na guia Dimensão.</span><span class="sxs-lookup"><span data-stu-id="40463-130">Click the Dimension tab.</span></span>
    * <span data-ttu-id="40463-131">Verifique qualquer uma das dimensões do produto estão ativas, e consequentemente deve ter um valor ou um atributo atribuído.</span><span class="sxs-lookup"><span data-stu-id="40463-131">Verify if any of the product dimensions are active,  and therefore must have a value or attribute assigned.</span></span>  
9. <span data-ttu-id="40463-132">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="40463-132">Click OK.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]