---
title: Resolver problemas de operações de depósito de saída
description: Este tópico descreve como corrigir problemas comuns que você pode encontrar ao trabalhar com operações de depósito de saída no Microsoft Dynamics 365 Supply Chain Management.
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
ms.openlocfilehash: 1344a1c16bf72b31f7aaf18aaeb6e08c7bc9d87e
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5223257"
---
# <a name="troubleshoot-outbound-warehouse-operations"></a><span data-ttu-id="a122e-103">Resolver problemas de operações de depósito de saída</span><span class="sxs-lookup"><span data-stu-id="a122e-103">Troubleshoot outbound warehouse operations</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a122e-104">Este tópico descreve como corrigir problemas comuns que você pode encontrar ao trabalhar com operações de depósito de saída no Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="a122e-104">This topic describes how to fix common issues that you might encounter while you work with outbound warehouse operations in Microsoft Dynamics 365 Supply Chain Management.</span></span>

## <a name="i-receive-the-following-error-message-sales-order-could-not-be-released"></a><span data-ttu-id="a122e-105">Recebo a seguinte mensagem de erro: "Não foi possível liberar a ordem de venda."</span><span class="sxs-lookup"><span data-stu-id="a122e-105">I receive the following error message: "Sales order could not be released."</span></span>

### <a name="issue-description"></a><span data-ttu-id="a122e-106">Descrição do problema</span><span class="sxs-lookup"><span data-stu-id="a122e-106">Issue description</span></span>

<span data-ttu-id="a122e-107">Esse problema pode ocorrer por vários motivos.</span><span class="sxs-lookup"><span data-stu-id="a122e-107">This issue can occur for several reasons.</span></span> <span data-ttu-id="a122e-108">Por exemplo, a ordem está em espera de gerenciamento de crédito e nenhuma remessa pode ser criada até que um endereço postal válido seja inserido para todas as linhas de vendas associadas a uma ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="a122e-108">For example, the order is on credit management hold, and no shipments can be created until a valid postal address is entered for all sales lines that are associated with a sales order.</span></span> <span data-ttu-id="a122e-109">Como alternativa, há um bloqueio de ordem que deve ser resolvido antes que a ordem possa ser liberada para o depósito.</span><span class="sxs-lookup"><span data-stu-id="a122e-109">Alternatively, there is an order hold that must be addressed before the order can be released to the warehouse.</span></span> <span data-ttu-id="a122e-110">Esse bloqueio pode ser específico da ordem ou pode ocorrer na conta do cliente.</span><span class="sxs-lookup"><span data-stu-id="a122e-110">This hold might be order-specific, or it might be on the customer account.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="a122e-111">Resolução do problema</span><span class="sxs-lookup"><span data-stu-id="a122e-111">Issue resolution</span></span>

<span data-ttu-id="a122e-112">Adicione ou atualize o endereço na ordem de venda e nas linhas de ordem e, depois, libere a ordem para o depósito.</span><span class="sxs-lookup"><span data-stu-id="a122e-112">Add or update the address on the sales order and order lines, and then release the order to the warehouse.</span></span> <span data-ttu-id="a122e-113">As ordens podem ser liberadas para o depósito somente se elas tiverem um endereço de entrega válido (de acordo com a configuração do formato de endereço no módulo **Administração da organização**).</span><span class="sxs-lookup"><span data-stu-id="a122e-113">Orders can be released to the warehouse only if they have a valid delivery address (per the address format setup in the **Organization administration** module).</span></span>

<span data-ttu-id="a122e-114">Investigue o bloqueio da ordem e resolva os problemas.</span><span class="sxs-lookup"><span data-stu-id="a122e-114">Investigate the order hold, and address the issues.</span></span> <span data-ttu-id="a122e-115">Depois, remova o bloqueio da ordem ou do cliente e libere a ordem no depósito.</span><span class="sxs-lookup"><span data-stu-id="a122e-115">Then remove the hold from the order or customer, and release the order to the warehouse.</span></span>

## <a name="i-receive-the-following-message-the-shipment-for-load-1-has-been-confirmed-however-no-lines-are-posted"></a><span data-ttu-id="a122e-116">Recebo a seguinte mensagem: "A remessa para carga 1% foi confirmada."</span><span class="sxs-lookup"><span data-stu-id="a122e-116">I receive the following message: "The shipment for load 1% has been confirmed."</span></span> <span data-ttu-id="a122e-117">Contudo, nenhuma linha é lançada.</span><span class="sxs-lookup"><span data-stu-id="a122e-117">However, no lines are posted.</span></span>

### <a name="issue-description"></a><span data-ttu-id="a122e-118">Descrição do problema</span><span class="sxs-lookup"><span data-stu-id="a122e-118">Issue description</span></span>

<span data-ttu-id="a122e-119">Uma remessa em uma carga foi confirmada, mas nenhum lançamento adicional ocorreu.</span><span class="sxs-lookup"><span data-stu-id="a122e-119">A shipment on a load was confirmed, but no further posting occurred.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="a122e-120">Resolução do problema</span><span class="sxs-lookup"><span data-stu-id="a122e-120">Issue resolution</span></span>

<span data-ttu-id="a122e-121">A confirmação da remessa não afeta o lançamento.</span><span class="sxs-lookup"><span data-stu-id="a122e-121">Shipment confirmation doesn't affect posting.</span></span> <span data-ttu-id="a122e-122">Ela apenas atualiza a remessa e o status da carga.</span><span class="sxs-lookup"><span data-stu-id="a122e-122">It just updates the shipment and load status.</span></span> <span data-ttu-id="a122e-123">O lançamento deve ocorrer em um processo separado.</span><span class="sxs-lookup"><span data-stu-id="a122e-123">Posting must occur in a separate process.</span></span>

## <a name="i-receive-the-following-error-message-direct-delivery-is-not-able-to-process-for-warehouse-1-as-it-has-warehouse-management-enabled-please-specify-another-warehouse-that-is-not-enabled-for-warehouse-management"></a><span data-ttu-id="a122e-124">Recebo a seguinte mensagem de erro: "A entrega direta não é capaz de processar para o depósito 1% porque tem o gerenciamento do depósito habilitado.</span><span class="sxs-lookup"><span data-stu-id="a122e-124">I receive the following error message: "Direct delivery is not able to process for warehouse 1% as it has warehouse management enabled.</span></span> <span data-ttu-id="a122e-125">Especifique outro depósito que não esteja habilitado para gerenciamento de depósito."</span><span class="sxs-lookup"><span data-stu-id="a122e-125">Please specify another warehouse that is not enabled for warehouse management."</span></span>

### <a name="issue-description"></a><span data-ttu-id="a122e-126">Descrição do problema</span><span class="sxs-lookup"><span data-stu-id="a122e-126">Issue description</span></span>

<span data-ttu-id="a122e-127">Um item é adicionado a uma linha de vendas para entrega direta de um depósito habilitado para gerenciamento de depósito (WMS).</span><span class="sxs-lookup"><span data-stu-id="a122e-127">An item is added to a sales line for direct delivery from a warehouse that is enabled for warehouse management (WMS).</span></span> <span data-ttu-id="a122e-128">Você recebe essa mensagem de erro quando a linha de vendas é atualizada.</span><span class="sxs-lookup"><span data-stu-id="a122e-128">You receive this error message when the sales line is updated.</span></span> 

### <a name="issue-resolution"></a><span data-ttu-id="a122e-129">Resolução do problema</span><span class="sxs-lookup"><span data-stu-id="a122e-129">Issue resolution</span></span>

<span data-ttu-id="a122e-130">A Microsoft avaliou esse problema e determinou que é uma limitação de recurso.</span><span class="sxs-lookup"><span data-stu-id="a122e-130">Microsoft has evaluated this issue and has determined that it's a feature limitation.</span></span> <span data-ttu-id="a122e-131">Atualmente, o WMS não oferece suporte para entrega direta.</span><span class="sxs-lookup"><span data-stu-id="a122e-131">Currently, WMS doesn't support direct delivery.</span></span> <span data-ttu-id="a122e-132">Portanto, para usar a entrega direta, você deve selecionar um item e depósito que não é WMS.</span><span class="sxs-lookup"><span data-stu-id="a122e-132">Therefore, to use direct delivery, you must select a non-WMS item and warehouse.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]