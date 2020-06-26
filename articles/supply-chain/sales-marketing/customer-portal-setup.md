---
title: Instalar, configurar e atualizar o portal do cliente
description: Este tópico oferece detalhes de licenciamento e instruções de configuração para o portal do cliente.
author: dasani-madipalli
manager: tfehr
ms.date: 04/22/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: damadipa
ms.search.validFrom: 2020-04-22
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: b9d1e742f78254d949dc49fda008d63b8bff4d65
ms.sourcegitcommit: 713b5dfc76a6875d0ba6d86c5cbd585ea502cf9d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/01/2020
ms.locfileid: "3413934"
---
# <a name="install-set-up-and-update-the-customer-portal"></a><span data-ttu-id="b8773-103">Instalar, configurar e atualizar o portal do cliente</span><span class="sxs-lookup"><span data-stu-id="b8773-103">Install, set up, and update the Customer portal</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="b8773-104">Requisitos de licenciamento</span><span class="sxs-lookup"><span data-stu-id="b8773-104">Licensing requirements</span></span>

<span data-ttu-id="b8773-105">Para implementar o portal do cliente, você deve ter as seguintes licenças:</span><span class="sxs-lookup"><span data-stu-id="b8773-105">To implement the Customer portal, you must have the following licenses:</span></span>

- <span data-ttu-id="b8773-106">Portais do **Power Apps** – essa licença é necessária para hospedar o portal do cliente.</span><span class="sxs-lookup"><span data-stu-id="b8773-106">**Power Apps portals** – This license is required to host the Customer portal.</span></span> <span data-ttu-id="b8773-107">Os portais são licenciados com base no uso.</span><span class="sxs-lookup"><span data-stu-id="b8773-107">Portals are licensed based on usage.</span></span> <span data-ttu-id="b8773-108">Para obter mais informações, consulte os [requisitos de licenciamento de portais do Power Apps](https://docs.microsoft.com/power-platform/admin/powerapps-flow-licensing-faq#portals).</span><span class="sxs-lookup"><span data-stu-id="b8773-108">For more information, see the [Power Apps portals licensing requirements](https://docs.microsoft.com/power-platform/admin/powerapps-flow-licensing-faq#portals).</span></span>
- <span data-ttu-id="b8773-109">**Gravação dupla** – você deve ter as licenças necessárias para habilitar a gravação dupla para entidades do Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="b8773-109">**Dual-write** – You must have the necessary licenses to enable dual-write for Supply Chain Management entities.</span></span> <span data-ttu-id="b8773-110">Para obter mais informações, consulte os [requisitos do sistema para gravação dupla](../../fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-system-req.md).</span><span class="sxs-lookup"><span data-stu-id="b8773-110">For more information, see the [system requirements for dual-write](../../fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-system-req.md).</span></span>

## <a name="dependencies-on-dual-write-and-power-apps-portals"></a><span data-ttu-id="b8773-111">Dependências de gravação dupla e de portais do Power Apps</span><span class="sxs-lookup"><span data-stu-id="b8773-111">Dependencies on dual-write and Power Apps portals</span></span>

<span data-ttu-id="b8773-112">O portal do cliente depende de portais do Power Apps e da gravação dupla, conforme mostrado na ilustração a seguir.</span><span class="sxs-lookup"><span data-stu-id="b8773-112">The Customer portal depends on Power Apps portals and dual-write, as shown in the following illustration.</span></span>

![![Dependências do portal do cliente](media/customer-portal-elements.png "Dependências do portal do cliente")](media/customer-portal-elements.png "Customer portal dependencies")

<span data-ttu-id="b8773-114">Diferente de outros recursos do Supply Chain Management, o modelo de portal do cliente reside em portais do Power Apps.</span><span class="sxs-lookup"><span data-stu-id="b8773-114">Unlike other features from Supply Chain Management, the Customer portal template resides in Power Apps portals.</span></span> <span data-ttu-id="b8773-115">Portanto, o portal do cliente é limitado pela funcionalidade e recursos fornecidos pelos portais do Power Apps e pelas entidades em gravação dupla.</span><span class="sxs-lookup"><span data-stu-id="b8773-115">Therefore, the Customer portal is limited by the functionality and capabilities that are provided by Power Apps portals and the entities in dual-write.</span></span>

## <a name="required-setup-to-enable-the-customer-portal"></a><a name="required-setup"></a><span data-ttu-id="b8773-116">Configuração necessária para habilitar o portal do cliente</span><span class="sxs-lookup"><span data-stu-id="b8773-116">Required setup to enable the Customer portal</span></span>

<span data-ttu-id="b8773-117">Após verificar que tem as licenças necessárias, você pode configurar a gravação dupla, conforme descrito nas [instruções de sincronização inicial de gravação dupla](../../fin-ops-core/dev-itpro/data-entities/dual-write/initial-sync.md).</span><span class="sxs-lookup"><span data-stu-id="b8773-117">After you've made sure that you have the required licenses, you can set up dual-write as described in the [dual-write initial synchronization instructions](../../fin-ops-core/dev-itpro/data-entities/dual-write/initial-sync.md).</span></span>

<span data-ttu-id="b8773-118">Certifique-se de habilitar os seguintes mapeamentos de entidade em gravação dupla:</span><span class="sxs-lookup"><span data-stu-id="b8773-118">Be sure to enable the following entity mappings in dual-write:</span></span>

- <span data-ttu-id="b8773-119">Cabeçalho de ordem de venda</span><span class="sxs-lookup"><span data-stu-id="b8773-119">Sales Order Header</span></span>
- <span data-ttu-id="b8773-120">Detalhes de ordem de venda</span><span class="sxs-lookup"><span data-stu-id="b8773-120">Sales Order Details</span></span>
- <span data-ttu-id="b8773-121">Contas</span><span class="sxs-lookup"><span data-stu-id="b8773-121">Accounts</span></span>
- <span data-ttu-id="b8773-122">Contatos</span><span class="sxs-lookup"><span data-stu-id="b8773-122">Contacts</span></span>
- <span data-ttu-id="b8773-123">Produtos</span><span class="sxs-lookup"><span data-stu-id="b8773-123">Products</span></span>

<span data-ttu-id="b8773-124">Após a conclusão dessa configuração, você poderá provisionar o modelo de portal do cliente.</span><span class="sxs-lookup"><span data-stu-id="b8773-124">After this setup is completed, you can provision the Customer portal template.</span></span>

## <a name="provision-the-customer-portal"></a><span data-ttu-id="b8773-125">Provisione o portal do cliente</span><span class="sxs-lookup"><span data-stu-id="b8773-125">Provision the Customer portal</span></span>

<span data-ttu-id="b8773-126">Antes de começar, verifique se você já concluiu a [configuração necessária](#required-setup).</span><span class="sxs-lookup"><span data-stu-id="b8773-126">Before you begin, make sure that you've already completed the [required setup](#required-setup).</span></span> <span data-ttu-id="b8773-127">Em seguida, siga estas etapas para provisionar o portal do cliente.</span><span class="sxs-lookup"><span data-stu-id="b8773-127">Then follow these steps to provision the Customer portal.</span></span>

1. <span data-ttu-id="b8773-128">Vá para [make.powerapps.com](https://make.powerapps.com/).</span><span class="sxs-lookup"><span data-stu-id="b8773-128">Go to [make.powerapps.com](https://make.powerapps.com/).</span></span>
2. <span data-ttu-id="b8773-129">Verifique se você está usando o ambiente no qual ativou a gravação dupla.</span><span class="sxs-lookup"><span data-stu-id="b8773-129">Make sure that you're using the environment where you enabled dual-write.</span></span>
3. <span data-ttu-id="b8773-130">Na guia **Criar**, role para baixo até a seção **Iniciar do modelo** e selecione o modelo denominado **Cliente do Supply Chain Management**.</span><span class="sxs-lookup"><span data-stu-id="b8773-130">On the **Create** tab, scroll down to the **Start from template** section, and select the template that is named **Supply Chain Management Customer**.</span></span>
4. <span data-ttu-id="b8773-131">Siga as instruções na tela.</span><span class="sxs-lookup"><span data-stu-id="b8773-131">Follow the on-screen instructions.</span></span>

<span data-ttu-id="b8773-132">Após a conclusão do provisionamento, você poderá acessar o portal do cliente na seção **Seus aplicativos** da página **Inicial**.</span><span class="sxs-lookup"><span data-stu-id="b8773-132">After provisioning is completed, you can access the Customer portal in the **Your apps** section of the **Home** page.</span></span>

> [!NOTE]
> <span data-ttu-id="b8773-133">Se a solução de gravação dupla não estiver instalada no ambiente no qual estiver trabalhando, você receberá uma mensagem de erro e o portal do cliente não será provisionado.</span><span class="sxs-lookup"><span data-stu-id="b8773-133">If the dual-write solution isn't installed in the environment that you're working in, you will receive an error message, and the Customer portal won't be provisioned.</span></span>

## <a name="update-the-customer-portal"></a><span data-ttu-id="b8773-134">Atualize o portal do cliente</span><span class="sxs-lookup"><span data-stu-id="b8773-134">Update the Customer portal</span></span>

<span data-ttu-id="b8773-135">Mais funcionalidades poderão ser adicionadas ao portal do cliente posteriormente.</span><span class="sxs-lookup"><span data-stu-id="b8773-135">More functionality might be added to the Customer portal later.</span></span> <span data-ttu-id="b8773-136">As alterações que a Microsoft fizer nos componentes da solução subjacente aparecerão automaticamente no seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="b8773-136">Any changes that Microsoft makes to the underlying solution components will automatically appear in your environment.</span></span> <span data-ttu-id="b8773-137">No entanto, o site provisionado no seu ambiente não refletirá automaticamente as alterações feitas nos dados de configuração.</span><span class="sxs-lookup"><span data-stu-id="b8773-137">However, the website that is provisioned in your environment won't automatically reflect changes that are made to the configuration data.</span></span> <span data-ttu-id="b8773-138">Será necessário aplicar manualmente essas alterações obtendo o código do novo modelo e mesclando-o com o site provisionado.</span><span class="sxs-lookup"><span data-stu-id="b8773-138">You will have to manually apply those changes by getting the code from the new template and merging it with the provisioned website.</span></span>

## <a name="resources"></a><span data-ttu-id="b8773-139">Recursos</span><span class="sxs-lookup"><span data-stu-id="b8773-139">Resources</span></span>

<span data-ttu-id="b8773-140">Para saber como você pode configurar e personalizar o portal do cliente, comece analisando a seguinte documentação para as tecnologias subjacentes:</span><span class="sxs-lookup"><span data-stu-id="b8773-140">To learn how you can set up and customize the Customer portal, you should start by reviewing the following documentation for the underlying technologies:</span></span>

- [<span data-ttu-id="b8773-141">Documentação de portais do Power Apps</span><span class="sxs-lookup"><span data-stu-id="b8773-141">Power Apps portals documentation</span></span>](https://docs.microsoft.com/powerapps/maker/portals/overview)
- [<span data-ttu-id="b8773-142">Documentação da gravação dupla</span><span class="sxs-lookup"><span data-stu-id="b8773-142">Dual-write documentation</span></span>](../../fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-home-page.md)

<span data-ttu-id="b8773-143">Para gerenciar com eficiência seus portais, você deve compreender os portais do Power Apps e o ciclo de vida do Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="b8773-143">To effectively manage your portals, you must understand the Power Apps portals and Common Data Service lifecycle.</span></span> <span data-ttu-id="b8773-144">Para obter mais informações, consulte os seguintes recursos:</span><span class="sxs-lookup"><span data-stu-id="b8773-144">For more information, see the following resources:</span></span>

- [<span data-ttu-id="b8773-145">Sobre o ciclo de vida do portal</span><span class="sxs-lookup"><span data-stu-id="b8773-145">About portal lifecycle</span></span>](https://docs.microsoft.com/powerapps/maker/portals/admin/portal-lifecycle)
- [<span data-ttu-id="b8773-146">Atualizar um portal</span><span class="sxs-lookup"><span data-stu-id="b8773-146">Upgrade a portal</span></span>](https://docs.microsoft.com/powerapps/maker/portals/admin/upgrade-portal)
- [<span data-ttu-id="b8773-147">Migrar configuração do portal</span><span class="sxs-lookup"><span data-stu-id="b8773-147">Migrate portal configuration</span></span>](https://docs.microsoft.com/powerapps/maker/portals/admin/migrate-portal-configuration)
- [<span data-ttu-id="b8773-148">Gerenciamento do ciclo de vida da solução: Dynamics 365 para aplicativos do Customer Engagement</span><span class="sxs-lookup"><span data-stu-id="b8773-148">Solution Lifecycle Management: Dynamics 365 for Customer Engagement apps</span></span>](https://www.microsoft.com/download/details.aspx?id=57777)