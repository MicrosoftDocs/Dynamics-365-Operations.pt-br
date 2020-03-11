---
title: Função de ER GUIDVALUE
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) GUIDVALUE é usada.
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
ms.openlocfilehash: a7b8c782aff488a433c40a49ab7f4fe2d0e944e4
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041141"
---
# <span data-ttu-id="4dc82-103"><a name="GUIDVALUE">Função de ER GUIDVALUE</a></span><span class="sxs-lookup"><span data-stu-id="4dc82-103"><a name="GUIDVALUE">GUIDVALUE ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4dc82-104">A função `GUIDVALUE` converte a entrada especificada do tipo *Cadeia de caracteres* em um item de dados do tipo *GUID*.</span><span class="sxs-lookup"><span data-stu-id="4dc82-104">The `GUIDVALUE` function converts the specified input of the *String* type to a data item of the *GUID* type.</span></span>

## <a name="syntax"></a><span data-ttu-id="4dc82-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="4dc82-105">Syntax</span></span>

```vb
GUIDVALUE (input)
```

## <a name="arguments"></a><span data-ttu-id="4dc82-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="4dc82-106">Arguments</span></span>

<span data-ttu-id="4dc82-107">`input`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="4dc82-107">`input`: *String*</span></span>

<span data-ttu-id="4dc82-108">O caminho válido de uma fonte de dados do tipo *Cadeia de caracteres*.</span><span class="sxs-lookup"><span data-stu-id="4dc82-108">The valid path of a data source of the *String* type.</span></span>

## <a name="return-values"></a><span data-ttu-id="4dc82-109">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="4dc82-109">Return values</span></span>

<span data-ttu-id="4dc82-110">*GUID*</span><span class="sxs-lookup"><span data-stu-id="4dc82-110">*GUID*</span></span>

<span data-ttu-id="4dc82-111">O valor do Identificador Global Exclusivo (GUID) resultante.</span><span class="sxs-lookup"><span data-stu-id="4dc82-111">The resulting globally unique identifier (GUID) value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="4dc82-112">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="4dc82-112">Usage notes</span></span>

<span data-ttu-id="4dc82-113">Para fazer uma conversão na direção oposta (isto é, para converter a entrada especificada do tipo de dados *GUID* em um item de dados do tipo *Cadeia de caracteres*), você pode usar a função [TEXT](er-functions-text-text.md).</span><span class="sxs-lookup"><span data-stu-id="4dc82-113">To do a conversion in the opposite direction (that is, to convert specified input of the *GUID* data type to a data item of the *String* data type), you can use the [TEXT](er-functions-text-text.md) function.</span></span>

## <a name="example"></a><span data-ttu-id="4dc82-114">Exemplo</span><span class="sxs-lookup"><span data-stu-id="4dc82-114">Example</span></span>

<span data-ttu-id="4dc82-115">Você define as seguintes fontes de dados no mapeamento de modelo:</span><span class="sxs-lookup"><span data-stu-id="4dc82-115">You define the following data sources in your model mapping:</span></span>

- <span data-ttu-id="4dc82-116">Uma fonte de dados **myID** do tipo *Campo calculado* que contém a expressão `GUIDVALUE ("AF5CCDAC-F728-4609-8C8B- A4B30B0C0AA0")`</span><span class="sxs-lookup"><span data-stu-id="4dc82-116">A **myID** data source of the *Calculated field* type that contains the expression `GUIDVALUE ("AF5CCDAC-F728-4609-8C8B- A4B30B0C0AA0")`</span></span>
- <span data-ttu-id="4dc82-117">Uma fonte de dados **Usuários** do tipo *Registros de tabela* que se refere à tabela UserInfo</span><span class="sxs-lookup"><span data-stu-id="4dc82-117">A **Users** data source of the *Table records* type that refers to the UserInfo table</span></span>

<span data-ttu-id="4dc82-118">Em seguida, você pode usar uma expressão como `FILTER (Users, Users.objectId = myID)` para filtrar a tabela UserInfo pelo campo **objectId** do tipo de dados *GUID*.</span><span class="sxs-lookup"><span data-stu-id="4dc82-118">You can then use an expression such as `FILTER (Users, Users.objectId = myID)` to filter the UserInfo table by the **objectId** field of the *GUID* data type.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="4dc82-119">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="4dc82-119">Additional resources</span></span>

[<span data-ttu-id="4dc82-120">Funções de texto</span><span class="sxs-lookup"><span data-stu-id="4dc82-120">Text functions</span></span>](er-functions-category-text.md)
