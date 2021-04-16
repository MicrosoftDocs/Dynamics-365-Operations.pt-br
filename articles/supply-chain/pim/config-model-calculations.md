---
title: Cálculo de modelo de configuração de produto
description: Este tópico descreve como criar cálculos para atributos em um modelo de configuração de produto
author: t-benebo
ms.date: 03/18/2021
ms.topic: article
ms.search.form: PCProductConfigurationModelListPage, PCProductConfigurationModelDetails
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-03-18
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: eaf6264f060d33575740ad38e7a65158baba296b
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5829609"
---
# <a name="product-configuration-model-calculations"></a><span data-ttu-id="02194-103">Cálculo de modelo de configuração de produto</span><span class="sxs-lookup"><span data-stu-id="02194-103">Product configuration model calculations</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="02194-104">Este tópico descreve como criar cálculos para atributos em um modelo de configuração de produto.</span><span class="sxs-lookup"><span data-stu-id="02194-104">This topic describes how to create calculations for attributes in a product configuration model.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="02194-105">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="02194-105">Prerequisites</span></span>

<span data-ttu-id="02194-106">Os cálculos são usados em um modelo de configuração de produto para calcular os valores da configuração de um produto.</span><span class="sxs-lookup"><span data-stu-id="02194-106">Calculations are used in a product configuration model to calculate the configuration values for a product.</span></span> <span data-ttu-id="02194-107">Antes de começar a configurar cálculos, o modelo de configuração de produto relacionado deve existir.</span><span class="sxs-lookup"><span data-stu-id="02194-107">Before you can start to set up calculations, the related product configuration model must exist.</span></span> <span data-ttu-id="02194-108">Para obter uma visão geral do processo de configuração dos modelos de configuração e das tarefas relacionadas, consulte [Configurar um modelo de configuração de produto](set-up-maintain-product-configuration-model.md).</span><span class="sxs-lookup"><span data-stu-id="02194-108">For an overview of the setup process for configuration models and the related tasks, see [Set up a product configuration model](set-up-maintain-product-configuration-model.md).</span></span>

## <a name="create-a-calculation"></a><span data-ttu-id="02194-109">Criar um cálculo</span><span class="sxs-lookup"><span data-stu-id="02194-109">Create a calculation</span></span>

<span data-ttu-id="02194-110">Um cálculo consiste em uma expressão e em um atributo de destino.</span><span class="sxs-lookup"><span data-stu-id="02194-110">A calculation consists of an expression and a target attribute.</span></span> <span data-ttu-id="02194-111">Para obter mais informações, consulte [Perguntas frequentes sobre cálculos para modelos de configuração de produto](calculate-product-configuration-models.md).</span><span class="sxs-lookup"><span data-stu-id="02194-111">For more information, see [Calculations for product configuration models FAQ](calculate-product-configuration-models.md).</span></span>

<span data-ttu-id="02194-112">Para criar um cálculo para um modelo de produto existente, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="02194-112">To create a calculation for an existing product model, follow these steps.</span></span>

1. <span data-ttu-id="02194-113">Vá para **Gerenciamento de informações sobre produtos \> Comum \> Modelos de configuração do produto**.</span><span class="sxs-lookup"><span data-stu-id="02194-113">Go to **Product information management \> Common \> Product configuration models**.</span></span>
1. <span data-ttu-id="02194-114">Abra um modelo de configuração de produto e selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="02194-114">Open a product configuration model, and then select **Edit**.</span></span>
1. <span data-ttu-id="02194-115">Na guia rápida **Cálculos**, selecione **Adicionar** para adicionar um cálculo e defina os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="02194-115">On the **Calculations** FastTab, select **Add** to add a calculation, and then set the following fields:</span></span>

    - <span data-ttu-id="02194-116">**Nome** – insira um nome para o cálculo.</span><span class="sxs-lookup"><span data-stu-id="02194-116">**Name** – Enter a name for the calculation.</span></span>
    - <span data-ttu-id="02194-117">**Descrição** – insira uma descrição do cálculo.</span><span class="sxs-lookup"><span data-stu-id="02194-117">**Description** – Enter a description of the calculation.</span></span>
    - <span data-ttu-id="02194-118">**Atributo de destino** – selecione o atributo para o qual você está fazendo o cálculo.</span><span class="sxs-lookup"><span data-stu-id="02194-118">**Target attribute** – Select the attribute that you're making the calculation for.</span></span>

1. <span data-ttu-id="02194-119">Selecione **Editar expressão**.</span><span class="sxs-lookup"><span data-stu-id="02194-119">Select **Edit expression**.</span></span>
1. <span data-ttu-id="02194-120">Na caixa de diálogo **Inserir um cálculo**, adicione os atributos, operadores e valores necessários à expressão.</span><span class="sxs-lookup"><span data-stu-id="02194-120">In the **Enter a calculation** dialog box, add the required attributes, operators, and values to the expression.</span></span> <span data-ttu-id="02194-121">Para obter mais informações sobre como trabalhar com esses elementos, consulte [Restrições de expressão e restrições de tabela nos modelos de configuração do produto](expression-constraints-table-constraints-product-configuration-models.md).</span><span class="sxs-lookup"><span data-stu-id="02194-121">For more information about how to work with these elements, see [Expression constraints and table constraints in product configuration models](expression-constraints-table-constraints-product-configuration-models.md).</span></span>
1. <span data-ttu-id="02194-122">Quando a expressão estiver pronta, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="02194-122">When your expression is ready, select **OK**.</span></span>

## <a name="calculation-examples"></a><span data-ttu-id="02194-123">Exemplos de cálculo</span><span class="sxs-lookup"><span data-stu-id="02194-123">Calculation examples</span></span>

<span data-ttu-id="02194-124">Esta seção fornece alguns exemplos que mostram como os cálculos funcionam.</span><span class="sxs-lookup"><span data-stu-id="02194-124">This section provides a few examples that show how calculations work.</span></span>

### <a name="example-1"></a><span data-ttu-id="02194-125">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="02194-125">Example 1</span></span>

<span data-ttu-id="02194-126">O atributo de destino é booliano e o cálculo usa a seguinte expressão condicional:</span><span class="sxs-lookup"><span data-stu-id="02194-126">The target attribute is Boolean, and the calculation uses the following conditional expression:</span></span>

`If[(decimalAttribute1 / decimalAttribute2) < 1, True, False]`

<span data-ttu-id="02194-127">This eEssa expressão retornará um valor *Verdadeiro* para o atributo de destino se `decimalAttribute2` for maior ou igual a `decimalAttribute1`.</span><span class="sxs-lookup"><span data-stu-id="02194-127">This expression returns a value of *True* to the target attribute if `decimalAttribute2` is greater than or equal to `decimalAttribute1`.</span></span> <span data-ttu-id="02194-128">Caso contrário, ela retorna um valor *Falso*.</span><span class="sxs-lookup"><span data-stu-id="02194-128">Otherwise, it returns a value of *False*.</span></span>

### <a name="example-2"></a><span data-ttu-id="02194-129">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="02194-129">Example 2</span></span>

<span data-ttu-id="02194-130">Este exemplo usa o atributo de texto `textFixedList` como o atributo de destino.</span><span class="sxs-lookup"><span data-stu-id="02194-130">This example uses the text attribute `textFixedList` as the target attribute.</span></span> <span data-ttu-id="02194-131">Este atributo contém a lista fixa a seguir.</span><span class="sxs-lookup"><span data-stu-id="02194-131">This attribute contains the following fixed list.</span></span>

| <span data-ttu-id="02194-132">Alíquota</span><span class="sxs-lookup"><span data-stu-id="02194-132">Value</span></span> | <span data-ttu-id="02194-133">Valor do agente de resolução</span><span class="sxs-lookup"><span data-stu-id="02194-133">Solver value</span></span> |
|---|---|
| <span data-ttu-id="02194-134">A</span><span class="sxs-lookup"><span data-stu-id="02194-134">A</span></span> | <span data-ttu-id="02194-135">1a</span><span class="sxs-lookup"><span data-stu-id="02194-135">1a</span></span> |
| <span data-ttu-id="02194-136">E</span><span class="sxs-lookup"><span data-stu-id="02194-136">B</span></span> | <span data-ttu-id="02194-137">2b</span><span class="sxs-lookup"><span data-stu-id="02194-137">2b</span></span> |
| <span data-ttu-id="02194-138">E</span><span class="sxs-lookup"><span data-stu-id="02194-138">C</span></span> | <span data-ttu-id="02194-139">2c</span><span class="sxs-lookup"><span data-stu-id="02194-139">2c</span></span> |

<span data-ttu-id="02194-140">A captura de tela a seguir mostra como as configurações desse atributo podem aparecer no seu sistema.</span><span class="sxs-lookup"><span data-stu-id="02194-140">The following screenshot shows how the settings for this attribute might look in your system.</span></span>

<span data-ttu-id="02194-141">![Configurações de tipo de atributo, por exemplo 2](media/model-calculations-example2.png "Configurações de tipo de atributo, por exemplo 2")</span><span class="sxs-lookup"><span data-stu-id="02194-141">![Attribute type settings for example 2](media/model-calculations-example2.png "Attribute type settings for example 2")</span></span>

<span data-ttu-id="02194-142">O atributo é usado na seguinte instrução condicional:</span><span class="sxs-lookup"><span data-stu-id="02194-142">The attribute is used in the following conditional statement:</span></span>

`If[integerAttribute < 150, 0, 2]`

<span data-ttu-id="02194-143">Se `integerAttribute` for menor que 150, esta instrução retornará o valor de texto do primeiro registro na lista fixa, *A*. Caso contrário, ele retorna o valor de texto do terceiro registro na lista fixa, *C*.</span><span class="sxs-lookup"><span data-stu-id="02194-143">If `integerAttribute` is less than 150, this statement returns the text value of the first record in the fixed list, *A*. Otherwise, it returns the text value of the third record in the fixed list, *C*.</span></span>

> [!NOTE]
> <span data-ttu-id="02194-144">A lista fixa é equivalente a uma enumeração baseada em zero (enum) e seus valores são acessados pelo valor inteiro apropriado.</span><span class="sxs-lookup"><span data-stu-id="02194-144">The fixed list is equivalent to a zero-based enumeration (enum), and its values are accessed by the appropriate integer value.</span></span> <span data-ttu-id="02194-145">Portanto, o primeiro valor de lista fixo (*A*) é correspondido como *0*, o segundo valor (*B*) corresponde a *1* e o terceiro valor (*C*) corresponde a *2*.</span><span class="sxs-lookup"><span data-stu-id="02194-145">Therefore, the first fixed list value (*A*) is matched to *0*, the second value (*B*) is matched to *1*, and the third value (*C*) is matched to *2*.</span></span>

### <a name="example-3"></a><span data-ttu-id="02194-146">Exemplo 3</span><span class="sxs-lookup"><span data-stu-id="02194-146">Example 3</span></span>

<span data-ttu-id="02194-147">Este exemplo usa o atributo de texto `textFixedList` do exemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="02194-147">This example uses the `textFixedList` target attribute from the previous example.</span></span> <span data-ttu-id="02194-148">Ele também usa outro atributo de texto, `textAttribute` que contém a lista fixa a seguir.</span><span class="sxs-lookup"><span data-stu-id="02194-148">It also uses another text attribute, `textAttribute`, that contains the following fixed list.</span></span>

| <span data-ttu-id="02194-149">Alíquota</span><span class="sxs-lookup"><span data-stu-id="02194-149">Value</span></span> | <span data-ttu-id="02194-150">Valor do agente de resolução</span><span class="sxs-lookup"><span data-stu-id="02194-150">Solver value</span></span> |
|---|---|
| <span data-ttu-id="02194-151">AA</span><span class="sxs-lookup"><span data-stu-id="02194-151">AA</span></span> | <span data-ttu-id="02194-152">1aa</span><span class="sxs-lookup"><span data-stu-id="02194-152">1aa</span></span> |
| <span data-ttu-id="02194-153">BB</span><span class="sxs-lookup"><span data-stu-id="02194-153">BB</span></span> | <span data-ttu-id="02194-154">2bb</span><span class="sxs-lookup"><span data-stu-id="02194-154">2bb</span></span> |

<span data-ttu-id="02194-155">A captura de tela a seguir mostra como as configurações desse atributo podem aparecer no seu sistema.</span><span class="sxs-lookup"><span data-stu-id="02194-155">The following screenshot shows how the settings for this attribute might look in your system.</span></span>

<span data-ttu-id="02194-156">![Configurações de tipo de atributo, por exemplo 3](media/model-calculations-example3.png "Configurações de tipo de atributo, por exemplo 3")</span><span class="sxs-lookup"><span data-stu-id="02194-156">![Attribute type settings for example 3](media/model-calculations-example3.png "Attribute type settings for example 3")</span></span>

<span data-ttu-id="02194-157">O valor do atributo `textFixedList` é calculado usando a seguinte instrução condicional:</span><span class="sxs-lookup"><span data-stu-id="02194-157">The value for the `textFixedList` attribute is calculated by using the following conditional statement:</span></span>

`If[textAttribute == "1aa", 0, 2]`

<span data-ttu-id="02194-158">Se o valor `textAttribute` tiver um valor de resolução igual a *1aa*, esta expressão retornará o valor de texto do primeiro registro na lista fixa `textFixedList`, *A*. Caso contrário, ele retorna o valor de texto do terceiro n lista fixa `textFixedList`, *C*.</span><span class="sxs-lookup"><span data-stu-id="02194-158">If the `textAttribute` value has a solver value that equals *1aa*, this expression returns the text value of the first record in the `textFixedList` fixed list, *A*. Otherwise, it returns the text value of the third record in the `textFixedList` fixed list, *C*.</span></span>

> [!NOTE]
> - <span data-ttu-id="02194-159">A instrução condicional deve usar o valor de resolução do atributo.</span><span class="sxs-lookup"><span data-stu-id="02194-159">The conditional statement must use the solver value of the attribute.</span></span>
> - <span data-ttu-id="02194-160">Somente atributos de texto de lista fixa podem ser usados em cálculos.</span><span class="sxs-lookup"><span data-stu-id="02194-160">Only fixed-list text attributes can be used in calculations.</span></span>

## <a name="see-also"></a><span data-ttu-id="02194-161">Consulte também</span><span class="sxs-lookup"><span data-stu-id="02194-161">See also</span></span>

- [<span data-ttu-id="02194-162">Perguntas frequentes sobre cálculos para modelos de configuração de produto</span><span class="sxs-lookup"><span data-stu-id="02194-162">Calculations for product configuration models FAQ</span></span>](calculate-product-configuration-models.md)
- [<span data-ttu-id="02194-163">Adicionar uma restrição de expressão para um modelo de configuração de produto</span><span class="sxs-lookup"><span data-stu-id="02194-163">Add an expression constraint to a product configuration model</span></span>](tasks/add-expression-constraint-product-configuration-model.md)
- [<span data-ttu-id="02194-164">Visão geral dos modelos de configuração de produto</span><span class="sxs-lookup"><span data-stu-id="02194-164">Product configuration models overview</span></span>](product-configuration-models.md)
