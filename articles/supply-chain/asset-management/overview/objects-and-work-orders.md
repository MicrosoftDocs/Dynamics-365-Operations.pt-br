---
title: Ativos e ordens de serviço
description: Este tópico descreve ativos e ordens de serviço no Asset Management.
author: josaw1
manager: tfehr
ms.date: 06/24/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5c2500a695fcffe0d60ac13b1b74cda4322b0e14
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4422225"
---
# <a name="assets-and-work-orders"></a><span data-ttu-id="0bb51-103">Ativos e ordens de serviço</span><span class="sxs-lookup"><span data-stu-id="0bb51-103">Assets and work orders</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="0bb51-104">Este tópico descreve ativos e ordens de serviço no Asset Management.</span><span class="sxs-lookup"><span data-stu-id="0bb51-104">This topic describes assets and work orders in Asset Management.</span></span> <span data-ttu-id="0bb51-105">Os ativos e as ordens de serviço são partes centrais do Asset Management.</span><span class="sxs-lookup"><span data-stu-id="0bb51-105">Assets and work orders are the central parts of Asset Management.</span></span> <span data-ttu-id="0bb51-106">Um *ativo* é um computador ou uma peça do computador que exige manutenção e serviço contínuos.</span><span class="sxs-lookup"><span data-stu-id="0bb51-106">An *asset* is a machine or machine part that requires continuous maintenance and service.</span></span> <span data-ttu-id="0bb51-107">Os ativos podem ser criados em uma estrutura hierárquica, e podem ser relacionados a locais funcionais.</span><span class="sxs-lookup"><span data-stu-id="0bb51-107">Assets can be created in a hierarchical structure, and they can be related to functional locations.</span></span> <span data-ttu-id="0bb51-108">Os trabalhos de manutenção podem ser planejados em todos os níveis na estrutura de ativos.</span><span class="sxs-lookup"><span data-stu-id="0bb51-108">Maintenance jobs can be planned at all levels in the asset structure.</span></span>

<span data-ttu-id="0bb51-109">Vários dados, como informações sobre o produto e as especificações de ativo, os planos de manutenção necessários são configurados em cada ativo.</span><span class="sxs-lookup"><span data-stu-id="0bb51-109">Various data, such as product information and asset specification, and required maintenance plans are set up on each asset.</span></span> <span data-ttu-id="0bb51-110">A ilustração a seguir mostra uma visão geral de dados de ativo e a afiliação de ativos a tipos de trabalho.</span><span class="sxs-lookup"><span data-stu-id="0bb51-110">The following illustration shows an overview of asset data and the affiliation of assets to job types.</span></span> <span data-ttu-id="0bb51-111">O texto em vermelho será usado para exemplos que mostrem a herança e as dependências.</span><span class="sxs-lookup"><span data-stu-id="0bb51-111">Red text is used for examples that show inheritance and dependencies.</span></span>

![Diagrama exibindo dados do ativo relacionados aos tipos de trabalho](media/05-overview-image.png)

<span data-ttu-id="0bb51-113">Cada ordem de serviço tem um tipo de ordem de serviço, como manutenção preventiva, manutenção corretiva ou inspeção.</span><span class="sxs-lookup"><span data-stu-id="0bb51-113">Every work order has a work order type, such preventive maintenance, corrective maintenance, or inspection.</span></span> <span data-ttu-id="0bb51-114">A ordem de serviço contém um ou vários trabalhos da ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="0bb51-114">The work order contains one or more work order jobs.</span></span> <span data-ttu-id="0bb51-115">Cada trabalho da ordem de serviço define um trabalho que deve ser realizado em um ativo e um tipo de trabalho relacionado.</span><span class="sxs-lookup"><span data-stu-id="0bb51-115">Every work order job defines a job that must be performed on an asset and a related job type.</span></span> <span data-ttu-id="0bb51-116">Os exemplos de tipos de trabalho relacionados incluem vistoria de 10 mil km, 50 mil km, 1 ano e inspeção de segurança.</span><span class="sxs-lookup"><span data-stu-id="0bb51-116">Examples of related job types include 10,000 km, 50,000 km, 1-year overhaul, and safety inspection.</span></span> <span data-ttu-id="0bb51-117">Um ordem de serviço pode ser relatada a vários ativos.</span><span class="sxs-lookup"><span data-stu-id="0bb51-117">One work order can be related to multiple assets.</span></span>

<span data-ttu-id="0bb51-118">A ilustração a seguir mostra uma visão geral dos dados principais de uma ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="0bb51-118">The following illustration shows an overview of the key data in a work order.</span></span>

![Diagrama exibindo os principais dados em uma ordem de serviço](media/06-overview-image.png)

<span data-ttu-id="0bb51-120">Um ordem de serviço pode ser relacionada a outra ordem de serviço, e os tipos de trabalho podem conter os trabalhos subsequentes que criam uma ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="0bb51-120">A work order can be related to another work order, and job types can contain succeeding jobs that create a work order.</span></span> <span data-ttu-id="0bb51-121">Geralmente, não existem dependências entre ordens de serviço.</span><span class="sxs-lookup"><span data-stu-id="0bb51-121">In general, there are no dependencies between work orders.</span></span> <span data-ttu-id="0bb51-122">Portanto, elas podem alterar o estado de ciclo de vida da ordem de serviço e podem ser agendadas de forma independente umas das outras.</span><span class="sxs-lookup"><span data-stu-id="0bb51-122">Therefore, they can change their work order lifecycle state and can be scheduled independently of each other.</span></span>

<span data-ttu-id="0bb51-123">As ordens de serviço podem ser criadas em várias formas relacionadas à manutenção corretiva, preventiva ou reativa.</span><span class="sxs-lookup"><span data-stu-id="0bb51-123">Work orders can be created in various ways that are related to corrective, preventive, or reactive maintenance.</span></span> <span data-ttu-id="0bb51-124">Você também pode criar ordens de serviço manualmente.</span><span class="sxs-lookup"><span data-stu-id="0bb51-124">You can also create work orders manually.</span></span> <span data-ttu-id="0bb51-125">A ilustração a seguir mostra uma visão geral do processo para a criação automática ou manual de ordens de serviço.</span><span class="sxs-lookup"><span data-stu-id="0bb51-125">The following illustration shows an overview of the process for automatic or manual creation of work orders.</span></span>

![Diagrama exibindo a criação automática ou manual de ordens de serviço](media/07-overview-image.png)

<span data-ttu-id="0bb51-127">Várias etapas devem ser concluídas quando você deseja agendar e executar um trabalho de manutenção em uma ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="0bb51-127">Several steps must be completed when you want to schedule and run a maintenance job on a work order.</span></span> <span data-ttu-id="0bb51-128">A ilustração a seguir mostra uma visão geral do processamento para uma ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="0bb51-128">The following illustration shows an overview of the processing for a work order.</span></span>

![Diagrama exibindo a visão geral do processamento de uma ordem de serviço](media/08-overview-image.png)

> [!NOTE]
> <span data-ttu-id="0bb51-130">Geralmente, quando você trabalha no Dynamics 365 Supply Chain Management e no módulo **Asset Management**, seleciona **Novo** para criar um novo registro, seleciona **Editar** para atualizar um registro existente e seleciona **Salvar** para salvar dados novos ou editados.</span><span class="sxs-lookup"><span data-stu-id="0bb51-130">In general, when you work in Dynamics 365 Supply Chain Management and the **Asset Management** module, you select **New** to create a new record, you select **Edit** to update an existing record, and you select **Save** to save new or edited data.</span></span>
