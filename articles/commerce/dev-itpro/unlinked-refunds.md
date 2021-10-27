---
title: Processar reembolsos desvinculados com o Dynamics 365 Commerce Payment Connector para Adyen
description: Este tópico descreve como funcionam os reembolsos desvinculados quando o Microsoft Dynamics365 Payment Connector para Adyen é usado.
author: BrianShook
ms.date: 10/07/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgri
ms.search.region: Global
ms.author: BrShoo
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: c137dcf7d35031a293c88d8c4f5dc1e5f3d9e2f9
ms.sourcegitcommit: a21a664cd35b95c8600c5af0aac588a64e892902
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/11/2021
ms.locfileid: "7623912"
---
# <a name="process-unlinked-refunds-with-the-dynamics-365-commerce-payment-connector-for-adyen"></a>Processar reembolsos desvinculados com o Dynamics 365 Commerce Payment Connector para Adyen

[!include [banner](../includes/banner.md)]

Este tópico descreve como funcionam os reembolsos desvinculados quando o [Microsoft Dynamics 365 Payment Connector para Adyen](adyen-connector.md) é usado. Ele também revisa a capacidade de processar um reembolso com base em um novo método de pagamento no POS (ponto de venda) ou no Call Center.

O Dynamics 365 Payment Connector para Adyen oferece suporte à capacidade de processar reembolsos usando um método de pagamento diferente do usado para a transação original. Embora seja recomendável usar [reembolsos vinculados](linked-refunds.md) para processar um reembolso com base no método de pagamento de origem fornecido, é necessário usar um método diferente para os reembolsos em algumas situações. Por exemplo, o cartão usado para o pagamento original pode estar vencido ou perdido, ou pode ter sido cancelado pelo usuário.

## <a name="prerequisites"></a>Pré-requisitos

Os pré-requisitos a seguir devem ser concluídos para que o Dynamics 365 Payment Connector para Adyen possa processar reembolsos não vinculados:

- Configurar [métodos de pagamento](../payment-methods.md).
- Configurar [pagamentos de omnicanal](../omni-channel-payments.md).

## <a name="additional-configuration"></a>Configurações adicionais

O Dynamics 365 Payment Connector para Adyen fornece uma implementação pronta para uso para todos os cenários compatíveis de reembolso descritos na próxima seção. Os clientes que não estiverem usando a implementação pronta para uso do Dynamics 365 Payment Connector para Adyen devem configurar o conector que oferece suporte à geração de tokens de cartões de crédito.

## <a name="supported-refund-scenarios"></a>Cenários compatíveis de reembolso

O Dynamics 365 Commerce oferece suporte a reembolsos de transações que foram aprovadas e confirmadas. Os reembolsos podem consistir em um reembolso total ou em um reembolso parcial da transação. Os reembolsos não podem exceder o valor total da autorização de pagamento original. Os reembolsos não vinculados são compatíveis somente com o POS e o call center.

## <a name="enable-unlinked-refunds-functionality"></a>Habilitar a funcionalidade de reembolsos não vinculados

Para habilitar a funcionalidade de reembolsos não vinculados na matriz do Commerce, siga estas etapas:

1. Vá para **Varejo e Comércio \> Configuração da sede \> Parâmetros \> Parâmetros compartilhados com o comércio**.
1. Na guia **Pagamentos de omnicanal**, defina a opção **Usar pagamentos de omnicanal** como **Sim**.

### <a name="supported-payment-method-variants"></a>Grades de formas de pagamento com suporte

As variantes de método de pagamento a seguir permitem reembolsos desvinculados sem qualquer configuração adicional:

- Cartões
- Carteira

Nem todas as variantes de método de pagamento são compatíveis com reembolsos não vinculados. A tabela a seguir fornece uma lista de métodos de pagamento comuns e mostra a funcionalidade de suporte de cada método a reembolsos vinculados e não vinculados.

| Forma de pagamento        | Reembolso vinculado | Reembolso não vinculado |
|-----------------------|:-------------:|:---------------:|
| amexcommercial        | Sim           | Sim             |
| amexconsumer          | Sim           | Sim             |
| amexcorporate         | Sim           | Sim             |
| amexdebit             | Sim           | Sim             |
| amexprepaid           | Sim           | Sim             |
| amexprepaidreloadable | Sim           | Sim             |
| amexsmallbusiness     | Sim           | Sim             |
| discover              | Sim           | Sim             |
| maestro               | Sim           | Sim             |
| maestrouk             | Sim           | Sim             |
| mc                    | Sim           | Sim             |
| mcalphabankbonus      | Sim           | Sim             |
| mcprepaidanonymous    | Sim           | Sim             |
| visa                  | Sim           | Sim             |
| visaalphabankbonus    | Sim           | Sim             |
| visacheckout          | Sim           | Sim             |
| visadankort           | Sim           | Sim             |
| visahipotecario       | Sim           | Sim             |
| visasaraivacard       | Sim           | Sim             |
| vpay                  | Sim           | Sim             |
| givex                 | **Não**        | Sim             |
| svs                   | **Não**        | Sim             |
| cup                   | Sim           | Sim             |
| diners                | Sim           | Sim             |
| interac               | **Não**        | Sim             |
| jcb                   | Sim           | Sim             |
| jcb_applepay          | Sim           | Sim             |
| unionpay              | Sim           | Sim             |

### <a name="process-an-unlinked-refund-in-pos"></a>Processar um reembolso não vinculado no POS

Um cliente devolve um item a um caixa do POS no período permitido para devoluções e tem uma nota fiscal válida. Durante o processamento da devolução, a caixa de diálogo **Pagamento de devolução** inclui uma opção **Escolher um método de pagamento**. O caixa pode selecionar um método de pagamento entre aqueles aceitos para reembolsos (cartões e a carteira).

### <a name="process-an-unlinked-refund-in-call-center"></a>Processar um reembolso não vinculado no call center

Quando um reembolso não vinculado é processado em uma ordem no call center, um funcionário de call center seleciona um método de pagamento que é diferente do método original. Em seguida, o funcionário é solicitado a obter um PIN (número de identificação pessoal) de substituição de administrador. O PIN é necessário para que o método de pagamento diferente possa ser processado para o reembolso.

#### <a name="set-up-an-administrator-override-pin-for-call-center"></a>Configurar um PIN de substituição de administrador para call center

Para configurar um PIN de substituição de administrador para call center na matriz do Commerce, siga estas etapas.

1. Vá para **Varejo e Comércio \> Configuração do canal \> Configuração do call center**, ou procure "Permissões de substituição".
1. Selecione a função para permitir o processamento de reembolsos não vinculados.
1. Na FastTab **Devoluções**, defina a opção **Permitir pagamento alternativo** como **Sim**.

## <a name="additional-resources"></a>Recursos adicionais

[Dynamics 365 Payment Connector para Adyen](adyen-connector.md)

[Devolução vinculadas de transações aprovadas e confirmadas](linked-refunds.md)
