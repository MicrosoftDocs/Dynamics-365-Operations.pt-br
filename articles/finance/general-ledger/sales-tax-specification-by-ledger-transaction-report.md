---
title: Especificação de impostos pelo relatório de transações do razão
description: Este artigo explica como usar o relatório Especificação de imposto por transação do razão para exibir e imprimir informações sobre transações do razão para as quais o imposto é calculado.
author: EricWang
ms.date: 08/19/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: kfend
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2019-08-19
ms.dyn365.ops.version: 10.0.6
ms.openlocfilehash: c96f457a0ea24aef1769f370c3c0657ada31eebf
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8898081"
---
# <a name="sales-tax-specification-by-ledger-transaction-report"></a>Especificação de impostos pelo relatório de transações do razão
[!include [banner](../includes/banner.md)]

Este artigo explica como usar o relatório **Especificação de imposto por transação do razão** para exibir e imprimir informações sobre transações do razão para as quais o imposto é calculado.

## <a name="tax-accounts-vs-non-tax-accounts"></a>Contas fiscais vs. não fiscais

O relatório **Especificação de imposto por transação do razão** mostra transações de imposto para contas fiscais e não fiscais. Essas contas são categorizadas da seguinte maneira:

- **Conta fiscal** – Uma conta é considerada fiscal quando uma transação de imposto é lançada, e a conta principal na linha de diário **Imposto** é uma conta fiscal, como uma conta de imposto a pagar ou uma conta de imposto a receber.
- **Conta não fiscal** – Uma conta é considerada não fiscal quando uma transação de imposto é lançada, e a conta principal na transação original é uma conta não fiscal, como uma conta de receita ou uma conta de despesa.

Para contas fiscais, as colunas **Origem**, **Imposto a receber** e **Imposto a pagar** no relatório mostram **0** (zero). Para contas não fiscais, essas colunas mostram valores.

## <a name="filtering-the-data-on-the-report"></a>Filtrando os dados no relatório

Quando você gera o relatório, os seguintes campos padrão são disponibilizados. Você pode usar esses campos para filtrar os dados que são mostrados no relatório.

| Campo                      | Descrição |
|----------------------------|-------------|
| Data                        | Use os campos nas seções **De** e **Para** a fim de definir um intervalo de datas para as transações de imposto. |
| Conta principal               | Use os campos nas seções **De** e **Para** a fim de definir um intervalo de contas principais. |
| Código do imposto             | Use os campos nas seções **De** e **Para** a fim de definir um intervalo de códigos de imposto. |
| Agrupamento                   | Selecione se o relatório deverá ser agrupado pela conta contábil ou pelo código de imposto. |
| Subtotal por código de imposto sobre vendas | Defina essa opção como **Sim** para mostrar subtotais por código de imposto. |
| Apenas totais                | Defina essa opção como **Sim** para mostrar apenas totais. |
| Somente contas principais         | Defina essa opção como **Sim** para incluir apenas contas principais no relatório. |

## <a name="showing-only-non-tax-accounts-on-the-report"></a>Mostrando apenas contas não fiscais no relatório

Para mostrar apenas contas não fiscais no relatório, configure uma condição de filtro, como um asterisco (\*), conforme mostrado na ilustração a seguir.

![Relatório mostrando contas não fiscais.](media/taxspecperledgertrans.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
