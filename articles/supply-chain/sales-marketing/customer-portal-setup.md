---
title: Instalar, configurar e atualizar o portal do cliente
description: Este tópico oferece detalhes de licenciamento e instruções de configuração para o portal do cliente.
author: dasani-madipalli
ms.date: 06/08/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: damadipa
ms.search.validFrom: 2020-04-22
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: 5c4cad305e3d130b3283ca3424c84f60e2d13307
ms.sourcegitcommit: 34b478f175348d99df4f2f0c2f6c0c21b6b2660a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/16/2021
ms.locfileid: "5907806"
---
# <a name="install-set-up-and-update-the-customer-portal"></a><span data-ttu-id="50013-103">Instalar, configurar e atualizar o portal do cliente</span><span class="sxs-lookup"><span data-stu-id="50013-103">Install, set up, and update the Customer portal</span></span>

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

## <a name="licensing-requirements"></a><span data-ttu-id="50013-104">Requisitos de licenciamento</span><span class="sxs-lookup"><span data-stu-id="50013-104">Licensing requirements</span></span>

<span data-ttu-id="50013-105">Para implementar o portal do cliente, você deve ter as seguintes licenças:</span><span class="sxs-lookup"><span data-stu-id="50013-105">To implement the Customer portal, you must have the following licenses:</span></span>

- <span data-ttu-id="50013-106">Portais do **Power Apps** – essa licença é necessária para hospedar o portal do cliente.</span><span class="sxs-lookup"><span data-stu-id="50013-106">**Power Apps portals** – This license is required to host the Customer portal.</span></span> <span data-ttu-id="50013-107">Os portais são licenciados com base no uso.</span><span class="sxs-lookup"><span data-stu-id="50013-107">Portals are licensed based on usage.</span></span> <span data-ttu-id="50013-108">Para obter mais informações, consulte os [requisitos de licenciamento de portais do Power Apps](/power-platform/admin/powerapps-flow-licensing-faq#portals).</span><span class="sxs-lookup"><span data-stu-id="50013-108">For more information, see the [Power Apps portals licensing requirements](/power-platform/admin/powerapps-flow-licensing-faq#portals).</span></span>
- <span data-ttu-id="50013-109">**Gravação dupla** – você deve ter as licenças necessárias para habilitar a gravação dupla para tabelas do Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="50013-109">**Dual-write** – You must have the necessary licenses to enable dual-write for Supply Chain Management tables.</span></span> <span data-ttu-id="50013-110">Para obter mais informações, consulte os [requisitos do sistema para gravação dupla](../../fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-system-req.md).</span><span class="sxs-lookup"><span data-stu-id="50013-110">For more information, see the [system requirements for dual-write](../../fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-system-req.md).</span></span>

## <a name="dependencies-on-dual-write-and-power-apps-portals"></a><span data-ttu-id="50013-111">Dependências de gravação dupla e de portais do Power Apps</span><span class="sxs-lookup"><span data-stu-id="50013-111">Dependencies on dual-write and Power Apps portals</span></span>

<span data-ttu-id="50013-112">O portal do cliente depende de portais do Power Apps e da gravação dupla, conforme mostrado na ilustração a seguir.</span><span class="sxs-lookup"><span data-stu-id="50013-112">The Customer portal depends on Power Apps portals and dual-write, as shown in the following illustration.</span></span>

<span data-ttu-id="50013-113">![Dependências do portal do cliente](media/customer-portal-elements.png "Dependências do portal do cliente")</span><span class="sxs-lookup"><span data-stu-id="50013-113">![Customer portal dependencies](media/customer-portal-elements.png "Customer portal dependencies")</span></span>

<span data-ttu-id="50013-114">Diferente de outros recursos do Supply Chain Management, o modelo de portal do cliente reside em portais do Power Apps.</span><span class="sxs-lookup"><span data-stu-id="50013-114">Unlike other features from Supply Chain Management, the Customer portal template resides in Power Apps portals.</span></span> <span data-ttu-id="50013-115">Portanto, o portal do cliente é limitado pela funcionalidade e recursos fornecidos pelos portais do Power Apps e pelas tabelas em gravação dupla.</span><span class="sxs-lookup"><span data-stu-id="50013-115">Therefore, the Customer portal is limited by the functionality and capabilities that are provided by Power Apps portals and the tables in dual-write.</span></span>

## <a name="required-setup-to-enable-the-customer-portal"></a><a name="required-setup"></a><span data-ttu-id="50013-116">Configuração necessária para habilitar o portal do cliente</span><span class="sxs-lookup"><span data-stu-id="50013-116">Required setup to enable the Customer portal</span></span>

<span data-ttu-id="50013-117">Após verificar que tem as licenças necessárias, você pode configurar a gravação dupla, conforme descrito nas [instruções de sincronização inicial de gravação dupla](/dynamics365/supply-chain/sales-marketing/enable-entity-map).</span><span class="sxs-lookup"><span data-stu-id="50013-117">After you've made sure that you have the required licenses, you can set up dual-write as described in the [dual-write initial synchronization instructions](/dynamics365/supply-chain/sales-marketing/enable-entity-map).</span></span>

<span data-ttu-id="50013-118">Certifique-se de habilitar os seguintes mapeamentos de tabela em gravação dupla:</span><span class="sxs-lookup"><span data-stu-id="50013-118">Be sure to enable the following table mappings in dual-write:</span></span>

- <span data-ttu-id="50013-119">Cabeçalho de ordem de venda</span><span class="sxs-lookup"><span data-stu-id="50013-119">Sales Order Header</span></span>
- <span data-ttu-id="50013-120">Detalhes de ordem de venda</span><span class="sxs-lookup"><span data-stu-id="50013-120">Sales Order Details</span></span>
- <span data-ttu-id="50013-121">Contas</span><span class="sxs-lookup"><span data-stu-id="50013-121">Accounts</span></span>
- <span data-ttu-id="50013-122">Contatos</span><span class="sxs-lookup"><span data-stu-id="50013-122">Contacts</span></span>
- <span data-ttu-id="50013-123">Produtos</span><span class="sxs-lookup"><span data-stu-id="50013-123">Products</span></span>

<span data-ttu-id="50013-124">Após a conclusão dessa configuração, você poderá provisionar o modelo de portal do cliente.</span><span class="sxs-lookup"><span data-stu-id="50013-124">After this setup is completed, you can provision the Customer portal template.</span></span>

## <a name="provision-the-customer-portal"></a><span data-ttu-id="50013-125">Provisione o portal do cliente</span><span class="sxs-lookup"><span data-stu-id="50013-125">Provision the Customer portal</span></span>

<span data-ttu-id="50013-126">Antes de começar, verifique se você já concluiu a [configuração necessária](#required-setup).</span><span class="sxs-lookup"><span data-stu-id="50013-126">Before you begin, make sure that you've already completed the [required setup](#required-setup).</span></span> <span data-ttu-id="50013-127">Em seguida, siga estas etapas para provisionar o portal do cliente.</span><span class="sxs-lookup"><span data-stu-id="50013-127">Then follow these steps to provision the Customer portal.</span></span>

1. <span data-ttu-id="50013-128">Vá para [make.powerapps.com](https://make.powerapps.com/).</span><span class="sxs-lookup"><span data-stu-id="50013-128">Go to [make.powerapps.com](https://make.powerapps.com/).</span></span>
2. <span data-ttu-id="50013-129">Verifique se você está usando o ambiente no qual ativou a gravação dupla.</span><span class="sxs-lookup"><span data-stu-id="50013-129">Make sure that you're using the environment where you enabled dual-write.</span></span>
3. <span data-ttu-id="50013-130">Na guia **Criar**, role para baixo até a seção **Iniciar do modelo** e selecione o modelo denominado **Portal do Cliente**.</span><span class="sxs-lookup"><span data-stu-id="50013-130">On the **Create** tab, scroll down to the **Start from template** section, and select the template that is named **Customer Portal**.</span></span>
4. <span data-ttu-id="50013-131">Siga as instruções na tela.</span><span class="sxs-lookup"><span data-stu-id="50013-131">Follow the on-screen instructions.</span></span>

<span data-ttu-id="50013-132">Após a conclusão do provisionamento, você poderá acessar o portal do cliente na seção **Seus aplicativos** da página **Inicial**.</span><span class="sxs-lookup"><span data-stu-id="50013-132">After provisioning is completed, you can access the Customer portal in the **Your apps** section of the **Home** page.</span></span>

> [!NOTE]
> <span data-ttu-id="50013-133">Se a solução de gravação dupla não estiver instalada no ambiente no qual estiver trabalhando, você receberá uma mensagem de erro e o portal do cliente não será provisionado.</span><span class="sxs-lookup"><span data-stu-id="50013-133">If the dual-write solution isn't installed in the environment that you're working in, you will receive an error message, and the Customer portal won't be provisioned.</span></span>

## <a name="update-the-customer-portal"></a><span data-ttu-id="50013-134">Atualize o portal do cliente</span><span class="sxs-lookup"><span data-stu-id="50013-134">Update the Customer portal</span></span>

<span data-ttu-id="50013-135">Mais funcionalidades poderão ser adicionadas ao portal do cliente posteriormente.</span><span class="sxs-lookup"><span data-stu-id="50013-135">More functionality might be added to the Customer portal later.</span></span> <span data-ttu-id="50013-136">As alterações que a Microsoft fizer nos componentes da solução subjacente aparecerão automaticamente no seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="50013-136">Any changes that Microsoft makes to the underlying solution components will automatically appear in your environment.</span></span> <span data-ttu-id="50013-137">No entanto, o site provisionado no seu ambiente não refletirá automaticamente as alterações feitas nos dados de configuração.</span><span class="sxs-lookup"><span data-stu-id="50013-137">However, the website that is provisioned in your environment won't automatically reflect changes that are made to the configuration data.</span></span> <span data-ttu-id="50013-138">Será necessário aplicar manualmente essas alterações obtendo o código do novo modelo e mesclando-o com o site provisionado.</span><span class="sxs-lookup"><span data-stu-id="50013-138">You will have to manually apply those changes by getting the code from the new template and merging it with the provisioned website.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="50013-139">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="50013-139">Additional resources</span></span>

<span data-ttu-id="50013-140">Para saber como você pode configurar e personalizar o portal do cliente, comece analisando a seguinte documentação para as tecnologias subjacentes:</span><span class="sxs-lookup"><span data-stu-id="50013-140">To learn how you can set up and customize the Customer portal, you should start by reviewing the following documentation for the underlying technologies:</span></span>

- [<span data-ttu-id="50013-141">Documentação de portais do Power Apps</span><span class="sxs-lookup"><span data-stu-id="50013-141">Power Apps portals documentation</span></span>](/powerapps/maker/portals/overview)
- [<span data-ttu-id="50013-142">Documentação da gravação dupla</span><span class="sxs-lookup"><span data-stu-id="50013-142">Dual-write documentation</span></span>](../../fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-home-page.md)

<span data-ttu-id="50013-143">Para gerenciar com eficiência seus portais, você deve compreender os portais do Power Apps e o ciclo de vida do Microsoft Dataverse.</span><span class="sxs-lookup"><span data-stu-id="50013-143">To effectively manage your portals, you must understand the Power Apps portals and Microsoft Dataverse lifecycle.</span></span> <span data-ttu-id="50013-144">Para obter mais informações, consulte os seguintes recursos:</span><span class="sxs-lookup"><span data-stu-id="50013-144">For more information, see the following resources:</span></span>

- [<span data-ttu-id="50013-145">Sobre o ciclo de vida do portal</span><span class="sxs-lookup"><span data-stu-id="50013-145">About portal lifecycle</span></span>](/powerapps/maker/portals/admin/portal-lifecycle)
- [<span data-ttu-id="50013-146">Atualizar um portal</span><span class="sxs-lookup"><span data-stu-id="50013-146">Upgrade a portal</span></span>](/powerapps/maker/portals/admin/upgrade-portal)
- [<span data-ttu-id="50013-147">Migrar configuração do portal</span><span class="sxs-lookup"><span data-stu-id="50013-147">Migrate portal configuration</span></span>](/powerapps/maker/portals/admin/migrate-portal-configuration)
- [<span data-ttu-id="50013-148">Gerenciamento do ciclo de vida da solução: Dynamics 365 para aplicativos do Customer Engagement</span><span class="sxs-lookup"><span data-stu-id="50013-148">Solution Lifecycle Management: Dynamics 365 for Customer Engagement apps</span></span>](https://www.microsoft.com/download/details.aspx?id=57777)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]