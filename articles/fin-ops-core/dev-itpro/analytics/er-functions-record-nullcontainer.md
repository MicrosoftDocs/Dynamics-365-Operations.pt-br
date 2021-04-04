---
title: Função de ER NULLCONTAINER
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) NULLCONTAINER é usada.
author: NickSelin
manager: kfend
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
ms.openlocfilehash: d08a4a12d2b142744d3f35c6f1088ec25158c97c
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5563213"
---
# <a name="nullcontainer-er-function"></a><span data-ttu-id="92f8d-103">Função de ER NULLCONTAINER</span><span class="sxs-lookup"><span data-stu-id="92f8d-103">NULLCONTAINER ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="92f8d-104">A função `NULLCONTAINER` retorna um valor de *Contêiner (registro)* nulo que tem a mesma estrutura do registro ou da lista de registros especificada.</span><span class="sxs-lookup"><span data-stu-id="92f8d-104">The `NULLCONTAINER` function returns a null *Container (record)* value that has the same structure as the specified record list or record.</span></span>

## <a name="syntax"></a><span data-ttu-id="92f8d-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="92f8d-105">Syntax</span></span>

```vb
NULLCONTAINER (list)
```

## <a name="arguments"></a><span data-ttu-id="92f8d-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="92f8d-106">Arguments</span></span>

<span data-ttu-id="92f8d-107">`list`: *Lista de registros* ou *Contêiner (registro)*</span><span class="sxs-lookup"><span data-stu-id="92f8d-107">`list`: *Record list* or *Container (record)*</span></span>

<span data-ttu-id="92f8d-108">O caminho válido de uma fonte de dados do tipo *Lista de registros* ou *Contêiner (registro)*.</span><span class="sxs-lookup"><span data-stu-id="92f8d-108">The valid path of a data source of either the *Record list* or *Container (record)* type.</span></span>

## <a name="return-values"></a><span data-ttu-id="92f8d-109">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="92f8d-109">Return values</span></span>

<span data-ttu-id="92f8d-110">*Contêiner (registro)*</span><span class="sxs-lookup"><span data-stu-id="92f8d-110">*Container (record)*</span></span>

<span data-ttu-id="92f8d-111">O valor de registro resultante.</span><span class="sxs-lookup"><span data-stu-id="92f8d-111">The resulting record value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="92f8d-112">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="92f8d-112">Usage notes</span></span>

> [!NOTE] 
> <span data-ttu-id="92f8d-113">Esta função é obsoleta.</span><span class="sxs-lookup"><span data-stu-id="92f8d-113">This function is obsolete.</span></span> <span data-ttu-id="92f8d-114">Em vez dela, use a função `EMPTYRECORD`.</span><span class="sxs-lookup"><span data-stu-id="92f8d-114">Use the `EMPTYRECORD` function instead.</span></span> <span data-ttu-id="92f8d-115">Para obter mais informações, consulte [EMPTYRECORD](er-functions-record-emptyrecord.md).</span><span class="sxs-lookup"><span data-stu-id="92f8d-115">For more information, see [EMPTYRECORD](er-functions-record-emptyrecord.md).</span></span>

## <a name="example"></a><span data-ttu-id="92f8d-116">Exemplo</span><span class="sxs-lookup"><span data-stu-id="92f8d-116">Example</span></span>

<span data-ttu-id="92f8d-117">`NULLCONTAINER (SPLIT ("abc", 1))` retorna um novo registro vazio que tem a mesma estrutura da lista retornada pela função `SPLIT`.</span><span class="sxs-lookup"><span data-stu-id="92f8d-117">`NULLCONTAINER (SPLIT ("abc", 1))` returns a new empty record that has the same structure as the list that is returned by the `SPLIT` function.</span></span> <span data-ttu-id="92f8d-118">Para obter mais informações, consulte [SPLIT](er-functions-list-split.md).</span><span class="sxs-lookup"><span data-stu-id="92f8d-118">For more information, see [SPLIT](er-functions-list-split.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="92f8d-119">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="92f8d-119">Additional resources</span></span>

[<span data-ttu-id="92f8d-120">Funções de registro</span><span class="sxs-lookup"><span data-stu-id="92f8d-120">Record functions</span></span>](er-functions-category-record.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]