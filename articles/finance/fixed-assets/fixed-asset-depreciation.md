---
title: Depreciação de ativo fixo
description: Este tópico oferece uma visão geral da depreciação de ativos fixos.
author: ShylaThompson
manager: AnnBe
ms.date: 10/30/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetBonus, AssetBookTable
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 3121
ms.assetid: 98ff891f-e0e2-4184-b618-28107a50851f
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1056dadab4294072cc064670f5cfcda239e22e19
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2176399"
---
# <a name="fixed-asset-depreciation"></a><span data-ttu-id="57283-103">Depreciação de ativo fixo</span><span class="sxs-lookup"><span data-stu-id="57283-103">Fixed asset depreciation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="57283-104">Este tópico oferece uma visão geral da depreciação de ativos fixos.</span><span class="sxs-lookup"><span data-stu-id="57283-104">This topic provides an overview of depreciation for fixed assets.</span></span>

<span data-ttu-id="57283-105">Depreciação é uma transação periódica que normalmente reduz o valor do ativo fixo no balanço e é cobrada como uma despesa em uma conta de lucros e perdas.</span><span class="sxs-lookup"><span data-stu-id="57283-105">Depreciation is a periodic transaction that typically reduces the value of the fixed asset on the balance sheet, and is charged as an expenditure to a profit and loss account.</span></span> <span data-ttu-id="57283-106">Portanto, uma conta principal é geralmente usada para creditar a depreciação periódica no balanço.</span><span class="sxs-lookup"><span data-stu-id="57283-106">Therefore, a main account is typically used to credit the periodic depreciation on the balance sheet.</span></span> <span data-ttu-id="57283-107">Contrapartida é uma conta na parte de lucros e perdas do plano de contas.</span><span class="sxs-lookup"><span data-stu-id="57283-107">An offset account is an account in the profit and loss part of the chart of accounts.</span></span>

## <a name="depreciation-adjustment"></a><span data-ttu-id="57283-108">Ajuste de depreciação</span><span class="sxs-lookup"><span data-stu-id="57283-108">Depreciation adjustment</span></span>
<span data-ttu-id="57283-109">Normalmente, apenas uma correção para uma transação de depreciação já lançada é lançada como sendo um ajuste de depreciação.</span><span class="sxs-lookup"><span data-stu-id="57283-109">Usually, only a correction to a posted depreciation transaction is posted as a depreciation adjustment.</span></span> <span data-ttu-id="57283-110">Portanto, a conta principal e a contrapartida são configuradas como as contas para depreciação.</span><span class="sxs-lookup"><span data-stu-id="57283-110">Therefore, both the main account and the offset account are set up just like the accounts for depreciation.</span></span> <span data-ttu-id="57283-111">Um ajuste de depreciação pode ser um valor positivo ou negativo, embora a funcionalidade da conta principal (como conta do balanço) e da contrapartida (normalmente, como conta de lucros e perdas) permaneça a mesma.</span><span class="sxs-lookup"><span data-stu-id="57283-111">A depreciation adjustment can be either a positive amount or a negative amount, but the functionality of the main account (as a balance sheet account) and the functionality of the offset account (usually as a profit and loss account) remain the same.</span></span>

## <a name="extraordinary-depreciation"></a><span data-ttu-id="57283-112">Depreciação extraordinária</span><span class="sxs-lookup"><span data-stu-id="57283-112">Extraordinary depreciation</span></span>
<span data-ttu-id="57283-113">A depreciação extraordinária funciona independentemente da depreciação básica.</span><span class="sxs-lookup"><span data-stu-id="57283-113">Extraordinary depreciation works like basic depreciation.</span></span> <span data-ttu-id="57283-114">Portanto, uma conta principal é usada para creditar o valor de depreciação para o saldo e reduzir o valor do ativo fixo.</span><span class="sxs-lookup"><span data-stu-id="57283-114">Therefore, a main account is used to credit the depreciation amount to the balance sheet and reduce the value of the fixed asset.</span></span> <span data-ttu-id="57283-115">Contrapartida é uma conta de lucros e perdas, na qual a depreciação calculada para o período fiscal é cobrada como uma despesa.</span><span class="sxs-lookup"><span data-stu-id="57283-115">An offset account is a profit and loss account, where the depreciation that is calculated for the fiscal period is charged as an expenditure.</span></span> 

<span data-ttu-id="57283-116">A depreciação extraordinária funciona independentemente da depreciação básica.</span><span class="sxs-lookup"><span data-stu-id="57283-116">Extraordinary depreciation works independently of basic depreciation.</span></span> <span data-ttu-id="57283-117">Ter uma depreciação extraordinária como um tipo de transação separado permite que você lance e informe a depreciação extraordinária separadamente da depreciação básica.</span><span class="sxs-lookup"><span data-stu-id="57283-117">By having extraordinary depreciation as a separate transaction type, you can post and report the extraordinary depreciation separately from the basic depreciation.</span></span>

## <a name="special-depreciation-allowance"></a><span data-ttu-id="57283-118">Provisão para depreciação especial</span><span class="sxs-lookup"><span data-stu-id="57283-118">Special depreciation allowance</span></span>
<span data-ttu-id="57283-119">É possível usar a depreciação de provisão especial para obter valores de depreciação extra durante o primeiro ano em que um ativo é disponibilizado e depreciado.</span><span class="sxs-lookup"><span data-stu-id="57283-119">You can use special depreciation allowances to take extra depreciation amounts during the first year that an asset is put in service and depreciated.</span></span> <span data-ttu-id="57283-120">Provisão para depreciação especial deve ser obtida antes de qualquer outro cálculo de depreciação.</span><span class="sxs-lookup"><span data-stu-id="57283-120">Special depreciation allowances must be taken before any other depreciation calculations.</span></span> <span data-ttu-id="57283-121">Porque as provisões de depreciação especial seja geralmente desconhecidas até posteriormente na vida útil do ativo fixo, é aconselhável usar este tipo de depreciação a um registro de não lançar na contabilidade.</span><span class="sxs-lookup"><span data-stu-id="57283-121">Because special depreciation allowances are often unknown until later in the service life of the fixed asset, it's best to use this type of depreciation with a book that doesn't post to the general ledger.</span></span> <span data-ttu-id="57283-122">Você pode usar a opção Transações de exclusão não lançadas na contabilidade para excluir transações de histórico dos registros ainda não lançados na contabilidade.</span><span class="sxs-lookup"><span data-stu-id="57283-122">You can use the Delete transactions not posted to general ledger periodic function to delete the transaction history for these books.</span></span> <span data-ttu-id="57283-123">Você poderá excluir o histórico do registro de ativos, lançar a provisão para depreciação especial quando soube, e lançá-los nas outras transações de depreciação para o ano.</span><span class="sxs-lookup"><span data-stu-id="57283-123">You can then delete the depreciation history for the fixed asset book, post the special depreciation allowance when it's known, and then post the remaining depreciation transactions for the year.</span></span> 

<span data-ttu-id="57283-124">É possível criar um número ilimitado de registros de depreciação de provisão especial.</span><span class="sxs-lookup"><span data-stu-id="57283-124">You can create an unlimited number of special depreciation allowance records.</span></span> <span data-ttu-id="57283-125">Depois de atribuí-los ao registro de depreciações de grupo de ativos, eles serão aplicados ao registro de depreciações de ativo.</span><span class="sxs-lookup"><span data-stu-id="57283-125">After you assign those records to an asset group book, they are applied to the asset book.</span></span> 

<span data-ttu-id="57283-126">A depreciação de provisão especial é inserida como uma porcentagem ou um valor fixo.</span><span class="sxs-lookup"><span data-stu-id="57283-126">A special depreciation allowance is entered as either a percentage or a fixed amount.</span></span> <span data-ttu-id="57283-127">Quando você lançar propostas de depreciação, as transações de depreciação extra serão lançadas no registro de depreciações como transações separadas das transações de depreciação.</span><span class="sxs-lookup"><span data-stu-id="57283-127">When you post depreciation proposals, special depreciation allowance transactions are posted to the book as transactions that are separate from the depreciation transactions.</span></span>

## <a name="depreciation-calendars"></a><span data-ttu-id="57283-128">Calendários de depreciação</span><span class="sxs-lookup"><span data-stu-id="57283-128">Depreciation calendars</span></span>
<span data-ttu-id="57283-129">Cada livro tiver um calendário usado quando depreciar ativos fixos.</span><span class="sxs-lookup"><span data-stu-id="57283-129">Each book has a calendar that is used when you depreciate fixed assets.</span></span> <span data-ttu-id="57283-130">O método usará o calendário fiscal do razão por padrão se você não indicar um calendário.</span><span class="sxs-lookup"><span data-stu-id="57283-130">By default, if you don't indicate a calendar on the book, the book uses the ledger fiscal calendar.</span></span> <span data-ttu-id="57283-131">Você deve selecionar um calendário fiscal para um registro quando o perfil de depreciação associado do registro usar um ano de depreciação fiscal.</span><span class="sxs-lookup"><span data-stu-id="57283-131">You must select a fiscal calendar for a book when the depreciation profile that is associated with the book uses a fiscal depreciation year.</span></span> 

<span data-ttu-id="57283-132">Você pode criar calendários compartilhados usando a página **Calendários fiscais** na Contabilidade.</span><span class="sxs-lookup"><span data-stu-id="57283-132">You can create shared calendars by using the **Fiscal calendars** page in General ledger.</span></span>

<span data-ttu-id="57283-133">Para obter mais informações, consulte [Métodos e convenções de depreciação](depreciation-methods-conventions.md).</span><span class="sxs-lookup"><span data-stu-id="57283-133">For more information, see [Depreciation methods and conventions](depreciation-methods-conventions.md).</span></span>



