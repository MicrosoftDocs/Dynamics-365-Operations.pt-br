---
title: Atividades nos processos
description: "Este tópico fornece informações sobre os vários tipos de atividades que podem ser usadas no processo de contratação."
author: 
manager: AnnBe
ms.date: 12/07/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: rschloma
ms.search.validFrom: 2018-10-15
ms.dyn365.ops.version: Talent October 2018 update
ms.translationtype: HT
ms.sourcegitcommit: be66d9f95551066bb8bc25445c652d4fa59066d4
ms.openlocfilehash: 4f59193991420fd9ec05a83049e569058bf81932
ms.contentlocale: pt-br
ms.lasthandoff: 12/07/2018

---

# <a name="activities-in-the-hiring-processes"></a>Atividades nos processos de contratação

[!include[banner](../includes/banner.md)]

As atividades podem ser adicionados como parte do processo de contratação no Microsoft Dynamics 365 for Talent: Attract. As atividades podem ser adicionadas a um modelo de processo ou podem ser adicionadas diretamente ao processo de contratação no trabalho. Quando um trabalho é definidos, um modelo de processo é selecionado e as atividades que estão incluídas no modelo são aplicadas ao trabalho. Se um modelo não for selecionado, o modelo padrão será usado. O processo de contratação também poderá ser modificado no trabalho depois que o modelo for aplicado.

> [!NOTE] 
> Os modelos de processo estão disponíveis com o complemento de Contratação abrangente.

## <a name="prospect-activity"></a>Atividade do candidato ao trabalho

A atividade do candidato ao trabalho controla se os candidatos podem ser adicionados a um trabalho. Por padrão, os candidatos podem ser adicionados a um trabalho. Para desativar a Atividade do candidato ao trabalho, defina a opção **Habilitar candidatos** como **Desativado**. Quando uma Atividade do candidato ao trabalho é ativada, os gerentes de contratação podem adicionar e exibir candidatos, e a guia **Candidato ao trabalho** é exibida no trabalho.

## <a name="application-activity"></a>Atividade de solicitação de emprego

A Atividade de solicitação de emprego é necessária em modelo do processo de contratação. Para enviar emails aos candidatos quando eles enviam suas solicitações ou são adicionados ao Estágio de solicitação de emprego, defina a opção **Enviar email ao candidato** como **Ativado**.

## <a name="scheduler-activity"></a>Atividade do agendador

A Atividade do agendador é opcional. Essa atividade tem dois componentes: disponibilidade do candidato e agenda. O componente de disponibilidade do candidato permite que você use o email para solicitar a disponibilidade de um candidato. O componente de Agenda fornece a possibilidade de agendar entrevistas com o candidato e a equipe de contratação. Na Atividade do agendador, as seguintes opções podem ser configuradas: **Solicitar a disponibilidade do candidato**, **Reunião online**, e **Enviar email ao candidato**.

- Para enviar email aos candidatos para solicitar a disponibilidade, defina a opção **Solicitar a disponibilidade do candidato** como **Ativado**. Se você definir opção como **Desativado**, a etapa não será exibida no processo de contratação no trabalho.
- Para fazer uma transmissão ao vivo ou uma chamada em conferência usando o Skype for Business, defina o campo **Reunião online** como **Skype for Business**. O link correto **Ingressar na Reunião do Skype** será adicionado à solicitação de reunião para entrevista enviada aos entrevistadores.
- Para enviar emails aos candidatos para finalizar a agenda, defina a opção **Enviar email ao candidato** como **Ativado**. Se você definir a opção **Desativado**, os candidatos receberão o o agendamento de entrevista somente quando eles entrarem no Portal do candidato.

## <a name="feedback-activity"></a>Atividade de comentários

A Atividade de comentários é opcional. Esta atividade permite que os participantes de entrevista insiram recomendações para um candidato. Eles também podem inserir outros comentários que queiram fazer. Se você ativar a opção **Herdar participantes de comentários da Equipe de Contratação**, o recrutador, o gerente de contratação e os entrevistadores serão inseridos automaticamente na Atividade de comentários. As organizações podem permitir que os entrevistadores exibam os comentários de outras pessoas antes que enviem seus próprios comentários. As organizações também podem permitir que os entrevistadores editem os comentários após o envio.

## <a name="interview-activity"></a>Atividade de entrevista

A Atividade de entrevista é opcional. Essa atividade tem três componentes: disponibilidade do candidato e agenda e comentários. O componente de disponibilidade do candidato permite que você use o email para solicitar a disponibilidade de um candidato. O componente de Agenda fornece a possibilidade de agendar entrevistas com o candidato e a equipe de contratação. Na Atividade do agendador, as seguintes opções podem ser configuradas: **Solicitar a disponibilidade do candidato**, **Reunião online**, e **Enviar email ao candidato**.

- Para enviar email aos candidatos para solicitar a disponibilidade, defina a opção **Solicitar a disponibilidade do candidato** como **Ativado**. Se você definir opção como **Desativado**, a etapa não será exibida no processo de contratação no trabalho.
- Para fazer uma transmissão ao vivo ou uma chamada em conferência usando o Skype for Business, defina o campo **Reunião online** como **Skype for Business**. O link correto **Ingressar na Reunião do Skype** será adicionado à solicitação de reunião para entrevista.
- Para enviar emails aos candidatos para finalizar a agenda, defina a opção **Enviar email ao candidato** como **Ativado**. Se você definir a opção **Desativado**, os candidatos receberão o o agendamento de entrevista somente quando eles entrarem no Portal do candidato.

>[!NOTE]
> - Para todas as entrevistas 1:1, lembretes serão enviados para os entrevistadores a cada 24 horas eles não responderem (aceitar ou rejeitar) à solicitação de entrevista.
> - Para todas as entrevistas de painel, não há lembretes automáticos para responder à solicitação de entrevista. Para disparar um lembrete manualmente, edite a entrevista e utilize a opção **Atualizar e Enviar** para retornar a solicitação para os entrevistadores.

O componente de comentários permite que as pessoas insiram recomendações para um candidato. Eles também podem inserir outros comentários que queiram fazer. Se você ativar a opção **Herdar participantes de comentários da Equipe de Contratação**, o recrutador, o gerente de contratação e os entrevistadores serão inseridos automaticamente no componente de comentários. As organizações podem permitir que os entrevistadores exibam os comentários de outras pessoas antes que enviem seus próprios comentários. As organizações também podem permitir que os entrevistadores editem os comentários após o envio.

## <a name="powerapps-activity"></a>Atividade de PowerApps

A atividade de PowerApps permite que você incorpore um aplicativo do Microsoft PowerApps no processo de contratação. O aplicativo poderá ser necessário para todos os candidatos, candidatos internos somente, candidatos externos somente, ou nenhum candidato. Se o aplicativo for marcado como necessário, ele deve ser concluído antes que se possa avançar para outro estágio. Se o aplicativo não for marcado como necessário, a atividade será uma etapa opcional e será possível avançar para outro estágio mesmo que o aplicativo não tenha sido concluído.

Para salvar a atividade do PowerApps no processo de contratação, você deve inserir um ID do PowerApps. Para encontrar a ID do PowerApps, acesse [PowerApps](https://web.powerapps.com), selecione **Aplicativos** e, em seguida, selecione **Detalhes**.

Se você selecionar a opção **Permitir a adição de participantes a esta atividade** , outros colaboradores poderão ser adicionados a uma solicitação de emprego que use a atividade de PowerApps. Por exemplo, uma organização criou um aplicativo do PowerApps que é uma biblioteca de perguntas de entrevista para funções técnicas. A organização está agora contratando um novo desenvolvedor de software e adicionou a atividade de PowerApps ao processo de contratação para a função de desenvolvedor de software. Se a opção **Permitir a adição de participantes a esta atividade** estiver selecionada, um recrutador ou gerente de contratação que esteja exibindo um candidato para a função do desenvolvedor de software poderá adicionar pessoas à atividade de PowerApps. Essas pessoas poderão então exibir o aplicativo que tem as perguntas de entrevista.

> [!NOTE]
> A atividade de PowerApps está disponível somente com o complemento de Contratação abrangente.

## <a name="youtube-activity"></a>Atividade de YouTube

A atividade de YouTube permite que você compartilhe um vídeo do YouTube como parte do processo de contratação. Para salvar a atividade de YouTube no processo de contratação, você deve especificar a URL do vídeo do YouTube. Quanto à atividade de PowerApps, você pode permitir que os participantes sejam adicionados à atividade. Se você selecionar a opção **Mostrar somente para o candidato**, o vídeo será exibido somente como parte da experiência do candidato. Ele não será exibido no processo de contratação no Attract.

> [!NOTE]
> A atividade de YouTube está disponível somente com o complemento de Contratação abrangente.

## <a name="web-content-activity"></a>Atividade de conteúdo da Web

A atividade de conteúdo da Web permite que você incorpore conteúdo online no processo de contratação. Para salvar a atividade de conteúdo da Web no processo de contratação, você deve especificar a URL do conteúdo. Quanto às atividade de PowerApps e de YouTube, você pode permitir que os participantes sejam adicionados à atividade. Se você selecionar a opção **Mostrar somente para o candidato**, o conteúdo será exibido somente como parte da experiência do candidato. Ele não será exibido no processo de contratação no Attract. É possível selecionar o tamanho do conteúdo exibido.

> [!NOTE]
> A atividade de conteúdo da Web está disponível somente com o complemento de Contratação abrangente.

## <a name="microsoft-forms-activity"></a>Atividade de Microsoft Forms

A atividade de Microsoft Forms permite que você incorpore um formulário do Microsoft Forms no processo de contratação. Os Microsoft Forms permite que você crie testes, pesquisas, e sondagens. Para salvar a atividade de Microsoft Forms no processo de contratação, você deve especificar a URL do formulário. Quanto às atividade de PowerApps, YouTube e conteúdo da Web, você pode permitir que os participantes sejam adicionados à atividade. Se você selecionar a opção **Mostrar somente para o candidato**, o formulário será exibido somente como parte da experiência do candidato. Ele não será exibido no processo de contratação no Attract.

No Microsoft Forms, os autores podem alterar as configurações para permitir que os usuários fora da organização respondam à pesquisa ou teste. Nesse caso, os usuários enviam as respostas de forma anônima. Se quiser ver quem preencheu a pesquisa ou teste, você poderá exigir que os entrevistados insiram seus nomes como parte da pesquisa ou do teste.

> [!NOTE]
> A atividade de Microsoft Forms está disponível somente com o complemento de Contratação abrangente.

