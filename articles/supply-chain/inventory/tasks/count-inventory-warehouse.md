---
title: Contar estoque em um depósito
description: Este tópico descreve o processo de criação e lançamento de um diário de contagem de estoque para que um item específico em um local do depósito seja contabilizado.
author: MarkusFogelberg
ms.date: 07/09/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: InventJournalCount, InventJournalCreate, HcmWorkerLookUp, InventItemIdLookupSimple, InventLocationIdLookup, WMSLocationIdLookup, InventTrans
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1cc89e3773005502c193364a721a835fe01dde9f1f22046e9c10c7d186b508d5
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6768134"
---
# <a name="count-inventory-in-a-warehouse"></a>Contar estoque em um depósito

[!include [banner](../../includes/banner.md)]

Este tópico descreve o processo de criação e lançamento de um diário de contagem de estoque para que um item específico em um local do depósito seja contabilizado. O procedimento é aplicado à funcionalidade de "armazenamento básico", disponível no módulo Gerenciamento de estoque, não à funcionalidade de armazenamento que está disponível no módulo Gerenciamento de depósito. Você pode ver todo esse procedimento na empresa USMF de dados demo, ou usando seus próprios dados. Se estiver usando seus próprios dados, certifique-se de que os produtos e localizações estão configurados e que você criou um nome de diário de estoque para diários de contagem. A contagem de estoque costuma ser realizada por um funcionário de depósito.


## <a name="create-an-inventory-counting-journal"></a>Criar diário de contagem de estoque
1. Acesse **Painel de navegação > Módulos > Gerenciamento de estoque > Entradas de diário > Contagem de itens > Contagem**.
2. Selecione **Novo**.
3. No campo **Nome** , selecione o nome de diário de contagem de estoque a ser usado na lista suspensa. Alguns outros campos serão preenchidos com base na configuração do nome do diário de contagem de estoque que você selecionar.  
4. No campo **Trabalhador**, selecione o botão suspenso para abrir a pesquisa.
5. Na lista, **Selecionar** o trabalhador que você deseja utilizar.
6. Selecione **OK**.

## <a name="create-journal-lines"></a>Criar linhas do diário
1. Selecione **Novo**.
2. No campo **Número do item**, selecione o registro desejado na lista suspensa. Se estiver usando a empresa de dados de demonstração USMF, selecione **A0001**.  
3. No campo **Site**, selecione o registro desejado na lista suspensa. Se estiver usando a empresa de dados de demonstração USMF, selecione o site **2**.
4. No campo **Depósito**, selecione o registro desejado na lista suspensa. Se estiver usando a empresa de dados de demonstração USMF, selecione o depósito **24**.  
5. No campo **Local**, selecione o registro desejado na lista suspensa. Se estiver usando a empresa de dados de demonstração USMF, selecione o local **BULK-001**.  
6. No campo Contado, insira um número. Se você inserir um número contabilizado que é diferente do número mostrado no campo **Disponível**, o campo **Quantidade** será atualizado para mostrar a discrepância.  
7. Selecione **Salvar**.

## <a name="post-the-inventory-counting-journal"></a>Lançar o diário de contagem de estoque
1. Selecione **Lançar**. Ao lançar um diário de contagem de estoque, se o valor contabilizado diferir do valor informado no campo **Disponível**, um recebimento ou emissão de estoque será lançado, o nível e o valor do estoque serão alterados e as transações do razão serão geradas.
2. Selecione **OK**.

## <a name="view-inventory-transactions"></a>Exibir transações de estoque
1. Selecione **Estoque**.
2. Selecione **Transações**. Aqui é possível ver qualquer transação relacionada que será criada quando você lançar seu diário de contagem de estoque.   



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]