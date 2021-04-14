---
title: Visão geral de sites de comércio eletrônico
description: Este tópico fornece uma visão geral do suporte para sites de comércio eletrônico no Microsoft Dynamics 365 Commerce.
author: bicyclingfool
ms.date: 11/05/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: stuharg
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: b0c7aa3bc1d4eef7b557bd9b07b31196faab273d
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5791069"
---
# <a name="e-commerce-site-overview"></a>Visão geral do site de comércio eletrônico

[!include [banner](includes/banner.md)]

Este tópico fornece uma visão geral do suporte para sites de comércio eletrônico no Microsoft Dynamics 365 Commerce. Ele inclui informações sobre como as lojas online de comércio eletrônico são inicializadas e gerenciadas no Dynamics 365 Commerce. Ele também fornece links para obter mais informações sobre lojas online e sobre como configurar um site de comércio eletrônico. Embora este tópico aborde muitos dos conceitos básicos, ele não cobre tudo o que é necessário para configurar um site de comércio eletrônico de produção. Tópicos mais avançados podem ser encontrados na documentação do Dynamics 365 Commerce.

## <a name="online-store-channel"></a>Canal de loja online

Antes de criar seu site no Dynamics 365 Commerce, pelo menos um canal de loja online deve ser configurado. Para obter mais informações, consulte [Configurar um canal online](channel-setup-online.md). 

No Dynamics 365 Commerce, você usa um canal de loja online para estabelecer produtos, preços, idiomas, formas de pagamento, modos de entrega, centros de atendimento e outros aspectos da experiência online que devem estar disponíveis para seus clientes.

Somente um canal de loja online deve ser configurado para que você possa começar a usar o Dynamics 365 Commerce. No entanto, um único site de comércio eletrônico pode fornecer a experiência online para várias lojas online. Por exemplo, se várias lojas online forem configuradas para oferecer suporte a diferentes regiões geográficas, um único conjunto de páginas de comércio eletrônico poderá ser usado para fornecer as experiências exclusivas definidas por cada loja. Para obter mais informações sobre como configurar um site para oferecer suporte a várias lojas online, consulte [Associar um site online a um canal](associate-site-online-store.md).

Depois que uma loja online for configurada, ela pode ser associada ao site do Dynamics 365 Commerce que servirá como uma vitrine online. Para obter mais informações sobre lojas online e sobre como configurá-las, consulte [Configurar lojas onlines](https://docs.microsoft.com/dynamics365/unified-operations/retail/online-stores).

## <a name="deploy-a-new-e-commerce-tenant"></a>Implantar um novo locatário de comércio eletrônico

Durante a inicialização de um site de comércio eletrônico, você será solicitado a informar um nome de domínio. Para obter mais informações sobre domínios no Commerce, consulte [Configurar seu nome de domínio](configure-your-domain-name.md) e [Domínios no Dynamics 365 Commerce](domains-commerce.md). Para implantar um novo locatário de comércio eletrônico usando o [Microsoft Dynamics Lifecycle Services (LCS)](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide), siga as etapas em [Implantar um novo locatário de comércio eletrônico](deploy-ecommerce-site.md). Depois que o seu locatário de comércio eletrônico for configurado no LCS, será fornecido um link para o construtor de sites do Commerce. Em seguida, você poderá usar o construtor de sites do Commerce para inicializar e configurar seus sites de comércio eletrônico.

## <a name="initialize-your-e-commerce-site"></a>Inicializar seu site de comércio eletrônico

Ao iniciar o construtor de sites do Commerce a partir do LCS, a página **Sites** é exibida. Essa página inclui dois sites pré-configurados, **padrão** e **fabrikam**, conforme mostrado no exemplo da ilustração a seguir.

![Página Sites no construtor de sites do Commerce](media/e-commerce-site-01.png)

Ao selecionar um desses sites, você será solicitado a selecionar um nome de domínio, um canal de loja online padrão, um idioma com suporte para o canal selecionado e um caminho. Se apenas um canal for usado, você poderá deixar o caminho em branco. Mais canais de loja online e idiomas podem ser configurados posteriormente no construtor de sites do Commerce. Cada canal ou idioma adicional exigirá um caminho exclusivo. Por exemplo, você tem dois canais online associados a um único site, e o nome de domínio do site é `www.fabrikam.com`. Nesse caso, o caminho para um canal pode ser o valor padrão que não tem caminho (`https://www.fabrikam.com`), e o segundo canal pode ser definido como um novo caminho, por exemplo, **site2**, que terá a URL `https://www.fabrikam.com/site2`. A ilustração a seguir mostra um exemplo de uma caixa de diálogo de inicialização de sites no construtor de sites do Commerce.

![Caixa de diálogo Inicialização de sites no construtor de sites do Commerce](media/e-commerce-site-02.png)

A página **Sites** também inclui um botão **Novo site**. A caixa de diálogo que aparece quando você seleciona esse botão é semelhante à caixa de diálogo de inicialização de sites, mas é usada para criar um novo site. Novos sites são vazios. Eles não incluem os mesmos modelos, fragmentos, páginas e imagens padrão fornecidos com os sites **padrão** e **fabrikam**. No entanto, conforme necessário, você pode abrir um tíquete de suporte para solicitar que uma cópia do conteúdo padrão seja adicionada a um novo site em branco. Para obter mais informações, consulte [Criar um site de comércio eletrônico](create-ecommerce-site.md).

Depois que um novo site for inicializado, a página **Página Inicial** do construtor de sites do Commerce será exibida. Essa página inclui links para ações comuns e conteúdo de orientação, conforme mostrado no exemplo da ilustração a seguir.

![Links na Home page do construtor de sites do Commerce](media/e-commerce-site-03.png)

## <a name="modify-online-store-channels-or-add-online-store-channels-to-an-e-commerce-site"></a>Modificar canais de loja online ou adicionar canais de loja online a um site de comércio eletrônico

Depois que um site de comércio eletrônico for criado, você poderá alterar o canal ao qual ele está associado seguindo as etapas em [Associar um site de comércio eletrônico a um canal online](associate-site-online-store.md). O exemplo na ilustração a seguir mostra como o número de unidade operacional (OUN) de um canal pode ser alterado na página **Canais** (**Configurações do site \> Canais**). Depois de concluir uma alteração, selecione **Salvar e publicar**. Dessa forma, você garante que a alteração seja publicada.

![Página Canais no construtor de sites do Commerce](media/e-commerce-site-04.png)

Você pode adicionar novos canais selecionando **Adicionar um canal**. Para adicionar novos idiomas a um canal, selecione o canal e, em seguida, selecione **Adicionar uma localidade** na caixa de diálogo de canal exibida. Antes que as localidades possam aparecer na caixa de diálogo, elas devem ser pré-configuradas para o canal de loja online na sede do Commerce.

![Caixa de diálogo Canal no construtor de sites do Commerce](media/e-commerce-site-05.png)

## <a name="set-up-an-azure-b2c-tenant"></a>Configurar um locatário B2C do Azure

O Dynamics 365 Commerce usa o B2C (business-to-consumer) do Azure Active Directory (Azure AD) para oferecer suporte aos fluxos de credenciais e autenticação de usuários. Para obter informações sobre como configurar seu locatário B2C do Azure, consulte [Configurar um locatário B2C no Commerce](set-up-b2c-tenant.md), [Configurar páginas personalizadas para entrada de usuários](custom-pages-user-logins.md) e [Configurar vários locatários B2C em um ambiente do Commerce](configure-multi-b2c-tenants.md).

## <a name="overview-of-the-default-site-pages"></a>Visão geral das páginas padrão de sites

Os sites **padrão** e **fabrikam** incluem modelos, fragmentos e páginas pré-configurados para ajudá-lo a começar. Para obter mais informações, consulte os seguintes tópicos:

- [Visão geral da página inicial](quick-tour-home-page.md)
- [Visão geral da página Detalhes do produto](quick-tour-pdp.md)
- [Visão geral das páginas de carrinho e de finalização da compra](quick-tour-cart-checkout.md)
- [Visão geral das páginas de gerenciamento da conta](quick-tour-account-management.md)

## <a name="manage-site-settings"></a>Gerenciar configurações de sites

Para obter informações sobre como gerenciar configurações de sites, consulte os seguintes tópicos:

- [Gerenciar usuários e funções de comércio eletrônico](manage-ecommerce-users-roles.md)
- [Considerações de otimização do mecanismo de pesquisa (SEO) para seu site](/search-engine-optimization-considerations.md)
- [Gerenciar a Política de Segurança de Conteúdo (CSP)](manage-csp.md)
- [Selecionar um tema de site](select-site-theme.md)

## <a name="manage-site-content"></a>Gerenciar conteúdo de sites

Para obter informações sobre como gerenciar conteúdo de sites, consulte os seguintes tópicos:

- [Glossário do modelo de página](page-elements-overview.md)
- [Estados de documento e de ciclo de vida](document-states-overview.md)
- [Modelos e layout](templates-layouts-overview.md)
- [Trabalhar com fragmentos](work-with-fragments.md)
- [Trabalhar com módulos](work-with-modules.md)
- [Visão geral do gerenciamento de ativos digitais](dam-overview.md)
- [Visão geral da biblioteca de módulos](starter-kit-overview.md)

## <a name="additional-resources"></a>Recursos adicionais

[Criar um site de comércio eletrônico](create-ecommerce-site.md)

[Implantar um novo site de comércio eletrônico](deploy-ecommerce-site.md)

[Associar um site online a um canal](associate-site-online-store.md)

[Configurar seu nome de domínio](configure-your-domain-name.md)

[Adicionar suporte para uma rede de entrega de conteúdo (CDN)](add-cdn-support.md)

[Habilitar detecção de lojas com base na localização](enable-store-detection.md)

[Configurar páginas personalizadas para logons dos usuários](custom-pages-user-logins.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]