---
title: Cálculo do TDS em transações entre empresas
description: Este tópico descreve o processo usado para calcular o Imposto Deduzido na Origem (TDS) em transações entre empresas em fases.
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: c978c84891a0c1ce5a079484eec24590283027c4
ms.sourcegitcommit: 6dc2b877cf8ea9185a07964ec05c5ddb7a78471b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/12/2022
ms.locfileid: "8407913"
---
# <a name="tds-calculation-on-intercompany-transactions"></a>Cálculo do TDS em transações entre empresas

[!include [banner](../includes/banner.md)]

Este tópico descreve o processo usado para calcular o Imposto Deduzido na Origem (TDS) em transações entre empresas em fases.

Quando uma ordem de compra ou venda entre empresas é criada, o grupo de TDS padrão definido para o cliente ou fornecedor é usado para calcular o valor do TDS. O valor do TDS é lançado nas contas a recuperar ou a pagar após o lançamento da fatura.

Uma ordem de venda ou compra entre empresas é criada automaticamente para a ordem de compra ou venda original. O grupo de TDS padrão é mostrado na ordem entre empresas para que o TDS possa ser calculado. Você pode alterar o grupo de TDS. A fatura pode ser lançada apenas se o valor líquido da fatura no pedido entre companhias criado automaticamente corresponder ao valor líquido da fatura na ordem original. (O valor líquido é o valor da fatura após a dedução do TDS.)

Por exemplo, uma fatura de venda é criada para 50.000 e o grupo de TDS de **10%** é anexado a ela. O valor da fatura lançada é 45.000 e o valor do TDS lançado para a nota fiscal de venda é 5.000. Uma ordem de compra é criada automaticamente para a ordem de venda entre empresas e o grupo de TDS de **10%** é anexado a ela. Se você alterar o grupo de TDS para **15%**, não poderá lançar a fatura, porque o valor líquido da fatura da ordem de venda entre empresas que foi criado automaticamente não corresponde ao valor líquido da fatura da ordem de venda original.

Um diário de pagamento criado para uma fatura entre empresas é lançado automaticamente. Esse diário de pagamentos pode ser lançado apenas se o valor do pagamento líquido nele corresponder ao valor do pagamento líquido no diário de pagamentos original.
