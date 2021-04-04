---
title: Função FORMATELEMENTNAME ER
description: Este tópico fornece informações sobre como a função de relatório eletrônico FORMATELEMENTNAME é usada.
author: NickSelin
manager: kfend
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
ms.openlocfilehash: 1e2ee2faa2784f34d540c113622cee2090f24cef
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5561293"
---
# <a name="formatelementname-er-function"></a><span data-ttu-id="5c9e2-103">Função FORMATELEMENTNAME ER</span><span class="sxs-lookup"><span data-stu-id="5c9e2-103">FORMATELEMENTNAME ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5c9e2-104">A função `FORMATELEMENTNAME` retorna um valor de *Cadeia de caracteres* que representa o nome do elemento do formato de relatório eletrônico (ER) atual.</span><span class="sxs-lookup"><span data-stu-id="5c9e2-104">The `FORMATELEMENTNAME` function returns a *String* value that represents the name of the current Electronic reporting (ER) format's element.</span></span>

## <a name="syntax"></a><span data-ttu-id="5c9e2-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="5c9e2-105">Syntax</span></span>

```vb
FORMATELEMENTNAME ()
```

## <a name="return-values"></a><span data-ttu-id="5c9e2-106">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="5c9e2-106">Return values</span></span>

<span data-ttu-id="5c9e2-107">*Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="5c9e2-107">*String*</span></span>

<span data-ttu-id="5c9e2-108">O valor de texto resultante.</span><span class="sxs-lookup"><span data-stu-id="5c9e2-108">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="5c9e2-109">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="5c9e2-109">Usage notes</span></span>

<span data-ttu-id="5c9e2-110">Essa função pode ser chamada em expressões de ER que foram configuradas para propriedades **Nome da chave de dados coletada** e **Valor da chave de dados coletada** de um componente de formato ER do grupo **Texto** que está no componente **Arquivo \\ comum** onde a opção **Coletar detalhes de saída** está ativada.</span><span class="sxs-lookup"><span data-stu-id="5c9e2-110">This function can be called in ER expressions that were configured for the **Collected data key name** and **Collected data key value** properties of an ER format component from the **Text** group that resides under the **Common\\File** component where the **Collect output details** option is turned on.</span></span>

## <a name="example"></a><span data-ttu-id="5c9e2-111">Exemplo</span><span class="sxs-lookup"><span data-stu-id="5c9e2-111">Example</span></span>

<span data-ttu-id="5c9e2-112">Para obter informações sobre como usar esta função, consulte o guia de tarefas [ER Usar dados de saída do formato contagem e soma](tasks/er-format-counting-summing-1.md), que faz parte do processo de negócios **Adquirir/Desenvolver componentes de solução/serviço de TI**.</span><span class="sxs-lookup"><span data-stu-id="5c9e2-112">For more information about how to use this function, see the [ER Use data of format output for counting and summing](tasks/er-format-counting-summing-1.md) task guide, which is part of the **Acquire/Develop IT service/solution components** business process.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="5c9e2-113">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="5c9e2-113">Additional resources</span></span>

[<span data-ttu-id="5c9e2-114">Funções de coleta de dados</span><span class="sxs-lookup"><span data-stu-id="5c9e2-114">Data collection functions</span></span>](er-functions-category-data-collection.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]