---
title: Função de ER REVERSE
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) REVERSE é usada.
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
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 895d5f13f065b2188f245d081fa69e7e63555dde
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4686431"
---
# <a name="reverse-er-function"></a><span data-ttu-id="5ee95-103">Função de ER REVERSE</span><span class="sxs-lookup"><span data-stu-id="5ee95-103">REVERSE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5ee95-104">A função `REVERSE` retorna a lista especificada como um valor de *Lista de registros* na ordem de classificação inversa.</span><span class="sxs-lookup"><span data-stu-id="5ee95-104">The `REVERSE` function returns the specified list as a *Record list* value in reversed sort order.</span></span>

## <a name="syntax"></a><span data-ttu-id="5ee95-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="5ee95-105">Syntax</span></span>

```vb
REVERSE (list)
```

## <a name="arguments"></a><span data-ttu-id="5ee95-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="5ee95-106">Arguments</span></span>

<span data-ttu-id="5ee95-107">`list`: *Lista de registros*</span><span class="sxs-lookup"><span data-stu-id="5ee95-107">`list`: *Record list*</span></span>

<span data-ttu-id="5ee95-108">O caminho válido de uma fonte de dados do tipo *Lista de registros*.</span><span class="sxs-lookup"><span data-stu-id="5ee95-108">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="5ee95-109">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="5ee95-109">Return values</span></span>

<span data-ttu-id="5ee95-110">*Lista de registros*</span><span class="sxs-lookup"><span data-stu-id="5ee95-110">*Record list*</span></span>

<span data-ttu-id="5ee95-111">A lista de registros resultante.</span><span class="sxs-lookup"><span data-stu-id="5ee95-111">The resulting list of records.</span></span>

## <a name="example-1"></a><span data-ttu-id="5ee95-112">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="5ee95-112">Example 1</span></span>

<span data-ttu-id="5ee95-113">Se você inserir a fonte de dados **DS** do tipo *Campo calculado* e ela contiver a expressão `SPLIT ("C|B|A", "|")`, a expressão `FIRST( REVERSE( ORDERBY( DS, DS. Value))).Value` retornará o valor de texto **"C"**.</span><span class="sxs-lookup"><span data-stu-id="5ee95-113">If you enter data source **DS** of the *Calculated field* type, and it contains the expression `SPLIT ("C|B|A", "|")`, the expression `FIRST( REVERSE( ORDERBY( DS, DS. Value))).Value` returns the text value **"C"**.</span></span>

## <a name="example-2"></a><span data-ttu-id="5ee95-114">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="5ee95-114">Example 2</span></span>

<span data-ttu-id="5ee95-115">Se **Fornecedor** estiver configurado como uma fonte de dados de relatório eletrônico (ER) que se refere à tabela VendTable, a expressão `REVERSE (ORDERBY (Vendors, Vendors.'name()'))` retornará uma lista de fornecedores que é classificada por nome em ordem decrescente.</span><span class="sxs-lookup"><span data-stu-id="5ee95-115">If **Vendor** is configured as an Electronic reporting (ER) data source that refers to the VendTable table, the expression `REVERSE (ORDERBY (Vendors, Vendors.'name()'))` returns a list of vendors that is sorted by name in descending order.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="5ee95-116">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="5ee95-116">Additional resources</span></span>

[<span data-ttu-id="5ee95-117">Funções de listagem</span><span class="sxs-lookup"><span data-stu-id="5ee95-117">List functions</span></span>](er-functions-category-list.md)
