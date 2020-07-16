---
title: Configurar realocação de item de pouca seleção
description: Este tópico mostra como permitir que os trabalhadores do depósito encontrem rapidamente locais alternativos se não houver estoque suficiente no local para o qual eles foram direcionados.
author: ShylaThompson
manager: tfehr
ms.date: 06/29/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWorkException, WHSWorker
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e14a4fc72d256bea31296bff80d5b5818b95ea9d
ms.sourcegitcommit: ce397c2759f642c595e30fef58a770b50360b2bd
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2020
ms.locfileid: "3527410"
---
# <a name="set-up-short-picking-item-reallocation"></a><span data-ttu-id="c4749-103">Configurar realocação de item de pouca seleção</span><span class="sxs-lookup"><span data-stu-id="c4749-103">Set up short picking item reallocation</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="c4749-104">Este procedimento mostra como permitir que os trabalhadores do depósito encontrem rapidamente locais alternativos se não houver estoque suficiente no local para o qual eles foram direcionados.</span><span class="sxs-lookup"><span data-stu-id="c4749-104">This procedure shows how to enable warehouse workers to quickly find alternative locations if there isn’t sufficient inventory at the location they’ve been directed to.</span></span> 

<span data-ttu-id="c4749-105">O processo de realocação é controlado por uma **Exceção de trabalho** e usado pelo **trabalhador** do depósito.</span><span class="sxs-lookup"><span data-stu-id="c4749-105">The reallocation process is controlled by a **Work exception** and used by the warehouse **worker.**</span></span>

<span data-ttu-id="c4749-106">É possível usar processos de realocação Automáticos, Manuais ou ambos:</span><span class="sxs-lookup"><span data-stu-id="c4749-106">It is possible to use Automatic, Manual, or both reallocation processes:</span></span>

- <span data-ttu-id="c4749-107">Realocação automática - As diretivas de localização são usadas para determinar se as mercadorias estão disponíveis em outro local.</span><span class="sxs-lookup"><span data-stu-id="c4749-107">Automatic reallocation - Location directives are used to determine if the goods are available at another location.</span></span> <span data-ttu-id="c4749-108">Se possível, o trabalho será atualizado e o usuário do depósito será direcionado para o local alternativo.</span><span class="sxs-lookup"><span data-stu-id="c4749-108">If possible, the work will be updated and the warehouse user will be directed to the alternative location.</span></span>
- <span data-ttu-id="c4749-109">Realocação manual - Permite que o usuário do depósito selecione um ou mais locais com quantidades de mercadorias não reservadas.</span><span class="sxs-lookup"><span data-stu-id="c4749-109">Manual reallocation - Allows the warehouse user to select from one or more locations with unreserved quantities of goods.</span></span> 
- <span data-ttu-id="c4749-110">Automática e manual - Se o sistema não puder executar uma realocação automática e os locais estiverem disponíveis com quantidades não reservadas, o usuário será solicitado a selecionar um local.</span><span class="sxs-lookup"><span data-stu-id="c4749-110">Automatic and manual - If the system is unable to perform an automatic reallocation, and locations are available with unreserved quantities, the user will be prompted to select a location.</span></span>

## <a name="set-up-work-exceptions"></a><span data-ttu-id="c4749-111">Configurar exceções de trabalho</span><span class="sxs-lookup"><span data-stu-id="c4749-111">Set up work exceptions</span></span>
<span data-ttu-id="c4749-112">É possível definir várias exceções de trabalho com diferentes políticas de realocação de itens para permitir que os trabalhadores do depósito escolham uma com base nas necessidades da remessa que eles estão processando.</span><span class="sxs-lookup"><span data-stu-id="c4749-112">It's possible to define several work exceptions with different item reallocation policies to enable the warehouse worker to choose one based on the needs of the shipment that they are processing.</span></span>

<span data-ttu-id="c4749-113">A empresa de dados de demonstração USMF foi usada para criar este procedimento.</span><span class="sxs-lookup"><span data-stu-id="c4749-113">The USMF demo data company was used to create this procedure.</span></span>

1. <span data-ttu-id="c4749-114">No **Painel de navegação**, acesse **Gerenciamento de depósito > Configuração > Trabalho > Exceções de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="c4749-114">In the **Navigation pane**, go to **Warehouse management > Setup > Work > Work exceptions**.</span></span>
2. <span data-ttu-id="c4749-115">Clique em **Novo**</span><span class="sxs-lookup"><span data-stu-id="c4749-115">Click **New**</span></span> 
3. <span data-ttu-id="c4749-116">No campo **Código de exceção do trabalho**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="c4749-116">In the **Work exception code** field, type a value.</span></span> <span data-ttu-id="c4749-117">Isso será o título dessa exceção.</span><span class="sxs-lookup"><span data-stu-id="c4749-117">This will be the title of this exception .</span></span> <span data-ttu-id="c4749-118">Por exemplo, manual de separação insuficiente.</span><span class="sxs-lookup"><span data-stu-id="c4749-118">For example, Short picking manual.</span></span>
4. <span data-ttu-id="c4749-119">No campo **Descrição**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="c4749-119">In the **Description** field, type a value.</span></span> <span data-ttu-id="c4749-120">Isso será uma breve descrição do uso dessa exceção.</span><span class="sxs-lookup"><span data-stu-id="c4749-120">This will be a short description of the usage of this exception.</span></span> <span data-ttu-id="c4749-121">Por exemplo, Separação insuficiente - item não disponível.</span><span class="sxs-lookup"><span data-stu-id="c4749-121">For example, Short picking - item not available.</span></span>
5. <span data-ttu-id="c4749-122">No campo do tipo de **Exceção**, selecione **Separação insuficiente**.</span><span class="sxs-lookup"><span data-stu-id="c4749-122">In the **Exception** type field, select **Short pick**.</span></span>
6. <span data-ttu-id="c4749-123">Marque a caixa de seleção **Ajustar estoque**.</span><span class="sxs-lookup"><span data-stu-id="c4749-123">Select the **Adjust inventory** check box.</span></span> <span data-ttu-id="c4749-124">Se marcada, o estoque será automaticamente ajustado para 0 no local de separação insuficiente.</span><span class="sxs-lookup"><span data-stu-id="c4749-124">If selected, inventory will automatically be adjusted to 0 at the short picked location.</span></span>
7. <span data-ttu-id="c4749-125">No campo **Código de tipo de ajuste padrão**, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="c4749-125">In the **Default adjustment type code** field, enter or select a value.</span></span> <span data-ttu-id="c4749-126">Por exemplo, na USMF, você pode selecionar **Remover Res Adj Out**. Cada Código de tipo de ajuste contém quatro características: nome, descrição, nome do diário de estoque e **Remover reservas**.</span><span class="sxs-lookup"><span data-stu-id="c4749-126">For example, in USMF you can select **Remove Res Adj Out**. Each Adjustment type code contains four characteristics: name, description, inventory journal name, and **Remove reservations**.</span></span> <span data-ttu-id="c4749-127">Se **Remover reservas** estiver habilitado, as reservas da linha de ordem de separação insuficiente serão removidas.</span><span class="sxs-lookup"><span data-stu-id="c4749-127">If **Remove reservations** is enabled, the short-picked order line's reservations will be removed.</span></span>  
8. <span data-ttu-id="c4749-128">No campo **Realocação de item**, selecione um valor, como Manual.</span><span class="sxs-lookup"><span data-stu-id="c4749-128">In the **Item reallocation** field, select a value, such as Manual.</span></span> <span data-ttu-id="c4749-129">Se você selecionar Manual, ou Automática e Manual, o trabalhador do depósito precisará estar habilitado para usar a realocação manual.</span><span class="sxs-lookup"><span data-stu-id="c4749-129">If you select Manual, or Automatic and Manual, the warehouse worker needs to be enabled to use manual reallocation.</span></span>

## <a name="set-up-a-worker-to-use-manual-item-reallocation"></a><span data-ttu-id="c4749-130">Configurar um trabalhador para usar a realocação de item manual</span><span class="sxs-lookup"><span data-stu-id="c4749-130">Set up a worker to use manual item reallocation</span></span>

<span data-ttu-id="c4749-131">A empresa de dados de demonstração USMF foi usada para criar este procedimento.</span><span class="sxs-lookup"><span data-stu-id="c4749-131">The USMF demo data company was used to create this procedure.</span></span>

1. <span data-ttu-id="c4749-132">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="c4749-132">Close the page.</span></span>
2. <span data-ttu-id="c4749-133">No **Painel de navegação**, acesse **Gerenciamento de depósito > Configuração > Trabalhador**.</span><span class="sxs-lookup"><span data-stu-id="c4749-133">In the **Navigation pane**, go to **Warehouse management > Setup > Worker**.</span></span>
3. <span data-ttu-id="c4749-134">Clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="c4749-134">Click **Edit**.</span></span>
4. <span data-ttu-id="c4749-135">Na lista, selecione o trabalhador.</span><span class="sxs-lookup"><span data-stu-id="c4749-135">In the list, select worker.</span></span> <span data-ttu-id="c4749-136">Por exemplo, Julia Funderburk.</span><span class="sxs-lookup"><span data-stu-id="c4749-136">For example, Julia Funderburk.</span></span>
5. <span data-ttu-id="c4749-137">Expanda a FastTab **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="c4749-137">Expand the **Users** FastTab.</span></span>
6. <span data-ttu-id="c4749-138">Na lista, selecione uma **ID de Usuário**.</span><span class="sxs-lookup"><span data-stu-id="c4749-138">In the list, select a **User ID**.</span></span> <span data-ttu-id="c4749-139">Por exemplo, 24.</span><span class="sxs-lookup"><span data-stu-id="c4749-139">For example, 24.</span></span>
7. <span data-ttu-id="c4749-140">Expanda a FastTab **Trabalho**.</span><span class="sxs-lookup"><span data-stu-id="c4749-140">Expand the **Work** FastTab.</span></span>
8. <span data-ttu-id="c4749-141">Selecione **Sim** no campo **Permitir realocação manual de itens**.</span><span class="sxs-lookup"><span data-stu-id="c4749-141">Select **Yes** in the **Allow manual item reallocation** field.</span></span>
