--- 
title: Reclassificar ativos fixos
description: "Para reclassificar um ativo fixo, você deve transferi-lo para um novo grupo de ativos fixos ou atribuir a ele um novo número de ativo fixo no mesmo grupo."
author: saraschi2
manager: AnnBe
ms.date: 10/30/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 02afc142187aed55e5186d83069c5419fc900106
ms.contentlocale: pt-br
ms.lasthandoff: 05/08/2018

---
# <a name="reclassify-fixed-assets"></a><span data-ttu-id="07a71-103">Reclassificar ativos fixos</span><span class="sxs-lookup"><span data-stu-id="07a71-103">Reclassify fixed assets</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="07a71-104">Para reclassificar um ativo fixo, você deve transferi-lo para um novo grupo de ativos fixos ou atribuir a ele um novo número de ativo fixo no mesmo grupo.</span><span class="sxs-lookup"><span data-stu-id="07a71-104">To reclassify a fixed asset, you must transfer it to a new fixed asset group or assign a new fixed asset number to it in the same group.</span></span> 

<span data-ttu-id="07a71-105">Quando um ativo fixo é reclassificado:</span><span class="sxs-lookup"><span data-stu-id="07a71-105">When a fixed asset is reclassified:</span></span>

<span data-ttu-id="07a71-106">• Todos os métodos de depreciação do ativo fixo existente são criados para o novo ativo fixo.</span><span class="sxs-lookup"><span data-stu-id="07a71-106">• All value models for the existing fixed asset are created for the new fixed asset.</span></span> <span data-ttu-id="07a71-107">Todas as informações configuradas para o ativo fixo original são copiadas para o novo ativo fixo.</span><span class="sxs-lookup"><span data-stu-id="07a71-107">Any information that was set up for the original fixed asset is copied to the new fixed asset.</span></span> <span data-ttu-id="07a71-108">O status dos métodos de depreciação para o ativo fixo original é Fechado.</span><span class="sxs-lookup"><span data-stu-id="07a71-108">The status of the value models for the original fixed asset is Closed.</span></span> 

<span data-ttu-id="07a71-109">• Os novos modelos de valor do novo ativo fixo contêm a data da reclassificação no campo Data de aquisição.</span><span class="sxs-lookup"><span data-stu-id="07a71-109">• The new value models of the new fixed asset contain the date of the reclassification in the Acquisition date field.</span></span> <span data-ttu-id="07a71-110">A data indicada no campo Data de execução da depreciação é copiada das informações originais de ativo.</span><span class="sxs-lookup"><span data-stu-id="07a71-110">The date in the Depreciation run date field is copied from the original asset information.</span></span> <span data-ttu-id="07a71-111">Caso a depreciação já tenha sido iniciada, o campo Data da última depreciação exibirá a data da reclassificação.</span><span class="sxs-lookup"><span data-stu-id="07a71-111">If the depreciation has already started, the Date when depreciation was last run field displays the date of the reclassification.</span></span> 

<span data-ttu-id="07a71-112">• As transações de ativo fixo existentes para o ativo fixo original são canceladas e geradas novamente para o novo ativo fixo.</span><span class="sxs-lookup"><span data-stu-id="07a71-112">• The existing fixed asset transactions for the original fixed asset are canceled and regenerated for the new fixed asset.</span></span>

1. <span data-ttu-id="07a71-113">Vá para Ativos fixos > Tarefas periódicas > Reclassificação.</span><span class="sxs-lookup"><span data-stu-id="07a71-113">Go to Fixed assets > Periodic tasks > Reclassification.</span></span>
2. <span data-ttu-id="07a71-114">No campo Grupo de ativos fixos, selecione o grupo a ser reclassificado.</span><span class="sxs-lookup"><span data-stu-id="07a71-114">In the Fixed asset group field, select the group to reclassify.</span></span>
3. <span data-ttu-id="07a71-115">No campo Número do ativo fixo, selecione o ativo fixo a ser reclassificado.</span><span class="sxs-lookup"><span data-stu-id="07a71-115">In the Fixed asset number field, select the fixed asset to reclassify.</span></span>
4. <span data-ttu-id="07a71-116">No campo Novo grupo de ativos fixos, selecione um grupo para o qual deseja transferir o ativo fixo.</span><span class="sxs-lookup"><span data-stu-id="07a71-116">In the New fixed asset group field, select a group to transfer the fixed asset to.</span></span>
    * <span data-ttu-id="07a71-117">Se o novo grupo de ativos fixos estiver associado a uma sequência numérica, o campo Número do novo ativo fixo será atualizado com o número da nova sequência numérica do grupo de ativos fixos.</span><span class="sxs-lookup"><span data-stu-id="07a71-117">If the new fixed asset group is attached to a number sequence, the New fixed asset number field is updated with the number from the new fixed asset group number sequence.</span></span> <span data-ttu-id="07a71-118">Caso contrário, o campo Número do novo ativo fixo será atualizado com o número da sequência numérica que está configurada na página Parâmetros do ativo fixo.</span><span class="sxs-lookup"><span data-stu-id="07a71-118">Otherwise, the New fixed asset number field is updated with the number from the number sequence that is set up in the Fixed asset parameters page.</span></span> <span data-ttu-id="07a71-119">Se uma sequência numérica não estiver configurada na página Parâmetros do ativo fixo, insira um número no campo Número do novo ativo fixo.</span><span class="sxs-lookup"><span data-stu-id="07a71-119">If a number sequence is not set up in the Fixed asset parameters page, enter a number in the New fixed asset number field.</span></span>  
5. <span data-ttu-id="07a71-120">No campo Data de reclassificação, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="07a71-120">In the Reclassification date field, enter a date.</span></span>
6. <span data-ttu-id="07a71-121">No campo Série de comprovante, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="07a71-121">In the Voucher series field, enter or select a value.</span></span>
7. <span data-ttu-id="07a71-122">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="07a71-122">Click OK.</span></span>


