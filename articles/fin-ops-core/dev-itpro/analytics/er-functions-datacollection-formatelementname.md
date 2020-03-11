---
title: Função FORMATELEMENTNAME ER
description: Este tópico fornece informações sobre como a função de relatório eletrônico FORMATELEMENTNAME é usada.
author: NickSelin
manager: kfend
ms.date: 12/05/2019
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
ms.openlocfilehash: 5f299a4bb697afce152a61ec35fcefab7157f356
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/12/2020
ms.locfileid: "3042518"
---
# <span data-ttu-id="8c80c-103"><a name="FORMATELEMENTNAME">Função FORMATELEMENTNAME ER</a></span><span class="sxs-lookup"><span data-stu-id="8c80c-103"><a name="FORMATELEMENTNAME">FORMATELEMENTNAME ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="8c80c-104">A função `FORMATELEMENTNAME` retorna um valor de *Cadeia de caracteres* que representa o nome do elemento do formato de relatório eletrônico (ER) atual.</span><span class="sxs-lookup"><span data-stu-id="8c80c-104">The `FORMATELEMENTNAME` function returns a *String* value that represents the name of the current Electronic reporting (ER) format's element.</span></span>

## <a name="syntax"></a><span data-ttu-id="8c80c-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="8c80c-105">Syntax</span></span>

```vb
FORMATELEMENTNAME ()
```

## <a name="return-values"></a><span data-ttu-id="8c80c-106">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="8c80c-106">Return values</span></span>

<span data-ttu-id="8c80c-107">*Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="8c80c-107">*String*</span></span>

<span data-ttu-id="8c80c-108">O valor de texto resultante.</span><span class="sxs-lookup"><span data-stu-id="8c80c-108">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="8c80c-109">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="8c80c-109">Usage notes</span></span>

<span data-ttu-id="8c80c-110">Essa função pode ser chamada em expressões de ER que foram configuradas para propriedades **Nome da chave de dados coletada** e **Valor da chave de dados coletada** de um componente de formato ER do grupo **Texto** que está no componente **Arquivo \\ comum** onde a opção **Coletar detalhes de saída** está ativada.</span><span class="sxs-lookup"><span data-stu-id="8c80c-110">This function can be called in ER expressions that were configured for the **Collected data key name** and **Collected data key value** properties of an ER format component from the **Text** group that resides under the **Common\\File** component where the **Collect output details** option is turned on.</span></span>

## <a name="example"></a><span data-ttu-id="8c80c-111">Exemplo</span><span class="sxs-lookup"><span data-stu-id="8c80c-111">Example</span></span>

<span data-ttu-id="8c80c-112">Para obter informações sobre como usar esta função, consulte o guia de tarefas [ER Usar dados de saída do formato contagem e soma](tasks/er-format-counting-summing-1.md), que faz parte do processo de negócios **Adquirir/Desenvolver componentes de solução/serviço de TI**.</span><span class="sxs-lookup"><span data-stu-id="8c80c-112">For more information about how to use this function, see the [ER Use data of format output for counting and summing](tasks/er-format-counting-summing-1.md) task guide, which is part of the **Acquire/Develop IT service/solution components** business process.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="8c80c-113">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="8c80c-113">Additional resources</span></span>

[<span data-ttu-id="8c80c-114">Funções de coleta de dados</span><span class="sxs-lookup"><span data-stu-id="8c80c-114">Data collection functions</span></span>](er-functions-category-data-collection.md)
