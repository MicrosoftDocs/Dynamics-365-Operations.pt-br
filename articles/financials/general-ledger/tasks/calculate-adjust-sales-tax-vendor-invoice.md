---
title: Calcular e ajustar imposto na fatura de fornecedor
description: Este tópico explica como ajustar impostos em uma fatura de fornecedor no Dynamics 365 for Finance and Operations.
author: twheeloc
manager: AnnBe
ms.date: 07/31/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransVendInvoice, VendTableLookup, TaxTmpWorkTrans
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 684529087d5348c9e02310f812f8aa6f64c6655f
ms.sourcegitcommit: 016832198c306e8329ad21b5254e7d1cdff74c2f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2019
ms.locfileid: "1862605"
---
# <a name="calculate-and-adjust-sales-tax-on-a-vendor-invoice"></a>Calcular e ajustar imposto na fatura de fornecedor

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este tópico explica como ajustar impostos em uma fatura de fornecedor no Dynamics 365 for Finance and Operations. Se o documento de origem exibir valores de imposto diferentes como calculados, você pode ajustar os valores antes do lançamento. Esta tarefa usa a empresa de demonstração DEMF.

1. No painel de navegação, vá para **Módulos > Contas a pagar > Faturas > Diário de faturas**.
2. Selecione **Novo**.
3. No campo **Nome** da nova linha, selecione uma opção no menu suspenso.
4. No Painel de Ações, selecione **Linhas**.
5. No campo **Conta**, especifique os valores desejados.
6. No campo **Fatura**, digite um valor.
7. No campo **Crédito**, insira um número.
8. No campo **Contrapartida**, especifique os valores desejados.
9. Selecione **Imposto**.
10. No campo **Valor total do imposto real**, insira um número.
11. Na guia **Ajuste**, os valores de impostos podem ser ajustados por código de imposto.
12. Selecione **Redefinir valor real a partir de valores calculados**.
13. Selecione **OK**.
14. Selecione **Salvar**.

