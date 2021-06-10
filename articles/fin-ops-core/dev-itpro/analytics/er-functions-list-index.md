---
title: Função de ER INDEX
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) INDEX é usada.
author: NickSelin
ms.date: 05/20/2021
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
ms.openlocfilehash: 5a0fdb8958670efe8e2a37cee183bf836fa6c7e8
ms.sourcegitcommit: 047b0503868cc7d7b21868e24405d76af35db747
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/21/2021
ms.locfileid: "6087742"
---
# <a name="index-er-function"></a><span data-ttu-id="1c398-103">Função de ER INDEX</span><span class="sxs-lookup"><span data-stu-id="1c398-103">INDEX ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="1c398-104">A função `INDEX` retorna um valor de *Contêiner (registro)* que é selecionado usando o índice numérico especificado na lista especificada.</span><span class="sxs-lookup"><span data-stu-id="1c398-104">The `INDEX` function returns a *Container (record)* value that is selected by using the specified numeric index in the specified list.</span></span> <span data-ttu-id="1c398-105">Se o índice estiver fora do intervalo dos registros na lista especificada, uma exceção será gerada.</span><span class="sxs-lookup"><span data-stu-id="1c398-105">If the index is out of range for the records in the specified list, an exception is thrown.</span></span>

## <a name="syntax"></a><span data-ttu-id="1c398-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="1c398-106">Syntax</span></span>

```vb
INDEX (list, index)
```

## <a name="arguments"></a><span data-ttu-id="1c398-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="1c398-107">Arguments</span></span>

<span data-ttu-id="1c398-108">`list`: *Lista de registros*</span><span class="sxs-lookup"><span data-stu-id="1c398-108">`list`: *Record list*</span></span>

<span data-ttu-id="1c398-109">O caminho válido de uma fonte de dados do tipo *Lista de registros*.</span><span class="sxs-lookup"><span data-stu-id="1c398-109">The valid path of a data source of the *Record list* data type.</span></span>

<span data-ttu-id="1c398-110">`index`: *Inteiro*</span><span class="sxs-lookup"><span data-stu-id="1c398-110">`index`: *Integer*</span></span>

<span data-ttu-id="1c398-111">Um índice numérico que indica a posição do registro desejado na lista especificada.</span><span class="sxs-lookup"><span data-stu-id="1c398-111">A numeric index that indicates the position of the desired record in the specified list.</span></span>

> [!NOTE]
> <span data-ttu-id="1c398-112">Como o número de uma base é usado para essa função, especifique o valor **1** para retornar o primeiro registro da lista especificada.</span><span class="sxs-lookup"><span data-stu-id="1c398-112">Because one-based numbering is used for this function, specify the value **1** to return the first record of the specified list.</span></span>

## <a name="return-values"></a><span data-ttu-id="1c398-113">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="1c398-113">Return values</span></span>

<span data-ttu-id="1c398-114">*Contêiner (registro)*</span><span class="sxs-lookup"><span data-stu-id="1c398-114">*Container (record)*</span></span>

<span data-ttu-id="1c398-115">O valor de registro resultante.</span><span class="sxs-lookup"><span data-stu-id="1c398-115">The resulting record value.</span></span>

## <a name="example-1"></a><span data-ttu-id="1c398-116">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="1c398-116">Example 1</span></span>

<span data-ttu-id="1c398-117">Se você inserir a fonte de dados **DS** do tipo *Campo calculado* e ela contiver a expressão `SPLIT ("A|B|C", "|")`, a expressão `DS.Value` retornará o valor de texto **"B"** para o segundo registro dessa lista de registros.</span><span class="sxs-lookup"><span data-stu-id="1c398-117">If you enter data source **DS** of the *Calculated field* type, and it contains the expression `SPLIT ("A|B|C", "|")`, the expression `DS.Value` returns the text value **"B"** for the second record of this record list.</span></span> <span data-ttu-id="1c398-118">A expressão `INDEX (SPLIT ("A|B|C", "|"), 2).Value` também retorna o valor de texto **"B"**.</span><span class="sxs-lookup"><span data-stu-id="1c398-118">The expression `INDEX (SPLIT ("A|B|C", "|"), 2).Value` also returns the text value **"B"**.</span></span>

## <a name="example-2"></a><span data-ttu-id="1c398-119">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="1c398-119">Example 2</span></span>

<span data-ttu-id="1c398-120">Se você inserir a fonte de dados **DS** do tipo *Campo calculado* e ela contiver a expressão `SPLIT ("A|B|C", "|")`, a expressão `INDEX (SPLIT ("A|B|C", "|"), 4).Value` gerará uma exceção no tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="1c398-120">If you enter data source **DS** of the *Calculated field* type, and it contains the expression `SPLIT ("A|B|C", "|")`, the expression `INDEX (SPLIT ("A|B|C", "|"), 4).Value` throws an exception at runtime.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="1c398-121">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="1c398-121">Additional resources</span></span>

[<span data-ttu-id="1c398-122">Funções de listagem</span><span class="sxs-lookup"><span data-stu-id="1c398-122">List functions</span></span>](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
