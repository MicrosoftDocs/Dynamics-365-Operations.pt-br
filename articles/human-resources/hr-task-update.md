---
title: Configurar tarefas no Gerenciamento de tarefas
description: Este artigo explica como configurar tarefas no Gerenciamento de tarefas no Microsoft Dynamics 365 Human Resources.
author: twheeloc
ms.date: 10/12/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2022-06-09
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 6a38cc2e36c24ddbfe0d8b2886301c108599ab25
ms.sourcegitcommit: 55e440e30490b2d36d86b22aa1263d5da97633aa
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2022
ms.locfileid: "9745380"
---
# <a name="set-up-tasks-in-task-management"></a>Configurar tarefas no Gerenciamento de tarefas

[!INCLUDE [PEAP](../includes/peap-1.md)]

Em versões do Microsoft Dynamics 365 Human Resources antes da versão 10.0.30, os usuários que desejam editar uma tarefa tinham que editá-la individualmente em cada lista de verificação contida nela. No entanto, a partir versão 10.0.30 do Human Resources, os usuários podem selecionar como as tarefas editadas são manipuladas. Se uma tarefa que está sendo editada estiver em uma lista de verificação, a opção **Habilitar upgrade de gerenciamento de tarefas** deverá estar selecionada na guia **Gerenciamento de tarefas** da página **Parâmetros compartilhados de recursos humanos** para habilitar a lista de verificação para usar a tarefa editada.

[![Opção Habilitar upgrade de gerenciamento de tarefas na página de parâmetros compartilhados de Recursos humanos.](./media/task-update.png)](./media/task-update.png)

Se as edições nas tarefas tiverem de ser aplicadas a todas as tarefas de lista de verificação, um relacionamento deverá existir entre a tarefa na biblioteca de tarefas e a tarefa na lista de verificação. Uma opção foi adicionada para criar o relacionamento entre a tarefa da biblioteca e a tarefa da lista de verificação.

Você pode criar tarefas individualmente e reutilizá-las em várias listas de verificação. Para criar uma tarefa, na página **Configuração de integração**, na guia **Tarefas**, selecione **Novo**.

## <a name="set-up-tasks"></a>Configurar tarefas

Para atribuir uma tarefa criada a várias listas de verificação selecione a tarefa e, em seguida, escolha **Aplicar às listas de verificação** no menu.

Como alternativa, você pode adicionar tarefas diretamente a uma lista de verificação. Para adicionar uma tarefa a uma lista de verificação, na página **Configuração de integração**, na guia **Lista de verificação**, crie uma nova lista de verificação para adicionar a tarefa, ou adicione a tarefa a uma lista de verificação existente.

Para editar uma tarefa da biblioteca, selecione **Editar** no menu biblioteca de tarefas. Se a tarefa estiver associada a quaisquer listas de verificação, essas listas de verificação serão mostradas na página **Editar tarefa**. Se desejar que as tarefas em qualquer listas de verificação sejam atualizadas com as edições, selecione as listas de verificação na seção **Aplicar às listas de verificação**.

Para excluir tarefas da biblioteca de tarefas, selecione a opção **Excluir**. Se a tarefa estiver associada a uma lista de verificação, esta ação não excluirá a tarefa da lista de verificação. É necessária uma ação separada para remover uma tarefa de uma lista de verificação.

### <a name="set-up-checklists"></a>Configurar listas de verificação

Uma lista de verificação é um grupo de tarefas. É possível criar tantas listas de verificação quanto forem necessárias, e você pode atribuir as mesmas tarefas a várias listas de verificação. Ao criar uma lista de verificação, especifique um proprietário e um calendário.

Para criar uma nova tarefa em uma lista de verificação, selecione **Novo** na barra de menu da tarefa. Ao criar uma nova tarefa, você pode adicionar a tarefa à biblioteca de tarefas, de forma que ela possa ser compartilhada entre várias listas de verificação. Para adicionar a tarefa à biblioteca de tarefas, você deve definir a opção **Aplicar tarefa à biblioteca** como **Sim**. Se você optar por adicionar a tarefa à biblioteca de tarefas, também poderá adicioná-la a outras listas de verificação ao mesmo tempo, selecionando essas listas de verificação na seção **Aplicar às listas de verificação**. Se você optar por não adicionar a tarefa à biblioteca de tarefas, ela só existirá na lista de verificação em que você a criar.

Para editar uma tarefa em uma lista de verificação, selecione **Editar** no menu de tarefas. Se a tarefa estiver associada a quaisquer listas de verificação, essas listas de verificação serão mostradas na página **Editar tarefa**. Se quiser que as tarefas em qualquer uma das outras listas de verificação sejam atualizadas com as edições, selecione as listas de verificação na seção **Aplicar às listas de verificação**.

Para remover tarefas de uma lista de verificação, selecione **Remover**. Esta ação removerá as tarefas da lista de verificação. No entanto, não as excluirá das tarefas da biblioteca de tarefas. Para excluir tarefas da biblioteca de tarefas, abra a página **Biblioteca de tarefas** e selecione **Excluir**.
