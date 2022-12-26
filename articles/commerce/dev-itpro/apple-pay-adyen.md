---
title: Configurar Google Pay com Adyen no Dynamics 365 Commerce
description: Este artigo descreve como configurar o Apple Pay com Adyen no Microsoft Dynamics 365 Commerce.
author: BrianShook
ms.date: 11/15/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: josaw
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2022-06-20
ms.openlocfilehash: 896847cee696e221b2114f7f28a0b56e73fc911b
ms.sourcegitcommit: bdee5e642d417a13abdb778c14ec5f2dbbf8dee7
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/09/2022
ms.locfileid: "9838220"
---
# <a name="set-up-apple-pay-with-adyen-in-dynamics-365-commerce"></a>Configurar Google Pay com Adyen no Dynamics 365 Commerce

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

Este artigo descreve como configurar o Apple Pay com Adyen no Microsoft Dynamics 365 Commerce.

## <a name="key-terms"></a>Condições principais

| Termo | Descrição |
|---|---|
| Apple Pay | Também conhecido como o "botão" Apple Pay, o Apple Pay é uma oferta de pagamento de carteira que é suportada por meio do conector Adyen. Ele permite a experiência e a integração do cliente suportadas pelo Conector do Apple Pay do Microsoft Dynamics 365. |
| Carteira | Um tipo de pagamento que não inclui as características de pagamento tradicionais, como intervalo do Número de identificação do banco (BIN) e a data de vencimento, que são usados para diferenciar tipos de cartão de crédito e de débito. |

O Dynamics 365 Commerce oferece integração imediata para o Apple Pay quando o serviço de gateway de pagamento da Adyen é usado. O Apple Pay é um método de pagamento de carteira digital que usa uma conta de comerciante do Apple Pay em conjunto com o serviço de pagamento da Adyen. Quando está configurado, o botão Apple Pay fica disponível como um método de pagamento selecionável que faz parte de uma página de finalização de compra do pedido online da loja. O botão Apple Pay aparece como uma opção de pagamento apenas para dispositivos Apple Pay suportados. Quando os usuários selecionam o **Apple Pay** em um navegador ou dispositivo com suporte, eles são direcionados para preencher seu pagamento diretamente com o serviço do Apple Pay. Em seguida, eles voltam à vitrine online para concluir a ordem.

A referência do Conector de Pagamento do Dynamics 365 para Apple Pay é usada além do Conector de Pagamento do Dynamics 365 para Adyen para habilitar os pagamentos com cartão de crédito e o Apple Pay em um site. O Apple Pay também pode ser configurado para lojas com terminais de pagamento Adyen que usam o Conector de Pagamento do Dynamics 365 para Adyen com o ponto de venda (PDV) de Commerce. Nesse caso, o Conector de Pagamento do Dynamics 365 para Adyen controla o dispositivo de Pagamento da Apple pelo terminal.

## <a name="prerequisites"></a>Pré-requisitos

Usar o Apple Pay com Adyen no Commerce requer uma conta de comerciante da Apple. Para obter informações sobre como configurar o Apple Pay em sua área de cliente de teste, consulte [Integração do Apple Pay Drop-in](https://docs.adyen.com/payment-methods/apple-pay/web-drop-in#set-up-apple-pay). Para obter informações sobre o que fazer quando para implementar seu ambiente de produção, consulte [Implementação](https://docs.adyen.com/payment-methods/apple-pay/web-drop-in#going-live).

A forma de pagamento do Apple Pay também deve ser integrada à sua conta da Adyen. A Adyen pode ajudá-lo a configurar a forma de pagamento e também pode ajudar a garantir que os domínios para os quais você usará o certificado sejam atribuídos para uso com o certificado.

Para habilitar a sinalização de recurso aprimorado de carteira no Commerce headquarters, acesse **Espaços de trabalho\> Gerenciamento de recursos** e pesquise pelo recurso **Aprimoramentos avançados de suporte para carteira e pagamento**. Selecione o recurso e **Habilitar**. Depois que o recurso for habilitado, execute o agendamento de distribuição **1110** para disponibilizar a alteração em todos os canais.

## <a name="map-the-apple-pay-payment-method"></a>Mapear a forma de pagamento do Apple Pay

O Apple Pay é uma forma de pagamento de carteira digital. Para obter informações sobre como configurar o mapeamento de pagamentos para o Apple Pay, consulte [Suporte de pagamento de carteira](../wallets.md).

Para mapear a forma de pagamento do Apple Pay no Commerce headquarters, siga estas etapas.

1. Acesse **Retail e Commerce \> Configuração do canal \> Métodos de pagamento \> Tipos de cartão**.
1. Selecione **Novo** para adicionar uma linha para o Apple Pay e defina os seguintes valores:

    - **ID:** ApplePay
    - **Nome do pagamento eletrônico:** Apple Pay
    - **Tipo:** Carteira
    - **Emissor:** Apple

1. Selecione **Mapeamento do processador** para abrir a caixa de diálogo **Métodos de mapeamento de pagamentos do processador**. A coluna **Métodos de Pagamento de Processador Não Mapeados** lista as formas de pagamento aceitas para cada conector disponível (Adyen, PayPal e Apple).
1. Mapeie as formas de pagamento aceitas para o **Conector de Pagamento do Dynamics 365 para Adyen** (para uso no PDV) e o **Conector de Pagamento do Dynamics 365 para Apple Pay** (para uso no canal online).
1. Para cada linha de mapeamento, na coluna **Métodos de Pagamento de Processador Não Mapeados**, selecione a linha para oferecer suporte, depois selecione **Adicionar** para mover as seleções para a coluna **Métodos de Pagamento de Processador Mapeados**.
1. Selecione **OK** e, na página **Tipos de Cartão**, selecione **Salvar**.

## <a name="set-up-the-apple-pay-certificate-for-your-site"></a>Configurar o certificado do Apple Pay para o seu site

Para cada site, você deve carregar o arquivo de associação de domínio (também conhecido como certificado Apple Pay) conforme descrito na [Documentação Adyen Apple Pay](https://docs.adyen.com/payment-methods/apple-pay/web-drop-in#going-live). Você pode usar o criador de sites do Commerce para carregar o arquivo de associação de domínio na Biblioteca de mídia do seu site.

Siga estas etapas para configurar o certificado do Apple Pay no criador de sites.

1. Baixe o certificado (arquivo de associação de domínio) da [Adyen](https://docs.adyen.com/payment-methods/apple-pay/web-drop-in#going-live).
1. Adicione a extensão .txt ao arquivo de associação de domínio.
1. No criador de sites, [faça upload](../upload-serve-static-files.md) do arquivo de associação de domínio na Biblioteca de mídia do seu site.
1. Vá para **URLs**.
1. Selecione **Novo \> Nova URL**.
1. Na caixa de diálogo **Nova URL**, selecione **Ativo de biblioteca de mídia**.
1. No campo **Caminho da URL**, insira o caminho da URL (se já não estiver inserido). Depois da URL de base do domínio, insira a seguinte string necessária da Apple: `<domain>/.well-known/apple-developer-merchantid-domain-association.txt`.
1. Selecione **Avançar**. A Biblioteca de Mídia mostra todos os ativos de mídia carregados do tipo **documento** (.txt).
1. Selecione o arquivo de associação de domínio que deve ser fornecido para solicitações à URL que você definiu anteriormente.
1. Selecione **Criar**.

Nesse momento, a URL que você criou está em estado de rascunho. Publique a URL para concluir o processo. O arquivo para o qual a URL aponta não será retornado até que você publique a URL.

## <a name="configure-a-commerce-online-store-for-apple-pay"></a>Configurar uma loja online do Commerce para Apple Pay

Para configurar uma loja online do Commerce para o Apple Pay, siga estas etapas.

1. No Commerce headquarters, vá para **Varejo e Comércio \> Canais \> Lojas online**.
1. Selecione o valor de **ID de Canal do Varejo** referente ao canal da loja online do site.
1. Na FastTab **Contas de pagamento**, adicione o conector **Dynamics 365 Payment Connector para Adyen**, se ainda não estiver configurado, seguindo as instruções em [Configurar o Dynamics 365 Payment Connector para Adyen](adyen-connector-setup.md).
1. Depois que o conector da Adyen estiver configurado, selecione **Adicionar** para adicionar o conector **Dynamics 365 Payment Connector para Apple Pay**.
1. Insira os valores para as propriedades do comerciante do conector.

    | Propriedade               | Descrição | Necessário | Automaticamente definido | Exemplo de valor |
    | ---------------------- | ----------- | -------- | ----------------- | ------------ |
    | Nome do assembly          | O nome do assembly do Conector de Pagamento do Dynamics 365 para Apple Pay. | Sim | Sim | Nome binário |
    | ID da conta de serviço     | O identificador exclusivo da configuração das propriedades do comerciante. Esse identificador é carimbado nas transações de pagamento e identifica as propriedades do comerciante que os processos downstream (como faturamento) devem usar. | Sim | Sim | Guid |
    | ID de conta de comerciante    | Insira o identificador exclusivo de comerciante do Adyen. Esse valor é fornecido quando você se inscreve no Adyen, conforme descrito em [Inscrever-se no Adyen](adyen-connector-setup.md#sign-up-with-adyen). | Sim | Número | MerchantIdentifier |
    | Chave de API de nuvem          | Insira a chave da API da nuvem do Adyen. Para obter essa chave, siga as instruções em [Como obter a chave de API](https://docs.adyen.com/developers/user-management/how-to-get-the-api-key). | Sim | Número | abcdefg |
    | Ambiente de gateway    | Insira o ambiente de gateway da Adyen a ser mapeado. Os valores possíveis são **Teste** e **Ativo**. Você deve definir este campo como **Ativo** apenas para dispositivos e transações de produção. | Sim | Sim | Ativa |
    | Moedas com suporte   | Insira as moedas que o conector deve processar. Em cenários do cartão presente, o Adyen pode dar suporte a moedas adicionais por meio da [conversão de moeda dinâmica](https://www.adyen.com/pos-payments/dynamic-currency-conversion) depois que a solicitação de transação for enviada para o terminal de pagamento. Contate o suporte da Adyen para obter uma lista de moedas com suporte. | Sim | Sim | USD;EUR |
    | Tipos de meio de pagamento com suporte | Insira os tipos de meio de pagamento que o conector deve processar. | Sim | Sim | ApplePay |

1. Depois de inserir as informações de comerciante, execute o trabalho de agendamento de distribuição **1070** de configuração do canal.


### <a name="configure-content-security-policies-in-site-builder"></a>Configurar políticas de segurança de conteúdo no criador de sites

Antes de configurar os fragmentos ou as páginas para usar o Apple Pay, verifique se suas políticas de segurança de conteúdo (CSPs) estão configuradas no criador de sites do Commerce para o seu site.

Para configurar políticas de segurança de conteúdo no criador de sites, siga estas etapas.

1. Acesse **Configurações do Site \> Extensões**.
1. Na guia **Política de segurança de conteúdo**, selecione **Adicionar** para adicionar a linha que tem `https://applepay.cdn-apple.com/jsapi/v1/apple-pay-sdk.js` às seções **child-src**, **connect-src**, **frame-src**, **img-src**, **script-src** e **style-src**.
1. Quando terminar, selecione **Salvar e publicar** para confirmar as alterações.

### <a name="set-up-apple-pay-as-a-checkout-payment-option"></a>Configurar o Apple Pay como uma opção de finalização de compra

Para configurar o Apple Pay como uma opção de pagamento na página de finalização de compra (não expressa) do seu site, siga estas etapas.

1. No criador de sites, vá para **Fragmentos** e selecione o fragmento de finalização de compra do seu site.
1. Selecione **Editar**.
1. No slot **Contêiner da seção de finalização da compra**, selecione as reticências (**...**) e, depois, **Adicionar módulo**.
1. Na caixa de diálogo **Selecionar módulos**, selecione o módulo **Apple Pay** e, depois, **OK**.
1. Selecione **Salvar**.
1. Selecione **Concluir edição** para fazer check-in do fragmento e, depois, selecione **Publicar** para publicá-lo.

As configurações para o módulo **Apple Pay** são incorporadas ao módulo e conectadas ao Dynamics 365 Payment Connector for Apple Pay configurado para o canal online do Commerce headquarters.

### <a name="apple-pay-payment-behavior"></a>Comportamento de pagamento do Apple Pay

O botão de pagamento **Apple Pay** aparece apenas para dispositivos Apple Pay suportados (iPhones, iPads e navegadores Safari com suporte ao Apple Pay). Se um usuário não estiver usando um desses dispositivos, o botão de pagamento **Apple Pay** ficará oculto.

Quando o usuário seleciona o botão de pagamento **Apple Pay**, a caixa de diálogo **Apple Pay** é exibida. Lá, o usuário pode fazer a autenticação em seu dispositivo ou navegador Apple Pay. A caixa de diálogo **Apple Pay** mostra um resumo do valor da ordem e a forma de pagamento que o usuário configurou em sua Apple Wallet. O usuário pode revisar esses detalhes e, em seguida, selecionar **Pagar** para concluir o pagamento. Após a conclusão do pagamento, o usuário é direcionado para a página do site **Ordem concluída** que mostra um resumo detalhado do pedido para a transação concluída.

## <a name="configure-commerce-pos-for-apple-pay"></a>Configurar PDV do Commerce para Apple Pay

A configuração de PDV usa a configuração do campo **Serviço de TEF** do perfil de hardware do Conector de Pagamento do Dynamics 365 para Adyen. No Commerce Headquarters, configure o serviço de TEF para o Dynamics 365 Payment Connector para Adyen, como descrito em [Configurar um perfil de hardware de PDV do Dynamics 365](adyen-connector-setup.md#set-up-a-dynamics-365-pos-hardware-profile).

Adicione **ApplePay** à lista de tipos de pagamento no campo **Tipos de pagamento com suporte**. Use ponto-e-vírgula (;) para separar os tipos de pagamento na lista.

O mapeamento do processador para o conector da Adyen vai capturar os tipos de cartão da carteira usados pelo Apple Pay usar no terminal de PDV.

## <a name="additional-resources"></a>Recursos adicionais

[Perguntas frequentes sobre pagamentos](payments-retail.md)

[Módulo de finalização da compra](../add-checkout-module.md)

[Módulo de pagamento](../payment-module.md)
