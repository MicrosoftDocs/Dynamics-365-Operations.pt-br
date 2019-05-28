---
title: Dados principais de nota fiscal no sistema AP usando a nota fiscal de fornecedor
description: Este guia de tarefas ajudará você a criar uma fatura de fornecedor a partir de uma ordem de compra e exibir os resultados da conciliação da ordem de compra, do recebimento e da fatura (conciliação tripla).
author: abruer
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, PurchCreateOrder, InventItemIdLookupPurchase, PurchEditLines, VendEditInvoice, InventItemIdLookupSimple, VendInvoiceMatchingDetails
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e1d2e31a5de7cefd20996c18bf4771296a587997
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1569623"
---
# <a name="key-invoice-data-in-ap-system-using-vendor-invoice"></a>Dados principais de nota fiscal no sistema AP usando a nota fiscal de fornecedor

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este guia de tarefas ajudará você a criar uma fatura de fornecedor a partir de uma ordem de compra e exibir os resultados da conciliação da ordem de compra, do recebimento e da fatura (conciliação tripla).


## <a name="create-a-purchase-order"></a>Crie uma ordem de compra
1. Vá para Contas a pagar > Ordens de compra > Todas as ordens de compra.
2. Clique em Novo.
3. No campo Conta de fornecedor, clique no botão suspenso para abrir a pesquisa.
4. Localize um fornecedor para selecionar. Por exemplo, role para baixo ao US-104.
5. Selecionar fornecedor US-104.
6. Clique em OK.
7. No campo Número de item, clique no botão suspenso para abrir a pesquisa.
8. Selecionar um item de estoque. Por exemplo, selecione número de item 1000.
9. Expandir ou recolher a seção Detalhes de linha.
10. Clique na guia Configuração.
    * Você pode substituir a política de conciliação para usar nenhuma conciliação, conciliação dupla ou conciliação tripla.  
11. Expandir ou recolher a seção Detalhes de linha.
12. No Painel de Ação, clique em Compra.
13. Clique em Confirmar.

## <a name="receive-the-products"></a>Receba os produtos
1. No Painel de Ação, clique em Receber.
2. Clique em Recebimento de produtos.
3. No campo Recebimento de produtos, insira o número de recebimento do produto. Por exemplo, insira PR123.
4. Clique em OK para lançar o recebimento do produto.
5. Feche a página.

## <a name="create-a-vendor-invoice"></a>Crie uma fatura de fornecedor
1. Ir para Contas a pagar > Ordens de compra > Ordens de compra recebidas, mas não faturadas.
2. Selecione a ordem de compra que você criou.
3. No Painel de Ação, clique em Fatura.
4. Clique em Fatura.
5. No campo Número, insira o número da fatura.
6. No campo Descrição da fatura, digite um valor.
7. No campo Data da fatura, insira uma data.
8. No campo Preço unitários, insira 1200.
9. Clique em Adicionar nova linha.
10. No campo Número de item, clique no botão suspenso para abrir a pesquisa.
11. Na lista, localize o número do item de encargos de instalação. Por exemplo, S0001
12. Selecione o número de item de encargo de instalação.
    * Observe que a conciliação não foi executada desde que você fez as alterações.  
13. Clique em Atualizar status de conciliação.
14. No Painel de Ação, clique em Revisar.
15. Clique em Detalhes da conciliação.
    * A nova linha com os serviços não precisa ser feita para que o status permaneça "Não realizado".  
16. Selecione o recebimento de produto para o item de estoque que você recebeu.
    * A linha com o recebimento do produto foi conciliada, mas, como há uma diferença de quantidade ou de preço, ela falha.  
17. No campo Preço unitário, insira um número.
    * Agora que o preço unitário foi conciliado, o status é atualizado para Aprovado. Se sua política permitir discrepâncias ou se a conciliação for apenas um aviso, você ainda poderá lançar a fatura.  
18. Feche a página.
19. Clique em Lançar.
20. Feche o formulário.
    * Observe que a ordem de compra não está mais listada como recebida, mas como não faturada.  

