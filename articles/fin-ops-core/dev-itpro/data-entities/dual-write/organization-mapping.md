---
title: Hierarquia da organização no Common Data Service
description: Este tópico descreve a integração de dados organizacionais entre aplicativos do Finance and Operations e o Common Data Service.
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
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: f502519ba419cb8fa322eb1d22f06d2b805f5f05
ms.sourcegitcommit: afc43699c0edc4ff2be310cb37add2ab586b64c0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/14/2020
ms.locfileid: "4000725"
---
# <a name="organization-hierarchy-in-common-data-service"></a><span data-ttu-id="62b14-103">Hierarquia da organização no Common Data Service</span><span class="sxs-lookup"><span data-stu-id="62b14-103">Organization hierarchy in Common Data Service</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="62b14-104">Como o Dynamics 365 Finance é um sistema financeiro, a *organização* é um conceito básico. A configuração do sistema começa com a configuração de uma hierarquia da organização.</span><span class="sxs-lookup"><span data-stu-id="62b14-104">Because Dynamics 365 Finance is a financial system, *organization* is a core concept, and system setup starts with the configuration of an organization hierarchy.</span></span> <span data-ttu-id="62b14-105">As finanças comerciais podem ser rastreadas em nível organizacional e também em qualquer nível da hierarquia da organização.</span><span class="sxs-lookup"><span data-stu-id="62b14-105">Business financials can then be tracked at the organization level and also at any level in the organization hierarchy.</span></span>

<span data-ttu-id="62b14-106">Embora o Common Data Service não tenha o conceito de uma hierarquia da organização, ele tem alguns conceitos soltos, como receita total de venda.</span><span class="sxs-lookup"><span data-stu-id="62b14-106">Although Common Data Service doesn't have the concept of an organization hierarchy, it does have a few loose concepts, such as total sales revenue.</span></span> <span data-ttu-id="62b14-107">Como parte da integração do Common Data Service, a estrutura de dados da hierarquia da organização é adicionada ao Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="62b14-107">As part of Common Data Service integration, the organization hierarchy data structure is added to Common Data Service.</span></span>

## <a name="data-flow"></a><span data-ttu-id="62b14-108">Fluxo de dados</span><span class="sxs-lookup"><span data-stu-id="62b14-108">Data flow</span></span>

<span data-ttu-id="62b14-109">Um ecossistema comercial que consiste em aplicativos do Finance and Operations e no Common Data Service continuará a ter uma hierarquia da organização.</span><span class="sxs-lookup"><span data-stu-id="62b14-109">A business ecosystem that consists of Finance and Operations apps and Common Data Service will continue to have an organization hierarchy.</span></span> <span data-ttu-id="62b14-110">Essa hierarquia da organização é criada nos aplicativos do Finance and Operations, mas é exposta no Common Data Service para fins informativos e de extensibilidade.</span><span class="sxs-lookup"><span data-stu-id="62b14-110">This organization hierarchy is built on Finance and Operations apps, but it's exposed in Common Data Service for informational and extensibility purposes.</span></span> <span data-ttu-id="62b14-111">A ilustração a seguir mostra informações da hierarquia da organização que é exposta no Common Data Service como um fluxo de dados unidirecional de aplicativos do Finance and Operations para o Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="62b14-111">The following illustration shows the organization hierarchy information that is exposed in Common Data Service as a one-way data flow from Finance and Operations apps to Common Data Service.</span></span>

![Imagem de arquitetura](media/dual-write-data-flow.png)

<span data-ttu-id="62b14-113">Os mapas de entidades da hierarquia da organização estão disponíveis para sincronização unidirecional de dados de aplicativos do Finance and Operations para o Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="62b14-113">Organization hierarchy entity maps are available for one-way synchronization of data from Finance and Operations apps to Common Data Service.</span></span>

## <a name="templates"></a><span data-ttu-id="62b14-114">Modelos</span><span class="sxs-lookup"><span data-stu-id="62b14-114">Templates</span></span>

<span data-ttu-id="62b14-115">As informações do produto contêm todos os dados relacionados ao produto e sua definição, como as dimensões do produto ou as dimensões de rastreamento e armazenamento.</span><span class="sxs-lookup"><span data-stu-id="62b14-115">Product information contains all the information related to the product and its definition, such as the product dimensions or the tracking and storage dimensions.</span></span> <span data-ttu-id="62b14-116">Como mostrado na tabela a seguir, é criada uma coleção de mapas de entidades para sincronizar produtos e as informações relacionadas.</span><span class="sxs-lookup"><span data-stu-id="62b14-116">As the following table shows, a collection of entity maps is created to sync products and related information.</span></span>

<span data-ttu-id="62b14-117">Aplicativos Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="62b14-117">Finance and Operations apps</span></span> | <span data-ttu-id="62b14-118">Outros aplicativos do Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="62b14-118">Other Dynamics 365 apps</span></span> | <span data-ttu-id="62b14-119">descrição</span><span class="sxs-lookup"><span data-stu-id="62b14-119">Description</span></span>
-----------------------|--------------------------------|---
<span data-ttu-id="62b14-120">Finalidades da hierarquia da organização</span><span class="sxs-lookup"><span data-stu-id="62b14-120">Organization hierarchy purposes</span></span> | <span data-ttu-id="62b14-121">msdyn_internalorganizationhierarchypurposes</span><span class="sxs-lookup"><span data-stu-id="62b14-121">msdyn_internalorganizationhierarchypurposes</span></span> | <span data-ttu-id="62b14-122">Este modelo oferece sincronização unidirecional da entidade Finalidade da hierarquia da organização.</span><span class="sxs-lookup"><span data-stu-id="62b14-122">This template provides one-way synchronization of the Organization Hierarchy Purpose entity.</span></span>
<span data-ttu-id="62b14-123">Tipo de hierarquia da organização</span><span class="sxs-lookup"><span data-stu-id="62b14-123">Organization hierarchy type</span></span> | <span data-ttu-id="62b14-124">msdyn_internalorganizationhierarchytypes</span><span class="sxs-lookup"><span data-stu-id="62b14-124">msdyn_internalorganizationhierarchytypes</span></span> | <span data-ttu-id="62b14-125">Este modelo oferece sincronização unidirecional da entidade Tipo da hierarquia da organização.</span><span class="sxs-lookup"><span data-stu-id="62b14-125">This template provides one-way synchronization of the Organization Hierarchy Type entity.</span></span>
<span data-ttu-id="62b14-126">Hierarquia da organização - publicada</span><span class="sxs-lookup"><span data-stu-id="62b14-126">Organization hierarchy - published</span></span> | <span data-ttu-id="62b14-127">msdyn_internalorganizationhierarchies</span><span class="sxs-lookup"><span data-stu-id="62b14-127">msdyn_internalorganizationhierarchies</span></span> | <span data-ttu-id="62b14-128">Este modelo oferece sincronização unidirecional da entidade Hierarquia da organização publicada.</span><span class="sxs-lookup"><span data-stu-id="62b14-128">This template provides one-way synchronization of the Organization Hierarchy Published entity.</span></span>
<span data-ttu-id="62b14-129">Unidade operacional</span><span class="sxs-lookup"><span data-stu-id="62b14-129">Operating unit</span></span> | <span data-ttu-id="62b14-130">msdyn_internalorganizations</span><span class="sxs-lookup"><span data-stu-id="62b14-130">msdyn_internalorganizations</span></span> |
<span data-ttu-id="62b14-131">Entidades legais</span><span class="sxs-lookup"><span data-stu-id="62b14-131">Legal entities</span></span> | <span data-ttu-id="62b14-132">msdyn_internalorganizations</span><span class="sxs-lookup"><span data-stu-id="62b14-132">msdyn_internalorganizations</span></span> |
<span data-ttu-id="62b14-133">Entidades legais</span><span class="sxs-lookup"><span data-stu-id="62b14-133">Legal entities</span></span> | <span data-ttu-id="62b14-134">cdm_companies</span><span class="sxs-lookup"><span data-stu-id="62b14-134">cdm_companies</span></span> | <span data-ttu-id="62b14-135">Oferece sincronização bidirecional de informações da entidade legal (empresa).</span><span class="sxs-lookup"><span data-stu-id="62b14-135">Provides bidirectional synchronization of legal entity (company) information.</span></span>

[!include [banner](../../includes/dual-write-symbols.md)]

[!include [Organization hierarchy purposes](includes/OrganizationHierarchyPurpose-msdyn-internalorganizationhierarchypurposes.md)]

[!include [Organization hierarchy type](includes/OrganizationHierarchyType-msdyn-internalorganizationhierarchytypes.md)]

[!include [Organization hierarchy - published](includes/OrganizationHierarchyPublished-msdyn-internalorganizationhierarchies.md)]

## <a name="internal-organization"></a><span data-ttu-id="62b14-136">Organização interna</span><span class="sxs-lookup"><span data-stu-id="62b14-136">Internal Organization</span></span>

<span data-ttu-id="62b14-137">As informações internas da organização no Common Data Service vêm de duas entidades, **unidade operacional** e **entidades legais**.</span><span class="sxs-lookup"><span data-stu-id="62b14-137">Internal organization information in Common Data Service comes from two entities, **operating unit** and **legal entities**.</span></span>

[!include [Operating unit](includes/OperatingUnit-msdyn-internalorganizations.md)]

[!include [Legal entities](includes/LegalEntities-msdyn-internalorganizations.md)]

[!include [Legal entities](includes/LegalEntities-Companies.md)]
