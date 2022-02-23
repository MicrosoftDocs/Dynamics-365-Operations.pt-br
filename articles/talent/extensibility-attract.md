---
title: Extensibilidade no Attract
description: Este tópico descreve como você pode estender o Microsoft Dynamics 365 Talent - Attract usando o Microsoft Power Platform.
author: andreabichsel
manager: AnnBe
ms.date: 03/18/2019
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
ms.author: anbichse
ms.search.validFrom: 2018-10-15
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: ddc6593431585ed79cc15f7ede5daf856f11b959
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "4527233"
---
# <a name="extensibility-in-attract"></a>Extensibilidade no Attract

[!include [banner](includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

O Microsoft Dynamics 365 Talent foi desenvolvido com base no Common Data Service e pode ser estendido de várias maneiras, usando o Microsoft Power Platform e os recursos oferecidos pelo Common Data Service. Portanto, você pode configurar e personalizar o sistema usando o Microsoft Power Apps e o Microsoft Power Automate. Você também pode obter análises adicionais sobre pessoas usando o Microsoft Power BI. Além disso, as novas atividades personalizadas, como Power Apps e atividades de conteúdo da Web (iframe), tornam o processo de contratação mais adaptável do que nunca. Usando essas atividades, você pode personalizar o processo da contratação de acordo com suas necessidades e processos de negócios, bem como garantir que a equipe de contratação e os candidatos tenham uma experiência completa, personalizada.

## <a name="extending-option-sets-in-attract"></a>Extensão dos conjuntos de opções no Attract

Um **Conjunto de opções** (lista de opções) é um tipo de campo que pode ser incluído em uma entidade. Define um conjunto de opções. Quando um conjunto de opções é exibido em um formulário, ele usa um controle de lista suspensa.  No Attract, existem vários campos que são conjuntos de opções.  Estamos começando a apresentar a capacidade de estender os conjuntos de opções, começando com os campos Motivo da rejeição, Tipo de emprego e Tipo de senioridade.   Além disso, você pode adicionar rótulos de exibição localizados para as opções adicionadas. Para obter mais informações, consulte [Personalizar rótulos de conjuntos de opções](https://docs.microsoft.com/powerapps/developer/common-data-service/customize-labels-support-multiple-languages).

> [!NOTE]
> A postagem de trabalho na funcionalidade do LinkedIn requer o uso de campos **Tipo de emprego** e **Tipo de senioridade** na página **Detalhes de trabalho**. Os valores padrão nesses campos são compatíveis com LinkedIn e são exibidos quando o trabalho é postado. Portanto, se estiver postando trabalhos no LinkedIn e modificar os valores de conjunto de opções existentes para esses campos, o trabalho será postado, mas o LinkedIn não exibirá os valores **Tipo de trabalho** e **Tipo de senioridade** personalizados.  

Abaixo estão listadas as etapas para atualizar o campo **Motivo da rejeição** com valores específicos para sua empresa.  

1. Para estender o conjunto de opções **Motivo da rejeição**, navegue até o [site de administração do Power Apps](https://admin.powerapps.com).
2. Talvez seja solicitado que você faça logon na sua conta. Forneça suas credenciais de ID de usuário e senha usadas para entrar no Dynamics365 e/ou Office365 e clique em **Próximo**.
3. Na guia **Ambientes**, selecione o ambiente que você deseja gerenciar e clique duas vezes para chegar à guia **Detalhes**.
4. Na guia **Detalhes**, selecione **Centro de Administração do Dynamics 365**.
5. Selecione a instância que você deseja modificar e selecione **Abrir**.
6. Navegue até **Configurações** e **Personalizações** e selecione **Personalizar o sistema**.
7. Encontre a entidade para a qual você deseja expandir o conjunto de opções selecionando **Entidades** e expandindo o grupo. Neste exemplo, será a **Entidade de solicitação de emprego**.
8. Vá para o campo para o qual você deseja estender o conjunto de opções selecionando a opção **Campos**. Neste exemplo, será a **msdyn_rejectionreason**. Clique duas vezes no campo.
9. No campo **Conjunto de opções**, selecione **Editar**.
10. Selecione o ícone **+**.
11. Insira um **Rótulo**.  (Deve ser um valor único - sem cópias).
12. Selecione **Salvar**.
13. Selecione **Publicar** na parte superior da página.

## <a name="take-advantage-of-the-microsoft-power-platform"></a>Tire proveito do Microsoft Power Platform 

Como todos os dados do Attract residem no Common Data Service, você pode usar ferramentas do Microsoft Power Platform para incorporar as necessidades exclusivas de seu negócio no Attract.

### <a name="power-apps"></a>Power Apps

Você pode usar o Power Apps para criar facilmente aplicativos que se conectam a dados do Attract e que usam expressões como as do Microsoft Excel para adicionar lógica. Os aplicativos que você cria usando o Power Apps podem ser executados na Web e em dispositivos Apple iOS e Google Android.

Por exemplo, você pode promover feiras de carreira universitária para recrutadores, criando um aplicativo leve que permita examinar currículos e alimentar candidatos a uma posição no Attract. Outra opção é criar um aplicativo que ajude a atender às necessidades de conformidade da sua organização. Para obter mais informações sobre o Power Apps e como usá-lo para criar aplicativos, consulte [Integrar dados no Common Data Service](https://docs.microsoft.com/powerapps).

### <a name="microsoft-power-automate"></a>Microsoft Power Automate 

Você pode usar o Microsoft Power Automate para criar fluxos de trabalho automatizados executados com base em dados do Attract. É fácil conectar-se a centenas de aplicativos e serviços conhecidos sem precisar escrever código. Ao criar fluxos que interagem com as entidades de Trabalho, Candidato e Solicitação de emprego do Attract no Common Data Service, você pode automatizar várias ações. Por exemplo, quando um candidato aceita uma oferta, uma notificação pode ser enviada a uma equipe de integração ou a notícia pode ser anunciada no Twitter. Para obter mais informações sobre fluxos, consulte a [documentação do Microsoft Power Automate](https://docs.microsoft.com/flow/).

### <a name="power-bi"></a>Power BI

O Power BI permite criar e exibir relatórios e painéis personalizados que oferecem uma visão mais detalhada dos dados do Attract. Para obter mais informações sobre o Power BI e como criar relatórios e painéis interativos, consulte a [documentação do Power BI](https://docs.microsoft.com/power-bi/).

### <a name="custom-activities"></a>Personalizar atividades 

Você pode adicionar atividades personalizadas, como aplicativos do Power Apps e atividades de conteúdo da Web (iframe), em nível do modelo de processo de trabalho ou ao criar um novo trabalho. Essas atividades permitem personalizar o processo de contratação e trazer lógica de negócios exclusiva da sua organização para o Attract.

#### <a name="power-apps-activity"></a>Atividade de Power Apps 

A atividade do Power Apps permite que o criador de um trabalho ou do modelo de processo de trabalho insira um aplicativo do Power Apps no fluxo de contratação. Após criar e publicar o aplicativo, você pode inserir a ID do aplicativo nas configurações da atividade. Usando um aplicativo do Power Apps, você pode ler e gravar dados no Common Data Service. Você pode até vincular o aplicativo a um fluxo. Por exemplo, você tem um aplicativo que os recrutadores utilizam para preencher um formulário enquanto conduzem entrevistas por telefone. Nesse caso, você pode vincular o aplicativo a um fluxo que avalia se um candidato pode avançar mais no processo de solicitação de emprego. Esse tipo de atividade pode ser exibido somente por membros da equipe de contratação. Para obter mais informações sobre como configurar a atividade do Power Apps, consulte [Atividades em processos de contratação](./activities-attract.md).

> [!NOTE]
> A atividade de Power Apps está disponível somente com o complemento de Contratação abrangente.

#### <a name="web-content-iframe-activity"></a>Atividade de conteúdo da Web (iframe)

A atividade de conteúdo da Web (iframe) permite que você insira uma solução personalizada da Web que você criou no processo interno de contratação ou o portal do Candidato. Você pode ler e gravar dados diretamente do Common Data Service. Você também pode personalizar a solução para que ela dispare fluxos ou aproveite as funções do Microsoft Azure. Para obter mais informações sobre como configurar a atividade de conteúdo da Web, consulte [Atividades em processos de contratação](./activities-attract.md).

> [!NOTE]
> A atividade de conteúdo da Web está disponível somente com o complemento de Contratação abrangente.
