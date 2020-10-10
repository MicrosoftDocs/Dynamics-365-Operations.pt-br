---
title: Tipo de severidade do ativo
description: O tópico explica os tipos de severidade de ativos no Asset Management.
author: josaw1
manager: tfehr
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetCriticality, EntAssetObjectCriticality
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4b7d6e3dea1b3c1ef47490df678f639c036cdd5c
ms.sourcegitcommit: c986d5234b81d31cc6d054298be6f6ec92c1754c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/25/2020
ms.locfileid: "3889808"
---
# <a name="asset-criticality-types"></a><span data-ttu-id="c612a-103">Tipo de severidade do ativo</span><span class="sxs-lookup"><span data-stu-id="c612a-103">Asset criticality types</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="c612a-104">O tópico explica os tipos de severidade de ativos no Asset Management.</span><span class="sxs-lookup"><span data-stu-id="c612a-104">The topic explains asset criticality types in Asset Management.</span></span> <span data-ttu-id="c612a-105">A severidade de ativos está relacionada aos ativos e é transferida para as ordens de serviço.</span><span class="sxs-lookup"><span data-stu-id="c612a-105">Asset criticality is related to assets and is transferred to work orders.</span></span> <span data-ttu-id="c612a-106">Não pode ser alterada em uma ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="c612a-106">It can't be changed on a work order.</span></span> <span data-ttu-id="c612a-107">A severidade de ativos é usada para calcular a severidade da ordem de serviço durante seu agendamento.</span><span class="sxs-lookup"><span data-stu-id="c612a-107">Asset criticality is used to calculate work order criticality during work order scheduling.</span></span> <span data-ttu-id="c612a-108">Em outras palavras, é usada para calcular até onde um trabalho de manutenção em um ativo afeta a agenda de produção e a produtividade da empresa.</span><span class="sxs-lookup"><span data-stu-id="c612a-108">In other words, it's used to calculate the extent to which a maintenance job on an asset affects the production schedule and productivity in your company.</span></span> <span data-ttu-id="c612a-109">Para obter mais informações sobre a instalação relacionadas ao cálculo de pontuações de classificação para o agendamento da ordem de serviço, consulte [Parâmetros do Asset Management](../setup-for-objects/enterprise-asset-management-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="c612a-109">For more information about the setup that is related to the calculation of rating scores for work order scheduling, see [Asset Management parameters](../setup-for-objects/enterprise-asset-management-parameters.md).</span></span>

<span data-ttu-id="c612a-110">Para configurar a severidade, primeiro você cria os tipos de severidade que devem ser usados na configuração do ativo.</span><span class="sxs-lookup"><span data-stu-id="c612a-110">To set up criticality, you first create the criticality types that should be used in the asset setup.</span></span> <span data-ttu-id="c612a-111">Então, você configura as severidades de ativo.</span><span class="sxs-lookup"><span data-stu-id="c612a-111">You then set up asset criticalities.</span></span>

## <a name="set-up-criticality-types"></a><span data-ttu-id="c612a-112">Configurar tipos de severidade</span><span class="sxs-lookup"><span data-stu-id="c612a-112">Set up criticality types</span></span>

1. <span data-ttu-id="c612a-113">Selecione **Gerenciamento de ativos** \> **Configuração** \> **Ativos** \> **Tipos de severidade**.</span><span class="sxs-lookup"><span data-stu-id="c612a-113">Select **Asset management** \> **Setup** \> **Assets** \> **Criticality types**.</span></span>
2. <span data-ttu-id="c612a-114">Selecione **Novo** para criar um registro.</span><span class="sxs-lookup"><span data-stu-id="c612a-114">Select **New** to create a record.</span></span>
3. <span data-ttu-id="c612a-115">No campo **Severidade** , insira um número que indique a severidade.</span><span class="sxs-lookup"><span data-stu-id="c612a-115">In the **Criticality** field, enter a number that indicates the criticality.</span></span>
4. <span data-ttu-id="c612a-116">No campo **Nome**, insira um nome para o tipo de severidade.</span><span class="sxs-lookup"><span data-stu-id="c612a-116">In the **Name** field, enter a name for the criticality type.</span></span>
5. <span data-ttu-id="c612a-117">No campo **Fator**, insira um fator.</span><span class="sxs-lookup"><span data-stu-id="c612a-117">In the **Factor** field, enter a factor.</span></span> <span data-ttu-id="c612a-118">Esse fator é usado no cálculo de agendamento da ordem de serviço para determinar o registro de severidade que deve ser usado.</span><span class="sxs-lookup"><span data-stu-id="c612a-118">This factor is used during the calculation of work order scheduling to determine the criticality record that should be used.</span></span> <span data-ttu-id="c612a-119">(O registro com o fator mais alto será sempre usado). Essa configuração será relevante se, conforme mostrado na ilustração, as linhas de severidade forem criadas com o mesmo valor de severidade.</span><span class="sxs-lookup"><span data-stu-id="c612a-119">(The record that has the highest factor is always used.) This setting is relevant if, as shown in the following illustration, criticality lines are created that have the same criticality value.</span></span>

    ![Página Tipos de severidade](media/23-setup-for-objects.png)

## <a name="set-up-asset-criticalities"></a><span data-ttu-id="c612a-121">Configurar severidades de ativo</span><span class="sxs-lookup"><span data-stu-id="c612a-121">Set up asset criticalities</span></span>

1. <span data-ttu-id="c612a-122">Selecione **Gerenciamento de ativos** \> **Configuração** \> **Severidades de ativo**.</span><span class="sxs-lookup"><span data-stu-id="c612a-122">Select **Asset management** \> **Setup** \> **Asset criticalities**.</span></span>
2. <span data-ttu-id="c612a-123">Selecione **Novo** para criar um registro.</span><span class="sxs-lookup"><span data-stu-id="c612a-123">Select **New** to create a record.</span></span>
3. <span data-ttu-id="c612a-124">Dependendo do grau de detalhamento desejado para a severidade do ativo, faça seleções relevantes nos campos **Local funcional**, **Tipo de ativo**, **Fabricante**, **Modelo**, **Ativo**, **Categoria do tipo de trabalho**, **Tipo de trabalho**, **Variação do tipo de trabalho** e **Necessidade de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="c612a-124">Depending on the required level of detail for asset criticality, make relevant selections in the **Functional location**, **Asset type**, **Manufacturer**, **Model**, **Asset**, **Job type category**, **Job type**, **Job type variant**, and **Job requirement** fields.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c612a-125">Quando uma severidade de ativo é selecionada, o Asset Management examina todos os registros de severidade de ativo para verificar a existência uma possível correspondência.</span><span class="sxs-lookup"><span data-stu-id="c612a-125">When an asset criticality is selected, Asset Management goes through all asset criticality records to check for a possible match.</span></span> <span data-ttu-id="c612a-126">Ele sempre verifica a combinação mais específica primeiro.</span><span class="sxs-lookup"><span data-stu-id="c612a-126">It always checks the most specific combination first.</span></span> <span data-ttu-id="c612a-127">Ou seja, o Asset Management primeiro verifica **Necessidade de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="c612a-127">In other words, Asset Management first checks **Job requirement**.</span></span> <span data-ttu-id="c612a-128">Se nenhuma correspondência for encontrada, verifica **Variação de tipo de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="c612a-128">If no match is found, it checks **Job type variant**.</span></span> <span data-ttu-id="c612a-129">Se nenhuma correspondência for encontrada, verifica **Tipo de trabalho** e assim em diante.</span><span class="sxs-lookup"><span data-stu-id="c612a-129">If no match is found, it checks **Job type**, and so on.</span></span> <span data-ttu-id="c612a-130">Como você pode perceber no layout da página, esse comportamento significa que, para encontrar a combinação mais específica, o Asset Management verifica cada registro da direita para a esquerda em busca de uma correspondência.</span><span class="sxs-lookup"><span data-stu-id="c612a-130">As you can see in the layout of the page, this behavior means that, to find the most specific combination, Asset Management checks each record from right to left for a match.</span></span> <span data-ttu-id="c612a-131">Se nenhuma correspondência for encontrada, o registro "padrão" que não possui nenhuma seleção é usado.</span><span class="sxs-lookup"><span data-stu-id="c612a-131">If no match is found, the "default" record that has no selections is used.</span></span>

4. <span data-ttu-id="c612a-132">No campo **Severidade**, selecione um dos valores de severidade que você criou no no procedimento anterior.</span><span class="sxs-lookup"><span data-stu-id="c612a-132">In the **Criticality** field, select one of the criticality values that you created in the previous procedure.</span></span>

### <a name="notes-about-criticality-setup"></a><span data-ttu-id="c612a-133">Observações sobre a configuração de severidade</span><span class="sxs-lookup"><span data-stu-id="c612a-133">Notes about criticality setup</span></span>

- <span data-ttu-id="c612a-134">Se você alterar a severidade de um ativo nessa configuração depois de já tê-la usado em uma ordem de serviço, a severidade da ordem de serviço não será atualizada de forma correspondente.</span><span class="sxs-lookup"><span data-stu-id="c612a-134">If you change an asset criticality in this setup after you've already used it on a work order, the criticality on the work order isn't updated accordingly.</span></span>
- <span data-ttu-id="c612a-135">A severidade em uma ordem de serviço é recalculada sempre que uma linha da ordem de serviço é adicionada ou excluída.</span><span class="sxs-lookup"><span data-stu-id="c612a-135">The criticality on a work order is recalculated every time that a work order line is added to or deleted from the work order.</span></span>
- <span data-ttu-id="c612a-136">Se uma ordem de serviço contiver vários trabalhos de ordem de serviço, a severidade mais alta, de acordo com o campo **Fator** na página **Tipos de severidade**, sempre será usada na ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="c612a-136">If a work order contains several work order jobs, the highest criticality, according to the **Factor** field on the **Criticality types** page, is always used on the work order.</span></span>
- <span data-ttu-id="c612a-137">Geralmente, a severidade do ativo pode mudar em um período.</span><span class="sxs-lookup"><span data-stu-id="c612a-137">Generally, asset criticality can change over a period.</span></span> <span data-ttu-id="c612a-138">A severidade pode ser afetada pela compra de novo equipamento, restaurações e assim em diante.</span><span class="sxs-lookup"><span data-stu-id="c612a-138">Criticality can be affected by the purchase of new equipment, refurbishments, and so on.</span></span> <span data-ttu-id="c612a-139">Considere a reavaliação das severidades do seu ativo em intervalos regulares (por exemplo, uma vez por ano em anos alternados) para garantir que as definições de severidade correspondam à sua configuração de produção atual.</span><span class="sxs-lookup"><span data-stu-id="c612a-139">Consider reevaluating your asset criticalities at regular intervals (for example, once per year or every other year) to make sure that your criticality definitions match your current production setup.</span></span>
