---
title: Lista de funções ER na categoria contêiner
description: Este tópico fornece informações sobre as funções de contêiner que são compatíveis no relatório eletrônico (ER).
author: NickSelin
manager: kfend
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
ms.openlocfilehash: b7e7d770c334647f8f11338d49b39a2e9cb5c04c
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5561749"
---
# <a name="list-of-er-functions-in-the-container-category"></a><span data-ttu-id="ec141-103">Lista de funções ER na categoria contêiner</span><span class="sxs-lookup"><span data-stu-id="ec141-103">List of ER functions in the container category</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ec141-104">As [funções](er-formula-language.md#functions) de [relatório eletrônico (ER)](general-electronic-reporting.md) podem ser usadas para realizar operações em fontes de dados do tipo de dado *Contêiner*.</span><span class="sxs-lookup"><span data-stu-id="ec141-104">[Electronic reporting (ER)](general-electronic-reporting.md) container [functions](er-formula-language.md#functions) can be used to perform operations that involve data sources of the *Container* data type.</span></span> <span data-ttu-id="ec141-105">Essas operações ocorrem quando os dados de processamento representam uma coleção de dados binários no formato de objeto binário grande (BLOB).</span><span class="sxs-lookup"><span data-stu-id="ec141-105">These operations occur when the processing data represents a collection of binary data in binary large object (BLOB) format.</span></span> <span data-ttu-id="ec141-106">Este tópico fornece um resumo dessas funções.</span><span class="sxs-lookup"><span data-stu-id="ec141-106">This topic provides a summary of these functions.</span></span>

## <a name="list-of-supported-functions"></a><span data-ttu-id="ec141-107">Lista de funções com suporte</span><span class="sxs-lookup"><span data-stu-id="ec141-107">List of supported functions</span></span>

| <span data-ttu-id="ec141-108">Função</span><span class="sxs-lookup"><span data-stu-id="ec141-108">Function</span></span> | <span data-ttu-id="ec141-109">descrição</span><span class="sxs-lookup"><span data-stu-id="ec141-109">Description</span></span> |
|----------|-------------|
| [<span data-ttu-id="ec141-110">Base64StringToContainer</span><span class="sxs-lookup"><span data-stu-id="ec141-110">Base64StringToContainer</span></span>](er-functions-container-base64stringtocontainer.md) | <span data-ttu-id="ec141-111">Esta função retorna um valor de *contêiner* que consiste no conteúdo binário decodificado com base na sequência de caracteres ASCII especificada que representa um grupo Base64 de esquemas de codificação de binário para texto.</span><span class="sxs-lookup"><span data-stu-id="ec141-111">This function returns a *Container* value that consists of binary content that is decoded from the specified ASCII string that represents a Base64 group of binary-to-text encoding schemes.</span></span> |

## <a name="additional-resources"></a><span data-ttu-id="ec141-112">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="ec141-112">Additional resources</span></span>

[<span data-ttu-id="ec141-113">Visão geral do Relatório Eletrônico</span><span class="sxs-lookup"><span data-stu-id="ec141-113">Electronic Reporting overview</span></span>](general-electronic-reporting.md)

[<span data-ttu-id="ec141-114">Designer de fórmulas no Relatório eletrônico</span><span class="sxs-lookup"><span data-stu-id="ec141-114">Formula designer in Electronic reporting</span></span>](general-electronic-reporting-formula-designer.md)

[<span data-ttu-id="ec141-115">Linguagem da fórmula de relatório eletrônico</span><span class="sxs-lookup"><span data-stu-id="ec141-115">Electronic reporting formula language</span></span>](er-formula-language.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]