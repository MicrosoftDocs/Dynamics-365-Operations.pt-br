---
title: Controle de horas de trabalho
description: Este tópico explica o controle de hora de trabalho no Gerenciamento de Ativos.
author: josaw1
manager: tfehr
ms.date: 08/23/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetHourControl
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 0d2f4e86b5dec84d4a24db6a4f9f9f16f6a765bd
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4422077"
---
# <a name="work-hour-control"></a><span data-ttu-id="58b4d-103">Controle de horas de trabalho</span><span class="sxs-lookup"><span data-stu-id="58b4d-103">Work hour control</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="58b4d-104">No Gerenciamento de ativos, é possível calcular as horas para obter uma visão geral de horas reais em comparação com as horas de orçamento em ativos, locais funcionais ou ordens de serviço.</span><span class="sxs-lookup"><span data-stu-id="58b4d-104">In Asset Management, you can calculate hours to get an overview of actual hours compared to budget hours on assets, functional locations, or work orders.</span></span> <span data-ttu-id="58b4d-105">As horas reais são baseadas em transações lançadas.</span><span class="sxs-lookup"><span data-stu-id="58b4d-105">Actual hours are based on posted transactions.</span></span>

## <a name="work-hour-control-for-assets-functional-locations-and-work-orders"></a><span data-ttu-id="58b4d-106">Controle de hora de trabalho para ativos, locais funcionais e ordens de serviço</span><span class="sxs-lookup"><span data-stu-id="58b4d-106">Work hour control for assets, functional locations, and work orders</span></span>

<span data-ttu-id="58b4d-107">Os cálculos efetuados para ativos, locais funcionais e ordens de trabalho são quase idênticos.</span><span class="sxs-lookup"><span data-stu-id="58b4d-107">The calculations made for assets, functional locations, and work orders are almost identical.</span></span> <span data-ttu-id="58b4d-108">A única diferença é que para ativos e locais funcionais, você também podem incluir subativos e sub-locais em seu cálculo.</span><span class="sxs-lookup"><span data-stu-id="58b4d-108">Only difference is that for assets and functional locations, you can also include sub assets and sub locations in your calculation.</span></span> <span data-ttu-id="58b4d-109">A data é a data da transação quando o registro foi feito.</span><span class="sxs-lookup"><span data-stu-id="58b4d-109">The date is the transaction date when the registration was recorded.</span></span>

1. <span data-ttu-id="58b4d-110">Clique em **Gerenciamento de ativos** > **Consultas** > **Ativos** > **Controle de horas de ativos** ou **Controle de horas do local funcional**, ou **Gerenciamento de ativos** > **Consultas** > **Ordens de serviço** > **Controle de horas da ordem de serviço**.</span><span class="sxs-lookup"><span data-stu-id="58b4d-110">Click **Asset management** > **Inquiries** > **Assets** > **Asset hour control** or **Functional location hour control**, or **Asset management** > **Inquiries** > **Work orders** > **Work order hour control**.</span></span>

2. <span data-ttu-id="58b4d-111">Na caixa de diálogo **Controle de horas de ativo**.</span><span class="sxs-lookup"><span data-stu-id="58b4d-111">In the **Asset hour control** dialog, .</span></span>

3. <span data-ttu-id="58b4d-112">Na caixa de diálogo **Controle de horas de ativo** / **Controle de horas do local funcional** / **Controle de horas da ordem de serviço**, selecione um período a ser calculado nos campos **De** e **Até**.</span><span class="sxs-lookup"><span data-stu-id="58b4d-112">In the **Asset hour control** / **Functional location hour control** / **Work order hour control** dialog, select a period to be calculated in the **From date** and **To date** fields.</span></span>

4. <span data-ttu-id="58b4d-113">Se necessário, selecione um **Conjunto de dimensões financeiras** para ser incluído no cálculo.</span><span class="sxs-lookup"><span data-stu-id="58b4d-113">If required, select a **Financial dimension set** to be included in the calculation.</span></span>

5. <span data-ttu-id="58b4d-114">Selecione "Sim" no botão de alternância **Ignorar zero** se não desejar exibir resultados contendo zero horas.</span><span class="sxs-lookup"><span data-stu-id="58b4d-114">Select "Yes" on the **Skip zero** toggle button if you don't want to show results containing zero hours.</span></span>

6. <span data-ttu-id="58b4d-115">Você pode usar o campo **Nível** para indicar o nível de detalhamento desejado das linhas de controle de hora em relação aos locais funcionais.</span><span class="sxs-lookup"><span data-stu-id="58b4d-115">You can use the **Level** field to indicate how detailed you want the hour control lines to be regarding functional locations.</span></span> 

    <span data-ttu-id="58b4d-116">Por exemplo, se você inserir o número "1" no campo e tiver uma hierarquia de localização funcional em vários níveis, todas as linhas de controles de horas para um local funcional serão mostradas no nível superior e, portanto, as horas em uma linha poderão ser adicionadas em locais funcionais localizados em um nível inferior.</span><span class="sxs-lookup"><span data-stu-id="58b4d-116">For example, if you insert the number "1" in the field, and you have a multi-level functional location hierarchy, all hour control lines for a functional location will be shown on the top level, and therefore the hours on a line may be added up from functional locations located at a lower level.</span></span> 
    
    <span data-ttu-id="58b4d-117">Se você inserir o número "0" no campo **Nível**, verá um resultado detalhado mostrando todas as linhas de controle de horas em todo o nível do local funcional ao qual elas estão relacionadas.</span><span class="sxs-lookup"><span data-stu-id="58b4d-117">If you insert the number "0" in the **Level** field, you will see a detailed result showing all hour control lines on all the functional location levels to which they are related.</span></span>

7. <span data-ttu-id="58b4d-118">Selecione "Sim" no botão de alternância **incluir subativos** para exibir custos relacionados a subativos como linhas separadas.</span><span class="sxs-lookup"><span data-stu-id="58b4d-118">Select "Yes" on the **Include sub assets** toggle button to show costs related to sub assets as separate lines.</span></span>

8. <span data-ttu-id="58b4d-119">Para limitar a pesquisa, você poderá selecionar ativos específicos/locais funcionais/ordens de trabalho na Guia Rápida **Registros a serem incluídos**.</span><span class="sxs-lookup"><span data-stu-id="58b4d-119">If you want to limit the search, you can select specific assets / functional locations / work orders on the **Records to include** FastTab.</span></span>

9. <span data-ttu-id="58b4d-120">Clique em **OK** para iniciar o cálculo.</span><span class="sxs-lookup"><span data-stu-id="58b4d-120">Click **OK** to start the calculation.</span></span>

10. <span data-ttu-id="58b4d-121">Na página **Controle de hora de ativo**, clique nos botões de **Agrupar por** para mostrar o nível de detalhe necessário do cálculo.</span><span class="sxs-lookup"><span data-stu-id="58b4d-121">On the **Asset hour control** page, click the **Group by** buttons to show the required detail level of the calculation.</span></span> <span data-ttu-id="58b4d-122">Os botões selecionados de **Agrupar por** são realçados.</span><span class="sxs-lookup"><span data-stu-id="58b4d-122">The selected **Group by** buttons are highlighted.</span></span> <span data-ttu-id="58b4d-123">Clique em um botão para ativá-los ou desativá-los.</span><span class="sxs-lookup"><span data-stu-id="58b4d-123">Click on a button to activate or deactivate it.</span></span>

## <a name="example"></a><span data-ttu-id="58b4d-124">Exemplo</span><span class="sxs-lookup"><span data-stu-id="58b4d-124">Example</span></span>

<span data-ttu-id="58b4d-125">A captura de tela abaixo mostra um exemplo de cálculo de **Controle de hora de ativo**.</span><span class="sxs-lookup"><span data-stu-id="58b4d-125">The screenshot below shows an example of an **Asset hour control** calculation.</span></span>

- <span data-ttu-id="58b4d-126">O campo **Orçamento original** mostra as horas do orçamento da previsão da ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="58b4d-126">The **Original budget** field shows budget hours from the work order forecast.</span></span> 
- <span data-ttu-id="58b4d-127">O campo **Horas reais** mostra as horas lançadas nas ordens de serviço.</span><span class="sxs-lookup"><span data-stu-id="58b4d-127">The **Actual hours** field shows posted hours on work orders.</span></span> 
- <span data-ttu-id="58b4d-128">O campo **Horas comprometidas** mostra a quantidade de horas totais com os quais sua empresa está comprometida em relação às ordens de serviço.</span><span class="sxs-lookup"><span data-stu-id="58b4d-128">The **Committed hours** field shows total amount of hours that your company is committed to in relation to work orders.</span></span>

![Exemplo de cálculo de controle de hora de ativo](media/04-controlling-and-reporting.png)

<span data-ttu-id="58b4d-130">Outra maneira de fazer um cálculo de uma hora é selecionar vários ativos em **Todos os ativos** ou **Ativos válidos**.</span><span class="sxs-lookup"><span data-stu-id="58b4d-130">Another way of making an hour calculation is to multi-select assets in **All assets** or **Active assets**.</span></span> <span data-ttu-id="58b4d-131">Em seguida, clique no botão **Controle de horas** na Guia Rápida **Geral**.</span><span class="sxs-lookup"><span data-stu-id="58b4d-131">Then you click the **Hour control** button on the **General** FastTab.</span></span> <span data-ttu-id="58b4d-132">Os ativos selecionados são inseridos automaticamente no campo **Ativo** na Guia Rápida **Registros a incluir**.</span><span class="sxs-lookup"><span data-stu-id="58b4d-132">The selected assets are automatically inserted in the **Asset** field on the **Records to include** FastTab.</span></span> <span data-ttu-id="58b4d-133">Clique em **OK** na caixa de diálogo **Controle de horas de ativo** e o cálculo para os ativos selecionados é exibido.</span><span class="sxs-lookup"><span data-stu-id="58b4d-133">Click **OK** in the **Asset hour control** dialog, and the calculation for the selected assets is shown.</span></span> <span data-ttu-id="58b4d-134">O mesmo procedimento pode ser feito para locais funcionais em **Todos os locais funcionais** ou **Locais funcionais ativos**, e para ordens de serviço **Todas as ordens de serviço** ou **Ordens de serviço ativas**.</span><span class="sxs-lookup"><span data-stu-id="58b4d-134">The same procedure can be done for functional locations in **All functional locations** or **Active functional locations**, and for work orders in **All work orders** or **Active work orders**.</span></span>


