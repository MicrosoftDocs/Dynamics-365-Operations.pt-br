---
title: Pagamentos de imposto e regras de arredondamento
description: "Este artigo explica como a configuração de regra de arredondamento funciona em Autoridades de imposto e o arredondamento do saldo de imposto durante o trabalho Liquidar e lançar imposto."
author: ShylaThompson
manager: AnnBe
ms.date: 08/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: TaxAuthority
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 6134
ms.assetid: 7dcd3cf5-ebdf-4a9f-806c-1296c7da0331
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 13470282efc6b9135e86355cf8071b841aad3071
ms.contentlocale: pt-br
ms.lasthandoff: 11/03/2017

---

# <a name="sales-tax-payments-and-rounding-rules"></a>Pagamentos de imposto e regras de arredondamento

[!include [banner](../includes/banner.md)]

Este artigo explica como a configuração de regra de arredondamento funciona em Autoridades de imposto e o arredondamento do saldo de imposto durante o trabalho Liquidar e lançar imposto.

Periodicamente, o imposto deve ser informado e pago às autoridades fiscais. Isso pode ser feito executando o processo de pagamento de liquidação e pós-venda na página de imposto de vendas. O imposto sobre vendas de um período será liquidado contra as contas de imposto sobre vendas e o saldo do imposto sobre vendas será lançado na conta de liquidação de imposto de vendas. O saldo do imposto, que é lançado na conta de liquidação do imposto, pode ser arredondado conforme exigido pelas autoridades fiscais para configurar uma regra de arredondamento na página Impostos. 

A diferença de arredondamento é lançada na conta de arredondamento de Impostos que é selecionada no campo Contas para transações automáticas na Contabilidade.

O exemplo a seguir ilustra como funciona a regra de arredondamento na autoridade de impostos.

### <a name="example"></a>Exemplo:

O imposto total para um período mostra um saldo de crédito de -98.765,43. A entidade legal coletou mais imposto do que pagou. Portanto, a entidade legal deve dinheiro à autoridade fiscal. 

A entidade legal quer usar um método de arredondamento que arredonda para o valor mais perto de 1,00. O usuário responsável pela contabilização do imposto conclua as etapas a seguir.

1.  Clique em Imposto &gt; Impostos indiretos &gt; Imposto &gt; Autoridades do imposto
2.  Na Guia Rápida Geral, selecione Normal no campo Forma de arredondamento.
3.  No campo Arredondamento, digite 1,00.
4.  Na época de pagar os impostos à autoridade fiscal, abra a página Liquidar e lançar imposto. (Clique em Imposto &gt; Declarações &gt; Imposto &gt; Liquidar e lançar imposto.)
5.  Na conta de liquidação do imposto, o valor da obrigação fiscal de 98.765.43 foi arredondado para 98.765.

A tabela a seguir mostra como um valor 98.765,43 é arredondado usando cada método de arredondamento que está disponível no campo Forma de arredondamento na página Autoridades do imposto.

| Opção da forma de arredondamento                | Valor de arredondamento = 0,01 | Valor de arredondamento = 0,10 | Valor de arredondamento = 1,00 | Valor de arredondamento = 100,00 |
|-------------------------------------|------------------------|------------------------|------------------------|--------------------------|
| Normal                              | 98,765.43              | 98,765.40              | 98,765.00              | 98,800.00                |
| Para baixo                            | 98,765.43              | 98,765.40              | 98,765.00              | 98,700.00                |
| Arredondamento                         | 98,765.43              | 98,765.50              | 98,766.00              | 98,800.00                |
| Vantagem própria, para um saldo de crédito | 98,765.43              | 98,765.40              | 98,765.00              | 98,700.00                |
| Vantagem própria, para um saldo de débito  | 98,765.43              | 98,765.50              | 98,766.00              | 98,800.00                |

> [!NOTE]                                                                                  
> Se você selecionar Vantagem própria, o arredondamento será sempre em benefício da entidade legal. 

Para obter mais informações, consulte os seguintes tópicos:
- [Visão geral de imposto](indirect-taxes-overview.md)
- [Criar um pagamento de imposto](tasks/create-sales-tax-payment.md)
- [Criar transações de vendas em documentos](tasks/create-sales-tax-transactions-documents.md)
- [Exibir transações de imposto lançadas](tasks/view-posted-sales-tax-transactions.md)



