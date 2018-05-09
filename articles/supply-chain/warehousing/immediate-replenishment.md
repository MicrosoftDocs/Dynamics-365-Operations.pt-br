---
title: Reabastecimento imediato
description: "Este tópico descreve como você pode usar o reabastecimento imediato para reabastecer o estoque quando uma diretiva de local não atribua o estoque."
author: Mirzaab
manager: AnnBe
ms.date: 03/15/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WHSLocDirTable
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.custom: 1705903
ms.assetid: 427e01b3-4968-4cff-9b85-1717530f72e4
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 8.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 1f24ffbba0c28b241de66f484546844bc72b90c9
ms.contentlocale: pt-br
ms.lasthandoff: 05/08/2018

---

# <a name="immediate-replenishment"></a><span data-ttu-id="55d44-103">Reabastecimento imediato</span><span class="sxs-lookup"><span data-stu-id="55d44-103">Immediate replenishment</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="55d44-104">O reabastecimento imediato permite a você reabastecer o estoque imediatamente após uma linha de diretiva de local falhe ao alocar o estoque.</span><span class="sxs-lookup"><span data-stu-id="55d44-104">Immediate replenishment lets you replenish inventory immediately after a location directive line fails to allocate inventory.</span></span> <span data-ttu-id="55d44-105">O reabastecimento se baseia em uma única linha na configuração da diretiva de local.</span><span class="sxs-lookup"><span data-stu-id="55d44-105">The replenishment is based on a single line in the setup of the location directive.</span></span> <span data-ttu-id="55d44-106">Se o estoque não estiver disponível na unidade de medida especificada por essa linha, o reabastecimento da unidade de medida ocorrerá imediatamente.</span><span class="sxs-lookup"><span data-stu-id="55d44-106">If inventory isn't on hand in the unit of measure that is specified by that line, replenishment of that unit of measure occurs immediately.</span></span>

<span data-ttu-id="55d44-107">O reabastecimento imediato fornece uma alternativa ao método em que alocação de estoque se baseia em mais linhas na diretiva de local, onde a demanda é resumida no final da alocação e reabastecida na unidade de medida especificada pela última linha na diretiva de local.</span><span class="sxs-lookup"><span data-stu-id="55d44-107">Immediate replenishment provides an alternative to the method where the allocation of inventory is based on more lines in the location directive, and where the demand is summed at the end of the allocation and replenished in the unit of measure that is specified by the last line in the location directive.</span></span>

<span data-ttu-id="55d44-108">Os benefícios de usar o reabastecimento imediato são o reabastecimento poder ser limitado por unidades específicas e a quantidade pode ser direcionada para locais específicos.</span><span class="sxs-lookup"><span data-stu-id="55d44-108">The benefits of using immediate replenishment are that replenishment can be limited by specific units and the quantity can be directed to specific locations.</span></span>

## <a name="business-scenario"></a><span data-ttu-id="55d44-109">Cenário de negócios</span><span class="sxs-lookup"><span data-stu-id="55d44-109">Business scenario</span></span>

<span data-ttu-id="55d44-110">Por exemplo, você tem um depósito com áreas de separação separadas para as unidades de medida "caixa" e "cada".</span><span class="sxs-lookup"><span data-stu-id="55d44-110">For example, you have a warehouse that has separate picking areas for the "box" and "each" units of measure.</span></span> <span data-ttu-id="55d44-111">Você deseja otimizar o processo de separação ao separar o máximo de caixas possível e ao escolher qualquer quantidade pendente inferior a uma caixa na área "cada".</span><span class="sxs-lookup"><span data-stu-id="55d44-111">You want to optimize the picking process by picking as many boxes as possible and then picking any remaining quantity that is less than a box from the "each" area.</span></span>

<span data-ttu-id="55d44-112">Nesse caso, você pode usar o reabastecimento imediato.</span><span class="sxs-lookup"><span data-stu-id="55d44-112">In this case, you can use immediate replenishment.</span></span> <span data-ttu-id="55d44-113">Na diretiva de local, você pode configurar o reabastecimento imediato para caixas de modo que o reabastecimento de demanda seja usado assim que houver uma escassez caixas que podem ser escolhidas para a quantidade de demanda.</span><span class="sxs-lookup"><span data-stu-id="55d44-113">In the location directive, you can set up immediate replenishment for boxes so that demand replenishment is used as soon as there is a shortage of boxes that can be picked for the demand quantity.</span></span> <span data-ttu-id="55d44-114">Assim, você otimiza o processo de separação de forma que a separação inclua o máximo de caixas possível.</span><span class="sxs-lookup"><span data-stu-id="55d44-114">In this way, you optimize the picking process so that picking includes as many boxes as possible.</span></span> <span data-ttu-id="55d44-115">O reabastecimento imediato gerará o reabastecimento das caixas, e a demanda não será passada, de forma que as quantidades são separadas na unidade de medida "cada".</span><span class="sxs-lookup"><span data-stu-id="55d44-115">Immediate replenishment will generate replenishment of the boxes, and the demand won't be passed on so that the quantities are picked in the "each" unit of measure.</span></span> <span data-ttu-id="55d44-116">Ou seja, somente as quantidades que devem ser separadas na unidade de medida "cada" (isto é, as quantidades inferiores a uma caixa) serão separadas da área "cada".</span><span class="sxs-lookup"><span data-stu-id="55d44-116">In other words, only the quantities that are supposed to be picked in the "each" unit of measure (that is, quantities that are less than a box) will be picked from the "each" area.</span></span> <span data-ttu-id="55d44-117">Se ocorre escassez na área "caixa", você poderá separar o máximo de caixas possível da demanda total.</span><span class="sxs-lookup"><span data-stu-id="55d44-117">If a shortage occurs in the "box" area, you can pick as many boxes as possible out of the total demand.</span></span> <span data-ttu-id="55d44-118">As quantidades restantes serão separadas da área "cada".</span><span class="sxs-lookup"><span data-stu-id="55d44-118">The remaining quantities will then be picked from the "each" area.</span></span>

## <a name="where-it-applies"></a><span data-ttu-id="55d44-119">Aplica-se a</span><span class="sxs-lookup"><span data-stu-id="55d44-119">Where it applies</span></span>

<span data-ttu-id="55d44-120">O reabastecimento imediato é usado durante a execução de onda se a alocação falhar para uma linha de diretiva de local para a qual um modelo de reabastecimento está definido.</span><span class="sxs-lookup"><span data-stu-id="55d44-120">Immediate replenishment is used during wave execution if allocation fails for a location directive line that a replenishment template is set for.</span></span>

## <a name="set-up-immediate-replenishment"></a><span data-ttu-id="55d44-121">Configurar o reabastecimento imediato</span><span class="sxs-lookup"><span data-stu-id="55d44-121">Set up immediate replenishment</span></span>

- <span data-ttu-id="55d44-122">Vá para **Gerenciamento de depósito** \> **Configuração** \> **Diretivas de local** e, então, na guia **Linhas** , na lista **Modelo de reabastecimento imediato**, selecione um modelo de reabastecimento para demanda da onda.</span><span class="sxs-lookup"><span data-stu-id="55d44-122">Go to **Warehouse management** \> **Setup** \> **Location directives**, and then, on the **Lines** tab, in the **Immediate replenishment template** list, select a replenishment template for wave demand.</span></span>

<span data-ttu-id="55d44-123">O modelo de reabastecimento só será aplicado se a linha de diretiva de local falhar ao alocar uma unidade de medida dedicada.</span><span class="sxs-lookup"><span data-stu-id="55d44-123">The replenishment template is applied if the location directive line fails to allocate a dedicated unit of measure.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="55d44-124">Solução de problemas</span><span class="sxs-lookup"><span data-stu-id="55d44-124">Troubleshooting</span></span>

<span data-ttu-id="55d44-125">Se o reabastecimento imediato estiver selecionado para uma linha de diretiva de local, mas se nenhum trabalho de reabastecimento for gerado quando você usar os modelos de reabastecimento de demanda para essa linha de diretiva de local, duas causas principais deverão ser investigadas:</span><span class="sxs-lookup"><span data-stu-id="55d44-125">If immediate replenishment is selected for a location directive line, but no replenishment work is generated when you use demand replenishment templates for that location directive line, two main causes must be investigated:</span></span>

- <span data-ttu-id="55d44-126">Verifique se o modelo de reabastecimento de demanda aplicado foi configurado para usar os modelos de local e de trabalho corretos do tipo **Reabastecimento**.</span><span class="sxs-lookup"><span data-stu-id="55d44-126">Make sure that the demand replenishment template that is applied is set up to use the correct location templates and work templates of the **Replenishment** type.</span></span>
- <span data-ttu-id="55d44-127">Verifique se há estoque disponível suficiente nos locais onde o modelo de reabastecimento de demanda procura estoque disponível para reabastecimento.</span><span class="sxs-lookup"><span data-stu-id="55d44-127">Make sure that there is enough on-hand inventory at the locations where the demand replenishment template searches for on-hand inventory for replenishment.</span></span>

