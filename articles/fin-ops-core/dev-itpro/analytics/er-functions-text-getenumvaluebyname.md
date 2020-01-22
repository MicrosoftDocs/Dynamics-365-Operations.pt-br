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
ms.openlocfilehash: 4ded0c62b4556b21e731cd9b98db2863ec6ec442
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916835"
---
# <span data-ttu-id="3a32c-103"><a name="GETENUMVALUEBYNAME">Função de ER GETENUMVALUEBYNAME</a></span><span class="sxs-lookup"><span data-stu-id="3a32c-103"><a name="GETENUMVALUEBYNAME">GETENUMVALUEBYNAME ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="3a32c-104">A função `GETENUMVALUEBYNAME` procura um valor de *Enum.* específico na fonte de dados de enumeração especificada usando o nome de enumeração especificado como um valor de *Cadeia de caracteres*.</span><span class="sxs-lookup"><span data-stu-id="3a32c-104">The `GETENUMVALUEBYNAME` function searches for a specific *Enum* value in the specified enumeration data source by using the enumeration name that is specified as a *String* value.</span></span> <span data-ttu-id="3a32c-105">Se o valor *Enum.* for encontrado, a função o retornará.</span><span class="sxs-lookup"><span data-stu-id="3a32c-105">If the *Enum* value is found, the function returns it.</span></span> <span data-ttu-id="3a32c-106">Caso contrário, a função retorna o valor de enumeração **nulo**.</span><span class="sxs-lookup"><span data-stu-id="3a32c-106">Otherwise, the function returns the **null** enumeration value.</span></span>

## <a name="syntax"></a><span data-ttu-id="3a32c-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="3a32c-107">Syntax</span></span>

```
GETENUMVALUEBYNAME (enumeration data source path, enumeration value text)
```

## <a name="arguments"></a><span data-ttu-id="3a32c-108">Argumentos</span><span class="sxs-lookup"><span data-stu-id="3a32c-108">Arguments</span></span>

<span data-ttu-id="3a32c-109">`enumeration data source path`: *Enumeração*</span><span class="sxs-lookup"><span data-stu-id="3a32c-109">`enumeration data source path`: *Enumeration*</span></span>

<span data-ttu-id="3a32c-110">O caminho válido de uma fonte de dados de um dos seguintes tipos de enumeração:</span><span class="sxs-lookup"><span data-stu-id="3a32c-110">The valid path of a data source of one of the following enumeration types:</span></span>

- <span data-ttu-id="3a32c-111">Enumeração de modelo de relatório eletrônico (ER)</span><span class="sxs-lookup"><span data-stu-id="3a32c-111">Electronic reporting (ER) model enumeration</span></span>
- <span data-ttu-id="3a32c-112">Enumeração de formato de ER</span><span class="sxs-lookup"><span data-stu-id="3a32c-112">ER format enumeration</span></span>
- <span data-ttu-id="3a32c-113">Enumeração do Microsoft Dynamics 365 Finance</span><span class="sxs-lookup"><span data-stu-id="3a32c-113">Microsoft Dynamics 365 Finance enumeration</span></span>

<span data-ttu-id="3a32c-114">`enumeration value text`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="3a32c-114">`enumeration value text`: *String*</span></span>

<span data-ttu-id="3a32c-115">Um valor de cadeia de caracteres que representa o nome de um único valor de enumeração.</span><span class="sxs-lookup"><span data-stu-id="3a32c-115">A string value that represents the name of a single enumeration value.</span></span>

## <a name="return-values"></a><span data-ttu-id="3a32c-116">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="3a32c-116">Return values</span></span>

<span data-ttu-id="3a32c-117">*Enum.* anulável</span><span class="sxs-lookup"><span data-stu-id="3a32c-117">Nullable *Enum*</span></span>

<span data-ttu-id="3a32c-118">O valor de enumeração resultante.</span><span class="sxs-lookup"><span data-stu-id="3a32c-118">The resulting enumeration value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="3a32c-119">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="3a32c-119">Usage notes</span></span>

<span data-ttu-id="3a32c-120">Nenhuma exceção é gerada se um valor de *Enum.* não for encontrado usando o nome do valor de enumeração especificado como um valor de *Cadeia de caracteres*.</span><span class="sxs-lookup"><span data-stu-id="3a32c-120">No exception is thrown if an *Enum* value isn't found by using the name of the enumeration value that is specified as a *String* value.</span></span>

## <a name="example"></a><span data-ttu-id="3a32c-121">Exemplo</span><span class="sxs-lookup"><span data-stu-id="3a32c-121">Example</span></span>

<span data-ttu-id="3a32c-122">Na ilustração a seguir, a enumeração de **ReportDirection** é apresentada em um modelo de dados.</span><span class="sxs-lookup"><span data-stu-id="3a32c-122">In the following illustration, the **ReportDirection** enumeration is introduced in a data model.</span></span> <span data-ttu-id="3a32c-123">Observe que os rótulos são definidos para os valores de enumeração.</span><span class="sxs-lookup"><span data-stu-id="3a32c-123">Notice that labels are defined for the enumeration values.</span></span>

<p><a href="./media/ER-data-model-enumeration-values.PNG"><img src="./media/ER-data-model-enumeration-values.PNG" alt="Available values for a data model enumeration" class="alignnone wp-image-290681 size-full" width="397" height="136" /></a>

<span data-ttu-id="3a32c-124">A ilustração a seguir mostra estes detalhes:</span><span class="sxs-lookup"><span data-stu-id="3a32c-124">The following illustration shows these details:</span></span>

- <span data-ttu-id="3a32c-125">A fonte de dados **$Direction** é configurada em um relatório de ER.</span><span class="sxs-lookup"><span data-stu-id="3a32c-125">The **$Direction** data source is configured in an ER report.</span></span> <span data-ttu-id="3a32c-126">Essa fonte de dados é configurada com base na enumeração do modelo **ReportDirection**.</span><span class="sxs-lookup"><span data-stu-id="3a32c-126">This data source is configured based on the **ReportDirection** model enumeration.</span></span>
- <span data-ttu-id="3a32c-127">A expressão `$IsArrivals` foi criada para usar a fonte de dados **$Direction** baseada na enumeração do modelo como um parâmetro desta função.</span><span class="sxs-lookup"><span data-stu-id="3a32c-127">The `$IsArrivals` expression is designed to use the model enumeration–based **$Direction** data source as a parameter of this function.</span></span>
- <span data-ttu-id="3a32c-128">O valor dessa expressão de comparação é **TRUE**.</span><span class="sxs-lookup"><span data-stu-id="3a32c-128">The value of this comparison expression is **TRUE**.</span></span>

<a href="./media/ER-data-model-enumeration-usage.PNG"><img src="./media/ER-data-model-enumeration-usage.PNG" alt="Example of data model enumeration" class="alignnone wp-image-290681 size-full" width="397" height="136" /></a>

## <a name="additional-resources"></a><span data-ttu-id="3a32c-129">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="3a32c-129">Additional resources</span></span>

[<span data-ttu-id="3a32c-130">Funções de texto</span><span class="sxs-lookup"><span data-stu-id="3a32c-130">Text functions</span></span>](er-functions-category-text.md)
