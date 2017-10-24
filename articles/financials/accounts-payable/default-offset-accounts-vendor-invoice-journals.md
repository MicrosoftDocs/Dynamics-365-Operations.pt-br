---
title: "Contrapartidas padrão para diários de fatura de fornecedor e diários de aprovação de fatura"
description: 
author: ShivamPandey-msft
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 62093
ms.assetid: 553933ca-928d-4031-bb8c-f9cff458320b
ms.search.region: global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: c2b62eafc71b5d1ad4eaaf252efd1dcbb97b86f3
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---

# <a name="default-offset-accounts-for-vendor-invoice-journals-and-invoice-approval-journals"></a><span data-ttu-id="f10de-102">Contrapartidas padrão para diários de fatura de fornecedor e diários de aprovação de fatura</span><span class="sxs-lookup"><span data-stu-id="f10de-102">Default offset accounts for vendor invoice journals and invoice approval journals</span></span>

[!include[banner](../includes/banner.md)]




<span data-ttu-id="f10de-103">As contrapartidas padrão são usadas nas seguintes páginas de diário de fatura de fornecedor:</span><span class="sxs-lookup"><span data-stu-id="f10de-103">Default offset accounts are used on the following vendor invoice journal pages:</span></span>

-   <span data-ttu-id="f10de-104">Diário de faturas</span><span class="sxs-lookup"><span data-stu-id="f10de-104">Invoice journal</span></span>
-   <span data-ttu-id="f10de-105">Diário de aprovações de fatura</span><span class="sxs-lookup"><span data-stu-id="f10de-105">Invoice approval journal</span></span>

<span data-ttu-id="f10de-106">Use a tabela a seguir para ajudar a decidir onde você deve atribuir contas padrão para diários de fatura.</span><span class="sxs-lookup"><span data-stu-id="f10de-106">Use the following table to help decide where you should assign default accounts for invoice journals.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f10de-107">Configure contas padrão aqui</span><span class="sxs-lookup"><span data-stu-id="f10de-107">Set up default accounts here</span></span></th>
<th><span data-ttu-id="f10de-108">Onde as contas padrão são fornecidas</span><span class="sxs-lookup"><span data-stu-id="f10de-108">Where default accounts are provided</span></span></th>
<th><span data-ttu-id="f10de-109">Como esta opção afeta o processamento</span><span class="sxs-lookup"><span data-stu-id="f10de-109">How this option affects processing</span></span></th>
<th><span data-ttu-id="f10de-110">Quando você deve usar esta opção</span><span class="sxs-lookup"><span data-stu-id="f10de-110">When you should use this option</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="f10de-111"><strong>Grupo de fornecedores</strong> – configure contrapartidas padrão para grupos de fornecedores na página <strong>Configuração de conta padrão</strong>, que você pode abrir da página <strong>Grupos de fornecedores</strong>.</span><span class="sxs-lookup"><span data-stu-id="f10de-111"><strong>Vendor group</strong> – Set up default offset accounts for vendor groups on the <strong>Default account setup</strong> page, which you can open from the <strong>Vendor groups</strong> page.</span></span></td>
<td><ul>
<li><span data-ttu-id="f10de-112">Conta de fornecedor</span><span class="sxs-lookup"><span data-stu-id="f10de-112">Vendor account</span></span></li>
<li><span data-ttu-id="f10de-113">Entradas de diário para contas de fornecedor no grupo de fornecedores, caso as contas padrão não sejam especificadas para contas de fornecedor</span><span class="sxs-lookup"><span data-stu-id="f10de-113">Journal entries for vendor accounts in the vendor group, if default accounts aren’t specified for vendor accounts</span></span></li>
</ul></td>
<td><span data-ttu-id="f10de-114">As contrapartidas padrão para grupos de fornecedores são mostradas como contrapartidas padrão para fornecedores na página <strong>Configuração de conta padrão</strong>.</span><span class="sxs-lookup"><span data-stu-id="f10de-114">The default offset accounts for vendor groups are shown as default offset accounts for vendors on the <strong>Default account setup</strong> page.</span></span> <span data-ttu-id="f10de-115">Você pode abrir essa página na página de listagem <strong>Todos os fornecedores</strong>.</span><span class="sxs-lookup"><span data-stu-id="f10de-115">You can open this page from the <strong>All vendors</strong> list page.</span></span></td>
<td><span data-ttu-id="f10de-116">Use esta opção se você normalmente pagar pelos mesmos tipos de itens dos mesmos grupos de fornecedores ao longo do tempo.</span><span class="sxs-lookup"><span data-stu-id="f10de-116">Use this option if you typically pay for the same types of things from the same vendor groups over time.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="f10de-117"><strong>Conta de fornecedor</strong> – configure contas padrão para contas de fornecedor na página <strong>Configuração de conta padrão</strong>, que você pode abrir da página <strong>Fornecedores</strong>.</span><span class="sxs-lookup"><span data-stu-id="f10de-117"><strong>Vendor account</strong> – Set up default accounts for vendor accounts on the <strong>Default account setup</strong> page, which you can open from the <strong>Vendors</strong> page.</span></span></td>
<td><span data-ttu-id="f10de-118">Entradas de diário para a conta de fornecedor</span><span class="sxs-lookup"><span data-stu-id="f10de-118">Journal entries for the vendor account</span></span></td>
<td><span data-ttu-id="f10de-119">As contrapartidas padrão para contas de fornecedor são mostradas como contrapartidas padrão para entradas de diário para a conta do fornecedor.</span><span class="sxs-lookup"><span data-stu-id="f10de-119">The default offset accounts for vendor accounts are shown as default offset accounts for journal entries for the vendor account.</span></span></td>
<td><span data-ttu-id="f10de-120">Use esta opção se você normalmente pagar pelos mesmos tipos de itens dos mesmos fornecedores ao longo do tempo.</span><span class="sxs-lookup"><span data-stu-id="f10de-120">Use this option if you typically pay for the same types of things from the same vendors over time.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="f10de-121"><strong>Nomes de diário</strong> – configure as contrapartidas padrão para diários na página <strong>Nomes de diário</strong>.</span><span class="sxs-lookup"><span data-stu-id="f10de-121"><strong>Journal names</strong> – Set up default offset accounts for journals on the <strong>Journal names</strong> page.</span></span> <span data-ttu-id="f10de-122">Selecione a opção <strong>Contrapartida fixa</strong>.</span><span class="sxs-lookup"><span data-stu-id="f10de-122">Select the <strong>Fixed offset account</strong> option.</span></span> <span data-ttu-id="f10de-123">Observe que não será possível especificar contrapartidas padrão em nomes de diário se o tipo de diário dos nomes de diário for <strong>Registro de fatura</strong> ou <strong>Aprovação</strong>.</span><span class="sxs-lookup"><span data-stu-id="f10de-123">Note that you can't specify default offset accounts on journal names if the journal type of the journal names is <strong>Invoice register</strong> or <strong>Approval</strong>.</span></span></td>
<td><ul>
<li><span data-ttu-id="f10de-124">Cabeçalho de diário que usa o nome do diário</span><span class="sxs-lookup"><span data-stu-id="f10de-124">Journal header that uses the journal name</span></span></li>
<li><span data-ttu-id="f10de-125">Entradas de diário em diários que usam o nome do diário</span><span class="sxs-lookup"><span data-stu-id="f10de-125">Journal entries in journals that use the journal name</span></span></li>
</ul></td>
<td><span data-ttu-id="f10de-126">Se a opção <strong>Contrapartida fixa</strong> na página <strong>Nomes de diário</strong> estiver selecionada, a contrapartida para o nome do diário substituirá a contrapartida padrão para o fornecedor ou para o grupo de fornecedores.</span><span class="sxs-lookup"><span data-stu-id="f10de-126">If the <strong>Fixed offset account</strong> option on the <strong>Journal names</strong> page is selected, the offset account for the journal name overrides the default offset account for the vendor or vendor group.</span></span></td>
<td><span data-ttu-id="f10de-127">Use essa opção para configurar diários para os custos e despesas específicos cobrados de contas específicas, independentemente do fornecedor ou do grupo de fornecedores do qual o fornecedor faz parte.</span><span class="sxs-lookup"><span data-stu-id="f10de-127">Use this option to set up journals for specific costs and expenses that are charged to specific accounts, regardless of the vendor or the vendor group that the vendor belongs to.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="f10de-128"><strong>Nomes de diário</strong> – configure as contrapartidas padrão para diários na página <strong>Nomes de diário</strong>.</span><span class="sxs-lookup"><span data-stu-id="f10de-128"><strong>Journal names</strong> – Set up default offset accounts for journals on the <strong>Journal names</strong> page.</span></span> <span data-ttu-id="f10de-129">Desmarque a opção <strong>Contrapartida fixa</strong>.</span><span class="sxs-lookup"><span data-stu-id="f10de-129">Clear the <strong>Fixed offset account</strong> option.</span></span> <span data-ttu-id="f10de-130">Observe que não será possível especificar contrapartidas padrão em nomes de diário se o tipo de diário dos nomes de diário for <strong>Registro de fatura</strong> ou <strong>Aprovação</strong>.</span><span class="sxs-lookup"><span data-stu-id="f10de-130">Note that you can't specify default offset accounts on journal names if the journal type of the journal names is <strong>Invoice register</strong> or <strong>Approval</strong>.</span></span></td>
<td><ul>
<li><span data-ttu-id="f10de-131">Cabeçalho do diário</span><span class="sxs-lookup"><span data-stu-id="f10de-131">Journal header</span></span></li>
<li><span data-ttu-id="f10de-132">Entradas de diário em diários que usam o nome do diário</span><span class="sxs-lookup"><span data-stu-id="f10de-132">Journal entries in journals that use the journal name</span></span></li>
</ul></td>
<td><span data-ttu-id="f10de-133">Essas entradas padrão são usadas em páginas de cabeçalho de diário, e a contrapartida na página de cabeçalho de diário é usada como uma entrada padrão nas páginas de comprovante de diário.</span><span class="sxs-lookup"><span data-stu-id="f10de-133">These default entries are used on journal header pages, and the offset account on the journal header page is used as a default entry on the journal voucher pages.</span></span> <span data-ttu-id="f10de-134">As contas padrão da página <strong>Nomes de diário </strong>só serão usadas se as contas padrão não tiverem sido configuradas para a conta de fornecedor.</span><span class="sxs-lookup"><span data-stu-id="f10de-134">Default accounts from the <strong>Journal names </strong>page are used only if default accounts aren’t set up for the vendor account.</span></span></td>
<td><span data-ttu-id="f10de-135">Use esta opção para configurar contas padrão usadas quando uma contrapartida de fornecedor padrão não tiver sido atribuída.</span><span class="sxs-lookup"><span data-stu-id="f10de-135">Use this option to set up default accounts that are used when a default vendor offset account isn't assigned.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="f10de-136"><strong>Cabeçalho do diário</strong> – configure uma contrapartida padrão para um diário como uma entrada padrão nas páginas de comprovante de diário.</span><span class="sxs-lookup"><span data-stu-id="f10de-136"><strong>Journal header</strong> – Set up a default offset account for a journal as a default entry on the journal voucher pages.</span></span> <span data-ttu-id="f10de-137">Observe que não será possível especificar contrapartidas padrão no cabeçalho do diário se o tipo de diário dos nomes de diário for <strong>Registro de fatura</strong> ou <strong>Aprovação</strong>.</span><span class="sxs-lookup"><span data-stu-id="f10de-137">Note that you can't specify default offset accounts on the journal header if the journal type of the journal names is <strong>Invoice register</strong> or <strong>Approval</strong>.</span></span></td>
<td><span data-ttu-id="f10de-138">Entradas de diário no diário</span><span class="sxs-lookup"><span data-stu-id="f10de-138">Journal entries in the journal</span></span></td>
<td><span data-ttu-id="f10de-139">A contrapartida padrão para um diário é usada como a entrada padrão nas páginas de comprovante de diário.</span><span class="sxs-lookup"><span data-stu-id="f10de-139">The default offset account for a journal is used as the default entry on the journal voucher pages.</span></span></td>
<td><span data-ttu-id="f10de-140">Use esta opção para ajudar a acelerar a entrada de dados caso a maioria das entradas de um diário tenha a mesma contrapartida.</span><span class="sxs-lookup"><span data-stu-id="f10de-140">Use this option to help speed up data entry if most entries in a journal have the same offset account.</span></span></td>
</tr>
</tbody>
</table>






