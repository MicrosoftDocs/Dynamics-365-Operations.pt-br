---
title: Terminais de pagamento dedicados e solicitações para uma impressora e caixa registradora
description: Este tópico fornece informações sobre o recurso para ter um terminal de pagamento dedicado e solicita que o usuário selecione uma caixa registradora e uma impressora de recibo.
author: rubendel
manager: AnnBe
ms.date: 05/20/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: 141393
ms.assetid: e23e944c-15de-459d-bcc5-ea03615ebf4c
ms.search.region: Global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2019-03-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 848e83505e9e20111c2809000dcf19f352142de4
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5223014"
---
# <a name="dedicated-payment-terminals-and-prompts-for-a-printer-and-cash-drawer"></a>Terminais de pagamento dedicados e solicitações para uma impressora e caixa registradora

[!include [banner](includes/banner.md)]

Este tópico fornece informações sobre o recurso para ter um terminal de pagamento dedicado e solicita que o usuário selecione uma caixa registradora e uma impressora de recibo.

## <a name="overview"></a>Visão Geral

Os varejistas modernos estão buscando maneiras de simplificar a experiência de check-out na loja. As tendências recentes em relação a check-out sem papel por meio de pagamentos eletrônicos não só ajudam a tornar a experiência de compras mais suave, mas também reduzem a necessidade de ter um complemento completo de dispositivos periféricos disponíveis para cada associação de armazenamento.

O Microsoft Dynamics 365 Commerce oferece suporte a essas tendências habilitando um cenário no qual um dispositivo de ponto de venda (PDV) tem um terminal de pagamento dedicado atribuído a ele o tempo todo, mas ele não tem sua própria impressora de recibo ou caixa registradora. Quando os associados tiverem de imprimir um recibo ou receber um pagamento à vista, deverão selecionar uma estação de hardware na qual esses dispositivos estão configurados.

## <a name="key-terms"></a>Condições principais

| Termo | descrição |
|---|---|
| PDV | A entidade usada para configurar uma instância de uma registradora de PDV. |
| Dispositivo | Uma representação da instância física de uma registradora de PDV e do aplicativo de Modern POS atribuído a ela. |
| Estação de hardware dedicada | A lógica de negócios de estação de hardware integrada aos aplicativos Modern POS para Windows e Modern POS para Android. |
| Porta de abertura de gaveta (d/k) | Um método tradicional para conectar uma caixa registradora a uma impressora de recibo. |
| Periféricos de rede | Suporte interno para terminais de pagamento habilitados para rede, impressoras de recibo e gavetas de caixa. |

## <a name="supported-pos-clients-and-devices"></a>Clientes e dispositivos de PDV com suporte

A funcionalidade descrita neste tópico é compatível com os clientes de PDV Modern POS para Windows e o Modern POS para Android.

Essa funcionalidade oferece suporte a terminais de pagamento e impressoras de recibo habilitados para rede. Você pode fornecer suporte à caixa registradora conectando a caixa registradora à impressora de recibo habilitada para rede por meio da porta d/k.

O suporte pronto para uso para essa funcionalidade é fornecido pelo [Dynamics 365 Payment Connector for Adyen](https://docs.microsoft.com/dynamics365/commerce/dev-itpro/adyen-connector?tabs=8-1-3). No entanto, outros conectores de pagamento podem ter suporte por meio do kit de desenvolvimento de software (SDK) do Commerce para pagamentos. As impressoras de recibo incluem impressoras de recebimento habilitadas para Star Micronics e Epson.

Para configurar impressoras de recibo Star Micronics, use o Utilitário de Impressora Star Micronics para configurar o dispositivo de forma que ele possa ser usado na rede. Esse utilitário também fornecerá o endereço IP do dispositivo.

Para configurar impressoras de recibo da Epson, use o utilitário Epson ePOS-Print para configurar o dispositivo a fim de usar protocolos de rede.

Para obter mais informações sobre como configurar os periféricos da rede, consulte [Visão geral de suporte de periféricos de rede](https://go.microsoft.com/fwlink/?linkid=2129965).

## <a name="set-up-a-dedicated-payment-terminal-and-a-prompt-for-a-printer-and-cash-drawer"></a>Configurar um terminal de pagamento dedicado e um solicitação para uma impressora e caixa registradora

### <a name="set-up-hardware-profiles"></a>Configurar perfis de hardware

Você deve ter dois tipos de perfil de hardware. O primeiro é atribuído à registradora. A segunda é atribuída a uma estação de hardware no nível da loja e é usada para agrupar logicamente as impressoras de recebimento de rede e as gavetas de caixa.

#### <a name="set-up-a-hardware-profile-for-the-register"></a>Configurar um perfil de hardware para a registradora

Para configurar o perfil de hardware atribuído à registradora, siga estas etapas.

1. No Dynamics 365 Commerce, procure **Perfil de hardware**.
2. Selecione **Novo**.
3. Atribua um número de perfil de hardware e digite uma descrição. Esse perfil de hardware será atribuído à própria registradora. Portanto, uma descrição como **Dedicada com fallback** será suficiente.
4. Nas Guias Rápidas para tipos de dispositivo diferentes, configure os seguintes tipos de dispositivo.

    | Dispositivo | Tipo | Nome do dispositivo | Detalhes adicionais |
    |---|---|---|---|
    | Impressora | Fallback | *Qualquer* | O nome do dispositivo diferencia letras maiúsculas de minúsculas. A **ID do perfil de recibo** deve ser igual à **ID do perfil de recibo** mapeada para a impressora de rede que está configurada no perfil de hardware atribuído à estação de hardware no nível do canal. |
    | Caixa registradora | Fallback | *Qualquer* | O nome do dispositivo diferencia letras maiúsculas de minúsculas. Defina a opção **Usar turno compartilhado** como **Sim**. |
    | Serviço de TEF | Adyen | Não Aplicável | Para obter informações sobre como configurar o conector Adyen pronto para uso, consulte [Dynamics 365 Payment Connector for Adyen](https://docs.microsoft.com/dynamics365/commerce/dev-itpro/adyen-connector?tabs=8-1-3). Outros conectores de pagamento podem ter suporte por meio do [kit de desenvolvimento de software (SDK) do Commerce para pagamentos](https://docs.microsoft.com/dynamics365/commerce/dev-itpro/end-to-end-payment-extension). |
    | Teclado do PIN | Rede | **MicrosoftAdyenDeviceV001** | Nenhum. |

5. No Dynamics 365 Commerce, procure **registradoras**.
6. Selecione uma registradora selecionando o número da registradora e selecione **Editar**.
7. Atribua o perfil de hardware que você acabou de criar para a registradora que deve usar um terminal de pagamento dedicado. O dispositivo mapeado para esse registro deve usar o aplicativo Modern POS para Windows ou o aplicativo Modern POS para Android.
8. Selecione **Salvar**.
9. No Painel de ações, na guia **Registradoras**, selecione **Configurar endereços IP**.
10. Na Guia Rápida **Teclado do PIN**, insira o endereço IP do terminal de pagamento. Para obter informações sobre como obter o endereço IP do terminal de pagamento usando o conector Adyen, consulte [Dynamics 365 Payment Connector for Adyen](https://docs.microsoft.com/dynamics365/commerce/dev-itpro/adyen-connector?tabs=8-1-3).
11. Selecione **Salvar**.

#### <a name="set-up-a-hardware-profile-for-the-receipt-printer-and-cash-drawer"></a>Configurar um perfil de hardware para a impressora de recibo e a caixa registradora

Para configurar o perfil de hardware usado para agrupar a impressora de recibo de rede e a caixa registradora, siga estas etapas.

1. No Dynamics 365 Commerce, procure **Perfil de hardware**.
2. Selecione **Novo**.
3. Atribua um número de perfil de hardware e digite uma descrição. Este perfil de hardware será usado para agrupar a impressora de recibo e a caixa registradora. Portanto, uma descrição, como **impressora de rede e caixa registradora**, será suficiente.
4. Nas Guias Rápidas para tipos de dispositivo diferentes, configure os seguintes tipos de dispositivo.

    | Dispositivo | Tipo | descrição | Detalhes adicionais |
    |---|---|---|---|
    | Impressora | Rede | **Epson** ou **Star** | O nome do dispositivo diferencia letras maiúsculas de minúsculas. A **ID do perfil de recibo** deve ser igual à **ID do perfil de recibo** mapeada para a impressora de rede que está configurada no perfil de hardware atribuído à registradora. |
    | Caixa registradora | Rede | **Epson** ou **Star** | O nome do dispositivo diferencia letras maiúsculas de minúsculas. defina a opção **Usar turno compartilhado** como **Sim**. |

5. Selecione **Salvar**.

### <a name="set-up-hardware-stations"></a>Configurar estações de hardware

Você deve ter duas estações de hardware. A primeira será mapeada para a registradora. A segunda será selecionada quando for necessária, sempre que um recibo tiver de ser impresso ou uma caixa registradora tiver de ser aberta.

#### <a name="register-a-hardware-station"></a>Registrar uma estação de hardware

1. No Dynamics 365 Commerce, procure **Todas as lojas**.
2. Selecione uma loja selecionando seus valores **Id de Canal de Varejo** e, em seguida, selecione **Editar**.
3. Na Guia Rápida **Estações de hardware**, selecione **Adicionar**.
4. Defina o campos **Tipo de estação de hardware** como **Dedicada**.
5. Insira uma descrição, mas não defina nenhum outro valor para essa estação de hardware. Essa estação de hardware será usada para a registradora o tempo todo. 

#### <a name="set-up-a-hardware-station-for-the-receipt-printer-and-cash-drawer"></a>Configurar uma estação de hardware para a impressora de recibo e a caixa registradora

1. No Dynamics 365 Commerce, procure **Todas as lojas**.
2. Selecione uma loja selecionando seus valores **Id de Canal de Varejo** e, em seguida, selecione **Editar**.
3. Na Guia Rápida **Estações de hardware**, selecione **Adicionar**.
4. Defina o campos **Tipo de estação de hardware** como **Dedicada**.
5. Insira uma descrição. Essa estação de hardware será usada para a impressora de recibo e a caixa registradora.
6. No campo **Perfil de hardware**, selecione o perfil de hardware criado anteriormente para a impressora de recibo e a caixa registradora.
7. Selecione **Salvar**.
8. Enquanto a estação de hardware para a impressora de recibo e a caixa registradora ainda está selecionada, escolha **Configurar endereços IP**.
9. Obtenha o endereço IP da impressora e digite-o como o endereço IP para a impressora de recibo e a caixa registradora.
10. Selecione **Salvar**
11. Procurar **Agendas de distribuição**.
12. Selecione a agenda de distribuição **1090** e selecione **Executar agora**.
13. Selecione a agenda de distribuição **1070** e selecione **Executar agora**.

### <a name="set-up-the-system-to-prompt-for-receipt-printer-and-cash-drawer-selection-as-its-required"></a>Configurar o sistema para solicitar a impressora de recibo e a seleção de caixa registradora conforme necessário

1. Em um cliente de PDV com suporte, feche o turno atual, se houver um turno aberto.
2. Entre e selecione **Operações de gaveta não sacadora**.
3. Use a operação **Gerenciar estações de hardware** para ativar uma estação de hardware.
4. Selecione a estação de hardware que você criou para a registradora para torná-la ativa.
5. Saia do PDV, entre novamente e abra um turno.

O terminal de pagamento atribuído ao perfil de hardware será sempre ativo e você será solicitado a informar se uma impressora de recibo ou uma caixa registradora é necessária.

Muitos comerciantes que solicitaram esse recurso estão interessados em reduzir o desperdício, fornecendo recibos por email e incentivando pagamentos eletrônicos. Dependendo da configuração do PDV, os associados da loja deverão selecionar uma impressora de recibo ou caixa registradora somente quando um cliente desejar um recebimento físico ou se quiser pagar com dinheiro.

Os associados da loja devem selecionar uma estação de hardware somente uma vez por transação, a menos que um recebimento deva ser impresso e o dinheiro seja usado para pagamento, mas o perfil de hardware que foi originalmente selecionado não inclui os dois dispositivos. Nesse caso, o associado da loja deverá selecionar novamente uma estação de hardware que possa ser usada para concluir a transação.

## <a name="related-articles"></a>Artigos relacionados

- [Configurar o aplicativo POS hybrid no Android e iOS](https://docs.microsoft.com/dynamics365/commerce/dev-itpro/hybridApp)
- [Conector de Pagamento do Dynamics 365 para Adyen](https://docs.microsoft.com/dynamics365/commerce/dev-itpro/adyen-connector?tabs=8-1-3)
- [Visão geral de suporte de periféricos de rede](https://go.microsoft.com/fwlink/?linkid=2129965)


[!INCLUDE[footer-include](../includes/footer-banner.md)]