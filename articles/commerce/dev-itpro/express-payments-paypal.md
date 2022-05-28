---
title: Configurar pagamentos expressos do PayPal
description: Este tópico descreve como configurar pagamentos expressos para o PayPal habilitar recursos de finalização de compra mais rápida no Microsoft Dynamics 365 Commerce.
author: BrianShook
ms.date: 05/11/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: 5fff17959e7ed9299df169c68b2ed07f6b7c7d2c
ms.sourcegitcommit: e4cc43b06ef3f0f562849e2c960025cb244d6017
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/12/2022
ms.locfileid: "8743561"
---
# <a name="configure-express-payments-for-paypal"></a>Configurar pagamentos expressos do PayPal

[!include [banner](../includes/banner.md)]

Este tópico descreve como configurar pagamentos expressos para o PayPal habilitar recursos de finalização de compra mais rápida no Microsoft Dynamics 365 Commerce.

## <a name="key-terms"></a>Condições principais

| Termo | Descrição |
|---|---|
| Carteira do PayPal | A experiência e a integração do cliente suportadas pelo conector do PayPal. Também é conhecido como o botão PayPal. |
| Carteira | Um tipo de pagamento que não inclui as características de pagamento tradicionais, como intervalo do número de identificação do banco (BIN) e a data de vencimento, que são usados para diferenciar tipos de cartão de crédito e débito. |
| Pagamento expresso | Um módulo do Commerce que dá suporte ao comportamento de finalização de compra rápida quando as formas de pagamento aceitas são usadas. Este tópico aborda o uso do módulo de pagamento expresso com o PayPal. |

Dynamics 365 Commerce oferece integração pronta para a Carteira do PayPal. Quando o Conector de Pagamento do Dynamics 365 para PayPal está configurado, o botão PayPal aparece como uma forma de pagamento selecionável durante a finalização de compra do pedido online. Quando os usuários selecionam PayPal, são direcionados para concluir o pagamento diretamente por meio do PayPal e, em seguida, retornam à loja online para concluir o pedido. A finalização de compra do carrinho pelo PayPal permite que os clientes usem suas informações de conta de pagamento para preencher o formulário de pagamento e concluir o processo mais rapidamente.

O Commerce adicionou um módulo de pagamento expresso para facilitar as finalizações de compra rápidas. O módulo de pagamento expresso pode ser usado em um fragmento incluído em uma página de finalização de compra ou de carrinho. Quando o PayPal é configurado, a mesma referência do Conector de Pagamento do Dynamics 365 para PayPal é usada para a opção de pagamento expresso e para a opção de finalização de compra regular.

## <a name="paypal-checkout-in-commerce"></a>Finalização de compra no PayPal no Commerce

### <a name="prerequisites"></a>Pré-requisitos

Configure a carteira do PayPal para seu ambiente, conforme descrito no [Conector de Pagamento do Dynamics 365 para PayPal](../paypal.md).

Se você estiver usando o PayPal como uma opção no fluxo de finalização de pagamento regular (em que os usuários inserem manualmente as informações da sua conta sem usar as ações de preenchimento automático de pagamento expresso), siga as instruções de configuração no [módulo de Pagamento](../payment-module.md).

### <a name="payment-express-module-with-paypal"></a>Módulo de pagamento expresso com PayPal

O módulo de pagamento expresso funciona com formas de pagamento de apoio para oferecer aos clientes do site a opção de finalizar a compra mais rápido, preenchendo automaticamente as informações da conta do serviço de pagamento durante o processo de finalização de compra. O módulo de pagamento expresso usa o conector de pagamento configurado para preencher automaticamente o formulário de finalização de compra com detalhes da conta de usuário, como endereço, informações de contato e a forma de pagamento selecionada.

Quando a finalização de compra expressa do PayPal é usada e um usuário seleciona o botão PayPal na seção Pagamento Expresso da página de finalização de compra, uma janela de pagamento do PayPal iFrame é aberta. Depois, o usuário faz logon na sua conta do PayPal para usar o endereço de envio, o endereço para cobrança, o endereço de email e a forma de pagamento do PayPal de escolha para pagar pela transação.

Depois que o usuário concluir a ação na janela PayPal, ele será redirecionado para a página de finalização de compra do site do Commerce, na qual o formulário de finalização de compra é preenchido automaticamente com os detalhes selecionados. No fluxo de pagamento expresso, a primeira opção de entrega disponível para o endereço de remessa retornada será preenchida para o usuário. Em seguida, o usuário terá a opção de revisar os detalhes do pedido e alterá-los antes de selecionar **Fazer pedido** para concluir.

### <a name="add-the-payment-express-module-with-paypal-to-a-fragment"></a>Adicionar o módulo de pagamento expresso com PayPal a um fragmento

Para adicionar o módulo de pagamento expresso com PayPal a um fragmento no construtor de sites do Commerce, siga estas etapas.

1. Navegue para seu site.
1. No painel de navegação à esquerda, selecione **Fragmentos** e depois **Novo**.
1. Na caixa de diálogo **Novo fragmento**, selecione o módulo **Pagamento expresso** e, em **Nome do fragmento**, insira um nome (por exemplo, **Finalização de compra expressa**).
1. Selecione **OK** para criar o fragmento.
1. Na exibição de esboço, selecione o slot do módulo de pagamento expresso que você criou.
1. No painel de propriedades, selecione **Título**.
1. Na caixa de diálogo **Título**, no campo **Texto do título**, insira o texto de título que você deseja mostrar para a seção de finalização de compra expressa do seu site (por exemplo, **Finalização de compra expressa**).
1. Em **Nível de título**, selecione o nível do título (por exemplo, **H2**).
1. Selecione **OK**.
1. No painel de propriedades, no campo **Altura do iFrame**, insira ou ajuste a altura do elemento iFrame (por exemplo, **60**).
1. No campo **Tipos de meio de pagamento com suporte**, insira **PayPal**.
1. Selecione **Salvar**, **Concluir edição** para fazer check-in do fragmento e depois selecione **Publicar** para publicá-lo.

### <a name="add-the-payment-express-fragment-to-the-checkout-page"></a>Adicionar o fragmento de pagamento expresso à página de finalização de compra

Para adicionar um fragmento de pagamento expresso a uma página de finalização de compra no construtor de sites, siga estas etapas.

1. Navegue para seu site.
1. No painel de navegação esquerdo, selecione **Páginas** e, em seguida, selecione a página de finalização de compra do seu site.
1. Selecione **Editar** para editar a página.
1. No slot **Principal**, selecione as reticências (**...**) e, depois, **Adicionar Módulo**.
1. Na caixa de diálogo **Selecionar módulos**, selecione o módulo **Contêiner** e, depois, **OK**.

    > [!NOTE]
    > Se já houver um módulo de contêiner com um fragmento de finalização de compra, mova a seção de pagamento expresso para que apareça acima do contêiner de finalização de compra existente no slot **Principal**. A seção de pagamento expresso será processada acima do contêiner de finalização de compra normal. Para mover um módulo de contêiner para cima ou para baixo, selecione o botão de reticências (**...**) e selecione **Mover para cima** ou **Mover para baixo**.

1. No painel de propriedades do **Contêiner**, recomendamos que você configure as configurações de propriedade da seguinte maneira:

    - **Layout do Contêiner** – selecione **Empilhado**.
    - **Largura** – selecione **Contêiner de preenchimento**.
    - **Filhos mostrados** – selecione **Três**.

1. No slot **Contêiner**, selecione as reticências (**...**) e, depois, **Adicionar Fragmento**.
1. Na caixa de diálogo **Selecionar fragmento**, selecione o fragmento de pagamento expresso criado anteriormente e, em seguida, selecione **OK**.
1. Selecione **Salvar**, **Concluir edição** para fazer check-in da página e depois selecione **Publicar** para publicá-lo.

### <a name="add-the-payment-express-fragment-to-the-cart-page"></a>Adicionar o fragmento de pagamento expresso à página de carrinho

Para adicionar um fragmento de pagamento expresso a uma página de carrinho no construtor de sites, siga estas etapas.

1. Navegue para seu site.
1. No painel de navegação esquerdo, selecione **Páginas** e, em seguida, selecione a página de carrinho no seu site.
1. Selecione **Editar** para editar a página.
1. No slot **Principal**, localize o contêiner que inclui o módulo do **Carrinho**. O módulo do **Carrinho** incluirá um slot de **Pagamento expresso**.
1. Selecione o slot **Pagamento Expresso**, selecione as reticências (**...**) e, depois, **Adicionar Módulo**.
1. Na caixa de diálogo **Selecionar módulos**, selecione o módulo **Pagamento expresso** e, depois, **OK**.
1. No painel de propriedades, no campo **Tipos de meio de pagamento com suporte**, insira **Paypal**.
1. Selecione **Salvar**, **Concluir edição** para fazer check-in da página e depois selecione **Publicar** para publicá-lo.

### <a name="modes-of-delivery"></a>Modos de entrega

Quando o módulo de pagamento expresso é configurado para usar o PayPal, a primeira opção de entrega retornada para o endereço de envio selecionado para a conta do PayPal será preenchida automaticamente. Os usuários poderão alterar o endereço de envio se desejarem.

A ordem do modo de entrega é configurada na seção **Modos de entrega** para o canal no Commerce Headquarters. Para obter mais informações, consulte [Configurar modos de entrega](/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery).

O módulo de finalização de compra também usará o módulo de opções de entrega quando os modos de entrega forem processados durante o pagamento. Para obter mais informações, consulte [Módulo de opções de entrega](../delivery-options-module.md).

Os modos de entrega são adicionados à lista para a loja online no Commerce Headquarters. Vá para **Retail e Commerce \> Canais \> Lojas online** e selecione o ID do canal para sua loja. Em seguida, selecione **Configuração \> Modos de entrega**. Os modos do módulo de entrega que são mostrados na configuração aparecerão de forma semelhante no site. Para adicionar ou remover modos de entrega para um canal ou produto de varejo, selecione **Gerenciar modos de entrega** no Painel de Ações.

## <a name="additional-resources"></a>Recursos adicionais

[Perguntas frequentes sobre pagamentos](payments-retail.md)

[Módulo de finalização da compra](../add-checkout-module.md)

[Módulo de pagamento](../payment-module.md)

[Configurar os modos de entrega](/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery)

[Módulo de opções de entrega](../delivery-options-module.md)
