---
title: Atribuir sequências numéricas
description: Este tópico explica como criar sequências numéricas para IDs de arrendamento. Também explica como criar IDs exclusivas que são usadas no processo de reavaliação do índice.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeasePostingAccounts
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 331542811b2ba9399185478b6d25d1a57fce3a05
ms.sourcegitcommit: d18d9cdb175c9d42eafbed66352c24b2aa94258b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/13/2021
ms.locfileid: "5881075"
---
# <a name="assign-number-sequences"></a><span data-ttu-id="56f8e-104">Atribuir sequências numéricas</span><span class="sxs-lookup"><span data-stu-id="56f8e-104">Assign number sequences</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="56f8e-105">Este tópico explica como criar sequências numéricas para IDs de arrendamento.</span><span class="sxs-lookup"><span data-stu-id="56f8e-105">This topic explains how to create number sequences for lease IDs.</span></span> <span data-ttu-id="56f8e-106">Também explica como criar IDs exclusivas que são usadas no processo de reavaliação do índice.</span><span class="sxs-lookup"><span data-stu-id="56f8e-106">It also explains how to create unique IDs that are used in the index revaluation process.</span></span>

1. <span data-ttu-id="56f8e-107">Acesse **Gerenciamento de ativos \> Configuração \> Parâmetros de gerenciamento de ativos**.</span><span class="sxs-lookup"><span data-stu-id="56f8e-107">Go to **Asset leasing \> Setup \> Asset leasing parameters**.</span></span>
2. <span data-ttu-id="56f8e-108">Selecione a guia lateral **Sequências numéricas**.</span><span class="sxs-lookup"><span data-stu-id="56f8e-108">Select the **Number sequences** side tab.</span></span>
3. <span data-ttu-id="56f8e-109">Selecione **Sequências numéricas** na barra lateral.</span><span class="sxs-lookup"><span data-stu-id="56f8e-109">Select **Number sequences** in the side bar.</span></span>
4. <span data-ttu-id="56f8e-110">Selecione a sequência numérica para a referência **ID do Arrendamento**.</span><span class="sxs-lookup"><span data-stu-id="56f8e-110">Select the number sequence for the **Lease ID** reference.</span></span> <span data-ttu-id="56f8e-111">Essa sequência numérica será usada para gerar o identificador exclusivo para cada arrendamento.</span><span class="sxs-lookup"><span data-stu-id="56f8e-111">This number sequence will be used to generate the unique identifier for each lease.</span></span>
5. <span data-ttu-id="56f8e-112">Selecione a sequência numérica para a referência **ID do Processo**.</span><span class="sxs-lookup"><span data-stu-id="56f8e-112">Select the number sequence for the **Process ID** reference.</span></span> <span data-ttu-id="56f8e-113">Essa sequência numérica será usada para gerar o identificador exclusivo para cada processo de reavaliação de índice.</span><span class="sxs-lookup"><span data-stu-id="56f8e-113">This number sequence will be used to generate the unique identifier for each index revaluation process.</span></span>
6. <span data-ttu-id="56f8e-114">Selecione a sequência numérica para a referência **ID de Proposta de Rescisão**.</span><span class="sxs-lookup"><span data-stu-id="56f8e-114">Select the number sequence for the **Termination Proposal ID** reference.</span></span> <span data-ttu-id="56f8e-115">Essa sequência numérica será usada para gerar o identificador exclusivo de cada proposta de rescisão.</span><span class="sxs-lookup"><span data-stu-id="56f8e-115">This number sequence will be used to generate the unique identifier for each termination proposal.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
