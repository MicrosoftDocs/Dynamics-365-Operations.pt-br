---
title: Visão geral das páginas de carrinho e de finalização da compra
description: Este tópico fornece uma visão geral páginas de carrinho e de finalização da compra no Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 4f7c708aa7f1a858e78cdbda809b90b944606022
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5244782"
---
# <a name="cart-and-checkout-pages-overview"></a>Visão geral das páginas de carrinho e de finalização da compra

[!include [banner](includes/banner.md)]

Este tópico fornece uma visão geral páginas de carrinho e de finalização da compra no Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visão Geral

A página do carrinho de um site de comércio eletrônico mostra todos os itens que um cliente adicionou ao carrinho. A página do carrinho é criada usando o módulo do carrinho. O módulo do carrinho é um contêiner que hospeda todos os módulos necessários para mostrar itens no carrinho. O módulo do carrinho também pode usar outros módulos para mostrar o resumo do pedido e quaisquer códigos promocionais que foram aplicados ao pedido do cliente.

A página de finalização de compra de um site de comércio eletrônico apresenta um fluxo passo a passo que os clientes seguem para inserir todas as informações necessárias para fazer um pedido. Um módulo de finalização de compra pode incluir módulos que lidam com o endereço de entrega, métodos de entrega, informações de cobrança, resumo do pedido e outras informações relacionadas aos pedidos do cliente.

## <a name="cart-page"></a>Página do carrinho

A página do carrinho serve como sacola de compras e contém todos os itens que foram adicionados ao carrinho.

A ilustração a seguir mostra um exemplo de uma página do carrinho que é criada com a biblioteca de módulos e o tema “Fabrikam”.

![Exemplo de uma página do carrinho](./media/cart2.PNG)

O corpo principal da página do carrinho mostra todos os itens que o cliente adicionou ao carrinho. Todos os descontos aplicáveis são exibidos. Esses descontos incluem descontos complexos. Os exemplos incluem "Compre 3 itens e obtenha 10% de desconto" ou "Compre uma garrafa e uma mochila para obter 10% de desconto". O módulo de resumo do pedido mostra o valor devido após a aplicação de descontos, entrega, impostos etc. Há também um módulo de código promocional que permite ao cliente aplicar ou remover códigos promocionais.

Um cliente pode comprar anonimamente ou como um usuário conectado. Se um cliente estiver conectado, os itens no carrinho serão preservados entre as sessões. Dessa forma, o cliente pode continuar comprando em vários dispositivos.

No carrinho, o cliente pode continuar para finalizar a compra. Um cliente pode iniciar a finalização da compra como usuário convidado ou como usuário conectado.

Para obter informações sobre como criar uma página de carrinho, consulte [Adicionar um módulo do carrinho a uma página](add-cart-module.md).

## <a name="checkout-page"></a>Página de finalização da compra

A página de finalização de compra é onde os clientes inserem as informações necessárias para fazer um pedido.

A ilustração a seguir mostra um exemplo de uma página de finalização de compra que foi criada usando a biblioteca de módulos.

![Exemplo de uma página de finalização de compra](./media/Checkout.PNG)

O corpo principal da página de finalização de compra é onde todas as informações do pedido são coletadas. Essas informações incluem o endereço de entrega, as opções de entrega, e as informações de pagamento. A finalização de compra tem um fluxo passo a passo, porque as informações devem ser inseridas em um pedido específico para serem processadas. Por exemplo, o endereço de entrega deve ser inserido antes que os custos da entrega possam ser calculados e o pagamento possa ser autorizado.

### <a name="shipping-address"></a>Endereço de remessa

É necessário um endereço de entrega, se os itens tiverem que ser enviados. O formato dos endereços de entrega para cada localidade pode ser configurado no Dynamics 365 Commerce. Por exemplo, se os itens forem enviados para os Estados Unidos, o endereço de entrega deverá incluir um endereço, estado e CEP. Alguma validação básica de entrada é feita para campos de endereço de entrega, como validação para caracteres alfanuméricos, comprimento máximo e números. Embora a validade do endereço em si não seja verificada, essa verificação pode ser feita usando serviços personalizados de terceiros.

O endereço de entrega é aplicado a todos os itens do carrinho para os quais a opção "entrega" está selecionada. Se você usar o fluxo de finalização de compra fornecido na biblioteca de módulos, os itens individuais do carrinho não poderão ser enviados para endereços diferentes. Se você precisar desse recurso, ele poderá ser implementado através da personalização dos módulos de finalização de compra.

Depois que o endereço de entrega for fornecido, os métodos de entrega disponíveis na loja online do Dynamics 365 Commerce serão mostrados. Os métodos de envio e os endereços que eles apoiam podem ser configurados no Commerce.

### <a name="payment"></a>Pagamento

A próxima etapa do fluxo de finalização de compra é o pagamento. No comércio eletrônico, vários métodos de pagamento podem ser usados para fazer pedidos, como cartões de crédito, vales-presentes e pontos de fidelidade. Uma combinação desses métodos de pagamento também pode ser usada. Dependendo dos métodos de pagamento usados, as informações adicionais poderão ser necessárias. Por exemplo, um pagamento com cartão de crédito exige um endereço de cobrança. Os pagamentos com cartão de crédito são processados usando o Conector de Pagamento de Adyen.

#### <a name="loyalty-points"></a>Pontos de fidelidade

Durante o fluxo de pagamento, um cliente que é membro de um programa de fidelidade e que acumulou pontos de fidelidade pode resgatar esses pontos de fidelidade para um pedido. O módulo de pontos de fidelidade é exibido apenas se o cliente tiver uma associação de fidelidade existente. Para não membros e usuários convidados, este módulo está oculto.

#### <a name="gift-cards"></a>Cartões-presente

A biblioteca de módulos permite que vales-presentes internos sejam resgatados para uma ordem. Para aplicar um vale-presente interno, o cliente precisar estar conectado. Para segurança adicional, recomendamos que você personalize o fluxo usando um número de identificação pessoal (PIN) para vales-presentes internos.

### <a name="signed-in-and-guest-users"></a>Usuários conectados e convidados

O cliente pode concluir o processo de finalização como usuário convidado ou como usuário conectado. Se o cliente entrar, as informações da conta, como endereços de entrega salvos e detalhes do cartão de crédito salvos, serão recuperados automaticamente.

### <a name="order-summary"></a>Resumo da ordem

A finalização de compra mostra um resumo dos itens de linha no carrinho, para que o cliente possa verificar o pedido antes de fazer o pedido. Os itens de linha não podem ser editados durante o fluxo de finalização de compra. No entanto, é fornecido um link para o carrinho, caso o usuário queira voltar e editar os itens de linha.

Depois que o cliente fornece as informações de entrega e cobrança, o resumo do pedido reflete o valor devido após a aplicação de pontos de fidelidade, vales-presentes e outros pagamentos.

### <a name="order-confirmation-and-email"></a>Confirmação de pedido e email

Quando o cliente faz um pedido, é fornecido um número de confirmação. Nesse momento, o pagamento foi autorizado, mas não cobrado. O pagamento será cobrado somente quando o pedido for atendido (ou seja, quando for entregue ou retirado).

Após a criação de um pedido, um email de confirmação do pedido é enviado ao cliente.

Para obter informações sobre como criar uma página de carrinho, consulte [Adicionar um módulo de finalização da compra a uma página](add-checkout-module.md).

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral da home page](quick-tour-home-page.md)

[Visão geral das páginas de detalhes do produto](quick-tour-pdp.md)

[Visão geral das páginas de gerenciamento da conta](quick-tour-account-management.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]