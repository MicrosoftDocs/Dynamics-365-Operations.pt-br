---
title: Atribuir um estado do ciclo de vida do produto a um produto mestre liberado
description: Este procedimento mostra como atribuir um estado do ciclo de vida do produto a um produto mestre liberado e suas grades.
author: cvocph
ms.date: 12/05/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 66859c7f7f5be6eaadd9470fd9b792daa28ce33d
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5807868"
---
# <a name="assign-a-product-lifecycle-state-to-a-released-product-master"></a><span data-ttu-id="950d4-103">Atribuir um estado do ciclo de vida do produto a um produto mestre liberado</span><span class="sxs-lookup"><span data-stu-id="950d4-103">Assign a product lifecycle state to a released product master</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="950d4-104">Este procedimento mostra como atribuir um estado do ciclo de vida do produto a um produto mestre liberado e suas grades.</span><span class="sxs-lookup"><span data-stu-id="950d4-104">This procedure shows how to assign a product lifecycle state to a released product master and its variants.</span></span> <span data-ttu-id="950d4-105">Pré-requisito: você precisará executar o guia de tarefas “Criar um novo estado do ciclo de vida do produto” primeiro para garantir que tem pelo menos um estado do ciclo de vida do produto criado antes de executar este guia de tarefas.</span><span class="sxs-lookup"><span data-stu-id="950d4-105">Prerequisite: You need to play the task guide "Create a new product lifecycle state" first to make sure that you have at least one product lifecycle state created before you can play this task guide.</span></span>


## <a name="find-a-released-product-master"></a><span data-ttu-id="950d4-106">Encontre um produto mestre liberado</span><span class="sxs-lookup"><span data-stu-id="950d4-106">Find a released product master</span></span>
1. <span data-ttu-id="950d4-107">Vá para Gerenciamento de informações do produto > Produtos > Produtos liberados.</span><span class="sxs-lookup"><span data-stu-id="950d4-107">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="950d4-108">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="950d4-108">In the list, find and select the desired record.</span></span>

> [!NOTE]
> <span data-ttu-id="950d4-109">Um produto mestre tem o subtipo de Produto Produto mestre.</span><span class="sxs-lookup"><span data-stu-id="950d4-109">A product master has the Product subtype Product master.</span></span>  

## <a name="update-the-lifecycle-state"></a><span data-ttu-id="950d4-110">Atualize o estado do ciclo de vida</span><span class="sxs-lookup"><span data-stu-id="950d4-110">Update the lifecycle state</span></span>
1. <span data-ttu-id="950d4-111">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="950d4-111">Click Edit.</span></span>
2. <span data-ttu-id="950d4-112">No campo Estado do ciclo de vida do produto, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="950d4-112">In the Product lifecycle state field, enter or select a value.</span></span>
3. <span data-ttu-id="950d4-113">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="950d4-113">Click Save.</span></span>
4. <span data-ttu-id="950d4-114">Clique em Sim.</span><span class="sxs-lookup"><span data-stu-id="950d4-114">Click Yes.</span></span>

> [!NOTE]
> <span data-ttu-id="950d4-115">Caso selecione Sim, todas as grades de produtos liberados relacionados, com o mesmo status original que o produto mestre liberado também serão atualizadas para o novo estado do ciclo de vida do produto.</span><span class="sxs-lookup"><span data-stu-id="950d4-115">If Yes is selected, all the related released product variants that have the same original status as the released product master are also updated to the new product lifecycle state.</span></span> <span data-ttu-id="950d4-116">Caso selecione Não, todas as grades manterão seu estado real.</span><span class="sxs-lookup"><span data-stu-id="950d4-116">If No is selected, all variants keep their actual state.</span></span> <span data-ttu-id="950d4-117">As grades que tiverem um estado do ciclo de vida do produto diferente do produto mestre liberado não serão atualizadas.</span><span class="sxs-lookup"><span data-stu-id="950d4-117">Variants that have a different product lifecycle state from the released product master are not updated.</span></span>  

## <a name="verify-the-lifecycle-state-of-the-variants"></a><span data-ttu-id="950d4-118">Verifique o estado do ciclo de vida das grades</span><span class="sxs-lookup"><span data-stu-id="950d4-118">Verify the lifecycle state of the variants</span></span>
1. <span data-ttu-id="950d4-119">Clique em Variantes de produtos liberados.</span><span class="sxs-lookup"><span data-stu-id="950d4-119">Click Released product variants.</span></span>

> [!NOTE]
> <span data-ttu-id="950d4-120">Observe que todas as grades herdaram o estado do ciclo de vida selecionado do produto mestre liberado.</span><span class="sxs-lookup"><span data-stu-id="950d4-120">Note that all variants have inherited the selected lifecycle state from the released product master.</span></span>  

2. <span data-ttu-id="950d4-121">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="950d4-121">In the list, mark the selected row.</span></span>
3. <span data-ttu-id="950d4-122">No campo Estado do ciclo de vida do produto, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="950d4-122">In the Product lifecycle state field, enter or select a value.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]