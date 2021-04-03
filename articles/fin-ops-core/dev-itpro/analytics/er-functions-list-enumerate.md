---
title: Função de ER ENUMERATE
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) ENUMERATE é usada.
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
ms.openlocfilehash: 0827fe33a548970c7673ac2ab830bb22d367c8cc
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5567859"
---
# <a name="enumerate-er-function"></a><span data-ttu-id="ea9a1-103">Função de ER ENUMERATE</span><span class="sxs-lookup"><span data-stu-id="ea9a1-103">ENUMERATE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ea9a1-104">A função `ENUMERATE` retorna um novo valor de *Lista de registros* que consiste em registros enumerados da lista especificada.</span><span class="sxs-lookup"><span data-stu-id="ea9a1-104">The `ENUMERATE` function returns a new *Record list* value that consists of enumerated records of the specified list.</span></span>

## <a name="syntax"></a><span data-ttu-id="ea9a1-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="ea9a1-105">Syntax</span></span>

```vb
ENUMERATE (list)
```

## <a name="arguments"></a><span data-ttu-id="ea9a1-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="ea9a1-106">Arguments</span></span>

<span data-ttu-id="ea9a1-107">`list`: *Lista de registros*</span><span class="sxs-lookup"><span data-stu-id="ea9a1-107">`list`: *Record list*</span></span>

<span data-ttu-id="ea9a1-108">O caminho válido de uma fonte de dados do tipo *Lista de registros*.</span><span class="sxs-lookup"><span data-stu-id="ea9a1-108">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="ea9a1-109">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="ea9a1-109">Return values</span></span>

<span data-ttu-id="ea9a1-110">*Lista de registros*</span><span class="sxs-lookup"><span data-stu-id="ea9a1-110">*Record list*</span></span>

<span data-ttu-id="ea9a1-111">A lista de registros resultante.</span><span class="sxs-lookup"><span data-stu-id="ea9a1-111">The resulting list of records.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="ea9a1-112">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="ea9a1-112">Usage notes</span></span>

<span data-ttu-id="ea9a1-113">A lista de registros enumerados que é retornada expõe os seguintes elementos adicionais:</span><span class="sxs-lookup"><span data-stu-id="ea9a1-113">The list of enumerated records that is returned exposes the following additional elements:</span></span>

- <span data-ttu-id="ea9a1-114">O registro de campos (componente **Valor**)</span><span class="sxs-lookup"><span data-stu-id="ea9a1-114">The record of fields (**Value** component)</span></span>
- <span data-ttu-id="ea9a1-115">O índice do registro atual (componente **Número**)</span><span class="sxs-lookup"><span data-stu-id="ea9a1-115">The current record index (**Number** component)</span></span>

## <a name="example"></a><span data-ttu-id="ea9a1-116">Exemplo</span><span class="sxs-lookup"><span data-stu-id="ea9a1-116">Example</span></span>

<span data-ttu-id="ea9a1-117">Na ilustração a seguir, uma fonte de dados **Enumerada** é criada como uma lista enumerada de registros do fornecedor da fonte de dados **Fornecedores** que se refere à tabela VendTable.</span><span class="sxs-lookup"><span data-stu-id="ea9a1-117">In the following illustration, an **Enumerated** data source is created as an enumerated list of vendor records from the **Vendors** data source that refers to the VendTable table.</span></span>

<a href="./media/picture-enumerate-datasource.jpg"><img src="./media/picture-enumerate-datasource.jpg" alt="Enumerated data source" class="alignnone wp-image-290711 size-full" width="387" height="136" /></a>

<span data-ttu-id="ea9a1-118">A ilustração a seguir mostra o formato de relatório eletrônico (ER).</span><span class="sxs-lookup"><span data-stu-id="ea9a1-118">The following illustration shows the Electronic reporting (ER) format.</span></span> <span data-ttu-id="ea9a1-119">Nesse formato, as associações são criadas para gerar saída no formato XML.</span><span class="sxs-lookup"><span data-stu-id="ea9a1-119">In this format, data bindings are created to generate output in XML format.</span></span> <span data-ttu-id="ea9a1-120">Esta saída apresenta fornecedores individuais como nós enumerados.</span><span class="sxs-lookup"><span data-stu-id="ea9a1-120">This output presents individual vendors as enumerated nodes.</span></span>

<a href="./media/picture-enumerate-format.jpg"><img src="./media/picture-enumerate-format.jpg" alt="Format that has data bindings" class="alignnone wp-image-290721 size-full" width="414" height="138" /></a>

<span data-ttu-id="ea9a1-121">A ilustração a seguir mostra o formato o resultado quando o formato criado é executado.</span><span class="sxs-lookup"><span data-stu-id="ea9a1-121">The following illustration shows the result when the designed format is run.</span></span>

<a href="./media/picture-enumerate-result.jpg"><img src="./media/picture-enumerate-result.jpg" alt="Result of running the format" class="alignnone wp-image-290731 size-full" width="567" height="176" /></a>

## <a name="additional-resources"></a><span data-ttu-id="ea9a1-122">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="ea9a1-122">Additional resources</span></span>

[<span data-ttu-id="ea9a1-123">Funções de listagem</span><span class="sxs-lookup"><span data-stu-id="ea9a1-123">List functions</span></span>](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]