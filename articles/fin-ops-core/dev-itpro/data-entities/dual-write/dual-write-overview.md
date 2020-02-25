---
title: Integração de dados quase em tempo real com o Common Data Service
description: Este tópico fornece uma visão geral da integração entre o Finance and Operations e o Common Data Service.
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
ms.openlocfilehash: 1c09b0c0bb695e7695acb7a8821ffb99ae1f6f06
ms.sourcegitcommit: 54baab2a04e5c534fc2d1fd67b67e23a152d4e57
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "3019642"
---
# <a name="near-real-time-data-integration-with-common-data-service"></a><span data-ttu-id="d5813-103">Integração de dados quase em tempo real com o Common Data Service</span><span class="sxs-lookup"><span data-stu-id="d5813-103">Near-real-time data integration with Common Data Service</span></span>

[!include [banner](../../includes/banner.md)]

[!include [preview-banner](../../includes/preview-banner.md)]

<span data-ttu-id="d5813-104">No mundo digital atual, os ecossistemas comerciais usam os aplicativos do Microsoft Dynamics 365 como um todo.</span><span class="sxs-lookup"><span data-stu-id="d5813-104">In the current digital world, business ecosystems use Microsoft Dynamics 365 applications as a whole.</span></span> <span data-ttu-id="d5813-105">Como os dados de dispositivos de contatos, clientes, operações e da Internet das Coisas (IoT) fluem para uma origem, há uma oportunidade de loops de comentários digitais.</span><span class="sxs-lookup"><span data-stu-id="d5813-105">Because data from people, customers, operations, and Internet of Things (IoT) devices flows into one source, there is an opportunity for digital feedback loops.</span></span> <span data-ttu-id="d5813-106">Para obter essa experiência, a integração entre os aplicativos do Finance and Operations e outros aplicativos do Dynamics 365 é essencial.</span><span class="sxs-lookup"><span data-stu-id="d5813-106">To achieve this experience, integration between Finance and Operations apps and other Dynamics 365 applications is essential.</span></span> <span data-ttu-id="d5813-107">Alguns aplicativos são desenvolvidos com base no Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="d5813-107">Some applications are built on top of Common Data Service.</span></span> <span data-ttu-id="d5813-108">A integração entre dados de aplicativos do Finance and Operations com o Common Data Service permite que outros aplicativos se comuniquem de maneira coerente e fluente com o Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d5813-108">Integration between Finance and Operations apps data with Common Data Service lets other applications communicate coherently and fluently with Finance and Operations.</span></span>

<span data-ttu-id="d5813-109">Os aplicativos do Finance and Operations e o Common Data Service oferecem sincronização de dados quase em tempo real entre aplicativos do Finance and Operations e outros aplicativos do Dynamics 365 por meio de uma estrutura de gravação dupla.</span><span class="sxs-lookup"><span data-stu-id="d5813-109">Finance and Operations apps and Common Data Service provide near-real-time data synchronization between Finance and Operations apps and other Dynamics 365 applications via a dual-write framework.</span></span> <span data-ttu-id="d5813-110">A cobertura é ampla e abrange 28 áreas de superfície do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="d5813-110">The coverage is broad and spans 28 surface areas of the application.</span></span> <span data-ttu-id="d5813-111">A meta é oferecer ao usuário uma experiência "One Dynamics 365" por meio de fluxos de dados contínuos que conectem processos de negócios em aplicativos.</span><span class="sxs-lookup"><span data-stu-id="d5813-111">The goal is to provide a "One Dynamics 365" user experience through seamless data flows that connect business processes across applications.</span></span>

![Diagrama de visão geral da arquitetura](media/dual-write-overview.jpg)

<span data-ttu-id="d5813-113">As seguintes propostas de valor estão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="d5813-113">The following value propositions are available:</span></span>

+ [<span data-ttu-id="d5813-114">Hierarquia da organização no Common Data Service</span><span class="sxs-lookup"><span data-stu-id="d5813-114">Organization hierarchy in Common Data Service</span></span>](organization-mapping.md)
+ [<span data-ttu-id="d5813-115">Conceito de empresa no Common Data Service</span><span class="sxs-lookup"><span data-stu-id="d5813-115">Company concept in Common Data Service</span></span>](company-data.md)
+ [<span data-ttu-id="d5813-116">Cliente mestre integrado</span><span class="sxs-lookup"><span data-stu-id="d5813-116">Integrated customer master</span></span>](customer-mapping.md)
+ [<span data-ttu-id="d5813-117">Razão integrado</span><span class="sxs-lookup"><span data-stu-id="d5813-117">Integrated ledger</span></span>](ledger-mapping.md)
+ [<span data-ttu-id="d5813-118">Experiência unificada de produto</span><span class="sxs-lookup"><span data-stu-id="d5813-118">Unified product experience</span></span>](product-mapping.md)
+ [<span data-ttu-id="d5813-119">Fornecedor mestre integrado</span><span class="sxs-lookup"><span data-stu-id="d5813-119">Integrated vendor master</span></span>](vendor-mapping.md)
+ [<span data-ttu-id="d5813-120">Sites e depósitos integrados</span><span class="sxs-lookup"><span data-stu-id="d5813-120">Integrated sites and warehouses</span></span>](sites-warehouses-mapping.md)
+ [<span data-ttu-id="d5813-121">Mestre de imposto integrado</span><span class="sxs-lookup"><span data-stu-id="d5813-121">Integrated tax master</span></span>](tax-mapping.md)

## <a name="system-requirements"></a><span data-ttu-id="d5813-122">Requisitos do sistema</span><span class="sxs-lookup"><span data-stu-id="d5813-122">System requirements</span></span>

<span data-ttu-id="d5813-123">Fluxos de dados assíncronos, bidirecionais quase em tempo real exigem as seguintes versões:</span><span class="sxs-lookup"><span data-stu-id="d5813-123">Synchronous, bidirectional, near-real-time data flows require the following versions:</span></span>

+ <span data-ttu-id="d5813-124">Microsoft Dynamics 365 for Finance and Operations versão 10.0.4 (julho de 2019) com atualização da plataforma 28 ou posterior</span><span class="sxs-lookup"><span data-stu-id="d5813-124">Microsoft Dynamics 365 for Finance and Operations version 10.0.4 (July 2019) with Platform update 28, or later</span></span>
+ <span data-ttu-id="d5813-125">Microsoft Dynamics 365 for Customer Engagement, versão de plataforma 9.1 (4.2) ou posterior</span><span class="sxs-lookup"><span data-stu-id="d5813-125">Microsoft Dynamics 365 for Customer Engagement, Platform version 9.1 (4.2) or later</span></span>

## <a name="setup-instructions"></a><span data-ttu-id="d5813-126">Instruções de configuração</span><span class="sxs-lookup"><span data-stu-id="d5813-126">Setup instructions</span></span>

<span data-ttu-id="d5813-127">Siga estas etapas para configurar a integração entre aplicativos do Finance and Operations e o Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="d5813-127">Follow these steps to set up integration between Finance and Operations apps and Common Data Service.</span></span>
    
1. <span data-ttu-id="d5813-128">Para a configuração do sistema de gravação dupla, consulte [guia passo a passo](https://aka.ms/dualwrite-docs) Anunciando a exibição de gravação dupla.</span><span class="sxs-lookup"><span data-stu-id="d5813-128">For the setup of the dual-write system, see the [step-by-step guide](https://aka.ms/dualwrite-docs) on Announcing Dual Write Preview.</span></span>
2. <span data-ttu-id="d5813-129">Baixe e instale a solução a partir do grupo [Integração com Fin Ops e CDS/CE por meio de gravação dupla](https://www.yammer.com/dynamicsaxfeedbackprograms/#/threads/inGroup?type=in_group&feedId=66052096)Yammer.</span><span class="sxs-lookup"><span data-stu-id="d5813-129">Download and install the solution from the [Fin Ops and CDS/CE Integration via Dual-Write](https://www.yammer.com/dynamicsaxfeedbackprograms/#/threads/inGroup?type=in_group&feedId=66052096) Yammer group.</span></span> <span data-ttu-id="d5813-130">O pacote contém cinco soluções:</span><span class="sxs-lookup"><span data-stu-id="d5813-130">The package contains five solutions:</span></span>

    + <span data-ttu-id="d5813-131">Dynamics365Company</span><span class="sxs-lookup"><span data-stu-id="d5813-131">Dynamics365Company</span></span>
    + <span data-ttu-id="d5813-132">CurrencyExchangeRates</span><span class="sxs-lookup"><span data-stu-id="d5813-132">CurrencyExchangeRates</span></span>
    + <span data-ttu-id="d5813-133">Dynamics365FinanceAndOperationsCommon</span><span class="sxs-lookup"><span data-stu-id="d5813-133">Dynamics365FinanceAndOperationsCommon</span></span>
    + <span data-ttu-id="d5813-134">Dynamics365FinanceCommon</span><span class="sxs-lookup"><span data-stu-id="d5813-134">Dynamics365FinanceCommon</span></span>
    + <span data-ttu-id="d5813-135">Dynamics365SupplyChainCommon</span><span class="sxs-lookup"><span data-stu-id="d5813-135">Dynamics365SupplyChainCommon</span></span>

3. <span data-ttu-id="d5813-136">Siga a ordem de execução para [sincronizar dados iniciais de referência](initial-sync.md).</span><span class="sxs-lookup"><span data-stu-id="d5813-136">Follow the execution order for [synchronizing initial reference data](initial-sync.md).</span></span>
4. <span data-ttu-id="d5813-137">Se você encontrar problemas de sincronização de gravação dupla, consulte o [Guia de solução de problemas de integração de dados](dual-write-troubleshooting.md).</span><span class="sxs-lookup"><span data-stu-id="d5813-137">If you encounter dual-write synchronization issues, see the [Troubleshooting guide for data integration](dual-write-troubleshooting.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d5813-138">Você não pode executar a gravação dupla e o [Prospect to cash](../../../../supply-chain/sales-marketing/prospect-to-cash.md) lado a lado.</span><span class="sxs-lookup"><span data-stu-id="d5813-138">You can’t run dual-write and [Prospect to cash](../../../../supply-chain/sales-marketing/prospect-to-cash.md) side-by-side.</span></span> <span data-ttu-id="d5813-139">Se você estiver executando a solução Prospect to cash, desinstale-a.</span><span class="sxs-lookup"><span data-stu-id="d5813-139">If you're running the Prospect to cash solution, you must uninstall it.</span></span> <span data-ttu-id="d5813-140">Você também pode desativar os modelos de gravação dupla para clientes e fornecedores que fazem parte da solução Prospect to cash.</span><span class="sxs-lookup"><span data-stu-id="d5813-140">You must also disable the customer and vendor dual-write templates that are part of the Prospect to cash solution.</span></span>
