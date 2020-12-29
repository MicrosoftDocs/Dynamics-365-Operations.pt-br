---
title: Controle de custo e data
description: Este tópico explica o controle de custo e data no Gerenciamento de Ativos.
author: josaw1
manager: tfehr
ms.date: 08/23/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetBICostControlWorkspace, EntAssetWorkOrderDateControl, EntAssetWorkOrderForecastCostInfoPart, EntAssetMaintenanceCostTrans, EntAssetWorkOrderDateControlCalcDialog, EntAssetCostControl, EntAssetCostObjectCalendar, EntAssetWorkOrderCostInfoPart
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 18373ff16b63ea61a3a4bc38ee7fa0b5e33154b5
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4422081"
---
# <a name="cost-and-date-control"></a><span data-ttu-id="16d21-103">Controle de custo e data</span><span class="sxs-lookup"><span data-stu-id="16d21-103">Cost and date control</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="16d21-104">No Gerenciamento de ativos, é possível calcular os custos para obter uma visão geral dos custos reais em comparação com os custos de orçamento em ativos, locais funcionais e ordens de serviço.</span><span class="sxs-lookup"><span data-stu-id="16d21-104">In Asset Management, you can calculate costs to get an overview of actual costs compared to budget costs on assets, functional locations, and work orders.</span></span> <span data-ttu-id="16d21-105">Os custos reais são baseados em transações lançadas.</span><span class="sxs-lookup"><span data-stu-id="16d21-105">Actual costs are based on posted transactions.</span></span> 

<span data-ttu-id="16d21-106">Você também pode fazer um cálculo de data para comparar datas inicial e final agendadas com datas de início e término reais em ordens de serviço.</span><span class="sxs-lookup"><span data-stu-id="16d21-106">You can also make a date calculation if you want to compare scheduled start and end dates to actual start and end dates on work orders.</span></span>

## <a name="cost-control-for-assets-functional-locations-and-work-orders"></a><span data-ttu-id="16d21-107">Controle de custos para ativos, locais funcionais e ordens de serviço</span><span class="sxs-lookup"><span data-stu-id="16d21-107">Cost control for assets, functional locations, and work orders</span></span>

<span data-ttu-id="16d21-108">Os cálculos efetuados para ativos, locais funcionais e ordens de trabalho são quase idênticos.</span><span class="sxs-lookup"><span data-stu-id="16d21-108">The calculations made for assets, functional locations, and work orders are almost identical.</span></span> <span data-ttu-id="16d21-109">A única diferença é que para ativos e locais funcionais, você também podem incluir subativos e sub-locais em seu cálculo.</span><span class="sxs-lookup"><span data-stu-id="16d21-109">The only difference is that for assets and functional locations, you can also include sub assets and sub locations in your calculation.</span></span> <span data-ttu-id="16d21-110">A data é a data da transação quando o registro foi feito.</span><span class="sxs-lookup"><span data-stu-id="16d21-110">The date is the transaction date when the registration was recorded.</span></span>

1. <span data-ttu-id="16d21-111">Clique em **Gerenciamento de ativos** > **Consultas** > **Ativos** > **Controle de custos de ativos** ou **Controle de custos do local funcional**, ou **Gerenciamento de ativos** > **Consultas** > **Ordens de serviço** > **Controle de custos da ordem de serviço**.</span><span class="sxs-lookup"><span data-stu-id="16d21-111">Click **Asset management** > **Inquiries** > **Assets** > **Asset cost control** or **Functional location cost control**, or **Asset management** > **Inquiries** > **Work orders** > **Work order cost control**.</span></span>

2. <span data-ttu-id="16d21-112">Na caixa de diálogo **Controle de custos de ativos** / **Controle de custos do local funcional** / **Controle de custos da ordem de serviço**, selecione um intervalo de tempo a ser calculado.</span><span class="sxs-lookup"><span data-stu-id="16d21-112">In the **Asset cost control** / **Functional location cost control** / **Work order cost control** dialog, select a time range to be calculated.</span></span>

3. <span data-ttu-id="16d21-113">Se necessário, selecione um conjunto de dimensões financeiras para ser incluído no cálculo.</span><span class="sxs-lookup"><span data-stu-id="16d21-113">If required, select a financial dimension set to be included in the calculation.</span></span>

4. <span data-ttu-id="16d21-114">Selecione "Sim" no botão de alternância **Ignorar zero** se não desejar exibir resultados com custo zero.</span><span class="sxs-lookup"><span data-stu-id="16d21-114">Select "Yes" on the **Skip zero** toggle button if you don't want to show results with a cost of zero.</span></span>

5. <span data-ttu-id="16d21-115">Você pode usar o campo **Nível** para indicar o nível de detalhamento desejado das linhas de controle de custo em relação aos locais funcionais.</span><span class="sxs-lookup"><span data-stu-id="16d21-115">You can use the **Level** field to indicate how detailed you want the cost control lines to be regarding functional locations.</span></span> 

    <span data-ttu-id="16d21-116">Por exemplo, se você inserir o número "1" no campo e tiver uma hierarquia de localização funcional em vários níveis, todas as linhas de controles de custos para um local funcional serão mostradas no nível superior e, portanto, as horas em uma linha poderão ser adicionadas em locais funcionais localizados em um nível inferior.</span><span class="sxs-lookup"><span data-stu-id="16d21-116">For example, if you insert the number "1" in the field, and you have a multi-level functional location hierarchy, all cost control lines for a functional location will be shown on the top level, and therefore the hours on a line may be added up from functional locations located at a lower level.</span></span> 
    
    <span data-ttu-id="16d21-117">Se você inserir o número "0" no campo **Nível**, verá um resultado detalhado mostrando todas as linhas de controle de custos em todo o nível do local funcional ao qual elas estão relacionadas.</span><span class="sxs-lookup"><span data-stu-id="16d21-117">If you insert the number "0" in the **Level** field, you will see a detailed result showing all cost control lines on all the functional location level to which they are related.</span></span>

6. <span data-ttu-id="16d21-118">Selecione "Sim" no botão de alternância **Mostrar custo comprometido aberto** se quiser incluir essa coluna no cálculo.</span><span class="sxs-lookup"><span data-stu-id="16d21-118">Select "Yes" on the **Show open committed cost** toggle button if you want to include that column in the calculation.</span></span>

7. <span data-ttu-id="16d21-119">Selecione "Sim" no botão de alternância **incluir subativos** para exibir custos relacionados a subativos como linhas separadas.</span><span class="sxs-lookup"><span data-stu-id="16d21-119">Select "Yes" on the **Include sub assets** toggle button to show costs related to sub assets as separate lines.</span></span>

8. <span data-ttu-id="16d21-120">Para limitar a pesquisa, você poderá selecionar ativos específicos/locais funcionais/ordens de trabalho na Guia Rápida **Registros a serem incluídos**.</span><span class="sxs-lookup"><span data-stu-id="16d21-120">If you want to limit the search, you can select specific assets / functional locations / work orders on the **Records to include** FastTab.</span></span>

9. <span data-ttu-id="16d21-121">Clique em **OK** para iniciar o cálculo.</span><span class="sxs-lookup"><span data-stu-id="16d21-121">Click **OK** to start the calculation.</span></span>

    <span data-ttu-id="16d21-122">A figura abaixo mostra um exemplo da caixa de diálogo **Controle de custos de ativos**.</span><span class="sxs-lookup"><span data-stu-id="16d21-122">The figure below shows an example of the **Asset cost control** dialog.</span></span>

    ![Caixa de diálogo Controle de custos de ativos](media/01-controlling-and-reporting.png)

10. <span data-ttu-id="16d21-124">Na página **Controle de custos de ativos**, clique nos botões **Agrupar por** para mostrar o nível de detalhe necessário do cálculo.</span><span class="sxs-lookup"><span data-stu-id="16d21-124">On the **Asset cost control** page, click the **Group by** buttons to show the required detail level of the calculation.</span></span> <span data-ttu-id="16d21-125">Os botões selecionados de **Agrupar por** são realçados.</span><span class="sxs-lookup"><span data-stu-id="16d21-125">The selected **Group by** buttons are highlighted.</span></span> <span data-ttu-id="16d21-126">Clique em um botão para ativá-los ou desativá-los.</span><span class="sxs-lookup"><span data-stu-id="16d21-126">Click on a button to activate or deactivate it.</span></span>

## <a name="example"></a><span data-ttu-id="16d21-127">Exemplo</span><span class="sxs-lookup"><span data-stu-id="16d21-127">Example</span></span>

<span data-ttu-id="16d21-128">A captura de tela abaixo mostra um exemplo de resultados de cálculo em **Controle de custos de ativos**.</span><span class="sxs-lookup"><span data-stu-id="16d21-128">The screenshot below shows an example of calculation results in **Asset cost control**.</span></span>

- <span data-ttu-id="16d21-129">O campo **Orçamento original** mostra os custos do orçamento da previsão da ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="16d21-129">The **Original budget** field shows budget costs from the work order forecast.</span></span> 
- <span data-ttu-id="16d21-130">O campo **Custo comprometido** mostra o valor total das despesas que uma entidade legal se comprometeu a pagar.</span><span class="sxs-lookup"><span data-stu-id="16d21-130">The **Committed cost** field shows the total amount of expenses that a legal entity has committed itself to pay.</span></span> 
- <span data-ttu-id="16d21-131">O campo **Custo comprometido aberto** mostra compromissos de pagamento por itens, horários e serviços que você solicitou ou recebeu, mas ainda não pagou.</span><span class="sxs-lookup"><span data-stu-id="16d21-131">The **Open committed cost** field shows commitments to pay for items, hours, and services you have ordered or received but not yet paid for.</span></span> 
- <span data-ttu-id="16d21-132">O **Custo real** mostra os custos relacionados após o lançamento de todos os registros de consumo.</span><span class="sxs-lookup"><span data-stu-id="16d21-132">The **Actual cost** field shows related costs after all consumption registrations have been posted.</span></span>

![Resultados do cálculo de exemplo em Controle de custos de ativos](media/02-controlling-and-reporting.png)

<span data-ttu-id="16d21-134">Outra maneira de fazer um cálculo de custo é selecionar vários ativos em **Todos os ativos** ou **Ativos ativos**.</span><span class="sxs-lookup"><span data-stu-id="16d21-134">Another way of making a cost calculation is to multi-select assets in **All assets** or **Active assets**.</span></span> <span data-ttu-id="16d21-135">Depois, você clica no botão **Controle de custo** na guia **Geral**. Na caixa de diálogo **Controle de custos de ativos**, os ativos selecionados são inseridos automaticamente no campo **Ativo** na Guia Rápida **Registros a serem incluídos**.</span><span class="sxs-lookup"><span data-stu-id="16d21-135">Then, you click the **Cost control** button on the **General** tab. In the **Asset cost control** dialog, the selected assets are automatically inserted in the **Asset** field on the **Records to include** FastTab.</span></span> <span data-ttu-id="16d21-136">Após clicar em **OK**, um cálculo de custo dos ativos selecionados será mostrado.</span><span class="sxs-lookup"><span data-stu-id="16d21-136">Click **OK**, and a cost calculation for the selected assets is shown.</span></span> <span data-ttu-id="16d21-137">O mesmo procedimento pode ser feito para locais funcionais em **Todos os locais funcionais** ou **Locais funcionais ativos**, e para ordens de serviço **Todas as ordens de serviço** ou **Ordens de serviço ativas**.</span><span class="sxs-lookup"><span data-stu-id="16d21-137">The same procedure can be done for functional locations in **All functional locations** or **Active functional locations**, and for work orders in **All work orders** or **Active work orders**.</span></span>


## <a name="work-order-date-control"></a><span data-ttu-id="16d21-138">Controle de data da ordem de serviço</span><span class="sxs-lookup"><span data-stu-id="16d21-138">Work order date control</span></span>

<span data-ttu-id="16d21-139">Use esta página para obter uma visão geral das datas inicial e final esperadas em comparação com as datas inicial e final reais nas ordens de serviço.</span><span class="sxs-lookup"><span data-stu-id="16d21-139">Use this page to get an overview of expected start and end dates compared to actual start and end dates on work orders.</span></span>

1. <span data-ttu-id="16d21-140">Clique em **Gerenciamento de ativos** > **Consultas** > **Ordens de trabalho** > **Controle de data da ordem de serviço**.</span><span class="sxs-lookup"><span data-stu-id="16d21-140">Click **Asset management** > **Inquiries** > **Work orders** > **Work order date control**.</span></span>

2. <span data-ttu-id="16d21-141">Clique em **Calcular**.</span><span class="sxs-lookup"><span data-stu-id="16d21-141">Click **Calculate**.</span></span>

3. <span data-ttu-id="16d21-142">Selecione um local funcional no campo **Local funcional**.</span><span class="sxs-lookup"><span data-stu-id="16d21-142">Select a functional location in the **Functional location** field.</span></span>

4. <span data-ttu-id="16d21-143">Insira o intervalo para o qual você deseja fazer o cálculo nos campos **Data inicial** e **Data final**.</span><span class="sxs-lookup"><span data-stu-id="16d21-143">Insert the range for which you want to make the calculation in the **From date** and **To date** fields.</span></span> <span data-ttu-id="16d21-144">Todas as ordens de serviço com data inicial esperada dentro do intervalo serão incluídas.</span><span class="sxs-lookup"><span data-stu-id="16d21-144">All work orders with expected start date within the range will be included.</span></span>

5. <span data-ttu-id="16d21-145">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="16d21-145">Click **OK**.</span></span>

6. <span data-ttu-id="16d21-146">Clique nos botões **Agrupar por** para mostrar o nível de detalhes necessário para o cálculo.</span><span class="sxs-lookup"><span data-stu-id="16d21-146">Click the **Group by** buttons to show the required detail level of the calculation.</span></span> <span data-ttu-id="16d21-147">Os botões selecionados de **Agrupar por** são realçados.</span><span class="sxs-lookup"><span data-stu-id="16d21-147">The selected **Group by** buttons are highlighted.</span></span> <span data-ttu-id="16d21-148">Clique em um botão para ativá-los ou desativá-los.</span><span class="sxs-lookup"><span data-stu-id="16d21-148">Click on a button to activate or deactivate it.</span></span>

## <a name="example"></a><span data-ttu-id="16d21-149">Exemplo</span><span class="sxs-lookup"><span data-stu-id="16d21-149">Example</span></span>

<span data-ttu-id="16d21-150">A captura de tela abaixo mostra um exemplo de resultados de cálculo em **Controle de data da ordem de serviço**.</span><span class="sxs-lookup"><span data-stu-id="16d21-150">The screenshot below shows an example of calculation results in **Work order date control**.</span></span>

- <span data-ttu-id="16d21-151">O campo **Atraso inicial médio** mostra a diferença de dias entre a data inicial agendada de uma ordem de serviço e a data inicial real.</span><span class="sxs-lookup"><span data-stu-id="16d21-151">The **Avg. start delay** field shows the difference in days between scheduled start date for a work order compared to actual start date.</span></span> <span data-ttu-id="16d21-152">Se, por exemplo, a data inicial real for dois dias antes da data inicial agendada, "-2" será exibido neste campo.</span><span class="sxs-lookup"><span data-stu-id="16d21-152">If, for example, the actual start date was two days before the scheduled start date, "-2" will be displayed in this field.</span></span>  
- <span data-ttu-id="16d21-153">O campo **Atraso final médio** mostra a diferença de dias entre a data final agendada de uma ordem de serviço e a data final real.</span><span class="sxs-lookup"><span data-stu-id="16d21-153">The **Avg. end delay** field shows the difference in days between scheduled end date for a work order compared to actual end date.</span></span> <span data-ttu-id="16d21-154">Se, por exemplo, a data final real foi três dias após a data final programada, "3" será exibido neste campo.</span><span class="sxs-lookup"><span data-stu-id="16d21-154">If, for example, the actual end date was three days after the scheduled end date, "3" will be displayed in this field.</span></span>  
- <span data-ttu-id="16d21-155">Os campos **Ocorrências** mostram o número de vezes em que ocorrem desvios em relação à data inicial agendada e real e a data final agendada e real na ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="16d21-155">The **Occurrences** fields show the number of times deviations occur in relation to scheduled and actual start date, and scheduled and actual end date on the work order.</span></span>

![Resultados do cálculo de exemplo em Controle de datas da ordem de serviço](media/03-controlling-and-reporting.png)


