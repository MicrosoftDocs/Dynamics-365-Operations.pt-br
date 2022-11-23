---
title: Liquidar um cheque pré-datado de um fornecedor
description: Estabeleça um cheque pós-datado emitido para um fornecedor quando o banco tiver compensado a transação de cheque, após o cheque ficar vencido e compensado pelo banco.
author: kweekley
ms.date: 11/15/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: VendPostDatedChecks, LedgerJournalTable, LedgerJournalTransDaily, LedgerTransVoucher
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3e3816a2f1c95d568a173cb07daad0473703da9c
ms.sourcegitcommit: cf6b764824bd1cf2c0dde6d37ddd0a7abab87ff0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/16/2022
ms.locfileid: "9779425"
---
# <a name="settle-a-postdated-check-for-a-vendor"></a>Liquidar um cheque pré-datado de um fornecedor

[!include [banner](../../includes/banner.md)]

Estabeleça um cheque pós-datado emitido para um fornecedor quando o banco tiver compensado a transação de cheque, após o cheque ficar vencido e compensado pelo banco. 

Conclua os seguintes procedimentos antes de iniciar este.

1) Configurar cheques pré-datados

2) Registrar e lançar um cheque pré-datado para um fornecedor



A função deste procedimento é Tesoureiro. Este procedimento usa a empresa de dados de demonstração USMF.

1. Vá para **Contas a pagar > Pagamentos > Cheques pós-datados do fornecedor**.
2. Clique em **Liquidar**.
3. Clique em **Liquidar entradas de compensação**.
    * Liquide a conta do fornecedor para a transação do cheque.  
4. Feche a página.
5. Acesse **Contabilidade > Entradas de diários > Diários gerais**.
6. Selecione **Todos** no campo **Mostrar**.
7. Marque ou desmarque a caixa de seleção **Mostrar apenas os que foram criados por usuário**.
8. Na lista, marque a linha selecionada.
9. Clique em **Linhas**.
10. Clique em **Comprovante**.
11. Feche a página.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
