---
title: Exibir transações de passivos, ativos e despesas
description: Este tópico explica como exibir transações para um ativo arrendado. Essas transações incluem transações de responsabilidade com arrendamento e transações de despesa de execução que foram lançadas.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations, Retail
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 7008891d194dc990d13a9f56db155c6990aae0c0
ms.sourcegitcommit: aeee39c01d3f93a6dfcf2013965fa975a740596a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/28/2020
ms.locfileid: "4440564"
---
# <a name="view-liability-asset-and-expense-transactions"></a><span data-ttu-id="6394f-104">Exibir transações de passivos, ativos e despesas</span><span class="sxs-lookup"><span data-stu-id="6394f-104">View liability, asset, and expense transactions</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6394f-105">Este tópico explica como exibir transações para um ativo arrendado.</span><span class="sxs-lookup"><span data-stu-id="6394f-105">This topic explains how to view transactions for a leased asset.</span></span> <span data-ttu-id="6394f-106">Essas transações incluem transações de responsabilidade com arrendamento e transações de despesa de execução que foram lançadas.</span><span class="sxs-lookup"><span data-stu-id="6394f-106">These transactions include lease liability transactions and executory expense transactions that have been posted.</span></span> <span data-ttu-id="6394f-107">Os valores de transporte do ativo passivo e de direito de uso (DDU) são usados em vários relatórios.</span><span class="sxs-lookup"><span data-stu-id="6394f-107">The carrying values of the liability and right-of-use (ROU) asset are used on several reports.</span></span> <span data-ttu-id="6394f-108">Eles também são usados para calcular os valores de ajuste.</span><span class="sxs-lookup"><span data-stu-id="6394f-108">They are also used to calculate adjustment values.</span></span>

## <a name="liability-transactions"></a><span data-ttu-id="6394f-109">Transações de passivo</span><span class="sxs-lookup"><span data-stu-id="6394f-109">Liability transactions</span></span>

<span data-ttu-id="6394f-110">Para exibir as transações de responsabilidade com arrendamento, selecione um arrendamento na página **Resumo do arrendamento** e, em seguida, selecione **Registros** para abrir os registros anexados ao registro de arrendamento.</span><span class="sxs-lookup"><span data-stu-id="6394f-110">To view the lease liability transactions, select a lease on the **Lease summary** page, and then select **Books** to open the books that are attached to the lease record.</span></span> <span data-ttu-id="6394f-111">Depois que um reconhecimento inicial, uma fatura ou um diário de juros tiver sido lançado, selecione **Transações de passivo**.</span><span class="sxs-lookup"><span data-stu-id="6394f-111">After an initial recognition, an invoice, or an interest journal has been posted, select **Liability transactions**.</span></span>

<span data-ttu-id="6394f-112">A página **Transações de passivo** mostra as transações que aumentam ou diminuem a responsabilidade com arrendamento.</span><span class="sxs-lookup"><span data-stu-id="6394f-112">The **Liability transactions** page shows the transactions that either increase or decrease the lease liability.</span></span> <span data-ttu-id="6394f-113">Os valores negativos nesta página representam transações de crédito no aplicativo padrão.</span><span class="sxs-lookup"><span data-stu-id="6394f-113">Negative amounts on this page represent credit transactions in the standard application.</span></span> <span data-ttu-id="6394f-114">As competências de juros são mostradas como valores negativos e aumentam a responsabilidade com arrendamento total.</span><span class="sxs-lookup"><span data-stu-id="6394f-114">Any interest accruals are shown as negative values and increase the total lease liability.</span></span> <span data-ttu-id="6394f-115">Os ajustes de arrendamento são mostrados como valores positivos ou negativos, dependendo da natureza e do impacto do registro de arrendamento.</span><span class="sxs-lookup"><span data-stu-id="6394f-115">Any lease adjustments are shown as positive or negative values, depending on the nature and impact of the lease book.</span></span> <span data-ttu-id="6394f-116">O saldo total líquido atual da responsabilidade com arrendamento para o arrendamento selecionado é mostrado no canto inferior esquerdo da página.</span><span class="sxs-lookup"><span data-stu-id="6394f-116">The current net total balance of the lease liability for the selected lease is shown at the bottom left of the page.</span></span>

## <a name="asset-transactions"></a><span data-ttu-id="6394f-117">Transações de ativo</span><span class="sxs-lookup"><span data-stu-id="6394f-117">Asset transactions</span></span>

<span data-ttu-id="6394f-118">Para exibir as transações de ativo, selecione um arrendamento na página **Resumo do arrendamento** e, em seguida, selecione **Registros** para abrir os registros de arrendamento anexados ao registro de arrendamento.</span><span class="sxs-lookup"><span data-stu-id="6394f-118">To view the lease asset transactions, select a lease on the **Lease summary** page, and then select **Books** to open the lease books that are attached to the lease record.</span></span> <span data-ttu-id="6394f-119">Em seguida, selecione **Transações de ativo**.</span><span class="sxs-lookup"><span data-stu-id="6394f-119">Then select **Asset transactions**.</span></span>

<span data-ttu-id="6394f-120">A página **Transação de ativo** mostra as transações que aumentam ou diminuem as contas de ativo de arrendamento e depreciação acumulada.</span><span class="sxs-lookup"><span data-stu-id="6394f-120">The **Asset transaction** page shows the transactions that either increase or decrease the lease asset and accumulated depreciation accounts.</span></span> <span data-ttu-id="6394f-121">Os débitos são mostrados como valores positivos, e os créditos são mostrados como valores negativos, como na página **Transações de passivo**.</span><span class="sxs-lookup"><span data-stu-id="6394f-121">Debits are shown as positive values, and credits are shown as negative values, as on the **Liability transactions** page.</span></span> <span data-ttu-id="6394f-122">O reconhecimento inicial lançado e a próxima depreciação acumulada são mostrados no canto inferior esquerdo da página como o saldo do ativo.</span><span class="sxs-lookup"><span data-stu-id="6394f-122">The posted initial recognition and the next of accumulated depreciation are shown at the bottom left of the page as the asset balance.</span></span> 

## <a name="expenses-transactions"></a><span data-ttu-id="6394f-123">Transações de despesas</span><span class="sxs-lookup"><span data-stu-id="6394f-123">Expenses transactions</span></span>

<span data-ttu-id="6394f-124">Para exibir as transações de despesas de ativo, selecione um arrendamento na página **Resumo do arrendamento** e, em seguida, selecione **Registros** para abrir os registros de arrendamento anexados ao registro de arrendamento.</span><span class="sxs-lookup"><span data-stu-id="6394f-124">To view the lease expense transactions, select a lease on the **Lease summary** page, and then select **Books** to open the lease books that are attached to the lease record.</span></span> <span data-ttu-id="6394f-125">Em seguida, selecione **Transações de despesa**.</span><span class="sxs-lookup"><span data-stu-id="6394f-125">Then select **Expense transactions**.</span></span>

<span data-ttu-id="6394f-126">A página **Transações de despesa** mostra todas as despesas que foram lançadas em relação ao arrendamento, como despesas de juros, despesas de depreciação e qualquer custo de execução.</span><span class="sxs-lookup"><span data-stu-id="6394f-126">The **Expense transactions** page shows all the expenses that have been posted against the lease, such as interest expenses, depreciation expenses, and any executory costs.</span></span>
