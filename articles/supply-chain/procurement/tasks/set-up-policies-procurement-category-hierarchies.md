--- 
title: "Configurar políticas para hierarquias de categoria de compras"
description: Use este procedimento para configurar regras para encomendar produtos em uma categoria.
author: mkirknel
manager: AnnBe
ms.date: 08/25/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: a8f21599aec191c0358d919b501834677cda30ac
ms.contentlocale: pt-br
ms.lasthandoff: 08/07/2018

---
# <a name="set-up-policies-for-procurement-category-hierarchies"></a><span data-ttu-id="54e27-103">Configurar políticas para hierarquias de categoria de compras</span><span class="sxs-lookup"><span data-stu-id="54e27-103">Set up policies for procurement category hierarchies</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="54e27-104">Use este procedimento para configurar regras para encomendar produtos em uma categoria.</span><span class="sxs-lookup"><span data-stu-id="54e27-104">Use this procedure to set up rules for ordering products in a category.</span></span> <span data-ttu-id="54e27-105">As regras são definidas para uma política de compra específica.</span><span class="sxs-lookup"><span data-stu-id="54e27-105">The rules are defined for a specific purchasing policy.</span></span> <span data-ttu-id="54e27-106">Os controles de regra de acesso a categoria aos quais os funcionários das categorias de aquisição têm acesso quando criam uma requisição.</span><span class="sxs-lookup"><span data-stu-id="54e27-106">The category access rule controls which procurement categories employees have access to when they create a requisition.</span></span> <span data-ttu-id="54e27-107">Quando uma requisição está sendo criada, a política de compras e a regra de acesso à categoria que devem ser aplicados são determinados pela entidade legal e a unidade operacional a qual o funcionário pertence.</span><span class="sxs-lookup"><span data-stu-id="54e27-107">When a requisition is being created, the purchasing policy and category access rule that should be applied are determined by the legal entity and the operational unit that the employee belongs to.</span></span> <span data-ttu-id="54e27-108">Você pode usar este procedimento na empresa USMF de dados de demonstração.</span><span class="sxs-lookup"><span data-stu-id="54e27-108">You can use this procedure in demo data company USMF.</span></span> <span data-ttu-id="54e27-109">Normalmente essa tarefa é realizada por um Gerente de compras.</span><span class="sxs-lookup"><span data-stu-id="54e27-109">This task would typically be carried out by a purchasing manager.</span></span>


## <a name="find-the-procurement-policy"></a><span data-ttu-id="54e27-110">Encontre a política de obtenção</span><span class="sxs-lookup"><span data-stu-id="54e27-110">Find the procurement policy</span></span>
1. <span data-ttu-id="54e27-111">Vá para Compras > Configuração > Políticas > Políticas de compras.</span><span class="sxs-lookup"><span data-stu-id="54e27-111">Go to Procurement and sourcing > Setup > Policies > Purchasing policies.</span></span>
2. <span data-ttu-id="54e27-112">Clique no link da política do USMF da política de aquisição.</span><span class="sxs-lookup"><span data-stu-id="54e27-112">Click the link on the Procurement Policy USMF policy.</span></span>
    * <span data-ttu-id="54e27-113">Esta é a política que você adicionará a uma regra.</span><span class="sxs-lookup"><span data-stu-id="54e27-113">This is the policy that you’ll add a rule to.</span></span> <span data-ttu-id="54e27-114">Deve ser uma política ativa.</span><span class="sxs-lookup"><span data-stu-id="54e27-114">It must be an Active policy.</span></span>  

## <a name="create-a-category-access-rule"></a><span data-ttu-id="54e27-115">Criar uma regra de acesso de categoria</span><span class="sxs-lookup"><span data-stu-id="54e27-115">Create a category access rule</span></span>
1. <span data-ttu-id="54e27-116">Selecione a regra de política de acesso à categoria.</span><span class="sxs-lookup"><span data-stu-id="54e27-116">Select the Category access policy rule.</span></span>
    * <span data-ttu-id="54e27-117">Se o botão Criar regra de política é escurecido, isso se dá porque já há uma regra de política ativa para o acesso à Categoria.</span><span class="sxs-lookup"><span data-stu-id="54e27-117">If the Create policy rule button is dimmed, it’s because there’s already an active policy rule for Category access.</span></span> <span data-ttu-id="54e27-118">Verifique os campos Eficaz e Data de validade para determinar qual é, a seguir selecione-os, e clique em Retirar regra de política.</span><span class="sxs-lookup"><span data-stu-id="54e27-118">Check the Effective and Expiration date fields to determine which it is, then select it, and click Retire policy rule.</span></span> <span data-ttu-id="54e27-119">Se o botão da regra da política da criação está disponível, você não precisa fazer nada.</span><span class="sxs-lookup"><span data-stu-id="54e27-119">If the Create policy rule button is available, you don’t need to do anything.</span></span>  
2. <span data-ttu-id="54e27-120">Clique em Criar regra de política.</span><span class="sxs-lookup"><span data-stu-id="54e27-120">Click Create policy rule.</span></span>
3. <span data-ttu-id="54e27-121">No campo de data efetiva, insira uma data e hora.</span><span class="sxs-lookup"><span data-stu-id="54e27-121">In the Effective date field, enter a date and time.</span></span>
    * <span data-ttu-id="54e27-122">O tempo não deve sobrepor com uma outra regra que seja ativa.</span><span class="sxs-lookup"><span data-stu-id="54e27-122">The time must not overlap with another rule that’s already active.</span></span>  
    * <span data-ttu-id="54e27-123">Selecione uma categoria a que a regra se aplique.</span><span class="sxs-lookup"><span data-stu-id="54e27-123">Select a category that the rule will apply to.</span></span> <span data-ttu-id="54e27-124">Faça uma anotação de que a categoria é – você precisará disso mais tarde.</span><span class="sxs-lookup"><span data-stu-id="54e27-124">Make a note of which category this is – you’ll need it later.</span></span> <span data-ttu-id="54e27-125">Quando você seleciona uma categoria, todas as suas categorias pai também são adicionadas à lista de categorias Selecionada.</span><span class="sxs-lookup"><span data-stu-id="54e27-125">When you select a category, its parent category or categories will also be added to the Selected categories list.</span></span>  
    * <span data-ttu-id="54e27-126">Se você quiser que a regra seja aplicada a todas subcategorias da categoria selecionada, selecione a caixa de seleção Incluir subcategorias.</span><span class="sxs-lookup"><span data-stu-id="54e27-126">If you want the rule to apply to all subcategories of the selected category, select the Include subcategories check box.</span></span>  
4. <span data-ttu-id="54e27-127">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="54e27-127">Click Add.</span></span>
    * <span data-ttu-id="54e27-128">Se você definir a opção de Incluir regra principal para Sim, a regra de diretiva definida para uma categoria pai será atribuída a categorias secundárias se nenhuma regra de diretiva for definida para as categorias secundárias.</span><span class="sxs-lookup"><span data-stu-id="54e27-128">If you set the Include parent rule option to Yes, the policy rule that you define for a parent category is also assigned to its child categories, if no policy rule has been defined for the child categories.</span></span>  
5. <span data-ttu-id="54e27-129">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="54e27-129">Click OK.</span></span>

## <a name="create-a-category-policy-rule"></a><span data-ttu-id="54e27-130">Criar uma regra de política de categoria</span><span class="sxs-lookup"><span data-stu-id="54e27-130">Create a category policy rule</span></span>
1. <span data-ttu-id="54e27-131">Selecione a regra de política da categoria</span><span class="sxs-lookup"><span data-stu-id="54e27-131">Select the Category policy rule</span></span>
    * <span data-ttu-id="54e27-132">Se o botão da regra da política da criação é escurecido, selecione a regra da política ativa, e clique então para retirar a regra da política.</span><span class="sxs-lookup"><span data-stu-id="54e27-132">If the Create policy rule button is dimmed, select the active policy rule, and then click Retire policy rule.</span></span>  
2. <span data-ttu-id="54e27-133">Clique em Criar regra de política.</span><span class="sxs-lookup"><span data-stu-id="54e27-133">Click Create policy rule.</span></span>
3. <span data-ttu-id="54e27-134">No campo de data efetiva, insira uma data e hora.</span><span class="sxs-lookup"><span data-stu-id="54e27-134">In the Effective date field, enter a date and time.</span></span>
4. <span data-ttu-id="54e27-135">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="54e27-135">Click Add.</span></span>
5. <span data-ttu-id="54e27-136">Selecione a mesma categoria que você usou para a regra do acesso da categoria.</span><span class="sxs-lookup"><span data-stu-id="54e27-136">Select the same category that you used for the Category access rule.</span></span>
6. <span data-ttu-id="54e27-137">No campo Seleção do fornecedor, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="54e27-137">In the Vendor selection field, select an option.</span></span>
    * <span data-ttu-id="54e27-138">Selecione uma regra para controlar quais tipos de vendedores podem ser selecionados para a categoria quando as requisições são criadas.</span><span class="sxs-lookup"><span data-stu-id="54e27-138">Select a rule to control which kind of vendors can be selected for the category when requisitions are created.</span></span>  
7. <span data-ttu-id="54e27-139">Clique em Fechar.</span><span class="sxs-lookup"><span data-stu-id="54e27-139">Click Close.</span></span>
    * <span data-ttu-id="54e27-140">A regra de política que você definiu foi para requisições do tipo consumo.</span><span class="sxs-lookup"><span data-stu-id="54e27-140">The policy rules that you have defined have been for requisitions of type Consumption.</span></span> <span data-ttu-id="54e27-141">Se você quis definir políticas para requisições do tipo Reabastecimento, você criaria uma regra para o tipo de regra de política chamado "Regra de política para acessar reabastecimento de categoria".</span><span class="sxs-lookup"><span data-stu-id="54e27-141">If you wanted to define policies for requisitions of type Replenishment, you would create a rule for the Policy rule type called “Replenishment category access policy rule”.</span></span>  


