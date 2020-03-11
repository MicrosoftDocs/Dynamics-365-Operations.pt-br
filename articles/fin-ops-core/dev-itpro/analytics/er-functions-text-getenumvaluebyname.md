---
title: Função de ER GETENUMVALUEBYNAME
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) GETENUMVALUEBYNAME é usada.
author: NickSelin
manager: kfend
ms.date: 12/12/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 87613978c149b5d41aefc58f9896424229819626
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041149"
---
# <span data-ttu-id="5de3a-103"><a name="GETENUMVALUEBYNAME">Função de ER GETENUMVALUEBYNAME</a></span><span class="sxs-lookup"><span data-stu-id="5de3a-103"><a name="GETENUMVALUEBYNAME">GETENUMVALUEBYNAME ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5de3a-104">A função `GETENUMVALUEBYNAME` procura um valor de *Enum.* específico na fonte de dados de enumeração especificada usando o nome de enumeração especificado como um valor de *Cadeia de caracteres*.</span><span class="sxs-lookup"><span data-stu-id="5de3a-104">The `GETENUMVALUEBYNAME` function searches for a specific *Enum* value in the specified enumeration data source by using the enumeration name that is specified as a *String* value.</span></span> <span data-ttu-id="5de3a-105">Se o valor *Enum.* for encontrado, a função o retornará.</span><span class="sxs-lookup"><span data-stu-id="5de3a-105">If the *Enum* value is found, the function returns it.</span></span> <span data-ttu-id="5de3a-106">Caso contrário, a função retorna o valor de enumeração **nulo**.</span><span class="sxs-lookup"><span data-stu-id="5de3a-106">Otherwise, the function returns the **null** enumeration value.</span></span>

## <a name="syntax"></a><span data-ttu-id="5de3a-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="5de3a-107">Syntax</span></span>

```vb
GETENUMVALUEBYNAME (enumeration data source path, enumeration value text)
```

## <a name="arguments"></a><span data-ttu-id="5de3a-108">Argumentos</span><span class="sxs-lookup"><span data-stu-id="5de3a-108">Arguments</span></span>

<span data-ttu-id="5de3a-109">`enumeration data source path`: *Enumeração*</span><span class="sxs-lookup"><span data-stu-id="5de3a-109">`enumeration data source path`: *Enumeration*</span></span>

<span data-ttu-id="5de3a-110">O caminho válido de uma fonte de dados de um dos seguintes tipos de enumeração:</span><span class="sxs-lookup"><span data-stu-id="5de3a-110">The valid path of a data source of one of the following enumeration types:</span></span>

- <span data-ttu-id="5de3a-111">Enumeração de modelo de relatório eletrônico (ER)</span><span class="sxs-lookup"><span data-stu-id="5de3a-111">Electronic reporting (ER) model enumeration</span></span>
- <span data-ttu-id="5de3a-112">Enumeração de formato de ER</span><span class="sxs-lookup"><span data-stu-id="5de3a-112">ER format enumeration</span></span>
- <span data-ttu-id="5de3a-113">Enumeração do Microsoft Dynamics 365 Finance</span><span class="sxs-lookup"><span data-stu-id="5de3a-113">Microsoft Dynamics 365 Finance enumeration</span></span>

<span data-ttu-id="5de3a-114">`enumeration value text`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="5de3a-114">`enumeration value text`: *String*</span></span>

<span data-ttu-id="5de3a-115">Um valor de cadeia de caracteres que representa o nome de um único valor de enumeração.</span><span class="sxs-lookup"><span data-stu-id="5de3a-115">A string value that represents the name of a single enumeration value.</span></span>

## <a name="return-values"></a><span data-ttu-id="5de3a-116">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="5de3a-116">Return values</span></span>

<span data-ttu-id="5de3a-117">*Enum.* anulável</span><span class="sxs-lookup"><span data-stu-id="5de3a-117">Nullable *Enum*</span></span>

<span data-ttu-id="5de3a-118">O valor de enumeração resultante.</span><span class="sxs-lookup"><span data-stu-id="5de3a-118">The resulting enumeration value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="5de3a-119">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="5de3a-119">Usage notes</span></span>

<span data-ttu-id="5de3a-120">Nenhuma exceção é gerada se um valor de *Enum.* não for encontrado usando o nome do valor de enumeração especificado como um valor de *Cadeia de caracteres*.</span><span class="sxs-lookup"><span data-stu-id="5de3a-120">No exception is thrown if an *Enum* value isn't found by using the name of the enumeration value that is specified as a *String* value.</span></span>

## <a name="example"></a><span data-ttu-id="5de3a-121">Exemplo</span><span class="sxs-lookup"><span data-stu-id="5de3a-121">Example</span></span>

<span data-ttu-id="5de3a-122">Na ilustração a seguir, a enumeração de **ReportDirection** é apresentada em um modelo de dados.</span><span class="sxs-lookup"><span data-stu-id="5de3a-122">In the following illustration, the **ReportDirection** enumeration is introduced in a data model.</span></span> <span data-ttu-id="5de3a-123">Observe que os rótulos são definidos para os valores de enumeração.</span><span class="sxs-lookup"><span data-stu-id="5de3a-123">Notice that labels are defined for the enumeration values.</span></span>

<p><a href="./media/ER-data-model-enumeration-values.PNG"><img src="./media/ER-data-model-enumeration-values.PNG" alt="Available values for a data model enumeration" class="alignnone wp-image-290681 size-full" width="397" height="136" /></a>

<span data-ttu-id="5de3a-124">A ilustração a seguir mostra estes detalhes:</span><span class="sxs-lookup"><span data-stu-id="5de3a-124">The following illustration shows these details:</span></span>

- <span data-ttu-id="5de3a-125">A fonte de dados **$Direction** é configurada em um relatório de ER.</span><span class="sxs-lookup"><span data-stu-id="5de3a-125">The **$Direction** data source is configured in an ER report.</span></span> <span data-ttu-id="5de3a-126">Essa fonte de dados é configurada com base na enumeração do modelo **ReportDirection**.</span><span class="sxs-lookup"><span data-stu-id="5de3a-126">This data source is configured based on the **ReportDirection** model enumeration.</span></span>
- <span data-ttu-id="5de3a-127">A expressão `$IsArrivals` foi criada para usar a fonte de dados **$Direction** baseada na enumeração do modelo como um parâmetro desta função.</span><span class="sxs-lookup"><span data-stu-id="5de3a-127">The `$IsArrivals` expression is designed to use the model enumeration–based **$Direction** data source as a parameter of this function.</span></span>
- <span data-ttu-id="5de3a-128">O valor dessa expressão de comparação é **TRUE**.</span><span class="sxs-lookup"><span data-stu-id="5de3a-128">The value of this comparison expression is **TRUE**.</span></span>

<a href="./media/ER-data-model-enumeration-usage.PNG"><img src="./media/ER-data-model-enumeration-usage.PNG" alt="Example of data model enumeration" class="alignnone wp-image-290681 size-full" width="397" height="136" /></a>

## <a name="additional-resources"></a><span data-ttu-id="5de3a-129">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="5de3a-129">Additional resources</span></span>

[<span data-ttu-id="5de3a-130">Funções de texto</span><span class="sxs-lookup"><span data-stu-id="5de3a-130">Text functions</span></span>](er-functions-category-text.md)
