---
title: Configurar políticas de fatura de fornecedor
description: Este tópico explica como configurar políticas de fatura de fornecedor.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 07/11/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendParameters,  SysPolicyListPage, SysPolicyParameters, SysPolicySourceDocumentRuleType, SysPolicy, SysPolicySourceDocumentRule, SysQueryForm, SysQueryTableLookUp, SysQueryPrefixLookUp, SysQueryFieldLookUp
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 72f017294c976dcd1b7ddda01ac9e39252f036d6
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/30/2019
ms.locfileid: "2250270"
---
# <a name="set-up-vendor-invoice-policies"></a><span data-ttu-id="bbe5d-103">Configurar políticas de fatura de fornecedor</span><span class="sxs-lookup"><span data-stu-id="bbe5d-103">Set up vendor invoice policies</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="bbe5d-104">Este tópico explica como configurar políticas de fatura de fornecedor.</span><span class="sxs-lookup"><span data-stu-id="bbe5d-104">This topic explains how to set up vendor invoice policies.</span></span> <span data-ttu-id="bbe5d-105">As políticas de fatura de fornecedor são executadas quando você lança uma fatura de fornecedor usando a página de fatura do fornecedor e quando você abre a página de violações de política da fatura de fornecedor.</span><span class="sxs-lookup"><span data-stu-id="bbe5d-105">Vendor invoice policies are run when you post a vendor invoice by using the Vendor invoice page and when you open the vendor invoice Policy violations page.</span></span> <span data-ttu-id="bbe5d-106">Você também pode configurar o fluxo de trabalho da fatura do fornecedor para executar as políticas de fatura do fornecedor todas as vezes que você enviar uma fatura para o fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="bbe5d-106">You can also configure the vendor invoice workflow to run vendor invoice policies every time that you submit an invoice to workflow.</span></span> 

- <span data-ttu-id="bbe5d-107">As políticas de fatura do fornecedor não se aplicam às faturas que foram criadas no registro de fatura ou no diário de faturas.</span><span class="sxs-lookup"><span data-stu-id="bbe5d-107">Vendor invoice policies do not apply to invoices that were created in the invoice register or invoice journal.</span></span>  
- <span data-ttu-id="bbe5d-108">A validação de conciliação de fatura não usa as políticas da fatura do fornecedor, mas é configurada na página de parâmetros de contas a pagar.</span><span class="sxs-lookup"><span data-stu-id="bbe5d-108">Invoice matching validation does not use vendor invoice policies, but is instead set up in the Accounts payable parameters page.</span></span>  
- <span data-ttu-id="bbe5d-109">Este registro usa a empresa de dados de demonstração USMF.</span><span class="sxs-lookup"><span data-stu-id="bbe5d-109">This recording uses the USMF demo company.</span></span> <span data-ttu-id="bbe5d-110">A função gerente de contas a pagar ou gerente de contabilidade executaria estas etapas.</span><span class="sxs-lookup"><span data-stu-id="bbe5d-110">The accounts payable manager or accounting manager role would perform these steps.</span></span> <span data-ttu-id="bbe5d-111">Antes de começar, verifique se a configuração conciliação de faturas está marcada.</span><span class="sxs-lookup"><span data-stu-id="bbe5d-111">Before you begin, make sure that the Invoice matching configuration key is selected.</span></span>


## <a name="prepare-to-create-vendor-invoice-policies"></a><span data-ttu-id="bbe5d-112">Preparar para criar políticas de fatura do fornecedor</span><span class="sxs-lookup"><span data-stu-id="bbe5d-112">Prepare to create vendor invoice policies</span></span>
1. <span data-ttu-id="bbe5d-113">Vá para **Painel de navegação > Módulos > Contas a pagar > Configuração > Parâmetros de contas a pagar**.</span><span class="sxs-lookup"><span data-stu-id="bbe5d-113">Go to **Navigation pane > Modules > Accounts payable > Setup > Accounts payable parameters**.</span></span>
2. <span data-ttu-id="bbe5d-114">Selecione a guia **Validação de fatura**.</span><span class="sxs-lookup"><span data-stu-id="bbe5d-114">Select the **Invoice validation** tab.</span></span>
3. <span data-ttu-id="bbe5d-115">Marque ou desmarque a caixa de seleção **Atualizar automaticamente cabeçalho de fatura**.</span><span class="sxs-lookup"><span data-stu-id="bbe5d-115">Select or clear the **Automatically update invoice header** status check box.</span></span>
4. <span data-ttu-id="bbe5d-116">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="bbe5d-116">Select **OK**.</span></span>
5. <span data-ttu-id="bbe5d-117">No campo **Lançar fatura com discrepâncias**, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="bbe5d-117">In the **Post invoice with discrepancies** field, select an option.</span></span>
6. <span data-ttu-id="bbe5d-118">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="bbe5d-118">Close the page.</span></span>
7. <span data-ttu-id="bbe5d-119">Vá para **Painel de navegação > Módulos > Contas a pagar > Configuração de política > Políticas de fatura de fornecedor**.</span><span class="sxs-lookup"><span data-stu-id="bbe5d-119">Go to **Navigation pane > Modules > Accounts payable > Policy setup > Vendor invoice policies**.</span></span>
8. <span data-ttu-id="bbe5d-120">Selecione **Parâmetros**.</span><span class="sxs-lookup"><span data-stu-id="bbe5d-120">Select **Parameters**.</span></span>
9. <span data-ttu-id="bbe5d-121">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="bbe5d-121">Select **Add**.</span></span>
10. <span data-ttu-id="bbe5d-122">Feche a página para voltar à home page.</span><span class="sxs-lookup"><span data-stu-id="bbe5d-122">Close the page to return to the home page.</span></span>

## <a name="create-policy-rule-types-for-vendor-invoices"></a><span data-ttu-id="bbe5d-123">Criar tipos de regras de política para faturas de fornecedor</span><span class="sxs-lookup"><span data-stu-id="bbe5d-123">Create policy rule types for vendor invoices</span></span>
1. <span data-ttu-id="bbe5d-124">Vá para **Painel de navegação > Módulos > Contas a pagar > Configuração de política > Tipos de regra de política de fatura de fornecedor**.</span><span class="sxs-lookup"><span data-stu-id="bbe5d-124">Go to **Navigation pane > Modules > Accounts payable > Policy setup > Vendor invoice policy rule types**.</span></span>
2. <span data-ttu-id="bbe5d-125">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="bbe5d-125">Select **New**.</span></span>
3. <span data-ttu-id="bbe5d-126">Nos campos **Nome da regra** e **Descrição**, digite valores.</span><span class="sxs-lookup"><span data-stu-id="bbe5d-126">In the **Rule name** and **Description** fields, type values.</span></span>
4. <span data-ttu-id="bbe5d-127">No campo **Nome da consulta**, selecione o botão suspenso para abrir a pesquisa e então selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="bbe5d-127">In the **Query name** field, select the drop-down button to open the lookup, then selec the desired record.</span></span>
5. <span data-ttu-id="bbe5d-128">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="bbe5d-128">Select **Save**.</span></span>
6. <span data-ttu-id="bbe5d-129">Feche a página para voltar à home page.</span><span class="sxs-lookup"><span data-stu-id="bbe5d-129">Close the page to return to the home page.</span></span>

## <a name="define-a-vendor-invoice-policy"></a><span data-ttu-id="bbe5d-130">Definir uma política de fatura de fornecedor</span><span class="sxs-lookup"><span data-stu-id="bbe5d-130">Define a vendor invoice policy</span></span>
1. <span data-ttu-id="bbe5d-131">Vá para **Painel de navegação > Módulos > Contas a pagar > Configuração de política > Políticas de fatura de fornecedor**.</span><span class="sxs-lookup"><span data-stu-id="bbe5d-131">Go to **Navigation pane > Modules > Accounts payable > Policy setup > Vendor invoice policies**.</span></span>
2. <span data-ttu-id="bbe5d-132">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="bbe5d-132">Select **New**.</span></span>
3. <span data-ttu-id="bbe5d-133">Nos campos **Nome** e **Descrição**, digite valores.</span><span class="sxs-lookup"><span data-stu-id="bbe5d-133">In the **Name** and **Description** fields, type values.</span></span>
4. <span data-ttu-id="bbe5d-134">Expanda ou recolha a seção de **Organizações de política**.</span><span class="sxs-lookup"><span data-stu-id="bbe5d-134">Expand or collapse the **Policy organizations** section.</span></span>
5. <span data-ttu-id="bbe5d-135">Na árvore, selecione **Contoso Entertainment System USA**.</span><span class="sxs-lookup"><span data-stu-id="bbe5d-135">In the tree, select **Contoso Entertainment System USA**.</span></span>
6. <span data-ttu-id="bbe5d-136">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="bbe5d-136">Select **Add**.</span></span>
7. <span data-ttu-id="bbe5d-137">Expanda ou recolha a seção de **Regras de política**.</span><span class="sxs-lookup"><span data-stu-id="bbe5d-137">Expand or collapse the **Policy rules** section.</span></span>
8. <span data-ttu-id="bbe5d-138">Selecione **Criar regra de política**.</span><span class="sxs-lookup"><span data-stu-id="bbe5d-138">Select **Create policy rule**.</span></span>
9. <span data-ttu-id="bbe5d-139">No campo **Descrição de regra de política**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="bbe5d-139">In the **Policy rule description** field, type a value.</span></span>
10. <span data-ttu-id="bbe5d-140">Selecione **Filtro**.</span><span class="sxs-lookup"><span data-stu-id="bbe5d-140">Select **Filter**.</span></span>
11. <span data-ttu-id="bbe5d-141">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="bbe5d-141">Select **Add**.</span></span> <span data-ttu-id="bbe5d-142">Selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="bbe5d-142">Select the desired record.</span></span>
12. <span data-ttu-id="bbe5d-143">Nos campos **Tabela**, **Tabela derivada** e **Campo**, selecione ou insira opções dos menus suspensos.</span><span class="sxs-lookup"><span data-stu-id="bbe5d-143">In the **Table**, **Derived table**, and **Field** fields, select or enter options from the drop-down menus.</span></span>
13. <span data-ttu-id="bbe5d-144">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="bbe5d-144">Close the page.</span></span>
14. <span data-ttu-id="bbe5d-145">No campo **Critérios**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="bbe5d-145">In the **Criteria** field, type a value.</span></span>
15. <span data-ttu-id="bbe5d-146">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="bbe5d-146">Select **OK**.</span></span>
16. <span data-ttu-id="bbe5d-147">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="bbe5d-147">Select **OK**.</span></span>
17. <span data-ttu-id="bbe5d-148">Feche as páginas para voltar à home page.</span><span class="sxs-lookup"><span data-stu-id="bbe5d-148">Close the pages to return to the home page.</span></span>
