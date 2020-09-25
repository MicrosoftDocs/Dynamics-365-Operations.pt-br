---
title: Função de ER NULLCONTAINER
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) NULLCONTAINER é usada.
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
ms.openlocfilehash: dac6283ec35d3d03f586ca157048bd3ecc4bfa8a
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/01/2020
ms.locfileid: "3743918"
---
# <a name="nullcontainer-er-function"></a><span data-ttu-id="ef35f-103">Função de ER NULLCONTAINER</span><span class="sxs-lookup"><span data-stu-id="ef35f-103">NULLCONTAINER ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ef35f-104">A função `NULLCONTAINER` retorna um valor de *Contêiner (registro)* nulo que tem a mesma estrutura do registro ou da lista de registros especificada.</span><span class="sxs-lookup"><span data-stu-id="ef35f-104">The `NULLCONTAINER` function returns a null *Container (record)* value that has the same structure as the specified record list or record.</span></span>

## <a name="syntax"></a><span data-ttu-id="ef35f-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="ef35f-105">Syntax</span></span>

```vb
NULLCONTAINER (list)
```

## <a name="arguments"></a><span data-ttu-id="ef35f-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="ef35f-106">Arguments</span></span>

<span data-ttu-id="ef35f-107">`list`: *Lista de registros* ou *Contêiner (registro)*</span><span class="sxs-lookup"><span data-stu-id="ef35f-107">`list`: *Record list* or *Container (record)*</span></span>

<span data-ttu-id="ef35f-108">O caminho válido de uma fonte de dados do tipo *Lista de registros* ou *Contêiner (registro)*.</span><span class="sxs-lookup"><span data-stu-id="ef35f-108">The valid path of a data source of either the *Record list* or *Container (record)* type.</span></span>

## <a name="return-values"></a><span data-ttu-id="ef35f-109">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="ef35f-109">Return values</span></span>

<span data-ttu-id="ef35f-110">*Contêiner (registro)*</span><span class="sxs-lookup"><span data-stu-id="ef35f-110">*Container (record)*</span></span>

<span data-ttu-id="ef35f-111">O valor de registro resultante.</span><span class="sxs-lookup"><span data-stu-id="ef35f-111">The resulting record value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="ef35f-112">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="ef35f-112">Usage notes</span></span>

> [!NOTE] 
> <span data-ttu-id="ef35f-113">Esta função é obsoleta.</span><span class="sxs-lookup"><span data-stu-id="ef35f-113">This function is obsolete.</span></span> <span data-ttu-id="ef35f-114">Em vez dela, use a função `EMPTYRECORD`.</span><span class="sxs-lookup"><span data-stu-id="ef35f-114">Use the `EMPTYRECORD` function instead.</span></span> <span data-ttu-id="ef35f-115">Para obter mais informações, consulte [EMPTYRECORD](er-functions-record-emptyrecord.md).</span><span class="sxs-lookup"><span data-stu-id="ef35f-115">For more information, see [EMPTYRECORD](er-functions-record-emptyrecord.md).</span></span>

## <a name="example"></a><span data-ttu-id="ef35f-116">Exemplo</span><span class="sxs-lookup"><span data-stu-id="ef35f-116">Example</span></span>

<span data-ttu-id="ef35f-117">`NULLCONTAINER (SPLIT ("abc", 1))` retorna um novo registro vazio que tem a mesma estrutura da lista retornada pela função `SPLIT`.</span><span class="sxs-lookup"><span data-stu-id="ef35f-117">`NULLCONTAINER (SPLIT ("abc", 1))` returns a new empty record that has the same structure as the list that is returned by the `SPLIT` function.</span></span> <span data-ttu-id="ef35f-118">Para obter mais informações, consulte [SPLIT](er-functions-list-split.md).</span><span class="sxs-lookup"><span data-stu-id="ef35f-118">For more information, see [SPLIT](er-functions-list-split.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ef35f-119">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="ef35f-119">Additional resources</span></span>

[<span data-ttu-id="ef35f-120">Funções de registro</span><span class="sxs-lookup"><span data-stu-id="ef35f-120">Record functions</span></span>](er-functions-category-record.md)
