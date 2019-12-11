---
title: Módulo de rodapé
description: Este tópico abrange os módulos de rodapés e como criá-los no Dynamics 365 Commerce.
author: anupamar
manager: annbe
ms.date: 10/31/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar-ms
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 7c253cd9620180b09f2f5cae232e46d236deabdd
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/01/2019
ms.locfileid: "2697304"
---
# <a name="footer-module"></a>Módulo de rodapé  

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Este tópico abrange os módulos de rodapé e descreve como criá-los no Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visão geral

O módulo de rodapé é um contêiner especial usado para armazenar os módulos que aparecem no rodapé da página. Por exemplo, pode incluir os links para várias páginas no site, como **Fale conosco** e **Armazenar políticas**.

## <a name="footer-module-properties"></a>Propriedades de módulo de rodapé 

Como a maioria dos contêineres, propriedades do suporte do módulo de rodapé para o título e largura. Também oferece suporte a adição de diversos módulos de categoria de rodapé. Cada módulo de categoria de rodapé que é adicionado é renderizado como uma coluna no módulo de rodapé.

## <a name="modules-available-in-a-footer-module"></a>Módulos disponíveis em um módulo de rodapé

**Itens do rodapé** – Um módulo de itens do rodapé pode conter um título, uma figura e um link. O cabeçalho pode ser usados independentemente ou em combinação com uma imagem e um link. Cada link no rodapé pode ser configurado de forma que tenha apenas texto (por exemplo, links de "Fale conosco" e "Privacidade"), de forma que possua um texto e uma imagem (por exemplo, links de mídias sociais.)

**Voltar para a parte superior** – Um módulo para voltar ao módulo superior fornece um link para navegação rápida ao topo da página. Um destino é necessário. O valor de destino padrão é #, que leva o usuário ao topo da página.

## <a name="author-a-footer-module"></a>Criar um módulo de rodapé

1. No painel de navegação, selecione **Fragmentos** e depois **Novo fragmento de página**.
1. Na caixa de diálogo **Novo fragmento de página**, selecione o módulo do rodapé, insira um nome para a parte mais importante de página, e selecione **OK**.
1. Na árvore em destaque à esquerda, selecione o botão de reticências (**…**) no módulo de rodapé, e depois selecione **Adicionar módulo**.
1. Na caixa de diálogo **Adicionar módulo**, selecione o módulo da categoria do rodapé, e depois selecione **OK**.
1. Na árvore em destaque, selecione o botão de reticências no módulo de categoria do rodapé, e depois selecione **Adicionar módulo**.
1. Na caixa de diálogo **Adicionar módulo**, selecione o módulo de item do rodapé, e depois selecione **OK**.
1. Na árvore em destaque, selecione o módulo de item do rodapé. Em seguida, no painel de propriedades à direita, configure o cabeçalho, link e vincule texto e imagem como quiser.
1. Para adicionar mais itens de rodapé, repita as etapas 5 a 7.
1. Para adicionar um link "voltar ao topo" em seu rodapé, selecione o botão de reticências no módulo de categoria do rodapé, e depois selecione **Adicionar módulo**.
1. Na caixa de diálogo **Adicionar módulo**, selecione o módulo voltar ao topo, e depois selecione **OK**.
1. Na árvore em destaque, selecione o módulo voltar ao topo. Em seguida, no painel de propriedades à direita, configure o módulo voltar ao topo conforme necessário.
1. Salve o fragmento de página, insira-o e publique-o.

Em cada modelo da página criada no site, siga essas etapas.

1. No slot **Principal** da página padrão, no módulo de rodapé, adicione a parte mais importante de rodapé que você criou.
1. Salve o modelo, insira-o e publique-o.

Ao adicionar o fragmento de página aos modelos de página, você ajuda a garantir que o rodapé está renderizado em cada página.

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral do kit de início](starter-kit-overview.md)

[Módulo de contêiner](add-container-module.md)

[Comprar módulo de caixa](add-buy-box.md)

[Módulo de carrinho](add-cart-module.md)

[Módulo de finalização da compra](add-checkout-module.md)

[Módulo de confirmação da ordem](order-confirmation-module.md)

[Módulo de cabeçalho](author-header-module.md)

[Módulo de rodapé](author-footer-module.md)
