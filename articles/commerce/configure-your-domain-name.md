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
ms.openlocfilehash: afc8c7fffbded82be32357bdeb30546afc8b0957
ms.sourcegitcommit: adf196c51e2b6f532d99c177b4c6778cea8a2efc
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2020
ms.locfileid: "3533289"
---
# <a name="configure-your-domain-name"></a>Configure seu nome de domínio


[!include [banner](includes/banner.md)]

Este tópico explica como configurar um nome de domínio para um site comercial online do Microsoft Dynamics 365. 

## <a name="add-domains-during-e-commerce-initialization"></a>Adicionar domínios durante a inicialização do comércio online

Para associar domínios com seu ambiente de comércio online, inicialize o comércio online como descrito em [Implantar um novo site comercial online](deploy-ecommerce-site.md). Durante a inicialização, é solicitado que você forneça as informações que serão usadas para provisionar seu ambiente de comércio online. No campo **Nomes de hospedagem com suporte**, adicione todos os domínios que você planeja usar com esse ambiente. Vários domínios devem ser separados com ponto-e-vírgula. Assim, os domínios são configurados nos componentes obrigatórios de comércio online, e está pronto para ser usado quando alternar o tráfego da rede de entrega de conteúdo (CDN) ou servidor da Web e apontá-lo para o front-end de comércios online.

## <a name="add-domains-after-e-commerce-initialization"></a>Adicionar domínios após a inicialização do comércio online

Para associar novos domínios com o ambiente de comércio online após a inicialização de comércio online, você deve enviar uma solicitação de serviço.

## <a name="additional-resources"></a>Recursos adicionais

[Implantar um novo site de comércio eletrônico](deploy-ecommerce-site.md)

[Criar um site de comércio eletrônico](create-ecommerce-site.md)

[Associar um site online a um canal](associate-site-online-store.md)

[Gerenciar arquivos robots.txt](manage-robots-txt-files.md)

[Carregar redirecionamentos de URL em massa](upload-bulk-redirects.md)

[Configurar um locatário B2C do Commerce](set-up-B2C-tenant.md)

[Configurar páginas personalizadas para logons dos usuários](custom-pages-user-logins.md)

[Configurar múltiplos locatários B2C em um ambiente do Commerce](configure-multi-B2C-tenants.md)

[Adicionar suporte para uma rede de entrega de conteúdo (CDN)](add-cdn-support.md)

[Habilitar detecção de lojas com base na localização](enable-store-detection.md)
