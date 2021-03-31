---
title: Criar uma proposta de depreciação
description: Este tópico descreve como as propostas de depreciação em lote funcionam e explica como propor a depreciação para ativos fixos.
author: abruer
manager: AnnBe
ms.date: 08/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransAsset
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e4852b25ef628cdef6f75f6edf550c539e344a4b
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5227055"
---
# <a name="create-a-depreciation-proposal"></a><span data-ttu-id="21a59-103">Criar uma proposta de depreciação</span><span class="sxs-lookup"><span data-stu-id="21a59-103">Create a depreciation proposal</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="21a59-104">Este tópico descreve como as propostas de depreciação em lote funcionam e explica como propor a depreciação para ativos fixos.</span><span class="sxs-lookup"><span data-stu-id="21a59-104">This topic describes how depreciation batch proposals work and explains how to propose depreciation for fixed assets.</span></span> <span data-ttu-id="21a59-105">A empresa usa essa tarefa de demonstração de USMF e a função de contador.</span><span class="sxs-lookup"><span data-stu-id="21a59-105">This task uses the USMF demo company and the accountant role.</span></span>


## <a name="create-a-depreciation-proposal"></a><span data-ttu-id="21a59-106">Criar uma proposta de depreciação</span><span class="sxs-lookup"><span data-stu-id="21a59-106">Create a depreciation proposal</span></span>
1. <span data-ttu-id="21a59-107">No Painel de Navegação, vá para **Módulos > Ativos fixos > Entradas de diário > Criar proposta de depreciação**.</span><span class="sxs-lookup"><span data-stu-id="21a59-107">In the navigation pane, go to **Modules > Fixed assets > Journal entries > Create depreciation proposal**.</span></span>
2. <span data-ttu-id="21a59-108">No campo **Nome do diário**, selecione uma opção no menu suspenso.</span><span class="sxs-lookup"><span data-stu-id="21a59-108">In the **Name of journal** field, select an option from the drop-down menu.</span></span>
3. <span data-ttu-id="21a59-109">No campo **Data final**, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="21a59-109">In the **To date** field, enter a date.</span></span>

    - <span data-ttu-id="21a59-110">Selecione a opção **Resumir depreciação** para resumir as depreciações mensais em uma linha do diário.</span><span class="sxs-lookup"><span data-stu-id="21a59-110">Select the **Summarize depreciation** option to summarize monthly depreciations into one journal line.</span></span>  
    - <span data-ttu-id="21a59-111">Por exemplo, se o valor "Até" for 31 de março de 2015, a seguinte descrição será gerada: "Depreciação desde 31 de janeiro de 2015."</span><span class="sxs-lookup"><span data-stu-id="21a59-111">For example, if the To date value is March 31, 2015, the following description is generated: "Depreciation since January 31, 2015."</span></span> <span data-ttu-id="21a59-112">O campo **Data** nas linhas de diário propostas é então definido para 31 de março de 2015.</span><span class="sxs-lookup"><span data-stu-id="21a59-112">The **Date** field on the proposed journal lines is then set to March 31, 2015.</span></span>  
    - <span data-ttu-id="21a59-113">A proposta de depreciação pode ser filtrada por ativo, por grupo de ativos, ou por outros critérios usando a opção **Filtrar**.</span><span class="sxs-lookup"><span data-stu-id="21a59-113">The depreciation proposal can be filtered by asset, asset group, or other criteria using the **Filter** option.</span></span>  
    - <span data-ttu-id="21a59-114">Ao usar o formulário **Criar propostas de aquisição ou depreciação para ativos fixos**, é possível propor a depreciação em lotes.</span><span class="sxs-lookup"><span data-stu-id="21a59-114">When you use the **Create acquisition or depreciation proposals for fixed assets** form, you can propose depreciation in batches.</span></span> <span data-ttu-id="21a59-115">Isso é recomendado para as propostas maiores que usarão mais recursos do sistema.</span><span class="sxs-lookup"><span data-stu-id="21a59-115">This is recommended for larger proposals that will use more system resources.</span></span> <span data-ttu-id="21a59-116">Se você selecionar a opção de lote, você ainda poderá concluir outras tarefas durante esse período.</span><span class="sxs-lookup"><span data-stu-id="21a59-116">If you select the batch option, you can still complete other tasks during that time.</span></span> <span data-ttu-id="21a59-117">Ao propor a depreciação dessa forma, a depreciação é calculada para os modelos de depreciação para ativos fixos.</span><span class="sxs-lookup"><span data-stu-id="21a59-117">When you propose depreciation in this way, depreciation is calculated for value models for fixed assets.</span></span>  

4. <span data-ttu-id="21a59-118">Selecione **Criar diário**.</span><span class="sxs-lookup"><span data-stu-id="21a59-118">Select **Create journal**.</span></span>

## <a name="review-depreciation-entries"></a><span data-ttu-id="21a59-119">Entradas de depreciação de revisão</span><span class="sxs-lookup"><span data-stu-id="21a59-119">Review depreciation entries</span></span>
1. <span data-ttu-id="21a59-120">No Painel de navegação, vá para **Módulos > Ativos fixos > Entradas de diário > Diário de ativos fixos**.</span><span class="sxs-lookup"><span data-stu-id="21a59-120">In the navigation pane, go to **Modules > Fixed assets > Journal entries > Fixed assets journal**.</span></span>
2. <span data-ttu-id="21a59-121">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="21a59-121">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="21a59-122">Selecione **Linhas**.</span><span class="sxs-lookup"><span data-stu-id="21a59-122">Select **Lines**.</span></span>
4. <span data-ttu-id="21a59-123">Selecione **Lançar**.</span><span class="sxs-lookup"><span data-stu-id="21a59-123">Select **Post**.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]