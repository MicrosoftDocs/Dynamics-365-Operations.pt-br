---
title: Módulo de rodapé
description: Este artigo abrange os módulos de rodapés e como criá-los no Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 05/18/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.custom: ''
ms.assetid: ''
ms.openlocfilehash: fefeed37ba0d0e800b9cd3cefcf207cde9a625d8
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9282948"
---
# <a name="footer-module"></a>Módulo de rodapé  

[!include [banner](includes/banner.md)]

Este artigo abrange os módulos de rodapé e descreve como criá-los no Microsoft Dynamics 365 Commerce.

O módulo de rodapé é um contêiner especial usado para armazenar os módulos que aparecem no rodapé da página. Por exemplo, pode incluir os links para várias páginas no site, como **Fale conosco** e **Armazenar políticas**.

A imagem a seguir mostra um exemplo de um módulo de rodapé em uma página de site.

![Exemplo de um módulo de rodapé.](./media/ecommerce-footer.PNG)

## <a name="footer-module-properties"></a>Propriedades de módulo de rodapé 

Como a maioria dos contêineres, o módulo de rodapé oferece suporte a propriedades para o título e a largura. Também oferece suporte a adição de diversos módulos de categoria de rodapé. Cada módulo de categoria de rodapé que é adicionado é renderizado como uma coluna no módulo de rodapé.

## <a name="modules-available-in-a-footer-module"></a>Módulos disponíveis em um módulo de rodapé

**Item do rodapé** – Um módulo de itens do rodapé pode conter um título ou um link. Geralmente, o título é usado como um título de seção de rodapé.  Cada link no rodapé pode ser configurado de forma que tenha apenas texto (por exemplo, links de "Fale conosco" e "Privacidade"), de forma que possua um texto e uma imagem (por exemplo, links de mídias sociais.) Se um título e um link forem fornecidos, a propriedade do título terá precedência sobre o link. 

**Voltar para a parte superior** – Um módulo para voltar ao módulo superior fornece um link para navegação rápida ao topo da página. Um destino é necessário. O valor de destino padrão é \#, que leva o usuário ao topo da página.

## <a name="create-a-footer-module"></a>Criar um módulo de rodapé

1. Acesse **Fragmentos** e selecione **Novo** para criar um novo fragmento.
1. Na caixa de diálogo **Selecionar um fragmento**, selecione o módulo **Contêiner**, insira um nome para o fragmento e, depois, selecione **OK**.
1. No slot **Contêiner padrão**, selecione as reticências (**...**) e, depois, **Adicionar módulo**.
1. Na caixa de diálogo **Selecionar módulos**, selecione o módulo **Categoria do rodapé** e, depois, **OK**.
1. No slot **Categoria de rodapé**, selecione as reticências (**...**) e, depois, **Adicionar módulo**.
1. Na caixa de diálogo **Selecionar módulos**, selecione o módulo **Item de rodapé** e, depois, **OK**.
1. Selecione o slot **Item de rodapé** e, depois, no painel de propriedades à direita, configure cabeçalho, link, texto do link e imagem conforme necessário.
1. Para adicionar mais itens de rodapé, repita as etapas 5 a 7 para cada.
1. Para adicionar um link "voltar ao topo" ao rodapé, selecione as reticências (**...**) no slot **Categoria do rodapé** e, depois, **Adicionar módulo**.
1. Na caixa de diálogo **Selecionar módulos**, selecione o módulo **Voltar ao início** e, depois, **OK**.
1. Selecione o slot **Voltar ao tipo** e, depois, no painel de propriedades à direita, configure texto e outras propriedades do módulo, conforme necessário.
1. Selecione **Concluir edição** para fazer check-in do fragmento e, depois, selecione **Publicar** para publicá-lo.

Para ajudar a garantir que um cabeçalho aparece em cada página, siga estas etapas em cada modelo da página que é desenvolvido para o site.

1. No slot **Rodapé** do módulo **Página padrão**, adicione o fragmento de rodapé que você criou.
1. Selecione **Concluir edição** para fazer check-in do modelo e depois selecione **Publicar** para publicá-lo.

Ao adicionar o fragmento aos modelos de página, você ajuda a garantir que o rodapé seja renderizado em todas as páginas.

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral da biblioteca de módulos](starter-kit-overview.md)

[Módulo de contêiner](add-container-module.md)

[Módulo de caixa de compra](add-buy-box.md)

[Módulo de carrinho](add-cart-module.md)

[Módulo de finalização da compra](add-checkout-module.md)

[Módulo de confirmação da ordem](order-confirmation-module.md)

[Módulo de cabeçalho](author-header-module.md)

[Módulo de rodapé](author-footer-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
