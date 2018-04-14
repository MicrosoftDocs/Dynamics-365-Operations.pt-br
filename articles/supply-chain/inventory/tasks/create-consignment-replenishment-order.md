---
title: "Criar uma ordem de reabastecimento de consignação"
description: Este procedimento mostra como criar uma ordem de reabastecimento de remessa que possa acompanhar a entrega esperada de um fornecedor no estoque de remessa.
author: mkirknel
manager: AnnBe
ms.date: 10/13/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: f7f8005ec9e723c94d53e6ab81f04ee388c83faa
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-consignment-replenishment-order"></a>Criar uma ordem de reabastecimento de consignação

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

Este procedimento mostra como criar uma ordem de reabastecimento de remessa que possa acompanhar a entrega esperada de um fornecedor no estoque de remessa. Também mostra como registrar o recebimento de produtos de modo que o estoque da remessa esteja registrado em um inventário disponível pertencido ao fornecedor. Esse procedimento seria feito normalmente por um profissional de compras. Você pode usar este guia na empresa USMF de dados de demonstração. Este procedimento é para um recurso que foi adicionado à versão 1611 do Dynamics 365 for Operations.




## <a name="create-a-consignment-replenishment-order"></a>Criar uma ordem de reabastecimento de consignação
1. Vá para Compras > Consignação > Ordens de reabastecimento de consignação.
2. Clique em Novo.
3. No campo Conta de fornecedor, selecione o fornecedor US-104.
    * Marque um fornecedor que está registrado como o proprietário da os proprietários de estoque.  
4. Clique em OK.
5. Clique em Adicionar linha.
6. No campo Número do item, digite M9211CI.
    * Você deve selecionar um item configurado para estoque de remessa.  
7. No campo Quantidade, insira um número.
8. No campo Data de entrega solicitada, insira uma data.
    * Datas solicitadas e confirmadas são usadas por mecanismo de MRP para entrada esperada de mercadorias.  
9. No campo Data de entrega confirmada, insira uma data.
10. Expanda a seção Detalhes da linha.
11. Clique na guia Dimensões de estoque.
12. Mostrar para o proprietário no proprietário de dimensões de estoque, atualizar a página.
    * O fornecedor US-104 agora está listado como proprietário.  

## <a name="check-the-inventory-transaction-status"></a>Verifique o status da Data da transação de estoque
1. Clique em Estoque.
2. Clique em Transações.
3. Na lista, marque a linha selecionada.
    * Observe que o campo de recebimento será definido como Encomendado.  
4. Feche a página.

## <a name="receive-items"></a>Receber itens
1. Clique em Recebimento de produtos.
2. No campo Recebimento de produtos externos, digite um valor.
3. No campo quantidade, insira um número que é menor que o número que é mostrado.
4. Clique em OK.

## <a name="check-the-on-hand-inventory"></a>Verifique o estoque disponível
1. Clique em Estoque.
2. Clique em Disponível.
3. Clique em Visão geral.
    * Os itens recebidos como o estoque de remessa possuído por fornecedor disponíveis disponível. A quantidade pendente na ordem de reabastecimento de remessa é mostrada no campo total de Solicitado.  
4. Feche a página.
5. Clique em Fechar.

