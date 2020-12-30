---
title: Cartões-fidelidade do cliente e pontos de premiação
description: Este tópico descreve a integração de dados sobre cartões de fidelidade do cliente e pontos de recompensa em gravação dupla.
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
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-10
ms.openlocfilehash: 28872e9510394cf3d5cee151798d4130b8b6fe27
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4683489"
---
# <a name="customer-loyalty-cards-and-reward-points"></a><span data-ttu-id="7b3c3-103">Cartões-fidelidade do cliente e pontos de premiação</span><span class="sxs-lookup"><span data-stu-id="7b3c3-103">Customer loyalty cards and reward points</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="7b3c3-104">As empresas classificam os clientes e fornecem serviços sofisticados, com base nos padrões de compras e gastos dos clientes.</span><span class="sxs-lookup"><span data-stu-id="7b3c3-104">Businesses classify customers and provide sophisticated services, based on customer shopping and spending patterns.</span></span> <span data-ttu-id="7b3c3-105">Por exemplo, o Dynamics 365 Commerce tem a infraestrutura e as funções para facilitar e lidar com cartões de fidelidade do cliente, pontos de recompensa, preços com base na fidelidade e experiências de compra com base em recompensas.</span><span class="sxs-lookup"><span data-stu-id="7b3c3-105">For example, Dynamics 365 Commerce has the infrastructure and functions to facilitate and handle customer loyalty cards, reward points, loyalty-based pricing, and rewards-based shopping experiences.</span></span> <span data-ttu-id="7b3c3-106">Quando dados sobre cartões de fidelidade do cliente e pontos de recompensa no Commerce são sincronizados com o Dataverse, os aplicativos de participação do cliente podem usar esses dados.</span><span class="sxs-lookup"><span data-stu-id="7b3c3-106">When data about customer loyalty cards and reward points in Commerce is synced to Dataverse, customer engagement apps can use that data.</span></span> <span data-ttu-id="7b3c3-107">Por exemplo, os usuários do Dynamics 365 Customer Service podem usar os dados para fornecer os mesmos serviços sofisticados por meio do suporte técnico.</span><span class="sxs-lookup"><span data-stu-id="7b3c3-107">For example, Dynamics 365 Customer Service users can use the data to provide the same sophisticated services through the help desk.</span></span>

## <a name="templates"></a><span data-ttu-id="7b3c3-108">Modelos</span><span class="sxs-lookup"><span data-stu-id="7b3c3-108">Templates</span></span>

| <span data-ttu-id="7b3c3-109">Aplicativos Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="7b3c3-109">Finance and Operations apps</span></span> | <span data-ttu-id="7b3c3-110">Aplicativos controlados por modelos no Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="7b3c3-110">Model-driven apps in Dynamics 365</span></span> | <span data-ttu-id="7b3c3-111">descrição</span><span class="sxs-lookup"><span data-stu-id="7b3c3-111">Description</span></span> |
|-----------------------------|-----------------------------------|-------------|
| <span data-ttu-id="7b3c3-112">Cartão-fidelidade</span><span class="sxs-lookup"><span data-stu-id="7b3c3-112">Loyalty card</span></span>                | <span data-ttu-id="7b3c3-113">msdyn\_loyaltycards</span><span class="sxs-lookup"><span data-stu-id="7b3c3-113">msdyn\_loyaltycards</span></span>               | <span data-ttu-id="7b3c3-114">Este modelo sincroniza informações sobre cartões de fidelidade do cliente.</span><span class="sxs-lookup"><span data-stu-id="7b3c3-114">This template syncs information about customer loyalty cards.</span></span> |
| <span data-ttu-id="7b3c3-115">Pontos de premiação de fidelidade</span><span class="sxs-lookup"><span data-stu-id="7b3c3-115">Loyalty reward points</span></span>       | <span data-ttu-id="7b3c3-116">msdyn\_loyaltyrewardpoints</span><span class="sxs-lookup"><span data-stu-id="7b3c3-116">msdyn\_loyaltyrewardpoints</span></span>        | <span data-ttu-id="7b3c3-117">Este modelo sincroniza informações sobre pontos de recompensa do cliente.</span><span class="sxs-lookup"><span data-stu-id="7b3c3-117">This template syncs information about customer reward points.</span></span> |

[!include [banner](../../includes/dual-write-symbols.md)]

[!include [mapping loyalty card](includes/LoyaltyCard-msdyn-loyaltycards.md)]

[!include [mapping reward points](includes/LoyaltyRewardPoints-msdyn-loyaltyrewardpoints.md)]
