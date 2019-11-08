---
title: Criar relatórios de consumo
description: Este tópico explica como criar relatórios de consumo no Gerenciamento de Ativos.
author: josaw1
manager: AnnBe
ms.date: 08/21/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: eecfb101af9a91f515aab221181c54d53e358a68
ms.sourcegitcommit: fb66731f05207094149a6bc7b8549a4dabbb071a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/22/2019
ms.locfileid: "2652416"
---
# <a name="create-consumption-reports"></a><span data-ttu-id="8c680-103">Criar relatórios de consumo</span><span class="sxs-lookup"><span data-stu-id="8c680-103">Create consumption reports</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="8c680-104">Quando você cria e publica registros de consumo em ordens de serviço no Gerenciamento de Ativos, dois relatórios estão disponíveis para exibir detalhes do consumo.</span><span class="sxs-lookup"><span data-stu-id="8c680-104">When you've created and posted consumption registrations on work orders in Asset Management, two reports are available to display consumption details.</span></span>


## <a name="asset-consumption-report"></a><span data-ttu-id="8c680-105">Relatório de consumo de ativos</span><span class="sxs-lookup"><span data-stu-id="8c680-105">Asset consumption report</span></span>

<span data-ttu-id="8c680-106">Após o cancelamento do consumo nas ordens de serviço, é possível imprimir um relatório de consumo de ativos.</span><span class="sxs-lookup"><span data-stu-id="8c680-106">When you have posted consumption on work orders, you can print an asset consumption report.</span></span> <span data-ttu-id="8c680-107">O relatório exibe horas, custos de horas, custos de itens e despesas lançados em ativos.</span><span class="sxs-lookup"><span data-stu-id="8c680-107">The report displays hours, hour costs, item costs, and expenses posted on assets.</span></span>

1. <span data-ttu-id="8c680-108">Clique em **Gerenciamento de ativos** > **Relatórios** > **Ativos** > **Consumo de ativos**.</span><span class="sxs-lookup"><span data-stu-id="8c680-108">Click **Asset management** > **Reports** > **Assets** > **Asset consumption**.</span></span>

2. <span data-ttu-id="8c680-109">Na caixa de diálogo **Consumo de ativos**, selecione os parâmetros e o nível de detalhe que deseja ver selecionando **Sim** nos botões de alternância relevantes e inserindo um nível de localização funcional na seção **Mostrar**.</span><span class="sxs-lookup"><span data-stu-id="8c680-109">In the **Asset consumption** dialog, select the parameters and detail level you want to see by selecting **Yes** on the relevant toggle buttons, and inserting a functional location level in the **Show** section.</span></span>
    - <span data-ttu-id="8c680-110">Você pode usar o campo **Níveis** para indicar o nível de detalhamento desejado das linhas de ativo em relação aos locais funcionais.</span><span class="sxs-lookup"><span data-stu-id="8c680-110">You can use the **Levels** field to indicate how detailed you want the asset lines to be regarding functional locations.</span></span> 
    
        <span data-ttu-id="8c680-111">Por exemplo, se você inserir o número "1" no campo e tiver uma estrutura de localização funcional em vários níveis, todos os ativos de um local funcional serão mostrados no nível superior e, portanto, uma linha poderá ser adicionadas em locais funcionais localizados em um nível inferior.</span><span class="sxs-lookup"><span data-stu-id="8c680-111">For example, if you enter the number "1" in the field, and you have a multi-level functional location structure, all assets for a functional location will be shown on the top level, and therefore a line may be added up from functional locations located at a lower level.</span></span> 
        
        <span data-ttu-id="8c680-112">Se você inserir o número "0" no campo **Níveis**, verá um resultado detalhado mostrando todos os ativos em todos os níveis do local funcional ao qual elas estão relacionadas.</span><span class="sxs-lookup"><span data-stu-id="8c680-112">If you enter the number "0" in the **Levels** field, you will see a detailed result showing all assets on all the functional location levels to which they are related.</span></span> 
        
    - <span data-ttu-id="8c680-113">Selecione **Sim** no botão **Soma em todos os subativos** para alternar entre as somas de cada subativo no relatório.</span><span class="sxs-lookup"><span data-stu-id="8c680-113">Select **Yes** on the **Sum on all sub assets** toggle button to see sums for each sub asset in the report.</span></span>

3. <span data-ttu-id="8c680-114">Selecione um intervalo de datas na seção **Datas**.</span><span class="sxs-lookup"><span data-stu-id="8c680-114">Select a date interval in the **Dates** section.</span></span>

4. <span data-ttu-id="8c680-115">Na Guia Rápida **Destination**, selecione se deseja exibir o relatório na tela, imprimi-lo ou salvá-lo como um arquivo ou email.</span><span class="sxs-lookup"><span data-stu-id="8c680-115">On the **Destination** FastTab, select if you want to display the report on screen, print it, or save it as a file or email.</span></span>

5. <span data-ttu-id="8c680-116">Se necessário, você pode selecionar ativos específicos a serem exibidos no relatório.</span><span class="sxs-lookup"><span data-stu-id="8c680-116">If required, you can select specific assets to be displayed in the report.</span></span> <span data-ttu-id="8c680-117">Na Guia Rápida **Registros a serem incluídos**, clique em **Filtrar** e adicione os ativos que você deseja incluir no relatório.</span><span class="sxs-lookup"><span data-stu-id="8c680-117">On the **Records to include** FastTab, click **Filter**, and add the assets you want to include in the report.</span></span>

6. <span data-ttu-id="8c680-118">Clique em **OK** para gerar o relatório.</span><span class="sxs-lookup"><span data-stu-id="8c680-118">Click **OK** to generate the report.</span></span>


## <a name="work-order-consumption-report"></a><span data-ttu-id="8c680-119">Relatório de consumo de ordem de serviço</span><span class="sxs-lookup"><span data-stu-id="8c680-119">Work order consumption report</span></span>

<span data-ttu-id="8c680-120">Após o cancelamento do consumo nas ordens de serviço, é possível imprimir um relatório de consumo de ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="8c680-120">When you have posted consumption on work orders, you can print a work order consumption report.</span></span> <span data-ttu-id="8c680-121">O relatório exibe horas, custos de horas, custos de itens e despesas lançados em ordens de serviço.</span><span class="sxs-lookup"><span data-stu-id="8c680-121">The report displays hours, hour costs, item costs, and expenses posted on work orders.</span></span>

1. <span data-ttu-id="8c680-122">Clique em **Gerenciamento de ativos** > **Relatórios** > **Ordens de trabalho** > **Consumo de ordem de serviço**.</span><span class="sxs-lookup"><span data-stu-id="8c680-122">Click **Asset management** > **Reports** > **Work orders** > **Work order consumption**.</span></span>

2. <span data-ttu-id="8c680-123">Na caixa de diálogo **Consumo de ordem de serviço**, selecione os parâmetros que deseja incluir no relatório, selecionando **Sim** nos botões de alternância relevantes na seção **Mostrar**.</span><span class="sxs-lookup"><span data-stu-id="8c680-123">In the **Work order consumption** dialog, select the parameters you want to include in the report by selecting **Yes** on the relevant toggle buttons in the **Show** section.</span></span>

3. <span data-ttu-id="8c680-124">Selecione um intervalo de datas na seção **Datas**.</span><span class="sxs-lookup"><span data-stu-id="8c680-124">Select a date interval in the **Dates** section.</span></span>

4. <span data-ttu-id="8c680-125">Na Guia Rápida **Destination**, selecione se deseja exibir o relatório na tela, imprimi-lo ou salvá-lo como um arquivo ou email.</span><span class="sxs-lookup"><span data-stu-id="8c680-125">On the **Destination** FastTab, select if you want to display the report on screen, print it, or save it as a file or email.</span></span>

5. <span data-ttu-id="8c680-126">Se necessário, você pode selecionar ordens de serviço específicas a serem exibidas no relatório.</span><span class="sxs-lookup"><span data-stu-id="8c680-126">If required, you can select specific work orders to be displayed in the report.</span></span> <span data-ttu-id="8c680-127">Na Guia Rápida **Registros a serem incluídos**, clique em **Filtrar** e adicione as ordens de serviço que você deseja incluir no relatório.</span><span class="sxs-lookup"><span data-stu-id="8c680-127">On the **Records to include** FastTab, click **Filter**, and add the work orders you want to include in the report.</span></span>

6. <span data-ttu-id="8c680-128">Clique em **OK** para gerar o relatório.</span><span class="sxs-lookup"><span data-stu-id="8c680-128">Click **OK** to generate the report.</span></span>


>[!NOTE]
><span data-ttu-id="8c680-129">Você também pode gerar um [relatório de ordem de serviço](../work-orders/work-order-report.md), que contém mais detalhes sobre a ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="8c680-129">You can also generate a [work order report](../work-orders/work-order-report.md), which contains more work order details.</span></span>

