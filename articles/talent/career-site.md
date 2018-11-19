---
title: A funcionalidade do site de carreiras no Attract
description: "Este artigo fornece uma visão geral da funcionalidade do site de carreiras voltada para o candidato no Microsoft Dynamics 365 for Talent - Attract. Ele também explica como configurar esta funcionalidade."
author: josaw
manager: AnnBe
ms.date: 10/18/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Talent
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: rschloma
ms.search.validFrom: 2018-10-18
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: e890e32049e930b70c2d0aac8aa8206ab999418a
ms.openlocfilehash: 452e3e92ea32ab5f1e3720ab81ff2f7ea18b2a06
ms.contentlocale: pt-br
ms.lasthandoff: 10/22/2018

---
# <a name="career-site-functionality-in-attract"></a><span data-ttu-id="74938-104">A funcionalidade do site de carreiras no Attract</span><span class="sxs-lookup"><span data-stu-id="74938-104">Career site functionality in Attract</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="74938-105">Este artigo fornece uma visão geral da funcionalidade do site de carreiras voltada para o candidato no Microsoft Dynamics 365 for Talent: Attract.</span><span class="sxs-lookup"><span data-stu-id="74938-105">This article provides an overview of the candidate-facing career site functionality in Microsoft Dynamics 365 for Talent: Attract.</span></span> <span data-ttu-id="74938-106">Ele também explica como configurar esta funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="74938-106">It also explains how to set up this functionality.</span></span>

## <a name="overview"></a><span data-ttu-id="74938-107">Visão Geral</span><span class="sxs-lookup"><span data-stu-id="74938-107">Overview</span></span>

<span data-ttu-id="74938-108">O Attract fornece um site de carreiras para cada ambiente em um locatário.</span><span class="sxs-lookup"><span data-stu-id="74938-108">Attract provides one career site for each environment in a tenant.</span></span> <span data-ttu-id="74938-109">Por exemplo, se uma organização tiver um ambiente de desenvolvimento e um ambiente de teste, um site de carreiras será provisionado para o ambiente de desenvolvimento e outro site de carreiras será provisionado para o ambiente de teste.</span><span class="sxs-lookup"><span data-stu-id="74938-109">For example, if an organization has a development environment and a test environment, one career site is provisioned for the development environment, and another career site is provisioned for the test environment.</span></span> <span data-ttu-id="74938-110">Cada site de carreiras é **totalmente isolado** e tem seu próprio mecanismo de autenticação.</span><span class="sxs-lookup"><span data-stu-id="74938-110">Each career site is **completely isolated** and has its own authentication mechanism.</span></span> <span data-ttu-id="74938-111">Os trabalhos e os perfis do candidato não são compartilhados entre sites de carreiras.</span><span class="sxs-lookup"><span data-stu-id="74938-111">Jobs and candidate profiles aren't shared between career sites.</span></span>

<span data-ttu-id="74938-112">Por padrão, o site de carreiras é público.</span><span class="sxs-lookup"><span data-stu-id="74938-112">By default, the career site is public.</span></span> <span data-ttu-id="74938-113">Portanto, os candidatos podem exibir todos os trabalhos que estão marcados como externos sem precisar fazer logon.</span><span class="sxs-lookup"><span data-stu-id="74938-113">Therefore, candidates can view all jobs that are marked as external without having to sign in.</span></span> <span data-ttu-id="74938-114">Entretanto, todas a outras ações exigem que os candidatos façam logon.</span><span class="sxs-lookup"><span data-stu-id="74938-114">However, all other actions require that candidates sign in.</span></span>

## <a name="career-site-management"></a><span data-ttu-id="74938-115">Gerenciamento do site de carreiras</span><span class="sxs-lookup"><span data-stu-id="74938-115">Career site management</span></span>

<span data-ttu-id="74938-116">Os seguintes itens no site de carreiras são controlados por configurações:</span><span class="sxs-lookup"><span data-stu-id="74938-116">The following items on the career site are controlled by settings:</span></span>

- <span data-ttu-id="74938-117">**Nome da organização:** o nome da organização aparece na barra de navegação na parte superior do site de carreiras.</span><span class="sxs-lookup"><span data-stu-id="74938-117">**Organization name:** The organization name appears on the navigation bar at the top of the career site.</span></span> <span data-ttu-id="74938-118">Ao selecionar o nome da organização, os candidatos vão para uma página que lista todos os trabalhos abertos.</span><span class="sxs-lookup"><span data-stu-id="74938-118">By selecting the organization name, candidates go to a page that lists all open jobs.</span></span>
- <span data-ttu-id="74938-119">**Logotipo organizacional:** uma imagem do logotipo organizacional aparece na parte superior esquerda do site de carreiras.</span><span class="sxs-lookup"><span data-stu-id="74938-119">**Organization logo:** An image of the organization's logo appears in the upper left of the career site.</span></span> <span data-ttu-id="74938-120">Ao selecionar a imagem do logotipo, os candidatos vão para uma página que lista todos os trabalhos abertos.</span><span class="sxs-lookup"><span data-stu-id="74938-120">By selecting the logo image, candidates go to a page that lists all open jobs.</span></span>

<span data-ttu-id="74938-121">Para definir os valores do nome e do logotipo da organização, entre no Attract como administrador, selecione **Centro de Administração** no menu **Configurações** (o símbolo de engrenagem) e selecione a guia **Informações sobre a empresa**.</span><span class="sxs-lookup"><span data-stu-id="74938-121">To set the values for the organization name and logo, sign in to Attract as an administrator, select **Admin center** on the **Settings** menu (the gear symbol), and then select the **Company information** tab.</span></span>

> [!NOTE]
> <span data-ttu-id="74938-122">A imagem de logotipo que aparece no site de carreiras tem uma altitude fixa de 20 pixels (px).</span><span class="sxs-lookup"><span data-stu-id="74938-122">The logo image that appears on the career site has a fixed height of 20 pixels (px).</span></span> <span data-ttu-id="74938-123">A imagem que você adiciona no Centro de administração é ajustada.</span><span class="sxs-lookup"><span data-stu-id="74938-123">The image that you add in the Admin center is scaled to fit.</span></span> <span data-ttu-id="74938-124">Portanto, dependendo da imagem, a largura pode mudar.</span><span class="sxs-lookup"><span data-stu-id="74938-124">Therefore, depending on the image, the width might change.</span></span>

## <a name="career-site-url"></a><span data-ttu-id="74938-125">URL do site de carreiras</span><span class="sxs-lookup"><span data-stu-id="74938-125">Career site URL</span></span>

<span data-ttu-id="74938-126">Ao [lançar um trabalho externo](./Creating-jobs-Attract.md#postings) pela primeira vez, você pode copiar o link **Solicitar** da solicitação de emprego do Attract.</span><span class="sxs-lookup"><span data-stu-id="74938-126">When you [post an external job](./Creating-jobs-Attract.md#postings) for the first time, you can copy the **Apply** link from the Attract application.</span></span> <span data-ttu-id="74938-127">A URL para esse link estará neste formato: `https://jobs.talent.dynamics.com/jobs/<company_name>/<environment_number>/<job_number>/apply`</span><span class="sxs-lookup"><span data-stu-id="74938-127">The URL for this link will be in the following format: `https://jobs.talent.dynamics.com/jobs/<company_name>/<environment_number>/<job_number>/apply`</span></span>

<span data-ttu-id="74938-128">A URL do site de carreiras é uma subcadeia de caracteres da URL **Solicitar**.</span><span class="sxs-lookup"><span data-stu-id="74938-128">The URL of the career site is a substring of the **Apply** URL.</span></span> <span data-ttu-id="74938-129">Ela consiste em tudo até o nome da empresa.</span><span class="sxs-lookup"><span data-stu-id="74938-129">It consists of everything up through the company name.</span></span> <span data-ttu-id="74938-130">Assim, para a URL **Solicitar** precedente, a URL do site de carreiras é `https://jobs.talent.dynamics.com/jobs/<company_name>/`.</span><span class="sxs-lookup"><span data-stu-id="74938-130">Therefore, for the preceding **Apply** URL, the career site URL is `https://jobs.talent.dynamics.com/jobs/<company_name>/`.</span></span>

## <a name="authentication-options"></a><span data-ttu-id="74938-131">Opções de autenticação</span><span class="sxs-lookup"><span data-stu-id="74938-131">Authentication options</span></span>

<span data-ttu-id="74938-132">Os candidatos têm as seguintes opções de logon para um site de carreiras do Attract:</span><span class="sxs-lookup"><span data-stu-id="74938-132">Candidates have the following sign-in options for an Attract career site:</span></span>

- <span data-ttu-id="74938-133">Conta pessoal:</span><span class="sxs-lookup"><span data-stu-id="74938-133">Personal account:</span></span>

    - <span data-ttu-id="74938-134">LinkedIn</span><span class="sxs-lookup"><span data-stu-id="74938-134">LinkedIn</span></span>
    - <span data-ttu-id="74938-135">Microsoft</span><span class="sxs-lookup"><span data-stu-id="74938-135">Microsoft</span></span>
    - <span data-ttu-id="74938-136">Google</span><span class="sxs-lookup"><span data-stu-id="74938-136">Google</span></span>
    - <span data-ttu-id="74938-137">Facebook</span><span class="sxs-lookup"><span data-stu-id="74938-137">Facebook</span></span>

- <span data-ttu-id="74938-138">Conta corporativa ou de estudante:</span><span class="sxs-lookup"><span data-stu-id="74938-138">Work or school account:</span></span>

    - <span data-ttu-id="74938-139">Microsoft Azure Active Directory (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="74938-139">Microsoft Azure Active Directory (Azure AD)</span></span>

<span data-ttu-id="74938-140">O logon do Azure AD se destina somente a candidatos internos.</span><span class="sxs-lookup"><span data-stu-id="74938-140">Azure AD sign-in is intended only for internal candidates.</span></span> <span data-ttu-id="74938-141">Portanto, ele só funciona para candidatos internos que usam suas credenciais do Azure AD da empresa.</span><span class="sxs-lookup"><span data-stu-id="74938-141">Therefore, it works only for internal candidates who use their company Azure AD credentials.</span></span> <span data-ttu-id="74938-142">Por exemplo, um candidato que no momento é um funcionário da Contoso Ltd deseja candidatar-se a um trabalho em uma empresa não relacionada, a Alpine Ski House.</span><span class="sxs-lookup"><span data-stu-id="74938-142">For example, a candidate who is currently an employee of Contoso Ltd wants to apply for a job in an unrelated company, Alpine Ski House.</span></span> <span data-ttu-id="74938-143">Nesse caso, o logon será malsucedido se o funcionário tentar usar suas credenciais do Azure AD da Contoso Ltd.</span><span class="sxs-lookup"><span data-stu-id="74938-143">In this case, the sign-in will be unsuccessful if the employee tries to use his or her Azure AD credentials from Contoso Ltd.</span></span>

## <a name="create-and-maintain-a-profile"></a><span data-ttu-id="74938-144">Criar e manter um perfil</span><span class="sxs-lookup"><span data-stu-id="74938-144">Create and maintain a profile</span></span>

<span data-ttu-id="74938-145">Após os candidatos entrarem no site de carreiras, eles podem selecionar **Meu perfil** na barra de navegação na parte superior da página para criar e manter o perfil.</span><span class="sxs-lookup"><span data-stu-id="74938-145">After candidates sign in to the career site, they can select **My profile** on the navigation bar at the top of the page to create and maintain their profile.</span></span> <span data-ttu-id="74938-146">O perfil inclui informações pessoais, informações sobre a experiência de trabalho, detalhes de formação educacional, documentos, links e informações sobre os conjuntos de habilidades.</span><span class="sxs-lookup"><span data-stu-id="74938-146">The profile includes personal information, information about work experience, education details, documents, links, and information about skill sets.</span></span> <span data-ttu-id="74938-147">Após um perfil ser criado, ele pode ser usado para candidatar-se a posições de interesse do candidato.</span><span class="sxs-lookup"><span data-stu-id="74938-147">After a profile is created, it can be used to apply for jobs that the candidate is interested in.</span></span> <span data-ttu-id="74938-148">Os perfis também ajudam o Attract a recomendar os trabalhos certos para candidatos.</span><span class="sxs-lookup"><span data-stu-id="74938-148">Profiles also help Attract recommend the right jobs to candidates.</span></span>

## <a name="find-the-right-job"></a><span data-ttu-id="74938-149">Localize o trabalho certo</span><span class="sxs-lookup"><span data-stu-id="74938-149">Find the right job</span></span>

<span data-ttu-id="74938-150">Na página de listas de trabalho, os candidatos podem procurar para um trabalho específico inserindo termos da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="74938-150">On the job list page, candidates can search for a specific job by entering search terms.</span></span> <span data-ttu-id="74938-151">A funcionalidade de pesquisa procura os termos da pesquisa em cargos e descrições de trabalho e mostra os trabalhos relevantes como resultados.</span><span class="sxs-lookup"><span data-stu-id="74938-151">The search functionality looks for the search terms in job titles and job descriptions, and shows relevant jobs as results.</span></span> <span data-ttu-id="74938-152">Os candidatos podem filtrar os resultados a qualquer momento, com base no local de trabalho ou na função de trabalho.</span><span class="sxs-lookup"><span data-stu-id="74938-152">Candidates can filter the results at any time, based on the job location or job function.</span></span>

<span data-ttu-id="74938-153">Os candidatos também podem exibir um conjunto de trabalhos recomendados no site de carreiras.</span><span class="sxs-lookup"><span data-stu-id="74938-153">Candidates can also view a set of recommended jobs on the career site.</span></span> <span data-ttu-id="74938-154">Os trabalhos que são recomendados para um um candidato se baseiam nas solicitações de emprego, nos perfis e nos currículos anteriores do candidato.</span><span class="sxs-lookup"><span data-stu-id="74938-154">The jobs that are recommended to a candidate are based on the candidate's past applications, profile, and resumes.</span></span>

> [!NOTE]
> <span data-ttu-id="74938-155">As recomendações de trabalho só serão mostradas se pelo menos 10 trabalhos forem lançados no site de carreiras e se o candidato preencher o perfil.</span><span class="sxs-lookup"><span data-stu-id="74938-155">Job recommendations are shown only if at least 10 jobs are posted on the career site, and if the candidate has completed his or her profile.</span></span>

## <a name="apply-for-jobs"></a><span data-ttu-id="74938-156">Candidatar-se a empregos</span><span class="sxs-lookup"><span data-stu-id="74938-156">Apply for jobs</span></span>

<span data-ttu-id="74938-157">Após os candidatos encontrarem o trabalho certo, eles podem candidatar-se usando o botão **Solicitar** na página de detalhes do trabalho.</span><span class="sxs-lookup"><span data-stu-id="74938-157">After candidates find the right job, they can apply by using the **Apply** button on the job details page.</span></span> <span data-ttu-id="74938-158">Nesse ponto, os candidatos podem criar um novo perfil ou revisar as informações do perfil existente.</span><span class="sxs-lookup"><span data-stu-id="74938-158">At this point, candidates can either create a brand-new profile or review the information in their existing profile.</span></span> <span data-ttu-id="74938-159">Os candidatos também podem carregar um currículo, conforme necessário, e enviar a solicitação de emprego.</span><span class="sxs-lookup"><span data-stu-id="74938-159">Candidates can also upload a resume, as required, and then submit the job application.</span></span>

## <a name="check-application-status"></a><span data-ttu-id="74938-160">Verificar o status da solicitação de emprego</span><span class="sxs-lookup"><span data-stu-id="74938-160">Check application status</span></span>

<span data-ttu-id="74938-161">Após os candidatos se candidatarem a um ou mais empregos, eles podem selecionar **Solicitações de emprego** na barra de navegação na parte superior da página para exibir as solicitações de emprego abertas e fechadas.</span><span class="sxs-lookup"><span data-stu-id="74938-161">After candidates apply for one or more jobs, they can select **Applications** on the navigation bar at the top of the page to view their open and closed applications.</span></span> <span data-ttu-id="74938-162">Quando os candidatos abrem uma de suas solicitações de emprego, eles veem o estágio atual e os itens de ação pendentes que precisam concluir.</span><span class="sxs-lookup"><span data-stu-id="74938-162">When candidates open one of their applications, they see the current stage and any pending action items that they must complete.</span></span> <span data-ttu-id="74938-163">Por exemplo, se um candidato precisar fornecer datas potenciais para uma entrevista pessoal, a página mostrará suas opções.</span><span class="sxs-lookup"><span data-stu-id="74938-163">For example, if a candidate must provide potential dates for an in-person interview, the page shows his or her options.</span></span>

## <a name="internal-jobs"></a><span data-ttu-id="74938-164">Cargos internos</span><span class="sxs-lookup"><span data-stu-id="74938-164">Internal jobs</span></span>

<span data-ttu-id="74938-165">No momento, os cargos marcados como internos e lançados no site de carreiras do Attract não aparecem no site de carreiras.</span><span class="sxs-lookup"><span data-stu-id="74938-165">Currently, jobs that are marked as internal and posted to the Attract career site don't appear on the career site.</span></span> <span data-ttu-id="74938-166">Eles só podem ser acessados por meio da URL **Solicitar** direta que pode ser copiada do aplicativo Attract.</span><span class="sxs-lookup"><span data-stu-id="74938-166">They are accessible only via the direct **Apply** URL that can be copied from the Attract application.</span></span>

