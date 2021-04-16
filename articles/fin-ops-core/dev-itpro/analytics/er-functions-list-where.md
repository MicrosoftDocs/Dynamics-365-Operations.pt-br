---
title: Função de ER WHERE
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) WHERE é usada.
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
ms.openlocfilehash: bdf5c658fda83399c7bcffeaaf07005164c53f8a
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5745488"
---
# <a name="where-er-function"></a><span data-ttu-id="8166d-103">Função de ER WHERE</span><span class="sxs-lookup"><span data-stu-id="8166d-103">WHERE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="8166d-104">A função `WHERE` retorna a lista especificada como um valor de *Lista de registros* após ser filtrada de acordo com a condição especificada.</span><span class="sxs-lookup"><span data-stu-id="8166d-104">The `WHERE` function returns the specified list as a *Record list* value after it has been filtered according to the specified condition.</span></span>

## <a name="syntax"></a><span data-ttu-id="8166d-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="8166d-105">Syntax</span></span>

```vb
WHERE (list, condition)
```

## <a name="arguments"></a><span data-ttu-id="8166d-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="8166d-106">Arguments</span></span>

<span data-ttu-id="8166d-107">`list`: *Lista de registros*</span><span class="sxs-lookup"><span data-stu-id="8166d-107">`list`: *Record list*</span></span>

<span data-ttu-id="8166d-108">O caminho válido de uma fonte de dados do tipo *Lista de registros*.</span><span class="sxs-lookup"><span data-stu-id="8166d-108">The valid path of a data source of the *Record list* data type.</span></span>

<span data-ttu-id="8166d-109">`condition`: *Booliano*</span><span class="sxs-lookup"><span data-stu-id="8166d-109">`condition`: *Boolean*</span></span>

<span data-ttu-id="8166d-110">Uma expressão condicional válida que é usada para filtrar os registros da lista especificada.</span><span class="sxs-lookup"><span data-stu-id="8166d-110">A valid conditional expression that is used to filter records of the specified list.</span></span>

## <a name="return-values"></a><span data-ttu-id="8166d-111">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="8166d-111">Return values</span></span>

<span data-ttu-id="8166d-112">*Lista de registros*</span><span class="sxs-lookup"><span data-stu-id="8166d-112">*Record list*</span></span>

<span data-ttu-id="8166d-113">A lista de registros resultante.</span><span class="sxs-lookup"><span data-stu-id="8166d-113">The resulting list of records.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="8166d-114">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="8166d-114">Usage notes</span></span>

<span data-ttu-id="8166d-115">Esta função difere da função [FILTER](er-functions-list-filter.md) porque a condição especificada é aplicada a todas as fontes de dados de relatório eletrônico (ER) do tipo *Lista de registros* presentes na memória.</span><span class="sxs-lookup"><span data-stu-id="8166d-115">This function differs from the [FILTER](er-functions-list-filter.md) function, because the specified condition is applied to any Electronic reporting (ER) data source of the *Record list* type that is present in memory.</span></span>

<span data-ttu-id="8166d-116">Se os argumentos configurados para esta função (`list` e `condition`) permitirem que essa solicitação seja traduzida para a chamada SQL direta, uma mensagem de aviso será gerada no momento do design.</span><span class="sxs-lookup"><span data-stu-id="8166d-116">If the arguments that are configured for this function (`list` and `condition`) allow this request to be translated to the direct SQL call, a warning message is thrown at design time.</span></span> <span data-ttu-id="8166d-117">Essa mensagem informa o usuário que o desempenho pode ser melhorado se a função [FILTER](er-functions-list-filter.md) for usada em vez de `WHERE`.</span><span class="sxs-lookup"><span data-stu-id="8166d-117">This message informs the user that performance might be improved if the [FILTER](er-functions-list-filter.md) function is used instead of `WHERE`.</span></span>

## <a name="example-1"></a><span data-ttu-id="8166d-118">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="8166d-118">Example 1</span></span>

<span data-ttu-id="8166d-119">Se **Fornecedor** estiver configurado como uma fonte de dados de ER que se refere à tabela VendTable, a expressão `WHERE (Vendors, Vendors.VendGroup = "40")` retornará uma lista apenas com os fornecedores que pertencem ao grupo de fornecedores 40.</span><span class="sxs-lookup"><span data-stu-id="8166d-119">If **Vendor** is configured as an ER data source that refers to the VendTable table, the expression `WHERE (Vendors, Vendors.VendGroup = "40")` returns a list of only vendors that belong to vendor group 40.</span></span>

## <a name="example-2"></a><span data-ttu-id="8166d-120">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="8166d-120">Example 2</span></span>

<span data-ttu-id="8166d-121">Se você inserir a fonte de dados **DS** do tipo *Campo calculado* e ela contiver a expressão `SPLIT ("A|B|C", "|")`, a expressão `WHERE( DS, DS.Value = "B")` retornará uma lista com apenas um registro que contém o texto **"B"** no campo **Valor**.</span><span class="sxs-lookup"><span data-stu-id="8166d-121">If you enter data source **DS** of the *Calculated field* type, and it contains the expression `SPLIT ("A|B|C", "|")`, the expression `WHERE( DS, DS.Value = "B")` returns a list of only one record that contains the text **"B"** in the **Value** field.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="8166d-122">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="8166d-122">Additional resources</span></span>

[<span data-ttu-id="8166d-123">Funções de listagem</span><span class="sxs-lookup"><span data-stu-id="8166d-123">List functions</span></span>](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]