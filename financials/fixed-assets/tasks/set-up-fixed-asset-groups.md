--- 
title: Configurar grupos de ativos fixos
description: Este procedimento mostra como criar um novo grupo de ativos fixos.
author: saraschi2
manager: AnnBe
ms.date: 02/23/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: c44ce1219c0fc860d621aa32c8eec7c5d640fa03
ms.contentlocale: pt-br
ms.lasthandoff: 08/29/2017

---
# <a name="set-up-fixed-asset-groups"></a><span data-ttu-id="d9932-103">Configurar grupos de ativos fixos</span><span class="sxs-lookup"><span data-stu-id="d9932-103">Set up fixed asset groups</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="d9932-104">Este procedimento mostra como criar um novo grupo de ativos fixos.</span><span class="sxs-lookup"><span data-stu-id="d9932-104">This procedure shows how to create a new fixed asset group.</span></span> <span data-ttu-id="d9932-105">Ela usa a função de contador e os dados de demonstração da entidade legal de USMF.</span><span class="sxs-lookup"><span data-stu-id="d9932-105">It uses the Accountant role and demo data for the USMF legal entity.</span></span>

1. <span data-ttu-id="d9932-106">Vá para Ativos fixos > Configuração > Grupos de ativo fixo.</span><span class="sxs-lookup"><span data-stu-id="d9932-106">Go to Fixed assets > Setup > Fixed asset groups.</span></span>
2. <span data-ttu-id="d9932-107">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="d9932-107">Click New.</span></span>
3. <span data-ttu-id="d9932-108">No campo grupo de ativo fixo, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="d9932-108">In the Fixed asset group field, type a value.</span></span>
4. <span data-ttu-id="d9932-109">No campo Nome, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="d9932-109">In the Name field, type a value.</span></span>
    * <span data-ttu-id="d9932-110">Os ativos fixos e o código da sequência numérica de Autonumber no grupo de ativos fixos substituirão as configurações nos parâmetros de ativos fixos.</span><span class="sxs-lookup"><span data-stu-id="d9932-110">Autonumber fixed assets and Number sequence code on the Fixed asset group will override the settings on the Fixed assets parameters.</span></span> <span data-ttu-id="d9932-111">Você pode alterá-lo aqui se os ativos no grupo de ativos fixos forem diferentes da numeração de outros grupos.</span><span class="sxs-lookup"><span data-stu-id="d9932-111">You can change it here if the assets in this fixed asset group will have different numbering from other groups.</span></span>  
5. <span data-ttu-id="d9932-112">Clique em Registros.</span><span class="sxs-lookup"><span data-stu-id="d9932-112">Click Books.</span></span>
6. <span data-ttu-id="d9932-113">No campo Livro, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="d9932-113">In the Book field, enter or select a value.</span></span>
    * <span data-ttu-id="d9932-114">Como o campo Calcular depreciação é definido como Sim, o registro do ativo será incluído nas propostas de depreciação.</span><span class="sxs-lookup"><span data-stu-id="d9932-114">The Calculate depreciation field is set to Yes, so the asset book will be included in depreciation proposals.</span></span> <span data-ttu-id="d9932-115">Se Calcular a depreciação for definido como Não, o ativo não será depreciado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="d9932-115">If Calculate depreciation is set to No, the asset will not be automatically depreciated.</span></span>  
7. <span data-ttu-id="d9932-116">Defina a vida útil do ativo fixo, em anos.</span><span class="sxs-lookup"><span data-stu-id="d9932-116">Set the Service life of the asset, in years.</span></span>
    * <span data-ttu-id="d9932-117">Observe que o valor do campo de períodos de depreciação será calculado depois de definir a vida útil.</span><span class="sxs-lookup"><span data-stu-id="d9932-117">Note that the Depreciation periods field value is calculated after setting the Service life.</span></span>  
8. <span data-ttu-id="d9932-118">No campo Convenção de depreciação, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="d9932-118">In the Depreciation convention field, select an option.</span></span>
9. <span data-ttu-id="d9932-119">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="d9932-119">Close the page.</span></span>


