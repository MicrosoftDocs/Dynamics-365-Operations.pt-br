---
title: Hierarquia da organização no Dataverse
description: Este tópico descreve a integração de dados organizacionais entre aplicativos do Finance and Operations e o Dataverse.
author: RamaKrishnamoorthy
ms.date: 07/15/2019
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 8b147c27b9309b1b3597f1194c415fbb2e2b7ad2
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5750803"
---
# <a name="organization-hierarchy-in-dataverse"></a><span data-ttu-id="bfbfc-103">Hierarquia da organização no Dataverse</span><span class="sxs-lookup"><span data-stu-id="bfbfc-103">Organization hierarchy in Dataverse</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="bfbfc-104">Como o Dynamics 365 Finance é um sistema financeiro, a *organização* é um conceito básico. A configuração do sistema começa com a configuração de uma hierarquia da organização.</span><span class="sxs-lookup"><span data-stu-id="bfbfc-104">Because Dynamics 365 Finance is a financial system, *organization* is a core concept, and system setup starts with the configuration of an organization hierarchy.</span></span> <span data-ttu-id="bfbfc-105">As finanças comerciais podem ser rastreadas em nível organizacional e também em qualquer nível da hierarquia da organização.</span><span class="sxs-lookup"><span data-stu-id="bfbfc-105">Business financials can then be tracked at the organization level and also at any level in the organization hierarchy.</span></span>

<span data-ttu-id="bfbfc-106">Embora o Dataverse não tenha o conceito de uma hierarquia da organização, ele tem alguns conceitos soltos, como receita total de venda.</span><span class="sxs-lookup"><span data-stu-id="bfbfc-106">Although Dataverse doesn't have the concept of an organization hierarchy, it does have a few loose concepts, such as total sales revenue.</span></span> <span data-ttu-id="bfbfc-107">Como parte da integração do Dataverse, a estrutura de dados da hierarquia da organização é adicionada ao Dataverse.</span><span class="sxs-lookup"><span data-stu-id="bfbfc-107">As part of Dataverse integration, the organization hierarchy data structure is added to Dataverse.</span></span>

## <a name="data-flow"></a><span data-ttu-id="bfbfc-108">Fluxo de dados</span><span class="sxs-lookup"><span data-stu-id="bfbfc-108">Data flow</span></span>

<span data-ttu-id="bfbfc-109">Um ecossistema comercial que consiste em aplicativos do Finance and Operations e no Dataverse continuará a ter uma hierarquia da organização.</span><span class="sxs-lookup"><span data-stu-id="bfbfc-109">A business ecosystem that consists of Finance and Operations apps and Dataverse will continue to have an organization hierarchy.</span></span> <span data-ttu-id="bfbfc-110">Essa hierarquia da organização é criada nos aplicativos do Finance and Operations, mas é exposta no Dataverse para fins informativos e de extensibilidade.</span><span class="sxs-lookup"><span data-stu-id="bfbfc-110">This organization hierarchy is built on Finance and Operations apps, but it's exposed in Dataverse for informational and extensibility purposes.</span></span> <span data-ttu-id="bfbfc-111">A ilustração a seguir mostra informações da hierarquia da organização que é exposta no Dataverse como um fluxo de dados unidirecional de aplicativos do Finance and Operations para o Dataverse.</span><span class="sxs-lookup"><span data-stu-id="bfbfc-111">The following illustration shows the organization hierarchy information that is exposed in Dataverse as a one-way data flow from Finance and Operations apps to Dataverse.</span></span>

![Imagem de arquitetura](media/dual-write-data-flow.png)

<span data-ttu-id="bfbfc-113">Os mapas de tabelas da hierarquia da organização estão disponíveis para sincronização unidirecional de dados de aplicativos do Finance and Operations para o Dataverse.</span><span class="sxs-lookup"><span data-stu-id="bfbfc-113">Organization hierarchy table maps are available for one-way synchronization of data from Finance and Operations apps to Dataverse.</span></span>

## <a name="templates"></a><span data-ttu-id="bfbfc-114">Modelos</span><span class="sxs-lookup"><span data-stu-id="bfbfc-114">Templates</span></span>

<span data-ttu-id="bfbfc-115">As informações do produto contêm todos os dados relacionados ao produto e sua definição, como as dimensões do produto ou as dimensões de rastreamento e armazenamento.</span><span class="sxs-lookup"><span data-stu-id="bfbfc-115">Product information contains all the information related to the product and its definition, such as the product dimensions or the tracking and storage dimensions.</span></span> <span data-ttu-id="bfbfc-116">Como mostrado na tabela a seguir, é criada uma coleção de mapas de tabelas para sincronizar produtos e as informações relacionadas.</span><span class="sxs-lookup"><span data-stu-id="bfbfc-116">As the following table shows, a collection of table maps is created to sync products and related information.</span></span>

<span data-ttu-id="bfbfc-117">Aplicativos Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="bfbfc-117">Finance and Operations apps</span></span> | <span data-ttu-id="bfbfc-118">Outros aplicativos do Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="bfbfc-118">Other Dynamics 365 apps</span></span> | <span data-ttu-id="bfbfc-119">descrição</span><span class="sxs-lookup"><span data-stu-id="bfbfc-119">Description</span></span>
-----------------------|--------------------------------|---
<span data-ttu-id="bfbfc-120">Finalidades da hierarquia da organização</span><span class="sxs-lookup"><span data-stu-id="bfbfc-120">Organization hierarchy purposes</span></span> | <span data-ttu-id="bfbfc-121">msdyn_internalorganizationhierarchypurposes</span><span class="sxs-lookup"><span data-stu-id="bfbfc-121">msdyn_internalorganizationhierarchypurposes</span></span> | <span data-ttu-id="bfbfc-122">Este modelo oferece sincronização unidirecional da tabela Finalidade da Hierarquia da Organização.</span><span class="sxs-lookup"><span data-stu-id="bfbfc-122">This template provides one-way synchronization of the Organization Hierarchy Purpose table.</span></span>
<span data-ttu-id="bfbfc-123">Tipo de hierarquia da organização</span><span class="sxs-lookup"><span data-stu-id="bfbfc-123">Organization hierarchy type</span></span> | <span data-ttu-id="bfbfc-124">msdyn_internalorganizationhierarchytypes</span><span class="sxs-lookup"><span data-stu-id="bfbfc-124">msdyn_internalorganizationhierarchytypes</span></span> | <span data-ttu-id="bfbfc-125">Este modelo oferece sincronização unidirecional da tabela Tipo da Hierarquia da Organização.</span><span class="sxs-lookup"><span data-stu-id="bfbfc-125">This template provides one-way synchronization of the Organization Hierarchy Type table.</span></span>
<span data-ttu-id="bfbfc-126">Hierarquia da organização - publicada</span><span class="sxs-lookup"><span data-stu-id="bfbfc-126">Organization hierarchy - published</span></span> | <span data-ttu-id="bfbfc-127">msdyn_internalorganizationhierarchies</span><span class="sxs-lookup"><span data-stu-id="bfbfc-127">msdyn_internalorganizationhierarchies</span></span> | <span data-ttu-id="bfbfc-128">Este modelo oferece sincronização unidirecional da tabela Hierarquia da Organização Publicada.</span><span class="sxs-lookup"><span data-stu-id="bfbfc-128">This template provides one-way synchronization of the Organization Hierarchy Published table.</span></span>
<span data-ttu-id="bfbfc-129">Unidade operacional</span><span class="sxs-lookup"><span data-stu-id="bfbfc-129">Operating unit</span></span> | <span data-ttu-id="bfbfc-130">msdyn_internalorganizations</span><span class="sxs-lookup"><span data-stu-id="bfbfc-130">msdyn_internalorganizations</span></span> |
<span data-ttu-id="bfbfc-131">Entidades legais</span><span class="sxs-lookup"><span data-stu-id="bfbfc-131">Legal entities</span></span> | <span data-ttu-id="bfbfc-132">msdyn_internalorganizations</span><span class="sxs-lookup"><span data-stu-id="bfbfc-132">msdyn_internalorganizations</span></span> |
<span data-ttu-id="bfbfc-133">Entidades legais</span><span class="sxs-lookup"><span data-stu-id="bfbfc-133">Legal entities</span></span> | <span data-ttu-id="bfbfc-134">cdm_companies</span><span class="sxs-lookup"><span data-stu-id="bfbfc-134">cdm_companies</span></span> | <span data-ttu-id="bfbfc-135">Oferece sincronização bidirecional de informações da entidade legal (empresa).</span><span class="sxs-lookup"><span data-stu-id="bfbfc-135">Provides bidirectional synchronization of legal entity (company) information.</span></span>

[!include [banner](../../includes/dual-write-symbols.md)]

[!include [Organization hierarchy purposes](includes/OrganizationHierarchyPurpose-msdyn-internalorganizationhierarchypurposes.md)]

[!include [Organization hierarchy type](includes/OrganizationHierarchyType-msdyn-internalorganizationhierarchytypes.md)]

[!include [Organization hierarchy - published](includes/OrganizationHierarchyPublished-msdyn-internalorganizationhierarchies.md)]

## <a name="internal-organization"></a><span data-ttu-id="bfbfc-136">Organização interna</span><span class="sxs-lookup"><span data-stu-id="bfbfc-136">Internal Organization</span></span>

<span data-ttu-id="bfbfc-137">As informações internas da organização no Dataverse vêm de duas tabelas, **unidade operacional** e **entidades legais**.</span><span class="sxs-lookup"><span data-stu-id="bfbfc-137">Internal organization information in Dataverse comes from two tables, **operating unit** and **legal entities**.</span></span>

[!include [Operating unit](includes/OperatingUnit-msdyn-internalorganizations.md)]

[!include [Legal entities](includes/LegalEntities-msdyn-internalorganizations.md)]

[!include [Legal entities](includes/LegalEntities-Companies.md)]


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]