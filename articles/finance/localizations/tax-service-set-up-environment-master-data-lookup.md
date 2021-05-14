---
title: Configurar um ambiente para pesquisa de dados mestres
description: Este tópico explica como configurar seu ambiente para usar o recurso de busca de dados mestres de Cálculo de Imposto.
author: kai-cloud
ms.date: 04/21/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: pashao
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 9f9b385df1db60b27698d90281c43fabb574af49
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924145"
---
# <a name="set-up-an-environment-for-master-data-lookup"></a><span data-ttu-id="9c398-103">Configurar um ambiente para pesquisa de dados mestres</span><span class="sxs-lookup"><span data-stu-id="9c398-103">Set up an environment for master data lookup</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9c398-104">Este tópico explica como configurar seu ambiente para usar o recurso de busca de dados mestres de Cálculo de Imposto.</span><span class="sxs-lookup"><span data-stu-id="9c398-104">This topic explains how to set up your environment to use the Tax Calculation master data lookup functionality.</span></span>

1. <span data-ttu-id="9c398-105">Configure a integração do Power Platform ao Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="9c398-105">Set up power platform integration in Lifecycle Services (LCS).</span></span> <span data-ttu-id="9c398-106">Para obter mais informações, consulte [Integração do Microsoft Power Platform — Visão geral dos suplementos](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md).</span><span class="sxs-lookup"><span data-stu-id="9c398-106">For more information, see [Microsoft Power Platform integration - Add-ins overview](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md).</span></span>
2. <span data-ttu-id="9c398-107">Configure o Dynamics 365 Finance e o Microsoft Dataverse.</span><span class="sxs-lookup"><span data-stu-id="9c398-107">Set up Dynamics 365 Finance and Microsoft Dataverse.</span></span> <span data-ttu-id="9c398-108">Para obter mais informações, consulte [Como obter a solução](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#getting-the-solution) e [Autenticação e autorização](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#authentication-and-authorization).</span><span class="sxs-lookup"><span data-stu-id="9c398-108">For more information, see [Getting the solution](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#getting-the-solution) and [Authentication and authorization](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#authentication-and-authorization).</span></span>
3. <span data-ttu-id="9c398-109">Configure as seguintes entidades.</span><span class="sxs-lookup"><span data-stu-id="9c398-109">Set up the following entities.</span></span> <span data-ttu-id="9c398-110">Para obter mais informações, consulte [Habilitar entidades virtuais](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#enabling-virtual-entities).</span><span class="sxs-lookup"><span data-stu-id="9c398-110">For more information, see [Enabling virtual entities](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#enabling-virtual-entities).</span></span>
      - <span data-ttu-id="9c398-111">CompanyInfoEntity</span><span class="sxs-lookup"><span data-stu-id="9c398-111">CompanyInfoEntity</span></span>
      - <span data-ttu-id="9c398-112">CurrencyEntity</span><span class="sxs-lookup"><span data-stu-id="9c398-112">CurrencyEntity</span></span>
      - <span data-ttu-id="9c398-113">CustCustomerV3Entity</span><span class="sxs-lookup"><span data-stu-id="9c398-113">CustCustomerV3Entity</span></span>
      - <span data-ttu-id="9c398-114">DeliveryTermsEntity</span><span class="sxs-lookup"><span data-stu-id="9c398-114">DeliveryTermsEntity</span></span>
      - <span data-ttu-id="9c398-115">EcoResProductCategoryEntity</span><span class="sxs-lookup"><span data-stu-id="9c398-115">EcoResProductCategoryEntity</span></span>
      - <span data-ttu-id="9c398-116">EcoResReleasedProductV2Entity</span><span class="sxs-lookup"><span data-stu-id="9c398-116">EcoResReleasedProductV2Entity</span></span>
      - <span data-ttu-id="9c398-117">LogisticsAddressCityEntity</span><span class="sxs-lookup"><span data-stu-id="9c398-117">LogisticsAddressCityEntity</span></span>
      - <span data-ttu-id="9c398-118">LogisticsAddressCountryRegionTranslationEntity</span><span class="sxs-lookup"><span data-stu-id="9c398-118">LogisticsAddressCountryRegionTranslationEntity</span></span>
      - <span data-ttu-id="9c398-119">LogisticsAddressStateEntity</span><span class="sxs-lookup"><span data-stu-id="9c398-119">LogisticsAddressStateEntity</span></span>
      - <span data-ttu-id="9c398-120">PurchProcurementChargeCDSEntity</span><span class="sxs-lookup"><span data-stu-id="9c398-120">PurchProcurementChargeCDSEntity</span></span>
      - <span data-ttu-id="9c398-121">SalesChargeCDSEntity</span><span class="sxs-lookup"><span data-stu-id="9c398-121">SalesChargeCDSEntity</span></span>
      - <span data-ttu-id="9c398-122">TaxGroupEntity</span><span class="sxs-lookup"><span data-stu-id="9c398-122">TaxGroupEntity</span></span>
      - <span data-ttu-id="9c398-123">TaxItemGroupHeadingEntity</span><span class="sxs-lookup"><span data-stu-id="9c398-123">TaxItemGroupHeadingEntity</span></span>
      - <span data-ttu-id="9c398-124">VendVendorV2Entity</span><span class="sxs-lookup"><span data-stu-id="9c398-124">VendVendorV2Entity</span></span>
4. <span data-ttu-id="9c398-125">Configure o Regulatory Configuration Service (RCS) do Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="9c398-125">Set up the Dynamics 365 Regulatory Configuration Service (RCS).</span></span> 
5. <span data-ttu-id="9c398-126">Crie uma solicitação de serviço para a Microsoft habilitar a liberação dos seguintes recursos:</span><span class="sxs-lookup"><span data-stu-id="9c398-126">Create a service request for Microsoft to enable flighting of the following features:</span></span>

      - <span data-ttu-id="9c398-127">ERCdsFeature</span><span class="sxs-lookup"><span data-stu-id="9c398-127">ERCdsFeature</span></span>
      - <span data-ttu-id="9c398-128">TaxServiceCDSFeature</span><span class="sxs-lookup"><span data-stu-id="9c398-128">TaxServiceCDSFeature</span></span>

6. <span data-ttu-id="9c398-129">Acesse o espaço de trabalho **Gerenciamento de recursos** e habilite estes recursos:</span><span class="sxs-lookup"><span data-stu-id="9c398-129">Go to the **Feature management** workspace, and enable the following features:</span></span>

      - <span data-ttu-id="9c398-130">(Versão preliminar) Suporte às fontes de dados do Dataverse para Relatório Eletrônico</span><span class="sxs-lookup"><span data-stu-id="9c398-130">(Preview) Electronic reporting Dataverse datasources support</span></span>
      - <span data-ttu-id="9c398-131">(Versão preliminar) Suporte à fonte de dados do Serviço de Imposto do Dataverse</span><span class="sxs-lookup"><span data-stu-id="9c398-131">(Preview) Tax Service Dataverse datasources support</span></span>
      - <span data-ttu-id="9c398-132">(Versão preliminar) Recursos de globalização</span><span class="sxs-lookup"><span data-stu-id="9c398-132">(Preview) Globalization features</span></span>

5. <span data-ttu-id="9c398-133">Entre no RCS usando uma conta do administrador de locatário.</span><span class="sxs-lookup"><span data-stu-id="9c398-133">Sign in to RCS using a tenant admin account.</span></span>
6. <span data-ttu-id="9c398-134">Acesse **Relatório Eletrônico** > **Aplicativos conectados**.</span><span class="sxs-lookup"><span data-stu-id="9c398-134">Go to **Electronic reporting** > **Connected applications**.</span></span> 
7. <span data-ttu-id="9c398-135">Selecione **Novo** para adicionar um registro e insira estas informações de campo.</span><span class="sxs-lookup"><span data-stu-id="9c398-135">Select **New** to add a record, and enter the following field information.</span></span> 

   - <span data-ttu-id="9c398-136">No campo **Nome**, insira um nome.</span><span class="sxs-lookup"><span data-stu-id="9c398-136">In the **Name** field, enter a name.</span></span>
   - <span data-ttu-id="9c398-137">No campo **Tipo**, selecione **Dataverse**.</span><span class="sxs-lookup"><span data-stu-id="9c398-137">In the **Type** field, select **Dataverse**.</span></span>
   - <span data-ttu-id="9c398-138">No campo **Aplicativo**, insira sua URL do Dataverse.</span><span class="sxs-lookup"><span data-stu-id="9c398-138">In the **Application** field, enter your Dataverse URL.</span></span>
   - <span data-ttu-id="9c398-139">No campo **Locatário**, insira seu locatário.</span><span class="sxs-lookup"><span data-stu-id="9c398-139">In the **Tenant** field, enter your tenant.</span></span>
   - <span data-ttu-id="9c398-140">No campo **URL personalizada**, insira sua URL do Dataverse e inclua "/api/data/v9.1" no final.</span><span class="sxs-lookup"><span data-stu-id="9c398-140">In the **Custom URL** field, enter your Dataverse URL and append it with "/api/data/v9.1".</span></span>

8. <span data-ttu-id="9c398-141">Selecione **Verificar conexão** e finalize o processo de conexão.</span><span class="sxs-lookup"><span data-stu-id="9c398-141">Select **Check connection**, and finish the connection process.</span></span> 

   <span data-ttu-id="9c398-142">[![Botão Verificar conexão](./media/tax-service-setup-environment-for-mater-date-pic1.png)](./media/tax-service-setup-environment-for-mater-date-pic1.png)</span><span class="sxs-lookup"><span data-stu-id="9c398-142">[![Check connection button](./media/tax-service-setup-environment-for-mater-date-pic1.png)](./media/tax-service-setup-environment-for-mater-date-pic1.png)</span></span>

9. <span data-ttu-id="9c398-143">Acesse **Relatório Eletrônico** > **Configurações de imposto** e importe configurações de imposto em [Configurações de imposto](https://go.microsoft.com/fwlink/?linkid=2158352).</span><span class="sxs-lookup"><span data-stu-id="9c398-143">Go to **Electronic reporting** > **Tax configurations**, and import tax configurations from [Tax configurations](https://go.microsoft.com/fwlink/?linkid=2158352).</span></span>

   <span data-ttu-id="9c398-144">[![Página Configurações de imposto, árvore de modelo de dados de imposto](./media/tax-service-setup-environment-for-mater-date-pic2.png)](./media/tax-service-setup-environment-for-mater-date-pic2.png)</span><span class="sxs-lookup"><span data-stu-id="9c398-144">[![Tax configurations page, Tax data model tree](./media/tax-service-setup-environment-for-mater-date-pic2.png)](./media/tax-service-setup-environment-for-mater-date-pic2.png)</span></span>

10. <span data-ttu-id="9c398-145">Acesse **Mapeamento do modelo de documento tributável** ou **Mapeamento do modelo do Dataverse** se estiver usando uma configuração da Microsoft, e no campo **Aplicativo conectado**, selecione o registro criado na etapa 7.</span><span class="sxs-lookup"><span data-stu-id="9c398-145">Go to the **Taxable document model mapping**, or **Dataverse Model Mapping** if you are using a Microsoft configuration, and in the **Connected application** field, select the record that you created in step 7.</span></span>
11. <span data-ttu-id="9c398-146">Defina a opção **Padrão do mapeamento de modelo** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="9c398-146">Set **Default for model mapping** to **Yes**.</span></span>

   <span data-ttu-id="9c398-147">[![Página Mapeamento do modelo](./media/tax-service-setup-environment-for-mater-date-pic3.png)](./media/tax-service-setup-environment-for-mater-date-pic3.png)</span><span class="sxs-lookup"><span data-stu-id="9c398-147">[![Model mapping page](./media/tax-service-setup-environment-for-mater-date-pic3.png)](./media/tax-service-setup-environment-for-mater-date-pic3.png)</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
