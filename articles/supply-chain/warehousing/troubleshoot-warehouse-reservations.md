---
title: Solucionar problemas de reservas no gerenciamento de depósito
description: Este tópico descreve como corrigir problemas comuns que você pode encontrar ao trabalhar com reservas de depósito no Microsoft Dynamics 365 Supply Chain Management.
author: perlynne
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: d0d73396772ed9e8397797d6685fb550d911303b
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5828097"
---
# <a name="troubleshoot-reservations-in-warehouse-management"></a><span data-ttu-id="6b052-103">Solucionar problemas de reservas no gerenciamento de depósito</span><span class="sxs-lookup"><span data-stu-id="6b052-103">Troubleshoot reservations in warehouse management</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6b052-104">Este tópico descreve como corrigir problemas comuns que você pode encontrar ao trabalhar com reservas de depósito no Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="6b052-104">This topic describes how to fix common issues that you might encounter while you work with warehouse reservations in Microsoft Dynamics 365 Supply Chain Management.</span></span>

<span data-ttu-id="6b052-105">Para os tópicos relacionados a registros de número de série e do lote, consulte [Solucionar problemas de reserva de números de série e do lote do depósito](troubleshoot-warehouse-batch-and-serial-reservation-hierarchies.md).</span><span class="sxs-lookup"><span data-stu-id="6b052-105">For topics that are related to batch and serial number registrations, see [Troubleshoot warehouse batch and serial reservation hierarchies](troubleshoot-warehouse-batch-and-serial-reservation-hierarchies.md).</span></span>

## <a name="i-receive-the-following-error-message-reservations-cannot-be-removed-because-there-is-work-created-which-relies-on-the-reservations"></a><span data-ttu-id="6b052-106">Recebo a seguinte mensagem de erro: "As reservas não podem ser removidas porque há um trabalho criado com base nas reservas."</span><span class="sxs-lookup"><span data-stu-id="6b052-106">I receive the following error message: "Reservations cannot be removed because there is work created which relies on the reservations."</span></span>

### <a name="issue-description"></a><span data-ttu-id="6b052-107">Descrição do problema</span><span class="sxs-lookup"><span data-stu-id="6b052-107">Issue description</span></span>

<span data-ttu-id="6b052-108">Não é possível cancelar a reserva de estoque em uma linha de vendas, porque há trabalho aberto em relação à linha.</span><span class="sxs-lookup"><span data-stu-id="6b052-108">You can't unreserve inventory on a sales line, because there is open work against the line.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="6b052-109">Resolução do problema</span><span class="sxs-lookup"><span data-stu-id="6b052-109">Issue resolution</span></span>

<span data-ttu-id="6b052-110">Investigue se existe trabalho de grupo de embalagem aberto para mudar o item de uma estação de embalagem para outro local (como *Baydoor*).</span><span class="sxs-lookup"><span data-stu-id="6b052-110">Investigate whether open packing group work exists to bring the item from a packing station to another location (such as *Baydoor*).</span></span> <span data-ttu-id="6b052-111">Revise os registros nas páginas **Log de histórico de criação de trabalho** e **Detalhes do trabalho** para determinar o que está reservando fisicamente o estoque e, depois, conclua ou exclua o trabalho para liberar a reserva.</span><span class="sxs-lookup"><span data-stu-id="6b052-111">Review the records on the **Work creation history log** and **Work details** pages to determine what is physically reserving the inventory, and then complete or delete the work to free up the reservation.</span></span>

## <a name="i-receive-the-following-error-message-inventory-quantity--1-could-not-be-updated-due-to-insufficient-inventory-transactions-for-item-2"></a><span data-ttu-id="6b052-112">Recebo a seguinte mensagem de erro: "A quantidade em estoque -%1 não pôde ser atualizada em razão de transações de estoque insuficientes para o item %2...."</span><span class="sxs-lookup"><span data-stu-id="6b052-112">I receive the following error message: "Inventory quantity -%1 could not be updated due to insufficient inventory transactions for item %2...."</span></span>

### <a name="issue-description"></a><span data-ttu-id="6b052-113">Descrição do problema</span><span class="sxs-lookup"><span data-stu-id="6b052-113">Issue description</span></span>

<span data-ttu-id="6b052-114">Esse problema pode ocorrer se o sistema não puder atualizar uma quantidade de estoque porque não há transações de estoque suficientes com as dimensões especificadas.</span><span class="sxs-lookup"><span data-stu-id="6b052-114">This issue can occur if the system can't update an inventory quantity because there aren't enough inventory transactions that have the specified dimensions.</span></span> <span data-ttu-id="6b052-115">Aqui está o texto completo da mensagem de erro completa:</span><span class="sxs-lookup"><span data-stu-id="6b052-115">Here is the full text of the full error message:</span></span>

> <span data-ttu-id="6b052-116">A quantidade de estoque -%1 não pôde ser atualizada em razão de transações de estoque insuficientes para o item %2 com dimensões de Tamanho = %3, Cor = %4, Adições = %5, Local = %6, Depósito = %7, Local = %8, Status do estoque = Disponível, Placa de licença = %9, Número do lote = %10 para a ID de referência %11 na ID de lote %12.</span><span class="sxs-lookup"><span data-stu-id="6b052-116">Inventory quantity -%1 could not be updated due to insufficient inventory transactions for item %2 with dimensions Size=%3, Color=%4, Additions=%5, Site=%6, Warehouse=%7, Location=%8, Inventory status=Available, License plate=%9, Batch number=%10 for reference ID %11 on Lot ID %12.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="6b052-117">Resolução do problema</span><span class="sxs-lookup"><span data-stu-id="6b052-117">Issue resolution</span></span>

<span data-ttu-id="6b052-118">Certifique-se de que nenhuma transação de estoque esteja reservando fisicamente a quantidade.</span><span class="sxs-lookup"><span data-stu-id="6b052-118">Make sure that no inventory transactions are physically reserving the quantity.</span></span> <span data-ttu-id="6b052-119">Por exemplo, essas transações podem abrir ordens de qualidade, registros de bloqueio de estoque ou ordens de saída.</span><span class="sxs-lookup"><span data-stu-id="6b052-119">For example, these transactions might open quality orders, inventory blocking records, or output orders.</span></span>

## <a name="i-receive-the-following-error-message-physical-on-handcannot-be-reserved-because-only-000-are-available-in-the-inventory"></a><span data-ttu-id="6b052-120">Recebo a seguinte mensagem de erro: "Físico disponível... não pode ser reservado porque apenas 0,00 estão disponíveis no estoque."</span><span class="sxs-lookup"><span data-stu-id="6b052-120">I receive the following error message: "Physical on-hand...cannot be reserved because only 0.00 are available in the inventory."</span></span>

### <a name="issue-description"></a><span data-ttu-id="6b052-121">Descrição do problema</span><span class="sxs-lookup"><span data-stu-id="6b052-121">Issue description</span></span>

<span data-ttu-id="6b052-122">Esse problema pode ocorrer se o sistema não puder atualizar uma quantidade de estoque porque não há transações de estoque suficientes com as dimensões especificadas.</span><span class="sxs-lookup"><span data-stu-id="6b052-122">This issue can occur if the system can't update an inventory quantity because there aren't enough inventory transactions that have the specified dimensions.</span></span> <span data-ttu-id="6b052-123">Aqui está o texto completo da mensagem de erro completa:</span><span class="sxs-lookup"><span data-stu-id="6b052-123">Here is the full text of the full error message:</span></span>

> <span data-ttu-id="6b052-124">Físico disponível Local = %1, Depósito = %2, Status do estoque = Disponível, Nº do lote = %3, Proprietário = %4: %5 não pode ser reservado porque somente 0,00 está disponível no estoque.</span><span class="sxs-lookup"><span data-stu-id="6b052-124">Physical on-hand Site=%1, Warehouse=%2, Inventory status=Available, Batch number=%3, Owner=%4: %5 cannot be reserved because only 0.00 are available in the inventory.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="6b052-125">Resolução do problema</span><span class="sxs-lookup"><span data-stu-id="6b052-125">Issue resolution</span></span>

<span data-ttu-id="6b052-126">Esse problema é provavelmente causado por um trabalho aberto.</span><span class="sxs-lookup"><span data-stu-id="6b052-126">This issue is probably caused by open work.</span></span> <span data-ttu-id="6b052-127">Conclua a obra ou receba sem criação de trabalho.</span><span class="sxs-lookup"><span data-stu-id="6b052-127">Either complete the work or receive without work creation.</span></span> <span data-ttu-id="6b052-128">Certifique-se de que nenhuma transação de estoque esteja reservando fisicamente a quantidade.</span><span class="sxs-lookup"><span data-stu-id="6b052-128">Make sure that no inventory transactions are physically reserving the quantity.</span></span> <span data-ttu-id="6b052-129">Por exemplo, essas transações podem abrir ordens de qualidade, registros de bloqueio de estoque ou ordens de saída.</span><span class="sxs-lookup"><span data-stu-id="6b052-129">For example, these transactions might be open quality orders, inventory blocking records, or output orders.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
