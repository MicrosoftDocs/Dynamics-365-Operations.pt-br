---
title: Encargos diversos de gerenciamento de transporte
description: Este tópico explica como os encargos gerados pelo transporte devem ser associados a um código de encargo.
author: Henrikan
manager: tfehr
ms.date: 10/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2020-10-16
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 4f58db216176832d61bdafbe43831ededd3dd6dc
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5233406"
---
# <a name="transportation-management-miscellaneous-charges"></a><span data-ttu-id="0dfab-103">Encargos diversos de gerenciamento de transporte</span><span class="sxs-lookup"><span data-stu-id="0dfab-103">Transportation management miscellaneous charges</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0dfab-104">Como acontece com todos os encargos diversos, os encargos gerados pelo transporte devem ser associados a um código de encargo.</span><span class="sxs-lookup"><span data-stu-id="0dfab-104">As with all miscellaneous charges, transportation-generated charges must be associated with a charge code.</span></span> <span data-ttu-id="0dfab-105">Caso contrário, eles não serão adicionados de volta à ordem como um encargo diverso.</span><span class="sxs-lookup"><span data-stu-id="0dfab-105">Otherwise, they won't be added back to the order as a miscellaneous charge.</span></span> <span data-ttu-id="0dfab-106">O **Código de encargo** determina como a cobrança é contabilizada em relação à ordem e à linha de ordem em que é adicionada.</span><span class="sxs-lookup"><span data-stu-id="0dfab-106">The **Charges code** determines how the charge is accounted for in relation to the order and order line where it is added.</span></span>

<span data-ttu-id="0dfab-107">Acesse **Gerenciamento de transporte > Configurar > Classificação > Encargos diversos** para definir os critérios de qualificação que determinam quando um **Código de encargo** específico é aplicado a uma cobrança.</span><span class="sxs-lookup"><span data-stu-id="0dfab-107">Go to **Transportation management > Setup > Rating > Miscellaneous charges** to define the qualifying criteria that determine when a specific **Charges code** is applied to a charge.</span></span>

<span data-ttu-id="0dfab-108">Você deve ter pelo menos uma configuração para cada configuração **Módulo de encargo** relevante (*Cliente* e *Fornecedor*) em que **Tipo de encargo diverso** é definido como *Nenhum*.</span><span class="sxs-lookup"><span data-stu-id="0dfab-108">You should have at least one setup for each relevant **Charges module** setting (*Customer* and *Vendor*) where the **Miscellaneous charge type** is set to *None*.</span></span> <span data-ttu-id="0dfab-109">Se estiver faltando, o encargo diverso *não* será adicionada à ordem.</span><span class="sxs-lookup"><span data-stu-id="0dfab-109">If this is missing, the miscellaneous charge will *not* be added to the order.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]