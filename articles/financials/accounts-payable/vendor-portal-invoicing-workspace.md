---
title: Espaço de trabalho de faturamento de colaboração do fornecedor
description: Este tópico explica como podem exibir faturas de fornecedor e enviar notas fiscais de colaboração de fornecedor que ao espaço de trabalho.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendInvoiceWorkspace
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 221534
ms.assetid: c4ed62f3-d351-41d7-a2ad-790576cde4ab
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 5520012a00e918e8748b974773eeaf2450f0c55e
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "340513"
---
# <a name="vendor-collaboration-invoicing-workspace"></a><span data-ttu-id="f5120-103">Espaço de trabalho de faturamento de colaboração do fornecedor</span><span class="sxs-lookup"><span data-stu-id="f5120-103">Vendor collaboration invoicing workspace</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f5120-104">Este tópico explica como podem exibir faturas de fornecedor e enviar notas fiscais de colaboração de fornecedor que ao espaço de trabalho.</span><span class="sxs-lookup"><span data-stu-id="f5120-104">This topic explains how you can view vendor invoices and submit invoices from the vendor collaboration invoicing workspace.</span></span>

<span data-ttu-id="f5120-105">O espaço de trabalho **Faturamento de colaboração de fornecedor**pode ser usado para exibir informações de fatura de fornecedor e enviar faturas ao Microsoft Dynamics 365 for Finance and Operations usando recursos de fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="f5120-105">The **Vendor collaboration invoicing** workspace can be used to view vendor invoice information and to submit invoices to Microsoft Dynamics 365 for Finance and Operations using workflow capabilities.</span></span>


<a name="vendor-collaboration-invoicing-workspace"></a><span data-ttu-id="f5120-106">Espaço de trabalho de faturamento da colaboração de fornecedores</span><span class="sxs-lookup"><span data-stu-id="f5120-106">Vendor collaboration invoicing workspace</span></span>
----------------------------------------

### <a name="summary-tiles"></a><span data-ttu-id="f5120-107">Blocos do resumo</span><span class="sxs-lookup"><span data-stu-id="f5120-107">Summary tiles</span></span>

<span data-ttu-id="f5120-108">Os blocos **Resumo** darão uma visão geral de notas fiscais do fornecedor selecionado.</span><span class="sxs-lookup"><span data-stu-id="f5120-108">The **Summary** tiles give an overview of the invoices for the selected vendor.</span></span> <span data-ttu-id="f5120-109">Você pode exibir faturas pelo estado.</span><span class="sxs-lookup"><span data-stu-id="f5120-109">You can view invoices by their state.</span></span>
-   <span data-ttu-id="f5120-110">Faturas de rascunho não foram enviadas ao fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="f5120-110">Draft invoices have not been submitted to workflow.</span></span>
-   <span data-ttu-id="f5120-111">As faturas enviadas não aprovadas são aquelas que o fornecedor enviou, mas que não foram lançadas no Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="f5120-111">Submitted, not approved invoices are those invoices that the vendor has submitted, but they have not been posted in Finance and Operations.</span></span>
-   <span data-ttu-id="f5120-112">As faturas aprovadas não pagas são aquelas que foram lançadas no Finance and Operations, mas que ainda não foram totalmente pagas.</span><span class="sxs-lookup"><span data-stu-id="f5120-112">Approved, not paid invoices are those that have been posted in Finance and Operations, but they have not yet been fully paid.</span></span>
-   <span data-ttu-id="f5120-113">As faturas pagas são aquelas que foram totalmente pagas no Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="f5120-113">Paid invoices are those that have been fully paid in Finance and Operations.</span></span>

<span data-ttu-id="f5120-114">Clique em um quadro abrirá uma exibição filtrada da página **Lista de notas fiscais**.</span><span class="sxs-lookup"><span data-stu-id="f5120-114">Clicking on a tile will open a filtered view of the **Invoices list** page.</span></span>

### <a name="tabular-lists"></a><span data-ttu-id="f5120-115">Listas tabulares</span><span class="sxs-lookup"><span data-stu-id="f5120-115">Tabular lists</span></span>

<span data-ttu-id="f5120-116">Na seção **Listas Tabular**, o status do faturamento está dividido de formas semelhantes como o resumo organiza lado a lado: Rascunho, e listas enviadas não aprovadas.</span><span class="sxs-lookup"><span data-stu-id="f5120-116">In the **Tabular lists** section, the status of the invoicing is broken down in similar ways as the summary tiles: Draft and Submitted, not approved lists.</span></span> <span data-ttu-id="f5120-117">Quando o estado de rascunho, uma nota fiscal pode ser enviada ao fluxo de trabalho ou ser excluída.</span><span class="sxs-lookup"><span data-stu-id="f5120-117">While in the Draft state, an invoice can be submitted to workflow or deleted.</span></span> <span data-ttu-id="f5120-118">A última lista tabular é uma opção para encontrar faturas.</span><span class="sxs-lookup"><span data-stu-id="f5120-118">The last tabular list is an option to find invoices.</span></span> <span data-ttu-id="f5120-119">Você pode filtrar enquanto pesquisa, para permitir pesquisas mais rápidas.</span><span class="sxs-lookup"><span data-stu-id="f5120-119">You can filter as you search, to allow for faster searches.</span></span>

### <a name="all-vendor-invoices-list-page"></a><span data-ttu-id="f5120-120">Página Todas faturas de fornecedor</span><span class="sxs-lookup"><span data-stu-id="f5120-120">All vendor invoices list page</span></span>

<span data-ttu-id="f5120-121">É possível exibir todas as faturas de fornecedor lançadas na página de listagem **Faturas de colaboração do fornecedor**.</span><span class="sxs-lookup"><span data-stu-id="f5120-121">You can view all posted and unposted vendor invoices on the **Vendor collaboration invoices** list page.</span></span> <span data-ttu-id="f5120-122">Você pode usar esta página de lista para visualizar o status de pagamento das faturas.</span><span class="sxs-lookup"><span data-stu-id="f5120-122">You can use this list page to view the payment status of the invoices.</span></span> <span data-ttu-id="f5120-123">Os status de pagamento inclui Não feito, e parcialmente pagas totalmente paga.</span><span class="sxs-lookup"><span data-stu-id="f5120-123">The payment statuses include Unposted, Unpaid, Partially paid, and Fully paid.</span></span>
<span data-ttu-id="f5120-124">Criar uma nova fatura a partir de uma ordem de compra</span><span class="sxs-lookup"><span data-stu-id="f5120-124">Creating a new invoice from a purchase order</span></span>

<span data-ttu-id="f5120-125">Você pode criar uma nova nota fiscal do fornecedor selecionando **Novo** a ação **Faturamento de colaboração de fornecedor** no espaço de trabalho.</span><span class="sxs-lookup"><span data-stu-id="f5120-125">You can create a new vendor invoice by selecting the **New** action on the **Vendor collaboration invoicing** workspace.</span></span> <span data-ttu-id="f5120-126">A ordem de compra e o número de nota fiscal devem ser fornecidos pelo fornecedor.</span><span class="sxs-lookup"><span data-stu-id="f5120-126">The purchase order number and invoice number must be provided by the vendor.</span></span> <span data-ttu-id="f5120-127">Por padrão, todas as linhas de ordem de compra de fornecedores aparecerão em nova nota fiscal.</span><span class="sxs-lookup"><span data-stu-id="f5120-127">By default, all of the lines from the vendor's purchase order will appear on the new invoice.</span></span> <span data-ttu-id="f5120-128">A quantidade e as informações de custo podem ser editadas antes de enviar a nota fiscal de fornecedor para o fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="f5120-128">The quantity and cost information can be edited prior to submitting the vendor invoice to workflow.</span></span> <span data-ttu-id="f5120-129">Você pode anexar arquivos, notas, imagens e URLs a uma nota fiscal antes enviá-la.</span><span class="sxs-lookup"><span data-stu-id="f5120-129">You can attach files, notes, images, and URLs to an invoice before submitting it.</span></span>

<span data-ttu-id="f5120-130">Para obter mais informações, consulte [Colaboração de fornecedores com fornecedores externos](../../supply-chain/procurement/vendor-collaboration-work-external-vendors.md)</span><span class="sxs-lookup"><span data-stu-id="f5120-130">For more information, see [Vendor collaboration with external vendors](../../supply-chain/procurement/vendor-collaboration-work-external-vendors.md)</span></span>



