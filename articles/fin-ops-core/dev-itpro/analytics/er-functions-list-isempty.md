---
title: Função de ER ISEMPTY
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) ISEMPTY é usada.
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
ms.openlocfilehash: 9c33e8b613bf5bf5bc17a42a7668d4cc4ee58e53
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5750427"
---
# <a name="isempty-er-function"></a><span data-ttu-id="45b21-103">Função de ER ISEMPTY</span><span class="sxs-lookup"><span data-stu-id="45b21-103">ISEMPTY ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="45b21-104">A função `ISEMPTY` retorna um valor *Booliano* de **TRUE** se a lista especificada não contiver registros.</span><span class="sxs-lookup"><span data-stu-id="45b21-104">The `ISEMPTY` function returns a *Boolean* value of **TRUE** if the specified list contains no records.</span></span> <span data-ttu-id="45b21-105">Caso contrário, ela retorna um valor *Booliano* de **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="45b21-105">Otherwise, it returns a *Boolean* value of **FALSE**.</span></span>

## <a name="syntax"></a><span data-ttu-id="45b21-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="45b21-106">Syntax</span></span>

```vb
ISEMPTY (list)
```

## <a name="arguments"></a><span data-ttu-id="45b21-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="45b21-107">Arguments</span></span>

<span data-ttu-id="45b21-108">`list`: *Lista de registros*</span><span class="sxs-lookup"><span data-stu-id="45b21-108">`list`: *Record list*</span></span>

<span data-ttu-id="45b21-109">O caminho válido de uma fonte de dados do tipo *Lista de registros*.</span><span class="sxs-lookup"><span data-stu-id="45b21-109">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="45b21-110">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="45b21-110">Return values</span></span>

<span data-ttu-id="45b21-111">*Booleano*</span><span class="sxs-lookup"><span data-stu-id="45b21-111">*Boolean*</span></span>

<span data-ttu-id="45b21-112">O valor *Booliano* resultante.</span><span class="sxs-lookup"><span data-stu-id="45b21-112">The resulting *Boolean* value.</span></span>

## <a name="example-1"></a><span data-ttu-id="45b21-113">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="45b21-113">Example 1</span></span>

<span data-ttu-id="45b21-114">Se você inserir a fonte de dados **DS** do tipo *Campo calculado* e ela contiver a expressão `SPLIT ("A|B|C", "|")`, a expressão `ISEMPTY(DS)` retornará **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="45b21-114">If you enter data source **DS** of the *Calculated field* type, and it contains the expression `SPLIT ("A|B|C", "|")`, the expression `ISEMPTY(DS)` returns **FALSE**.</span></span>

## <a name="example-2"></a><span data-ttu-id="45b21-115">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="45b21-115">Example 2</span></span>

<span data-ttu-id="45b21-116">A expressão `ISEMPTY (SPLIT ("",1))` retorna **TRUE**.</span><span class="sxs-lookup"><span data-stu-id="45b21-116">The expression `ISEMPTY (SPLIT ("",1))` returns **TRUE**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="45b21-117">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="45b21-117">Additional resources</span></span>

[<span data-ttu-id="45b21-118">Funções de listagem</span><span class="sxs-lookup"><span data-stu-id="45b21-118">List functions</span></span>](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]