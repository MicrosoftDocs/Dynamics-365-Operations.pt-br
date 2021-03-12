---
title: Solucionar problemas de trabalho do depósito
description: Este tópico descreve como corrigir problemas comuns que você pode encontrar ao trabalhar com trabalho de depósito no Microsoft Dynamics 365 Supply Chain Management.
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
ms.openlocfilehash: 3015ec777953cedb5a5d8eea873ed1043cac04cb
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4970222"
---
# <a name="troubleshoot-warehouse-work"></a><span data-ttu-id="b9596-103">Solucionar problemas de trabalho do depósito</span><span class="sxs-lookup"><span data-stu-id="b9596-103">Troubleshoot warehouse work</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b9596-104">Este tópico descreve como corrigir problemas comuns que você pode encontrar ao trabalhar com trabalho de depósito no Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="b9596-104">This topic describes how to fix common issues that you might encounter while you work with warehouse work in Microsoft Dynamics 365 Supply Chain Management.</span></span>

## <a name="i-cant-move-license-plates-that-have-serial-number-items-when-blank-issue-and-blank-receipt-are-allowed-on-the-tracking-dimension-group"></a><span data-ttu-id="b9596-105">Não consigo mover placas de licença com itens de número de série quando a emissão e o recebimento em branco são permitidos no grupo de dimensão de rastreamento.</span><span class="sxs-lookup"><span data-stu-id="b9596-105">I can't move license plates that have serial number items when blank issue and blank receipt are allowed on the tracking dimension group.</span></span>

### <a name="issue-description"></a><span data-ttu-id="b9596-106">Descrição do problema</span><span class="sxs-lookup"><span data-stu-id="b9596-106">Issue description</span></span>

<span data-ttu-id="b9596-107">Você não consegue mover uma placa de licença usando um item de menu **Movimento** se o número de série tiver configurações de *Problema em branco permitido* e *Recibo em branco permitido* no grupo de dimensão de rastreamento e se houver várias placas no mesmo local, algumas das quais com números de série e outras sem.</span><span class="sxs-lookup"><span data-stu-id="b9596-107">You can't move a license plate by using a **Movement** menu item if the serial number has settings of *Blank issue allowed* and *Blank receipt allowed* on the tracking dimension group, and if there are multiple license plates in the same location, some of which have serial numbers and some of which don't have them.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="b9596-108">Resolução do problema</span><span class="sxs-lookup"><span data-stu-id="b9596-108">Issue resolution</span></span>

<span data-ttu-id="b9596-109">Esse problema será corrigido por mudanças que são implantadas no [KB 4571546](https://fix.lcs.dynamics.com/Issue/Details?kb=4571546&bugId=467880&dbType=3&qc=5b46d7faa9cc326cebfe9854cb30be8ea30b21ef33d3572c325fbb21202de687).</span><span class="sxs-lookup"><span data-stu-id="b9596-109">This issue will be fixed by changes that are deployed in [KB 4571546](https://fix.lcs.dynamics.com/Issue/Details?kb=4571546&bugId=467880&dbType=3&qc=5b46d7faa9cc326cebfe9854cb30be8ea30b21ef33d3572c325fbb21202de687).</span></span> <span data-ttu-id="b9596-110">Essas alterações tornarão o campo **Número de série** opcional quando recibo e emissão em branco forem permitidos.</span><span class="sxs-lookup"><span data-stu-id="b9596-110">Those changes will make the **Serial number** field optional when blank receipt and blank issue are allowed.</span></span>

## <a name="i-receive-the-following-error-message-in-the-warehouse-app-when-i-process-movements-the-inventory-owner-1-is-not-allowed-in-this-process"></a><span data-ttu-id="b9596-111">Recebo a seguinte mensagem de erro no aplicativo de depósito quando processo movimentos: "O proprietário do estoque %1 não é permitido neste processo."</span><span class="sxs-lookup"><span data-stu-id="b9596-111">I receive the following error message in the warehouse app when I process movements: "The inventory owner %1 is not allowed in this process."</span></span>

### <a name="issue-description"></a><span data-ttu-id="b9596-112">Descrição do problema</span><span class="sxs-lookup"><span data-stu-id="b9596-112">Issue description</span></span>

<span data-ttu-id="b9596-113">A dimensão de rastreamento do **Proprietário** está ausente quando o aplicativo de depósito é usado para fazer movimentos.</span><span class="sxs-lookup"><span data-stu-id="b9596-113">The **Owner** tracking dimension is missing when the warehouse app is used to make movements.</span></span> <span data-ttu-id="b9596-114">Um diário regular de transferência de estoque do cliente do Supply Chain Management parece funcionar conforme o esperado e pode ser lançado apenas se a dimensão do **Proprietário** for preenchida.</span><span class="sxs-lookup"><span data-stu-id="b9596-114">A regular inventory transfer journal from the Supply Chain Management client appears to work as intended and can be posted only if the **Owner** dimension is filled in.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="b9596-115">Resolução do problema</span><span class="sxs-lookup"><span data-stu-id="b9596-115">Issue resolution</span></span>

<span data-ttu-id="b9596-116">A Microsoft avaliou esse problema e determinou que é uma limitação de recurso.</span><span class="sxs-lookup"><span data-stu-id="b9596-116">Microsoft has evaluated this issue and has determined that it's a feature limitation.</span></span> <span data-ttu-id="b9596-117">Atualmente, os processos de gerenciamento de depósito oferecem suporte apenas ao estoque de propriedade da entidade legal.</span><span class="sxs-lookup"><span data-stu-id="b9596-117">Currently, warehouse management processes support only inventory that is owned by the legal entity.</span></span>
