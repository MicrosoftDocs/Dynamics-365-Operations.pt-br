---
title: Gerenciar unidade de medida
description: Este procedimento mostra como definir uma unidade de medida, fornecer traduções para a unidade e para suas descrições, e definir regras de conversão para unidades relacionadas.
author: sorenva
manager: tfehr
ms.date: 07/08/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductMaintainWorkspace, EcoResProductOpenCasesFormPart, UnitOfMeasure, UnitOfMeasureReportingTranslation, UnitOfMeasureTranslation, UnitOfMeasureConversion, UnitOfMeasureConversionEditOrCreate, UnitOfMeasureLookup, UnitOfMeasureCalculator, UnitOfMeasureWizard, UnitOfMeasureLookupTest
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d8d9b6f18fdc1c47d6a695ca6a2330f6f02fc1bd
ms.sourcegitcommit: cde71bc7d14ea6cdff2c4e991057d39a6a0473d9
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/24/2020
ms.locfileid: "3886983"
---
# <a name="manage-unit-of-measure"></a><span data-ttu-id="d46a4-103">Gerenciar unidade de medida</span><span class="sxs-lookup"><span data-stu-id="d46a4-103">Manage unit of measure</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="d46a4-104">Este procedimento mostra como definir uma unidade de medida, fornecer traduções para a unidade e para suas descrições, e definir regras de conversão para unidades relacionadas.</span><span class="sxs-lookup"><span data-stu-id="d46a4-104">This procedure shows how to define a unit of measure, provide translations for the unit and it's description, and define conversion rules for related units.</span></span> <span data-ttu-id="d46a4-105">Você pode explorar esse procedimento usando os dados demonstrativos, ou usando seus próprios dados.</span><span class="sxs-lookup"><span data-stu-id="d46a4-105">You can walk through this procedure using demo data, or using your own data.</span></span>

1. <span data-ttu-id="d46a4-106">Vá para **Painel de Navegação > Módulos > Gerenciamento de informações do produto > Manutenção de produto liberado**.</span><span class="sxs-lookup"><span data-stu-id="d46a4-106">Go to **Navigation pane > Modules > Product information management > Released product maintenance**.</span></span>
2. <span data-ttu-id="d46a4-107">Clique em **Unidades**.</span><span class="sxs-lookup"><span data-stu-id="d46a4-107">Click **Units**.</span></span>

## <a name="create-a-unit-of-measure"></a><span data-ttu-id="d46a4-108">Criar uma unidade de medida</span><span class="sxs-lookup"><span data-stu-id="d46a4-108">Create a unit of measure</span></span>
1. <span data-ttu-id="d46a4-109">Clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="d46a4-109">Click **New**.</span></span>
2. <span data-ttu-id="d46a4-110">No campo **Unidade**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="d46a4-110">In the **Unit** field, type a value.</span></span> <span data-ttu-id="d46a4-111">Insira o ID ou símbolo a ser usado para se referir à unidade de medida.</span><span class="sxs-lookup"><span data-stu-id="d46a4-111">Enter the ID or symbol to use when referring to the unit of measure.</span></span>  
3. <span data-ttu-id="d46a4-112">No campo **Descrição**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="d46a4-112">In the **Description** field, type a value.</span></span> <span data-ttu-id="d46a4-113">Insira um nome descritivo para a unidade de medida no idioma do sistema.</span><span class="sxs-lookup"><span data-stu-id="d46a4-113">Enter a descriptive name for the unit of measure in the system language.</span></span>  
4. <span data-ttu-id="d46a4-114">No campo **Classe de unidade**, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="d46a4-114">In the **Unit class** field, select an option.</span></span> <span data-ttu-id="d46a4-115">A classe de unidade define a qual agrupamento lógico, como área, massa ou quantidade, a unidade de medida pertence.</span><span class="sxs-lookup"><span data-stu-id="d46a4-115">The unit class defines what logical grouping, such as area, mass, or quantity, the unit of measure is part of.</span></span>  
5. <span data-ttu-id="d46a4-116">No campo **Precisão decimal**, insira um número.</span><span class="sxs-lookup"><span data-stu-id="d46a4-116">In the **Decimal precision** field, enter a number.</span></span> <span data-ttu-id="d46a4-117">Especifique o número de decimais ao qual a unidade de medida convertida deve ser arredondada quando um cálculo é concluído para a unidade de medida.</span><span class="sxs-lookup"><span data-stu-id="d46a4-117">Specify the number of decimals that the converted unit of measure must be rounded to when a calculation is completed for the unit of measure.</span></span>  
6. <span data-ttu-id="d46a4-118">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="d46a4-118">Click **Save**.</span></span>

## <a name="define-unit-translations"></a><span data-ttu-id="d46a4-119">Definir traduções de unidades</span><span class="sxs-lookup"><span data-stu-id="d46a4-119">Define unit translations</span></span>
1. <span data-ttu-id="d46a4-120">No **Painel de Ações**, clique em **Textos de unidade**.</span><span class="sxs-lookup"><span data-stu-id="d46a4-120">On the **Action Pane**, click **Unit texts**.</span></span>
2. <span data-ttu-id="d46a4-121">Clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="d46a4-121">Click **New**.</span></span> <span data-ttu-id="d46a4-122">Use texto de unidade para criar uma tradução de ID ou símbolo que representa a unidade de medida para o uso em documentos externos nos idiomas específicos do cliente ou fornecedor.</span><span class="sxs-lookup"><span data-stu-id="d46a4-122">Use unit text to create a translation of the ID or a symbol representing the unit of measure for use on external documents in customer- or vendor-specific languages.</span></span>  
3. <span data-ttu-id="d46a4-123">No campo **Idioma**, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="d46a4-123">In the **Language** field, enter or select a value.</span></span>
4. <span data-ttu-id="d46a4-124">No campo **Texto**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="d46a4-124">In the **Text** field, type a value.</span></span>
5. <span data-ttu-id="d46a4-125">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="d46a4-125">Click **Save**.</span></span>
6. <span data-ttu-id="d46a4-126">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="d46a4-126">Close the page.</span></span>
7. <span data-ttu-id="d46a4-127">No **Painel de Ações**, clique em **Descrição da unidade traduzida**.</span><span class="sxs-lookup"><span data-stu-id="d46a4-127">On the **Action Pane**, click **Translated unit descriptions**.</span></span>
8. <span data-ttu-id="d46a4-128">Clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="d46a4-128">Click **New**.</span></span> <span data-ttu-id="d46a4-129">Defina descrições específicas para um idioma para a unidade de medida.</span><span class="sxs-lookup"><span data-stu-id="d46a4-129">Define language-specific descriptions for the unit of measure.</span></span>  
9. <span data-ttu-id="d46a4-130">No campo **Idioma**, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="d46a4-130">In the **Language** field, enter or select a value.</span></span>
10. <span data-ttu-id="d46a4-131">No campo **Descrição**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="d46a4-131">In the **Description** field, type a value.</span></span>
11. <span data-ttu-id="d46a4-132">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="d46a4-132">Click **Save**.</span></span>
12. <span data-ttu-id="d46a4-133">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="d46a4-133">Close the page.</span></span>

## <a name="define-unit-conversion-rules"></a><span data-ttu-id="d46a4-134">Definir regras de conversão de unidades</span><span class="sxs-lookup"><span data-stu-id="d46a4-134">Define unit conversion rules</span></span>
1. <span data-ttu-id="d46a4-135">No **Painel de Ações**, clique em **Conversões de unidade**.</span><span class="sxs-lookup"><span data-stu-id="d46a4-135">On the **Action Pane**, click **Unit conversions**.</span></span> <span data-ttu-id="d46a4-136">Defina regras de conversão da unidade de medida de e para outras unidades de medida da classe de unidades selecionada.</span><span class="sxs-lookup"><span data-stu-id="d46a4-136">Define rules for converting the unit of measure to and from other units of measure in the selected unit class.</span></span>  
2. <span data-ttu-id="d46a4-137">Clique em **Novo** para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="d46a4-137">Click **New** to open the drop dialog.</span></span>
3. <span data-ttu-id="d46a4-138">No campo **Fator**, insira um número.</span><span class="sxs-lookup"><span data-stu-id="d46a4-138">In the **Factor** field, enter a number.</span></span> <span data-ttu-id="d46a4-139">Fator de conversão entre De unidade e Para unidade.</span><span class="sxs-lookup"><span data-stu-id="d46a4-139">Conversion factor between the From unit and the To unit.</span></span> <span data-ttu-id="d46a4-140">Por exemplo, o fator de conversão de centímetro para metro é 100 porque existem 100 centímetros em um metro.</span><span class="sxs-lookup"><span data-stu-id="d46a4-140">For example, the conversion factor from centimeter to meter is 100 because there are 100 centimeters in one meter.</span></span>  
4. <span data-ttu-id="d46a4-141">No campo **Para unidade**, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="d46a4-141">In the **To unit** field, enter or select a value.</span></span>
5. <span data-ttu-id="d46a4-142">No campo **Arredondamento**, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="d46a4-142">In the **Rounding** field, select an option.</span></span> <span data-ttu-id="d46a4-143">Definir como o valor convertido deve ser arredondado.</span><span class="sxs-lookup"><span data-stu-id="d46a4-143">Define how the converted value should be rounded.</span></span>  
6. <span data-ttu-id="d46a4-144">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="d46a4-144">Click **OK**.</span></span>
7. <span data-ttu-id="d46a4-145">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="d46a4-145">Close the page.</span></span>

