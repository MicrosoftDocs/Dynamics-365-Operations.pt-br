---
title: Solucionar problemas do configurador de produto
description: Este tópico descreve como corrigir problemas que podem ocorrer durante o trabalho com configurador de produto.
author: SmithaNataraj
manager: tfehr
ms.date: 11/04/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-11-04
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: dacc7205eaf2084f6fbd3be9d8ac0572f9e1bcde
ms.sourcegitcommit: 8eefb4e14ae0ea27769ab2cecca747755560efa3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/13/2020
ms.locfileid: "4516727"
---
# <a name="troubleshoot-the-product-configurator"></a><span data-ttu-id="82504-103">Solucionar problemas do configurador de produto</span><span class="sxs-lookup"><span data-stu-id="82504-103">Troubleshoot the product configurator</span></span>

<span data-ttu-id="82504-104">Este tópico descreve como corrigir problemas que podem ocorrer durante o trabalho com o configurador de produto.</span><span class="sxs-lookup"><span data-stu-id="82504-104">This topic describes how to fix issues that you might encounter while you work with the product configurator.</span></span>

## <a name="item-text-is-overwritten-when-i-configure-a-product-on-a-sales-order-line"></a><span data-ttu-id="82504-105">O texto do item é substituído quando eu configuro um produto em uma linha de ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="82504-105">Item text is overwritten when I configure a product on a sales order line.</span></span>

### <a name="issue-description"></a><span data-ttu-id="82504-106">Descrição do problema</span><span class="sxs-lookup"><span data-stu-id="82504-106">Issue description</span></span>

<span data-ttu-id="82504-107">Esse problema ocorre quando você cria uma linha de ordem de venda para um item configurável e, em seguida, modifica o texto do item.</span><span class="sxs-lookup"><span data-stu-id="82504-107">This issue occurs when you create a sales order line for a configurable item and then modify the item text.</span></span> <span data-ttu-id="82504-108">Ao configurar o item e selecionar **OK**, o texto é substituído pelo texto padrão.</span><span class="sxs-lookup"><span data-stu-id="82504-108">When you configure the item and then select **OK**, the text is overwritten with the standard text.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="82504-109">Resolução do problema</span><span class="sxs-lookup"><span data-stu-id="82504-109">Issue resolution</span></span>

<span data-ttu-id="82504-110">Esse comportamento é esperado.</span><span class="sxs-lookup"><span data-stu-id="82504-110">This behavior is expected.</span></span> <span data-ttu-id="82504-111">O campo de texto inclui o nome da variante, que é preenchido somente após a configuração da linha.</span><span class="sxs-lookup"><span data-stu-id="82504-111">The text field includes the variant name, which is filled in only after you configure the line.</span></span> <span data-ttu-id="82504-112">Portanto, você deve alterar o texto depois de configurar a linha, não antes.</span><span class="sxs-lookup"><span data-stu-id="82504-112">Therefore, you must change the text after you've configured the line, not before.</span></span>

## <a name="integer-attributes-are-incorrectly-rounded-when-product-configuration-models-are-calculated"></a><span data-ttu-id="82504-113">Atributos Inteiro são arredondados incorretamente quando os modelos de configuração do produto são calculados.</span><span class="sxs-lookup"><span data-stu-id="82504-113">Integer attributes are incorrectly rounded when product configuration models are calculated.</span></span>

### <a name="issue-description"></a><span data-ttu-id="82504-114">Descrição do problema</span><span class="sxs-lookup"><span data-stu-id="82504-114">Issue description</span></span>

<span data-ttu-id="82504-115">Esse problema pode ocorrer quando você executa a seguinte série de ações:</span><span class="sxs-lookup"><span data-stu-id="82504-115">This issue can occur when you perform the following series of actions:</span></span>

1. <span data-ttu-id="82504-116">Defina os seguintes atributos em um modelo de configuração de produção:</span><span class="sxs-lookup"><span data-stu-id="82504-116">Set up the following attributes on a production configuration model:</span></span>

    - <span data-ttu-id="82504-117">Entrada (inteiro)</span><span class="sxs-lookup"><span data-stu-id="82504-117">Input (integer)</span></span>
    - <span data-ttu-id="82504-118">Porcentagem (decimal)</span><span class="sxs-lookup"><span data-stu-id="82504-118">Percent (decimal)</span></span>
    - <span data-ttu-id="82504-119">Resultado (inteiro)</span><span class="sxs-lookup"><span data-stu-id="82504-119">Result (integer)</span></span>

2. <span data-ttu-id="82504-120">Crie um cálculo que tenha a seguinte expressão:</span><span class="sxs-lookup"><span data-stu-id="82504-120">Create a calculation that has the following expression:</span></span>

    <span data-ttu-id="82504-121">*Resultado* = *Entrada* × *Porcentagem* ÷ 100</span><span class="sxs-lookup"><span data-stu-id="82504-121">*Result* = *Input* × *Percent* ÷ 100</span></span>

<span data-ttu-id="82504-122">Nesse caso, o resultado inteiro nem sempre é arredondado corretamente.</span><span class="sxs-lookup"><span data-stu-id="82504-122">In this case, the integer result isn't always correctly rounded.</span></span> <span data-ttu-id="82504-123">Por exemplo, a entrada é 1.000 e a porcentagem é 2,40.</span><span class="sxs-lookup"><span data-stu-id="82504-123">For example, the input is 1,000, and the percentage is 2.40.</span></span> <span data-ttu-id="82504-124">Portanto, você espera que o resultado inteiro seja 24, porque 2,40% de 1.000 é 24 (ou 24,00 na forma decimal).</span><span class="sxs-lookup"><span data-stu-id="82504-124">Therefore, you expect the integer result to be 24, because 2.40 percent of 1,000 is 24 (or 24.00 in decimal form).</span></span> <span data-ttu-id="82504-125">Em vez disso, o resultado é mostrado como 23.</span><span class="sxs-lookup"><span data-stu-id="82504-125">Instead, the result is shown as 23.</span></span> <span data-ttu-id="82504-126">Contudo, quando a porcentagem é 2,39, o cálculo é arredondado para 24 em vez de 23.</span><span class="sxs-lookup"><span data-stu-id="82504-126">However, when the percentage is 2.39, the calculation is rounded to 24 instead of 23.</span></span> <span data-ttu-id="82504-127">Quando a porcentagem é 2,50, o cálculo é arredondado para 25, conforme o esperado.</span><span class="sxs-lookup"><span data-stu-id="82504-127">When the percentage is 2.50, the calculation is rounded to 25, as expected.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="82504-128">Resolução do problema</span><span class="sxs-lookup"><span data-stu-id="82504-128">Issue resolution</span></span>

<span data-ttu-id="82504-129">Esse problema se deve à maneira como o Microsoft Solver Foundation representa internamente os números usando frações.</span><span class="sxs-lookup"><span data-stu-id="82504-129">This issue occurs because of the way that Microsoft Solver Foundation internally represents numbers by using fractions.</span></span> <span data-ttu-id="82504-130">No exemplo anterior, o resultado do cálculo em que a porcentagem é 2,40 é representado como 27021597764222975 ÷ 1125899906842624 = 23,99999999999999911182158029987476766109466552734375.</span><span class="sxs-lookup"><span data-stu-id="82504-130">For the preceding example, the result of the calculation where the percentage is 2.40 is represented as 27021597764222975 ÷ 1125899906842624 = 23.99999999999999911182158029987476766109466552734375.</span></span> <span data-ttu-id="82504-131">Quando o .NET converte esse valor como um inteiro, ele retorna 23.</span><span class="sxs-lookup"><span data-stu-id="82504-131">When .NET casts this value as an integer, it will return 23.</span></span>

<span data-ttu-id="82504-132">Esse comportamento não será alterado, pois outros cenários dependem dele.</span><span class="sxs-lookup"><span data-stu-id="82504-132">This behavior won't be changed, because other scenarios depend on it.</span></span> <span data-ttu-id="82504-133">No exemplo anterior, você pode corrigir o problema introduzindo um atributo decimal adicional e um cálculo.</span><span class="sxs-lookup"><span data-stu-id="82504-133">For the preceding example, you can fix the issue by introducing an additional decimal attribute and a calculation.</span></span>

<span data-ttu-id="82504-134">Por exemplo, você pode definir os seguintes atributos em um modelo de configuração de produção:</span><span class="sxs-lookup"><span data-stu-id="82504-134">For example, you can set up the following attributes on a production configuration model:</span></span>

- <span data-ttu-id="82504-135">Entrada (inteiro)</span><span class="sxs-lookup"><span data-stu-id="82504-135">Input (integer)</span></span>
- <span data-ttu-id="82504-136">Porcentagem (decimal)</span><span class="sxs-lookup"><span data-stu-id="82504-136">Percent (decimal)</span></span>
- <span data-ttu-id="82504-137">ResultDecimal (decimal)</span><span class="sxs-lookup"><span data-stu-id="82504-137">ResultDecimal (decimal)</span></span>
- <span data-ttu-id="82504-138">ResultInteger (inteiro)</span><span class="sxs-lookup"><span data-stu-id="82504-138">ResultInteger (integer)</span></span>

<span data-ttu-id="82504-139">Você pode então adicionar os seguintes cálculos:</span><span class="sxs-lookup"><span data-stu-id="82504-139">You can then add the following calculations:</span></span>

- <span data-ttu-id="82504-140">*ResultDecimal* = *Entrada* × *Porcentagem* ÷ 100</span><span class="sxs-lookup"><span data-stu-id="82504-140">*ResultDecimal* = *Input* × *Percent* ÷ 100</span></span>
- <span data-ttu-id="82504-141">*ResultInteger* = *ResultDecimal*</span><span class="sxs-lookup"><span data-stu-id="82504-141">*ResultInteger* = *ResultDecimal*</span></span>
