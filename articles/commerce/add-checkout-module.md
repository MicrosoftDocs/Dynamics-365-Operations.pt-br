---
title: Módulo de finalização da compra
description: Este artigo descreve como adicionar um módulo de finalização da compra a uma página e definir as propriedades necessárias.
author: anupamar-ms
ms.date: 11/04/2022
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
ms.openlocfilehash: 295b99c7012e35a40af34d454ff7082d4100c74a
ms.sourcegitcommit: 9e2e54ff7d15aa51e58309da3eb52366328e199d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2022
ms.locfileid: "9746216"
---
# <a name="checkout-module"></a>Módulo de finalização da compra

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

Este artigo descreve como adicionar um módulo de finalização da compra a uma página e definir as propriedades necessárias.

Um módulo de finalização da compra é um contêiner especial que hospeda todos os módulos necessários para criar um pedido. Apresenta um fluxo passo a passo que um cliente usa para inserir todas as informações relevantes para fazer uma compra. Ele captura o endereço de remessa, o método de remessa e as informações de cobrança. Ele também fornece um resumo do pedido e outras informações relacionadas a um pedido do cliente.

Um módulo de finalização da compra renderiza dados com base na ID de carrinho. Essa ID de carrinho é salva como um cookie do navegador. É necessária uma ID de carrinho para renderizar informações no módulo de finalização da compra, como os itens da ordem, o valor total e os descontos. 

A imagem a seguir mostra um exemplo de um módulo de finalização da compra da Fabrikam em uma página de finalização da compra.

![Exemplo de um módulo de finalização da compra.](./media/Checkout.PNG)

## <a name="checkout-module-properties"></a>Propriedades do módulo de finalização da compra

Um módulo de finalização de compra mostra um resumo do pedido e fornece a funcionalidade para a realização de um pedido. Para coletar todas as informações de cliente necessárias antes que um pedido possa ser feito, os módulos adicionais devem ser adicionados ao módulo de finalização de compra. Portanto, os varejistas têm a flexibilidade de adicionar módulos personalizados ao fluxo de finalização de compra ou a excluir módulos, de acordo com suas necessidades.

| Nome da propriedade | Valores | Descrição |
|----------------|--------|-------------|
| Título da finalização da compra | Texto do cabeçalho e uma tag do cabeçalho (**H1**, **H2**, **H3**, **H4**, **H5** ou **H6**) | Um cabeçalho para o módulo de finalização da compra. |
| Título do resumo da ordem | Texto do título | Um cabeçalho para a seção de resumo do pedido do módulo. |
| Título dos itens de linha do carrinho | Texto do título | Um título para os itens da linha do carrinho que são mostrados no módulo de finalização da compra. |
| Mostrar encargos de remessa no item de linha | **Verdadeiro** ou **Falso** | Se esta propriedade for definida como **True**, os encargos de remessa aplicáveis para itens de linha serão mostrados nas linhas do carrinho. Se o recurso **Encargo de cabeçalho sem rateio** for ativado no Commerce headquarters, o encargo de remessa será aplicado no nível do cabeçalho, não no nível da linha. Esse recurso foi adicionado no Commerce versão 10.0.13. |

## <a name="modules-that-can-be-used-in-the-checkout-module"></a>Módulos que podem ser usados no módulo de finalização da compra

- **Endereço de remessa** – Este módulo permite que um cliente adicione ou selecione o endereço de remessa para uma ordem. Para obter mais informações sobre esse módulo, consulte [Módulo de endereço de remessa](ship-address-module.md).

    A imagem a seguir mostra um exemplo de um módulo de endereço de remessa em uma página de finalização da compra.

    ![Exemplo de módulo de endereço de remessa.](./media/ecommerce-shippingaddress.PNG)

- **Opções de entrega** – Este módulo permite que um cliente selecione um modo de entrega para um pedido. Para obter mais informações sobre esse módulo, consulte [Módulo de opções de entrega](delivery-options-module.md).

    A imagem a seguir mostra um exemplo de um módulo de opções de entrega em uma página de finalização da compra.
 
    ![Exemplo de um módulo opções de entrega.](./media/ecommerce-deliveryoptions.PNG)

- **Contêiner da seção de finalização da compra** – Este módulo é um contêiner dentro do qual é possível colocar vários módulos para criar uma seção dentro do fluxo de finalização da compra. Por exemplo, você pode colocar todos os módulos relacionados a pagamento dentro desse contêiner para que eles apareçam como uma seção. Esse módulo afeta apenas o layout do fluxo.

- **Vale-presente** – Este módulo permite que um cliente pague uma ordem usando um vale-presente. Para obter mais informações sobre esse módulo, consulte [Módulo de cartão-presente](add-giftcard.md).

- **Pontos de fidelidade** – Este módulo permite que um cliente pague uma ordem usando pontos de fidelidade. Ele fornece um resumo dos pontos disponíveis e pontos vencidos e permite que o cliente selecione o número de pontos a serem resgatados. Se o cliente não estiver conectado ou não for um membro de fidelidade, ou se o valor total no carrinho for 0 (zero), esse módulo ficará oculto automaticamente.

- **Pagamento** – este módulo permite que um cliente pague um pedido usando um cartão de crédito ou de débito. Os clientes também podem fornecer um endereço de cobrança para a opção de pagamento selecionada. Para obter mais informações sobre esse módulo, consulte [Módulo de pagamento](payment-module.md).

    A imagem a seguir mostra um exemplo de um cartão-presente, pontos de fidelidade e módulos de pagamento em uma página de finalização de compra.

    ![Exemplo de um cartão-presente, pontos de fidelidade e módulos de pagamento em uma página de finalização de compra.](./media/ecommerce-payments.PNG)

- **Informações de contato** – Este módulo permite que um cliente adicione ou altere as informações de contato (endereço de email) de uma ordem.

- **Bloco de texto** – Este módulo contém mensagens controladas pelo sistema de gerenciamento de conteúdo (CMS). Por exemplo, ele pode conter uma mensagem informando "Caso você tenha problemas com uma ordem, entre em contato com 1-800-Fabrikam". 

- **Termos e condições de finalização da compra** – este módulo mostra um arquivo Rich Text que contém os termos e condições e uma caixa de seleção para a entrada do cliente. A caixa de seleção é opcional e configurável. A entrada é capturada pelo módulo e pode ser usada como uma verificação antes que a colocação do pedido seja acionada, mas ela não é incluída nas informações de resumo do pedido. Este módulo pode ser adicionado ao contêiner de finalização da compra, ao contêiner da seção de finalização da compra ou ao slot de termos e condições, de acordo com as necessidades comerciais. Se for adicionado ao contêiner de finalização da compra ou ao slot do contêiner da seção de finalização da compra, ele será exibido como uma etapa no processo de finalização da compra. Se for adicionado ao slot de termos e condições, ele aparecerá próximo ao botão de colocação do pedido.

    A imagem a seguir mostra um exemplo de termos e condições em uma página de finalização de compra.

    ![Exemplo de termos e condições em uma página de finalização da compra.](./media/ecommerce-checkout-terms.PNG)

## <a name="commerce-scale-unit-interaction"></a>Interação do Commerce Scale Unit

A maioria das informações de finalização da compra, como endereço e método de remessa, é armazenada no carrinho e processada como parte da ordem. A única exceção são as informações de cartão de crédito. Essas informações são processadas diretamente usando o conector de pagamento Adyen. O pagamento é autorizado, mas não é cobrado até o pedido ser cumprido.

## <a name="add-a-checkout-module-to-a-page-and-set-the-required-properties"></a>Adicionar um módulo de finalização da compra a uma página e definir as propriedades necessárias

Para adicionar um módulo de finalização da compra a uma nova página e definir as propriedades necessárias, siga estas etapas.

1. Acesse **Fragmentos** e selecione **Novo** para criar um novo fragmento.
1. Na caixa de diálogo **Selecionar fragmento**, selecione o módulo **Finalizar compra**.
1. Em **Nome do fragmento**, digite o nome **Fragmento de finalização da compra** e selecione **OK**.
1. Selecione o slot **Módulo de finalização da compra**.
1. No painel de propriedades à direita, selecione o símbolo de lápis, digite o texto do título no campo e, em seguida, selecione o símbolo de marca de seleção.
1. No slot **Informações de finalização da compra**, selecione as reticências (**...**) e, depois, **Adicionar módulo**.
1. Na caixa de diálogo **Selecionar módulos**, selecione os módulos **Endereço de remessa**, **Opções de entrega**, **Contêiner de seção de finalização da compra** e **Informações de contato** e, depois, selecione **OK**.
1. No slot **Contêiner da seção de finalização da compra**, selecione as reticências (**...**) e, depois, **Adicionar módulo**.
1. Na caixa de diálogo **Selecionar módulos**, selecione os módulos **Cartão-presente**, **Fidelidade** e **Pagamento** e, depois, selecione **OK**. Dessa forma, verifique se todos os métodos de pagamento aparecem juntos em uma seção.
1. No slot **Termos e condições**, adicione um módulo de **Termos e condições de finalização da compra**, se necessário. No painel de propriedades do módulo, configure o texto dos termos e condições conforme apropriado.
1. Selecione **Salvar** e, depois, **Visualizar** para visualizar o fragmento. Alguns módulos que não tem um contexto de carrinho talvez não sejam renderizados na visualização.
1. Selecione **Concluir edição** para fazer check-in do fragmento e, depois, selecione **Publicar** para publicá-lo.
1. Crie um modelo que use o novo fragmento de finalização da compra.
1. Crie uma página de finalização da compra que use o novo modelo.

> [OBSERVAÇÃO] Ao usar uma única autorização de pagamento, conforme descrito em [Aprimoramento de pagamentos em finalização da compra de loja](./dev-itpro/enhanced-sca.md), na seção **Informações da finalização da compra** da página da finalização da compra, confirme se o contêiner da seção da finalização da compra está posicionado por último. Isso garante que todas as informações necessárias sejam coletadas pela página da finalização da compra, antes das ações de finalização de pagamento e conclusão de ordem. 

## <a name="additional-resources"></a>Recursos adicionais

[Módulo de carrinho](add-cart-module.md)

[Módulo de ícone de carrinho](cart-icon-module.md)

[Módulo de pagamento](payment-module.md)

[Módulo de endereço de remessa](ship-address-module.md)

[Módulo de opções de entrega](delivery-options-module.md)

[Módulo de informações sobre retirada](pickup-info-module.md)

[Módulo de detalhes da ordem](order-confirmation-module.md)

[Módulo de cartão-presente](add-giftcard.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
