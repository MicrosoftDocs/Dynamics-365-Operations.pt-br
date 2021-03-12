---
title: Criar dimensões financeiras para canais de varejo e configurar valores de dimensão em lojas
description: Este procedimento mostra como criar uma dimensão financeira de canal de comércio com os valores de dimensão e as etapas para configurar valores de dimensão financeira em lojas.
author: jashanno
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 86fc9c9a400bee1280b32f10b1e8f55e581e1984
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4964736"
---
# <a name="create-financial-dimensions-for-retail-channels-and-configure-dimension-values-on-stores"></a><span data-ttu-id="815f8-103">Criar dimensões financeiras para canais de varejo e configurar valores de dimensão em lojas</span><span class="sxs-lookup"><span data-stu-id="815f8-103">Create financial dimensions for retail channels and configure dimension values on stores</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="815f8-104">Este procedimento mostra como criar uma dimensão financeira de canal de comércio com os valores de dimensão e as etapas para configurar valores de dimensão financeira em lojas.</span><span class="sxs-lookup"><span data-stu-id="815f8-104">This procedure walks through creating a commerce channel financial dimension with dimension values and steps to configure financial dimension values on stores.</span></span> <span data-ttu-id="815f8-105">O tópico não inclui outras etapas relacionadas, como a criação de conjuntos de dimensões e de estruturas de conta.</span><span class="sxs-lookup"><span data-stu-id="815f8-105">The topic does not include other related steps, such as creating dimension sets and account structures.</span></span> <span data-ttu-id="815f8-106">Este procedimento usa a empresa USRT nos dados de demonstração.</span><span class="sxs-lookup"><span data-stu-id="815f8-106">This procedure uses the USRT company in demo data.</span></span>

1. <span data-ttu-id="815f8-107">Vá para Contabilidade > Plano de contas > Dimensões > Dimensões financeiras.</span><span class="sxs-lookup"><span data-stu-id="815f8-107">Go to General ledger > Chart of accounts > Dimensions > Financial dimensions.</span></span>
2. <span data-ttu-id="815f8-108">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="815f8-108">Click New.</span></span>
3. <span data-ttu-id="815f8-109">No campo Usar valores de, selecione 'Canais de comércio'.</span><span class="sxs-lookup"><span data-stu-id="815f8-109">In the Use values from field, select 'Commerce channels'.</span></span>
4. <span data-ttu-id="815f8-110">No campo Nome da dimensão, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="815f8-110">In the Dimension name field, type a value.</span></span>
5. <span data-ttu-id="815f8-111">Clique em Ativar.</span><span class="sxs-lookup"><span data-stu-id="815f8-111">Click Activate.</span></span>
6. <span data-ttu-id="815f8-112">Clique em Fechar.</span><span class="sxs-lookup"><span data-stu-id="815f8-112">Click Close.</span></span>
7. <span data-ttu-id="815f8-113">Clique em Ativar.</span><span class="sxs-lookup"><span data-stu-id="815f8-113">Click Activate.</span></span>
8. <span data-ttu-id="815f8-114">Clique em Valores de dimensão.</span><span class="sxs-lookup"><span data-stu-id="815f8-114">Click Dimension values.</span></span>
9. <span data-ttu-id="815f8-115">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="815f8-115">Close the page.</span></span>
10. <span data-ttu-id="815f8-116">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="815f8-116">Click Save.</span></span>
11. <span data-ttu-id="815f8-117">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="815f8-117">Close the page.</span></span>
12. <span data-ttu-id="815f8-118">Vá para Retail e Commerce > Canais > Lojas > Todas as lojas.</span><span class="sxs-lookup"><span data-stu-id="815f8-118">Go to Retail and Commerce > Channels > Stores > All stores.</span></span>
13. <span data-ttu-id="815f8-119">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="815f8-119">In the list, click the link in the selected row.</span></span>
14. <span data-ttu-id="815f8-120">Ative a expansão da seção Dimensões financeiras.</span><span class="sxs-lookup"><span data-stu-id="815f8-120">Toggle the expansion of the Financial dimensions section.</span></span>
15. <span data-ttu-id="815f8-121">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="815f8-121">Click Edit.</span></span>
16. <span data-ttu-id="815f8-122">No campo Canal de comércio, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="815f8-122">In the Commerce channel field, click the drop-down button to open the lookup.</span></span>
17. <span data-ttu-id="815f8-123">Na lista, localize e selecione o valor de dimensão para o armazenamento que está sendo atualizado.</span><span class="sxs-lookup"><span data-stu-id="815f8-123">In the list, find and select the dimension value for the store being updated.</span></span>
18. <span data-ttu-id="815f8-124">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="815f8-124">In the list, click the link in the selected row.</span></span>
19. <span data-ttu-id="815f8-125">No campo Centro de Custo, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="815f8-125">In the CostCenter field, click the drop-down button to open the lookup.</span></span>
20. <span data-ttu-id="815f8-126">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="815f8-126">In the list, find and select the desired record.</span></span>
21. <span data-ttu-id="815f8-127">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="815f8-127">In the list, click the link in the selected row.</span></span>
22. <span data-ttu-id="815f8-128">No campo Departamento, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="815f8-128">In the Department field, click the drop-down button to open the lookup.</span></span>
23. <span data-ttu-id="815f8-129">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="815f8-129">In the list, find and select the desired record.</span></span>
24. <span data-ttu-id="815f8-130">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="815f8-130">In the list, click the link in the selected row.</span></span>
25. <span data-ttu-id="815f8-131">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="815f8-131">Click Save.</span></span>

