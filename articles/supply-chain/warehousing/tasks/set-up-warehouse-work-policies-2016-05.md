--- 
title: "Configurar políticas de trabalho de depósito "
description: "Os processos de depósito nem sempre incluem o trabalho do depósito."
author: johanhoffmann
manager: AnnBe
ms.date: 06/23/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: fe237543770fd05198b46cc7fc72b21926177807
ms.contentlocale: pt-br
ms.lasthandoff: 04/13/2018

---
# <a name="set-up-warehouse-work-policies"></a><span data-ttu-id="d707f-103">Configurar políticas de trabalho de depósito </span><span class="sxs-lookup"><span data-stu-id="d707f-103">Set up warehouse work policies</span></span> 

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="d707f-104">Os processos de depósito nem sempre incluem o trabalho do depósito.</span><span class="sxs-lookup"><span data-stu-id="d707f-104">Warehouse processes don’t always include warehouse work.</span></span> <span data-ttu-id="d707f-105">Ao definir uma diretiva de trabalho, você pode impedir a criação de trabalho para a separação de matéria-prima e o separar as mercadorias concluídas para um conjunto de produtos em locais específicos.</span><span class="sxs-lookup"><span data-stu-id="d707f-105">By defining a work policy, you can prevent the creation of work for raw material picking and put-away of finished goods for a set of products at specific locations.</span></span> <span data-ttu-id="d707f-106">A empresa de dados demo USMF foi usada para criar este registro.</span><span class="sxs-lookup"><span data-stu-id="d707f-106">The USMF demo data company was used to create this recording.</span></span> <span data-ttu-id="d707f-107">Essa guia da tarefa requer a aplicação 7.0.1 do Dynamics AX ou posterior.</span><span class="sxs-lookup"><span data-stu-id="d707f-107">This task guide requires Dynamics AX application 7.0.1 or later.</span></span>

1. <span data-ttu-id="d707f-108">Vá para Gerenciamento de depósito > Configuração > Políticas de trabalho.</span><span class="sxs-lookup"><span data-stu-id="d707f-108">Go to Warehouse management > Setup > Work > Work policies.</span></span>
2. <span data-ttu-id="d707f-109">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="d707f-109">Click New.</span></span>
3. <span data-ttu-id="d707f-110">No campo Nome de política de trabalho, digite "Sem trabalhos ausentes".</span><span class="sxs-lookup"><span data-stu-id="d707f-110">In the Work policy name field, type 'No put-away work'.</span></span>
4. <span data-ttu-id="d707f-111">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="d707f-111">Click Save.</span></span>
5. <span data-ttu-id="d707f-112">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="d707f-112">Click Add.</span></span>
6. <span data-ttu-id="d707f-113">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="d707f-113">In the list, mark the selected row.</span></span>
7. <span data-ttu-id="d707f-114">No campo Tipo de ordem de trabalho, selecione as mercadorias “Concluiu mercadorias dadas”.</span><span class="sxs-lookup"><span data-stu-id="d707f-114">In the Work order type field, select 'Finished goods put away'.</span></span>
8. <span data-ttu-id="d707f-115">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="d707f-115">Click Add.</span></span>
9. <span data-ttu-id="d707f-116">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="d707f-116">In the list, mark the selected row.</span></span>
10. <span data-ttu-id="d707f-117">No campo Tipo de ordem de trabalho, selecione "Coproduto e subproduto cedido".</span><span class="sxs-lookup"><span data-stu-id="d707f-117">In the Work order type field, select 'Co-product and by-product put away'.</span></span>
11. <span data-ttu-id="d707f-118">Expanda a seção Localizações de estoque.</span><span class="sxs-lookup"><span data-stu-id="d707f-118">Expand the Inventory locations section.</span></span>
12. <span data-ttu-id="d707f-119">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="d707f-119">Click Add.</span></span>
13. <span data-ttu-id="d707f-120">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="d707f-120">In the list, mark the selected row.</span></span>
14. <span data-ttu-id="d707f-121">Na lista Depósito, insira "51".</span><span class="sxs-lookup"><span data-stu-id="d707f-121">In the Warehouse list, enter '51'.</span></span>
15. <span data-ttu-id="d707f-122">No campo Local, insira ou selecione "001".</span><span class="sxs-lookup"><span data-stu-id="d707f-122">In the Location field, enter or select '001'.</span></span>
16. <span data-ttu-id="d707f-123">Expanda a seção Produtos.</span><span class="sxs-lookup"><span data-stu-id="d707f-123">Expand the Products section.</span></span>
17. <span data-ttu-id="d707f-124">No campo Seleção do produto, selecione "Selecionado".</span><span class="sxs-lookup"><span data-stu-id="d707f-124">In the Product selection field, select 'Selected'.</span></span>
18. <span data-ttu-id="d707f-125">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="d707f-125">Click Add.</span></span>
19. <span data-ttu-id="d707f-126">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="d707f-126">In the list, mark the selected row.</span></span>
20. <span data-ttu-id="d707f-127">No campo Número do item, insira ou selecione "L0101".</span><span class="sxs-lookup"><span data-stu-id="d707f-127">In the Item number field, enter or select 'L0101'.</span></span>
21. <span data-ttu-id="d707f-128">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="d707f-128">Click Save.</span></span>


