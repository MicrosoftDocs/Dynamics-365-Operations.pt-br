---
title: Função de ER JSONVALUE
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) JSONVALUE é usada.
author: NickSelin
manager: kfend
ms.date: 12/11/2019
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
ms.openlocfilehash: 75f20632074cb4dead98991fd6522ab9b20b9965
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041139"
---
# <span data-ttu-id="973b7-103"><a name="JSONVALUE">Função de ER JSONVALUE</a></span><span class="sxs-lookup"><span data-stu-id="973b7-103"><a name="JSONVALUE">JSONVALUE ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="973b7-104">A função `JSONVALUE` analisa os dados no formato JSON (JavaScript Object Notation) que são acessados no caminho especificado e extrai um valor escalar que tem a ID especificada.</span><span class="sxs-lookup"><span data-stu-id="973b7-104">The `JSONVALUE` function parses data in JavaScript Object Notation (JSON) format that is accessed at the specified path, and it extracts a scalar value that has the specified ID.</span></span> <span data-ttu-id="973b7-105">Em seguida, ela retorna o valor escalar extraído como um valor de *Cadeia de caracteres*.</span><span class="sxs-lookup"><span data-stu-id="973b7-105">It then returns the extracted scalar value as a *String* value.</span></span>

## <a name="syntax"></a><span data-ttu-id="973b7-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="973b7-106">Syntax</span></span>

```vb
JSONVALUE (input, path)
```

## <a name="arguments"></a><span data-ttu-id="973b7-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="973b7-107">Arguments</span></span>

<span data-ttu-id="973b7-108">`input`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="973b7-108">`input`: *String*</span></span>

<span data-ttu-id="973b7-109">O caminho válido de uma fonte de dados do tipo *Cadeia de caracteres* que contém dados JSON.</span><span class="sxs-lookup"><span data-stu-id="973b7-109">The valid path of a data source of the *String* type that contains JSON data.</span></span>

<span data-ttu-id="973b7-110">`path`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="973b7-110">`path`: *String*</span></span>

<span data-ttu-id="973b7-111">O identificador de um valor escalar de dados JSON.</span><span class="sxs-lookup"><span data-stu-id="973b7-111">The identifier of a scalar value of JSON data.</span></span>

## <a name="return-values"></a><span data-ttu-id="973b7-112">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="973b7-112">Return values</span></span>

<span data-ttu-id="973b7-113">*Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="973b7-113">*String*</span></span>

<span data-ttu-id="973b7-114">O valor de texto resultante.</span><span class="sxs-lookup"><span data-stu-id="973b7-114">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="973b7-115">Exemplo</span><span class="sxs-lookup"><span data-stu-id="973b7-115">Example</span></span>

<span data-ttu-id="973b7-116">A fonte de dados **JsonField** contém os seguintes dados no formato JSON: **{"BuildNumber":"7.3.1234.1", "KeyThumbprint":"7366E"}**.</span><span class="sxs-lookup"><span data-stu-id="973b7-116">The **JsonField** data source contains the following data in JSON format: **{"BuildNumber":"7.3.1234.1", "KeyThumbprint":"7366E"}**.</span></span> <span data-ttu-id="973b7-117">Nesse caso, a expressão `JSONVALUE (JsonField, "BuildNumber")` retorna o seguinte valor do tipo de dados *Cadeia de caracteres*: **"7.3.1234.1"**.</span><span class="sxs-lookup"><span data-stu-id="973b7-117">In this case, the expression `JSONVALUE (JsonField, "BuildNumber")` returns the following value of the *String* data type: **"7.3.1234.1"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="973b7-118">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="973b7-118">Additional resources</span></span>

[<span data-ttu-id="973b7-119">Funções de texto</span><span class="sxs-lookup"><span data-stu-id="973b7-119">Text functions</span></span>](er-functions-category-text.md)
