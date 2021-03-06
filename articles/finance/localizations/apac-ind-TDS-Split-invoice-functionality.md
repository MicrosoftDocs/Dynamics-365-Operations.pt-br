---
title: Funcionalidade de divisão de fatura
description: Este tópico descreve a configuração e a funcionalidade para dividir faturas por endereço de entrega e número de conta de imposto (TAN).
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
ms.openlocfilehash: 7dddbb9f69a9735c2a03d2b23928f5cb92d4e0fd
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023033"
---
# <a name="split-invoice-functionality"></a>Funcionalidade de divisão de fatura

[!include [banner](../includes/banner.md)]

Este tópico descreve a configuração e a funcionalidade para dividir faturas por endereço de entrega e número de conta de imposto (TAN).

Na página **Parâmetros de contas a pagar**, na guia **Geral** , marque a caixa de seleção **Recebimento de produtos** ou **Fatura** para lançar e dividir um recibo de produto ou fatura que tenha endereços de entrega e TANs diferentes na página **Ordem de compra**. A fatura lançada será dividida por endereço de entrega e TAN.

Na guia **Atualização resumida**, na FastTab **Divisão baseada em**, na linha **Informações de entrega**, defina a opção **Confirmação**, **Lista de separação**, **Guia de remessa** ou **Fatura** como **Sim** para lançar e dividir uma confirmação, lista de separação, guia de remessa ou fatura onde diferentes endereços de entrega e TANs são definidos para diferentes faturas linhas na página **Ordem de venda**. A fatura será dividida primeiro por endereço de entrega e depois por TAN.

> [!IMPORTANT]
> - Se nenhuma opção para **Informações de entrega** for definida como **Sim**, a fatura será lançada como uma única fatura. Nenhuma divisão de fatura ocorrerá.
> - Para dividir e lançar uma guia de remessa onde as linhas da fatura têm endereços de entrega e TANs diferentes, você deve definir a opção **Guia de remessa** de **Informações de entrega** como **Sim**.
> - Para dividir e lançar uma fatura onde as linhas da fatura têm endereços de entrega e TANs diferentes, você deve definir a opção **Fatura** de **Informações de entrega** como **Sim**.
> - Para lançar uma fatura onde as linhas da fatura têm endereços de entrega diferentes, mas o mesmo TAN, você deve definir a opção **Fatura** de **Informações de entrega** como **Não**. A fatura será dividida por endereço de entrega.

## <a name="example"></a>Exemplo

Neste exemplo, a opção **Fatura** de **Informações de entrega** é definida como **Sim** na guia **Atualização resumida** da página **Parâmetros de contas a pagar**. Uma fatura de compra é lançada com a seguinte configuração para endereços de entrega e TANs nas linhas:

- **Linha de item 1:** endereço de entrega 1, TAN-ABCD12345A
- **Linha de item 2:** endereço de entrega 1, TAN-ABCD12345A
- **Linha de item 3:** endereço de entrega 2, TAN-ABCE12345B
- **Linha de item 4:** endereço de entrega 3, TAN-ABCD12345A

Nesse caso, a fatura original é dividida em duas faturas e lançada da seguinte forma:

- A fatura 1 é lançada para a linha de item 1 e linha de item 2, porque ambas as linhas têm o mesmo endereço de entrega e TAN.
- A fatura 2 é lançada para a linha de item 3.
- A fatura 3 é lançada para a linha de item 4.
