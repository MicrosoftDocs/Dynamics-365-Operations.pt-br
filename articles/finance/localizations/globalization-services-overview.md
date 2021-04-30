---
title: Serviços de globalização do Dynamics 365
description: Este tópico oferece uma visão geral de serviços de globalização do Microsoft Dynamics 365.
author: JaneA07
manager: AnnBe
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RCS, Regulatory Configuration Services, Localization, Electronic invoicing, Tax calculation
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-02-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: 8c6f3b7fb4dec0dffe55014e9e2d60620dc3b193
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/13/2021
ms.locfileid: "5893039"
---
# <a name="dynamics-365-globalization-services"></a><span data-ttu-id="03dc5-103">Serviços de globalização do Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="03dc5-103">Dynamics 365 globalization services</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="03dc5-104">Os seguintes serviços de globalização podem ser configurados para estender os recursos existentes em alguns serviços do Microsoft Dynamics 365 Online:</span><span class="sxs-lookup"><span data-stu-id="03dc5-104">The following globalization services can be configured to extend the capabilities that exist in some Microsoft Dynamics 365 online services:</span></span>

- <span data-ttu-id="03dc5-105">O **Regulatory Configuration Service (RCS)** oferece suporte à configuração de diferentes tipos de documentos eletrônicos e relatórios.</span><span class="sxs-lookup"><span data-stu-id="03dc5-105">**Regulatory Configuration Service (RCS)** supports the configuration of different types of electronic documents and reports.</span></span> <span data-ttu-id="03dc5-106">O RCS fornece uma versão aprimorada do designer de Relatório Eletrônico (ER) em que o repositório de configuração é um serviço autônomo.</span><span class="sxs-lookup"><span data-stu-id="03dc5-106">RCS provides an enhanced version of the Electronic reporting (ER) designer where the configuration repository is a standalone service.</span></span> <span data-ttu-id="03dc5-107">Para obter mais informações, consulte [Regulatory Configuration Service](rcs-overview.md).</span><span class="sxs-lookup"><span data-stu-id="03dc5-107">For more information, see [Regulatory Configuration Service](rcs-overview.md).</span></span>
- <span data-ttu-id="03dc5-108">O **faturamento eletrônico** reúne formatos configuráveis para transformações, assinaturas digitais e integrações configuráveis para a conectividade com serviços Web externos, incluindo a certificação e o tratamento de respostas.</span><span class="sxs-lookup"><span data-stu-id="03dc5-108">**Electronic Invoicing** brings together configurable formats for transformations, digital signatures, and configurable integrations for connectivity with external web services, including certification and response handling.</span></span> <span data-ttu-id="03dc5-109">Para obter mais informações, consulte [Faturamento Eletrônico](e-invoicing-service-overview.md).</span><span class="sxs-lookup"><span data-stu-id="03dc5-109">For more information, see [Electronic Invoicing](e-invoicing-service-overview.md).</span></span>
- <span data-ttu-id="03dc5-110">O **Cálculo de Imposto** oferece maior flexibilidade, dando suporte a várias IDs de imposto, determinação de código de imposto, designer de cálculo de imposto e um mecanismo de tempo de execução para atender a regulamentações de impostos complexas no mundo inteiro.</span><span class="sxs-lookup"><span data-stu-id="03dc5-110">**Tax Calculation** provides enhanced flexibility by supporting multiple tax IDs, tax code determination, the tax calculation designer, and a runtime engine to comply with complex tax regulations worldwide.</span></span> <span data-ttu-id="03dc5-111">Para obter mais informações, consulte [Cálculo de Imposto](global-tax-calcuation-service-overview.md).</span><span class="sxs-lookup"><span data-stu-id="03dc5-111">For more information, see [Tax Calculation](global-tax-calcuation-service-overview.md).</span></span>

<span data-ttu-id="03dc5-112">Esses serviços de globalização fornecem integração imediata com os serviços online do Dynamics 365 a seguir.</span><span class="sxs-lookup"><span data-stu-id="03dc5-112">These globalization services provide out-of-box integration with the following Dynamics 365 online services.</span></span>

| <span data-ttu-id="03dc5-113">Serviço online</span><span class="sxs-lookup"><span data-stu-id="03dc5-113">Online service</span></span> | <span data-ttu-id="03dc5-114">SCR</span><span class="sxs-lookup"><span data-stu-id="03dc5-114">RCS</span></span> | <span data-ttu-id="03dc5-115">Faturamento Eletrônico</span><span class="sxs-lookup"><span data-stu-id="03dc5-115">Electronic Invoicing</span></span> | <span data-ttu-id="03dc5-116">Cálculo de Imposto (Versão preliminar)</span><span class="sxs-lookup"><span data-stu-id="03dc5-116">Tax Calculation (Preview)</span></span> |
|----------------|-----|----------------------|---------------------------|
| <span data-ttu-id="03dc5-117">Dynamics 365 Finance</span><span class="sxs-lookup"><span data-stu-id="03dc5-117">Dynamics 365 Finance</span></span> | <span data-ttu-id="03dc5-118">Sim</span><span class="sxs-lookup"><span data-stu-id="03dc5-118">Yes</span></span> | <span data-ttu-id="03dc5-119">Sim</span><span class="sxs-lookup"><span data-stu-id="03dc5-119">Yes</span></span> | <span data-ttu-id="03dc5-120">Sim</span><span class="sxs-lookup"><span data-stu-id="03dc5-120">Yes</span></span> | 
| <span data-ttu-id="03dc5-121">Dynamics 365 Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="03dc5-121">Dynamics 365 Supply Chain Management</span></span> | <span data-ttu-id="03dc5-122">Sim</span><span class="sxs-lookup"><span data-stu-id="03dc5-122">Yes</span></span> | <span data-ttu-id="03dc5-123">Sim</span><span class="sxs-lookup"><span data-stu-id="03dc5-123">Yes</span></span> | <span data-ttu-id="03dc5-124">Sim</span><span class="sxs-lookup"><span data-stu-id="03dc5-124">Yes</span></span> | 
| <span data-ttu-id="03dc5-125">Dynamics 365 Project Operations</span><span class="sxs-lookup"><span data-stu-id="03dc5-125">Dynamics 365 Project Operations</span></span> | <span data-ttu-id="03dc5-126">Sim</span><span class="sxs-lookup"><span data-stu-id="03dc5-126">Yes</span></span> | <span data-ttu-id="03dc5-127">Sim</span><span class="sxs-lookup"><span data-stu-id="03dc5-127">Yes</span></span> | <span data-ttu-id="03dc5-128">Não Aplicável</span><span class="sxs-lookup"><span data-stu-id="03dc5-128">Not applicable</span></span> | 
| <span data-ttu-id="03dc5-129">Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="03dc5-129">Dynamics 365 Commerce</span></span> | <span data-ttu-id="03dc5-130">Sim</span><span class="sxs-lookup"><span data-stu-id="03dc5-130">Yes</span></span> | <span data-ttu-id="03dc5-131">Não Aplicável</span><span class="sxs-lookup"><span data-stu-id="03dc5-131">Not applicable</span></span> | <span data-ttu-id="03dc5-132">Não Aplicável</span><span class="sxs-lookup"><span data-stu-id="03dc5-132">Not applicable</span></span> | 

> [!NOTE]
> <span data-ttu-id="03dc5-133">Devido a diferenças na disponibilidade das localizações geográficas do Azure (áreas geográficas) para RCS, a configuração desse serviço pode fazer com que dados do cliente sejam transferidos para fora da área geográfica selecionada para o serviço online do Dynamics 365 aplicável.</span><span class="sxs-lookup"><span data-stu-id="03dc5-133">Because of differences in the availability of Azure geographic locations (geos) for RCS, configuration of this service might cause customer data to be transferred outside the geo that is selected for the applicable Dynamics 365 online service.</span></span> <span data-ttu-id="03dc5-134">Para obter mais informações, consulte [Dynamics 365 e Power Platform: disponibilidade, local de dados, idioma e localização](https://aka.ms/rcs/D365Productavailabilityguide).</span><span class="sxs-lookup"><span data-stu-id="03dc5-134">For more information, see [Dynamics 365 and Power Platform: Availability, data location, language, and localization](https://aka.ms/rcs/D365Productavailabilityguide).</span></span>