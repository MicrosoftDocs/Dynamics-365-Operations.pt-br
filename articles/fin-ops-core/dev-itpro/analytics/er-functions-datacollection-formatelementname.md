---
title: Função FORMATELEMENTNAME ER
description: Este tópico fornece informações sobre como a função de relatório eletrônico FORMATELEMENTNAME é usada.
author: NickSelin
ms.date: 12/05/2019
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
ms.openlocfilehash: f716fe779903b4e9142b7959d868256f2d84c624
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5755219"
---
# <a name="formatelementname-er-function"></a><span data-ttu-id="bfbd7-103">Função FORMATELEMENTNAME ER</span><span class="sxs-lookup"><span data-stu-id="bfbd7-103">FORMATELEMENTNAME ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="bfbd7-104">A função `FORMATELEMENTNAME` retorna um valor de *Cadeia de caracteres* que representa o nome do elemento do formato de relatório eletrônico (ER) atual.</span><span class="sxs-lookup"><span data-stu-id="bfbd7-104">The `FORMATELEMENTNAME` function returns a *String* value that represents the name of the current Electronic reporting (ER) format's element.</span></span>

## <a name="syntax"></a><span data-ttu-id="bfbd7-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="bfbd7-105">Syntax</span></span>

```vb
FORMATELEMENTNAME ()
```

## <a name="return-values"></a><span data-ttu-id="bfbd7-106">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="bfbd7-106">Return values</span></span>

<span data-ttu-id="bfbd7-107">*Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="bfbd7-107">*String*</span></span>

<span data-ttu-id="bfbd7-108">O valor de texto resultante.</span><span class="sxs-lookup"><span data-stu-id="bfbd7-108">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="bfbd7-109">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="bfbd7-109">Usage notes</span></span>

<span data-ttu-id="bfbd7-110">Essa função pode ser chamada em expressões de ER que foram configuradas para propriedades **Nome da chave de dados coletada** e **Valor da chave de dados coletada** de um componente de formato ER do grupo **Texto** que está no componente **Arquivo \\ comum** onde a opção **Coletar detalhes de saída** está ativada.</span><span class="sxs-lookup"><span data-stu-id="bfbd7-110">This function can be called in ER expressions that were configured for the **Collected data key name** and **Collected data key value** properties of an ER format component from the **Text** group that resides under the **Common\\File** component where the **Collect output details** option is turned on.</span></span>

## <a name="example"></a><span data-ttu-id="bfbd7-111">Exemplo</span><span class="sxs-lookup"><span data-stu-id="bfbd7-111">Example</span></span>

<span data-ttu-id="bfbd7-112">Para obter informações sobre como usar esta função, consulte o guia de tarefas [ER Usar dados de saída do formato contagem e soma](tasks/er-format-counting-summing-1.md), que faz parte do processo de negócios **Adquirir/Desenvolver componentes de solução/serviço de TI**.</span><span class="sxs-lookup"><span data-stu-id="bfbd7-112">For more information about how to use this function, see the [ER Use data of format output for counting and summing](tasks/er-format-counting-summing-1.md) task guide, which is part of the **Acquire/Develop IT service/solution components** business process.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="bfbd7-113">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="bfbd7-113">Additional resources</span></span>

[<span data-ttu-id="bfbd7-114">Funções de coleta de dados</span><span class="sxs-lookup"><span data-stu-id="bfbd7-114">Data collection functions</span></span>](er-functions-category-data-collection.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]