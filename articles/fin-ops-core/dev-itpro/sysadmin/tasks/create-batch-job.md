---
title: Criar um trabalho em lotes
description: Um trabalho em lotes é um grupo de tarefas que são enviadas para uma instância do Application Object Server (AOS) para processamento automático.
author: matapg007
ms.date: 11/22/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: matgupta
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.search.form: BatchJob, SysRecurrence, BatchAlerts
ms.openlocfilehash: 06fb9a18e70c316be97645ba76f9462cd3ccc729
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9292440"
---
# <a name="create-a-batch-job"></a>Criar um trabalho em lotes

[!include [banner](../../includes/banner.md)]

Um trabalho em lotes é um grupo de tarefas que são enviadas para uma instância do Application Object Server (AOS) para processamento automático. Os trabalhos em lotes são executados usando as credenciais de segurança do usuário que criou o trabalho. Use o procedimento a seguir para criar um trabalho de lote. A empresa de dados demo usada para criar este procedimento é USMF.


## <a name="create-the-batch-job"></a>Criar o trabalho em lotes
1. Acesse **Painel de navegação > Módulos > Administração do sistema > Consultas > Trabalhos em lotes**.
2. Selecione **Novo**.
3. No campo **Descrição do trabalho**, insira uma descrição do trabalho em lotes.
4. No campo **Data/hora inicial agendada**, insira a data e a hora em que o trabalho em lotes deve ser executado.
5. Selecione **Salvar**.

## <a name="create-a-recurrence"></a>Criar uma recorrência
1. No Painel de Ação, selecione **Trabalho em lotes**.
2. Selecione **Recorrência**. Use estas opções para inserir um intervalo e um padrão para a recorrência.  
3. Selecione **OK**.

## <a name="add-alerts"></a>Adicionar alertas
1. No Painel de Ação, selecione **Trabalho em lotes**.
2. Selecione **Alertas**. Indique se você quer que mensagens de alertas sejam enviadas quando as extremidades do trabalho de grupo, tiverem um erro ou forem canceladas. Especifique então se você quer que os alertas indiquem como mensagens pop-up.   
3. Selecione **OK**.

## <a name="add-a-task-to-a-batch-job"></a>Adicionar uma tarefa para um trabalho em lotes
1.  Na página **Trabalho em lotes**, selecione **Exibir tarefas**.
2.  Selecione **Ctrl + N** para criar uma tarefa.
3.  Insira uma descrição da tarefa em lotes.
4.  No campo **Contas da empresa**, selecione o banco de dados da empresa em que a tarefa deve ser executada.
5.  No campo **Nome da classe**, selecione o processo que a tarefa deve executar. 
6.  Conforme apropriado, selecione um grupo de lotes para a tarefa.

    As tarefas de cliente devem ser atribuídas a um grupo de lotes. Elas são atribuídas automaticamente ao grupo de lotes padrão (também conhecido como Grupo de lotes vazio).

7.  Selecione **Ctrl + S** para salvar a tarefa.
8.  Para tornar a tarefa selecionada dependente de outra tarefa no trabalho, selecione a grade **Tem condições** e siga estas etapas para cada condição que você deseja definir:

    1. Selecione **Ctrl + N** para criar uma condição.
    2. Selecione a ID da tarefa na tarefa pai.
    3. Selecione o status que a tarefa pai deve alcançar antes que a tarefa dependente possa ser executada.
    4. Selecione **Ctrl + S** para salvar a condição.

    Se você definir mais de uma condição e se *todas* as condições tiverem que atendidas antes que a tarefa dependente possa ser executada, selecione o tipo de condição **Todos**. Se a tarefa dependente puder ser executada depois que *qualquer* uma das condições for atendida, selecione um tipo de condição **Qualquer**.

9.  Selecione como as falhas da tarefas devem ser tratadas. Para ignorar a falha de uma tarefa específica, na guia **Geral**, selecione a opção **Ignorar falha da tarefa** para essa tarefa. Se essa opção estiver selecionada, a falha da tarefa não causará falha do trabalho. Você também pode usar o campo **Número máximo de tentativas** para especificar o número de vezes que uma tarefa deve ser repetida antes que possa ser considerada como falha. Como uma melhor prática, recomendamos que você não defina o campo **Número máximo de tentativas** como um valor maior do que **5**.

    Para obter mais informações sobre tentativas em lotes, consulte [Habilitar tentativas em lotes](../retryable-batch.md).

## <a name="adjust-batch-job-status"></a>Ajuste o status de trabalho em lotes
1. Acesse **Administração do sistema > Consultas > Trabalhos em lotes**.
2. Selecione o trabalho em lotes apropriado.
3. No Painel de Ação, selecione **Trabalho em lotes > Funções > Alterar status**.
4. Selecione o status apropriado:
    - **Reter**: definir o trabalho em lotes como **reter** para que seja retido do agendador de trabalho em lotes. Equivalente a *parar*.
    - **Aguardar**: definir o trabalho em lotes como **aguardar** para que aguarde para ser retirado pelo agendador de trabalho em lotes. Equivalente a *ir*.
5. Selecione **OK**.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
