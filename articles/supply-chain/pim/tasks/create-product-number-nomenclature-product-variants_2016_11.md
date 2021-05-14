---
title: Criar uma nomenclatura de produtos de grades de produto configuradas
description: Este procedimento mostra como configurar uma nomenclatura de número de produto para grades de produtos configurados e como ela pode ser anexada a um produto mestre configurável.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, EcoResNomenclature, EcoResProductListPage, EcoResProductDetails, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7ea30dc107213b1a2c6b2a109188066a6ea82159
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/20/2021
ms.locfileid: "5921002"
---
# <a name="create-a-product-number-nomenclature-for-configured-product-variants"></a><span data-ttu-id="28954-103">Criar uma nomenclatura de produtos de grades de produto configuradas</span><span class="sxs-lookup"><span data-stu-id="28954-103">Create a product number nomenclature for configured product variants</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="28954-104">Este procedimento mostra como configurar uma nomenclatura de número de produto para grades de produtos configurados e como ela pode ser anexada a um produto mestre configurável.</span><span class="sxs-lookup"><span data-stu-id="28954-104">This procedure shows you how to set up a product number nomenclature for configured product variants, and how it can be attached to a configurable product master.</span></span> <span data-ttu-id="28954-105">O procedimento também demonstra como você pode criar uma nomenclatura de configuração para um componente de modelo de configuração de produto.</span><span class="sxs-lookup"><span data-stu-id="28954-105">This procedure also demonstrates how you can build a configuration nomenclature for a product configuration model component.</span></span> <span data-ttu-id="28954-106">A empresa de dados demo usada para criar este procedimento é USMF.</span><span class="sxs-lookup"><span data-stu-id="28954-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="28954-107">A nova nomenclatura de número de produto é atribuída ao produto mestre D0004.</span><span class="sxs-lookup"><span data-stu-id="28954-107">The new product number nomenclature is assigned to the D0004 product master.</span></span> <span data-ttu-id="28954-108">A tarefa geralmente seria realizada por um designer de produto.</span><span class="sxs-lookup"><span data-stu-id="28954-108">This task would typically be done by a product designer.</span></span>

## <a name="create-a-product-number-nomenclature"></a><span data-ttu-id="28954-109">Criar uma nomenclatura de número de produto</span><span class="sxs-lookup"><span data-stu-id="28954-109">Create a product number nomenclature</span></span>

1. <span data-ttu-id="28954-110">Vá para **Gerenciamento de informações sobre produtos \> Configuração \> Nomenclatura de produto**.</span><span class="sxs-lookup"><span data-stu-id="28954-110">Go to **Product information management \> Setup \> Product nomenclature**.</span></span>
1. <span data-ttu-id="28954-111">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="28954-111">Select **New**.</span></span>
1. <span data-ttu-id="28954-112">No campo **Nome**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="28954-112">In the **Name** field, type a value.</span></span>
1. <span data-ttu-id="28954-113">No campo **Descrição**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="28954-113">In the **Description** field, type a value.</span></span>
1. <span data-ttu-id="28954-114">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="28954-114">Select **Add**.</span></span>
1. <span data-ttu-id="28954-115">Selecione **Número do produto mestre**.</span><span class="sxs-lookup"><span data-stu-id="28954-115">Select **Product master number**.</span></span>
1. <span data-ttu-id="28954-116">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="28954-116">Select **Add**.</span></span>
1. <span data-ttu-id="28954-117">Selecione **Constante de texto**.</span><span class="sxs-lookup"><span data-stu-id="28954-117">Select **Text constant**.</span></span>
1. <span data-ttu-id="28954-118">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="28954-118">In the list, mark the selected row.</span></span>
1. <span data-ttu-id="28954-119">No campo **Texto**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="28954-119">In the **Text** field, type a value.</span></span>
1. <span data-ttu-id="28954-120">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="28954-120">Select **Add**.</span></span>
1. <span data-ttu-id="28954-121">Selecione **Configuração**.</span><span class="sxs-lookup"><span data-stu-id="28954-121">Select **Configuration**.</span></span>
1. <span data-ttu-id="28954-122">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="28954-122">Close the page.</span></span>

## <a name="assign-the-product-number-nomenclature-to-a-product-master"></a><span data-ttu-id="28954-123">Atribuir a nomenclatura de número de produto a um produto mestre</span><span class="sxs-lookup"><span data-stu-id="28954-123">Assign the product number nomenclature to a product master</span></span>

1. <span data-ttu-id="28954-124">Vá para **Gerenciamento de informações sobre produtos \> Produtos \> Produtos mestre**.</span><span class="sxs-lookup"><span data-stu-id="28954-124">Go to **Product information management \> Products \> Product masters**.</span></span>
1. <span data-ttu-id="28954-125">Use o Filtro Rápido para localizar registros.</span><span class="sxs-lookup"><span data-stu-id="28954-125">Use the Quick Filter to find records.</span></span> <span data-ttu-id="28954-126">Por exemplo, filtre no campo **Número do produto** com um valor de 'D'.</span><span class="sxs-lookup"><span data-stu-id="28954-126">For example, filter on the **Product number** field with a value of 'D'.</span></span>
1. <span data-ttu-id="28954-127">Na lista, selecione o link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="28954-127">In the list, select the link in the selected row.</span></span>
1. <span data-ttu-id="28954-128">Selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="28954-128">Select **Edit**.</span></span>
1. <span data-ttu-id="28954-129">Selecione *Sim* no campo **Usar nomenclatura**.</span><span class="sxs-lookup"><span data-stu-id="28954-129">Select *Yes* in the **Use nomenclature** field.</span></span>
1. <span data-ttu-id="28954-130">No campo **Nomenclatura de número de grade de produto**, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="28954-130">In the **Product variant number nomenclature** field, enter or select a value.</span></span>
1. <span data-ttu-id="28954-131">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="28954-131">Close the page.</span></span>
1. <span data-ttu-id="28954-132">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="28954-132">Close the page.</span></span>

## <a name="create-nomenclature-for-a-product-configuration-model-component"></a><span data-ttu-id="28954-133">Criar nomenclatura para um componente de modelo de configuração de produto</span><span class="sxs-lookup"><span data-stu-id="28954-133">Create nomenclature for a product configuration model component</span></span>

1. <span data-ttu-id="28954-134">Vá para **Gerenciamento de informações do produto \> Produtos \> Modelos de configuração do produto**.</span><span class="sxs-lookup"><span data-stu-id="28954-134">Go to **Product information management \> Products \> Product configuration models**.</span></span>
1. <span data-ttu-id="28954-135">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="28954-135">In the list, find and select the desired record.</span></span>
1. <span data-ttu-id="28954-136">Na lista, selecione o link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="28954-136">In the list, select the link in the selected row.</span></span>
1. <span data-ttu-id="28954-137">Selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="28954-137">Select **Edit**.</span></span>
1. <span data-ttu-id="28954-138">Selecione *Sim* no campo **Usar nomenclatura de configuração**.</span><span class="sxs-lookup"><span data-stu-id="28954-138">Select *Yes* in the **Use configuration nomenclature** field.</span></span>
1. <span data-ttu-id="28954-139">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="28954-139">Select **Add**.</span></span>
1. <span data-ttu-id="28954-140">Selecione **Valor do atributo**.</span><span class="sxs-lookup"><span data-stu-id="28954-140">Select **Attribute value**.</span></span>
1. <span data-ttu-id="28954-141">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="28954-141">In the list, mark the selected row.</span></span>
1. <span data-ttu-id="28954-142">No campo **Atributo**, informe ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="28954-142">In the **Attribute** field, enter or select a value.</span></span>
1. <span data-ttu-id="28954-143">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="28954-143">Select **Add**.</span></span>
1. <span data-ttu-id="28954-144">Selecione **Constante de texto**.</span><span class="sxs-lookup"><span data-stu-id="28954-144">Select **Text constant**.</span></span>
1. <span data-ttu-id="28954-145">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="28954-145">In the list, mark the selected row.</span></span>
1. <span data-ttu-id="28954-146">No campo **Texto**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="28954-146">In the **Text** field, type a value.</span></span>
1. <span data-ttu-id="28954-147">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="28954-147">Select **Add**.</span></span>
1. <span data-ttu-id="28954-148">Selecione **Valor do atributo**.</span><span class="sxs-lookup"><span data-stu-id="28954-148">Select **Attribute value**.</span></span>
1. <span data-ttu-id="28954-149">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="28954-149">In the list, mark the selected row.</span></span>
1. <span data-ttu-id="28954-150">No campo **Atributo**, informe ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="28954-150">In the **Attribute** field, enter or select a value.</span></span>
1. <span data-ttu-id="28954-151">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="28954-151">Select **Add**.</span></span>
1. <span data-ttu-id="28954-152">Selecione **Constante de texto**.</span><span class="sxs-lookup"><span data-stu-id="28954-152">Select **Text constant**.</span></span>
1. <span data-ttu-id="28954-153">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="28954-153">In the list, mark the selected row.</span></span>
1. <span data-ttu-id="28954-154">No campo **Texto**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="28954-154">In the **Text** field, type a value.</span></span>
1. <span data-ttu-id="28954-155">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="28954-155">Select **Add**.</span></span>
1. <span data-ttu-id="28954-156">Selecione **Valor do atributo**.</span><span class="sxs-lookup"><span data-stu-id="28954-156">Select **Attribute value**.</span></span>
1. <span data-ttu-id="28954-157">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="28954-157">In the list, mark the selected row.</span></span>
1. <span data-ttu-id="28954-158">No campo **Atributo**, informe ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="28954-158">In the **Attribute** field, enter or select a value.</span></span>
1. <span data-ttu-id="28954-159">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="28954-159">Select **Add**.</span></span>
1. <span data-ttu-id="28954-160">Selecione **Constante de texto**.</span><span class="sxs-lookup"><span data-stu-id="28954-160">Select **Text constant**.</span></span>
1. <span data-ttu-id="28954-161">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="28954-161">In the list, mark the selected row.</span></span>
1. <span data-ttu-id="28954-162">No campo **Texto**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="28954-162">In the **Text** field, type a value.</span></span>
1. <span data-ttu-id="28954-163">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="28954-163">Select **Add**.</span></span>
1. <span data-ttu-id="28954-164">Selecione **Valor do atributo**.</span><span class="sxs-lookup"><span data-stu-id="28954-164">Select **Attribute value**.</span></span>
1. <span data-ttu-id="28954-165">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="28954-165">In the list, mark the selected row.</span></span>
1. <span data-ttu-id="28954-166">No campo **Atributo**, informe ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="28954-166">In the **Attribute** field, enter or select a value.</span></span>
1. <span data-ttu-id="28954-167">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="28954-167">Select **Add**.</span></span>
1. <span data-ttu-id="28954-168">Selecione **Constante de texto**.</span><span class="sxs-lookup"><span data-stu-id="28954-168">Select **Text constant**.</span></span>
1. <span data-ttu-id="28954-169">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="28954-169">In the list, mark the selected row.</span></span>
1. <span data-ttu-id="28954-170">No campo **Texto**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="28954-170">In the **Text** field, type a value.</span></span>
1. <span data-ttu-id="28954-171">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="28954-171">Select **Add**.</span></span>
1. <span data-ttu-id="28954-172">Selecione **Valor de sequência numérica**.</span><span class="sxs-lookup"><span data-stu-id="28954-172">Select **Number sequence value**.</span></span>
1. <span data-ttu-id="28954-173">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="28954-173">In the list, mark the selected row.</span></span>
1. <span data-ttu-id="28954-174">No campo **Sequência numérica**, informe ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="28954-174">In the **Number sequence** field, enter or select a value.</span></span>
1. <span data-ttu-id="28954-175">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="28954-175">Close the page.</span></span>
1. <span data-ttu-id="28954-176">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="28954-176">Close the page.</span></span>
1. <span data-ttu-id="28954-177">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="28954-177">Close the page.</span></span>

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]