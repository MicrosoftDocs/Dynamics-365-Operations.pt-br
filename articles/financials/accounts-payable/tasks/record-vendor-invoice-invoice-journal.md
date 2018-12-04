--- 
title: "Registrar uma fatura de fornecedor no diário de faturas"
description: "Este guia de tarefa mostrará como registrar as notas fiscais de fornecedor que não estão associadas às ordens de compra."
author: abruer
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: VendInvoiceWorkspace, LedgerJournalTable, LedgerJournalTransVendInvoice
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 42f93e6d8fcf62babc3e3244bc1fe76d1efd9d13
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---
# <a name="record-a-vendor-invoice-in-the-invoice-journal"></a>Registrar uma fatura de fornecedor no diário de faturas

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este guia de tarefa mostrará como registrar as notas fiscais de fornecedor que não estão associadas às ordens de compra. Exemplos deste tipo de nota fiscal incluem despesas de fornecimentos ou serviços.  Este registro usa a empresa de dados de demonstração USMF.

1. Vá para Contas a pagar > Espaços de trabalho > Entrada de fatura de fornecedor.
2. Clique em Novo diário de faturas.
3. Clique em Novo.
4. No campo Nome, insira o nome do diário ou clique no botão suspenso para abrir a pesquisa.
5. No campo Descrição, digite um valor.
6. Clique em Linhas.
    * No campo data, insira a data de lançamento que atualizará a contabilidade.  
7. No campo Conta, especifique a Conta do fornecedor.
8. No campo Fatura, insira o número da fatura.
9. No campo Descrição, digite um valor.
10. No campo Crédito, insira um número.
11. No campo Contrapartida, insira o número da conta ou clique no botão suspenso para abrir a pesquisa
    * O grupo de imposto será padrão da conta do fornecedor.  
    * O grupo de imposto será padrão da conta principal especificada no campo Contrapartida.  
    * A data de vencimento será calculada com base nos Termos de pagamento.  
    * O desconto à vista será padrão da Conta do fornecedor.  
12. Clique em Lançar.
13. Feche a página.


