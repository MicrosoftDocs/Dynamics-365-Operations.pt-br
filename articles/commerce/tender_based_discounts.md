---
title: Descontos com base no meio de pagamento
description: Este artigo fornece uma visão geral da funcionalidade que permite que os varejistas configurem descontos para tipos específicos de meio de pagamento.
author: bebeale
ms.date: 10/30/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailTenderDiscount
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: shajain
ms.search.validFrom: 2018-10-31
ms.dyn365.ops.version: Version 10.0.7
ms.openlocfilehash: d67819fce0fb0002ffd85324cb24aea2d2abdabb
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8871572"
---
# <a name="tender-based-discounts"></a>Descontos com base no meio de pagamento

[!include [banner](includes/banner.md)]


É uma prática comum entre varejistas liberar cartões de crédito privados e com bandeira. Os varejistas têm vantagem porque conseguem tarifas preferenciais dos bancos. Além disso, como esses cartões de crédito podem incentivar os clientes a ir à loja mais vezes, isso ajuda a melhorar o lucro líquido do varejista. Portanto, os varejistas têm um incentivo para aumentar o uso de seus cartões de crédito com bandeira pelos clientes. Para atingir essa meta, geralmente oferecem descontos adicionais para clientes que usam esses cartões de crédito.

Como alternativa, os varejistas que não fornecem cartões de crédito com bandeira podem querer encorajar os clientes a realizar o pagamento usando outros meios, como dinheiro, cartões-presente ou pontos de fidelidade. Dessa forma, podem ajudar a reduzir as despesas com taxas de processamento de cartão de crédito. Portanto, os varejistas podem fornecer descontos para clientes que usam esses tipos de meio de pagamento alternativos.

No Microsoft Dynamics 365 Commerce, os varejistas podem configurar uma porcentagem de desconto que é aplicada às linhas qualificadas, se o cliente pagar usando o tipo de meio de pagamento preferencial. O cliente pode decidir entre realizar um pagamento parcial ou integral, e o Commerce determina o valor de desconto apropriado. Observe que o desconto é definido sempre com base no valor antes do imposto dos itens qualificados.

Os descontos baseados em meios de pagamento não competem com descontos baseados em itens, como descontos periódicos ou manuais. Eles são sempre compostos com base nos descontos do item. Portanto, mesmo se um desconto periódico exclusivo for aplicado a um item, o desconto com base no meio de pagamento ainda é aplicado sobre o desconto periódico exclusivo. Da mesma forma, se um desconto de limite for aplicado à transação e o desconto baseado em meios de pagamento reduzir o total para abaixo do limite, o desconto de limite ainda será aplicado à transação.

Mesmo que os descontos com base no meio de pagamento reduzam o subtotal da transação, as cobranças automáticas aplicadas à transação não serão afetadas. Por exemplo, se os encargos de entrega forem calculados como $5 porque o subtotal era superior a $100 e o desconto baseado em meios de pagamento reduzir o valor para que seja inferior a $100, os encargos de entrega ainda serão $5 para a ordem.


> [!NOTE]
> Os descontos baseados em meios de pagamento são distribuídos proporcionalmente às linhas de vendas qualificadas e reduzem o valor antes do imposto das linhas individuais. Se múltiplos descontos baseados em meios de pagamento estiverem configurados para um tipo de meio de pagamento (por exemplo, dinheiro), somente o melhor desconto com base no meio de pagamento será aplicado.

Os descontos com base no meio de pagamento podem ser aplicados somente a linhas de vendas nas quais os preços não estão bloqueados. Se novas linhas de vendas forem adicionadas a uma ordem, o desconto com base no meio de pagamento será aplicado às novas linhas de vendas somente durante o pagamento. Enquanto estiver criando uma ordem do cliente para retirada ou entrega, o desconto com base no meio de pagamento será aplicado somente ao valor de depósito. Depois que a ordem for realizada, durante o processamento, os preços das linhas de vendas serão bloqueados. Portanto, nenhum desconto com base no meio de pagamento será aplicado a um saldo pago na entrega ou autorizado durante o envio. O desconto com base no meio de pagamento pode ser aplicado ao valor total de uma ordem do cliente somente se o varejista cobrar o valor total como depósito enquanto a ordem está sendo efetuada.

> [!IMPORTANT]
> No Commerce, os descontos com base no meio de pagamento estão atualmente limitados a dois tipos de pagamento: dinheiro e cartões de crédito.

## <a name="pos-user-experience"></a>Experiência do usuário em PDV

Se o desconto com base no meio de pagamento estiver definido como em dinheiro e o caixa no ponto de venda (PDV) selecionar um botão mapeado para a operação Pagar em dinheiro, o desconto com base no meio de pagamento será aplicado automaticamente à transação. O valor com desconto será exibido como o saldo. No entanto, se o caixa selecionar o botão **Voltar** na tela do pagamento, o desconto será removido e o valor original será exibido na tela de transação. O desconto com base no meio de pagamento será removido se a linha de pagamento for anulada.

Para pagamentos em cartão, os varejistas podem definir o desconto com base no meio de pagamento para um ou mais tipos de cartões de crédito. No entanto, o sistema não pode verificar o tipo de cartão de crédito usado a menos que o cartão seja autorizado. Se o desconto for aplicado após a autorização, a autorização do pagamento será aplicada a um valor maior, mas a captura do pagamento será para um valor menor.

Para ajudar a evitar situações como essa, se um cliente pagar com cartão de crédito, o caixa visualizará uma caixa de diálogo que lista os cartões de crédito que fornecerão economias adicionais para o cliente. O caixa poderá perguntar se o cliente deseja usar um dos cartões preferenciais para obter um desconto adicional. Se o caixa usar um cartão preferencial, o desconto com base no meio de pagamento será aplicado à transação e o valor com desconto será exibido na tela de pagamento. A autorização será para o valor com desconto. Se o cliente inserir um cartão diferente daquele selecionado pelo caixa, uma mensagem de erro será exibida e a autorização será anulada.


## <a name="call-center-user-experience"></a>Experiência de usuário de call center

Quando o usuário selecionar **Concluir** durante uma ordem do call center, a tela **Totais** será exibida. Inicialmente, os totais nesta tela não incluem descontos com base no meio de pagamento, pois o método de pagamento ainda não foi selecionado. Na tela **Adicionar pagamento**, se o usuário selecionar o método de pagamento para o qual o desconto com base no meio de pagamento foi configurado, o valor do pagamento será ajustado automaticamente para refletir o valor com desconto. Assim como o cliente no PDV, o cliente do call center pode decidir se deseja realizar o pagamento parcial ou integral. Com base no valor pago, o desconto com base no meio de pagamento será aplicado à ordem de venda.

> [!NOTE]
> A validação do cartão não é feita para ordens de call center. Por exemplo, se o usuário do call center selecionar Visa como o cartão de crédito, mas o cliente usar Mastercard, o sistema ainda aplicará o desconto.

## <a name="exclude-items-from-discounts"></a>Excluir itens dos descontos

Os varejistas geralmente optam por excluir alguns produtos, como novos itens ou itens de demanda, dos descontos. No entanto, ainda podem querer aplicar descontos com base no meio de pagamento. Por exemplo, um varejista configura o Commerce para não permitir descontos com base nos meios de pagamento ou descontos manuais. No entanto, se o cliente pagar usando o meio de pagamento preferencial, o Commerce ainda aplicará o desconto baseado em meios de pagamento. Para configurar o Commerce dessa maneira, os varejistas deverão acessar **Gerenciamento de informações sobre produtos > Produtos > Produtos lançados**, selecionar o item e, depois, na Guia Rápida **Commerce**, definir as opções **Impedir todos os descontos** e **Impedir descontos com base no meio de pagamento** como **Não**, e as opções **Impedir descontos** e **Impedir descontos manuais** como **Sim**.

> [!NOTE]
> Quando a configuração **Impedir todos os descontos** estiver definida como **Sim**, nenhum desconto será aplicado ao produto. Os descontos com base no meio de pagamento também não serão aplicados.


[!INCLUDE[footer-include](../includes/footer-banner.md)]