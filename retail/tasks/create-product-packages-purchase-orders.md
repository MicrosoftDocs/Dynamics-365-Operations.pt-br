--- 
title: " Criar pacotes de produto para ordens de compra"
description: "Este procedimento mostra a criação de um pacote de produtos e a utilização dele em uma ordem de compra."
author: josaw1
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: a3be1e7aca7f0382aea55fa8a371c33c8b53df95
ms.contentlocale: pt-br
ms.lasthandoff: 08/29/2017

---
# <a name="create-product-packages-for-purchase-orders"></a><span data-ttu-id="260e7-103"> Criar pacotes de produto para ordens de compra</span><span class="sxs-lookup"><span data-stu-id="260e7-103">Create product packages for purchase orders</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="260e7-104">Este procedimento mostra a criação de um pacote de produtos e a utilização dele em uma ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="260e7-104">This procedure walks through creating a product package and using it on a purchase order.</span></span> <span data-ttu-id="260e7-105">A ordem de compra será usada para criar uma ordem para um conjunto predefinido de produtos.</span><span class="sxs-lookup"><span data-stu-id="260e7-105">The purchase order will be used to create an order for a pre-defined set of products.</span></span> <span data-ttu-id="260e7-106">Este procedimento usa a empresa de dados de demonstração USRT.</span><span class="sxs-lookup"><span data-stu-id="260e7-106">This procedure uses the USRT demo data company.</span></span>


## <a name="create-a-product-package"></a><span data-ttu-id="260e7-107">Criar um pacote de produtos</span><span class="sxs-lookup"><span data-stu-id="260e7-107">Create a product package</span></span>
1. <span data-ttu-id="260e7-108">Vá para Varejo e comércio > Gerenciamento de estoque > Reabastecimento > Pacotes de produto.</span><span class="sxs-lookup"><span data-stu-id="260e7-108">Go to Retail and commerce > Inventory management > Replenishment > Product packages.</span></span>
2. <span data-ttu-id="260e7-109">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="260e7-109">Click New.</span></span>
3. <span data-ttu-id="260e7-110">No campo Número do pacote, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="260e7-110">In the Package number field, type a value.</span></span>
4. <span data-ttu-id="260e7-111">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="260e7-111">In the Description field, type a value.</span></span>
5. <span data-ttu-id="260e7-112">No campo Conta de fornecedor, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="260e7-112">In the Vendor account field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="260e7-113">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="260e7-113">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="260e7-114">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="260e7-114">Click Add.</span></span>
8. <span data-ttu-id="260e7-115">No campo do número de item, digite '0160'.</span><span class="sxs-lookup"><span data-stu-id="260e7-115">In the Item number field, type '0160'.</span></span>
9. <span data-ttu-id="260e7-116">No campo Tamanho, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="260e7-116">In the Size field, click the drop-down button to open the lookup.</span></span>
10. <span data-ttu-id="260e7-117">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="260e7-117">In the list, click the link in the selected row.</span></span>
11. <span data-ttu-id="260e7-118">No campo Quantidade, insira um número.</span><span class="sxs-lookup"><span data-stu-id="260e7-118">In the Quantity field, enter a number.</span></span>
12. <span data-ttu-id="260e7-119">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="260e7-119">Click Add.</span></span>
13. <span data-ttu-id="260e7-120">No campo do número de item, digite '0160'.</span><span class="sxs-lookup"><span data-stu-id="260e7-120">In the Item number field, type '0160'.</span></span>
14. <span data-ttu-id="260e7-121">No campo Número da grade, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="260e7-121">In the Variant number field, click the drop-down button to open the lookup.</span></span>
15. <span data-ttu-id="260e7-122">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="260e7-122">In the list, click the link in the selected row.</span></span>
16. <span data-ttu-id="260e7-123">No campo Quantidade, insira um número.</span><span class="sxs-lookup"><span data-stu-id="260e7-123">In the Quantity field, enter a number.</span></span>
17. <span data-ttu-id="260e7-124">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="260e7-124">Click Add.</span></span>
18. <span data-ttu-id="260e7-125">No campo Número de item, digite '0175'.</span><span class="sxs-lookup"><span data-stu-id="260e7-125">In the Item number field, type '0175'.</span></span>
19. <span data-ttu-id="260e7-126">No campo Quantidade, insira um número.</span><span class="sxs-lookup"><span data-stu-id="260e7-126">In the Quantity field, enter a number.</span></span>
20. <span data-ttu-id="260e7-127">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="260e7-127">Click Save.</span></span>
21. <span data-ttu-id="260e7-128">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="260e7-128">Close the page.</span></span>

## <a name="add-package-to-puchase-order"></a><span data-ttu-id="260e7-129">Adicione o pacote à ordem de compra</span><span class="sxs-lookup"><span data-stu-id="260e7-129">Add package to puchase order</span></span>
1. <span data-ttu-id="260e7-130">Vá para Contas a pagar > Ordens de compra > Todas as ordens de compra.</span><span class="sxs-lookup"><span data-stu-id="260e7-130">Go to Accounts payable > Purchase orders > All purchase orders.</span></span>
2. <span data-ttu-id="260e7-131">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="260e7-131">Click New.</span></span>
3. <span data-ttu-id="260e7-132">No campo Conta de fornecedor, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="260e7-132">In the Vendor account field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="260e7-133">Na lista, selecione o mesmo fornecedor para o qual o pacote de produtos foi criado anteriormente, se um fornecedor foi selecionado.</span><span class="sxs-lookup"><span data-stu-id="260e7-133">In the list, select the same vendor that the product package was previously created for, if a vendor was selected.</span></span>
5. <span data-ttu-id="260e7-134">Alternar a expansão da seção Geral.</span><span class="sxs-lookup"><span data-stu-id="260e7-134">Toggle the expansion of the General section.</span></span>
6. <span data-ttu-id="260e7-135">No campo Local, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="260e7-135">In the Site field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="260e7-136">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="260e7-136">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="260e7-137">No campo Depósito, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="260e7-137">In the Warehouse field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="260e7-138">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="260e7-138">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="260e7-139">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="260e7-139">Click OK.</span></span>
11. <span data-ttu-id="260e7-140">Ative a expansão da seção Detalhes de linha.</span><span class="sxs-lookup"><span data-stu-id="260e7-140">Toggle the expansion of the Line details section.</span></span>
12. <span data-ttu-id="260e7-141">Clique na guia de Pacotes do produto.</span><span class="sxs-lookup"><span data-stu-id="260e7-141">Click the Product packages tab.</span></span>
13. <span data-ttu-id="260e7-142">Clique na Linha de ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="260e7-142">Click Purchase order line.</span></span>
14. <span data-ttu-id="260e7-143">Clique em Criar linhas a partir de pacote.</span><span class="sxs-lookup"><span data-stu-id="260e7-143">Click Create lines from package.</span></span>
15. <span data-ttu-id="260e7-144">Na lista, localize e selecione o grupo de produtos criado na etapa anterior.</span><span class="sxs-lookup"><span data-stu-id="260e7-144">In the list, find and select the product package created in previous step.</span></span>
16. <span data-ttu-id="260e7-145">No campo Quantidade, insira um número.</span><span class="sxs-lookup"><span data-stu-id="260e7-145">In the Quantity field, enter a number.</span></span>
17. <span data-ttu-id="260e7-146">Clique em Criar.</span><span class="sxs-lookup"><span data-stu-id="260e7-146">Click Create.</span></span>
18. <span data-ttu-id="260e7-147">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="260e7-147">Click Save.</span></span>


