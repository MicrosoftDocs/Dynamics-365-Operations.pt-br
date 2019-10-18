---
title: Definições de lançamento
description: Este artigo fornece informações sobre definições de lançamento, e como definir e vinculá-las. Para tipos de lançamento e documentos com suporte, você pode usar definições de lançamento em vez de perfis de lançamento para classificar as contas principais e as dimensões financeiras em entradas contábeis.
author: ShylaThompson
manager: AnnBe
ms.date: 09/03/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: JournalizingDefinition, JournalizingDefinitionTrans, LedgerParameters
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 15741
ms.assetid: 1495e7e0-2e39-464c-8da9-f55b1ca1c6bb
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 76bae24a975c922ea49ee2584e87cf43ccca61c7
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2176363"
---
# <a name="posting-definitions"></a><span data-ttu-id="40cf8-104">Definições de lançamento</span><span class="sxs-lookup"><span data-stu-id="40cf8-104">Posting definitions</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="40cf8-105">Este artigo fornece informações sobre definições de lançamento, e como definir e vinculá-las.</span><span class="sxs-lookup"><span data-stu-id="40cf8-105">This article provides information about posting definitions, and how to define and link them.</span></span>
<span data-ttu-id="40cf8-106">Para tipos de lançamento e documentos com suporte, você pode usar definições de lançamento em vez de perfis de lançamento para classificar as contas principais e as dimensões financeiras em entradas contábeis.</span><span class="sxs-lookup"><span data-stu-id="40cf8-106">For supported posting types and documents, you can use posting definitions instead of posting profiles to classify main accounts and financial dimensions on accounting entries.</span></span> <span data-ttu-id="40cf8-107">Você pode exibir os documentos e os tipos de lançamento com suporte na página **Definições de lançamento de transação**.</span><span class="sxs-lookup"><span data-stu-id="40cf8-107">You can view the supported documents and posting types on the **Transaction posting definitions** page.</span></span> 

<span data-ttu-id="40cf8-108">Para começar a usar definições de lançamento, selecione a opção**Usar definições de lançamento** na página **Parâmetros de contabilidade**.</span><span class="sxs-lookup"><span data-stu-id="40cf8-108">To start using posting definitions, select the **Use posting definitions** option on the **General ledger parameters** page.</span></span> <span data-ttu-id="40cf8-109">Mesmo quando você usa definições de lançamento, ainda deve definir perfis de lançamento para as entradas de origem e os tipos de lançamento e os documentos sem suporte.</span><span class="sxs-lookup"><span data-stu-id="40cf8-109">Even when you use posting definitions, you must still define posting profiles for the originating entries and non-supported posting types and documents.</span></span> 

<span data-ttu-id="40cf8-110">Você deve usar definições de lançamento para habilitar a contabilidade de ônus para ordens de compra e a contabilidade de pré-ônus para requisições de compra.</span><span class="sxs-lookup"><span data-stu-id="40cf8-110">You must use posting definitions in order to enable encumbrance accounting for purchase orders and pre-encumbrance accounting for purchase requisitions.</span></span>

## <a name="defining-posting-definitions"></a><span data-ttu-id="40cf8-111">Definições de lançamento</span><span class="sxs-lookup"><span data-stu-id="40cf8-111">Defining posting definitions</span></span>
<span data-ttu-id="40cf8-112">Use a página **Definições de lançamento** para especificar os critérios de correspondência e para definir as entradas que devem ser geradas quando ocorre uma correspondência.</span><span class="sxs-lookup"><span data-stu-id="40cf8-112">Use the **Posting definitions** page to specify the match criteria and define the entries that should be generated when a match occurs.</span></span> <span data-ttu-id="40cf8-113">Os critérios de correspondência são avaliados para as entradas de origem como distribuições contábeis.</span><span class="sxs-lookup"><span data-stu-id="40cf8-113">The match criteria are evaluated for the originating entries as accounting distributions.</span></span> 

<span data-ttu-id="40cf8-114">Na página **Definições de lançamento**, você também pode atribuir números de prioridade a linhas de entrada para controlar a ordem em que as linhas são avaliadas.</span><span class="sxs-lookup"><span data-stu-id="40cf8-114">On the **Posting definitions** page, you can also assign priority numbers to entry lines to control the order in which the lines are evaluated.</span></span> <span data-ttu-id="40cf8-115">As linhas com o número de menor prioridade são avaliadas primeiro.</span><span class="sxs-lookup"><span data-stu-id="40cf8-115">The lines that have the lowest priority number are evaluated first.</span></span> <span data-ttu-id="40cf8-116">Por exemplo, todas as linhas com uma prioridade 1 são avaliadas, depois as linhas com uma prioridade 2 e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="40cf8-116">For example, all lines that have a priority of 1 are evaluated, and then lines that have a priority of 2, and so on.</span></span> <span data-ttu-id="40cf8-117">Quando uma correspondência for encontrada, os outros critérios de correspondência serão ignorados.</span><span class="sxs-lookup"><span data-stu-id="40cf8-117">When a match is found, the other match criteria are ignored.</span></span> <span data-ttu-id="40cf8-118">Além disso, apenas os critérios no grupo que correspondem à transação de origem criarão entradas geradas.</span><span class="sxs-lookup"><span data-stu-id="40cf8-118">Additionally, only the criteria in the group that match the originating transaction create generated entries.</span></span> 

<span data-ttu-id="40cf8-119">Você pode validar suas definições de lançamento usando o assistente **Testar definição de lançamento**.</span><span class="sxs-lookup"><span data-stu-id="40cf8-119">You can validate your posting definitions by using the **Test posting definition** wizard.</span></span> <span data-ttu-id="40cf8-120">Depois de definir uma entrada de origem de exemplo para uma definição de lançamento, você verá as entradas geradas.</span><span class="sxs-lookup"><span data-stu-id="40cf8-120">After you define a sample originating entry for a posting definition, you'll see the generated entries.</span></span> 

<span data-ttu-id="40cf8-121">Você pode usar versões da definição de lançamento junto com datas efetivas.</span><span class="sxs-lookup"><span data-stu-id="40cf8-121">You can use posting definition versions together with effective dates.</span></span> <span data-ttu-id="40cf8-122">Por exemplo, você pode criar uma versão futura de uma definição de lançamento para lançar em uma conta contábil diferente em um novo ano fiscal.</span><span class="sxs-lookup"><span data-stu-id="40cf8-122">For example, you can create a future version of a posting definition to post to a different ledger account in a new fiscal year.</span></span> 

<span data-ttu-id="40cf8-123">Use a página **Definições de lançamento de transação** para atribuir definições de lançamento aos tipos de transação.</span><span class="sxs-lookup"><span data-stu-id="40cf8-123">Use the **Transaction posting definitions** page to assign posting definitions to transaction types.</span></span>

## <a name="linking-posting-definitions"></a><span data-ttu-id="40cf8-124">Vinculação de definições de lançamento</span><span class="sxs-lookup"><span data-stu-id="40cf8-124">Linking posting definitions</span></span>
<span data-ttu-id="40cf8-125">Você pode vincular de uma definição de lançamento para outra quando cria definições de lançamento.</span><span class="sxs-lookup"><span data-stu-id="40cf8-125">You can link from one posting definition to another when you create posting definitions.</span></span> <span data-ttu-id="40cf8-126">Os critérios para a definição à qual você vinculou são então considerados, além dos critérios para a definição de lançamento atual.</span><span class="sxs-lookup"><span data-stu-id="40cf8-126">The criteria for the definition that you linked to are then considered in addition to the criteria for the current posting definition.</span></span> <span data-ttu-id="40cf8-127">Esse recurso ajuda a economizar seu tempo, já que você não precisa reinserir os critérios na Guia Rápida **Entradas** na página **Definições de lançamento** para a definição atual caso você já tenha inserido essas linhas para outra definição.</span><span class="sxs-lookup"><span data-stu-id="40cf8-127">This feature helps save you time, because you don't have to reenter criteria on the **Entries** FastTab on the **Posting definitions** page for the current posting definition if you already entered those lines for another definition.</span></span> 

<span data-ttu-id="40cf8-128">Nos diagramas ou nas tabelas, inclua todos os links que talvez sejam usados.</span><span class="sxs-lookup"><span data-stu-id="40cf8-128">In the diagrams or tables, include any links that you might use.</span></span> <span data-ttu-id="40cf8-129">Para evitar conflitos com a definição de lançamento atual, verifique se as linhas em qualquer definição de lançamento às quais você esteja vinculando sejam exclusivas.</span><span class="sxs-lookup"><span data-stu-id="40cf8-129">To avoid conflicts with the current posting definition, make sure that the lines in any posting definitions that you link to are unique.</span></span> 

<span data-ttu-id="40cf8-130">As seguintes limitações se aplicam quando você cria links em definições de lançamento:</span><span class="sxs-lookup"><span data-stu-id="40cf8-130">The following restrictions apply when you create links in posting definitions:</span></span>

-   <span data-ttu-id="40cf8-131">Uma determinada definição de lançamento pode vincular a outra definição de lançamento ou ser vinculada de outra definição de lançamento, mas não ambos.</span><span class="sxs-lookup"><span data-stu-id="40cf8-131">A given posting definition can either link to another posting definition or be linked to from another posting definition, but not both.</span></span> <span data-ttu-id="40cf8-132">No entanto, uma definição de lançamento pode ser vinculada a várias definições de lançamento.</span><span class="sxs-lookup"><span data-stu-id="40cf8-132">However, a posting definition can link to multiple posting definitions.</span></span>
-   <span data-ttu-id="40cf8-133">Você só pode configurar links entre definições de lançamento que estejam no mesmo módulo.</span><span class="sxs-lookup"><span data-stu-id="40cf8-133">You can set up links only among posting definitions that are in the same module.</span></span>
-   <span data-ttu-id="40cf8-134">Você pode atribuir uma definição de lançamento a qualquer tipo de transação, mas o tipo de transação deve estar no mesmo módulo que a definição de lançamento.</span><span class="sxs-lookup"><span data-stu-id="40cf8-134">You can assign a posting definition to any transaction type, but the transaction type must be in the same module as the posting definition.</span></span> <span data-ttu-id="40cf8-135">Use a página **Definições de lançamento de transação** para ver em qual módulo está um tipo de transação.</span><span class="sxs-lookup"><span data-stu-id="40cf8-135">Use the **Transaction posting definitions** page to see what module a transaction type is in.</span></span>


<span data-ttu-id="40cf8-136">Para obter mais informações, consulte [Exemplos de definição de lançamento](example-posting-definitions.md).</span><span class="sxs-lookup"><span data-stu-id="40cf8-136">For more information, see [Posting definitions examples](example-posting-definitions.md).</span></span> 


