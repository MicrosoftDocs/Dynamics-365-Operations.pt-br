---
title: Visão geral do gerenciamento de depósito
description: Use o gerenciamento de depósito para monitorar e automatizar os processos de depósito.
author: ShylaThompson
manager: tfehr
ms.date: 04/20/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSParameters, WHSWorkPool
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ad0659a86e75dc4a5a204ebc05405f62abf2ca1e
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "4422562"
---
# <a name="warehouse-management-overview"></a><span data-ttu-id="ade11-103">Visão geral de gerenciamento de depósito</span><span class="sxs-lookup"><span data-stu-id="ade11-103">Warehouse management overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ade11-104">O módulo de gerenciamento de depósito permite gerenciar processos de depósito na fabricação, na distribuição e nas empresas de varejo.</span><span class="sxs-lookup"><span data-stu-id="ade11-104">The Warehouse management module lets you manage warehouse processes in manufacturing, distribution, and retail companies.</span></span> <span data-ttu-id="ade11-105">Este módulo tem uma grande variedade de recursos para suportar a instalação de depósito em nível ideal, a qualquer momento.</span><span class="sxs-lookup"><span data-stu-id="ade11-105">This module has a wide range of features to support the warehouse facility at an optimal level, at any time.</span></span> <span data-ttu-id="ade11-106">O gerenciamento de depósito é totalmente integrado aos outros processos de negócios, como transporte, fabricação, controle de qualidade, compras, transferência, vendas e devoluções.</span><span class="sxs-lookup"><span data-stu-id="ade11-106">Warehouse management is fully integrated with other business processes such as transportation, manufacturing, quality control, purchase, transfer, sales, and returns.</span></span>

## <a name="get-started"></a><span data-ttu-id="ade11-107">Introdução</span><span class="sxs-lookup"><span data-stu-id="ade11-107">Get started</span></span>
<span data-ttu-id="ade11-108">Para começar o Gerenciamento de depósito, é necessário concluir a configuração dos parâmetro gerais do depósito para suportar os processos de negócios de sua empresa.</span><span class="sxs-lookup"><span data-stu-id="ade11-108">To start working with Warehouse management, you need to complete the setup of the general warehouse parameters to support the business processes of your company.</span></span>

- <span data-ttu-id="ade11-109">Vá até a página **Parâmetros de gerenciamento de depósito** em **Gerenciamento de depósito** > **Configuração** para configurar os parâmetros gerais do depósito.</span><span class="sxs-lookup"><span data-stu-id="ade11-109">Go to the **Warehouse management parameters** page under **Warehouse management** > **Setup** to set up general warehouse parameters.</span></span>

<span data-ttu-id="ade11-110">É necessário configurar os componentes de fluxos de trabalho do processo de entrada e saída do depósito, de acordo com os requisitos de negócios.</span><span class="sxs-lookup"><span data-stu-id="ade11-110">You must configure components for inbound and outbound warehouse process workflows according to business requirements.</span></span> <span data-ttu-id="ade11-111">Os componentes mais importantes que você deve configurar são os modelos de onda, modelos de trabalho, grupos de trabalho, bem como diretivas de localização.</span><span class="sxs-lookup"><span data-stu-id="ade11-111">The most important components that you must configure are wave templates, work templates, work pools, and location directives.</span></span>

- [<span data-ttu-id="ade11-112">Visão geral de configuração de depósito</span><span class="sxs-lookup"><span data-stu-id="ade11-112">Warehouse configuration overview</span></span>](warehouse-configuration.md)
- [<span data-ttu-id="ade11-113">Controlar o trabalho do depósito por meio de modelos de trabalho e diretivas de localização</span><span class="sxs-lookup"><span data-stu-id="ade11-113">Control warehouse work by using work templates and location directives</span></span>](control-warehouse-location-directives.md)
- [<span data-ttu-id="ade11-114">Configurar dispositivos móveis para trabalho de depósito</span><span class="sxs-lookup"><span data-stu-id="ade11-114">Set up mobile devices for warehouse work</span></span>](configure-mobile-devices-warehouse.md)
- [<span data-ttu-id="ade11-115">Configurar uma diretiva de localização para o armazenamento da ordem de compra</span><span class="sxs-lookup"><span data-stu-id="ade11-115">Set up a location directive for purchase order put-away</span></span>](../transportation/tasks/set-up-location-directive-purchase-order-put-away.md)
- [<span data-ttu-id="ade11-116">Configurar um modelo de trabalho para ordens de compra</span><span class="sxs-lookup"><span data-stu-id="ade11-116">Set up a work template for purchase orders</span></span>](./tasks/set-up-work-template-purchase-orders.md)

## <a name="warehouse-management-processes"></a><span data-ttu-id="ade11-117">Processos de gerenciamento de depósito</span><span class="sxs-lookup"><span data-stu-id="ade11-117">Warehouse management processes</span></span>
- <span data-ttu-id="ade11-118">Suporte integrada para documentos de origem para ordens de venda, devoluções, ordens de transferência, ordens de produção e kanban</span><span class="sxs-lookup"><span data-stu-id="ade11-118">Integrated support for source documents for sales orders, returns, transfer orders, production orders, and kanban</span></span>  
- <span data-ttu-id="ade11-119">Suporte flexível, fluxo de trabalho do material de entrada e saída com base em consultas</span><span class="sxs-lookup"><span data-stu-id="ade11-119">Flexible, inbound and outbound material workflow support based on queries</span></span>
- <span data-ttu-id="ade11-120">Integração completa com as ofertas de fabricação e transporte</span><span class="sxs-lookup"><span data-stu-id="ade11-120">Full integration with the Manufacturing and Transportation offerings</span></span>
- <span data-ttu-id="ade11-121">Controle total de limites de estoque de local e de volumetria de localização</span><span class="sxs-lookup"><span data-stu-id="ade11-121">Full control of location stocking limits and location volumetrics</span></span>
- <span data-ttu-id="ade11-122">Propriedades de estoque controladas por status de estoque</span><span class="sxs-lookup"><span data-stu-id="ade11-122">Inventory properties controlled by inventory status</span></span>
- <span data-ttu-id="ade11-123">Suporte completo de lote e de série</span><span class="sxs-lookup"><span data-stu-id="ade11-123">Full batch and serial item support</span></span>
- <span data-ttu-id="ade11-124">Vários recursos de recebimento de item</span><span class="sxs-lookup"><span data-stu-id="ade11-124">Various item receiving capabilities</span></span>
- <span data-ttu-id="ade11-125">Várias estratégias de separação</span><span class="sxs-lookup"><span data-stu-id="ade11-125">Multiple picking strategies</span></span>
- <span data-ttu-id="ade11-126">Suporte pronto para uso da próxima geração do scanner de código de barras</span><span class="sxs-lookup"><span data-stu-id="ade11-126">Out-of-the-box support for the next generation of barcode scanners</span></span>
- <span data-ttu-id="ade11-127">Tipos de palete/contêiner para processos de depósito</span><span class="sxs-lookup"><span data-stu-id="ade11-127">Pallet/container types for warehouse processes</span></span>
- <span data-ttu-id="ade11-128">Recursos avançados de contagem</span><span class="sxs-lookup"><span data-stu-id="ade11-128">Advanced counting capabilities</span></span>
- <span data-ttu-id="ade11-129">Impressão e roteamento de etiqueta com suporte para Zebra ZPL</span><span class="sxs-lookup"><span data-stu-id="ade11-129">Label printing and label routing with Zebra ZPL support</span></span>
- <span data-ttu-id="ade11-130">Integração do Business intelligence ao Power BI</span><span class="sxs-lookup"><span data-stu-id="ade11-130">Business intelligence integration into Power BI</span></span>
- <span data-ttu-id="ade11-131">Movimentação de estoque manual e automática</span><span class="sxs-lookup"><span data-stu-id="ade11-131">Manual and automatic movement of inventory</span></span>
- <span data-ttu-id="ade11-132">Controle de qualidade totalmente integrado (QMS)</span><span class="sxs-lookup"><span data-stu-id="ade11-132">Fully-integrated quality control (QMS)</span></span>
- <span data-ttu-id="ade11-133">Rastreabilidade total de manuseio de material dos trabalhadores</span><span class="sxs-lookup"><span data-stu-id="ade11-133">Full traceability of workers' material handling</span></span>
- <span data-ttu-id="ade11-134">Processamento de onda de saída</span><span class="sxs-lookup"><span data-stu-id="ade11-134">Outbound wave processing</span></span>
- <span data-ttu-id="ade11-135">Embalagem manual e suporte a transporte em contêineres automático</span><span class="sxs-lookup"><span data-stu-id="ade11-135">Manual packing and automatic containerization support</span></span>
- <span data-ttu-id="ade11-136">Separação de cluster</span><span class="sxs-lookup"><span data-stu-id="ade11-136">Cluster picking</span></span>
- <span data-ttu-id="ade11-137">Distribuição integrada simples</span><span class="sxs-lookup"><span data-stu-id="ade11-137">Simple cross docking</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ade11-138">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="ade11-138">Additional resources</span></span>
### <a name="whats-new-and-in-development"></a><span data-ttu-id="ade11-139">Novidades e o que está em desenvolvimento</span><span class="sxs-lookup"><span data-stu-id="ade11-139">What's new and in development</span></span>
<span data-ttu-id="ade11-140">Visite o [Roteiro do Microsoft Dynamics 365](https://roadmap.dynamics.com/) para conferir os novos recursos que foram lançados e os novos recursos em desenvolvimento.</span><span class="sxs-lookup"><span data-stu-id="ade11-140">Go to the [Microsoft Dynamics 365 Roadmap](https://roadmap.dynamics.com/) to see what new features have been released and what new features are in development.</span></span>

### <a name="blogs"></a><span data-ttu-id="ade11-141">Blogs</span><span class="sxs-lookup"><span data-stu-id="ade11-141">Blogs</span></span>
<span data-ttu-id="ade11-142">Você encontra opiniões, notícias, além de informações sobre o Gerenciamento de depósitos e outras soluções no [blog do Microsoft Dynamics 365](https://community.dynamics.com/b/msftdynamicsblog).</span><span class="sxs-lookup"><span data-stu-id="ade11-142">You can find opinions, news, and other information about Warehouse management and other solutions on the [Microsoft Dynamics 365 blog](https://community.dynamics.com/b/msftdynamicsblog).</span></span>


 

