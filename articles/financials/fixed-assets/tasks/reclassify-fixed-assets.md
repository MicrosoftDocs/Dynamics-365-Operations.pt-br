---
title: Reclassificar ativos fixos
description: Para reclassificar um ativo fixo, você deve transferi-lo para um novo grupo de ativos fixos ou atribuir a ele um novo número de ativo fixo no mesmo grupo.
author: saraschi2
manager: AnnBe
ms.date: 05/14/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 47d8cf2ff1e275df0466a7fe327a3180c0399e49
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1839920"
---
# <a name="reclassify-fixed-assets"></a><span data-ttu-id="d4c7d-103">Reclassificar ativos fixos</span><span class="sxs-lookup"><span data-stu-id="d4c7d-103">Reclassify fixed assets</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="d4c7d-104">Para reclassificar um ativo fixo, você deve transferi-lo para um novo grupo de ativos fixos ou atribuir a ele um novo número de ativo fixo no mesmo grupo.</span><span class="sxs-lookup"><span data-stu-id="d4c7d-104">To reclassify a fixed asset, you must transfer it to a new fixed asset group or assign a new fixed asset number to it in the same group.</span></span> 

<span data-ttu-id="d4c7d-105">Quando um ativo fixo é reclassificado:</span><span class="sxs-lookup"><span data-stu-id="d4c7d-105">When a fixed asset is reclassified:</span></span>

<span data-ttu-id="d4c7d-106">• Todos os livros do ativo fixo existente são criados para o novo ativo fixo.</span><span class="sxs-lookup"><span data-stu-id="d4c7d-106">• All books for the existing fixed asset are created for the new fixed asset.</span></span> <span data-ttu-id="d4c7d-107">Todas as informações configuradas para o ativo fixo original são copiadas para o novo ativo fixo.</span><span class="sxs-lookup"><span data-stu-id="d4c7d-107">Any information that was set up for the original fixed asset is copied to the new fixed asset.</span></span> <span data-ttu-id="d4c7d-108">O status dos livros para o ativo fixo original é Fechado.</span><span class="sxs-lookup"><span data-stu-id="d4c7d-108">The status of the books for the original fixed asset is Closed.</span></span> 

<span data-ttu-id="d4c7d-109">• Os novos livros do novo ativo fixo contêm a data da reclassificação no campo **Data de aquisição**.</span><span class="sxs-lookup"><span data-stu-id="d4c7d-109">• The new books of the new fixed asset contain the date of the reclassification in the **Acquisition date** field.</span></span> <span data-ttu-id="d4c7d-110">A data indicada no campo **Data de execução da depreciação** é copiada das informações originais de ativo.</span><span class="sxs-lookup"><span data-stu-id="d4c7d-110">The date in the **Depreciation run date** field is copied from the original asset information.</span></span> <span data-ttu-id="d4c7d-111">Caso a depreciação já tenha sido iniciada, o campo **Data da última depreciação exibirá** a data da reclassificação.</span><span class="sxs-lookup"><span data-stu-id="d4c7d-111">If the depreciation has already started, the **Date when depreciation was last run** field displays the date of the reclassification.</span></span> 

<span data-ttu-id="d4c7d-112">• As transações de ativo fixo existentes para o ativo fixo original são canceladas e geradas novamente para o novo ativo fixo.</span><span class="sxs-lookup"><span data-stu-id="d4c7d-112">• The existing fixed asset transactions for the original fixed asset are canceled and regenerated for the new fixed asset.</span></span>

<span data-ttu-id="d4c7d-113">Siga essa etapas para reclassificar um ativo fixo:</span><span class="sxs-lookup"><span data-stu-id="d4c7d-113">Follow these steps to reclassify a fixed asset:</span></span>

1. <span data-ttu-id="d4c7d-114">Vá para **Ativos fixos > Tarefas periódicas > Reclassificação**.</span><span class="sxs-lookup"><span data-stu-id="d4c7d-114">Go to **Fixed assets > Periodic tasks > Reclassification.**</span></span>
2. <span data-ttu-id="d4c7d-115">No campo **Grupo de ativos fixos**, selecione o grupo a ser reclassificado.</span><span class="sxs-lookup"><span data-stu-id="d4c7d-115">In the **Fixed asset group** field, select the group to reclassify.</span></span>
3. <span data-ttu-id="d4c7d-116">No campo **Número do ativo fixo**, selecione o ativo fixo a ser reclassificado.</span><span class="sxs-lookup"><span data-stu-id="d4c7d-116">In the **Fixed asset number** field, select the fixed asset to reclassify.</span></span>
4. <span data-ttu-id="d4c7d-117">No campo **Novo grupo de ativos fixos**, selecione um grupo para o qual deseja transferir o ativo fixo.</span><span class="sxs-lookup"><span data-stu-id="d4c7d-117">In the **New fixed asset group** field, select a group to transfer the fixed asset to.</span></span>
    * <span data-ttu-id="d4c7d-118">Se o novo grupo de ativos fixos estiver associado a uma sequência numérica, o campo **Número do novo ativo fixo** será atualizado com o número da nova sequência numérica do grupo de ativos fixos.</span><span class="sxs-lookup"><span data-stu-id="d4c7d-118">If the new fixed asset group is attached to a number sequence, the **New fixed asset number** field is updated with the number from the new fixed asset group number sequence.</span></span> <span data-ttu-id="d4c7d-119">Caso contrário, o campo **Número do novo ativo fixo** será atualizado com o número da sequência numérica que está configurada na página **Parâmetros do ativo fixo**.</span><span class="sxs-lookup"><span data-stu-id="d4c7d-119">Otherwise, the **New fixed asset number** field is updated with the number from the number sequence that is set up on the **Fixed asset parameters** page.</span></span> <span data-ttu-id="d4c7d-120">Se uma sequência numérica não estiver configurada na página **Parâmetros do ativo fixo**, insira um número no campo **Número do novo ativo fixo**.</span><span class="sxs-lookup"><span data-stu-id="d4c7d-120">If a number sequence is not set up on the **Fixed asset parameters** page, enter a number in the **New fixed asset number** field.</span></span>  
5. <span data-ttu-id="d4c7d-121">No campo **Data de reclassificação**, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="d4c7d-121">In the **Reclassification date** field, enter a date.</span></span>
6. <span data-ttu-id="d4c7d-122">No campo **Série de comprovante**, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="d4c7d-122">In the **Voucher series** field, enter or select a value.</span></span>
7. <span data-ttu-id="d4c7d-123">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="d4c7d-123">Click **OK**.</span></span>
