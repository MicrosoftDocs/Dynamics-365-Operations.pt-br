---
title: Visão geral do Dynamics 365 Payment Connector para Adyen
description: Este artigo fornece uma visão geral do Microsoft Dynamics 365 Payment Connector para Adyen.
author: rassadi
ms.date: 11/16/2022
ms.topic: overview
audience: Application User, Developer, IT Pro
ms.reviewer: josaw
ms.custom: 141393
ms.assetid: e23e944c-15de-459d-bcc5-ea03615ebf4c
ms.search.region: Global
ms.search.industry: Retail
ms.author: rassadi
ms.search.validFrom: 2019-01-01
ms.openlocfilehash: 58d88e023b73ce19331bd6f54644a62d8f6f35af
ms.sourcegitcommit: 3aa3dedc3123cb079614762e2718841c2f7d7d35
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/30/2022
ms.locfileid: "9812077"
---
# <a name="dynamics-365-payment-connector-for-adyen-overview"></a>Visão geral do Dynamics 365 Payment Connector para Adyen

[!include [banner](../includes/banner.md)]

Este artigo fornece uma visão geral do Microsoft Dynamics 365 Payment Connector para Adyen. e inclui uma lista abrangente de recursos e funcionalidades compatíveis. Os artigos relacionados abordam inscrição de Adyen, a configuração do conector, as perguntas frequentes e a orientação de solução de problemas para alguns problemas comuns.

## <a name="key-terms"></a>Condições principais

| Termo | Descrição |
|---|---|
| Conector de pagamento | Uma extensão que facilita a comunicação entre o Microsoft Dynamics 365 Commerce (e componentes associados) e um serviço de pagamento. O conector que é descrito neste artigo foi implementado usando o kit de desenvolvimento de software (SDK) de pagamentos padrão. |
| O cartão está presente | Consulte as transações de pagamento nas quais um cartão físico é apresentado e usado em um conector do terminal de pagamento para o Ponto de Venda do Dynamics 365. |
| O cartão não está presente | Consulte as transações de pagamento nas quais não há uma placa física, como cenários de Comércio Eletrônico ou de Call Center. Nestes cenários, as informações relacionadas ao pagamento são inseridas manualmente em um site de Comércio Eletrônico, em um fluxo do Call Center ou no terminal de PDV ou de pagamento. |

## <a name="supported-features-functionality-versions-and-terminals"></a>Recursos, funcionalidades, versões e terminais compatíveis

O Dynamics 365 Payment Connector para Adyen pronto para uso usa o SDK de pagamentos padrão. Portanto, ele não tem recursos especiais que também não estão disponíveis para outros conectores de pagamento.

### <a name="supported-versions"></a>Versões com suporte

#### <a name="microsoft-dynamics-365-supported-versions"></a>Versões compatíveis com o Microsoft Dynamics 365
O Dynamics 365 Payment Connector para Adyen próprio e pronto para uso é compatível no Microsoft Dynamics 365 Finance, versão 8.1.3 (Janeiro de 2019) ou posterior, e no Microsoft Dynamics 365 Retail, versão 8.1.3 ou posterior. No entanto, as empresas terceirizadas ainda podem desenvolver outros conectores de pagamento para Adyen para versões anteriores do Microsoft Dynamics 365.

#### <a name="supported-adyen-firmware-versions"></a>Versões de firmware Adyen compatíveis

A lista a seguir descreve as versões mínima e máxima do firmware Adyen suportadas para cada versão do Microsoft Dynamics 365 Retail POS.

---

# <a name="10025"></a>[10.0.25](#tab/10-0-25)
### <a name="dynamics-365-retail-pos-version-10025"></a>Versão 10.0.25 do Dynamics 365 Retail POS
| Versão mínima de Firmware Adyen | Versão máxima de Firmware Adyen |
| --- | --- |
| adyen_v1_71p16 | adyen_v1_73p6 |

# <a name="10026"></a>[10.0.26](#tab/10-0-26)
### <a name="dynamics-365-retail-pos-version-10026"></a>Versão 10.0.26 do Dynamics 365 Retail POS
| Versão mínima de Firmware Adyen | Versão máxima de Firmware Adyen |
| --- | --- |
| adyen_v1_73p6 | adyen_v1_75p13 |

# <a name="10027"></a>[10.0.27](#tab/10-0-27)
### <a name="dynamics-365-retail-pos-version-10027"></a>Versão 10.0.27 do Dynamics 365 Retail POS
| Versão mínima de Firmware Adyen | Versão máxima de Firmware Adyen |
| --- | --- |
| adyen_v1_73p6 | adyen_v1_75p13 |

# <a name="10028"></a>[10.0.28](#tab/10-0-28)
### <a name="dynamics-365-retail-pos-version-10028"></a>Versão 10.0.28 do Dynamics 365 Retail POS
| Versão mínima de Firmware Adyen | Versão máxima de Firmware Adyen |
| --- | --- |
| adyen_v1_73p6 | adyen_v1_75p22 |

# <a name="10029"></a>[10.0.29](#tab/10-0-29)
### <a name="dynamics-365-retail-pos-version-10029"></a>Versão 10.0.29 do Dynamics 365 Retail POS
| Versão mínima de Firmware Adyen | Versão máxima de Firmware Adyen |
| --- | --- |
| adyen_v1_71p16 | adyen_v1_78p6 |

# <a name="10030"></a>[10.0.30](#tab/10-0-30)
### <a name="dynamics-365-retail-pos-version-10030"></a>Versão 10.0.30 do Dynamics 365 Retail POS
| Versão mínima de Firmware Adyen | Versão máxima de Firmware Adyen |
| --- | --- |
| adyen_v1_71p16 | adyen_v1_78p6 |

---

> [!NOTE]
> O Adyen pode lançar atualizações secundárias da versão após a Microsoft ter testado a versão principal. Desde que haja suporte para uma versão principal, não há problema em ter atualizações de versão secundárias na mesma versão principal. Essas atualizações normalmente são correções pretendidas e não atendem à barra para o reteste completo, desde que a mesma versão principal do firmware tenha sido testada anteriormente. As atualizações não devem exceder a versão máxima do firmware Adyen listada na documentação. 
>
> A migração de uma versão de firmware Adyen anterior à versão 53 para a versão 53 requer o POS KB **4577957** para atualizações mensais do Commerce, versões 10.0.11 até 10.0.14. Se uma dessas versões estiver em uso e não incluir o hotfix, a atualização após o terminal de pagamento só permitirá pagamentos via NFC. A aplicação do hotfix no PDV resolve esse problema. Se a versão de PDV for anterior à versão 10.0.11, arquivar uma solicitação de suporte que indica uma correção para o KB **4577957** é necessária para um dos MPOs de serviço.
> 
> Para versões de firmware de Adyen 59p7 até 62p9, a operação **resgate do cartão presente** solicita a entrada do PIN duas vezes em cenários em que o cartão-presente é inserido manualmente. Esse problema não é reproduzido quando o vale-presente é passado. Adyen está investigando. 

### <a name="supported-payment-terminals"></a>Terminais de pagamento com suporte
O Dynamics 365 Payment Connector para Adyen se beneficia da [API de Terminal de Pagamento da Adyen](https://www.adyen.com/blog/introducing-the-terminal-api) independente do dispositivo. Ele oferece suporte a todos os terminais de pagamento para os quais essa API (interface de programação de aplicativos) é compatível. Para obter uma lista completa dos terminais de pagamento com suporte, visite [Terminais de PDV Adyen](https://www.adyen.com/pos-payments/terminals).

O vídeo a seguir descreve os recursos do terminal de pagamento Adyen Castles SE1 Android.


> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE5bKeM]

### <a name="supported-payment-instruments"></a>Meios de pagamento compatíveis

#### <a name="supported-debit-and-credit-cards"></a>Cartões de crédito e débito compatíveis

| Marca | Grade | O cartão está presente | Comércio eletrônico | Call center |
|---|---|:-:|:-:|:-:|
| MasterCard | Crédito | ✔ | ✔ | ✔ |
| MasterCard | Débito | ✔ | ✔ | ✔ |
| MasterCard | Alpha Bank Bonus | ✔ | ✔ | ✔ |
| MasterCard | Apple Pay | ✔ |  |  |
| MasterCard | Samsung Pay | ✔ |  |  |
| MasterCard | Maestro | ✔ | ✔ | ✔ |
| MasterCard | Maestro Samsung Pay | ✔ |  |  |
| MasterCard | Maestro UK | ✔ | ✔ | ✔ |
| VISA | Crédito | ✔ | ✔ | ✔ |
| VISA | Débito | ✔ | ✔ | ✔ |
| VISA | Alpha Bank Bonus | ✔ | ✔ | ✔ |
| VISA | Android Pay | ✔ |  |  |
| VISA | Apple Pay | ✔ |  |  |
| VISA | Samsung Pay | ✔ |  |  |
| VISA | Finalização da Compra VISA | ✔ | ✔ | ✔ |
| VISA | VISA Dankort | ✔ | ✔ | ✔ |
| VISA | VISA Hipotecario | ✔ | ✔ | ✔ |
| VISA | Cartão de Aravia da VISA | ✔ | ✔ | ✔ |
| AMEX | Crédito | ✔ | ✔ | ✔ |
| AMEX | Débito | ✔ | ✔ | ✔ |
| AMEX | Android Pay | ✔ |  |  |
| AMEX | Apple Pay | ✔ |  |  |
| AMEX | Samsung Pay | ✔ |  |  |
| AMEX | AMEX Commercial | ✔ | ✔ | ✔ |
| AMEX | AMEX Consumer | ✔ | ✔ | ✔ |
| AMEX | AMEX Corporate | ✔ | ✔ | ✔ |
| AMEX | AMEX Pequenas empresas | ✔ | ✔ | ✔ |
| Discover | Padrão | ✔ | ✔ | ✔ |
| Discover | Android Pay | ✔ |  |  |
| Discover | Apple Pay | ✔ |  |  |
| Discover | Samsung Pay | ✔ |  |  |
| Diners   | Padrão | ✔ | ✔ | ✔ |
| Dineromail | Padrão | ✔ | ✔ | ✔ |
| JCB | Padrão | ✔ | ✔ | ✔ |
| Union Pay\* | Padrão | ✔ |  |  |
| Interac Debit\* | Padrão | ✔ |  |  |

\*Tokens de cartão recorrente Interac e Union não são fornecidos por Adyen e, portanto, não têm suporte para transações de cartão não presente.

#### <a name="supported-gift-cards"></a>Cartões-presente compatíveis
| Esquema | O cartão está presente | O cartão não está presente |
|---|:-:|---|
| Givex | ✔ | ✔ |
| SVS | ✔ | ✔ |

Para dar suporte a esses esquemas de cartão-presente externos por meio do Dynamics 365 Payment Connector para Adyen, você deve executar etapas adicionais. Para obter mais informações, consulte [Suporte a cartões-presente externos](/dynamics365/unified-operations/retail/dev-itpro/gift-card)externos.

#### <a name="supported-wallets"></a>Wallets com suporte

| Esquema | O cartão está presente | O cartão não está presente |
|---|---|---|
| Alipay | O suporte será adicionado em uma versão futura. | Número |
| WeChat | O suporte será adicionado em uma versão futura. | Número |

#### <a name="supported-card-present-input-methods"></a>Métodos de entrada de cartão-presente compatíveis
| Método de entrada | Com suporte | Notas |
|---|:-:|---|
| Dip | ✔ | |
| Passar cartão | ✔ | |
| Toque | ✔ | |
| A Entrada Manual por meio da IU de PDV. |  | Não há suporte neste momento |
| Entrada Manual por meio de um Terminal de Pagamento. | ✔ | Oferece suporte à entrada manual de cartões de crédito, débito e presente com entrada de PIN. | 


#### <a name="supported-card-present-countries"></a>Cartão com suporte para os países atuais

Os seguintes países têm componentes do Commerce disponíveis e o suporte do cartão presente no Adyen. Para a disponibilidade internacional atual do Commerce, visite a [página de disponibilidade internacional](/dynamics365/get-started/availability).

| País | Com suporte |
| --- | :-: |
| Austrália | ✔ |
| Áustria | ✔ |
| Bélgica | ✔ |
| Canadá | ✔ |
| República Tcheca | ✔ |
| Dinamarca | ✔ |
| Estônia | ✔ |
| Finlândia | ✔ |
| França | ✔ |
| Alemanha | ✔ |
| RAE de Hong Kong | ✔ |
| Hungria | ✔ |
| Islândia | ✔ |
| Irlanda | ✔ |
| Itália | ✔ |
| Japão | Versão futura |
| Letônia | ✔ |
| Lituânia | ✔ |
| Malásia | ✔ |
| Países Baixos | ✔ |
| Nova Zelândia | ✔ |
| Noruega | ✔ |
| Polônia | ✔ |
| Singapura | ✔ |
| Suíça | ✔ |
| Espanha | ✔ |
| Suécia | ✔ |
| Suíça | ✔ |
| Reino Unido | ✔ |
| Estados Unidos | ✔ |
| Brasil | Versão futura |

#### <a name="supported-card-not-present-countries"></a>Cartão sem suporte para países atuais

Os países a seguir têm suporte do Adyen para transações de cartão não presente. [Contatar a Adyen](https://www.adyen.com/contact/sales) para obter detalhes sobre o suporte a um país específico. Para a disponibilidade internacional atual do Commerce, visite a [página de disponibilidade internacional](/dynamics365/get-started/availability).

| País | 
| --- |
| Argentina |
| Armênia |
| Austrália |
| Áustria |
| Barein |
| Bélgica |
| Brasil |
| Bulgária |
| Canadá |
| Chile |
| China |
| Colômbia |
| Croácia |
| Chipre |
| República Tcheca  |
| Dinamarca |
| Egito |
| Estônia |
| Finlândia |
| França |
| Geórgia |
| Alemanha |
| Gibraltar |
| Grécia |
| Guernsey |
| RAE de Hong Kong |
| Hungria |
| Islândia |
| Índia |
| Indonésia |
| Irlanda |
| Ilha de Man |
| Israel |
| Itália |
| Japão |
| Jersey |
| Coreia |
| Kuwait |
| Letônia |
| Lituânia |
| Luxemburgo |
| Malásia |
| Malta |
| México |
| Marrocos |
| Países Baixos |
| Nova Zelândia |
| Noruega |
| Peru |
| Polônia |
| Portugal |
| Catar |
| Romênia |
| Arábia Saudita |
| Sérvia |
| Singapura |
| Eslováquia |
| Eslovênia |
| África do Sul |
| Espanha |
| Suécia |
| Suíça |
| Taiwan |
| Tanzânia |
| Tailândia |
| Turquia |
| Emirados Árabes Unidos (EAU) |
| Reino Unido |
| Estados Unidos da América, incluindo Porto Rico  |

#### <a name="supported-dynamics-365-payment-features"></a>Recursos de pagamento do Dynamics 365 compatíveis

A tabela a seguir mostra o conjunto de recursos para os quais o Dynamics 365 Payment Connector para Adyen oferece suporte. Esses recursos usam aperfeiçoamentos que foram introduzidos no SDK de pagamentos e alguns componentes em dezembro de 2018. Eles não são exclusivas do Dynamics 365 Payment Connector para Adyen. Para obter mais informações sobre como seguir esses aperfeiçoamentos para um conector de pagamento diferente, consulte [Criar uma integração de pagamento de ponta a ponta para um terminal de pagamento](/dynamics365/unified-operations/retail/dev-itpro/end-to-end-payment-extension).

| Esquema | O cartão está presente | O cartão não está presente |
|---|:-:|:-:|
| [Resgatar Saldo de Cartão-Presente](/dynamics365/unified-operations/retail/dev-itpro/gift-card-cash-out) | ✔ | |
| [Proteção de Pagamento Duplicada](/dynamics365/unified-operations/retail/duplicate-payment-protection) | ✔ | |
| Tokenização do Omnicanal | ✔ | ✔ |
| Reembolsos Vinculados | ✔<br>(Iniciando com 10.0.1) | ✔<br>(Iniciando com 10.0.1) |
| [Salvar pagamentos online](../dev-itpro/adyen-connector-listPI.md) | | ✔<br>(Iniciando com 10.0.2) | 
| [Cartões-presente externos para call center e comércio eletrônico](./gift-card.md) | ✔<br>(Iniciando com 10.0.10) | 
| [Redirecionamento de pagamento de SCA](../adyen_redirect.md) | | ✔<br>(Iniciando com 10.0.12) |
| [Terminais de pagamento dedicados e solicitações para uma impressora e caixa registradora](../pos-multi-hws.md) | ✔<br>(Iniciando com 10.0.12) | |
| [Suporte a gorjetas no nível do SDK por meio do conector Adyen](tipping.md) | ✔<br>(Iniciando com 10.0.14) | |
| [Captura incremental para faturamento de ordem](incremental-capture.md) |  | ✔<br>(Iniciando com 10.0.18) |
| [Pagamentos de Carteira](../wallets.md) |  | ✔<br>(Iniciando com 10.0.20) |
| [Google Pay com Adyen](google-pay-adyen.md) |  | ✔<br>(Iniciando com 10.0.27) |

## <a name="next-steps"></a>Próximas etapas

Para obter mais informações sobre como fazer a inscrição e configurar o Dynamics 365 Payment Connector para Adyen, consulte [Configuração do Dynamics 365 Payment Connector para Adyen](adyen-connector-setup.md).

## <a name="additional-resources"></a>Recursos adicionais

[Configurar o Dynamics 365 Payment Connector para Adyen](adyen-connector-setup.md)

[Perguntas frequentes sobre o Dynamics 365 Payment Connector para Adyen](adyen-connector-faq.md)

[Solucionar problemas do Dynamics 365 Payment Connector para Adyen](adyen-connector-troubleshoot.md)

[Perguntas frequentes sobre pagamentos](/dynamics365/unified-operations/retail/dev-itpro/payments-retail)

[!INCLUDE [footer-include](../../includes/footer-banner.md)]
