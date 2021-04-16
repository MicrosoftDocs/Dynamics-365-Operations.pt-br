---
title: Função de ER FILTER
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) FILTER é usada.
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
ms.openlocfilehash: aa8c0b4601db625d442dd545151968f38bd58cf1
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746594"
---
# <a name="filter-er-function"></a><span data-ttu-id="04a64-103">Função de ER FILTER</span><span class="sxs-lookup"><span data-stu-id="04a64-103">FILTER ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="04a64-104">A função `FILTER` retorna a lista especificada como um valor de *Lista de registros* após a consulta ser alterada, de forma que ela filtre para a condição especificada.</span><span class="sxs-lookup"><span data-stu-id="04a64-104">The `FILTER` function returns the specified list as a *Record list* value after the query has been changed so that it filters for the specified condition.</span></span>

## <a name="syntax"></a><span data-ttu-id="04a64-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="04a64-105">Syntax</span></span>

```vb
FILTER (list, condition)
```

## <a name="arguments"></a><span data-ttu-id="04a64-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="04a64-106">Arguments</span></span>

<span data-ttu-id="04a64-107">`list`: *Lista de registros*</span><span class="sxs-lookup"><span data-stu-id="04a64-107">`list`: *Record list*</span></span>

<span data-ttu-id="04a64-108">O caminho válido de uma fonte de dados do tipo *Lista de registros*.</span><span class="sxs-lookup"><span data-stu-id="04a64-108">The valid path of a data source of the *Record list* data type.</span></span>

<span data-ttu-id="04a64-109">`condition`: *Booliano*</span><span class="sxs-lookup"><span data-stu-id="04a64-109">`condition`: *Boolean*</span></span>

<span data-ttu-id="04a64-110">Uma expressão condicional válida que é usada para filtrar os registros da lista especificada.</span><span class="sxs-lookup"><span data-stu-id="04a64-110">A valid conditional expression that is used to filter records of the specified list.</span></span>

## <a name="return-values"></a><span data-ttu-id="04a64-111">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="04a64-111">Return values</span></span>

<span data-ttu-id="04a64-112">*Lista de registros*</span><span class="sxs-lookup"><span data-stu-id="04a64-112">*Record list*</span></span>

<span data-ttu-id="04a64-113">A lista de registros resultante.</span><span class="sxs-lookup"><span data-stu-id="04a64-113">The resulting list of records.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="04a64-114">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="04a64-114">Usage notes</span></span>

<span data-ttu-id="04a64-115">Esta função difere da função [WHERE](er-functions-list-where.md) porque a condição especificada é aplicada a todas as fontes de dados de relatório eletrônico (ER) do tipo *Registros de tabela* no nível do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="04a64-115">This function differs from the [WHERE](er-functions-list-where.md) function, because the specified condition is applied to any Electronic reporting (ER) data source of the *Table records* type at the database level.</span></span> <span data-ttu-id="04a64-116">A lista e a condição podem ser definidas usando tabelas e relações.</span><span class="sxs-lookup"><span data-stu-id="04a64-116">The list and condition can be defined by using tables and relations.</span></span>

<span data-ttu-id="04a64-117">Se um ou ambos os argumentos configurados para esta função (`list` e `condition`) não permitirem que essa solicitação seja traduzida para a chamada SQL direta, uma exceção será gerada no momento do design.</span><span class="sxs-lookup"><span data-stu-id="04a64-117">If one or both arguments that are configured for this function (`list` and `condition`) don't allow this request to be translated to the direct SQL call, an exception is thrown at design time.</span></span> <span data-ttu-id="04a64-118">Essa exceção informa o usuário que `list` ou `condition` não pode ser usado para consultar o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="04a64-118">This exception informs the user that either `list` or `condition` can't be used to query the database.</span></span>

## <a name="example-1"></a><span data-ttu-id="04a64-119">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="04a64-119">Example 1</span></span>

<span data-ttu-id="04a64-120">Se **Fornecedor** estiver configurado como uma fonte de dados de ER que se refere à tabela VendTable, a expressão `FILTER (Vendors, Vendors.VendGroup = "40")` retornará uma lista apenas com os fornecedores que pertencem ao grupo de fornecedores 40.</span><span class="sxs-lookup"><span data-stu-id="04a64-120">If **Vendor** is configured as an ER data source that refers to the VendTable table, the expression `FILTER (Vendors, Vendors.VendGroup = "40")` returns a list of only vendors that belong to vendor group 40.</span></span>

## <a name="example-2"></a><span data-ttu-id="04a64-121">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="04a64-121">Example 2</span></span>

<span data-ttu-id="04a64-122">Se **Fornecedor** estiver configurado como uma fonte de dados de ER que se refere à tabela VendTable e se **parmVendorBankGroup** estiver configurado como uma fonte de dados de ER que retorna um valor do tipo *Cadeia de caracteres*, a expressão `FILTER ( Vendor.'<Relations'.VendBankAccount, Vendor.'<Relations'.VendBankAccount.BankGroupID = parmVendorBankGroup)` retornará uma lista apenas com as contas de fornecedores que pertencem a um grupo bancário específico.</span><span class="sxs-lookup"><span data-stu-id="04a64-122">If **Vendor** is configured as an ER data source that refers to the VendTable table, and if **parmVendorBankGroup** is configured as an ER data source that returns a value of the *String* data type, the expression `FILTER ( Vendor.'<Relations'.VendBankAccount, Vendor.'<Relations'.VendBankAccount.BankGroupID = parmVendorBankGroup)` returns a list of only vendor accounts that belong to a specific bank group.</span></span>

## <a name="example-3"></a><span data-ttu-id="04a64-123">Exemplo 3</span><span class="sxs-lookup"><span data-stu-id="04a64-123">Example 3</span></span>

<span data-ttu-id="04a64-124">Você insere a fonte de dados **DS** do tipo *Campo calculado* e ela contém a expressão `SPLIT ("A,B,C", ",")`.</span><span class="sxs-lookup"><span data-stu-id="04a64-124">You enter data source **DS** of the *Calculated field* type, and it contains the expression `SPLIT ("A,B,C", ",")`.</span></span> <span data-ttu-id="04a64-125">Em seguida, você insere outra expressão, `FILTER( DS, DS.Value = "B")`.</span><span class="sxs-lookup"><span data-stu-id="04a64-125">You then enter another expression, `FILTER( DS, DS.Value = "B")`.</span></span> <span data-ttu-id="04a64-126">Ao tentar salvar essa expressão no designer de fórmulas de ER, a seguinte exceção é gerada: "Erro de validação: A expressão de lista da função FILTER não é consultável".</span><span class="sxs-lookup"><span data-stu-id="04a64-126">When you try to save this expression in the ER formula designer, the following exception is thrown: "Validation error: The list expression of FILTER function is not queryable."</span></span>

## <a name="additional-resources"></a><span data-ttu-id="04a64-127">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="04a64-127">Additional resources</span></span>

[<span data-ttu-id="04a64-128">Funções de listagem</span><span class="sxs-lookup"><span data-stu-id="04a64-128">List functions</span></span>](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]