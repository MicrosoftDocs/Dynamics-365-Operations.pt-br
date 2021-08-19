---
title: Reconciliar frete manualmente
description: Este procedimento mostra como reconciliar manualmente o frete.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: WHSLoadPlanningWorkbench, TMSFreightBillDetail, TMSInvoiceTable, TMSFreightBillInvoiceReconcile, TMSInvoiceJournal, LedgerJournalTable, LedgerJournalTransDaily, TMSFBDetailReconcile
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ded0f19c8acb4cbd89978f2ae7ce296f54f03155c2eed7ad4b25d486c20cfeb9
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6740590"
---
# <a name="reconcile-freight-manually"></a>Reconciliar frete manualmente

[!include [banner](../../includes/banner.md)]]

Este procedimento mostra como reconciliar manualmente o frete. Normalmente isso é feito por um coordenador de transporte. Você pode usar este procedimento na empresa USMF de dados de demonstração.


## <a name="select-a-load-to-reconcile"></a>Selecione uma carga para reconciliar
1. Acesse Gerenciamento de transporte > Planejamento > Bancada de planejamento de carga.
2. Desmarque a caixa de seleção Esconder envio e recebido. 
3. Na lista, selecione custo indireto que tem a identificação ID 00006 de carga.

## <a name="create-a-carrier-invoice"></a>Criar uma fatura da transportadora
Quando você reconciliar o frete manualmente e não receber notas fiscais da transportadora automaticamente, você pode criar uma nota fiscal com base na conta de frete.  
1. Clique em Informações Relacionadas.
2. Clique em Detalhes da nota de frete.
3. Clique em gerar fatura da nota de frete.
4. No campo Fatura, digite um valor.
5. Clique em OK.

## <a name="reconcile-the-invoice"></a>Reconciliar a fatura
Quando você reconciliar uma nota fiscal da transportadora e uma conta de frete, isso é feito linha por linha.  
1. Clique em Fazer correspondência de faturas e notas de frete.
2. Expanda a seção Detalhes de fatura.
3. Expanda a seção não correspondida de detalhes da conta de frete.
4. Na lista, marque a linha selecionada.
5. Clique em Corresponder.
6. Expanda a seção correspondida de detalhes da conta de frete.

## <a name="submit-the-invoice-for-approval"></a>Enviar a fatura para aprovação
1. Clique em Enviar para aprovação.
2. Feche a página.
3. Desmarque a caixa de seleção Ocultar aprovado. 
4. Clique em Diários de fatura de fornecedor.
5. Clique para seguir o link no campo Número de referência do diário.
6. Clique em Linhas.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]