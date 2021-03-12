---
title: Mapear uma dimensão do elemento de custo
description: Um controlador de custo pode usar esse procedimento para mapear uma dimensão do elemento de custo com uma dimensão do elemento de custo na entidade legal MXMF.
author: ShylaThompson
manager: AnnBe
ms.date: 06/28/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f5570d7cf2a8139d7959cb708d306e8b91065ed1
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4990658"
---
# <a name="map-a-cost-element-dimension"></a><span data-ttu-id="17b73-103">Mapear uma dimensão do elemento de custo</span><span class="sxs-lookup"><span data-stu-id="17b73-103">Map a cost element dimension</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="17b73-104">Um controlador de custo pode usar esse procedimento para mapear uma dimensão do elemento de custo com uma dimensão do elemento de custo na entidade legal MXMF.</span><span class="sxs-lookup"><span data-stu-id="17b73-104">A cost controller can use this procedure to map a cost element dimension to a cost element dimension in the MXMF legal entity.</span></span> <span data-ttu-id="17b73-105">Esta gravação usa os dados da empresa de demonstração USP2.</span><span class="sxs-lookup"><span data-stu-id="17b73-105">This recording uses the USP2 demo data company.</span></span>

1. <span data-ttu-id="17b73-106">Vá para Contabilização de custos > Dimensões > Dimensões do elemento de custo.</span><span class="sxs-lookup"><span data-stu-id="17b73-106">Go to Cost accounting > Dimensions > Cost element dimensions.</span></span>
2. <span data-ttu-id="17b73-107">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="17b73-107">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="17b73-108">Para este exemplo, selecione Elementos de custo.</span><span class="sxs-lookup"><span data-stu-id="17b73-108">For this example, select Cost elements.</span></span>  
3. <span data-ttu-id="17b73-109">Clique em Mapeamentos de dimensões.</span><span class="sxs-lookup"><span data-stu-id="17b73-109">Click Dimension mappings.</span></span>
4. <span data-ttu-id="17b73-110">Clique em Configurar mapeamentos desta dimensão.</span><span class="sxs-lookup"><span data-stu-id="17b73-110">Click Configure mappings from this dimension.</span></span>
5. <span data-ttu-id="17b73-111">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="17b73-111">Click New.</span></span>
6. <span data-ttu-id="17b73-112">No campo Dimensão de destino, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="17b73-112">In the To dimension field, enter or select a value.</span></span>
    * <span data-ttu-id="17b73-113">Neste exemplo, selecione Elementos de custo de MXMF.</span><span class="sxs-lookup"><span data-stu-id="17b73-113">For this example, select MXMF Cost elements.</span></span>  
7. <span data-ttu-id="17b73-114">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="17b73-114">Click New.</span></span>
8. <span data-ttu-id="17b73-115">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="17b73-115">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="17b73-116">No campo Membro da dimensão de origem, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="17b73-116">In the From dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="17b73-117">Neste exemplo, selecione custos com telefone e fax do membro da dimensão 606400.</span><span class="sxs-lookup"><span data-stu-id="17b73-117">For this example, select dimension member 606400 Telephone & Fax Expense.</span></span>  
10. <span data-ttu-id="17b73-118">No campo Membro da dimensão de destino, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="17b73-118">In the To dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="17b73-119">Neste exemplo, selecione telefone 6001004 de membro de dimensão.</span><span class="sxs-lookup"><span data-stu-id="17b73-119">For this example, select dimension member 6001004 Telefono.</span></span>  
11. <span data-ttu-id="17b73-120">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="17b73-120">Click Save.</span></span>

