--- 
title: "Criar uma regra kanban de substituição"
description: "Esse procedimento se concentra em substituir uma regra kanban existente por uma nova regra kanban em uma data específica."
author: ChristianRytt
manager: AnnBe
ms.date: 06/20/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 9b947a02be981155053e33a4ef20e19bf2a194a5
ms.openlocfilehash: 58b12edbbdcf77429c32193dfd850bc53f4c26a8
ms.contentlocale: pt-br
ms.lasthandoff: 07/27/2017

---
# <a name="create-a-replacement-kanban-rule"></a>Criar uma regra kanban de substituição

[!include[task guide banner](../../includes/task-guide-banner.md)]

Esse procedimento se concentra em substituir uma regra kanban existente por uma nova regra kanban em uma data específica. Isso é útil quando as alterações no fluxo de produção ou as regras de reabastecimento precisam ser coordenadas e programadas. A empresa de dados de demonstração usada para criar o procedimento é USMF. Este procedimento destina-se ao engenheiro do processo ou gerente de fluxo de valor, pois eles preparam a produção para uma produção de fluxo ou um produto novo ou modificado. Essa tarefa substitui a regra kanban 000022 com uma nova regra e aumenta a quantidade máxima de 48 para 100 da nova regra.


## <a name="select-a-kanban-rule-to-replace"></a>Selecionar uma regra kanban para substituir
1. Vá para Regras kanban.
2. Na lista, localize e selecione o PDV desejado.
    * Selecionar regra kanban 000022.  

## <a name="create-a-replacement-kanban-rule"></a>Criar uma regra kanban de substituição
1. Clique em Substituir regra kanban.
2. No campo de data efetiva, insira uma data e hora.
    * Selecione uma data futura, como uma semana a partir de agora. Esta é a data e a hora em que a nova regra kanban se torna ativa e substitui a regra kanban antiga.  
    * Se a regra kanban alterar o caminho no fluxo de produção, outra atividade pode ser marcada.  Nesse procedimento, manteremos a atividade intocada.  
3. Clique em OK.
    * Observe que uma nova regra kanban será criada para substituir a regra kanban 000022.  
    * A data efetiva será definida como a data separada quando você substituir a regra kanban.  
4. Na lista, localize e selecione o PDV desejado.
    * Selecionar a regra kanban substituída 000022.  
    * Observe que a regra kanban substituída tem a mesma data que a data de vencimento porque essa é a data na qual ela vai expirar.  
5. Na lista, selecione a linha 1.
    * Selecionar a nova regra kanban no topo da lista. Esta é a regra kanban com o número mais alto.  
6. Na lista, clique no link na linha selecionada.
    * Clique no número da regra kanban para abrir a regra kanban.  

## <a name="modify-maximum-quantity-for-the-replacement-kanban-rule"></a>Modifique a quantidade máxima para a regra kanban de substituição
1. Defina Quantidade máxima como '100'.
    * Expanda as quantidades FastTab para ver o campo Quantidade máxima. Alterar a quantidade máxima para 100 permitirá que até 100 kanbans sejam processados.    Esta é a última etapa da tarefa.  


