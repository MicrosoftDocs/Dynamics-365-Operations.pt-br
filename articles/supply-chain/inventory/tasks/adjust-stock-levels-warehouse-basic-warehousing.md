---
title: Ajustar níveis de estoque no depósito (armazenamento básico)
description: Esse procedimento o orientará no processo de criação e lançamento de um diário de ajuste de estoque para que os níveis de estoque de produtos no depósito sejam ajustados.
author: yufeihuang
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: InventJournalLossProfit, InventJournalCreate, InventLocationIdLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 02458d588c9925a1f4cb9afeada793dfc55a2071
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7573816"
---
# <a name="adjust-stock-levels-in-the-warehouse-basic-warehousing"></a>Ajustar níveis de estoque no depósito (armazenamento básico)

[!include [banner](../../includes/banner.md)]

Esse procedimento o orientará no processo de criação e lançamento de um diário de ajuste de estoque para que os níveis de estoque de produtos no depósito sejam ajustados. Você precisa definir um nome de diário de estoque para ajustes de estoque antes de criar este. Você pode ver todo esse procedimento na empresa USMF de dados demo, ou usando seus próprios dados. Essas tarefas normalmente seriam realizadas por um funcionário do depósito.


## <a name="create-an-inventory-adjustment-journal"></a>Criar um diário de ajuste de estoque
1. Acesse Gerenciamento de estoque > Entradas de diário > Itens > Ajuste de estoque.
2. Clique em Novo.
3. No campo Nome, clique no botão suspenso para abrir a pesquisa.
4. Na lista, clique no nome do diário de ajuste de estoque que deseja usar.
    * Alguns outros campos serão preenchidos com base na configuração do nome do diário de ajuste de estoque que você selecionar.  
5. Clique em OK.

## <a name="create-journal-lines"></a>Criar linhas de diário
1. Clique em Novo.
2. Na lista, marque o campo de número do item.
3. No campo de número do item, selecione um item. Se estiver usando a empresa USMF de dados de demonstração, digite 'D0001'.
4. No campo Local, clique no botão suspenso para abrir a pesquisa.
5. Na lista, selecione um site.
6. No campo Depósito, clique no botão suspenso para abrir a pesquisa.
7. Na lista, selecione um depósito.
    * Se já selecionou um item com Localização como dimensão obrigatória, você precisaria especificar a localização aqui.  
8. No campo Quantidade, insira um número.
    * O campo de preço de custo especifica o custo por unidade para recebimentos de estoque. Se o custo não for especificado para o número do item ou se você pretendia alterá-lo manualmente, você poderia fazer isso aqui.  

## <a name="validate-and-post-the-inventory-adjustment-journal"></a>Validar e lançar o diário de ajuste de estoque
1. Clique em Validar.
2. Clique em OK.
3. Clique em Lançar.
    * Quando você lança esse tipo de diário, é lançado um recebimento ou uma saída de estoque, o nível de estoque e o valor são alterados e as transações do razão são geradas.  
4. Clique em OK.
5. Feche o formulário.
6. Feche a página.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]