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
ms.openlocfilehash: 9efc63c385c31a6d8848d016c1a8689460908dcc
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/06/2019
ms.locfileid: "2769651"
---
# <a name="organization-hierarchy-in-common-data-service"></a><span data-ttu-id="a6aa0-103">Hierarquia da organização no Common Data Service</span><span class="sxs-lookup"><span data-stu-id="a6aa0-103">Organization hierarchy in Common Data Service</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a6aa0-104">Como o Dynamics 365 Finance é um sistema financeiro, a *organização* é um conceito básico. A configuração do sistema começa com a configuração de uma hierarquia da organização.</span><span class="sxs-lookup"><span data-stu-id="a6aa0-104">Because Dynamics 365 Finance is a financial system, *organization* is a core concept, and system setup starts with the configuration of an organization hierarchy.</span></span> <span data-ttu-id="a6aa0-105">As finanças comerciais podem ser rastreadas em nível organizacional e também em qualquer nível da hierarquia da organização.</span><span class="sxs-lookup"><span data-stu-id="a6aa0-105">Business financials can then be tracked at the organization level and also at any level in the organization hierarchy.</span></span>

<span data-ttu-id="a6aa0-106">Embora o Common Data Service não tenha o conceito de uma hierarquia da organização, ele tem alguns conceitos soltos, como receita total de venda.</span><span class="sxs-lookup"><span data-stu-id="a6aa0-106">Although Common Data Service doesn't have the concept of an organization hierarchy, it does have a few loose concepts, such as total sales revenue.</span></span> <span data-ttu-id="a6aa0-107">Como parte da integração do Common Data Service, a estrutura de dados da hierarquia da organização é adicionada ao Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="a6aa0-107">As part of Common Data Service integration, the organization hierarchy data structure is added to Common Data Service.</span></span>

## <a name="data-flow"></a><span data-ttu-id="a6aa0-108">Fluxo de dados</span><span class="sxs-lookup"><span data-stu-id="a6aa0-108">Data flow</span></span>

<span data-ttu-id="a6aa0-109">Um ecossistema comercial que consiste em aplicativos do Finance and Operations e no Common Data Service continuará a ter uma hierarquia da organização.</span><span class="sxs-lookup"><span data-stu-id="a6aa0-109">A business ecosystem that consists of Finance and Operations apps and Common Data Service will continue to have an organization hierarchy.</span></span> <span data-ttu-id="a6aa0-110">Essa hierarquia da organização é criada nos aplicativos do Finance and Operations, mas é exposta no Common Data Service para fins informativos e de extensibilidade.</span><span class="sxs-lookup"><span data-stu-id="a6aa0-110">This organization hierarchy is built on Finance and Operations apps, but it's exposed in Common Data Service for informational and extensibility purposes.</span></span> <span data-ttu-id="a6aa0-111">A ilustração a seguir mostra informações da hierarquia da organização que é exposta no Common Data Service como um fluxo de dados unidirecional de aplicativos do Finance and Operations para o Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="a6aa0-111">The following illustration shows the organization hierarchy information that is exposed in Common Data Service as a one-way data flow from Finance and Operations apps to Common Data Service.</span></span>

![Imagem de arquitetura](media/dual-write-data-flow.png)

## <a name="templates"></a><span data-ttu-id="a6aa0-113">Modelos</span><span class="sxs-lookup"><span data-stu-id="a6aa0-113">Templates</span></span>

<span data-ttu-id="a6aa0-114">Os mapas de entidades da hierarquia da organização estão disponíveis para sincronização unidirecional de dados de aplicativos do Finance and Operations para o Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="a6aa0-114">Organization hierarchy entity maps are available for one-way synchronization of data from Finance and Operations apps to Common Data Service.</span></span>

## <a name="templates"></a><span data-ttu-id="a6aa0-115">Modelos</span><span class="sxs-lookup"><span data-stu-id="a6aa0-115">Templates</span></span>

<span data-ttu-id="a6aa0-116">As informações do produto contêm todos os dados relacionados ao produto e sua definição, como as dimensões do produto ou as dimensões de rastreamento e armazenamento.</span><span class="sxs-lookup"><span data-stu-id="a6aa0-116">Product information contains all the information related to the product and its definition, such as the product dimensions or the tracking and storage dimensions.</span></span> <span data-ttu-id="a6aa0-117">Como mostrado na tabela a seguir, é criada uma coleção de mapas de entidades para sincronizar produtos e as informações relacionadas.</span><span class="sxs-lookup"><span data-stu-id="a6aa0-117">As the following table shows, a collection of entity maps is created to sync products and related information.</span></span>

<span data-ttu-id="a6aa0-118">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="a6aa0-118">Finance and Operations</span></span> | <span data-ttu-id="a6aa0-119">Outros aplicativos do Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="a6aa0-119">Other Dynamics 365 apps</span></span> | <span data-ttu-id="a6aa0-120">Descrição</span><span class="sxs-lookup"><span data-stu-id="a6aa0-120">Description</span></span>
-----------------------|--------------------------------|---
<span data-ttu-id="a6aa0-121">Finalidades da hierarquia da organização</span><span class="sxs-lookup"><span data-stu-id="a6aa0-121">Organization hierarchy purposes</span></span> | <span data-ttu-id="a6aa0-122">msdyn_internalorganizationhierarchypurposes</span><span class="sxs-lookup"><span data-stu-id="a6aa0-122">msdyn_internalorganizationhierarchypurposes</span></span> | <span data-ttu-id="a6aa0-123">Este modelo oferece sincronização unidirecional da entidade Finalidade da hierarquia da organização.</span><span class="sxs-lookup"><span data-stu-id="a6aa0-123">This template provides one-way synchronization of the Organization Hierarchy Purpose entity.</span></span>
<span data-ttu-id="a6aa0-124">Tipo de hierarquia da organização</span><span class="sxs-lookup"><span data-stu-id="a6aa0-124">Organization hierarchy type</span></span> | <span data-ttu-id="a6aa0-125">msdyn_internalorganizationhierarchytypes</span><span class="sxs-lookup"><span data-stu-id="a6aa0-125">msdyn_internalorganizationhierarchytypes</span></span> | <span data-ttu-id="a6aa0-126">Este modelo oferece sincronização unidirecional da entidade Tipo da hierarquia da organização.</span><span class="sxs-lookup"><span data-stu-id="a6aa0-126">This template provides one-way synchronization of the Organization Hierarchy Type entity.</span></span>
<span data-ttu-id="a6aa0-127">Hierarquia da organização - publicada</span><span class="sxs-lookup"><span data-stu-id="a6aa0-127">Organization hierarchy - published</span></span> | <span data-ttu-id="a6aa0-128">msdyn_internalorganizationhierarchies</span><span class="sxs-lookup"><span data-stu-id="a6aa0-128">msdyn_internalorganizationhierarchies</span></span> | <span data-ttu-id="a6aa0-129">Este modelo oferece sincronização unidirecional da entidade Hierarquia da organização publicada.</span><span class="sxs-lookup"><span data-stu-id="a6aa0-129">This template provides one-way synchronization of the Organization Hierarchy Published entity.</span></span>
<span data-ttu-id="a6aa0-130">Unidade operacional</span><span class="sxs-lookup"><span data-stu-id="a6aa0-130">Operating unit</span></span> | <span data-ttu-id="a6aa0-131">msdyn_internalorganizations</span><span class="sxs-lookup"><span data-stu-id="a6aa0-131">msdyn_internalorganizations</span></span> | 
<span data-ttu-id="a6aa0-132">Entidades legais</span><span class="sxs-lookup"><span data-stu-id="a6aa0-132">Legal entities</span></span> | <span data-ttu-id="a6aa0-133">msdyn_internalorganizations</span><span class="sxs-lookup"><span data-stu-id="a6aa0-133">msdyn_internalorganizations</span></span> | 
<span data-ttu-id="a6aa0-134">Entidades legais</span><span class="sxs-lookup"><span data-stu-id="a6aa0-134">Legal entities</span></span> | <span data-ttu-id="a6aa0-135">cdm_companies</span><span class="sxs-lookup"><span data-stu-id="a6aa0-135">cdm_companies</span></span> | <span data-ttu-id="a6aa0-136">Oferece sincronização bidirecional de informações da entidade legal (empresa).</span><span class="sxs-lookup"><span data-stu-id="a6aa0-136">Provides bidirectional synchronization of legal entity (company) information.</span></span>


[!include [banner](../includes/dual-write-symbols.md)]

[!include [Organization hierarchy purposes](dual-write/OrganizationHierarchyPurpose-msdyn-internalorganizationhierarchypurposes.md)]

[!include [Organization hierarchy type](dual-write/OrganizationHierarchyType-msdyn-internalorganizationhierarchytypes.md)]

[!include [Organization hierarchy - published](dual-write/OrganizationHierarchyPublished-msdyn-internalorganizationhierarchies.md)]

## <a name="internal-organization"></a><span data-ttu-id="a6aa0-137">Organização interna</span><span class="sxs-lookup"><span data-stu-id="a6aa0-137">Internal Organization</span></span>

<span data-ttu-id="a6aa0-138">As informações internas da organização no Common Data Service vêm de duas entidades, **unidade operacional** e **entidades legais**.</span><span class="sxs-lookup"><span data-stu-id="a6aa0-138">Internal organization information in Common Data Service comes from two entities, **operating unit** and **legal entities**.</span></span>

[!include [Operating unit](dual-write/OperatingUnit-msdyn-internalorganizations.md)]

[!include [Legal entities](dual-write/LegalEntities-msdyn-internalorganizations.md)]

[!include [Legal entities](dual-write/LegalEntities-Companies.md)]

