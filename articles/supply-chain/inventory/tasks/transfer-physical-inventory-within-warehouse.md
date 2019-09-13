---
title: Transferir estoque físico no depósito
description: Este procedimento aborda o processo de criação e lançamento de um diário de transferência de estoque para registrar a movimentação de um item de um local em um depósito para outro.
author: MarkusFogelberg
manager: AnnBe
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventJournalTransfer, InventJournalCreate, InventItemIdLookupSimple, InventLocationIdLookup, WMSLocationIdLookup, InventTrans
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7715c8e7a56703993e8512af03f2ab8d6802a987
ms.sourcegitcommit: cbcf344b3b552acca56c3e27606eac7f2f124afe
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/22/2019
ms.locfileid: "1916567"
---
# <a name="transfer-physical-inventory-within-the-warehouse"></a>Transferir estoque físico no depósito

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este procedimento aborda o processo de criação e lançamento de um diário de transferência de estoque para registrar a movimentação de um item de um local em um depósito para outro. Você precisa definir um nome de diário de estoque para transferências de estoque antes de criar este. Você pode seguir esse procedimento na empresa de dados de demonstração USMF usando os valores do exemplo que são mostrados ou usando seus próprios dados se tiver produtos e locais configurados. Essas tarefas normalmente seriam realizadas por um funcionário do depósito.


## <a name="create-an-inventory-transfer-journal"></a>Criar um diário de transferência de estoque
1. No **Painel de navegação**, acesse **Gerenciamento de estoque > Entradas de diário > Itens > Transferência**.
2. Clique em **Novo**.
3. No campo **Nome**, insira ou selecione um valor.
4. Clique em **OK**. Há uma opção para especificar as dimensões 'De' e 'Para' de cada linha do diário. Elas são essenciais para esse tipo de diário. Você pode transferir os itens para localizações com diferentes regras. Neste exemplo, transferiremos um item, no mesmo depósito, de um local controlado por placa de licença a um local que não é controlado por placa de licença.   

## <a name="create-journal-lines"></a>Criar linhas do diário
1. Na Guia Rápida **Linhas do diário**, clique em **Novo**.
2. No campo **Número do item**, insira ou selecione um valor. Se você estiver usando USMF, você pode selecionar 'A0001'.  
3. No campo **Site de origem**, insira ou selecione um valor. Se você estiver usando USMF, você pode selecionar '2'.  
4. No campo **Site de destino**, insira ou selecione um valor. Se você estiver usando USMF, você pode selecionar '2'.  
5. No campo **Depósito de origem**, insira ou selecione um valor. Se você estiver usando USMF, você pode selecionar '24'.  
6. No campo **Depósito de destino**, insira ou selecione um valor. Se você estiver usando USMF, você pode selecionar '24'.  
7. No campo **Localização de origem**, insira ou selecione um valor. Se você estiver usando USMF, você pode selecionar 'FL-001'.  
8. No campo **Local de destino**, insira ou selecione um valor. Se você estiver usando USMF, você pode selecionar 'BULK-001'.  
9. No campo **Quantidade.**, insira um número
10. Na Guia Rápida **Detalhes da linha**, clique na guia **Dimensões de estoque**.
11. Em **Das dimensões de estoque**, no campo **Placa de licença**, insira ou selecione um valor. Se você estiver usando USMF, você pode selecionar '24'.  
12. Clique em **Salvar**.

## <a name="post-the-inventory-transfer-journal"></a>Lançar o diário de transferência de estoque
1. No **Painel de Ações**, clique em **Lançar**.
2. Clique em **OK**.

## <a name="view-inventory-transactions"></a>Exibir transações de estoque
1. Clique em **Estoque**.
2. Clique em **Transações**. Aqui é possível ver as transações que foram criadas quando você lançou seu diário.  

