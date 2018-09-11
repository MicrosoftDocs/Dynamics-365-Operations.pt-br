--- 
title: "Contar estoque em um depósito"
description: "Este procedimento aborda o processo de criação e lançamento de um diário de contagem de estoque para que um item específico em um local do depósito seja contabilizado."
author: MarkusFogelberg
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventJournalCount, InventJournalCreate, HcmWorkerLookUp, InventItemIdLookupSimple, InventLocationIdLookup, WMSLocationIdLookup, InventTrans
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: fa72cb0d651f5e60797fa41f6e2b2cf1891730b5
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---
# <a name="count-inventory-in-a-warehouse"></a>Contar estoque em um depósito

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este procedimento aborda o processo de criação e lançamento de um diário de contagem de estoque para que um item específico em um local do depósito seja contabilizado. O procedimento é aplicado à funcionalidade de “armazenamento básico“, disponível no módulo Gerenciamento de estoque, não à funcionalidade de armazenamento que está disponível no módulo Gerenciamento de depósito. Você pode ver todo esse procedimento na empresa USMF de dados demo, ou usando seus próprios dados. Se estiver usando seus próprios dados, certifique-se de que os produtos e localizações estão configurados e que você criou um nome de diário de estoque para diários de contagem. A contagem de estoque costuma ser realizada por um funcionário de depósito.


## <a name="create-an-inventory-counting-journal"></a>Criar diário de contagem de estoque
1. Vá para Gerenciamento de estoque > Entradas de diário > Contagem de itens > Contagem.
2. Clique em Novo.
3. No campo Nome, clique no botão suspenso para abrir a pesquisa.
4. Na lista, clique no nome do diário de contagem de estoque que deseja usar
    * Alguns outros campos serão preenchidos com base na configuração do nome do diário de contagem de estoque que você selecionar.  
5. No campo Trabalhador, clique no botão suspenso para abrir a pesquisa.
6. Na lista, selecione o trabalhador que deseja utilizar.
7. Clique em Selecionar.
8. Clique em OK.

## <a name="create-journal-lines"></a>Criar linhas de diário
1. Clique em Novo.
2. No campo Número de item, clique no botão suspenso para abrir a pesquisa.
3. Na lista, localize e selecione o PDV desejado.
    * Se estiver usando a empresa de dados de demonstração USMF, selecione 'A0001'.  
4. No campo Local, clique no botão suspenso para abrir a pesquisa.
5. Na lista, localize e selecione o PDV desejado.
    * Se estiver usando a empresa de dados de demonstração USMF, selecione o site '2'.  
6. No campo Depósito, clique no botão suspenso para abrir a pesquisa.
7. Na lista, localize e selecione o PDV desejado.
    * Se estiver usando a empresa de dados de demonstração USMF, selecione o depósito '24'.  
8. No campo Localização, clique no botão suspenso para abrir a pesquisa.
9. Na lista, localize e selecione o PDV desejado.
    * Se estiver usando a empresa de dados de demonstração USMF, selecione a localização 'BULK-001'.  
10. No campo Contado, insira um número.
    * Se você inserir um número contabilizado que é diferente do número mostrado no campo Disponível, o campo Quantidade é atualizado para mostrar a discrepância.  
11. Clique em Salvar.

## <a name="post-the-inventory-counting-journal"></a>Lançar o diário de contagem de estoque
1. Clique em Lançar.
    * Ao lançar um diário de contagem de estoque, se o valor contabilizado diferir do valor informado no campo Disponível, um recebimento ou emissão de estoque é lançado, o nível e o valor do estoque são alterados e as transações do razão são geradas.  
2. Clique em OK.

## <a name="view-inventory-transactions"></a>Exibir transações de estoque
1. Clique em Estoque.
2. Clique em Transações.
    * Aqui é possível ver qualquer transação relacionada que será criada quando você lançar seu diário de contagem de estoque.   


