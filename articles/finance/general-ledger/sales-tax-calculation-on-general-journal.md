---
title: Cálculo de imposto nas linhas do diário geral
description: Este tópico explica como os impostos são calculados para diferentes tipos de conta (fornecedor, cliente, razão e projeto) nas linhas do diário geral.
author: EricWang
manager: Ann Beebe
ms.date: 08/14/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2019-08-14
ms.dyn365.ops.version: 10.0.6
ms.openlocfilehash: 25eb8dd6965f659f0febe53a6340cb1381c5664f
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5204897"
---
# <a name="sales-tax-calculation-on-general-journal-lines"></a>Cálculo de imposto nas linhas do diário geral
[!include [banner](../includes/banner.md)]

Este tópico explica como os impostos são calculados para diferentes tipos de conta (fornecedor, cliente, razão e projeto) nas linhas do diário geral.

O processo pode ser dividido em três etapas:

- Determinar a direção do imposto.

- Determinar o valor do imposto que será armazenado em uma tabela de impostos temporária.

- Determinar o valor do imposto e a conta no comprovante.

## <a name="determine-the-sales-tax-direction"></a>Determinar a direção do imposto

A maneira como a direção do imposto é determinada depende do tipo de conta no comprovante. A direção do imposto é determinada pela combinação de tipo de conta e de código de imposto. As seguintes seções listam as possibilidades mais detalhadamente. 

### <a name="account-type-is-project"></a>Tipo de conta é Projeto

Se um comprovante tiver uma linha de diário, onde o tipo de conta for **Projeto**, todas as linhas do diário no comprovante aplicarão a mesma direção de imposto. A ilustração a seguir mostra a regra. Os seguintes pontos mostram as possíveis direções de imposto para contas do projeto.

•   Se o código do imposto for imposto sobre uso, a direção do imposto será Imposto sobre o Uso.

•   Se o código do imposto for isenção de imposto, a direção do imposto será Compra Isenta de Imposto.

•   Se o código do imposto for IVA intracom, a direção do imposto será Imposto a Pagar.

•   Se o código do imposto for encargo revertido, a direção do imposto será Imposto a Pagar.

Caso contrário, a direção do imposto será Imposto a Receber.

O diagrama a seguir ilustra a regra graficamente.

![Possibilidades de direção do imposto para contas do projeto](media/Sales-Tax-Direction-Vendor.jpg)

### <a name="account-type-is-vendor"></a>Tipo de conta é Fornecedor

Se um comprovante tiver uma linha de diário, onde o tipo de conta for **Fornecedor**, todas as linhas do diário no comprovante aplicarão a mesma direção de imposto. Os seguintes pontos mostram as possíveis direções de imposto para contas de fornecedor. 

•   Se o código do imposto for imposto sobre uso, a direção do imposto será Imposto sobre o Uso.

•   Se o código do imposto for isenção de imposto, a direção do imposto será Compra Isenta de Imposto.

•   Se o código do imposto for IVA intracom, a direção do imposto será Imposto a Pagar.

•   Se o código do imposto for encargo revertido, a direção do imposto será Imposto a Pagar.

Caso contrário, a direção do imposto será Imposto a Receber.

O diagrama a seguir ilustra a regra graficamente.

![Possibilidades de direção do imposto para contas de fornecedor](media/Sales-Tax-Direction-Vendor.jpg)

### <a name="account-type-is-customer"></a>Tipo de conta é Cliente

Se um comprovante tiver uma linha de diário, onde o tipo de conta for **Cliente**, todas as linhas do diário no comprovante aplicarão a mesma direção de imposto. Os seguintes pontos mostram as possíveis direções de imposto para contas de cliente.

•   Se o código do imposto for isenção de imposto, a direção do imposto será Compra Isenta de Imposto.

•   Se o código do imposto for IVA intracom, a direção do imposto será Imposto a Receber.

•   Se o código do imposto for encargo revertido, a direção do imposto será Imposto a Receber.

Caso contrário, a direção do imposto será Imposto a Pagar.

O diagrama a seguir ilustra a regra graficamente.

![Possibilidades de direção do imposto para contas de cliente](media/Sales-Tax-Direction-Customer.jpg)

### <a name="account-type-is-ledger"></a>Tipo de conta é Razão

A ilustração a seguir mostra a regra que se aplica quando um comprovante tem apenas linhas de diário onde o tipo de conta é **Razão**. Os seguintes pontos mostram as possíveis direções de imposto para contas de razão.

•   Se o código do imposto for imposto sobre uso, a direção do imposto será Imposto sobre o Uso.

•   Se o código do imposto for isenção de imposto, a direção do imposto será Compra Isenta de Imposto.

Caso contrário, se o valor do diário for débito (positivo), a direção do imposto será Imposto a Receber; se o valor do diário for crédito (negativo), a direção do imposto será Imposto a Pagar.

O diagrama a seguir ilustra a regra graficamente.

![Possibilidades de direção do imposto para contas de razão](media/Sales-Tax-Direction-Ledger.jpg)

#### <a name="override-the-sales-tax-direction"></a>Substituir a direção do imposto

Você poderá substituir a direção do imposto quando o comprovante contiver apenas linhas onde o tipo de conta for **Razão**.

Vá para **Contabilidade \> Plano de contas \> Contas \> Contas principais** e selecione a guia rápida **Substituições da entidade legal**.

## <a name="determine-the-sales-tax-amount"></a>Determinar o valor do imposto

Esta seção descreve como o valor do sinal do imposto é calculado.

![Página Transações de imposto](media/sales-tax-amount-sign.jpg)

A tabela a seguir mostra a regra genérica para determinar o sinal de valores do imposto na tabela temporária de impostos.

| Valor da linha do diário | Direção de imposto  | Sinal do valor do imposto |
|---------------------|----------------------|-----------------------|
| Positivo            | Imposto a Receber | Positivo              |
| Positivo            | Imposto a Pagar    | Negativo              |
| Negativo            | Imposto a Receber | Negativo              |
| Negativo            | Imposto a Pagar    | Positivo              |

Há uma regra especial para os comprovantes que têm apenas as linhas **Projeto** ou **Razão**, quando um grupo de impostos de item é selecionado na linha **Razão**. A regra é controlada pelo recurso Habilitar cálculo de imposto independente para diários gerais. Quando esse recurso está desativado, o valor do imposto da linha **Razão** usa a direção de débito/crédito da linha **Projeto**. Quando o recurso está ativado, o valor do imposto da linha **Razão** usa sua própria direção de débito/crédito. As tabelas a seguir mostram a regra para cada cenário. 

**Regra quando o recurso estiver ativado**

| Valor da linha do diário do projeto | Direção de imposto  | Sinal do valor do imposto |
|--------------------------------|----------------------|-----------------------|
| Positivo                       | Imposto a Receber | Positivo              |
| Negativo                       | Imposto a Receber | Negativo              |

**Regra quando o recurso estiver desativado**

| Valor da linha do diário do razão  | Direção de imposto  | Sinal do valor do imposto |
|--------------------------------|----------------------|-----------------------|
| Positivo                       | Imposto a Receber | Positivo              |
| Negativo                       | Imposto a Receber | Negativo              |

## <a name="determine-the-sales-tax-amount-and-account-on-the-voucher"></a>Determinar o valor do imposto e a conta no comprovante

Ao lançar impostos, a conta principal é recuperada do perfil do grupo de lançamento do razão. Quando há impostos a receber, o sistema usa a conta Imposto a Receber que está especificada no perfil. Quando há impostos a pagar, o sistema usa a conta Imposto a Pagar que está especificada no perfil.

A tabela a seguir mostra a regra genérica.

| Direção de imposto  | Sinal do valor do imposto | Conta de imposto      | Valor no comprovante |
|----------------------|-----------------------|------------------------|-------------------|
| Imposto a Receber | Positivo              | Contas de Imposto a Receber | Positivo (Débito)  |
| Imposto a Receber | Negativo              | Contas de Imposto a Receber | Negativo (Crédito)  |
| Imposto a Pagar    | Positivo              | Conta de Imposto a Pagar    | Negativo (Crédito)  |
| Imposto a Pagar    | Negativo              | Conta de Imposto a Pagar    | Positivo (Débito)  |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]