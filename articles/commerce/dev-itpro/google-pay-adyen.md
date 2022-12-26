---
title: Configurar Google Pay com Adyen
description: Este artigo descreve como configurar o Google Pay com Adyen no Microsoft Dynamics 365 Commerce.
author: BrianShook
ms.date: 07/05/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: cdf950fc7b3720543d93e108d4e3c3c2ab254e09
ms.sourcegitcommit: bdee5e642d417a13abdb778c14ec5f2dbbf8dee7
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/09/2022
ms.locfileid: "9838382"
---
# <a name="configure-google-pay-with-adyen"></a>Configurar Google Pay com Adyen

[!include [banner](../includes/banner.md)]

Este artigo descreve como configurar o Google Pay com Adyen no Microsoft Dynamics 365 Commerce.

O Dynamics 365 Commerce oferece integração imediata para o Google Pay quando o serviço de gateway de pagamento de Adyen é usado. O Google Pay é um método de pagamento de carteira digital que usa uma conta de comerciante do Google Pay em conjunto com o serviço de pagamento de Adyen. Quando está configurado, o botão Google Pay fica disponível como um método de pagamento selecionável durante a finalização de compra do pedido online. Quando os usuários selecionam o **Google Pay** em um navegador ou dispositivo com suporte, eles são direcionados para preencher seu pagamento diretamente com o serviço do Google Pay. Em seguida, eles são devolvidos à vitrine online para concluir a ordem.

Quando o Google Pay é usado com o módulo de finalização expressa no Commerce, as informações da conta de pagamento do usuário são preenchidas automaticamente no formulário de finalização de compra para ajudar o usuário a obter o processo de finalização de compra mais rápido. O Commerce inclui um módulo de pagamento expresso que permite o comportamento de finalização de compra expressa. O módulo de pagamento expresso pode ser usado em um fragmento incluído em uma página de finalização de compra ou de carrinho. A referência do Conector de Pagamento do Dynamics 365 para Google Pay é usada além do Conector de Pagamento do Dynamics 365 para Adyen para habilitar as opções de pagamento expresso e finalização de compras normal quando o PayPal está configurado. O Google Pay também pode ser configurado com terminais de pagamento Adyen e o ponto de venda (PDV) do Commerce para uso na loja.

## <a name="key-terms"></a>Condições principais

| Termo | Descrição |
|---|---|
| Google Pay | Também conhecido como o "botão" Google Pay, o Google Pay é uma oferta de pagamento de carteira que é suportada por meio do conector de Adyen. Ele permite a experiência e a integração do cliente suportadas pelo Conector do Dynamics Google Pay. |
| Carteira | Um tipo de pagamento que não inclui as características de pagamento tradicionais, como intervalo do número de identificação do banco (BIN) e a data de vencimento, que são usados para diferenciar tipos de cartão de crédito e de débito. |
| Módulo expresso de pagamento | Um módulo do Dynamics 365 Commerce que dá suporte ao comportamento de finalização de compra rápida com formas de pagamento aceitas. |

## <a name="prerequisites"></a>Pré-requisitos

Usando o Google Pay com Adyen no Commerce requer uma conta de comerciante do Google. Para obter informações sobre como configurar sua conta de comerciante do Google, consulte a [documentação do Adyen no Google Pay](https://docs.adyen.com/payment-methods/google-pay/) e a [Lista de verificação de integração](https://developers.google.com/pay/api/web/guides/test-and-deploy/integration-checklist) do Google.

A forma de pagamento do Google Pay também deve ser integrada à sua conta do Adyen. Para obter instruções sobre o link de integração, consulte [Google Pay do Adyen](https://www.adyen.com/payment-methods/google-pay).

Você também deve habilitar o recurso de carteira avançada no Dynamics 365 Commerce headquarters. Vá para **Espaços de trabalho \> Gerenciamento de recursos**, pesquise pelo recurso **Aprimoramentos avançados de suporte para carteira e pagamento**, selecione o recurso e depois **Habilitar**. Depois que o recurso for habilitado, execute o agendamento de distribuição **1110** para disponibilizar a alteração em todos os canais.

## <a name="map-the-google-pay-payment-method"></a>Mapear a forma de pagamento do Google Pay

O Google Pay é uma forma de pagamento de carteira digital. Para obter informações sobre como configurar o mapeamento de pagamentos para o Google Pay, consulte [Suporte de pagamento de carteira](../wallets.md).

Para mapear o método de pagamento do Google Pay para os tipos de meio de pagamento do cartão para os canais de PDV e online, siga estas etapas.

1. No Commerce Headquarters, acesse **Retail e Commerce \> Configuração do canal \> Métodos de pagamento \> Tipos de cartão**.
1. Selecione **Novo** para adicionar uma linha ao Google Pay.
1. No campo **ID**, insira **GooglePay**.
1. No campo **Nome do pagamento eletrônico**, digite **Google Pay**.
1. No campo **Tipo**, digite **Carteira**.
1. No campo **Emissor**, digite **Google**.
1. No Painel de Ações, selecione **Mapeamento do processador** para abrir a caixa de diálogo **Métodos de mapeamento de pagamentos do processador**.
1. Em **Métodos de Pagamento de Processador Não Mapeados**, você verá uma lista de métodos de pagamento de processador não mapeado, sendo que cada um é emparelhado com o conector apropriado. Para mapear os métodos de pagamento do processador do Google Pay não mapeados para tipos de meio de pagamento do cartão, siga estas etapas para cada tipo de meio de pagamento:

    1. Em **Tipos de meio de pagamento do cartão**, selecione um tipo de meio de pagamento do cartão.
    1. Na coluna **Métodos de Pagamento de Processador Não Mapeados**, selecione **Conector de Pagamento do Dynamics 365 para Adyen** (para uso no PDV) e o **Conector de Pagamento do Dynamics 365 para Google Pay** (para uso em canais online).
    1. Selecione **Adicionar**. As seleções são adicionadas à coluna **Métodos de Pagamento de Processador Mapeados**.

1. Ao concluir o mapeamento dos métodos de pagamento, selecione **Salvar**.
1. Na página **Tipos de cartões**, selecione **Salvar**.

## <a name="configure-a-commerce-online-store-for-google-pay"></a>Configurar uma loja online de Commerce para Google Pay

Para configurar uma loja online do Commerce para usar o Google Pay, siga estas etapas.

1. No Commerce headquarters, vá para **Varejo e Comércio \> Canais \> Lojas online**.
1. Selecione o canal da loja online do site, selecionando o valor **ID do Canal de Varejo** do canal.
1. Na Guia Rápida **Contas de pagamento**, em **Conector**, confirme se o **Conector de Pagamento do Dynamics 365 para Adyen** está listado. Se não estiver listado, siga as instruções em [Configurar o Conector de Pagamento do Dynamics 365 para Adyen](adyen-connector-setup.md) para adicioná-lo.

    > [!NOTE]
    > Na maioria dos casos, o **Conector de Pagamento do Dynamics 365 para Adyen** deve ser listado como o primeiro conector do canal (o primeiro conector também é conhecido como conector principal). Em seguida, ele deve ser seguido por outros conectores que serão usados, como o **Conector de Pagamento do Dynamics 365 para PayPal** e **Conector de Pagamento do Dynamics 365 para GooglePay**.

1. Depois que o **Conector de Pagamento do Dynamics 365 para Adyen** for adicionado, selecione **Adicionar** para adicionar o **Conector de Pagamento do Dynamics 365 para GooglePay**. Em seguida, defina as propriedades a seguir para o conector.

    | Campo                  | Descrição | Necessário | Automaticamente definido | Valor de exemplo |
    | ---------------------- | ----------- | -------- | ----------------- | ------------ |
    | Nome do assembly          | O nome do assembly do Conector de Pagamento do Dynamics 365 para GooglePay. | Sim | Sim | *Nome binário* |
    | ID da conta de serviço     | O identificador exclusivo da configuração das propriedades do comerciante. Esse identificador é carimbado nas transações de pagamento e identifica as propriedades do comerciante que os processos downstream (como faturamento) devem usar. | Sim | Sim | *GUID* |
    | ID do comerciante do Google     | Insira a ID do comerciante do Google que é atribuída à sua conta de comerciante do Google. Essa propriedade é necessária para ambientes de produção, mas é opcional para ambientes de teste. Para obter mais informações, consulte <https://pay.google.com/>. | Sim | Número | *Identificador numérico* |
    | ID de conta de comerciante    | Insira o identificador exclusivo de comerciante do Adyen. Esse valor é fornecido quando você se inscreve no Adyen, conforme descrito em [Inscrever-se no Adyen](adyen-connector-setup.md#sign-up-with-adyen). | Sim | Número | *Identificador do Comerciante* |
    | Chave de API de nuvem          | Insira a chave da API da nuvem do Adyen. Para obter essa chave, siga as instruções em [Como obter a chave de API](https://docs.adyen.com/developers/user-management/how-to-get-the-api-key). | Sim | Número | "abcdefg" |
    | Ambiente de gateway    | O ambiente de gateway do Adyen a ser mapeado. Os valores possíveis são **Teste** e **Ativo**. Você deve definir este campo como **Ativo** apenas para dispositivos e transações de produção. | Sim | Sim | "Ativo" |
    | Moedas com suporte   | As moedas que o conector deve processar. Em cenários do cartão presente, o Adyen pode dar suporte a moedas adicionais por meio da [Conversão de Moeda Dinâmica](https://www.adyen.com/pos-payments/dynamic-currency-conversion) depois que a solicitação de transação for enviada para o terminal de pagamento. Contate o suporte do Adyen para obter uma lista de moedas com suporte. | Sim | Sim | "USD;EUR" |
    | Tipos de meio de pagamento com suporte | Os tipos de meio de pagamento que o conector deve processar. | Sim | Sim | "GooglePay" |

1. Depois de concluir a configuração das propriedades do conector, execute o trabalho de agendamento de distribuição **1070 (Configuração do canal**).


### <a name="use-the-payment-express-module-with-google-pay"></a>Usar o módulo expresso de pagamento com o Google Pay

O módulo de pagamento expresso do Commerce funciona com formas de pagamento de apoio para oferecer aos clientes do site a opção de finalizar a compra mais rápido, preenchendo automaticamente as informações da conta do serviço de pagamento durante o processo de finalização de compra. O módulo de pagamento expresso faz referência ao botão do conector configurado e retorna os detalhes da ordem selecionados pelo usuários (endereço, informações de contato e a forma de pagamento) para preencher o formulário de finalização de compra.

Quando o módulo de pagamento expresso é usado com o Google Pay, se os clientes selecionarem o botão Google Pay na seção **Pagamento Expresso**, a janela iframe do Google Pay será aberta. Os usuários podem entrar na conta do Google para usarem o endereço de envio, o endereço para cobrança, o endereço de email e a forma de pagamento do Google Pay de sua escolha para pagar pela transação.

Quando os usuários concluírem a ação na janela do Google Pay, eles serão redirecionados para a página de finalização de compra do site do Commerce, na qual o formulário de finalização de compra é preenchido automaticamente com os detalhes da conta do Google Pay. Depois que os usuários retornarem à página de finalização de compra da janela do Google Pay, eles verão os seguintes detalhes:

- No fluxo de pagamento expresso, a primeira opção de entrega disponível para o endereço de remessa retornado será pré-selecionada para o cliente.
- Quando o Google Pay for usado, nenhum endereço de email de contato será retornado. Os usuários de finalização de compra do convidado precisarão inserir um endereço de email na seção contato da página de finalização de compra. Os usuários conectados terão seus dados de contato automaticamente preenchidos da conta de cliente do Dynamics (o endereço de email principal usado para autenticação).

Os clientes têm a opção de revisar os pedidos e alterar os detalhes de finalização de compra do pedido antes de selecionar **Fazer pedido** para finalizar o pedido.

### <a name="configure-google-pay-in-site-builder"></a>Configurar Google Pay no construtor de sites 

Antes de configurar os fragmentos ou as páginas com o Google Pay, você deve garantir que suas diretivas de segurança de conteúdo do site estejam definidas no construtor de sites do Commerce.

Para garantir que as diretivas de segurança de conteúdo estejam definidas no construtor de sites, siga estas etapas.

1. Em seu site, vá para **Configurações do site \> Extensões**.
1. Na guia **Política de segurança de conteúdo**, adicione uma linha para `*.google.com` às diretivas **child-src**, **connect-src**, **frame-ancestors**, **frame-src**, **img-src**, **script-src** e **style-src**.
1. Quando terminar, selecione **Salvar e publicar**.

### <a name="configure-the-payment-express-fragment-with-google-pay-in-site-builder"></a>Configurar o fragmento de pagamento expresso com o Google Pay no construtor de sites

Para configurar o fragmento de pagamento expresso com o Google Pay para a loja online, siga estas etapas.

1. No construtor de sites, navegue até **Fragmentos**.
1. Selecione **Novo**.
1. Na caixa de diálogo **Novo fragmento**, selecione o módulo **Contêiner**, informe um nome de fragmento (por exemplo, **Finalização de Compra Expressa**), depois selecione **OK**. 
1. Selecione o novo slot **Contêiner Padrão** do fragmento.
1. No painel de propriedades à direita, defina as propriedades do módulo do contêiner:

    - **Cabeçalho** – Insira um título para ser exibido na seção de finalização de compra expressa do seu site (por exemplo, **Finalização de Compra Expressa**).
    - **Layout do contêiner** – Selecione **Fluxo**.
    - **Largura** – selecione **Contêiner de preenchimento**.
    - **Filhos mostrados** – Selecione **Três** para especificar o número de filhos que caberão em uma linha da seção de finalização de compra expressa da página de finalização de compra (por exemplo, uma caixa de texto, pagamento expresso para o Paypal e pagamento expresso para o Google Pay).
    - **Nome da classe de CSS** – insira **contêiner de pagamento expresso msc** (obrigatório).

    > [!IMPORTANT]
    > - O valor do **nome da classe de CSS** deve ser definido como **contêiner de pagamento expresso msc** para controlar o comportamento do contêiner durante a finalização de compra. Esse comportamento inclui ocultar, recolher e outras ações que se aplicam à seção de finalização de compra expressa durante o fluxo de finalização de compra. A classe **contêiner de pagamento expresso msc** funciona com as operações padrão liberadas com o módulo de finalização de compra da biblioteca do módulo.
    > - Estilos adicionais podem ser incluídos em relação ao **nome da classe CSS**. Se você personalizar o comportamento do módulo, verifique se os controles de estilo estão usando o mesmo comportamento codificado da biblioteca de módulos no módulo de finalização de compra para o comportamento de finalização de compra expressa.

1. No slot **Contêiner padrão**, selecione as reticências (**...**) e, depois, **Adicionar módulo**.
1. Na caixa de diálogo **Selecionar módulos**, selecione o módulo **Pagamento expresso** e, depois, **OK**.
1. No painel de propriedades do módulo de **Pagamento expresso**, defina ou ajuste o valor **Altura do iFrame** em pixels (por exemplo, **60**).
1. No campo **Tipos de meio de pagamento com suporte**, insira **GooglePay**. O valor deve corresponder à cadeia de caracteres **Tipos de Meio de Pagamento com Suporte** no conector configurado para o canal (conforme descrito na seção [Configurar uma loja online do Commerce para o Google Pay](#configure-a-commerce-online-store-for-google-pay), anteriormente neste artigo).

    > [!NOTE]
    > Você pode repetir as etapas de 6 a 9 para adicionar os módulos de **Pagamento expresso** a outros métodos de pagamento. Alinhe o valor de **Tipos de meio de pagamento com suporte** com os tipos de pagamento adicionais configurados (por exemplo, **Paypal**).

1. Opcional: você pode adicionar um módulo de bloco de texto ao módulo de contêiner padrão para incluir instruções ou informações de divulgação. Depois de adicionar o módulo, no painel Propriedades, insira o texto desejado no campo **Rich text**. Você pode posicionar o texto acima ou abaixo dos módulos de pagamento expresso selecionando as reticências (**...**) no slot **Bloco de texto** e selecionando **Mover para cima** ou **Mover para baixo**.
1. Selecione **Salvar** para salvar suas alterações e depois selecione **Finalizar edição**.
1. Selecione **Publicar** para publicar o fragmento.

### <a name="add-the-payment-express-fragment-to-the-checkout-page"></a>Adicionar o fragmento de pagamento expresso à página de finalização de compra

Para adicionar um fragmento de pagamento expresso a uma página de finalização de compra, siga estas etapas.

1. No construtor de sites, vá para **Páginas** e, em seguida, selecione a página de finalização de compra do seu site.
1. Selecione **Editar**.
1. No **Slot principal**, selecione as reticências (**...**) e depois selecione **Adicionar módulo**.
1. Na caixa de diálogo **Selecionar módulos**, selecione o módulo **Contêiner** e, depois, **OK**.
1. No painel de propriedades à direita, defina as propriedades do módulo do contêiner:

    - **Layout do Contêiner** – selecione **Empilhado**.
    - **Largura** – selecione **Contêiner de preenchimento**.
    - **Filhos Mostrados** – Selecione **Três** para especificar o número de filhos que caberão em uma linha da seção de finalização de compra expressa da página de finalização de compra (por exemplo, uma caixa de texto, pagamento expresso para o Paypal e pagamento expresso para o Google Pay).

1. No slot do módulo **Contêiner**, selecione as reticências (**...**) e, depois, **Adicionar fragmento**.
1. Na caixa de diálogo **Selecionar um fragmento**, selecione o fragmento de pagamento expresso criado anteriormente e, em seguida, selecione **OK**.
1. Selecione **Salvar** para salvar suas alterações e depois selecione **Finalizar edição**.
1. Selecione **Publicar** para publicar a página.

> [!NOTE]
> Se a página de finalização de compra já incluir um contêiner que tem o fragmento de finalização de compra e você desejar que o módulo de pagamento expresso seja renderizado acima do contêiner de finalização de compra normal, você pode posicioná-lo acima ou abaixo da finalização de compra existente, selecionando as reticências (**...**) no **Slot principal** e selecionando **Mover para cima** ou **Mover para baixo**.

### <a name="add-the-payment-express-fragment-to-the-cart-page"></a>Adicionar o fragmento de pagamento expresso à página de carrinho

Para adicionar o fragmento de pagamento expresso a uma página do carrinho, siga estas etapas.

1. No construtor de sites, vá para **Páginas** e, em seguida, selecione a página do carrinho do seu site.
2. Selecione **Editar**.
3. Na exibição de esboço, expanda o **Slot principal** na exibição de árvore e localize o contêiner que contém o módulo **Carrinho**.
4. No módulo **Carrinho**, selecione o slot **Pagamento Expresso**, selecione as reticências (**...**) e selecione **Adicionar módulo**.
5. Na caixa de diálogo **Selecionar módulos**, selecione o módulo **Pagamento expresso** e, depois, **OK**.
6. Selecione o slot do módulo **Pagamento expresso**. Em seguida, no painel Propriedades, à direita, em **Tipos de meio de pagamento com suporte**, digite **GooglePay**. O valor deve corresponder à cadeia de caracteres **Tipos de Meio de Pagamento com Suporte** no conector configurado para o canal (conforme descrito na seção [Configurar uma loja online do Commerce para o Google Pay](#configure-a-commerce-online-store-for-google-pay), anteriormente neste artigo).
1. Selecione **Salvar** para salvar suas alterações e depois selecione **Finalizar edição**.
1. Selecione **Publicar** para publicar a página.

Os usuários podem incluir até três módulos expressos de **Pagamento Expresso** (em outras palavras, três opções de pagamento disponíveis) no slot de **Pagamento Expresso** do carrinho.

### <a name="set-up-google-pay-as-an-option-in-the-checkout-payment-section"></a>Configurar o Google Pay como uma opção na seção de finalização de compra

Você pode configurar o Google Pay como uma opção na seção de finalização de compra para funcionalidade somente pagamento e não expressa. O formulário de finalização de compra será preenchido pelo usuário, e a página de pagamento do Google Pay só estará pronta para a finalização de compra pelo Google Pay. Nenhuma informação de conta do Google será usada para substituir os detalhes preenchidos da finalização de compra.

> [!NOTE]
> O procedimento a seguir supõe que seu site usa um fragmento de finalização de compra configurado com informações de retirada, um endereço de remessa, opções de entrega, informações de contato, termos e condições opcionais e uma seção para elementos de finalização de compra. O módulo de finalização de compra da biblioteca de módulos padrão é liberado com um contêiner de seção de finalização de compra que tem bloco de texto, pontos de fidelidade, cartão de presente e módulos de pagamento. Para obter mais informações, consulte [Módulo de pagamento](../payment-module.md).

Para configurar o Google Pay como uma opção de pagamento regular na seção **Método de Pagamento** da página de finalização de compra, siga estas etapas.

1. No construtor de sites, vá para **Fragmentos** e, em seguida, selecione o fragmento de finalização de compra do seu site.
1. Selecione **Editar**.
1. No slot **Informações de Finalização de compra**, selecione as reticências (**...**) e, depois, **Adicionar módulo**.
1. Na caixa de diálogo **Selecionar módulos**, selecione o módulo **Pagamento** e, depois, **OK**.
1. No painel de propriedades **Pagamento** à direita, defina as propriedades do módulo do contêiner:

    - **Cabeçalho** – Insira um título para ser exibido na seção de finalização de compra expressa do seu site (por exemplo, **Google Pay**).
    - **Altura do iFrame** – Altere o valor de altura de design preferida em pixels (por exemplo, **75**). 
    - **Tipos de meio de pagamento com suporte** – insira **GooglePay** para coincidir com a configuração do conector do Google Pay no Commerce Headquarters.
    - **É pagamento principal** – deixe a caixa de seleção desmarcada. (Esta propriedade é geralmente habilitada para o módulo de finalização de compra do Adyen).
    - **Substituição de estilo de pagamento** – não há suporte para essa propriedade na configuração do Google Pay.
    - **Usar ID do conector** – esta propriedade deverá ser selecionada, se vários conectores de pagamento forem usados na página.

1. Posicione o módulo acima ou abaixo dos outros módulos de pagamento, selecionando as reticências (**...**) no slot **Pagamento** e selecionando **Mover para cima** ou **Mover para baixo**.
1. Selecione **Salvar** para salvar suas alterações e depois selecione **Finalizar edição**.
1. Selecione **Publicar**.

### <a name="modes-of-delivery"></a>Modos de entrega

Com o módulo de pagamento expresso que usa o Google Pay, a primeira opção de entrega retornada para o endereço de envio selecionado da conta do Google Pay será preenchida automaticamente. Os usuários têm a oportunidade de ajustar o endereço de remessa para uma opção diferente, caso queiram.

A ordem na qual os métodos de entrega são exibidos no módulo de pagamento expresso é configurada na página **Modos de entrega** no Commerce Headquarters. No Commerce headquarters, vá para **Varejo e Comércio \> Canais \> Lojas online** e selecione o valor **Retail channel ID** para sua loja. No Painel de Ações, na guia **Configuração**, selecione **Modos de entrega**. Os modos de entrega listados serão exibidos na mesma ordem no módulo de pagamento expresso. Selecione **Gerenciar modos de entrega** no Painel de Ações para adicionar ou remover modos de entrega para um canal ou produto de varejo. Para obter mais informações sobre como configurar o modo de entrega, consulte [Configurar os modos de entrega](/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery).

O módulo de finalização de compra também usa o módulo de opções de entrega quando os modos de entrega são processados durante a finalização de compra. Para obter mais informações, consulte [Módulo de opções de entrega](../delivery-options-module.md).

Os modos de entrega são exibidos à medida que são adicionados à lista de **Modos de entrega** na loja online.

## <a name="configure-commerce-pos-for-google-pay"></a>Configurar PDV do Commerce para Google Pay

A configuração de PDV usa a definição do campo **Serviço de TEF** do perfil de hardware do Conector de Pagamento do Dynamics 365 para Adyen. Para obter informações sobre como configurar o serviço de transferência eletrônica de fundos (TEF) para o Dynamics 365 Payment Connector para Adyen no Commerce Headquarters, consulte [Configurar uma seção de perfil de hardware de PDV do Dynamics 365](adyen-connector-setup.md#set-up-a-dynamics-365-pos-hardware-profile).

O mapeamento do processador para o conector de Adyen captura os tipos de cartão da carteira que o Google Pay usar no terminal de PDV.

## <a name="additional-resources"></a>Recursos adicionais

[Perguntas frequentes sobre pagamentos](payments-retail.md)

[Módulo de finalização da compra](../add-checkout-module.md)

[Módulo de pagamento](../payment-module.md)
