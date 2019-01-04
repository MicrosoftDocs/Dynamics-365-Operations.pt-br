---
title: Avaliar lucratividade do cliente e do produto
description: "Este artigo explica como você pode usar a análise na memória e em tempo real para acessar, explorar e obter informações sobre clientes e lucratividade de produto com base nos dados do Microsoft Dynamics 365 for Retail."
author: ashishmsft
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: SysOperationsTemplateForm, RetailStoreManagementWorkspace
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 52902
ms.assetid: 1a77d04b-2985-4bee-9138-c216fe0483de
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 190d0b59ad2e232b33b3c0d1700cbaf95c45aeca
ms.openlocfilehash: 28d4eeaa3fcae33f817690ad496b4b123a5838ce
ms.contentlocale: pt-br
ms.lasthandoff: 01/04/2019

---

# <a name="assess-customer-and-product-profitability"></a><span data-ttu-id="3d266-103">Avaliar a lucratividade dos clientes e dos produtos</span><span class="sxs-lookup"><span data-stu-id="3d266-103">Assess customer and product profitability</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="3d266-104">Este artigo explica como você pode usar a análise na memória e em tempo real para acessar, explorar e obter informações sobre clientes e lucratividade de produto com base nos dados do Microsoft Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="3d266-104">This article explains how you can use the in-memory and real-time analytics to access, explore, and gain insight about customers and product profitability from your Microsoft Dynamics 365 for Retail data.</span></span>

<span data-ttu-id="3d266-105">Como parte do Dynamics 365 for Retail, os usuários podem estudar a lucratividade dos melhores clientes (10 a 100) nos diferentes níveis da hierarquia organizacional, com base em um dos seguintes critérios:</span><span class="sxs-lookup"><span data-stu-id="3d266-105">As part of Dynamics 365 for Retail, users can study profitability for the top customers (10 to 100) across different levels of the organization hierarchy, based on one of the following criteria:</span></span>

- <span data-ttu-id="3d266-106">Valor de venda</span><span class="sxs-lookup"><span data-stu-id="3d266-106">Sales amount</span></span>
- <span data-ttu-id="3d266-107">Quantidade</span><span class="sxs-lookup"><span data-stu-id="3d266-107">Quantity</span></span>
- <span data-ttu-id="3d266-108">Margem de lucro bruto</span><span class="sxs-lookup"><span data-stu-id="3d266-108">Gross profit margin</span></span>
- <span data-ttu-id="3d266-109">Percentual de margem</span><span class="sxs-lookup"><span data-stu-id="3d266-109">Margin percentage</span></span>

<span data-ttu-id="3d266-110">Nesta avaliação, você pode usar o relatório predefinido de **Melhores clientes**, que pode ser aberto em qualquer um destes locais:</span><span class="sxs-lookup"><span data-stu-id="3d266-110">For this assessment, you can use the out-of-box **Top customers** report, which you can open from any of the following locations:</span></span>

- <span data-ttu-id="3d266-111">Área de trabalho **Gerenciamento de loja de varejo** &gt; **Varejo** &gt; **Canais** &gt; **Gerenciamento de loja de varejo** &gt; **Relatórios** &gt; **Relatório de melhores clientes**</span><span class="sxs-lookup"><span data-stu-id="3d266-111">**Retail store management** workspace &gt; **Retail** &gt; **Channels** &gt; **Retail store management** &gt; **Reports** &gt; **Top customers report**</span></span>
- <span data-ttu-id="3d266-112">Seção **Consultas e relatórios** &gt; **Varejo** &gt; **Consultas e relatórios** &gt; **Relatórios de vendas** &gt; **Relatório de melhores clientes**</span><span class="sxs-lookup"><span data-stu-id="3d266-112">**Inquiries and reports** section &gt; **Retail** &gt; **Inquiries and reports** &gt; **Sales reports** &gt; **Top customers report**</span></span>

<span data-ttu-id="3d266-113">Da mesma forma, os usuários podem estudar a lucratividade dos melhores produtos (10 a 100) nos diferentes níveis da hierarquia organizacional, com base em um dos seguintes critérios:</span><span class="sxs-lookup"><span data-stu-id="3d266-113">Likewise, users can study profitability for the top products (10 to 100) across different levels of the organization hierarchy, based on one of the following criteria:</span></span>

- <span data-ttu-id="3d266-114">Valor de venda</span><span class="sxs-lookup"><span data-stu-id="3d266-114">Sales amount</span></span>
- <span data-ttu-id="3d266-115">Quantidade</span><span class="sxs-lookup"><span data-stu-id="3d266-115">Quantity</span></span>
- <span data-ttu-id="3d266-116">Margem de lucro bruto</span><span class="sxs-lookup"><span data-stu-id="3d266-116">Gross profit margin</span></span>
- <span data-ttu-id="3d266-117">Percentual de margem</span><span class="sxs-lookup"><span data-stu-id="3d266-117">Margin percentage</span></span>

<span data-ttu-id="3d266-118">Nesta avaliação, você pode usar o relatório predefinido de **Melhores produtos**, que pode ser aberto em qualquer um destes locais:</span><span class="sxs-lookup"><span data-stu-id="3d266-118">For this assessment, you can use the out-of-box **Top products** report, which you can open from any of the following locations:</span></span>

- <span data-ttu-id="3d266-119">Área de trabalho **Gerenciamento de loja de varejo** &gt; **Varejo** &gt; **Canais** &gt; **Gerenciamento de loja de varejo** &gt; **Relatórios** &gt; **Relatório de melhores produtos**</span><span class="sxs-lookup"><span data-stu-id="3d266-119">**Retail store management** workspace &gt; **Retail** &gt; **Channels** &gt; **Retail store management** &gt; **Reports** &gt; **Top products report**</span></span>
- <span data-ttu-id="3d266-120">Área de trabalho **Gerenciamento de categorias e produto** &gt; **Varejo** &gt; **Produtos e categorias** &gt; **Gerenciamento de loja de varejo** &gt; **Relatórios** &gt; **Relatório de melhores produtos**</span><span class="sxs-lookup"><span data-stu-id="3d266-120">**Category and product management** workspace &gt; **Retail** &gt; **Products and categories** &gt; **Retail store management** &gt; **Reports** &gt; **Top products report**</span></span>
- <span data-ttu-id="3d266-121">Seção **Consultas e relatórios** &gt; **Varejo** &gt; **Consultas e relatórios** &gt; **Relatórios de vendas** &gt; **Relatório de melhores produtos**</span><span class="sxs-lookup"><span data-stu-id="3d266-121">**Inquiries and reports** section &gt; **Retail** &gt; **Inquiries and reports** &gt; **Sales reports** &gt; **Top products report**</span></span>

