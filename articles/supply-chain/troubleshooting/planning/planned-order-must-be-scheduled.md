---
title: A ordem de produção planejada deve ser agendada antes de ser firmada
description: Quando tenta firmar uma ordem planejada, você recebe uma mensagem de erro que afirma que a ordem deve ser agendada antes que ela possa ser firmada.
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
ms.openlocfilehash: a360cb3cbd26e1bc1ebb1baf1a6a4d8282c28c5c
ms.sourcegitcommit: 18ca2df785e9656fdd4e8c0734eca2b2624fda10
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/22/2021
ms.locfileid: "6294015"
---
# <a name="planned-production-order-must-be-scheduled-before-it-can-be-firmed"></a><span data-ttu-id="db187-103">A ordem de produção planejada deve ser agendada antes de ser firmada</span><span class="sxs-lookup"><span data-stu-id="db187-103">Planned production order must be scheduled before it can be firmed</span></span>

<span data-ttu-id="db187-104">Código de erro: SYS309802</span><span class="sxs-lookup"><span data-stu-id="db187-104">Error code: SYS309802</span></span>

## <a name="symptoms"></a><span data-ttu-id="db187-105">Sintomas</span><span class="sxs-lookup"><span data-stu-id="db187-105">Symptoms</span></span>

<span data-ttu-id="db187-106">Ao tentar firmar uma ordem planejada, você recebe a seguinte mensagem de erro:</span><span class="sxs-lookup"><span data-stu-id="db187-106">When you try to firm a planned order, you receive the following error message:</span></span>

> <span data-ttu-id="db187-107">A ordem de produção planejada deve ser agendada para que possa ser confirmada.</span><span class="sxs-lookup"><span data-stu-id="db187-107">The planned production order must be scheduled before it can be firmed.</span></span>

## <a name="cause"></a><span data-ttu-id="db187-108">Causa</span><span class="sxs-lookup"><span data-stu-id="db187-108">Cause</span></span>

<span data-ttu-id="db187-109">As datas agendadas de início e término não podem ficar em branco.</span><span class="sxs-lookup"><span data-stu-id="db187-109">The scheduled start and end dates can't be blank.</span></span>

## <a name="resolution"></a><span data-ttu-id="db187-110">Resolução</span><span class="sxs-lookup"><span data-stu-id="db187-110">Resolution</span></span>

<span data-ttu-id="db187-111">Para especificar as datas de início e término da ordem planejada, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="db187-111">To specify start and end dates for the planned order, follow these steps.</span></span>

1. <span data-ttu-id="db187-112">Vá para **Planejamento mestre \> Planejamento mestre \> Ordens planejadas**.</span><span class="sxs-lookup"><span data-stu-id="db187-112">Go to **Master planning \> Master planning \> Planned orders**.</span></span>
1. <span data-ttu-id="db187-113">Abra a ordem planejada relevante.</span><span class="sxs-lookup"><span data-stu-id="db187-113">Open the relevant planned order.</span></span>
1. <span data-ttu-id="db187-114">Na FastTab **Geral**, na seção **Agendado**, especifique as datas nos campos **Data de início** e **Data de término**.</span><span class="sxs-lookup"><span data-stu-id="db187-114">On the **General** FastTab, in the **Scheduled** section, specify dates in the **Start date** and **End date** fields.</span></span>
