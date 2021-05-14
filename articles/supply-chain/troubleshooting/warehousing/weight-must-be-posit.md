---
title: O peso deve ser positivo
description: O peso deve ser positivo
author: perlynne
ms.date: 04/15/2021
ms.topic: troubleshooting
ms.search.form: WHSContainerCloseDiag_canClose
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-05-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: dcbcde3143cb509b68b277cb7c709263e2659b5b
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924294"
---
# <a name="weight-must-be-positive"></a><span data-ttu-id="8800b-103">O peso deve ser positivo</span><span class="sxs-lookup"><span data-stu-id="8800b-103">Weight must be positive</span></span>

<span data-ttu-id="8800b-104">Código de erro: WeightMustBePositive</span><span class="sxs-lookup"><span data-stu-id="8800b-104">Error code: WeightMustBePositive</span></span>

## <a name="symptoms"></a><span data-ttu-id="8800b-105">Sintomas</span><span class="sxs-lookup"><span data-stu-id="8800b-105">Symptoms</span></span>

<span data-ttu-id="8800b-106">O sistema mostra a seguinte mensagem de erro:</span><span class="sxs-lookup"><span data-stu-id="8800b-106">The system shows the following error message:</span></span>

> <span data-ttu-id="8800b-107">O peso deve ser positivo.</span><span class="sxs-lookup"><span data-stu-id="8800b-107">Weight must be positive.</span></span>

## <a name="cause"></a><span data-ttu-id="8800b-108">Causa</span><span class="sxs-lookup"><span data-stu-id="8800b-108">Cause</span></span>

<span data-ttu-id="8800b-109">O campo **Peso Bruto** é definido como *0* (zero) ou um valor negativo.</span><span class="sxs-lookup"><span data-stu-id="8800b-109">The **Gross Weight** field is set to *0* (zero) or a negative value.</span></span>

## <a name="resolution"></a><span data-ttu-id="8800b-110">Resolução</span><span class="sxs-lookup"><span data-stu-id="8800b-110">Resolution</span></span>

<span data-ttu-id="8800b-111">Para especificar um peso, siga uma destas etapas.</span><span class="sxs-lookup"><span data-stu-id="8800b-111">To specify a weight, follow one of these steps.</span></span>

- <span data-ttu-id="8800b-112">No campo **Peso bruto**, defina um valor.</span><span class="sxs-lookup"><span data-stu-id="8800b-112">In the **Gross weight** field, set a value.</span></span> <span data-ttu-id="8800b-113">Em seguida, selecione uma unidade na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="8800b-113">Then select a unit in the drop-down list.</span></span>
- <span data-ttu-id="8800b-114">Selecione **Obter peso do sistema** para calcular o valor **Peso bruto**.</span><span class="sxs-lookup"><span data-stu-id="8800b-114">Select **Get system weight** to calculate the **Gross weight** value.</span></span>
