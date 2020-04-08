---
title: Cenários com suporte para configuração de gravação dupla
description: Este tópico descreve os cenários com suporte para configuração de gravação dupla.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 01/06/2020
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
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: d7ff514768ee8e4797b591da89e190a855385885
ms.sourcegitcommit: 68f1485de7d64a6c9eba1088af63bd07992d972d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2020
ms.locfileid: "3172845"
---
# <a name="supported-scenarios-for-dual-write-setup"></a><span data-ttu-id="5589d-103">Cenários com suporte para configuração de gravação dupla</span><span class="sxs-lookup"><span data-stu-id="5589d-103">Supported scenarios for dual-write setup</span></span>

[!include [banner](../../includes/banner.md)]

[!include [preview-banner](../../includes/preview-banner.md)]

<span data-ttu-id="5589d-104">É possível configurar uma conexão de gravação dupla entre um ambiente do Finance and Operations e um ambiente do Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="5589d-104">You can set up a dual-write connection between a Finance and Operations environment and a Common Data Service environment.</span></span>

+ <span data-ttu-id="5589d-105">Um **ambiente do Finance and Operations** fornece a plataforma subjacente para **aplicativos do Finance and Operations** (por exemplo, Microsoft Dynamics 365 Finance, Dynamics 365 Supply Chain Management, Dynamics 365 Retail e Dynamics 365 Human Resources).</span><span class="sxs-lookup"><span data-stu-id="5589d-105">A **Finance and Operations environment** provides the underlying platform for **Finance and Operations apps** (for example, Microsoft Dynamics 365 Finance, Dynamics 365 Supply Chain Management, Dynamics 365 Retail, and Dynamics 365 Human Resources).</span></span>
+ <span data-ttu-id="5589d-106">Um **ambiente do Common Data Service** fornece a plataforma subjacente para **aplicativos baseados em modelo no Dynamics 365** (Dynamics 365 Sales, Dynamics 365 Customer Service, Dynamics 365 Field Service, Dynamics 365 Marketing e Dynamics 365 Project Service Automation).</span><span class="sxs-lookup"><span data-stu-id="5589d-106">A **Common Data Service environment** provides the underlying platform for **model-driven apps in Dynamics 365** (Dynamics 365 Sales, Dynamics 365 Customer Service, Dynamics 365 Field Service, Dynamics 365 Marketing, and Dynamics 365 Project Service Automation).</span></span>

<span data-ttu-id="5589d-107">O mecanismo de configuração varia, dependendo da sua assinatura e do ambiente.</span><span class="sxs-lookup"><span data-stu-id="5589d-107">The setup mechanism varies, depending on your subscription and the environment.</span></span>

+ <span data-ttu-id="5589d-108">Para novas instâncias de aplicativos do Finance and Operations, a configuração de uma conexão de gravação dupla começa no Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="5589d-108">For new instances of Finance and Operations apps, the setup of a dual-write connection begins in Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="5589d-109">Se você possuir uma licença para a Microsoft Power Platform, receberá um novo ambiente do Common Data Service caso o locatário não tenha um.</span><span class="sxs-lookup"><span data-stu-id="5589d-109">If you have a license for Microsoft Power Platform, you will get a new Common Data Service environment if your tenant doesn't have one.</span></span>
+ <span data-ttu-id="5589d-110">Para aplicativos do Finance and Operations de instâncias existentes, a configuração de uma conexão de gravação dupla começa no ambiente do Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="5589d-110">For existing instances Finance and Operations apps, the setup of a dual-write connection begins in the Finance and Operations environment.</span></span>

<span data-ttu-id="5589d-111">Há suporte para os seguintes cenários de instalação:</span><span class="sxs-lookup"><span data-stu-id="5589d-111">The following setup scenarios are supported:</span></span>

+ [<span data-ttu-id="5589d-112">Uma nova instância de aplicativo do Finance and Operations e uma nova instância de aplicativo baseado em modelo</span><span class="sxs-lookup"><span data-stu-id="5589d-112">A new Finance and Operations app instance and a new model-driven app instance</span></span>](#new-new)
+ [<span data-ttu-id="5589d-113">Uma nova instância de aplicativo do Finance and Operations e uma instância existente de aplicativo baseado em modelo</span><span class="sxs-lookup"><span data-stu-id="5589d-113">A new Finance and Operations app instance and an existing model-driven app instance</span></span>](#new-existing)
+ [<span data-ttu-id="5589d-114">Uma nova instância de aplicativo do Finance and Operations com dados de demonstração e uma nova instância de aplicativo baseado em modelo</span><span class="sxs-lookup"><span data-stu-id="5589d-114">A new Finance and Operations app instance that has demo data and a new model-driven app instance</span></span>](#new-demo-new)
+ [<span data-ttu-id="5589d-115">Uma nova instância de aplicativo do Finance and Operations com dados de demonstração e uma instância existente de aplicativo baseado em modelo</span><span class="sxs-lookup"><span data-stu-id="5589d-115">A new Finance and Operations app instance that has demo data and an existing model-driven app instance</span></span>](#new-demo-existing)
+ [<span data-ttu-id="5589d-116">Uma instância existente de aplicativo do Finance and Operations e uma instância nova ou existente de aplicativo baseado em modelo</span><span class="sxs-lookup"><span data-stu-id="5589d-116">An existing Finance and Operations app instance and a new or existing model-driven app instance</span></span>](#existing-existing)

## <a name="a-new-finance-and-operations-app-instance-and-a-new-model-driven-app-instance"></a><a id="new-new"></a><span data-ttu-id="5589d-117">Uma nova instância de aplicativo do Finance and Operations e uma nova instância de aplicativo baseado em modelo</span><span class="sxs-lookup"><span data-stu-id="5589d-117">A new Finance and Operations app instance and a new model-driven app instance</span></span>

<span data-ttu-id="5589d-118">Para configurar uma conexão de gravação dupla entre uma nova instância de um aplicativo do Finance and Operations que não possui dados e uma nova instância de um aplicativo baseado em modelo no Dynamics 365, siga as etapas em [Configuração de gravação dupla do Lifecycle Services](lcs-setup.md).</span><span class="sxs-lookup"><span data-stu-id="5589d-118">To set up a dual-write connection between a new instance of a Finance and Operations app that has no data and a new instance of a model-driven app in Dynamics 365, follow the steps in [Dual-write setup from Lifecycle Services](lcs-setup.md).</span></span> <span data-ttu-id="5589d-119">Quando a configuração da conexão é concluída, as seguintes ações ocorrem automaticamente:</span><span class="sxs-lookup"><span data-stu-id="5589d-119">When the connection setup is completed, the following actions occur automatically:</span></span>

- <span data-ttu-id="5589d-120">Um novo ambiente vazio do Finance and Operations é provisionado.</span><span class="sxs-lookup"><span data-stu-id="5589d-120">A new, empty Finance and Operations environment is provisioned.</span></span>
- <span data-ttu-id="5589d-121">É provisionada uma nova instância vazia de um aplicativo baseado em modelo, em que a solução principal do CRM está instalada.</span><span class="sxs-lookup"><span data-stu-id="5589d-121">A new, empty instance of a model-driven app is provisioned, where the CRM prime solution is installed.</span></span>
- <span data-ttu-id="5589d-122">Uma conexão de gravação dupla é estabelecida para os dados da empresa DAT.</span><span class="sxs-lookup"><span data-stu-id="5589d-122">A dual-write connection is established for DAT company data.</span></span>
- <span data-ttu-id="5589d-123">Os mapas de entidade estão habilitados para sincronização em tempo real.</span><span class="sxs-lookup"><span data-stu-id="5589d-123">Entity maps are enabled for live synchronization.</span></span>

<span data-ttu-id="5589d-124">Ambos os ambientes estão prontos para sincronização de dados em tempo real.</span><span class="sxs-lookup"><span data-stu-id="5589d-124">Both environments are then ready for live data synchronization.</span></span>

## <a name="a-new-finance-and-operations-app-instance-and-an-existing-model-driven-app-instance"></a><a id="new-existing"></a><span data-ttu-id="5589d-125">Uma nova instância de aplicativo do Finance and Operations e uma instância existente de aplicativo baseado em modelo</span><span class="sxs-lookup"><span data-stu-id="5589d-125">A new Finance and Operations app instance and an existing model-driven app instance</span></span>

<span data-ttu-id="5589d-126">Para configurar uma conexão de gravação dupla entre uma nova instância de um aplicativo do Finance and Operations que não possui dados e uma instância existente de um aplicativo baseado em modelo no Dynamics 365, siga as etapas em [Configuração de gravação dupla do Lifecycle Services](lcs-setup.md).</span><span class="sxs-lookup"><span data-stu-id="5589d-126">To set up a dual-write connection between a new instance of a Finance and Operations app that has no data and an existing instance of a model-driven app in Dynamics 365, follow the steps in [Dual-write setup from Lifecycle Services](lcs-setup.md).</span></span> <span data-ttu-id="5589d-127">Quando a configuração da conexão é concluída, as seguintes ações ocorrem automaticamente:</span><span class="sxs-lookup"><span data-stu-id="5589d-127">When the connection setup is completed, the following actions occur automatically:</span></span>

- <span data-ttu-id="5589d-128">Um novo ambiente vazio do Finance and Operations é provisionado.</span><span class="sxs-lookup"><span data-stu-id="5589d-128">A new, empty Finance and Operations environment is provisioned.</span></span>
- <span data-ttu-id="5589d-129">Uma conexão de gravação dupla é estabelecida para os dados da empresa DAT.</span><span class="sxs-lookup"><span data-stu-id="5589d-129">A dual-write connection is established for DAT company data.</span></span>
- <span data-ttu-id="5589d-130">Os mapas de entidade estão habilitados para sincronização em tempo real.</span><span class="sxs-lookup"><span data-stu-id="5589d-130">Entity maps are enabled for live synchronization.</span></span>

<span data-ttu-id="5589d-131">Ambos os ambientes estão prontos para sincronização de dados em tempo real.</span><span class="sxs-lookup"><span data-stu-id="5589d-131">Both environments are then ready for live data synchronization.</span></span>

<span data-ttu-id="5589d-132">Para sincronizar os dados existentes do Common Data Service com o aplicativo do Finance and Operations, siga as etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="5589d-132">To sync the existing Common Data Service data to the Finance and Operations app, follow these steps.</span></span>

1. <span data-ttu-id="5589d-133">Crie uma empresa no aplicativo do Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="5589d-133">Create a new company in the Finance and Operations app.</span></span>
2. <span data-ttu-id="5589d-134">Adicione a empresa à configuração da conexão de gravação dupla.</span><span class="sxs-lookup"><span data-stu-id="5589d-134">Add the company to the dual-write connection setup.</span></span>
3. <span data-ttu-id="5589d-135">[Inicialize](bootstrap-company-data.md) os dados do Common Data Service usando o código de uma empresa da Organização Internacional de Normalização (ISO) com três letras.</span><span class="sxs-lookup"><span data-stu-id="5589d-135">[Bootstrap](bootstrap-company-data.md) the Common Data Service data by using a three-letter International Organization for Standardization (ISO) company code.</span></span>

<span data-ttu-id="5589d-136">Como a gravação dupla está no modo de sincronização em tempo real, os dados do Common Data Service começam a fluir automaticamente para o aplicativo do Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="5589d-136">Because dual-write is in live synchronization mode, the data from Common Data Service automatically starts to flow to the Finance and Operations app.</span></span>

## <a name="a-new-finance-and-operations-app-instance-that-has-demo-data-and-a-new-model-driven-app-instance"></a><a id="new-demo-new"></a><span data-ttu-id="5589d-137">Uma nova instância de aplicativo do Finance and Operations com dados de demonstração e uma nova instância de aplicativo baseado em modelo</span><span class="sxs-lookup"><span data-stu-id="5589d-137">A new Finance and Operations app instance that has demo data and a new model-driven app instance</span></span>

<span data-ttu-id="5589d-138">Para configurar uma conexão de gravação dupla entre uma nova instância de um aplicativo do Finance and Operations com dados de demonstração e uma nova instância de um aplicativo baseado em modelo no Dynamics 365, siga as etapas na seção [Uma nova instância de aplicativo do Finance and Operations e uma nova instância de aplicativo baseado em modelo](#new-new) anteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="5589d-138">To set up a dual-write connection between a new instance of a Finance and Operations app that has demo data and a new instance of a model-driven app in Dynamics 365, follow the steps in the [A new Finance and Operations app instance and a new model-driven app instance](#new-new) section earlier in this topic.</span></span> <span data-ttu-id="5589d-139">Quando a configuração da conexão estiver concluída, para sincronizar os dados de demonstração com o aplicativo baseado em modelo, siga as etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="5589d-139">When the connection setup is completed, if you want to sync the demo data to the model-driven app, follow these steps.</span></span>

1. <span data-ttu-id="5589d-140">Abra o aplicativo do Finance and Operations na página do LCS, entre e acesse **Gerenciamento de dados \> Gravação dupla**.</span><span class="sxs-lookup"><span data-stu-id="5589d-140">Open the Finance and Operations app from the LCS page, sign in, and then go to **Data Management \> Dual-write**.</span></span>
2. <span data-ttu-id="5589d-141">Execute a funcionalidade **Sincronização inicial** para as entidades das quais você deseja sincronizar dados.</span><span class="sxs-lookup"><span data-stu-id="5589d-141">Run the **Initial sync** functionality for the entities that you want to sync data for.</span></span>

## <a name="a-new-finance-and-operations-app-instance-that-has-demo-data-and-an-existing-model-driven-app-instance"></a><a id="new-demo-existing"></a><span data-ttu-id="5589d-142">Uma nova instância de aplicativo do Finance and Operations com dados de demonstração e uma instância existente de aplicativo baseado em modelo</span><span class="sxs-lookup"><span data-stu-id="5589d-142">A new Finance and Operations app instance that has demo data and an existing model-driven app instance</span></span>

<span data-ttu-id="5589d-143">Para configurar uma conexão de gravação dupla entre uma nova instância de um aplicativo do Finance and Operations com dados de demonstração e uma instância existente de um aplicativo baseado em modelo no Dynamics 365, siga as etapas na seção [Uma nova instância de aplicativo do Finance and Operations e uma instância existente de aplicativo baseado em modelo](#new-existing) anteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="5589d-143">To set up a dual-write connection between a new instance of a Finance and Operations app that has demo data and an existing instance of a model-driven app in Dynamics 365, follow the steps in the [A new Finance and Operations app instance and an existing model-driven app instance](#new-existing) section earlier in this topic.</span></span> <span data-ttu-id="5589d-144">Quando a configuração da conexão estiver concluída, para sincronizar os dados de demonstração com o aplicativo baseado em modelo, siga as etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="5589d-144">When the connection setup is completed, if you want to sync the demo data to the model-driven app, follow these steps.</span></span>

1. <span data-ttu-id="5589d-145">Abra o aplicativo do Finance and Operations na página do LCS, entre e acesse **Gerenciamento de dados \> Gravação dupla**.</span><span class="sxs-lookup"><span data-stu-id="5589d-145">Open the Finance and Operations app from the LCS page, sign in, and then go to **Data Management \> Dual-write**.</span></span>
2. <span data-ttu-id="5589d-146">Execute a funcionalidade **Sincronização inicial** para as entidades das quais você deseja sincronizar dados.</span><span class="sxs-lookup"><span data-stu-id="5589d-146">Run the **Initial sync** functionality for the entities that you want to sync data for.</span></span>

<span data-ttu-id="5589d-147">Para sincronizar os dados existentes do Common Data Service com o aplicativo do Finance and Operations, siga as etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="5589d-147">To sync the existing Common Data Service data to the Finance and Operations app, follow these steps.</span></span>

1. <span data-ttu-id="5589d-148">Crie uma empresa no aplicativo do Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="5589d-148">Create a new company in the Finance and Operations app.</span></span>
2. <span data-ttu-id="5589d-149">Adicione a empresa à configuração da conexão de gravação dupla.</span><span class="sxs-lookup"><span data-stu-id="5589d-149">Add the company to the dual-write connection setup.</span></span>
3. <span data-ttu-id="5589d-150">[Inicialize](bootstrap-company-data.md) os dados do Common Data Service usando o código de uma empresa da Organização Internacional de Normalização (ISO) com três letras.</span><span class="sxs-lookup"><span data-stu-id="5589d-150">[Bootstrap](bootstrap-company-data.md) the Common Data Service data by using a three-letter ISO company code.</span></span>

<span data-ttu-id="5589d-151">Como a gravação dupla está no modo de sincronização em tempo real, os dados do Common Data Service começam a fluir automaticamente para o aplicativo do Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="5589d-151">Because dual-write is in live synchronization mode, the data from Common Data Service automatically starts to flow to the Finance and Operations app.</span></span>

## <a name="an-existing-finance-and-operations-app-instance-and-a-new-or-existing-model-driven-app-instance"></a><a id="existing-existing"></a><span data-ttu-id="5589d-152">Uma instância existente de aplicativo do Finance and Operations e uma instância nova ou existente de aplicativo baseado em modelo</span><span class="sxs-lookup"><span data-stu-id="5589d-152">An existing Finance and Operations app instance and a new or existing model-driven app instance</span></span>

<span data-ttu-id="5589d-153">A configuração de uma conexão de gravação dupla entre uma instância existente de um aplicativo do Finance and Operations e uma instância nova ou existente de um aplicativo baseado em modelo no Dynamics 365 ocorre no ambiente do Finance and Operation.</span><span class="sxs-lookup"><span data-stu-id="5589d-153">The setup of a dual-write connection between an existing instance of a Finance and Operations app and a new or existing instance of a model-driven app in Dynamics 365 occurs in the Finance and Operation environment.</span></span>

1. <span data-ttu-id="5589d-154">Configure a conexão do aplicativo do Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="5589d-154">Set up the connection from the Finance and Operations app.</span></span>
2. <span data-ttu-id="5589d-155">Para sincronizar os dados existentes do Common Data Service com o aplicativo do Finance and Operations, [inicialize](bootstrap-company-data.md) os dados do Common Data Service usando o código de uma empresa da ISO com três letras.</span><span class="sxs-lookup"><span data-stu-id="5589d-155">To sync the existing Common Data Service data to the Finance and Operations app, [bootstrap](bootstrap-company-data.md) the Common Data Service data by using a three-letter ISO company code.</span></span>

<span data-ttu-id="5589d-156">Como a gravação dupla está no modo de sincronização em tempo real, os dados do Common Data Service começam a fluir automaticamente para o aplicativo do Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="5589d-156">Because dual-write is in live synchronization mode, the data from Common Data Service automatically starts to flow to the Finance and Operations app.</span></span>
