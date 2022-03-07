---
title: Cálculo de TDS em faturas
description: Este tópico fornece uma referência para transações em que o Imposto Deduzido na Origem (TDS) é calculado no nível da fatura.
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 496e87e3028025f738d2f0a697d91c18b77ad1c9
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023032"
---
# <a name="tds-calculation-on-invoices"></a>Cálculo de TDS em faturas

[!include [banner](../includes/banner.md)]

Este tópico fornece uma referência para transações em que o Imposto Deduzido na Origem (TDS) é calculado no nível da fatura.

| Nº de série | Tipo de transação                                 | Valor da transação | Nome da página e caminho de seleção                                 | Tipo de conta e tipo de contrapartida                         |
| ------------- | ------------------------------------------------ | ------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| 1.            | Compra feita no fornecedor/registro de despesas   | Débito ou crédito  | Página de diários gerais (Contabilidade > Entradas de diário> Diários gerais), página de diário de aprovação de fatura (Contas a pagar > Faturas> Aprovação de fatura), página de diário de fatura (Contas a pagar> Faturas > Diário de fatura) | Razão (Dr.)  fornecedor (Cr.).  O imposto retido na fonte é calculado para a combinação Fornecedor-Razão apenas quando a conta contábil tem o tipo de lançamento **Compra**  **pagamento à vista**. |
| 2.            | Compra feita no cliente/registro de despesas | Débito ou crédito  | Página de diário geral (Contabilidade > Entradas de diário> Diário geral), página de diário de fatura (Contas a pagar > Faturas > Diário de fatura) | Razão (Dr.)  cliente (Cr.)                                 |
| 3.            | Compra de ativo fixo do vendedor              | Débito ou crédito  | Página de diários gerais (Contabilidade > Entradas de diário> Diários gerais), página de diário de registro de fatura (Contas a pagar > Faturas> Registro de fatura), página de diário de fatura (Contas a pagar> Faturas > Diário de fatura) | Ativos fixos (Dr.)  fornecedor (Cr.)                             |
| 4.            | Compra de ativo fixo do cliente            | Débito ou crédito  | Página de diário geral (Contabilidade > Entradas de diário> Diário geral), página de diário de fatura (Contas a pagar > Faturas > Diário de fatura) | Ativos fixos (Dr.)  cliente (Cr.)                           |
| 5.            | Fatura de compra (TDS a pagar)                  |                    | Página de ordem de compra (Contas a pagar > Ordens de compra > Todas as ordens de compra) |                                                              |
| 6.            | Fatura de vendas (TDS a receber)                  |                    | Página de ordem de venda (Contas a receber > Ordens > Todas as ordens de venda), página de fatura de texto livre (Contas a receber > Faturas > Todas as faturas de texto livre) |                                                              |
