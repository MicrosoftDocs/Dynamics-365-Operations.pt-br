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
ms.search.form: CAMAXGeneralLedgerEntryProviderConfiguration
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7246d42b42404f0f1215bbf14b8ad168fe12691c
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4990708"
---
# <a name="manage-a-data-source-for-the-cost-accounting-ledger"></a><span data-ttu-id="7653f-103">Gerenciar uma fonte de dados para o razão de contabilização de custos</span><span class="sxs-lookup"><span data-stu-id="7653f-103">Manage a data source for the cost accounting ledger</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="7653f-104">Use este procedimento para gerenciar a fonte de dados da contabilidade para um razão de contabilização de custos.</span><span class="sxs-lookup"><span data-stu-id="7653f-104">Use this procedure to manage the general ledger data source for a cost accounting ledger.</span></span> <span data-ttu-id="7653f-105">Antes de concluir esta tarefa, certifique-se de que executou os guias de tarefas "Criar um razão de contabilização de custos" e "Definir unidades de controle de custos".</span><span class="sxs-lookup"><span data-stu-id="7653f-105">Before you complete this task, make sure that you play the "Create a cost accounting ledger" and "Define cost control units" task guides.</span></span> <span data-ttu-id="7653f-106">Esta gravação usa os dados da empresa de demonstração USP2.</span><span class="sxs-lookup"><span data-stu-id="7653f-106">This recording uses the USP2 demo data company.</span></span>

1. <span data-ttu-id="7653f-107">Vá para Contabilização de custos > Configuração do razão > Razões de contabilização de custos.</span><span class="sxs-lookup"><span data-stu-id="7653f-107">Go to Cost accounting > Ledger setup > Cost accounting ledgers.</span></span>
2. <span data-ttu-id="7653f-108">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="7653f-108">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="7653f-109">Clique em Versões reais.</span><span class="sxs-lookup"><span data-stu-id="7653f-109">Click Actual versions.</span></span>
4. <span data-ttu-id="7653f-110">No Painel de Ação, clique em Gerenciar.</span><span class="sxs-lookup"><span data-stu-id="7653f-110">On the Action Pane, click Manage.</span></span>
5. <span data-ttu-id="7653f-111">Clique em Contabilidade.</span><span class="sxs-lookup"><span data-stu-id="7653f-111">Click General ledger.</span></span>
6. <span data-ttu-id="7653f-112">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="7653f-112">Click New.</span></span>
7. <span data-ttu-id="7653f-113">No campo Nome, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="7653f-113">In the Name field, type a value.</span></span>
8. <span data-ttu-id="7653f-114">No campo Provedor de dados, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="7653f-114">In the Data provider field, enter or select a value.</span></span>
    * <span data-ttu-id="7653f-115">Para este exemplo, selecione Dynamics 365 Finance - Entradas da contabilidade.</span><span class="sxs-lookup"><span data-stu-id="7653f-115">For this example, select Dynamics 365 Finance - General ledger entries.</span></span>  
9. <span data-ttu-id="7653f-116">No campo Dimensão do elemento de custo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="7653f-116">In the Cost element dimension field, enter or select a value.</span></span>
    * <span data-ttu-id="7653f-117">Para este exemplo, selecione Elementos de custo.</span><span class="sxs-lookup"><span data-stu-id="7653f-117">For this example, select Cost elements.</span></span>  
10. <span data-ttu-id="7653f-118">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="7653f-118">Click Save.</span></span>
11. <span data-ttu-id="7653f-119">Clique em Configurar provedor de dados.</span><span class="sxs-lookup"><span data-stu-id="7653f-119">Click Configure data provider.</span></span>
12. <span data-ttu-id="7653f-120">No campo Entidade legal, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="7653f-120">In the Legal entity field, enter or select a value.</span></span>
    * <span data-ttu-id="7653f-121">Para este exemplo, selecione USP2.</span><span class="sxs-lookup"><span data-stu-id="7653f-121">For this example, select USP2.</span></span>  
13. <span data-ttu-id="7653f-122">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="7653f-122">Click New.</span></span>
14. <span data-ttu-id="7653f-123">No campo Nível de lançamento, selecione Atual.</span><span class="sxs-lookup"><span data-stu-id="7653f-123">In the Posting layer field, select Current.</span></span>
15. <span data-ttu-id="7653f-124">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="7653f-124">Click OK.</span></span>

