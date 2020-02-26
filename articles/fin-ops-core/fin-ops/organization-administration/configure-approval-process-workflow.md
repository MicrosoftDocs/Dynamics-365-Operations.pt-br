---
title: Configurar processos de aprovação em um fluxo de trabalho
description: Use os procedimentos a seguir para configurar as propriedades do processo de aprovação.
author: sericks007
manager: AnnBe
ms.date: 01/24/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 195643
ms.assetid: f853f57b-83ae-4fb0-a9fa-06ea3fc34fa1
ms.search.region: Global
ms.author: donaldc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1f58e227542b1e5ca1235748d14e71bddac826ee
ms.sourcegitcommit: 759325234a763e14071348a6f5399999a92f8264
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/25/2020
ms.locfileid: "2983755"
---
# <a name="configure-approval-processes-in-a-workflow"></a>Configurar processos de aprovação em um fluxo de trabalho

[!include [banner](../includes/banner.md)]

Use os procedimentos a seguir para configurar as propriedades do processo de aprovação.

Para configurar um processo de aprovação, no editor de fluxo de trabalho, clique com o botão direito do mouse no elemento de aprovação e depois clique em **Propriedades** para abrir o formulário **Propriedades**.

## <a name="name-the-approval-process"></a>Nomear o processo de aprovação

Siga estas etapas para inserir um nome para o processo de aprovação.

1. No painel esquerdo, clique em **Configurações Básicas**.
2. No campo **Nome**, insira um nome exclusivo para o processo de aprovação.

## <a name="specify-when-the-system-automatically-acts-on-the-document"></a>Especificar quando o sistema deve executar automaticamente uma ação no documento

Você pode configurar o sistema para executar automaticamente uma ação no documento se condições específicas forem atendidas. Por exemplo, o sistema pode aprovar os relatórios de despesas que tenham valores totais inferiores a USD 100. Siga estas etapas para especificar quando o sistema deve executar uma ação no documento.

1. No painel esquerdo, clique em **Ações automáticas**.
2. Marque a caixa de seleção **Habilitar ações automáticas**.
3. Clique em **Adicionar condição**.
4. Insira uma condição.
5. Insira outras condições, se necessário.
6. Para verificar se as condições inseridas foram configuradas corretamente, execute as etapas a seguir:

    1. Clique em **Teste** para abrir o formulário **Condição de fluxo de trabalho de teste**.
    2. Selecione um registro na área **Validar condição** do formulário.
    3. Clique em **Teste**. O sistema avaliará o registro para determinar se ele atende às condições definidas.
    4. Clique em **OK** ou em **Cancelar** para retornar ao formulário **Propriedades**.

7. Na lista **Ação de autocompletar**, selecione a ação que o sistema deve executar no documento.

## <a name="specify-when-notifications-are-sent"></a>Especificar quando enviar notificações

Você poderá enviar notificações às pessoas quando um documento tiver sido aprovado, rejeitado, delegado ou escalonada ou quando uma alteração tiver sido solicitada. Siga estas etapas para especificar quando enviar notificações e a quem elas devem ser enviadas.

1. No painel esquerdo, clique em **Notificações**.
2. Marque a caixa de seleção ao lado dos eventos para os quais enviar notificações:

    - **Delegar** – quando um documento tiver sido atribuído a outro usuário para aprovação.
    - **Escalonar** – quando o usuário atribuído não executar uma ação em um documento no tempo alocado.
    - **Aprovar** – quando um documento tiver sido aprovado.
    - **Rejeitar** – quando um documento tiver sido rejeitado.
    - **Solicitar alteração** – quando o usuário atribuído tiver solicitado uma alteração em um documento enviado.

3. Selecione a linha de um evento que você selecionou na etapa 2.
4. Clique na guia **Texto de Notificação**.
5. Na caixa de texto, insira o texto da notificação.
6. Para personalizar o texto, insira espaços reservados, que serão substituídos pelos dados adequados quando forem exibidos aos usuários. Para inserir um espaço reservado, siga estas etapas:

    1. Clique na caixa de texto, no local onde o espaço reservado deve aparecer.
    2. Clique em **Inserir espaço reservado**.
    3. Na lista exibida, selecione o espaço reservado a ser inserido.
    4. Clique em **Inserir**.

7. Para adicionar traduções da notificação, clique em **Traduções**. No formulário que é exibido, siga estas etapas:

    1. Clique em **Adicionar**.
    2. Na lista exibida, selecione o idioma no qual o texto será inserido.
    3. Na caixa de texto **Texto traduzido**, insira o texto.
    4. Para personalizar o texto, insira espaços reservados.
    5. Clique em **Fechar**.

8. Clique na guia **Destinatário**.
9. Especifique a quem as notificações serão enviadas. Selecione uma das opções na tabela a seguir e execute as etapas adicionais para a opção antes de ir para a etapa 10.

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
    <td><strong>Participante</strong></td>
    <td>Usuários que foram atribuídos a uma função ou um grupo específico</td>
    <td>
    <ol>
    <li>Após selecionar <strong>Participante</strong>, clique na guia <strong>Função baseada</strong>.</li>
    <li>Na lista <strong>Tipo de Participante</strong>, selecione o tipo de grupo ou a função ao qual serão enviadas notificações.</li>
    <li>Na lista <strong>Participante</strong>, selecione o grupo ou a função ao qual serão enviadas notificações.</li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><strong>Usuário de fluxo de trabalho</strong></td>
    <td>Usuários que participam do fluxo de trabalho atual</td>
    <td>
    <ol>
    <li>Após selecionar <strong>Usuário de fluxo de trabalho</strong>, clique na guia <strong>Usuário de fluxo de trabalho</strong>.</li>
    <li>Na lista <strong>Usuário de fluxo de trabalho</strong>, selecione um usuário que participa do fluxo de trabalho.</li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><strong>Usuário</strong></td>
    <td>Usuários específicos</td>
    <td>
    <ol>
    <li>Após selecionar <strong>Usuário</strong>, clique na guia <strong>Usuário</strong>.</li>
    <li>Selecione os usuários aos quais você enviará notificações e mova-os para a lista: <strong>Usuários selecionados</strong>.</li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

10. Repita as etapas de 3 a 9 para cada evento selecionado na etapa 2.

## <a name="specify-a-final-approver"></a>Especificar um aprovador final

Você pode designar um aprovador final para cenários em que o aprovador é a pessoa que enviou o documento para aprovação e a opção "Proibir aprovação pelo emissor" está sendo usada. Siga estas etapas para especificar um aprovador final.

1. No editor de fluxo de trabalho, clique com o botão direito do mouse no elemento de aprovação e selecione **Propriedades** para abrir o formulário **Propriedades**.
2. No painel esquerdo, clique em **Configurações avançadas**.
3. Marque a caixa de seleção **Usar aprovador final**.
4. Na lista, selecione um usuário que será o aprovador final.

## <a name="set-a-time-limit"></a>Definir um limite de tempo

Siga estas etapas se o processo de aprovação tiver que ser concluído em um horário específico.

> [!NOTE]
> As opções selecionadas aqui substituirão as que você selecionar nas guias **Atribuição** e **Escalonamento** de cada etapa de aprovação.

1. No painel esquerdo, clique em **Configurações avançadas**.
2. Marque a caixa de seleção **Definir um limite de tempo para o** **elemento de fluxo de trabalho**.
3. No campo **Duração**, especifique quando o processo de aprovação deve ser concluído. Selecione uma das seguintes opções:

    - **Horas** – insira o número de horas em que o processo de aprovação deve ser concluído. Selecione o calendário usado pela sua organização e insira informações sobre a semana de trabalho da organização.
    - **Dias** – insira o número de dias em que o processo de aprovação deve ser concluído. Selecione o calendário usado pela sua organização e insira informações sobre a semana de trabalho da organização.
    - **Semanas** – insira o número de semanas em que o processo de aprovação deve ser concluído.
    - **Meses** – selecione o dia, a semana e o mês de limite para a conclusão do processo de aprovação. Por exemplo, você pode querer que o processo seja concluído até sexta-feira da terceira semana do mês.
    - **Anos** – selecione o dia, a semana e o mês de limite para a conclusão do processo de aprovação. Por exemplo, você pode querer que o processo seja concluído até a sexta-feira da terceira semana de dezembro.

4. Se o limite de tempo for excedido, o sistema executará uma ação no documento. Na lista **Ação**, selecione a ação que o sistema deve executar.

## <a name="specify-which-actions-are-available-to-the-user"></a>Especificar quais ações estarão disponíveis para o usuário

Quando um documento for atribuído a um usuário para aprovação, o usuário deverá executar uma ação no documento. Siga estas etapas para especificar quais as ações o usuário poderá executar no documento enviado.

1. No painel esquerdo, clique em **Configurações avançadas**.
2. Marque a caixa de seleção **Aprovar** se o usuário puder aprovar o documento.
3. Marque a caixa de seleção **Rejeitar** se o usuário puder rejeitar o documento.
4. Marque a caixa de seleção **Solicitar alteração** se o usuário puder solicitar alterações no documento.
5. Marque a caixa de seleção **Delegar** se o usuário puder atribuir o documento a outro usuário para aprovação.

> [!NOTE]
> A caixa de seleção **Habilitar ações da lista de trabalho no Portal Empresarial** foi substituída.

## <a name="configure-the-approval-steps"></a>Configurar as etapas de aprovação

Um processo de aprovação consiste em etapas de aprovação. Conclua o procedimento a seguir para adicionar etapas ao processo de aprovação e configurar as etapas.

1. No editor de fluxo de trabalho, clique duas vezes no processo de aprovação. O editor de fluxo de trabalho exibe as etapas do processo de aprovação.
2. Para adicionar uma etapa de aprovação, arraste-a da área **Elementos de fluxo de trabalho** para a tela.
3. Para configurar uma etapa de aprovação, consulte [Configurar etapas de aprovação em um fluxo de trabalho](configure-approval-step-workflow.md).
