---
title: Atribuir um estado do ciclo de vida do produto a um produto mestre liberado
description: Este procedimento mostra como atribuir um estado do ciclo de vida do produto a um produto mestre liberado e suas grades.
author: cvocph
manager: AnnBe
ms.date: 12/05/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: dd9d40bb331b9e024617c8be55330dfce8ba1cc6
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "309463"
---
# <a name="assign-a-product-lifecycle-state-to-a-released-product-master"></a><span data-ttu-id="f6eea-103">Atribuir um estado do ciclo de vida do produto a um produto mestre liberado</span><span class="sxs-lookup"><span data-stu-id="f6eea-103">Assign a product lifecycle state to a released product master</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="f6eea-104">Este procedimento mostra como atribuir um estado do ciclo de vida do produto a um produto mestre liberado e suas grades.</span><span class="sxs-lookup"><span data-stu-id="f6eea-104">This procedure shows how to assign a product lifecycle state to a released product master and its variants.</span></span> <span data-ttu-id="f6eea-105">Pré-requisito: você precisará executar o guia de tarefas “Criar um novo estado do ciclo de vida do produto” primeiro para garantir que tem pelo menos um estado do ciclo de vida do produto criado antes de executar este guia de tarefas.</span><span class="sxs-lookup"><span data-stu-id="f6eea-105">Prerequisite: You need to play the task guide "Create a new product lifecycle state" first to make sure that you have at least one product lifecycle state created before you can play this task guide.</span></span>


## <a name="find-a-released-product-master"></a><span data-ttu-id="f6eea-106">Encontre um produto mestre liberado</span><span class="sxs-lookup"><span data-stu-id="f6eea-106">Find a released product master</span></span>
1. <span data-ttu-id="f6eea-107">Vá para Gerenciamento de informações do produto > Produtos > Produtos liberados.</span><span class="sxs-lookup"><span data-stu-id="f6eea-107">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="f6eea-108">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="f6eea-108">In the list, find and select the desired record.</span></span>

> [!NOTE]
> <span data-ttu-id="f6eea-109">Um produto mestre tem o subtipo de Produto Produto mestre.</span><span class="sxs-lookup"><span data-stu-id="f6eea-109">A product master has the Product subtype Product master.</span></span>  

## <a name="update-the-lifecycle-state"></a><span data-ttu-id="f6eea-110">Atualize o estado do ciclo de vida</span><span class="sxs-lookup"><span data-stu-id="f6eea-110">Update the lifecycle state</span></span>
1. <span data-ttu-id="f6eea-111">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="f6eea-111">Click Edit.</span></span>
2. <span data-ttu-id="f6eea-112">No campo Estado do ciclo de vida do produto, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="f6eea-112">In the Product lifecycle state field, enter or select a value.</span></span>
3. <span data-ttu-id="f6eea-113">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="f6eea-113">Click Save.</span></span>
4. <span data-ttu-id="f6eea-114">Clique em Sim.</span><span class="sxs-lookup"><span data-stu-id="f6eea-114">Click Yes.</span></span>

> [!NOTE]
> <span data-ttu-id="f6eea-115">Caso selecione Sim, todas as grades de produtos liberados relacionados, com o mesmo status original que o produto mestre liberado também serão atualizadas para o novo estado do ciclo de vida do produto.</span><span class="sxs-lookup"><span data-stu-id="f6eea-115">If Yes is selected, all the related released product variants that have the same original status as the released product master are also updated to the new product lifecycle state.</span></span> <span data-ttu-id="f6eea-116">Caso selecione Não, todas as grades manterão seu estado real.</span><span class="sxs-lookup"><span data-stu-id="f6eea-116">If No is selected, all variants keep their actual state.</span></span> <span data-ttu-id="f6eea-117">As grades que tiverem um estado do ciclo de vida do produto diferente do produto mestre liberado não serão atualizadas.</span><span class="sxs-lookup"><span data-stu-id="f6eea-117">Variants that have a different product lifecycle state from the released product master are not updated.</span></span>  

## <a name="verify-the-lifecycle-state-of-the-variants"></a><span data-ttu-id="f6eea-118">Verifique o estado do ciclo de vida das grades</span><span class="sxs-lookup"><span data-stu-id="f6eea-118">Verify the lifecycle state of the variants</span></span>
1. <span data-ttu-id="f6eea-119">Clique em Variantes de produtos liberados.</span><span class="sxs-lookup"><span data-stu-id="f6eea-119">Click Released product variants.</span></span>

> [!NOTE]
> <span data-ttu-id="f6eea-120">Observe que todas as grades herdaram o estado do ciclo de vida selecionado do produto mestre liberado.</span><span class="sxs-lookup"><span data-stu-id="f6eea-120">Note that all variants have inherited the selected lifecycle state from the released product master.</span></span>  

2. <span data-ttu-id="f6eea-121">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="f6eea-121">In the list, mark the selected row.</span></span>
3. <span data-ttu-id="f6eea-122">No campo Estado do ciclo de vida do produto, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="f6eea-122">In the Product lifecycle state field, enter or select a value.</span></span>

