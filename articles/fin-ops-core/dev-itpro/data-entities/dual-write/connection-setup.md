---
title: Orientações sobre como configurar a gravação dupla
description: Este tópico descreve os cenários com suporte para configuração de gravação dupla.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 10/12/2020
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
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 2d77a1458f3f4c79b231e6a6d7cc320b8ee1fad9
ms.sourcegitcommit: ee643d651d57560bccae2f99238faa39881f5c64
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/21/2020
ms.locfileid: "4088497"
---
# <a name="guidance-for-how-to-set-up-dual-write"></a><span data-ttu-id="9704d-103">Orientações sobre como configurar a gravação dupla</span><span class="sxs-lookup"><span data-stu-id="9704d-103">Guidance for how to set up dual-write</span></span>

[!include [banner](../../includes/banner.md)]

[!include [preview-banner](../../includes/preview-banner.md)]

<span data-ttu-id="9704d-104">É possível configurar uma conexão de gravação dupla entre um ambiente do Finance and Operations e um ambiente do Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="9704d-104">You can set up a dual-write connection between a Finance and Operations environment and a Common Data Service environment.</span></span>

+ <span data-ttu-id="9704d-105">Um ambiente do **Finance and Operations** fornece a plataforma subjacente para aplicativos **Finance and Operations** (por exemplo, Microsoft Dynamics 365 Finance, Dynamics 365 Supply Chain Management e Dynamics 365 Retail).</span><span class="sxs-lookup"><span data-stu-id="9704d-105">A **Finance and Operations environment** provides the underlying platform for **Finance and Operations apps** (for example, Microsoft Dynamics 365 Finance, Dynamics 365 Supply Chain Management, and Dynamics 365 Retail).</span></span>
+ <span data-ttu-id="9704d-106">Um **ambiente do Common Data Service** fornece a plataforma subjacente para **Aplicativos do Customer Engagement** (Dynamics 365 Sales, Dynamics 365 Customer Service, Dynamics 365 Field Service, Dynamics 365 Marketing e Dynamics 365 Project Service Automation).</span><span class="sxs-lookup"><span data-stu-id="9704d-106">A **Common Data Service environment** provides the underlying platform for **customer engagement apps** (Dynamics 365 Sales, Dynamics 365 Customer Service, Dynamics 365 Field Service, Dynamics 365 Marketing, and Dynamics 365 Project Service Automation).</span></span>

>[!IMPORTANT]
><span data-ttu-id="9704d-107">Recursos humanos no Finance and Operations oferece suporte a conexões de gravação dupla, mas o aplicativo Dynamics 365 Human Resources não.</span><span class="sxs-lookup"><span data-stu-id="9704d-107">Human Resources in Finance and Operations supports dual-write connections, but the Dynamics 365 Human Resources app doesn't.</span></span>

<span data-ttu-id="9704d-108">O mecanismo de configuração varia, dependendo da sua assinatura e do ambiente.</span><span class="sxs-lookup"><span data-stu-id="9704d-108">The setup mechanism varies, depending on your subscription and the environment.</span></span>

+ <span data-ttu-id="9704d-109">Para novas instâncias de aplicativos do Finance and Operations, a configuração de uma conexão de gravação dupla começa no Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="9704d-109">For new instances of Finance and Operations apps, the setup of a dual-write connection begins in Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="9704d-110">Se você possuir uma licença para a Power Platform, receberá um novo ambiente do Common Data Service caso o locatário não tenha um.</span><span class="sxs-lookup"><span data-stu-id="9704d-110">If you have a license for Power Platform, you will get a new Common Data Service environment if your tenant doesn't have one.</span></span>
+ <span data-ttu-id="9704d-111">Para aplicativos do Finance and Operations de instâncias existentes, a configuração de uma conexão de gravação dupla começa no ambiente do Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="9704d-111">For existing instances Finance and Operations apps, the setup of a dual-write connection begins in the Finance and Operations environment.</span></span>

<span data-ttu-id="9704d-112">Antes de iniciar a gravação dupla em uma entidade, você poderá executar uma sincronização inicial para manipular dados existentes em ambos os lados de aplicativos do Finance and Operations e aplicativos do Customer Engagement.</span><span class="sxs-lookup"><span data-stu-id="9704d-112">Before you start dual-write on an entity, you can run an initial sync to handle existing data on both sides of Finance and Operations apps and customer engagement apps.</span></span> <span data-ttu-id="9704d-113">Você poderá ignorar a sincronização inicial se não precisar sincronizar dados entre os dois ambientes.</span><span class="sxs-lookup"><span data-stu-id="9704d-113">You can skip the initial sync if you don't need to synchronize data between the two environments.</span></span>

<span data-ttu-id="9704d-114">Uma sincronização inicial permite copiar dados existentes de um aplicativo para outro bidirecionalmente.</span><span class="sxs-lookup"><span data-stu-id="9704d-114">An initial sync lets you copy existing data from one app to another bidirectionally.</span></span> <span data-ttu-id="9704d-115">Há vários cenários de configuração diferentes, dependendo de quais ambientes você já tiver e que tipo de dados estiverem nos ambientes.</span><span class="sxs-lookup"><span data-stu-id="9704d-115">There are several different setup scenarios depending on which environments you already have and what type of data is in the environments.</span></span>

<span data-ttu-id="9704d-116">Há suporte para os seguintes cenários de instalação:</span><span class="sxs-lookup"><span data-stu-id="9704d-116">The following setup scenarios are supported:</span></span>

+ [<span data-ttu-id="9704d-117">Uma nova instância de aplicativo do Finance and Operations e uma nova instância de aplicativo do Customer Engagement</span><span class="sxs-lookup"><span data-stu-id="9704d-117">A new Finance and Operations app instance and a new customer engagement app instance</span></span>](#new-new)
+ [<span data-ttu-id="9704d-118">Uma nova instância de aplicativo do Finance and Operations e uma instância existente de aplicativo do Customer Engagement</span><span class="sxs-lookup"><span data-stu-id="9704d-118">A new Finance and Operations app instance and an existing customer engagement app instance</span></span>](#new-existing)
+ [<span data-ttu-id="9704d-119">Uma nova instância de aplicativo do Finance and Operations com dados e uma nova instância de aplicativo do Customer Engagement</span><span class="sxs-lookup"><span data-stu-id="9704d-119">A new Finance and Operations app instance that has data and a new customer engagement app instance</span></span>](#new-data-new)
+ [<span data-ttu-id="9704d-120">Uma nova instância de aplicativo do Finance and Operations com dados e uma instância existente de aplicativo do Customer Engagement</span><span class="sxs-lookup"><span data-stu-id="9704d-120">A new Finance and Operations app instance that has data and an existing customer engagement app instance</span></span>](#new-data-existing)
+ [<span data-ttu-id="9704d-121">Uma instância existente de aplicativo do Finance and Operations e uma instância de aplicativo do Customer Engagement</span><span class="sxs-lookup"><span data-stu-id="9704d-121">An existing Finance and Operations app instance and a new customer engagement app instance</span></span>](#existing-new)
+ [<span data-ttu-id="9704d-122">Uma instância existente de aplicativo do Finance and Operations e uma instância existente de aplicativo do Customer Engagement</span><span class="sxs-lookup"><span data-stu-id="9704d-122">An existing Finance and Operations app instance and an existing customer engagement app instance</span></span>](#existing-existing)

## <a name="a-new-finance-and-operations-app-instance-and-a-new-customer-engagement-app-instance"></a><a id="new-new"></a><span data-ttu-id="9704d-123">Uma nova instância de aplicativo do Finance and Operations e uma nova instância de aplicativo do Customer Engagement</span><span class="sxs-lookup"><span data-stu-id="9704d-123">A new Finance and Operations app instance and a new customer engagement app instance</span></span>

<span data-ttu-id="9704d-124">Para configurar uma conexão de gravação dupla entre uma nova instância de um aplicativo do Finance and Operations que não possui dados e uma nova instância de um aplicativo do Customer Engagement, siga as etapas em [Configuração de gravação dupla do Lifecycle Services](lcs-setup.md).</span><span class="sxs-lookup"><span data-stu-id="9704d-124">To set up a dual-write connection between a new instance of a Finance and Operations app that has no data and a new instance of a customer engagement app, follow the steps in [Dual-write setup from Lifecycle Services](lcs-setup.md).</span></span> <span data-ttu-id="9704d-125">Quando a configuração da conexão é concluída, as seguintes ações ocorrem automaticamente:</span><span class="sxs-lookup"><span data-stu-id="9704d-125">When the connection setup is completed, the following actions occur automatically:</span></span>

- <span data-ttu-id="9704d-126">Um novo ambiente vazio do Finance and Operations é provisionado.</span><span class="sxs-lookup"><span data-stu-id="9704d-126">A new, empty Finance and Operations environment is provisioned.</span></span>
- <span data-ttu-id="9704d-127">É provisionada uma nova instância vazia de um aplicativo do Customer Engagement, em que a solução principal do CRM está instalada.</span><span class="sxs-lookup"><span data-stu-id="9704d-127">A new, empty instance of a customer engagement app is provisioned, where the CRM prime solution is installed.</span></span>
- <span data-ttu-id="9704d-128">Uma conexão de gravação dupla é estabelecida para os dados da empresa DAT.</span><span class="sxs-lookup"><span data-stu-id="9704d-128">A dual-write connection is established for DAT company data.</span></span>
- <span data-ttu-id="9704d-129">Os mapas de entidade estão habilitados para sincronização em tempo real.</span><span class="sxs-lookup"><span data-stu-id="9704d-129">Entity maps are enabled for live synchronization.</span></span>

<span data-ttu-id="9704d-130">Ambos os ambientes estão prontos para sincronização de dados em tempo real.</span><span class="sxs-lookup"><span data-stu-id="9704d-130">Both environments are then ready for live data synchronization.</span></span>

## <a name="a-new-finance-and-operations-app-instance-and-an-existing-customer-engagement-app-instance"></a><a id="new-existing"></a><span data-ttu-id="9704d-131">Uma nova instância de aplicativo do Finance and Operations e uma instância existente de aplicativo do Customer Engagement</span><span class="sxs-lookup"><span data-stu-id="9704d-131">A new Finance and Operations app instance and an existing customer engagement app instance</span></span>

<span data-ttu-id="9704d-132">Para configurar uma conexão de gravação dupla entre uma nova instância de um aplicativo do Finance and Operations que não possui dados e uma instância existente de um aplicativo do Customer Engagement, siga as etapas em [Configuração de gravação dupla do Lifecycle Services](lcs-setup.md).</span><span class="sxs-lookup"><span data-stu-id="9704d-132">To set up a dual-write connection between a new instance of a Finance and Operations app that has no data and an existing instance of a customer engagement app, follow the steps in [Dual-write setup from Lifecycle Services](lcs-setup.md).</span></span> <span data-ttu-id="9704d-133">Quando a configuração da conexão é concluída, as seguintes ações ocorrem automaticamente:</span><span class="sxs-lookup"><span data-stu-id="9704d-133">When the connection setup is completed, the following actions occur automatically:</span></span>

- <span data-ttu-id="9704d-134">Um novo ambiente vazio do Finance and Operations é provisionado.</span><span class="sxs-lookup"><span data-stu-id="9704d-134">A new, empty Finance and Operations environment is provisioned.</span></span>
- <span data-ttu-id="9704d-135">Uma conexão de gravação dupla é estabelecida para os dados da empresa DAT.</span><span class="sxs-lookup"><span data-stu-id="9704d-135">A dual-write connection is established for DAT company data.</span></span>
- <span data-ttu-id="9704d-136">Os mapas de entidade estão habilitados para sincronização em tempo real.</span><span class="sxs-lookup"><span data-stu-id="9704d-136">Entity maps are enabled for live synchronization.</span></span>

<span data-ttu-id="9704d-137">Ambos os ambientes estão prontos para sincronização de dados em tempo real.</span><span class="sxs-lookup"><span data-stu-id="9704d-137">Both environments are then ready for live data synchronization.</span></span>

<span data-ttu-id="9704d-138">Para sincronizar os dados existentes do Common Data Service com o aplicativo do Finance and Operations, siga as etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="9704d-138">To sync the existing Common Data Service data to the Finance and Operations app, follow these steps.</span></span>

1. <span data-ttu-id="9704d-139">Crie uma empresa no aplicativo do Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="9704d-139">Create a new company in the Finance and Operations app.</span></span>
2. <span data-ttu-id="9704d-140">Adicione a empresa à configuração da conexão de gravação dupla.</span><span class="sxs-lookup"><span data-stu-id="9704d-140">Add the company to the dual-write connection setup.</span></span>
3. <span data-ttu-id="9704d-141">[Inicialize](bootstrap-company-data.md) os dados do Common Data Service usando o código de uma empresa da Organização Internacional de Normalização (ISO) com três letras.</span><span class="sxs-lookup"><span data-stu-id="9704d-141">[Bootstrap](bootstrap-company-data.md) the Common Data Service data by using a three-letter International Organization for Standardization (ISO) company code.</span></span>
4. <span data-ttu-id="9704d-142">Execute a funcionalidade **Sincronização inicial** para as entidades das quais você deseja sincronizar dados.</span><span class="sxs-lookup"><span data-stu-id="9704d-142">Run the **Initial sync** functionality for the entities that you want to sync data for.</span></span>

<span data-ttu-id="9704d-143">Para obter um exemplo e uma abordagem alternativa, consulte [Exemplo](#example).</span><span class="sxs-lookup"><span data-stu-id="9704d-143">For an example and alternative approach, see [Example](#example).</span></span>

## <a name="a-new-finance-and-operations-app-instance-that-has-data-and-a-new-customer-engagement-app-instance"></a><a id="new-data-new"></a><span data-ttu-id="9704d-144">Uma nova instância de aplicativo do Finance and Operations com dados e uma nova instância de aplicativo do Customer Engagement</span><span class="sxs-lookup"><span data-stu-id="9704d-144">A new Finance and Operations app instance that has data and a new customer engagement app instance</span></span>

<span data-ttu-id="9704d-145">Para configurar uma conexão de gravação dupla entre uma nova instância de um aplicativo do Finance and Operations com dados de demonstração e uma nova instância de um aplicativo do Customer Engagement, siga as etapas na seção [Uma nova instância de aplicativo do Finance and Operations e uma nova instância de aplicativo do Customer Engagement](#new-new), anteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="9704d-145">To set up a dual-write connection between a new instance of a Finance and Operations app that has data and a new instance of a customer engagement app, follow the steps in the [A new Finance and Operations app instance and a new customer engagement app instance](#new-new) section earlier in this topic.</span></span> <span data-ttu-id="9704d-146">Quando a configuração da conexão estiver concluída, para sincronizar os dados com o aplicativo do Customer Engagement, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="9704d-146">When the connection setup is completed, if you want to sync the data to the customer engagement app, follow these steps.</span></span>

1. <span data-ttu-id="9704d-147">Abra o aplicativo do Finance and Operations na página do LCS, entre e acesse **Gerenciamento de dados \> Gravação dupla**.</span><span class="sxs-lookup"><span data-stu-id="9704d-147">Open the Finance and Operations app from the LCS page, sign in, and then go to **Data Management \> Dual-write**.</span></span>
2. <span data-ttu-id="9704d-148">Execute a funcionalidade **Sincronização inicial** para as entidades das quais você deseja sincronizar dados.</span><span class="sxs-lookup"><span data-stu-id="9704d-148">Run the **Initial sync** functionality for the entities that you want to sync data for.</span></span>

<span data-ttu-id="9704d-149">Para obter um exemplo e uma abordagem alternativa, consulte [Exemplo](#example).</span><span class="sxs-lookup"><span data-stu-id="9704d-149">For an example and alternative approach, see [Example](#example).</span></span>

## <a name="a-new-finance-and-operations-app-instance-that-has-data-and-an-existing-customer-engagement-app-instance"></a><a id="new-data-existing"></a><span data-ttu-id="9704d-150">Uma nova instância de aplicativo do Finance and Operations com dados e uma instância existente de aplicativo do Customer Engagement</span><span class="sxs-lookup"><span data-stu-id="9704d-150">A new Finance and Operations app instance that has data and an existing customer engagement app instance</span></span>

<span data-ttu-id="9704d-151">Para configurar uma conexão de gravação dupla entre uma nova instância de um aplicativo do Finance and Operations com dados de demonstração e uma instância existente de um aplicativo do Customer Engagement, siga as etapas na seção [Uma nova instância de aplicativo do Finance and Operations e uma instância existente de aplicativo do Customer Engagement](#new-existing), anteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="9704d-151">To set up a dual-write connection between a new instance of a Finance and Operations app that has data and an existing instance of a customer engagement app, follow the steps in the [A new Finance and Operations app instance and an existing customer engagement app instance](#new-existing) section earlier in this topic.</span></span> <span data-ttu-id="9704d-152">Quando a configuração da conexão estiver concluída, para sincronizar os dados com o aplicativo do Customer Engagement, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="9704d-152">When the connection setup is completed, if you want to sync the data to the customer engagement app, follow these steps.</span></span>

1. <span data-ttu-id="9704d-153">Abra o aplicativo do Finance and Operations na página do LCS, entre e acesse **Gerenciamento de dados \> Gravação dupla**.</span><span class="sxs-lookup"><span data-stu-id="9704d-153">Open the Finance and Operations app from the LCS page, sign in, and then go to **Data Management \> Dual-write**.</span></span>
2. <span data-ttu-id="9704d-154">Execute a funcionalidade **Sincronização inicial** para as entidades das quais você deseja sincronizar dados.</span><span class="sxs-lookup"><span data-stu-id="9704d-154">Run the **Initial sync** functionality for the entities that you want to sync data for.</span></span>

<span data-ttu-id="9704d-155">Para sincronizar os dados existentes do Common Data Service com o aplicativo do Finance and Operations, siga as etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="9704d-155">To sync the existing Common Data Service data to the Finance and Operations app, follow these steps.</span></span>

1. <span data-ttu-id="9704d-156">Crie uma empresa no aplicativo do Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="9704d-156">Create a new company in the Finance and Operations app.</span></span>
2. <span data-ttu-id="9704d-157">Adicione a empresa à configuração da conexão de gravação dupla.</span><span class="sxs-lookup"><span data-stu-id="9704d-157">Add the company to the dual-write connection setup.</span></span>
3. <span data-ttu-id="9704d-158">[Inicialize](bootstrap-company-data.md) os dados do Common Data Service usando o código de uma empresa da Organização Internacional de Normalização (ISO) com três letras.</span><span class="sxs-lookup"><span data-stu-id="9704d-158">[Bootstrap](bootstrap-company-data.md) the Common Data Service data by using a three-letter ISO company code.</span></span>
4. <span data-ttu-id="9704d-159">Execute a funcionalidade **Sincronização inicial** para as entidades das quais você deseja sincronizar dados.</span><span class="sxs-lookup"><span data-stu-id="9704d-159">Run the **Initial sync** functionality for the entities that you want to sync data for.</span></span>

<span data-ttu-id="9704d-160">Para obter um exemplo e uma abordagem alternativa, consulte [Exemplo](#example).</span><span class="sxs-lookup"><span data-stu-id="9704d-160">For an example and alternative approach, see [Example](#example).</span></span>

## <a name="an-existing-finance-and-operations-app-instance-and-a-new-customer-engagement-app-instance"></a><a id="existing-new"></a><span data-ttu-id="9704d-161">Uma instância existente de aplicativo do Finance and Operations e uma nova instância de aplicativo do Customer Engagement</span><span class="sxs-lookup"><span data-stu-id="9704d-161">An existing Finance and Operations app instance and a new customer engagement app instance</span></span>

<span data-ttu-id="9704d-162">A configuração de uma conexão de gravação dupla entre uma instância existente de um aplicativo do Finance and Operations e uma nova instância de um aplicativo do Customer Engagement ocorre no ambiente do Finance and Operation.</span><span class="sxs-lookup"><span data-stu-id="9704d-162">The setup of a dual-write connection between an existing instance of a Finance and Operations app and a new instance of a customer engagement app occurs in the Finance and Operation environment.</span></span>

1. <span data-ttu-id="9704d-163">[Configurar a conexão do aplicativo do Finance and Operations](enable-dual-write.md).</span><span class="sxs-lookup"><span data-stu-id="9704d-163">[Set up the connection from the Finance and Operations app](enable-dual-write.md).</span></span>
2. <span data-ttu-id="9704d-164">Execute a funcionalidade **Sincronização inicial** para as entidades das quais você deseja sincronizar dados.</span><span class="sxs-lookup"><span data-stu-id="9704d-164">Run the **Initial sync** functionality for the entities that you want to sync data for.</span></span>

<span data-ttu-id="9704d-165">Para obter um exemplo e uma abordagem alternativa, consulte [Exemplo](#example).</span><span class="sxs-lookup"><span data-stu-id="9704d-165">For an example and alternative approach, see [Example](#example).</span></span>

## <a name="an-existing-finance-and-operations-app-instance-and-an-existing-customer-engagement-app-instance"></a><a id="existing-existing"></a><span data-ttu-id="9704d-166">Uma instância existente de aplicativo do Finance and Operations e uma instância existente de aplicativo do Customer Engagement</span><span class="sxs-lookup"><span data-stu-id="9704d-166">An existing Finance and Operations app instance and an existing customer engagement app instance</span></span>

<span data-ttu-id="9704d-167">A configuração de uma conexão de gravação dupla entre uma instância existente de um aplicativo do Finance and Operations e uma instância existente de um aplicativo do Customer Engagement ocorre no ambiente do Finance and Operation.</span><span class="sxs-lookup"><span data-stu-id="9704d-167">The setup of a dual-write connection between an existing instance of a Finance and Operations app and an existing instance of a customer engagement app  occurs in the Finance and Operation environment.</span></span>

1. <span data-ttu-id="9704d-168">Configure a conexão do aplicativo do Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="9704d-168">Set up the connection from the Finance and Operations app.</span></span>
2. <span data-ttu-id="9704d-169">Para sincronizar os dados existentes do Common Data Service com o aplicativo do Finance and Operations, [inicialize](bootstrap-company-data.md) os dados do Common Data Service usando o código de uma empresa da ISO com três letras.</span><span class="sxs-lookup"><span data-stu-id="9704d-169">To sync the existing Common Data Service data to the Finance and Operations app, [bootstrap](bootstrap-company-data.md) the Common Data Service data by using a three-letter ISO company code.</span></span>
3. <span data-ttu-id="9704d-170">Execute a funcionalidade **Sincronização inicial** para as entidades das quais você deseja sincronizar dados.</span><span class="sxs-lookup"><span data-stu-id="9704d-170">Run the **Initial sync** functionality for the entities that you want to sync data for.</span></span>

<span data-ttu-id="9704d-171">Para obter um exemplo e uma abordagem alternativa, consulte [Exemplo](#example).</span><span class="sxs-lookup"><span data-stu-id="9704d-171">For an example and alternative approach, see [Example](#example).</span></span>

## <a name="example"></a><span data-ttu-id="9704d-172">Exemplo</span><span class="sxs-lookup"><span data-stu-id="9704d-172">Example</span></span>

<span data-ttu-id="9704d-173">Para obter um exemplo, consulte [Como habilitar Customers V3 — Mapa de entidades de contato](enable-entity-map.md#example-enabling-the-customers-v3contacts-entity-map)</span><span class="sxs-lookup"><span data-stu-id="9704d-173">For an example, see [Enabling the Customers V3—Contacts entity map](enable-entity-map.md#example-enabling-the-customers-v3contacts-entity-map)</span></span>

<span data-ttu-id="9704d-174">Para obter uma abordagem alternativa baseada em volumes de dados em cada entidade que precise executar a sincronização inicial, consulte [Considerações sobre a sincronização inicial](initial-sync-guidance.md).</span><span class="sxs-lookup"><span data-stu-id="9704d-174">For an alternative approach based on data volumes in each entity that need to run initial sync, see [Considerations for initial synchronization](initial-sync-guidance.md).</span></span>
