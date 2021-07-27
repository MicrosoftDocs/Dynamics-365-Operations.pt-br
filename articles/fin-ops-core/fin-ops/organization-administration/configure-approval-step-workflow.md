---
title: Configurar etapas de aprovação em um fluxo de trabalho
description: Este tópico explica como configurar as propriedades de uma etapa de aprovação.
author: ChrisGarty
ms.date: 08/23/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: 192161
ms.assetid: 8b478e3d-d6b4-403b-aae0-f639a71ca36c
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 988340d9e5fc12c9329a587c7401fe039c8e5722
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/06/2021
ms.locfileid: "6350685"
---
# <a name="configure-approval-steps-in-a-workflow"></a>Configurar etapas de aprovação em um fluxo de trabalho

[!include [banner](../includes/banner.md)]

Este tópico explica como configurar as propriedades de uma etapa de aprovação.

Para configurar uma etapa de aprovação no editor de fluxo de trabalho, clique com o botão direito do mouse na etapa de aprovação e clique em **Propriedades** para abrir a página **Propriedades**. Depois, use os procedimentos a seguir para configurar as propriedades da etapa de aprovação.

## <a name="name-the-step"></a>Nomear a etapa
Siga estas etapas para inserir um nome para a etapa de aprovação.

1. No painel esquerdo, clique em **Configurações Básicas**.
2. No campo **Nome**, insira um nome exclusivo para a etapa de aprovação.

## <a name="enter-a-subject-line-and-instructions"></a>Inserir uma linha de assunto e instruções

Você deve fornecer uma linha de assunto e instruções para os usuários atribuídos à etapa de aprovação. Por exemplo, se você estiver configurando uma etapa de aprovação para requisições de compra, o usuário que foi atribuído à etapa verá a linha de assunto e as instruções na página **Requisições de compra**. A linha de assunto aparece em uma barra de mensagens na página. Em seguida, o usuário pode clicar no ícone na barra de mensagens para ver as instruções. Siga estas etapas para inserir uma linha de assunto e instruções.

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

## <a name="assign-the-approval-step"></a>Atribuir a etapa de aprovação

Siga estas etapas para especificar a quem a etapa de aprovação deve ser atribuída.

1. No painel esquerdo, clique em **Atribuição**.
2. Na guia **Tipo de atribuição**, selecione uma das opções na tabela a seguir e execute as etapas adicionais dessa opção antes de passar para a etapa 3.

    <table>
    <thead>
    <tr>
    <th>Opção</th>
    <th>Os usuários aos quais a etapa de aprovação foi atribuída</th>
    <th>Etapas adicionais</th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td>Participante</td>
    <td>Usuários que foram atribuídos a uma função ou um grupo específico</td>
    <td>
    <ol>
    <li>Depois que você selecionar <strong>Participante</strong>, na guia <strong>Baseado em função</strong>, na lista <strong>Tipo de participante</strong>, selecione o tipo de grupo ou de função ao qual atribuir a etapa.</li>
    <li>Na lista <strong>Participante</strong>, selecione o grupo ou a função ao qual atribuir a etapa.</li>
    </ol>
    </td>
    </tr>
    <tr>
    <td>Hierarquia</td>
    <td>Usuários em uma hierarquia organizacional específica</td>
    <td>
    <ol>
    <li>Depois que você selecionar <strong>Hierarquia</strong>, na guia <strong>Seleção de hierarquia</strong>, na lista <strong>Tipo de hierarquia</strong>, selecione o tipo de hierarquia ao qual atribuir a etapa.</li>
    <li>O sistema deve recuperar um intervalo de nomes de usuário da hierarquia. Esses nomes representam os usuários aos quais a etapa pode ser atribuída. Siga estas etapas para especificar o ponto inicial e final do intervalo de nomes de usuário que o sistema recupera: <ol>
    <li>Para especificar o ponto de partida, selecione uma pessoa na lista <strong>Iniciar em</strong>.</li>
    <li>Para especificar o ponto final, clique em <strong>Adicionar condição</strong>. Em seguida, insira uma condição que determine em que ponto da hierarquia o sistema para de recuperar nomes.</li>
    </ol>
    </li>
    <li>Na guia <strong>Opções de hierarquia</strong>, especifique a quais usuários no intervalo a etapa deve ser atribuída: <ul>
    <li><strong>Atribuir a todos os usuários recuperados</strong> – A etapa é atribuída a todos os usuários do intervalo.</li>
    <li><strong>Atribuir somente ao último usuário recuperado</strong> – A etapa é atribuída somente ao último usuário do intervalo.</li>
    <li><strong>Excluir usuários com a seguinte condição</strong> – A etapa não é atribuído aos usuários do intervalo que atenderem a determinada condição. Clique em <strong>Adicionar condição</strong> para especificar a condição.</li>
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
    <li>A lista <strong>Usuários disponíveis</strong> inclui todos os usuários do sistema. Selecione os usuários aos quais deseja atribuir a etapa e mova-os para a lista <strong>Usuários selecionados</strong>.</li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

3. Na guia **Limite de tempo**, no campo **Duração**, especifique quanto tempo o usuário tem para executar uma ação nos documentos que atingem a etapa de aprovação ou responder a eles. Selecione uma das seguintes opções:

    - **Horas** – Insira o número de horas que o usuário tem para responder. Selecione o calendário usado pela sua organização e insira informações sobre a semana de trabalho da organização.
    - **Dias** – Insira o número de dias que o usuário tem para responder. Selecione o calendário usado pela sua organização e insira informações sobre a semana de trabalho da organização.
    - **Semanas** – Insira o número de semanas que o usuário tem para responder.
    - **Meses** – Selecione até que dia e semana o usuário deve responder. Por exemplo, talvez você queira que o usuário responda até sexta-feira da terceira semana do mês.
    - **Anos** – Selecione até que dia, semana e mês o usuário deve responder. Por exemplo, talvez você queira que o usuário responda até sexta-feira da terceira semana de dezembro.

    Se o usuário não executar nenhuma ação no documento no tempo alocado, o documento vencerá. Um documento vencido será escalonado, com base nas opções selecionadas na área **Escalonamento** da página.

4. Se você tiver atribuído a etapa de aprovação a vários usuários ou a um grupo de usuários, na guia **Política de conclusão**, selecione uma das seguintes opções:

    - **Aprovador único** – a ação que é aplicada ao documento é determinada pela primeira pessoa que responde. Por exemplo, suponha que Samuel tenha enviado um relatório de despesas de US$ 15.000. O relatório de despesas está atribuído no momento à Suzana, à Joana e a Guilherme. Se Suzana for a primeira pessoa a responder ao documento, a ação tomada por ela será aplicada. Se Suzana rejeitar o documento, ele será rejeitado e enviado novamente para Samuel. Se Suzana aprovar o documento, ele será enviado a Ana para aprovação.

        ![Fluxo de trabalho que tem um processo de aprovação.](./media/workflow_multipleusersinstep.gif)

    - **Maioria dos aprovadores** – a ação que é aplicada ao documento é determinada quando a maioria dos aprovadores responde. Por exemplo, suponha que Samuel tenha enviado um relatório de despesas de US$ 15.000. O relatório de despesas está atribuído no momento à Suzana, à Joana e a Guilherme. Se Suzana e Joana forem os dois primeiros aprovadores a responder, a ação tomada por ambas será aplicada ao documento.

        - Se Suzana aprovar o documento, mas Joana o rejeitar, o documento será rejeitado e enviado novamente para Samuel.
        - Se Suzana e Joana aprovarem o documento, ele será enviado a Ana para aprovação.

    - **Porcentagem de aprovadores** – a ação que é aplicada ao documento é determinada quando uma porcentagem específica dos aprovadores responde. Por exemplo, suponha que Samuel tenha enviado um relatório de despesas de US$ 15.000. O relatório de despesas está atribuído no momento à Suzana, à Joana e ao Guilherme, e você inseriu **50** como porcentagem. Se Suzana e Joana forem os dois primeiros aprovadores a responderem, a ação que elas executarem será aplicada ao documento, pois o requisito de 50% dos aprovadores foi atendido.

        - Se Suzana aprovar o documento, mas Joana o rejeitar, o documento será rejeitado e enviado novamente para Samuel.
        - Se Suzana e Joana aprovarem o documento, ele será enviado a Ana para aprovação.

    - **Todos os aprovadores** – todos os aprovadores deverão aprovar o documento. Caso contrário, o fluxo de trabalho não poderá continuar. Por exemplo, suponha que Samuel tenha enviado um relatório de despesas de US$ 15.000. O relatório de despesas está atribuído no momento à Suzana, à Joana e a Guilherme. Se Suzana e Joana aprovarem o documento, mas Guilherme o rejeitar, o documento será rejeitado e enviado novamente para Samuel. Se Suzana, Joana e Guilherme aprovarem o documento, ele será enviado a Ana para aprovação.

## <a name="specify-when-the-approval-step-is-required"></a>Especificar quando a etapa de aprovação é necessária

Você pode especificar quando a etapa de aprovação é necessária. Possivelmente, ela sempre será necessária ou será necessária apenas se condições específicas forem atendidas.

### <a name="the-approval-step-is-always-required"></a>A etapa de aprovação é sempre necessária

Siga estas etapas caso a etapa de aprovação seja sempre necessária.

1. No painel esquerdo, clique em **Condição**.
2. Selecione a opção **Executar sempre esta etapa**.

### <a name="the-approval-step-is-required-in-specific-conditions"></a>A etapa de aprovação é necessária em condições específicas

A etapa de aprovação que você está configurando poderá ser necessária apenas se condições específicas forem atendidas. Por exemplo, se você estiver configurando uma etapa de aprovação para um fluxo de trabalho de requisição de compra, talvez seja conveniente que a etapa de aprovação ocorra somente se o valor da requisição de compra for superior a US$ 10.000. Siga estas etapas para especificar quando a etapa de aprovação é necessária.

1. No painel esquerdo, clique em **Condição**.
2. Selecione a opção **Executar esta etapa somente quando a seguinte condição for atendida**.
3. Insira uma condição.
4. Insira quaisquer condições adicionais necessárias.
5. Para verificar se as condições inseridas foram configuradas corretamente, execute estas etapas:

    1. Clique em **Teste**.
    2. Na página **Testar condição de fluxo de trabalho**, na área **Validar condição**, selecione um registro.
    3. Clique em **Teste**. O sistema avaliará o registro para determinar se ele atende às condições definidas.
    4. Clique em **OK** ou **Cancelar** para retornar à página **Propriedades**.

## <a name="specify-what-happens-when-the-document-is-overdue"></a>Especificar o que acontece quando o documento está vencido

Se um usuário não executar nenhuma ação em um documento no tempo alocado, o documento vencerá. Um documento vencido pode ser escalonado ou atribuído automaticamente a outro usuário para aprovação. Siga estas etapas para escalonar o documento se ele estiver vencido.

1. No painel esquerdo, clique em **Escalonamento**.
2. Marque a caixa de seleção **Usar caminho de escalonamento** para criar um caminho de escalonamento. O sistema atribuirá automaticamente o documento aos usuários listados nesse caminho. Por exemplo, a tabela a seguir representa um caminho de escalonamento.

    | Sequência | Caminho de escalonamento      |
    |----------|----------------------|
    | 1        | Atribuir a: Denise     |
    | 2        | Atribuir a: Eduardo      |
    | 3        | Ação final: Rejeitar |

    Nesse exemplo, o sistema atribui o documento vencido à Denise. Se Denise não responder no tempo alocado, o sistema atribuirá o documento a Eduardo. Se Eduardo não responder no tempo alocado, o sistema rejeitará o documento.

3. Para adicionar um usuário ao caminho de escalonamento, clique em **Adicionar escalonamento**. Na guia **Tipo de atribuição**, selecione uma das opções na tabela a seguir e execute as etapas adicionais dessa opção antes de passar para a etapa 4.

    <table>
    <thead>
    <tr>
    <th>Opção</th>
    <th>Usuários aos quais o documento será escalonado</th>
    <th>Etapas adicionais</th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td>Hierarquia</td>
    <td>Usuários em uma hierarquia organizacional específica</td>
    <td>
    <ol>
    <li>Depois que você selecionar <strong>Hierarquia</strong>, na guia <strong>Seleção de hierarquia</strong>, na lista <strong>Tipo de hierarquia</strong>, selecione o tipo de hierarquia ao qual o documento será escalonado.</li>
    <li>O sistema deve recuperar um intervalo de nomes de usuário da hierarquia. Esses nomes representam usuários para os quais o documento pode ser escalonado. Siga estas etapas para especificar o ponto inicial e final do intervalo de nomes de usuário que o sistema recupera: <ol>
    <li>Para especificar o ponto de partida, selecione uma pessoa na lista <strong>Iniciar em</strong>.</li>
    <li>Para especificar o ponto final, clique em <strong>Adicionar condição</strong>. Em seguida, insira uma condição que determine em que ponto da hierarquia o sistema para de recuperar nomes.</li>
    </ol>
    </li>
    <li>Na guia <strong>Opções de hierarquia</strong>, especifique a quais usuários no intervalo o documento deve ser escalonado: <ul>
    <li><strong>Atribuir a todos os usuários recuperados</strong> – O documento é escalonado para todos os usuários do intervalo.</li>
    <li><strong>Atribuir somente ao último usuário recuperado</strong> – O documento é escalonado somente ao último usuário do intervalo.</li>
    <li><strong>Excluir usuários com a seguinte condição</strong> – O documento não é escalonado aos usuários do intervalo que atenderem a determinada condição. Clique em <strong>Adicionar condição</strong> para especificar a condição.</li>
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
    <li>A lista <strong>Usuários disponíveis</strong> inclui todos os usuários. Selecione os usuários aos quais o documento será escalonado e mova-os para a lista <strong>Usuários selecionados</strong>.</li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

4. Na guia **Limite de tempo**, no campo **Duração**, especifique quanto tempo o usuário tem para executar uma ação nos documentos que atingem a etapa de aprovação ou responder a eles. Selecione uma das seguintes opções:

    - **Horas** – Insira o número de horas que o usuário tem para responder. Selecione o calendário usado pela sua organização e insira informações sobre a semana de trabalho da organização.
    - **Dias** – Insira o número de dias que o usuário tem para responder. Selecione o calendário usado pela sua organização e insira informações sobre a semana de trabalho da organização.
    - **Semanas** – Insira o número de semanas que o usuário tem para responder.
    - **Meses** – Selecione até que dia e semana o usuário deve responder. Por exemplo, talvez você queira que o usuário responda até sexta-feira da terceira semana do mês.
    - **Anos** – Selecione até que dia, semana e mês o usuário deve responder. Por exemplo, talvez você queira que o usuário responda até sexta-feira da terceira semana de dezembro.

5. Repita as etapas de 3 a 4 para cada usuário que deve ser adicionado ao caminho de escalonamento. Você pode alterar a ordem dos usuários.
6. Se os usuários no caminho de escalonamento não responderem no tempo alocado, o sistema executará uma ação no documento automaticamente. Para especificar a ação que o sistema executará, selecione a linha **Ação** e, na guia **Encerrar ação**, selecione uma ação.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]