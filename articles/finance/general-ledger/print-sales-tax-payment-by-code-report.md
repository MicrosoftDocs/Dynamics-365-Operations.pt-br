---
title: Imprimir o relatório Pagamento de imposto sobre vendas por código
description: Este artigo fornece informações sobre as configurações e as ações necessárias para imprimir o relatório Pagamento de imposto por código na contabilidade ou na moeda do código do imposto.
author: anasyash
ms.date: 05/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: anasyash
ms.search.validFrom: 2020-04-08
ms.dyn365.ops.version: 10.0.11
ms.openlocfilehash: 9c6b51da41f2aaa3206f8ad97a364a9cd5ca6d49
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8856644"
---
# <a name="print-the-sales-tax-payment-by-code-report"></a>Imprimir o relatório Pagamento de imposto sobre vendas por código 

[!include [banner](../includes/banner.md)]

Para imprimir o **Pagamento de imposto sobre vendas por código**, Acesse **Imposto** \> **Consultas e relatórios** \> **Relatórios de imposto sobre vendas** \> **Pagamento de imposto sobre vendas por código**. Por padrão, os valores do relatório são gerados na moeda contábil da entidade legal para todos os códigos do relatório definidos na página **Códigos de relatório de imposto sobre vendas**.

Também é possível gerar esse relatório para mostrar os valores do pagamento de imposto sobre vendas nas moedas dos códigos de imposto sobre venda de todos os códigos de relatório atribuídos aos códigos de impostos sobre vendas na página **Códigos de imposto sobre vendas**.

## <a name="turn-on-the-feature"></a>Ativar o recurso

No espaço de trabalho **Gerenciamento de recursos**, ative o seguinte recurso: **Gerar relatório de pagamento de imposto sobre vendas por código na moeda do código de imposto**.

## <a name="run-the-report"></a>Executar o relatório

1. Acesse **Imposto** \> **Consultas e relatórios** \> **Relatórios de imposto** \> **Pagamento de imposto sobre vendas por código**.
2. No campo **Moeda do relatório**, selecione um dos seguintes valores:

    - **Moeda contábil** – Imprima os valores do relatório na moeda contábil.
    - **Moeda do código de imposto** – Imprima os valores do relatório nas moedas dos códigos de imposto.

    ![Caixa de diálogo Pagamento de imposto sobre vendas por código.](media/Sales-tax-payment-by-code.png)

A ilustração a seguir mostra um exemplo do relatório que é gerado. O relatório mostra que o código de relatório **101** tem a moeda **EUR** se o campo **Moeda do imposto** estiver definido como **EUR** para o código do imposto ao qual o código de relatório está atribuído.

![Exemplo do relatório Pagamento de imposto sobre vendas por código.](media/Sales-tax-payment-by-code-2.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]