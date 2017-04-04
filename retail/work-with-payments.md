---
title: "Métodos de pagamento em um call center"
description: "Este tópico aborda os métodos de pagamento diferentes que você pode usar em um call center no varejo e comércio."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 92163
ms.assetid: 8e738907-870b-466c-ab0c-07f4a4aa47f3
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 636d83ecc7732a164924352853603588cded0db4
ms.lasthandoff: 03/31/2017


---

# <a name="payment-methods-in-a-call-center"></a>Métodos de pagamento em um call center

Este tópico aborda os métodos de pagamento diferentes que você pode usar em um call center no varejo e comércio.

Os métodos de pagamento usados em outros canais em Varejo e no comércio no Microsoft Dynamics AX, como à vista, cheques, cartões de crédito e cartões-presente, também podem ser usados em call centers. Depois de configurar um método de pagamento para um call center, ele aparecerá como uma das opções na seção **Pagamentos** do formulário **Ordens de venda** para usuários de call center. Além disso, você pode configurar cupons para oferecer descontos para clientes quando eles fazem um pedido no call center da sua organização. Os cupons podem ser um desconto de valor fixo ou uma porcentagem do preço de um item ou do total da ordem. Por exemplo, um valor base de cupom pode oferecer aos clientes um desconto de R$75,00 quando o cliente gasta R$750,00 ou mais. Você pode criar diferentes tipos de cupons, configurar cupons de pai/filho e copiar ou anular um cupom. Use as opções na tabela a seguir para criar cupons.

|                           |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|---------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Atributo**             | No campo **Taxa de resgate **, insira a taxa de resgate esperada para o cupom como uma porcentagem, e selecione se o cupom pode ser usado uma única vez, se ele será reemitido automaticamente, ou se é específico de um cliente.                                                                                                                                                                                                                                                                                                                                                                                       |
| **Válido**                 | Nos campos **Data de início** e **Data de fim**, insira as datas para o primeiro e o último dias em que o cupom é válido.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| **Regras de inclusão/exclusão** | Nos campos **Catálogos** e **Itens**, selecione se algum catálogo ou item é incluído ou excluído no cupom. Se você selecionar **incluir** ou **excluir**, clique em **configurar**, selecione **incluir/excluir catálogos** ou **incluir/excluir produtos** e insira informações sobre o catálogo ou item. Se você selecionar **Nenhum** nesses campos, todos os catálogos ou itens serão incluídos no cupom.                                                                                                                                                                                                                          |
| **Diversos**         | Se esse cupom não puder ser usado em conjunto com outros descontos, selecione a caixa de seleção **Exclusivo**. Em seguida, no campo **Origem**, selecione onde o cupom pode ser usado. Se esse cupom for um cupom do fabricante, marque a caixa de seleção **Cupom de fabricante**.                                                                                                                                                                                                                                                                                                                                                                |
| **Cupom futuro**         | Se esse cupom for associado com outros cupons como o pai de outros cupons, marque a caixa de seleção **Cupom pai**. Se esse cupom precisar ser associado a um cupom filho com um cupom existente, selecione o cupom pai no campo **ID de cupom pai**. Por exemplo, você pode criar um cupom para o próximo catálogo de primavera. Todos cupons restantes que você criasse para o catálogo de primavera seria cupons filhos do cupom do catálogo de primavera. Os filhos cupons podem incluir um desconto de 20% para novas ordens de cliente, um desconto de 10% sobre um item recém-lançado ou um desconto de R$95,00 em ordens a partir de R$1.000,00. |

Se você enviar um pagamento com cartão de crédito na página **Ordens de venda** e receber uma mensagem informando que o cartão não estava autorizado, você pode manipular a autorização manualmente. Você pode autorizar, recusar ou reenviar uma transação de cartão de crédito usando a página **Gerenciamento de autorização**. Use a página de parâmetros de call center para configurar as opções de processamento de pagamento adicionais:

-   Suspensões de seleção permitem que o pessoal de finanças de ordens de processo coloquem em retidos, pois há uma verificação usada como o método de pagamento e ela mantêm o valor de limite que foi excedido. A suspensão pode ser lançada manualmente ou automaticamente expirar no final do período configurado.
-   Você pode definir limites acima do reembolso que são emitidos por meio de cheque e o cartão de crédito deve ser aprovado manualmente. Qualquer reembolso que exceda o valor de limite é adicionado à fila de aprovação. Depois de aprovar o reembolso, a ordem de venda de devolução pode ser faturada.



