---
title: Estender o Talent usando o PowerApps e o Microsoft Flow — cenários de exemplo
description: Este tópico descreve alguns exemplos de cenários de extensibilidade para o Microsoft Dynamics 365 for Talent que usam o Microsoft PowerApps e o Microsoft Flow.
author: negudava
manager: Annbe
ms.date: 03/04/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: Dynamics 365 for Talent;PowerApps;Flow;Common Data Service
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent;Core;Experience Apps
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: negudava
ms.search.validFrom: 2019-03-04
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: 0aa3578047b9397682a7039d0dbcc05cc1b167e4
ms.sourcegitcommit: 9796d022a8abf5c07abcdee6852ee34f06d2eb57
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/12/2019
ms.locfileid: "949911"
---
# <a name="extend-talent-by-using-powerapps-and-microsoft-flow---example-scenarios"></a><span data-ttu-id="8b121-103">Estender o Talent usando o PowerApps e o Microsoft Flow — cenários de exemplo</span><span class="sxs-lookup"><span data-stu-id="8b121-103">Extend Talent by using PowerApps and Microsoft Flow - Example scenarios</span></span>

<span data-ttu-id="8b121-104">Este tópico descreve alguns exemplos de cenários de extensibilidade para o Microsoft Dynamics 365 for Talent que usam o Microsoft PowerApps e o Microsoft Flow.</span><span class="sxs-lookup"><span data-stu-id="8b121-104">This topic describes some examples of extensibility scenarios for Microsoft Dynamics 365 for Talent that use Microsoft PowerApps and Microsoft Flow.</span></span> <span data-ttu-id="8b121-105">Você pode importar o pacote da solução que está associado a cada exemplo para seu ambiente do PowerApps.</span><span class="sxs-lookup"><span data-stu-id="8b121-105">You can import the solution package that is associated with each example into your PowerApps environment.</span></span> <span data-ttu-id="8b121-106">Depois, você pode usar os pacotes como orientação ou como pontos de partida para implementar cenários aplicáveis à sua organização.</span><span class="sxs-lookup"><span data-stu-id="8b121-106">You can then use the packages either as guidance or as starting points to implement scenarios that are applicable to your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8b121-107">Se quiser usar os modelos e o aplicativo que estão descritos neste tópico "no estado em que se encontram", certifique-se de testá-los para garantir que cubram todos os cenários que são específicos à sua implementação.</span><span class="sxs-lookup"><span data-stu-id="8b121-107">If you want to use the templates and app that are described in this topic "as is," be sure to test them to make sure that they cover all the scenarios that are specific to your implementation.</span></span>


## <a name="prerequisites"></a><span data-ttu-id="8b121-108">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="8b121-108">Prerequisites</span></span>

- <span data-ttu-id="8b121-109">Para importar os pacotes, os usuários devem ter a permissão **Criador de Ambiente**.</span><span class="sxs-lookup"><span data-stu-id="8b121-109">To import packages, users must have the **Environment Maker** permission.</span></span>
- <span data-ttu-id="8b121-110">Para exportar ou importar aplicativos, os usuários devem ter uma licença do plano 2 do PowerApps ou uma licença de avaliação do plano 2 do PowerApps.</span><span class="sxs-lookup"><span data-stu-id="8b121-110">To export or import apps, users must have a PowerApps Plan 2 license or a PowerApps Plan 2 trial license.</span></span>

## <a name="flow--form-connect"></a><span data-ttu-id="8b121-111">Flow — Form Connect</span><span class="sxs-lookup"><span data-stu-id="8b121-111">Flow – Form Connect</span></span>

<span data-ttu-id="8b121-112">O modelo **Flow — Form Connect** pode ser usado para ler dados do Microsoft Forms e armazená-los em uma entidade do Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="8b121-112">The **Flow – Form Connect** template can be used to read data from Microsoft Forms and store it in a Common Data Service entity.</span></span>

<span data-ttu-id="8b121-113">Esse método pode ser estendido para que possa ser usado em outros cenários.</span><span class="sxs-lookup"><span data-stu-id="8b121-113">This template can be extended so that it can be used for other scenarios.</span></span> <span data-ttu-id="8b121-114">Eis alguns exemplos:</span><span class="sxs-lookup"><span data-stu-id="8b121-114">Here are some examples:</span></span>

- <span data-ttu-id="8b121-115">Capturar avaliações de candidatos.</span><span class="sxs-lookup"><span data-stu-id="8b121-115">Capture candidate assessments.</span></span>
- <span data-ttu-id="8b121-116">Capturar resultados de questionários de cursos.</span><span class="sxs-lookup"><span data-stu-id="8b121-116">Capture results from course questionnaires.</span></span>
- <span data-ttu-id="8b121-117">Compilar uma biblioteca de perguntas de entrevista para os administradores de recursos humanos (RH).</span><span class="sxs-lookup"><span data-stu-id="8b121-117">Compile a library of interview questions for Human resources (HR) administrators.</span></span>
- <span data-ttu-id="8b121-118">Capturar a avaliação de um candidato do processo de entrevista</span><span class="sxs-lookup"><span data-stu-id="8b121-118">Capture a candidate's evaluation of the interview process</span></span>

<span data-ttu-id="8b121-119">No Microsoft Dynamics 365: Attract, os formulários podem aparecer no Portal do candidato, e os candidatos podem preencher os detalhes.</span><span class="sxs-lookup"><span data-stu-id="8b121-119">In Microsoft Dynamics 365: Attract, forms can appear in Candidate portal, and candidates can fill in details.</span></span> <span data-ttu-id="8b121-120">Os formulários podem ser incorporados como atividades em um modelo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="8b121-120">Forms can also be embedded as activities in a job template.</span></span>

<span data-ttu-id="8b121-121">Quando um candidato envia um formulário, o Microsoft Flow captura o envio do formulário, lê os dados e armazena-os na entidade do Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="8b121-121">When a candidate submits a form, Microsoft Flow captures the form submission, reads the data, and stores it in the Common Data Service entity.</span></span>

<span data-ttu-id="8b121-122">Para baixar o modelo **Flow — Form Connect** e a Estrutura de Entidades Personalizadas, acesse [Flow — Form Connect](https://go.microsoft.com/fwlink/?linkid=2081988) no Centro de Download da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8b121-122">To download the **Flow – Form Connect** template and Custom Entity Structure, go to [Flow – Form Connect](https://go.microsoft.com/fwlink/?linkid=2081988) on the Microsoft Download Center.</span></span>

## <a name="initiate-and-extract-parameters-passed-to-powerapps"></a><span data-ttu-id="8b121-123">Iniciar e extrair os parâmetros transmitidos para o Powerapps</span><span class="sxs-lookup"><span data-stu-id="8b121-123">Initiate and Extract Parameters Passed to Powerapps</span></span>

<span data-ttu-id="8b121-124">O modelo **Iniciar e extrair os parâmetros transmitidos para o Powerapps** pode ser usado como ponto de partida para qualquer cenário de PowerApps que seja específico para o Attract.</span><span class="sxs-lookup"><span data-stu-id="8b121-124">The **Initiate and Extract Parameters Passed to Powerapps** template can be used as a starting point for any PowerApps scenario that is specific to Attract.</span></span> <span data-ttu-id="8b121-125">Ele inclui todos os parâmetros padrão que são transmitidos pelo Attract, como, **Solicitação de emprego**, **ID do Candidato**e **JobID**.</span><span class="sxs-lookup"><span data-stu-id="8b121-125">It includes all the default parameters that are passed by Attract, such as **Job Application**, **Candidate ID**, and **JobID**.</span></span>

<span data-ttu-id="8b121-126">Esse modelo pode ser usado para recuperar um formulário de avaliação do candidato, de modo que um gerente de contratação possa exibir a avaliação que o candidato preencheu.</span><span class="sxs-lookup"><span data-stu-id="8b121-126">This template can be used to retrieve a candidate assessment form, so that a hiring manager can view the assessment that a candidate filled in.</span></span>

<span data-ttu-id="8b121-127">Os aplicativos criados usando o PowerApps podem ser incorporados no modelo de trabalho no Attract.</span><span class="sxs-lookup"><span data-stu-id="8b121-127">Apps that are created by using PowerApps can be embedded into the job template in Attract.</span></span>

<span data-ttu-id="8b121-128">Para baixar o modelo **Iniciar e extrair os parâmetros transmitidos para o Powerapps** e a Estrutura de Entidades Personalizadas, acesse [Iniciar e extrair os parâmetros transmitidos para o Powerapps](https://go.microsoft.com/fwlink/?linkid=2081991) no Centro de Download da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8b121-128">To download the **Initiate and Extract Parameters Passed to Powerapps** template and Custom Entity Structure, go to [Initiate and Extract Parameters Passed to Powerapps](https://go.microsoft.com/fwlink/?linkid=2081991) on the Microsoft Download Center.</span></span>

## <a name="integration-with-office-365"></a><span data-ttu-id="8b121-129">Integração ao Office 365</span><span class="sxs-lookup"><span data-stu-id="8b121-129">Integration with Office 365</span></span>

<span data-ttu-id="8b121-130">O aplicativo **Integração com o Office 365** pode ser usado para extrair informações da equipe para usuários conectados a partir do Microsoft Office 365.</span><span class="sxs-lookup"><span data-stu-id="8b121-130">The **Integration with Office 365** app can be used to extract team information for signed-in users from Microsoft Office 365.</span></span> <span data-ttu-id="8b121-131">Ele faz referência aos trabalhadores no Talent para extrair detalhes de registros de entrada e de saída e gravações de exceção.</span><span class="sxs-lookup"><span data-stu-id="8b121-131">It references workers in Talent to extract clock-in and clock-out details and exception recordings.</span></span> <span data-ttu-id="8b121-132">Os detalhes de registros de entrada e de saída são armazenados em entidades personalizadas do Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="8b121-132">Clock-in and Clock-out details are stored in custom Common Data Service entities.</span></span> <span data-ttu-id="8b121-133">A suposição é que esses detalhes são preenchidas por sistemas de terceiros por meio da integração.</span><span class="sxs-lookup"><span data-stu-id="8b121-133">The assumption is that these details are filled in from third-party systems via integration.</span></span>

<span data-ttu-id="8b121-134">Esse aplicativo pode ser estendido para que possa ser usado em outros cenários.</span><span class="sxs-lookup"><span data-stu-id="8b121-134">This app can be extended so that it can be used for other scenarios.</span></span> <span data-ttu-id="8b121-135">Por exemplo, ele pode ser usado para mostrar informações de férias da equipe, eventos do calendário e todos os eventos específicos da equipe.</span><span class="sxs-lookup"><span data-stu-id="8b121-135">For example, it can be used to show team vacation information, calendar events, and any team-specific events.</span></span>

<span data-ttu-id="8b121-136">Para baixar o aplicativo **Integração com o Office 365** e a Estrutura de Entidades Personalizadas, acesse [Integração com Office 365](https://go.microsoft.com/fwlink/?linkid=2081787) no Centro de Download da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8b121-136">To download the **Integration with Office 365** app and Custome Entity Structure, go to [Integration with Office 365](https://go.microsoft.com/fwlink/?linkid=2081787) on the Microsoft Download Center.</span></span>

## <a name="flow--email-notification"></a><span data-ttu-id="8b121-137">Flow — Notificação por email</span><span class="sxs-lookup"><span data-stu-id="8b121-137">Flow – Email Notification</span></span>

<span data-ttu-id="8b121-138">O modelo **Flow — Notificação por email** pode ser usado em cenários de notificação por email.</span><span class="sxs-lookup"><span data-stu-id="8b121-138">The **Flow – Email Notification** template can be used for email notification scenarios.</span></span> <span data-ttu-id="8b121-139">Ele pode ser usado para acionar o envio de emails de notificação aos candidatos que a equipe de contratação rejeita durante qualquer estágio do processo de recrutamento.</span><span class="sxs-lookup"><span data-stu-id="8b121-139">It can be used to trigger notification emails to candidates that the hiring team rejects during any stage of the recruiting process.</span></span>

<span data-ttu-id="8b121-140">Esse modelo pode ser estendido para controlar alterações no estágio do candidato durante o processo de recrutamento e para enviar notificações à equipe de contratação e ao candidato.</span><span class="sxs-lookup"><span data-stu-id="8b121-140">This template can be extended to track changes to the candidate stage throughout the recruiting process, and to send notifications to the hiring team and candidate.</span></span>

<span data-ttu-id="8b121-141">Em geral, para entidades que são armazenados no Common Data Service, os fluxos podem ser configurados para enviar notificações de eventos que ocorrem no Core HR, no Attract ou no Dynamics 365 Talent: Onboard.</span><span class="sxs-lookup"><span data-stu-id="8b121-141">In general, for entities that are stored in Common Data Service, flows can be set up to send notifications for events that occur in Core HR, Attract, or Dynamics 365 Talent: Onboard.</span></span>

<span data-ttu-id="8b121-142">Para baixar o modelo **Flow — Notificação por email**, acesse [Flow — Notificação por email](https://go.microsoft.com/fwlink/?linkid=2082103) no Centro de Download da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8b121-142">To download the **Flow – Email Notification** template, go to [Flow – Email Notification](https://go.microsoft.com/fwlink/?linkid=2082103) on the Microsoft Download Center.</span></span>

## <a name="flow--sql-connect-and-execute"></a><span data-ttu-id="8b121-143">Flow — Conectar ao SQL e executar</span><span class="sxs-lookup"><span data-stu-id="8b121-143">Flow – SQL Connect and execute</span></span>

<span data-ttu-id="8b121-144">O modelo **Flow — Conectar ao SQL e executar** conecta-se ao Microsoft SQL Server e habilita a execução de consultas SQL.</span><span class="sxs-lookup"><span data-stu-id="8b121-144">The **Flow – SQL Connect and execute** template connects to Microsoft SQL Server and enables SQL queries to be run.</span></span>

<span data-ttu-id="8b121-145">Embora esse modelo tenha sido criado para ler e atualizar tabelas SQL, ele também pode ser estendido para que possa ser usado em outros cenários.</span><span class="sxs-lookup"><span data-stu-id="8b121-145">Although this template is designed to read and update SQL tables, it can be extended so that it can be used for other scenarios.</span></span> <span data-ttu-id="8b121-146">Por exemplo, ele pode ser usado para preencher uma tabela de preparação no Common Data Service com registros do SQL Server e para sincronizar periodicamente a tabela de preparação usando um push incremental do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="8b121-146">For example, it can be used to fill a staging table in Common Data Service with records from SQL Server, and to periodically synchronize the staging table by using an incremental push from SQL Server.</span></span>

<span data-ttu-id="8b121-147">Para baixar o modelo **Flow — Conectar ao SQL e executar**, acesse [Flow — Conectar ao SQL e executar](https://go.microsoft.com/fwlink/?linkid=2081789) no Centro de Download da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8b121-147">To download the **Flow – SQL Connect and execute** template, go to [Flow – SQL Connect and execute](https://go.microsoft.com/fwlink/?linkid=2081789) on the Microsoft Download Center.</span></span>

## <a name="flow--sharepoint-integration"></a><span data-ttu-id="8b121-148">Flow — Integração do SharePoint</span><span class="sxs-lookup"><span data-stu-id="8b121-148">Flow – SharePoint Integration</span></span>

<span data-ttu-id="8b121-149">O modelo **Flow — Integração do SharePoint** pode ser usado para ler dados de uma lista do Microsoft SharePoint, comparar a lista com os valores de campo para qualquer entidade do Common Data Service e enviar os resultados da comparação como um email de notificação.</span><span class="sxs-lookup"><span data-stu-id="8b121-149">The **Flow – SharePoint Integration** template can be used to read data from a Microsoft SharePoint list, compare the list with field values for any Common Data Service entity, and send the results of the comparison as a notification email.</span></span> 

<span data-ttu-id="8b121-150">Uma organização pode precisar de um conjunto de habilidades urgentemente.</span><span class="sxs-lookup"><span data-stu-id="8b121-150">An organization might have a set of skills that it urgently requires.</span></span> <span data-ttu-id="8b121-151">Essas habilidades podem ser armazenadas no SharePoint como uma lista do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="8b121-151">These skills can be stored in SharePoint as a SharePoint list.</span></span> <span data-ttu-id="8b121-152">Quando um candidato se candidatar a qualquer trabalho que exija um conjunto de habilidades que esteja listado, se houver uma correspondência significativa entre as habilidade do candidato e as habilidades que estão armazenadas no SharePoint, um email de notificação será enviado.</span><span class="sxs-lookup"><span data-stu-id="8b121-152">When a candidate applies for any job that a set of required skills is listed for, if there is a significant match between the candidate's skill and the skills that are stored in SharePoint, a notification email is sent.</span></span> <span data-ttu-id="8b121-153">Dessa forma, as posições que são necessárias urgentemente são preenchidas com mais rapidez, pois as notificações ajudam os recrutadores a entrar em contato com os candidatos e fazer contratações em toda a organização.</span><span class="sxs-lookup"><span data-stu-id="8b121-153">In this way, positions that are urgently required are filled faster, because the notifications help recruiters reach out and cross-hire candidates throughout the organization.</span></span>

<span data-ttu-id="8b121-154">Esse modelo pode ser estendido para que possa ser usado para qualquer cenário que envolva a integração do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="8b121-154">This template can be extended so that it can be used for any scenario that involves SharePoint integration.</span></span>

<span data-ttu-id="8b121-155">Para baixar o modelo **Flow — Integração do SharePoint**, acesse [Flow — Integração do SharePoint](https://go.microsoft.com/fwlink/?linkid=2082109) no Centro de Download da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8b121-155">To download the **Flow – SharePoint Integration** template, go to [Flow – SharePoint Integration](https://go.microsoft.com/fwlink/?linkid=2082109) on the Microsoft Download Center.</span></span>



## <a name="additional-resources"></a><span data-ttu-id="8b121-156">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="8b121-156">Additional resources</span></span>

[<span data-ttu-id="8b121-157">A Microsoft Power Platform</span><span class="sxs-lookup"><span data-stu-id="8b121-157">The Microsoft Power Platform</span></span>](https://docs.microsoft.com/power-platform/admin/admin-documentation)

[<span data-ttu-id="8b121-158">Migrar aplicativos entre locatários e ambientes</span><span class="sxs-lookup"><span data-stu-id="8b121-158">Migrate app between tenants and environments</span></span>](https://docs.microsoft.com/en-us/power-platform/admin/environment-and-tenant-migration)
