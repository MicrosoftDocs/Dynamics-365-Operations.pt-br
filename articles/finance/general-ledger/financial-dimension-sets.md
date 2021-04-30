---
title: Conjuntos de dimensões financeiras
description: Este tópico descreve os conjuntos de dimensões financeiras e fornece algumas dicas para otimizar o uso.
author: yukonpeegs
manager: AnnBe
ms.date: 03/23/2021
ms.topic: article
ems.prod: ''
ms.technology: ''
ms.search.form: DimensionFocus, LedgerTrialBalanceListPage
audience: Application User
ms.reviewer: roschlom
ms.custom: 25871
ms.search.region: Global
ms.author: epegors
ms.search.validFrom: 2021-03-23
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: b719d8eb868cb1722b470be4443d01181078ce21
ms.sourcegitcommit: 97ada5d52ed1829dcf030dad254096cd8df25da8
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/06/2021
ms.locfileid: "5864403"
---
# <a name="financial-dimension-sets"></a><span data-ttu-id="31577-103">Conjuntos de dimensões financeiras</span><span class="sxs-lookup"><span data-stu-id="31577-103">Financial dimension sets</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="31577-104">Este tópico descreve os conjuntos de dimensões financeiras e fornece algumas dicas para otimizar o uso.</span><span class="sxs-lookup"><span data-stu-id="31577-104">This topic describes financial dimension sets and provides some tips for optimizing their use.</span></span>

<span data-ttu-id="31577-105">Um conjunto de dimensões é uma lista ordenada de dimensões financeiras que podem ser usadas para resumir os dados da contabilidade de forma definida pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="31577-105">A dimension set is an ordered list of financial dimensions that can be used to summarize General ledger data in a user-defined way.</span></span> <span data-ttu-id="31577-106">Um uso principal de conjuntos de dimensões é definir um balancete.</span><span class="sxs-lookup"><span data-stu-id="31577-106">A primary use of dimension sets is to define a trial balance.</span></span>

<span data-ttu-id="31577-107">O único conjunto de dimensões padrão é o conjunto de dimensões que contém somente a conta principal.</span><span class="sxs-lookup"><span data-stu-id="31577-107">The only standard dimension set is the dimension set that contains only the main account.</span></span>

<span data-ttu-id="31577-108">Use a página **Conjuntos de dimensões financeiras** para criar e gerenciar conjuntos de dimensões financeiras.</span><span class="sxs-lookup"><span data-stu-id="31577-108">You use the **Financial dimension sets** page to create and manage financial dimension sets.</span></span>

## <a name="dimension-set-balances"></a><span data-ttu-id="31577-109">Saldos do conjunto de dimensões</span><span class="sxs-lookup"><span data-stu-id="31577-109">Dimension set balances</span></span>

<span data-ttu-id="31577-110">Um conjunto de dimensões pode ter saldos baseados em dimensões financeiras.</span><span class="sxs-lookup"><span data-stu-id="31577-110">A dimension set can have balances that are based on its financial dimensions.</span></span> <span data-ttu-id="31577-111">Os saldos existem na contabilidade e se baseiam na definição do conjunto de dimensões.</span><span class="sxs-lookup"><span data-stu-id="31577-111">The balances exist in General ledger and are based on the dimension set definition.</span></span> <span data-ttu-id="31577-112">Os saldos são resumidos a partir dos dados da contabilidade para ajudar a melhorar o desempenho quando são recuperados (por exemplo, quando um balancete é gerado).</span><span class="sxs-lookup"><span data-stu-id="31577-112">The balances are summarized from the General ledger data to help improve performance when they are retrieved (for example, when a trial balance is generated).</span></span>

## <a name="create-balances"></a><span data-ttu-id="31577-113">Criar saldos</span><span class="sxs-lookup"><span data-stu-id="31577-113">Create balances</span></span>

<span data-ttu-id="31577-114">Use o botão **Criar saldos** para inicializar os saldos para um conjunto de dimensões sem saldos no momento.</span><span class="sxs-lookup"><span data-stu-id="31577-114">Use the **Create balances** button to initialize the balances for a dimension set that doesn't currently have balances.</span></span>

> [!NOTE]
> <span data-ttu-id="31577-115">É recomendável limitar o número de conjuntos de dimensões que têm saldos, pois as atualizações de saldo afetam todas as atividades lançamento de contabilidade.</span><span class="sxs-lookup"><span data-stu-id="31577-115">We recommend that you limit the number of dimension sets that have balances, because balance updates affect all General ledger posting activities.</span></span>

## <a name="update-balances"></a><span data-ttu-id="31577-116">Atualizar saldos</span><span class="sxs-lookup"><span data-stu-id="31577-116">Update balances</span></span>

<span data-ttu-id="31577-117">Use o botão **Atualizar saldos** para incluir a atividade de lançamento de contabilidade mais recente nos saldos.</span><span class="sxs-lookup"><span data-stu-id="31577-117">Use the **Update balances** button to include the latest General ledger posting activity in the balances.</span></span> <span data-ttu-id="31577-118">As atualizações de saldo são operações leves.</span><span class="sxs-lookup"><span data-stu-id="31577-118">Balance updates are light operations.</span></span> <span data-ttu-id="31577-119">Elas devem processar somente a atividade de lançamento de contabilidade que ocorreu desde a última atualização.</span><span class="sxs-lookup"><span data-stu-id="31577-119">They must process only the General ledger posting activity that has occurred since the last update.</span></span>

> [!NOTE]
> <span data-ttu-id="31577-120">A exibição do balancete força uma atualização a garantir que os saldos mostrados sejam atuais.</span><span class="sxs-lookup"><span data-stu-id="31577-120">Display of the trial balance forces an update, to ensure that the balances that are shown are current.</span></span> <span data-ttu-id="31577-121">Considere o uso de um trabalho em lotes recorrente para que as atualizações dos conjuntos de dimensões usados com mais frequência sejam rápidas.</span><span class="sxs-lookup"><span data-stu-id="31577-121">Consider using a recurring batch job so that updates to your most frequently used dimension sets are quick.</span></span> <span data-ttu-id="31577-122">Dessa forma, você ajuda a minimizar o tempo de espera de usuários do balancete.</span><span class="sxs-lookup"><span data-stu-id="31577-122">In this way, you help minimize the time that trial balance users must wait.</span></span>

## <a name="rebuild-balances"></a><span data-ttu-id="31577-123">Reconstruir saldos</span><span class="sxs-lookup"><span data-stu-id="31577-123">Rebuild balances</span></span>

<span data-ttu-id="31577-124">Use o botão **Recriar saldos** para recriar os saldos desde o início.</span><span class="sxs-lookup"><span data-stu-id="31577-124">Use the **Rebuild balances** button to re-create the balances from scratch.</span></span> <span data-ttu-id="31577-125">Dessa forma, você ajuda a garantir que eles correspondam aos dados na contabilidade.</span><span class="sxs-lookup"><span data-stu-id="31577-125">In this way, you help ensure that they match the data in General ledger.</span></span> <span data-ttu-id="31577-126">Uma recriação de saldos exige muito processamento e geralmente não deve ser necessária.</span><span class="sxs-lookup"><span data-stu-id="31577-126">A rebuild of balances requires lots of processing and should not usually be required.</span></span>

> [!NOTE]
> <span data-ttu-id="31577-127">Se você tiver um cenário que exija regularmente uma recriação de saldos, será recomendável falar com o suporte ao cliente.</span><span class="sxs-lookup"><span data-stu-id="31577-127">If you have a scenario that regularly requires a rebuild of balances, we recommend that you contact customer support.</span></span> <span data-ttu-id="31577-128">O suporte ao cliente pode ajudá-lo a determinar por que os saldos não correspondem aos dados na contabilidade.</span><span class="sxs-lookup"><span data-stu-id="31577-128">Customer support can help you determine why balances don't match the data in General ledger.</span></span>

## <a name="clear-balances"></a><span data-ttu-id="31577-129">Limpar saldos</span><span class="sxs-lookup"><span data-stu-id="31577-129">Clear balances</span></span>

<span data-ttu-id="31577-130">Use o botão **Limpar saldos** para remover os saldos e interromper atualizações adicionais.</span><span class="sxs-lookup"><span data-stu-id="31577-130">Use the **Clear balances** button to remove the balances and stop any further updates.</span></span> <span data-ttu-id="31577-131">O conjunto de dimensões não terá mais impacto nas atividades de lançamento da contabilidade.</span><span class="sxs-lookup"><span data-stu-id="31577-131">The dimension set will no longer have an impact on General ledger posting activities.</span></span>

<span data-ttu-id="31577-132">Para obter mais informações, consulte [Dimensões financeiras](financial-dimensions.md).</span><span class="sxs-lookup"><span data-stu-id="31577-132">For more information, see [Financial dimensions](financial-dimensions.md).</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
