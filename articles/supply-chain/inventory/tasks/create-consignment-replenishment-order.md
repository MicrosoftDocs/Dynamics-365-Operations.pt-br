---
title: Criar uma ordem de reabastecimento de consignação
description: Este tópico explica como criar uma ordem de reabastecimento de remessa que possa acompanhar a entrega esperada de um fornecedor no estoque de remessa.
author: mkirknel
manager: AnnBe
ms.date: 08/19/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ConsignmentReplenishmentOrder, ConsignmentReplenishmentOrderCreate, InventTrans, ConsignmentDraftReplenishmentOrderJournal, InventOnhandMovement, InventOnhandItem, InventItemIdLookupSimple
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f426dbf00eace23da2f26eb50dd9675fe22ed445
ms.sourcegitcommit: e10491a2ff04f65d9f306ef6e068ee123213b23b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/21/2019
ms.locfileid: "1914760"
---
# <a name="create-a-consignment-replenishment-order"></a>Criar uma ordem de reabastecimento de consignação

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este tópico explica como criar uma ordem de reabastecimento de remessa que possa acompanhar a entrega esperada de um fornecedor no estoque de remessa. Também mostra como registrar o recebimento de produtos de modo que o estoque da remessa esteja registrado em um inventário disponível pertencido ao fornecedor. Esse procedimento seria feito normalmente por um profissional de compras. Você pode usar este guia na empresa USMF de dados de demonstração. Este procedimento é para um recurso que foi adicionado na versão 1611 do Dynamics 365 for Operations.

## <a name="create-a-consignment-replenishment-order"></a>Criar uma ordem de reabastecimento de consignação
1. No Painel de Navegação, vá para **Módulos > Compras e fornecimento > Consignação > Ordens de reabastecimento de consignação**.
2. Selecione **Novo**.
3. No campo **Conta de fornecedor**, selecione o fornecedor **US-104** (é preciso selecionar um fornecedor registrado como proprietário na página **proprietários de estoque**). 
4. Selecione **OK**.
5. Selecione **Adicionar linha**.
6. No campo **Número do item**, digite `M9211CI` (é preciso selecionar um item configurado para o estoque em consignação).
7. No campo **Quantidade.**, insira um número
8. No campo **Data de entrega solicitada**, insira uma data. Datas solicitadas e confirmadas são usadas por mecanismo de MRP para entrada esperada de mercadorias.  
9. No campo **Data de entrega confirmada**, insira uma data.
10. Expanda a seção **Detalhes da linha**.
11. Selecione a guia **Dimensões de estoque**.
12. Para mostrar o proprietário no campo **Proprietário de dimensões de estoque**, atualize a página. O fornecedor US-104 agora está listado como proprietário.  

## <a name="check-the-inventory-transaction-status"></a>Verifique o status da Data da transação de estoque
1. Selecione **Estoque**.
2. Selecione **Transações**.
3. Na linha desejada, observe que o campo **Recibo** é definido como **Encomendado**.  
4. Feche a página.

## <a name="receive-items"></a>Receber itens
1. Selecione **Recebimento de produtos**.
2. No campo **Recebimento de produtos externos**, digite um valor.
3. No campo **Quantidade**, insira um número que é menor que o número que é mostrado. 
4. Selecione **OK**.

## <a name="check-the-on-hand-inventory"></a>Verifique o estoque disponível
1. Selecione **Estoque**.
2. Selecione **Disponível**.
3. Selecione **Visão Geral**. Os itens recebidos como o estoque de remessa possuído por fornecedor disponíveis disponível. A quantidade pendente na ordem de reabastecimento da consignação é mostrada no campo **Total encomendado**.  
4. Feche a página.

