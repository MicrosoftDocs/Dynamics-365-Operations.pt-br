---
title: Configurar classificações e opiniões
description: Este artigo descreve como configurar seu site de comércio eletrônico para mostrar avaliações de cliente e opiniões no Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 02/17/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.custom: ''
ms.assetid: ''
ms.openlocfilehash: 27b1beddd474a2ca4db73f8e344b2d85934c43b1
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9276856"
---
# <a name="configure-ratings-and-reviews"></a>Configurar classificações e opiniões

[!include [banner](includes/banner.md)]

Este artigo descreve como configurar seu site de comércio eletrônico para mostrar avaliações de cliente e opiniões no Microsoft Dynamics 365 Commerce.

As avaliações e opiniões sobre sites comerciais online ajudam os clientes a aprenderem sobre produtos antes de realizarem uma decisão de compra, mostrando a eles o que os clientes pensam sobre esses produtos. Para sites de comércio online, avaliações e opiniões também são um mecanismo para coletar feedback de clientes sobre produtos. 

## <a name="configure-a-site-to-show-ratings-and-reviews"></a>Configurar um site para exibir classificações e opiniões

Os valores de configuração de classificações e revisões, como ID de locatário, comprimento do texto de avaliação, e comprimento de título de avaliação são configurados no nível do site. 

Para configurar um site para exibir avaliações e opiniões, siga estas etapas. 

1. Acesse **Início \> Sites**.
1. Selecione o nome do site. 
1. Acesse **Configurações do site \> Extensões**. 
1. No campo **Revisar o tamanho máximo do texto**, insira o número máximo de caracteres que o texto de avaliação pode ter (por exemplo, **1000**). 
1. No campo **Revisar o tamanho máximo do título**, insira o número máximo de caracteres que os títulos de avaliação pode ter (por exemplo, **55**). 
1. Selecione **Salvar e publicar**. 

A ilustração a seguir mostra como essa configuração se parece no Dynamics 365 Commerce.

![Configurando um site para exibir classificações e opiniões.](media/rnr-eCommerce-site-appsettings.png)

## <a name="link-a-product-rating-to-the-reviews-section-of-a-pdp"></a>Vincule uma avaliação de produto à seção Avaliações de um PDP

Uma classificação de produtos é exibida abaixo do título do produto na parte superior de PDP. A classificação de produto pode ser configurada de forma que está vinculada à seção **Revisões** do mesmo PDP. 

Para vincular um produto que avalie a seção **Avaliações** do PDP, rastreie essas etapas.

1. Abra o modelo do PDP. 
1. Acesse **Comprar configurações de módulo de contêiner de caixa**.
1. Em **Comprar uma caixa**, selecione **Classificações de produtos**, e selecione a caixa de seleção **Vincular o clique ao módulo inteiro de revisões de desempenho**.

A ilustração a seguir mostra como essa configuração se parece no Dynamics 365 Commerce.

![Vinculando uma avaliação de produto à seção Avaliações de um PDP.](media/rnr-eCommerce-buy-box-rating-summary.png)

## <a name="configure-the-link-for-the-privacy-and-policy-page"></a>Configurar o link para a página de privacidade e política

Para configurar o link para a página de privacidade e política, siga estas etapas.

1. Acesse **Início \> Sites**.
1. Selecione o nome do site. 
1. Acesse **Configurações do site \> Extensões**.
1. Na guia **Roteiros**, em **Privacidade e política de RNR**, selecione **Adicionar um link**. Se um link já tiver sido inserido e você desejar substituí-lo, selecione o link. 
1. Na caixa de diálogo **Adicionar um link**, selecione o link para a página de privacidade e política, e selecione **OK**. 
1. Selecione **Salvar e publicar**. 

A ilustração a seguir mostra como essa configuração se parece no Dynamics 365 Commerce.

![Configurando o link para a página de privacidade e política.](media/rnr-eCommerce-rnr-privacy-policy-link.png)

## <a name="configure-ratings-and-reviews-modules-on-product-details-pages"></a>Configurar os módulos de classificações e revisões nas páginas de detalhes do produto

Para obter informações sobre como configurar módulos de classificações e revisões nas páginas de detalhes do produto, consulte [Módulos de classificações e opiniões](ratings-reviews-modules.md).

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral de classificações e opiniões](ratings-reviews-overview.md)

[Aceitar o uso das classificações e opiniões](opt-in-ratings-reviews.md)

[Gerenciar classificações e opiniões](manage-reviews.md)

[Sincronizar classificações de produto no Dynamics 365 Retail](sync-product-ratings.md)

[Habilitar a publicação manual de classificações e opiniões por um moderador](manual-publish-rating-reviews.md)

[Importar e exportar avaliações e revisões](import-export-reviews.md)

[Configurar autenticação de serviço a serviço](service-to-service-auth.md)

[Perguntas frequentes sobre classificações e opiniões](ratings-reviews-faq.md)

[Módulos de classificações e opiniões](ratings-reviews-modules.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
