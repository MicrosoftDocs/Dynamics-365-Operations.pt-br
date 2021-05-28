---
title: Os administradores de sistema não podem liberar bloqueios de ordem, pois não estão autorizados a fazer isso
description: Os administradores de sistema não podem liberar bloqueios de ordem, pois não estão autorizados a fazer isso.
author: SmithaNataraj
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: acabd6409d9b2860535335bc648bcc34304e0cb0
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026286"
---
# <a name="system-administrators-cant-clear-order-holds-because-they-arent-authorized"></a><span data-ttu-id="df269-103">Os administradores de sistema não podem liberar bloqueios de ordem, pois não estão autorizados a fazer isso</span><span class="sxs-lookup"><span data-stu-id="df269-103">System administrators can't clear order holds because they aren't authorized</span></span>

<span data-ttu-id="df269-104">Número de KB: 4614642</span><span class="sxs-lookup"><span data-stu-id="df269-104">KB number: 4614642</span></span>

## <a name="symptoms"></a><span data-ttu-id="df269-105">Sintomas</span><span class="sxs-lookup"><span data-stu-id="df269-105">Symptoms</span></span>

<span data-ttu-id="df269-106">Os administradores de sistema não podem liberar bloqueios de ordem de venda, exceto se desempenhar uma função atribuída no código de bloqueio da ordem.</span><span class="sxs-lookup"><span data-stu-id="df269-106">System administrators can't clear sales order holds unless they have the specific role that is assigned in the order hold code.</span></span>

## <a name="resolution"></a><span data-ttu-id="df269-107">Resolução</span><span class="sxs-lookup"><span data-stu-id="df269-107">Resolution</span></span>

<span data-ttu-id="df269-108">O acesso a algumas operações, como a liberação de ordens de venda, é orientado pela definição de uma política corporativa.</span><span class="sxs-lookup"><span data-stu-id="df269-108">Access to some operations, such as clearing sales order holds, is driven by the setup of a business policy.</span></span> <span data-ttu-id="df269-109">Os administradores de sistema geralmente não têm permissão para realizar operações desse tipo.</span><span class="sxs-lookup"><span data-stu-id="df269-109">System administrators aren't typically allowed to perform operations of this type.</span></span> 

<span data-ttu-id="df269-110">Na maioria das vezes, a permissão para realizar tarefas específicas é definida por políticas corporativas, e apenas certas pessoas em uma empresa podem realizar aquela tarefa.</span><span class="sxs-lookup"><span data-stu-id="df269-110">More often, access to perform a specific task is governed by business policies, and only specific persons in an organization are approved to perform that task.</span></span> <span data-ttu-id="df269-111">Os exemplos incluem aprovações resultantes de permissões de fluxo de trabalho e tarefas específicas que surgem por conta de uma configuração de fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="df269-111">Examples include approvals that are the result of workflow approvals and specific tasks that are the result of a workflow configuration.</span></span>

<span data-ttu-id="df269-112">Embora nenhum fluxo de trabalho esteja associado a bloqueios de ordem, o princípio é semelhante.</span><span class="sxs-lookup"><span data-stu-id="df269-112">Although no workflow is associated with order holds, the principle is similar.</span></span> <span data-ttu-id="df269-113">Uma função relevante define o grupo específico de pessoas em uma empresa que têm o direito de liberar bloqueios de ordem.</span><span class="sxs-lookup"><span data-stu-id="df269-113">A relevant role designates the specific group of people in an organization who have the right to clear order holds.</span></span> <span data-ttu-id="df269-114">Esse direito não deve necessariamente ser concedido a todos os administradores, pois essa abordagem viola a política corporativa definida.</span><span class="sxs-lookup"><span data-stu-id="df269-114">This right should not necessarily be granted to all administrators, because that approach violates the defined business policy.</span></span>
