---
title: Usar o diário de estoque de segurança para atualizar a cobertura mínima
description: Este procedimento mostra como calcular propostas de cobertura mínima baseadas em transações históricas e, em seguida, atualizar a cobertura do item com as propostas.
author: ChristianRytt
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqItemJournalName, ReqItemJournalSafetyStock, EcoResProductInformationDialog, EcoResProductDetailsExtended, ReqItemTable
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7a6e217d476cedc0318c382e12b7dc2036e557c3
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1571418"
---
# <a name="use-the-safety-stock-journal-to-update-minimum-coverage"></a>Usar o diário de estoque de segurança para atualizar a cobertura mínima

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este procedimento mostra como calcular propostas de cobertura mínima baseadas em transações históricas e, em seguida, atualizar a cobertura do item com as propostas. Isso é feito usando o diário de estoque de segurança. A empresa de dados demo usada para criar esta tarefa é USMF. Essa tarefa é pretendida para o planejador da produção, para ajudar a manter a cobertura mínima.


## <a name="create-a-new-safety-stock-journal-name"></a>Crie um novo nome de diário de estoque seguro
1. Vá para Nomes do diário de estoque de segurança.
2. Clique em Novo.
3. No campo Nome, digite "Material".
4. No campo Descrição, digite "Material".
5. Feche a página.

## <a name="create-a-safety-stock-journal"></a>Criar um diário de estoque de segurança
1. Vá para Cálculo de estoque de segurança.
2. Clique em Novo.
3. No campo Nome, insira ou selecione um valor.
    * Selecione o nome do diário de estoque de segurança que você criou, por exemplo, Material.  
4. Clique em Criar linhas.
5. No campo De data, insira uma data.
    * Defina a data para '2015-01-02'.  
6. No campo Para data, insira uma data.
    * Defina a data para '2015-12-30'.  
7. Clique em OK.
    * Isso criará linhas para as dimensões que têm transações de estoque.  

## <a name="calculate-proposal"></a>Calcular proposta
1. Clique em Calcular proposta.
2. Selecione a opção Usar média de saídas durante o prazo de entrega.
3. Defina o fator de multiplicação como "10".
    * O fator da multiplicação é usado para ajustar a proposta. Como os dados de demonstração têm somente algumas transações, você precisará definir o fator para obter uma proposta realística.  
4. Clique em OK.
    * Role para baixo para encontrar M0002 e M0003. Veja a coluna Quantidade mínima calculada.   

## <a name="update-minimum-quantity"></a>Atualizar quantidade mínima
1. No campo Nova quantidade mínima, insira um número.
    * Atualize a Nova quantidade mínima para corresponder ao valor na Quantidade mínima calculada. Se o mínimo calculado for zero, você poderá inserir o valor futuro desejado. Por exemplo, você pode inserir a Quantidade mínima calculada neste campo para o M0002 que tem o armazém 12.  
2. Na lista, localize e selecione o PDV desejado.
    * Por exemplo, você pode selecionar o M0002 que tem o armazém 12.  
3. No campo Nova quantidade mínima, insira um número.
    * Atualize a Nova quantidade mínima para corresponder ao valor na Quantidade mínima calculada. Se o mínimo calculado for zero, você poderá inserir o valor futuro desejado.  

## <a name="post-the-new-minimum-quantity-and-validate-the-result"></a>Lançar a nova quantidade mínima e validar o resultado
1. Clique em Lançar.
2. Clique em OK.
3. Clique para seguir o link no campo Número de item.
4. Clique para seguir o link no campo Número de item.
5. No Painel de Ação, clique em Plano.
6. Clique em Cobertura de item.
    * Observe que a Quantidade mínima foi atualizada com a nova quantidade mínima do diário de estoque de segurança.  

