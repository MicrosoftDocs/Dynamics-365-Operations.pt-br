--- 
title: " Criar dimensões financeiras para canais de varejo e configurar valores de dimensão em lojas"
description: "Este procedimento mostra a criação de uma dimensão financeira de canal de varejo com os valores de dimensão e as etapas para configurar valores de dimensão financeira em lojas de varejo."
author: jashanno
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: ceea24519d641c676521771cee274feb64ca7783
ms.openlocfilehash: 9c46be996b2c002b05b9ee10329ff266e1a077c1
ms.contentlocale: pt-br
ms.lasthandoff: 01/19/2018

---
# <a name="create-financial-dimensions-for-retail-channels-and-configure-dimension-values-on-stores"></a><span data-ttu-id="09aa6-103"> Criar dimensões financeiras para canais de varejo e configurar valores de dimensão em lojas</span><span class="sxs-lookup"><span data-stu-id="09aa6-103">Create financial dimensions for Retail channels and configure dimension values on stores</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="09aa6-104">Este procedimento mostra a criação de uma dimensão financeira de canal de varejo com os valores de dimensão e as etapas para configurar valores de dimensão financeira em lojas de varejo.</span><span class="sxs-lookup"><span data-stu-id="09aa6-104">This procedure walks through creating a retail channel financial dimension with dimension values and steps to configure financial dimension values on retail stores.</span></span> <span data-ttu-id="09aa6-105">O tópico não inclui outras etapas relacionadas, como a criação de conjuntos de dimensões e de estruturas de conta.</span><span class="sxs-lookup"><span data-stu-id="09aa6-105">The topic does not include other related steps, such as creating dimension sets and account structures.</span></span> <span data-ttu-id="09aa6-106">Este procedimento usa a empresa USRT nos dados de demonstração.</span><span class="sxs-lookup"><span data-stu-id="09aa6-106">This procedure uses the USRT company in demo data.</span></span>

1. <span data-ttu-id="09aa6-107">Vá para Contabilidade > Plano de contas > Dimensões > Dimensões financeiras.</span><span class="sxs-lookup"><span data-stu-id="09aa6-107">Go to General ledger > Chart of accounts > Dimensions > Financial dimensions.</span></span>
2. <span data-ttu-id="09aa6-108">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="09aa6-108">Click New.</span></span>
3. <span data-ttu-id="09aa6-109">No campo Usar valores de, selecione 'Canais de varejo'.</span><span class="sxs-lookup"><span data-stu-id="09aa6-109">In the Use values from field, select 'Retail channels'.</span></span>
4. <span data-ttu-id="09aa6-110">No campo Nome da dimensão, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="09aa6-110">In the Dimension name field, type a value.</span></span>
5. <span data-ttu-id="09aa6-111">Clique em Ativar.</span><span class="sxs-lookup"><span data-stu-id="09aa6-111">Click Activate.</span></span>
6. <span data-ttu-id="09aa6-112">Clique em Fechar.</span><span class="sxs-lookup"><span data-stu-id="09aa6-112">Click Close.</span></span>
7. <span data-ttu-id="09aa6-113">Clique em Ativar.</span><span class="sxs-lookup"><span data-stu-id="09aa6-113">Click Activate.</span></span>
8. <span data-ttu-id="09aa6-114">Clique em Valores de dimensão.</span><span class="sxs-lookup"><span data-stu-id="09aa6-114">Click Dimension values.</span></span>
9. <span data-ttu-id="09aa6-115">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="09aa6-115">Close the page.</span></span>
10. <span data-ttu-id="09aa6-116">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="09aa6-116">Click Save.</span></span>
11. <span data-ttu-id="09aa6-117">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="09aa6-117">Close the page.</span></span>
12. <span data-ttu-id="09aa6-118">Vá para Varejo e comércio > Canais > Lojas de varejo > Todas as lojas de varejo.</span><span class="sxs-lookup"><span data-stu-id="09aa6-118">Go to Retail and commerce > Channels > Retail stores > All retail stores.</span></span>
13. <span data-ttu-id="09aa6-119">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="09aa6-119">In the list, click the link in the selected row.</span></span>
14. <span data-ttu-id="09aa6-120">Ative a expansão da seção Dimensões financeiras.</span><span class="sxs-lookup"><span data-stu-id="09aa6-120">Toggle the expansion of the Financial dimensions section.</span></span>
15. <span data-ttu-id="09aa6-121">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="09aa6-121">Click Edit.</span></span>
16. <span data-ttu-id="09aa6-122">No campo Retailchannel, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="09aa6-122">In the Retailchannel field, click the drop-down button to open the lookup.</span></span>
17. <span data-ttu-id="09aa6-123">Na lista, localize e selecione o valor de dimensão para o armazenamento que está sendo atualizado.</span><span class="sxs-lookup"><span data-stu-id="09aa6-123">In the list, find and select the dimension value for the store being updated.</span></span>
18. <span data-ttu-id="09aa6-124">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="09aa6-124">In the list, click the link in the selected row.</span></span>
19. <span data-ttu-id="09aa6-125">No campo Centro de Custo, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="09aa6-125">In the CostCenter field, click the drop-down button to open the lookup.</span></span>
20. <span data-ttu-id="09aa6-126">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="09aa6-126">In the list, find and select the desired record.</span></span>
21. <span data-ttu-id="09aa6-127">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="09aa6-127">In the list, click the link in the selected row.</span></span>
22. <span data-ttu-id="09aa6-128">No campo Departamento, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="09aa6-128">In the Department field, click the drop-down button to open the lookup.</span></span>
23. <span data-ttu-id="09aa6-129">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="09aa6-129">In the list, find and select the desired record.</span></span>
24. <span data-ttu-id="09aa6-130">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="09aa6-130">In the list, click the link in the selected row.</span></span>
25. <span data-ttu-id="09aa6-131">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="09aa6-131">Click Save.</span></span>


