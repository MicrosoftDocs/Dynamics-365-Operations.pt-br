---
title: Contratar candidatos com o LinkedIn Recruiter no Attract
description: Use a integração com o LinkedIn fornecida pelo Microsoft Dynamics 365 Talent - Attract para contratar candidatos a trabalho por meio do LinkedIn Recruiter.
author: andreabichsel
manager: AnnBe
ms.date: 08/31/2020
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
ms.search.industry: ''
ms.author: anbichse
ms.search.validFrom: 2018-10-15
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: 96e4660c4958bf5f2a0910bfad770e1e713f800f
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "4528260"
---
# <a name="source-candidates-with-linkedin-recruiter-in-attract"></a>Contratar candidatos com o LinkedIn Recruiter no Attract

[!include [banner](includes/banner.md)]

O LinkedIn e a maior rede profissional online do mundo, dando a você acesso aos melhores talentos do mundo. O Microsoft Dynamics 365 Talent: Attract permite contratar candidatos diretamente no LinkedIn. Portanto, está mais fácil do que nunca encontrar os talentos de que você precisa para preencher os cargos abertos. Depois de configurar a conexão com o LinkedIn pelo Attract, você poderá exibir candidatos potenciais do LinkedIn aos cargos e exportá-los para o Attract com apenas um clique.

Se você não tiver esse recurso, contate seu administrador. Antes que possa aproveitar ao máximo o LinkedIn Recruiter por meio do Attract, seu administrador deve [configurar a integração com o LinkedIn](./attract-admin-linkedin.md). Você poderá então configurar sua conexão com o LinkedIn Recruiter e começar a encontrar candidatos.

>[!IMPORTANT]
>A partir de 1º de julho de 2020, o LinkedIn não oferece mais suporte ao Internet Explorer 11. Os usuários ainda podem acessar o LinkedIn com o Internet Explorer 11, mas serão solicitados a atualizar ou usar um navegador diferente. Para obter mais informações, consulte [Navegadores da Internet com suporte para o LinkedIn](https://www.linkedin.com/help/linkedin/answer/4135/supported-internet-browsers-for-linkedin).

## <a name="set-up-your-connection-with-linkedin-recruiter"></a>Configurar sua conexão com o LinkedIn Recruiter

Antes de começar a trabalhar com o LinkedIn Recruiter pelo Attract, você deverá configurar sua conexão com o LinkedIn Recruiter. Para esta etapa, suas credenciais do LinkedIn Recruiter serão necessárias.

1. Selecione o botão **Configurações** (ícone de engrenagem) no canto superior direito da página.
2. Selecione **Configurações do usuário**.
3. Na guia **Conexões**, selecione **Conectar** ao lado de **LinkedIn**. Siga as instruções fornecidas pelo LinkedIn.

    ![[Configurar conexão para o LinkedIn Recruiter com o Attract](./media/attract-set-up-linkedin-recruiter-connection.png)](./media/attract-set-up-linkedin-recruiter-connection.png)

## <a name="view-linkedin-candidates-in-attract"></a>Exibir candidatos do LinkedIn no Attract

Depois que estiver conectado ao LinkedIn Recruiter, você poderá exibir perfis do LinkedIn de candidatos no Attract.

>[!NOTE]
>Se você tiver uma função de Recrutador atribuída a você, poderá ver as informações completas dos candidatos.<br><br>
>Se você tiver uma função de Gerente de Contratação ou nenhuma função atribuída a você, saia do LinkedIn ou do LinkedIn Recruiter antes de navegar para a guia LinkedIn de um candidato no Attract. Você poderá ver os dados básicos do perfil público do candidato, como nome e sobrenome.

1. No Attract, selecione **Trabalhos** ou **Grupos de talentos** à esquerda e, em seguida, selecione um candidato.

    ![[Exibir candidatos do LinkedIn no Attract](./media/attract-view-linkedin-candidates.png)](./media/attract-view-linkedin-candidates.png)

2. O perfil do candidato, selecione a guia **LinkedIn**. Você poderá exibir o perfil do candidato e o histórico do InMail.

   ![Exibir informações do LinkedIn de um candidato](./media/attract-candidate-linkedin-tab.png)

De lá, você poderá executar as seguintes ações:

- Selecione a guia **Atividades de recrutamento** para exibir:
   
   - Notas do recrutador (públicas e particulares). Por padrão, as anotações são particulares e visíveis somente para o proprietário das anotações.
   - Atividade do InMail (mas não o conteúdo do InMail). Role até a parte inferior da página para exibir a troca do InMail com o cliente potencial e exibir outros usuários na organização que estão interagindo com o cliente potencial.
   - Atividade de rejeição de candidato

- Selecione **Enviar InMail** para enviar o InMail sem sair do Attract.

- Selecione **Salvar em um trabalho** para salvar o trabalho sem sair do Attract.

> [!NOTE]
> O perfil do LinkedIn de um candidato será exibido no Attract quando as informações do Attract do candidato corresponderem às informações do LinkedIn. Veja as regras de correspondência que são usadas:
> 
> 1. Se o endereço de email e a ID do membro do LinkedIn corresponderem no Attract e no LinkedIn, o perfil do candidato será exibido. Os candidatos ainda têm a opção de vincular ou desvincular seu perfil do LinkedIn do Attract.
> 2. Se o endereço de email ou a ID do membro do LinkedIn não corresponderem, uma lista de possíveis candidatos será exibida. Você poderá então selecionar um candidato na lista e vincular o perfil.
> 3. Se não houver boas correspondências, você será notificado que nenhuma correspondência foi encontrada.

## <a name="export-linkedin-candidates-to-attract-with-one-click"></a>Exportar candidatos do LinkedIn para o Attract com um clique

Ao examinar os candidatos no LinkedIn Recruiter, você poderá exportá-los para os trabalhos que tiver em aberto no Attract no momento. Para esta etapa, são necessárias permissões de Recrutador ou de Gerente de contratação no Attract. Para obter mais informações sobre funções no Attract, consulte [Gerenciamento de segurança e funções no Attract](https://docs.microsoft.com/dynamics365/unified-operations/talent/security-attract).

Você também deve certificar-se de que o trabalho tenha um estágio de Colaborador potencial. Para obter mais informações, consulte [Atividade de colaborador potencial](./activities-attract.md#prospect-activity).

1. No Attract, crie um trabalho, atribua as funções adequadas e ative o trabalho.
2. No LinkedIn Recruiter, encontre um bom candidato para o trabalho, e acesse o perfil do candidato.
3. Na caixa de pesquisa de trabalhos no cartão de contato, encontre o trabalho usando o título ou a ID do Trabalho que foi ativado no Attract. Se não encontrar o trabalho, selecione **Alterar ATS** para encontrar a instância correta do Attract.
4. Selecione o trabalho e depois selecione **Exportar**.
5. No Attract, abra o trabalho. O candidato exportado será exibido na guia **Colaborador potencial** do trabalho.

## <a name="view-attract-information-in-linkedin-recruiter"></a>Exibir informações do Attract no LinkedIn Recruiter

No LinkedIn Recruiter, você poderá rastrear se um candidato se candidatou a outros trabalhos em sua organização, acompanhar em que parte ele está em estágios diferentes das solicitações de emprego e exibir os comentários do Attract.

1. Abra o LinkedIn Recruiter e selecione o perfil de um candidato.
2. Passe o mouse sobre **Em ATS**.
3. Selecione uma das seguintes opções para exibir as informações do candidato que estão armazenadas no Attract:

    - **Trabalho e Status** — consulte os trabalhos dos quais o candidato faz parte, o status mais recente e como o candidato é progredindo em cada trabalho.
    - **Comentários da entrevista** — veja os comentários que os entrevistadores enviaram no Attract.
    - **Observações** — veja as observações que foram inseridas para o candidato no Attract.

    ![[Exibir informações do Attract no LinkedIn Recruiter](./media/attract-view-information-from-linkedin-recruiter.png)](./media/attract-view-information-from-linkedin-recruiter.png)

> [!NOTE]
> Os dados do candidato e da solicitação de emprego não serão sincronizados no LinkedIn Recruiter se o candidato não passar do estágio de Colaborador potencial.

## <a name="view-linkedin-talent-pools"></a>Exibir grupos de talentos do LinkedIn

Se os candidatos concordarem em compartilhar seus perfis do LinkedIn com qualquer usuário em sua organização, um novo registro do candidato será criado no Attract. Esses candidatos serão exibidos em um grupo de talentos do LinkedIn criado pelo sistema.

1. No Attract, selecione **Grupos de talentos** à esquerda.
2. Selecione o grupo de talentos do LinkedIn. Você verá uma lista de candidatos e seus perfis stub do LinkedIn. Os perfis stub contêm o nome e sobrenome do candidato e um endereço de email se o candidato optou por compartilhá-los.

## <a name="see-also"></a>Consulte também

[Perguntas frequentes sobre a integração do Attract com o LinkedIn](./attract-linkedin-faq.md)

[Configurar a integração com o LinkedIn para o Microsoft Dynamics 365 Talent - Attract](./attract-admin-linkedin.md)

[Criar, aprovar e lançar trabalhos no Attract](./creating-jobs-attract.md)

[Postar trabalhos no LinkedIn usando o Microsoft Dynamics 365 Talent - Attract](./attract-post-jobs-to-linkedin.md)

[Solucionar problemas de integração entre o LinkedIn e o Microsoft Dynamics 365 Talent - Attract](./attract-troubleshoot-linkedin.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]