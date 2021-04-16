---
title: Aceitar usar classificações e opiniões
description: Este tópico explica como aceitar usar classificações e opiniões em seu site do Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 01/30/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: gmohanv
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 9e3f2a17e182c0e3efc8b90380eff74f350c3278
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5804640"
---
# <a name="opt-in-to-use-ratings-and-reviews"></a><span data-ttu-id="9ea27-103">Aceitar o uso das classificações e opiniões</span><span class="sxs-lookup"><span data-stu-id="9ea27-103">Opt in to use ratings and reviews</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="9ea27-104">Este tópico explica como aceitar usar classificações e opiniões em seu site do Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="9ea27-104">This topic explains how to opt in to use ratings and reviews on your Microsoft Dynamics 365 Commerce site.</span></span>

## <a name="overview"></a><span data-ttu-id="9ea27-105">Visão Geral</span><span class="sxs-lookup"><span data-stu-id="9ea27-105">Overview</span></span>

<span data-ttu-id="9ea27-106">A solução de classificações e revisões é uma solução de omni-channel que você pode disponibilizar no Dynamics 365 Commerce usando o Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="9ea27-106">The ratings and reviews solution is an omni-channel solution that you can make available in Dynamics 365 Commerce by using Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="9ea27-107">O LCS é um portal de administração que os fornecedores usam para gerenciar os ambientes desde o provisionamento até a desativação.</span><span class="sxs-lookup"><span data-stu-id="9ea27-107">LCS is an administration portal that retailers use to manage their environments from provisioning to decommissioning.</span></span>

<span data-ttu-id="9ea27-108">Se desejar usar a solução de classificações e revisões no site do Commerce, opte por classificações e revisões durante a implantação do seu site de comércio eletrônico no Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="9ea27-108">If you want to use the ratings and reviews solution on your Commerce website, you must opt in for ratings and reviews during deployment of your e-Commerce site on Dynamics 365 Commerce.</span></span>

## <a name="opt-in-to-use-ratings-and-reviews"></a><span data-ttu-id="9ea27-109">Aceitar usar classificações e opiniões</span><span class="sxs-lookup"><span data-stu-id="9ea27-109">Opt in to use ratings and reviews</span></span>

<span data-ttu-id="9ea27-110">Para aceitar usar as classificações e opiniões em seu site, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="9ea27-110">To opt in to use ratings and reviews on your site, follow these steps.</span></span>

1. <span data-ttu-id="9ea27-111">Siga as etapas em [Implantar um novo site de comércio eletrônico](deploy-ecommerce-site.md).</span><span class="sxs-lookup"><span data-stu-id="9ea27-111">Follow the steps in [Deploy a new e-Commerce site](deploy-ecommerce-site.md).</span></span>
1. <span data-ttu-id="9ea27-112">Enquanto ainda estiver no LCS, vá para **Configuração de implantação do Retail \> Outras configurações**.</span><span class="sxs-lookup"><span data-stu-id="9ea27-112">While you're still in LCS, go to **Retail deployment setup \> Other settings**.</span></span>
1. <span data-ttu-id="9ea27-113">Defina a opção **Habilitar serviço de classificações e opiniões** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="9ea27-113">Set the **Enable ratings and reviews service** option to **Yes**.</span></span>
1. <span data-ttu-id="9ea27-114">No campo **Grupo de segurança de DAA para moderador de classificações e opiniões (ID do objeto do grupo de segurança)** , insira a ID do grupo de segurança do Microsoft Azure Active Directory (Azure AD) que inclui moderadores de classificações e opiniões.</span><span class="sxs-lookup"><span data-stu-id="9ea27-114">In the **AAD security group for ratings and review moderator (security group object id)** field, enter the ID of the Microsoft Azure Active Directory (Azure AD) security group that includes the ratings and reviews moderators.</span></span>

    ![Aceitar usar classificações e opiniões](media/LCS_RnR_Preference.png)

1. <span data-ttu-id="9ea27-116">Conclua o processo de inicialização do comércio eletrônico.</span><span class="sxs-lookup"><span data-stu-id="9ea27-116">Complete the e-Commerce initialization process.</span></span>

> [!NOTE] 
> <span data-ttu-id="9ea27-117">Se você for um cliente existente do Dynamics 365 Commerce que já implantou um site de comércio eletrônico sem ter optado por classificações e revisões e desejar usar classificações e revisões do pacote do Dynamics 365 Commerce, envie uma solicitação de serviço.</span><span class="sxs-lookup"><span data-stu-id="9ea27-117">If you are an existing Dynamics 365 Commerce customer who has already deployed an e-Commerce site without having opted in for ratings and reviews and now want to use ratings and reviews from the Dynamics 365 Commerce package, please submit a service request.</span></span> <span data-ttu-id="9ea27-118">Para obter informações sobre como enviar uma solicitação de serviço, consulte o [processo de envio de solicitações de serviço](../fin-ops-core/dev-itpro/lifecycle-services/submit-request-dynamics-service-engineering-team.md?toc=/dynamics365/commerce/toc.json).</span><span class="sxs-lookup"><span data-stu-id="9ea27-118">For information about how to submit a service request, see [Submit service requests process](../fin-ops-core/dev-itpro/lifecycle-services/submit-request-dynamics-service-engineering-team.md?toc=/dynamics365/commerce/toc.json).</span></span> 

## <a name="additional-resources"></a><span data-ttu-id="9ea27-119">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="9ea27-119">Additional resources</span></span>

[<span data-ttu-id="9ea27-120">Visão geral de classificações e opiniões</span><span class="sxs-lookup"><span data-stu-id="9ea27-120">Ratings and reviews overview</span></span>](ratings-reviews-overview.md)

[<span data-ttu-id="9ea27-121">Gerenciar classificações e opiniões</span><span class="sxs-lookup"><span data-stu-id="9ea27-121">Manage ratings and reviews</span></span>](manage-reviews.md)

[<span data-ttu-id="9ea27-122">Configurar classificações e opiniões</span><span class="sxs-lookup"><span data-stu-id="9ea27-122">Configure ratings and reviews</span></span>](configure-ratings-reviews.md)

[<span data-ttu-id="9ea27-123">Sincronizar classificações de produto no Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="9ea27-123">Sync product ratings in Dynamics 365 Commerce</span></span>](sync-product-ratings.md)




[!INCLUDE[footer-include](../includes/footer-banner.md)]