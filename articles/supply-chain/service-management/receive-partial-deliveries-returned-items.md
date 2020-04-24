---
title: Receber entregas parciais de itens devolvidos
description: As entregas parciais são definidas em termos de linhas de ordem de devolução, não nas remessas de ordem de devolução.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2e33096abc8e4fd84f5c3c53ce4f62db9e4e0f03
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3211758"
---
# <a name="receive-partial-deliveries-of-returned-items"></a><span data-ttu-id="3e5cd-103">Receber entregas parciais de itens devolvidos</span><span class="sxs-lookup"><span data-stu-id="3e5cd-103">Receive partial deliveries of returned items</span></span>    

[!include [banner](../includes/banner.md)]


<span data-ttu-id="3e5cd-104">As entregas parciais são definidas em termos de linhas de ordem de devolução, não nas remessas de ordem de devolução.</span><span class="sxs-lookup"><span data-stu-id="3e5cd-104">Partial deliveries are defined in terms of return order lines, not return order shipments.</span></span>

<span data-ttu-id="3e5cd-105">Isso significa que se você receber a quantidade total indicada em uma linha da ordem de devolução, mas não receber nada das outras linhas da ordem, a entrega não é uma entrega parcial.</span><span class="sxs-lookup"><span data-stu-id="3e5cd-105">This means that if you receive the full quantity that is indicated on one return order line, but you receive nothing from the other lines in the return order, the delivery is not a partial delivery.</span></span> <span data-ttu-id="3e5cd-106">No entanto, se uma linha da ordem de devolução precisar de 10 unidades de um determinado item, mas somente quatro forem recebidos, trata-se de uma entrega parcial.</span><span class="sxs-lookup"><span data-stu-id="3e5cd-106">However, if a return order line requires 10 units of a particular item to be returned, but you receive only four, it is a partial delivery.</span></span>

<span data-ttu-id="3e5cd-107">Se uma remessa de devolução contém menos do que a quantidade total de uma linha da ordem de devolução, você pode reservar a remessa e aguardar até a chegada do resto da quantidade devolvida ou pode registrar e lançar a quantidade parcial.</span><span class="sxs-lookup"><span data-stu-id="3e5cd-107">If a return shipment contains less than the full quantity of a return order line, you can set the shipment aside and wait for the rest of the returned quantity to arrive, or you can register and post the partial quantity.</span></span>

## <a name="register-and-post-a-partial-quantity"></a><span data-ttu-id="3e5cd-108">Registrar e lançar uma quantidade parcial</span><span class="sxs-lookup"><span data-stu-id="3e5cd-108">Register and post a partial quantity</span></span>

1.  <span data-ttu-id="3e5cd-109">Depois de selecionar uma ordem de devolução para entrada no formulário **Visão geral de entrada - Depósito: %1, Doca: %2, Nome do diário: %3**, clique em **Iniciar entrada** para criar o diário de entrada, e clique em **Diários** \> **Mostrar entradas a partir de recebimentos** para abrir o formulário **Diário de localização**.</span><span class="sxs-lookup"><span data-stu-id="3e5cd-109">After you select a return order for arrival on the **Arrival overview - Warehouse: %1, Dock: %2, Journal name: %3** form, click **Start arrival** to create the arrival journal, and then click **Journals** \> **Show arrivals from receipts** to open the **Location journal** form.</span></span>

2.  <span data-ttu-id="3e5cd-110">Selecione a linha do diário com o qual deseja trabalhar e clique em **Linhas** para abrir o formulário **Linhas de diário, locais**.</span><span class="sxs-lookup"><span data-stu-id="3e5cd-110">Select the line of the journal that you want to work with, and then click **Lines** to open the **Journal lines, locations** form.</span></span>

3.  <span data-ttu-id="3e5cd-111">Selecione a linha do número de item para o qual apenas uma quantidade parcial foi recebida e clique em **Funções** \> **Separar** para abrir o formulário **Separar**.</span><span class="sxs-lookup"><span data-stu-id="3e5cd-111">Select the line of the item number for which only a partial quantity has arrived, and then click **Functions** \> **Split** to open the **Split** form.</span></span>

4.  <span data-ttu-id="3e5cd-112">No campo **Separar quantidade**, insira a quantidade do número total de itens recebidos e, em seguida, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="3e5cd-112">In the **Split quantity** field, enter the quantity for the total number of items that have been received, and then click **OK**.</span></span>

5.  <span data-ttu-id="3e5cd-113">No formulário **Linhas de diário, local**, selecione a linha para a quantidade de itens recebidos e clique em **Lançar**.</span><span class="sxs-lookup"><span data-stu-id="3e5cd-113">On the **Journal lines, locations** form, select the line for the quantity of items that has arrived, and then click **Post**.</span></span> <span data-ttu-id="3e5cd-114">É possível lançar a linha para a quantidade adicional após os itens chegarem.</span><span class="sxs-lookup"><span data-stu-id="3e5cd-114">You can post the line for the additional quantity after the items have arrived.</span></span>




