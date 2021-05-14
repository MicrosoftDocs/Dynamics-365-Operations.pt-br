---
title: O trabalho não está bloqueado
description: O trabalho não está bloqueado
author: perlynne
ms.date: 04/15/2021
ms.topic: troubleshooting
ms.search.form: WHSWorkTable_WHSWorkUnblocking
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-05-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: d64ab282972e46e8857581b59e5705dd15667328
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924195"
---
# <a name="work-isnt-blocked"></a><span data-ttu-id="f3d0d-103">O trabalho não está bloqueado</span><span class="sxs-lookup"><span data-stu-id="f3d0d-103">Work isn't blocked</span></span>

<span data-ttu-id="f3d0d-104">Código de erro: WHSUnblockNotBlockedWorkErrorMessage</span><span class="sxs-lookup"><span data-stu-id="f3d0d-104">Error code: WHSUnblockNotBlockedWorkErrorMessage</span></span>

## <a name="symptoms"></a><span data-ttu-id="f3d0d-105">Sintomas</span><span class="sxs-lookup"><span data-stu-id="f3d0d-105">Symptoms</span></span>

<span data-ttu-id="f3d0d-106">O sistema mostra a seguinte mensagem de erro:</span><span class="sxs-lookup"><span data-stu-id="f3d0d-106">The system shows the following error message:</span></span>

> <span data-ttu-id="f3d0d-107">O trabalho com a ID %1 não está bloqueado.</span><span class="sxs-lookup"><span data-stu-id="f3d0d-107">Work with Id %1 is not blocked.</span></span>

## <a name="cause"></a><span data-ttu-id="f3d0d-108">Causa</span><span class="sxs-lookup"><span data-stu-id="f3d0d-108">Cause</span></span>

<span data-ttu-id="f3d0d-109">A opção **Ciclo bloqueado** no ciclo está definida como *Não*.</span><span class="sxs-lookup"><span data-stu-id="f3d0d-109">The **Blocked wave** option on the wave is set to *No*.</span></span> <span data-ttu-id="f3d0d-110">O trabalho não pode ser desbloqueado porque não está bloqueado no momento.</span><span class="sxs-lookup"><span data-stu-id="f3d0d-110">The work can't be unblocked because it isn't currently blocked.</span></span>

## <a name="resolution"></a><span data-ttu-id="f3d0d-111">Resolução</span><span class="sxs-lookup"><span data-stu-id="f3d0d-111">Resolution</span></span>

 <span data-ttu-id="f3d0d-112">Somente o trabalho em que a opção **Ciclo bloqueado** esteja definida como *Sim* pode ser desbloqueado.</span><span class="sxs-lookup"><span data-stu-id="f3d0d-112">Only work where the **Blocked wave** option is set to *Yes* can be unblocked.</span></span>
