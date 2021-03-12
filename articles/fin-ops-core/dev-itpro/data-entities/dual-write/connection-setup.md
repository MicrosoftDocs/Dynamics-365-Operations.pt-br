---
title: Orientações sobre configuração da gravação dupla
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
ms.openlocfilehash: 78a7cdc18476a1c523c83c92ca6f354c3ba806dc
ms.sourcegitcommit: 7e1be696894731e1c58074d9b5e9c5b3acf7e52a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/17/2020
ms.locfileid: "4744844"
---
# <a name="guidance-for-dual-write-setup"></a><span data-ttu-id="c9750-103">Orientações sobre configuração da gravação dupla</span><span class="sxs-lookup"><span data-stu-id="c9750-103">Guidance for dual-write setup</span></span>

[!include [banner](../../includes/banner.md)]

[!include [preview-banner](../../includes/preview-banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="c9750-104">É possível configurar uma conexão de gravação dupla entre um ambiente do Finance and Operations e um ambiente do Dataverse.</span><span class="sxs-lookup"><span data-stu-id="c9750-104">You can set up a dual-write connection between a Finance and Operations environment and a Dataverse environment.</span></span>

+ <span data-ttu-id="c9750-105">Um **ambiente do Finance and Operations** fornece a plataforma subjacente para **aplicativos do Finance and Operations** (por exemplo, Microsoft Dynamics 365 Finance, Dynamics 365 Supply Chain Management, Dynamics 365 Commerce e Dynamics 365 Human Resources).</span><span class="sxs-lookup"><span data-stu-id="c9750-105">A **Finance and Operations environment** provides the underlying platform for **Finance and Operations apps** (for example, Microsoft Dynamics 365 Finance, Dynamics 365 Supply Chain Management, Dynamics 365 Commerce, and Dynamics 365 Human Resources).</span></span>
+ <span data-ttu-id="c9750-106">Um **ambiente do Dataverse** fornece a plataforma subjacente para **aplicativos do Customer Engagement** (Dynamics 365 Sales, Dynamics 365 Customer Service, Dynamics 365 column Service, Dynamics 365 Marketing e Dynamics 365 Project Service Automation).</span><span class="sxs-lookup"><span data-stu-id="c9750-106">A **Dataverse environment** provides the underlying platform for **customer engagement apps** (Dynamics 365 Sales, Dynamics 365 Customer Service, Dynamics 365 column Service, Dynamics 365 Marketing, and Dynamics 365 Project Service Automation).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c9750-107">O módulo de recursos humanos no Dynamics 365 Finance oferece suporte a conexões de gravação dupla, mas o aplicativo Dynamics 365 Human Resources não.</span><span class="sxs-lookup"><span data-stu-id="c9750-107">The Human Resources module in Dynamics 365 Finance supports dual-write connections, but the Dynamics 365 Human Resources app doesn't.</span></span>

<span data-ttu-id="c9750-108">O mecanismo de configuração varia, dependendo da sua assinatura e do ambiente:</span><span class="sxs-lookup"><span data-stu-id="c9750-108">The setup mechanism varies, depending on your subscription and the environment:</span></span>

+ <span data-ttu-id="c9750-109">Para novas instâncias de aplicativos do Finance and Operations, a configuração de uma conexão de gravação dupla começa no Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="c9750-109">For new instances of Finance and Operations apps, the setup of a dual-write connection begins in Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="c9750-110">Se você possuir uma licença para a Microsoft Power Platform, receberá um novo ambiente do Dataverse caso o locatário não tenha um.</span><span class="sxs-lookup"><span data-stu-id="c9750-110">If you have a license for Microsoft Power Platform, you will get a new Dataverse environment if your tenant doesn't have one.</span></span>
+ <span data-ttu-id="c9750-111">Para aplicativos do Finance and Operations de instâncias existentes, a configuração de uma conexão de gravação dupla começa no ambiente do Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="c9750-111">For existing instances Finance and Operations apps, the setup of a dual-write connection begins in the Finance and Operations environment.</span></span>

<span data-ttu-id="c9750-112">Antes de iniciar a gravação dupla em uma entidade, você poderá executar uma sincronização inicial para manipular dados existentes em ambos os lados: aplicativos do Finance and Operations e aplicativos do Customer Engagement.</span><span class="sxs-lookup"><span data-stu-id="c9750-112">Before you start dual-write on an entity, you can run an initial synchronization to handle existing data on both sides: Finance and Operations apps and customer engagement apps.</span></span> <span data-ttu-id="c9750-113">Você poderá ignorar a sincronização inicial se não precisar sincronizar dados entre os dois ambientes.</span><span class="sxs-lookup"><span data-stu-id="c9750-113">You can skip the initial synchronization if you don't have to sync data between the two environments.</span></span>

<span data-ttu-id="c9750-114">Uma sincronização inicial permite copiar dados existentes de um aplicativo para outro bidirecionalmente.</span><span class="sxs-lookup"><span data-stu-id="c9750-114">An initial synchronization lets you copy existing data from one app to another bidirectionally.</span></span> <span data-ttu-id="c9750-115">Há vários cenários de configuração, dependendo do ambiente que você já tiver e que tipo de dados existirem neles.</span><span class="sxs-lookup"><span data-stu-id="c9750-115">There are several setup scenarios, depending on the environments that you already have and the type of data in them.</span></span>

<span data-ttu-id="c9750-116">Há suporte para os seguintes cenários de instalação:</span><span class="sxs-lookup"><span data-stu-id="c9750-116">The following setup scenarios are supported:</span></span>

+ [<span data-ttu-id="c9750-117">Uma nova instância de aplicativo do Finance and Operations e uma nova instância de aplicativo do Customer Engagement</span><span class="sxs-lookup"><span data-stu-id="c9750-117">A new Finance and Operations app instance and a new customer engagement app instance</span></span>](#new-new)
+ [<span data-ttu-id="c9750-118">Uma nova instância de aplicativo do Finance and Operations e uma instância existente de aplicativo do Customer Engagement</span><span class="sxs-lookup"><span data-stu-id="c9750-118">A new Finance and Operations app instance and an existing customer engagement app instance</span></span>](#new-existing)
+ [<span data-ttu-id="c9750-119">Uma nova instância de aplicativo do Finance and Operations com dados e uma nova instância de aplicativo do Customer Engagement</span><span class="sxs-lookup"><span data-stu-id="c9750-119">A new Finance and Operations app instance that has data and a new customer engagement app instance</span></span>](#new-data-new)
+ [<span data-ttu-id="c9750-120">Uma nova instância de aplicativo do Finance and Operations com dados e uma instância existente de aplicativo do Customer Engagement</span><span class="sxs-lookup"><span data-stu-id="c9750-120">A new Finance and Operations app instance that has data and an existing customer engagement app instance</span></span>](#new-data-existing)
+ [<span data-ttu-id="c9750-121">Uma instância existente de aplicativo do Finance and Operations e uma instância de aplicativo do Customer Engagement</span><span class="sxs-lookup"><span data-stu-id="c9750-121">An existing Finance and Operations app instance and a new customer engagement app instance</span></span>](#existing-new)
+ [<span data-ttu-id="c9750-122">Uma instância existente de aplicativo do Finance and Operations e uma instância existente de aplicativo do Customer Engagement</span><span class="sxs-lookup"><span data-stu-id="c9750-122">An existing Finance and Operations app instance and an existing customer engagement app instance</span></span>](#existing-existing)

## <a name="a-new-finance-and-operations-app-instance-and-a-new-customer-engagement-app-instance"></a><a id="new-new"></a><span data-ttu-id="c9750-123">Uma nova instância de aplicativo do Finance and Operations e uma nova instância de aplicativo do Customer Engagement</span><span class="sxs-lookup"><span data-stu-id="c9750-123">A new Finance and Operations app instance and a new customer engagement app instance</span></span>

<span data-ttu-id="c9750-124">Para configurar uma conexão de gravação dupla entre uma nova instância de um aplicativo do Finance and Operations que não possui dados e uma nova instância de um aplicativo do Customer Engagement, siga as etapas em [Configuração de gravação dupla do Lifecycle Services](lcs-setup.md).</span><span class="sxs-lookup"><span data-stu-id="c9750-124">To set up a dual-write connection between a new instance of a Finance and Operations app that has no data and a new instance of a customer engagement app, follow the steps in [Dual-write setup from Lifecycle Services](lcs-setup.md).</span></span> <span data-ttu-id="c9750-125">Quando a configuração da conexão é concluída, as seguintes ações ocorrem automaticamente:</span><span class="sxs-lookup"><span data-stu-id="c9750-125">When the connection setup is completed, the following actions automatically occur:</span></span>

- <span data-ttu-id="c9750-126">Um novo ambiente vazio do Finance and Operations é provisionado.</span><span class="sxs-lookup"><span data-stu-id="c9750-126">A new, empty Finance and Operations environment is provisioned.</span></span>
- <span data-ttu-id="c9750-127">É provisionada uma nova instância vazia de um aplicativo do Customer Engagement, em que a solução principal do CRM está instalada.</span><span class="sxs-lookup"><span data-stu-id="c9750-127">A new, empty instance of a customer engagement app is provisioned, where the CRM prime solution is installed.</span></span>
- <span data-ttu-id="c9750-128">Uma conexão de gravação dupla é estabelecida para os dados da empresa DAT.</span><span class="sxs-lookup"><span data-stu-id="c9750-128">A dual-write connection is established for DAT company data.</span></span>
- <span data-ttu-id="c9750-129">Os mapas de tabela estão habilitados para sincronização em tempo real.</span><span class="sxs-lookup"><span data-stu-id="c9750-129">Table maps are enabled for live synchronization.</span></span>

<span data-ttu-id="c9750-130">Ambos os ambientes estão prontos para sincronização de dados em tempo real.</span><span class="sxs-lookup"><span data-stu-id="c9750-130">Both environments are then ready for live data synchronization.</span></span>

## <a name="a-new-finance-and-operations-app-instance-and-an-existing-customer-engagement-app-instance"></a><a id="new-existing"></a><span data-ttu-id="c9750-131">Uma nova instância de aplicativo do Finance and Operations e uma instância existente de aplicativo do Customer Engagement</span><span class="sxs-lookup"><span data-stu-id="c9750-131">A new Finance and Operations app instance and an existing customer engagement app instance</span></span>

<span data-ttu-id="c9750-132">Para configurar uma conexão de gravação dupla entre uma nova instância de um aplicativo do Finance and Operations que não possui dados e uma instância existente de um aplicativo do Customer Engagement, siga as etapas em [Configuração de gravação dupla do Lifecycle Services](lcs-setup.md).</span><span class="sxs-lookup"><span data-stu-id="c9750-132">To set up a dual-write connection between a new instance of a Finance and Operations app that has no data and an existing instance of a customer engagement app, follow the steps in [Dual-write setup from Lifecycle Services](lcs-setup.md).</span></span> <span data-ttu-id="c9750-133">Quando a configuração da conexão é concluída, as seguintes ações ocorrem automaticamente:</span><span class="sxs-lookup"><span data-stu-id="c9750-133">When the connection setup is completed, the following actions automatically occur:</span></span>

- <span data-ttu-id="c9750-134">Um novo ambiente vazio do Finance and Operations é provisionado.</span><span class="sxs-lookup"><span data-stu-id="c9750-134">A new, empty Finance and Operations environment is provisioned.</span></span>
- <span data-ttu-id="c9750-135">Uma conexão de gravação dupla é estabelecida para os dados da empresa DAT.</span><span class="sxs-lookup"><span data-stu-id="c9750-135">A dual-write connection is established for DAT company data.</span></span>
- <span data-ttu-id="c9750-136">Os mapas de tabela estão habilitados para sincronização em tempo real.</span><span class="sxs-lookup"><span data-stu-id="c9750-136">Table maps are enabled for live synchronization.</span></span>

<span data-ttu-id="c9750-137">Ambos os ambientes estão prontos para sincronização de dados em tempo real.</span><span class="sxs-lookup"><span data-stu-id="c9750-137">Both environments are then ready for live data synchronization.</span></span>

<span data-ttu-id="c9750-138">Para sincronizar os dados existentes do Dataverse com o aplicativo do Finance and Operations, siga as etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="c9750-138">To sync the existing Dataverse data to the Finance and Operations app, follow these steps.</span></span>

1. <span data-ttu-id="c9750-139">Crie uma empresa no aplicativo do Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="c9750-139">Create a new company in the Finance and Operations app.</span></span>
2. <span data-ttu-id="c9750-140">Adicione a empresa à configuração da conexão de gravação dupla.</span><span class="sxs-lookup"><span data-stu-id="c9750-140">Add the company to the dual-write connection setup.</span></span>
3. <span data-ttu-id="c9750-141">[Inicialize](bootstrap-company-data.md) os dados do Dataverse usando o código de uma empresa da Organização Internacional de Normalização (ISO) com três letras.</span><span class="sxs-lookup"><span data-stu-id="c9750-141">[Bootstrap](bootstrap-company-data.md) the Dataverse data by using a three-letter International Organization for Standardization (ISO) company code.</span></span>
4. <span data-ttu-id="c9750-142">Execute a funcionalidade **Sincronização inicial** para as tabelas das quais você deseja sincronizar dados.</span><span class="sxs-lookup"><span data-stu-id="c9750-142">Run the **Initial sync** functionality for the tables that you want to sync data for.</span></span>

<span data-ttu-id="c9750-143">Para obter links para um exemplo e uma abordagem alternativa, consulte a seção [Exemplo](#example) posteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="c9750-143">For links to an example and an alternative approach, see the [Example](#example) section later in this topic.</span></span>

## <a name="a-new-finance-and-operations-app-instance-that-has-data-and-a-new-customer-engagement-app-instance"></a><a id="new-data-new"></a><span data-ttu-id="c9750-144">Uma nova instância de aplicativo do Finance and Operations com dados e uma nova instância de aplicativo do Customer Engagement</span><span class="sxs-lookup"><span data-stu-id="c9750-144">A new Finance and Operations app instance that has data and a new customer engagement app instance</span></span>

<span data-ttu-id="c9750-145">Para configurar uma conexão de gravação dupla entre uma nova instância de um aplicativo do Finance and Operations com dados de demonstração e uma nova instância de um aplicativo do Customer Engagement, siga as etapas na seção [Uma nova instância de aplicativo do Finance and Operations e uma nova instância de aplicativo do Customer Engagement](#new-new), anteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="c9750-145">To set up a dual-write connection between a new instance of a Finance and Operations app that has data and a new instance of a customer engagement app, follow the steps in the [A new Finance and Operations app instance and a new customer engagement app instance](#new-new) section earlier in this topic.</span></span> <span data-ttu-id="c9750-146">Quando a configuração da conexão estiver concluída, para sincronizar os dados com o aplicativo do Customer Engagement, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="c9750-146">When the connection setup is completed, if you want to sync the data to the customer engagement app, follow these steps.</span></span>

1. <span data-ttu-id="c9750-147">Abra o aplicativo do Finance and Operations na página do LCS, entre e acesse **Gerenciamento de dados \> Gravação dupla**.</span><span class="sxs-lookup"><span data-stu-id="c9750-147">Open the Finance and Operations app from the LCS page, sign in, and then go to **Data Management \> Dual-write**.</span></span>
2. <span data-ttu-id="c9750-148">Execute a funcionalidade **Sincronização inicial** para as tabelas das quais você deseja sincronizar dados.</span><span class="sxs-lookup"><span data-stu-id="c9750-148">Run the **Initial sync** functionality for the tables that you want to sync data for.</span></span>

<span data-ttu-id="c9750-149">Para obter links para um exemplo e uma abordagem alternativa, consulte a seção [Exemplo](#example).</span><span class="sxs-lookup"><span data-stu-id="c9750-149">For links to an example and an alternative approach, see the [Example](#example) section.</span></span>

## <a name="a-new-finance-and-operations-app-instance-that-has-data-and-an-existing-customer-engagement-app-instance"></a><a id="new-data-existing"></a><span data-ttu-id="c9750-150">Uma nova instância de aplicativo do Finance and Operations com dados e uma instância existente de aplicativo do Customer Engagement</span><span class="sxs-lookup"><span data-stu-id="c9750-150">A new Finance and Operations app instance that has data and an existing customer engagement app instance</span></span>

<span data-ttu-id="c9750-151">Para configurar uma conexão de gravação dupla entre uma nova instância de um aplicativo do Finance and Operations com dados de demonstração e uma instância existente de um aplicativo do Customer Engagement, siga as etapas na seção [Uma nova instância de aplicativo do Finance and Operations e uma instância existente de aplicativo do Customer Engagement](#new-existing), anteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="c9750-151">To set up a dual-write connection between a new instance of a Finance and Operations app that has data and an existing instance of a customer engagement app, follow the steps in the [A new Finance and Operations app instance and an existing customer engagement app instance](#new-existing) section earlier in this topic.</span></span> <span data-ttu-id="c9750-152">Quando a configuração da conexão estiver concluída, para sincronizar os dados com o aplicativo do Customer Engagement, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="c9750-152">When the connection setup is completed, if you want to sync the data to the customer engagement app, follow these steps.</span></span>

1. <span data-ttu-id="c9750-153">Abra o aplicativo do Finance and Operations na página do LCS, entre e acesse **Gerenciamento de dados \> Gravação dupla**.</span><span class="sxs-lookup"><span data-stu-id="c9750-153">Open the Finance and Operations app from the LCS page, sign in, and then go to **Data Management \> Dual-write**.</span></span>
2. <span data-ttu-id="c9750-154">Execute a funcionalidade **Sincronização inicial** para as tabelas das quais você deseja sincronizar dados.</span><span class="sxs-lookup"><span data-stu-id="c9750-154">Run the **Initial sync** functionality for the tables that you want to sync data for.</span></span>

<span data-ttu-id="c9750-155">Para sincronizar os dados existentes do Dataverse com o aplicativo do Finance and Operations, siga as etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="c9750-155">To sync the existing Dataverse data to the Finance and Operations app, follow these steps.</span></span>

1. <span data-ttu-id="c9750-156">Crie uma empresa no aplicativo do Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="c9750-156">Create a new company in the Finance and Operations app.</span></span>
2. <span data-ttu-id="c9750-157">Adicione a empresa à configuração da conexão de gravação dupla.</span><span class="sxs-lookup"><span data-stu-id="c9750-157">Add the company to the dual-write connection setup.</span></span>
3. <span data-ttu-id="c9750-158">[Inicialize](bootstrap-company-data.md) os dados do Dataverse usando o código de uma empresa da Organização Internacional de Normalização (ISO) com três letras.</span><span class="sxs-lookup"><span data-stu-id="c9750-158">[Bootstrap](bootstrap-company-data.md) the Dataverse data by using a three-letter ISO company code.</span></span>
4. <span data-ttu-id="c9750-159">Execute a funcionalidade **Sincronização inicial** para as tabelas das quais você deseja sincronizar dados.</span><span class="sxs-lookup"><span data-stu-id="c9750-159">Run the **Initial sync** functionality for the tables that you want to sync data for.</span></span>

<span data-ttu-id="c9750-160">Para obter links para um exemplo e uma abordagem alternativa, consulte a seção [Exemplo](#example).</span><span class="sxs-lookup"><span data-stu-id="c9750-160">For links to an example and an alternative approach, see the [Example](#example) section.</span></span>

## <a name="an-existing-finance-and-operations-app-instance-and-a-new-customer-engagement-app-instance"></a><a id="existing-new"></a><span data-ttu-id="c9750-161">Uma instância existente de aplicativo do Finance and Operations e uma nova instância de aplicativo do Customer Engagement</span><span class="sxs-lookup"><span data-stu-id="c9750-161">An existing Finance and Operations app instance and a new customer engagement app instance</span></span>

<span data-ttu-id="c9750-162">A configuração de uma conexão de gravação dupla entre uma instância existente de um aplicativo do Finance and Operations e uma nova instância de um aplicativo do Customer Engagement ocorre no ambiente do Finance and Operation.</span><span class="sxs-lookup"><span data-stu-id="c9750-162">The setup of a dual-write connection between an existing instance of a Finance and Operations app and a new instance of a customer engagement app occurs in the Finance and Operation environment.</span></span>

1. <span data-ttu-id="c9750-163">[Configurar a conexão do aplicativo do Finance and Operations](enable-dual-write.md).</span><span class="sxs-lookup"><span data-stu-id="c9750-163">[Set up the connection from the Finance and Operations app](enable-dual-write.md).</span></span>
2. <span data-ttu-id="c9750-164">Execute a funcionalidade **Sincronização inicial** para as tabelas das quais você deseja sincronizar dados.</span><span class="sxs-lookup"><span data-stu-id="c9750-164">Run the **Initial sync** functionality for the tables that you want to sync data for.</span></span>

<span data-ttu-id="c9750-165">Para obter links para um exemplo e uma abordagem alternativa, consulte a seção [Exemplo](#example).</span><span class="sxs-lookup"><span data-stu-id="c9750-165">For links to an example and an alternative approach, see the [Example](#example) section.</span></span>

## <a name="an-existing-finance-and-operations-app-instance-and-an-existing-customer-engagement-app-instance"></a><a id="existing-existing"></a><span data-ttu-id="c9750-166">Uma instância existente de aplicativo do Finance and Operations e uma instância existente de aplicativo do Customer Engagement</span><span class="sxs-lookup"><span data-stu-id="c9750-166">An existing Finance and Operations app instance and an existing customer engagement app instance</span></span>

<span data-ttu-id="c9750-167">A configuração de uma conexão de gravação dupla entre uma instância existente de um aplicativo do Finance and Operations e uma instância existente de um aplicativo do Customer Engagement ocorre no ambiente do Finance and Operation.</span><span class="sxs-lookup"><span data-stu-id="c9750-167">The setup of a dual-write connection between an existing instance of a Finance and Operations app and an existing instance of a customer engagement app occurs in the Finance and Operation environment.</span></span>

1. <span data-ttu-id="c9750-168">[Configurar a conexão do aplicativo do Finance and Operations](enable-dual-write.md).</span><span class="sxs-lookup"><span data-stu-id="c9750-168">[Set up the connection from the Finance and Operations app](enable-dual-write.md).</span></span>
2. <span data-ttu-id="c9750-169">Para sincronizar os dados existentes do Dataverse com o aplicativo do Finance and Operations, [inicialize](bootstrap-company-data.md) os dados do Dataverse usando o código de uma empresa da ISO com três letras.</span><span class="sxs-lookup"><span data-stu-id="c9750-169">To sync the existing Dataverse data to the Finance and Operations app, [bootstrap](bootstrap-company-data.md) the Dataverse data by using a three-letter ISO company code.</span></span>
3. <span data-ttu-id="c9750-170">Execute a funcionalidade **Sincronização inicial** para as tabelas das quais você deseja sincronizar dados.</span><span class="sxs-lookup"><span data-stu-id="c9750-170">Run the **Initial sync** functionality for the tables that you want to sync data for.</span></span>

<span data-ttu-id="c9750-171">Para obter links para um exemplo e uma abordagem alternativa, consulte a seção [Exemplo](#example).</span><span class="sxs-lookup"><span data-stu-id="c9750-171">For links to an example and an alternative approach, see the [Example](#example) section.</span></span>

## <a name="example"></a><span data-ttu-id="c9750-172">Exemplo</span><span class="sxs-lookup"><span data-stu-id="c9750-172">Example</span></span>

<span data-ttu-id="c9750-173">Para obter um exemplo, consulte [Como habilitar Customers V3 — Mapa de tabelas de contato](enable-entity-map.md#enable-table-map)</span><span class="sxs-lookup"><span data-stu-id="c9750-173">For an example, see [Enabling the Customers V3—Contacts table map](enable-entity-map.md#enable-table-map)</span></span>

<span data-ttu-id="c9750-174">Para obter uma abordagem alternativa baseada em volumes de dados em cada entidade que precise executar a sincronização inicial, consulte [Considerações sobre a sincronização inicial](initial-sync-guidance.md).</span><span class="sxs-lookup"><span data-stu-id="c9750-174">For an alternative approach that is based on data volumes in each entity that must run an initial synchronization, see [Considerations for initial synchronization](initial-sync-guidance.md).</span></span>
