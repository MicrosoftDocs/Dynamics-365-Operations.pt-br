---
title: Aceitar usar classificações e opiniões
description: Este tópico explica como aceitar usar classificações e opiniões em seu site do Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 02/16/2020
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
ms.openlocfilehash: 19c3e8b32654f7c4b7803c547e9d5692f9fc461b
ms.sourcegitcommit: 4d52c67f52ad0add63cd905df61367b344389069
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/16/2022
ms.locfileid: "8311920"
---
# <a name="opt-in-to-use-ratings-and-reviews"></a>Aceitar o uso das classificações e opiniões

[!include [banner](includes/banner.md)]

Este tópico explica como aceitar usar classificações e opiniões em seu site do Microsoft Dynamics 365 Commerce.

A solução de classificações e revisões é uma solução de omni-channel que você pode disponibilizar no Dynamics 365 Commerce usando o Microsoft Dynamics Lifecycle Services (LCS). O LCS é um portal de administração que os fornecedores usam para gerenciar os ambientes desde o provisionamento até a desativação.

Se desejar usar a solução de classificações e revisões no site do Commerce, opte por classificações e revisões durante a implantação do seu site de comércio eletrônico no Dynamics 365 Commerce.

## <a name="opt-in-to-use-ratings-and-reviews"></a>Aceitar usar classificações e opiniões

Para aceitar usar as classificações e opiniões em seu site, siga estas etapas.

1. Siga as etapas em [Implantar um novo site de comércio eletrônico](deploy-ecommerce-site.md).
1. Enquanto ainda estiver no LCS, Acesse **Configuração de implantação do Retail \> Outras configurações**.
1. Defina a opção **Habilitar serviço de classificações e opiniões** como **Sim**.
1. No campo **Grupo de segurança de AAD para moderador de classificações e opiniões** , insira a ID do grupo de segurança do Microsoft Azure Active Directory (Azure AD) que inclui moderadores de classificações e opiniões.

    ![Aceitar o uso das classificações e opiniões.](media/LCS_RnR_Preference_2.png)

1. Conclua o processo de inicialização do comércio eletrônico.

> [!NOTE] 
> Se você for um cliente existente do Dynamics 365 Commerce que já implantou um site de comércio eletrônico sem ter optado por classificações e revisões e desejar usar classificações e revisões do pacote do Dynamics 365 Commerce, envie uma solicitação de serviço. Para obter informações sobre como enviar uma solicitação de serviço, consulte o [processo de envio de solicitações de serviço](../fin-ops-core/dev-itpro/lifecycle-services/submit-request-dynamics-service-engineering-team.md?toc=/dynamics365/commerce/toc.json). 

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral de classificações e opiniões](ratings-reviews-overview.md)

[Gerenciar classificações e opiniões](manage-reviews.md)

[Configurar classificações e opiniões](configure-ratings-reviews.md)

[Sincronizar classificações de produto no Dynamics 365 Commerce](sync-product-ratings.md)

[Habilitar a publicação manual de classificações e opiniões por um moderador](manual-publish-rating-reviews.md)

[Importar e exportar avaliações e revisões](import-export-reviews.md)

[Configurar autenticação de serviço a serviço](service-to-service-auth.md)

[Perguntas frequentes sobre classificações e opiniões](ratings-reviews-faq.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
