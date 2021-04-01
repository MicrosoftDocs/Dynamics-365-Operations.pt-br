---
title: Alterar regras kanban para um trabalho de processamento
description: Esse procedimento se concentra em alterar a regra kanban usada para um kanban específico.
author: ChristianRytt
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanRules, KanbanRuleDuplicate, KanbanJobSchedulingListPage, LeanRuleReassignmentWizard, KanbanReassignRuleLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ba77197f51b871f452c2aa94320aa2a68cf314df
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5255364"
---
# <a name="change-kanban-rules-for-a-process-job"></a>Alterar regras kanban para um trabalho de processamento

[!include [banner](../../includes/banner.md)]

Esse procedimento se concentra em alterar a regra kanban usada para um kanban específico. Isso é útil para nivelar recursos de carga ou no caso de divisão. A empresa de dados demo usada para criar este procedimento é USMF. Esse procedimento é destinado ao planejador que trabalha em uma empresa de lean manufacturing, responsável pelo fluxo de valor.


## <a name="copy-kanban-rule"></a>Copiar regra kanban
1. Vá para Regras kanban.
2. Na lista, localize e selecione o PDV desejado.
    * Selecione a regra kanban de evento 000022 para L0001.  
3. Clique em Duplicar regra kanban.
4. Clique em OK.

## <a name="change-kanban-rule"></a>Alterar a regra kanban
1. Feche a página.
2. Vá para Agendamento do trabalho kanban.
3. Na lista, marque a linha selecionada.
    * Selecione a linha com kanban 000177.  
4. Clique em Usar regra kanban alternativa.
5. Clique em Avançar.
6. No campo Regra kanban, insira ou selecione um valor.
    * Selecione a regra kanban que criada anteriormente. Esta é a regra kanban com o número mais alto.  
7. Clique em Finish (Concluir).
    * Agora o trabalho kanban está usando uma outra regra kanban. Isso pode ser útil para nivelar células de trabalho de carga.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]