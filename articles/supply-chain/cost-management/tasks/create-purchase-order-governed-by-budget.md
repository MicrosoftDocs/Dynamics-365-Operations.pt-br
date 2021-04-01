---
title: Criar uma ordem de compra regida por orçamento
description: Use este procedimento para criar uma ordem de compra que seja verificada para o orçamento disponível.
author: ShylaThompson
manager: tfehr
ms.date: 06/20/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 100db102f74d477bcfde48a24828b817fd65e033
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5239486"
---
# <a name="create-a-purchase-order-governed-by-budget"></a><span data-ttu-id="5695f-103">Criar uma ordem de compra regida por orçamento</span><span class="sxs-lookup"><span data-stu-id="5695f-103">Create a purchase order governed by budget</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="5695f-104">Use este procedimento para criar uma ordem de compra que seja verificada para o orçamento disponível.</span><span class="sxs-lookup"><span data-stu-id="5695f-104">Use this procedure to create a purchase order that is checked for available budget.</span></span> <span data-ttu-id="5695f-105">Esta gravação usa os dados da empresa de demonstração USMF.</span><span class="sxs-lookup"><span data-stu-id="5695f-105">This recording uses the USMF demo data company.</span></span>


## <a name="review-the-budget-control-configuration"></a><span data-ttu-id="5695f-106">Revise a configuração de controle de orçamento</span><span class="sxs-lookup"><span data-stu-id="5695f-106">Review the budget control configuration</span></span>
1. <span data-ttu-id="5695f-107">Vá para Orçamento > Configuração > Controle de orçamento > Configuração de controle de orçamento.</span><span class="sxs-lookup"><span data-stu-id="5695f-107">Go to Budgeting > Setup > Budget control > Budget control configuration.</span></span>
2. <span data-ttu-id="5695f-108">Clique na guia disponível dos fundos de orçamento.</span><span class="sxs-lookup"><span data-stu-id="5695f-108">Click the Budget funds available tab.</span></span>
3. <span data-ttu-id="5695f-109">Clique na guia Documentos e diários.</span><span class="sxs-lookup"><span data-stu-id="5695f-109">Click the Documents and journals tab.</span></span>
4. <span data-ttu-id="5695f-110">Clique na guia Definir regras de controle de orçamento.</span><span class="sxs-lookup"><span data-stu-id="5695f-110">Click the Define budget control rules tab.</span></span>
5. <span data-ttu-id="5695f-111">Clique na guia Definir os grupos orçamentários.</span><span class="sxs-lookup"><span data-stu-id="5695f-111">Click the Define budget groups tab.</span></span>
6. <span data-ttu-id="5695f-112">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="5695f-112">Close the page.</span></span>

## <a name="create-the-purchase-order-header"></a><span data-ttu-id="5695f-113">Criar o cabeçalho da ordem de compra</span><span class="sxs-lookup"><span data-stu-id="5695f-113">Create the purchase order header</span></span>
1. <span data-ttu-id="5695f-114">Vá para Aquisição e fornecimento > Ordens de compra > Todas as ordens de compra.</span><span class="sxs-lookup"><span data-stu-id="5695f-114">Go to Procurement and sourcing > Purchase orders > All purchase orders.</span></span>
2. <span data-ttu-id="5695f-115">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="5695f-115">Click New.</span></span>
3. <span data-ttu-id="5695f-116">No campo Conta de fornecedor, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="5695f-116">In the Vendor account field, enter or select a value.</span></span>
4. <span data-ttu-id="5695f-117">Expanda a seção Geral.</span><span class="sxs-lookup"><span data-stu-id="5695f-117">Expand the General section.</span></span>
5. <span data-ttu-id="5695f-118">No campo Data contábil, defina a data como '01-01-2016'.</span><span class="sxs-lookup"><span data-stu-id="5695f-118">In the Accounting date field, set the date to '2016-01-01'.</span></span>
6. <span data-ttu-id="5695f-119">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="5695f-119">Click OK.</span></span>

## <a name="add-a-purchase-order-line"></a><span data-ttu-id="5695f-120">Adicionar uma linha de ordem de compra</span><span class="sxs-lookup"><span data-stu-id="5695f-120">Add a purchase order line</span></span>
1. <span data-ttu-id="5695f-121">No campo Categoria de compras, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="5695f-121">In the Procurement category field, enter or select a value.</span></span>
2. <span data-ttu-id="5695f-122">Defina Quantidade como '2'.</span><span class="sxs-lookup"><span data-stu-id="5695f-122">Set Quantity to '2'.</span></span>
3. <span data-ttu-id="5695f-123">No campo Unidade, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="5695f-123">In the Unit field, enter or select a value.</span></span>
4. <span data-ttu-id="5695f-124">Defina o preço unitário como "10000".</span><span class="sxs-lookup"><span data-stu-id="5695f-124">Set Unit price to '10000'.</span></span>
5. <span data-ttu-id="5695f-125">Clique em Financeiros.</span><span class="sxs-lookup"><span data-stu-id="5695f-125">Click Financials.</span></span>
6. <span data-ttu-id="5695f-126">Clique em Distribuir valores.</span><span class="sxs-lookup"><span data-stu-id="5695f-126">Click Distribute amounts.</span></span>
7. <span data-ttu-id="5695f-127">No campo Conta contábil, especifique o valor '601300-001-023--'.</span><span class="sxs-lookup"><span data-stu-id="5695f-127">In the Ledger account field, specify the value '601300-001-023--'.</span></span>
8. <span data-ttu-id="5695f-128">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="5695f-128">Close the page.</span></span>

## <a name="perform-budget-checking"></a><span data-ttu-id="5695f-129">Executar verificação de orçamento</span><span class="sxs-lookup"><span data-stu-id="5695f-129">Perform budget checking</span></span>
1. <span data-ttu-id="5695f-130">Clique em Financeiros.</span><span class="sxs-lookup"><span data-stu-id="5695f-130">Click Financials.</span></span>
2. <span data-ttu-id="5695f-131">Clique em Executar verificação de orçamento.</span><span class="sxs-lookup"><span data-stu-id="5695f-131">Click Perform budget checking.</span></span>
3. <span data-ttu-id="5695f-132">Clique em Financeiros.</span><span class="sxs-lookup"><span data-stu-id="5695f-132">Click Financials.</span></span>
4. <span data-ttu-id="5695f-133">Clique em Erros ou avisos da verificação de orçamento.</span><span class="sxs-lookup"><span data-stu-id="5695f-133">Click Budget check errors or warnings.</span></span>
5. <span data-ttu-id="5695f-134">Clique em Fechar.</span><span class="sxs-lookup"><span data-stu-id="5695f-134">Click Close.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]