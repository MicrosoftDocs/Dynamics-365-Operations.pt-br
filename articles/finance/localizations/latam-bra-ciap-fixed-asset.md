---
title: Adquirir e alienar um ativo fixo do CIAP
description: Os livros fiscais podem adquirir e alienar ativos fixos de ICMS recuperável a longo prazo.
author: v-gonode
manager: AnnBe
ms.date: 10/31/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Brazil
ms.author: v-gonode
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 0f30981275688845f11c28dd107d580a434f4565
ms.sourcegitcommit: 75db3b75d35d27034f9b56e7119c9d0cb7666830
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/03/2019
ms.locfileid: "2551134"
---
# <a name="acquire-and-dispose-a-ciap-fixed-asset"></a><span data-ttu-id="39def-103">Adquirir e alienar um ativo fixo do CIAP</span><span class="sxs-lookup"><span data-stu-id="39def-103">Acquire and dispose a CIAP fixed asset</span></span>

[!include [banner](../includes/banner.md)]

## <a name="acquire-a-ciap-fixed-asset"></a><span data-ttu-id="39def-104">​Adquirir um ativo fixo CIAP​</span><span class="sxs-lookup"><span data-stu-id="39def-104">Acquire a CIAP fixed asset</span></span>
<span data-ttu-id="39def-105">Use esta funcionalidade para registrar no módulo Livros fiscais a aquisição de um ativo fixo controlado pelo ICMS recuperável a longo prazo.</span><span class="sxs-lookup"><span data-stu-id="39def-105">Use this functionality to register in Fiscal books module the acquisition of a fixed asset controlled by the ICMS tax long term return.</span></span>

1. <span data-ttu-id="39def-106">Na página **Todas as ordens de compra**, no campo **Conta de fornecedor**, selecione um fornecedor.</span><span class="sxs-lookup"><span data-stu-id="39def-106">On the **All purchase orders** page, in the **Vendor account** field, select a vendor.</span></span>
2. <span data-ttu-id="39def-107">Clique em **Adicionar linha**.</span><span class="sxs-lookup"><span data-stu-id="39def-107">Click **Add line**.</span></span>
   -  <span data-ttu-id="39def-108">Preencha os campos **Número de item**, **CFOP**, **Quantidade**, **Preço unitário**.</span><span class="sxs-lookup"><span data-stu-id="39def-108">Fill in the **Item number**, **CFOP**, **Quantity**, **Unit price** fields.</span></span>
3. <span data-ttu-id="39def-109">Expanda a seção Detalhes da linha.</span><span class="sxs-lookup"><span data-stu-id="39def-109">Expand the Line details section.</span></span>
4. <span data-ttu-id="39def-110">Clique na guia **Ativos fixos**.</span><span class="sxs-lookup"><span data-stu-id="39def-110">Click the **Fixed assets** tab.</span></span>
5. <span data-ttu-id="39def-111">Selecione o campo **Sim para o novo ativo fixo?**.</span><span class="sxs-lookup"><span data-stu-id="39def-111">Select **Yes in the New fixed asset?** field.</span></span>
6. <span data-ttu-id="39def-112">No campo **Grupo de ativo fixo**, selecione um grupo de ativo fixo.</span><span class="sxs-lookup"><span data-stu-id="39def-112">In the **Fixed asset group** field, select a fixed asset group.</span></span>
7. <span data-ttu-id="39def-113">Na guia **Dimensões financeiras**, preencha os campos **CostCenter** e **Filial**.</span><span class="sxs-lookup"><span data-stu-id="39def-113">On the **Financial dimensions** tab, fill out the **CostCenter** and **Filial** fields.</span></span>
8. <span data-ttu-id="39def-114">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="39def-114">Click **Confirm**.</span></span>
9. <span data-ttu-id="39def-115">Na página **Todas as ordens de compra**, clique no link para selecionar uma Ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="39def-115">On the **All purchase orders** page, click the link to select a Purchase order.</span></span>
10. <span data-ttu-id="39def-116">No Painel de Ação, clique em **Fatura** > **Padrão de: Quantidade de recebimento de produtos**.</span><span class="sxs-lookup"><span data-stu-id="39def-116">On the Action Pane, click **Invoice** > **Default from: Product receipt quantity**.</span></span> <span data-ttu-id="39def-117">No campo **Quantidade padrão para linhas**, selecione uma quantidade.</span><span class="sxs-lookup"><span data-stu-id="39def-117">In the **Default quantity for lines** field, select a quantity.</span></span>
11. <span data-ttu-id="39def-118">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="39def-118">Click **OK**.</span></span>
12. <span data-ttu-id="39def-119">Preencha os campos **Modelo de documento**, **Chave de acesso**, **Data da fatura** e **Data de lançamento**.</span><span class="sxs-lookup"><span data-stu-id="39def-119">Fill in the **Document model**, **Access key**, **Invoice date** and **Posting date** fields.</span></span>
13. <span data-ttu-id="39def-120">Clique em **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="39def-120">Click **Post**.</span></span>
14. <span data-ttu-id="39def-121">Na página **Período de escrituração**, clique em **Criar novo período de escrituração**.</span><span class="sxs-lookup"><span data-stu-id="39def-121">On the **Booking period** page, click **Create new booking period**.</span></span>
15. <span data-ttu-id="39def-122">Preencha os campos **Estabelecimento fiscal**, **Mês** e **Ano**.</span><span class="sxs-lookup"><span data-stu-id="39def-122">Fill in the **Fiscal establishment**, **Month** and **Year** fields.</span></span>
16. <span data-ttu-id="39def-123">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="39def-123">Click **OK**.</span></span>
17. <span data-ttu-id="39def-124">Clique em **Sincronizar** > **OK**.</span><span class="sxs-lookup"><span data-stu-id="39def-124">Click **Sync** > **OK**.</span></span>
18. <span data-ttu-id="39def-125">Clique em **ICMS** > **Apuração de imposto ICMS** > **OK**.</span><span class="sxs-lookup"><span data-stu-id="39def-125">Click **ICMS** > **ICMS tax assessment** > **OK**.</span></span>
19. <span data-ttu-id="39def-126">Na página **Todos os ativos fixos CIAP**, clique no link para selecionar uma ID de ativo CIAP.</span><span class="sxs-lookup"><span data-stu-id="39def-126">On the **All CIAP fixed assets** page, click the link to select a CIAP asset ID.</span></span>
20. <span data-ttu-id="39def-127">Expanda a seção Detalhes da linha.</span><span class="sxs-lookup"><span data-stu-id="39def-127">Expand the Line details section.</span></span>
21. <span data-ttu-id="39def-128">Na página **Relatório CIAP**, no campo **Estabelecimento fiscal**, insira um estabelecimento fiscal.</span><span class="sxs-lookup"><span data-stu-id="39def-128">On the **CIAP Report** page, in the **Fiscal establishment** field, enter a fiscal establishment.</span></span>
22. <span data-ttu-id="39def-129">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="39def-129">Click **OK**.</span></span>

## <a name="dispose-of-a-ciap-fixed-asset"></a><span data-ttu-id="39def-130">Alienação de um ativo fixo CIAP</span><span class="sxs-lookup"><span data-stu-id="39def-130">Dispose of a CIAP fixed asset</span></span>
<span data-ttu-id="39def-131">Use esta funcionalidade para registrar no módulo Livros fiscais a alienação de um ativo fixo controlado pelo ICMS recuperável a longo prazo.</span><span class="sxs-lookup"><span data-stu-id="39def-131">Use this functionality to register in Fiscal books module the disposal of a fixed asset controlled by the ICMS tax long term return.</span></span>

1.  <span data-ttu-id="39def-132">Na página **Todas as faturas de texto livre**, clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="39def-132">On the **All free text invoices** page, click **New**.</span></span>
2.  <span data-ttu-id="39def-133">Preencha os campos **ID do estabelecimento fiscal**, **Conta do cliente**, **Data**, **Descrição**, **Conta principal**, **CFOP**, **Grupo de impostos**, **Grupo de impostos do item**, **Quantidade** e **Preço unitário**.</span><span class="sxs-lookup"><span data-stu-id="39def-133">Fill in the **Fiscal establishment ID**, **Customer account**, **Date**, **Description**, **Main account**, **CFOP**, **Sales tax group**, **Item sales tax group**, **Quantity** and **Unit price** fields.</span></span>
3.  <span data-ttu-id="39def-134">Expanda a seção **Detalhes da linha**, > no campo **Número do ativo fixo**, e insira um ativo fixo.</span><span class="sxs-lookup"><span data-stu-id="39def-134">Expand the **Line details** section, > in the **Fixed asset number** field, enter a fixed asset.</span></span>
4.  <span data-ttu-id="39def-135">Clique em **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="39def-135">Click **Post**.</span></span>
5.  <span data-ttu-id="39def-136">Expanda a seção **Conhecimento de embarque**, preencha os campos **Nome da transportadora**, **Tipo de volume**, **Quantidade de volume**, **Peso líquido** e **Peso bruto**.</span><span class="sxs-lookup"><span data-stu-id="39def-136">Expand the **Bill of lading** section, fill in the **Carrier name**, **Volume type**, **Volume quantity**, **Net weight**, **Gross weight** fields.</span></span>
6.  <span data-ttu-id="39def-137">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="39def-137">Click **OK**.</span></span>
7.  <span data-ttu-id="39def-138">No **Exportar/importar processo de NF-e** > **OK**.</span><span class="sxs-lookup"><span data-stu-id="39def-138">On the **Export/import NF-e process** > **OK**.</span></span>
8.  <span data-ttu-id="39def-139">Na página **Período de escrituração** > **Criar novo período de escrituração**.</span><span class="sxs-lookup"><span data-stu-id="39def-139">One the **Booking period** page > **Create new booking period**.</span></span>
9.  <span data-ttu-id="39def-140">Preencha os campos **Estabelecimento fiscal**, **Mês** e **Ano**.</span><span class="sxs-lookup"><span data-stu-id="39def-140">Fill in the **Fiscal establishment**, **Month** and **Year** fields.</span></span>
10. <span data-ttu-id="39def-141">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="39def-141">Click **OK**.</span></span>
11. <span data-ttu-id="39def-142">Clique em **Sincronizar** > **OK**.</span><span class="sxs-lookup"><span data-stu-id="39def-142">Click **Sync** > **OK**.</span></span>
12. <span data-ttu-id="39def-143">Clique em **ICMS** > **Apuração de imposto ICMS** > **OK**.</span><span class="sxs-lookup"><span data-stu-id="39def-143">Click **ICMS** > **ICMS tax assessment** > **OK**.</span></span>
13. <span data-ttu-id="39def-144">Na página **Todos os ativos fixos CIAP**, clique no link para selecionar uma ID de ativo CIAP.</span><span class="sxs-lookup"><span data-stu-id="39def-144">On the **All CIAP fixed assets** page, click the link to select a CIAP asset ID.</span></span>
14. <span data-ttu-id="39def-145">No **Relatório CIAP**, no campo **Estabelecimento fiscal**, selecione um estabelecimento fiscal.</span><span class="sxs-lookup"><span data-stu-id="39def-145">On the **CIAP Report**, in the **Fiscal establishment** field, select a fiscal establishment.</span></span>
15. <span data-ttu-id="39def-146">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="39def-146">Click **OK**.</span></span>
