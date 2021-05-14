---
title: Criar uma lista de materiais para um produto mestre baseado na dimensão
description: Para esse procedimento é necessário ter concluído as 4 guias anteriores nesta sequência de oito registros.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductMaintainWorkspace, EcoResProductOpenCasesFormPart, EcoResProductDetailsExtended, BOMConsistOf, BOMTable, InventItemIdLookupSimple, HcmWorkerLookUp
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 13053dd87242963586678b46c64493feb3383c4c
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/20/2021
ms.locfileid: "5920696"
---
# <a name="create-a-bill-of-materials-for-a-dimension-based-product-master"></a><span data-ttu-id="29da9-103">Criar uma lista de materiais para um produto mestre baseado na dimensão</span><span class="sxs-lookup"><span data-stu-id="29da9-103">Create a bill of materials for a dimension-based product master</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="29da9-104">Para esse procedimento é necessário ter concluído as 4 guias anteriores nesta sequência de oito registros.</span><span class="sxs-lookup"><span data-stu-id="29da9-104">For this procedure you should have completed the previous 4 guides in this sequence of eight recordings.</span></span> <span data-ttu-id="29da9-105">Os primeiras 4 registros configuram os dados necessários para concluir este procedimento.</span><span class="sxs-lookup"><span data-stu-id="29da9-105">The first 4 recordings set up data that is required to complete this procedure.</span></span> <span data-ttu-id="29da9-106">A empresa de dados demo usada para criar este procedimento é USMF.</span><span class="sxs-lookup"><span data-stu-id="29da9-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="29da9-107">Esta tarefa é tratada normalmente pelo designer do produto.</span><span class="sxs-lookup"><span data-stu-id="29da9-107">This task is typically handled by the product designer.</span></span>

## <a name="select-the-product"></a><span data-ttu-id="29da9-108">Selecionar o produto</span><span class="sxs-lookup"><span data-stu-id="29da9-108">Select the product</span></span>

1. <span data-ttu-id="29da9-109">Vá para **Gerenciamento de informações do produto \> Produtos \> Produtos liberados**.</span><span class="sxs-lookup"><span data-stu-id="29da9-109">Go to **Product information management \> Products \> Released products**.</span></span>
1. <span data-ttu-id="29da9-110">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="29da9-110">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="29da9-111">Localize o produto mestre liberado com tecnologia de configuração baseada em dimensão que você criou no primeiro guia de tarefa nesta sequência.</span><span class="sxs-lookup"><span data-stu-id="29da9-111">Find the released product master with dimension-based configuration technology that you created in the first task guide in this sequence.</span></span>  
1. <span data-ttu-id="29da9-112">No Painel de Ação, selecione **Engenheiro**.</span><span class="sxs-lookup"><span data-stu-id="29da9-112">On the Action Pane, select **Engineer**.</span></span>
1. <span data-ttu-id="29da9-113">Selecione **Versões da BOM**.</span><span class="sxs-lookup"><span data-stu-id="29da9-113">Select **BOM versions**.</span></span>

## <a name="create-new-bom-and-bom-version"></a><span data-ttu-id="29da9-114">Criar uma nova BOM e versão da BOM</span><span class="sxs-lookup"><span data-stu-id="29da9-114">Create new BOM and BOM version</span></span>

1. <span data-ttu-id="29da9-115">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="29da9-115">Select **New**.</span></span>
1. <span data-ttu-id="29da9-116">Selecione **BOM e versão da BOM**.</span><span class="sxs-lookup"><span data-stu-id="29da9-116">Select **BOM and BOM version**.</span></span>
1. <span data-ttu-id="29da9-117">No campo **Nome**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="29da9-117">In the **Name** field, type a value.</span></span>
    * <span data-ttu-id="29da9-118">Configurações do site</span><span class="sxs-lookup"><span data-stu-id="29da9-118">Setting a site</span></span>  
    * <span data-ttu-id="29da9-119">Nesse procedimento, não definimos um site específico da BOM.</span><span class="sxs-lookup"><span data-stu-id="29da9-119">In this procedure we don't set a specific site for the BOM.</span></span>  
1. <span data-ttu-id="29da9-120">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="29da9-120">Select **OK**.</span></span>
1. <span data-ttu-id="29da9-121">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="29da9-121">Select **New**.</span></span>
    * <span data-ttu-id="29da9-122">Nesse procedimento adicionaremos quatro linhas à BOM.</span><span class="sxs-lookup"><span data-stu-id="29da9-122">In this procedure we will add four lines to the BOM.</span></span> <span data-ttu-id="29da9-123">Duas linhas representam as opções de aumento e duas linhas representam as opções do gabinete.</span><span class="sxs-lookup"><span data-stu-id="29da9-123">Two lines represent cable options and two lines represent cabinet options.</span></span>  
1. <span data-ttu-id="29da9-124">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="29da9-124">In the list, mark the selected row.</span></span>
1. <span data-ttu-id="29da9-125">No campo **Número do item**, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="29da9-125">In the **Item number** field, enter or select a value.</span></span>
    * <span data-ttu-id="29da9-126">Selecionar número de item Cabos A0001, HDMI 6'.</span><span class="sxs-lookup"><span data-stu-id="29da9-126">Select item number A0001, HDMI 6' Cables.</span></span>  
1. <span data-ttu-id="29da9-127">No campo **Grupo de configuração**, informe ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="29da9-127">In the **Configuration group** field, enter or select a value.</span></span>
    * <span data-ttu-id="29da9-128">Selecione o grupo de configuração de cabo criado na guia 4 nesta sequência.</span><span class="sxs-lookup"><span data-stu-id="29da9-128">Select the cable configuration group created in guide 4 in this sequence.</span></span>  
1. <span data-ttu-id="29da9-129">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="29da9-129">Select **New**.</span></span>
    * <span data-ttu-id="29da9-130">Selecionar número de item Cabos A0002, HDMI 12'.</span><span class="sxs-lookup"><span data-stu-id="29da9-130">Select item number A0002, HDMI 12' Cables.</span></span>  
1. <span data-ttu-id="29da9-131">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="29da9-131">In the list, mark the selected row.</span></span>
1. <span data-ttu-id="29da9-132">No campo **Número do item**, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="29da9-132">In the **Item number** field, enter or select a value.</span></span>
1. <span data-ttu-id="29da9-133">No campo **Grupo de configuração**, informe ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="29da9-133">In the **Configuration group** field, enter or select a value.</span></span>
    * <span data-ttu-id="29da9-134">Selecione o grupo de configurações do cabo novamente.</span><span class="sxs-lookup"><span data-stu-id="29da9-134">Select the cable configuration group again.</span></span>  
1. <span data-ttu-id="29da9-135">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="29da9-135">Select **New**.</span></span>
1. <span data-ttu-id="29da9-136">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="29da9-136">In the list, mark the selected row.</span></span>
1. <span data-ttu-id="29da9-137">No campo **Número do item**, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="29da9-137">In the **Item number** field, enter or select a value.</span></span>
    * <span data-ttu-id="29da9-138">Selecionar número de item Gabinete D0002.</span><span class="sxs-lookup"><span data-stu-id="29da9-138">Select item number D0002 Cabinet.</span></span>  
1. <span data-ttu-id="29da9-139">No campo **Grupo de configuração**, informe ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="29da9-139">In the **Configuration group** field, enter or select a value.</span></span>
    * <span data-ttu-id="29da9-140">Selecione o grupo de configuração do gabinete para esta linha da BOM.</span><span class="sxs-lookup"><span data-stu-id="29da9-140">Select the cabinet configuration group for this BOM line.</span></span>  
1. <span data-ttu-id="29da9-141">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="29da9-141">Select **New**.</span></span>
1. <span data-ttu-id="29da9-142">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="29da9-142">In the list, mark the selected row.</span></span>
1. <span data-ttu-id="29da9-143">No campo **Número do item**, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="29da9-143">In the **Item number** field, enter or select a value.</span></span>
    * <span data-ttu-id="29da9-144">Selecione o número do item M0007 StandardCabinet como a linha BOM da última vez.</span><span class="sxs-lookup"><span data-stu-id="29da9-144">Select Item number M0007 StandardCabinet as the last BOM line.</span></span>  
1. <span data-ttu-id="29da9-145">No campo **Grupo de configuração**, informe ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="29da9-145">In the **Configuration group** field, enter or select a value.</span></span>
    * <span data-ttu-id="29da9-146">Selecione o grupo de configuração do gabinete para a última linha da BOM.</span><span class="sxs-lookup"><span data-stu-id="29da9-146">Select the Cabinet configuration group for the last BOM line.</span></span>  

## <a name="approve-and-activate"></a><span data-ttu-id="29da9-147">Aprovar e ativar</span><span class="sxs-lookup"><span data-stu-id="29da9-147">Approve and activate</span></span>

1. <span data-ttu-id="29da9-148">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="29da9-148">Close the page.</span></span>
1. <span data-ttu-id="29da9-149">Selecione **Aprovar**.</span><span class="sxs-lookup"><span data-stu-id="29da9-149">Select **Approve**.</span></span>
1. <span data-ttu-id="29da9-150">No campo **Aprovado por** insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="29da9-150">In the **Approved by** field, enter or select a value.</span></span>
1. <span data-ttu-id="29da9-151">Selecione *Sim* no campo **Também deseja aprovar a lista de materiais?**.</span><span class="sxs-lookup"><span data-stu-id="29da9-151">Select *Yes* in the **Do you also want to approve the bill of materials?** field.</span></span>
1. <span data-ttu-id="29da9-152">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="29da9-152">Select **OK**.</span></span>
1. <span data-ttu-id="29da9-153">Selecione **Ativar**.</span><span class="sxs-lookup"><span data-stu-id="29da9-153">Select **Activate**.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]