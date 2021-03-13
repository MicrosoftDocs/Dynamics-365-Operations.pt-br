---
title: Referências a faturas originais em notas de crédito
description: Este tópico explica como configurar e imprimir os números de fatura originais nas notas de crédito relacionadas.
author: ilkond
manager: AnnBe
ms.date: 01/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: ilyako
ms.search.validFrom: 2021-03-19
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 673288f04b33aa2a578f9e2e7913dbe7ac309644
ms.sourcegitcommit: 7cdec5469ff0da145ac4e01caf3287d0627ae2dc
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/01/2021
ms.locfileid: "5099993"
---
# <a name="references-to-original-invoices-in-credit-notes"></a><span data-ttu-id="0f282-103">Referências a faturas originais em notas de crédito</span><span class="sxs-lookup"><span data-stu-id="0f282-103">References to original invoices in credit notes</span></span>

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

<span data-ttu-id="0f282-104">Em alguns países e regiões, há um requisito legal de que notas de crédito impressas incluem referências às faturas originais.</span><span class="sxs-lookup"><span data-stu-id="0f282-104">In some countries and regions, there is a legal requirement that printed credit notes include references to the original invoices.</span></span> <span data-ttu-id="0f282-105">Este tópico explica como configurar e imprimir os números de fatura originais nas notas de crédito relacionadas.</span><span class="sxs-lookup"><span data-stu-id="0f282-105">This topic explains how to set up and print the original invoice numbers in related credit notes.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="0f282-106">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="0f282-106">Prerequisites</span></span>

- <span data-ttu-id="0f282-107">No espaço de trabalho **Gerenciamento de recursos**, ative o recurso **Layout de faturamento de crédito para vendas e relatórios de faturas de projetos**.</span><span class="sxs-lookup"><span data-stu-id="0f282-107">In the **Feature management** workspace, turn on the **Credit invoicing layout for sales and project invoice reports** feature.</span></span> <span data-ttu-id="0f282-108">Para obter mais informações, consulte [Visão geral do Gerenciamento de recursos](../../fin-and-ops/get-started/feature-management/feature-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="0f282-108">For more information, see [Feature management overview](../../fin-and-ops/get-started/feature-management/feature-management-overview.md).</span></span>
- <span data-ttu-id="0f282-109">Os formatos imprimíveis dos documentos necessários devem ser configurados no gerenciamento de impressão.</span><span class="sxs-lookup"><span data-stu-id="0f282-109">The printable formats of the required documents must be configured in Print management.</span></span>

<span data-ttu-id="0f282-110">A funcionalidade descrita neste tópico aplica-se aos seguintes documentos:</span><span class="sxs-lookup"><span data-stu-id="0f282-110">The functionality that is described in this topic applies to the following documents:</span></span>

<span data-ttu-id="0f282-111">**Contas a receber**</span><span class="sxs-lookup"><span data-stu-id="0f282-111">**Accounts receivable**</span></span>

- <span data-ttu-id="0f282-112">Nota de crédito em texto livre</span><span class="sxs-lookup"><span data-stu-id="0f282-112">Free text credit note</span></span>
- <span data-ttu-id="0f282-113">Nota de crédito de clientes</span><span class="sxs-lookup"><span data-stu-id="0f282-113">Customer credit note</span></span>

<span data-ttu-id="0f282-114">**Gerenciamento e contabilidade do projeto**</span><span class="sxs-lookup"><span data-stu-id="0f282-114">**Project management and accounting**</span></span>

- <span data-ttu-id="0f282-115">Nota de crédito do projeto</span><span class="sxs-lookup"><span data-stu-id="0f282-115">Project credit note</span></span>

## <a name="configure-accounts-receivable-parameters"></a><span data-ttu-id="0f282-116">Configurar Parâmetros de contas a receber</span><span class="sxs-lookup"><span data-stu-id="0f282-116">Configure Accounts receivable parameters</span></span>

<span data-ttu-id="0f282-117">Siga estas etapas para definir o parâmetro que controla se as referências às faturas originais são impressas em notas de crédito relacionadas.</span><span class="sxs-lookup"><span data-stu-id="0f282-117">Follow these steps to set the parameter that controls whether references to the original invoices are printed in related credit notes.</span></span>

1. <span data-ttu-id="0f282-118">Vá para **Contas a receber** \> **Configuração** \> **Parâmetros de contas a receber**.</span><span class="sxs-lookup"><span data-stu-id="0f282-118">Go to **Accounts receivable** \> **Setup** \> **Accounts receivable parameters**.</span></span>
2. <span data-ttu-id="0f282-119">Na guia **Atualizações**, na FastTab **Fatura**, defina a opção **Aplicar o layout de faturamento de crédito para vendas e relatórios de faturas de projetos** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="0f282-119">On the **Updates** tab, on the **Invoice** FastTab, set the **Apply the credit invoicing layout into sales and project invoice reports** option to **Yes**.</span></span>

![Configurar Parâmetros de contas a receber](media/original-invoice-number-in-credit-note.jpg)

## <a name="define-references-to-original-invoices"></a><span data-ttu-id="0f282-121">Definir referências a faturas originais</span><span class="sxs-lookup"><span data-stu-id="0f282-121">Define references to original invoices</span></span>

<span data-ttu-id="0f282-122">Use os procedimentos a seguir para definir referências a faturas originais com base no tipo de documento.</span><span class="sxs-lookup"><span data-stu-id="0f282-122">Use the following procedures to define references to original invoices, based on the document type.</span></span>

### <a name="free-text-credit-note"></a><span data-ttu-id="0f282-123">Nota de crédito em texto livre</span><span class="sxs-lookup"><span data-stu-id="0f282-123">Free text credit note</span></span>

1. <span data-ttu-id="0f282-124">Acesse **Contas a receber** \> **Faturas** \> **Todas as faturas de texto livre**.</span><span class="sxs-lookup"><span data-stu-id="0f282-124">Go to **Accounts receivable** \> **Invoices** \> **All free text invoices**.</span></span>
2. <span data-ttu-id="0f282-125">Crie uma nova nota de crédito ou selecione uma nota de crédito existente.</span><span class="sxs-lookup"><span data-stu-id="0f282-125">Create a new credit note, or select an existing credit note.</span></span>
3. <span data-ttu-id="0f282-126">Abra a fatura.</span><span class="sxs-lookup"><span data-stu-id="0f282-126">Open the invoice.</span></span>
4. <span data-ttu-id="0f282-127">No Painel de Ações, na guia **Fatura**, no grupo **Funções**, selecione **Faturamento de crédito**.</span><span class="sxs-lookup"><span data-stu-id="0f282-127">On the Action Pane, on the **Invoice** tab, in the **Functions** group, select **Credit invoicing**.</span></span>
5. <span data-ttu-id="0f282-128">Insira a referência à fatura original e selecione o motivo da correção.</span><span class="sxs-lookup"><span data-stu-id="0f282-128">Enter the reference to the original invoice, and select the reason for the correction.</span></span>

![Definir a referência para uma fatura de texto livre](media/reference-original-invoice-FTI.jpg)

### <a name="customer-credit-note"></a><span data-ttu-id="0f282-130">Nota de crédito de clientes</span><span class="sxs-lookup"><span data-stu-id="0f282-130">Customer credit note</span></span>

1. <span data-ttu-id="0f282-131">Acesse **Contas a receber** \> **Ordens** \> **Todas as ordens de vendas**.</span><span class="sxs-lookup"><span data-stu-id="0f282-131">Go to **Accounts receivable** \> **Orders** \> **All sales orders**.</span></span>
2. <span data-ttu-id="0f282-132">Selecione e abra a ordem de venda faturada a ser corrigida.</span><span class="sxs-lookup"><span data-stu-id="0f282-132">Select and open the invoiced sales order that must be corrected.</span></span>
3. <span data-ttu-id="0f282-133">No Painel de Ações, na guia **Vender**, no grupo **Nota de crédito**, selecione **Nota de crédito**.</span><span class="sxs-lookup"><span data-stu-id="0f282-133">On the Action Pane, on the **Sell** tab, in the **Credit note** group, select **Credit note**.</span></span>
4. <span data-ttu-id="0f282-134">Insira o motivo da correção.</span><span class="sxs-lookup"><span data-stu-id="0f282-134">Enter the reason for the correction.</span></span> <span data-ttu-id="0f282-135">A referência à fatura original é estabelecida automaticamente.</span><span class="sxs-lookup"><span data-stu-id="0f282-135">The reference to the original invoice is automatically established.</span></span>

![Definir a referência para uma ordem de venda](media/reference-original-invoice-SO.jpg)

### <a name="project-credit-note"></a><span data-ttu-id="0f282-137">Nota de crédito do projeto</span><span class="sxs-lookup"><span data-stu-id="0f282-137">Project credit note</span></span>

1. <span data-ttu-id="0f282-138">Acesse **Gerenciamento e contabilidade de projeto** \> **Faturas de projeto** \> **Faturas de projeto**.</span><span class="sxs-lookup"><span data-stu-id="0f282-138">Go to **Project management and accounting** \> **Project invoices** \> **Project invoices**.</span></span>
2. <span data-ttu-id="0f282-139">Selecione e abra a fatura de projeto a ser corrigida.</span><span class="sxs-lookup"><span data-stu-id="0f282-139">Select and open the project invoice that must be corrected.</span></span>
3. <span data-ttu-id="0f282-140">No Painel de Ações, na guia **Fatura de projeto**, no grupo **Funções**, selecione **Selecionar nota de crédito**.</span><span class="sxs-lookup"><span data-stu-id="0f282-140">On the Action Pane, on the **Project invoice** tab, in the **Functions** group, select **Select for credit note**.</span></span>
4. <span data-ttu-id="0f282-141">Selecione **Faturamento de crédito**.</span><span class="sxs-lookup"><span data-stu-id="0f282-141">Select **Credit invoicing**.</span></span>
5. <span data-ttu-id="0f282-142">Insira o motivo da correção.</span><span class="sxs-lookup"><span data-stu-id="0f282-142">Enter the reason for the correction.</span></span> <span data-ttu-id="0f282-143">A referência à fatura original é estabelecida automaticamente.</span><span class="sxs-lookup"><span data-stu-id="0f282-143">The reference to the original invoice is automatically established.</span></span>

![Definir a referência para uma fatura de projeto](media/reference-original-invoice-project.jpg)

## <a name="printing-credit-notes"></a><span data-ttu-id="0f282-145">Imprimir notas de crédito</span><span class="sxs-lookup"><span data-stu-id="0f282-145">Printing credit notes</span></span>

<span data-ttu-id="0f282-146">Quando você imprime notas de crédito de texto livre, cliente e projeto, elas incluem a referência à fatura original e a razão da correção.</span><span class="sxs-lookup"><span data-stu-id="0f282-146">When you print free text, customer, and project credit notes, they will include the reference to the original invoice and the correction reason.</span></span>

![Nota de crédito impressa](media/credit-note-FTI.jpg)

> [!NOTE]
> <span data-ttu-id="0f282-148">Verifique se os formatos imprimíveis dos documentos estão configurados corretamente, supondo que as referências a faturas originais serão impressas.</span><span class="sxs-lookup"><span data-stu-id="0f282-148">Make sure that the printable formats of the documents are correctly configured, on the assumption that references to original invoices will be printed.</span></span>
