---
title: Pagamentos de impostos e regras de arredondamento
description: Este tópico explica como a configuração da regra de arredondamento funciona em Autoridades de imposto e o arredondamento do saldo de imposto durante o trabalho Liquidar e lançar imposto.
author: kailiang
ms.date: 10/29/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TaxAuthority
audience: Application User
ms.reviewer: kfend
ms.custom: 6134
ms.assetid: 7dcd3cf5-ebdf-4a9f-806c-1296c7da0331
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ff69afae675b9f8824ac0b29b5611420136b6a57
ms.sourcegitcommit: 631d2cea52590af15f208e9af584446e85540fcf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2022
ms.locfileid: "8726540"
---
# <a name="sales-tax-payments-and-rounding-rules"></a>Pagamentos de impostos e regras de arredondamento

[!include [banner](../includes/banner.md)]

Este tópico explica como a configuração da regra de arredondamento funciona em Autoridades de imposto e o arredondamento do saldo de imposto durante o trabalho Liquidar e lançar imposto.

Periodicamente, o imposto deve ser informado e pago às autoridades fiscais. Essa ação pode ser concluída executando o processo Liquidar e lançar imposto na página **Imposto**. O imposto de um período será liquidado em relação às contas de impostos, e o saldo de imposto será lançado na Conta de liquidação de imposto. O saldo de imposto, que é lançado na Conta de liquidação de imposto, pode ser arredondado conforme exigido pelas autoridades de imposto configurando uma regra de arredondamento na página **Imposto**. 

A diferença de arredondamento é lançada na conta de arredondamento de Impostos que é selecionada no campo Contas para transações automáticas na Contabilidade.

O exemplo a seguir ilustra como funciona a regra de arredondamento na autoridade de impostos.

## <a name="examples"></a>Exemplos

O imposto total para um período mostra um saldo de crédito de -98.765,43. A entidade legal coletou mais imposto do que pagou. Portanto, a entidade legal deve dinheiro à autoridade fiscal. 

A entidade legal quer usar um método de arredondamento que arredonda para o valor mais perto de 1,00. O usuário responsável pela contabilização do imposto conclua as etapas a seguir.

1. Clique em **Imposto** > **Impostos indiretos** > **Imposto** > **Autoridades do imposto**.
2. Na Guia Rápida **Geral**, no campo **Forma de arredondamento**, selecione **Normal**.
3. No campo **Arredondamento**, digite 1,00.
4. Na época de pagar os impostos à autoridade fiscal, acesse **Imposto** > **Declarações** > **Imposto** > **Liquidar e lançar imposto**. Na conta de liquidação do imposto, você pode verificar se o valor da obrigação fiscal de **98.765,43** foi arredondado para **98.765**.

A tabela a seguir mostra como um valor 98.765,43 é arredondado usando cada método de arredondamento que está disponível no campo **Forma de arredondamento** na página **Autoridades do imposto**.

> [!NOTE]                                                                                  
> Se o valor de arredondamento for definido como 0,00:
>
> - No arredondamentos normal, o comportamento de arredondamento é o mesmo aplicado em **Arredondamento = 0,01**.
> - Nas **Opções da forma de arredondamento**, **Para baixo**, **Arredondamento** e **Vantagem própria**, o comportamento é o mesmo que o aplicado em **Arredondamento = 1,00**.

| Opção da forma de arredondamento                | Valor de arredondamento = 0,01 | Valor de arredondamento = 0,10 | Valor de arredondamento = 1,00 | Valor de arredondamento = 100,00 | Valor de arredondamento = 0,00   |
|-------------------------------------|------------------------|------------------------|------------------------|--------------------------|--------------------------|
| Normal                              | 98,765.43              | 98,765.40              | 98,765.00              | 98,800.00                | 98,765.43                |
| Para baixo                            | 98,765.43              | 98,765.40              | 98,765.00              | 98,700.00                | 98,765.00                |
| Arredondamento                         | 98,765.43              | 98,765.50              | 98,766.00              | 98,800.00                | 98,766.00                |
| Vantagem própria, para um saldo de crédito | 98,765.43              | 98,765.40              | 98,765.00              | 98,700.00                | 98,765.00                |
| Vantagem própria, para um saldo de débito  | 98,765.43              | 98,765.50              | 98,766.00              | 98,800.00                | 98,766.00                |

### <a name="normal-round-and-round-precision-is-001"></a>Arredondamento normal, e a precisão do arredondamento é de 0,01

```<table>
  <tr>
    <td>Rounding
    </td>
    <td>Calculation process
    </td>
  </tr>
    <tr>
    <td>round(1.015, 0.01) = 1.02
    </td>
    <td>
      <ol>
        <li>round(1.015 / 0.01, 0) = round(101.5, 0) = 102
        </li>
        <li>102 * 0.01 = 1.02
        </li>
      </ol>
    </td>
  </tr>
    <tr>
    <td>round(1.014, 0.01) = 1.01
    </td>
    <td> <ol>
        <li>round(1.014 / 0.01, 0) = round(101.4, 0) = 101
        </li>
        <li>101 * 0.01 = 1.01
        </li>
      </ol>
    </td>
  </tr>
    <tr>
    <td>round(1.011, 0.02) = 1.02
    </td>
    <td> <ol>
        <li>round(1.011 / 0.02, 0) = round(50.55, 0) = 51
        </li>
        <li>51 * 0.02 = 1.02
        </li>
      </ol>
    </td>
  </tr>
    <tr>
    <td>round(1.009, 0.02) = 1.00
    </td>
    <td> <ol>
        <li>round(1.009 / 0.02, 0) = round(50.45, 0) = 50
        </li>
        <li>50 * 0.02 = 1.00
        </li>
      </ol>
    </td>
  </tr>
</table>
```

> [!NOTE]                                                                                  
> Se você selecionar Vantagem própria, o arredondamento será sempre em benefício da entidade legal. 

Para obter mais informações, consulte os seguintes tópicos:
- [Visão geral de imposto](indirect-taxes-overview.md)
- [Criar um pagamento de imposto](tasks/create-sales-tax-payment.md)
- [Criar transações de imposto em documentos](tasks/create-sales-tax-transactions-documents.md)
- [Exibir transações de imposto lançadas](tasks/view-posted-sales-tax-transactions.md)
- [Função round](/previous-versions/dynamics/ax-2012/reference/aa850656(v=ax.60))




[!INCLUDE[footer-include](../../includes/footer-banner.md)]
