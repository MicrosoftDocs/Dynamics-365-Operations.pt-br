--- 
title: Registrar o recebimento de mercadorias na ordem de compra
description: Este procedimento mostra como registrar o recebimento de mercadorias diretamente em uma ordem de compra.
author: FrankDahl
manager: AnnBe
ms.date: 08/23/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: fdahl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 9b2300a593c9e153ee598fa72e29907c82f2b79e
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---
# <a name="record-the-receipt-of-goods-on-the-purchase-order"></a>Registrar o recebimento de mercadorias na ordem de compra

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este procedimento mostra como registrar o recebimento de mercadorias diretamente em uma ordem de compra. Também é possível registrar o recebimento de produtos no depósito e, posteriormente, registrá-lo na ordem de compra. Essa tarefa é normalmente executada por um agente de compras ou um coordenador de contas a pagar. O exemplo mostrado neste guia pode ser usado na empresa dos dados do programa demonstrativo de USMF. O exemplo inclui etapas para criar uma ordem de compra simples de modo que você possa usar o procedimento como um guia da tarefa. Se você usava o procedimento em seus próprios dados, começaria na subtarefa Registrar recebimento de mercadorias.


## <a name="prepare-a-new-purchase-order-for-receipt-of-goods"></a>Registrar o recebimento de mercadorias para uma linha da ordem de compra
1. Vá para Aquisição e fornecimento > Ordens de compra > Todas as ordens de compra.
2. Clique em Novo.
3. No campo Conta de fornecedor, digite US-101.
4. Clique em OK.
5. No campo Número do item, insira M0001.
6. No campo Quantidade, insira 5.
7. No Painel de Ação, clique em Compra.
8. Clique em Confirmar.

## <a name="record-receipt-of-goods"></a>Registrar recebimento de mercadorias
1. No Painel de Ação, clique em Receber.
2. Clique em Recebimento de produtos.
    * O campo Quantidade permite que você selecione opções diferentes para a quantidade que você quer receber. Por exemplo, se uma quantidade foi registrada previamente no armazém, você pode selecionar a quantidade registrada.  Para este exemplo, use o valor de Quantidade solicitada.   
3. No campo Recebimento de produtos, digite qualquer valor.
    * Este campo é usado para inserir uma referência que seja usada como comprovante do diário de recebimentos de produtos.  
4. Expandir a seção Linhas.
5. Defina a quantidade como '4'.
    * Aqui você pode especificar manualmente a quantidade que está sendo recebida para cada linha na ordem.  
6. Recolha a seção Linhas.
7. Clique em OK.
    * As mercadorias foram agora registradas como recebidas na ordem de compra, e um diário de recebimentos de produtos foi criado como documento para refletir isto. Você pode usar a ação de Recebimento de produtos para revisar os diários criados com a ordem de compra e ver o que foi recebido, e quando.  


