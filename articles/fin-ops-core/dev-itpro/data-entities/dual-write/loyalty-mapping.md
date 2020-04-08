---
title: Cartões-fidelidade do cliente e pontos de premiação
description: Este tópico descreve a integração de dados sobre cartões de fidelidade do cliente e pontos de recompensa entre aplicativos do Finance and Operations e Common Data Service.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 03/10/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-10
ms.openlocfilehash: e7e67946930404ab7ba0c7fccf468722f723d675
ms.sourcegitcommit: 68f1485de7d64a6c9eba1088af63bd07992d972d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2020
ms.locfileid: "3172960"
---
# <a name="customer-loyalty-cards-and-reward-points"></a><span data-ttu-id="5d4ec-103">Cartões-fidelidade do cliente e pontos de premiação</span><span class="sxs-lookup"><span data-stu-id="5d4ec-103">Customer loyalty cards and reward points</span></span>

[!include [banner](../../includes/banner.md)]



<span data-ttu-id="5d4ec-104">As empresas classificam os clientes e fornecem serviços sofisticados, com base nos padrões de compras e gastos dos clientes.</span><span class="sxs-lookup"><span data-stu-id="5d4ec-104">Businesses classify customers and provide sophisticated services, based on customer shopping and spending patterns.</span></span> <span data-ttu-id="5d4ec-105">No conjunto de aplicativos do Microsoft Dynamics 365, o Dynamics 365 Commerce possui a infraestrutura e as funções para facilitar e lidar com cartões de fidelidade do cliente, pontos de recompensa, preços com base na fidelidade e experiências de compra com base em recompensas.</span><span class="sxs-lookup"><span data-stu-id="5d4ec-105">In the Microsoft Dynamics 365 suite of applications, Dynamics 365 Commerce has the infrastructure and functions to facilitate and handle customer loyalty cards, reward points, loyalty-based pricing, and rewards-based shopping experiences.</span></span> <span data-ttu-id="5d4ec-106">Quando dados sobre cartões de fidelidade do cliente e pontos de recompensa no Commerce são sincronizados com o Common Data Service, os aplicativos baseados em modelo no Dynamics 365 podem usar esses dados.</span><span class="sxs-lookup"><span data-stu-id="5d4ec-106">When data about customer loyalty cards and reward points in Commerce is synced to Common Data service, model-driven apps in Dynamics 365 can use that data.</span></span> <span data-ttu-id="5d4ec-107">Por exemplo, os usuários do Dynamics 365 Customer Service podem usar os dados para fornecer os mesmos serviços sofisticados por meio do suporte técnico.</span><span class="sxs-lookup"><span data-stu-id="5d4ec-107">For example, Dynamics 365 Customer Service users can use the data to provide the same sophisticated services through the help desk.</span></span>

## <a name="templates"></a><span data-ttu-id="5d4ec-108">Modelos</span><span class="sxs-lookup"><span data-stu-id="5d4ec-108">Templates</span></span>

| <span data-ttu-id="5d4ec-109">Aplicativos Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="5d4ec-109">Finance and Operations apps</span></span> | <span data-ttu-id="5d4ec-110">Aplicativos controlados por modelos no Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="5d4ec-110">Model-driven apps in Dynamics 365</span></span> | <span data-ttu-id="5d4ec-111">descrição</span><span class="sxs-lookup"><span data-stu-id="5d4ec-111">Description</span></span> |
|-----------------------------|-----------------------------------|-------------|
| <span data-ttu-id="5d4ec-112">Cartão-fidelidade</span><span class="sxs-lookup"><span data-stu-id="5d4ec-112">Loyalty card</span></span>                | <span data-ttu-id="5d4ec-113">msdyn\_loyaltycards</span><span class="sxs-lookup"><span data-stu-id="5d4ec-113">msdyn\_loyaltycards</span></span>               | <span data-ttu-id="5d4ec-114">Este modelo sincroniza informações sobre cartões de fidelidade do cliente.</span><span class="sxs-lookup"><span data-stu-id="5d4ec-114">This template syncs information about customer loyalty cards.</span></span> |
| <span data-ttu-id="5d4ec-115">Pontos de premiação de fidelidade</span><span class="sxs-lookup"><span data-stu-id="5d4ec-115">Loyalty reward points</span></span>       | <span data-ttu-id="5d4ec-116">msdyn\_loyaltyrewardpoints</span><span class="sxs-lookup"><span data-stu-id="5d4ec-116">msdyn\_loyaltyrewardpoints</span></span>        | <span data-ttu-id="5d4ec-117">Este modelo sincroniza informações sobre pontos de recompensa do cliente.</span><span class="sxs-lookup"><span data-stu-id="5d4ec-117">This template syncs information about customer reward points.</span></span> |

[!include [banner](../../includes/dual-write-symbols.md)]

[!include [mapping loyalty card](includes/LoyaltyCard-msdyn-loyaltycards.md)]

[!include [mapping reward points](includes/LoyaltyRewardPoints-msdyn-loyaltyrewardpoints.md)]
