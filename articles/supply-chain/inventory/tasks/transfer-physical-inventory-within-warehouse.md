---
title: "Transferir estoque físico no depósito"
description: "Este procedimento aborda o processo de criação e lançamento de um diário de transferência de estoque para registrar a movimentação de um item de um local em um depósito para outro."
author: MarkusFogelberg
manager: AnnBe
ms.date: 03/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 9b947a02be981155053e33a4ef20e19bf2a194a5
ms.openlocfilehash: fedb209ab111ed1fb6281fda2f4dea345e0905ef
ms.contentlocale: pt-br
ms.lasthandoff: 07/27/2017

---
# <a name="transfer-physical-inventory-within-the-warehouse"></a>Transferir estoque físico no depósito

[!include[task guide banner](../../includes/task-guide-banner.md)]

Este procedimento aborda o processo de criação e lançamento de um diário de transferência de estoque para registrar a movimentação de um item de um local em um depósito para outro. Você precisa definir um nome de diário de estoque para transferências de estoque antes de criar este. Você pode seguir esse procedimento na empresa de dados de demonstração USMF usando os valores do exemplo que são mostrados ou usando seus próprios dados se tiver produtos e locais configurados. Essas tarefas normalmente seriam realizadas por um funcionário do depósito.


## <a name="create-an-inventory-transfer-journal"></a>Criar um diário de transferência de estoque
1. Vá para Transferência.
2. Clique em Novo.
3. No campo Nome, insira ou selecione um valor.
4. Clique em OK.
    * Há uma opção para especificar as dimensões 'De' e 'Para' de cada linha do diário. Elas são essenciais para esse tipo de diário. Você pode transferir os itens para localizações com diferentes regras. Neste exemplo, transferiremos um item, no mesmo depósito, de um local controlado por placa de licença a um local que não é controlado por placa de licença.   

## <a name="create-journal-lines"></a>Criar linhas de diário
1. Clique em Novo.
2. No campo Número do item, insira ou selecione um valor.
    * Se você estiver usando USMF, você pode selecionar 'A0001'.  
3. No campo Site de origem, insira ou selecione um valor.
    * Se você estiver usando USMF, você pode selecionar '2'.  
4. No campo Site de destino, insira ou selecione um valor.
    * Se você estiver usando USMF, você pode selecionar '2'.  
5. No campo Depósito de origem, insira ou selecione um valor.
    * Se você estiver usando USMF, você pode selecionar '24'.  
6. No campo Depósito de destino, insira ou selecione um valor.
    * Se você estiver usando USMF, você pode selecionar '24'.  
7. No campo Localização de origem, insira ou selecione um valor.
    * Se você estiver usando USMF, você pode selecionar 'FL-001'.  
8. No campo Local de destino, insira ou selecione um valor.
    * Se você estiver usando USMF, você pode selecionar 'BULK-001'.  
9. No campo Quantidade, insira um número.
10. Clique na guia Dimensões de estoque.
11. No campo Placa de licença, insira ou selecione um valor.
    * Se você estiver usando USMF, você pode selecionar '24'.  
12. Clique em Salvar.

## <a name="post-the-inventory-transfer-journal"></a>Lançar o diário de transferência de estoque
1. Clique em Lançar.
2. Clique em OK.

## <a name="view-inventory-transactions"></a>Exibir transações de estoque
1. Clique em Estoque.
2. Clique em Transações.
    * Aqui é possível ver as transações que foram criadas quando você lançou seu diário.  
