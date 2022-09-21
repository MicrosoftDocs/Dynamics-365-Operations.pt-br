---
title: Descontos com base no meio de pagamento
description: Este artigo descreve a funcionalidade de desconto com base no meio de pagamento que permite que os varejistas configurem descontos para tipos específicos de meio de pagamento no Microsoft Dynamics 365 Commerce.
author: bebeale
ms.date: 08/19/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: shajain
ms.search.validFrom: 2018-10-31
ms.openlocfilehash: b11145c0c12f973b437ebf87921a5686d217d327
ms.sourcegitcommit: b1df4db7facb5e7094138836c41a65c4a158f01d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/13/2022
ms.locfileid: "9473771"
---
# <a name="tender-based-discount"></a>Desconto com base no meio de pagamento

[!include [banner](includes/banner.md)]

Este artigo descreve a funcionalidade de desconto com base no meio de pagamento que permite que os varejistas configurem descontos para tipos específicos de meio de pagamento no Microsoft Dynamics 365 Commerce.

É uma prática comum entre varejistas liberar cartões de crédito privados e com bandeira. Os varejistas têm vantagem porque conseguem tarifas preferenciais dos bancos. Além disso, como esses cartões de crédito podem incentivar os clientes a ir à loja mais vezes, isso ajuda a melhorar o lucro líquido do varejista. Portanto, os varejistas têm um incentivo para aumentar o uso de seus cartões de crédito com bandeira pelos clientes. Para atingir essa meta, geralmente oferecem descontos adicionais para clientes que usam esses cartões de crédito.

Como alternativa, os varejistas que não fornecem cartões de crédito com bandeira podem querer encorajar os clientes a realizar o pagamento usando outros meios, como dinheiro, cartões-presente ou pontos de fidelidade. Dessa forma, podem ajudar a reduzir as despesas com taxas de processamento de cartão de crédito. Portanto, os varejistas podem fornecer descontos para clientes que usam esses tipos de meio de pagamento alternativos.

## <a name="tender-based-discount"></a>Desconto com base no meio de pagamento

O Commerce oferece suporte a um *desconto com base no meio de pagamento*, que permite aos varejistas configurar um percentual de desconto aplicado a uma transação se o total da transação exceder um valor específico e o cliente pagar usando o tipo de pagamento preferencial. O desconto com base no meio de pagamento baseia-se em camadas, de forma que diferentes porcentagens de desconto possam ser associadas a diferentes limites de valores. O cliente pode decidir entre realizar um pagamento parcial ou integral, e o mecanismo de preço determina o valor de desconto apropriado. O desconto com base no meio de pagamento é sempre atribuído ao valor do imposto antecipado das linhas de venda.

O desconto com base no meio de pagamento só poderá ser aplicado a linhas de vendas em que os preços não estejam bloqueados e é distribuído proporcionalmente às linhas qualificadas. Se novas linhas de vendas forem adicionadas a uma ordem, o desconto com base no meio de pagamento só será aplicado às novas linhas de vendas durante o pagamento. Quando uma ordem do cliente para retirada ou entrega estiver sendo feita, o desconto com base no meio de pagamento será aplicado somente ao valor de depósito. Depois que a ordem for realizada, durante o processamento, os preços das linhas de vendas serão bloqueados. Nenhum desconto com base no meio de pagamento será aplicado a um saldo pago na entrega ou autorizado durante o envio. O desconto com base no meio de pagamento pode ser aplicado ao valor total de uma ordem do cliente somente se o varejista cobrar o valor total como depósito enquanto a ordem está sendo efetuada.

Os descontos com base no meio de pagamento não competem com os descontos baseados em item, como descontos simples, descontos por quantidade, descontos limite, descontos de compra combinada e descontos manuais. Os descontos com base no meio de pagamento sempre são compostos por descontos baseados em item. Portanto, mesmo se um desconto exclusivo for aplicado a um item, o desconto com base no meio de pagamento ainda pode ser aplicado sobre o desconto exclusivo. Da mesma forma, se um desconto de limite for aplicado à transação e o desconto baseado em meios de pagamento reduzir o total para abaixo do limite, o desconto de limite ainda será aplicado à transação.

Mesmo que os descontos com base no meio de pagamento reduzam o subtotal de uma transação, as cobranças automáticas aplicadas à transação não serão afetadas. Por exemplo, se os encargos de entrega forem calculados como US$ 5 porque o subtotal era superior a US$ 100 e o desconto com base no meio de pagamento reduzir para um valor inferior a US$ 100, os encargos de entrega continuarão a ser de US$ 5 para a ordem.

O desconto com base no meio de pagamento atualmente limita-se a dois tipos de pagamento: cartões de crédito e em dinheiro. Se vários descontos com base no meio de pagamento estiverem configurados para um tipo de pagamento, somente o melhor desconto com base no meio de pagamento será aplicado.

## <a name="pos-user-experience"></a>Experiência do usuário em PDV

Se um desconto com base no meio de pagamento estiver definido como à vista e um caixa no PDV (ponto de venda) selecionar o botão **Pagar em dinheiro** para fazer check-out de uma transação cash and carry, o desconto com base no meio de pagamento será automaticamente aplicado à transação. O valor com desconto será exibido como o saldo. No entanto, se o caixa selecionar o botão **Voltar** na tela do pagamento, o desconto será removido e o valor original será exibido na tela de transação. O desconto com base no meio de pagamento será removido se a linha de pagamento for anulada.

Para pagamentos em cartão de crédito, os varejistas podem definir o desconto com base no meio de pagamento para um ou mais tipos de cartões de crédito. No entanto, o sistema não pode verificar o tipo de cartão de crédito usado a menos que o cartão seja autorizado. Se o desconto for aplicado após a autorização, a autorização do pagamento será aplicada a um valor maior, mas a captura do pagamento será para um valor menor. Para ajudar a evitar essa situação, se um cliente pagar com cartão de crédito, o caixa verá uma caixa de diálogo com uma lista dos cartões de crédito preferenciais que fornecerão um desconto adicional ao cliente. O caixa poderá perguntar se o cliente deseja usar um dos cartões preferenciais para obter um desconto adicional. Se o caixa selecionar um cartão preferencial, o desconto com base no meio de pagamento será aplicado à transação e o valor com desconto será exibido na tela de pagamento. A autorização será para o valor com desconto. Se o cliente inserir um cartão diferente daquele selecionado pelo caixa, uma mensagem de erro será exibida e a autorização será anulada.

## <a name="call-center-user-experience"></a>Experiência de usuário de call center

Se um usuário do call center selecionar **Concluir** durante uma ordem do call center, a tela **Totais** será exibida. Inicialmente, os totais nesta tela não incluem descontos com base no meio de pagamento, pois o método de pagamento ainda não foi selecionado. Na tela **Adicionar pagamento**, se o usuário selecionar o método de pagamento para o qual o desconto com base no meio de pagamento foi configurado, o valor do pagamento será ajustado automaticamente para refletir o valor com desconto. Assim como um cliente no PDV, o cliente do call center pode decidir se deseja realizar o pagamento parcial ou integral. Com base no valor pago, o desconto com base no meio de pagamento será aplicado à ordem de venda.

> [!NOTE]
> A validação do cartão não é feita para ordens de call center. Por exemplo, se o usuário do call center selecionar Visa como o cartão de crédito, mas o cliente usar Mastercard, o sistema ainda aplicará o desconto.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
