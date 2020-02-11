---
title: Função de ER ENUMERATE
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) ENUMERATE é usada.
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
ms.openlocfilehash: f0a1c83ee869810e816b6d32ea890d172d2910e5
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916214"
---
# <span data-ttu-id="1b063-103"><a name="ENUMERATE">Função de ER ENUMERATE</a></span><span class="sxs-lookup"><span data-stu-id="1b063-103"><a name="ENUMERATE">ENUMERATE ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="1b063-104">A função `ENUMERATE` retorna um novo valor de *Lista de registros* que consiste em registros enumerados da lista especificada.</span><span class="sxs-lookup"><span data-stu-id="1b063-104">The `ENUMERATE` function returns a new *Record list* value that consists of enumerated records of the specified list.</span></span>

## <a name="syntax"></a><span data-ttu-id="1b063-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="1b063-105">Syntax</span></span>

```
ENUMERATE (list)
```

## <a name="arguments"></a><span data-ttu-id="1b063-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="1b063-106">Arguments</span></span>

<span data-ttu-id="1b063-107">`list`: *Lista de registros*</span><span class="sxs-lookup"><span data-stu-id="1b063-107">`list`: *Record list*</span></span>

<span data-ttu-id="1b063-108">O caminho válido de uma fonte de dados do tipo *Lista de registros*.</span><span class="sxs-lookup"><span data-stu-id="1b063-108">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="1b063-109">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="1b063-109">Return values</span></span>

<span data-ttu-id="1b063-110">*Lista de registros*</span><span class="sxs-lookup"><span data-stu-id="1b063-110">*Record list*</span></span>

<span data-ttu-id="1b063-111">A lista de registros resultante.</span><span class="sxs-lookup"><span data-stu-id="1b063-111">The resulting list of records.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="1b063-112">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="1b063-112">Usage notes</span></span>

<span data-ttu-id="1b063-113">A lista de registros enumerados que é retornada expõe os seguintes elementos adicionais:</span><span class="sxs-lookup"><span data-stu-id="1b063-113">The list of enumerated records that is returned exposes the following additional elements:</span></span>

- <span data-ttu-id="1b063-114">O registro de campos (componente **Valor**)</span><span class="sxs-lookup"><span data-stu-id="1b063-114">The record of fields (**Value** component)</span></span>
- <span data-ttu-id="1b063-115">O índice do registro atual (componente **Número**)</span><span class="sxs-lookup"><span data-stu-id="1b063-115">The current record index (**Number** component)</span></span>

## <a name="example"></a><span data-ttu-id="1b063-116">Exemplo</span><span class="sxs-lookup"><span data-stu-id="1b063-116">Example</span></span>

<span data-ttu-id="1b063-117">Na ilustração a seguir, uma fonte de dados **Enumerada** é criada como uma lista enumerada de registros do fornecedor da fonte de dados **Fornecedores** que se refere à tabela VendTable.</span><span class="sxs-lookup"><span data-stu-id="1b063-117">In the following illustration, an **Enumerated** data source is created as an enumerated list of vendor records from the **Vendors** data source that refers to the VendTable table.</span></span>

<a href="./media/picture-enumerate-datasource.jpg"><img src="./media/picture-enumerate-datasource.jpg" alt="Enumerated data source" class="alignnone wp-image-290711 size-full" width="387" height="136" /></a>

<span data-ttu-id="1b063-118">A ilustração a seguir mostra o formato de relatório eletrônico (ER).</span><span class="sxs-lookup"><span data-stu-id="1b063-118">The following illustration shows the Electronic reporting (ER) format.</span></span> <span data-ttu-id="1b063-119">Nesse formato, as associações são criadas para gerar saída no formato XML.</span><span class="sxs-lookup"><span data-stu-id="1b063-119">In this format, data bindings are created to generate output in XML format.</span></span> <span data-ttu-id="1b063-120">Esta saída apresenta fornecedores individuais como nós enumerados.</span><span class="sxs-lookup"><span data-stu-id="1b063-120">This output presents individual vendors as enumerated nodes.</span></span>

<a href="./media/picture-enumerate-format.jpg"><img src="./media/picture-enumerate-format.jpg" alt="Format that has data bindings" class="alignnone wp-image-290721 size-full" width="414" height="138" /></a>

<span data-ttu-id="1b063-121">A ilustração a seguir mostra o formato o resultado quando o formato criado é executado.</span><span class="sxs-lookup"><span data-stu-id="1b063-121">The following illustration shows the result when the designed format is run.</span></span>

<a href="./media/picture-enumerate-result.jpg"><img src="./media/picture-enumerate-result.jpg" alt="Result of running the format" class="alignnone wp-image-290731 size-full" width="567" height="176" /></a>

## <a name="additional-resources"></a><span data-ttu-id="1b063-122">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="1b063-122">Additional resources</span></span>

[<span data-ttu-id="1b063-123">Funções de listagem</span><span class="sxs-lookup"><span data-stu-id="1b063-123">List functions</span></span>](er-functions-category-list.md)