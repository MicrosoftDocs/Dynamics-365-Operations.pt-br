---
title: Controle de custo e data
description: Este tópico explica o controle de custo e data no Gerenciamento de Ativos.
author: josaw1
manager: AnnBe
ms.date: 08/23/2019
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
ms.openlocfilehash: 2bcd1584f6a858f7589387fbfe96267b7c16176a
ms.sourcegitcommit: 2292b54e2da96f71b59ec9ccf17cd32d3d1d8b21
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/23/2019
ms.locfileid: "1918386"
---
# <a name="cost-and-date-control"></a><span data-ttu-id="b5d72-103">Controle de custo e data</span><span class="sxs-lookup"><span data-stu-id="b5d72-103">Cost and date control</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="b5d72-104">No Gerenciamento de ativos, é possível calcular os custos para obter uma visão geral dos custos reais em comparação com os custos de orçamento em ativos, locais funcionais e ordens de serviço.</span><span class="sxs-lookup"><span data-stu-id="b5d72-104">In Asset Management, you can calculate costs to get an overview of actual costs compared to budget costs on assets, functional locations, and work orders.</span></span> <span data-ttu-id="b5d72-105">Os custos reais são baseados em transações lançadas.</span><span class="sxs-lookup"><span data-stu-id="b5d72-105">Actual costs are based on posted transactions.</span></span> <span data-ttu-id="b5d72-106">Você também pode fazer um cálculo de data para comparar datas inicial e final agendadas com datas de início e término reais em ordens de serviço.</span><span class="sxs-lookup"><span data-stu-id="b5d72-106">You can also make a date calculation if you want to compare scheduled start and end dates to actual start and end dates on work orders.</span></span>

## <a name="cost-control-for-assets-functional-locations-and-work-orders"></a><span data-ttu-id="b5d72-107">Controle de custos para ativos, locais funcionais e ordens de serviço</span><span class="sxs-lookup"><span data-stu-id="b5d72-107">Cost control for assets, functional locations, and work orders</span></span>

<span data-ttu-id="b5d72-108">Os cálculos efetuados para ativos, locais funcionais e ordens de trabalho são quase idênticos.</span><span class="sxs-lookup"><span data-stu-id="b5d72-108">The calculations made for assets, functional locations, and work orders are almost identical.</span></span> <span data-ttu-id="b5d72-109">A única diferença é que para ativos e locais funcionais, você também podem incluir subativos e sub-locais em seu cálculo.</span><span class="sxs-lookup"><span data-stu-id="b5d72-109">Only difference is that for assets and functional locations, you can also include sub assets and sub locations in your calculation.</span></span> <span data-ttu-id="b5d72-110">A data é a data da transação quando o registro foi feito.</span><span class="sxs-lookup"><span data-stu-id="b5d72-110">The date is the transaction date when the registration was recorded.</span></span>

1. <span data-ttu-id="b5d72-111">Clique em **Gerenciamento de ativos** > **Consultas** > **Ativos** > **Controle de custos de ativos** ou **Controle de custos do local funcional**, ou **Gerenciamento de ativos** > **Consultas** > **Ordens de serviço** > **Controle de custos da ordem de serviço**.</span><span class="sxs-lookup"><span data-stu-id="b5d72-111">Click **Asset management** > **Inquiries** > **Assets** > **Asset cost control** or **Functional location cost control**, or **Asset management** > **Inquiries** > **Work orders** > **Work order cost control**.</span></span>

2. <span data-ttu-id="b5d72-112">Na caixa de diálogo **Controle de custos de ativos** / **Controle de custos do local funcional** / **Controle de custos da ordem de serviço**, selecione um período a ser calculado.</span><span class="sxs-lookup"><span data-stu-id="b5d72-112">In the **Asset cost control** / **Functional location cost control** / **Work order cost control** dialog, select a period to be calculated.</span></span>

3. <span data-ttu-id="b5d72-113">Se necessário, selecione um conjunto de dimensões financeiras para ser incluído no cálculo.</span><span class="sxs-lookup"><span data-stu-id="b5d72-113">If required, select a financial dimension set to be included in the calculation.</span></span>

4. <span data-ttu-id="b5d72-114">Selecione "Sim" no botão de alternância **Ignorar zero** se não desejar exibir resultados com custo zero.</span><span class="sxs-lookup"><span data-stu-id="b5d72-114">Select "Yes" on the **Skip zero** toggle button if you don't want to show results with a cost of zero.</span></span>

5. <span data-ttu-id="b5d72-115">Você pode usar o campo **Nível** para indicar o nível de detalhamento desejado das linhas de controle de custo em relação aos locais funcionais.</span><span class="sxs-lookup"><span data-stu-id="b5d72-115">You can use the **Level** field to indicate how detailed you want the cost control lines to be regarding functional locations.</span></span> <span data-ttu-id="b5d72-116">Por exemplo, se você inserir o número "1" no campo e tiver uma hierarquia de localização funcional em vários níveis, todas as linhas de controles de custos para um local funcional serão mostradas no nível superior e, portanto, as horas em uma linha poderão ser adicionadas em locais funcionais localizados em um nível inferior.</span><span class="sxs-lookup"><span data-stu-id="b5d72-116">For example, if you insert the number "1" in the field, and you have a multi-level functional location hierarchy, all cost control lines for a functional location will be shown on the top level, and therefore the hours on a line may be added up from functional locations located at a lower level.</span></span> <span data-ttu-id="b5d72-117">Se você inserir o número "0" no campo **Nível**, verá um resultado detalhado mostrando todas as linhas de controle de custos em todo o nível do local funcional ao qual elas estão relacionadas.</span><span class="sxs-lookup"><span data-stu-id="b5d72-117">If you insert the number "0" in the **Level** field, you will see a detailed result showing all cost control lines on all the functional location level to which they are related.</span></span>

6. <span data-ttu-id="b5d72-118">Selecione "Sim" no botão de alternância **Mostrar custo comprometido aberto** se quiser incluir essa coluna no cálculo.</span><span class="sxs-lookup"><span data-stu-id="b5d72-118">Select "Yes" on the **Show open committed cost** toggle button if you want to include that column in the calculation.</span></span>

7. <span data-ttu-id="b5d72-119">Selecione "Sim" no botão de alternância **incluir subativos** para exibir custos relacionados a subativos como linhas separadas.</span><span class="sxs-lookup"><span data-stu-id="b5d72-119">Select "Yes" on the **Include sub assets** toggle button to show costs related to sub assets as separate lines.</span></span>

8. <span data-ttu-id="b5d72-120">Para limitar a pesquisa, você poderá selecionar ativos específicos/locais funcionais/ordens de trabalho na Guia Rápida **Registros a serem incluídos**.</span><span class="sxs-lookup"><span data-stu-id="b5d72-120">If you want to limit the search, you can select specific assets / functional locations / work orders on the **Records to include** FastTab.</span></span>

9. <span data-ttu-id="b5d72-121">Clique em **OK**para iniciar o cálculo.</span><span class="sxs-lookup"><span data-stu-id="b5d72-121">Click **OK** to start the calculation.</span></span>

<span data-ttu-id="b5d72-122">A figura abaixo mostra um exemplo da caixa de diálogo **Controle de custos de ativos**.</span><span class="sxs-lookup"><span data-stu-id="b5d72-122">The figure below shows an example of the **Asset cost control** dialog.</span></span>

![Figura 1](media/01-controlling-and-reporting.png)

10. <span data-ttu-id="b5d72-124">Nos grupos do Painel de Ações **Agrupar por...** na página **Controle de custos de ativos**, clique nos botões relevantes para mostrar o nível de detalhe necessário do cálculo.</span><span class="sxs-lookup"><span data-stu-id="b5d72-124">In the **Group by...** action pane groups on the **Asset cost control** page, click the relevant buttons to show the required detail level of the calculation.</span></span> <span data-ttu-id="b5d72-125">Os botões do painel de ações selecionados são destacados.</span><span class="sxs-lookup"><span data-stu-id="b5d72-125">The selected action pane buttons are highlighted.</span></span> <span data-ttu-id="b5d72-126">Clique em um botão para ativá-los ou desativá-los.</span><span class="sxs-lookup"><span data-stu-id="b5d72-126">Click on a button to activate or deactivate it.</span></span>

<span data-ttu-id="b5d72-127">A figura abaixo mostra um exemplo de resultados de cálculo em **Controle de custos de ativos**.</span><span class="sxs-lookup"><span data-stu-id="b5d72-127">The figure below shows an example of calculation results in **Asset cost control**.</span></span>

![Figura 2](media/02-controlling-and-reporting.png)

<span data-ttu-id="b5d72-129">Outra maneira de fazer um cálculo de custo é selecionar vários ativos em **Todos os ativos** ou **Ativos ativos**.</span><span class="sxs-lookup"><span data-stu-id="b5d72-129">Another way of making a cost calculation is to multi-select assets in **All assets** or **Active assets**.</span></span> <span data-ttu-id="b5d72-130">Depois, você clica no botão **Controle de custo** na guia **Geral**. Na caixa de diálogo **Controle de custos de ativos**, os ativos selecionados são inseridos automaticamente no campo **Ativo** na Guia Rápida **Registros a serem incluídos**.</span><span class="sxs-lookup"><span data-stu-id="b5d72-130">Then, you click the **Cost control** button on the **General** tab. In the **Asset cost control** dialog, the selected assets are automatically inserted in the **Asset** field on the **Records to include** FastTab.</span></span> <span data-ttu-id="b5d72-131">Após clicar em **OK**, um cálculo de custo dos ativos selecionados será mostrado.</span><span class="sxs-lookup"><span data-stu-id="b5d72-131">Click **OK**, and a cost calculation for the selected assets is shown.</span></span> <span data-ttu-id="b5d72-132">O mesmo procedimento pode ser feito para locais funcionais em **Todos os locais funcionais** ou **Locais funcionais ativos**, e para ordens de serviço **Todas as ordens de serviço** ou **Ordens de serviço ativas**.</span><span class="sxs-lookup"><span data-stu-id="b5d72-132">The same procedure can be done for functional locations in **All functional locations** or **Active functional locations**, and for work orders in **All work orders** or **Active work orders**.</span></span>

>[!NOTE]
><span data-ttu-id="b5d72-133">O campo **Orçamento original** mostra os custos do orçamento da previsão da ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="b5d72-133">The **Original budget** field shows budget costs from the work order forecast.</span></span> <span data-ttu-id="b5d72-134">O campo **Custo comprometido** mostra o valor total das despesas que uma entidade legal se comprometeu a pagar.</span><span class="sxs-lookup"><span data-stu-id="b5d72-134">The **Committed cost** field shows the total amount of expenses that a legal entity has committed itself to pay.</span></span> <span data-ttu-id="b5d72-135">O campo **Custo comprometido aberto** mostra compromissos de pagamento por itens, horários e serviços que você solicitou ou recebeu, mas ainda não pagou.</span><span class="sxs-lookup"><span data-stu-id="b5d72-135">The **Open committed cost** field shows commitments to pay for items, hours, and services you have ordered or received but not yet paid for.</span></span> <span data-ttu-id="b5d72-136">Após o lançamento de todos os registros de consumo, os custos relacionados serão incluídos no campo **Custo real**.</span><span class="sxs-lookup"><span data-stu-id="b5d72-136">When all consumption registrations have been posted, the related costs are included in the **Actual cost** field.</span></span>

## <a name="work-order-date-control"></a><span data-ttu-id="b5d72-137">Controle de data da ordem de serviço</span><span class="sxs-lookup"><span data-stu-id="b5d72-137">Work order date control</span></span>

<span data-ttu-id="b5d72-138">Use esta página para obter uma visão geral das datas inicial e final esperadas em comparação com as datas inicial e final reais nas ordens de serviço.</span><span class="sxs-lookup"><span data-stu-id="b5d72-138">Use this page to get an overview of expected start and end dates compared to actual start and end dates on work orders.</span></span>

1. <span data-ttu-id="b5d72-139">Clique em **Gerenciamento de ativos** > **Consultas** > **Ordens de trabalho** > **Controle de data da ordem de serviço**.</span><span class="sxs-lookup"><span data-stu-id="b5d72-139">Click **Asset management** > **Inquiries** > **Work orders** > **Work order date control**.</span></span>

2. <span data-ttu-id="b5d72-140">Clique em **Calcular**.</span><span class="sxs-lookup"><span data-stu-id="b5d72-140">Click **Calculate**.</span></span>

3. <span data-ttu-id="b5d72-141">Selecione um local funcional no campo **Local funcional**.</span><span class="sxs-lookup"><span data-stu-id="b5d72-141">Select a functional location in the **Functional location** field.</span></span>

4. <span data-ttu-id="b5d72-142">Insira o período para o qual você deseja fazer o cálculo nos campos **Data inicial** e **Data final**.</span><span class="sxs-lookup"><span data-stu-id="b5d72-142">Insert the period for which you want to make the calculation in the **From date** and **To date** fields.</span></span> <span data-ttu-id="b5d72-143">Todas as ordens de serviço com início esperado dentro do período serão incluídas.</span><span class="sxs-lookup"><span data-stu-id="b5d72-143">All work orders with expected start within the period will be included.</span></span>

5. <span data-ttu-id="b5d72-144">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="b5d72-144">Click **OK**.</span></span>

6. <span data-ttu-id="b5d72-145">Nos grupos do Painel de Ações **Agrupar por...**, clique nos botões relevantes para mostrar o nível de detalhe necessário do cálculo.</span><span class="sxs-lookup"><span data-stu-id="b5d72-145">In the **Group by...** action pane groups, click the relevant buttons to show the required detail level of the calculation.</span></span> <span data-ttu-id="b5d72-146">Os botões do painel de ações selecionados são destacados.</span><span class="sxs-lookup"><span data-stu-id="b5d72-146">The selected action pane buttons are highlighted.</span></span> <span data-ttu-id="b5d72-147">Clique em um botão para ativá-los ou desativá-los.</span><span class="sxs-lookup"><span data-stu-id="b5d72-147">Click on a button to activate or deactivate it.</span></span>

<span data-ttu-id="b5d72-148">A figura abaixo mostra um exemplo de resultados de cálculo em **Controle de data da ordem de serviço**.</span><span class="sxs-lookup"><span data-stu-id="b5d72-148">The figure below shows an example of calculation results in **Work order date control**.</span></span>

![Figura 3](media/03-controlling-and-reporting.png)

- <span data-ttu-id="b5d72-150">O campo **Atraso inicial médio** mostra a diferença de dias entre a data inicial agendada de uma ordem de serviço e a data inicial real.</span><span class="sxs-lookup"><span data-stu-id="b5d72-150">The **Avg. start delay** field shows the difference in days between scheduled start date for a work order compared to actual start date.</span></span> <span data-ttu-id="b5d72-151">Se, por exemplo, a data inicial real for dois dias antes da data inicial agendada, "-2" será exibido neste campo.</span><span class="sxs-lookup"><span data-stu-id="b5d72-151">If, for example, the actual start date was two days before the scheduled start date, "-2" will be displayed in this field.</span></span>  
- <span data-ttu-id="b5d72-152">O campo **Atraso final médio** mostra a diferença de dias entre a data final agendada de uma ordem de serviço e a data final real.</span><span class="sxs-lookup"><span data-stu-id="b5d72-152">The **Avg. end delay** field shows the difference in days between scheduled end date for a work order compared to actual end date.</span></span> <span data-ttu-id="b5d72-153">Se, por exemplo, a data final real foi três dias após a data final programada, "3" será exibido neste campo.</span><span class="sxs-lookup"><span data-stu-id="b5d72-153">If, for example, the actual end date was three days after the scheduled end date, "3" will be displayed in this field.</span></span>  
- <span data-ttu-id="b5d72-154">Os campos **Ocorrências** mostram o número de vezes em que ocorrem desvios em relação à data inicial agendada e real e a data final agendada e real na ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="b5d72-154">The **Occurrences** fields show the number of times deviations occur in relation to scheduled and actual start date, and scheduled and actual end date on the work order.</span></span>

