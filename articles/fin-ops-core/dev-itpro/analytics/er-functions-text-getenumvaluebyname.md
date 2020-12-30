---
title: Função de ER GETENUMVALUEBYNAME
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) GETENUMVALUEBYNAME é usada.
author: NickSelin
manager: kfend
ms.date: 09/23/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 29d7ec6498090ea47259303237c5a64a26e4926b
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4685922"
---
# <a name="getenumvaluebyname-er-function"></a><span data-ttu-id="6d5f3-103">Função de ER GETENUMVALUEBYNAME</span><span class="sxs-lookup"><span data-stu-id="6d5f3-103">GETENUMVALUEBYNAME ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6d5f3-104">A função `GETENUMVALUEBYNAME` procura um valor de *Enum.* específico na fonte de dados de enumeração especificada usando o nome de enumeração especificado como um valor de *Cadeia de caracteres*.</span><span class="sxs-lookup"><span data-stu-id="6d5f3-104">The `GETENUMVALUEBYNAME` function searches for a specific *Enum* value in the specified enumeration data source by using the enumeration name that is specified as a *String* value.</span></span> <span data-ttu-id="6d5f3-105">Se o valor *Enum.* for encontrado, a função o retornará.</span><span class="sxs-lookup"><span data-stu-id="6d5f3-105">If the *Enum* value is found, the function returns it.</span></span> <span data-ttu-id="6d5f3-106">Caso contrário, a função retorna o valor de enumeração **nulo**.</span><span class="sxs-lookup"><span data-stu-id="6d5f3-106">Otherwise, the function returns the **null** enumeration value.</span></span>

## <a name="syntax"></a><span data-ttu-id="6d5f3-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="6d5f3-107">Syntax</span></span>

```vb
GETENUMVALUEBYNAME (enumeration data source path, enumeration value text)
```

## <a name="arguments"></a><span data-ttu-id="6d5f3-108">Argumentos</span><span class="sxs-lookup"><span data-stu-id="6d5f3-108">Arguments</span></span>

<span data-ttu-id="6d5f3-109">`enumeration data source path`: *Enumeração*</span><span class="sxs-lookup"><span data-stu-id="6d5f3-109">`enumeration data source path`: *Enumeration*</span></span>

<span data-ttu-id="6d5f3-110">O caminho válido de uma fonte de dados de um dos seguintes tipos de enumeração:</span><span class="sxs-lookup"><span data-stu-id="6d5f3-110">The valid path of a data source of one of the following enumeration types:</span></span>

- <span data-ttu-id="6d5f3-111">Enumeração de modelo de relatório eletrônico (ER)</span><span class="sxs-lookup"><span data-stu-id="6d5f3-111">Electronic reporting (ER) model enumeration</span></span>
- <span data-ttu-id="6d5f3-112">Enumeração de formato de ER</span><span class="sxs-lookup"><span data-stu-id="6d5f3-112">ER format enumeration</span></span>
- <span data-ttu-id="6d5f3-113">Enumeração do Microsoft Dynamics 365 Finance</span><span class="sxs-lookup"><span data-stu-id="6d5f3-113">Microsoft Dynamics 365 Finance enumeration</span></span>

<span data-ttu-id="6d5f3-114">`enumeration value text`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="6d5f3-114">`enumeration value text`: *String*</span></span>

<span data-ttu-id="6d5f3-115">Um valor de cadeia de caracteres que representa o nome de um único valor de enumeração.</span><span class="sxs-lookup"><span data-stu-id="6d5f3-115">A string value that represents the name of a single enumeration value.</span></span>

## <a name="return-values"></a><span data-ttu-id="6d5f3-116">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="6d5f3-116">Return values</span></span>

<span data-ttu-id="6d5f3-117">*Enum.* anulável</span><span class="sxs-lookup"><span data-stu-id="6d5f3-117">Nullable *Enum*</span></span>

<span data-ttu-id="6d5f3-118">O valor de enumeração resultante.</span><span class="sxs-lookup"><span data-stu-id="6d5f3-118">The resulting enumeration value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="6d5f3-119">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="6d5f3-119">Usage notes</span></span>

<span data-ttu-id="6d5f3-120">Nenhuma exceção é gerada se um valor de *Enum.* não for encontrado usando o nome do valor de enumeração especificado como um valor de *Cadeia de caracteres*.</span><span class="sxs-lookup"><span data-stu-id="6d5f3-120">No exception is thrown if an *Enum* value isn't found by using the name of the enumeration value that is specified as a *String* value.</span></span>

## <a name="example-1"></a><span data-ttu-id="6d5f3-121">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="6d5f3-121">Example 1</span></span>

<span data-ttu-id="6d5f3-122">Na ilustração a seguir, a enumeração de **ReportDirection** é apresentada em um modelo de dados.</span><span class="sxs-lookup"><span data-stu-id="6d5f3-122">In the following illustration, the **ReportDirection** enumeration is introduced in a data model.</span></span> <span data-ttu-id="6d5f3-123">Observe que os rótulos são definidos para os valores de enumeração.</span><span class="sxs-lookup"><span data-stu-id="6d5f3-123">Notice that labels are defined for the enumeration values.</span></span>

![Valores disponíveis para uma enumeração de modelo de dados](./media/ER-data-model-enumeration-values.PNG)

<span data-ttu-id="6d5f3-125">A ilustração a seguir mostra estes detalhes:</span><span class="sxs-lookup"><span data-stu-id="6d5f3-125">The following illustration shows these details:</span></span>

- <span data-ttu-id="6d5f3-126">A fonte de dados **$Direction** é configurada em um relatório de ER.</span><span class="sxs-lookup"><span data-stu-id="6d5f3-126">The **$Direction** data source is configured in an ER report.</span></span> <span data-ttu-id="6d5f3-127">Essa fonte de dados é configurada com base na enumeração do modelo **ReportDirection**.</span><span class="sxs-lookup"><span data-stu-id="6d5f3-127">This data source is configured based on the **ReportDirection** model enumeration.</span></span>
- <span data-ttu-id="6d5f3-128">A expressão `$IsArrivals` foi criada para usar a fonte de dados **$Direction** baseada na enumeração do modelo como um parâmetro desta função.</span><span class="sxs-lookup"><span data-stu-id="6d5f3-128">The `$IsArrivals` expression is designed to use the model enumeration–based **$Direction** data source as a parameter of this function.</span></span>
- <span data-ttu-id="6d5f3-129">O valor dessa expressão de comparação é **TRUE**.</span><span class="sxs-lookup"><span data-stu-id="6d5f3-129">The value of this comparison expression is **TRUE**.</span></span>

![Exemplo de enumeração de modelo de dados](./media/ER-data-model-enumeration-usage.PNG)

## <a name="example-2"></a><span data-ttu-id="6d5f3-131">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="6d5f3-131">Example 2</span></span>

<span data-ttu-id="6d5f3-132">As funções `GETENUMVALUEBYNAME` e [`LISTOFFIELDS`](er-functions-list-listoffields.md) permitem buscar valores e etiquetas de enumerações com suporte como valores de texto.</span><span class="sxs-lookup"><span data-stu-id="6d5f3-132">The `GETENUMVALUEBYNAME` and [`LISTOFFIELDS`](er-functions-list-listoffields.md) functions let you fetch values and labels of supported enumerations as text values.</span></span> <span data-ttu-id="6d5f3-133">(As enumerações com suporte são enumerações de aplicativo, enumerações de modelo de dados e enumerações de formato.)</span><span class="sxs-lookup"><span data-stu-id="6d5f3-133">(The supported enumerations are application enumerations, data model enumerations, and format enumerations.)</span></span>

<span data-ttu-id="6d5f3-134">Na ilustração a seguir, a fonte de dados **TransType** é apresentada em um mapeamento de modelo.</span><span class="sxs-lookup"><span data-stu-id="6d5f3-134">In the following illustration, the **TransType** data source is introduced in a model mapping.</span></span> <span data-ttu-id="6d5f3-135">Essa fonte de dados refere-se à enumeração de aplicativo **LedgerTransType**.</span><span class="sxs-lookup"><span data-stu-id="6d5f3-135">This data source refers to the **LedgerTransType** application enumeration.</span></span>

![Fonte de dados de um mapeamento de modelo que se refere a uma enumeração de aplicativo](./media/er-functions-text-getenumvaluebyname-example2-1.png)

<span data-ttu-id="6d5f3-137">A ilustração a seguir mostra a fonte de dados **TransTypeList** configurada em um mapeamento de modelo.</span><span class="sxs-lookup"><span data-stu-id="6d5f3-137">The following illustration shows the **TransTypeList** data source that is configured in a model mapping.</span></span> <span data-ttu-id="6d5f3-138">Essa fonte de dados é configurada com base na enumeração do aplicativo **TransType**.</span><span class="sxs-lookup"><span data-stu-id="6d5f3-138">This data source is configured based on the **TransType** application enumeration.</span></span> <span data-ttu-id="6d5f3-139">A função `LISTOFFIELDS` é usada para retornar todos os valores de enumeração como uma lista de registros que contêm campos.</span><span class="sxs-lookup"><span data-stu-id="6d5f3-139">The `LISTOFFIELDS` function is used to return all enumeration values as a list of records that contain fields.</span></span> <span data-ttu-id="6d5f3-140">Dessa forma, os detalhes de cada valor de enumeração são expostos.</span><span class="sxs-lookup"><span data-stu-id="6d5f3-140">In this way, the details of every enumeration value are exposed.</span></span>

> [!NOTE]
> <span data-ttu-id="6d5f3-141">O campo **EnumValue** é configurado para a fonte de dados **TransTypeList** usando a expressão `GETENUMVALUEBYNAME(TransType, TransTypeList.Name)`.</span><span class="sxs-lookup"><span data-stu-id="6d5f3-141">The **EnumValue** field is configured for the **TransTypeList** data source by using the `GETENUMVALUEBYNAME(TransType, TransTypeList.Name)` expression.</span></span> <span data-ttu-id="6d5f3-142">Esse campo retorna um valor de enumeração para cada registro nessa lista.</span><span class="sxs-lookup"><span data-stu-id="6d5f3-142">This field returns an enumeration value for every record in this list.</span></span>

![Fonte de dados de um mapeamento de modelo que retorna todos os valores de enumeração de uma enumeração selecionada como uma lista de registros](./media/er-functions-text-getenumvaluebyname-example2-2.png)

<span data-ttu-id="6d5f3-144">A ilustração a seguir mostra a fonte de dados **VendTrans** configurada em um mapeamento de modelo.</span><span class="sxs-lookup"><span data-stu-id="6d5f3-144">The following illustration shows the **VendTrans** data source that is configured in a model mapping.</span></span> <span data-ttu-id="6d5f3-145">Essa fonte de dados retorna registros de transações do fornecedor da tabela de aplicativos **VendTrans**.</span><span class="sxs-lookup"><span data-stu-id="6d5f3-145">This data source returns vendor transaction records from the **VendTrans** application table.</span></span> <span data-ttu-id="6d5f3-146">O tipo de razão de cada transação é definido pelo valor do campo **TransType**.</span><span class="sxs-lookup"><span data-stu-id="6d5f3-146">The ledger type of every transaction is defined by the value of the **TransType** field.</span></span>

> [!NOTE]
> <span data-ttu-id="6d5f3-147">O campo **TransTypeTitle** é configurado para a fonte de dados **VendTrans** usando a expressão `FIRSTORNULL(WHERE(TransTypeList, TransTypeList.EnumValue = @.TransType)).Label`.</span><span class="sxs-lookup"><span data-stu-id="6d5f3-147">The **TransTypeTitle** field is configured for the **VendTrans** data source by using the `FIRSTORNULL(WHERE(TransTypeList, TransTypeList.EnumValue = @.TransType)).Label` expression.</span></span> <span data-ttu-id="6d5f3-148">Esse campo retorna o rótulo de um valor de enumeração da transação atual como texto, se esse valor de enumeração estiver disponível.</span><span class="sxs-lookup"><span data-stu-id="6d5f3-148">This field returns the label of an enumeration value of the current transaction as text, if this enumeration value is available.</span></span> <span data-ttu-id="6d5f3-149">Caso contrário, ele retorna um valor de cadeia de caracteres em branco.</span><span class="sxs-lookup"><span data-stu-id="6d5f3-149">Otherwise, it returns a blank string value.</span></span>
>
> <span data-ttu-id="6d5f3-150">O campo **TransTypeTitle** está vinculado ao campo **LedgerType** de um modelo de dados que permite que essas informações sejam usadas em todos os formatos ER que usam o modelo de dados como fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="6d5f3-150">The **TransTypeTitle** field is bound to the **LedgerType** field of a data model that enables this information to be used in every ER format that uses the data model as a source of data.</span></span>

![Fonte de dados de um mapeamento de modelo que retorna as transações do fornecedor](./media/er-functions-text-getenumvaluebyname-example2-3.png)

<span data-ttu-id="6d5f3-152">A ilustração a seguir mostra como você pode usar o [depurador da fonte de dados](er-debug-data-sources.md) para testar o mapeamento do modelo configurado.</span><span class="sxs-lookup"><span data-stu-id="6d5f3-152">The following illustration shows how you can use the [data source debugger](er-debug-data-sources.md) to test the configured model mapping.</span></span>

![Uso do depurador de fonte de dados para testar o mapeamento do modelo configurado](./media/er-functions-text-getenumvaluebyname-example2-4.gif)

<span data-ttu-id="6d5f3-154">O campo **LedgerType** de um modelo de dados expõe etiquetas de tipos de transação conforme o esperado.</span><span class="sxs-lookup"><span data-stu-id="6d5f3-154">The **LedgerType** field of a data model exposes labels of transaction types as expected.</span></span>

<span data-ttu-id="6d5f3-155">Se você planeja usar essa abordagem para uma grande quantidade de dados transacionais, deve considerar o desempenho de execução.</span><span class="sxs-lookup"><span data-stu-id="6d5f3-155">If you plan to use this approach for a large amount of transactional data, you must consider execution performance.</span></span> <span data-ttu-id="6d5f3-156">Para obter mais informações, consulte [Rastrear a execução de formatos de ER para solucionar problemas de desempenho](trace-execution-er-troubleshoot-perf.md).</span><span class="sxs-lookup"><span data-stu-id="6d5f3-156">For more information, see [Trace the execution of ER formats to troubleshoot performance issues](trace-execution-er-troubleshoot-perf.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="6d5f3-157">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="6d5f3-157">Additional resources</span></span>

[<span data-ttu-id="6d5f3-158">Funções de texto</span><span class="sxs-lookup"><span data-stu-id="6d5f3-158">Text functions</span></span>](er-functions-category-text.md)

[<span data-ttu-id="6d5f3-159">Rastrear a execução de formatos de ER para solucionar problemas de desempenho</span><span class="sxs-lookup"><span data-stu-id="6d5f3-159">Trace the execution of ER formats to troubleshoot performance issues</span></span>](trace-execution-er-troubleshoot-perf.md)

[<span data-ttu-id="6d5f3-160">Função de ER LISTOFFIELDS</span><span class="sxs-lookup"><span data-stu-id="6d5f3-160">LISTOFFIELDS ER function</span></span>](er-functions-list-listoffields.md)

[<span data-ttu-id="6d5f3-161">Função de ER FIRSTORNULL</span><span class="sxs-lookup"><span data-stu-id="6d5f3-161">FIRSTORNULL ER function</span></span>](er-functions-list-firstornull.md)

[<span data-ttu-id="6d5f3-162">Função de ER WHERE</span><span class="sxs-lookup"><span data-stu-id="6d5f3-162">WHERE ER function</span></span>](er-functions-list-where.md)
