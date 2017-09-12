--- 
title: "Criar regras de configuração"
description: "Esse procedimento cria regras de configuração que podem ser usadas na configuração baseada em dimensão para forçar ou evitar certas combinações de linhas da Lista de Materiais."
author: BibiSp
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: c901ebea4fd7423db61ef2c33689e606e33e2434
ms.contentlocale: pt-br
ms.lasthandoff: 08/29/2017

---
# <a name="create-configuration-rules"></a><span data-ttu-id="31c8e-103">Criar regras de configuração</span><span class="sxs-lookup"><span data-stu-id="31c8e-103">Create configuration rules</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="31c8e-104">Esse procedimento cria regras de configuração que podem ser usadas na configuração baseada em dimensão para forçar ou evitar certas combinações de linhas da Lista de Materiais.</span><span class="sxs-lookup"><span data-stu-id="31c8e-104">This procedure creates configuration rules that can be used for dimension-based configuration to enforce or prevent certain combinations of BOM lines.</span></span> <span data-ttu-id="31c8e-105">A empresa de dados demo usada para criar este procedimento é USMF.</span><span class="sxs-lookup"><span data-stu-id="31c8e-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="31c8e-106">Este é o sétimo procedimento dos oito que explicam como criar combinações para configuração baseada em dimensão.</span><span class="sxs-lookup"><span data-stu-id="31c8e-106">This is the seventh procedure out of eight that explains how to build combinations for dimension-based configuration.</span></span>

1. <span data-ttu-id="31c8e-107">Vá para Gerenciamento de informações sobre produtos > Lista de materiais e fórmulas > Lista de materiais.</span><span class="sxs-lookup"><span data-stu-id="31c8e-107">Go to Product information management > Bills of materials and formulas > Bills of materials.</span></span>
2. <span data-ttu-id="31c8e-108">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="31c8e-108">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="31c8e-109">Localize e selecione a Lista de Materiais para a configuração baseada em dimensão.</span><span class="sxs-lookup"><span data-stu-id="31c8e-109">Find and select the BOM for the dimension-based configuration.</span></span>  
3. <span data-ttu-id="31c8e-110">No Painel de Ação, clique em Opções.</span><span class="sxs-lookup"><span data-stu-id="31c8e-110">On the Action Pane, click Options.</span></span>
4. <span data-ttu-id="31c8e-111">Clique em Alterar exibição.</span><span class="sxs-lookup"><span data-stu-id="31c8e-111">Click Change view.</span></span>
5. <span data-ttu-id="31c8e-112">Clique em Exibição do cabeçalho.</span><span class="sxs-lookup"><span data-stu-id="31c8e-112">Click Header view.</span></span>
    * <span data-ttu-id="31c8e-113">Abra a exibição do cabeçalho para acessar a aba rápida do Roteiro de configuração.</span><span class="sxs-lookup"><span data-stu-id="31c8e-113">Open the header view to access the Configuration route FastTab.</span></span>  
6. <span data-ttu-id="31c8e-114">Expandir ou recolher a seção Rota de configuração.</span><span class="sxs-lookup"><span data-stu-id="31c8e-114">Expand or collapse the Configuration route section.</span></span>
    * <span data-ttu-id="31c8e-115">A aba rápida Roteiro de configuração deve estar no modo expandido.</span><span class="sxs-lookup"><span data-stu-id="31c8e-115">The Configuration route FastTab must be in the expanded mode.</span></span>  
7. <span data-ttu-id="31c8e-116">Clique em Regras de configuração.</span><span class="sxs-lookup"><span data-stu-id="31c8e-116">Click Configuration rules.</span></span>
8. <span data-ttu-id="31c8e-117">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="31c8e-117">Click New.</span></span>
9. <span data-ttu-id="31c8e-118">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="31c8e-118">In the list, mark the selected row.</span></span>
10. <span data-ttu-id="31c8e-119">No campo Número de item, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="31c8e-119">In the Item number field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="31c8e-120">Os itens do grupo de configuração atual estão exibidos.</span><span class="sxs-lookup"><span data-stu-id="31c8e-120">The items in the current configuration group are displayed.</span></span> <span data-ttu-id="31c8e-121">Selecione aquele que representa a condição na regra.</span><span class="sxs-lookup"><span data-stu-id="31c8e-121">Select the one that represents the condition in the rule.</span></span>  
11. <span data-ttu-id="31c8e-122">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="31c8e-122">In the list, click the link in the selected row.</span></span>
12. <span data-ttu-id="31c8e-123">No campo Método, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="31c8e-123">In the Method field, select an option.</span></span>
    * <span data-ttu-id="31c8e-124">É possível forçar tanto uma seleção como uma desmarcação de um item de outro grupo de configuração.</span><span class="sxs-lookup"><span data-stu-id="31c8e-124">It is possible to enforce either a selection or a deselection of an item from another configuration group.</span></span>  
13. <span data-ttu-id="31c8e-125">No campo Grupo derivado, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="31c8e-125">In the Derived group field, click the drop-down button to open the lookup.</span></span>
14. <span data-ttu-id="31c8e-126">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="31c8e-126">In the list, find and select the desired record.</span></span>
15. <span data-ttu-id="31c8e-127">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="31c8e-127">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="31c8e-128">Selecione o grupo de configuração desejado.</span><span class="sxs-lookup"><span data-stu-id="31c8e-128">Select the desired configuration group.</span></span>  
16. <span data-ttu-id="31c8e-129">No campo Número de item derivado, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="31c8e-129">In the Derived item number field, click the drop-down button to open the lookup.</span></span>
17. <span data-ttu-id="31c8e-130">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="31c8e-130">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="31c8e-131">Selecione o número de item que será selecionado ou desmarcado de acordo com o método escolhido.</span><span class="sxs-lookup"><span data-stu-id="31c8e-131">Select the item number that will be either selected or deselected depending on the chosen method.</span></span>  
18. <span data-ttu-id="31c8e-132">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="31c8e-132">Close the page.</span></span>


