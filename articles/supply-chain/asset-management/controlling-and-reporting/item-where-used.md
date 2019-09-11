---
title: Item onde é usado
description: Este tópico explica como obter uma visão geral de onde o item é usado no Gerenciamento de Ativos.
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
ms.openlocfilehash: 84ab803aedf5b803b6c5f39ff1907726335cb45d
ms.sourcegitcommit: 2292b54e2da96f71b59ec9ccf17cd32d3d1d8b21
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/23/2019
ms.locfileid: "1918317"
---
# <a name="item-where-used"></a><span data-ttu-id="d68d6-103">Item onde é usado</span><span class="sxs-lookup"><span data-stu-id="d68d6-103">Item where used</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="d68d6-104">Você pode criar um cálculo para que um item específico obtenha uma visão geral de onde o item foi usado no Gerenciamento de Ativos.</span><span class="sxs-lookup"><span data-stu-id="d68d6-104">You can make a calculation for a specific item to get an overview of where in Asset Management the item has been used.</span></span> <span data-ttu-id="d68d6-105">Os resultados mostram o contexto no qual o item foi usado durante seu tempo de vida.</span><span class="sxs-lookup"><span data-stu-id="d68d6-105">The results show the context in which the item has been used during its lifetime.</span></span> <span data-ttu-id="d68d6-106">A página **Item onde usado** pode ser aberta do menu principal do Gerenciamento de ativos e também pode ser acessada das seguintes páginas:</span><span class="sxs-lookup"><span data-stu-id="d68d6-106">The **Item where used** page can be opened from the main Asset management menu, and it can also be accessed from the following pages:</span></span>

[<span data-ttu-id="d68d6-107">BOM de ativos</span><span class="sxs-lookup"><span data-stu-id="d68d6-107">Asset BOM</span></span>](../objects/object-BOM.md)

[<span data-ttu-id="d68d6-108">Peças sobressalentes nos padrões do tipo de ativo</span><span class="sxs-lookup"><span data-stu-id="d68d6-108">Spare parts on asset type defaults</span></span>](../setup-for-objects/object-types.md)

[<span data-ttu-id="d68d6-109">Previsão do item na previsão padrão do tipo de trabalho de manutenção</span><span class="sxs-lookup"><span data-stu-id="d68d6-109">Item forecast on Maintenance job type defaults forecast</span></span>](../setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md)

[<span data-ttu-id="d68d6-110">Previsão de manutenção da ordem de serviço</span><span class="sxs-lookup"><span data-stu-id="d68d6-110">Work order maintenance forecast</span></span>](../work-orders/maintenance-forecasts.md)

[<span data-ttu-id="d68d6-111">Requisição de compra da ordem de serviço</span><span class="sxs-lookup"><span data-stu-id="d68d6-111">Work order purchase requisition</span></span>](../work-orders/procurement.md)

[<span data-ttu-id="d68d6-112">Compra da ordem de serviço</span><span class="sxs-lookup"><span data-stu-id="d68d6-112">Work order purchase</span></span>](../work-orders/procurement.md)

## <a name="make-an-item-where-used-calculation"></a><span data-ttu-id="d68d6-113">Criar um cálculo de item onde usado</span><span class="sxs-lookup"><span data-stu-id="d68d6-113">Make an item-where-used calculation</span></span>

1. <span data-ttu-id="d68d6-114">Clique em **Gerenciamento de ativos** > **Consultas** > **Item onde usado** ou selecione o botão **Item onde usado** em uma das páginas mencionadas acima.</span><span class="sxs-lookup"><span data-stu-id="d68d6-114">Click **Asset management** > **Inquiries** > **Item where used**, or select the **Item where used** button on one of the pages mentioned above.</span></span>

2. <span data-ttu-id="d68d6-115">Na caixa de diálogo **Item onde usado**, selecione o item para o qual você deseja fazer o cálculo no campo **Número do item**.</span><span class="sxs-lookup"><span data-stu-id="d68d6-115">In the **Item where used** dialog, select the item for which you want to make the calculation in the **Item number** field.</span></span>

3. <span data-ttu-id="d68d6-116">Você pode usar o campo **Nível** para indicar o nível de detalhamento desejado das linhas de item em relação aos locais funcionais.</span><span class="sxs-lookup"><span data-stu-id="d68d6-116">You can use the **Level** field to indicate how detailed you want the item lines to be regarding functional locations.</span></span> <span data-ttu-id="d68d6-117">Por exemplo, se você inserir o número “1 "no campo e tiver uma estrutura de local funcional com vários níveis, todas as linhas do item de um local funcional serão mostrados em nível superior.</span><span class="sxs-lookup"><span data-stu-id="d68d6-117">For example, if you insert the number "1" in the field, and you have a multi-level functional location structure, all item lines for a functional location will be shown on the top level.</span></span> <span data-ttu-id="d68d6-118">Portanto, relação/quantidade em uma linha podem ser adicionado de locais funcionais localizados em nível inferior.</span><span class="sxs-lookup"><span data-stu-id="d68d6-118">Therefore, relation/quantity on a line may be added up from functional locations located at a lower level.</span></span> <span data-ttu-id="d68d6-119">Se você inserir o número "0" no campo **Nível**, verá um resultado detalhado mostrando todas as linhas de item em todos os níveis do local funcional ao qual elas estão relacionadas.</span><span class="sxs-lookup"><span data-stu-id="d68d6-119">If you insert the number "0" in the **Level** field, you will see a detailed result showing all item lines on all the functional location levels to which they are related.</span></span>

4. <span data-ttu-id="d68d6-120">Na seção **Incluir**, selecione "Sim" nos botões de alternância que você deseja incluir no cálculo.</span><span class="sxs-lookup"><span data-stu-id="d68d6-120">In the **Include** section, select "Yes" on the toggle buttons that you want to include in the calculation.</span></span>

5. <span data-ttu-id="d68d6-121">Clique em **OK**para iniciar o cálculo.</span><span class="sxs-lookup"><span data-stu-id="d68d6-121">Click **OK** to start the calculation.</span></span>

6. <span data-ttu-id="d68d6-122">Na guia **Item onde usado** > grupos do painel de ação **Agrupar por...**, selecione os botões relevantes para mostrar o nível de detalhe necessário do cálculo.</span><span class="sxs-lookup"><span data-stu-id="d68d6-122">On the **Item where used** tab > **Group by...** action pane groups, select the relevant buttons to show the required detail level of the calculation.</span></span> <span data-ttu-id="d68d6-123">Os botões do painel de ações selecionados são destacados.</span><span class="sxs-lookup"><span data-stu-id="d68d6-123">The selected action pane buttons are highlighted.</span></span> <span data-ttu-id="d68d6-124">Clique em um botão para ativá-los ou desativá-los.</span><span class="sxs-lookup"><span data-stu-id="d68d6-124">Click on a button to activate or deactivate it.</span></span>

7. <span data-ttu-id="d68d6-125">Se quiser mostrar as dimensões relacionadas ao item, clique em **Exibir dimensões** e selecione as dimensões a serem mostradas.</span><span class="sxs-lookup"><span data-stu-id="d68d6-125">If you want to show dimensions related to the item, click **Display dimensions**, and select the dimensions to be shown.</span></span>

<span data-ttu-id="d68d6-126">Na figura abaixo, você verá um exemplo de um cálculo de item onde usado para o número do item "1000".</span><span class="sxs-lookup"><span data-stu-id="d68d6-126">In the figure below, you see an example of an item-where-used calculation for item number "1000".</span></span>

![Figura 1](media/12-controlling-and-reporting.png)

