---
title: Diversas transações de inventário para números de lote quando Mediante atualização física está desabilitado
description: Diversas transações de inventário são criadas quando você ajusta a linha do pedido de compra para itens em que a opção Mediante atualização física do grupo de número de lote está definida como Não.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: InventNumGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 1fa54cdfdbc5608fb6c7114dced0f96bab47253e
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026283"
---
# <a name="multiple-inventory-transactions-for-batch-numbers-when-on-physical-update-is-disabled"></a><span data-ttu-id="6a602-103">Diversas transações de inventário para números de lote quando Mediante atualização física está desabilitado</span><span class="sxs-lookup"><span data-stu-id="6a602-103">Multiple inventory transactions for batch numbers when On physical update is disabled</span></span>

<span data-ttu-id="6a602-104">Número da base de dados de conhecimento: 4613390</span><span class="sxs-lookup"><span data-stu-id="6a602-104">KB number: 4613390</span></span>

## <a name="symptoms"></a><span data-ttu-id="6a602-105">Sintomas</span><span class="sxs-lookup"><span data-stu-id="6a602-105">Symptoms</span></span>

<span data-ttu-id="6a602-106">Diversas transações de inventário são criadas quando você ajusta a linha do pedido de compra para itens em que a opção **Mediante atualização física** do grupo de número de lote está definida como *Não*.</span><span class="sxs-lookup"><span data-stu-id="6a602-106">Multiple inventory transactions are created after you adjust a purchase order line for items where the **On physical update** option of the batch number group is set to *No*.</span></span>

<span data-ttu-id="6a602-107">Quando você criar um item em que a opção **Mediante atualização física** do grupo de número de lote está definida como *Não*, o sistema cria automaticamente um novo número de lote se você modificar uma quantidade da linha de compra e salvar a página do pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="6a602-107">When you create an item where the **On physical update** option of the batch number group is set to *No*, the system automatically creates a new batch number if you modify a purchase line quantity and save the purchase order page.</span></span>

## <a name="resolution"></a><span data-ttu-id="6a602-108">Resolução</span><span class="sxs-lookup"><span data-stu-id="6a602-108">Resolution</span></span>

<span data-ttu-id="6a602-109">A configuração **Mediante atualização física** para os grupos de número de lote funciona da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="6a602-109">The **On physical update** setting for batch number groups works in the following way:</span></span>

- <span data-ttu-id="6a602-110">Quando a opção estiver definida como *Sim*, novos números de lote serão criados somente após uma atualização física (por exemplo, quanto os itens foram enviados ou recebidos).</span><span class="sxs-lookup"><span data-stu-id="6a602-110">When the option is set to *Yes*, new batch numbers are created only after a physical update (for example, when items are shipped or received).</span></span>
- <span data-ttu-id="6a602-111">Quando a opção estiver definida como *Não*, um novo número de lote será criado sempre que uma atualização aplicável ocorrer (por exemplo, quando uma nova quantidade for adicionada ao pedido de compra).</span><span class="sxs-lookup"><span data-stu-id="6a602-111">When the option is set to *No*, a new batch number is created every time that an applicable update occurs (for example, when a new quantity is added to a purchase order).</span></span>
