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
# <a name="opt-in-to-use-ratings-and-reviews"></a>Aceitar usar classificações e opiniões

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Este tópico explica como aceitar usar classificações e opiniões em seu site do Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visão geral

A solução de classificações e opiniões é uma solução do omnicanal que você pode disponibilizar no Dynamics 365 Commerce usando o Microsoft Dynamics Lifecycle Services (LCS). O LCS é um portal de administração que os fornecedores usam para gerenciar os ambientes desde o provisionamento até a desativação.

Se quiser usar a solução de classificações e opiniões em seu site de comércio eletrônico, primeiro você deverá aceitar.

## <a name="opt-in-to-use-ratings-and-reviews"></a>Aceitar usar classificações e opiniões

Para aceitar usar as classificações e opiniões em seu site, siga estas etapas.

1. Siga as etapas em [Implantar um novo site de comércio eletrônico](deploy-ecommerce-site.md).
1. Enquanto ainda estiver no LCS, vá para **Configuração de implantação do Retail \> Outras configurações**.
1. Defina a opção **Habilitar serviço de classificações e opiniões** como **Sim**.
1. No campo **Grupo de segurança de DAA para moderador de classificações e opiniões (ID do objeto do grupo de segurança)** , insira a ID do grupo de segurança do Microsoft Azure Active Directory (Azure AD) que inclui moderadores de classificações e opiniões.

    ![Aceitar usar classificações e opiniões](media/LCS_RnR_Preference.png)

1. Conclua o processo de inicialização do comércio eletrônico.

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral de classificações e opiniões](ratings-reviews-overview.md)

[Gerenciar classificações e opiniões](manage-reviews.md)

[Configurar classificações e opiniões](configure-ratings-reviews.md)

[Sincronizar classificações de produto no Dynamics 365 Retail](sync-product-ratings.md)
