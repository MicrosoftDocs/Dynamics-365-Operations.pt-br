---
title: A funcionalidade do site de carreiras no Attract
description: Este tópico fornece uma visão geral da funcionalidade do site de carreiras voltada para o candidato no Attract.
author: josaw1
manager: AnnBe
ms.date: 02/12/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2019-02-12
ms.dyn365.ops.version: AX 7.1.0, Talent April 2018 update
ms.openlocfilehash: 087ab4034a1e601e7f3514c77d56ef54b0c5c52d
ms.sourcegitcommit: 1ee613a88edddab036d145f27f19d071a4b8ad24
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/13/2019
ms.locfileid: "389948"
---
# <a name="career-site-functionality-in-attract"></a><span data-ttu-id="2c7c4-103">A funcionalidade do site de carreiras no Attract</span><span class="sxs-lookup"><span data-stu-id="2c7c4-103">Career site functionality in Attract</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="2c7c4-104">Este tópico fornece uma visão geral da funcionalidade do site de carreiras voltada para o candidato no Microsoft Dynamics 365 for Talent: Attract.</span><span class="sxs-lookup"><span data-stu-id="2c7c4-104">This topic provides an overview of the candidate-facing career site functionality in Microsoft Dynamics 365 for Talent: Attract.</span></span> <span data-ttu-id="2c7c4-105">Ele também explica como configurar esta funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="2c7c4-105">It also explains how to set up this functionality.</span></span>

<span data-ttu-id="2c7c4-106">O Attract fornece um site de carreiras para cada ambiente em um locatário.</span><span class="sxs-lookup"><span data-stu-id="2c7c4-106">Attract provides one career site for each environment in a tenant.</span></span> <span data-ttu-id="2c7c4-107">Por exemplo, se uma organização tiver um ambiente de desenvolvimento e um ambiente de teste, um site de carreiras será provisionado para o ambiente de desenvolvimento e outro site de carreiras será provisionado para o ambiente de teste.</span><span class="sxs-lookup"><span data-stu-id="2c7c4-107">For example, if an organization has a development environment and a test environment, one career site is provisioned for the development environment, and another career site is provisioned for the test environment.</span></span> <span data-ttu-id="2c7c4-108">Cada site de carreiras é totalmente isolado e tem seu próprio mecanismo de autenticação.</span><span class="sxs-lookup"><span data-stu-id="2c7c4-108">Each career site is completely isolated and has its own authentication mechanism.</span></span> <span data-ttu-id="2c7c4-109">Os trabalhos e os perfis do candidato não são compartilhados entre sites de carreiras.</span><span class="sxs-lookup"><span data-stu-id="2c7c4-109">Jobs and candidate profiles aren't shared between career sites.</span></span>

<span data-ttu-id="2c7c4-110">Por padrão, o site de carreiras é público.</span><span class="sxs-lookup"><span data-stu-id="2c7c4-110">By default, the career site is public.</span></span> <span data-ttu-id="2c7c4-111">Portanto, os candidatos podem exibir todos os trabalhos que estão marcados como externos sem precisar fazer logon.</span><span class="sxs-lookup"><span data-stu-id="2c7c4-111">Therefore, candidates can view all jobs that are marked as external without having to sign in.</span></span> <span data-ttu-id="2c7c4-112">Entretanto, todas a outras ações exigem que os candidatos façam logon.</span><span class="sxs-lookup"><span data-stu-id="2c7c4-112">However, all other actions require that candidates sign in.</span></span>

## <a name="career-site-management"></a><span data-ttu-id="2c7c4-113">Gerenciamento do site de carreiras</span><span class="sxs-lookup"><span data-stu-id="2c7c4-113">Career site management</span></span>

<span data-ttu-id="2c7c4-114">Para definir os valores dos itens a seguir, entre no Attract como administrador, selecione **Centro de Administração** no menu **Configurações** (o símbolo de engrenagem) e selecione a guia **Informações sobre a empresa**.</span><span class="sxs-lookup"><span data-stu-id="2c7c4-114">To set the values for the following items, sign in to Attract as an administrator, select **Admin center** on the **Settings** menu (the gear symbol), and then select the **Company information** tab.</span></span>

-   <span data-ttu-id="2c7c4-115">**Nome da organização** - O nome da organização aparece na barra de navegação na parte superior do site de carreiras.</span><span class="sxs-lookup"><span data-stu-id="2c7c4-115">**Organization name** - The organization name appears on the navigation bar at the top of the career site.</span></span> <span data-ttu-id="2c7c4-116">Ao selecionar o nome da organização, os candidatos vão para uma página que lista todos os trabalhos abertos.</span><span class="sxs-lookup"><span data-stu-id="2c7c4-116">By selecting the organization name, candidates go to a page that lists all open jobs.</span></span>

-   <span data-ttu-id="2c7c4-117">**Logotipo organizacional** - Uma imagem do logotipo organizacional aparece na parte superior esquerda do site de carreiras.</span><span class="sxs-lookup"><span data-stu-id="2c7c4-117">**Organization logo** - An image of the organization's logo appears in the upper left of the career site.</span></span> <span data-ttu-id="2c7c4-118">Ao selecionar a imagem do logotipo, os candidatos vão para uma página que lista todos os trabalhos abertos.</span><span class="sxs-lookup"><span data-stu-id="2c7c4-118">By selecting the logo image, candidates go to a page that lists all open jobs.</span></span>

    >   [!NOTE] 
    >   <span data-ttu-id="2c7c4-119">A imagem de logotipo que aparece no site de carreiras tem uma altitude fixa de 20 pixels (px).</span><span class="sxs-lookup"><span data-stu-id="2c7c4-119">The logo image that appears on the career site has a fixed height of 20 pixels (px).</span></span> <span data-ttu-id="2c7c4-120">A imagem que você adiciona no Centro de administração é ajustada.</span><span class="sxs-lookup"><span data-stu-id="2c7c4-120">The image that you add in the Admin center is scaled to fit.</span></span> <span data-ttu-id="2c7c4-121">Portanto, dependendo da imagem, a largura pode mudar.</span><span class="sxs-lookup"><span data-stu-id="2c7c4-121">Therefore, depending on the image, the width might change.</span></span>
 
<span data-ttu-id="2c7c4-122">Para definir os valores dos itens a seguir, entre no Attract como administrador, selecione **Centro de Administração** no menu **Configurações** e selecione a guia **Gerenciamento do site de carreiras**.</span><span class="sxs-lookup"><span data-stu-id="2c7c4-122">To set the values for the following items, sign in to Attract as an administrator, select **Admin center** on the **Settings** menu, and then select the **Career site management** tab.</span></span>

-   <span data-ttu-id="2c7c4-123">**Otimização do mecanismo de pesquisa** - Quando habilitada, todos os trabalhos públicos postados para o site de carreiras do Attract serão pesquisados usando mecanismos de pesquisa, como o Bing e o Google.</span><span class="sxs-lookup"><span data-stu-id="2c7c4-123">**Search Engine Optimization** - When enabled, all public jobs posted to Attract career site will be searchable using search engines like Bing and Google.</span></span>

    >   [!NOTE] 
    >   <span data-ttu-id="2c7c4-124">Pode haver um atraso entre ativar essa configuração e os resultados da pesquisa, dependendo do mecanismo de pesquisa que você está usando.</span><span class="sxs-lookup"><span data-stu-id="2c7c4-124">There might be a delay between turning this setting on and search results appearing, depending on the search engine that you are using.</span></span>
         
## <a name="career-site-urls"></a><span data-ttu-id="2c7c4-125">URLs do site de carreiras</span><span class="sxs-lookup"><span data-stu-id="2c7c4-125">Career site URLs</span></span>

<span data-ttu-id="2c7c4-126">A lista a seguir contém as URLs do site de carreiras comumente usadas e como acessá-las.</span><span class="sxs-lookup"><span data-stu-id="2c7c4-126">The following list contains the commonly used career site URLs and how to access them.</span></span>

-   <span data-ttu-id="2c7c4-127">**URL da página inicial do site de carreira** - Para visualizar a URL da página inicial do site de carreira, entre no Attract como administrador, selecione **Centro de administração** no menu **Configurações** e selecione a guia **Gerenciamento do site de carreiras**.</span><span class="sxs-lookup"><span data-stu-id="2c7c4-127">**Career site home page URL** - To view the career site home page URL, sign in to Attract as an administrator, select **Admin center** on the **Settings** menu, and then select the **Career site management** tab.</span></span>

-   <span data-ttu-id="2c7c4-128">**URL da solicitação de lançamento de trabalho individual** - Ao [postar um trabalho externo](Creating-jobs-Attract.md#postings) pela primeira vez, você pode copiar o link **Solicitar** da solicitação de emprego do Attract.</span><span class="sxs-lookup"><span data-stu-id="2c7c4-128">**Individual job post apply URL** - When you [post an external job](Creating-jobs-Attract.md#postings) for the first time, you can copy the **Apply** link from the Attract application.</span></span> <span data-ttu-id="2c7c4-129">A URL para esse link estará neste formato: [https://jobs.talent.dynamics.com/jobs/\<company_name\>/\<environment_number\>/\<job_number\>/apply](https://jobs.talent.dynamics.com/jobs/%3ccompany_name%3e/%3cenvironment_number%3e/%3cjob_number%3e/apply)</span><span class="sxs-lookup"><span data-stu-id="2c7c4-129">The URL for this link will be in the following format: [https://jobs.talent.dynamics.com/jobs/\<company_name\>/\<environment_number\>/\<job_number\>/apply](https://jobs.talent.dynamics.com/jobs/%3ccompany_name%3e/%3cenvironment_number%3e/%3cjob_number%3e/apply)</span></span>

-   <span data-ttu-id="2c7c4-130">**URL de lançamento de trabalho individual** - A URL de lançamento de trabalho é uma subsequência da URL de solicitação.</span><span class="sxs-lookup"><span data-stu-id="2c7c4-130">**Individual job post URL** - The URL of the job post is a substring of the Apply URL.</span></span> <span data-ttu-id="2c7c4-131">Ela consiste em tudo até o número de trabalho.</span><span class="sxs-lookup"><span data-stu-id="2c7c4-131">It consists of everything up through the job number.</span></span> <span data-ttu-id="2c7c4-132">Assim, para a URL de solicitação precedente, a URL de lançamento de trabalho é [https://jobs.talent.dynamics.com/jobs/\<company_name\>/\<environment_number\>/\<job_number\>](https://jobs.talent.dynamics.com/jobs/%3ccompany_name%3e/%3cenvironment_number%3e/%3cjob_number%3e)</span><span class="sxs-lookup"><span data-stu-id="2c7c4-132">Therefore, for the preceding Apply URL, the job post URL is [https://jobs.talent.dynamics.com/jobs/\<company_name\>/\<environment_number\>/\<job_number\>](https://jobs.talent.dynamics.com/jobs/%3ccompany_name%3e/%3cenvironment_number%3e/%3cjob_number%3e)</span></span>

## <a name="authentication-options"></a><span data-ttu-id="2c7c4-133">Opções de autenticação</span><span class="sxs-lookup"><span data-stu-id="2c7c4-133">Authentication options</span></span>

<span data-ttu-id="2c7c4-134">Os candidatos têm as seguintes opções de logon para um site de carreiras do Attract:</span><span class="sxs-lookup"><span data-stu-id="2c7c4-134">Candidates have the following sign-in options for an Attract career site:</span></span>

-   <span data-ttu-id="2c7c4-135">Conta pessoal:</span><span class="sxs-lookup"><span data-stu-id="2c7c4-135">Personal account:</span></span>

    -   <span data-ttu-id="2c7c4-136">LinkedIn</span><span class="sxs-lookup"><span data-stu-id="2c7c4-136">LinkedIn</span></span>

    -   <span data-ttu-id="2c7c4-137">Microsoft</span><span class="sxs-lookup"><span data-stu-id="2c7c4-137">Microsoft</span></span>

    -   <span data-ttu-id="2c7c4-138">Google</span><span class="sxs-lookup"><span data-stu-id="2c7c4-138">Google</span></span>

    -   <span data-ttu-id="2c7c4-139">Facebook</span><span class="sxs-lookup"><span data-stu-id="2c7c4-139">Facebook</span></span>

-   <span data-ttu-id="2c7c4-140">Conta corporativa ou de estudante:</span><span class="sxs-lookup"><span data-stu-id="2c7c4-140">Work or school account:</span></span>

    -   <span data-ttu-id="2c7c4-141">Microsoft Azure Active Directory (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="2c7c4-141">Microsoft Azure Active Directory (Azure AD)</span></span>

<span data-ttu-id="2c7c4-142">O logon do Azure AD se destina somente a candidatos internos.</span><span class="sxs-lookup"><span data-stu-id="2c7c4-142">Azure AD sign-in is intended only for internal candidates.</span></span> <span data-ttu-id="2c7c4-143">Portanto, ele só funciona para candidatos internos que usam suas credenciais do Azure AD da empresa.</span><span class="sxs-lookup"><span data-stu-id="2c7c4-143">Therefore, it works only for internal candidates who use their company Azure AD credentials.</span></span> <span data-ttu-id="2c7c4-144">Por exemplo, um candidato que no momento é um funcionário da Contoso Ltd deseja candidatar-se a um trabalho em uma empresa não relacionada, a Alpine Ski House.</span><span class="sxs-lookup"><span data-stu-id="2c7c4-144">For example, a candidate who is currently an employee of Contoso Ltd wants to apply for a job in an unrelated company, Alpine Ski House.</span></span> <span data-ttu-id="2c7c4-145">Nesse caso, o logon será malsucedido se o funcionário tentar usar as credenciais do Azure AD da Contoso Ltd.</span><span class="sxs-lookup"><span data-stu-id="2c7c4-145">In this case, the sign-in will be unsuccessful if the employee tries to use Azure AD credentials from Contoso Ltd.</span></span>

## <a name="create-and-maintain-a-profile"></a><span data-ttu-id="2c7c4-146">Criar e manter um perfil</span><span class="sxs-lookup"><span data-stu-id="2c7c4-146">Create and maintain a profile</span></span>

<span data-ttu-id="2c7c4-147">Após os candidatos entrarem no site de carreiras, eles podem selecionar **Meu perfil** na barra de navegação na parte superior da página para criar e manter o perfil.</span><span class="sxs-lookup"><span data-stu-id="2c7c4-147">After candidates sign in to the career site, they can select **My profile** on the navigation bar at the top of the page to create and maintain their profile.</span></span>
<span data-ttu-id="2c7c4-148">O perfil inclui informações pessoais, informações sobre a experiência de trabalho, detalhes de formação educacional, documentos, links e informações sobre os conjuntos de habilidades.</span><span class="sxs-lookup"><span data-stu-id="2c7c4-148">The profile includes personal information, information about work experience, education details, documents, links, and information about skill sets.</span></span> <span data-ttu-id="2c7c4-149">Após um perfil ser criado, ele pode ser usado para candidatar-se a posições de interesse do candidato.</span><span class="sxs-lookup"><span data-stu-id="2c7c4-149">After a profile is created, it can be used to apply for jobs that the candidate is interested in.</span></span> <span data-ttu-id="2c7c4-150">Os perfis também ajudam o Attract a recomendar os trabalhos certos para candidatos.</span><span class="sxs-lookup"><span data-stu-id="2c7c4-150">Profiles also help Attract recommend the right jobs to candidates.</span></span>

>   [!NOTE]
>   <span data-ttu-id="2c7c4-151">Se um candidato usar uma ID de email para fazer logon usando um dos provedores de autenticação listados acima, essa ID de email será padronizado para a ID de email de contato associada ao perfil.</span><span class="sxs-lookup"><span data-stu-id="2c7c4-151">If a candidate uses an email ID to sign in using one of the authentication providers listed above, that email ID will default to the contact email ID associated with the profile.</span></span> <span data-ttu-id="2c7c4-152">No entanto, esse última pode ser alterada a qualquer momento e é completamente independente da primeira.</span><span class="sxs-lookup"><span data-stu-id="2c7c4-152">However, the latter can be changed at any time and is completely independent of the former.</span></span> <span data-ttu-id="2c7c4-153">O Attract sempre usará a ID de email de contato para associar ao seu perfil para todas as comunicações por email.</span><span class="sxs-lookup"><span data-stu-id="2c7c4-153">Attract will always use the contact email ID to associate with your profile for all email communications.</span></span>

## <a name="find-the-right-job"></a><span data-ttu-id="2c7c4-154">Localizar o trabalho certo</span><span class="sxs-lookup"><span data-stu-id="2c7c4-154">Find the right job</span></span>

<span data-ttu-id="2c7c4-155">Na página de listas de trabalho, os candidatos podem procurar para um trabalho específico inserindo termos da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="2c7c4-155">On the job list page, candidates can search for a specific job by entering search terms.</span></span> <span data-ttu-id="2c7c4-156">A funcionalidade de pesquisa procura os termos da pesquisa em cargos e descrições de trabalho e mostra os trabalhos relevantes como resultados.</span><span class="sxs-lookup"><span data-stu-id="2c7c4-156">The search functionality looks for the search terms in job titles and job descriptions, and shows relevant jobs as results.</span></span> <span data-ttu-id="2c7c4-157">Os candidatos podem filtrar os resultados a qualquer momento, com base no local de trabalho ou na função de trabalho.</span><span class="sxs-lookup"><span data-stu-id="2c7c4-157">Candidates can filter the results at any time, based on the job location or job function.</span></span>

<span data-ttu-id="2c7c4-158">Os candidatos também podem exibir um conjunto de trabalhos recomendados no site de carreiras.</span><span class="sxs-lookup"><span data-stu-id="2c7c4-158">Candidates can also view a set of recommended jobs on the career site.</span></span> <span data-ttu-id="2c7c4-159">Os trabalhos que são recomendados para um um candidato se baseiam nas solicitações de emprego, nos perfis e nos currículos anteriores do candidato.</span><span class="sxs-lookup"><span data-stu-id="2c7c4-159">The jobs that are recommended to a candidate are based on the candidate's past applications, profile, and resumes.</span></span>

>   [!NOTE] 
>   <span data-ttu-id="2c7c4-160">As recomendações de trabalho só serão mostradas se pelo menos 10 trabalhos forem lançados no site de carreiras e se o candidato preencher um perfil.</span><span class="sxs-lookup"><span data-stu-id="2c7c4-160">Job recommendations are shown only if at least 10 jobs are posted on the career site, and if the candidate has completed a profile.</span></span>

## <a name="apply-for-jobs"></a><span data-ttu-id="2c7c4-161">Candidatar-se a empregos</span><span class="sxs-lookup"><span data-stu-id="2c7c4-161">Apply for jobs</span></span>

<span data-ttu-id="2c7c4-162">Após os candidatos encontrarem o trabalho certo, eles podem se candidatar usando o botão **Solicitar** na página **Detalhes do trabalho**.</span><span class="sxs-lookup"><span data-stu-id="2c7c4-162">After candidates find the right job, they can apply by using the **Apply** button on the **Job details** page.</span></span> <span data-ttu-id="2c7c4-163">Nesse ponto, os candidatos podem criar um novo perfil ou revisar as informações do perfil existente.</span><span class="sxs-lookup"><span data-stu-id="2c7c4-163">At this point, candidates can either create a new profile or review the information in their existing profile.</span></span>
<span data-ttu-id="2c7c4-164">Os candidatos também podem carregar um currículo, conforme necessário, e enviar a solicitação de emprego.</span><span class="sxs-lookup"><span data-stu-id="2c7c4-164">Candidates can also upload a resume, as required, and then submit the job application.</span></span>

## <a name="check-application-status"></a><span data-ttu-id="2c7c4-165">Verificar o status da solicitação de emprego</span><span class="sxs-lookup"><span data-stu-id="2c7c4-165">Check application status</span></span>

<span data-ttu-id="2c7c4-166">Após os candidatos se candidatarem a um ou mais empregos, eles podem selecionar **Solicitações de emprego** na barra de navegação na parte superior da página para exibir as solicitações de emprego abertas e fechadas.</span><span class="sxs-lookup"><span data-stu-id="2c7c4-166">After candidates apply for one or more jobs, they can select **Applications** on the navigation bar at the top of the page to view their open and closed applications.</span></span> <span data-ttu-id="2c7c4-167">Quando os candidatos abrem uma de suas solicitações de emprego, eles veem o estágio atual e os itens de ação pendentes que precisam concluir.</span><span class="sxs-lookup"><span data-stu-id="2c7c4-167">When candidates open one of their applications, they see the current stage and any pending action items that they must complete.</span></span> <span data-ttu-id="2c7c4-168">Por exemplo, se um candidato precisar fornecer datas potenciais para uma entrevista pessoal, a página mostrará as opções disponíveis.</span><span class="sxs-lookup"><span data-stu-id="2c7c4-168">For example, if a candidate must provide potential dates for an in-person interview, the page shows the available options.</span></span>

## <a name="internal-jobs"></a><span data-ttu-id="2c7c4-169">Cargos internos</span><span class="sxs-lookup"><span data-stu-id="2c7c4-169">Internal jobs</span></span>

<span data-ttu-id="2c7c4-170">No momento, os cargos marcados como internos e lançados no site de carreiras do Attract não aparecem no site de carreiras.</span><span class="sxs-lookup"><span data-stu-id="2c7c4-170">Currently, jobs that are marked as internal and posted to the Attract career site don't appear on the career site.</span></span> <span data-ttu-id="2c7c4-171">Eles só podem ser acessados por meio da URL **Solicitar** direta que pode ser copiada do aplicativo Attract.</span><span class="sxs-lookup"><span data-stu-id="2c7c4-171">They are only accessible using the direct **Apply** URL that can be copied from the Attract application.</span></span>
