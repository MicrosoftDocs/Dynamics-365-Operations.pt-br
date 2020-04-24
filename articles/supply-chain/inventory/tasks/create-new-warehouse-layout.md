---
title: Criar um novo layout de depósito
description: Este tópico descreve como configurar informações sobre as localizações em um depósito.
author: perlynne
manager: tfehr
ms.date: 07/29/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventParameters, DefaultDashboard, InventLocation, WMSLocationWizard
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 09666e95cc90913f1bf8555b9ff2c48aa55369ed
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3214012"
---
# <a name="create-a-new-warehouse-layout"></a><span data-ttu-id="9eee2-103">Criar um novo layout de depósito</span><span class="sxs-lookup"><span data-stu-id="9eee2-103">Create a new warehouse layout</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="9eee2-104">Este tópico descreve como configurar informações sobre as localizações em um depósito.</span><span class="sxs-lookup"><span data-stu-id="9eee2-104">This topic describes how to set up information about the locations in a warehouse.</span></span> <span data-ttu-id="9eee2-105">Aplica-se apenas a depósitos criados usando o "armazenamento básico” no módulo de gerenciamento de estoque, não a depósitos criados no módulo de gerenciamento de depósito.</span><span class="sxs-lookup"><span data-stu-id="9eee2-105">This applies only to warehouses created using "basic warehousing" in the Inventory management module, not to warehouses created in the Warehouse management module.</span></span> <span data-ttu-id="9eee2-106">Você pode usar esse procedimento na empresa USMF de dados demo, ou usando seus próprios dados.</span><span class="sxs-lookup"><span data-stu-id="9eee2-106">You can use this procedure in demo data company USMF, or on your own data.</span></span>


## <a name="set-the-default-location-capacity"></a><span data-ttu-id="9eee2-107">Definir a capacidade do local padrão</span><span class="sxs-lookup"><span data-stu-id="9eee2-107">Set the default location capacity</span></span>
1. <span data-ttu-id="9eee2-108">No Painel de Navegação, vá para **Painel de navegação > Módulos > Gerenciamento de estoque > Configuração > Parâmetros de gerenciamento de depósito e estoque**.</span><span class="sxs-lookup"><span data-stu-id="9eee2-108">In the navigation pane, go to **Modules > Inventory management > Setup > Inventory and warehouse management parameters**.</span></span>
2. <span data-ttu-id="9eee2-109">Selecione a guia **Localizações**.</span><span class="sxs-lookup"><span data-stu-id="9eee2-109">Select the **Locations** tab.</span></span>
3. <span data-ttu-id="9eee2-110">No campo **Largura padrão**, digite um número.</span><span class="sxs-lookup"><span data-stu-id="9eee2-110">In the **Standard width** field, enter a number.</span></span>
4. <span data-ttu-id="9eee2-111">No campo **Profundidade padrão**, insira um número.</span><span class="sxs-lookup"><span data-stu-id="9eee2-111">In the **Standard depth** field, enter a number.</span></span>
5. <span data-ttu-id="9eee2-112">No campo **Altura padrão**, insira um número.</span><span class="sxs-lookup"><span data-stu-id="9eee2-112">In the **Standard height** field, enter a number.</span></span>
6. <span data-ttu-id="9eee2-113">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="9eee2-113">Select **Save**.</span></span>
7. <span data-ttu-id="9eee2-114">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="9eee2-114">Close the page.</span></span>

## <a name="define-the-location-name-format"></a><span data-ttu-id="9eee2-115">Definir o formato do nome da localização</span><span class="sxs-lookup"><span data-stu-id="9eee2-115">Define the location name format</span></span>
1. <span data-ttu-id="9eee2-116">No Painel de Navegação, vá para **Módulos > Gerenciamento de estoque > Configuração > Divisão de estoque > Depósitos**.</span><span class="sxs-lookup"><span data-stu-id="9eee2-116">In the navigation pane, go to **Modules > Inventory management > Setup > Inventory breakdown > Warehouses**.</span></span>
2. <span data-ttu-id="9eee2-117">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="9eee2-117">Select **New**.</span></span>
3. <span data-ttu-id="9eee2-118">No campo **Depósito**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="9eee2-118">In the **Warehouse** field, type a value.</span></span>
4. <span data-ttu-id="9eee2-119">No campo **Nome**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="9eee2-119">In the **Name** field, type a value.</span></span>
5. <span data-ttu-id="9eee2-120">No campo **Site**, selecione o registro desejado na pesquisa.</span><span class="sxs-lookup"><span data-stu-id="9eee2-120">In the **Site** field, select the desired record in the lookup.</span></span>
6. <span data-ttu-id="9eee2-121">Alternar a expansão da seção **Nomes de local**.</span><span class="sxs-lookup"><span data-stu-id="9eee2-121">Toggle the expansion of the **Location names** section.</span></span> <span data-ttu-id="9eee2-122">As opções nesta seção definem o formato padrão para nomes da localização.</span><span class="sxs-lookup"><span data-stu-id="9eee2-122">The options in this section define the default format for location names.</span></span> <span data-ttu-id="9eee2-123">Em nosso exemplo, incluiremos o número do corredor, o número do rack e o número da prateleira.</span><span class="sxs-lookup"><span data-stu-id="9eee2-123">In our example, we'll include the aisle number, rack number and shelf number.</span></span>  
7. <span data-ttu-id="9eee2-124">Defina a opção **Incluir corredor** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="9eee2-124">Set the **Include aisle** option to **Yes**.</span></span>
8. <span data-ttu-id="9eee2-125">Defina a opção **Incluir rack** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="9eee2-125">Set the **Include rack** option to **Yes**.</span></span> 
9. <span data-ttu-id="9eee2-126">No campo **Formato**, digite o valor para o rack.</span><span class="sxs-lookup"><span data-stu-id="9eee2-126">In the **Format** field, for the rack, type a value.</span></span>
10. <span data-ttu-id="9eee2-127">Defina a opção **Incluir prateleira** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="9eee2-127">Set the **Include shelf** option to **Yes**.</span></span>
11. <span data-ttu-id="9eee2-128">No campo **Formato**, digite o valor para a prateleira.</span><span class="sxs-lookup"><span data-stu-id="9eee2-128">In the **Format** field, for the shelf, type a value.</span></span>

## <a name="define-warehouse-locations"></a><span data-ttu-id="9eee2-129">Definir locais de depósito</span><span class="sxs-lookup"><span data-stu-id="9eee2-129">Define warehouse locations</span></span>
1. <span data-ttu-id="9eee2-130">No Painel de Ações, selecione **Depósito**.</span><span class="sxs-lookup"><span data-stu-id="9eee2-130">On the Action Pane, select **Warehouse**.</span></span>
2. <span data-ttu-id="9eee2-131">Selecione **Assistente de Localização**.</span><span class="sxs-lookup"><span data-stu-id="9eee2-131">Select **Location Wizard**.</span></span>
3. <span data-ttu-id="9eee2-132">Selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="9eee2-132">Select **Next**.</span></span>
4. <span data-ttu-id="9eee2-133">Desmarque a opção **Docas de saída**</span><span class="sxs-lookup"><span data-stu-id="9eee2-133">De-select the **Outbound docks** option</span></span>
5. <span data-ttu-id="9eee2-134">Desmarque a opção **Locais de massa**</span><span class="sxs-lookup"><span data-stu-id="9eee2-134">De-select the **Bulk locations** option</span></span>
6. <span data-ttu-id="9eee2-135">Selecione **Avançar** até chegar à opção de selecionar **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="9eee2-135">Select **Next** until you come to the option to select **Finish**.</span></span>
7. <span data-ttu-id="9eee2-136">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="9eee2-136">Close the page.</span></span>
8. <span data-ttu-id="9eee2-137">Atualize a página.</span><span class="sxs-lookup"><span data-stu-id="9eee2-137">Refresh the page.</span></span>

