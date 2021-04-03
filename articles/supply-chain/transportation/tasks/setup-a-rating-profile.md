---
title: Perfis de classificação
description: Este tópico descreve como configurar dados para perfis de classificação.
author: Henrikan
manager: ''
ms.date: 10/30/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TMSRatingProfile
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: henrikan
ms.search.validFrom: 2020-10-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5f754a8b86b0d369af03812a831d77a8a6fa8154
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5233502"
---
# <a name="rating-profiles"></a><span data-ttu-id="da259-103">Perfis de classificação</span><span class="sxs-lookup"><span data-stu-id="da259-103">Rating profiles</span></span>

<span data-ttu-id="da259-104">Um perfil de classificação se assemelha a um contrato de logística (mas não a um contrato legal).</span><span class="sxs-lookup"><span data-stu-id="da259-104">A rating profile resembles a logistics contract (but not a legal contract).</span></span> <span data-ttu-id="da259-105">É usado para determinar as tarifas de transporte de cargas.</span><span class="sxs-lookup"><span data-stu-id="da259-105">It's used to determine transportation tariffs for loads.</span></span> 

<span data-ttu-id="da259-106">Cada perfil de classificação é exclusivo para uma transportadora.</span><span class="sxs-lookup"><span data-stu-id="da259-106">Each rating profile is unique to a shipping carrier.</span></span> <span data-ttu-id="da259-107">No perfil, você associa a transportadora a um mestre de taxa.</span><span class="sxs-lookup"><span data-stu-id="da259-107">In the profile, you associate the shipping carrier with a rate master.</span></span> <span data-ttu-id="da259-108">O mestre de taxa define a atribuição de base da taxa e a base de taxa.</span><span class="sxs-lookup"><span data-stu-id="da259-108">The rate master defines the rate base assignment and the rate base.</span></span> <span data-ttu-id="da259-109">A base da taxa determina a taxa da transportadora.</span><span class="sxs-lookup"><span data-stu-id="da259-109">The rate base determines the rate of the carrier.</span></span>

<span data-ttu-id="da259-110">Você pode configurar um perfil de classificação usando uma página genérica que mostra uma visão geral de todos os perfis de classificação existentes.</span><span class="sxs-lookup"><span data-stu-id="da259-110">You can set up a rating profile by using a generic page that shows an overview of all existing rating profiles.</span></span> <span data-ttu-id="da259-111">Como alternativa, você pode configurar um perfil de classificação diretamente da transportadora.</span><span class="sxs-lookup"><span data-stu-id="da259-111">Alternatively, you can set up a rating profile directly from the shipping carrier.</span></span> <span data-ttu-id="da259-112">Em ambos os casos, as informações que você configura para o perfil de classificação são as mesmas.</span><span class="sxs-lookup"><span data-stu-id="da259-112">In both cases, the information that you set up for the rating profile is the same.</span></span>

## <a name="create-or-edit-a-rating-profile-on-the-rating-profiles-page"></a><span data-ttu-id="da259-113">Criar ou editar um perfil de classificação na página Perfis de classificação</span><span class="sxs-lookup"><span data-stu-id="da259-113">Create or edit a rating profile on the Rating profiles page</span></span>

<span data-ttu-id="da259-114">Na página **Perfis de classificação**, você pode revisar todos os perfis de classificação disponíveis.</span><span class="sxs-lookup"><span data-stu-id="da259-114">On the **Rating profiles** page, you can review all available rating profiles.</span></span> <span data-ttu-id="da259-115">Você também pode editar perfis existentes e criar outros.</span><span class="sxs-lookup"><span data-stu-id="da259-115">You can also edit existing profiles and create new profiles.</span></span>

1. <span data-ttu-id="da259-116">Vá para **Gerenciamento de transporte \> Configurar \> Classificação \> Perfil de classificação**.</span><span class="sxs-lookup"><span data-stu-id="da259-116">Go to **Transportation management \> Setup \> Rating \> Rating profile**.</span></span>
1. <span data-ttu-id="da259-117">No Painel de Ações, selecione **Novo** para adicionar um novo perfil de classificação à grade ou selecione **Editar** para editar um perfil existente.</span><span class="sxs-lookup"><span data-stu-id="da259-117">On the Action Pane, select **New** to add a new rating profile to the grid, or select **Edit** to edit an existing profile.</span></span>
1. <span data-ttu-id="da259-118">Na linha do perfil de classificação novo ou existente, defina os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="da259-118">In the row for the new or existing rating profile, set the following fields:</span></span>

    - <span data-ttu-id="da259-119">**Perfil de classificação** - Insira um identificador (ID) exclusivo para o perfil de classificação.</span><span class="sxs-lookup"><span data-stu-id="da259-119">**Rating profile** – Enter a unique identifier (ID) for the rating profile.</span></span>
    - <span data-ttu-id="da259-120">**Nome** – Insira um nome descritivo para o perfil de classificação.</span><span class="sxs-lookup"><span data-stu-id="da259-120">**Name** – Enter a descriptive name for the rating profile.</span></span>
    - <span data-ttu-id="da259-121">**Transportadora** – Selecione uma transportadora.</span><span class="sxs-lookup"><span data-stu-id="da259-121">**Shipping carrier** – Select a shipping carrier.</span></span> <span data-ttu-id="da259-122">O perfil de classificação que você está configurando também será mostrado na página **Transportadoras** da transportadora selecionada.</span><span class="sxs-lookup"><span data-stu-id="da259-122">The rating profile that you're setting up will also be shown on the **Shipping carriers** page for the selected carrier.</span></span>
    - <span data-ttu-id="da259-123">**Local** e **Depósito** – Selecione um local e depósito.</span><span class="sxs-lookup"><span data-stu-id="da259-123">**Site** and **Warehouse** – Select a site and warehouse.</span></span>
    - <span data-ttu-id="da259-124">**Mecanismo de taxa** – Selecione o mecanismo de taxa para o perfil de classificação.</span><span class="sxs-lookup"><span data-stu-id="da259-124">**Rate engine** – Select the rate engine for the rating profile.</span></span>
    - <span data-ttu-id="da259-125">**Mestre de taxa** – Selecione o mestre de taxa para o perfil de classificação.</span><span class="sxs-lookup"><span data-stu-id="da259-125">**Rate master** – Select the rate master for the rating profile.</span></span> <span data-ttu-id="da259-126">Você pode usar o modelo de taxa para definir um tipo de base de taxa e uma base de taxa.</span><span class="sxs-lookup"><span data-stu-id="da259-126">You can use the rate master to define a rate base type and a rate base.</span></span> <span data-ttu-id="da259-127">Para obter mais informações, consulte [Configurar mestres de taxa](set-up-rate-masters.md).</span><span class="sxs-lookup"><span data-stu-id="da259-127">For more information, see [Set up rate masters](set-up-rate-masters.md).</span></span>
    - <span data-ttu-id="da259-128">**Mecanismo de tempo em trânsito** – Selecione o mecanismo de tempo de trânsito para o perfil de classificação.</span><span class="sxs-lookup"><span data-stu-id="da259-128">**Transit time engine** – Select the transit time engine for the rating profile.</span></span>
    - <span data-ttu-id="da259-129">**Índice de combustível da transportadora** – Selecione o índice de combustível da transportadora para o perfil de classificação.</span><span class="sxs-lookup"><span data-stu-id="da259-129">**Carrier fuel index** – Select the carrier fuel index for the rating profile.</span></span>
    - <span data-ttu-id="da259-130">**Data e hora de início de efetivação** e **Data e hora de término de efetivação** – Defina o período em que o perfil de classificação deve estar ativo.</span><span class="sxs-lookup"><span data-stu-id="da259-130">**Effect start date and time** and **Effective end date and time** – Define the period when the rating profile should be active.</span></span>

1. <span data-ttu-id="da259-131">No Painel de ações, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="da259-131">On the Action Pane, select **Save**.</span></span>

## <a name="create-a-rating-profile-directly-on-the-shipping-carriers-page"></a><span data-ttu-id="da259-132">Criar um perfil de classificação diretamente na página das transportadoras</span><span class="sxs-lookup"><span data-stu-id="da259-132">Create a rating profile directly on the Shipping carriers page</span></span>

1. <span data-ttu-id="da259-133">Vá para **Gerenciamento de transporte \> Configurar \> Transportadoras \> Transportadoras**.</span><span class="sxs-lookup"><span data-stu-id="da259-133">Go to **Transportation management \> Setup \> Carriers \> Shipping carriers**.</span></span>
1. <span data-ttu-id="da259-134">Selecione uma transportadora na lista.</span><span class="sxs-lookup"><span data-stu-id="da259-134">Select a shipping carrier in the list.</span></span>
1. <span data-ttu-id="da259-135">Na FastTab **Perfis de classificação**, selecione **Novo** para criar um perfil de classificação.</span><span class="sxs-lookup"><span data-stu-id="da259-135">On the **Rating profiles** FastTab, select **New** to create a rating profile.</span></span>
1. <span data-ttu-id="da259-136">Defina os campos para o novo perfil de classificação.</span><span class="sxs-lookup"><span data-stu-id="da259-136">Set the fields for the new rating profile.</span></span> <span data-ttu-id="da259-137">Esses campos correspondem aos campos da página **Perfis de classificação**, conforme descrito na seção anterior deste tópico.</span><span class="sxs-lookup"><span data-stu-id="da259-137">These fields correspond to the fields on the **Rating profiles** page, as described in previous section of this topic.</span></span>

> [!NOTE]
> <span data-ttu-id="da259-138">Os perfis criados na página **Transportadoras** também são exibidos na página **Perfis de classificação**.</span><span class="sxs-lookup"><span data-stu-id="da259-138">Profiles that are created on the **Shipping carriers** page are also shown on the **Rating profiles** page.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]