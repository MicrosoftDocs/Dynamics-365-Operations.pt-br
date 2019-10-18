---
title: Hierarquia da organização no Common Data Service
description: Este tópico descreve a integração de dados organizacionais entre os aplicativos do Finance and Operations e o Common Data Service.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 07/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: fd159b38f69305dcaecb364ba0ccb3befabb3582
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2182016"
---
## <a name="organization-hierarchy-in-common-data-service"></a><span data-ttu-id="df447-103">Hierarquia da organização no Common Data Service</span><span class="sxs-lookup"><span data-stu-id="df447-103">Organization hierarchy in Common Data Service</span></span>

[!include [banner](../includes/banner.md)]

[!include [preview](../includes/preview-banner.md)]

<span data-ttu-id="df447-104">Como o Dynamics 365 Finance é um sistema financeiro, a *organização* é um conceito básico. A configuração do sistema começa com a configuração de uma hierarquia da organização.</span><span class="sxs-lookup"><span data-stu-id="df447-104">Because Dynamics 365 Finance is a financial system, *organization* is a core concept, and system setup starts with the configuration of an organization hierarchy.</span></span> <span data-ttu-id="df447-105">As finanças comerciais podem ser rastreadas em nível organizacional e também em qualquer nível da hierarquia da organização.</span><span class="sxs-lookup"><span data-stu-id="df447-105">Business financials can then be tracked at the organization level and also at any level in the organization hierarchy.</span></span>

<span data-ttu-id="df447-106">Embora o Common Data Service não tenha o conceito de uma hierarquia da organização, ele tem alguns conceitos soltos, como receita total de venda.</span><span class="sxs-lookup"><span data-stu-id="df447-106">Although Common Data Service doesn't have the concept of an organization hierarchy, it does have a few loose concepts, such as total sales revenue.</span></span> <span data-ttu-id="df447-107">Como parte da integração do Common Data Service, a estrutura de dados da hierarquia da organização é adicionada ao Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="df447-107">As part of Common Data Service integration, the organization hierarchy data structure is added to Common Data Service.</span></span>

## <a name="data-flow"></a><span data-ttu-id="df447-108">Fluxo de dados</span><span class="sxs-lookup"><span data-stu-id="df447-108">Data flow</span></span>

<span data-ttu-id="df447-109">Um ecossistema comercial que consiste em aplicativos do Finance and Operations e no Common Data Service continuará a ter uma hierarquia da organização.</span><span class="sxs-lookup"><span data-stu-id="df447-109">A business ecosystem that consists of Finance and Operations apps and Common Data Service will continue to have an organization hierarchy.</span></span> <span data-ttu-id="df447-110">Essa hierarquia da organização é criada nos aplicativos do Finance and Operations, mas é exposta no Common Data Service para fins informativos e de extensibilidade.</span><span class="sxs-lookup"><span data-stu-id="df447-110">This organization hierarchy is built on Finance and Operations apps, but it's exposed in Common Data Service for informational and extensibility purposes.</span></span> <span data-ttu-id="df447-111">A ilustração a seguir mostra informações da hierarquia da organização que é exposta no Common Data Service como um fluxo de dados unidirecional de aplicativos do Finance and Operations para o Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="df447-111">The following illustration shows the organization hierarchy information that is exposed in Common Data Service as a one-way data flow from Finance and Operations apps to Common Data Service.</span></span>

![Imagem de arquitetura](media/dual-write-data-flow.png)

## <a name="templates"></a><span data-ttu-id="df447-113">Modelos</span><span class="sxs-lookup"><span data-stu-id="df447-113">Templates</span></span>

<span data-ttu-id="df447-114">Os mapas de entidades da hierarquia da organização estão disponíveis para sincronização unidirecional de dados de aplicativos do Finance and Operations para o Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="df447-114">Organization hierarchy entity maps are available for one-way synchronization of data from Finance and Operations apps to Common Data Service.</span></span>

[!include [banner](../includes/dual-write-symbols.md)]

## <a name="internal-organization-hierarchy-purpose"></a><span data-ttu-id="df447-115">Finalidade da hierarquia da organização interna</span><span class="sxs-lookup"><span data-stu-id="df447-115">Internal Organization Hierarchy Purpose</span></span>

<span data-ttu-id="df447-116">Este modelo oferece sincronização unidirecional da entidade de Finalidade da Hierarquia da Organização do Finance and Operations para outros aplicativos do Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="df447-116">This template provides one-way synchronization of the Organization Hierarchy Purpose entity from Finance and Operations to other Dynamics 365 apps.</span></span>

<!-- ![architecture image](media/dual-write-purpose.png) -->

<span data-ttu-id="df447-117">Campo de origem</span><span class="sxs-lookup"><span data-stu-id="df447-117">Source field</span></span> | <span data-ttu-id="df447-118">Tipo de mapa</span><span class="sxs-lookup"><span data-stu-id="df447-118">Map type</span></span> | <span data-ttu-id="df447-119">Campo de destino</span><span class="sxs-lookup"><span data-stu-id="df447-119">Destination field</span></span>
---|---|---
<span data-ttu-id="df447-120">HIERARCHYTYPE</span><span class="sxs-lookup"><span data-stu-id="df447-120">HIERARCHYTYPE</span></span> | \> | <span data-ttu-id="df447-121">msdyn\_hierarchypurposetypename</span><span class="sxs-lookup"><span data-stu-id="df447-121">msdyn\_hierarchypurposetypename</span></span>
<span data-ttu-id="df447-122">HIERARCHYTYPE</span><span class="sxs-lookup"><span data-stu-id="df447-122">HIERARCHYTYPE</span></span> | \> | <span data-ttu-id="df447-123">msdyn\_hierarchytype.msdyn\_name</span><span class="sxs-lookup"><span data-stu-id="df447-123">msdyn\_hierarchytype.msdyn\_name</span></span>
<span data-ttu-id="df447-124">HIERARCHYPURPOSE</span><span class="sxs-lookup"><span data-stu-id="df447-124">HIERARCHYPURPOSE</span></span> | \>\> | <span data-ttu-id="df447-125">msdyn\_hierarchypurpose</span><span class="sxs-lookup"><span data-stu-id="df447-125">msdyn\_hierarchypurpose</span></span>
<span data-ttu-id="df447-126">IMMUTABLE</span><span class="sxs-lookup"><span data-stu-id="df447-126">IMMUTABLE</span></span> | \>\> | <span data-ttu-id="df447-127">msdyn\_immutable</span><span class="sxs-lookup"><span data-stu-id="df447-127">msdyn\_immutable</span></span>
<span data-ttu-id="df447-128">SETASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="df447-128">SETASDEFAULT</span></span> | \>\> | <span data-ttu-id="df447-129">msdyn\_setasdefault</span><span class="sxs-lookup"><span data-stu-id="df447-129">msdyn\_setasdefault</span></span>

## <a name="internal-organization-hierarchy-type"></a><span data-ttu-id="df447-130">Tipo de hierarquia da organização interna</span><span class="sxs-lookup"><span data-stu-id="df447-130">Internal Organization Hierarchy Type</span></span>

<span data-ttu-id="df447-131">Este modelo oferece sincronização unidirecional da entidade de Tipo de Hierarquia da Organização do Finance and Operations para outros aplicativos do Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="df447-131">Tihs template provides one-way synchronization of the Organization Hierarchy Type entity from Finance and Operations to other Dynamics 365 apps.</span></span>

<!-- ![architecture image](media/dual-write-type.png) -->

<span data-ttu-id="df447-132">Campo de origem</span><span class="sxs-lookup"><span data-stu-id="df447-132">Source field</span></span> | <span data-ttu-id="df447-133">Tipo de mapa</span><span class="sxs-lookup"><span data-stu-id="df447-133">Map type</span></span> | <span data-ttu-id="df447-134">Campo de destino</span><span class="sxs-lookup"><span data-stu-id="df447-134">Destination field</span></span>
---|---|---
<span data-ttu-id="df447-135">NOME</span><span class="sxs-lookup"><span data-stu-id="df447-135">NAME</span></span> | \> | <span data-ttu-id="df447-136">msdyn\_name</span><span class="sxs-lookup"><span data-stu-id="df447-136">msdyn\_name</span></span>

## <a name="internal-organization-hierarchy"></a><span data-ttu-id="df447-137">Hierarquia da organização interna</span><span class="sxs-lookup"><span data-stu-id="df447-137">Internal Organization Hierarchy</span></span>

<span data-ttu-id="df447-138">Este modelo oferece sincronização unidirecional da entidade de Hierarquia da Organização Publicada do Finance and Operations para outros aplicativos do Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="df447-138">This template provides one-way synchronization of the Organization Hierarchy Published entity from Finance and Operations to other Dynamics 365 apps.</span></span>

<!-- ![architecture image](media/dual-write-organization.png) -->

<span data-ttu-id="df447-139">Campo de origem</span><span class="sxs-lookup"><span data-stu-id="df447-139">Source field</span></span> | <span data-ttu-id="df447-140">Tipo de mapa</span><span class="sxs-lookup"><span data-stu-id="df447-140">Map type</span></span> | <span data-ttu-id="df447-141">Campo de destino</span><span class="sxs-lookup"><span data-stu-id="df447-141">Destination field</span></span>
---|---|---
<span data-ttu-id="df447-142">VALIDTO</span><span class="sxs-lookup"><span data-stu-id="df447-142">VALIDTO</span></span> | \> | <span data-ttu-id="df447-143">msdyn\_validto</span><span class="sxs-lookup"><span data-stu-id="df447-143">msdyn\_validto</span></span>
<span data-ttu-id="df447-144">VALIDFROM</span><span class="sxs-lookup"><span data-stu-id="df447-144">VALIDFROM</span></span> | \> | <span data-ttu-id="df447-145">msdyn\_validfrom</span><span class="sxs-lookup"><span data-stu-id="df447-145">msdyn\_validfrom</span></span>
<span data-ttu-id="df447-146">HIERARCHYTYPE</span><span class="sxs-lookup"><span data-stu-id="df447-146">HIERARCHYTYPE</span></span> | \> | <span data-ttu-id="df447-147">msdyn\_hierarchytypename</span><span class="sxs-lookup"><span data-stu-id="df447-147">msdyn\_hierarchytypename</span></span>
<span data-ttu-id="df447-148">PARENTORGANIZATIONPARTYNUMBER</span><span class="sxs-lookup"><span data-stu-id="df447-148">PARENTORGANIZATIONPARTYNUMBER</span></span> | \> | <span data-ttu-id="df447-149">msdyn\_parentpartyid</span><span class="sxs-lookup"><span data-stu-id="df447-149">msdyn\_parentpartyid</span></span>
<span data-ttu-id="df447-150">CHILDORGANIZATIONPARTYNUMBER</span><span class="sxs-lookup"><span data-stu-id="df447-150">CHILDORGANIZATIONPARTYNUMBER</span></span> | \> | <span data-ttu-id="df447-151">msdyn\_childpartyid</span><span class="sxs-lookup"><span data-stu-id="df447-151">msdyn\_childpartyid</span></span>
<span data-ttu-id="df447-152">HIERARCHYTYPE</span><span class="sxs-lookup"><span data-stu-id="df447-152">HIERARCHYTYPE</span></span> | \> | <span data-ttu-id="df447-153">msdyn\_hierarchytypeid.msdyn\_name</span><span class="sxs-lookup"><span data-stu-id="df447-153">msdyn\_hierarchytypeid.msdyn\_name</span></span>
<span data-ttu-id="df447-154">CHILDORGANIZATIONPARTYNUMBER</span><span class="sxs-lookup"><span data-stu-id="df447-154">CHILDORGANIZATIONPARTYNUMBER</span></span> | \> | <span data-ttu-id="df447-155">msdyn\_childid.msdyn\_partynumber</span><span class="sxs-lookup"><span data-stu-id="df447-155">msdyn\_childid.msdyn\_partynumber</span></span>
<span data-ttu-id="df447-156">PARENTORGANIZATIONPARTYNUMBER</span><span class="sxs-lookup"><span data-stu-id="df447-156">PARENTORGANIZATIONPARTYNUMBER</span></span> | \> | <span data-ttu-id="df447-157">msdyn\_parentid.msdyn\_partynumber</span><span class="sxs-lookup"><span data-stu-id="df447-157">msdyn\_parentid.msdyn\_partynumber</span></span>

## <a name="internal-organization"></a><span data-ttu-id="df447-158">Organização interna</span><span class="sxs-lookup"><span data-stu-id="df447-158">Internal Organization</span></span>

<span data-ttu-id="df447-159">As informações internas da organização no Common Data Service vêm de duas entidades, **unidade operacional** e **entidades legais**.</span><span class="sxs-lookup"><span data-stu-id="df447-159">Internal organization information in Common Data Service comes from two entities, **operating unit** and **legal entities**.</span></span>

<!-- ![architecture image](media/dual-write-operating-unit.png) -->

<!-- ![architecture image](media/dual-write-legal-entities.png) -->

### <a name="operating-unit"></a><span data-ttu-id="df447-160">Unidade operacional</span><span class="sxs-lookup"><span data-stu-id="df447-160">Operating unit</span></span>

<span data-ttu-id="df447-161">Campo de origem</span><span class="sxs-lookup"><span data-stu-id="df447-161">Source field</span></span> | <span data-ttu-id="df447-162">Tipo de mapa</span><span class="sxs-lookup"><span data-stu-id="df447-162">Map type</span></span> | <span data-ttu-id="df447-163">Campo de destino</span><span class="sxs-lookup"><span data-stu-id="df447-163">Destination field</span></span>
---|---|---
<span data-ttu-id="df447-164">LANGUAGEID</span><span class="sxs-lookup"><span data-stu-id="df447-164">LANGUAGEID</span></span> | \> | <span data-ttu-id="df447-165">msdyn\_languageid</span><span class="sxs-lookup"><span data-stu-id="df447-165">msdyn\_languageid</span></span>
<span data-ttu-id="df447-166">NAMEALIAS</span><span class="sxs-lookup"><span data-stu-id="df447-166">NAMEALIAS</span></span> | \> | <span data-ttu-id="df447-167">msdyn\_namealias</span><span class="sxs-lookup"><span data-stu-id="df447-167">msdyn\_namealias</span></span>
<span data-ttu-id="df447-168">NOME</span><span class="sxs-lookup"><span data-stu-id="df447-168">NAME</span></span> | \> | <span data-ttu-id="df447-169">msdyn\_name</span><span class="sxs-lookup"><span data-stu-id="df447-169">msdyn\_name</span></span>
<span data-ttu-id="df447-170">PARTYNUMBER</span><span class="sxs-lookup"><span data-stu-id="df447-170">PARTYNUMBER</span></span> | \> | <span data-ttu-id="df447-171">msdyn\_partynumber</span><span class="sxs-lookup"><span data-stu-id="df447-171">msdyn\_partynumber</span></span>
<span data-ttu-id="df447-172">OPERATINGUNITTYPE</span><span class="sxs-lookup"><span data-stu-id="df447-172">OPERATINGUNITTYPE</span></span> | \>\> | <span data-ttu-id="df447-173">msdyn\_type</span><span class="sxs-lookup"><span data-stu-id="df447-173">msdyn\_type</span></span>

### <a name="legal-entity"></a><span data-ttu-id="df447-174">Pessoa jurídica em geral</span><span class="sxs-lookup"><span data-stu-id="df447-174">Legal entity</span></span>

<span data-ttu-id="df447-175">Campo de origem</span><span class="sxs-lookup"><span data-stu-id="df447-175">Source field</span></span> | <span data-ttu-id="df447-176">Tipo de mapa</span><span class="sxs-lookup"><span data-stu-id="df447-176">Map type</span></span> | <span data-ttu-id="df447-177">Campo de destino</span><span class="sxs-lookup"><span data-stu-id="df447-177">Destination field</span></span>
---|---|---
<span data-ttu-id="df447-178">NAMEALIAS</span><span class="sxs-lookup"><span data-stu-id="df447-178">NAMEALIAS</span></span> | \> | <span data-ttu-id="df447-179">msdyn\_namealias</span><span class="sxs-lookup"><span data-stu-id="df447-179">msdyn\_namealias</span></span>
<span data-ttu-id="df447-180">LANGUAGEID</span><span class="sxs-lookup"><span data-stu-id="df447-180">LANGUAGEID</span></span> | \> | <span data-ttu-id="df447-181">msdyn\_languageid</span><span class="sxs-lookup"><span data-stu-id="df447-181">msdyn\_languageid</span></span>
<span data-ttu-id="df447-182">NOME</span><span class="sxs-lookup"><span data-stu-id="df447-182">NAME</span></span> | \> | <span data-ttu-id="df447-183">msdyn\_name</span><span class="sxs-lookup"><span data-stu-id="df447-183">msdyn\_name</span></span>
<span data-ttu-id="df447-184">PARTYNUMBER</span><span class="sxs-lookup"><span data-stu-id="df447-184">PARTYNUMBER</span></span> | \> | <span data-ttu-id="df447-185">msdyn\_partynumber</span><span class="sxs-lookup"><span data-stu-id="df447-185">msdyn\_partynumber</span></span>
<span data-ttu-id="df447-186">nenhuma</span><span class="sxs-lookup"><span data-stu-id="df447-186">none</span></span> | \>\> | <span data-ttu-id="df447-187">msdyn\_type</span><span class="sxs-lookup"><span data-stu-id="df447-187">msdyn\_type</span></span>
<span data-ttu-id="df447-188">LEGALENTITYID</span><span class="sxs-lookup"><span data-stu-id="df447-188">LEGALENTITYID</span></span> | \> | <span data-ttu-id="df447-189">msdyn\_companycode</span><span class="sxs-lookup"><span data-stu-id="df447-189">msdyn\_companycode</span></span>

## <a name="company"></a><span data-ttu-id="df447-190">Empresa</span><span class="sxs-lookup"><span data-stu-id="df447-190">Company</span></span>

<span data-ttu-id="df447-191">Fornece sincronização bidirecional de informações da entidade legal (empresa) entre o Finance and Operations e outros aplicativos do Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="df447-191">Provides bidirectional synchronization of legal entity (company) information between Finance and Operations and other Dynamics 365 apps.</span></span>

<!-- ![architecture image](media/dual-write-company.png) -->

<span data-ttu-id="df447-192">Campo de origem</span><span class="sxs-lookup"><span data-stu-id="df447-192">Source field</span></span> | <span data-ttu-id="df447-193">Tipo de mapa</span><span class="sxs-lookup"><span data-stu-id="df447-193">Map type</span></span> | <span data-ttu-id="df447-194">Campo de destino</span><span class="sxs-lookup"><span data-stu-id="df447-194">Destination field</span></span>
---|---|---
<span data-ttu-id="df447-195">NOME</span><span class="sxs-lookup"><span data-stu-id="df447-195">NAME</span></span> | = | <span data-ttu-id="df447-196">cdm\_name</span><span class="sxs-lookup"><span data-stu-id="df447-196">cdm\_name</span></span>
<span data-ttu-id="df447-197">LEGALENTITYID</span><span class="sxs-lookup"><span data-stu-id="df447-197">LEGALENTITYID</span></span> | = | <span data-ttu-id="df447-198">cdm\_companycode</span><span class="sxs-lookup"><span data-stu-id="df447-198">cdm\_companycode</span></span>
