---
title: Registrar o recebimento de mercadorias na ordem de compra
description: Este tópico explica como registrar o recebimento de mercadorias diretamente em uma ordem de compra.
author: kamaybac
ms.date: 07/09/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart, PurchCreateOrder, InventItemIdLookupPurchase, PurchEditLines
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: dabourq
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a030de902915d25d1b309e53a2af5d8b7ec32125
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5811957"
---
# <a name="record-the-receipt-of-goods-on-the-purchase-order"></a>Registrar o recebimento de mercadorias na ordem de compra

[!include [banner](../../includes/banner.md)]

Este tópico explica como registrar o recebimento de mercadorias diretamente em uma ordem de compra. Também é possível registrar o recebimento de produtos no depósito e, posteriormente, registrá-lo na ordem de compra. Essa tarefa é normalmente executada por um agente de compras ou um coordenador de contas a pagar. O exemplo mostrado neste guia pode ser usado na empresa dos dados do programa demonstrativo de USMF. O exemplo inclui etapas para criar uma ordem de compra simples de modo que você possa usar o procedimento como um guia da tarefa. Se você usava o procedimento em seus próprios dados, começaria na subtarefa **Registrar recebimento de mercadorias**.


## <a name="prepare-a-new-purchase-order-for-receipt-of-goods"></a>Registrar o recebimento de mercadorias para uma linha da ordem de compra
1. Vá para **Painel de navegação > Módulos > Compras e fornecimento > Ordens de compra > Todas as ordens de compra**.
2. Selecione **Novo**.
3. No campo **Conta de fornecedor**, insira `US-101`.
4. Selecione **OK**.
5. No campo **Número do item**, insira `M0001`.
6. No campo **Quantidade**, insira `5`.
7. No Painel de Ação, selecione **Compra**.
8. Selecione **Confirmar**.

## <a name="record-receipt-of-goods"></a>Registrar recebimento de mercadorias
1. No Painel de Ação, selecione **Receber**.
2. Selecione **Recebimento de produtos**. O campo **Quantidade** permite que você selecione opções diferentes para a quantidade que você quer receber. Por exemplo, se uma quantidade tiver sido registrada previamente no armazém, você poderá selecionar **Quantidade registrada**. Neste exemplo, use o valor **Quantidade solicitada**.
3. Expanda a seção **Visão geral**.
4. No campo **Recebimento de produtos**, digite qualquer valor. Este campo é usado para inserir uma referência que seja usada como comprovante do diário de recebimentos de produtos.  
5. Expanda a seção **Linhas**.
6. Defina **Quantidade** como '4'. Aqui você pode especificar manualmente a quantidade que está sendo recebida para cada linha na ordem.  
7. Selecione **OK**. As mercadorias foram agora registradas como recebidas na ordem de compra, e um diário de recebimentos de produtos foi criado como documento para refletir isto. Você pode usar a ação de Recebimento de produtos para revisar os diários criados com a ordem de compra e ver o que foi recebido, e quando.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]