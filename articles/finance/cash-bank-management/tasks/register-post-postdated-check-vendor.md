---
title: Registrar e lançar um cheque pré-datado para um fornecedor
description: Você pode registrar os detalhes de um cheque pós-datado antes de emitir o cheque para um fornecedor usando o comprovante de diário.
author: kweekley
ms.date: 11/15/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransVendPaym
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 312f7c58352e3cb86c22f8c34b1b6c11456c0083
ms.sourcegitcommit: cf6b764824bd1cf2c0dde6d37ddd0a7abab87ff0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/16/2022
ms.locfileid: "9779413"
---
# <a name="register-and-post-a-postdated-check-for-a-vendor"></a>Registrar e lançar um cheque pré-datado para um fornecedor

[!include [banner](../../includes/banner.md)]

Você pode registrar os detalhes de um cheque pós-datado antes de emitir o cheque para um fornecedor usando o comprovante de diário. Você também pode lançar o cheque pré-datado e gerar transações financeiras. Antes de registrar e lançar um cheque pré-datado de um fornecedor, conclua a seguinte tarefa: 

Configurar cheques pós-datado na página **Gerenciamento de caixa e banco**. 

A função desta guias de tarefas é Tesoureiro. Esta tarefa usa a empresa de demonstração USMF.

1. Vá para **Contas a pagar > Pagamentos > Diário de pagamentos**.
2. Clique em **Novo**.
3. No campo **Nome**, digite "VendPay".
4. Clique em **Linhas**.
5. No campo **Conta**, especifique os valores desejados.
6. Na lista, marque a linha selecionada.
7. No campo **Débito**, insira um número.
8. No campo **Método de pagamento**, clique no botão suspenso para abrir a pesquisa.
    * Selecione o método de pagamento para o cheque pré-datado  
9. Na lista, localize e selecione o PDV desejado.
10. Na lista, clique no link na linha selecionada.
11. Clique na guia **Cheques pré-datados**.
12. Insira um valor no campo **Número do cheque**.
    * Insira ou modifique o número do cheque pós-datado.  
13. No campo **Nome do banco emissor**, digite um valor.
    * Digite os detalhes do banco para o banco emissor.  
14. Clique na guia **Listar**.
15. Clique em **Enviar**.
16. Feche a página.
17. Clique na aba Cheques pré-datados.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
