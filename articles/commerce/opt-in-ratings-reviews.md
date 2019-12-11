---
title: Aceitar usar classificações e opiniões
description: Este tópico explica como aceitar usar classificações e opiniões em seu site do Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
manager: annbe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: gmohanv
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 10e3c33af232fa46df09a103b2e73eae09a909eb
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/01/2019
ms.locfileid: "2697971"
---
# <a name="opt-in-to-use-ratings-and-reviews"></a><span data-ttu-id="e2622-103">Aceitar usar classificações e opiniões</span><span class="sxs-lookup"><span data-stu-id="e2622-103">Opt in to use ratings and reviews</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="e2622-104">Este tópico explica como aceitar usar classificações e opiniões em seu site do Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="e2622-104">This topic explains how to opt in to use ratings and reviews on your Microsoft Dynamics 365 Commerce site.</span></span>

## <a name="overview"></a><span data-ttu-id="e2622-105">Visão geral</span><span class="sxs-lookup"><span data-stu-id="e2622-105">Overview</span></span>

<span data-ttu-id="e2622-106">A solução de classificações e opiniões é uma solução do omnicanal que você pode disponibilizar no Dynamics 365 Commerce usando o Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="e2622-106">The ratings and reviews solution is an omnichannel solution that you can make available in Dynamics 365 Commerce by using Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="e2622-107">O LCS é um portal de administração que os fornecedores usam para gerenciar os ambientes desde o provisionamento até a desativação.</span><span class="sxs-lookup"><span data-stu-id="e2622-107">LCS is an administration portal that retailers use to manage their environments from provisioning to decommissioning.</span></span>

<span data-ttu-id="e2622-108">Se quiser usar a solução de classificações e opiniões em seu site de comércio eletrônico, primeiro você deverá aceitar.</span><span class="sxs-lookup"><span data-stu-id="e2622-108">If you want to use the ratings and reviews solution on your Commerce website, you must first opt in.</span></span>

## <a name="opt-in-to-use-ratings-and-reviews"></a><span data-ttu-id="e2622-109">Aceitar usar classificações e opiniões</span><span class="sxs-lookup"><span data-stu-id="e2622-109">Opt in to use ratings and reviews</span></span>

<span data-ttu-id="e2622-110">Para aceitar usar as classificações e opiniões em seu site, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="e2622-110">To opt in to use ratings and reviews on your site, follow these steps.</span></span>

1. <span data-ttu-id="e2622-111">Siga as etapas em [Implantar um novo site de comércio eletrônico](deploy-ecommerce-site.md).</span><span class="sxs-lookup"><span data-stu-id="e2622-111">Follow the steps in [Deploy a new e-Commerce site](deploy-ecommerce-site.md).</span></span>
1. <span data-ttu-id="e2622-112">Enquanto ainda estiver no LCS, vá para **Configuração de implantação do Retail \> Outras configurações**.</span><span class="sxs-lookup"><span data-stu-id="e2622-112">While you're still in LCS, go to **Retail deployment setup \> Other settings**.</span></span>
1. <span data-ttu-id="e2622-113">Defina a opção **Habilitar serviço de classificações e opiniões** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="e2622-113">Set the **Enable ratings and reviews service** option to **Yes**.</span></span>
1. <span data-ttu-id="e2622-114">No campo **Grupo de segurança de DAA para moderador de classificações e opiniões (ID do objeto do grupo de segurança)** , insira a ID do grupo de segurança do Microsoft Azure Active Directory (Azure AD) que inclui moderadores de classificações e opiniões.</span><span class="sxs-lookup"><span data-stu-id="e2622-114">In the **AAD security group for ratings and review moderator (security group object id)** field, enter the ID of the Microsoft Azure Active Directory (Azure AD) security group that includes the ratings and reviews moderators.</span></span>

    ![Aceitar usar classificações e opiniões](media/LCS_RnR_Preference.png)

1. <span data-ttu-id="e2622-116">Conclua o processo de inicialização do comércio eletrônico.</span><span class="sxs-lookup"><span data-stu-id="e2622-116">Complete the e-Commerce initialization process.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e2622-117">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="e2622-117">Additional resources</span></span>

[<span data-ttu-id="e2622-118">Visão geral de classificações e opiniões</span><span class="sxs-lookup"><span data-stu-id="e2622-118">Ratings and reviews overview</span></span>](ratings-reviews-overview.md)

[<span data-ttu-id="e2622-119">Gerenciar classificações e opiniões</span><span class="sxs-lookup"><span data-stu-id="e2622-119">Manage ratings and reviews</span></span>](manage-reviews.md)

[<span data-ttu-id="e2622-120">Configurar classificações e opiniões</span><span class="sxs-lookup"><span data-stu-id="e2622-120">Configure ratings and reviews</span></span>](configure-ratings-reviews.md)

[<span data-ttu-id="e2622-121">Sincronizar classificações de produto no Dynamics 365 Retail</span><span class="sxs-lookup"><span data-stu-id="e2622-121">Sync product ratings in Dynamics 365 Retail</span></span>](sync-product-ratings.md)
