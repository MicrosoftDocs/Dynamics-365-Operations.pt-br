---
title: Cartões-presente digitais de comércio eletrônico
description: Este tópico descreve como os cartões-presente digitais funcionam na implementação de comércio eletrônico do Microsoft Dynamics 365 Commerce. Ele também fornece uma visão geral de etapas de configuração importantes.
author: anupamar-ms
ms.date: 05/27/2022
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
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: de8811b3265bc582a055aaad1f3dea32def552f4
ms.sourcegitcommit: d38d2fe85dc2497211ba5731617f590029d07145
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/27/2022
ms.locfileid: "8809578"
---
# <a name="e-commerce-digital-gift-cards"></a>Cartões-presente digitais de comércio eletrônico

[!include [banner](includes/banner.md)]

Este tópico descreve como os cartões-presente digitais funcionam na implementação de comércio eletrônico do Microsoft Dynamics 365 Commerce. Ele também fornece uma visão geral de etapas de configuração importantes.

No Dynamics 365 Commerce, a compra de cartões-presente digitais segue o mesmo fluxo que a compra de outros produtos no sistema. Nenhum módulo adicional precisa ser configurado. Se vários cartões-presente forem adicionados ao carrinho, os itens do cartão-presente não serão agregados em uma única linha de venda. Esse comportamento é necessário porque cada linha de venda é faturada usando um número de cartão-presente separado.

A compra de cartões-presente digitais tem suporte no Dynamics 365 Commerce versão 10.0.16 e posterior.

A ilustração a seguir mostra um exemplo da página de detalhes do produto (PDP) de um cartão-presente digital no site de comércio eletrônico da Fabrikam.

![Exemplo de um PDP de cartão-presente digital no site de comércio eletrônico da Fabrikam.](./media/GiftcardPDP.PNG)

## <a name="turn-on-the-digital-gift-card-feature-in-commerce-headquarters"></a>Ativar o recurso de cartão-presente digital na sede do Commerce

Para que o fluxo de compras para cartões-presente digitais funcione no Dynamics 365 Commerce, o recurso **Comprar cartão-presente no recurso de comércio eletrônico** deve estar ativado na sede do Commerce. Você pode encontrar o recurso no espaço de trabalho **Gerenciamento de recursos** na sede do Commerce, conforme mostrado na ilustração a seguir.

![Espaço de trabalho de gerenciamento de recursos na sede do Commerce.](./media/Featureflag.PNG)

## <a name="configure-a-digital-gift-card-in-commerce-headquarters"></a>Configurar um cartão-presente digital na sede do Commerce

Produtos de cartão-presente digital devem ser configurados na sede do Commerce. O processo se parece com o processo para outros produtos. No entanto, as etapas importantes a seguir são específicas da configuração de cartões-presente para compra. Para obter mais informações sobre como criar e configurar produtos, consulte [Criar um novo produto no Commerce](create-new-product-commerce.md).

- Ao configurar produtos de cartão-presente digital na caixa de diálogo **Novo produto**, defina o campo **Tipo de produto** como **Serviço**. (Para abrir a caixa de diálogo, acesse **Varejo e comércio \> Produtos e categorias \> Produtos por categoria** e selecione **Novo**.) Os produtos do tipo **Serviço** não são verificados quanto ao estoque disponível antes da ordem ser efetuada. Para obter mais informações, consulte [Criar um novo produto](create-new-product-commerce.md#create-a-new-product).
- Na página **Parâmetros do Commerce**, na guia **Lançamento**, o campo **Produto para o cartão-presente** deve ser definido como **Cartão-presente digital**, conforme mostrado na ilustração a seguir. Se o produto for um cartão-presente externo, consulte [Suporte a cartões-presente externos](./dev-itpro/gift-card.md) para obter mais informações.

    ![Campo de produto do cartão-presente na sede do Commerce.](./media/PostGiftcard.png)

- Se um cartão-presente precisar dar suporte a vários valores predefinidos (por exemplo, US$ 25, US$ 50 e US$ 100), a dimensão **Tamanho** deverá ser usada para configurar esses valores predefinidos. Cada valor predefinido será uma grade de produto. Para obter mais informações, consulte [Dimensões do produto](../supply-chain/pim/product-dimensions.md?toc=%2fdynamics365%2fretail%2ftoc.json).
- Se os clientes precisarem especificar um valor personalizado para um cartão-presente além dos valores predefinidos, primeiro configure uma grade que permita um valor personalizado. O atributo **Tamanho** oferece suporte a grades de valor personalizado. Em seguida, abra o produto na página **Produtos liberados na categoria**. Na FastTab **Commerce**, defina o campo **Inserir preço** como **Novo preço deve ser inserido**, conforme mostrado no exemplo de ilustração a seguir. Essa configuração garante que os clientes possam inserir um preço quando procurarem o produto em um PDP.

    ![Campo Chave no preço na sede do Commerce.](./media/KeyInPrice.png)
    
    A ilustração do exemplo a seguir mostra uma lista de grades de produtos digitais do cartão-presente no Commerce headquarters, incluindo duas grades de preços personalizadas.
    ![Grades de produtos de cartão-presente digital com exemplo de grade de preço personalizado](./media/DigitalGiftCards_ProductVariantsWithCustom.png)

- O modo de entrega de um cartão-presente digital deve ser definido como **Eletrônico**. Na página **Modos de entrega** (**Varejo e comércio \> Configuração de canal \> Modos de entrega**), selecione o modo de entrega **Eletrônico** no painel de lista e, depois, adicione o produto do cartão-presente digital à grade na FastTab **Produtos**, conforme mostrado na ilustração a seguir. Para obter mais informações, consulte [Configurar modos de entrega](/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery).

    ![Produtos de cartão-presente digital na página Modo de entrega na sede do Commerce.](./media/ElectronicMode.PNG)
    
- Verifique se um perfil de funcionalidade online foi criado e associado à sua loja online na sede do Commerce. No perfil de funcionalidade, defina a opção **Agregar produtos** como **Sim**. Essa configuração garante que todos os itens, exceto cartões-presente, sejam agregados. Para obter mais informações, consulte [Criar um perfil de funcionalidade online](online-functionality-profile.md).
- Para garantir que clientes recebam um email depois que um cartão-presente for faturado, crie um novo tipo de notificação de email na página **Perfis de notificação por email** e defina o campo **Tipo de notificação por email** como **Emitir cartão-presente**. Para obter mais informações, consulte [Configurar um perfil de notificação por email](email-notification-profiles.md).

## <a name="add-product-images-to-the-commerce-site-builder-media-library"></a>Adicionar imagens do produto à biblioteca de mídia do assistente para criação de sites do Commerce

Você deve adicionar imagens de produto para produtos de cartão-presente digital à biblioteca de mídia do assistente para criação de sites do Commerce. Verifique se os nomes de arquivo dos arquivos de imagem do cartão-presente seguem as convenções de nomenclatura do site para imagens de produtos. Para obter mais informações, consulte [Carregar imagens](dam-upload-images.md).

## <a name="configure-a-custom-amount-for-a-digital-gift-card-in-commerce-site-builder"></a>Configurar um valor personalizado para um cartão-presente digital no assistente para criação de sites do Commerce

Se um cartão-presente digital estiver configurado para permitir um valor personalizado, esse comportamento também deverá ser habilitado no [módulo de caixa de compra](add-buy-box.md) que é usado em PDPs do site. O módulo de caixa de compra oferece suporte à configuração de módulos para permitir valores personalizados. Você também pode definir os valores mínimo e máximo permitidos para valores personalizados.

Para configurar um valor personalizado para um cartão-presente digital no assistente para criação de sites do Commerce, siga estas etapas.

1. Acesse o módulo de caixa de compra usado em PDPs do seu site. Este módulo de caixa de compra pode ser implementado em um fragmento, em um modelo ou em uma página.
1. Selecione **Editar**.
1. No painel de propriedades à direita, marque a caixa de seleção **Permitir preço personalizado**.
1. Opcional: para definir valores mínimo e máximo para valores personalizados, insira valores em **Preço mínimo** e **Preço máximo**.
1. Selecione **Concluir edição** e **Publicar**.

## <a name="additional-resources"></a>Recursos adicionais

[Módulo de caixa de compra](add-buy-box.md)

[Módulo de finalização da compra](add-checkout-module.md)

[Módulo de carrinho](add-cart-module.md)

[Criar um novo produto no Commerce](create-new-product-commerce.md)

[Configurar os modos de entrega](/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery)

[Dimensões do produto](../supply-chain/pim/product-dimensions.md?toc=%2fdynamics365%2fretail%2ftoc.json)

[Configurar perfil de notificação por email](email-notification-profiles.md)

[Criar um perfil de funcionalidade online](online-functionality-profile.md)

[Suporte a cartões-presente externos](./dev-itpro/gift-card.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
