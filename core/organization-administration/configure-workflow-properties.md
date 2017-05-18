---
title: Configurar as propriedades de um fluxo de trabalho
description: "Este tópico explica como configurar as várias propriedades de um fluxo de trabalho."
author: sericks007
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 196083
ms.assetid: 192b7a98-7d04-4c7a-a986-29d797a8a837
ms.search.region: Global
ms.author: donaldc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: 6c44ba2771bab0bc428c0c348a6c34c2deb0be26
ms.contentlocale: pt-br
ms.lasthandoff: 04/25/2017


---

# <a name="configure-the-properties-of-a-workflow"></a>Configurar as propriedades de um fluxo de trabalho

[!include[banner](../includes/banner.md)]


Este tópico explica como configurar as várias propriedades de um fluxo de trabalho.

Para configurar as propriedades de um fluxo de trabalho, abra o fluxo de trabalho no editor. Clique na tela do editor de fluxo de trabalho e clique em **Propriedades** para abrir a página **Propriedades**. Em seguida, use os procedimentos a seguir para configurar as várias propriedades do fluxo de trabalho.

## <a name="name-the-workflow"></a>Nomear o fluxo de trabalho
Siga as etapas abaixo para inserir um nome para o fluxo de trabalho.

1.  No painel esquerdo, clique em **Configurações Básicas**.
2.  No campo **Nome**, insira um nome exclusivo para o fluxo de trabalho. Por exemplo, se você criar um fluxo de trabalho de requisição de compra para cada país/região onde opera, poderá nomear um fluxo de trabalho como **Requisições de Compra - Dinamarca** ou **Requisições de Compra - Espanha**.

## <a name="specify-the-workflow-owner"></a>Especificar o proprietário do fluxo de trabalho
O proprietário do fluxo de trabalho é a pessoa que gerencia e mantém o fluxo de trabalho. Siga estas etapas para especificar o proprietário do fluxo de trabalho.

1.  No painel esquerdo, clique em **Configurações Básicas**.
2.  Na lista **Proprietário**, selecione o nome da pessoa que gerenciará o fluxo de trabalho.

## <a name="select-an-email-template"></a>Selecionar um modelo de email
Siga estas etapas para selecionar o modelo de email que será usado para gerar mensagens de notificação sobre o fluxo de trabalho.

1.  No painel esquerdo, clique em **Configurações Básicas**.
2.  Na lista **Modelo de email para notificações de fluxo de trabalho**, selecione o modelo.

## <a name="enter-instructions-for-users"></a>Inserir instruções para os usuários
Você pode fornecer instruções aos usuários que enviarão documentos para processamento e aprovação. Esses usuários também são conhecidos como *originadores*. Por exemplo, suponha que você esteja criando um fluxo de trabalho de requisição de compra e insira instruções. Essas instruções fornecidas poderão ser exibidas pelos usuários que inserirem requisições de compra na página **Requisições de compra**. Para exibir instruções, o originador clica no ícone na barra de mensagens de fluxo de trabalho. Siga estas etapas para inserir instruções para os usuários.

1.  No painel esquerdo, clique em **Configurações Básicas**.
2.  No campo **Enviar instruções**, insira as instruções.
3.  Para personalizar as instruções, você pode inserir espaços reservados. Os espaços reservados são substituídos pelos dados adequados quando as instruções são exibidas para os usuários. Para inserir um espaço reservado, siga estas etapas:
    1.  Clique no campo **Instruções de envio** para especificar onde o espaço reservado deve aparecer.
    2.  Clique em **Inserir espaço reservado**.
    3.  Na lista exibida, selecione o espaço reservado a ser inserido.
    4.  Clique em **Inserir**.

4.  Para adicionar traduções das instruções, siga estas etapas:
    1.  Clique em **Traduções**.
    2.  Na página exibida, clique em **Adicionar**.
    3.  Na lista exibida, selecione o idioma do texto que você inserirá.
    4.  No campo **Texto traduzido**, insira o texto.
    5.  Para personalizar o texto, você poderá inserir espaços reservados. Para obter instruções sobre como inserir um espaço reservado, consulte a etapa 3.
    6.  Clique em **Fechar**.

## <a name="specify-when-this-workflow-is-used"></a>Especificar quando esse fluxo de trabalho será usado
Você pode criar vários fluxos de trabalho baseados no mesmo tipo. Por exemplo, você pode criar um fluxo de trabalho de requisição de compra para cada país/região onde opera, como Requisições de Compra - Dinamarca e Requisições de Compra - Espanha. Se houver vários fluxos de trabalho baseados no mesmo tipo, será necessário especificar quando cada um deles será usado. No exemplo anterior, especifique as seguintes condições:

-   As Requisições de Compra - Dinamarca são usadas quando: país/região = DK
-   As Requisições de Compra - Espanha são usadas quando: país/região = DK

Siga estas etapas para especificar quando o fluxo de trabalho que você está configurando será usado.

1.  No painel esquerdo, clique em **Ativação**.
2.  Marque a caixa de seleção **Definir as condições para executar este fluxo de trabalho**.
3.  Clique em **Adicionar condição**.
4.  Insira uma condição.
5.  Insira quaisquer condições adicionais necessárias.
6.  Para verificar se as condições inseridas foram definidas corretamente, execute estas etapas:
    1.  Clique em **Teste**.
    2.  Na página **Testar condição de fluxo de trabalho**, na área **Validar condição**, selecione um registro.
    3.  Clique em **Teste**. O sistema avaliará o registro para determinar se ele atende às condições especificadas. Por exemplo, se você estiver criando um fluxo de trabalho de requisição de compra para a Espanha, a área **Validar condição** da página exibirá uma lista de requisições de compra. Quando você clicar em **Testar**, o sistema avaliará a requisição de compra selecionada para determinar se o país/região é ES.
    4.  Clique em **OK** ou **Cancelar** para retornar à página **Propriedades**.

## <a name="specify-when-notifications-are-sent"></a>Especificar quando enviar notificações
Quando um documento é enviado para processamento, é criada uma instância do fluxo de trabalho. Você poderá enviar notificações para os usuários quando instâncias baseadas nesse fluxo de trabalho forem iniciadas, concluídas, encerradas ou interrompidas devido a um erro. Siga estas etapas para especificar quando as notificações serão enviadas.

1.  No painel esquerdo, clique em **Notificações**.
2.  Marque a caixa de seleção para cada evento que disparará notificações:
    -   **Iniciado**– Enviar notificações quando uma instância de fluxo de trabalho for iniciada.
    -   **Parado** – Enviar notificações quando uma instância de fluxo de trabalho for interrompida devido a um erro.
    -   **Concluído** – Enviar notificações quando uma instância de fluxo de trabalho for concluída.
    -   **Irrecuperável** – Enviar notificações quando uma instância de fluxo de trabalho for interrompida devido a um erro irrecuperável.
    -   **Encerrado** – Enviar notificações quando uma instância de fluxo de trabalho for encerrada.

3.  Selecione a linha de um evento que você selecionou na etapa 2.
4.  Na guia **Texto da notificação**, insira o texto da notificação.
5.  Para personalizar o texto, você poderá inserir espaços reservados. Esses espaços reservados são substituídos pelos dados adequados quando o texto é exibido para os usuários. Para inserir um espaço reservado, siga estas etapas:
    1.  Clique no campo para especificar onde o espaço reservado deve aparecer.
    2.  Clique em **Inserir espaço reservado**.
    3.  Na lista exibida, selecione o espaço reservado a ser inserido.
    4.  Clique em **Inserir**.

6.  Para adicionar traduções do texto, siga estas etapas:
    1.  Clique em **Traduções**.
    2.  Na página exibida, clique em **Adicionar**.
    3.  Na lista exibida, selecione o idioma do texto que você inserirá.
    4.  No campo **Texto traduzido**, insira o texto.
    5.  Para personalizar o texto, você poderá inserir espaços reservados. Para obter instruções sobre como inserir um espaço reservado, consulte a etapa 5.
    6.  Clique em **Fechar**.

7.  Na guia **Destinatário**, use as seguintes opções para especificar quem deverá receber as notificações.
    <table>
    <colgroup>
    <col width="33%" />
    <col width="33%" />
    <col width="33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Opção</th>
    <th>As notificações são enviadas a esses usuários</th>
    <th>Para enviar notificações, siga estas etapas</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>Participante</td>
    <td>Usuários que foram atribuídos a uma função ou um grupo específico</td>
    <td><ol>
    <li>Na guia <strong>Destinatário</strong>, clique em <strong>Participante</strong>.</li>
    <li>Na guia <strong>Baseado em função</strong>, na lista <strong>Tipo de participante</strong>, selecione o tipo de grupo ou de função ao qual serão enviadas notificações.</li>
    <li>Na lista <strong>Participante</strong>, selecione o grupo ou a função ao qual serão enviadas notificações.</li>
    </ol></td>
    </tr>
    <tr class="even">
    <td>Usuário de fluxo de trabalho</td>
    <td>Usuários participantes desse fluxo de trabalho</td>
    <td><ol>
    <li>Na guia <strong>Destinatário</strong>, clique em <strong>Usuário de fluxo de trabalho</strong>.</li>
    <li>Na guia <strong>Usuário de fluxo de trabalho</strong>, na lista <strong>Usuário de fluxo de trabalho</strong>, selecione um participante desse fluxo.</li>
    </ol></td>
    </tr>
    <tr class="odd">
    <td>Usuário</td>
    <td>Especificar usuários do Dynamics 365 for Operations</td>
    <td><ol>
    <li>Na guia <strong>Destinatário</strong>, clique em <strong>Usuário</strong>.</li>
    <li>Na guia <strong>Usuário</strong>, a lista <strong>Usuários disponíveis</strong> inclui todos os usuários do Dynamics 365 for Operations. Selecione os usuários aos quais enviar notificações e mova- os para a lista <strong>Usuários selecionados</strong>.</li>
    </ol></td>
    </tr>
    </tbody>
    </table>

8.  Repita as etapas de 3 a 7 para cada evento selecionado na etapa 2.

## <a name="enter-comments-about-the-changes-that-you-made-to-the-workflow"></a>Insira comentários sobre as alterações feitas no fluxo de trabalho
Para inserir comentários sobre as alterações feitas no fluxo de trabalho, siga as etapas abaixo.

1.  No painel esquerdo, clique em **Observações**.
2.  No campo **Inserir comentários sobre o fluxo de trabalho**, insira seus comentários.
3.  Revise seus comentários. Depois que você adicionar comentários, não poderá modificá-los.
4.  Clique em **Adicionar** para adicionar comentários à área **Histórico de comentários**.





