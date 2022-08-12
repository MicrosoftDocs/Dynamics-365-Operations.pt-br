---
title: Descontos à vista
description: Os descontos à vista são configurados compartilhados para contas a pagar e contas a receber.  O desconto à vista disponível pode ser definido na nota fiscal do cliente ou na nota fiscal de fornecedor, e será usado se a nota fiscal for paga na data do desconto à vista.
author: angelad116
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CashDisc
audience: Application User
ms.reviewer: kfend
ms.custom: 3741
ms.assetid: c25f9d85-2702-46aa-8e61-0b4886e069b3
ms.search.region: Global
ms.author: angelading
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1969aecbda6798290367fd505bf1b6ac06235a1d
ms.sourcegitcommit: 0b7a034e644f4d93fe55c7baca5a3f89dbe56898
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/14/2022
ms.locfileid: "9151900"
---
# <a name="cash-discounts"></a>Descontos à vista

[!include [banner](../includes/banner.md)]

Os descontos à vista são configurados compartilhados para contas a pagar e contas a receber.  O desconto à vista disponível pode ser definido na nota fiscal do cliente ou na nota fiscal de fornecedor, e será usado se a nota fiscal for paga na data do desconto à vista. 

## <a name="cash-discounts"></a>Descontos à vista

Os descontos à vista para clientes ou fornecedores podem ser criados na página Descontos à vista. Você pode definir, usando o campo Próximo código de desconto, uma série de descontos à vista que se sucedem à medida que as datas de vencimento de desconto à vista anteriores se aproxima. Para obter mais informações, consulte “exemplo: série de descontos à vista” mais adiante neste artigo. Se a fatura, a transação de crédito (um pagamento ou uma nota de crédito), ou ambos forem inseridos em uma moeda diferente da moeda contábil da entidade legal, o desconto à vista é calculado usando a taxa de câmbio baseada na data de pagamento ou nota de crédito. Se a fatura e o documento de crédito forem inseridos em pessoas jurídicas diferentes, e se as moedas contábeis para a pessoa jurídica forem diferentes, a taxa de câmbio será a mesma da pessoa jurídica da fatura, a partir da data do documento de crédito. Para obter mais informações, consulte “Exemplo: taxas de câmbio para descontos à vista” mais adiante neste tópico.

## <a name="defaulting-order-of-cash-discount-main-account"></a>Usando o padrão da ordem de conta principal do desconto à vista

Se uma fatura é liquidada a tempo de obter um desconto à vista, o desconto é automaticamente lançado em uma conta principal de descontos à vista, de acordo com a seguinte prioridade padrão:
1.  A conta principal especificada no campo Conta de desconto à vista alternativa na página Liquidar transações em aberto do cliente ou na página Liquidar transações em aberto do fornecedor.
2.  A conta principal que é especificada no campo Desconto à vista do cliente ou no campo Desconto à vista do fornecedor do grupo de lançamento do razão que é atribuído ao código de imposto sobre vendas da fatura. Configure grupos de lançamentos contáveis na página Grupos de lançamento contáveis e atribua-os aos códigos de imposto na página Códigos de imposto.
3.  A conta de lançamento principal na página Descontos à vista no campo Conta principal para descontos do cliente ou no campo Conta principal para descontos de fornecedor para o código de desconto à vista que está presente na fatura liquidada.
4.  Conta principal para descontos à vista, conforme definido na página Contas para transações automáticas.

## <a name="example-series-of-cash-discounts"></a>Exemplo: série de descontos à vista
Configure três códigos de desconto à vista, da seguinte maneira:
-   Código 5D10% – um código de desconto à vista de 10% quando o valor é pago em 5 dias.
-   Código 10D5% – um desconto à vista de 5% quando o valor é pago em 10 dias.
-   Código 14D2% – um desconto à vista de 2% quando o valor é pago em 14 dias.

No campo Próximo do código de desconto:
-   Para o código 5D10%, selecione 10D5%.
-   Para o código 10D5%, selecione 14D2%.
-   Para o código 14D2%, deixe o campo Próximo código de desconto em branco.

Os três descontos à vista se sucedem conforme a data de pagamento excede a data anterior do desconto à vista na fatura. Somente um desconto à vista é concedido quando a fatura é paga, com base na data do desconto à vista que é atendida na sequência de descontos à vista.

## <a name="example-exchange-rates-for-cash-discounts"></a>Exemplo: taxas de câmbio para descontos à vista
A moeda contábil da pessoa jurídica é USD e as seguintes taxas de câmbio são especificadas para BRL:
-   1 de fevereiro = 110
-   1 de março = 80

Uma fatura de US$ 1000 com base nas condições do desconto à vista de 20D2% é lançada o 15 de fevereiro. O valor da moeda contábil da fatura é de € 1100. Um pagamento de US$ 980 é liquidado com a fatura em 1 de março. O valor do desconto à vista é de US$ 20. O valor da moeda contábil de pagamento é de US$ 490,00. O valor da moeda contábil do desconto à vista é calculado usando a taxa de câmbio de 1 de março: 20 \* 80 / 100 = € 16.

> [!NOTE]
> Se a opção Calcular descontos à vista para pagamentos parciais for selecionada nas páginas Parâmetros de contas a receber ou Parâmetros de contas a pagar, a taxa de câmbio que está em vigor na data de cada pagamento parcial será utilizada. 



[!INCLUDE[footer-include](../../includes/footer-banner.md)]
