--- 
title: Definir grupos de agendamento de lean manufacturing
description: "Os grupos de agendamento de lean manufacturing são definidos para agrupar e distinguir produtos na programação do kanban."
author: cvocph
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 9b947a02be981155053e33a4ef20e19bf2a194a5
ms.openlocfilehash: 75d8b6614fd3b36d87bcb95b0b753b611a101f62
ms.contentlocale: pt-br
ms.lasthandoff: 07/27/2017

---
# <a name="define-lean-schedule-groups"></a>Definir grupos de agendamento de lean manufacturing

[!include[task guide banner](../../includes/task-guide-banner.md)]

Os grupos de agendamento de lean manufacturing são definidos para agrupar e distinguir produtos na programação do kanban. O agrupamento pode ser feito como a associação genérica por empresa ou ser específico de uma célula de trabalho. Cada grupo tem um código de cor atribuído para a indicação visual na página de lista da programação kanban. A empresa de dados demo usada para criar este procedimento é USMF.


## <a name="define-lean-scheduling-group"></a>Definir grupo de agendamento de lean manufacturing
1. Vá para Gerenciamento de informações do produto > Lean manufacturing > Grupos de agendamento de lean manufacturing.
2. Clique em Novo.
3. No campo Grupo de agendamento, digite um valor.
    * Um grupo de agendamento pode ser definido como o grupo global ou específico para uma célula de trabalho. Neste exemplo simples, definimos um grupo global e a célula de trabalho é mantida em branco. As configurações deste grupo se aplicam a todas as células de trabalho que não tenham grupos de agendamento específicos.  
4. Selecione uma cor da seleção de cor.
    * As cores são usadas para realçar os trabalhos na página de lista da agenda kanban ou no quadro do processo do kanban.  
5. Na lista, marque a linha selecionada.
6. Na lista, clique no link na linha selecionada.

## <a name="associate-product"></a>Produtos associados
1. Associar um produto específico
    * Há duas maneiras de associar a grupos de agendamento de lean manufacturing, como um produto específico (Tipo de relação de itens = Item) ou como parte de uma chave de alocação de itens (tipo de relação de item = grupo).    
2. No campo Tipo de relação de itens, selecione Item
3. No campo Número de item, digite um valor.
4. No campo Índice de produtividade, insira um número.
    * O Índice de produtividade padrão é 1, o que significa que os produtos relacionados consomem exatamente a capacidade especificada em activites do processo dos fluxos de produção. O Índice de produtividade > 1 define um consumo de recursos mais alto, e o Índice de produtividade < 1 define um consumo de recursos mais baixo. O índice é usado no cálculo do custo e no cálculo do consumo de trabalhos kanban.  

## <a name="associate-item-allocation-key"></a>Associe chave de alocação de item
1. Associe uma chave de alocação de item
    * Adicionar uma associação a uma chave de alocação de item usando o Grupo do tipo de relação de itens.   Observe que para esse processo, você precisa de uma chave de alocação de item de previsão definida em seus dados.  
2. No campo Tipo de relação de itens, selecione Grupo
3. No campo Chave de alocação de itens, clique no botão suspenso para abrir a pesquisa.
4. Na lista, clique no link na linha selecionada.

