--- 
title: Definir grupos de agendamento de lean manufacturing
description: "Os grupos de agendamento de lean manufacturing são definidos para agrupar e distinguir produtos na programação do kanban."
author: cvocph
manager: AnnBe
ms.date: 11/03/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 3e07fa270b47be3527c572dc53ca30a7bcde5ba6
ms.contentlocale: pt-br
ms.lasthandoff: 11/03/2017

---
# <a name="define-lean-schedule-groups"></a>Definir grupos de agendamento de lean manufacturing

[!include [task guide banner](../../includes/task-guide-banner.md)]

Os grupos de agendamento de lean manufacturing são definidos para agrupar e distinguir produtos na programação do kanban. O agrupamento pode ser feito como a associação genérica por empresa ou ser específico de uma célula de trabalho. Cada grupo tem um código de cor atribuído para a indicação visual na página de listagem de agendamento de kanban. A empresa de dados demo usada para criar este procedimento é USMF.


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
    * O Índice de produtividade padrão é 1, o que significa que os produtos relacionados consomem exatamente a capacidade especificada em atividades de processo dos fluxos de produção. O Índice de produtividade > 1 define um consumo de recursos mais alto, e o Índice de produtividade < 1 define um consumo de recursos mais baixo. O índice é usado no cálculo do custo e no cálculo do consumo de trabalhos kanban.  

## <a name="associate-item-allocation-key"></a>Associe chave de alocação de item
1. Associe uma chave de alocação de item
    * Adicionar uma associação a uma chave de alocação de item usando o Grupo do tipo de relação de itens.   Observe que, para esse processo, você precisa de uma chave de alocação de item de previsão definida em seus dados.  
2. No campo Tipo de relação de itens, selecione Grupo
3. No campo Chave de alocação de itens, clique no botão suspenso para abrir a pesquisa.
4. Na lista, clique no link na linha selecionada.


