---
title: Configurar seu site de carreiras no Microsoft Dynamics 365 Talent - Attract
description: Este tópico fornece uma visão geral da funcionalidade do site de carreiras voltada para o candidato no Microsoft Dynamics 365 Talent - Attract.
author: hasrivas
manager: AnnBe
ms.date: 03/20/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: hasrivas
ms.search.validFrom: 2019-02-12
ms.dyn365.ops.version: AX 7.1.0, Talent April 2018 update
ms.openlocfilehash: ec5fe31c6547b008b29e656729c35863d90bffc1
ms.sourcegitcommit: f87de0f949b5d60993b19e0f61297f02d42b5bef
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/24/2019
ms.locfileid: "2026270"
---
# <a name="set-up-your-career-site"></a>Configurar seu site de carreiras

[!include[banner](../includes/banner.md)]

Este tópico fornece uma visão geral da funcionalidade do site de carreiras voltada para o candidato no Microsoft Dynamics 365 Talent: Attract. Ele também explica como configurar esta funcionalidade.

O Attract fornece um site de carreiras para cada ambiente em um locatário. Por exemplo, se uma organização tiver um ambiente de desenvolvimento e um ambiente de teste, um site de carreiras será provisionado para o ambiente de desenvolvimento e outro site de carreiras será provisionado para o ambiente de teste. Cada site de carreiras é totalmente isolado e tem seu próprio mecanismo de autenticação. Os trabalhos e os perfis do candidato não são compartilhados entre sites de carreiras.

Por padrão, o site de carreiras é público. Portanto, os candidatos podem exibir todos os trabalhos que estão marcados como externos sem precisar fazer logon. Entretanto, todas a outras ações exigem que os candidatos façam logon.

## <a name="career-site-management"></a>Gerenciamento do site de carreiras

Para definir os valores dos itens a seguir, entre no Attract como administrador, selecione **Centro de Administração** no menu **Configurações** (o símbolo de engrenagem) e selecione a guia **Informações sobre a empresa**.

-   **Nome da organização** - O nome da organização aparece na barra de navegação na parte superior do site de carreiras. Ao selecionar o nome da organização, os candidatos vão para uma página que lista todos os trabalhos abertos.

-   **Logotipo organizacional** - Uma imagem do logotipo organizacional aparece na parte superior esquerda do site de carreiras. Ao selecionar a imagem do logotipo, os candidatos vão para uma página que lista todos os trabalhos abertos.

    > [!NOTE] 
    > A imagem de logotipo que aparece no site de carreiras tem uma altitude fixa de 20 pixels (px). A imagem que você adiciona no Centro de administração é ajustada. Portanto, dependendo da imagem, a largura pode mudar.
 
Para definir os valores dos itens a seguir, entre no Attract como administrador, selecione **Centro de Administração** no menu **Configurações** e selecione a guia **Gerenciamento do site de carreiras**.

-   **Otimização do mecanismo de pesquisa** - Quando habilitada, todos os trabalhos públicos postados para o site de carreiras do Attract serão pesquisados usando mecanismos de pesquisa, como o Bing e o Google. 

    > [!NOTE] 
    > Pode haver um atraso entre ativar essa configuração e os resultados da pesquisa, dependendo do mecanismo de pesquisa que você está usando.
    
-   **Termos e condições** - Quando habilitada, todos os candidatos devem concordar com os termos e condições da organização ao candidatarem-se a um trabalho. O administrador do Attract pode configurar seu próprio texto de consentimento assim como o link para a página de termos e condições. 

        
## <a name="career-site-urls"></a>URLs do site de carreiras

A lista a seguir contém as URLs do site de carreiras comumente usadas e como acessá-las.

-   **URL da página inicial do site de carreira** - Para visualizar a URL da página inicial do site de carreira, entre no Attract como administrador, selecione **Centro de administração** no menu **Configurações** e selecione a guia **Gerenciamento do site de carreiras**.

-   **URL da solicitação de lançamento de trabalho individual** - Ao [postar um trabalho externo](Creating-jobs-Attract.md#postings) pela primeira vez, você pode copiar o link **Solicitar** do Attract. A URL para esse link estará neste formato: [https://jobs.talent.dynamics.com/jobs/\<company_name\>/\<environment_number\>/\<job_number\>/apply](https://jobs.talent.dynamics.com/jobs/%3ccompany_name%3e/%3cenvironment_number%3e/%3cjob_number%3e/apply)

-   **URL de lançamento de trabalho individual** - A URL de lançamento de trabalho é uma subsequência da URL de solicitação. Ela consiste em tudo até o número de trabalho. Assim, para a URL de solicitação precedente, a URL de lançamento de trabalho é [https://jobs.talent.dynamics.com/jobs/\<company_name\>/\<environment_number\>/\<job_number\>](https://jobs.talent.dynamics.com/jobs/%3ccompany_name%3e/%3cenvironment_number%3e/%3cjob_number%3e)

## <a name="authentication-options"></a>Opções de autenticação

Os candidatos têm as seguintes opções de logon para um site de carreiras do Attract:

-   Conta pessoal:

    -   LinkedIn

    -   Microsoft

    -   Google

    -   Facebook

-   Conta corporativa ou de estudante:

    -   Microsoft Azure Active Directory (Azure AD)

O logon do Azure AD se destina somente a candidatos internos. Portanto, ele só funciona para candidatos internos que usam suas credenciais do Azure AD da empresa. Por exemplo, um candidato que no momento é um funcionário da Contoso Ltd deseja candidatar-se a um trabalho em uma empresa não relacionada, a Alpine Ski House. Nesse caso, o logon será malsucedido se o funcionário tentar usar as credenciais do Azure AD da Contoso Ltd. 

Os candidatos deverão entrar usando o Azure AD se o trabalho que estão visualizando ou para o qual estão se candidatando estiver listado como somente interno.

## <a name="create-and-maintain-a-profile"></a>Criar e manter um perfil

Após os candidatos entrarem no site de carreiras, eles podem selecionar **Meu perfil** na barra de navegação na parte superior da página para criar e manter o perfil.
O perfil inclui informações pessoais, informações sobre a experiência de trabalho, detalhes de formação educacional, documentos, links e informações sobre os conjuntos de habilidades. Após um perfil ser criado, ele pode ser usado para candidatar-se a posições de interesse do candidato. Os perfis também ajudam o Attract a recomendar os trabalhos certos para candidatos.

> [!NOTE]
> Se um candidato usar uma ID de email para fazer logon usando um dos provedores de autenticação listados acima, essa ID de email será padronizado para a ID de email de contato associada ao perfil. No entanto, esse última pode ser alterada a qualquer momento e é completamente independente da primeira. O Attract sempre usará a ID de email de contato para associar ao seu perfil para todas as comunicações por email.

## <a name="find-the-right-job"></a>Localizar o trabalho certo

Na página de listas de trabalho, os candidatos podem procurar para um trabalho específico inserindo termos da pesquisa. A funcionalidade de pesquisa procura os termos da pesquisa em cargos e descrições de trabalho e mostra os trabalhos relevantes como resultados. Os candidatos podem filtrar os resultados a qualquer momento, com base no local de trabalho ou na função de trabalho.

Os candidatos também podem exibir um conjunto de trabalhos recomendados no site de carreiras. Os trabalhos que são recomendados para um um candidato se baseiam nas solicitações de emprego, nos perfis e nos currículos anteriores do candidato.

> [!NOTE] 
> As recomendações de trabalho só serão mostradas se pelo menos 10 trabalhos forem lançados no site de carreiras e se o candidato preencher um perfil.

Os candidatos internos também podem ver quem o é gerente de contratação e/ou o recrutador para um trabalho, caso eles queiram contatar esses membros da equipe de contratação. No entanto, os candidatos externos não têm visibilidade dos membros da equipe de contratação para nenhum trabalho.

## <a name="contact-the-hiring-team"></a>Entrar em contato com a equipe de contratação
Somente os candidatos internos podem contatar a equipe de contratação. Essa limitação se aplica a todos os trabalhos, independentemente se são somente internos ou se foram lançados publicamente.

Os candidatos podem querer contatar a equipe de contratação para expressar interesse em um trabalho que foi lançado ou para saber mais sobre ele. Eles podem contatar um membro da equipe de contratação que esteja listado (gerente de contratação ou recrutadores). Opcionalmente, eles também podem anexar um currículo à mensagem ou podem selecionar um currículo existente carregado anteriormente como parte do perfil.

Depois que um candidato interno seleciona o membro da equipe de contratação para contatar, o Attract envia um email a essas pessoas em nome do candidato. Ao mesmo tempo, o perfil do candidato será adicionado ao estágio **Colaborador potencial** , se esse estágio estiver disponível para o trabalho. No estágio **Colaborador potencial**, os recrutadores ou gerentes da contratação podem exibir os candidatos que entraram em contato com eles. Eles também podem examinar os perfis dos candidatos e convidar candidatos potenciais para se candidatar.

Os candidatos podem se candidatar ao trabalho sobre o qual já contataram membros da equipe de contratação. Depois que se candidatarem, eles não poderão mais contatar a equipe de contratação pelo site de carreiras.

## <a name="apply-for-jobs"></a>Candidatar-se a empregos

Depois que os candidatos encontrarem o trabalho certo, eles poderão se candidatar usando o botão  **Candidatar-se**  na página **Detalhes do trabalho**. Nesse ponto, os candidatos podem criar um novo perfil ou revisar as informações do perfil existente.
Os candidatos também podem carregar um currículo, conforme necessário, e enviar a solicitação de emprego.

### <a name="enable-applying-for-jobs-with-linkedin-profiles"></a>Habilitar a possibilidade de candidatar-se a trabalhos com perfis do LinkedIn

Você pode facilitar para que os candidatos se candidatem às posições configurando o Attract para permitir que façam isso pelo LinkedIn.

> [!NOTE] 
> É necessário ter uma ou mais licenças de recrutador do LinkedIn antes que possa permitir que os candidatos se candidatem com o LinkedIn.

1. Entre no Attract como administrador.
2. Selecione o botão **Configurações** (o símbolo de engrenagem) no canto superior direito da página e selecione **Centro de administração**.
3. Selecione a guia **Integração com o LinkedIn** e conecte-se com uma conta do LinkedIn Recruiter.
4. Na seção **Integração do LinkedIn Recruiter System Connect**, selecione **Habilitado** para a configuração **Candidatar-se com o LinkedIn**.

Depois que habilitar a configuração, os candidatos poderão se candidatar usando os dados existentes de seu perfil do LinkedIn. Quando os candidatos optarem por usar o botão **Candidatar-se com o LinkedIn**, será solicitado que façam a autenticação com o LinkedIn se ainda não estiverem conectados. Após a autenticação, o perfil do LinkedIn substituirá os dados de perfil existentes mostrados na página do aplicativo. Os candidatos podem editar as informações conforme necessário e enviar a solicitação de emprego. Se um candidato navegar para outra página sem se candidatar ao trabalho, os dados do perfil não serão atualizados no Attract.

## <a name="check-application-status"></a>Verificar o status da solicitação de emprego

Após os candidatos se candidatarem a um ou mais empregos, eles podem selecionar **Solicitações de emprego** na barra de navegação na parte superior da página para exibir as solicitações de emprego abertas e fechadas. Quando os candidatos abrem uma de suas solicitações de emprego, eles veem o estágio atual e os itens de ação pendentes que precisam concluir. Por exemplo, se um candidato precisar fornecer datas potenciais para uma entrevista pessoal, a página mostrará as opções disponíveis.

## <a name="internal-jobs"></a>Cargos internos

No momento, os cargos marcados como internos e lançados no site de carreiras do Attract não aparecem no site de carreiras. Eles só podem ser acessados por meio da URL **Solicitar** direta que pode ser copiada do aplicativo Attract.
