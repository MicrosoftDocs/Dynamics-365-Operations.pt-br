---
title: Estender o Talent usando o PowerApps e o Microsoft Flow — cenários de exemplo
description: Este tópico descreve alguns exemplos de cenários de extensibilidade para o Microsoft Dynamics 365 for Talent que usam o Microsoft PowerApps e o Microsoft Flow.
author: negudava
manager: Annbe
ms.date: 05/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: Dynamics 365 for Talent;PowerApps;Flow;Common Data Service
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent;Core;Experience Apps
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: negudava
ms.search.validFrom: 2019-03-04
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: c113b0f4ab2c8e44d00fcfca3f0a6ca828a854ae
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2019
ms.locfileid: "1517314"
---
# <a name="extend-talent-by-using-powerapps-and-microsoft-flow---example-scenarios"></a><span data-ttu-id="bc832-103">Estender o Talent usando o PowerApps e o Microsoft Flow — cenários de exemplo</span><span class="sxs-lookup"><span data-stu-id="bc832-103">Extend Talent by using PowerApps and Microsoft Flow - Example scenarios</span></span>

<span data-ttu-id="bc832-104">Este tópico descreve alguns exemplos de cenários de extensibilidade para o Microsoft Dynamics 365 for Talent que usam o Microsoft PowerApps e o Microsoft Flow.</span><span class="sxs-lookup"><span data-stu-id="bc832-104">This topic describes some examples of extensibility scenarios for Microsoft Dynamics 365 for Talent that use Microsoft PowerApps and Microsoft Flow.</span></span> <span data-ttu-id="bc832-105">Você pode importar o pacote da solução que está associado a cada exemplo para seu ambiente do PowerApps.</span><span class="sxs-lookup"><span data-stu-id="bc832-105">You can import the solution package that is associated with each example into your PowerApps environment.</span></span> <span data-ttu-id="bc832-106">Depois, você pode usar os pacotes como orientação ou como pontos de partida para implementar cenários aplicáveis à sua organização.</span><span class="sxs-lookup"><span data-stu-id="bc832-106">You can then use the packages either as guidance or as starting points to implement scenarios that are applicable to your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bc832-107">Se quiser usar os modelos e o aplicativo que estão descritos neste tópico "no estado em que se encontram", certifique-se de testá-los para garantir que cubram todos os cenários que são específicos à sua implementação.</span><span class="sxs-lookup"><span data-stu-id="bc832-107">If you want to use the templates and app that are described in this topic "as is," be sure to test them to make sure that they cover all the scenarios that are specific to your implementation.</span></span>


## <a name="prerequisites"></a><span data-ttu-id="bc832-108">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="bc832-108">Prerequisites</span></span>

- <span data-ttu-id="bc832-109">Para importar os pacotes, os usuários devem ter a permissão **Criador de Ambiente**.</span><span class="sxs-lookup"><span data-stu-id="bc832-109">To import packages, users must have the **Environment Maker** permission.</span></span>
- <span data-ttu-id="bc832-110">Para exportar ou importar aplicativos, os usuários devem ter uma licença do plano 2 do PowerApps ou uma licença de avaliação do plano 2 do PowerApps.</span><span class="sxs-lookup"><span data-stu-id="bc832-110">To export or import apps, users must have a PowerApps Plan 2 license or a PowerApps Plan 2 trial license.</span></span>

## <a name="flow--form-connect"></a><span data-ttu-id="bc832-111">Flow — Form Connect</span><span class="sxs-lookup"><span data-stu-id="bc832-111">Flow – Form Connect</span></span>

<span data-ttu-id="bc832-112">O modelo **Flow — Form Connect** pode ser usado para ler dados do Microsoft Forms e armazená-los em uma entidade do Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="bc832-112">The **Flow – Form Connect** template can be used to read data from Microsoft Forms and store it in a Common Data Service entity.</span></span>

<span data-ttu-id="bc832-113">Esse método pode ser estendido para que possa ser usado em outros cenários.</span><span class="sxs-lookup"><span data-stu-id="bc832-113">This template can be extended so that it can be used for other scenarios.</span></span> <span data-ttu-id="bc832-114">Eis alguns exemplos:</span><span class="sxs-lookup"><span data-stu-id="bc832-114">Here are some examples:</span></span>

- <span data-ttu-id="bc832-115">Capturar avaliações de candidatos.</span><span class="sxs-lookup"><span data-stu-id="bc832-115">Capture candidate assessments.</span></span>
- <span data-ttu-id="bc832-116">Capturar resultados de questionários de cursos.</span><span class="sxs-lookup"><span data-stu-id="bc832-116">Capture results from course questionnaires.</span></span>
- <span data-ttu-id="bc832-117">Compilar uma biblioteca de perguntas de entrevista para os administradores de recursos humanos (RH).</span><span class="sxs-lookup"><span data-stu-id="bc832-117">Compile a library of interview questions for Human resources (HR) administrators.</span></span>
- <span data-ttu-id="bc832-118">Capturar a avaliação de um candidato do processo de entrevista</span><span class="sxs-lookup"><span data-stu-id="bc832-118">Capture a candidate's evaluation of the interview process</span></span>

<span data-ttu-id="bc832-119">No Microsoft Dynamics 365: Attract, os formulários podem aparecer no Portal do candidato, e os candidatos podem preencher os detalhes.</span><span class="sxs-lookup"><span data-stu-id="bc832-119">In Microsoft Dynamics 365: Attract, forms can appear in Candidate portal, and candidates can fill in details.</span></span> <span data-ttu-id="bc832-120">Os formulários podem ser incorporados como atividades em um modelo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="bc832-120">Forms can also be embedded as activities in a job template.</span></span>

<span data-ttu-id="bc832-121">Quando um candidato envia um formulário, o Microsoft Flow captura o envio do formulário, lê os dados e armazena-os na entidade do Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="bc832-121">When a candidate submits a form, Microsoft Flow captures the form submission, reads the data, and stores it in the Common Data Service entity.</span></span>

<span data-ttu-id="bc832-122">Para baixar o modelo **Flow — Form Connect** e a Estrutura de Entidades Personalizadas, acesse [Flow — Form Connect](https://go.microsoft.com/fwlink/?linkid=2081988) no Centro de Download da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="bc832-122">To download the **Flow – Form Connect** template and Custom Entity Structure, go to [Flow – Form Connect](https://go.microsoft.com/fwlink/?linkid=2081988) on the Microsoft Download Center.</span></span>

## <a name="initiate-and-extract-parameters-passed-to-powerapps"></a><span data-ttu-id="bc832-123">Iniciar e extrair os parâmetros transmitidos para o Powerapps</span><span class="sxs-lookup"><span data-stu-id="bc832-123">Initiate and Extract Parameters Passed to Powerapps</span></span>

<span data-ttu-id="bc832-124">O modelo **Iniciar e extrair os parâmetros transmitidos para o Powerapps** pode ser usado como ponto de partida para qualquer cenário de PowerApps que seja específico para o Attract.</span><span class="sxs-lookup"><span data-stu-id="bc832-124">The **Initiate and Extract Parameters Passed to Powerapps** template can be used as a starting point for any PowerApps scenario that is specific to Attract.</span></span> <span data-ttu-id="bc832-125">Ele inclui todos os parâmetros padrão que são transmitidos pelo Attract, como, **Solicitação de emprego**, **ID do Candidato**e **JobID**.</span><span class="sxs-lookup"><span data-stu-id="bc832-125">It includes all the default parameters that are passed by Attract, such as **Job Application**, **Candidate ID**, and **JobID**.</span></span>

<span data-ttu-id="bc832-126">Esse modelo pode ser usado para recuperar um formulário de avaliação do candidato, de modo que um gerente de contratação possa exibir a avaliação que o candidato preencheu.</span><span class="sxs-lookup"><span data-stu-id="bc832-126">This template can be used to retrieve a candidate assessment form, so that a hiring manager can view the assessment that a candidate filled in.</span></span>

<span data-ttu-id="bc832-127">Os aplicativos criados usando o PowerApps podem ser incorporados no modelo de trabalho no Attract.</span><span class="sxs-lookup"><span data-stu-id="bc832-127">Apps that are created by using PowerApps can be embedded into the job template in Attract.</span></span>

<span data-ttu-id="bc832-128">Para baixar o modelo **Iniciar e extrair os parâmetros transmitidos para o Powerapps** e a Estrutura de Entidades Personalizadas, acesse [Iniciar e extrair os parâmetros transmitidos para o Powerapps](https://go.microsoft.com/fwlink/?linkid=2081991) no Centro de Download da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="bc832-128">To download the **Initiate and Extract Parameters Passed to Powerapps** template and Custom Entity Structure, go to [Initiate and Extract Parameters Passed to Powerapps](https://go.microsoft.com/fwlink/?linkid=2081991) on the Microsoft Download Center.</span></span>

## <a name="integration-with-office-365"></a><span data-ttu-id="bc832-129">Integração ao Office 365</span><span class="sxs-lookup"><span data-stu-id="bc832-129">Integration with Office 365</span></span>

<span data-ttu-id="bc832-130">O aplicativo **Integração com o Office 365** pode ser usado para extrair informações da equipe para usuários conectados a partir do Microsoft Office 365.</span><span class="sxs-lookup"><span data-stu-id="bc832-130">The **Integration with Office 365** app can be used to extract team information for signed-in users from Microsoft Office 365.</span></span> <span data-ttu-id="bc832-131">Ele faz referência aos trabalhadores no Talent para extrair detalhes de registros de entrada e de saída e gravações de exceção.</span><span class="sxs-lookup"><span data-stu-id="bc832-131">It references workers in Talent to extract clock-in and clock-out details and exception recordings.</span></span> <span data-ttu-id="bc832-132">Os detalhes de registros de entrada e de saída são armazenados em entidades personalizadas do Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="bc832-132">Clock-in and Clock-out details are stored in custom Common Data Service entities.</span></span> <span data-ttu-id="bc832-133">A suposição é que esses detalhes são preenchidas por sistemas de terceiros por meio da integração.</span><span class="sxs-lookup"><span data-stu-id="bc832-133">The assumption is that these details are filled in from third-party systems via integration.</span></span>

<span data-ttu-id="bc832-134">Esse aplicativo pode ser estendido para que possa ser usado em outros cenários.</span><span class="sxs-lookup"><span data-stu-id="bc832-134">This app can be extended so that it can be used for other scenarios.</span></span> <span data-ttu-id="bc832-135">Por exemplo, ele pode ser usado para mostrar informações de férias da equipe, eventos do calendário e todos os eventos específicos da equipe.</span><span class="sxs-lookup"><span data-stu-id="bc832-135">For example, it can be used to show team vacation information, calendar events, and any team-specific events.</span></span>

<span data-ttu-id="bc832-136">Para baixar o aplicativo **Integração com o Office 365** e a Estrutura de Entidades Personalizadas, acesse [Integração com Office 365](https://go.microsoft.com/fwlink/?linkid=2081787) no Centro de Download da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="bc832-136">To download the **Integration with Office 365** app and Custome Entity Structure, go to [Integration with Office 365](https://go.microsoft.com/fwlink/?linkid=2081787) on the Microsoft Download Center.</span></span>

## <a name="flow--email-notification"></a><span data-ttu-id="bc832-137">Flow — Notificação por email</span><span class="sxs-lookup"><span data-stu-id="bc832-137">Flow – Email Notification</span></span>

<span data-ttu-id="bc832-138">O modelo **Flow — Notificação por email** pode ser usado em cenários de notificação por email.</span><span class="sxs-lookup"><span data-stu-id="bc832-138">The **Flow – Email Notification** template can be used for email notification scenarios.</span></span> <span data-ttu-id="bc832-139">Ele pode ser usado para acionar o envio de emails de notificação aos candidatos que a equipe de contratação rejeita durante qualquer estágio do processo de recrutamento.</span><span class="sxs-lookup"><span data-stu-id="bc832-139">It can be used to trigger notification emails to candidates that the hiring team rejects during any stage of the recruiting process.</span></span>

<span data-ttu-id="bc832-140">Esse modelo pode ser estendido para controlar alterações no estágio do candidato durante o processo de recrutamento e para enviar notificações à equipe de contratação e ao candidato.</span><span class="sxs-lookup"><span data-stu-id="bc832-140">This template can be extended to track changes to the candidate stage throughout the recruiting process, and to send notifications to the hiring team and candidate.</span></span>

<span data-ttu-id="bc832-141">Em geral, para entidades que são armazenados no Common Data Service, os fluxos podem ser configurados para enviar notificações de eventos que ocorrem no Core HR, no Attract ou no Dynamics 365 Talent: Onboard.</span><span class="sxs-lookup"><span data-stu-id="bc832-141">In general, for entities that are stored in Common Data Service, flows can be set up to send notifications for events that occur in Core HR, Attract, or Dynamics 365 Talent: Onboard.</span></span>

<span data-ttu-id="bc832-142">Para baixar o modelo **Flow — Notificação por email**, acesse [Flow — Notificação por email](https://go.microsoft.com/fwlink/?linkid=2082103) no Centro de Download da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="bc832-142">To download the **Flow – Email Notification** template, go to [Flow – Email Notification](https://go.microsoft.com/fwlink/?linkid=2082103) on the Microsoft Download Center.</span></span>

## <a name="flow--sql-connect-and-execute"></a><span data-ttu-id="bc832-143">Flow — Conectar ao SQL e executar</span><span class="sxs-lookup"><span data-stu-id="bc832-143">Flow – SQL Connect and execute</span></span>

<span data-ttu-id="bc832-144">O modelo **Flow — Conectar ao SQL e executar** conecta-se ao Microsoft SQL Server e habilita a execução de consultas SQL.</span><span class="sxs-lookup"><span data-stu-id="bc832-144">The **Flow – SQL Connect and execute** template connects to Microsoft SQL Server and enables SQL queries to be run.</span></span>

<span data-ttu-id="bc832-145">Embora esse modelo tenha sido criado para ler e atualizar tabelas SQL, ele também pode ser estendido para que possa ser usado em outros cenários.</span><span class="sxs-lookup"><span data-stu-id="bc832-145">Although this template is designed to read and update SQL tables, it can be extended so that it can be used for other scenarios.</span></span> <span data-ttu-id="bc832-146">Por exemplo, ele pode ser usado para preencher uma tabela de preparação no Common Data Service com registros do SQL Server e para sincronizar periodicamente a tabela de preparação usando um push incremental do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="bc832-146">For example, it can be used to fill a staging table in Common Data Service with records from SQL Server, and to periodically synchronize the staging table by using an incremental push from SQL Server.</span></span>

<span data-ttu-id="bc832-147">Para baixar o modelo **Flow — Conectar ao SQL e executar**, acesse [Flow — Conectar ao SQL e executar](https://go.microsoft.com/fwlink/?linkid=2081789) no Centro de Download da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="bc832-147">To download the **Flow – SQL Connect and execute** template, go to [Flow – SQL Connect and execute](https://go.microsoft.com/fwlink/?linkid=2081789) on the Microsoft Download Center.</span></span>

## <a name="flow--sharepoint-integration"></a><span data-ttu-id="bc832-148">Flow — Integração do SharePoint</span><span class="sxs-lookup"><span data-stu-id="bc832-148">Flow – SharePoint Integration</span></span>

<span data-ttu-id="bc832-149">O modelo **Flow — Integração do SharePoint** pode ser usado para ler dados de uma lista do Microsoft SharePoint, comparar a lista com os valores de campo para qualquer entidade do Common Data Service e enviar os resultados da comparação como um email de notificação.</span><span class="sxs-lookup"><span data-stu-id="bc832-149">The **Flow – SharePoint Integration** template can be used to read data from a Microsoft SharePoint list, compare the list with field values for any Common Data Service entity, and send the results of the comparison as a notification email.</span></span> 

<span data-ttu-id="bc832-150">Uma organização pode precisar de um conjunto de habilidades urgentemente.</span><span class="sxs-lookup"><span data-stu-id="bc832-150">An organization might have a set of skills that it urgently requires.</span></span> <span data-ttu-id="bc832-151">Essas habilidades podem ser armazenadas no SharePoint como uma lista do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="bc832-151">These skills can be stored in SharePoint as a SharePoint list.</span></span> <span data-ttu-id="bc832-152">Quando um candidato se candidatar a qualquer trabalho que exija um conjunto de habilidades que esteja listado, se houver uma correspondência significativa entre as habilidade do candidato e as habilidades que estão armazenadas no SharePoint, um email de notificação será enviado.</span><span class="sxs-lookup"><span data-stu-id="bc832-152">When a candidate applies for any job that a set of required skills is listed for, if there is a significant match between the candidate's skill and the skills that are stored in SharePoint, a notification email is sent.</span></span> <span data-ttu-id="bc832-153">Dessa forma, as posições que são necessárias urgentemente são preenchidas com mais rapidez, pois as notificações ajudam os recrutadores a entrar em contato com os candidatos e fazer contratações em toda a organização.</span><span class="sxs-lookup"><span data-stu-id="bc832-153">In this way, positions that are urgently required are filled faster, because the notifications help recruiters reach out and cross-hire candidates throughout the organization.</span></span>

<span data-ttu-id="bc832-154">Esse modelo pode ser estendido para que possa ser usado para qualquer cenário que envolva a integração do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="bc832-154">This template can be extended so that it can be used for any scenario that involves SharePoint integration.</span></span>

<span data-ttu-id="bc832-155">Para baixar o modelo **Flow — Integração do SharePoint**, acesse [Flow — Integração do SharePoint](https://go.microsoft.com/fwlink/?linkid=2082109) no Centro de Download da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="bc832-155">To download the **Flow – SharePoint Integration** template, go to [Flow – SharePoint Integration](https://go.microsoft.com/fwlink/?linkid=2082109) on the Microsoft Download Center.</span></span>

## <a name="admin-console-to-manage-talent-pools"></a><span data-ttu-id="bc832-156">Administração de console para gerenciar grupos do Talent</span><span class="sxs-lookup"><span data-stu-id="bc832-156">Admin console to manage talent pools</span></span>

<span data-ttu-id="bc832-157">Ao habilitar a integração com LinkedIn, Attract cria automaticamente um grupo do Talent no LinkedIn.</span><span class="sxs-lookup"><span data-stu-id="bc832-157">When you enable integration with LinkedIn, Attract automatically createas a LinkedIn talent pool.</span></span> <span data-ttu-id="bc832-158">Quando um recrutador troca InMail com um recruta por meio do LinkedIn, Attract cria um perfil para o recruta, e o recruta se torna membro de um grupo do Talent do LinkedIn.</span><span class="sxs-lookup"><span data-stu-id="bc832-158">When a recruiter exchanges InMail with a recruit through LinkedIn, Attract creates a profile for the recruit, and the recruit becomes a member of the LinkedIn talent pool.</span></span> <span data-ttu-id="bc832-159">Este aplicativo do PowerApps é útil para reorganizar candidatos em grupos do Talent com base em habilidades.</span><span class="sxs-lookup"><span data-stu-id="bc832-159">This PowerApps app is useful for reorganizing candidates in talent pools based on skill.</span></span>

<span data-ttu-id="bc832-160">Execute esse aplicativo do PowerApps como um console do administrador para realizar as tarefas a seguir:</span><span class="sxs-lookup"><span data-stu-id="bc832-160">Run this PowerApps app as an admin console to perform the following tasks:</span></span>

- <span data-ttu-id="bc832-161">Listar candidatos em um grupo de talentos</span><span class="sxs-lookup"><span data-stu-id="bc832-161">List candidates in a talent pool</span></span>
- <span data-ttu-id="bc832-162">Adicionar e remover candidatos de um grupo de talentos</span><span class="sxs-lookup"><span data-stu-id="bc832-162">Add and remove candidates from a talent pool</span></span>
- <span data-ttu-id="bc832-163">Mova candidatos de um grupo do Talent para outro</span><span class="sxs-lookup"><span data-stu-id="bc832-163">Move candidates from one talent pool to another</span></span>
- <span data-ttu-id="bc832-164">Determine se os candidatos já são parte de um grupo do Talent antes de movê-los</span><span class="sxs-lookup"><span data-stu-id="bc832-164">Determine whether candidates are already part of a talent pool before moving them</span></span>
- <span data-ttu-id="bc832-165">Verifique as habilidades dos candidatos antes de movê-los para outros grupos do Talent</span><span class="sxs-lookup"><span data-stu-id="bc832-165">Check the skills of candidates before moving them to other talent pools</span></span>

<span data-ttu-id="bc832-166">Esse aplicativo do PowerApps usa relacionamentos muitos para muitos, então você pode usá-lo como um modelo para outros cenários onde você precisa extrair registros que têm relacionamentos muitos para muitos.</span><span class="sxs-lookup"><span data-stu-id="bc832-166">This PowerApps app uses many-to-many relationships, so you can use it as a template for other scenarios where you need to extract records that have many-to-many relationships.</span></span>

<span data-ttu-id="bc832-167">Para baixar o modelo **Console de administrador para gerenciar grupos do Talent**, acesse [Console de administração para gerenciar grupos do Talent](http://www.microsoft.com/downloads/details.aspx?FamilyID=780a5eee-0e2a-4159-9a83-009f9ccdc469) no Microsoft Download Center.</span><span class="sxs-lookup"><span data-stu-id="bc832-167">To download the **Admin console to manage talent pools** template,  go to [Admin console to manage talent pools](http://www.microsoft.com/downloads/details.aspx?FamilyID=780a5eee-0e2a-4159-9a83-009f9ccdc469) on the Microsoft Download Center.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="bc832-168">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="bc832-168">Additional resources</span></span>

[<span data-ttu-id="bc832-169">A Microsoft Power Platform</span><span class="sxs-lookup"><span data-stu-id="bc832-169">The Microsoft Power Platform</span></span>](https://docs.microsoft.com/power-platform/admin/admin-documentation)

[<span data-ttu-id="bc832-170">Migrar aplicativos entre locatários e ambientes</span><span class="sxs-lookup"><span data-stu-id="bc832-170">Migrate app between tenants and environments</span></span>](https://docs.microsoft.com/en-us/power-platform/admin/environment-and-tenant-migration)
