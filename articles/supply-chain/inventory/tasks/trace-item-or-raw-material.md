---
title: "Rastrear um item ou uma matéria-prima"
description: "Este procedimento demonstra como usar o rastreamento de itens para identificar onde itens ou matérias-primas foram usados ou estão sendo usados."
author: pjacobse
manager: AnnBe
ms.date: 06/21/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: pjacobse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 5c8126322f85b317a9737978295ec0ebd2fd7cdc
ms.contentlocale: pt-br
ms.lasthandoff: 04/13/2018

---
# <a name="trace-an-item-or-raw-material"></a><span data-ttu-id="75984-103">Rastrear um item ou uma matéria-prima</span><span class="sxs-lookup"><span data-stu-id="75984-103">Trace an item or raw material</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="75984-104">Este procedimento demonstra como usar o rastreamento de itens para identificar onde itens ou matérias-primas foram usados ou estão sendo usados.</span><span class="sxs-lookup"><span data-stu-id="75984-104">This procedure demonstrates how to use item tracing to identify where items or raw materials have been used or are being used.</span></span> <span data-ttu-id="75984-105">Com esse procedimento, você pode identificar um item, rastreá-lo até sua origem e encaminhá-lo por meio da produção e venda do produto finalizado.</span><span class="sxs-lookup"><span data-stu-id="75984-105">With this procedure, you can identify an item, trace it back to the source, and then trace forward through the production and sale of the finished product.</span></span> <span data-ttu-id="75984-106">O processo pode ser usado para investigar os clientes impactados, as ordens de venda afetadas etc.</span><span class="sxs-lookup"><span data-stu-id="75984-106">The process can be used to investigate the customers impacted, the sales orders affected, and more.</span></span> <span data-ttu-id="75984-107">Este procedimento usa a empresa de dados de demonstração USP2.</span><span class="sxs-lookup"><span data-stu-id="75984-107">This procedure uses demo data company USP2.</span></span>


## <a name="trace-an-item-backwards-using-a-known-batch-number"></a><span data-ttu-id="75984-108">Rastrear um item regressivamente usando um número de lote conhecido</span><span class="sxs-lookup"><span data-stu-id="75984-108">Trace an item backwards using a known batch number</span></span>
1. <span data-ttu-id="75984-109">Vá para Gerenciamento de estoque > Consultas e relatórios > Dimensões de rastreamento > Rastreamento de item.</span><span class="sxs-lookup"><span data-stu-id="75984-109">Go to Inventory management > Inquiries and reports > Tracking dimensions > Item tracing.</span></span>
2. <span data-ttu-id="75984-110">No campo Número do item, selecione P9100.</span><span class="sxs-lookup"><span data-stu-id="75984-110">In the Item number field, select P9100.</span></span>
3. <span data-ttu-id="75984-111">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="75984-111">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="75984-112">No campo Avançar ou recuar, selecione 'Recuar'.</span><span class="sxs-lookup"><span data-stu-id="75984-112">In the Forward or backward field, select 'Backward'.</span></span>
5. <span data-ttu-id="75984-113">No campo Número do lote, selecione as-12-344-01.</span><span class="sxs-lookup"><span data-stu-id="75984-113">In the Batch number field, select as-12-344-01.</span></span>
6. <span data-ttu-id="75984-114">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="75984-114">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="75984-115">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="75984-115">Click OK.</span></span>

## <a name="identify-an-item-trace-it-forward-and-make-an-analysis"></a><span data-ttu-id="75984-116">Identificar um item, rastreá-lo progressivamente e fazer uma análise</span><span class="sxs-lookup"><span data-stu-id="75984-116">Identify an item, trace it forward, and make an analysis</span></span>
    * <span data-ttu-id="75984-117">O nó superior da árvore representa a quantidade disponível do item e lote selecionados.</span><span class="sxs-lookup"><span data-stu-id="75984-117">The top node of the tree represents the on hand quantity of the selected item and batch.</span></span> <span data-ttu-id="75984-118">Você precisa expandir os nós da árvore para localizar o item onde o rastreamento deve ser executado.</span><span class="sxs-lookup"><span data-stu-id="75984-118">You need to expand the nodes of the tree to find the item that the forward trace should be executed on.</span></span>   
1. <span data-ttu-id="75984-119">Na árvore, expanda "os nós descrito abaixo e selecione o último nó".</span><span class="sxs-lookup"><span data-stu-id="75984-119">In the tree, expand 'the nodes described below, and then select the last node'.</span></span>
    * <span data-ttu-id="75984-120">Expanda: 'P9100 / 1 / 10 / como-12-344-01 ● 2 keg ● 7.00 gal  \P9100 ● Separado ● Ordem de venda 000072 ● 12/22/2015 ● -1 keg ● -4.00 gal ● Local=1, Depósito=10, Número do lote=as-12-344-01  \P9100 ● Produção B-000050 ● 12/9/2015● 7 keg ● 27.00 gal ● Local=1,Depósito=10, Número de lote=as-12-344-01 ● Coprodutos: P9101' e então selecione esse nó.</span><span class="sxs-lookup"><span data-stu-id="75984-120">Expand: 'P9100 / 1 / 10 / as-12-344-01 ● 2 keg ● 7.00 gal  \P9100 ● Picked ● Sales order 000072 ● 12/22/2015  ● -1 keg ● -4.00 gal ● Site=1, Warehouse=10, Batch number=as-12-344-01  \P9100 ● Production B-000050 ● 12/9/2015● 7 keg ● 27.00 gal ● Site=1,Warehouse=10,Batch number=as-12-344-01 ● Co-products: P9101' and then select that node.</span></span>     
2. <span data-ttu-id="75984-121">Na árvore, expanda "o nó descrito abaixo e selecione aquele nó".</span><span class="sxs-lookup"><span data-stu-id="75984-121">In the tree, expand 'the node described below and then select that node'.</span></span>
    * <span data-ttu-id="75984-122">A partir do nó que você acabou de selecionar, expanda 'M9103 ● Linha de produção B-000050 ● 12/9/2015 ● -160.00 libras ● Tamanho=70, Cor=OK, Local=1, Depósito=10, Número de lote=App01' e então selecione o nó.</span><span class="sxs-lookup"><span data-stu-id="75984-122">Starting from the node that you’ve just selected,  expand 'M9103 ● Production line B-000050 ● 12/9/2015  ● -160.00 lb ● Size=70, Color=OK, Site=1, Warehouse=10, Batch number=App01' and then select that node.</span></span>  
3. <span data-ttu-id="75984-123">Clique em Rastreamento a partir do nó.</span><span class="sxs-lookup"><span data-stu-id="75984-123">Click Trace from node.</span></span>
4. <span data-ttu-id="75984-124">Clique em Encaminhar.</span><span class="sxs-lookup"><span data-stu-id="75984-124">Click Forward.</span></span>
5. <span data-ttu-id="75984-125">No Painel de Ação, clique em Rastreamento.</span><span class="sxs-lookup"><span data-stu-id="75984-125">On the Action Pane, click Tracing.</span></span>
    * <span data-ttu-id="75984-126">Há várias opções de rastreamento que fornecem informações sobre os clientes afetados por item que está sendo rastreado, e para ordens de venda relacionadas ao item que foram e não foram enviadas.</span><span class="sxs-lookup"><span data-stu-id="75984-126">There are several tracing options which provide information about the customers impacted by the item that you’re tracing, and the sales orders related to the item which have and haven’t been shipped.</span></span>   
6. <span data-ttu-id="75984-127">Clique em Clientes.</span><span class="sxs-lookup"><span data-stu-id="75984-127">Click Customers.</span></span>
7. <span data-ttu-id="75984-128">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="75984-128">Close the page.</span></span>
8. <span data-ttu-id="75984-129">No Painel de Ação, clique em Rastreamento.</span><span class="sxs-lookup"><span data-stu-id="75984-129">On the Action Pane, click Tracing.</span></span>
9. <span data-ttu-id="75984-130">Clique em Ordens de venda remetidas.</span><span class="sxs-lookup"><span data-stu-id="75984-130">Click Shipped sales orders.</span></span>
10. <span data-ttu-id="75984-131">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="75984-131">Close the page.</span></span>

