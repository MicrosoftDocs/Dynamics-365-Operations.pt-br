---
title: Gerenciar uma fonte de dados para o razão de contabilização de custos
description: Use este procedimento para gerenciar a fonte de dados da contabilidade para um razão de contabilização de custos.
author: ShylaThompson
manager: AnnBe
ms.date: 06/27/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 543c1cd4bbb35e51e17d5e0c7c588d87fbe3c106
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2187696"
---
# <a name="manage-a-data-source-for-the-cost-accounting-ledger"></a><span data-ttu-id="f6970-103">Gerenciar uma fonte de dados para o razão de contabilização de custos</span><span class="sxs-lookup"><span data-stu-id="f6970-103">Manage a data source for the cost accounting ledger</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="f6970-104">Use este procedimento para gerenciar a fonte de dados da contabilidade para um razão de contabilização de custos.</span><span class="sxs-lookup"><span data-stu-id="f6970-104">Use this procedure to manage the general ledger data source for a cost accounting ledger.</span></span> <span data-ttu-id="f6970-105">Antes de concluir esta tarefa, certifique-se de que executou os guias de tarefas "Criar um razão de contabilização de custos" e "Definir unidades de controle de custos".</span><span class="sxs-lookup"><span data-stu-id="f6970-105">Before you complete this task, make sure that you play the "Create a cost accounting ledger" and "Define cost control units" task guides.</span></span> <span data-ttu-id="f6970-106">Esta gravação usa os dados da empresa de demonstração USP2.</span><span class="sxs-lookup"><span data-stu-id="f6970-106">This recording uses the USP2 demo data company.</span></span>

1. <span data-ttu-id="f6970-107">Vá para Contabilização de custos > Configuração do razão > Razões de contabilização de custos.</span><span class="sxs-lookup"><span data-stu-id="f6970-107">Go to Cost accounting > Ledger setup > Cost accounting ledgers.</span></span>
2. <span data-ttu-id="f6970-108">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="f6970-108">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="f6970-109">Clique em Versões reais.</span><span class="sxs-lookup"><span data-stu-id="f6970-109">Click Actual versions.</span></span>
4. <span data-ttu-id="f6970-110">No Painel de Ação, clique em Gerenciar.</span><span class="sxs-lookup"><span data-stu-id="f6970-110">On the Action Pane, click Manage.</span></span>
5. <span data-ttu-id="f6970-111">Clique em Contabilidade.</span><span class="sxs-lookup"><span data-stu-id="f6970-111">Click General ledger.</span></span>
6. <span data-ttu-id="f6970-112">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="f6970-112">Click New.</span></span>
7. <span data-ttu-id="f6970-113">No campo Nome, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="f6970-113">In the Name field, type a value.</span></span>
8. <span data-ttu-id="f6970-114">No campo Provedor de dados, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="f6970-114">In the Data provider field, enter or select a value.</span></span>
    * <span data-ttu-id="f6970-115">Para este exemplo, selecione Dynamics 365 Finance - Entradas da contabilidade.</span><span class="sxs-lookup"><span data-stu-id="f6970-115">For this example, select Dynamics 365 Finance - General ledger entries.</span></span>  
9. <span data-ttu-id="f6970-116">No campo Dimensão do elemento de custo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="f6970-116">In the Cost element dimension field, enter or select a value.</span></span>
    * <span data-ttu-id="f6970-117">Para este exemplo, selecione Elementos de custo.</span><span class="sxs-lookup"><span data-stu-id="f6970-117">For this example, select Cost elements.</span></span>  
10. <span data-ttu-id="f6970-118">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="f6970-118">Click Save.</span></span>
11. <span data-ttu-id="f6970-119">Clique em Configurar provedor de dados.</span><span class="sxs-lookup"><span data-stu-id="f6970-119">Click Configure data provider.</span></span>
12. <span data-ttu-id="f6970-120">No campo Entidade legal, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="f6970-120">In the Legal entity field, enter or select a value.</span></span>
    * <span data-ttu-id="f6970-121">Para este exemplo, selecione USP2.</span><span class="sxs-lookup"><span data-stu-id="f6970-121">For this example, select USP2.</span></span>  
13. <span data-ttu-id="f6970-122">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="f6970-122">Click New.</span></span>
14. <span data-ttu-id="f6970-123">No campo Nível de lançamento, selecione Atual.</span><span class="sxs-lookup"><span data-stu-id="f6970-123">In the Posting layer field, select Current.</span></span>
15. <span data-ttu-id="f6970-124">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="f6970-124">Click OK.</span></span>

