---
title: Auditar faturas e dados-chave no sistema de AP
description: Ao receber uma fatura de um fornecedor para bens em uma ordem de compra, seus processos de negócios podem necessitar que os bens ou serviços sejam recebidos antes que a nota fiscal possa ser aprovada para pagamento.
author: saraschi2
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, PurchCreateOrder, PurchEditLines, VendEditInvoice, VendEditInvoiceDefaultQuantityForLinesDropDialog,  VendJournalMatch_PackingSlip, VendInvoiceMatchingDetails
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c6e8967fe4db67ff98fc7093792bdb82b73a33d9
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2176359"
---
# <a name="audit-invoices-and-key-data-in-ap-system"></a>Auditar faturas e dados-chave no sistema de AP

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ao receber uma fatura de um fornecedor para bens em uma ordem de compra, seus processos de negócios podem necessitar que os bens ou serviços sejam recebidos antes que a nota fiscal possa ser aprovada para pagamento. Antes de começar, verifique se a configuração conciliação de faturas está marcada. 

Na página de parâmetros de contas a pagar, verifique se a opção de validação de conciliação de nota fiscal está selecionada, o campo Lançar nota fiscal com discrepâncias é configurado para exigir aprovação, e o campo da diretiva de conciliação de linha está definido à conciliação tripla.

Este procedimento usa a empresa de dados de demonstração USMF. A função gerente de contas a pagar ou gerente de contabilidade executaria estas etapas.


## <a name="create-a-purchase-order"></a>Crie uma ordem de compra
1. Ir para **Todas as ordens de compra**.
2. Clique em **Novo**.
3. No campo **Conta de fornecedor**, insira um valor.
4. Clique em **OK**.
5. Clique em **Adicionar linha**.
6. No campo **Número de item**, digite um valor.
7. No Painel de Ação, clique em **Compra**.
8. Clique em **Confirmar**.

## <a name="post-a-product-receipt"></a>Lançar um recebimento de produto
1. No Painel de Ação, clique em **Receber**.
2. Clique em **Recebimento de produtos**.
3. No campo **Recebimento de produtos**, digite um valor.
4. Clique em **OK**.

## <a name="record-and-match-a-vendor-invoice-to-a-product-receipt"></a>Registre e a concilie uma fatura de fornecedor com um recebimento de produto
1. No Painel de Ação, clique em **Fatura > Fatura**.
2. No campo **Número**, digite um valor.
3. Clique no **padrão de: Quantidade encomendada** para abrir a caixa de diálogo de descarte.
4. No campo **Quantidade padrão para linhas**, selecione uma opção.
5. Clique em **OK**.
6. Clique em **Sim**.
7. Clique em **Conciliar recebimentos de produtos**.
8. Clique em **OK**.
9. No Painel de Ação, clique em **Revisar**.
10. Clique em **Detalhes da conciliação**.

