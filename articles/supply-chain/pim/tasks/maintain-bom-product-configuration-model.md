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
ms.openlocfilehash: b4ad73265e321b6339c061a7866b55cb2769954b
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/20/2021
ms.locfileid: "5921308"
---
# <a name="maintain-bom-for-a-product-configuration-model"></a><span data-ttu-id="b6d5e-103">Manter BOM para um modelo de configuração de produtos</span><span class="sxs-lookup"><span data-stu-id="b6d5e-103">Maintain BOM for a product configuration model</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="b6d5e-104">Executar este procedimento exige um modelo de configuração de produto existente.</span><span class="sxs-lookup"><span data-stu-id="b6d5e-104">Running this procedure requires an existing product configuration model.</span></span> <span data-ttu-id="b6d5e-105">O modelo de alto-falante avançado na empresa de demonstração USMF é usado para criar este procedimento.</span><span class="sxs-lookup"><span data-stu-id="b6d5e-105">The High end speaker model in the demo company USMF is used to create this procedure.</span></span>

## <a name="add-a-bom-line"></a><span data-ttu-id="b6d5e-106">Adicione uma linha da BOM</span><span class="sxs-lookup"><span data-stu-id="b6d5e-106">Add a BOM line</span></span>

1. <span data-ttu-id="b6d5e-107">Vá para **Gerenciamento de informações do produto \> Produtos \> Modelos de configuração do produto**.</span><span class="sxs-lookup"><span data-stu-id="b6d5e-107">Go to **Product information management \> Products \> Product configuration models**.</span></span>
1. <span data-ttu-id="b6d5e-108">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="b6d5e-108">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="b6d5e-109">Selecione o alto-falante avançado para este procedimento.</span><span class="sxs-lookup"><span data-stu-id="b6d5e-109">Select the High end speaker for this procedure.</span></span>  
1. <span data-ttu-id="b6d5e-110">Na lista, selecione o link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="b6d5e-110">In the list, select the link in the selected row.</span></span>
1. <span data-ttu-id="b6d5e-111">Expanda a seção **Linhas de BOM**.</span><span class="sxs-lookup"><span data-stu-id="b6d5e-111">Expand the **BOM lines** section.</span></span>
1. <span data-ttu-id="b6d5e-112">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="b6d5e-112">Select **Add**.</span></span>
1. <span data-ttu-id="b6d5e-113">No campo **Nome**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="b6d5e-113">In the **Name** field, type a value.</span></span>
1. <span data-ttu-id="b6d5e-114">No campo **Descrição**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="b6d5e-114">In the **Description** field, type a value.</span></span>
1. <span data-ttu-id="b6d5e-115">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="b6d5e-115">Select **Save**.</span></span>

## <a name="add-bom-line-details"></a><span data-ttu-id="b6d5e-116">Adicione Detalhes da linha de BOM</span><span class="sxs-lookup"><span data-stu-id="b6d5e-116">Add BOM line details</span></span>

1. <span data-ttu-id="b6d5e-117">Selecione **Detalhes da linha de BOM**.</span><span class="sxs-lookup"><span data-stu-id="b6d5e-117">Select **BOM line details**.</span></span>
2. <span data-ttu-id="b6d5e-118">No campo **Número do item**, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="b6d5e-118">In the **Item number** field, enter or select a value.</span></span>
    * <span data-ttu-id="b6d5e-119">Por exemplo, você pode selecionar o item M0055.</span><span class="sxs-lookup"><span data-stu-id="b6d5e-119">For example, you can select the item M0055.</span></span>  
    * <span data-ttu-id="b6d5e-120">Para cada propriedade da linha da BOM, você pode selecionar se ela tem um valor fixo ou está mapeada a um atributo.</span><span class="sxs-lookup"><span data-stu-id="b6d5e-120">For each BOM line property, you can select if it takes a fixed value or is mapped to an attribute.</span></span>  
3. <span data-ttu-id="b6d5e-121">Marque a caixa de seleção **Definir**.</span><span class="sxs-lookup"><span data-stu-id="b6d5e-121">Select the **Set** check box.</span></span>
4. <span data-ttu-id="b6d5e-122">Selecione *Sim* no campo **Cálculo**.</span><span class="sxs-lookup"><span data-stu-id="b6d5e-122">Select *Yes* in the **Calculation** field.</span></span>
    * <span data-ttu-id="b6d5e-123">Definir a propriedade **Cálculo** como *Sim* garante que a linha de BOM seja incluída em cálculos de custo.</span><span class="sxs-lookup"><span data-stu-id="b6d5e-123">Setting the **Calculation** property to *Yes* ensures that the BOM line is included in cost calculations.</span></span>  
5. <span data-ttu-id="b6d5e-124">Selecione a guia **Configuração**.</span><span class="sxs-lookup"><span data-stu-id="b6d5e-124">Select the **Setup** tab.</span></span>
6. <span data-ttu-id="b6d5e-125">Marque a caixa de seleção **Definir**.</span><span class="sxs-lookup"><span data-stu-id="b6d5e-125">Select the **Set** check box.</span></span>
7. <span data-ttu-id="b6d5e-126">No campo **Quantidade.**, insira um número</span><span class="sxs-lookup"><span data-stu-id="b6d5e-126">In the **Quantity** field, enter a number.</span></span>
    * <span data-ttu-id="b6d5e-127">O campo Quantidade determina a quantidade do item que será incluída na BOM.</span><span class="sxs-lookup"><span data-stu-id="b6d5e-127">The quantity field determines how much of the item that will be included in the BOM.</span></span> <span data-ttu-id="b6d5e-128">Pode ser um candidato óbvio para um mapeamento de atributos.</span><span class="sxs-lookup"><span data-stu-id="b6d5e-128">This could be an obvious candidate for an attribute mapping.</span></span>  
8. <span data-ttu-id="b6d5e-129">Selecione a guia **Dimensão**.</span><span class="sxs-lookup"><span data-stu-id="b6d5e-129">Select the **Dimension** tab.</span></span>
    * <span data-ttu-id="b6d5e-130">Verifique qualquer uma das dimensões do produto estão ativas, e consequentemente deve ter um valor ou um atributo atribuído.</span><span class="sxs-lookup"><span data-stu-id="b6d5e-130">Verify if any of the product dimensions are active,  and therefore must have a value or attribute assigned.</span></span>  
9. <span data-ttu-id="b6d5e-131">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="b6d5e-131">Select **OK**.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]