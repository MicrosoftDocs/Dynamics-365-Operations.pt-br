---
title: "Depreciação extra"
description: "Este artigo fornece uma visão geral da funcionalidade de depreciações bônus."
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetBonus
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 3621
ms.assetid: 835ec594-744e-461c-a676-1b9abc094173
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 5e05c0c195ddb948547ae008d050686bbcdc6ed3
ms.contentlocale: pt-br
ms.lasthandoff: 08/07/2018

---

# <a name="bonus-depreciation"></a><span data-ttu-id="37f0e-103">Depreciação extra</span><span class="sxs-lookup"><span data-stu-id="37f0e-103">Bonus depreciation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="37f0e-104">Este artigo fornece uma visão geral da funcionalidade de depreciações bônus.</span><span class="sxs-lookup"><span data-stu-id="37f0e-104">This article provides an overview of the bonus depreciation functionality.</span></span>

<span data-ttu-id="37f0e-105">Com a depreciação extra, você pode obter valores de depreciação extra durante o primeiro ano em que o ativo é disponibilizado e depreciado.</span><span class="sxs-lookup"><span data-stu-id="37f0e-105">For bonus depreciation, you can take extra or bonus depreciation amounts during the first year that the asset is put in service and depreciated.</span></span> <span data-ttu-id="37f0e-106">A depreciação extra será obtida antes de qualquer outro cálculo de depreciação.</span><span class="sxs-lookup"><span data-stu-id="37f0e-106">Bonus depreciation must be taken before any other depreciation calculations.</span></span> <span data-ttu-id="37f0e-107">Portanto, é aconselhável usar a depreciação extra com registros que lançar à funcionalidade de contabilização está desabilitado.</span><span class="sxs-lookup"><span data-stu-id="37f0e-107">Therefore, it's best to use bonus depreciation with books where the Post to general ledger functionality is disabled.</span></span> <span data-ttu-id="37f0e-108">Você pode usar a opção **Transações de exclusão não lançadas na contabilidade** para excluir transações de histórico dos registros ainda não lançados na contabilidade.</span><span class="sxs-lookup"><span data-stu-id="37f0e-108">You can use the **Delete transactions not posted to general ledger** option to delete historical transactions for books that don't post to the general ledger.</span></span> <span data-ttu-id="37f0e-109">Você poderá então acomodar a depreciação extra posteriormente no ciclo de vida de ativo excluindo as transações de depreciação que foram lançadas anteriormente.</span><span class="sxs-lookup"><span data-stu-id="37f0e-109">You can then accommodate bonus depreciation later in the asset life cycle by deleting depreciation transactions that were previously posted.</span></span> 

<span data-ttu-id="37f0e-110">É possível calcular a depreciação extra usando o processo de proposta ou criar transações de depreciação extra manuais.</span><span class="sxs-lookup"><span data-stu-id="37f0e-110">You can calculate bonus depreciation by using the proposal process, or you can create manual bonus depreciation transactions.</span></span> <span data-ttu-id="37f0e-111">Você não pode criar transações de depreciação extra se existirem transações de depreciação ou transações de ajuste de depreciação para aquele registro de depreciações de ativo.</span><span class="sxs-lookup"><span data-stu-id="37f0e-111">You can't create bonus depreciation transactions if depreciation transactions or depreciation adjustment transactions exist for that asset book.</span></span>

<span data-ttu-id="37f0e-112">Quando você usa o processo de proposta para calcular a depreciação extra, todas as transações extras existentes são incluídas no cálculo base.</span><span class="sxs-lookup"><span data-stu-id="37f0e-112">When you use the proposal process to calculate bonus depreciation, all existing bonus transactions are included in the calculation of the basis.</span></span> <span data-ttu-id="37f0e-113">O cálculo também inclui todas as depreciações extras anteriores que tenham sido inseridas manualmente para o ativo.</span><span class="sxs-lookup"><span data-stu-id="37f0e-113">The calculation also includes any previous bonus depreciations that you manually entered for the asset.</span></span> 

<span data-ttu-id="37f0e-114">Se mais de uma depreciação extra for obtida para um ativo, a prioridade deverá ser levada em conta.</span><span class="sxs-lookup"><span data-stu-id="37f0e-114">If more than one bonus depreciation will be taken for an asset, the priority is considered.</span></span> <span data-ttu-id="37f0e-115">Cada extra reduz a base do ativo para o próximo extra.</span><span class="sxs-lookup"><span data-stu-id="37f0e-115">Each bonus reduces the asset basis for the next bonus.</span></span> <span data-ttu-id="37f0e-116">O valor residual não é considerado na base do ativo para cálculos de depreciação extra e a convenção de depreciação não se aplica à depreciação extra.</span><span class="sxs-lookup"><span data-stu-id="37f0e-116">Salvage value isn't considered in the asset basis for bonus depreciation calculations, and the depreciation convention doesn't apply for bonus depreciation.</span></span> 

<span data-ttu-id="37f0e-117">Atualmente, nos Estados Unidos, determinada propriedade qualifica-se como a propriedade da Seção 179.</span><span class="sxs-lookup"><span data-stu-id="37f0e-117">Currently, in the United States, some property qualifies as Section 179 property.</span></span> <span data-ttu-id="37f0e-118">Usando a dedução da seção 179, é possível recuperar todo ou parte do custo de determinada propriedade, até um limite.</span><span class="sxs-lookup"><span data-stu-id="37f0e-118">By using the Section 179 deduction, you can recover all or part of the cost of some property, up to a limit.</span></span> <span data-ttu-id="37f0e-119">É possível recuperar os custos deduzindo-os no ano em que você disponibilizar a propriedade.</span><span class="sxs-lookup"><span data-stu-id="37f0e-119">You can recover the cost by deducting it in the year when you put the property in service.</span></span>

## <a name="example"></a><span data-ttu-id="37f0e-120">Exemplo</span><span class="sxs-lookup"><span data-stu-id="37f0e-120">Example</span></span>
<span data-ttu-id="37f0e-121">As seguintes depreciações extras estão associadas a um registro de depreciações de ativo:</span><span class="sxs-lookup"><span data-stu-id="37f0e-121">The following bonus depreciations are associated with an asset book:</span></span>

-   <span data-ttu-id="37f0e-122">**Seção 179:** 1.000,00, Prioridade 1</span><span class="sxs-lookup"><span data-stu-id="37f0e-122">**Section 179:** 1,000.00, Priority 1</span></span>
-   <span data-ttu-id="37f0e-123">**Zona de liberdade:** 30%, Prioridade 2</span><span class="sxs-lookup"><span data-stu-id="37f0e-123">**Liberty Zone:** 30 percent, Priority 2</span></span>

<span data-ttu-id="37f0e-124">O custo de aquisição de ativo é US$ 5.000,00.</span><span class="sxs-lookup"><span data-stu-id="37f0e-124">The asset acquisition cost is 5,000.00.</span></span> <span data-ttu-id="37f0e-125">Quando a depreciação extra for calculada, o primeiro valor de depreciação extra será de US$ 1.000,00 para a depreciação da Seção 179.</span><span class="sxs-lookup"><span data-stu-id="37f0e-125">When bonus depreciation is calculated, the first bonus depreciation amount is 1,000.00 for the Section 179 depreciation.</span></span> 

<span data-ttu-id="37f0e-126">O próximo valor de depreciação extra, para a depreciação da Zona de Liberdade, será calculado da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="37f0e-126">The next bonus depreciation amount, for the Liberty Zone depreciation, is calculated as follows:</span></span> 

<span data-ttu-id="37f0e-127">Custo de aquisição – 1.000 (depreciação da Seção 179) × 30% = 1.200</span><span class="sxs-lookup"><span data-stu-id="37f0e-127">Acquisition cost – 1,000 (Section 179 depreciation) × 30 percent = 1,200</span></span> 

<span data-ttu-id="37f0e-128">Se o valor da depreciação extra for maior que o custo de aquisição pendente, o valor da depreciação extra será o resultado do cálculo da depreciação extra ou o custo de aquisição pendente, o que for menor.</span><span class="sxs-lookup"><span data-stu-id="37f0e-128">If the bonus depreciation amount is more than the remaining acquisition cost, the bonus depreciation amount is either the result of the bonus depreciation calculation or the remaining acquisition cost, whichever amount is less.</span></span> 

<span data-ttu-id="37f0e-129">Se o custo de aquisição pendente for 0 (zero) ou menos, as transações de depreciação extra não serão geradas.</span><span class="sxs-lookup"><span data-stu-id="37f0e-129">If the remaining acquisition cost is 0 (zero) or less, bonus depreciation transactions isn't generated.</span></span> 

<span data-ttu-id="37f0e-130">Quando a depreciação extra for calculada usando o processo de proposta, uma transação de depreciação extra será criada para todos os registros de depreciações extras aplicáveis, associados ao registro de depreciações do ativo.</span><span class="sxs-lookup"><span data-stu-id="37f0e-130">When bonus depreciation is calculated by using the proposal process, a bonus depreciation transaction is created for all applicable bonus depreciation records that are associated with the asset book.</span></span> 

<span data-ttu-id="37f0e-131">É possível criar um número ilimitado de registros de depreciação extra.</span><span class="sxs-lookup"><span data-stu-id="37f0e-131">You can create an unlimited number of bonus depreciation records.</span></span> <span data-ttu-id="37f0e-132">Depois de atribuí-los ao registro de depreciações de grupo de ativos, eles serão aplicados ao registro de depreciações de ativo.</span><span class="sxs-lookup"><span data-stu-id="37f0e-132">After you assign those records to the asset group book, they are applied to the asset book.</span></span> 

<span data-ttu-id="37f0e-133">A depreciação extra é inserida como uma porcentagem ou um valor fixo.</span><span class="sxs-lookup"><span data-stu-id="37f0e-133">Bonus depreciation is entered as either a percentage or a fixed amount.</span></span> <span data-ttu-id="37f0e-134">Quando você lançar propostas de depreciação, as transações de depreciação extra serão lançadas no registro de depreciações como transações separadas das transações de depreciação.</span><span class="sxs-lookup"><span data-stu-id="37f0e-134">When you post depreciation proposals, bonus depreciation transactions are posted to the book as separate transactions from the depreciation transactions.</span></span>




