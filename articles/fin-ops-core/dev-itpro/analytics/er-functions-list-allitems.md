---
title: Função de ER ALLITEMS
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) ALLITEMS é usada.
author: NickSelin
manager: kfend
ms.date: 12/04/2019
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
ms.openlocfilehash: 47113d52e15d3d61f00b3c54229e286eb0f1a8d7
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/01/2020
ms.locfileid: "3745384"
---
# <a name="allitems-er-function"></a><span data-ttu-id="1f59c-103">Função de ER ALLITEMS</span><span class="sxs-lookup"><span data-stu-id="1f59c-103">ALLITEMS ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="1f59c-104">A função `ALLITEMS` é executada como uma seleção na memória e retorna um novo valor de *Lista de registros* simplificado como uma lista de registros que representa todos os itens correspondentes ao caminho especificado.</span><span class="sxs-lookup"><span data-stu-id="1f59c-104">The `ALLITEMS` function runs as an in-memory selection and returns a new flattened *Record list* value as a list of records that represents all items that match the specified path.</span></span>

## <a name="syntax"></a><span data-ttu-id="1f59c-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="1f59c-105">Syntax</span></span>

```vb
ALLITEMS (path)
```

## <a name="arguments"></a><span data-ttu-id="1f59c-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="1f59c-106">Arguments</span></span>

<span data-ttu-id="1f59c-107">`path`: *Lista de registros*</span><span class="sxs-lookup"><span data-stu-id="1f59c-107">`path`: *Record list*</span></span>

<span data-ttu-id="1f59c-108">O caminho válido de uma fonte de dados do tipo *Lista de registros*.</span><span class="sxs-lookup"><span data-stu-id="1f59c-108">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="1f59c-109">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="1f59c-109">Return values</span></span>

<span data-ttu-id="1f59c-110">*Lista de registros*</span><span class="sxs-lookup"><span data-stu-id="1f59c-110">*Record list*</span></span>

<span data-ttu-id="1f59c-111">A lista de registros resultante.</span><span class="sxs-lookup"><span data-stu-id="1f59c-111">The resulting list of records.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="1f59c-112">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="1f59c-112">Usage notes</span></span>

<span data-ttu-id="1f59c-113">O caminho deve ser definido como um caminho de fonte de dados válido de um elemento da fonte de dados do tipo *Lista de registros*.</span><span class="sxs-lookup"><span data-stu-id="1f59c-113">The path must be defined as a valid data source path of a data source element of the *Record list* data type.</span></span> <span data-ttu-id="1f59c-114">Os elementos de dados, como a cadeia de caracteres e a data do caminho, devem gerar um erro no construtor de expressões de relatório eletrônico (ER) no momento do design.</span><span class="sxs-lookup"><span data-stu-id="1f59c-114">Data elements such as the path string and date should raise an error in the Electronic reporting (ER) expression builder at design time.</span></span>

<span data-ttu-id="1f59c-115">Não é recomendável usar esta função para fontes de dados transacionais que possam conter um grande volume de dados.</span><span class="sxs-lookup"><span data-stu-id="1f59c-115">We don't recommend that you use this function for transactional data sources that might contain a large volume of data.</span></span> <span data-ttu-id="1f59c-116">Em vez dela, considere usar a função [ALLTEMSQUERY](er-functions-list-allitemsquery.md).</span><span class="sxs-lookup"><span data-stu-id="1f59c-116">Instead, consider using the [ALLTEMSQUERY](er-functions-list-allitemsquery.md) function.</span></span>

## <a name="example-1"></a><span data-ttu-id="1f59c-117">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="1f59c-117">Example 1</span></span>

<span data-ttu-id="1f59c-118">Se você inserir `SPLIT("abcdef" , 2)` como a fonte de dados **DS**, a expressão `COUNT( ALLITEMS (DS))` retornará **3**.</span><span class="sxs-lookup"><span data-stu-id="1f59c-118">If you enter `SPLIT("abcdef" , 2)` as data source **DS**, the expression `COUNT( ALLITEMS (DS))` returns **3**.</span></span>

## <a name="example-2"></a><span data-ttu-id="1f59c-119">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="1f59c-119">Example 2</span></span>

<span data-ttu-id="1f59c-120">Se você inserir **Forn.** como a fonte de dados do tipo *Lista de registros* que se refere à tabela do aplicativo VendTable, a expressão `ALLITEMS (Vend.'<Relations'.ContactPerson)` retornará uma lista simplificada de registros que tem a estrutura da tabela **ContactPerson** e contém todas as pessoas de contato que podem ser acessadas usando a relação **ContactPerson.ContactForParty == VendTable.Party**, e isso está disponível para todos os fornecedores da tabela de fornecedores referenciada.</span><span class="sxs-lookup"><span data-stu-id="1f59c-120">If you enter **Vend** as the data source of the *Record list* data type that refers to the VendTable application table, the expression `ALLITEMS (Vend.'<Relations'.ContactPerson)` returns a flattened list of records that has the **ContactPerson** table structure and contains all contact persons that can be accessed by using the **ContactPerson.ContactForParty == VendTable.Party** relation, and that is available for all vendors from the referenced vendor table.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="1f59c-121">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="1f59c-121">Additional resources</span></span>

[<span data-ttu-id="1f59c-122">Funções de listagem</span><span class="sxs-lookup"><span data-stu-id="1f59c-122">List functions</span></span>](er-functions-category-list.md)
