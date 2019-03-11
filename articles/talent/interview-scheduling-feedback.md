---
title: Agendamento de entrevistas e comentários
description: Este tópico fornece informações sobre o planejamento de entrevista e atividades de comentários no Attract.
author: ''
manager: AnnBe
ms.date: 02/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent, Core
ms.search.region: Global
ms.author: hasrivas
ms.openlocfilehash: 7bc5a66bb221cb0ab2c69fcb1013ed48a7c664a6
ms.sourcegitcommit: 1e32d78868098fd76124bb41363f15c4ec3ea15a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2019
ms.locfileid: "374849"
---
# <a name="interview-scheduling-and-feedback"></a>Agendamento de entrevistas e comentários

[!include[banner](../includes/banner.md)]

## <a name="scheduler-activity"></a>Atividade do agendador

A atividade do agendador é opcional e terá dois componentes: solicitação de disponibilidade do candidato e agenda. O componente de disponibilidade do candidato permite que você use o email para solicitar a disponibilidade de um candidato. O componente de Agenda fornece a possibilidade de agendar entrevistas com o candidato e a equipe de contratação.

### <a name="candidate-availability-request"></a>Solicitação de disponibilidade do candidato

Para enviar um email aos candidatos solicitando a disponibilidade, selecione co campo **Solicitar disponibilidade do candidato**. Se o campo não estiver selecionado, esta etapa não será exibida no processo de contratação do trabalho.

Para enviar a solicitação de disponibilidade, clique em **Enviar solicitação**, escolha as datas disponíveis e um modelo de email e, em seguida, envie o email para o candidato.

[![Exibição de recrutador do Attract para enviar solicitação de disponibilidade do candidato](./media/scheduler-candidate-request.png)](./media/scheduler-candidate-request.png)

Quando o candidato recebe um email para responder à solicitação, ele poderá se conectar ao portal do candidato, escolher as datas que correspondem à sua disponibilidade, e clicar em **Enviar**.

### <a name="schedule"></a>Plano
Há várias configurações disponíveis no agendador de entrevista para usar e criar rapidamente, e enviar o loop de entrevistas para o entrevistador e o candidato.

1. Clique em **Criar agendamento** e na caixa **Adicionar entrevistadores**, liste todos os entrevistadores que fazem parte do loop de entrevista.
[![Exibição do recrutador do Attract para iniciar o agendamento de um loop de entrevista](./media/schedule-start-over.png)](./media/schedule-start-over.png)   
    Se o candidato respondeu à solicitação de disponibilidade da entrevista, o campo **Data da entrevista** será preenchido com sua seleção. Você pode selecionar uma data diferente, se necessário.
    
    Se você selecionar o campo **Tornar esta entrevista de painel**, o grupo de entrevistadores da esquerda será movido para um loop de painel único para criar a entrevista. Você precisará definir uma sequência específica das entrevistas.
    
    O planejamento da entrevista deve ser organizado para corresponder à melhor disponibilidade dos participantes. Se for um candidato interno, você pode incluir a disponibilidade como parte da recomendação de agendamento.
    
    Para ter uma reunião online, selecione o campo **Adicionar reuniões do Skype** e cada evento de entrevista terá um link **Skype for Business** disponível.

2. Selecione a duração da entrevista para cada evento de entrevista e clique em **OK** para iniciar a criação da agenda.

    Se a opção **Recomendações** for selecionada, as sugestões serão mostradas e a grade de entrevista será preenchida. Você poderá ver a disponibilidade do calendário atual de todos os entrevistados escolhidos. Você também poderá exibir o calendário do candidato, se for um candidato interno.

3. Se não houver nenhuma sugestão disponível, na coluna **Entrevistadores** , clique em um intervalo de tempo, forneça o título da entrevista, detalhes, e preencha os detalhes do local, conforme necessário. Você pode optar por incluir o link **Skype for Business** para a entrevista.

4. Para incluir entrevistadores adicionais, clique na coluna de grade **Adicionar entrevista** para selecionar um ou mais entrevistadores. Você pode usar a opção de reticências (...) para remover uma entrevista do loop.
    
5. Se os entrevistadores estiverem agendados em um fuso horário diferente, escolha a cidade/fuso horário da lista suspensa superior direita. A grade de disponibilidade do entrevistador será atualizada para mostrar o novo fuso horário. Esta seleção de fuso horário agora também mostrará a exibição **Resumo da entrevista** , que será compartilhado com os entrevistadores e o candidato. 

6. Clique em **Enviar aos entrevistadores** para enviar os convites da reunião aos entrevistadores envolvidos.

    Depois que as solicitações de entrevista forem enviadas aos entrevistadores, eles podem responder diretamente o convite de email que receberam.

    >[!NOTE]
    > Para todas as entrevistas 1:1, lembretes serão enviados para os entrevistadores a cada 24 horas eles não responderem (aceitar ou rejeitar) à solicitação de entrevista.

    > Para todas as entrevistas de painel, não há lembretes automáticos para a solicitação de entrevista. Para disparar um lembrete manualmente, edite a entrevista e utilize a opção **Atualizar e Enviar** para retornar a solicitação para os entrevistadores.

    As respostas de entrevistador são capturadas e mostradas no Attract. Se um entrevistador recusar o convite, você será notificado para fazer uma alteração. Para exibir sua resposta na exibição em grade do **Agendador**, clique no ícone de bolha.

[![Exibição do recrutador do Attract de uma resposta do entrevistador](./media/schedule-interviewer-response.png)](./media/schedule-interviewer-response.png)

7. Depois que a agenda da entrevista estiver pronta para ser compartilhada com o candidato, clique em **Enviar ao candidato**. Você pode optar por ocultar ou mostrar os nomes e intervalos de tempo do entrevistador com o candidato.

8. Selecione um modelo de email e envie o resumo da entrevista ao candidato. O candidato pode exibir estas informações no email, assim como no portal do candidato.
    
>[!NOTE] 
> A disponibilidade do calendário de um candidato é exibida apenas se o candidato for interno. De forma similar, somente os candidatos internos podem ser usados para melhorar recomendações de agenda da entrevista. Atualmente, os candidatos (internos ou externos) não recebem um convite de reunião por email, eles recebem somente um resumo das entrevistas.

## <a name="feedback-activity"></a>Atividade de comentários

A atividade dos comentários é opcional em um modelo de trabalho. Esta atividade permite que os participantes da entrevista insiram recomendações ou comentários de um candidato. Se o campo **Herdar participantes de comentários da Equipe de Contratação** for selecionado, o recrutador, gerente de contratação e os entrevistadores serão inseridos automaticamente na atividade de comentários. As organizações podem permitir que os entrevistadores exibam os comentários de outras pessoas antes que enviem seus próprios comentários. As organizações também podem permitir que os entrevistadores editem os comentários após o envio. Os entrevistadores são avisados para enviar comentários das entrevistas que conduziram recentemente, com base na configuração predefinida, com parte do modelo de trabalho. O gerente de contratação ou o recrutador do trabalho também pode optar por lembrar um entrevistador, manualmente, para enviar o comentário.

## <a name="interview-activity"></a>Atividade de entrevista

A atividade da entrevista é uma atividade opcional com três componentes: solicitação de disponibilidade do candidato, agendamento e comentário. Use a atividade de entrevista no modelo de trabalho, se quiser toda a solicitação de disponibilidade do candidato, agenda e comentários como parte do processo, em vez de usá-la individualmente como parte do processo de contratação.
