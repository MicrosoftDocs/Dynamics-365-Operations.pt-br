--- 
title: Criar um estado do ciclo de vida do produto para excluir produtos do Planejamento mestre
description: "Este procedimento mostra como criar um novo estado do ciclo de vida do produto que exclua os produtos do Planejamento mestre e do cálculo do nível da BOM."
author: cvocph
manager: AnnBe
ms.date: 12/05/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 156972cdbf4ffb02b01b00972cc83d003d941378
ms.contentlocale: pt-br
ms.lasthandoff: 08/07/2018

---
# <a name="create-a-product-lifecycle-state-to-exclude-products-from-master-planning"></a><span data-ttu-id="c9692-103">Criar um estado do ciclo de vida do produto para excluir produtos do Planejamento mestre</span><span class="sxs-lookup"><span data-stu-id="c9692-103">Create a product lifecycle state to exclude products from Master planning</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="c9692-104">Este procedimento mostra como criar um novo estado do ciclo de vida do produto que exclua os produtos do Planejamento mestre e do cálculo do nível da BOM.</span><span class="sxs-lookup"><span data-stu-id="c9692-104">This procedure shows how to create a new product lifecycle state that excludes the products from Master planning and BOM-level calculation.</span></span>


## <a name="create-an-obsolete-state"></a><span data-ttu-id="c9692-105">Crie um estado obsoleto</span><span class="sxs-lookup"><span data-stu-id="c9692-105">Create an obsolete state</span></span>
1. <span data-ttu-id="c9692-106">Vá para Gerenciamento de informações de produto > Configuração > Estado do ciclo de vida do produto.</span><span class="sxs-lookup"><span data-stu-id="c9692-106">Go to Product information management > Setup > Product lifecycle state.</span></span>
2. <span data-ttu-id="c9692-107">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="c9692-107">Click New.</span></span>
3. <span data-ttu-id="c9692-108">No campo Estado, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="c9692-108">In the State field, type a value.</span></span>
4. <span data-ttu-id="c9692-109">Selecione Não no campo Está ativo para planejar.</span><span class="sxs-lookup"><span data-stu-id="c9692-109">Select No in the Is active for planning field.</span></span>
5. <span data-ttu-id="c9692-110">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="c9692-110">In the Description field, type a value.</span></span>

## <a name="associate-the-obsolete-state-to-a-released-product"></a><span data-ttu-id="c9692-111">Associe o estado obsoleto a um produto liberado</span><span class="sxs-lookup"><span data-stu-id="c9692-111">Associate the obsolete state to a released product</span></span>
1. <span data-ttu-id="c9692-112">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="c9692-112">Close the page.</span></span>
2. <span data-ttu-id="c9692-113">Vá para Gerenciamento de informações do produto > Produtos > Produtos liberados.</span><span class="sxs-lookup"><span data-stu-id="c9692-113">Go to Product information management > Products > Released products.</span></span>
3. <span data-ttu-id="c9692-114">Use o Filtro Rápido para localizar registros.</span><span class="sxs-lookup"><span data-stu-id="c9692-114">Use the Quick Filter to find records.</span></span> <span data-ttu-id="c9692-115">Por exemplo, filtre o campo Nome de pesquisa com um valor de 'M00'.</span><span class="sxs-lookup"><span data-stu-id="c9692-115">For example, filter on the Search name field with a value of 'M00'.</span></span>
4. <span data-ttu-id="c9692-116">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="c9692-116">Click Edit.</span></span>
5. <span data-ttu-id="c9692-117">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="c9692-117">In the list, mark the selected row.</span></span>
6. <span data-ttu-id="c9692-118">No campo Estado do ciclo de vida do produto, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="c9692-118">In the Product lifecycle state field, enter or select a value.</span></span>


