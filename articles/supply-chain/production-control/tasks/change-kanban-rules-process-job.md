--- 
title: Alterar regras kanban para um trabalho de processamento
description: "Esse procedimento se concentra em alterar a regra kanban usada para um kanban específico."
author: ChristianRytt
manager: AnnBe
ms.date: 03/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 7f8b2a67e03a64deae9d4bc9c7e3e714d134443c
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---
# <a name="change-kanban-rules-for-a-process-job"></a>Alterar regras kanban para um trabalho de processamento

[!include[task guide banner](../../includes/task-guide-banner.md)]

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


