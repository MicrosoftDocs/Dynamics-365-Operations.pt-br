---
title: Configure seu nome de domínio
description: Este tópico explica como configurar um nome de domínio para um site comercial online do Microsoft Dynamics 365.
author: psimolin
manager: AnnBe
ms.date: 07/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: ac1b0c8baaddd6ca62cc49657fff364df21c14f2
ms.sourcegitcommit: 4bf5ae2f2f144a28e431ed574c7e8438dc5935de
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/13/2020
ms.locfileid: "4517104"
---
# <a name="configure-your-domain-name"></a>Configure seu nome de domínio


[!include [banner](includes/banner.md)]

Este tópico explica como configurar um nome de domínio para um site comercial online do Microsoft Dynamics 365. 

## <a name="add-domains-during-e-commerce-initialization"></a>Adicionar domínios durante a inicialização do comércio eletrônico

Para associar domínios com o ambiente de comércio eletrônico do Dynamics 365 Commerce, inicialize o comércio eletrônico como descrito em [Implantar um novo locatário de comércio eletrônico](deploy-ecommerce-site.md). Durante a inicialização, é solicitado que você forneça as informações que serão usadas para provisionar seu ambiente de comércio eletrônico. No campo **Nomes de hospedagem com suporte**, adicione todos os domínios que você planeja usar com esse ambiente. Vários domínios devem ser separados com ponto-e-vírgula. Assim, os domínios são configurados nos componentes obrigatórios de comércio e estão prontos para serem usados quando você alternar o tráfego da rede de entrega de conteúdo (CDN) ou servidor Web e apontá-lo para os front-ends de comércio eletrônico.

## <a name="add-domains-after-e-commerce-initialization"></a>Adicionar domínios após a inicialização do comércio eletrônico

Para associar novos domínios com o ambiente de comércio eletrônico após a inicialização de comércio eletrônico, você deve enviar uma solicitação de serviço.

## <a name="additional-resources"></a>Recursos adicionais

[Implantar um novo locatário de comércio eletrônico](deploy-ecommerce-site.md)

[Criar um site de comércio eletrônico](create-ecommerce-site.md)

[Associar um site do Dynamics 365 Commerce a um canal online](associate-site-online-store.md)

[Gerenciar arquivos robots.txt](manage-robots-txt-files.md)

[Carregar redirecionamentos de URL em massa](upload-bulk-redirects.md)

[Configurar um locatário B2C do Commerce](set-up-B2C-tenant.md)

[Configurar páginas personalizadas para logons dos usuários](custom-pages-user-logins.md)

[Configurar múltiplos locatários B2C em um ambiente do Commerce](configure-multi-B2C-tenants.md)

[Adicionar suporte para uma rede de entrega de conteúdo (CDN)](add-cdn-support.md)

[Habilitar detecção de lojas com base na localização](enable-store-detection.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]