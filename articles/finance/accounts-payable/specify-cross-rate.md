---
title: Especificar a taxa cruzada
description: Este tópico fornece informações sobre taxas cruzadas no Microsoft Dynamics 365 Finance.
author: abruer
manager: AnnBe
ms.date: 05/16/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 146794557a3a6ba1801598fe6b814e209d9f5fc6
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4440194"
---
# <a name="specify-the-cross-rate"></a>Especificar a taxa cruzada

[!include [banner](../includes/banner.md)]

Este tópico explica a finalidade de uma taxa cruzada, e como especificar a taxa cruzada ao liquidar um pagamento com uma fatura. Use uma taxa cruzada quando todos os critérios a seguir se aplicarem: 
-   Você está liquidando um pagamento com uma fatura. 
-   A linha de pagamento e a linha da fatura usam moedas diferentes. 
-   Nenhuma das duas é a moeda contábil. 

A taxa cruzada não é usada para calcular a conversão da moeda de transação de pagamento na moeda contábil de pagamento. Em vez disso, as taxas de câmbio das tabelas de taxa de câmbio são recuperadas para calcular o valor monetário da transação de pagamento e o valor monetário contábil de pagamento. 

Por exemplo, a moeda contábil é USD, a moeda da fatura é CAD e a moeda do pagamento é EUR. A taxa cruzada permite que você insira uma taxa de câmbio para traduzir diretamente entre CAD e EUR, e não seja preciso traduzir USD. Ao selecionar uma nota fiscal e um pagamento principal, você poderá inserir uma taxa cruzada para a linha da nota fiscal. A taxa cruzada é a taxa de câmbio entre as moedas para as transações, a partir da data de liquidação.

1.  Vá para uma das seguintes páginas:
- **Contas a receber > Comum > Clientes > Todos os clientes** 
- **Contas a pagar > Comum > Fornecedores > Todos os fornecedores** 
- **Compras > Comum > Fornecedores > Todos os fornecedores**
2.  Selecione o cliente ou o fornecedor cujas transações abertas você está liquidando. 
3.  Para um cliente, na página de listagem **Todos os clientes**, vá para **Coletar > Liquidar transações abertas**. Para um fornecedor, na página de listagem **Todos os fornecedores**, vá para **Fatura > Liquidar transações abertas**. 
4.  Selecione a transação que é o pagamento principal e clique em **Marcar pagamento**. A caixa de seleção na coluna **Marcar** será marcada e um ícone de informações aparecerá na coluna **Pagamento principal**. 
5.  No campo **Taxa cruzada**, insira a taxa de câmbio entre a moeda da fatura e a moeda do pagamento, a partir da data de liquidação. 
