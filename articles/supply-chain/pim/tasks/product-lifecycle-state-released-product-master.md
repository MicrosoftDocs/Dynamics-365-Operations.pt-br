---
title: Atribuir um estado do ciclo de vida do produto a um produto mestre liberado
description: Este procedimento mostra como atribuir um estado do ciclo de vida do produto a um produto mestre liberado e suas grades.
author: cvocph
manager: tfehr
ms.date: 12/05/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2c644f118e0bdb46b296cec7e4a3ea89031f2d52
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/10/2020
ms.locfileid: "3981125"
---
# <a name="assign-a-product-lifecycle-state-to-a-released-product-master"></a><span data-ttu-id="2d050-103">Atribuir um estado do ciclo de vida do produto a um produto mestre liberado</span><span class="sxs-lookup"><span data-stu-id="2d050-103">Assign a product lifecycle state to a released product master</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="2d050-104">Este procedimento mostra como atribuir um estado do ciclo de vida do produto a um produto mestre liberado e suas grades.</span><span class="sxs-lookup"><span data-stu-id="2d050-104">This procedure shows how to assign a product lifecycle state to a released product master and its variants.</span></span> <span data-ttu-id="2d050-105">Pré-requisito: você precisará executar o guia de tarefas “Criar um novo estado do ciclo de vida do produto” primeiro para garantir que tem pelo menos um estado do ciclo de vida do produto criado antes de executar este guia de tarefas.</span><span class="sxs-lookup"><span data-stu-id="2d050-105">Prerequisite: You need to play the task guide "Create a new product lifecycle state" first to make sure that you have at least one product lifecycle state created before you can play this task guide.</span></span>


## <a name="find-a-released-product-master"></a><span data-ttu-id="2d050-106">Encontre um produto mestre liberado</span><span class="sxs-lookup"><span data-stu-id="2d050-106">Find a released product master</span></span>
1. <span data-ttu-id="2d050-107">Vá para Gerenciamento de informações do produto > Produtos > Produtos liberados.</span><span class="sxs-lookup"><span data-stu-id="2d050-107">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="2d050-108">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="2d050-108">In the list, find and select the desired record.</span></span>

> [!NOTE]
> <span data-ttu-id="2d050-109">Um produto mestre tem o subtipo de Produto Produto mestre.</span><span class="sxs-lookup"><span data-stu-id="2d050-109">A product master has the Product subtype Product master.</span></span>  

## <a name="update-the-lifecycle-state"></a><span data-ttu-id="2d050-110">Atualize o estado do ciclo de vida</span><span class="sxs-lookup"><span data-stu-id="2d050-110">Update the lifecycle state</span></span>
1. <span data-ttu-id="2d050-111">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="2d050-111">Click Edit.</span></span>
2. <span data-ttu-id="2d050-112">No campo Estado do ciclo de vida do produto, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="2d050-112">In the Product lifecycle state field, enter or select a value.</span></span>
3. <span data-ttu-id="2d050-113">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="2d050-113">Click Save.</span></span>
4. <span data-ttu-id="2d050-114">Clique em Sim.</span><span class="sxs-lookup"><span data-stu-id="2d050-114">Click Yes.</span></span>

> [!NOTE]
> <span data-ttu-id="2d050-115">Caso selecione Sim, todas as grades de produtos liberados relacionados, com o mesmo status original que o produto mestre liberado também serão atualizadas para o novo estado do ciclo de vida do produto.</span><span class="sxs-lookup"><span data-stu-id="2d050-115">If Yes is selected, all the related released product variants that have the same original status as the released product master are also updated to the new product lifecycle state.</span></span> <span data-ttu-id="2d050-116">Caso selecione Não, todas as grades manterão seu estado real.</span><span class="sxs-lookup"><span data-stu-id="2d050-116">If No is selected, all variants keep their actual state.</span></span> <span data-ttu-id="2d050-117">As grades que tiverem um estado do ciclo de vida do produto diferente do produto mestre liberado não serão atualizadas.</span><span class="sxs-lookup"><span data-stu-id="2d050-117">Variants that have a different product lifecycle state from the released product master are not updated.</span></span>  

## <a name="verify-the-lifecycle-state-of-the-variants"></a><span data-ttu-id="2d050-118">Verifique o estado do ciclo de vida das grades</span><span class="sxs-lookup"><span data-stu-id="2d050-118">Verify the lifecycle state of the variants</span></span>
1. <span data-ttu-id="2d050-119">Clique em Variantes de produtos liberados.</span><span class="sxs-lookup"><span data-stu-id="2d050-119">Click Released product variants.</span></span>

> [!NOTE]
> <span data-ttu-id="2d050-120">Observe que todas as grades herdaram o estado do ciclo de vida selecionado do produto mestre liberado.</span><span class="sxs-lookup"><span data-stu-id="2d050-120">Note that all variants have inherited the selected lifecycle state from the released product master.</span></span>  

2. <span data-ttu-id="2d050-121">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="2d050-121">In the list, mark the selected row.</span></span>
3. <span data-ttu-id="2d050-122">No campo Estado do ciclo de vida do produto, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="2d050-122">In the Product lifecycle state field, enter or select a value.</span></span>

