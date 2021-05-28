---
title: Introdução à API de integração da folha de pagamento
description: Este tópico descreve a API de integração da folha de pagamento do Dynamics 365 Human Resources.
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
ms.author: jcart
ms.search.validFrom: 2021-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 3a7be5ad42642de48ffdb2731a1300a953c5ede4
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6022754"
---
# <a name="payroll-integration-api-introduction"></a><span data-ttu-id="4cf15-103">Introdução à API de integração da folha de pagamento</span><span class="sxs-lookup"><span data-stu-id="4cf15-103">Payroll integration API introduction</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="4cf15-104">Este documento descreve a API de integração da folha de pagamento do Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="4cf15-104">This document describes the Dynamics 365 Human Resources Payroll integration API.</span></span> <span data-ttu-id="4cf15-105">A API permite integrações completas simplificadas entre o Human Resources e sistemas de folha de pagamento de parceiros.</span><span class="sxs-lookup"><span data-stu-id="4cf15-105">The API enables streamlined end-to-end integrations between Human Resources and partnering payroll systems.</span></span> <span data-ttu-id="4cf15-106">A experiência integrada começa em Human Resources com o perfil do funcionário, salário e dedução e informações de contribuição.</span><span class="sxs-lookup"><span data-stu-id="4cf15-106">The integrated experience begins in Human Resources with the employee profile, salary and deduction, and contribution information.</span></span> <span data-ttu-id="4cf15-107">Quando você contrata um funcionário e insere as informações necessárias sobre o perfil e o pagamento em Human Resources, o sistema de folha de pagamento recebe essas informações para usar ao processar a folha de pagamento.</span><span class="sxs-lookup"><span data-stu-id="4cf15-107">When you hire an employee and enter the required profile and pay information into Human Resources, the payroll system pulls this information to use when processing payroll.</span></span> <span data-ttu-id="4cf15-108">As atualizações feitas nas informações do funcionário ou do pagamento também são extraídas para uso em execuções de pagamento futuras.</span><span class="sxs-lookup"><span data-stu-id="4cf15-108">Any updates made to the employee or pay information are also pulled for use in later pay runs.</span></span>

![Fluxo de integração da folha de pagamento](media/hr-admin-integration-payroll-api-introduction-flow.png)

<span data-ttu-id="4cf15-110">Para habilitar a integração, o Human Resources inclui os seguintes componentes:</span><span class="sxs-lookup"><span data-stu-id="4cf15-110">To enable the integration, Human Resources includes the following components:</span></span>

- <span data-ttu-id="4cf15-111">Funcionalidade para marcar um funcionário como pronto para pagar</span><span class="sxs-lookup"><span data-stu-id="4cf15-111">Functionality to mark an employee as ready to pay</span></span>
- <span data-ttu-id="4cf15-112">Uma API de integração que abre a nova funcionalidade para integrar aplicativos</span><span class="sxs-lookup"><span data-stu-id="4cf15-112">An integration API opening up the new functionality to integrating applications</span></span>

## <a name="microsoft-dataverse"></a><span data-ttu-id="4cf15-113">Microsoft Dataverse</span><span class="sxs-lookup"><span data-stu-id="4cf15-113">Microsoft Dataverse</span></span>

<span data-ttu-id="4cf15-114">Esta API foi desenvolvida com base no Microsoft Dataverse (antes conhecido como Common Data Service).</span><span class="sxs-lookup"><span data-stu-id="4cf15-114">This API is built on Microsoft Dataverse (formerly Common Data Service).</span></span> <span data-ttu-id="4cf15-115">Toda a interação RESTful com essa API é realizada por meio da API Web do Microsoft Dataverse, que usa OData.</span><span class="sxs-lookup"><span data-stu-id="4cf15-115">All RESTful interaction with this API is done via the Microsoft Dataverse Web API, which uses OData.</span></span> <span data-ttu-id="4cf15-116">Essa API é um subconjunto da API Web do Dataverse.</span><span class="sxs-lookup"><span data-stu-id="4cf15-116">This API is a subset of the Dataverse Web API.</span></span> <span data-ttu-id="4cf15-117">A API Web do Dataverse define características como autenticação, SLAs, lote, controle de simultaneidade e tratamento de erros.</span><span class="sxs-lookup"><span data-stu-id="4cf15-117">The Dataverse Web API defines characteristics such as authentication, SLAs, batch, concurrency control, and error handling.</span></span>

<span data-ttu-id="4cf15-118">Para obter mais informações gerais sobre a API Web do Microsoft Dataverse, consulte:</span><span class="sxs-lookup"><span data-stu-id="4cf15-118">For more general information about the Microsoft Dataverse Web API, see:</span></span>

- [<span data-ttu-id="4cf15-119">O que é o Microsoft Dataverse?</span><span class="sxs-lookup"><span data-stu-id="4cf15-119">What is Microsoft Dataverse?</span></span>](/powerapps/maker/data-platform/data-platform-intro)
- [<span data-ttu-id="4cf15-120">Use a API Web do Microsoft Dataverse</span><span class="sxs-lookup"><span data-stu-id="4cf15-120">Use the Microsoft Dataverse Web API</span></span>](/powerapps/developer/data-platform/webapi/overview)
- [<span data-ttu-id="4cf15-121">Guia do desenvolvedor do Microsoft Dataverse</span><span class="sxs-lookup"><span data-stu-id="4cf15-121">Microsoft Dataverse developer guide</span></span>](/powerapps/developer/data-platform)

<span data-ttu-id="4cf15-122">Esta documentação inclui detalhes e orientações para o desenvolvedor sobre o uso da API Web do Dataverse, incluindo os seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="4cf15-122">This documentation includes details and developer guidance for using the Dataverse Web API, including the following topics:</span></span>

- [<span data-ttu-id="4cf15-123">Autenticar para o Microsoft Dataverse com a API Web</span><span class="sxs-lookup"><span data-stu-id="4cf15-123">Authenticate to Microsoft Dataverse with the Web API</span></span>](/powerapps/developer/data-platform/webapi/authenticate-web-api)
- [<span data-ttu-id="4cf15-124">Executar operações usando a API Web</span><span class="sxs-lookup"><span data-stu-id="4cf15-124">Perform operations using the Web API</span></span>](/powerapps/developer/data-platform/webapi/perform-operations-web-api)
- [<span data-ttu-id="4cf15-125">Usar o Postman com a API Web</span><span class="sxs-lookup"><span data-stu-id="4cf15-125">Use Postman with the Web API</span></span>](/powerapps/developer/data-platform/webapi/use-postman-web-api)
- [<span data-ttu-id="4cf15-126">Usar o controle de alterações para sincronizar dados com sistemas externos</span><span class="sxs-lookup"><span data-stu-id="4cf15-126">Use change tracking to synchronize data with external systems</span></span>](/powerapps/developer/data-platform/use-change-tracking-synchronize-data-external-systems)

### <a name="virtual-tables-for-human-resources-in-dataverse"></a><span data-ttu-id="4cf15-127">Tabelas virtuais para o Human Resources no Dataverse</span><span class="sxs-lookup"><span data-stu-id="4cf15-127">Virtual tables for Human Resources in Dataverse</span></span>

<span data-ttu-id="4cf15-128">Os pontos de extremidade para a API de integração da folha de pagamento usam os recursos da plataforma de tabela virtual do Microsoft Dataverse.</span><span class="sxs-lookup"><span data-stu-id="4cf15-128">The endpoints for the Payroll integration API use the virtual table platform capabilities of Microsoft Dataverse.</span></span> <span data-ttu-id="4cf15-129">Por padrão, as tabelas virtuais e os pontos de extremidade da API associados não são implantados para ambientes do Human Resources, permitindo que organizações determinem quais pontos de extremidade OData serão expostos para o ambiente.</span><span class="sxs-lookup"><span data-stu-id="4cf15-129">By default, the virtual tables and their associated API endpoints aren't deployed for Human Resources environments, enabling organizations to determine which OData endpoints will be exposed for the environment.</span></span> <span data-ttu-id="4cf15-130">Para usar a API, as tabelas virtuais de entidades do Human Resources devem ser geradas para o ambiente.</span><span class="sxs-lookup"><span data-stu-id="4cf15-130">To use the API, the virtual tables for the Human Resources entities must be generated for the environment.</span></span>

<span data-ttu-id="4cf15-131">Para obter informações sobre como gerar as tabelas virtuais da API, consulte [Configurar tabelas virtuais do Dataverse](./hr-admin-integration-common-data-service-virtual-entities.md).</span><span class="sxs-lookup"><span data-stu-id="4cf15-131">For information on generating the virtual tables for the API, see [Configure Dataverse virtual tables](./hr-admin-integration-common-data-service-virtual-entities.md).</span></span>

## <a name="data-model"></a><span data-ttu-id="4cf15-132">Modelo de dados</span><span class="sxs-lookup"><span data-stu-id="4cf15-132">Data model</span></span>

<span data-ttu-id="4cf15-133">O diagrama a seguir ilustra relacionamentos na API.</span><span class="sxs-lookup"><span data-stu-id="4cf15-133">The following diagram illustrates relationships within the API.</span></span> <span data-ttu-id="4cf15-134">Vários tipos têm chaves estrangeiras para outras entidades preexistentes no Human Resources que não estão ilustradas aqui.</span><span class="sxs-lookup"><span data-stu-id="4cf15-134">Several types have foreign keys to other, pre-existing entities in Human Resources that aren't illustrated here.</span></span> <span data-ttu-id="4cf15-135">Este documento fornece informações sobre entidades específicas para cenários de integração da folha de pagamento.</span><span class="sxs-lookup"><span data-stu-id="4cf15-135">This document provides information on entities that are specific to payroll integration scenarios.</span></span> <span data-ttu-id="4cf15-136">No entanto, há várias outras entidades na API Web do Dataverse para o Human Resources que também podem ser relevantes para sua integração.</span><span class="sxs-lookup"><span data-stu-id="4cf15-136">However, there are many other entities in the Dataverse Web API for Human Resources that may also be relevant to your integration.</span></span> <span data-ttu-id="4cf15-137">Algumas dessas entidades são referenciadas em relações de chave estrangeira ou propriedades de navegação.</span><span class="sxs-lookup"><span data-stu-id="4cf15-137">Some of these entities are referenced in foreign key relationships or navigation properties.</span></span>

![Modelo de dados de API de integração da folha de pagamento](media/hr-admin-payroll-api-data-model.png)

## <a name="payroll-employee-and-related-entities"></a><span data-ttu-id="4cf15-139">Funcionário da folha de pagamento e entidades relacionadas</span><span class="sxs-lookup"><span data-stu-id="4cf15-139">Payroll employee and related entities</span></span>

<span data-ttu-id="4cf15-140">Entidades:</span><span class="sxs-lookup"><span data-stu-id="4cf15-140">Entities:</span></span>

- [<span data-ttu-id="4cf15-141">Funcionário da folha de pagamento</span><span class="sxs-lookup"><span data-stu-id="4cf15-141">Payroll employee</span></span>](hr-admin-integration-payroll-api-payroll-employee.md)
- [<span data-ttu-id="4cf15-142">Endereço do trabalhador da folha de pagamento</span><span class="sxs-lookup"><span data-stu-id="4cf15-142">Payroll worker address</span></span>](hr-admin-integration-payroll-api-payroll-worker-address.md)
- [<span data-ttu-id="4cf15-143">Plano de remuneração fixa da folha de pagamento</span><span class="sxs-lookup"><span data-stu-id="4cf15-143">Payroll fixed compensation plan</span></span>](hr-admin-integration-ats-api-recruiting-request-education.md)
- [<span data-ttu-id="4cf15-144">Trabalho da posição na folha de pagamento</span><span class="sxs-lookup"><span data-stu-id="4cf15-144">Payroll position job</span></span>](hr-admin-integration-payroll-api-payroll-position-job.md)
- [<span data-ttu-id="4cf15-145">Posição na folha de pagamento</span><span class="sxs-lookup"><span data-stu-id="4cf15-145">Payroll position</span></span>](hr-admin-integration-payroll-api-payroll-position.md)

## <a name="see-also"></a><span data-ttu-id="4cf15-146">Consulte também</span><span class="sxs-lookup"><span data-stu-id="4cf15-146">See also</span></span>

[<span data-ttu-id="4cf15-147">Gerar e revisar entidades da folha de pagamento</span><span class="sxs-lookup"><span data-stu-id="4cf15-147">Generate and review payroll entities</span></span>](hr-admin-integration-payroll-api-generate-review-entities.md)<br>
[<span data-ttu-id="4cf15-148">Configurar parâmetros do Human Resources</span><span class="sxs-lookup"><span data-stu-id="4cf15-148">Configure Human Resources parameters</span></span>](hr-setup-parameters.md)<br>
[<span data-ttu-id="4cf15-149">Configurar parâmetros compartilhados do Human Resources</span><span class="sxs-lookup"><span data-stu-id="4cf15-149">Configure Human Resources shared parameters</span></span>](hr-setup-shared-parameters.md)<br>
[<span data-ttu-id="4cf15-150">O que é o Microsoft Dataverse?</span><span class="sxs-lookup"><span data-stu-id="4cf15-150">What is Microsoft Dataverse?</span></span>](/powerapps/maker/data-platform/data-platform-intro)<br>
[<span data-ttu-id="4cf15-151">Use a API Web do Microsoft Dataverse</span><span class="sxs-lookup"><span data-stu-id="4cf15-151">Use the Microsoft Dataverse Web API</span></span>](/powerapps/developer/data-platform/webapi/overview)<br>

[!INCLUDE[footer-include](../includes/footer-banner.md)]