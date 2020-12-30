---
title: Registrar e lançar um cheque pré-datado para um fornecedor
description: Você pode registrar os detalhes de um cheque pós-datado antes de emitir o cheque para um fornecedor usando o comprovante de diário.
author: kweekley
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransVendPaym
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 63a822350ce2bd4d673d7f9841822c84fb883601
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4440385"
---
# <a name="register-and-post-a-postdated-check-for-a-vendor"></a>Registrar e lançar um cheque pré-datado para um fornecedor

[!include [banner](../../includes/banner.md)]

Você pode registrar os detalhes de um cheque pós-datado antes de emitir o cheque para um fornecedor usando o comprovante de diário. Você também pode lançar o cheque pré-datado e gerar transações financeiras. Antes de registrar e lançar um cheque pré-datado de um fornecedor, conclua a seguinte tarefa: 

Configurar cheques pós-datado na página Gerenciamento de caixa e banco. 



A função desta guias de tarefas é Tesoureiro. Esta tarefa usa a empresa de demonstração USMF.

1. Vá para Contas a pagar > Pagamentos > Diário de pagamentos
2. Clique em Novo.
3. No campo Nome, digite 'VendPay'.
4. Clique em Linhas.
5. No campo Conta, especifique os valores desejados.
6. Na lista, marque a linha selecionada.
7. No campo Débito, insira um número.
8. No campo Método de pagamento, clique no botão suspenso para abrir a pesquisa.
    * Selecione o método de pagamento para o cheque pré-datado  
9. Na lista, localize e selecione o PDV desejado.
10. Na lista, clique no link na linha selecionada.
11. Clique na aba Cheques pré-datados.
12. No campo Número do cheque, digite um valor.
    * Insira ou modifique o número do cheque pós-datado.  
13. No campo Nome do banco emissor, digite um valor.
    * insira os detalhes do banco para o banco emissor.  
14. Clique na guia Listar.
15. Clique em Lançar.
16. Feche a página.
17. Clique na aba Cheques pré-datados.

