---
title: Lista de funções ER na categoria contêiner
description: Este tópico fornece informações sobre as funções de contêiner que são compatíveis no relatório eletrônico (ER).
author: NickSelin
ms.date: 12/14/2020
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
ms.search.validFrom: 2020-12-01
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 95f207538ea4f0f7df775bf28d0dcf6529d1a91c
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5753231"
---
# <a name="list-of-er-functions-in-the-container-category"></a><span data-ttu-id="e570a-103">Lista de funções ER na categoria contêiner</span><span class="sxs-lookup"><span data-stu-id="e570a-103">List of ER functions in the container category</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e570a-104">As [funções](er-formula-language.md#functions) de [relatório eletrônico (ER)](general-electronic-reporting.md) podem ser usadas para realizar operações em fontes de dados do tipo de dado *Contêiner*.</span><span class="sxs-lookup"><span data-stu-id="e570a-104">[Electronic reporting (ER)](general-electronic-reporting.md) container [functions](er-formula-language.md#functions) can be used to perform operations that involve data sources of the *Container* data type.</span></span> <span data-ttu-id="e570a-105">Essas operações ocorrem quando os dados de processamento representam uma coleção de dados binários no formato de objeto binário grande (BLOB).</span><span class="sxs-lookup"><span data-stu-id="e570a-105">These operations occur when the processing data represents a collection of binary data in binary large object (BLOB) format.</span></span> <span data-ttu-id="e570a-106">Este tópico fornece um resumo dessas funções.</span><span class="sxs-lookup"><span data-stu-id="e570a-106">This topic provides a summary of these functions.</span></span>

## <a name="list-of-supported-functions"></a><span data-ttu-id="e570a-107">Lista de funções com suporte</span><span class="sxs-lookup"><span data-stu-id="e570a-107">List of supported functions</span></span>

| <span data-ttu-id="e570a-108">Função</span><span class="sxs-lookup"><span data-stu-id="e570a-108">Function</span></span> | <span data-ttu-id="e570a-109">descrição</span><span class="sxs-lookup"><span data-stu-id="e570a-109">Description</span></span> |
|----------|-------------|
| [<span data-ttu-id="e570a-110">Base64StringToContainer</span><span class="sxs-lookup"><span data-stu-id="e570a-110">Base64StringToContainer</span></span>](er-functions-container-base64stringtocontainer.md) | <span data-ttu-id="e570a-111">Esta função retorna um valor de *contêiner* que consiste no conteúdo binário decodificado com base na sequência de caracteres ASCII especificada que representa um grupo Base64 de esquemas de codificação de binário para texto.</span><span class="sxs-lookup"><span data-stu-id="e570a-111">This function returns a *Container* value that consists of binary content that is decoded from the specified ASCII string that represents a Base64 group of binary-to-text encoding schemes.</span></span> |

## <a name="additional-resources"></a><span data-ttu-id="e570a-112">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="e570a-112">Additional resources</span></span>

[<span data-ttu-id="e570a-113">Visão geral do Relatório Eletrônico</span><span class="sxs-lookup"><span data-stu-id="e570a-113">Electronic Reporting overview</span></span>](general-electronic-reporting.md)

[<span data-ttu-id="e570a-114">Designer de fórmulas no Relatório eletrônico</span><span class="sxs-lookup"><span data-stu-id="e570a-114">Formula designer in Electronic reporting</span></span>](general-electronic-reporting-formula-designer.md)

[<span data-ttu-id="e570a-115">Linguagem da fórmula de relatório eletrônico</span><span class="sxs-lookup"><span data-stu-id="e570a-115">Electronic reporting formula language</span></span>](er-formula-language.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]