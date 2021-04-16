---
title: Atribuir sequências numéricas
description: Este tópico explica como criar sequências numéricas para IDs de arrendamento. Também explica como criar IDs exclusivas que são usadas no processo de reavaliação do índice.
author: moaamer
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: a0b5d622df1e5dcdf7f1322328bce7e185f8edb8
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5819809"
---
# <a name="assign-number-sequences"></a><span data-ttu-id="21a7c-104">Atribuir sequências numéricas</span><span class="sxs-lookup"><span data-stu-id="21a7c-104">Assign number sequences</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="21a7c-105">Este tópico explica como criar sequências numéricas para IDs de arrendamento.</span><span class="sxs-lookup"><span data-stu-id="21a7c-105">This topic explains how to create number sequences for lease IDs.</span></span> <span data-ttu-id="21a7c-106">Também explica como criar IDs exclusivas que são usadas no processo de reavaliação do índice.</span><span class="sxs-lookup"><span data-stu-id="21a7c-106">It also explains how to create unique IDs that are used in the index revaluation process.</span></span>

1. <span data-ttu-id="21a7c-107">Acesse **Gerenciamento de ativos \> Configuração \> Parâmetros de gerenciamento de ativos**.</span><span class="sxs-lookup"><span data-stu-id="21a7c-107">Go to **Asset leasing \> Setup \> Asset leasing parameters**.</span></span>
2. <span data-ttu-id="21a7c-108">Selecione a guia lateral **Sequências numéricas**.</span><span class="sxs-lookup"><span data-stu-id="21a7c-108">Select the **Number sequences** side tab.</span></span>
3. <span data-ttu-id="21a7c-109">Selecione **Sequências numéricas** na barra lateral.</span><span class="sxs-lookup"><span data-stu-id="21a7c-109">Select **Number sequences** in the side bar.</span></span>
4. <span data-ttu-id="21a7c-110">Selecione a sequência numérica para a referência **ID do Arrendamento**.</span><span class="sxs-lookup"><span data-stu-id="21a7c-110">Select the number sequence for the **Lease ID** reference.</span></span> <span data-ttu-id="21a7c-111">Essa sequência numérica será usada para gerar o identificador exclusivo para cada arrendamento.</span><span class="sxs-lookup"><span data-stu-id="21a7c-111">This number sequence will be used to generate the unique identifier for each lease.</span></span>
5. <span data-ttu-id="21a7c-112">Selecione a sequência numérica para a referência **ID do Processo**.</span><span class="sxs-lookup"><span data-stu-id="21a7c-112">Select the number sequence for the **Process ID** reference.</span></span> <span data-ttu-id="21a7c-113">Essa sequência numérica será usada para gerar o identificador exclusivo para cada processo de reavaliação de índice.</span><span class="sxs-lookup"><span data-stu-id="21a7c-113">This number sequence will be used to generate the unique identifier for each index revaluation process.</span></span>
6. <span data-ttu-id="21a7c-114">Selecione a sequência numérica para a referência **ID de Proposta de Rescisão**.</span><span class="sxs-lookup"><span data-stu-id="21a7c-114">Select the number sequence for the **Termination Proposal ID** reference.</span></span> <span data-ttu-id="21a7c-115">Essa sequência numérica será usada para gerar o identificador exclusivo de cada proposta de rescisão.</span><span class="sxs-lookup"><span data-stu-id="21a7c-115">This number sequence will be used to generate the unique identifier for each termination proposal.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]