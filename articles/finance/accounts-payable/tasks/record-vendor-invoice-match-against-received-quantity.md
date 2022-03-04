---
title: Registrar fatura de fornecedor e corresponder com a quantidade recebida
description: Ao receber uma fatura de um fornecedor para bens em uma ordem de compra, seus processos de negócios podem necessitar que os bens ou serviços sejam recebidos antes que a nota fiscal possa ser aprovada para pagamento.
author: ShivamPandey-msft
ms.date: 02/11/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: PurchTable, PurchCreateOrder, PurchEditLines, VendEditInvoice, VendEditInvoiceDefaultQuantityForLinesDropDialog,  VendJournalMatch_PackingSlip, VendInvoiceMatchingDetails
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8a3f1463821a43af0d8d5f15225944b080414e4c
ms.sourcegitcommit: 3105642fca2392edef574b60b4748a82cda0a386
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/12/2022
ms.locfileid: "8109909"
---
# <a name="record-vendor-invoice-and-match-against-received-quantity"></a>Registrar fatura de fornecedor e corresponder com a quantidade recebida

[!include [banner](../../includes/banner.md)]

Ao receber uma fatura de um fornecedor para bens em uma ordem de compra, seus processos de negócios podem necessitar que os bens ou serviços sejam recebidos antes que a nota fiscal possa ser aprovada para pagamento. Antes de começar, verifique se a configuração conciliação de faturas está marcada. 

Na página **Parâmetros de contas a pagar**, verifique se a opção **Habilitar validação da conciliação de faturas** está selecionada, o campo **Lançar fatura com discrepâncias** está definido como **Exigir aprovação** e o campo **Política de conciliação de linha** está definido como **Conciliação tripla**.

Este procedimento usa a empresa de dados de demonstração USMF. A função gerente de contas a pagar ou gerente de contabilidade executaria estas etapas.


## <a name="create-a-purchase-order"></a>Crie uma ordem de compra
1. Ir para Todas as ordens de compra.
2. Clique em **Novo**.
3. No campo **Conta de fornecedor**, clique no botão suspenso para abrir a pesquisa.
4. No campo **Conta de fornecedor**, insira um valor.
5. Clique em **OK**.
6. Clique em **Adicionar linha**.
7. No campo **Número de item**, digite um valor.
8. No Painel de Ação, clique em **Compra**.
9. Clique em **Confirmar**.

## <a name="post-a-product-receipt"></a>Lançar um recebimento de produto
1. No Painel de Ação, clique em **Receber**.
2. Clique em **Recebimento de produtos**.
3. Na lista, marque a linha selecionada.
4. No campo **Recebimento de produtos**, digite um valor.
5. Clique em **OK**.

## <a name="record-and-match-a-vendor-invoice-to-a-product-receipt"></a>Registre e a concilie uma fatura de fornecedor com um recebimento de produto
1. No Painel de Ação, clique em **Fatura**.
2. Clique em **Fatura**.
3. No campo **Número**, digite um valor.
4. Clique no **padrão de: Quantidade encomendada** para abrir a caixa de diálogo de descarte.
5. No campo **Quantidade padrão para linhas**, selecione uma opção.
6. Clique em **OK**.
7. Clique em **Sim**.
8. Clique em **Conciliar recebimentos de produtos**.
9. Clique em **OK**.
10. No Painel de Ação, clique em **Revisar**.
11. Clique em **Detalhes da conciliação**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
