---
title: Pagamentos de imposto e regras de arredondamento
description: Este artigo explica como a configuração de regra de arredondamento funciona em Autoridades de imposto e o arredondamento do saldo de imposto durante o trabalho Liquidar e lançar imposto.
author: ShylaThompson
manager: AnnBe
ms.date: 05/30/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxAuthority
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 6134
ms.assetid: 7dcd3cf5-ebdf-4a9f-806c-1296c7da0331
ms.search.region: Global
ms.author: yijialuan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 168c2fb9edfc994617ef6764a5b9f5949d599882
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1834989"
---
# <a name="sales-tax-payments-and-rounding-rules"></a>Pagamentos de imposto e regras de arredondamento

[!include [banner](../includes/banner.md)]

Este artigo explica como a configuração de regra de arredondamento funciona em Autoridades de imposto e o arredondamento do saldo de imposto durante o trabalho Liquidar e lançar imposto.

Periodicamente, o imposto deve ser informado e pago às autoridades fiscais. Isso pode ser feito executando o processo de pagamento de liquidação e pós-venda na página de imposto de vendas. O imposto sobre vendas de um período será liquidado contra as contas de imposto sobre vendas e o saldo do imposto sobre vendas será lançado na conta de liquidação de imposto de vendas. O saldo do imposto, que é lançado na conta de liquidação do imposto, pode ser arredondado conforme exigido pelas autoridades fiscais para configurar uma regra de arredondamento na página Impostos. 

A diferença de arredondamento é lançada na conta de arredondamento de Impostos que é selecionada no campo Contas para transações automáticas na Contabilidade.

O exemplo a seguir ilustra como funciona a regra de arredondamento na autoridade de impostos.

## <a name="examples"></a>Exemplos

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


### <a name="no-rounding-at-all-since-the-round-off-is-000"></a>Sem arredondamento, pois o arredondamento é 0,00

arredondar (1,0151, 0,00) = 1,0151 (1,0149, 0,00) = 1,0149

### <a name="normal-round-and-round-precision-is-001"></a>Arredondamento normal, e a precisão do arredondamento é de 0,01

<table>
  <tr>
    <td>Arredondamento
    </td>
    <td>Processo de cálculo
    </td>
  </tr>
    <tr>
    <td>arredondar (1,015, 0,01) = 1,02
    </td>
    <td>
      <ol>
        <li>arredondar (1,015 / 0,01, 0) = arredondar (101,5, 0) = 102
        </li>
        <li>102 * 0,01 = 1,02
        </li>
      </ol>
    </td>
  </tr>
    <tr>
    <td>arredondar (1,014, 0,01) = 1,01
    </td>
    <td> <ol>
        <li>arredondar (1,014 / 0,01, 0) = arredondar (101,4, 0) = 101
        </li>
        <li>101 * 0,01 = 1,01
        </li>
      </ol>
    </td>
  </tr>
    <tr>
    <td>arredondar (1,011, 0,02) = 1,02
    </td>
    <td> <ol>
        <li>arredondar (1,011 / 0,02, 0) = arredondar (50,55, 0) = 51
        </li>
        <li>51 * 0,02 = 1,02
        </li>
      </ol>
    </td>
  </tr>
    <tr>
    <td>arredondar (1,009, 0,02) = 1,00
    </td>
    <td> <ol>
        <li>arredondar (1,009 / 0,02, 0) = arredondar (50,45, 0) = 50
        </li>
        <li>50 * 0,02 = 1,00
        </li>
      </ol>
    </td>
  </tr>
</table>

> [!NOTE]                                                                                  
> Se você selecionar Vantagem própria, o arredondamento será sempre em benefício da entidade legal. 

Para obter mais informações, consulte os seguintes tópicos:
- [Visão geral de imposto](indirect-taxes-overview.md)
- [Criar um pagamento de imposto](tasks/create-sales-tax-payment.md)
- [Criar transações de vendas em documentos](tasks/create-sales-tax-transactions-documents.md)
- [Exibir transações de imposto lançadas](tasks/view-posted-sales-tax-transactions.md)
- [Função round](https://msdn.microsoft.com/library/aa850656.aspx)


