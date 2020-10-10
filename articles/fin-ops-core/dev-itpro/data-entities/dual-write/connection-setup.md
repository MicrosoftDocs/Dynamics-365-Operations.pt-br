---
title: Cenários com suporte para configuração de gravação dupla
description: Este tópico descreve os cenários com suporte para configuração de gravação dupla.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 08/17/2020
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
ms.openlocfilehash: b4f69e7933bc5a50cccad6911c99cf08d2768578
ms.sourcegitcommit: b3df62842e62234e8eaa16992375582518976131
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/17/2020
ms.locfileid: "3818587"
---
# <a name="supported-scenarios-for-dual-write-setup"></a><span data-ttu-id="778d4-103">Cenários com suporte para configuração de gravação dupla</span><span class="sxs-lookup"><span data-stu-id="778d4-103">Supported scenarios for dual-write setup</span></span>

[!include [banner](../../includes/banner.md)]

[!include [preview-banner](../../includes/preview-banner.md)]

<span data-ttu-id="778d4-104">É possível configurar uma conexão de gravação dupla entre um ambiente do Finance and Operations e um ambiente do Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="778d4-104">You can set up a dual-write connection between a Finance and Operations environment and a Common Data Service environment.</span></span>

+ <span data-ttu-id="778d4-105">Um ambiente do **Finance and Operations** fornece a plataforma subjacente para aplicativos **Finance and Operations** (por exemplo, Microsoft Dynamics 365 Finance, Dynamics 365 Supply Chain Management e Dynamics 365 Retail).</span><span class="sxs-lookup"><span data-stu-id="778d4-105">A **Finance and Operations environment** provides the underlying platform for **Finance and Operations apps** (for example, Microsoft Dynamics 365 Finance, Dynamics 365 Supply Chain Management, and Dynamics 365 Retail).</span></span>
+ <span data-ttu-id="778d4-106">Um **ambiente do Common Data Service** fornece a plataforma subjacente para **aplicativos baseados em modelo no Dynamics 365** (Dynamics 365 Sales, Dynamics 365 Customer Service, Dynamics 365 Field Service, Dynamics 365 Marketing e Dynamics 365 Project Service Automation).</span><span class="sxs-lookup"><span data-stu-id="778d4-106">A **Common Data Service environment** provides the underlying platform for **model-driven apps in Dynamics 365** (Dynamics 365 Sales, Dynamics 365 Customer Service, Dynamics 365 Field Service, Dynamics 365 Marketing, and Dynamics 365 Project Service Automation).</span></span>

>[!IMPORTANT]
><span data-ttu-id="778d4-107">Recursos humanos no Finance and Operations oferece suporte a conexões de gravação dupla, mas o aplicativo Dynamics 365 Human Resources não.</span><span class="sxs-lookup"><span data-stu-id="778d4-107">Human Resources in Finance and Operations supports dual-write connections, but the Dynamics 365 Human Resources app doesn't.</span></span>

<span data-ttu-id="778d4-108">O mecanismo de configuração varia, dependendo da sua assinatura e do ambiente.</span><span class="sxs-lookup"><span data-stu-id="778d4-108">The setup mechanism varies, depending on your subscription and the environment.</span></span>

+ <span data-ttu-id="778d4-109">Para novas instâncias de aplicativos do Finance and Operations, a configuração de uma conexão de gravação dupla começa no Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="778d4-109">For new instances of Finance and Operations apps, the setup of a dual-write connection begins in Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="778d4-110">Se você possuir uma licença para a Power Platform, receberá um novo ambiente do Common Data Service caso o locatário não tenha um.</span><span class="sxs-lookup"><span data-stu-id="778d4-110">If you have a license for Power Platform, you will get a new Common Data Service environment if your tenant doesn't have one.</span></span>
+ <span data-ttu-id="778d4-111">Para aplicativos do Finance and Operations de instâncias existentes, a configuração de uma conexão de gravação dupla começa no ambiente do Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="778d4-111">For existing instances Finance and Operations apps, the setup of a dual-write connection begins in the Finance and Operations environment.</span></span>

<span data-ttu-id="778d4-112">Há suporte para os seguintes cenários de instalação:</span><span class="sxs-lookup"><span data-stu-id="778d4-112">The following setup scenarios are supported:</span></span>

+ [<span data-ttu-id="778d4-113">Uma nova instância de aplicativo do Finance and Operations e uma nova instância de aplicativo baseado em modelo</span><span class="sxs-lookup"><span data-stu-id="778d4-113">A new Finance and Operations app instance and a new model-driven app instance</span></span>](#new-new)
+ [<span data-ttu-id="778d4-114">Uma nova instância de aplicativo do Finance and Operations e uma instância existente de aplicativo baseado em modelo</span><span class="sxs-lookup"><span data-stu-id="778d4-114">A new Finance and Operations app instance and an existing model-driven app instance</span></span>](#new-existing)
+ [<span data-ttu-id="778d4-115">Uma nova instância de aplicativo do Finance and Operations com dados de demonstração e uma nova instância de aplicativo baseado em modelo</span><span class="sxs-lookup"><span data-stu-id="778d4-115">A new Finance and Operations app instance that has demo data and a new model-driven app instance</span></span>](#new-demo-new)
+ [<span data-ttu-id="778d4-116">Uma nova instância de aplicativo do Finance and Operations com dados de demonstração e uma instância existente de aplicativo baseado em modelo</span><span class="sxs-lookup"><span data-stu-id="778d4-116">A new Finance and Operations app instance that has demo data and an existing model-driven app instance</span></span>](#new-demo-existing)
+ [<span data-ttu-id="778d4-117">Uma instância existente de aplicativo do Finance and Operations e uma instância nova ou existente de aplicativo baseado em modelo</span><span class="sxs-lookup"><span data-stu-id="778d4-117">An existing Finance and Operations app instance and a new or existing model-driven app instance</span></span>](#existing-existing)

## <a name="a-new-finance-and-operations-app-instance-and-a-new-model-driven-app-instance"></a><a id="new-new"></a><span data-ttu-id="778d4-118">Uma nova instância de aplicativo do Finance and Operations e uma nova instância de aplicativo baseado em modelo</span><span class="sxs-lookup"><span data-stu-id="778d4-118">A new Finance and Operations app instance and a new model-driven app instance</span></span>

<span data-ttu-id="778d4-119">Para configurar uma conexão de gravação dupla entre uma nova instância de um aplicativo do Finance and Operations que não possui dados e uma nova instância de um aplicativo baseado em modelo no Dynamics 365, siga as etapas em [Configuração de gravação dupla do Lifecycle Services](lcs-setup.md).</span><span class="sxs-lookup"><span data-stu-id="778d4-119">To set up a dual-write connection between a new instance of a Finance and Operations app that has no data and a new instance of a model-driven app in Dynamics 365, follow the steps in [Dual-write setup from Lifecycle Services](lcs-setup.md).</span></span> <span data-ttu-id="778d4-120">Quando a configuração da conexão é concluída, as seguintes ações ocorrem automaticamente:</span><span class="sxs-lookup"><span data-stu-id="778d4-120">When the connection setup is completed, the following actions occur automatically:</span></span>

- <span data-ttu-id="778d4-121">Um novo ambiente vazio do Finance and Operations é provisionado.</span><span class="sxs-lookup"><span data-stu-id="778d4-121">A new, empty Finance and Operations environment is provisioned.</span></span>
- <span data-ttu-id="778d4-122">É provisionada uma nova instância vazia de um aplicativo baseado em modelo, em que a solução principal do CRM está instalada.</span><span class="sxs-lookup"><span data-stu-id="778d4-122">A new, empty instance of a model-driven app is provisioned, where the CRM prime solution is installed.</span></span>
- <span data-ttu-id="778d4-123">Uma conexão de gravação dupla é estabelecida para os dados da empresa DAT.</span><span class="sxs-lookup"><span data-stu-id="778d4-123">A dual-write connection is established for DAT company data.</span></span>
- <span data-ttu-id="778d4-124">Os mapas de entidade estão habilitados para sincronização em tempo real.</span><span class="sxs-lookup"><span data-stu-id="778d4-124">Entity maps are enabled for live synchronization.</span></span>

<span data-ttu-id="778d4-125">Ambos os ambientes estão prontos para sincronização de dados em tempo real.</span><span class="sxs-lookup"><span data-stu-id="778d4-125">Both environments are then ready for live data synchronization.</span></span>

## <a name="a-new-finance-and-operations-app-instance-and-an-existing-model-driven-app-instance"></a><a id="new-existing"></a><span data-ttu-id="778d4-126">Uma nova instância de aplicativo do Finance and Operations e uma instância existente de aplicativo baseado em modelo</span><span class="sxs-lookup"><span data-stu-id="778d4-126">A new Finance and Operations app instance and an existing model-driven app instance</span></span>

<span data-ttu-id="778d4-127">Para configurar uma conexão de gravação dupla entre uma nova instância de um aplicativo do Finance and Operations que não possui dados e uma instância existente de um aplicativo baseado em modelo no Dynamics 365, siga as etapas em [Configuração de gravação dupla do Lifecycle Services](lcs-setup.md).</span><span class="sxs-lookup"><span data-stu-id="778d4-127">To set up a dual-write connection between a new instance of a Finance and Operations app that has no data and an existing instance of a model-driven app in Dynamics 365, follow the steps in [Dual-write setup from Lifecycle Services](lcs-setup.md).</span></span> <span data-ttu-id="778d4-128">Quando a configuração da conexão é concluída, as seguintes ações ocorrem automaticamente:</span><span class="sxs-lookup"><span data-stu-id="778d4-128">When the connection setup is completed, the following actions occur automatically:</span></span>

- <span data-ttu-id="778d4-129">Um novo ambiente vazio do Finance and Operations é provisionado.</span><span class="sxs-lookup"><span data-stu-id="778d4-129">A new, empty Finance and Operations environment is provisioned.</span></span>
- <span data-ttu-id="778d4-130">Uma conexão de gravação dupla é estabelecida para os dados da empresa DAT.</span><span class="sxs-lookup"><span data-stu-id="778d4-130">A dual-write connection is established for DAT company data.</span></span>
- <span data-ttu-id="778d4-131">Os mapas de entidade estão habilitados para sincronização em tempo real.</span><span class="sxs-lookup"><span data-stu-id="778d4-131">Entity maps are enabled for live synchronization.</span></span>

<span data-ttu-id="778d4-132">Ambos os ambientes estão prontos para sincronização de dados em tempo real.</span><span class="sxs-lookup"><span data-stu-id="778d4-132">Both environments are then ready for live data synchronization.</span></span>

<span data-ttu-id="778d4-133">Para sincronizar os dados existentes do Common Data Service com o aplicativo do Finance and Operations, siga as etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="778d4-133">To sync the existing Common Data Service data to the Finance and Operations app, follow these steps.</span></span>

1. <span data-ttu-id="778d4-134">Crie uma empresa no aplicativo do Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="778d4-134">Create a new company in the Finance and Operations app.</span></span>
2. <span data-ttu-id="778d4-135">Adicione a empresa à configuração da conexão de gravação dupla.</span><span class="sxs-lookup"><span data-stu-id="778d4-135">Add the company to the dual-write connection setup.</span></span>
3. <span data-ttu-id="778d4-136">[Inicialize](bootstrap-company-data.md) os dados do Common Data Service usando o código de uma empresa da Organização Internacional de Normalização (ISO) com três letras.</span><span class="sxs-lookup"><span data-stu-id="778d4-136">[Bootstrap](bootstrap-company-data.md) the Common Data Service data by using a three-letter International Organization for Standardization (ISO) company code.</span></span>

<span data-ttu-id="778d4-137">Como a gravação dupla está no modo de sincronização em tempo real, os dados do Common Data Service começam a fluir automaticamente para o aplicativo do Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="778d4-137">Because dual-write is in live synchronization mode, the data from Common Data Service automatically starts to flow to the Finance and Operations app.</span></span>

## <a name="a-new-finance-and-operations-app-instance-that-has-demo-data-and-a-new-model-driven-app-instance"></a><a id="new-demo-new"></a><span data-ttu-id="778d4-138">Uma nova instância de aplicativo do Finance and Operations com dados de demonstração e uma nova instância de aplicativo baseado em modelo</span><span class="sxs-lookup"><span data-stu-id="778d4-138">A new Finance and Operations app instance that has demo data and a new model-driven app instance</span></span>

<span data-ttu-id="778d4-139">Para configurar uma conexão de gravação dupla entre uma nova instância de um aplicativo do Finance and Operations com dados de demonstração e uma nova instância de um aplicativo baseado em modelo no Dynamics 365, siga as etapas na seção [Uma nova instância de aplicativo do Finance and Operations e uma nova instância de aplicativo baseado em modelo](#new-new) anteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="778d4-139">To set up a dual-write connection between a new instance of a Finance and Operations app that has demo data and a new instance of a model-driven app in Dynamics 365, follow the steps in the [A new Finance and Operations app instance and a new model-driven app instance](#new-new) section earlier in this topic.</span></span> <span data-ttu-id="778d4-140">Quando a configuração da conexão estiver concluída, para sincronizar os dados de demonstração com o aplicativo baseado em modelo, siga as etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="778d4-140">When the connection setup is completed, if you want to sync the demo data to the model-driven app, follow these steps.</span></span>

1. <span data-ttu-id="778d4-141">Abra o aplicativo do Finance and Operations na página do LCS, entre e acesse **Gerenciamento de dados \> Gravação dupla**.</span><span class="sxs-lookup"><span data-stu-id="778d4-141">Open the Finance and Operations app from the LCS page, sign in, and then go to **Data Management \> Dual-write**.</span></span>
2. <span data-ttu-id="778d4-142">Execute a funcionalidade **Sincronização inicial** para as entidades das quais você deseja sincronizar dados.</span><span class="sxs-lookup"><span data-stu-id="778d4-142">Run the **Initial sync** functionality for the entities that you want to sync data for.</span></span>

## <a name="a-new-finance-and-operations-app-instance-that-has-demo-data-and-an-existing-model-driven-app-instance"></a><a id="new-demo-existing"></a><span data-ttu-id="778d4-143">Uma nova instância de aplicativo do Finance and Operations com dados de demonstração e uma instância existente de aplicativo baseado em modelo</span><span class="sxs-lookup"><span data-stu-id="778d4-143">A new Finance and Operations app instance that has demo data and an existing model-driven app instance</span></span>

<span data-ttu-id="778d4-144">Para configurar uma conexão de gravação dupla entre uma nova instância de um aplicativo do Finance and Operations com dados de demonstração e uma instância existente de um aplicativo baseado em modelo no Dynamics 365, siga as etapas na seção [Uma nova instância de aplicativo do Finance and Operations e uma instância existente de aplicativo baseado em modelo](#new-existing) anteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="778d4-144">To set up a dual-write connection between a new instance of a Finance and Operations app that has demo data and an existing instance of a model-driven app in Dynamics 365, follow the steps in the [A new Finance and Operations app instance and an existing model-driven app instance](#new-existing) section earlier in this topic.</span></span> <span data-ttu-id="778d4-145">Quando a configuração da conexão estiver concluída, para sincronizar os dados de demonstração com o aplicativo baseado em modelo, siga as etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="778d4-145">When the connection setup is completed, if you want to sync the demo data to the model-driven app, follow these steps.</span></span>

1. <span data-ttu-id="778d4-146">Abra o aplicativo do Finance and Operations na página do LCS, entre e acesse **Gerenciamento de dados \> Gravação dupla**.</span><span class="sxs-lookup"><span data-stu-id="778d4-146">Open the Finance and Operations app from the LCS page, sign in, and then go to **Data Management \> Dual-write**.</span></span>
2. <span data-ttu-id="778d4-147">Execute a funcionalidade **Sincronização inicial** para as entidades das quais você deseja sincronizar dados.</span><span class="sxs-lookup"><span data-stu-id="778d4-147">Run the **Initial sync** functionality for the entities that you want to sync data for.</span></span>

<span data-ttu-id="778d4-148">Para sincronizar os dados existentes do Common Data Service com o aplicativo do Finance and Operations, siga as etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="778d4-148">To sync the existing Common Data Service data to the Finance and Operations app, follow these steps.</span></span>

1. <span data-ttu-id="778d4-149">Crie uma empresa no aplicativo do Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="778d4-149">Create a new company in the Finance and Operations app.</span></span>
2. <span data-ttu-id="778d4-150">Adicione a empresa à configuração da conexão de gravação dupla.</span><span class="sxs-lookup"><span data-stu-id="778d4-150">Add the company to the dual-write connection setup.</span></span>
3. <span data-ttu-id="778d4-151">[Inicialize](bootstrap-company-data.md) os dados do Common Data Service usando o código de uma empresa da Organização Internacional de Normalização (ISO) com três letras.</span><span class="sxs-lookup"><span data-stu-id="778d4-151">[Bootstrap](bootstrap-company-data.md) the Common Data Service data by using a three-letter ISO company code.</span></span>

<span data-ttu-id="778d4-152">Como a gravação dupla está no modo de sincronização em tempo real, os dados do Common Data Service começam a fluir automaticamente para o aplicativo do Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="778d4-152">Because dual-write is in live synchronization mode, the data from Common Data Service automatically starts to flow to the Finance and Operations app.</span></span>

## <a name="an-existing-finance-and-operations-app-instance-and-a-new-or-existing-model-driven-app-instance"></a><a id="existing-existing"></a><span data-ttu-id="778d4-153">Uma instância existente de aplicativo do Finance and Operations e uma instância nova ou existente de aplicativo baseado em modelo</span><span class="sxs-lookup"><span data-stu-id="778d4-153">An existing Finance and Operations app instance and a new or existing model-driven app instance</span></span>

<span data-ttu-id="778d4-154">A configuração de uma conexão de gravação dupla entre uma instância existente de um aplicativo do Finance and Operations e uma instância nova ou existente de um aplicativo baseado em modelo no Dynamics 365 ocorre no ambiente do Finance and Operation.</span><span class="sxs-lookup"><span data-stu-id="778d4-154">The setup of a dual-write connection between an existing instance of a Finance and Operations app and a new or existing instance of a model-driven app in Dynamics 365 occurs in the Finance and Operation environment.</span></span>

1. <span data-ttu-id="778d4-155">Configure a conexão do aplicativo do Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="778d4-155">Set up the connection from the Finance and Operations app.</span></span>
2. <span data-ttu-id="778d4-156">Para sincronizar os dados existentes do Common Data Service com o aplicativo do Finance and Operations, [inicialize](bootstrap-company-data.md) os dados do Common Data Service usando o código de uma empresa da ISO com três letras.</span><span class="sxs-lookup"><span data-stu-id="778d4-156">To sync the existing Common Data Service data to the Finance and Operations app, [bootstrap](bootstrap-company-data.md) the Common Data Service data by using a three-letter ISO company code.</span></span>

<span data-ttu-id="778d4-157">Como a gravação dupla está no modo de sincronização em tempo real, os dados do Common Data Service começam a fluir automaticamente para o aplicativo do Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="778d4-157">Because dual-write is in live synchronization mode, the data from Common Data Service automatically starts to flow to the Finance and Operations app.</span></span>
