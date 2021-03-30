---
title: Configurar classificações e opiniões
description: Este tópico descreve como configurar seu site comercial online para mostrar avaliações de cliente e opiniões no Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
manager: annbe
ms.date: 02/17/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 130c80c1d68c7fb207a4fa073fe2b0476cbdd409
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5220525"
---
# <a name="configure-ratings-and-reviews"></a>Configurar classificações e opiniões

[!include [banner](includes/banner.md)]

Este tópico descreve como configurar seu site comercial online para mostrar avaliações de cliente e opiniões no Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visão Geral

As avaliações e opiniões sobre sites comerciais online ajudam os clientes a aprenderem sobre produtos antes de realizarem uma decisão de compra, mostrando a eles o que os clientes pensam sobre esses produtos. Para sites de comércio online, avaliações e opiniões também são um mecanismo para coletar feedback de clientes sobre produtos. 

## <a name="configure-a-site-to-show-ratings-and-reviews"></a>Configurar um site para exibir classificações e opiniões

Os valores de configuração de classificações e revisões, como ID de locatário, comprimento do texto de avaliação, e comprimento de título de avaliação são configurados no nível do site. 

Para configurar um site para exibir avaliações e opiniões, siga estas etapas. 

1. Vá para **Início \> Sites**.
1. Selecione o nome do site. 
1. Acesse **Configurações do site \> Extensões**. 
1. No campo **Revisar o tamanho máximo do texto**, insira o número máximo de caracteres que o texto de avaliação pode ter (por exemplo, **1000**). 
1. No campo **Revisar o tamanho máximo do título**, insira o número máximo de caracteres que os títulos de avaliação pode ter (por exemplo, **55**). 
1. Selecione **Salvar e publicar**. 

A ilustração a seguir mostra como essa configuração se parece no Dynamics 365 Commerce.

![Configurando um site para exibir classificações e opiniões](media/rnr-eCommerce-site-appsettings.png)

## <a name="link-a-product-rating-to-the-reviews-section-of-a-pdp"></a>Vincule uma avaliação de produto à seção Avaliações de um PDP

Uma classificação de produtos é exibida abaixo do título do produto na parte superior de PDP. A classificação de produto pode ser configurada de forma que está vinculada à seção **Revisões** do mesmo PDP. 

Para vincular um produto que avalie a seção **Avaliações** do PDP, rastreie essas etapas.

1. Abra o modelo do PDP. 
1. Vá para **Comprar configurações de módulo de contêiner de caixa**.
1. Em **Comprar uma caixa**, selecione **Classificações de produtos**, e selecione a caixa de seleção **Vincular o clique ao módulo inteiro de revisões de desempenho**.

A ilustração a seguir mostra como essa configuração se parece no Dynamics 365 Commerce.

![Vinculando uma avaliação de produto à seção Avaliações de um PDP](media/rnr-eCommerce-buy-box-rating-summary.png)

## <a name="configure-the-link-for-the-privacy-and-policy-page"></a>Configurar o link para a página de privacidade e política

Para configurar o link para a página de privacidade e política, siga estas etapas.

1. Vá para **Início \> Sites**.
1. Selecione o nome do site. 
1. Acesse **Configurações do site \> Extensões**.
1. Na guia **Roteiros**, em **Privacidade e política de RNR**, selecione **Adicionar um link**. Se um link já tiver sido inserido e você desejar substituí-lo, selecione o link. 
1. Na caixa de diálogo **Adicionar um link**, selecione o link para a página de privacidade e política, e selecione **OK**. 
1. Selecione **Salvar e publicar**. 

A ilustração a seguir mostra como essa configuração se parece no Dynamics 365 Commerce.

![Configurando o link para a página de privacidade e política](media/rnr-eCommerce-rnr-privacy-policy-link.png)

## <a name="configure-ratings-and-reviews-modules-on-product-details-pages"></a>Configurar os módulos de classificações e revisões nas páginas de detalhes do produto

Para obter informações sobre como configurar módulos de classificações e revisões nas páginas de detalhes do produto, consulte [Módulos de classificações e opiniões](ratings-reviews-modules.md).

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral de classificações e opiniões](ratings-reviews-overview.md)

[Aceitar usar classificações e opiniões](opt-in-ratings-reviews.md)

[Gerenciar classificações e opiniões](manage-reviews.md)

[Configurar os módulos de classificações e revisões nas páginas de detalhes do produto](ratings-reviews-modules.md)

[Sincronizar classificações de produto no Dynamics 365 Retail](sync-product-ratings.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]