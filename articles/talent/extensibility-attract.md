---
title: Extensibilidade no Attract
description: "Este tópico descreve como você pode estender o aplicativo Microsoft Dynamics 365 for Talent - Attract usando o Microsoft Power Platform."
author: josaw
manager: AnnBe
ms.date: 10/15/2018
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
ms.sourcegitcommit: e890e32049e930b70c2d0aac8aa8206ab999418a
ms.openlocfilehash: 0af60a0aea0f7a5de793631445aaebb37dbb0d74
ms.contentlocale: pt-br
ms.lasthandoff: 10/22/2018

---

# <a name="extensibility-in-attract"></a>Extensibilidade no Attract

[!include[banner](../includes/banner.md)]

O Microsoft Dynamics 365 for Talent é criado sobre a plataforma do CDS (Common Data Service) para Aplicativos e pode ser estendido de várias formas usando o Microsoft Power Platform e os recursos oferecidos pelo CDS para Aplicativos. Portanto, você pode configurar e personalizar o sistema usando o Microsoft PowerApps e o Microsoft Flow. Você também pode obter análises adicionais sobre pessoas usando o Microsoft Power BI. Além disso, as novas atividades personalizados, como as atividades do PowerApps e conteúdo da Web (iframe), tornam o processo de contratação mais adaptável do que nunca. Usando essas atividades, você pode personalizar o processo da contratação de acordo com suas necessidades e processos de negócios, bem como garantir que a equipe de contratação e os candidatos tenham uma experiência completa, personalizada.

## <a name="take-advantage-of-the-microsoft-power-platform"></a>Aproveite o Microsoft Power Platform 

Como todos os dados do Attract residem no Common Data Service para Aplicativos, você pode usar ferramentas do Microsoft Power Platform para incorporar suas necessidades de negócios exclusivas no Attract.

### <a name="powerapps"></a>PowerApps

Você pode usar o PowerApps para criar facilmente aplicativos que se conectam a dados do Attract e que usam expressões como as expressões do Microsoft Excel para adicionar lógica. Os aplicativos que você cria usando o PowerApps podem ser executados na Web e nos dispositivos Apple iOS e Google Android.

Por exemplo, você pode promover feiras de carreira universitária para recrutadores, criando um aplicativo leve que permita examinar currículos e alimentar candidatos a uma posição no Attract. Outra opção é criar um aplicativo que ajude a atender às necessidades de conformidade da sua organização. Para obter mais informações sobre o PowerApps e como usá-lo para criar aplicativos, consulte [Integrar dados ao Common Data Service para Aplicativos](https://docs.microsoft.com/en-us/powerapps).

### <a name="microsoft-flow"></a>Microsoft Flow 

Você pode usar o Microsoft Flow para criar fluxos de trabalho automatizados que são executados sobre dados do Attract. É fácil conectar-se a centenas de aplicativos e serviços conhecidos sem precisar escrever código. Ao criar fluxos que interagem com entidades de trabalho, de candidatos e de solicitações de emprego do Attract no Common Data Service para Aplicativos, você pode automatizar várias ações. Por exemplo, quando um candidato aceita uma oferta, uma notificação pode ser enviada a uma equipe de integração ou a notícia pode ser anunciada no Twitter. Para obter mais informações sobre fluxos, consulte a [documentação do Microsoft Flow](https://docs.microsoft.com/en-us/flow/).

### <a name="power-bi"></a>Power BI

O Power BI permite criar e exibir relatórios personalizados e painéis que oferecem insight mais profundo de dados do Attract. Para obter mais informações sobre o Power BI e sobre como criar relatórios e painéis interativos, consulte a [documentação do Power BI](https://docs.microsoft.com/en-us/power-bi/).

### <a name="custom-activities"></a>Personalizar atividades 

Você pode adicionar atividades personalizadas, como aplicativos do PowerApps e atividades de conteúdo da Web (iframe), em nível do modelo de processo de trabalho ou ao criar um novo trabalho. Essas atividades permitem personalizar o processo de contratação e trazer lógica de negócios exclusiva da sua organização para o Attract.

#### <a name="powerapps-activity"></a>Atividade do PowerApps 

A atividade do PowerApps permite ao criador de um trabalho ou do modelo de processo de trabalho inserir um aplicativo do PowerApps no fluxo de contratação. Após criar e publicar o aplicativo, você pode inserir a ID do aplicativo nas configurações da atividade. Usando um aplicativo do PowerApps, você pode ler e gravar dados no Common Data Service para Aplicativos. Você pode até vincular o aplicativo a um fluxo. Por exemplo, você tem um aplicativo que os recrutadores utilizam para preencher um formulário enquanto conduzem entrevistas por telefone. Nesse caso, você pode vincular o aplicativo a um fluxo que avalia se um candidato pode avançar mais no processo de solicitação de emprego. Esse tipo de atividade pode ser exibido somente por membros da equipe de contratação. Para obter mais informações sobre como configurar a atividade do PowerApps, consulte [Atividades no Attract](./activities-attract.md).

> [!NOTE]
> A atividade de PowerApps está disponível somente com o complemento de Contratação abrangente.

#### <a name="web-content-iframe-activity"></a>Atividade de conteúdo da Web (iframe)

A atividade de conteúdo da Web (iframe) permite que você insira uma solução personalizada da Web que você criou no processo interno de contratação ou o portal do Candidato. Você pode ler e gravar dados diretamente do Common Data Service para Aplicativos. Você também pode personalizar a solução de forma que dispare fluxos ou aproveite funções do Microsoft Azure. Para obter mais informações sobre como configurar a atividade de conteúdo da Web, consulte [Atividades no Attract](./activities-attract.md).

> [!NOTE]
> A atividade de conteúdo da Web está disponível somente com o complemento de Contratação abrangente.

