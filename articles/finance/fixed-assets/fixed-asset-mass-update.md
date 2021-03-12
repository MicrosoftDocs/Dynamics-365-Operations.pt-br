---
title: Atualização em massa de ativos fixos
description: Ao usar registros, você poderá alterar as convenções de depreciação para grupos de ativos que fazem parte do mesmo registro.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 3521
ms.assetid: 50207ffb-6b89-4fb9-92e9-928bc0729489
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7ccccfd3168cf132453b41a74c57f4fd2629fb22
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4994881"
---
# <a name="fixed-asset-mass-update"></a><span data-ttu-id="3e45a-103">Atualização em massa de ativos fixos</span><span class="sxs-lookup"><span data-stu-id="3e45a-103">Fixed asset mass update</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="3e45a-104">Ao usar registros, você poderá alterar as convenções de depreciação para grupos de ativos que fazem parte do mesmo registro.</span><span class="sxs-lookup"><span data-stu-id="3e45a-104">If you use books, you can change the depreciation conventions for groups of assets that are part of the same book.</span></span>

<span data-ttu-id="3e45a-105">Por exemplo, se você estiver nos Estados Unidos e colocou mais de 40% de seus ativos em serviço durante o quarto trimestre do ano, você deverá usar a convenção de depreciação na metade do trimestre.</span><span class="sxs-lookup"><span data-stu-id="3e45a-105">For example, if you are in the United States, and you put more than 40 percent of your assets in service during the fourth quarter of the year, you must use the mid-quarter depreciation convention.</span></span> <span data-ttu-id="3e45a-106">Você pode usar o processo de uma atualização em massa para alterar todos os ativos que exigem a nova convenção de depreciação.</span><span class="sxs-lookup"><span data-stu-id="3e45a-106">You can use the process for a mass update to change all assets that require the new depreciation convention.</span></span> 

<span data-ttu-id="3e45a-107">Ao atualizar a convenção de depreciação para ativos, você exclui todas as transações de depreciação que existem para esses ativos.</span><span class="sxs-lookup"><span data-stu-id="3e45a-107">When you update the depreciation convention for assets, you delete all depreciation transactions that exist for those assets.</span></span> <span data-ttu-id="3e45a-108">Você também exclui todas as transações de ajustes de depreciação, transações de depreciação extra e transações de depreciação extraordinária para esses ativos.</span><span class="sxs-lookup"><span data-stu-id="3e45a-108">You also delete all transactions for depreciation adjustments, transactions for bonus depreciation, and transactions for extraordinary depreciation for those assets.</span></span> 

<span data-ttu-id="3e45a-109">Para atualizar a convenção de depreciação para ativos que já foram descartados, primeiro você deve excluir as transações de alienação existentes.</span><span class="sxs-lookup"><span data-stu-id="3e45a-109">To update the depreciation convention for assets that have already been disposed of, you must first delete the existing disposal transactions.</span></span> <span data-ttu-id="3e45a-110">Você também deve excluir todas as transações que foram geradas devido ao processo de alienação.</span><span class="sxs-lookup"><span data-stu-id="3e45a-110">You must also delete all transactions that were generated because of the disposal process.</span></span> 

<span data-ttu-id="3e45a-111">Após atualizar a convenção de depreciação para ativos, você poderá processar a depreciação e a depreciação extraordinária para cada ativo.</span><span class="sxs-lookup"><span data-stu-id="3e45a-111">After you update the depreciation convention for assets, you can process depreciation and extraordinary depreciation for each asset.</span></span> <span data-ttu-id="3e45a-112">Você também pode fazer ajustes de depreciação manuais, se qualquer ajuste for necessário.</span><span class="sxs-lookup"><span data-stu-id="3e45a-112">You can also make manual depreciation adjustments, if any adjustments are required.</span></span>





