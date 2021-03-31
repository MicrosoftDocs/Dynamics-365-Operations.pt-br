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
ms.search.form: WHSWorkException, WHSWorker, WHSLocationWithWorkException
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3ecd05add44bacae517109f8bab2cb43376fe07c
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5216802"
---
# <a name="set-up-short-picking-item-reallocation"></a><span data-ttu-id="394a6-103">Configurar realocação de item de pouca seleção</span><span class="sxs-lookup"><span data-stu-id="394a6-103">Set up short picking item reallocation</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="394a6-104">Este procedimento mostra como permitir que os trabalhadores do depósito encontrem rapidamente locais alternativos se não houver estoque suficiente no local para o qual eles foram direcionados.</span><span class="sxs-lookup"><span data-stu-id="394a6-104">This procedure shows how to enable warehouse workers to quickly find alternative locations if there isn’t sufficient inventory at the location they’ve been directed to.</span></span> 

<span data-ttu-id="394a6-105">O processo de realocação é controlado por uma **Exceção de trabalho** e usado pelo **trabalhador** do depósito.</span><span class="sxs-lookup"><span data-stu-id="394a6-105">The reallocation process is controlled by a **Work exception** and used by the warehouse **worker.**</span></span>

<span data-ttu-id="394a6-106">É possível usar processos de realocação Automáticos, Manuais ou ambos:</span><span class="sxs-lookup"><span data-stu-id="394a6-106">It is possible to use Automatic, Manual, or both reallocation processes:</span></span>

- <span data-ttu-id="394a6-107">Realocação automática - As diretivas de localização são usadas para determinar se as mercadorias estão disponíveis em outro local.</span><span class="sxs-lookup"><span data-stu-id="394a6-107">Automatic reallocation - Location directives are used to determine if the goods are available at another location.</span></span> <span data-ttu-id="394a6-108">Se possível, o trabalho será atualizado e o usuário do depósito será direcionado para o local alternativo.</span><span class="sxs-lookup"><span data-stu-id="394a6-108">If possible, the work will be updated and the warehouse user will be directed to the alternative location.</span></span>
- <span data-ttu-id="394a6-109">Realocação manual - Permite que o usuário do depósito selecione um ou mais locais com quantidades de mercadorias não reservadas.</span><span class="sxs-lookup"><span data-stu-id="394a6-109">Manual reallocation - Allows the warehouse user to select from one or more locations with unreserved quantities of goods.</span></span> 
- <span data-ttu-id="394a6-110">Automática e manual - Se o sistema não puder executar uma realocação automática e os locais estiverem disponíveis com quantidades não reservadas, o usuário será solicitado a selecionar um local.</span><span class="sxs-lookup"><span data-stu-id="394a6-110">Automatic and manual - If the system is unable to perform an automatic reallocation, and locations are available with unreserved quantities, the user will be prompted to select a location.</span></span>

## <a name="set-up-work-exceptions"></a><span data-ttu-id="394a6-111">Configurar exceções de trabalho</span><span class="sxs-lookup"><span data-stu-id="394a6-111">Set up work exceptions</span></span>
<span data-ttu-id="394a6-112">É possível definir várias exceções de trabalho com diferentes políticas de realocação de itens para permitir que os trabalhadores do depósito escolham uma com base nas necessidades da remessa que eles estão processando.</span><span class="sxs-lookup"><span data-stu-id="394a6-112">It's possible to define several work exceptions with different item reallocation policies to enable the warehouse worker to choose one based on the needs of the shipment that they are processing.</span></span>

<span data-ttu-id="394a6-113">A empresa de dados de demonstração USMF foi usada para criar este procedimento.</span><span class="sxs-lookup"><span data-stu-id="394a6-113">The USMF demo data company was used to create this procedure.</span></span>

1. <span data-ttu-id="394a6-114">No **Painel de navegação**, acesse **Gerenciamento de depósito > Configuração > Trabalho > Exceções de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="394a6-114">In the **Navigation pane**, go to **Warehouse management > Setup > Work > Work exceptions**.</span></span>
2. <span data-ttu-id="394a6-115">Clique em **Novo**</span><span class="sxs-lookup"><span data-stu-id="394a6-115">Click **New**</span></span> 
3. <span data-ttu-id="394a6-116">No campo **Código de exceção do trabalho**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="394a6-116">In the **Work exception code** field, type a value.</span></span> <span data-ttu-id="394a6-117">Isso será o título dessa exceção.</span><span class="sxs-lookup"><span data-stu-id="394a6-117">This will be the title of this exception .</span></span> <span data-ttu-id="394a6-118">Por exemplo, manual de separação insuficiente.</span><span class="sxs-lookup"><span data-stu-id="394a6-118">For example, Short picking manual.</span></span>
4. <span data-ttu-id="394a6-119">No campo **Descrição**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="394a6-119">In the **Description** field, type a value.</span></span> <span data-ttu-id="394a6-120">Isso será uma breve descrição do uso dessa exceção.</span><span class="sxs-lookup"><span data-stu-id="394a6-120">This will be a short description of the usage of this exception.</span></span> <span data-ttu-id="394a6-121">Por exemplo, Separação insuficiente - item não disponível.</span><span class="sxs-lookup"><span data-stu-id="394a6-121">For example, Short picking - item not available.</span></span>
5. <span data-ttu-id="394a6-122">No campo do tipo de **Exceção**, selecione **Separação insuficiente**.</span><span class="sxs-lookup"><span data-stu-id="394a6-122">In the **Exception** type field, select **Short pick**.</span></span>
6. <span data-ttu-id="394a6-123">Marque a caixa de seleção **Ajustar estoque**.</span><span class="sxs-lookup"><span data-stu-id="394a6-123">Select the **Adjust inventory** check box.</span></span> <span data-ttu-id="394a6-124">Se marcada, o estoque será automaticamente ajustado para 0 no local de separação insuficiente.</span><span class="sxs-lookup"><span data-stu-id="394a6-124">If selected, inventory will automatically be adjusted to 0 at the short picked location.</span></span>
7. <span data-ttu-id="394a6-125">No campo **Código de tipo de ajuste padrão**, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="394a6-125">In the **Default adjustment type code** field, enter or select a value.</span></span> <span data-ttu-id="394a6-126">Por exemplo, na USMF, você pode selecionar **Remover Res Adj Out**. Cada Código de tipo de ajuste contém quatro características: nome, descrição, nome do diário de estoque e **Remover reservas**.</span><span class="sxs-lookup"><span data-stu-id="394a6-126">For example, in USMF you can select **Remove Res Adj Out**. Each Adjustment type code contains four characteristics: name, description, inventory journal name, and **Remove reservations**.</span></span> <span data-ttu-id="394a6-127">Se **Remover reservas** estiver habilitado, as reservas da linha de ordem de separação insuficiente serão removidas.</span><span class="sxs-lookup"><span data-stu-id="394a6-127">If **Remove reservations** is enabled, the short-picked order line's reservations will be removed.</span></span>  
8. <span data-ttu-id="394a6-128">No campo **Realocação de item**, selecione um valor, como Manual.</span><span class="sxs-lookup"><span data-stu-id="394a6-128">In the **Item reallocation** field, select a value, such as Manual.</span></span> <span data-ttu-id="394a6-129">Se você selecionar Manual, ou Automática e Manual, o trabalhador do depósito precisará estar habilitado para usar a realocação manual.</span><span class="sxs-lookup"><span data-stu-id="394a6-129">If you select Manual, or Automatic and Manual, the warehouse worker needs to be enabled to use manual reallocation.</span></span>

## <a name="set-up-a-worker-to-use-manual-item-reallocation"></a><span data-ttu-id="394a6-130">Configurar um trabalhador para usar a realocação de item manual</span><span class="sxs-lookup"><span data-stu-id="394a6-130">Set up a worker to use manual item reallocation</span></span>

<span data-ttu-id="394a6-131">A empresa de dados de demonstração USMF foi usada para criar este procedimento.</span><span class="sxs-lookup"><span data-stu-id="394a6-131">The USMF demo data company was used to create this procedure.</span></span>

1. <span data-ttu-id="394a6-132">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="394a6-132">Close the page.</span></span>
2. <span data-ttu-id="394a6-133">No **Painel de navegação**, acesse **Gerenciamento de depósito > Configuração > Trabalhador**.</span><span class="sxs-lookup"><span data-stu-id="394a6-133">In the **Navigation pane**, go to **Warehouse management > Setup > Worker**.</span></span>
3. <span data-ttu-id="394a6-134">Clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="394a6-134">Click **Edit**.</span></span>
4. <span data-ttu-id="394a6-135">Na lista, selecione o trabalhador.</span><span class="sxs-lookup"><span data-stu-id="394a6-135">In the list, select worker.</span></span> <span data-ttu-id="394a6-136">Por exemplo, Julia Funderburk.</span><span class="sxs-lookup"><span data-stu-id="394a6-136">For example, Julia Funderburk.</span></span>
5. <span data-ttu-id="394a6-137">Expanda a FastTab **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="394a6-137">Expand the **Users** FastTab.</span></span>
6. <span data-ttu-id="394a6-138">Na lista, selecione uma **ID de Usuário**.</span><span class="sxs-lookup"><span data-stu-id="394a6-138">In the list, select a **User ID**.</span></span> <span data-ttu-id="394a6-139">Por exemplo, 24.</span><span class="sxs-lookup"><span data-stu-id="394a6-139">For example, 24.</span></span>
7. <span data-ttu-id="394a6-140">Expanda a FastTab **Trabalho**.</span><span class="sxs-lookup"><span data-stu-id="394a6-140">Expand the **Work** FastTab.</span></span>
8. <span data-ttu-id="394a6-141">Selecione **Sim** no campo **Permitir realocação manual de itens**.</span><span class="sxs-lookup"><span data-stu-id="394a6-141">Select **Yes** in the **Allow manual item reallocation** field.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]