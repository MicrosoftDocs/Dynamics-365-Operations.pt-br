---
title: Portal do cliente para a visão geral do Dynamics 365 Supply Chain Management (contém vídeo)
description: Este tópico apresenta o portal do cliente e explica quem deve usá-lo e como ele funciona.
author: Henrikan
ms.date: 06/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: intro-internal
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2020-04-22
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: c1383ee3c8e72f630d29a557de4150cdd3aa905f
ms.sourcegitcommit: ef0dd4245fc499907ffe00e2a32f59a6cd96e45d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/18/2021
ms.locfileid: "7937495"
---
# <a name="customer-portal-for-dynamics-365-supply-chain-management-overview"></a>Visão geral do portal do cliente para o Dynamics 365 Supply Chain Management

[!include [banner](../includes/banner.md)]
[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

## <a name="what-is-the-customer-portal"></a>O que é o portal do cliente?

Os sistemas de cadeia de fornecimento modernos dependem da integração. Eles exigem que o estoque, a demanda do cliente e os departamentos de vendas sejam integrados em vez de residirem em silos separados. O portal do cliente ajuda as organizações que executam o Microsoft Dynamics 365 Supply Chain Management a aperfeiçoar essa integração e manter os clientes informados com mais eficiência.

O portal do cliente é um modelo de [portais do Power Apps](/powerapps/maker/portals/overview) que permite às empresas criar um site de B2B externamente para cenários relacionados ao processamento de ordens de venda. O modelo usa a [gravação dupla](../../fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-home-page.md), o Supply Chain Management e portais do Power Apps para habilitar clientes corporativos externos para exibir e criar dados do ambiente Dynamics 365 da empresa.

O modelo de portal de clientes tem todos os recursos de personalização oferecidos pelo recurso de portais do Power Apps. O modelo pode ser modificado facilmente para representar a marca da empresa, adicionar funcionalidade aprimorada e alterar a experiência do usuário. Toda a funcionalidade que o modelo oferece pronta para uso pode ser modificada conforme desejado.

> [!IMPORTANT]
> Não espera-se que o modelo seja totalmente funcional por si só. Ele serve apenas como ativador para clientes que desejam criar um site externamente para que clientes corporativos possam se interagir com dados do Supply Chain Management.

> [!NOTE]
> A documentação do portal do cliente é voltada para administradores, personalizadores e integradores de sistemas que configurarão o portal do cliente para instalação do Supply Chain Management. Ele usa os termos _cliente_ e _usuário_ para descrever as pessoas que são clientes da organização que está executando o Supply Chain Management e quem usará o próprio portal final.

## <a name="video"></a>Vídeo

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4ylwW]

O vídeo [Visão geral do modelo do portal do Cliente no Dynamics 365 Supply Chain Management](https://youtu.be/nPrqoLuHfV8) (exibido acima) está incluído na [Playlist do Finance and Operations](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) disponível no YouTube.

## <a name="who-should-use-it"></a>Quem deve usá-lo?

O portal do cliente foi criado para empresas que executam o Supply Chain Management e têm estas características:

- Eles desejam criar um site externamente que comunique as informações de processamento da ordem (como status da ordem ou informações da conta) diretamente do sistema Supply Chain Management para os clientes da empresa.
- Eles estão migrando do Dynamics AX 2012 para o Supply Chain Management e antes usavam o [portal de autoatendimento de clientes do AX 2012](/dynamicsax-2012/appuser-itpro/about-the-customer-self-service-portal).

Os seguintes tipos de organização **não** são ideias para a implementação do portal do cliente:

- Empresas que desejam criar um site para clientes não empresariais. Essas empresas devem considerar a criação de um [site de comércio eletrônico do Dynamics 365 Commerce](../../commerce/create-ecommerce-site.md).
- Empresas que já estão usando um site de portais existentes do Power Apps para uma finalidade semelhante. Essas empresas não receberão benefício adicional do portal do cliente. O portal do cliente é entregue como um modelo que atua como um guia e um ponto de partida para os clientes que desejam "ligar os pontos" entre a gravação dupla, o Supply Chain Management e portais do Power Apps. Se você já configurou um site com essa finalidade, talvez não valha a pena usar o modelo de portal do cliente para reprovisionar esse site.

## <a name="how-does-it-work"></a>Como funciona?

O portal do cliente é fornecido como um modelo de portais do Power Apps. Ele depende de portais do Power Apps e de gravação dupla.

[Portais do Power Apps](/powerapps/maker/portals/overview) é um recurso que permite aos usuários criar um site externo que as pessoas fora da organização podem acessar. Pouca ou nenhuma codificação é necessária para criar portais. O portal do cliente é um dos muitos [modelos de portal Dynamics 365](/powerapps/maker/portals/portal-templates#environment-with-model-driven-apps-in-dynamics-365) disponibilizados pela Microsoft.

A [gravação dupla](/powerapps/maker/portals/overview) é um produto pronto para uso que fornece interação quase em tempo real entre aplicativos do Customer Engagement e aplicativos do Finance and Operations. A gravação dupla fornece integração bidirecional entre aplicativos do Finance and Operations e o Microsoft Dataverse. Portanto, ela fornece uma experiência de usuário integrada nos aplicativos. O portal do cliente depende das tabelas sincronizadas com a gravação dupla. Para que os dados do Supply Chain Management sejam exibidos no portal do cliente, a gravação dupla deve ser habilitada para todas as tabelas apropriadas.

![Dependências do portal do cliente.](media/customer-portal-elements.png "Dependências do portal do cliente")

O portal do cliente atua como um ponto de partida para organizações que desejam usar portais do Power Apps para criar um site externamente que use dados da instalação do Supply Chain Management. Ele ajuda as organizações a conectar gravação dupla, Supply Chain Management e portais do Power Apps.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]