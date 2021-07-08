---
title: Parâmetros para o plano mestre não existem
description: Quando você tenta firmar uma ordem planejada, você recebe uma mensagem de erro que afirma que não existem parâmetros para o plano mestre.
author: ankubik
ms.date: 06/10/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPo
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ankubik
ms.search.validFrom: 2021-06-10
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: d4b64af2e30109b8560d40c4c532504611528bbe
ms.sourcegitcommit: 18ca2df785e9656fdd4e8c0734eca2b2624fda10
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/22/2021
ms.locfileid: "6294013"
---
# <a name="parameters-for-the-master-plan-dont-exist"></a><span data-ttu-id="8d6cd-103">Parâmetros para o plano mestre não existem</span><span class="sxs-lookup"><span data-stu-id="8d6cd-103">Parameters for the master plan don't exist</span></span>

<span data-ttu-id="8d6cd-104">Código de erro: SYS25368</span><span class="sxs-lookup"><span data-stu-id="8d6cd-104">Error code: SYS25368</span></span>

## <a name="symptoms"></a><span data-ttu-id="8d6cd-105">Sintomas</span><span class="sxs-lookup"><span data-stu-id="8d6cd-105">Symptoms</span></span>

<span data-ttu-id="8d6cd-106">Ao tentar firmar uma ordem planejada, você recebe a seguinte mensagem de erro:</span><span class="sxs-lookup"><span data-stu-id="8d6cd-106">When you try to firm a planned order, you receive the following error message:</span></span>

> <span data-ttu-id="8d6cd-107">Os parâmetros do plano mestre %1 não existem.</span><span class="sxs-lookup"><span data-stu-id="8d6cd-107">Parameters for master plan %1 do not exist.</span></span>

## <a name="cause"></a><span data-ttu-id="8d6cd-108">Causa</span><span class="sxs-lookup"><span data-stu-id="8d6cd-108">Cause</span></span>

<span data-ttu-id="8d6cd-109">Devido a problemas de configuração, o sistema não consegue encontrar as configurações do plano especificado.</span><span class="sxs-lookup"><span data-stu-id="8d6cd-109">Because of configuration issues, the system can't find the settings for the specified plan.</span></span>

## <a name="resolution"></a><span data-ttu-id="8d6cd-110">Resolução</span><span class="sxs-lookup"><span data-stu-id="8d6cd-110">Resolution</span></span>

- <span data-ttu-id="8d6cd-111">Vá para **Planejamento mestre \> Configuração \> Planos \> Planos mestres** e certifique-se de que um plano que tenha o nome especificado exista.</span><span class="sxs-lookup"><span data-stu-id="8d6cd-111">Go to **Master planning \> Setup \> Plans \> Master plans**, and make sure that a plan that has the specified name exists.</span></span>
