---
title: Configurar decisões manuais em um fluxo de trabalho
description: Este tópico explica como configurar as propriedades de uma decisão manual.
author: ChrisGarty
manager: AnnBe
ms.date: 06/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 192101
ms.assetid: 0bccad77-1a44-4f08-967b-12c62c02afc7
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 859e74b869fcf9b8a886f27f67f51bdf28819979
ms.sourcegitcommit: e55efd2f62bf60f678108c09ad4701a76b20cc68
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/17/2020
ms.locfileid: "3698234"
---
# <a name="configure-manual-decisions-in-a-workflow"></a>Configurar decisões manuais em um fluxo de trabalho

[!include [banner](../includes/banner.md)]

Este tópico explica como configurar as propriedades de uma decisão manual.

Para configurar uma decisão manual no editor de fluxo de trabalho, clique com o botão direito do mouse na decisão manual e clique em **Propriedades** para abrir a página **Propriedades**. Em seguida, use os procedimentos a seguir para configurar as propriedades da decisão manual.

## <a name="name-the-decision"></a>Nomear a decisão

Siga estas etapas para inserir um nome para a decisão manual.

1. No painel esquerdo, clique em **Configurações Básicas**.
2. No campo **Nome**, insira um nome exclusivo para a decisão manual.

## <a name="enter-a-subject-line-and-instructions"></a>Inserir uma linha de assunto e instruções

Você deve fornecer uma linha de assunto e instruções para os usuários atribuídos à decisão manual. Por exemplo, se você estiver configurando uma decisão de requisições de compra, o usuário que foi atribuído à decisão verá a linha de assunto e as instruções na página **Requisições de compra**. A linha de assunto aparece em uma barra de mensagens na página. O usuário poderá clicar no ícone na barra de mensagens para exibir as instruções. Siga estas etapas para inserir uma linha de assunto e instruções.

1. No painel esquerdo, clique em **Configurações Básicas**.
2. Na guia **Instruções**, no campo **Assunto do item de trabalho**, insira a linha de assunto.
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

## <a name="specify-the-possible-outcomes-of-a-decision"></a>Especificar os possíveis resultados de uma decisão

Geralmente, quando um documento é atribuído a um tomador de decisão, uma pergunta é feita a ele. A resposta para essa pergunta normalmente é **Sim** ou **Não**, ou **Verdadeiro** ou **Falso**. Siga estas etapas para especificar os possíveis resultados de decisão manual.

1. No painel esquerdo, clique em **Configurações Básicas**.
2. Na guia **Resultados**, no campo **Resultado 1**, insira o nome do resultado ou a opção.
3. Para adicionar traduções do resultado, siga estas etapas:

    1. Clique em **Traduções**.
    2. Na página exibida, clique em **Adicionar**.
    3. Na lista exibida, selecione o idioma do texto que você está inserindo.
    4. No campo **Texto traduzido**, insira o texto.
    5. Clique em **Fechar**.

4. No campo **Resultado 2**, insira o nome do resultado ou a opção.
5. Para adicionar traduções do resultado, siga estas etapas:

    1. Clique em **Traduções**.
    2. Na página exibida, clique em **Adicionar**.
    3. Na lista exibida, selecione o idioma do texto que você está inserindo.
    4. No campo **Texto traduzido**, insira o texto.
    5. Clique em **Fechar**.

## <a name="specify-when-notifications-are-sent"></a>Especificar quando enviar notificações

Você pode enviar notificações às pessoas quando uma decisão é tomada, delegada ou escalonada. Siga estas etapas para especificar quando enviar notificações e a quem elas devem ser enviadas.

1. No painel esquerdo, clique em **Notificações**.
2. Marque a caixa de seleção ao lado dos eventos para os quais as notificações devem ser enviadas:

    - **\[Opção 1\]** – O usuário atribuído selecionou **\[Opção 1\]**.
    - **\[Opção 2\]** – O usuário atribuído selecionou **\[Opção 2\]**.
    - **Delegar** – O usuário atribuído atribuiu a decisão a outro usuário.
    - **Escalonar** – O usuário atribuído não tomou a decisão no tempo alocado.

3. Selecione a linha de um evento que você selecionou na etapa 2.
4. Na guia **Texto da notificação**, insira o texto da notificação na caixa de texto.
5. Para personalizar a notificação, você poderá inserir espaços reservados. Os espaços reservados são substituídos pelos dados adequados quando a notificação é exibida para os usuários. Siga estas etapas para inserir um espaço reservado:

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
    <li>Na lista <strong>Participante</strong>, selecione o grupo ao qual serão enviadas notificações.</li>
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

## <a name="assign-a-decision"></a>Atribuir uma decisão

Siga estas etapas para especificar a quem uma decisão manual deve ser atribuída.

1. No painel esquerdo, clique em **Atribuição**.
2. Na guia **Tipo de atribuição**, selecione uma das opções na tabela a seguir e execute as etapas adicionais dessa opção antes de passar para a etapa 3.

    <table>
    <thead>
    <tr>
    <th>Opção</th>
    <th>Usuários aos quais a decisão é atribuída</th>
    <th>Etapas adicionais</th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td>Participante</td>
    <td>Usuários que foram atribuídos a uma função ou um grupo específico</td>
    <td>
    <ol>
    <li>Depois que você selecionar <strong>Participante</strong>, na guia <strong>Baseado em função</strong>, na lista <strong>Tipo de participante</strong>, selecione o tipo de grupo ou de função ao qual atribuir a decisão.</li>
    <li>Na lista <strong>Participante</strong>, selecione o grupo ou a função ao qual atribuir a decisão.</li>
    </ol>
    </td>
    </tr>
    <tr>
    <td>Hierarquia</td>
    <td>Usuários em uma hierarquia organizacional específica</td>
    <td>
    <ol>
    <li>Depois que você selecionar <strong>Hierarquia</strong>, na guia <strong>Seleção de hierarquia</strong>, na lista <strong>Tipo de hierarquia</strong>, selecione o tipo de hierarquia ao qual atribuir a decisão.</li>
    <li>O sistema deve recuperar um intervalo de nomes de usuário da hierarquia. Esses nomes representam usuários aos quais a decisão pode ser atribuída. Siga estas etapas para especificar o ponto inicial e final do intervalo de nomes de usuário que o sistema recupera: <ol>
    <li>Para especificar o ponto de partida, selecione uma pessoa na lista <strong>Iniciar em</strong>.</li>
    <li>Para especificar o ponto final, clique em <strong>Adicionar condição</strong>. Em seguida, insira uma condição que determine em que ponto da hierarquia o sistema para de recuperar nomes.</li>
    </ol>
    </li>
    <li>Na guia <strong>Opções de hierarquia</strong>, especifique a quais usuários no intervalo a decisão deve ser atribuída: <ul>
    <li><strong>Atribuir a todos os usuários recuperados</strong> – A decisão é atribuída a todos os usuários do intervalo.</li>
    <li><strong>Atribuir somente ao último usuário recuperado</strong> – A decisão é atribuída somente ao último usuário do intervalo.</li>
    <li><strong>Excluir usuários com a seguinte condição</strong> – A decisão não é atribuída aos usuários do intervalo que atenderem a determinada condição. Clique em <strong>Adicionar condição</strong> para especificar a condição.</li>
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
    <li>A lista <strong>Usuários disponíveis</strong> inclui todos os usuários. Selecione os usuários aos quais deseja atribuir a decisão e mova-os para a lista <strong>Usuários selecionados</strong>.</li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

3. Na guia **Limite de tempo**, no campo **Duração**, especifique quanto tempo o usuário tem para tomar a decisão. Selecione uma das seguintes opções:

    - **Horas** – Insira o número de horas que o usuário tem para tomar a decisão. Selecione o calendário usado pela sua organização e insira informações sobre a semana de trabalho da organização.
    - **Dias** – Insira o número de dias que o usuário tem para tomar a decisão. Selecione o calendário usado pela sua organização e insira informações sobre a semana de trabalho da organização.
    - **Semanas** – Insira o número de semanas que o usuário tem para tomar a decisão.
    - **Meses** – Selecione o dia e a semana até quando o usuário deve tomar a decisão. Por exemplo, talvez você queira que o usuário tome a decisão até sexta-feira da terceira semana do mês.
    - **Anos** – Selecione o dia, a semana e o mês até quando o usuário deve tomar a decisão. Por exemplo, talvez você queira que o usuário tome a decisão até a sexta-feira da terceira semana de dezembro.

    Se o usuário não tomar a decisão no tempo alocado, a decisão vencerá. Uma decisão vencida será escalonado, com base nas opções selecionadas na área **Escalonamento** da página.

## <a name="specify-what-happens-when-a-decision-is-overdue"></a>Especificar o que acontece quando uma decisão vence

Se um usuário não tomar a decisão no tempo alocado, a decisão vencerá. Uma decisão vencida pode ser escalonada ou atribuída automaticamente a outro usuário. Siga estas etapas para escalonar a decisão se ela estiver vencida.

1. No painel esquerdo, clique em **Escalonamento**.
2. Marque a caixa de seleção **Usar caminho de escalonamento** para criar um caminho de escalonamento. O sistema atribuirá automaticamente a decisão aos usuários listados no caminho de escalonamento. Por exemplo, a tabela a seguir representa um caminho de escalonamento.

    | Sequência | Caminho de escalonamento            |
    |----------|----------------------------|
    | 1        | Atribuir a: Denise           |
    | 2        | Atribuir a: Eduardo            |
    | 3        | Ação final: \[Opção 1\] |

    Neste exemplo, o sistema atribui a decisão vencida à Denise. Se a Denise não tomar a decisão no tempo alocado, o sistema a atribuirá a Eduardo. Se Eduardo não tomar a decisão no tempo alocado, o sistema selecionará **\[Opção 1\]** como decisão.

3. Para adicionar um usuário ao caminho de escalonamento, clique em **Adicionar escalonamento**. Selecione uma das opções na tabela a seguir e execute as etapas adicionais dessa opção antes de passar para a etapa 4.

    <table>
    <thead>
    <tr>
    <th>Opção</th>
    <th>Usuários para os quais a decisão será escalonada</th>
    <th>Etapas adicionais</th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td>Hierarquia</td>
    <td>Usuários em uma hierarquia organizacional específica</td>
    <td>
    <ol>
    <li>Depois que você selecionar <strong>Hierarquia</strong>, na guia <strong>Seleção de hierarquia</strong>, na lista <strong>Tipo de hierarquia</strong>, selecione o tipo de hierarquia ao qual a decisão será escalonada.</li>
    <li>O sistema deve recuperar um intervalo de nomes de usuário da hierarquia. Esses nomes representam os usuários aos quais a decisão pode ser escalonada. Siga estas etapas para especificar o ponto inicial e final do intervalo de nomes de usuário que o sistema recupera: <ol>
    <li>Para especificar o ponto de partida, selecione uma pessoa na lista <strong>Iniciar em</strong>.</li>
    <li>Para especificar o ponto final, clique em <strong>Adicionar condição</strong>. Em seguida, insira uma condição que determine em que ponto da hierarquia o sistema para de recuperar nomes.</li>
    </ol>
    </li>
    <li>Na guia <strong>Opções de hierarquia</strong>, especifique a quais usuários no intervalo a decisão deve ser escalonada: <ul>
    <li><strong>Atribuir a todos os usuários recuperados</strong> – A decisão é escalonada a todos os usuários do intervalo.</li>
    <li><strong>Atribuir somente ao último usuário recuperado</strong> – A decisão é escalonada somente ao último usuário do intervalo.</li>
    <li><strong>Excluir usuários com a seguinte condição:</strong> – A decisão não é escalonada aos usuários do intervalo que atenderem a determinada condição. Clique em <strong>Adicionar condição</strong> para especificar a condição.</li>
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
    <li>A lista <strong>Usuários disponíveis</strong> inclui todos os usuários. Selecione os usuários aos quais a decisão será escalonada e mova-os para a lista <strong>Usuários selecionados</strong>.</li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

4. Na guia **Limite de tempo**, no campo **Duração**, especifique quanto tempo o usuário tem para tomar a decisão. Selecione uma das seguintes opções:

    - **Horas** – Insira o número de horas que o usuário tem para tomar a decisão. Selecione o calendário usado pela sua organização e insira informações sobre a semana de trabalho da organização.
    - **Dias** – Insira o número de dias que o usuário tem para tomar a decisão. Selecione o calendário usado pela sua organização e insira informações sobre a semana de trabalho da organização.
    - **Semanas** – Insira o número de semanas que o usuário tem para tomar a decisão.
    - **Meses** – Selecione o dia e a semana até quando o usuário deve tomar a decisão. Por exemplo, talvez você queira que o usuário tome a decisão até sexta-feira da terceira semana do mês.
    - **Anos** – Selecione o dia, a semana e o mês até quando o usuário deve tomar a decisão. Por exemplo, talvez você queira que o usuário tome a decisão até a sexta-feira da terceira semana de dezembro.

5. Repita as etapas de 3 a 4 para cada usuário que deve ser adicionado ao caminho de escalonamento. Você pode alterar a ordem dos usuários.
6. Se os usuários listados no caminho de escalonamento não tomarem a decisão no tempo alocado, o sistema tomará a decisão. Para especificar a opção que o sistema selecionará, selecione a linha **Ação** e, na guia **Encerrar ação**, selecione uma opção.

## <a name="set-a-time-limit"></a>Definir um limite de tempo

Siga estas etapas caso a decisão deva ser tomada em um horário específico.

> [!NOTE]
> As opções selecionadas neste procedimento substituirão as que você selecionou nas áreas **Atribuição** e **Escalonamento** da página.

1. No painel esquerdo, clique em **Configurações avançadas**.
2. Marque a caixa de seleção **Definir um limite de tempo para o elemento de fluxo de trabalho**.
3. No campo **Duração**, especifique quando a decisão deve ser tomada. Selecione uma das seguintes opções:

    - **Horas** - Insira o número de horas. Selecione o calendário usado pela sua organização e insira informações sobre a semana de trabalho da organização.
    - **Dias** – Insira o número de dias. Selecione o calendário usado pela sua organização e insira informações sobre a semana de trabalho da organização.
    - **Semanas** – Insira o número de semanas.
    - **Meses** – Selecione o dia e a semana até quando a decisão deve ser tomada. Por exemplo, você talvez queira que a decisão seja tomada até a sexta-feira da terceira semana do mês.
    - **Anos** – Selecione o dia, a semana e o mês até quando a decisão deve ser tomada. Por exemplo, você talvez queira que a decisão seja tomada até a sexta-feira da terceira semana de dezembro.

4. Se o limite de tempo for excedido, o sistema tomará a decisão. Na lista **Ação**, selecione a opção que o sistema deve selecionar.
