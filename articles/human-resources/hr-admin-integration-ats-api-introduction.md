---
title: Introdução da API de integração do sistema de acompanhamento de candidatos
description: Este tópico descreve a API de integração do ATS (sistema de acompanhamento de candidatos) do Dynamics 365 Human Resources.
author: andreabichsel
ms.date: 02/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 599f9728019cd6bc59c59a4f08df06c6c9c9ac31
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5798408"
---
# <a name="applicant-tracking-system-integration-api-introduction"></a><span data-ttu-id="aeb5d-103">Introdução da API de integração do sistema de acompanhamento de candidatos</span><span class="sxs-lookup"><span data-stu-id="aeb5d-103">Applicant Tracking System integration API introduction</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="aeb5d-104">Este tópico descreve a API de integração do ATS (sistema de acompanhamento de candidatos) do Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="aeb5d-104">This topic describes the Dynamics 365 Human Resources Applicant Tracking System (ATS) integration API.</span></span> <span data-ttu-id="aeb5d-105">A intenção da API é habilitar integrações otimizadas entre o Dynamics 365 Human Resources e ATSs de parceria.</span><span class="sxs-lookup"><span data-stu-id="aeb5d-105">The intent of the API is to enable streamlined integrations between Dynamics 365 Human Resources and partnering ATSs.</span></span>

![Fluxo de integração do ATS](media/hr-admin-integration-ats-api-introduction-flow.png)

<span data-ttu-id="aeb5d-107">A experiência integrada começa no Human Resources quando um gerente de contratação cria uma solicitação de recrutamento.</span><span class="sxs-lookup"><span data-stu-id="aeb5d-107">The integrated experience begins in Human Resources when a hiring manager creates a recruiting request.</span></span> <span data-ttu-id="aeb5d-108">Quando a solicitação é ativada, o ATS recebe os detalhes da solicitação para criar um projeto de recrutamento.</span><span class="sxs-lookup"><span data-stu-id="aeb5d-108">When the request is activated, the ATS pulls the detail for the request to create a recruiting project.</span></span> <span data-ttu-id="aeb5d-109">Ele segue o pipeline de recrutamento para selecionar e contratar um candidato para as posições.</span><span class="sxs-lookup"><span data-stu-id="aeb5d-109">Then it follows the recruiting pipeline to select and hire a candidate for the position(s).</span></span> <span data-ttu-id="aeb5d-110">Finalmente, o ATS conclui a integração de ida e volta enviando o registro do candidato selecionado para o Human Resources.</span><span class="sxs-lookup"><span data-stu-id="aeb5d-110">Finally, the ATS completes the round-trip integration by sending the selected candidate’s record into Human Resources.</span></span> <span data-ttu-id="aeb5d-111">O registro de candidatos pode passar pela integração de mais validações e fluxos de trabalho para criar o registro de funcionário.</span><span class="sxs-lookup"><span data-stu-id="aeb5d-111">The candidate record can then go through more onboarding validations and workflows to create the employee record.</span></span>

<span data-ttu-id="aeb5d-112">Para habilitar a integração, o Human Resources adicionou os seguintes componentes:</span><span class="sxs-lookup"><span data-stu-id="aeb5d-112">To enable the integration, Human Resources has added the following components:</span></span>

1.  <span data-ttu-id="aeb5d-113">Funcionalidade para criar uma solicitação de recrutamento.</span><span class="sxs-lookup"><span data-stu-id="aeb5d-113">Functionality to create a recruiting request.</span></span>
2.  <span data-ttu-id="aeb5d-114">Um perfil de candidato expandido e os fluxos de trabalho relacionados.</span><span class="sxs-lookup"><span data-stu-id="aeb5d-114">An expanded candidate profile and related workflows.</span></span>
3.  <span data-ttu-id="aeb5d-115">Uma API de integração que abre a nova funcionalidade para integrar aplicativos.</span><span class="sxs-lookup"><span data-stu-id="aeb5d-115">An integration API opening up the new functionality to integrating applications.</span></span>

<span data-ttu-id="aeb5d-116">Para obter mais informações sobre como configurar e usar a solicitação de recrutamento e a funcionalidade do candidato, consulte [Recrutar candidatos ao trabalho](hr-personnel-recruit.md).</span><span class="sxs-lookup"><span data-stu-id="aeb5d-116">For more information about setting up and using the recruiting request and candidate functionality, see [Recruit job candidates](hr-personnel-recruit.md).</span></span>

## <a name="microsoft-dataverse"></a><span data-ttu-id="aeb5d-117">Microsoft Dataverse</span><span class="sxs-lookup"><span data-stu-id="aeb5d-117">Microsoft Dataverse</span></span>

<span data-ttu-id="aeb5d-118">Esta API foi desenvolvida com base no Microsoft Dataverse (antes conhecido como Common Data Service).</span><span class="sxs-lookup"><span data-stu-id="aeb5d-118">This API is built on Microsoft Dataverse (formerly Common Data Service).</span></span> <span data-ttu-id="aeb5d-119">Toda a interação RESTful com essa API é realizada por meio da API Web do Microsoft Dataverse, que usa OData.</span><span class="sxs-lookup"><span data-stu-id="aeb5d-119">All RESTful interaction with this API is done via the Microsoft Dataverse Web API, which uses OData.</span></span> <span data-ttu-id="aeb5d-120">Essa API é um subconjunto da API Web do Dataverse.</span><span class="sxs-lookup"><span data-stu-id="aeb5d-120">This API is a subset of the Dataverse Web API.</span></span> <span data-ttu-id="aeb5d-121">A API Web do Dataverse define características como autenticação, SLAs, lote, controle de simultaneidade e tratamento de erros.</span><span class="sxs-lookup"><span data-stu-id="aeb5d-121">The Dataverse Web API defines characteristics such as authentication, SLAs, batch, concurrency control, and error handling.</span></span>

<span data-ttu-id="aeb5d-122">Para obter mais informações gerais sobre a API Web do Microsoft Dataverse, consulte:</span><span class="sxs-lookup"><span data-stu-id="aeb5d-122">For more general information about the Microsoft Dataverse Web API, see:</span></span>

- [<span data-ttu-id="aeb5d-123">O que é o Microsoft Dataverse?</span><span class="sxs-lookup"><span data-stu-id="aeb5d-123">What is Microsoft Dataverse?</span></span>](https://docs.microsoft.com/powerapps/maker/data-platform/data-platform-intro)
- [<span data-ttu-id="aeb5d-124">Use a API Web do Microsoft Dataverse</span><span class="sxs-lookup"><span data-stu-id="aeb5d-124">Use the Microsoft Dataverse Web API</span></span>](https://docs.microsoft.com/powerapps/developer/data-platform/webapi/overview)
- [<span data-ttu-id="aeb5d-125">Guia do desenvolvedor do Microsoft Dataverse</span><span class="sxs-lookup"><span data-stu-id="aeb5d-125">Microsoft Dataverse developer guide</span></span>](https://docs.microsoft.com/powerapps/developer/data-platform)

<span data-ttu-id="aeb5d-126">A documentação acima inclui diretrizes de detalhe e desenvolvedor sobre o uso da API Web do Dataverse, como [gerenciamento de autenticação](https://docs.microsoft.com/powerapps/developer/data-platform/webapi/authenticate-web-api), [execução de operações](https://docs.microsoft.com/powerapps/developer/data-platform/webapi/perform-operations-web-api), [uso do Postman com a API](https://docs.microsoft.com/powerapps/developer/data-platform/webapi/use-postman-web-api) e [uso de controle de alterações ou tokens delta](https://docs.microsoft.com/powerapps/developer/data-platform/use-change-tracking-synchronize-data-external-systems) com a API.</span><span class="sxs-lookup"><span data-stu-id="aeb5d-126">The above documentation includes detail and developer guidance on using the Dataverse Web API, such as [managing authentication](https://docs.microsoft.com/powerapps/developer/data-platform/webapi/authenticate-web-api), [performing operations](https://docs.microsoft.com/powerapps/developer/data-platform/webapi/perform-operations-web-api), [using Postman with the API](https://docs.microsoft.com/powerapps/developer/data-platform/webapi/use-postman-web-api), and [using change tracking or delta tokens](https://docs.microsoft.com/powerapps/developer/data-platform/use-change-tracking-synchronize-data-external-systems) with the API.</span></span>

### <a name="option-sets"></a><span data-ttu-id="aeb5d-127">Conjuntos de opções</span><span class="sxs-lookup"><span data-stu-id="aeb5d-127">Option sets</span></span>

<span data-ttu-id="aeb5d-128">O modelo de dados para a API de integração ATS descrito neste documento inclui conjuntos de opções que fornecem valores enumerados associados a propriedades da entidade.</span><span class="sxs-lookup"><span data-stu-id="aeb5d-128">The data model for the ATS integration API described in this document includes option sets that provide enumerated values associated with entity properties.</span></span> <span data-ttu-id="aeb5d-129">Para obter detalhes sobre como trabalhar com conjuntos de opções na API Web do Dataverse, consulte [Criar e atualizar conjuntos de opções usando a API Web](https://docs.microsoft.com/powerapps/developer/data-platform/webapi/create-update-optionsets).</span><span class="sxs-lookup"><span data-stu-id="aeb5d-129">For detail on working with option sets in the Dataverse Web API, see [Create and update option sets using the Web API](https://docs.microsoft.com/powerapps/developer/data-platform/webapi/create-update-optionsets).</span></span> <span data-ttu-id="aeb5d-130">Os conjuntos de opções são definidos para cada ambiente do Dataverse.</span><span class="sxs-lookup"><span data-stu-id="aeb5d-130">Option sets are defined for each Dataverse environment.</span></span>

### <a name="virtual-tables-for-human-resources-in-dataverse"></a><span data-ttu-id="aeb5d-131">Tabelas virtuais para o Human Resources no Dataverse</span><span class="sxs-lookup"><span data-stu-id="aeb5d-131">Virtual tables for Human Resources in Dataverse</span></span>

<span data-ttu-id="aeb5d-132">Os pontos de extremidade para a API de integração ATS usam os recursos da plataforma de tabela virtual do Microsoft Dataverse.</span><span class="sxs-lookup"><span data-stu-id="aeb5d-132">The endpoints for the ATS integration API use the virtual table platform capabilities of Microsoft Dataverse.</span></span> <span data-ttu-id="aeb5d-133">Por padrão, as tabelas virtuais e os pontos de extremidade da API associados não são implantados para ambientes do Human Resources, permitindo que organizações determinem quais pontos de extremidade OData serão expostos para o ambiente.</span><span class="sxs-lookup"><span data-stu-id="aeb5d-133">By default, the virtual tables and their associated API endpoints are not deployed for Human Resources environments, enabling organizations to determine which OData endpoints will be exposed for the environment.</span></span> <span data-ttu-id="aeb5d-134">Para usar a API, as tabelas virtuais de entidades do Human Resources devem ser geradas para o ambiente.</span><span class="sxs-lookup"><span data-stu-id="aeb5d-134">To use the API, the virtual tables for the Human Resources entities must be generated for the environment.</span></span> 

<span data-ttu-id="aeb5d-135">Para obter informações sobre como gerar as tabelas virtuais da API, consulte [Configurar tabelas virtuais do Dataverse](https://docs.microsoft.com/dynamics365/human-resources/hr-admin-integration-common-data-service-virtual-entities).</span><span class="sxs-lookup"><span data-stu-id="aeb5d-135">For information on generating the virtual tables for the API, see [Configure Dataverse virtual tables](https://docs.microsoft.com/dynamics365/human-resources/hr-admin-integration-common-data-service-virtual-entities).</span></span>

## <a name="data-model"></a><span data-ttu-id="aeb5d-136">Modelo de dados</span><span class="sxs-lookup"><span data-stu-id="aeb5d-136">Data model</span></span>

<span data-ttu-id="aeb5d-137">O modelo de dados está centrado em duas entidades principais:</span><span class="sxs-lookup"><span data-stu-id="aeb5d-137">The data model is centered around two main entities:</span></span>

- <span data-ttu-id="aeb5d-138">**RecruitingRequest** representa uma solicitação de um ATS para recrutar uma ou mais posições abertas. Para obter um exemplo de consulta, consulte [Exemplo de consulta para solicitação de recrutamento](hr-admin-integration-ats-api-recruiting-request-example-query.md).</span><span class="sxs-lookup"><span data-stu-id="aeb5d-138">**RecruitingRequest** represents a request to an ATS to recruit for one or more open positions.For an example query, see [Example query for Recruiting request](hr-admin-integration-ats-api-recruiting-request-example-query.md).</span></span>
- <span data-ttu-id="aeb5d-139">**CandidateToHire** representa detalhes de um candidato que aceitou uma oferta para uma posição.</span><span class="sxs-lookup"><span data-stu-id="aeb5d-139">**CandidateToHire** represents details of a candidate who has accepted an offer for a position.</span></span> <span data-ttu-id="aeb5d-140">**Pessoa** representa o indivíduo que é o candidato.</span><span class="sxs-lookup"><span data-stu-id="aeb5d-140">**Person** represents the individual who is the candidate.</span></span> <span data-ttu-id="aeb5d-141">Uma pessoa pode ter várias funções na empresa, como candidato, trabalhador, funcionário ou prestador de serviço.</span><span class="sxs-lookup"><span data-stu-id="aeb5d-141">A person can have multiple roles in the company, such as candidate, worker, employee, or contractor.</span></span> <span data-ttu-id="aeb5d-142">Para obter um exemplo de consulta, consulte [Exemplo de consulta de candidato a ser contratado](hr-admin-integration-ats-api-candidate-to-hire-example-query.md).</span><span class="sxs-lookup"><span data-stu-id="aeb5d-142">For an example query, see [Example query for Candidate to hire](hr-admin-integration-ats-api-candidate-to-hire-example-query.md).</span></span>

<span data-ttu-id="aeb5d-143">O diagrama a seguir ilustra relacionamentos na API.</span><span class="sxs-lookup"><span data-stu-id="aeb5d-143">The following diagram illustrates relationships within the API.</span></span> <span data-ttu-id="aeb5d-144">Vários tipos têm chaves estrangeiras para outras entidades preexistentes no Human Resources que não estão ilustradas aqui.</span><span class="sxs-lookup"><span data-stu-id="aeb5d-144">Several types have foreign keys to other, pre-existing entities in Human Resources that aren't illustrated here.</span></span> <span data-ttu-id="aeb5d-145">Este documento fornece informações sobre entidades específicas para recrutar cenários de integração.</span><span class="sxs-lookup"><span data-stu-id="aeb5d-145">This document provides information on entities that are specific to recruiting integration scenarios.</span></span> <span data-ttu-id="aeb5d-146">No entanto, há várias outras entidades na API Web do Dataverse para o Dynamics 365 Human Resources que também podem ser relevantes para sua integração.</span><span class="sxs-lookup"><span data-stu-id="aeb5d-146">However, there are many other entities in the Dataverse Web API for Dynamics 365 Human Resources that may also be relevant to your integration.</span></span> <span data-ttu-id="aeb5d-147">Por exemplo, você também pode precisar de detalhes sobre trabalhadores, cargos, posições ou outras entidades não definidas aqui.</span><span class="sxs-lookup"><span data-stu-id="aeb5d-147">For example, you may also need detail for workers, jobs, positions, or other entities not defined here.</span></span> <span data-ttu-id="aeb5d-148">Muitas dessas entidades são referenciadas em relações de chave estrangeira ou propriedades de navegação.</span><span class="sxs-lookup"><span data-stu-id="aeb5d-148">Many of these entities are referenced in foreign key relationships or navigation properties.</span></span>

![Modelo de dados de API de integração do ATS](media/hr-admin-integration-ats-api-data-model.png)

## <a name="recruiting-request-and-related-entities-and-option-sets"></a><span data-ttu-id="aeb5d-150">Recrutar solicitação, entidades relacionadas e conjuntos de opções</span><span class="sxs-lookup"><span data-stu-id="aeb5d-150">Recruiting request and related entities and option sets</span></span>

<span data-ttu-id="aeb5d-151">Exemplo de consulta:</span><span class="sxs-lookup"><span data-stu-id="aeb5d-151">Example query:</span></span> 

- [<span data-ttu-id="aeb5d-152">Consulta de exemplo de solicitação de recrutamento</span><span class="sxs-lookup"><span data-stu-id="aeb5d-152">Example query for Recruiting request</span></span>](hr-admin-integration-ats-api-recruiting-request-example-query.md)

<span data-ttu-id="aeb5d-153">Entidades:</span><span class="sxs-lookup"><span data-stu-id="aeb5d-153">Entities:</span></span>

- [<span data-ttu-id="aeb5d-154">Solicitação de recrutamento</span><span class="sxs-lookup"><span data-stu-id="aeb5d-154">Recruiting request</span></span>](hr-admin-integration-ats-api-recruiting-request.md)
- [<span data-ttu-id="aeb5d-155">Posição da solicitação de recrutamento</span><span class="sxs-lookup"><span data-stu-id="aeb5d-155">Recruiting request position</span></span>](hr-admin-integration-ats-api-recruiting-request-position.md)
- [<span data-ttu-id="aeb5d-156">Habilidade de solicitação de recrutamento</span><span class="sxs-lookup"><span data-stu-id="aeb5d-156">Recruiting request skill</span></span>](hr-admin-integration-ats-api-recruiting-request-skill.md)
- [<span data-ttu-id="aeb5d-157">Formação educacional de solicitação de recrutamento</span><span class="sxs-lookup"><span data-stu-id="aeb5d-157">Recruiting request education</span></span>](hr-admin-integration-ats-api-recruiting-request-education.md)
- [<span data-ttu-id="aeb5d-158">Localização da solicitação de recrutamento</span><span class="sxs-lookup"><span data-stu-id="aeb5d-158">Recruiting request location</span></span>](hr-admin-integration-ats-api-recruiting-request-location.md)

<span data-ttu-id="aeb5d-159">Conjuntos de opções:</span><span class="sxs-lookup"><span data-stu-id="aeb5d-159">Option sets:</span></span>

- [<span data-ttu-id="aeb5d-160">Status de isenção de trabalho</span><span class="sxs-lookup"><span data-stu-id="aeb5d-160">Job exempt status</span></span>](hr-admin-integration-ats-api-job-exempt-status.md)
- [<span data-ttu-id="aeb5d-161">Status da posição da solicitação de recrutamento</span><span class="sxs-lookup"><span data-stu-id="aeb5d-161">Recruiting request position status</span></span>](hr-admin-integration-ats-api-recruiting-request-position-status.md)
- [<span data-ttu-id="aeb5d-162">Status da solicitação de recrutamento</span><span class="sxs-lookup"><span data-stu-id="aeb5d-162">Recruiting request status</span></span>](hr-admin-integration-ats-api-recruiting-request-status.md)
- [<span data-ttu-id="aeb5d-163">Categoria de trabalho regulatório</span><span class="sxs-lookup"><span data-stu-id="aeb5d-163">Regulatory job category</span></span>](hr-admin-integration-ats-api-regulatory-job-category.md)

## <a name="candidate-to-hire-and-related-entities-and-option-sets"></a><span data-ttu-id="aeb5d-164">Candidato a ser contratado, entidades relacionadas e conjuntos de opções</span><span class="sxs-lookup"><span data-stu-id="aeb5d-164">Candidate to hire and related entities and option sets</span></span>

<span data-ttu-id="aeb5d-165">Exemplo de consulta:</span><span class="sxs-lookup"><span data-stu-id="aeb5d-165">Example query:</span></span>

- [<span data-ttu-id="aeb5d-166">Exemplo de consulta de candidato a ser contratado</span><span class="sxs-lookup"><span data-stu-id="aeb5d-166">Example query for Candidate to hire</span></span>](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)

<span data-ttu-id="aeb5d-167">Entidades:</span><span class="sxs-lookup"><span data-stu-id="aeb5d-167">Entities:</span></span>

- [<span data-ttu-id="aeb5d-168">Candidatos para contratação</span><span class="sxs-lookup"><span data-stu-id="aeb5d-168">Candidate to hire</span></span>](hr-admin-integration-ats-api-candidate-to-hire.md)
- [<span data-ttu-id="aeb5d-169">Pessoa</span><span class="sxs-lookup"><span data-stu-id="aeb5d-169">Person</span></span>](hr-admin-integration-ats-api-person.md)
- [<span data-ttu-id="aeb5d-170">Educação da pessoa</span><span class="sxs-lookup"><span data-stu-id="aeb5d-170">Person education</span></span>](hr-admin-integration-ats-api-person-education.md)
- [<span data-ttu-id="aeb5d-171">Experiência profissional da pessoa</span><span class="sxs-lookup"><span data-stu-id="aeb5d-171">Person professional experience</span></span>](hr-admin-integration-ats-api-person-professional-experience.md)
- [<span data-ttu-id="aeb5d-172">Endereço da pessoa</span><span class="sxs-lookup"><span data-stu-id="aeb5d-172">Person address</span></span>](hr-admin-integration-ats-api-person-address.md)
- [<span data-ttu-id="aeb5d-173">Contato do participante</span><span class="sxs-lookup"><span data-stu-id="aeb5d-173">Party contact</span></span>](hr-admin-integration-ats-api-party-contact.md)
- [<span data-ttu-id="aeb5d-174">Habilidade da pessoa</span><span class="sxs-lookup"><span data-stu-id="aeb5d-174">Person skill</span></span>](hr-admin-integration-ats-api-person-skill.md)
- [<span data-ttu-id="aeb5d-175">Nível de avaliação</span><span class="sxs-lookup"><span data-stu-id="aeb5d-175">Rating level</span></span>](hr-admin-integration-ats-api-rating-level.md)
- [<span data-ttu-id="aeb5d-176">Certificado de pessoa</span><span class="sxs-lookup"><span data-stu-id="aeb5d-176">Person certificate</span></span>](hr-admin-integration-ats-api-person-certificate.md)
- [<span data-ttu-id="aeb5d-177">Tipo de certificado</span><span class="sxs-lookup"><span data-stu-id="aeb5d-177">Certificate type</span></span>](hr-admin-integration-ats-api-certificate-type.md)
- [<span data-ttu-id="aeb5d-178">Triagem da pessoa</span><span class="sxs-lookup"><span data-stu-id="aeb5d-178">Person screening</span></span>](hr-admin-integration-ats-api-person-screening.md)
- [<span data-ttu-id="aeb5d-179">Tipos de triagem</span><span class="sxs-lookup"><span data-stu-id="aeb5d-179">Screening types</span></span>](hr-admin-integration-ats-api-screening-types.md)
- [<span data-ttu-id="aeb5d-180">Número de identificação da pessoa</span><span class="sxs-lookup"><span data-stu-id="aeb5d-180">Person identification number</span></span>](hr-admin-integration-ats-api-person-identification-number.md)

<span data-ttu-id="aeb5d-181">Conjuntos de opções:</span><span class="sxs-lookup"><span data-stu-id="aeb5d-181">Option sets:</span></span>

- [<span data-ttu-id="aeb5d-182">Resultado da integração do candidato</span><span class="sxs-lookup"><span data-stu-id="aeb5d-182">Applicant integration result</span></span>](hr-admin-integration-ats-api-applicant-integration-result.md)
- [<span data-ttu-id="aeb5d-183">Em branco Sim/Não</span><span class="sxs-lookup"><span data-stu-id="aeb5d-183">Blank Yes No</span></span>](hr-admin-integration-ats-api-blank-yes-no.md)
- [<span data-ttu-id="aeb5d-184">Status de conclusão</span><span class="sxs-lookup"><span data-stu-id="aeb5d-184">Completion status</span></span>](hr-admin-integration-ats-api-completion-status.md)
- [<span data-ttu-id="aeb5d-185">Tipo de contato</span><span class="sxs-lookup"><span data-stu-id="aeb5d-185">Contact type</span></span>](hr-admin-integration-ats-api-contact-type.md)
- [<span data-ttu-id="aeb5d-186">Base de crédito de educação</span><span class="sxs-lookup"><span data-stu-id="aeb5d-186">Education credit basis</span></span>](hr-admin-integration-ats-api-education-credit-basis.md)
- [<span data-ttu-id="aeb5d-187">Sexo</span><span class="sxs-lookup"><span data-stu-id="aeb5d-187">Gender</span></span>](hr-admin-integration-ats-api-gender.md)
- [<span data-ttu-id="aeb5d-188">Estado civil</span><span class="sxs-lookup"><span data-stu-id="aeb5d-188">Marital status</span></span>](hr-admin-integration-ats-api-marital-status.md)
- [<span data-ttu-id="aeb5d-189">Meses do ano</span><span class="sxs-lookup"><span data-stu-id="aeb5d-189">Months of year</span></span>](hr-admin-integration-ats-api-months-of-year.md)
- [<span data-ttu-id="aeb5d-190">Não Sim</span><span class="sxs-lookup"><span data-stu-id="aeb5d-190">No Yes</span></span>](hr-admin-integration-ats-api-no-yes.md)
- [<span data-ttu-id="aeb5d-191">Unidade de período</span><span class="sxs-lookup"><span data-stu-id="aeb5d-191">Period unit</span></span>](hr-admin-integration-ats-api-period-unit.md)
- [<span data-ttu-id="aeb5d-192">Frequência de triagem</span><span class="sxs-lookup"><span data-stu-id="aeb5d-192">Screening frequency</span></span>](hr-admin-integration-ats-api-screening-frequency.md)
- [<span data-ttu-id="aeb5d-193">Geração de frequência de triagem de</span><span class="sxs-lookup"><span data-stu-id="aeb5d-193">Screening frequency generate from</span></span>](hr-admin-integration-ats-api-screening-frequency-generate-from.md)
- [<span data-ttu-id="aeb5d-194">Tipo de nível de habilidade</span><span class="sxs-lookup"><span data-stu-id="aeb5d-194">Skill level type</span></span>](hr-admin-integration-ats-api-skill-level-type.md)

## <a name="see-also"></a><span data-ttu-id="aeb5d-195">Consulte também</span><span class="sxs-lookup"><span data-stu-id="aeb5d-195">See also</span></span>

[<span data-ttu-id="aeb5d-196">Candidatos de trabalho de recrutamento</span><span class="sxs-lookup"><span data-stu-id="aeb5d-196">Recruit job candidates</span></span>](hr-personnel-recruit.md)<br>
[<span data-ttu-id="aeb5d-197">O que é o Microsoft Dataverse?</span><span class="sxs-lookup"><span data-stu-id="aeb5d-197">What is Microsoft Dataverse?</span></span>](https://docs.microsoft.com/powerapps/maker/data-platform/data-platform-intro)<br>
[<span data-ttu-id="aeb5d-198">Use a API Web do Microsoft Dataverse</span><span class="sxs-lookup"><span data-stu-id="aeb5d-198">Use the Microsoft Dataverse Web API</span></span>](https://docs.microsoft.com/powerapps/developer/data-platform/webapi/overview)<br>
[<span data-ttu-id="aeb5d-199">Criar e atualizar conjuntos de opções usando a API Web</span><span class="sxs-lookup"><span data-stu-id="aeb5d-199">Create and update option sets using the Web API</span></span>](https://docs.microsoft.com/powerapps/developer/data-platform/webapi/create-update-optionsets)<br>

[!INCLUDE[footer-include](../includes/footer-banner.md)]