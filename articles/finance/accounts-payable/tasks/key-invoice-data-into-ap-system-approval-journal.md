---
title: Dados-chave de fatura em contas a pagar usando um diário de aprovações
description: Este tópico explica como usar o registro de fatura para criar faturas e usar no diário de aprovações para atualizar as contas de despesas.
author: abruer
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransInvoiceRegister, HcmWorkerLookUp, LedgerJournalTransApprove, LedgerJournalTransApproveFetchVouchers, LedgerTransVoucher
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d01c04fcf707109cd7bc6f056846506914e96dec
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5838876"
---
# <a name="key-invoice-data-into-accounts-payable-using-an-approval-journal"></a>Dados-chave de fatura em contas a pagar usando um diário de aprovações

[!include [banner](../../includes/banner.md)]

Este tópico explica como usar o registro de fatura para criar faturas e usar no diário de aprovações para atualizar as contas de despesas.

## <a name="create-and-post-and-invoice"></a>Criar e lançar e faturar
1. No painel de navegação, vá para **Módulos > Contas a pagar > Faturas > Registro de faturas**.
2. Selecione **Novo**.
3. Selecione o nome do registro de fatura que você deseja usar.
4. Selecione **Linhas** para abrir o registro e inserir as linhas de despesa.
5. Selecione um fornecedor. Por exemplo, digite ou selecione `US-104`.
6. No campo **Fatura**, digite um valor.
7. No campo **Descrição**, digite um valor.
8. No campo **Crédito**, insira um número.
9. No campo **Aprovado por**, selecione um aprovador do menu suspenso.
10. Selecione **Lançar**.

## <a name="approve-an-invoice"></a>Aprovar uma fatura
1. No painel de navegação, vá para **Módulos > Contas a pagar > Faturas > Aprovação da fatura**.
2. Selecione **Novo**.
3. Selecione o nome do diário de aprovação de fatura que você deseja usar.
4. Selecione **Linhas** para exibir a página na qual você poderá selecionar as faturas que deseja aprovar.
5. Selecione **Localizar comprovantes** para exibir todas as faturas que estão prontas para aprovação.
6. Marque a fatura que criou, depois clique em **Selecionar**. Os comprovantes que tiver selecionado acima são movidos para esta lista depois que você os seleciona.  
7. Selecione **OK**.
8. Selecione o campo **número da conta** para adicionar uma conta de despesa à fatura.
9. Insira um número de conta e desmarque o campo. Por exemplo, insira `600120`.
10. Selecione **Lançar**.
11. Selecione **Comprovante** para exibir as entradas lançadas. A nota fiscal durante a conta de aprovação é revertida e substituída pela conta de despesa real.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]