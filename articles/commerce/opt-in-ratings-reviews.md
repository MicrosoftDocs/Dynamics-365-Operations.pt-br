---
title: Aceitar usar classificações e opiniões
description: Este tópico explica como aceitar usar classificações e opiniões em seu site do Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
manager: annbe
ms.date: 01/30/2020
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
ms.openlocfilehash: cbdb69202ebec19f4442041cfb1f99857da36d2e
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4410197"
---
# <a name="opt-in-to-use-ratings-and-reviews"></a>Aceitar usar classificações e opiniões

[!include [banner](includes/banner.md)]

Este tópico explica como aceitar usar classificações e opiniões em seu site do Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visão geral

A solução de classificações e revisões é uma solução de omni-channel que você pode disponibilizar no Dynamics 365 Commerce usando o Microsoft Dynamics Lifecycle Services (LCS). O LCS é um portal de administração que os fornecedores usam para gerenciar os ambientes desde o provisionamento até a desativação.

Se desejar usar a solução de classificações e revisões no site do Commerce, opte por classificações e revisões durante a implantação do seu site de comércio eletrônico no Dynamics 365 Commerce.

## <a name="opt-in-to-use-ratings-and-reviews"></a>Aceitar usar classificações e opiniões

Para aceitar usar as classificações e opiniões em seu site, siga estas etapas.

1. Siga as etapas em [Implantar um novo site de comércio eletrônico](deploy-ecommerce-site.md).
1. Enquanto ainda estiver no LCS, vá para **Configuração de implantação do Retail \> Outras configurações**.
1. Defina a opção **Habilitar serviço de classificações e opiniões** como **Sim**.
1. No campo **Grupo de segurança de DAA para moderador de classificações e opiniões (ID do objeto do grupo de segurança)** , insira a ID do grupo de segurança do Microsoft Azure Active Directory (Azure AD) que inclui moderadores de classificações e opiniões.

    ![Aceitar usar classificações e opiniões](media/LCS_RnR_Preference.png)

1. Conclua o processo de inicialização do comércio eletrônico.

> [!NOTE] 
> Se você for um cliente existente do Dynamics 365 Commerce que já implantou um site de comércio eletrônico sem ter optado por classificações e revisões e desejar usar classificações e revisões do pacote do Dynamics 365 Commerce, envie uma solicitação de serviço. Para obter informações sobre como enviar uma solicitação de serviço, consulte o [processo de envio de solicitações de serviço](../fin-ops-core/dev-itpro/lifecycle-services/submit-request-dynamics-service-engineering-team.md?toc=/dynamics365/commerce/toc.json). 

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral de classificações e opiniões](ratings-reviews-overview.md)

[Gerenciar classificações e opiniões](manage-reviews.md)

[Configurar classificações e opiniões](configure-ratings-reviews.md)

[Sincronizar classificações de produto no Dynamics 365 Commerce](sync-product-ratings.md)




[!INCLUDE[footer-include](../includes/footer-banner.md)]