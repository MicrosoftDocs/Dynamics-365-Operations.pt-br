---
title: Fornecer candidatos com o LinkedIn Recruiter no Microsoft Dynamics 365 for Talent - Attract
description: Use a integração com o LinkedIn fornecida pelo Microsoft Dynamics 365 for Talent - Attract para fornecer candidatos a trabalho por meio do LinkedIn Recruiter.
author: andreabichsel
manager: AnnBe
ms.date: 07/08/2019
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
ms.openlocfilehash: 14aba16fa81a8f25d0f88247319254407d428b2a
ms.sourcegitcommit: 7c49475402632069685df714546770d30804af7f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/11/2019
ms.locfileid: "1739440"
---
# <a name="source-candidates-with-linkedin-recruiter"></a>Fornecer candidatos com o LinkedIn Recruiter
[!include[banner](../includes/banner.md)]

O LinkedIn e a maior rede profissional online do mundo, dando a você acesso aos melhores talentos do mundo. O Microsoft Dynamics 365 for Talent: Attract permite que você forneça candidatos diretamente do LinkedIn. Portanto, está mais fácil do que nunca encontrar os talentos de que você precisa para preencher os cargos abertos. Depois de configurar a conexão com o LinkedIn pelo Attract, você poderá exibir candidatos potenciais do LinkedIn aos cargos e exportá-los para o Attract com apenas um clique.

Se você não tiver esse recurso, contate seu administrador. Antes que possa aproveitar ao máximo o LinkedIn Recruiter por meio do Attract, seu administrador deve [configurar a integração com o LinkedIn](./attract-admin-linkedin.md). Você poderá então configurar sua conexão com o LinkedIn Recruiter e começar a encontrar candidatos.

## <a name="set-up-your-connection-with-linkedin-recruiter"></a>Configurar sua conexão com o LinkedIn Recruiter

Antes de começar a trabalhar com o LinkedIn Recruiter pelo Attract, você deverá configurar sua conexão com o LinkedIn Recruiter. Para esta etapa, suas credenciais do LinkedIn Recruiter serão necessárias.

1. Selecione o botão **Configurações** (ícone de engrenagem) no canto superior direito da página.
2. Selecione **Configurações do usuário**.
3. Na guia **Conexões**, selecione **Conectar** ao lado de **LinkedIn**. Siga as instruções fornecidas pelo LinkedIn.

    ![[Configurar a conexão ao LinkedIn Recruiter por meio do Attract](./media/attract-set-up-linkedin-recruiter-connection.png)](./media/attract-set-up-linkedin-recruiter-connection.png)

## <a name="view-linkedin-candidates-in-attract"></a>Exibir candidatos do LinkedIn no Attract

Depois que estiver conectado ao LinkedIn Recruiter, você poderá exibir perfis do LinkedIn de candidatos no Attract.

1. No Attract, selecione **Trabalhos** ou **Grupos de talentos** à esquerda e, em seguida, selecione um candidato.

    ![[Exibir candidatos do LinkedIn no Attract](./media/attract-view-linkedin-candidates.png)](./media/attract-view-linkedin-candidates.png)

2. O perfil do candidato, selecione a guia **LinkedIn**. Você poderá exibir o perfil do candidato, juntamente com o histórico do InMail e o histórico de observações do LinkedIn.

Aqui, é possível salvar o candidato em um projeto do LinkedIn Recruiter, enviar inMail ou usar a opção Atualizar-me para definir um alerta no LinkedIn Recruiter.

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

    ![[Exibir informações do Attract por meio do LinkedIn Recruiter](./media/attract-view-information-from-linkedin-recruiter.png)](./media/attract-view-information-from-linkedin-recruiter.png)

> [!NOTE]
> Os dados do candidato e da solicitação de emprego não serão sincronizados no LinkedIn Recruiter se o candidato não passar do estágio de Colaborador potencial.

## <a name="view-linkedin-talent-pools"></a>Exibir grupos de talentos do LinkedIn

Se os candidatos concordarem em compartilhar seus perfis do LinkedIn com qualquer usuário em sua organização, um novo registro do candidato será criado no Attract. Esses candidatos serão exibidos em um grupo de talentos do LinkedIn criado pelo sistema.

1. No Attract, selecione **Grupos de talentos** à esquerda.
2. Selecione o grupo de talentos do LinkedIn. Você verá uma lista de candidatos e seus perfis stub do LinkedIn. Os perfis stub contêm o nome e sobrenome do candidato e um endereço de email se o candidato optou por compartilhá-los.

## <a name="see-also"></a>Consulte também

[Perguntas frequentes sobre o LinkedIn](./attract-linkedin-faq.md)

[Configurar a integração com o LinkedIn](./attract-admin-linkedin.md)

[Criar trabalhos](./creating-jobs-attract.md)

[Lançar trabalhos no LinkedIn do Attract](./attract-post-jobs-to-linkedin.md)

[Solucionar problemas de integração com o LinkedIn](./attract-troubleshoot-linkedin.md)
