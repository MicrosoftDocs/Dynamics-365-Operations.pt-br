---
title: Importar e exportar classificações e opiniões
description: Este tópico descreve como importar e exportar classificações e opiniões de produtos no Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 01/12/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgri
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: 3ae85f21f7a78d56621aed60527207badcee9c75
ms.sourcegitcommit: 7adf9ad53b4e6d1c4d5d612ce0977b76c61ec173
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/13/2022
ms.locfileid: "7968509"
---
# <a name="import-and-export-ratings-and-reviews"></a>Importar e exportar classificações e opiniões

[!include [banner](includes/banner.md)]

Este tópico descreve como importar e exportar classificações e opiniões de produtos no Microsoft Dynamics 365 Commerce.

Ofertas do Dynamics 365 Commerce [classificações e opiniões](ratings-reviews-overview.md) como uma solução omni-channel. Ao alternar para a solução de classificações e opiniões do Dynamics 365 Commerce, talvez você queira mover os dados das classificações e opiniões existentes para a plataforma do Commerce. Você também pode desejar exportar dados de classificações e opiniões do Commerce, com base em suas necessidades comerciais. Um conector do Power Automate permite importar classificações e opiniões para o Commerce e exportá-las do Commerce.

> [!NOTE]
> Para obter informações sobre a introdução aos fluxos lógicos no Power Automate, consulte [Criar um fluxo da nuvem no Power Automate](/power-automate/get-started-logic-flow).

## <a name="prerequisites"></a>Pré-requisitos

Antes de poder importar e exportar classificações e opiniões, você deve preencher os seguintes pré-requisitos:

- A solução de classificações e opiniões deve estar habilitada para seu site de comércio eletrônico na plataforma do Commerce. Para obter mais informações, consulte [Aceitar o uso de classificações e opiniões](opt-in-ratings-reviews.md).
- O conector Dynamics 365 Ratings and Reviews do Power App deve ser configurado para habilitar as ações "enviar opiniões" ou "exportar opiniões" no Power Automate. Para obter mais informações, consulte [Dynamics 365 Commerce - Ratings and Reviews (versão preliminar)](/connectors/dynamics365ratingsre/).
- A autenticação S2S (Serviço a Serviço) deve ser configurada para chamar com segurança a classificação e revisar a API (interface de programação de aplicativo) fora do Commerce. Para obter mais informações, consulte [Configurar a autenticação Serviço a Serviço](service-to-service-auth.md).

## <a name="import-ratings-and-reviews"></a>Importar classificações e opiniões

Para importar dados de classificações e opiniões do sistema existente para o Commerce, você deverá adicionar o conector Dynamics 365 Ratings and Review do Power Automate a um fluxo existente do Power Automate ou a um novo. Para obter mais informações, consulte [Dynamics 365 Commerce - Ratings and Reviews (versão preliminar)](/connectors/dynamics365ratingsre/).

> [!IMPORTANT]
> Antes de concluir este procedimento, você deverá [configurar a autenticação S2S](service-to-service-auth.md).

Para importar classificações e opiniões para o Commerce usando o conector Dynamics 365 Ratings and Reviews do Power Automate, siga estas etapas.

1. Selecione a ação **Enviar Opinião do Usuário**.
1. Estabeleça uma conexão usando as informações do aplicativo do Azure AD (Azure Active Directory) criadas quando você configurou a autenticação S2S. Para obter mais informações, consulte [Configurar a autenticação serviço a serviço](service-to-service-auth.md).
1. A ação **Enviar Opinião do Usuário** usa uma opinião de cada vez. Portanto, repita a ação. Use as opiniões de origem como uma lista para enviar opiniões em massa.
    
## <a name="export-ratings-and-reviews"></a>Exportar classificações e opiniões

Para exportar dados de classificações e opiniões do Commerce, você deverá adicionar o conector Dynamics 365 Ratings and Review do Power Automate a um fluxo existente do Power Automate ou a um novo. Para obter mais informações, consulte [Dynamics 365 Commerce - Ratings and Reviews (versão preliminar)](/connectors/dynamics365ratingsre/).

Para exportar classificações e opiniões do Commerce usando o conector Dynamics 365 Ratings and Reviews do Power Automate, siga estas etapas.

1. Selecione a ação **Exportar Todas as Opiniões**.
1. Conclua a ação. 

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral de classificações e opiniões](ratings-reviews-overview.md)

[Aceitar o uso das classificações e opiniões](opt-in-ratings-reviews.md)

[Gerenciar classificações e opiniões](manage-reviews.md)

[Configurar classificações e opiniões](configure-ratings-reviews.md)

[Sincronizar classificações de produto](sync-product-ratings.md)

[Habilitar a publicação manual de classificações e opiniões por um moderador](manual-publish-rating-reviews.md)

[Configurar autenticação de serviço a serviço](service-to-service-auth.md)

[Perguntas frequentes sobre classificações e opiniões](ratings-reviews-faq.md)
