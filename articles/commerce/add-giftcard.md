---
title: Módulo do vale-presente
description: Este tópico abrange os módulos de cartão-presente e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 08/02/2021
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
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 5a4aaf8e072f6547fe1dcf6fa156d2e144fd03ed806a2dc809a2cedb991461f7
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6728330"
---
# <a name="gift-card-module"></a>Módulo de cartão-presente

[!include [banner](includes/banner.md)]

Este tópico abrange os módulos de cartão-presente e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.

Os módulos de cartão-presente podem ser usados em módulos de finalização de compra para aceitar cartões-presente, uma forma comum de pagamento usada para transações de comércio eletrônico. O módulo de cartão-presente oferece suporte a cartões-presente Dynamics 365, SVS e Givex. Os cartões-presente SVS e Givex são resgatados por meio do provedor de pagamentos Adyen. Para obter mais informações sobre suporte a cartões-presente externos, como SVS e Givex, consulte [Suporte a cartões-presente externos](./dev-itpro/gift-card.md).

> [!NOTE]
> O suporte para o resgate de vales-presentes SVS e Givex durante o fluxo de finalização de compra está disponível na versão 10.0.11 do Dynamics 365 Commerce. 

Há dois módulos de cartão-presente disponíveis:

- **Cartão-presente** - Este módulo pode ser usado em uma página de finalização de compra para resgatar um cartão-presente como meio de pagamento. 
- **Verificação de saldo do cartão-presente** - Este módulo pode ser usado em qualquer página para verificar o saldo de um cartão-presente. Este módulo está disponível nas versões 10.0.14 e posterior do Commerce.

> [!NOTE]
> O suporte para o módulo de verificação de saldo de vale-presente está disponível na versão do 10.0.14 do Dynamics 365 Commerce.

A imagem a seguir mostra um exemplo de um módulo de cartão-presente em uma página de finalização de compra.

![Exemplo de um módulo de cartão-presente.](./media/ecommerce-giftcard.PNG)

## <a name="module-properties"></a>Propriedades do módulo

- **Mostrar campos adicionais**- Essa propriedade define quais campos devem ser exibidos para cartões-presente além do número do cartão-presente, que é sempre exibido por padrão. Por exemplo, alguns cartões-presente suportam a exibição de um PIN (número de identificação pessoal) e outros suportam a exibição de um PIN e uma data de validade. Como alternativa, essa propriedade pode ser definida como "Nenhum", que exibiria somente o número do cartão-presente e nenhum outro campo.

    Os seguintes valores são compatíveis:

    - PIN
    - Data de expiração
    - PIN e data de vencimento 
    - Nenhuma

- **Habilitar para usuários convidados**: quando esta propriedade estiver habilitada, os usuários convidados podem resgatar ou consultar os saldos nos vales-presentes. Esta propriedade requer que o acesso anônimo (convidado) a vales-presentes seja habilitado no Commerce Headquarters. Para obter mais informações, consulte [Habilitar pagamentos de vale-presente para finalização do convidado](#enable-gift-card-payments-for-guest-checkout).

> [!IMPORTANT]
> A propriedade **Habilitar para usuários convidados** está disponível a partir da versão 10.0.21 do Commerce. Ela requer que o pacote de biblioteca do módulo da versão 9.31 do Commerce esteja instalado.

## <a name="site-settings-for-gift-card-modules"></a>Configurações do site para módulos de cartão-presente

No construtor de sites do Commerce em **Configurações de site \> Extensões**, há uma configuração de módulo de cartão-presente chamada **Tipo de cartão-presente compatível**. Esta configuração oferece suporte a três valores:
- **Cartão-presente do Dynamics 365** - Quando essa configuração é aplicada, o módulo do cartão-presente só permite o resgate dos cartões-presente do Dynamics 365. Essa configuração só tem suporte para usuários conectados no site de comércio eletrônico.
- **Cartões-presente SVS e Givex** - Quando essa configuração é aplicada, o módulo do cartão-presente só permite o resgate dos cartões-presente Givex e SVS. Essa configuração tem suporte para usuários conectados e anônimos no site de comércio eletrônico.
- **Cartões-presente Dynamics 365, SVS e Givex** - Quando essa configuração é aplicada, o módulo do cartão-presente só permite o resgate dos cartões-presente Dynamics 365, Givex e SVS. Essa configuração só tem suporte para usuários conectados no site de comércio eletrônico.

> [!IMPORTANT]
> Essas configurações estão disponíveis na versão 10.0.11 do Dynamics 365 Commerce e são necessárias somente se você precisar de suporte para vales-presente SVS ou Givex. Se estiver atualizando de uma versão mais antiga do Dynamics 365 Commerce, você deverá atualizar manualmente o arquivo appsettings.json. Para obter instruções sobre como atualizar o arquivo appsettings.json, consulte [SDK e atualizações da biblioteca de módulos](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file). 

## <a name="extend-internal-gift-cards-for-use-in-e-commerce-storefronts"></a>Estender cartões de presente internos para uso em lojas de comércio eletrônico

Por padrão, os cartões de presente internos não são otimizados para uso em lojas de comércio eletrônico. Portanto, antes de permitir que cartões de presente internos sejam usados para pagamento, você deve configurá-los com extensões que ajudam a torná-los mais seguros. Aqui estão as áreas de vale-presente que você deve estender antes de permitir que os vales-presentes internos sejam usados na produção:

- **Número do vale-presente** - as sequências numéricas são usadas para gerar números de vale-presente para vales-presentes internos. Como as sequências numéricas podem ser facilmente previstas, você deve estender a geração de números de vale-presente para que sequências de caracteres de segurança aleatórias e criptografadas sejam usadas para os números de cartão de presente que são emitidos.
- **Getbalance** – a API **GetBalance** é usada na pesquisa de saldos do vale-presente. Por padrão, essa API é pública. Se um PIN não for necessário para procurar saldos do vale-presente, há um risco que os ataques de força bruta pudessem usar a **API Getbalance** para tentar procurar números de vale-presente que tenham saldos. Ao implementar os dois requisitos de PIN para vales-presentes internos e limitação de API, você pode ajudar a mitigar o risco.
- **PIN** – por padrão, os vales-presentes internos não dão suporte a PINs. Você deve estender os vales-presentes internos para que um PIN seja necessário para pesquisar saldos. Essa funcionalidade também pode ser usada para bloquear vales-presentes após tentativas incorretas consecutivas de inserir o PIN.

## <a name="enable-gift-card-payments-for-guest-checkout"></a>Habilitar pagamentos do vale-presente para o finalização de compra do convidado

Por padrão, os pagamentos de vale-presente são habilitados para finalização de compra de convidado (anônimo). Para habilitá-los, siga estas etapas.

1. No Commerce headquarters, Acesse **Varejo e Comércio \> Configuração de canal \> Configuração do PDV \> PDV \> Operações de PDV**.
1. Selecione e segure (ou clique com o botão direito do mouse) no cabeçalho da grade e, em seguida, selecione **Inserir colunas**.
1. Na caixa de diálogo **Inserir colunas**, marque a caixa de seleção **AllowAnonymousAccess**.
1. Selecione **Atualizar**.
1. Para operações **520** (saldo do vale-presente) e **214**, defina o valor de **AllowAnonymousAccess** como **1**.
1. Selecione **Salvar**.
1. Execute o trabalho do agendador **1090** para sincronizar alterações para o banco de dados do canal. 

## <a name="add-a-gift-card-module-to-a-page"></a>Adicionar um módulo de cartão-presente a uma página

Para obter instruções sobre como adicionar um módulo de cartão-presente a uma página de check-in e definir as propriedades necessárias, consulte [Módulo de finalização](add-checkout-module.md).

## <a name="additional-resources"></a>Recursos adicionais

[Módulo de carrinho](add-cart-module.md)

[Módulo de ícone de carrinho](cart-icon-module.md)

[Módulo de finalização da compra](add-checkout-module.md)

[Módulo de pagamento](payment-module.md)

[Módulo de endereço de remessa](ship-address-module.md)

[Módulo de opções de entrega](delivery-options-module.md)

[Módulo de informações sobre retirada](pickup-info-module.md)

[Módulo de detalhes da ordem](order-confirmation-module.md)

[Suporte a cartões-presente externos](./dev-itpro/gift-card.md)

[SDK e atualizações da biblioteca de módulos](e-commerce-extensibility/sdk-updates.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
