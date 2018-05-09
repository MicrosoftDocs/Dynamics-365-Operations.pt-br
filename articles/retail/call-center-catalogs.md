---
title: "Catálogos de call center"
description: "Este artigo descreve a funcionalidade específica do call center para catálogos no Microsoft Dynamics 365 for Retail."
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: RetailMCRChannelDetailPage, RetailCatalogDetails
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 16231
ms.assetid: f28a827c-3a50-4d5e-83eb-e5a768db70a1
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 99f66e975cf5875f357af095ead66529b9784eff
ms.contentlocale: pt-br
ms.lasthandoff: 05/08/2018

---

# <a name="call-center-catalogs"></a><span data-ttu-id="e10b6-103">Catálogos do call center</span><span class="sxs-lookup"><span data-stu-id="e10b6-103">Call center catalogs</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="e10b6-104">Este artigo descreve a funcionalidade específica do call center para catálogos no Microsoft Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="e10b6-104">This article describes the call center–specific functionality for catalogs in Microsoft Dynamics 365 for Retail.</span></span>

<span data-ttu-id="e10b6-105">Em um call center, você pode usar catálogos de produtos para identificar os produtos que deseja oferecer para os clientes.</span><span class="sxs-lookup"><span data-stu-id="e10b6-105">In a call center, you can use product catalogs to identify the products that you want to offer to customers.</span></span> <span data-ttu-id="e10b6-106">Os call centers usam normalmente catálogos impressos.</span><span class="sxs-lookup"><span data-stu-id="e10b6-106">Call centers typically use printed catalogs.</span></span> <span data-ttu-id="e10b6-107">O design e a produção de um catálogo impresso são tratados fora do Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="e10b6-107">The design and production of a printed catalog is handled outside Dynamics 365 for Retail.</span></span> <span data-ttu-id="e10b6-108">No entanto, você pode criar e armazenar um formulário digital de um catálogo usando as mesmas páginas que você usa para configurar catálogos de varejo online.</span><span class="sxs-lookup"><span data-stu-id="e10b6-108">However, you can create and store a digital form of a catalog by using the same pages that you use to set up online retail catalogs.</span></span> <span data-ttu-id="e10b6-109">Antes de criar um catálogo, você deve configurar classificações de produtos e atribuir as classificações a um call center.</span><span class="sxs-lookup"><span data-stu-id="e10b6-109">Before you can create a catalog, you must set up product assortments and assign the assortments to a call center.</span></span> <span data-ttu-id="e10b6-110">Então, você pode adicionar produtos ao catálogo selecionando produtos desses sortimentos.</span><span class="sxs-lookup"><span data-stu-id="e10b6-110">You then add products to the catalog by selecting products from these assortments.</span></span> <span data-ttu-id="e10b6-111">Depois que o produtos tiverem sido adicionados ao catálogo, e o catálogo estiver concluído, você deve validar o catálogo para verificar os dados.</span><span class="sxs-lookup"><span data-stu-id="e10b6-111">After products have been added to the catalog, and the catalog is complete, you must validate the catalog to verify the data.</span></span> <span data-ttu-id="e10b6-112">Em seguida, é necessário enviar o catálogo para revisão e aprovação.</span><span class="sxs-lookup"><span data-stu-id="e10b6-112">You must then submit the catalog for review and approval.</span></span> <span data-ttu-id="e10b6-113">Depois que o catálogo for aprovado, ele poderá ser publicado.</span><span class="sxs-lookup"><span data-stu-id="e10b6-113">After the catalog is approved, it can be published.</span></span> <span data-ttu-id="e10b6-114">Quando um catálogo de call center é criado, você pode fazer um instantâneo dos dados do catálogo no momento em que o catálogo é publicado.</span><span class="sxs-lookup"><span data-stu-id="e10b6-114">When a call center catalog is created, you can take a snapshot of the catalog data at the time that the catalog is published.</span></span> <span data-ttu-id="e10b6-115">Essa funcionalidade do instantâneo permite acessar uma versão específica do catálogo, mesmo se ele for alterado e atualizado posteriormente.</span><span class="sxs-lookup"><span data-stu-id="e10b6-115">This snapshot functionality lets you access a particular version of the catalog even if the catalog is later changed and updated.</span></span> <span data-ttu-id="e10b6-116">Catálogos de call center também podem ser configurados para incluir os seguintes recursos opcionais:</span><span class="sxs-lookup"><span data-stu-id="e10b6-116">Call center catalogs can also be set up to include the following optional features:</span></span>

-   <span data-ttu-id="e10b6-117">**Códigos de fonte** – Códigos de fonte são usados para rastrear a resposta do cliente para endereçamentos de catálogo específicos.</span><span class="sxs-lookup"><span data-stu-id="e10b6-117">**Source codes** – Source codes are used to track the customer response to specific catalog mailings.</span></span>
-   <span data-ttu-id="e10b6-118">**Produtos gratuitos** – Produtos podem ser incluídos em uma ordem do cliente sem encargos adicionais.</span><span class="sxs-lookup"><span data-stu-id="e10b6-118">**Free products** – Products can be included in a customer's order at no additional charge.</span></span> <span data-ttu-id="e10b6-119">Esses produtos são adicionados automaticamente a uma ordem quando o código de origem do catálogo é inserido na ordem.</span><span class="sxs-lookup"><span data-stu-id="e10b6-119">These products are automatically added to an order when the source code for the catalog is entered into the order.</span></span>
-   <span data-ttu-id="e10b6-120">**Scripts** – Os scripts são textos que um trabalhador do call center lê para um cliente quando uma ordem de venda está sendo criada.</span><span class="sxs-lookup"><span data-stu-id="e10b6-120">**Scripts** – Scripts are texts that a call center worker reads to a customer when a sales order is being created.</span></span> <span data-ttu-id="e10b6-121">Os scripts podem incluir cumprimentos ou sugestões de compra.</span><span class="sxs-lookup"><span data-stu-id="e10b6-121">Scripts can include greetings or purchase suggestions.</span></span>
-   <span data-ttu-id="e10b6-122">**Layout da página** – Um layout de página captura a posição da página de produtos no catálogo impresso.</span><span class="sxs-lookup"><span data-stu-id="e10b6-122">**Page layout** – A page layout captures the page position of products in the printed catalog.</span></span> <span data-ttu-id="e10b6-123">Essas informações são usadas para o relatório de análise da área de catálogo.</span><span class="sxs-lookup"><span data-stu-id="e10b6-123">This information is used for the catalog area analysis report.</span></span>





