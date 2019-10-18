---
title: Dimensões de objeto de custo
description: Quando você a analisar custos, dimensões de usar elementos de custo estimado para determinar onde os custos a interno. Use dimensões de objeto de custo para determinar onde atribua custos. Este tópico fornece informações sobre dimensões de objeto de custo.
author: AndersGirke
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CAMDimensionMember
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 223174
ms.assetid: 2a1cdd35-30cb-41e7-9506-67fd04a537c5
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: shylaw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 90d9176a2ca37b581ef82306cc1ceef515ceb624
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2187880"
---
# <a name="cost-object-dimensions"></a><span data-ttu-id="e1f47-105">Dimensões de objeto de custo</span><span class="sxs-lookup"><span data-stu-id="e1f47-105">Cost object dimensions</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e1f47-106">Quando você a analisar custos, dimensões de usar elementos de custo estimado para determinar onde os custos a interno.</span><span class="sxs-lookup"><span data-stu-id="e1f47-106">When you analyze costs, you use cost element dimensions to determine where costs flow to.</span></span> <span data-ttu-id="e1f47-107">Use dimensões de objeto de custo para determinar onde atribua custos.</span><span class="sxs-lookup"><span data-stu-id="e1f47-107">You use cost object dimensions to determine where you should assign costs.</span></span> <span data-ttu-id="e1f47-108">Este tópico fornece informações sobre dimensões de objeto de custo.</span><span class="sxs-lookup"><span data-stu-id="e1f47-108">This topic provides information about cost object dimensions.</span></span>

<span data-ttu-id="e1f47-109">Um objeto de custo previsto pode ser qualquer tipo de objeto ao qual você deseja prever, alocar custos, ou os para medir diretamente.</span><span class="sxs-lookup"><span data-stu-id="e1f47-109">A cost object can be any type of object that you want to estimate, allocate costs to, or measure directly.</span></span> <span data-ttu-id="e1f47-110">Os objetos de custo previsto típicos incluem produto, recursos, projetos, departamentos, centros de custo, e regiões em.</span><span class="sxs-lookup"><span data-stu-id="e1f47-110">Typical cost objects include products, projects, resources, departments, cost centers, and geographical regions.</span></span> <span data-ttu-id="e1f47-111">O gerenciamento usa objetos de custo para quantificar custos e realizar análises de lucratividade.</span><span class="sxs-lookup"><span data-stu-id="e1f47-111">Management uses cost objects to quantify costs and also to drive profitability analysis.</span></span>

## <a name="cost-object-dimensions-and-cost-object-dimension-members"></a><span data-ttu-id="e1f47-112">Dimensões de elemento de custo previsto e membros da dimensão do elemento de custo previsto</span><span class="sxs-lookup"><span data-stu-id="e1f47-112">Cost object dimensions and cost object dimension members</span></span>
<span data-ttu-id="e1f47-113">Os objetos de custo previsto são conhecidos como *dimensões de custo previsto do objeto*.</span><span class="sxs-lookup"><span data-stu-id="e1f47-113">Cost objects are known as *cost object dimensions*.</span></span> <span data-ttu-id="e1f47-114">Após decidir qual entidade a dimensão de custo previsto de objeto deve consulte, especifique os valores de dimensão ou importá-los individualmente na contabilização de custo previsto de outros sistemas de origem.</span><span class="sxs-lookup"><span data-stu-id="e1f47-114">After you’ve decided which entity the cost object dimension should refer to, you must specify the individual dimension values or import them into Cost accounting from other source systems.</span></span> <span data-ttu-id="e1f47-115">Os valores de dimensão específicos são chamados de *membros da dimensão do elemento de custo previsto*.</span><span class="sxs-lookup"><span data-stu-id="e1f47-115">These individual dimension values are known as *cost object dimension members*.</span></span> <span data-ttu-id="e1f47-116">Por exemplo, desejar usar a dimensão financeira que é chamada centro de custo como a dimensão de custo previsto do objeto.</span><span class="sxs-lookup"><span data-stu-id="e1f47-116">For example, you want to use the financial dimension that is named Cost center as the cost object dimension.</span></span> <span data-ttu-id="e1f47-117">Para ver como os custos para os centros de custo individuais, você deve importar os membros de custo previsto de dimensão de objeto.</span><span class="sxs-lookup"><span data-stu-id="e1f47-117">To see how costs flow to the individual cost centers, you must import the cost object dimension members.</span></span> <span data-ttu-id="e1f47-118">Nesse caso, os membros de custo previsto de dimensão de objetos são centros de custo real, como venda, produção, administração e localizações, em.</span><span class="sxs-lookup"><span data-stu-id="e1f47-118">In this case, the cost object dimension members are the actual cost centers, such as Sales, Production, Administration, and Geographic locations.</span></span> <span data-ttu-id="e1f47-119">A captura de tela a seguir mostra um exemplo de centros de custo como dimensão de objeto de custo com seus centros de custo real como membros de dimensão de objeto de custo.</span><span class="sxs-lookup"><span data-stu-id="e1f47-119">The following screenshot shows an example of Cost Centers as the cost object dimension with its actual cost centers as cost object dimension members.</span></span> 

<span data-ttu-id="e1f47-120">[![cost-object-dimensions](./media/cost-object-dimensions.png)](./media/cost-object-dimensions.png)</span><span class="sxs-lookup"><span data-stu-id="e1f47-120">[![cost-object-dimensions](./media/cost-object-dimensions.png)](./media/cost-object-dimensions.png)</span></span>

## <a name="import-cost-object-dimension-members-through-data-connectors"></a><span data-ttu-id="e1f47-121">Membros de custo previsto de dimensão de objeto de importação em dos conectores de dados</span><span class="sxs-lookup"><span data-stu-id="e1f47-121">Import cost object dimension members through data connectors</span></span>
<span data-ttu-id="e1f47-122">Para fazer a importação de objeto de custo previsto dimensionar membros mais disso, use conectores de dados para recuperar os valores das entidades que deseja usar como dimensões de custo previsto do objeto.</span><span class="sxs-lookup"><span data-stu-id="e1f47-122">To make the import of cost object dimension members easier, you use data connectors to retrieve the values from the entities that you want to use as cost object dimensions.</span></span> <span data-ttu-id="e1f47-123">Você pode usar os conectores compilados anteriormente dados ou dos conectores personalizados de dados que você cria.</span><span class="sxs-lookup"><span data-stu-id="e1f47-123">You can use either the pre-built data connectors or custom data connectors that you build.</span></span>



