---
title: Controle de custo de falhas de ativos
description: Este tópico explica o controle de custo de falhas de ativos no Gerenciamento de Ativos.
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
ms.openlocfilehash: 3c34180ad99db29147587bb002aaa6badc918717
ms.sourcegitcommit: fb66731f05207094149a6bc7b8549a4dabbb071a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/22/2019
ms.locfileid: "2652232"
---
# <a name="asset-fault-cost-control"></a><span data-ttu-id="bbecf-103">Controle de custo de falhas de ativos</span><span class="sxs-lookup"><span data-stu-id="bbecf-103">Asset fault cost control</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="bbecf-104">No Gerenciamento de Ativos, é possível calcular os custos nos registros de falhas de ativos para obter uma visão geral dos custos reais em comparação com os custos de orçamento.</span><span class="sxs-lookup"><span data-stu-id="bbecf-104">In Asset Management, you can calculate costs on asset fault registrations to get an overview of actual costs compared to budget costs.</span></span> <span data-ttu-id="bbecf-105">Os custos reais são baseados em transações lançadas.</span><span class="sxs-lookup"><span data-stu-id="bbecf-105">Actual costs are based on posted transactions.</span></span> <span data-ttu-id="bbecf-106">A data é a data da falha na qual o sintoma foi registrado.</span><span class="sxs-lookup"><span data-stu-id="bbecf-106">The date is the fault date on which the symptom was recorded.</span></span>

1. <span data-ttu-id="bbecf-107">Clique em **Gerenciamento de ativos** > **Consultas** > **Falha de ativo** > **Controle de custo de falhas de ativos**.</span><span class="sxs-lookup"><span data-stu-id="bbecf-107">Click **Asset management** > **Inquiries** > **Asset fault** > **Asset fault cost control**.</span></span>

2. <span data-ttu-id="bbecf-108">Na caixa de diálogo **Controle de custo de falhas de ativos**, selecione uma dimensão financeira definida para ser incluída no cálculo, se necessário.</span><span class="sxs-lookup"><span data-stu-id="bbecf-108">In the **Asset fault cost control** dialog, select a financial dimension set to be included in the calculation, if required.</span></span>

4. <span data-ttu-id="bbecf-109">Selecione "Sim" no botão de alternância **Ignorar zero** se não desejar exibir resultados com custo zero.</span><span class="sxs-lookup"><span data-stu-id="bbecf-109">Select "Yes" on the **Skip zero** toggle button if you don't want to show results with a cost of zero.</span></span>

5. <span data-ttu-id="bbecf-110">Você pode usar o campo **Nível** para indicar o nível de detalhamento desejado das linhas de controle de custo em relação aos locais funcionais.</span><span class="sxs-lookup"><span data-stu-id="bbecf-110">You can use the **Level** field to indicate how detailed you want the cost control lines to be regarding functional locations.</span></span> 

    <span data-ttu-id="bbecf-111">Por exemplo, se você inserir o número "1" no campo e tiver uma estrutura de localização funcional em vários níveis, todas as linhas de controle de custo de falhas de ativos para um local funcional serão mostradas no nível superior e, portanto, as horas em uma linha poderão ser adicionadas em locais funcionais localizados em um nível inferior.</span><span class="sxs-lookup"><span data-stu-id="bbecf-111">For example, if you insert the number "1" in the field, and you have a multi-level functional location structure, all asset fault cost control lines for a functional location will be shown on the top level, and therefore the hours on a line may be added up from functional locations located at a lower level.</span></span> 
    
    <span data-ttu-id="bbecf-112">Se você inserir o número "0" no campo **Nível**, verá um resultado detalhado mostrando todas as linhas de controle de custos de falhas de ativos em todo o nível do local funcional ao qual elas estão relacionadas.</span><span class="sxs-lookup"><span data-stu-id="bbecf-112">If you insert the number "0" in the **Level** field, you will see a detailed result showing all asset fault cost control lines on all the functional location levels to which they are related.</span></span>

6. <span data-ttu-id="bbecf-113">Para limitar a pesquisa, você poderá selecionar ativos específicos, datas de falha e causas de falha na Guia Rápida **Registros a serem incluídos**.</span><span class="sxs-lookup"><span data-stu-id="bbecf-113">If you want to limit the search, you can select specific assets, fault dates, and fault causes on the **Records to include** FastTab.</span></span>

7. <span data-ttu-id="bbecf-114">Clique em **OK**para iniciar o cálculo.</span><span class="sxs-lookup"><span data-stu-id="bbecf-114">Click **OK** to start the calculation.</span></span>

8. <span data-ttu-id="bbecf-115">Clique nos botões **Agrupar por** para mostrar o nível de detalhes necessário para o cálculo.</span><span class="sxs-lookup"><span data-stu-id="bbecf-115">Click the **Group by** buttons to show the required detail level of the calculation.</span></span> <span data-ttu-id="bbecf-116">Os botões selecionados de **Agrupar por** são realçados.</span><span class="sxs-lookup"><span data-stu-id="bbecf-116">The selected **Group by** buttons are highlighted.</span></span> <span data-ttu-id="bbecf-117">Clique em um botão para ativá-los ou desativá-los.</span><span class="sxs-lookup"><span data-stu-id="bbecf-117">Click on a button to activate or deactivate it.</span></span>

## <a name="example"></a><span data-ttu-id="bbecf-118">Exemplo</span><span class="sxs-lookup"><span data-stu-id="bbecf-118">Example</span></span>

<span data-ttu-id="bbecf-119">Esse exemplo mostra um cálculo de controle de custo de falha de ativo.</span><span class="sxs-lookup"><span data-stu-id="bbecf-119">This example shows an asset fault cost control calculation.</span></span>

- <span data-ttu-id="bbecf-120">O campo **Orçamento original** mostra os custos do orçamento da previsão da ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="bbecf-120">The **Original budget** field shows budget costs from the work order forecast.</span></span> 
- <span data-ttu-id="bbecf-121">O campo **Custo real** mostra os custos lançados nas ordens de serviço.</span><span class="sxs-lookup"><span data-stu-id="bbecf-121">The **Actual cost** field shows posted costs on work orders.</span></span> 
- <span data-ttu-id="bbecf-122">O campo **Custo comprometido** mostra os custos totais com os quais sua empresa está comprometida em relação às ordens de serviço.</span><span class="sxs-lookup"><span data-stu-id="bbecf-122">The **Committed cost** field shows total costs that your company is committed to in relation to work orders.</span></span>

    ![Figura 1](media/05-controlling-and-reporting.png)

<span data-ttu-id="bbecf-124">Para obter informações sobre como configurar as falhas, consulte o tópico [Gerenciamento de falhas](../setup-for-work-orders/fault-management.md).</span><span class="sxs-lookup"><span data-stu-id="bbecf-124">For information about how to set up faults, see the [Fault management](../setup-for-work-orders/fault-management.md) topic.</span></span>
