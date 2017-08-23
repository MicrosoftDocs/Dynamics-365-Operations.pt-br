--- 
title: Criar um trabalho em lotes
description: "Um trabalho em lotes é um grupo de tarefas que são enviadas para uma instância do Application Object Server (AOS) para processamento automático."
author: maertenm
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.author: maertenm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: ca2b755406fb7fce4b11457be86f6a8685004438
ms.contentlocale: pt-br
ms.lasthandoff: 07/27/2017

---
# <a name="create-a-batch-job"></a>Criar um trabalho em lotes

[!include[task guide banner](../../includes/task-guide-banner.md)]

Um trabalho em lotes é um grupo de tarefas que são enviadas para uma instância do Application Object Server (AOS) para processamento automático. Os trabalhos em lotes são executados usando as credenciais de segurança do usuário que criou o trabalho. Use o procedimento a seguir para criar um trabalho de lote. A empresa de dados demo usada para criar este procedimento é USMF.


## <a name="create-the-batch-job"></a>Criar o trabalho em lotes
1. Vá para Administração do sistema > Consultas > Trabalhos em lotes.
2. Clique em Novo.
3. No campo Descrição do trabalho, digite um valor.
4. No campo Data/hora inicial agendada, insira uma data e hora.
5. Clique em Salvar.

## <a name="create-a-recurrence"></a>Criar uma recorrência
1. No Painel de Ação, clique em Trabalho em lotes.
2. Clique em Recorrência.
    * Use estas opções para inserir um intervalo e um padrão para a recorrência.  
3. Clique em OK.

## <a name="add-alerts"></a>Adicionar alertas
1. No Painel de Ação, clique em Trabalho em lotes.
2. Clique em Alertas.
    * Indique se você quer que mensagens de alertas sejam enviadas quando as extremidades do trabalho de grupo, tiverem um erro ou forem canceladas. Especifique então se você quer que os alertas indiquem como mensagens pop-up.   
3. Clique em OK.


