---
title: Classes de carga parcial (LTL)
description: Este tópico explica o que são classes de carga parcial (LTL) e descreve como configurá-las no Microsoft Dynamics 365 Supply Chain Management.
author: Henrikan
ms.date: 04/05/2021
ms.topic: article
ms.search.form: WHSLTLClass
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-04-05
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: 295006cac0a67cd577809a1b62566de043ea55fb
ms.sourcegitcommit: 636c1bf096a8666a551b67e898da1f48feb9a187
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/26/2021
ms.locfileid: "5941801"
---
# <a name="less-than-truckload-ltl-classes"></a><span data-ttu-id="27b36-103">Classes de carga parcial (LTL)</span><span class="sxs-lookup"><span data-stu-id="27b36-103">Less than truckload (LTL) classes</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="27b36-104">Uma classe de carga parcial (LTL) é uma classe de remessa de frete usada para classificar itens que podem ser enviados.</span><span class="sxs-lookup"><span data-stu-id="27b36-104">A less than truckload (LTL) class is a freight shipping class that is used to classify items that can be shipped.</span></span> <span data-ttu-id="27b36-105">Geralmente, cada tipo de produto ou mercadoria tem um código National Motor Freight Classification (NMFC) que corresponde a um número de classe de frete específico para remessas LTL.</span><span class="sxs-lookup"><span data-stu-id="27b36-105">Generally, every type of product or commodity has a National Motor Freight Classification (NMFC) code that corresponds to a specific freight class number for LTL shipments.</span></span> <span data-ttu-id="27b36-106">As classes de frete LTL representam categorias de itens, enquanto os códigos NMFC estão relacionados a mercadorias específicas em cada uma das 18 classes de frete.</span><span class="sxs-lookup"><span data-stu-id="27b36-106">LTL freight classes represent categories of items, whereas NMFC codes are related to specific commodities in each of the 18 freight classes.</span></span>

<span data-ttu-id="27b36-107">Este recurso permite usar o seu sistema para executar as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="27b36-107">This feature lets you use your system to perform the following tasks:</span></span>

- <span data-ttu-id="27b36-108">Defina as classes de frete LTL usadas na sua empresa.</span><span class="sxs-lookup"><span data-stu-id="27b36-108">Define the LTL freight classes that are used at your company.</span></span>
- <span data-ttu-id="27b36-109">Atribua cada classe LTL a um código NMFC na página **Códigos NMFC**.</span><span class="sxs-lookup"><span data-stu-id="27b36-109">Assign each LTL class to an NMFC code on the **NMFC Codes** page.</span></span> <span data-ttu-id="27b36-110">Para obter mais informações, consulte [Códigos National Motor Freight Classification (NMFC)](nmfc-codes.md).</span><span class="sxs-lookup"><span data-stu-id="27b36-110">For more information, see [National Motor Freight Classification (NMFC) codes](nmfc-codes.md).</span></span>
- <span data-ttu-id="27b36-111">Atribua um código NMFC (e, portanto, o código LTL associado) a cada produto na página **Produtos**.</span><span class="sxs-lookup"><span data-stu-id="27b36-111">Assign an NMFC code (and therefore its associated LTL code) to each product on the **Products** page.</span></span>
- <span data-ttu-id="27b36-112">Avalie com precisão a classe LTL de cada produto ao qual um código NMFC é atribuído.</span><span class="sxs-lookup"><span data-stu-id="27b36-112">Accurately assess the LTL class of each product that an NMFC code is assigned to.</span></span>
- <span data-ttu-id="27b36-113">Determine os requisitos de embalagem para cada classe LTL, verificando os padrões internacionais da LTL.</span><span class="sxs-lookup"><span data-stu-id="27b36-113">Determine packing requirements for each LTL class by checking the international LTL standards.</span></span> <span data-ttu-id="27b36-114">Dessa forma, você garante que os produtos serão bem protegidos e enviados com segurança.</span><span class="sxs-lookup"><span data-stu-id="27b36-114">In this way, you ensure that your products will be well protected and safely shipped.</span></span>
- <span data-ttu-id="27b36-115">Obtenha estimativas de remessa precisas, com base na classe de frete LTL para cada produto.</span><span class="sxs-lookup"><span data-stu-id="27b36-115">Get accurate shipping estimates, based on the LTL freight class for each product.</span></span>

<span data-ttu-id="27b36-116">Este tópico descreve como criar classes LTL no Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="27b36-116">This topic describes how to create LTL classes in Microsoft Dynamics 365 Supply Chain Management.</span></span>

## <a name="create-an-ltl-class"></a><span data-ttu-id="27b36-117">Criar uma classe LTL</span><span class="sxs-lookup"><span data-stu-id="27b36-117">Create an LTL class</span></span>

<span data-ttu-id="27b36-118">Para criar uma classe LTL, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="27b36-118">To create an LTL class, follow these steps.</span></span>

1. <span data-ttu-id="27b36-119">Siga uma destas etapas:</span><span class="sxs-lookup"><span data-stu-id="27b36-119">Follow one of these steps:</span></span>

    - <span data-ttu-id="27b36-120">Acesse **Gerenciamento de depósito \> Configuração \> Estoque \> Classes LTL**.</span><span class="sxs-lookup"><span data-stu-id="27b36-120">Go to **Warehouse management \> Setup \> Inventory \> LTL classes**.</span></span>
    - <span data-ttu-id="27b36-121">Acesse **Gerenciamento de transporte \> Configuração \> Padrões de transporte \> Classes LTL**.</span><span class="sxs-lookup"><span data-stu-id="27b36-121">Go to **Transportation management \> Setup \> Transportation standards \> LTL classes**.</span></span>

2. <span data-ttu-id="27b36-122">No Painel de Ações, selecione **Novo** para criar uma classe LTL.</span><span class="sxs-lookup"><span data-stu-id="27b36-122">On the Action Pane, select **New** to create an LTL class.</span></span> <span data-ttu-id="27b36-123">Defina os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="27b36-123">Then set the following fields:</span></span>

    - <span data-ttu-id="27b36-124">**Classe LTL** – insira o identificador de classe (ID) LTL interno da empresa para o tipo de mercadoria.</span><span class="sxs-lookup"><span data-stu-id="27b36-124">**LTL class** – Enter your company's internal LTL class identifier (ID) for the commodity type.</span></span> <span data-ttu-id="27b36-125">A maioria das empresas usam o padrão internacional.</span><span class="sxs-lookup"><span data-stu-id="27b36-125">Most companies use the international standard.</span></span> <span data-ttu-id="27b36-126">Nesse caso, o valor desse campo corresponderá ao valor do campo **Classe**.</span><span class="sxs-lookup"><span data-stu-id="27b36-126">In that case, the value of this field will match the value of the **Class** field.</span></span> <span data-ttu-id="27b36-127">Mas, se a empresa usar seu próprio padrão, insira um código que cumpra esse padrão.</span><span class="sxs-lookup"><span data-stu-id="27b36-127">However, if your company uses its own standard, enter a code that conforms to that standard.</span></span>
    - <span data-ttu-id="27b36-128">**Nome** – insira um nome descritivo que ajudará você e outros usuários a selecionarem a classe LTL correta para cada código NMFC.</span><span class="sxs-lookup"><span data-stu-id="27b36-128">**Name** – Enter a descriptive name that will help you and other users select the correct LTL class for each NMFC code.</span></span>
    - <span data-ttu-id="27b36-129">**Classe** – insira a ID da classe LTL padrão internacional para o tipo de mercadoria.</span><span class="sxs-lookup"><span data-stu-id="27b36-129">**Class** – Enter the international standard LTL class ID for the commodity type.</span></span> <span data-ttu-id="27b36-130">O código inserido aqui deve estar de acordo com o padrão oficial.</span><span class="sxs-lookup"><span data-stu-id="27b36-130">The code that you enter here must conform to the official standard.</span></span>

## <a name="example-set-up-ltl-classes"></a><span data-ttu-id="27b36-131">Exemplo: Configurar classes LTL</span><span class="sxs-lookup"><span data-stu-id="27b36-131">Example: Set up LTL classes</span></span>

<span data-ttu-id="27b36-132">O exemplo a seguir mostra como configurar duas classes LTL diferentes que podem ser usadas com diferentes tipos de produtos.</span><span class="sxs-lookup"><span data-stu-id="27b36-132">The following example shows how to set up two different LTL classes that you can use with different types of products.</span></span>

1. <span data-ttu-id="27b36-133">Acesse **Gerenciamento de depósito \> Configuração \> Estoque \> Classes LTL**.</span><span class="sxs-lookup"><span data-stu-id="27b36-133">Go to **Warehouse management \> Setup \> Inventory \> LTL classes**.</span></span>
1. <span data-ttu-id="27b36-134">No Painel de Ações, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="27b36-134">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="27b36-135">Na nova linha, defina os valores a seguir:</span><span class="sxs-lookup"><span data-stu-id="27b36-135">On the new line, set the following values:</span></span>

    - <span data-ttu-id="27b36-136">**Classe LTL:** *92,5*</span><span class="sxs-lookup"><span data-stu-id="27b36-136">**LTL class:** *92.5*</span></span>
    - <span data-ttu-id="27b36-137">**Nome:** *Computadores, monitores, refrigeradores*</span><span class="sxs-lookup"><span data-stu-id="27b36-137">**Name:** *Computers, monitors, refrigerators*</span></span>
    - <span data-ttu-id="27b36-138">**Classe:** *92,5*</span><span class="sxs-lookup"><span data-stu-id="27b36-138">**Class:** *92.5*</span></span>

1. <span data-ttu-id="27b36-139">No Painel de ações, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="27b36-139">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="27b36-140">No Painel de Ações, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="27b36-140">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="27b36-141">Na nova linha, defina os valores a seguir:</span><span class="sxs-lookup"><span data-stu-id="27b36-141">On the new line, set the following values:</span></span>

    - <span data-ttu-id="27b36-142">**Classe LTL:** *125*</span><span class="sxs-lookup"><span data-stu-id="27b36-142">**LTL class:** *125*</span></span>
    - <span data-ttu-id="27b36-143">**Nome:** *Pequenos dispositivos domésticos*</span><span class="sxs-lookup"><span data-stu-id="27b36-143">**Name:** *Small household appliances*</span></span>
    - <span data-ttu-id="27b36-144">**Classe:** *125*</span><span class="sxs-lookup"><span data-stu-id="27b36-144">**Class:** *125*</span></span>

1. <span data-ttu-id="27b36-145">No Painel de ações, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="27b36-145">On the Action Pane, select **Save**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="27b36-146">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="27b36-146">Additional resources</span></span>

- [<span data-ttu-id="27b36-147">Códigos National Motor Freight Classification (NMFC)</span><span class="sxs-lookup"><span data-stu-id="27b36-147">National Motor Freight Classification (NMFC) codes</span></span>](nmfc-codes.md)
- [<span data-ttu-id="27b36-148">Criar um conhecimento de embarque</span><span class="sxs-lookup"><span data-stu-id="27b36-148">Create a bill of lading</span></span>](create-bill-of-lading.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
