---
title: Função de ER GUIDVALUE
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) GUIDVALUE é usada.
author: NickSelin
ms.date: 12/12/2019
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: ec8222708b999a17794a396b5bf807dab037799d
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746378"
---
# <a name="guidvalue-er-function"></a><span data-ttu-id="ab76b-103">Função de ER GUIDVALUE</span><span class="sxs-lookup"><span data-stu-id="ab76b-103">GUIDVALUE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ab76b-104">A função `GUIDVALUE` converte a entrada especificada do tipo *Cadeia de caracteres* em um item de dados do tipo *GUID*.</span><span class="sxs-lookup"><span data-stu-id="ab76b-104">The `GUIDVALUE` function converts the specified input of the *String* type to a data item of the *GUID* type.</span></span>

## <a name="syntax"></a><span data-ttu-id="ab76b-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="ab76b-105">Syntax</span></span>

```vb
GUIDVALUE (input)
```

## <a name="arguments"></a><span data-ttu-id="ab76b-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="ab76b-106">Arguments</span></span>

<span data-ttu-id="ab76b-107">`input`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="ab76b-107">`input`: *String*</span></span>

<span data-ttu-id="ab76b-108">O caminho válido de uma fonte de dados do tipo *Cadeia de caracteres*.</span><span class="sxs-lookup"><span data-stu-id="ab76b-108">The valid path of a data source of the *String* type.</span></span>

## <a name="return-values"></a><span data-ttu-id="ab76b-109">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="ab76b-109">Return values</span></span>

<span data-ttu-id="ab76b-110">*GUID*</span><span class="sxs-lookup"><span data-stu-id="ab76b-110">*GUID*</span></span>

<span data-ttu-id="ab76b-111">O valor do Identificador Global Exclusivo (GUID) resultante.</span><span class="sxs-lookup"><span data-stu-id="ab76b-111">The resulting globally unique identifier (GUID) value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="ab76b-112">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="ab76b-112">Usage notes</span></span>

<span data-ttu-id="ab76b-113">Para fazer uma conversão na direção oposta (isto é, para converter a entrada especificada do tipo de dados *GUID* em um item de dados do tipo *Cadeia de caracteres*), você pode usar a função [TEXT](er-functions-text-text.md).</span><span class="sxs-lookup"><span data-stu-id="ab76b-113">To do a conversion in the opposite direction (that is, to convert specified input of the *GUID* data type to a data item of the *String* data type), you can use the [TEXT](er-functions-text-text.md) function.</span></span>

## <a name="example"></a><span data-ttu-id="ab76b-114">Exemplo</span><span class="sxs-lookup"><span data-stu-id="ab76b-114">Example</span></span>

<span data-ttu-id="ab76b-115">Você define as seguintes fontes de dados no mapeamento de modelo:</span><span class="sxs-lookup"><span data-stu-id="ab76b-115">You define the following data sources in your model mapping:</span></span>

- <span data-ttu-id="ab76b-116">Uma fonte de dados **myID** do tipo *Campo calculado* que contém a expressão `GUIDVALUE ("AF5CCDAC-F728-4609-8C8B- A4B30B0C0AA0")`</span><span class="sxs-lookup"><span data-stu-id="ab76b-116">A **myID** data source of the *Calculated field* type that contains the expression `GUIDVALUE ("AF5CCDAC-F728-4609-8C8B- A4B30B0C0AA0")`</span></span>
- <span data-ttu-id="ab76b-117">Uma fonte de dados **Usuários** do tipo *Registros de tabela* que se refere à tabela UserInfo</span><span class="sxs-lookup"><span data-stu-id="ab76b-117">A **Users** data source of the *Table records* type that refers to the UserInfo table</span></span>

<span data-ttu-id="ab76b-118">Em seguida, você pode usar uma expressão como `FILTER (Users, Users.objectId = myID)` para filtrar a tabela UserInfo pelo campo **objectId** do tipo de dados *GUID*.</span><span class="sxs-lookup"><span data-stu-id="ab76b-118">You can then use an expression such as `FILTER (Users, Users.objectId = myID)` to filter the UserInfo table by the **objectId** field of the *GUID* data type.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ab76b-119">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="ab76b-119">Additional resources</span></span>

[<span data-ttu-id="ab76b-120">Funções de texto</span><span class="sxs-lookup"><span data-stu-id="ab76b-120">Text functions</span></span>](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]