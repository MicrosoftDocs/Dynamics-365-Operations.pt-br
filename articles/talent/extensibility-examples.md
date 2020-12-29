---
title: Estender o Talent com o Power Apps e o Power Automate
description: Este artigo descreve alguns exemplos de cenários de extensibilidade para o Microsoft Dynamics 365 Talent – Attract que usam o Microsoft Power Apps e o Microsoft Power Automate.
author: negudava
manager: Annbe
ms.date: 02/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent;Core;Experience Apps
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: negudava
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: cfdf36e9486aa4853d3bf674afa73ec3a4d1c161
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "4529625"
---
# <a name="extend-talent-with-power-apps-and-power-automate"></a><span data-ttu-id="c80de-103">Estender o Talent com o Power Apps e o Power Automate</span><span class="sxs-lookup"><span data-stu-id="c80de-103">Extend Talent with Power Apps and Power Automate</span></span>

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="c80de-104">Este artigo descreve alguns exemplos de cenários de extensibilidade para o Microsoft Dynamics 365 Talent: Attract que usam o Microsoft Power Apps e o Microsoft Power Automate.</span><span class="sxs-lookup"><span data-stu-id="c80de-104">This article describes some examples of extensibility scenarios for Microsoft Dynamics 365 Talent: Attract that use Microsoft Power Apps and Microsoft Power Automate.</span></span> <span data-ttu-id="c80de-105">Você pode importar o pacote da solução associado a cada exemplo para o seu ambiente do Power Apps.</span><span class="sxs-lookup"><span data-stu-id="c80de-105">You can import the solution package that is associated with each example into your Power Apps environment.</span></span> <span data-ttu-id="c80de-106">Depois, você pode usar os pacotes como orientação ou como pontos de partida para implementar cenários aplicáveis à sua organização.</span><span class="sxs-lookup"><span data-stu-id="c80de-106">You can then use the packages either as guidance or as starting points to implement scenarios that are applicable to your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c80de-107">Se quiser usar os modelos e o aplicativo que estão descritos neste artigo "no estado em que se encontram", certifique-se de testá-los para garantir que cubram todos os cenários que são específicos à sua implementação.</span><span class="sxs-lookup"><span data-stu-id="c80de-107">If you want to use the templates and app that are described in this article "as is," be sure to test them to make sure that they cover all the scenarios that are specific to your implementation.</span></span>


## <a name="prerequisites"></a><span data-ttu-id="c80de-108">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="c80de-108">Prerequisites</span></span>

- <span data-ttu-id="c80de-109">Para importar os pacotes, os usuários devem ter a permissão **Criador de Ambiente**.</span><span class="sxs-lookup"><span data-stu-id="c80de-109">To import packages, users must have the **Environment Maker** permission.</span></span>
- <span data-ttu-id="c80de-110">Para exportar ou importar aplicativos, os usuários devem ter uma licença do plano 2 do Power Apps ou uma licença de avaliação do plano 2 do Power Apps.</span><span class="sxs-lookup"><span data-stu-id="c80de-110">To export or import apps, users must have a Power Apps Plan 2 license or a Power Apps Plan 2 trial license.</span></span>

## <a name="power-automate--form-connect"></a><span data-ttu-id="c80de-111">Power Automate – Conexão a Formulário</span><span class="sxs-lookup"><span data-stu-id="c80de-111">Power Automate – Form Connect</span></span>

<span data-ttu-id="c80de-112">O modelo **Power Automate – Conexão a Formulário** pode ser usado para ler dados do Microsoft Forms e armazená-los em uma entidade do Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="c80de-112">The **Power Automate – Form Connect** template can be used to read data from Microsoft Forms and store it in a Common Data Service entity.</span></span>

<span data-ttu-id="c80de-113">Esse método pode ser estendido para que possa ser usado em outros cenários.</span><span class="sxs-lookup"><span data-stu-id="c80de-113">This template can be extended so that it can be used for other scenarios.</span></span> <span data-ttu-id="c80de-114">Eis alguns exemplos:</span><span class="sxs-lookup"><span data-stu-id="c80de-114">Here are some examples:</span></span>

- <span data-ttu-id="c80de-115">Capturar avaliações de candidatos.</span><span class="sxs-lookup"><span data-stu-id="c80de-115">Capture candidate assessments.</span></span>
- <span data-ttu-id="c80de-116">Capturar resultados de questionários de cursos.</span><span class="sxs-lookup"><span data-stu-id="c80de-116">Capture results from course questionnaires.</span></span>
- <span data-ttu-id="c80de-117">Compilar uma biblioteca de perguntas de entrevista para os administradores de recursos humanos (RH).</span><span class="sxs-lookup"><span data-stu-id="c80de-117">Compile a library of interview questions for Human resources (HR) administrators.</span></span>
- <span data-ttu-id="c80de-118">Capturar a avaliação de um candidato do processo de entrevista</span><span class="sxs-lookup"><span data-stu-id="c80de-118">Capture a candidate's evaluation of the interview process</span></span>

<span data-ttu-id="c80de-119">No Microsoft Dynamics 365: Attract, você pode usar formulários no portal do candidato, onde os candidatos preenchem os detalhes.</span><span class="sxs-lookup"><span data-stu-id="c80de-119">In Microsoft Dynamics 365: Attract, you can use forms in the candidate portal, where candidates fill in details.</span></span> <span data-ttu-id="c80de-120">Também é possível inserir formulários como atividades em um modelo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="c80de-120">You can also embed forms as activities in a job template.</span></span>

<span data-ttu-id="c80de-121">Quando um candidato envia um formulário, o Microsoft Power Automate captura o envio do formulário, lê os dados e armazena-os na entidade do Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="c80de-121">When a candidate submits a form, Microsoft Power Automate captures the form submission, reads the data, and stores it in the Common Data Service entity.</span></span>

<span data-ttu-id="c80de-122">Para baixar o modelo **Power Automate – Conexão a Formulário** e a Estrutura de Entidades Personalizadas, acesse [Power Automate – Conexão a Formulário](https://go.microsoft.com/fwlink/?linkid=2081988) no Centro de Download da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c80de-122">To download the **Power Automate – Form Connect** template and Custom Entity Structure, go to [Power Automate – Form Connect](https://go.microsoft.com/fwlink/?linkid=2081988) on the Microsoft Download Center.</span></span>

## <a name="power-automate--sharepoint-integration"></a><span data-ttu-id="c80de-123">Integração Power Automate – SharePoint</span><span class="sxs-lookup"><span data-stu-id="c80de-123">Power Automate – SharePoint Integration</span></span>

<span data-ttu-id="c80de-124">O modelo **Integração Power Automate – SharePoint** pode ser usado para ler dados de uma lista do Microsoft SharePoint, comparar a lista com os valores de campo para qualquer entidade do Common Data Service e enviar os resultados da comparação como um email de notificação.</span><span class="sxs-lookup"><span data-stu-id="c80de-124">The **Power Automate – SharePoint Integration** template can be used to read data from a Microsoft SharePoint list, compare the list with field values for any Common Data Service entity, and send the results of the comparison as a notification email.</span></span> 

<span data-ttu-id="c80de-125">Uma organização pode precisar de um conjunto de habilidades urgentemente.</span><span class="sxs-lookup"><span data-stu-id="c80de-125">An organization might have a set of skills that it urgently requires.</span></span> <span data-ttu-id="c80de-126">Essas habilidades podem ser armazenadas no SharePoint como uma lista do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="c80de-126">These skills can be stored in SharePoint as a SharePoint list.</span></span> <span data-ttu-id="c80de-127">Quando um candidato se candidatar a qualquer trabalho que exija um conjunto de habilidades que esteja listado, se houver uma correspondência significativa entre as habilidade do candidato e as habilidades que estão armazenadas no SharePoint, um email de notificação será enviado.</span><span class="sxs-lookup"><span data-stu-id="c80de-127">When a candidate applies for any job that a set of required skills is listed for, if there is a significant match between the candidate's skill and the skills that are stored in SharePoint, a notification email is sent.</span></span> <span data-ttu-id="c80de-128">Isso ajuda a preencher as posições urgentemente necessárias com mais rapidez, pois as notificações ajudam os recrutadores a fazer contratações de candidatos em toda a organização.</span><span class="sxs-lookup"><span data-stu-id="c80de-128">This helps fill positions that are urgently required faster, because the notifications help recruiters cross-hire candidates throughout the organization.</span></span>

<span data-ttu-id="c80de-129">Esse modelo pode ser estendido para que possa ser usado para qualquer cenário que envolva a integração do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="c80de-129">This template can be extended so that it can be used for any scenario that involves SharePoint integration.</span></span>

<span data-ttu-id="c80de-130">Para baixar o modelo **Integração do Power Automate – SharePoint**, acesse [Integração do Power Automate – SharePoint](https://go.microsoft.com/fwlink/?linkid=2082109) no Centro de Download da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c80de-130">To download the **Power Automate – SharePoint Integration** template, go to [Power Automate – SharePoint Integration](https://go.microsoft.com/fwlink/?linkid=2082109) on the Microsoft Download Center.</span></span>

## <a name="referral-app"></a><span data-ttu-id="c80de-131">Aplicativo Referral</span><span class="sxs-lookup"><span data-stu-id="c80de-131">Referral App</span></span>

<span data-ttu-id="c80de-132">Você pode usar o aplicativo Referral para adicionar candidatos a um grupo de talentos compartilhado.</span><span class="sxs-lookup"><span data-stu-id="c80de-132">You can use the Referral App to add candidates to a shared talent pool.</span></span> <span data-ttu-id="c80de-133">O indicador pode inserir **Nome**, **Sobrenome**, **Email** e **URL do LinkedIn** ao enviar um candidato.</span><span class="sxs-lookup"><span data-stu-id="c80de-133">The referrer can enter **Firstname**, **Lastname**, **Email**, and **LinkedIn URL** when submitting a candidate.</span></span> <span data-ttu-id="c80de-134">Em seguida, os metadados de origem do candidato são preenchidos com as informações do indicador.</span><span class="sxs-lookup"><span data-stu-id="c80de-134">The candidate source metadata is then populated with the referrer’s information.</span></span>

<span data-ttu-id="c80de-135">Você pode inserir este aplicativo no Autoatendimento para funcionários a fim de enviar indicações ou pode usá-lo como um hiperlink no portal corporativo e executá-lo como um aplicativo autônomo.</span><span class="sxs-lookup"><span data-stu-id="c80de-135">You can embed this app in Employee self service for submitting referrals, or you can use it as a hyperlink in the corporate portal and run it as a stand-alone app.</span></span>

<span data-ttu-id="c80de-136">Para baixar o **Aplicativo Referral**, acesse a solução de extensibilidade do [Dynamics 365 Talent: aplicativo Referral](https://www.microsoft.com/download/details.aspx?id=58497) no Microsoft Download Center.</span><span class="sxs-lookup"><span data-stu-id="c80de-136">To download **Referral App**, go to [Dynamics 365 Talent extensibility solution: Referral App](https://www.microsoft.com/download/details.aspx?id=58497) on the Microsoft Download Center.</span></span> <span data-ttu-id="c80de-137">Você pode importar este aplicativo e personalizá-lo para adicionar funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="c80de-137">You can import this app and customize it to add additional functionality.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c80de-138">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="c80de-138">Additional resources</span></span>

[<span data-ttu-id="c80de-139">A Microsoft Power Platform</span><span class="sxs-lookup"><span data-stu-id="c80de-139">The Microsoft Power Platform</span></span>](https://docs.microsoft.com/power-platform/admin/admin-documentation)</br>
[<span data-ttu-id="c80de-140">Migrar aplicativos entre locatários e ambientes</span><span class="sxs-lookup"><span data-stu-id="c80de-140">Migrate app between tenants and environments</span></span>](https://docs.microsoft.com/power-platform/admin/environment-and-tenant-migration)
