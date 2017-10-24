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
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 52902
ms.assetid: 1a77d04b-2985-4bee-9138-c216fe0483de
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 84a9e0b3936adcf2ed99fddca77dd57dfedeb050
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---

# <a name="assess-customer-and-product-profitability"></a><span data-ttu-id="9b337-103">Avaliar a lucratividade dos clientes e dos produtos</span><span class="sxs-lookup"><span data-stu-id="9b337-103">Assess customer and product profitability</span></span>

[!include[banner](includes/banner.md)]


<span data-ttu-id="9b337-104">Este artigo explica como você pode usar a análise na memória e em tempo real para acessar, explorar e obter informações sobre clientes e lucratividade de produto com base nos dados do Microsoft Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="9b337-104">This article explains how you can use the in-memory and real-time analytics to access, explore, and gain insight about customers and product profitability from your Microsoft Dynamics 365 for Retail data.</span></span> 

<span data-ttu-id="9b337-105">Como parte do Dynamics 365 for Retail, os usuários podem estudar a lucratividade dos melhores clientes (10 a 100) nos diferentes níveis da hierarquia organizacional, com base em um dos seguintes critérios:</span><span class="sxs-lookup"><span data-stu-id="9b337-105">As part of Dynamics 365 for Retail, users can study profitability for the top customers (10 to 100) across different levels of the organization hierarchy, based on one of the following criteria:</span></span>

-   <span data-ttu-id="9b337-106">Valor de venda</span><span class="sxs-lookup"><span data-stu-id="9b337-106">Sales amount</span></span>
-   <span data-ttu-id="9b337-107">Quantidade</span><span class="sxs-lookup"><span data-stu-id="9b337-107">Quantity</span></span>
-   <span data-ttu-id="9b337-108">Margem de lucro bruto</span><span class="sxs-lookup"><span data-stu-id="9b337-108">Gross profit margin</span></span>
-   <span data-ttu-id="9b337-109">Percentual de margem</span><span class="sxs-lookup"><span data-stu-id="9b337-109">Margin percentage</span></span>

<span data-ttu-id="9b337-110">Nesta avaliação, você pode usar o relatório predefinido de **Melhores clientes**, que pode ser aberto em qualquer um destes locais:</span><span class="sxs-lookup"><span data-stu-id="9b337-110">For this assessment, you can use the out-of-box **Top customers** report, which you can open from any of the following locations:</span></span>

-   <span data-ttu-id="9b337-111">Área de trabalho **Gerenciamento de loja de varejo** &gt; **Varejo** &gt; **Canais** &gt; **Gerenciamento de loja de varejo** &gt; **Relatórios** &gt; **Relatório de melhores clientes**</span><span class="sxs-lookup"><span data-stu-id="9b337-111">**Retail store management** workspace &gt; **Retail** &gt; **Channels** &gt; **Retail store management** &gt; **Reports** &gt; **Top customers report**</span></span>
-   <span data-ttu-id="9b337-112">Seção **Consultas e relatórios** &gt; **Varejo** &gt; **Consultas e relatórios** &gt; **Relatórios de vendas** &gt; **Relatório de melhores clientes**</span><span class="sxs-lookup"><span data-stu-id="9b337-112">**Inquiries and reports** section &gt; **Retail** &gt; **Inquiries and reports** &gt; **Sales reports** &gt; **Top customers report**</span></span>

<span data-ttu-id="9b337-113">Da mesma forma, os usuários podem estudar a lucratividade dos melhores produtos (10 a 100) nos diferentes níveis da hierarquia organizacional, com base em um dos seguintes critérios:</span><span class="sxs-lookup"><span data-stu-id="9b337-113">Likewise, users can study profitability for the top products (10 to 100) across different levels of the organization hierarchy, based on one of the following criteria:</span></span>

-   <span data-ttu-id="9b337-114">Valor de venda</span><span class="sxs-lookup"><span data-stu-id="9b337-114">Sales amount</span></span>
-   <span data-ttu-id="9b337-115">Quantidade</span><span class="sxs-lookup"><span data-stu-id="9b337-115">Quantity</span></span>
-   <span data-ttu-id="9b337-116">Margem de lucro bruto</span><span class="sxs-lookup"><span data-stu-id="9b337-116">Gross profit margin</span></span>
-   <span data-ttu-id="9b337-117">Percentual de margem</span><span class="sxs-lookup"><span data-stu-id="9b337-117">Margin percentage</span></span>

<span data-ttu-id="9b337-118">Nesta avaliação, você pode usar o relatório predefinido de **Melhores produtos**, que pode ser aberto em qualquer um destes locais:</span><span class="sxs-lookup"><span data-stu-id="9b337-118">For this assessment, you can use the out-of-box **Top products** report, which you can open from any of the following locations:</span></span>

-   <span data-ttu-id="9b337-119">Área de trabalho **Gerenciamento de loja de varejo** &gt; **Varejo** &gt; **Canais** &gt; **Gerenciamento de loja de varejo** &gt; **Relatórios** &gt; **Relatório de melhores produtos**</span><span class="sxs-lookup"><span data-stu-id="9b337-119">**Retail store management** workspace &gt; **Retail** &gt; **Channels** &gt; **Retail store management** &gt; **Reports** &gt; **Top products report**</span></span>
-   <span data-ttu-id="9b337-120">Área de trabalho **Gerenciamento de categorias e produto** &gt; **Varejo** &gt; **Produtos e categorias** &gt; **Gerenciamento de loja de varejo** &gt; **Relatórios** &gt; **Relatório de melhores produtos**</span><span class="sxs-lookup"><span data-stu-id="9b337-120">**Category and product management** workspace &gt; **Retail** &gt; **Products and categories** &gt; **Retail store management** &gt; **Reports** &gt; **Top products report**</span></span>
-   <span data-ttu-id="9b337-121">Seção **Consultas e relatórios** &gt; **Varejo** &gt; **Consultas e relatórios** &gt; **Relatórios de vendas** &gt; **Relatório de melhores produtos**</span><span class="sxs-lookup"><span data-stu-id="9b337-121">**Inquiries and reports** section &gt; **Retail** &gt; **Inquiries and reports** &gt; **Sales reports** &gt; **Top products report**</span></span>




