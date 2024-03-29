---
title: Habilitar a publicação manual de classificações e opiniões por um moderador
description: Este artigo descreve como habilitar a publicação manual de classificações e opiniões por um moderador no Microsoft Dynamics 365 Commerce e como publicar manualmente classificações e opiniões.
author: gvrmohanreddy
ms.date: 09/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-09-03
ms.dyn365.ops.version: 10.0.22
manager: annbe
ms.openlocfilehash: 6591e18ff8e83ec9030d91d8348271b8113e453f
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9276766"
---
# <a name="enable-manual-publishing-of-ratings-and-reviews-by-a-moderator"></a>Habilitar a publicação manual de classificações e opiniões por um moderador

[!include [banner](includes/banner.md)]

Este artigo descreve como habilitar a publicação manual de classificações e opiniões por um moderador no Microsoft Dynamics 365 Commerce e como publicar manualmente classificações e opiniões.

A solução de classificações e opiniões do Dynamics 365 Commerce usa o Azure Cognitive Services para censurar linguagem ofensiva em títulos e conteúdos de opiniões e publicar classificações e opiniões automaticamente. Portanto, a intervenção manual não é necessária para revisar e publicar classificações e opiniões no site de comércio eletrônico.

No entanto, algumas empresas podem preferir que os moderadores revisem e aprovem manualmente as opiniões antes de serem publicadas. Para habilitar a publicação manual de classificações e opiniões por um moderador, você deve habilitar o recurso **Exigir moderador para classificações e opiniões** no construtor de sites do Commerce.

## <a name="enable-the-require-moderator-for-ratings-and-reviews-feature-in-commerce-site-builder"></a>Habilitar o recurso Exigir moderador para classificações e opiniões no construtor de sites do Commerce

Para habilitar o recurso **Exigir moderador para classificações e opiniões** no construtor de sites do Commerce, siga estas etapas.

1. Acesse **Início \> Opiniões \> Configurações**.
1. Defina a opção **Exigir moderador para classificações e opiniões** como **Ativado**.

> [!NOTE]
> Ao habilitar o recurso **Exigir moderador para classificações e opiniões**, você interrompe a publicação automática de classificações e opiniões, portanto, a publicação manual agora é necessária. No entanto, o Azure Cognitive Services continuará censurando linguagem ofensiva em títulos e conteúdos de opiniões.

<!--![Require moderator for ratings and reviews setting in Commerce site builder.](media/Ratings-reviews-settings-human-moderation.png)-->

## <a name="publish-ratings-and-reviews"></a>Publicar classificações e opiniões

Ao habilitar o recurso **Exigir moderador para classificações e opiniões**, um moderador deve revisar e publicar classificações e opiniões para que sejam exibidas no site de comércio eletrônico.

Para revisar e publicar classificações e opiniões no construtor de sites do Commerce, siga estas etapas.

1. Acesse **Revisões \> Moderação**.
1. Na grade, se o campo **Status** de uma linha estiver definido como **Não publicado**, a classificação e a opinião nessa linha ainda não foram publicadas. Para exibir somente as classificações e opiniões não publicadas, selecione **Status: Requer revisão** no filtro de status acima da grade.
1. Selecione uma ou mais classificações e opiniões que tenham um status **Não publicado** e selecione **Publicar** na barra de comandos. As classificações e opiniões selecionadas são adicionadas à fila de publicação e serão exibidas no site de comércio eletrônico depois que forem publicadas.

> [!NOTE]
> - Depois que uma classificação e uma opinião forem publicadas, o valor do status será alterado de **Não publicado** para um valor nulo (campo em branco).
> - Se você selecionar várias classificações e opiniões com status mistos e selecionar **Publicar**, as classificações e opiniões que ainda não foram publicadas serão publicadas. No entanto, as classificações e opiniões que já foram publicadas não serão publicadas novamente.

A ilustração a seguir mostra um exemplo em que três classificações e opiniões não publicadas são selecionadas na página **Moderação** no construtor de sites do Commerce.

![Três classificações e opiniões não publicadas selecionadas na página Moderação no construtor de sites do Commerce.](media/Ratings-reviews-publishing-reviews.png)

<!--![Dynamics 365 Commerce - Ratings and Review configuration 2](media/Ratings-reviews-published-reviews.png)-->
<!--![Status filter](media/Ratings-reviews-published-reviews-status-filter.png)-->

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral de classificações e opiniões](ratings-reviews-overview.md)

[Aceitar o uso das classificações e opiniões](opt-in-ratings-reviews.md)

[Gerenciar classificações e opiniões](manage-reviews.md)

[Configurar classificações e opiniões](configure-ratings-reviews.md)

[Sincronizar classificações de produto](sync-product-ratings.md)

[Importar e exportar avaliações e revisões](import-export-reviews.md)

[Configurar autenticação de serviço a serviço](service-to-service-auth.md)

[Perguntas frequentes sobre classificações e opiniões](ratings-reviews-faq.md)
