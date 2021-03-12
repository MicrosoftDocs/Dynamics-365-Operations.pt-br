---
title: Monitorar o desempenho de vendas e margem
description: Você pode monitorar o desempenho de vendas e de margem em tempo real usando o Dynamics 365 Commerce.
author: ashishmsft
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailSales
audience: Application User
ms.reviewer: josaw
ms.custom: 85123
ms.assetid: ddd15820-c3e6-4607-819e-8cef744ce9c9
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 51dc7c4b62a497e3dc9279b3c5a616057316c106
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4985877"
---
# <a name="monitor-sales-and-margin-performance"></a><span data-ttu-id="b8a67-103">Monitorar o desempenho de vendas e margem</span><span class="sxs-lookup"><span data-stu-id="b8a67-103">Monitor sales and margin performance</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="b8a67-104">Você pode monitorar o desempenho de vendas e de margem em tempo real usando o Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="b8a67-104">You can monitor sales and margin performance in real time using Dynamics 365 Commerce.</span></span>

<span data-ttu-id="b8a67-105">Como parte do Commerce, os usuários podem monitorar o desempenho de vendas e de margem em tempo real em diferentes níveis da hierarquia da organização para as seguintes dimensões:</span><span class="sxs-lookup"><span data-stu-id="b8a67-105">As part of Commerce, users can monitor sales and margin performance in real time across different levels of the organization hierarchy for the following dimensions:</span></span>

- <span data-ttu-id="b8a67-106">Produtos</span><span class="sxs-lookup"><span data-stu-id="b8a67-106">Products</span></span>
- <span data-ttu-id="b8a67-107">Categorias</span><span class="sxs-lookup"><span data-stu-id="b8a67-107">Categories</span></span>
- <span data-ttu-id="b8a67-108">Descontos</span><span class="sxs-lookup"><span data-stu-id="b8a67-108">Discounts</span></span>
- <span data-ttu-id="b8a67-109">Anos como o período de tempo</span><span class="sxs-lookup"><span data-stu-id="b8a67-109">Years as time period</span></span>
- <span data-ttu-id="b8a67-110">Registros/terminais</span><span class="sxs-lookup"><span data-stu-id="b8a67-110">Registers/terminals</span></span>
- <span data-ttu-id="b8a67-111">Equipe/funcionários</span><span class="sxs-lookup"><span data-stu-id="b8a67-111">Staff/employees</span></span>
- <span data-ttu-id="b8a67-112">Clientes</span><span class="sxs-lookup"><span data-stu-id="b8a67-112">Customers</span></span>
- <span data-ttu-id="b8a67-113">Unidades operacionais</span><span class="sxs-lookup"><span data-stu-id="b8a67-113">Operating units</span></span>

<span data-ttu-id="b8a67-114">Além disso, dois relatórios exclusivos que aproveitam a estruturação da grade hierárquica permitem que os usuários monitorem o desempenho de vendas e de margem ao fazerem uma busca detalhada no nó superior da categoria de nós folha na hierarquia de categorias de produto padrão.</span><span class="sxs-lookup"><span data-stu-id="b8a67-114">Additionally, two unique reports that take advantage of hierarchical grid structuring let users monitor sales and margin performance by drilling down from the top category node to individual leaf nodes of the category in the default product category hierarchy.</span></span> <span data-ttu-id="b8a67-115">Os usuários também podem fazer busca detalhada da unidade operacional superior para um canal individual na hierarquia da organização definida como a hierarquia da organização padrão para relatórios.</span><span class="sxs-lookup"><span data-stu-id="b8a67-115">Users can also drill-down from the top operating unit to an individual channel in the organization hierarchy that is defined as the default organization hierarchy for reporting.</span></span> <span data-ttu-id="b8a67-116">Você pode abrir os relatórios de qualquer um dos seguintes locais:</span><span class="sxs-lookup"><span data-stu-id="b8a67-116">You can open the reports from any of the following locations:</span></span>

- <span data-ttu-id="b8a67-117">Espaço de trabalho **Gerenciamento de loja** &gt; **Varejo e Comércio** &gt; **Canais** &gt; **Gerenciamento de loja** &gt; **Relatórios**</span><span class="sxs-lookup"><span data-stu-id="b8a67-117">**Store management** workspace &gt; **Retail and Commerce** &gt; **Channels** &gt; **Store management** &gt; **Reports**</span></span>
- <span data-ttu-id="b8a67-118">Espaço de trabalho **Gerenciamento de categorias e produtos** &gt; **Varejo e Comércio** &gt; **Produto e categorias** &gt; **Gerenciamento de loja** &gt; **Relatórios**</span><span class="sxs-lookup"><span data-stu-id="b8a67-118">**Category and product management** workspace &gt; **Retail and Commerce** &gt; **Product and categories** &gt; **Store management** &gt; **Reports**</span></span>
- <span data-ttu-id="b8a67-119">Espaço de trabalho **Gerenciamento de preços e descontos** &gt; **Varejo e Comércio** &gt; **Preços e descontos** &gt; **Gerenciamento de loja** &gt; **Relatórios**</span><span class="sxs-lookup"><span data-stu-id="b8a67-119">**Pricing and discount management** workspace &gt; **Retail and Commerce** &gt; **Pricing and discounts** &gt; **Store management** &gt; **Reports**</span></span>
- <span data-ttu-id="b8a67-120">Seção **Consultas e relatórios** &gt; **Varejo e Comércio** &gt; **Consultas e relatórios** &gt; **Relatórios de vendas**</span><span class="sxs-lookup"><span data-stu-id="b8a67-120">**Inquiries and reports** section &gt; **Retail and Commerce** &gt; **Inquiries and reports** &gt; **Sales reports**</span></span>
