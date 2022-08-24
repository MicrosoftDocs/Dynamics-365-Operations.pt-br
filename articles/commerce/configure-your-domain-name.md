---
title: Configurar seu nome de domínio
description: Este artigo explica como configurar um nome de domínio para um site de comércio eletrônico do Microsoft Dynamics 365.
author: josaw1
ms.date: 07/02/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.search.region: global
ms.author: josaw
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.custom: ''
ms.assetid: ''
ms.search.industry: Retail
ms.search.form: ''
ms.openlocfilehash: 298ce84008e60cc82a494320b6a41f35338508c3
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9278615"
---
# <a name="configure-your-domain-name"></a>Configurar seu nome de domínio


[!include [banner](includes/banner.md)]

Este artigo explica como configurar um nome de domínio para um site de comércio eletrônico do Microsoft Dynamics 365. 

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
