---
title: Procurar fornecedores
description: Aprenda como pesquisar fornecedores com base em critérios específicos.
author: mkirknel
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendSearchCriterion, VendSearchAddCategory, VendSearchAddReviewCriterionGroup, VendSearchResults, VendSearchAddReviewCriterion
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: bc28deb979fe8dc4e31befe6d4d5f6f91388f13e
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "4422610"
---
# <a name="search-for-vendors"></a><span data-ttu-id="dceb1-103">Procurar fornecedores</span><span class="sxs-lookup"><span data-stu-id="dceb1-103">Search for vendors</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="dceb1-104">Aprenda como pesquisar fornecedores com base em critérios específicos.</span><span class="sxs-lookup"><span data-stu-id="dceb1-104">Learn how to search for vendors based on specific criteria.</span></span> <span data-ttu-id="dceb1-105">Este exemplo mostra como procurar fornecedores que estão aprovados para uma categoria de aquisição específica e têm seu endereço principal em um país/região específico.</span><span class="sxs-lookup"><span data-stu-id="dceb1-105">This example shows you how to search for vendors that are approved for a particular procurement category and have their primary address in a specific country.</span></span> <span data-ttu-id="dceb1-106">Você pode executar esse procedimento na empresa de dados demonstrativos USMF, ou usando seus próprios dados.</span><span class="sxs-lookup"><span data-stu-id="dceb1-106">You can run this procedure in demo data company USMF, or on your own data.</span></span> <span data-ttu-id="dceb1-107">Essa tarefa é tipicamente realizada por um profissional de aquisição.</span><span class="sxs-lookup"><span data-stu-id="dceb1-107">This task would usually be carried out by a procurement professional.</span></span>

1. <span data-ttu-id="dceb1-108">Vá para Aquisição e fornecimento > Fornecedores > Pesquisa de fornecedores.</span><span class="sxs-lookup"><span data-stu-id="dceb1-108">Go to Procurement and sourcing > Vendors > Vendor search.</span></span>
2. <span data-ttu-id="dceb1-109">Clique no ícone Mais para abrir a página de seleção da categoria de aquisição.</span><span class="sxs-lookup"><span data-stu-id="dceb1-109">Click on the Plus icon to open the Procurement category selection page.</span></span>  
3. <span data-ttu-id="dceb1-110">Na árvore, selecione 'CATEGORIAS DE AQUISIÇÃO CORPORATIVA\MÁQUINAS DE ESCRITÓRIO'.</span><span class="sxs-lookup"><span data-stu-id="dceb1-110">In the tree, select 'CORP PROCUREMENT CATEGORIES\OFFICE MACHINES'.</span></span>
    * <span data-ttu-id="dceb1-111">Se você estiver executando este procedimento como um guia de tarefa, você talvez precise clicar no botão Desbloquear antes de poder selecionar o nó correto.</span><span class="sxs-lookup"><span data-stu-id="dceb1-111">If you're running this procedure as a task guide, you may have to click the Unlock button before you can select the correct node.</span></span> <span data-ttu-id="dceb1-112">Se você não estiver usando USMF, selecione uma das categorias que você tenha.</span><span class="sxs-lookup"><span data-stu-id="dceb1-112">If you're not using USMF, select one of the categories that you have.</span></span>  
4. <span data-ttu-id="dceb1-113">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="dceb1-113">Click Add.</span></span>
    * <span data-ttu-id="dceb1-114">É possível selecionar mais de uma categoria aqui.</span><span class="sxs-lookup"><span data-stu-id="dceb1-114">It's possible to select more than one category here.</span></span> <span data-ttu-id="dceb1-115">Se você fizer isso, a pesquisa irá encontrar todos os fornecedores que estão aprovados para em pelo menos uma das categorias.</span><span class="sxs-lookup"><span data-stu-id="dceb1-115">If you do so, the search will find all the vendors that are approved for at least one of the categories.</span></span>  
5. <span data-ttu-id="dceb1-116">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="dceb1-116">Click OK.</span></span>
6. <span data-ttu-id="dceb1-117">No campo País/Região, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="dceb1-117">In the Country/region field, type a value.</span></span>
7. <span data-ttu-id="dceb1-118">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="dceb1-118">Click OK.</span></span>

