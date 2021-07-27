---
title: Visão geral do tema Adventure Works
description: Este tópico fornece uma visão geral do tema Adventure Works e descreve como aplicá-lo às páginas do site no Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 07/08/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: c7557a36a948de5ae877d74bbbdea78821099b82
ms.sourcegitcommit: 7e976059118938b0089e40bef948029a8c088b38
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/09/2021
ms.locfileid: "6479404"
---
# <a name="adventure-works-theme-overview"></a>Visão geral do tema Adventure Works

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

Este tópico fornece uma visão geral do tema Adventure Works e descreve como aplicá-lo às páginas do site no Microsoft Dynamics 365 Commerce.

O Dynamics 365 Commerce tem um tema para comércio eletrônico chamado Adventure Works. O tema Adventure Works demonstra produtos de esportes e recreação e é otimizado para uma experiência de narrativa rica e aprimorada. Ele oferece uma aparência moderna, novos layouts e efeitos de animação para criar uma experiência de compra online envolvente e atrativa para clientes de comércio eletrônico.

O tema Adventure Works fornece os seguintes novos fluxos de trabalho:

- O módulo de player de vídeo agora oferece suporte à funcionalidade de cabeçalho, parágrafo e links para narrativas adicionais.
- A ação adicionar ao carrinho invoca o mini carrinho em vez de fornecer uma notificação.
- O módulo de exibição rápida é um painel que aparece nas portas de exibição de desktop e móveis.
- Um carrinho vazio agora pode apresentar promoções.

O tema Adventure Works inclui os seguintes módulos de narrativa na biblioteca de módulos do Commerce:

- Módulo de lista de blocos
- Módulo de recurso interativo
- Módulo de assinatura
- Módulo de imagem ativa
- Módulo de lista de imagens

O tema Adventure Works é totalmente responsivo e oferece uma experiência otimizada para portas de exibição de desktop, dispositivos móveis e tablets.

> [!IMPORTANT]
> O tema Adventure Works e os novos módulos estão disponíveis a partir da versão 10.0.20 do Dynamics 365 Commerce.

A ilustração a seguir mostra um exemplo de uma página inicial que usa o tema Adventure Works.

![Exemplo de uma página inicial que usa o tema Adventure Works](./media/aw_b2c.PNG)

A ilustração a seguir mostra um exemplo de uma página de lista que usa o tema Adventure Works.

![Exemplo de uma página de lista que usa o tema Adventure Works](./media/Aw_list.PNG)

A ilustração a seguir mostra um exemplo de uma página de detalhes de produto (PDP) que usa o tema Adventure Works.

![Exemplo de uma página de detalhes de produto (PDP) que usa o tema Adventure Works](./media/aw_pdp.PNG)

## <a name="use-the-adventure-works-theme-for-b2b-sites"></a>Usar o tema Adventure Works para sites B2B

O tema Adventure Works também é um tema de referência para sites B2B (Business-to-Business). Todos os módulos e fluxos de trabalho de B2B são configurados no tema Adventure Works. Para obter informações sobre como configurar um site de B2B, consulte [Configuração de site de B2B](./b2b/set-up-b2b-site.md).

A ilustração a seguir mostra um exemplo de uma página inicial de B2B que usa o tema Adventure Works.

![Exemplo de uma página inicial de B2B que usa o tema Adventure Works](./media/aw_b2b.PNG)

## <a name="theme-extensions"></a>Extensões de tema

O tema Adventure Works inclui várias extensões de tema, como as **Extensões de exibição** e as extensões de **Definição de módulo**. O tema Adventure Works pode ser usado como um tema de referência para criar extensões semelhantes. Por exemplo, a página de lista no tema Adventure Works é implementada como uma extensão de exibição que tem um refinador horizontal. (Para fins de comparação, um refinador do painel esquerdo é usado no tema Fabrikam).

Da mesma forma, outros módulos incluem extensões de definição de módulo. Por exemplo, o [módulo de ícone de carrinho](cart-icon-module.md) contém dois slots **Carrinho vazio** e **Conteúdo promocional** adicionais que são implementados usando extensões de definição de módulo. Além disso, uma nova propriedade **Logotipo móvel** foi adicionada ao módulo de cabeçalho para dar suporte a um logotipo em portas de exibição móveis. Esta propriedade é implementada como uma extensão de definição de módulo de cabeçalho.

Para obter mais informações sobre extensões de tema, consulte [extensões de tema](e-commerce-extensibility/theme-module-extensions.md).

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral da biblioteca de módulos](starter-kit-overview.md)

[Módulo de lista de blocos](tile-list-module.md)

[Módulo de recurso interativo](interactive-feature-module.md)

[Módulo de imagem ativa](active-image-module.md)

[Módulo de assinatura](subscribe-module.md)

[Módulo de lista de imagens](image-list-module.md)

[Extensões de tema](e-commerce-extensibility/theme-module-extensions.md)

[Módulo de ícone de carrinho](cart-icon-module.md)

[Configurar um site de comércio eletrônico B2B](./b2b/set-up-b2b-site.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
