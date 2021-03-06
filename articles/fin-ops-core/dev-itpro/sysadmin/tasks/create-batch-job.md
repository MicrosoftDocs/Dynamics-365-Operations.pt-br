---
title: Criar um trabalho em lotes
description: Um trabalho em lotes é um grupo de tarefas que são enviadas para uma instância do Application Object Server (AOS) para processamento automático.
author: maertenm
ms.date: 06/21/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: BatchJob, SysRecurrence, BatchAlerts
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f498014555e0beccbc8965dd43e5162944867978
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5745852"
---
# <a name="create-a-batch-job"></a>Criar um trabalho em lotes

[!include [banner](../../includes/banner.md)]

Um trabalho em lotes é um grupo de tarefas que são enviadas para uma instância do Application Object Server (AOS) para processamento automático. Os trabalhos em lotes são executados usando as credenciais de segurança do usuário que criou o trabalho. Use o procedimento a seguir para criar um trabalho de lote. A empresa de dados demo usada para criar este procedimento é USMF.


## <a name="create-the-batch-job"></a>Criar o trabalho em lotes
1. Vá para **Painel de navegação > Módulos > Administração do sistema > Consultas > Trabalhos em lotes**.
2. Clique em **Novo**.
3. No campo **Descrição do trabalho**, digite um valor.
4. No campo **Data/hora inicial agendada**, insira uma data e hora.
5. Clique em **Salvar**.

## <a name="create-a-recurrence"></a>Criar uma recorrência
1. No Painel de Ação, clique em **Trabalho em lotes**.
2. Clique em **Recorrência**. Use estas opções para inserir um intervalo e um padrão para a recorrência.  
3. Clique em **OK**.

## <a name="add-alerts"></a>Adicionar alertas
1. No Painel de Ação, clique em **Trabalho em lotes**.
2. Clique em **Alertas**. Indique se você quer que mensagens de alertas sejam enviadas quando as extremidades do trabalho de grupo, tiverem um erro ou forem canceladas. Especifique então se você quer que os alertas indiquem como mensagens pop-up.   
3. Clique em **OK**.

## <a name="adjust-batch-job-status"></a>Ajuste o status de trabalho em lotes
1. Vá para **Administração do sistema > Consultas > Trabalhos em lotes**.
2. Selecione o trabalho em lotes apropriado.
3. No Painel de Ação, clique em **Trabalho em lotes > Funções > Alterar status**.
4. Selecione o status apropriado:
    - **Reter**: definir o trabalho em lotes como **reter** para que seja retido do agendador de trabalho em lotes. Equivalente a *parar*.
    - **Aguardar**: definir o trabalho em lotes como **aguardar** para que aguarde para ser retirado pelo agendador de trabalho em lotes. Equivalente a *ir*.
5. Clique em **OK**.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]