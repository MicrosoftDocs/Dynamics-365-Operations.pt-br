---
title: Códigos National Motor Freight Classification (NMFC)
description: Este tópico descreve como trabalhar com códigos National Motor Freight Classification (NMFC) no Microsoft Dynamics 365 Supply Chain Management
author: Henrikan
ms.date: 04/22/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-04-22
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: 0307437d3868f7ac34fa16a0913907a046ac14d4
ms.sourcegitcommit: 636c1bf096a8666a551b67e898da1f48feb9a187
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/26/2021
ms.locfileid: "5941873"
---
# <a name="national-motor-freight-classification-nmfc-codes"></a><span data-ttu-id="c0bb7-103">Códigos National Motor Freight Classification (NMFC)</span><span class="sxs-lookup"><span data-stu-id="c0bb7-103">National Motor Freight Classification (NMFC) codes</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c0bb7-104">Os códigos National Motor Freight Classification (NMFC) ajudam você a classificar itens que podem ser enviados.</span><span class="sxs-lookup"><span data-stu-id="c0bb7-104">National Motor Freight Classification (NMFC) codes help you classify items that can be shipped.</span></span> <span data-ttu-id="c0bb7-105">O código NMFC é uma designação usada para agrupar mercadorias.</span><span class="sxs-lookup"><span data-stu-id="c0bb7-105">The NMFC code is a designation that is used to group commodities.</span></span> <span data-ttu-id="c0bb7-106">Ele permite que empresas de transporte avaliem mercadorias para remessa por meio da classificação de itens com base em considerações como ajuste de caminhão, problemas de carregamento, problemas de manipulação e perecibilidade.</span><span class="sxs-lookup"><span data-stu-id="c0bb7-106">It enables transport companies to evaluate goods for shipment by classifying items based on considerations such as truck fit, loading issues, handling issues, and perishability.</span></span> <span data-ttu-id="c0bb7-107">As mercadorias são agrupadas em uma de 18 classes de frete usando um intervalo de números de 50 a 500.</span><span class="sxs-lookup"><span data-stu-id="c0bb7-107">Commodities are grouped into one of 18 freight classes by using a range of numbers from 50 to 500.</span></span> <span data-ttu-id="c0bb7-108">A classe na qual uma mercadoria é agrupada se baseia em uma avaliação de quatro características de transporte: densidade, capacidade de armazenamento, manuseio e responsabilidade.</span><span class="sxs-lookup"><span data-stu-id="c0bb7-108">The class that a commodity is grouped into is based on an evaluation of four transportation characteristics: density, stowability, handling, and liability.</span></span> <span data-ttu-id="c0bb7-109">Juntas, essas características estabelecem a transportabilidade da mercadoria.</span><span class="sxs-lookup"><span data-stu-id="c0bb7-109">Together, these characteristics establish the commodity's transportability.</span></span>

<span data-ttu-id="c0bb7-110">Um código NMFC está associado a cada item de remessa de carga parcial (LTL).</span><span class="sxs-lookup"><span data-stu-id="c0bb7-110">An NMFC code is associated with every less than truckload (LTL) shipping item.</span></span> <span data-ttu-id="c0bb7-111">Por exemplo, um laptop pode receber um NMFC classificado como 2,5, enquanto os cabos elétricos podem receber um NMFC classificado como 65.</span><span class="sxs-lookup"><span data-stu-id="c0bb7-111">For example, a laptop might be assigned an NMFC that is classed at 2.5, whereas electrical cords might be assigned an NMFC that is classed at 65.</span></span>

<span data-ttu-id="c0bb7-112">Esse recurso pode ajudar os trabalhadores a usar códigos NMFC para classificar itens de remessa LTL.</span><span class="sxs-lookup"><span data-stu-id="c0bb7-112">This feature can help workers use NMFC codes to classify LTL shipping items.</span></span> <span data-ttu-id="c0bb7-113">Veja alguns exemplos:</span><span class="sxs-lookup"><span data-stu-id="c0bb7-113">Here are some examples:</span></span>

- <span data-ttu-id="c0bb7-114">Se a sua empresa incluir uma descrição de frete no conhecimento de embarque (BOL), a operadora terá uma ideia do que é o frete.</span><span class="sxs-lookup"><span data-stu-id="c0bb7-114">If your company includes a freight description on the bill of lading (BOL), the carrier will have some idea what the freight is.</span></span> <span data-ttu-id="c0bb7-115">O frete é uma classificação importante, pois muitas empresas de transporte baseiam todo o modelo comercial nos tipos de frete enviados.</span><span class="sxs-lookup"><span data-stu-id="c0bb7-115">Freight is an important classification because many transportation companies base their whole business model on the types of freight that they ship.</span></span>
- <span data-ttu-id="c0bb7-116">Essa classificação pode ser essencial para a sua empresa, pois ela é usada para determinar o custo de determinada carga.</span><span class="sxs-lookup"><span data-stu-id="c0bb7-116">This classification might be essential to your company because it's used to determine the cost of a given load.</span></span>
- <span data-ttu-id="c0bb7-117">Sua empresa pode identificar a lucratividade de uma empresa de transporte e logística LTL.</span><span class="sxs-lookup"><span data-stu-id="c0bb7-117">Your company can identify the profitability of an LTL logistics and transportation company.</span></span>

<span data-ttu-id="c0bb7-118">Este tópico descreve como trabalhar com códigos NMFC no Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="c0bb7-118">This topic describes how to work with NMFC codes in Microsoft Dynamics 365 Supply Chain Management.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c0bb7-119">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="c0bb7-119">Prerequisites</span></span>

<span data-ttu-id="c0bb7-120">Para poder criar códigos NMFC, você deve configurar todas as classes de frete LTL a serem mapeadas para eles.</span><span class="sxs-lookup"><span data-stu-id="c0bb7-120">Before you can create NMFC codes, you must set up all the LTL freight classes that must be mapped to them.</span></span> <span data-ttu-id="c0bb7-121">As classes de frete LTL representam categorias de itens, enquanto os códigos NMFC estão relacionados a mercadorias específicas em cada uma das 18 classes de frete.</span><span class="sxs-lookup"><span data-stu-id="c0bb7-121">LTL freight classes represent categories of items, whereas NMFC codes are related to specific commodities in each of the 18 freight classes.</span></span> <span data-ttu-id="c0bb7-122">Para obter mais informações sobre como trabalhar com classes LTL, consulte [Classes de carga parcial (LTL)](ltl-class.md).</span><span class="sxs-lookup"><span data-stu-id="c0bb7-122">For more information about how to work with LTL classes, see [Less than truckload (LTL) classes](ltl-class.md).</span></span>

## <a name="create-an-nmfc-code"></a><span data-ttu-id="c0bb7-123">Criar um código NMFC</span><span class="sxs-lookup"><span data-stu-id="c0bb7-123">Create an NMFC code</span></span>

<span data-ttu-id="c0bb7-124">Para criar um código NMFC, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="c0bb7-124">To create an NMFC code, follow these steps.</span></span>

1. <span data-ttu-id="c0bb7-125">Siga uma destas etapas:</span><span class="sxs-lookup"><span data-stu-id="c0bb7-125">Follow one of these steps:</span></span>

    - <span data-ttu-id="c0bb7-126">Acesse **Gerenciamento de depósito \> Configuração \> Estoque \> Códigos NMFC**.</span><span class="sxs-lookup"><span data-stu-id="c0bb7-126">Go to **Warehouse management \> Setup \> Inventory \> NMFC codes**.</span></span>
    - <span data-ttu-id="c0bb7-127">Acesse **Gerenciamento de transporte \> Configuração \> Padrões de transporte \> Códigos NMFC**.</span><span class="sxs-lookup"><span data-stu-id="c0bb7-127">Go to **Transportation management \> Setup \> Transportation standards \> NMFC codes**.</span></span>

1. <span data-ttu-id="c0bb7-128">Selecione **Novo** para criar um código NMFC.</span><span class="sxs-lookup"><span data-stu-id="c0bb7-128">Select **New** to create an NMFC code.</span></span> <span data-ttu-id="c0bb7-129">Defina os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="c0bb7-129">Then set the following fields:</span></span>

    - <span data-ttu-id="c0bb7-130">**Código NMFC** – insira o código NMFC para o tipo de mercadoria.</span><span class="sxs-lookup"><span data-stu-id="c0bb7-130">**NMFC code** – Enter the NMFC code for the commodity type.</span></span>
    - <span data-ttu-id="c0bb7-131">**Nome** – insira um nome para o código NMFC.</span><span class="sxs-lookup"><span data-stu-id="c0bb7-131">**Name** – Enter a name for the NMFC code.</span></span>
    - <span data-ttu-id="c0bb7-132">**Classe LTL** – selecione a classe LTL associada ao código NMFC.</span><span class="sxs-lookup"><span data-stu-id="c0bb7-132">**LTL class** – Select the LTL class that is associated with the NMFC code.</span></span>
    - <span data-ttu-id="c0bb7-133">**Unidade de manuseio de material BOL** – defina o tipo de manuseio padrão para a remessa.</span><span class="sxs-lookup"><span data-stu-id="c0bb7-133">**BOL handling unit** – Define the default handling type for the shipment.</span></span>

## <a name="example-set-up-nmfc-codes"></a><span data-ttu-id="c0bb7-134">Exemplo: Configurar códigos NMFC</span><span class="sxs-lookup"><span data-stu-id="c0bb7-134">Example: Set up NMFC codes</span></span>

<span data-ttu-id="c0bb7-135">O exemplo a seguir mostra como configurar dois códigos NMFC diferentes que podem ser usados com diferentes produtos.</span><span class="sxs-lookup"><span data-stu-id="c0bb7-135">The following example shows how to set up two different NMFC codes that can be used with different products.</span></span>

1. <span data-ttu-id="c0bb7-136">Acesse **Gerenciamento de depósito \> Configuração \> Estoque \> Códigos NMFC**.</span><span class="sxs-lookup"><span data-stu-id="c0bb7-136">Go to **Warehouse management \> Setup \> Inventory \> NMFC codes**.</span></span>
1. <span data-ttu-id="c0bb7-137">No Painel de Ações, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="c0bb7-137">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="c0bb7-138">Na nova linha, defina os valores a seguir:</span><span class="sxs-lookup"><span data-stu-id="c0bb7-138">On the new line, set the following values:</span></span>

    - <span data-ttu-id="c0bb7-139">**Código NMFC:** *92,5*</span><span class="sxs-lookup"><span data-stu-id="c0bb7-139">**NMFC code:** *92.5*</span></span>
    - <span data-ttu-id="c0bb7-140">**Nome:** *Computadores*</span><span class="sxs-lookup"><span data-stu-id="c0bb7-140">**Name:** *Computers*</span></span>
    - <span data-ttu-id="c0bb7-141">**Classe LTL:** *92,5*</span><span class="sxs-lookup"><span data-stu-id="c0bb7-141">**LTL class:** *92.5*</span></span>
    - <span data-ttu-id="c0bb7-142">**Unidade de manuseio de material BOL:** *Unidade*</span><span class="sxs-lookup"><span data-stu-id="c0bb7-142">**BOL handling unit:** *Unit*</span></span>

1. <span data-ttu-id="c0bb7-143">No Painel de ações, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="c0bb7-143">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="c0bb7-144">No Painel de Ações, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="c0bb7-144">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="c0bb7-145">Na nova linha, defina os valores a seguir:</span><span class="sxs-lookup"><span data-stu-id="c0bb7-145">On the new line, set the following values:</span></span>

    - <span data-ttu-id="c0bb7-146">**Código NMFC:** *125*</span><span class="sxs-lookup"><span data-stu-id="c0bb7-146">**NMFC code:** *125*</span></span>
    - <span data-ttu-id="c0bb7-147">**Nome:** *Telefones*</span><span class="sxs-lookup"><span data-stu-id="c0bb7-147">**Name:** *Phones*</span></span>
    - <span data-ttu-id="c0bb7-148">**Classe LTL:** *125*</span><span class="sxs-lookup"><span data-stu-id="c0bb7-148">**LTL class:** *125*</span></span>
    - <span data-ttu-id="c0bb7-149">**Unidade de manuseio de material BOL:** *Unidade*</span><span class="sxs-lookup"><span data-stu-id="c0bb7-149">**BOL handling unit:** *Unit*</span></span>

1. <span data-ttu-id="c0bb7-150">No Painel de ações, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="c0bb7-150">On the Action Pane, select **Save**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c0bb7-151">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="c0bb7-151">Additional resources</span></span>

- [<span data-ttu-id="c0bb7-152">Classes de carga parcial (LTL)</span><span class="sxs-lookup"><span data-stu-id="c0bb7-152">Less than truckload (LTL) classes</span></span>](ltl-class.md)
- [<span data-ttu-id="c0bb7-153">Criar um conhecimento de embarque</span><span class="sxs-lookup"><span data-stu-id="c0bb7-153">Create a bill of landing</span></span>](create-bill-of-lading.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
