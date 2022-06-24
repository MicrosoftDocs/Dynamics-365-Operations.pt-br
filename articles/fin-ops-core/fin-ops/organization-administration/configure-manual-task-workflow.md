---
title: Configurar tarefas manuais em um fluxo de trabalho
description: Este artigo explica como configurar as propriedades de uma tarefa manual.
author: ChrisGarty
ms.date: 08/23/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: 192191
ms.assetid: 27f1afde-ff26-4b6f-8c11-27ec49130bbb
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 265f127f948aa7425c5eb523abe18986a942cfb0
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8889197"
---
# <a name="configure-manual-tasks-in-a-workflow"></a>Configurar tarefas manuais em um fluxo de trabalho

[!include [banner](../includes/banner.md)]


[!INCLUDE [PEAP](../../../includes/peap-1.md)]

Este artigo explica como configurar as propriedades de uma tarefa manual.

Para configurar uma tarefa manual no editor de fluxo de trabalho, clique com o botão direito do mouse na tarefa e clique em **Propriedades** para abrir a página **Propriedades**. Em seguida, use os procedimentos a seguir para configurar as propriedades da tarefa manual.

## <a name="name-the-task"></a>Nomear a tarefa

Siga estas etapas para inserir um nome para a tarefa manual.

1. No painel esquerdo, clique em **Configurações Básicas**.
2. No campo **Nome**, insira um nome exclusivo para a tarefa.

## <a name="enter-a-subject-line-and-instructions"></a>Inserir uma linha de assunto e instruções

Você deve fornecer uma linha de assunto e instruções para os usuários atribuídos à tarefa. Por exemplo, se você estiver configurando uma tarefa de requisições de compra, o usuário que foi atribuído à tarefa verá a linha de assunto e as instruções na página **Requisições de compra**. A linha de assunto aparece em uma barra de mensagens na página. O usuário poderá clicar no ícone na barra de mensagens para exibir as instruções. Siga estas etapas para inserir uma linha de assunto e instruções.

1. No painel esquerdo, clique em **Configurações Básicas**.
2. No campo **Assunto do item de trabalho**, insira a linha de assunto.
3. Para personalizar a linha de assunto, você pode inserir espaços reservados. Esses espaços reservados são substituídos pelos dados adequados quando a linha de assunto for exibida para os usuários. Siga estas etapas para inserir um espaço reservado:

    1. Na caixa de texto, clique no local onde o espaço reservado deve aparecer.
    2. Clique em **Inserir espaço reservado**.
    3. Na lista exibida, selecione o espaço reservado a ser inserido.
    4. Clique em **Inserir**.

4. Para adicionar traduções da linha de assunto, siga estas etapas:

    1. Clique em **Traduções**.
    2. Na página exibida, clique em **Adicionar**.
    3. Na lista exibida, selecione o idioma do texto que você está inserindo.
    4. No campo **Texto traduzido**, insira o texto.
    5. Para personalizar o texto, insira os espaços reservados conforme descrito na etapa 3.
    6. Clique em **Fechar**.

5. No campo **Instruções do item de trabalho**, insira as instruções.
6. Para personalizar as instruções, você pode inserir espaços reservados. Esses espaços reservados são substituídos pelos dados adequados quando as instruções são exibidas para os usuários. Siga estas etapas para inserir um espaço reservado:

    1. Na caixa de texto, clique no local onde o espaço reservado deve aparecer.
    2. Clique em **Inserir espaço reservado**.
    3. Na lista exibida, selecione o espaço reservado a ser inserido.
    4. Clique em **Inserir**.

7. Para adicionar traduções das instruções, siga estas etapas:

    1. Clique em **Traduções**.
    2. Na página exibida, clique em **Adicionar**.
    3. Na lista exibida, selecione o idioma do texto que você está inserindo.
    4. No campo **Texto traduzido**, insira o texto.
    5. Para personalizar o texto, insira os espaços reservados conforme descrito na etapa 6.
    6. Clique em **Fechar**.

## <a name="assign-the-task"></a>Atribuir a tarefa

Siga estas etapas para especificar a quem a tarefa manual deve ser atribuída.

1. No painel esquerdo, clique em **Atribuição**.
2. Na guia **Tipo de atribuição**, selecione uma das opções na tabela a seguir e execute as etapas adicionais dessa opção antes de passar para a etapa 3.

    <table>
    <thead>
    <tr>
    <th>Opção</th>
    <th>Usuários aos quais a tarefa será atribuída</th>
    <th>Etapas adicionais</th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td>Participante</td>
    <td>Usuários que foram atribuídos a uma função ou um grupo específico</td>
    <td>
    <ol>
    <li>Depois que você selecionar <strong>Participante</strong>, na guia <strong>Baseado em função</strong>, na lista <strong>Tipo de participante</strong>, selecione o tipo de grupo ou de função ao qual atribuir a tarefa.</li>
    <li>Na lista <strong>Participante</strong>, selecione o grupo ou a função ao qual atribuir a tarefa.</li>
    </ol>
    </td>
    </tr>
    <tr>
    <td>Hierarquia</td>
    <td>Usuários em uma hierarquia organizacional específica</td>
    <td>
    <ol>
    <li>Depois que você selecionar <strong>Hierarquia</strong>, na guia <strong>Seleção de hierarquia</strong>, na lista <strong>Tipo de hierarquia</strong>, selecione o tipo de hierarquia ao qual atribuir a tarefa.</li>
    <li>O sistema deve recuperar um intervalo de nomes de usuário da hierarquia. Esses nomes representam os usuários aos quais a tarefa pode ser atribuída. Siga estas etapas para especificar o ponto inicial e final do intervalo de nomes de usuário que o sistema recupera: <ol>
    <li>Para especificar o ponto de partida, selecione uma pessoa na lista <strong>Iniciar em</strong>.</li>
    <li>Para especificar o ponto final, clique em <strong>Adicionar condição</strong>. Em seguida, insira uma condição que determine em que ponto da hierarquia o sistema para de recuperar nomes.</li>
    </ol>
    </li>
    <li>Na guia <strong>Opções de hierarquia</strong>, especifique a quais usuários no intervalo a tarefa deve ser atribuída: <ul>
    <li><strong>Atribuir a todos os usuários recuperados</strong> – A tarefa é atribuída a todos os usuários do intervalo.</li>
    <li><strong>Atribuir somente ao último usuário recuperado</strong> – A tarefa é atribuída somente ao último usuário do intervalo.</li>
    <li><strong>Excluir usuários com a seguinte condição</strong> – A tarefa não é atribuída aos usuários do intervalo que atenderem a determinada condição. Clique em <strong>Adicionar condição</strong> para especificar a condição.</li>
    </ul>
    </li>
    </ol>
    </td>
    </tr>
    <tr>
    <td>Usuário de fluxo de trabalho</td>
    <td>Usuários no fluxo de trabalho atual</td>
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
    <li>A lista <strong>Usuários disponíveis</strong> inclui todos os usuários. Selecione os usuários aos quais deseja atribuir a tarefa e mova-os para a lista <strong>Usuários selecionados</strong>.</li>
    </ol>
    </td>
    </tr>
    <tr>
    <td>Fila</td>
    <td>Uma fila de itens de trabalho</td>
    <td>
    <ol>
    <li>Após selecionar <strong>Fila</strong>, clique na guia <strong>Fila baseada</strong>.</li>
    <li>Para atribuir a tarefa a uma fila específica, siga estas etapas: <ol>
    <li>Na lista <strong>Tipo de fila</strong>, selecione <strong>Fila de itens de trabalho</strong>.</li>
    <li>Na lista <strong>Nome da fila</strong>, selecione a fila.</li>
    </ol>
    </li>
    <li>Se uma condição específica tiver que determinar a qual fila atribuir a tarefa, siga estas etapas: <ol>
    <li>Na lista <strong>Tipo de fila</strong>, selecione <strong>Filas de itens de trabalho condicionais</strong>.</li>
    <li>Na lista <strong>Nome da fila</strong>, selecione <strong>Fila condicional</strong>.</li>
    </ol>
    </li>
    </ol>
    <blockquote>[!NOTE] Esta opção é usada apenas para alguns fluxos de trabalho, como Gerenciamento de casos.</blockquote>
    </td>
    </tr>
    </tbody>
    </table>

3. Na guia **Limite de tempo**, no campo **Duração**, especifique quanto tempo o usuário tem para concluir a tarefa. Selecione uma das seguintes opções:

    - **Horas** – Insira o número de horas que o usuário tem para concluir a tarefa. Selecione o calendário usado pela sua organização e insira informações sobre a semana de trabalho da organização.
    - **Dias** – Insira o número de dias que o usuário tem para concluir a tarefa. Selecione o calendário usado pela sua organização e insira informações sobre a semana de trabalho da organização.
    - **Semanas** – Insira o número de semanas que o usuário tem para concluir a tarefa.
    - **Meses** – Selecione o dia e a semana até quando o usuário deve concluir a tarefa. Por exemplo, você talvez você queira que o usuário conclua a tarefa até a sexta-feira da terceira semana do mês.
    - **Anos** – Selecione o dia, a semana e o mês até quando o usuário deve concluir a tarefa. Por exemplo, talvez você queira que o usuário conclua a tarefa até a sexta-feira da terceira semana de dezembro.

    Se o usuário não concluir a tarefa no tempo alocado, a tarefa vencerá. Uma tarefa vencida poderá ser escalonada, com base nas opções selecionadas na área **Escalonamento** da página.

## <a name="specify-what-happens-when-the-task-is-overdue"></a>Especificar o que acontece quando a tarefa está vencida

Se um usuário não concluir a tarefa manual no tempo alocado, a tarefa vencerá. Uma tarefa vencida pode ser escalonada ou atribuída automaticamente a outro usuário. Siga estas etapas para escalonar a tarefa se ela estiver vencida.

1. No painel esquerdo, clique em **Escalonamento**.
2. Marque a caixa de seleção **Usar caminho de escalonamento** para criar um caminho de escalonamento. O sistema atribuirá automaticamente a tarefa aos usuários listados no caminho de escalonamento. Por exemplo, a tabela a seguir representa um caminho de escalonamento.

    | Sequência | Caminho de escalonamento      |
    |----------|----------------------|
    | 1        | Atribuir a: Denise     |
    | 2        | Atribuir a: Eduardo      |
    | 3        | Ação final: Rejeitar |

    Nesse exemplo, o sistema atribui a tarefa vencida à Denise. Se a Denise não concluir a tarefa no tempo alocado, o sistema a atribuirá a Eduardo. Se Eduardo não concluir a tarefa no tempo alocado, o sistema rejeitará o documento enviado para processamento.

3. Para adicionar um usuário ao caminho de escalonamento, clique em **Adicionar escalonamento**. Na guia **Tipo de atribuição**, selecione uma das opções na tabela a seguir e execute as etapas adicionais dessa opção antes de passar para a etapa 4.

    <table>
    <thead>
    <tr>
    <th>Opção</th>
    <th>Usuários aos quais a tarefa será escalonada</th>
    <th>Etapas adicionais</th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td>Hierarquia</td>
    <td>Usuários em uma hierarquia organizacional específica</td>
    <td>
    <ol>
    <li>Depois que você selecionar <strong>Hierarquia</strong>, na guia <strong>Seleção de hierarquia</strong>, na lista <strong>Tipo de hierarquia</strong>, selecione o tipo de hierarquia ao qual a tarefa será escalonada.</li>
    <li>O sistema deve recuperar um intervalo de nomes de usuário da hierarquia. Esses nomes representam os usuários aos quais a tarefa pode ser escalonada. Siga estas etapas para especificar o ponto inicial e final do intervalo de nomes de usuário que o sistema recupera: <ol>
    <li>Para especificar o ponto de partida, selecione uma pessoa na lista <strong>Iniciar em</strong>.</li>
    <li>Para especificar o ponto final, clique em <strong>Adicionar condição</strong>. Em seguida, insira uma condição que determine em que ponto da hierarquia o sistema para de recuperar nomes.</li>
    </ol>
    </li>
    <li>Na guia <strong>Opções de hierarquia</strong>, especifique a quais usuários no intervalo a tarefa deve ser escalonada: <ul>
    <li><strong>Atribuir a todos os usuários recuperados</strong> – A tarefa é escalonada a todos os usuários do intervalo.</li>
    <li><strong>Atribuir somente ao último usuário recuperado</strong> – A tarefa é escalonada somente ao último usuário do intervalo.</li>
    <li><strong>Excluir usuários com a seguinte condição</strong> – Esta tarefa não é escalonada aos usuários do intervalo que atenderem a determinada condição. Clique em <strong>Adicionar condição</strong> para especificar a condição.</li>
    </ul>
    </li>
    </ol>
    </td>
    </tr>
    <tr>
    <td>Usuário de fluxo de trabalho</td>
    <td>Usuários no fluxo de trabalho atual</td>
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
    <li>A lista <strong>Usuários disponíveis</strong> inclui todos os usuários. Selecione os usuários aos quais escalonar a tarefa e mova-os para a lista <strong>Usuários selecionados</strong>.</li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

4. Na guia **Limite de tempo**, no campo **Duração**, especifique quanto tempo o usuário tem para concluir a tarefa. Selecione uma das seguintes opções:

    - **Horas** – Insira o número de horas que o usuário tem para concluir a tarefa. Selecione o calendário usado pela sua organização e insira informações sobre a semana de trabalho da organização.
    - **Dias** – Insira o número de dias que o usuário tem para concluir a tarefa. Selecione o calendário usado pela sua organização e insira informações sobre a semana de trabalho da organização.
    - **Semanas** – Insira o número de semanas que o usuário tem para concluir a tarefa.
    - **Meses** – Selecione o dia e a semana até quando o usuário deve concluir a tarefa. Por exemplo, você talvez você queira que o usuário conclua a tarefa até a sexta-feira da terceira semana do mês.
    - **Anos** – Selecione o dia, a semana e o mês até quando o usuário deve concluir a tarefa. Por exemplo, talvez você queira que o usuário conclua a tarefa até a sexta-feira da terceira semana de dezembro.

5. Repita as etapas de 3 a 4 para cada usuário que deve ser adicionado ao caminho de escalonamento. Você pode alterar a ordem dos usuários.
6. Se os usuários no caminho de escalonamento não concluírem a tarefa no tempo alocado, o sistema executará uma ação na tarefa. Para especificar a ação que o sistema executará, selecione a linha **Ação** e, na guia **Encerrar ação**, selecione uma ação.

## <a name="specify-when-the-system-automatically-acts-on-the-task"></a>Especificar quando o sistema deve executar automaticamente uma ação na tarefa

Você pode configurar o sistema para executar uma ação na tarefa manual se condições específicas forem atendidas. Por exemplo, uma tarefa requer que um membro do departamento de relatórios de despesas revise os recibos que são enviados com um relatório de despesas. De acordo com a política da empresa, essa tarefa deverá ser executada se o valor total do relatório de despesas for superior a US$ 100. Nesse cenário, você pode configurar o sistema para marcar automaticamente a tarefa como **Concluída** quando o valor total for inferior a 100. Siga estas etapas para especificar quando o sistema executará uma ação na tarefa manual.

1. No painel esquerdo, clique em **Ações automáticas**.
2. Marque a caixa de seleção **Habilitar ações automáticas**.
3. Clique em **Adicionar condição**.
4. Insira uma condição.
5. Insira quaisquer condições adicionais necessárias.
6. Para verificar se as condições inseridas foram configuradas corretamente, execute estas etapas:

    1. Clique em **Teste**.
    2. Na página **Testar condição de fluxo de trabalho**, na área **Validar condição**, selecione um registro.
    3. Clique em **Teste**. O sistema avaliará o registro para determinar se ele atende às condições definidas.
    4. Clique em **OK** ou **Cancelar** para retornar à página **Propriedades**.

7. Na lista **Ação de autocompletar**, selecione a ação que o sistema deve executar na tarefa.

## <a name="specify-when-notifications-are-sent"></a>Especificar quando enviar notificações

Você poderá enviar notificações às pessoas quando uma tarefa manual for delegada, escalonada, concluída ou rejeitada, ou quando uma alteração for solicitada. Siga estas etapas para especificar quando enviar notificações e a quem elas devem ser enviadas.

1. No painel esquerdo, clique em **Notificações**.
2. Marque a caixa de seleção ao lado dos eventos para os quais as notificações devem ser enviadas:

    - **Delegar** – A tarefa foi atribuída a outro usuário.
    - **Escalonar** – O usuário atribuído não concluiu a tarefa no tempo alocado.
    - **Concluída** – O usuário atribuído concluiu a tarefa.
    - **Rejeitar** – O usuário atribuído rejeitou o documento enviado.
    - **Solicitar alteração** – O usuário atribuído solicitou uma alteração no documento enviado.

3. Selecione a linha de um evento que você selecionou na etapa 2.
4. Na guia **Texto da notificação**, insira o texto da notificação na caixa de texto.
5. Para personalizar a notificação, você poderá inserir espaços reservados. Os espaços reservados são substituídos pelas informações adequadas quando a notificação é exibida para os usuários. Siga estas etapas para inserir um espaço reservado:

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
    <td>Usuários no fluxo de trabalho atual</td>
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

## <a name="set-a-time-limit"></a>Definir um limite de tempo

Siga estas etapas se a tarefa manual tiver que ser concluída em um horário específico.

> [!NOTE]
> As opções selecionadas neste procedimento substituirão as que você selecionou nas áreas **Atribuição** e **Escalonamento** da página.

1. No painel esquerdo, clique em **Configurações avançadas**.
2. Marque a caixa de seleção **Definir um limite de tempo para o elemento de fluxo de trabalho**.
3. No campo **Duração**, especifique quando a tarefa deve ser concluída. Selecione uma das seguintes opções:

    - **Horas** – Insira o número de Horas em que a tarefa deve ser concluída. Selecione o calendário usado pela sua organização e insira informações sobre a semana de trabalho da organização.
    - **Dias** – Insira o número de dias em que a tarefa deve ser concluída. Selecione o calendário usado pela sua organização e insira informações sobre a semana de trabalho da organização.
    - **Semanas** – Insira o número de semanas em que a tarefa deve ser concluída.
    - **Meses** – Selecione o dia e a semana até quando a tarefa deve ser concluída. Por exemplo, você talvez queira que a tarefa seja concluída até a sexta-feira da terceira semana do mês.
    - **Anos** – Selecione o dia, a semana e o mês até quando a tarefa deve ser concluída. Por exemplo, talvez você queira que a tarefa seja concluída até a sexta-feira da terceira semana de dezembro.

4. Se o limite de tempo for excedido, o sistema executará uma ação na tarefa. Na lista **Ação**, selecione a ação que o sistema deve executar.

## <a name="specify-which-actions-are-available-to-the-user"></a>Especificar quais ações estarão disponíveis para o usuário

Quando a tarefa manual for atribuída a um usuário, este deverá executar uma ação nessa tarefa. Siga estas etapas para especificar quais ações o usuário pode executar na tarefa

> [!NOTE]
> As ações disponíveis variam de acordo com o design da tarefa.

1. No painel esquerdo, clique em **Configurações avançadas**.
2. Marque a caixa de seleção **Concluída** se o usuário puder marcar a tarefa como **Concluída**.
3. Marque a caixa de seleção **Rejeitar** se o usuário puder rejeitar o documento enviado.
4. Marque a caixa de seleção **Solicitar alteração** se o usuário puder solicitar alterações no documento que foi enviado.
5. Marque a caixa de seleção **Delegar** se o usuário puder atribuir a tarefa a outro usuário.
6. Marque a caixa de seleção **Reatribuir** se o usuário puder reatribuir a tarefa a outro usuário na fila de itens de trabalho.
7. Marque a caixa de seleção **Liberar** se o usuário puder reatribuir a tarefa na fila de itens de trabalho. Assim, outro usuário poderá concluir a tarefa.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]