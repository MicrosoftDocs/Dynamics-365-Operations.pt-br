---
title: Diagnóstico de segurança de gravações de tarefas
description: Este tópico fornece informações sobre como analisar e gerenciar requisitos de permissão de segurança com base em uma gravação de tarefas.
author: Peakerbl
ms.date: 05/05/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: ''
ms.dyn365.ops.version: Version 10.0.9
ms.openlocfilehash: cb4d544d8d74ad10432901381253f84ec9331ae7
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5745756"
---
# <a name="security-diagnostics-for-task-recordings"></a>Diagnóstico de segurança de gravações de tarefas

[!include [banner](../../includes/banner.md)]

## <a name="before-you-begin"></a>Antes de começar

Este tópico fornece informações sobre como analisar e gerenciar requisitos de permissão de segurança com base em uma gravação de tarefas. Antes de concluir as etapas deste tópico, você deve ter uma gravação de tarefa do processo comercial que deseja analisar. Para registrar um processo comercial, consulte [Recursos do gravador de tarefas](../../user-interface/task-recorder.md). 

## <a name="manage-security-for-a-task-recording"></a>Gerenciar a segurança de um registro de tarefa

1. Vá para **Administração do sistema** > **Segurança** > **Diagnóstico de segurança para registro de tarefa**.
2. Abra o registro de tarefa a partir da localização. Selecione **Abrir neste PC** ou **Abrir a partir do Lifecycle Services** e selecione **Fechar**.
3. Isso abrirá a página **Detalhes do item de menu segurança** que lista os objetos de segurança necessários para o processo.

 > [!NOTE]
 > Os itens de menu **Ação** e **Saída** não estão incluídos na lista.

4. No campo **ID de usuário**, selecione um usuário. Se o usuário não tiver permissões para alguns itens de menu, o campo **Permissões ausentes** será atualizado para **Sim**.
  
  ![Página de detalhes do item de menu de segurança](../media/Security-Menu-Item-Details.png)

5. Selecione **Adicionar referência** para ver uma lista dos objetos de segurança, incluindo as funções, as obrigações e os privilégios que concedem a permissão ausente.
6. Selecione um objeto de segurança na lista:

    - Se a **função** for selecionada, selecione **Adicionar função ao usuário**. Isso abrirá a página **Atribuir usuários a funções**. Para obter mais informações, consulte a página [Atribuir usuários a funções de segurança](assign-users-security-roles.md).
    - Se **Obrigação** estiver selecionado, selecione **Adicionar obrigação à função**, selecione as funções às quais o imposto deve ser adicionado e, em seguida, selecione **OK**.
    - Se **Privilégio** estiver selecionado, selecione **Adicionar privilégio a obrigações**, selecione as funções às quais o imposto deve ser adicionado e, em seguida, selecione **OK**.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]