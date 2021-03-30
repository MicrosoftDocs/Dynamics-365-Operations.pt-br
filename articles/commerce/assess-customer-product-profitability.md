---
title: Avaliar lucratividade do cliente e do produto
description: Este artigo explica como você pode usar a análise na memória e em tempo real para acessar, explorar e obter informações sobre clientes e lucratividade de produto com base nos dados do Dynamics 365 Commerce.
author: ashishmsft
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: SysOperationsTemplateForm, RetailStoreManagementWorkspace
audience: Application User
ms.reviewer: josaw
ms.custom: 52902
ms.assetid: 1a77d04b-2985-4bee-9138-c216fe0483de
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: e0589748247cf9195116687cf70228b4ef36e29b
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5211537"
---
# <a name="assess-customer-and-product-profitability"></a><span data-ttu-id="bcf59-103">Avaliar a lucratividade dos clientes e dos produtos</span><span class="sxs-lookup"><span data-stu-id="bcf59-103">Assess customer and product profitability</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="bcf59-104">Este artigo explica como você pode usar a análise na memória e em tempo real para acessar, explorar e obter informações sobre clientes e lucratividade de produto com base nos dados do Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="bcf59-104">This article explains how you can use the in-memory and real-time analytics to access, explore, and gain insight about customers and product profitability from your Dynamics 365 Commerce data.</span></span>

<span data-ttu-id="bcf59-105">Como parte do Commerce, os usuários podem estudar a lucratividade dos melhores clientes (10 a 100) nos diferentes níveis da hierarquia da organização com base em um dos seguintes critérios:</span><span class="sxs-lookup"><span data-stu-id="bcf59-105">As part of Commerce, users can study profitability for the top customers (10 to 100) across different levels of the organization hierarchy, based on one of the following criteria:</span></span>

- <span data-ttu-id="bcf59-106">Valor de venda</span><span class="sxs-lookup"><span data-stu-id="bcf59-106">Sales amount</span></span>
- <span data-ttu-id="bcf59-107">Quantidade</span><span class="sxs-lookup"><span data-stu-id="bcf59-107">Quantity</span></span>
- <span data-ttu-id="bcf59-108">Margem de lucro bruto</span><span class="sxs-lookup"><span data-stu-id="bcf59-108">Gross profit margin</span></span>
- <span data-ttu-id="bcf59-109">Percentual de margem</span><span class="sxs-lookup"><span data-stu-id="bcf59-109">Margin percentage</span></span>

<span data-ttu-id="bcf59-110">Nesta avaliação, você pode usar o relatório predefinido de **Melhores clientes**, que pode ser aberto em qualquer um destes locais:</span><span class="sxs-lookup"><span data-stu-id="bcf59-110">For this assessment, you can use the out-of-box **Top customers** report, which you can open from any of the following locations:</span></span>

- <span data-ttu-id="bcf59-111">Espaço de trabalho **Gerenciamento de loja** &gt; **Varejo e Comércio** &gt; **Canais** &gt; **Gerenciamento de loja** &gt; **Relatórios** &gt; **Relatório de principais clientes**</span><span class="sxs-lookup"><span data-stu-id="bcf59-111">**Store management** workspace &gt; **Retail and Commerce** &gt; **Channels** &gt; **Store management** &gt; **Reports** &gt; **Top customers report**</span></span>
- <span data-ttu-id="bcf59-112">Seção **Consultas e relatórios** &gt; **Varejo e Comércio** &gt; **Consultas e relatórios** &gt; **Relatórios de vendas** &gt; **Relatório de principais clientes**</span><span class="sxs-lookup"><span data-stu-id="bcf59-112">**Inquiries and reports** section &gt; **Retail and Commerce** &gt; **Inquiries and reports** &gt; **Sales reports** &gt; **Top customers report**</span></span>

<span data-ttu-id="bcf59-113">Da mesma forma, os usuários podem estudar a lucratividade dos melhores produtos (10 a 100) nos diferentes níveis da hierarquia organizacional, com base em um dos seguintes critérios:</span><span class="sxs-lookup"><span data-stu-id="bcf59-113">Likewise, users can study profitability for the top products (10 to 100) across different levels of the organization hierarchy, based on one of the following criteria:</span></span>

- <span data-ttu-id="bcf59-114">Valor de venda</span><span class="sxs-lookup"><span data-stu-id="bcf59-114">Sales amount</span></span>
- <span data-ttu-id="bcf59-115">Quantidade</span><span class="sxs-lookup"><span data-stu-id="bcf59-115">Quantity</span></span>
- <span data-ttu-id="bcf59-116">Margem de lucro bruto</span><span class="sxs-lookup"><span data-stu-id="bcf59-116">Gross profit margin</span></span>
- <span data-ttu-id="bcf59-117">Percentual de margem</span><span class="sxs-lookup"><span data-stu-id="bcf59-117">Margin percentage</span></span>

<span data-ttu-id="bcf59-118">Nesta avaliação, você pode usar o relatório predefinido de **Melhores produtos**, que pode ser aberto em qualquer um destes locais:</span><span class="sxs-lookup"><span data-stu-id="bcf59-118">For this assessment, you can use the out-of-box **Top products** report, which you can open from any of the following locations:</span></span>

- <span data-ttu-id="bcf59-119">Espaço de trabalho **Gerenciamento de loja** &gt; **Varejo e Comércio** &gt; **Canais** &gt; **Gerenciamento de loja** &gt; **Relatórios** &gt; **Relatório de principais produtos**</span><span class="sxs-lookup"><span data-stu-id="bcf59-119">**Store management** workspace &gt; **Retail and Commerce** &gt; **Channels** &gt; **Store management** &gt; **Reports** &gt; **Top products report**</span></span>
- <span data-ttu-id="bcf59-120">Área de trabalho **Gerenciamento de categorias e produtos** &gt; **Varejo e Comércio** &gt; **Produtos e categorias** &gt; **Gerenciamento de loja** &gt; **Relatórios** &gt; **Relatório de principais produtos**</span><span class="sxs-lookup"><span data-stu-id="bcf59-120">**Category and product management** workspace &gt; **Retail and Commerce** &gt; **Products and categories** &gt; **Store management** &gt; **Reports** &gt; **Top products report**</span></span>
- <span data-ttu-id="bcf59-121">Seção **Consultas e relatórios** &gt; **Varejo e Comércio** &gt; **Consultas e relatórios** &gt; **Relatórios de vendas** &gt; **Relatório de principais produtos**</span><span class="sxs-lookup"><span data-stu-id="bcf59-121">**Inquiries and reports** section &gt; **Retail and Commerce** &gt; **Inquiries and reports** &gt; **Sales reports** &gt; **Top products report**</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]