---
title: Solucionar problemas de reabastecimento de depósito
description: Este tópico descreve como corrigir problemas comuns que você pode encontrar ao trabalhar com reabastecimento de depósito no Microsoft Dynamics 365 Supply Chain Management.
author: perlynne
manager: tfehr
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 7748a18d2b6f612b3ac9ac1a75efb6ae5f13859a
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4993851"
---
# <a name="troubleshoot-warehouse-replenishment"></a><span data-ttu-id="8f38a-103">Solucionar problemas de reabastecimento de depósito</span><span class="sxs-lookup"><span data-stu-id="8f38a-103">Troubleshoot warehouse replenishment</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="8f38a-104">Este tópico descreve como corrigir problemas comuns que você pode encontrar ao trabalhar com reabastecimento de depósito no Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="8f38a-104">This topic describes how to fix common issues that you might encounter while you work with warehouse replenishment in Microsoft Dynamics 365 Supply Chain Management.</span></span>

## <a name="i-receive-the-following-error-message-work-1-cannot-be-unblocked-because-it-has-unfinished-replenishment-work"></a><span data-ttu-id="8f38a-105">Recebo a seguinte mensagem de erro: "Não é possível desbloquear a ID de trabalho %1 porque existe trabalho de reabastecimento não concluído."</span><span class="sxs-lookup"><span data-stu-id="8f38a-105">I receive the following error message: "Work %1 cannot be unblocked because it has unfinished replenishment work."</span></span>

### <a name="issue-description"></a><span data-ttu-id="8f38a-106">Descrição do problema</span><span class="sxs-lookup"><span data-stu-id="8f38a-106">Issue description</span></span>

<span data-ttu-id="8f38a-107">O trabalho de separação está bloqueado por causa do trabalho de reabastecimento dependente.</span><span class="sxs-lookup"><span data-stu-id="8f38a-107">Picking work is blocked because of dependent replenishment work.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="8f38a-108">Resolução do problema</span><span class="sxs-lookup"><span data-stu-id="8f38a-108">Issue resolution</span></span>

<span data-ttu-id="8f38a-109">Quando você usa o reabastecimento por demanda de ciclo, se um local de separação deve ser reabastecido para atender à demanda da ordem de origem, o sistema cria o trabalho de reabastecimento e o trabalho de separação.</span><span class="sxs-lookup"><span data-stu-id="8f38a-109">When you use wave demand replenishment, if a picking location must be replenished to fulfill the source order demand, the system creates both the replenishment work and the picking work.</span></span> <span data-ttu-id="8f38a-110">Contudo, ele bloqueia o trabalho de separação até que o trabalho de reabastecimento seja concluído.</span><span class="sxs-lookup"><span data-stu-id="8f38a-110">However, it blocks the picking work until the replenishment work is completed.</span></span> <span data-ttu-id="8f38a-111">Esse comportamento é intencional, porque o local de separação não terá estoque suficiente a menos que o trabalho de reabastecimento seja concluído.</span><span class="sxs-lookup"><span data-stu-id="8f38a-111">This behavior is intentional, because the picking location won't have enough inventory unless the replenishment work is completed.</span></span> <span data-ttu-id="8f38a-112">Conclua o trabalho de reabastecimento e processe o trabalho de separação.</span><span class="sxs-lookup"><span data-stu-id="8f38a-112">Complete the replenishment work, and then process the picking work.</span></span>
