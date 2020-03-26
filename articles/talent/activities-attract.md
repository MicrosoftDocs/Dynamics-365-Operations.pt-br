---
title: Adicionar atividades a um processo de contratação
description: Este tópico fornece informações sobre os vários tipos de atividades que você pode adicionar a um processo de contratação no Microsoft Dynamics 365 Talent - Attract.
author: hasrivas
manager: AnnBe
ms.date: 05/28/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: shielas
ms.search.validFrom: 2018-10-15
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: ce8c0bd74a41b9857538b37d0875583d06e8c11d
ms.sourcegitcommit: 1d5a4f70a931e78b06811add97c1962e8d93689b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/13/2020
ms.locfileid: "3124764"
---
# <a name="add-activities-to-a-hiring-process"></a>Adicionar atividades a um processo de contratação

[!include [banner](includes/banner.md)]

As atividades podem ser adicionados como parte do processo de contratação no Microsoft Dynamics 365 Talent: Attract. As atividades podem ser adicionadas a um modelo de processo ou podem ser adicionadas diretamente ao processo de contratação no trabalho. Quando um trabalho é definidos, um modelo de processo é selecionado e as atividades que estão incluídas no modelo são aplicadas ao trabalho. Se um modelo não for selecionado, o modelo padrão será usado. O processo de contratação também poderá ser modificado no trabalho depois que o modelo for aplicado.

> [!NOTE] 
> Os modelos de processo estão disponíveis com o complemento de Contratação abrangente. Para obter mais informações, consulte [Qual versão do Microsoft Dynamics 365 Talent - Attract](./attract-comprehensive-hiring.md).

## <a name="prospect-activity"></a>Atividade do candidato ao trabalho

A atividade do candidato ao trabalho controla se os candidatos podem ser adicionados a um trabalho. Por padrão, os candidatos podem ser adicionados a um trabalho. Para desativar a Atividade do candidato ao trabalho, defina a opção **Habilitar candidatos** como **Desativado**. Quando uma Atividade do candidato ao trabalho é ativada, os gerentes de contratação podem adicionar e exibir candidatos, e a guia **Candidato ao trabalho** é exibida no trabalho.

> [!NOTE]
> Para permitir que os candidatos sejam adicionados a um trabalho no LinkedIn, você deve definir a opção **Habilitar colaboradores potenciais** com **Ativado**.

## <a name="application-activity"></a>Atividade de solicitação de emprego

A Atividade de solicitação de emprego é necessária em modelo do processo de contratação. Para enviar emails aos candidatos quando eles enviam suas solicitações ou são adicionados ao Estágio de solicitação de emprego, defina a opção **Enviar email ao candidato** como **Ativado**.

## <a name="interview-schedule-and-feedback-activity"></a>Agendamento de entrevistas e atividade de comentários

Essa atividade tem três componentes: solicitação de disponibilidade do candidato, agenda e comentários. Use a atividade da entrevista no modelo de trabalho se você deseja incluir a solicitação de disponibilidade do candidato, agenda e comentários como parte do processo em vez de usá-las individualmente como parte do processo de contratação. Para obter mais informações, consulte [Agendamento de entrevistas e comentários](interview-scheduling-feedback.md).

## <a name="power-apps-activity"></a>Atividade de Power Apps

A atividade do Power Apps permite que você incorpore um aplicativo do Microsoft Power Apps no processo de contratação. O aplicativo poderá ser necessário para todos os candidatos, candidatos internos somente, candidatos externos somente, ou nenhum candidato. Se o aplicativo for marcado como necessário, ele deve ser concluído antes que se possa avançar para outro estágio. Para ser considerado concluído, o campo **Status da solicitação de emprego** deve ser definido como **Concluído**. Este campo está localizado na entidade JobApplicationActivity, de modo que o aplicativo Power Apps precisará atualizar esse campo para que seja possível avançar de estágio. Se o aplicativo não for marcado como necessário, a atividade será uma etapa opcional e será possível avançar para outro estágio mesmo que o aplicativo não tenha sido concluído.

Para salvar a atividade do Power Apps no processo de contratação, você deve inserir uma ID do Power Apps. Para localizar a ID do Power Apps ID, acesse [Power Apps](https://web.powerapps.com), selecione **Aplicativos** e **Detalhes**.

Por padrão, a atividade do Power Apps está disponível para o Gerente de contratação, o Recrutador e seus representantes. Se você selecionar a opção **Permitir a adição de participantes a esta atividade**, outros participantes da equipe de contratação poderão ser adicionados a um aplicativo que usa a atividade do Power Apps. Por exemplo, uma organização criou um aplicativo do Power Apps que é uma biblioteca de perguntas de entrevista para funções técnicas. A organização está contratando um novo desenvolvedor de software e adicionou a atividade do Power Apps ao processo de contratação para a função de desenvolvedor de software. Se a opção **Permitir a adição de participantes a esta atividade** estiver selecionada, um recrutador ou gerente de contratação que esteja exibindo um candidato à função de desenvolvedor de software poderá adicionar entrevistadores à atividade do Power Apps. Essas pessoas poderão então exibir o aplicativo que tem as perguntas de entrevista.

> [!NOTE]
> A atividade de Power Apps está disponível somente com o complemento de Contratação abrangente. Para obter mais informações, consulte [Qual versão do Microsoft Dynamics 365 Talent - Attract](./attract-comprehensive-hiring.md).

## <a name="youtube-activity"></a>Atividade de YouTube

A atividade de YouTube permite que você compartilhe um vídeo do YouTube como parte do processo de contratação. Para salvar a atividade de YouTube no processo de contratação, você deve especificar a URL do vídeo do YouTube. Você pode optar por exibir o conteúdo para a **Equipe de contratação**, os **Candidatos internos somente**, os **Candidatos externos somente** ou **Todos os candidatos**. Como no caso da atividade do Power Apps, você pode permitir que os participantes da equipe de contratação sejam adicionados à atividade. Se optar por exibir o conteúdo aos candidatos, o vídeo será exibido somente como parte da experiência do candidato e não no processo de contratação.

> [!NOTE]
> A atividade de YouTube está disponível somente com o complemento de Contratação abrangente. Para obter mais informações, consulte [Qual versão do Microsoft Dynamics 365 Talent - Attract](./attract-comprehensive-hiring.md).

## <a name="web-content-activity"></a>Atividade de conteúdo da Web

A atividade de conteúdo da Web permite que você incorpore conteúdo online no processo de contratação. Para salvar a atividade de conteúdo da Web no processo de contratação, você deve especificar a URL do conteúdo. Você pode optar por exibir o conteúdo para a **Equipe de contratação**, os **Candidatos internos somente**, os **Candidatos externos somente** ou **Todos os candidatos**. Como no caso das atividades do Power Apps e do YouTube, você pode permitir que os participantes da equipe de contratação sejam adicionados à atividade. Se escolher exibir o conteúdo aos candidatos, o conteúdo da Web será exibido apenas como parte da experiência do candidato e não no processo de contratação. É possível escolher o tamanho do conteúdo exibido.

> [!NOTE]
> A atividade de conteúdo da Web está disponível somente com o complemento de Contratação abrangente. Para obter mais informações, consulte [Qual versão do Microsoft Dynamics 365 Talent - Attract](./attract-comprehensive-hiring.md).

## <a name="microsoft-forms-activity"></a>Atividade de Microsoft Forms

A atividade do Microsoft Forms permite que você incorpore uma atividade do Microsoft Forms no processo de contratação. Os Microsoft Forms permite que você crie testes, pesquisas, e sondagens. Para salvar a atividade do Microsoft Forms no processo de contratação, você deve especificar a URL do formulário. Você pode optar por exibir o conteúdo para a **Equipe de contratação**, os **Candidatos internos somente**, os **Candidatos externos somente** ou **Todos os candidatos**. Como no caso das atividades do Power Apps, do YouTube e do conteúdo da Web, você pode permitir que os participantes da equipe de contratação sejam adicionados à atividade. Se escolher exibir o conteúdo aos candidatos, o formulário será exibido apenas como parte da experiência do candidato e não no processo de contratação.

No Microsoft Forms, os autores podem alterar as configurações para permitir que os usuários fora da organização respondam à pesquisa ou teste. Nesse caso, os usuários enviam as respostas de forma anônima. Se quiser ver quem preencheu a pesquisa ou teste, você poderá exigir que os entrevistados insiram seus nomes como parte da pesquisa ou do teste.

> [!NOTE]
> A atividade de Microsoft Forms está disponível somente com o complemento de Contratação abrangente. Para obter mais informações, consulte [Qual versão do Microsoft Dynamics 365 Talent - Attract](./attract-comprehensive-hiring.md).

## <a name="offer-activity"></a>Atividade Oferta

O modelo de processo e contratação requer a atividade Oferta. Para usar o aplicativo Gerenciamento de Ofertas integrado, defina **Iniciar Aplicativo Gerenciamento de Ofertas em Preparar Oferta** como **Ativado**. Se esta configuração estiver desativada, o candidato não aparecerá no aplicativo Oferta, portanto será necessário rastrear as atualizações à atividade da oferta de um candidato manualmente. Para definir se os gerentes de contratação podem preparar a oferta do candidato no aplicativo Oferta, defina **Os gerentes de contratação podem preparar a oferta** como **Ativado**. Se o trabalho tiver várias posições associadas a ele, você poderá decidir se deseja preparar várias ofertas em relação ao mesmo número de posição. Se quiser permitir somente uma oferta por posição por trabalho, defina **Permitir que as posições sejam reutilizadas no trabalho** como **Desativado**.

> [!NOTE]
> O aplicativo Gerenciamento de Ofertas integrado está disponível somente com o complemento de Contratação abrangente. Para obter mais informações, consulte [Qual versão do Microsoft Dynamics 365 Talent - Attract](./attract-comprehensive-hiring.md).


