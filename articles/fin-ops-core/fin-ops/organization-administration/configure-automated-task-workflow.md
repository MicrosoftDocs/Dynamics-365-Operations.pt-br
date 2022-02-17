---
title: Configurar tarefas automatizadas em um fluxo de trabalho
description: Este tópico explica como configurar as propriedades de uma tarefa automatizada.
author: ChrisGarty
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: 192061
ms.assetid: c0aceb57-b5e6-4ef3-91e7-89a21c9f048a
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c7346649108824eb4e7209a2476456a469affa1c
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8066509"
---
# <a name="configure-automated-tasks-in-a-workflow"></a>Configurar tarefas automatizadas em um fluxo de trabalho

[!include [banner](../includes/banner.md)]


[!INCLUDE [PEAP](../../../includes/peap-1.md)]

Este tópico explica como configurar as propriedades de uma tarefa automatizada.

Para configurar uma tarefa automatizada no editor de fluxo de trabalho, clique com o botão direito do mouse na tarefa e clique em **Propriedades** para abrir a página **Propriedades**. Em seguida, use os procedimentos a seguir para configurar as propriedades da tarefa automatizada.

## <a name="name-the-task"></a>Nomear a tarefa

Siga estas etapas para inserir um nome para a tarefa automatizada.

1. No painel esquerdo, clique em **Configurações Básicas**.
2. No campo **Nome**, insira um nome exclusivo para a tarefa.

## <a name="specify-when-notifications-are-sent"></a>Especificar quando enviar notificações

É possível enviar notificações às pessoas quando uma tarefa automatizada tiver sido executada ou cancelada. Siga estas etapas para especificar quando as notificações são enviadas, e a quem são enviadas.

1. No painel esquerdo, clique em **Notificações**.
2. Marque a caixa de seleção ao lado dos eventos para os quais enviar notificações:

    - **Execução** – as notificações são enviadas quando a tarefa tiver sido executada.
    - **Cancelada** – as notificações são enviadas quando a tarefa tiver sido cancelada.

3. Selecione a linha de um evento que você selecionou na etapa 2.
4. Na guia **Texto da notificação**, insira o texto da notificação na caixa de texto.
5. Para personalizar a notificação, você poderá inserir espaços reservados. Esses espaços reservados são substituídos pelos dados adequados quando a notificação é exibida para os usuários. Siga estas etapas para inserir um espaço reservado:

    1. Na caixa de texto, clique no local onde o espaço reservado deve aparecer.
    2. Clique em **Inserir espaço reservado**.
    3. Na lista exibida, selecione o espaço reservado a ser inserido.
    4. Clique em **Inserir**.

6. Para adicionar traduções da notificação, siga estas etapas:

    1. Clique em **Traduções**.
    2. Na página exibida, clique em **Adicionar**.
    3. Na lista exibida, selecione o idioma do texto que você está inserindo.
    4. No campo **Texto traduzido**, insira o texto.
    5. Para personalizar o texto, insira os espaços reservados conforme descrito na etapa 5.
    6. Clique em **Fechar**.

7. Na guia **Destinatário**, especifique para quem as notificações serão enviadas. Selecione uma das opções na tabela a seguir e execute as etapas adicionais dessa opção antes de passar para a etapa 8.

    <table>
    <thead>
    <tr>
    <th>Opção</th>
    <th>Destinatários da notificação</th>
    <th>Etapas adicionais</th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td>Participante</td>
    <td>Usuários que foram atribuídos a uma função ou um grupo específico</td>
    <td>
    <ol>
    <li>Depois que você selecionar <strong>Participante</strong>, na guia <strong>Baseado em função</strong>, na lista <strong>Tipo de participante</strong>, selecione o tipo de grupo ou de função ao qual enviar notificações.</li>
    <li>Na lista <strong>Participante</strong>, selecione o grupo ou a função ao qual serão enviadas notificações.</li>
    </ol>
    </td>
    </tr>
    <tr>
    <td>Usuário de fluxo de trabalho</td>
    <td>Usuários que participam do fluxo de trabalho atual</td>
    <td>
    <ul>
    <li>Depois que você selecionar <strong>Usuário de fluxo de trabalho</strong> na guia <strong>Usuário de fluxo de trabalho</strong>, na lista <strong>Usuário de fluxo de trabalho</strong>, selecione um usuário que participa do fluxo de trabalho.</li>
    </ul>
    </td>
    </tr>
    <tr>
    <td>Usuário</td>
    <td>Usuários específicos</td>
    <td>
    <ol>
    <li>Após selecionar <strong>Usuário</strong>, clique na guia <strong>Usuário</strong>.</li>
    <li>A lista <strong>Usuários disponíveis</strong> inclui todos os usuários. Selecione os usuários aos quais enviar notificações e mova- os para a lista <strong>Usuários selecionados</strong>.</li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

8. Repita as etapas de 3 a 7 para cada evento selecionado na etapa 2.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]