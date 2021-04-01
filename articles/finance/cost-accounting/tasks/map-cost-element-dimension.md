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
ms.openlocfilehash: e48110182f79195483a0f54b7859ee0cd54e8cf0
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5235828"
---
# <a name="map-a-cost-element-dimension"></a><span data-ttu-id="8b26e-103">Mapear uma dimensão do elemento de custo</span><span class="sxs-lookup"><span data-stu-id="8b26e-103">Map a cost element dimension</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="8b26e-104">Um controlador de custo pode usar esse procedimento para mapear uma dimensão do elemento de custo com uma dimensão do elemento de custo na entidade legal MXMF.</span><span class="sxs-lookup"><span data-stu-id="8b26e-104">A cost controller can use this procedure to map a cost element dimension to a cost element dimension in the MXMF legal entity.</span></span> <span data-ttu-id="8b26e-105">Esta gravação usa os dados da empresa de demonstração USP2.</span><span class="sxs-lookup"><span data-stu-id="8b26e-105">This recording uses the USP2 demo data company.</span></span>

1. <span data-ttu-id="8b26e-106">Vá para Contabilização de custos > Dimensões > Dimensões do elemento de custo.</span><span class="sxs-lookup"><span data-stu-id="8b26e-106">Go to Cost accounting > Dimensions > Cost element dimensions.</span></span>
2. <span data-ttu-id="8b26e-107">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="8b26e-107">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="8b26e-108">Para este exemplo, selecione Elementos de custo.</span><span class="sxs-lookup"><span data-stu-id="8b26e-108">For this example, select Cost elements.</span></span>  
3. <span data-ttu-id="8b26e-109">Clique em Mapeamentos de dimensões.</span><span class="sxs-lookup"><span data-stu-id="8b26e-109">Click Dimension mappings.</span></span>
4. <span data-ttu-id="8b26e-110">Clique em Configurar mapeamentos desta dimensão.</span><span class="sxs-lookup"><span data-stu-id="8b26e-110">Click Configure mappings from this dimension.</span></span>
5. <span data-ttu-id="8b26e-111">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="8b26e-111">Click New.</span></span>
6. <span data-ttu-id="8b26e-112">No campo Dimensão de destino, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="8b26e-112">In the To dimension field, enter or select a value.</span></span>
    * <span data-ttu-id="8b26e-113">Neste exemplo, selecione Elementos de custo de MXMF.</span><span class="sxs-lookup"><span data-stu-id="8b26e-113">For this example, select MXMF Cost elements.</span></span>  
7. <span data-ttu-id="8b26e-114">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="8b26e-114">Click New.</span></span>
8. <span data-ttu-id="8b26e-115">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="8b26e-115">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="8b26e-116">No campo Membro da dimensão de origem, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="8b26e-116">In the From dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="8b26e-117">Neste exemplo, selecione custos com telefone e fax do membro da dimensão 606400.</span><span class="sxs-lookup"><span data-stu-id="8b26e-117">For this example, select dimension member 606400 Telephone & Fax Expense.</span></span>  
10. <span data-ttu-id="8b26e-118">No campo Membro da dimensão de destino, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="8b26e-118">In the To dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="8b26e-119">Neste exemplo, selecione telefone 6001004 de membro de dimensão.</span><span class="sxs-lookup"><span data-stu-id="8b26e-119">For this example, select dimension member 6001004 Telefono.</span></span>  
11. <span data-ttu-id="8b26e-120">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="8b26e-120">Click Save.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]