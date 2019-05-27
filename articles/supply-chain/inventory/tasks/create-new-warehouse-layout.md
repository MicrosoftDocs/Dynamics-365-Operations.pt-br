---
title: Criar um novo layout de depósito
description: Este procedimento mostra como configurar informações sobre as localizações de um depósito.
author: perlynne
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventParameters, DefaultDashboard, InventLocation, WMSLocationWizard
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 26314f9015feded41f105814b85069fff0c62964
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1572756"
---
# <a name="create-a-new-warehouse-layout"></a><span data-ttu-id="a39b8-103">Criar um novo layout de depósito</span><span class="sxs-lookup"><span data-stu-id="a39b8-103">Create a new warehouse layout</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="a39b8-104">Este procedimento mostra como configurar informações sobre as localizações de um depósito.</span><span class="sxs-lookup"><span data-stu-id="a39b8-104">This procedure shows you how to set up information about the locations in a warehouse.</span></span> <span data-ttu-id="a39b8-105">Aplica-se apenas a depósitos criados usando o "armazenamento básico” no módulo de gerenciamento de estoque, não a depósitos criados no módulo de gerenciamento de depósito.</span><span class="sxs-lookup"><span data-stu-id="a39b8-105">This applies only to warehouses created using "basic warehousing" in the Inventory management module, not to warehouses created in the Warehouse management module.</span></span> <span data-ttu-id="a39b8-106">Você pode usar esse procedimento na empresa USMF de dados demo, ou usando seus próprios dados.</span><span class="sxs-lookup"><span data-stu-id="a39b8-106">You can use this procedure in demo data company USMF, or on your own data.</span></span>


## <a name="set-the-default-location-capacity"></a><span data-ttu-id="a39b8-107">Definir a capacidade do local padrão</span><span class="sxs-lookup"><span data-stu-id="a39b8-107">Set the default location capacity</span></span>
1. <span data-ttu-id="a39b8-108">Vá para Gerenciamento de estoque > Configuração > Parâmetros de gerenciamento de depósito e estoque.</span><span class="sxs-lookup"><span data-stu-id="a39b8-108">Go to Inventory management > Setup > Inventory and warehouse management parameters.</span></span>
2. <span data-ttu-id="a39b8-109">Clique na guia Locais.</span><span class="sxs-lookup"><span data-stu-id="a39b8-109">Click the Locations tab.</span></span>
3. <span data-ttu-id="a39b8-110">No campo de largura padrão, insira um número.</span><span class="sxs-lookup"><span data-stu-id="a39b8-110">In the Standard width field, enter a number.</span></span>
4. <span data-ttu-id="a39b8-111">No campo de profundidade padrão, insira um número.</span><span class="sxs-lookup"><span data-stu-id="a39b8-111">In the Standard depth field, enter a number.</span></span>
5. <span data-ttu-id="a39b8-112">No campo de altura padrão, insira um número.</span><span class="sxs-lookup"><span data-stu-id="a39b8-112">In the Standard height field, enter a number.</span></span>
6. <span data-ttu-id="a39b8-113">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="a39b8-113">Click Save.</span></span>
7. <span data-ttu-id="a39b8-114">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="a39b8-114">Close the page.</span></span>

## <a name="define-the-location-name-format"></a><span data-ttu-id="a39b8-115">Definir o formato do nome da localização</span><span class="sxs-lookup"><span data-stu-id="a39b8-115">Define the location name format</span></span>
1. <span data-ttu-id="a39b8-116">Vá para Gerenciamento do estoque > Configuração > Divisão do estoque > Depósitos.</span><span class="sxs-lookup"><span data-stu-id="a39b8-116">Go to Inventory management > Setup > Inventory breakdown > Warehouses.</span></span>
2. <span data-ttu-id="a39b8-117">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="a39b8-117">Click New.</span></span>
3. <span data-ttu-id="a39b8-118">No campo Depósito, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="a39b8-118">In the Warehouse field, type a value.</span></span>
4. <span data-ttu-id="a39b8-119">No campo Nome, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="a39b8-119">In the Name field, type a value.</span></span>
5. <span data-ttu-id="a39b8-120">No campo Local, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="a39b8-120">In the Site field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="a39b8-121">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="a39b8-121">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="a39b8-122">Alternar a expansão da seção Nomes de local.</span><span class="sxs-lookup"><span data-stu-id="a39b8-122">Toggle the expansion of the Location names section.</span></span>
    * <span data-ttu-id="a39b8-123">As opções nesta seção definem o formato padrão para nomes da localização.</span><span class="sxs-lookup"><span data-stu-id="a39b8-123">The options in this section define the default format for location names.</span></span> <span data-ttu-id="a39b8-124">Em nosso exemplo, incluiremos o número do corredor, o número do rack e o número da prateleira.</span><span class="sxs-lookup"><span data-stu-id="a39b8-124">In our example, we'll include the aisle number, rack number and shelf number.</span></span>  
8. <span data-ttu-id="a39b8-125">Definir a opção do corredor para Sim.</span><span class="sxs-lookup"><span data-stu-id="a39b8-125">Set the Include aisle option to Yes.</span></span>
9. <span data-ttu-id="a39b8-126">Definir a opção do rack para Sim.</span><span class="sxs-lookup"><span data-stu-id="a39b8-126">Set the Include rack option to Yes.</span></span> 
10. <span data-ttu-id="a39b8-127">No campo Formato, digite o valor para o rack.</span><span class="sxs-lookup"><span data-stu-id="a39b8-127">In the Format field, for the rack, type a value.</span></span>
    * <span data-ttu-id="a39b8-128">Por exemplo: -##</span><span class="sxs-lookup"><span data-stu-id="a39b8-128">For example: -##</span></span>  
11. <span data-ttu-id="a39b8-129">Definir a opção Incluir prateleira como Sim.</span><span class="sxs-lookup"><span data-stu-id="a39b8-129">Set the Include shelf option to Yes.</span></span>
12. <span data-ttu-id="a39b8-130">No campo Formato, digite o valor para a prateleira.</span><span class="sxs-lookup"><span data-stu-id="a39b8-130">In the Format field, for the shelf, type a value.</span></span>
    * <span data-ttu-id="a39b8-131">Por exemplo: -##</span><span class="sxs-lookup"><span data-stu-id="a39b8-131">For example: -##</span></span>  

## <a name="define-warehouse-locations"></a><span data-ttu-id="a39b8-132">Definir locais de depósito</span><span class="sxs-lookup"><span data-stu-id="a39b8-132">Define warehouse locations</span></span>
1. <span data-ttu-id="a39b8-133">No Painel de Ação, clique em Depósito.</span><span class="sxs-lookup"><span data-stu-id="a39b8-133">On the Action Pane, click Warehouse.</span></span>
2. <span data-ttu-id="a39b8-134">Clique em Assistente de localização.</span><span class="sxs-lookup"><span data-stu-id="a39b8-134">Click Location Wizard.</span></span>
3. <span data-ttu-id="a39b8-135">Clique em Avançar.</span><span class="sxs-lookup"><span data-stu-id="a39b8-135">Click Next.</span></span>
4. <span data-ttu-id="a39b8-136">Desmarque a opção de Docas de saída</span><span class="sxs-lookup"><span data-stu-id="a39b8-136">De-select the Outbound docks option</span></span>
5. <span data-ttu-id="a39b8-137">Desmarque a opção de Locais de massa</span><span class="sxs-lookup"><span data-stu-id="a39b8-137">De-select the Bulk locations option</span></span>
6. <span data-ttu-id="a39b8-138">Clique em Avançar.</span><span class="sxs-lookup"><span data-stu-id="a39b8-138">Click Next.</span></span>
7. <span data-ttu-id="a39b8-139">Clique em Avançar.</span><span class="sxs-lookup"><span data-stu-id="a39b8-139">Click Next.</span></span>
8. <span data-ttu-id="a39b8-140">Clique em Avançar.</span><span class="sxs-lookup"><span data-stu-id="a39b8-140">Click Next.</span></span>
9. <span data-ttu-id="a39b8-141">Clique em Avançar.</span><span class="sxs-lookup"><span data-stu-id="a39b8-141">Click Next.</span></span>
10. <span data-ttu-id="a39b8-142">Clique em Avançar.</span><span class="sxs-lookup"><span data-stu-id="a39b8-142">Click Next.</span></span>
11. <span data-ttu-id="a39b8-143">Clique em Avançar.</span><span class="sxs-lookup"><span data-stu-id="a39b8-143">Click Next.</span></span>
12. <span data-ttu-id="a39b8-144">Clique em Avançar.</span><span class="sxs-lookup"><span data-stu-id="a39b8-144">Click Next.</span></span>
    * <span data-ttu-id="a39b8-145">Observe que as dimensões físicas mostradas nessa página são aquelas configuradas que você definiu no início deste procedimento.</span><span class="sxs-lookup"><span data-stu-id="a39b8-145">Note that the physical dimensions shown on this page are the ones that you set at the start of this procedure.</span></span>  
13. <span data-ttu-id="a39b8-146">Clique em Avançar.</span><span class="sxs-lookup"><span data-stu-id="a39b8-146">Click Next.</span></span>
14. <span data-ttu-id="a39b8-147">Clique em Finish (Concluir).</span><span class="sxs-lookup"><span data-stu-id="a39b8-147">Click Finish.</span></span>
15. <span data-ttu-id="a39b8-148">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="a39b8-148">Close the page.</span></span>
16. <span data-ttu-id="a39b8-149">Atualize a página.</span><span class="sxs-lookup"><span data-stu-id="a39b8-149">Refresh the page.</span></span>

