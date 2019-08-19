---
title: Integração de dados quase em tempo real entre o Finance and Operations e o Common Data Service
description: Este tópico fornece uma visão geral da integração entre o Microsoft Dynamics 365 for Finance and Operations e o Common Data Service.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 07/15/2019
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
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: aa614c8e6a79a3f7a4f8f2f99f1f1bd1a67ac921
ms.sourcegitcommit: efcc0dee8bde5f8f93f6291e7f059ad426843e57
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/31/2019
ms.locfileid: "1797219"
---
# <a name="near-real-time-data-integration-between-finance-and-operations-and-common-data-service"></a><span data-ttu-id="67cde-103">Integração de dados quase em tempo real entre o Finance and Operations e o Common Data Service</span><span class="sxs-lookup"><span data-stu-id="67cde-103">Near-real-time data integration between Finance and Operations and Common Data Service</span></span>

[!include [banner](../includes/banner.md)]

[!include [preview](../includes/preview-banner.md)]

<span data-ttu-id="67cde-104">No mundo digital atual, os ecossistemas comerciais usam o conjunto de aplicativos do Microsoft Dynamics 365 como um todo.</span><span class="sxs-lookup"><span data-stu-id="67cde-104">In the current digital world, business ecosystems use the Microsoft Dynamics 365 suite as a whole.</span></span> <span data-ttu-id="67cde-105">Como os dados de dispositivos de contatos, clientes, operações e da Internet das Coisas (IoT) fluem para uma origem, há uma oportunidade de loops de comentários digitais.</span><span class="sxs-lookup"><span data-stu-id="67cde-105">Because data from people, customers, operations, and Internet of Things (IoT) devices flows into one source, there is an opportunity for digital feedback loops.</span></span> <span data-ttu-id="67cde-106">Para obter essa experiência, é essencial a integração entre aplicativos do Dynamics 365 for Finance and Operations e do Dynamics 365 for Customer Engagement.</span><span class="sxs-lookup"><span data-stu-id="67cde-106">To achieve this experience, integration between Dynamics 365 for Finance and Operations and Dynamics 365 for Customer Engagement applications is essential.</span></span> <span data-ttu-id="67cde-107">Os aplicativos de Customer Engagement são criados sobre o Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="67cde-107">Customer Engagement applications are built on top of Common Data Service.</span></span> <span data-ttu-id="67cde-108">A integração entre dados do Finance and Operations com o Common Data Service permite que aplicativos do Customer Engagement comuniquem-se de maneira coerente e fluente com o Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="67cde-108">Integration between Finance and Operations data with Common Data Service lets Customer Engagement applications communicate coherently and fluently with Finance and Operations.</span></span>

<span data-ttu-id="67cde-109">O Finance and Operations e o Common Data Service oferecem sincronização de dados quase em tempo real entre aplicativos do Finance and Operations e do Customer Engagement em uma estrutura de gravação dupla.</span><span class="sxs-lookup"><span data-stu-id="67cde-109">Finance and Operations and Common Data Service provide near-real-time data synchronization between Finance and Operations and Customer Engagement applications via a dual-write framework.</span></span> <span data-ttu-id="67cde-110">A cobertura é ampla e abrange 28 áreas de superfície do Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="67cde-110">The coverage is broad and spans 28 surface areas of Finance and Operations.</span></span> <span data-ttu-id="67cde-111">A meta é oferecer ao usuário uma experiência "One Dynamics 365" por meio de fluxos de dados contínuos que conectem processos de negócios em aplicativos.</span><span class="sxs-lookup"><span data-stu-id="67cde-111">The goal is to provide a "One Dynamics 365" user experience through seamless data flows that connect business processes across applications.</span></span>

![Diagrama de visão geral da arquitetura](media/dual-write-overview.jpg)

<span data-ttu-id="67cde-113">As seguintes propostas de valor estão disponíveis para clientes:</span><span class="sxs-lookup"><span data-stu-id="67cde-113">The following value propositions are available for customers:</span></span>

+ [<span data-ttu-id="67cde-114">Hierarquia da organização no Common Data Service</span><span class="sxs-lookup"><span data-stu-id="67cde-114">Organization hierarchy in Common Data Service</span></span>](dual-write-organization.md)
+ [<span data-ttu-id="67cde-115">Conceito de empresa no Common Data Service</span><span class="sxs-lookup"><span data-stu-id="67cde-115">Company concept in Common Data Service</span></span>](dual-write-company.md)
+ [<span data-ttu-id="67cde-116">Cliente mestre integrado</span><span class="sxs-lookup"><span data-stu-id="67cde-116">Integrated customer master</span></span>](dual-write-customer.md)
+ [<span data-ttu-id="67cde-117">Fornecedor mestre integrado</span><span class="sxs-lookup"><span data-stu-id="67cde-117">Integrated vendor master</span></span>](dual-write-vendor.md)
+ <span data-ttu-id="67cde-118">Produto mestre unificado</span><span class="sxs-lookup"><span data-stu-id="67cde-118">Unified product master</span></span>

## <a name="system-requirements"></a><span data-ttu-id="67cde-119">Requisitos do sistema</span><span class="sxs-lookup"><span data-stu-id="67cde-119">System requirements</span></span>

<span data-ttu-id="67cde-120">Fluxos de dados assíncronos, bidirecionais quase em tempo real exigem as seguintes versões:</span><span class="sxs-lookup"><span data-stu-id="67cde-120">Synchronous, bidirectional, near-real-time data flows require the following versions:</span></span>

+ <span data-ttu-id="67cde-121">Microsoft Dynamics 365 for Finance and Operations versão 10.0.4 (julho de 2019) com atualização da plataforma 28 ou posterior</span><span class="sxs-lookup"><span data-stu-id="67cde-121">Microsoft Dynamics 365 for Finance and Operations version 10.0.4 (July 2019) with Platform update 28, or later</span></span>
+ <span data-ttu-id="67cde-122">Microsoft Dynamics 365 for Customer Engagement, versão de plataforma 9.1 (4.2) ou posterior</span><span class="sxs-lookup"><span data-stu-id="67cde-122">Microsoft Dynamics 365 for Customer Engagement, Platform version 9.1 (4.2) or later</span></span>

## <a name="setup-instructions"></a><span data-ttu-id="67cde-123">Instruções de configuração</span><span class="sxs-lookup"><span data-stu-id="67cde-123">Setup instructions</span></span>

<span data-ttu-id="67cde-124">Siga estas etapas para configurar a integração entre o Finance and Operations e o Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="67cde-124">Follow these steps to set up integration between Finance and Operations and Common Data Service.</span></span>
    
1. <span data-ttu-id="67cde-125">Para a configuração do sistema de gravação dupla, consulte [guia passo a passo](https://aka.ms/dualwrite-docs) Anunciando a exibição de gravação dupla.</span><span class="sxs-lookup"><span data-stu-id="67cde-125">For the setup of the dual-write system, see the [step-by-step guide](https://aka.ms/dualwrite-docs) on Announcing Dual Write Preview.</span></span>
2. <span data-ttu-id="67cde-126">Baixe e instale a solução do grupo [Finance and Operations, Common Data Service e Customer Engagement Integration](https://www.yammer.com/dynamicsaxfeedbackprograms/#/threads/inGroup?type=in_group&feedId=66052096) Yammer.</span><span class="sxs-lookup"><span data-stu-id="67cde-126">Download and install the solution from the [Finance and Operations, Common Data Service, and Customer Engagement Integration](https://www.yammer.com/dynamicsaxfeedbackprograms/#/threads/inGroup?type=in_group&feedId=66052096) Yammer group.</span></span> <span data-ttu-id="67cde-127">O pacote contém cinco soluções:</span><span class="sxs-lookup"><span data-stu-id="67cde-127">The package contains five solutions:</span></span>

    + <span data-ttu-id="67cde-128">Dynamics365Company</span><span class="sxs-lookup"><span data-stu-id="67cde-128">Dynamics365Company</span></span>
    + <span data-ttu-id="67cde-129">CurrencyExchangeRates</span><span class="sxs-lookup"><span data-stu-id="67cde-129">CurrencyExchangeRates</span></span>
    + <span data-ttu-id="67cde-130">Dynamics365FinanceAndOperationsCommon</span><span class="sxs-lookup"><span data-stu-id="67cde-130">Dynamics365FinanceAndOperationsCommon</span></span>
    + <span data-ttu-id="67cde-131">Dynamics365FinanceCommon</span><span class="sxs-lookup"><span data-stu-id="67cde-131">Dynamics365FinanceCommon</span></span>
    + <span data-ttu-id="67cde-132">Dynamics365SupplyChainCommon</span><span class="sxs-lookup"><span data-stu-id="67cde-132">Dynamics365SupplyChainCommon</span></span>

3. <span data-ttu-id="67cde-133">Siga a ordem de execução para [sincronizar dados iniciais de referência](dual-write-initial.md).</span><span class="sxs-lookup"><span data-stu-id="67cde-133">Follow the execution order for [synchronizing initial reference data](dual-write-initial.md).</span></span>
4. <span data-ttu-id="67cde-134">Se você encontrar problemas de sincronização de gravação dupla, consulte o [Guia de solução de problemas de integração de dados](dual-write-troubleshooting.md).</span><span class="sxs-lookup"><span data-stu-id="67cde-134">If you encounter dual-write synchronization issues, see the [Troubleshooting guide for data integration](dual-write-troubleshooting.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="67cde-135">Você não pode executar a gravação dupla e o [Prospect to cash](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/accounts-template-mapping-direct) lado a lado.</span><span class="sxs-lookup"><span data-stu-id="67cde-135">You can’t run dual-write and [Prospect to cash](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/accounts-template-mapping-direct) side-by-side.</span></span> <span data-ttu-id="67cde-136">Se você estiver executando a solução Prospect to cash, desinstale-a.</span><span class="sxs-lookup"><span data-stu-id="67cde-136">If you're running the Prospect to cash solution, you must uninstall it.</span></span> <span data-ttu-id="67cde-137">Você também pode desativar os modelos de gravação dupla para clientes e fornecedores que fazem parte da solução Prospect to cash.</span><span class="sxs-lookup"><span data-stu-id="67cde-137">You must also disable the customer and vendor dual-write templates that are part of the Prospect to cash solution.</span></span>
