---
title: Configurar um ambiente para pesquisa de dados mestres
description: Este tópico explica como configurar seu ambiente para usar o recurso de busca de dados mestres de Cálculo de Imposto.
author: kai-cloud
ms.date: 03/31/2021
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
ms.openlocfilehash: eda093a75898bace2f3c7968933b83ccafa7fabb
ms.sourcegitcommit: 66095f1b7e0fd2756aa29fd7deb9ce5392b7e0b2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/08/2021
ms.locfileid: "5869043"
---
# <a name="set-up-an-environment-for-master-data-lookup"></a><span data-ttu-id="04d43-103">Configurar um ambiente para pesquisa de dados mestres</span><span class="sxs-lookup"><span data-stu-id="04d43-103">Set up an environment for master data lookup</span></span>

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

<span data-ttu-id="04d43-104">Este tópico explica como configurar seu ambiente para usar o recurso de busca de dados mestres de Cálculo de Imposto.</span><span class="sxs-lookup"><span data-stu-id="04d43-104">This topic explains how to set up your environment to use the Tax Calculation master data lookup functionality.</span></span>

1. <span data-ttu-id="04d43-105">Configure a integração do Power Platform ao Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="04d43-105">Set up power platform integration in Lifecycle Services (LCS).</span></span> <span data-ttu-id="04d43-106">Para obter mais informações, consulte [Integração do Microsoft Power Platform — Visão geral dos suplementos](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md).</span><span class="sxs-lookup"><span data-stu-id="04d43-106">For more information, see [Microsoft Power Platform integration - Add-ins overview](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md).</span></span>
2. <span data-ttu-id="04d43-107">Configure o Dynamics 365 Finance e o Microsoft Dataverse.</span><span class="sxs-lookup"><span data-stu-id="04d43-107">Set up Dynamics 365 Finance and Microsoft Dataverse.</span></span> <span data-ttu-id="04d43-108">Para obter mais informações, consulte [Como obter a solução](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#getting-the-solution) e [Autenticação e autorização](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#authentication-and-authorization).</span><span class="sxs-lookup"><span data-stu-id="04d43-108">For more information, see [Getting the solution](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#getting-the-solution) and [Authentication and authorization](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#authentication-and-authorization).</span></span>
3. <span data-ttu-id="04d43-109">Importe a *Solução da entidade virtual como pré-requisito do serviço de imposto* da [Entidade virtual do serviço de imposto](https://go.microsoft.com/fwlink/?linkid=2158160).</span><span class="sxs-lookup"><span data-stu-id="04d43-109">Import the *Prerequisite tax service virtual entity solution* from the [Tax service virtual entity](https://go.microsoft.com/fwlink/?linkid=2158160).</span></span>
4. <span data-ttu-id="04d43-110">Configure o Regulatory Configuration Service (RCS) do Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="04d43-110">Set up the Dynamics 365 Regulatory Configuration Service (RCS).</span></span> 
5. <span data-ttu-id="04d43-111">Crie uma solicitação de serviço para a Microsoft habilitar a liberação dos seguintes recursos:</span><span class="sxs-lookup"><span data-stu-id="04d43-111">Create a service request for Microsoft to enable flighting of the following features:</span></span>

      - <span data-ttu-id="04d43-112">ERCdsFeature</span><span class="sxs-lookup"><span data-stu-id="04d43-112">ERCdsFeature</span></span>
      - <span data-ttu-id="04d43-113">TaxServiceCDSFeature</span><span class="sxs-lookup"><span data-stu-id="04d43-113">TaxServiceCDSFeature</span></span>

6. <span data-ttu-id="04d43-114">Em Finanças, acesse o espaço de trabalho **Gerenciamento de recursos** e habilite estes recursos:</span><span class="sxs-lookup"><span data-stu-id="04d43-114">In Finance, go to the **Feature management** workspace, and enable the following features:</span></span>

      - <span data-ttu-id="04d43-115">(Versão preliminar) Suporte às fontes de dados do Dataverse para Relatório Eletrônico</span><span class="sxs-lookup"><span data-stu-id="04d43-115">(Preview) Electronic reporting Dataverse datasources support</span></span>
      - <span data-ttu-id="04d43-116">(Versão preliminar) Suporte à fonte de dados do Serviço de Imposto do Dataverse</span><span class="sxs-lookup"><span data-stu-id="04d43-116">(Preview) Tax Service Dataverse datasources support</span></span>
      - <span data-ttu-id="04d43-117">(Versão preliminar) Recursos de globalização</span><span class="sxs-lookup"><span data-stu-id="04d43-117">(Preview) Globalization features</span></span>

5. <span data-ttu-id="04d43-118">Entre no RCS usando uma conta do administrador de locatário.</span><span class="sxs-lookup"><span data-stu-id="04d43-118">Sign in to RCS using a tenant admin account.</span></span>
6. <span data-ttu-id="04d43-119">Acesse **Relatório Eletrônico** > **Aplicativos conectados**.</span><span class="sxs-lookup"><span data-stu-id="04d43-119">Go to **Electronic reporting** > **Connected applications**.</span></span> 
7. <span data-ttu-id="04d43-120">Selecione **Novo** para adicionar um registro e insira estas informações de campo.</span><span class="sxs-lookup"><span data-stu-id="04d43-120">Select **New** to add a record, and enter the following field information.</span></span> 

   - <span data-ttu-id="04d43-121">No campo **Nome**, insira um nome.</span><span class="sxs-lookup"><span data-stu-id="04d43-121">In the **Name** field, enter a name.</span></span>
   - <span data-ttu-id="04d43-122">No campo **Tipo**, selecione **Dataverse**.</span><span class="sxs-lookup"><span data-stu-id="04d43-122">In the **Type** field, select **Dataverse**.</span></span>
   - <span data-ttu-id="04d43-123">No campo **Aplicativo**, insira sua URL do Dataverse.</span><span class="sxs-lookup"><span data-stu-id="04d43-123">In the **Application** field, enter your Dataverse URL.</span></span>
   - <span data-ttu-id="04d43-124">No campo **Locatário**, insira seu locatário.</span><span class="sxs-lookup"><span data-stu-id="04d43-124">In the **Tenant** field, enter your tenant.</span></span>
   - <span data-ttu-id="04d43-125">No campo **URL personalizada**, insira sua URL do Dataverse e inclua "/api/data/v9.1" no final.</span><span class="sxs-lookup"><span data-stu-id="04d43-125">In the **Custom URL** field, enter your Dataverse URL and append it with "/api/data/v9.1".</span></span>

8. <span data-ttu-id="04d43-126">Selecione **Verificar conexão** e finalize o processo de conexão.</span><span class="sxs-lookup"><span data-stu-id="04d43-126">Select **Check connection**, and finish the connection process.</span></span> 

   <span data-ttu-id="04d43-127">[![Botão Verificar conexão](./media/tax-service-setup-environment-for-mater-date-pic1.png)](./media/tax-service-setup-environment-for-mater-date-pic1.png)</span><span class="sxs-lookup"><span data-stu-id="04d43-127">[![Check connection button](./media/tax-service-setup-environment-for-mater-date-pic1.png)](./media/tax-service-setup-environment-for-mater-date-pic1.png)</span></span>

9. <span data-ttu-id="04d43-128">Acesse **Relatório Eletrônico** > **Configurações de imposto** e importe configurações de imposto em [Configurações de imposto](https://go.microsoft.com/fwlink/?linkid=2158352).</span><span class="sxs-lookup"><span data-stu-id="04d43-128">Go to **Electronic reporting** > **Tax configurations**, and import tax configurations from [Tax configurations](https://go.microsoft.com/fwlink/?linkid=2158352).</span></span>

   <span data-ttu-id="04d43-129">[![Página Configurações de imposto, árvore de modelo de dados de imposto](./media/tax-service-setup-environment-for-mater-date-pic2.png)](./media/tax-service-setup-environment-for-mater-date-pic2.png)</span><span class="sxs-lookup"><span data-stu-id="04d43-129">[![Tax configurations page, Tax data model tree](./media/tax-service-setup-environment-for-mater-date-pic2.png)](./media/tax-service-setup-environment-for-mater-date-pic2.png)</span></span>

10. <span data-ttu-id="04d43-130">Acesse **Mapeamento do modelo de documento tributável** ou **Mapeamento do modelo do Dataverse** se estiver usando uma configuração da Microsoft, e no campo **Aplicativo conectado**, selecione o registro criado na etapa 7.</span><span class="sxs-lookup"><span data-stu-id="04d43-130">Go to the **Taxable document model mapping**, or **Dataverse Model Mapping** if you are using a Microsoft configuration, and in the **Connected application** field, select the record that you created in step 7.</span></span>
11. <span data-ttu-id="04d43-131">Defina a opção **Padrão do mapeamento de modelo** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="04d43-131">Set **Default for model mapping** to **Yes**.</span></span>

   <span data-ttu-id="04d43-132">[![Página Mapeamento do modelo](./media/tax-service-setup-environment-for-mater-date-pic3.png)](./media/tax-service-setup-environment-for-mater-date-pic3.png)</span><span class="sxs-lookup"><span data-stu-id="04d43-132">[![Model mapping page](./media/tax-service-setup-environment-for-mater-date-pic3.png)](./media/tax-service-setup-environment-for-mater-date-pic3.png)</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
