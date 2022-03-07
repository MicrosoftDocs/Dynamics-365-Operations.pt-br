---
title: Liquidar um cheque pré-datado de um fornecedor
description: Estabeleça um cheque pós-datado emitido para um fornecedor quando o banco tiver compensado a transação de cheque, após o cheque ficar vencido e compensado pelo banco.
author: kweekley
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: VendPostDatedChecks, LedgerJournalTable, LedgerJournalTransDaily, LedgerTransVoucher
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6b7755c3c3d092692dde6582a8d4ba74f00b10a95ba82a2782e3dad34d28e7b9
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6728046"
---
# <a name="settle-a-postdated-check-for-a-vendor"></a>Liquidar um cheque pré-datado de um fornecedor

[!include [banner](../../includes/banner.md)]

Estabeleça um cheque pós-datado emitido para um fornecedor quando o banco tiver compensado a transação de cheque, após o cheque ficar vencido e compensado pelo banco. 

Conclua os seguintes procedimentos antes de iniciar este.

1) Configurar cheques pré-datados

2) Registrar e lançar um cheque pré-datado para um fornecedor



A função deste procedimento é Tesoureiro. Este procedimento usa a empresa de dados de demonstração USMF.

1. Acesse Contas a pagar > Pagamentos > Cheques pós-datados do fornecedor.
2. Clique em Liquidar.
3. Clique em Liquidar entradas de compensação.
    * Liquide a conta do fornecedor para a transação do cheque.  
4. Feche a página.
5. Ir para Contabilidade > Entradas de diários > Diários gerais.
6. No campo Mostrar, selecione 'Todos.
7. Marque ou desmarque a caixa de seleção Mostrar apenas os que foram criados por usuário.
8. Na lista, marque a linha selecionada.
9. Clique em Linhas.
10. Clique em Comprovante.
11. Feche a página.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]