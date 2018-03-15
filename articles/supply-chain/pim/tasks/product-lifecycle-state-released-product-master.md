--- 
title: Atribuir um estado do ciclo de vida do produto a um produto mestre liberado
description: Este procedimento mostra como atribuir um estado do ciclo de vida do produto a um produto mestre liberado e suas grades.
author: cvocph
manager: AnnBe
ms.date: 12/05/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: d445ea2f2362f146a1e3e7bcf747898dc2cc89ba
ms.openlocfilehash: f476c1b2585ce0b5b67cd0d91684c86f7d3bda36
ms.contentlocale: pt-br
ms.lasthandoff: 02/08/2018

---
# <a name="assign-a-product-lifecycle-state-to-a-released-product-master"></a><span data-ttu-id="2c788-103">Atribuir um estado do ciclo de vida do produto a um produto mestre liberado</span><span class="sxs-lookup"><span data-stu-id="2c788-103">Assign a product lifecycle state to a released product master</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="2c788-104">Este procedimento mostra como atribuir um estado do ciclo de vida do produto a um produto mestre liberado e suas grades.</span><span class="sxs-lookup"><span data-stu-id="2c788-104">This procedure shows how to assign a product lifecycle state to a released product master and its variants.</span></span> <span data-ttu-id="2c788-105">Pré-requisito: você precisará executar o guia de tarefas “Criar um novo estado do ciclo de vida do produto” primeiro para garantir que tem pelo menos um estado do ciclo de vida do produto criado antes de executar este guia de tarefas.</span><span class="sxs-lookup"><span data-stu-id="2c788-105">Prerequisite: You need to play the task guide "Create a new product lifecycle state" first to make sure that you have at least one product lifecycle state created before you can play this task guide.</span></span>


## <a name="find-a-released-product-master"></a><span data-ttu-id="2c788-106">Encontre um produto mestre liberado</span><span class="sxs-lookup"><span data-stu-id="2c788-106">Find a released product master</span></span>
1. <span data-ttu-id="2c788-107">Vá para Gerenciamento de informações do produto > Produtos > Produtos liberados.</span><span class="sxs-lookup"><span data-stu-id="2c788-107">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="2c788-108">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="2c788-108">In the list, find and select the desired record.</span></span>

> [!NOTE]
> <span data-ttu-id="2c788-109">Um produto mestre tem o subtipo de Produto Produto mestre.</span><span class="sxs-lookup"><span data-stu-id="2c788-109">A product master has the Product subtype Product master.</span></span>  

## <a name="update-the-lifecycle-state"></a><span data-ttu-id="2c788-110">Atualize o estado do ciclo de vida</span><span class="sxs-lookup"><span data-stu-id="2c788-110">Update the lifecycle state</span></span>
1. <span data-ttu-id="2c788-111">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="2c788-111">Click Edit.</span></span>
2. <span data-ttu-id="2c788-112">No campo Estado do ciclo de vida do produto, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="2c788-112">In the Product lifecycle state field, enter or select a value.</span></span>
3. <span data-ttu-id="2c788-113">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="2c788-113">Click Save.</span></span>
4. <span data-ttu-id="2c788-114">Clique em Sim.</span><span class="sxs-lookup"><span data-stu-id="2c788-114">Click Yes.</span></span>

> [!NOTE]
> <span data-ttu-id="2c788-115">Caso selecione Sim, todas as grades de produtos liberados relacionados, com o mesmo status original que o produto mestre liberado também serão atualizadas para o novo estado do ciclo de vida do produto.</span><span class="sxs-lookup"><span data-stu-id="2c788-115">If Yes is selected, all the related released product variants that have the same original status as the released product master are also updated to the new product lifecycle state.</span></span> <span data-ttu-id="2c788-116">Caso selecione Não, todas as grades manterão seu estado real.</span><span class="sxs-lookup"><span data-stu-id="2c788-116">If No is selected, all variants keep their actual state.</span></span> <span data-ttu-id="2c788-117">As grades que tiverem um estado do ciclo de vida do produto diferente do produto mestre liberado não serão atualizadas.</span><span class="sxs-lookup"><span data-stu-id="2c788-117">Variants that have a different product lifecycle state from the released product master are not updated.</span></span>  

## <a name="verify-the-lifecycle-state-of-the-variants"></a><span data-ttu-id="2c788-118">Verifique o estado do ciclo de vida das grades</span><span class="sxs-lookup"><span data-stu-id="2c788-118">Verify the lifecycle state of the variants</span></span>
1. <span data-ttu-id="2c788-119">Clique em Variantes de produtos liberados.</span><span class="sxs-lookup"><span data-stu-id="2c788-119">Click Released product variants.</span></span>

> [!NOTE]
> <span data-ttu-id="2c788-120">Observe que todas as grades herdaram o estado do ciclo de vida selecionado do produto mestre liberado.</span><span class="sxs-lookup"><span data-stu-id="2c788-120">Note that all variants have inherited the selected lifecycle state from the released product master.</span></span>  

2. <span data-ttu-id="2c788-121">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="2c788-121">In the list, mark the selected row.</span></span>
3. <span data-ttu-id="2c788-122">No campo Estado do ciclo de vida do produto, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="2c788-122">In the Product lifecycle state field, enter or select a value.</span></span>


