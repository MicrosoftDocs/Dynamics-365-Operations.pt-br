--- 
title: Criar um novo produto
description: Essa tarefa mostra como criar um novo produto compartilhado.
author: YuyuScheller
manager: AnnBe
ms.date: 06/08/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Operations
ms.search.region: Global
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 6dd2aa1ebc713287120106a9d1ec7dc15c24def9
ms.openlocfilehash: 56ce5d965952d0cb41278915e4631ae9d920f5f9
ms.contentlocale: pt-br
ms.lasthandoff: 09/14/2017

---
# <a name="create-a-new-product"></a><span data-ttu-id="68c25-103">Criar um novo produto</span><span class="sxs-lookup"><span data-stu-id="68c25-103">Create a new product</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="68c25-104">Essa tarefa mostra como criar um novo produto compartilhado.</span><span class="sxs-lookup"><span data-stu-id="68c25-104">This task shows how to create a new shared product.</span></span> <span data-ttu-id="68c25-105">Geralmente é realizado por um designer do produto.</span><span class="sxs-lookup"><span data-stu-id="68c25-105">It is usually carried out by a product designer.</span></span> <span data-ttu-id="68c25-106">A empresa de dados demo usada para criar esta tarefa é USMF.</span><span class="sxs-lookup"><span data-stu-id="68c25-106">The demo data company used to create this task is USMF.</span></span>

1. <span data-ttu-id="68c25-107">Vá para Gerenciamento de informações sobre produtos > Produtos > Produtos.</span><span class="sxs-lookup"><span data-stu-id="68c25-107">Go to Product information management > Products > Products.</span></span>

## <a name="create-a-product"></a><span data-ttu-id="68c25-108">Criar um produto</span><span class="sxs-lookup"><span data-stu-id="68c25-108">Create a product</span></span>
1. <span data-ttu-id="68c25-109">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="68c25-109">Click New.</span></span>
2. <span data-ttu-id="68c25-110">No campo Número do produto, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="68c25-110">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="68c25-111">Se uma sequência numérica não foi configurada para o número do produto, deve ser inserida manualmente.</span><span class="sxs-lookup"><span data-stu-id="68c25-111">If a number sequence has not been set up for the product number, it must be entered manually.</span></span>  
3. <span data-ttu-id="68c25-112">No campo Nome do produto, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="68c25-112">In the Product name field, type a value.</span></span>
    * <span data-ttu-id="68c25-113">O Nome do produto padrão ao nome de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="68c25-113">The product name defaults to the search name.</span></span> <span data-ttu-id="68c25-114">Você pode mudar isso, se necessário.</span><span class="sxs-lookup"><span data-stu-id="68c25-114">You can change this if needed.</span></span>  
4. <span data-ttu-id="68c25-115">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="68c25-115">Click OK.</span></span>

## <a name="set-up-dimension-groups"></a><span data-ttu-id="68c25-116">Configurar grupos de dimensões</span><span class="sxs-lookup"><span data-stu-id="68c25-116">Set up dimension groups</span></span>
1. <span data-ttu-id="68c25-117">Clique em Grupos de dimensões para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="68c25-117">Click Dimension groups to open the drop dialog.</span></span>
2. <span data-ttu-id="68c25-118">No campo Grupo de dimensões de armazenamento, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="68c25-118">In the Storage dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="68c25-119">O grupo de dimensões de armazenamento determina quais dimensões de estoque você deve inserir em cada transação para o produto e como são rastreados no estoque.</span><span class="sxs-lookup"><span data-stu-id="68c25-119">The storage dimension group determines which storage dimensions you must enter on each transaction for the product and how it will be tracked in inventory.</span></span>  
3. <span data-ttu-id="68c25-120">No campo Grupo de dimensões de rastreamento, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="68c25-120">In the Tracking dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="68c25-121">O grupo de dimensões de rastreamento determina quais dimensões de rastreamento você deve inserir em cada transação para o produto e como são lidadas no estoque.</span><span class="sxs-lookup"><span data-stu-id="68c25-121">The tracking dimension group determines which tracking dimensions you must enter for each transaction for the product, and how it will be handled in inventory.</span></span>  
4. <span data-ttu-id="68c25-122">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="68c25-122">Click OK.</span></span>


