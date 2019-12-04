---
title: Visão geral das competências
description: Este artigo descreve competências, e fornece informações sobre como configurá-las e criar transações.
author: aprilolson
manager: AnnBe
ms.date: 01/11/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerAccuralTable
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 14131
ms.assetid: 0489b59a-37a7-4a78-87bf-4b597e9efad9
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4b97055f7eac12e3e82d028a0097ca926e5c355a
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2186753"
---
# <a name="accruals-overview"></a><span data-ttu-id="0877a-103">Visão geral das competências</span><span class="sxs-lookup"><span data-stu-id="0877a-103">Accruals overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0877a-104">Este artigo descreve competências, e fornece informações sobre como configurá-las e criar transações.</span><span class="sxs-lookup"><span data-stu-id="0877a-104">This article describes accruals, and provides information about how to set them up and create transactions.</span></span>

<span data-ttu-id="0877a-105">As competências são usadas em regime de competência para rastrear a receita que é reconhecida no período em que é gerada, não quando o pagamento é recebido e para rastrear as despesas (custo) que são reconhecidas quando ocorrem, não quando o pagamento é efetuado.</span><span class="sxs-lookup"><span data-stu-id="0877a-105">Accruals are used in accrual accounting to track revenue that is recognized in the period that it's earned in, not when payment is received, and to track expenses (costs) that are recognized when they occur, not when payment is made.</span></span>

## <a name="accrual-schemes"></a><span data-ttu-id="0877a-106">Esquemas de competência</span><span class="sxs-lookup"><span data-stu-id="0877a-106">Accrual schemes</span></span>
<span data-ttu-id="0877a-107">Os esquemas das competências são usados para configurar a receita e os custos diferidos e o mesmo esquema de competências pode ser usado para as receitas e os custos.</span><span class="sxs-lookup"><span data-stu-id="0877a-107">Accrual schemes are used to set up the deferred revenue and costs, and the same accrual scheme can be used for both revenue and costs.</span></span> <span data-ttu-id="0877a-108">As competências do razão redistribuem os custos ou as receitas de uma linha de diário para serem reconhecidos nos períodos apropriados.</span><span class="sxs-lookup"><span data-stu-id="0877a-108">Ledger accruals redistribute the costs or revenue of a journal line so that the costs and revenues are recognized in the appropriate periods.</span></span> <span data-ttu-id="0877a-109">Na página **Esquema de competência**, você especifica o débito e as contas de crédito que serão usados quando o esquema de competência é aplicado.</span><span class="sxs-lookup"><span data-stu-id="0877a-109">On the **Accrual scheme** page, you specify the debit and the credit accounts that will be used when the accrual scheme is applied.</span></span>

-   <span data-ttu-id="0877a-110">**Débito** – A conta principal que você define substituirá a conta principal do débito na linha do comprovante do diário.</span><span class="sxs-lookup"><span data-stu-id="0877a-110">**Debit** – The main account that you define will replace the debit main account on the journal voucher line.</span></span> <span data-ttu-id="0877a-111">Essa conta será usada também para a reversão de adiamento, com base nas transações de competência do razão.</span><span class="sxs-lookup"><span data-stu-id="0877a-111">This account will also be used for the reversal of the deferral, based on the ledger accrual transactions.</span></span>
-   <span data-ttu-id="0877a-112">**Crédito** – A conta principal definida substituirá a conta principal do crédito na linha do comprovante do diário.</span><span class="sxs-lookup"><span data-stu-id="0877a-112">**Credit** – the main account that you define will replace the credit main account on the journal voucher line.</span></span> <span data-ttu-id="0877a-113">Essa conta será usada também para a reversão de adiamento, com base nas transações de competência do razão.</span><span class="sxs-lookup"><span data-stu-id="0877a-113">This account will also be used for the reversal of the deferral, based on the ledger accrual transactions.</span></span>

<span data-ttu-id="0877a-114">Depois que você determina quais contas usar, é possível especificar como o número do comprovante é criado quando as transações de competência são criadas.</span><span class="sxs-lookup"><span data-stu-id="0877a-114">After you determine which accounts to use, you can specify how the voucher number is created when accrual transactions are created.</span></span> <span data-ttu-id="0877a-115">Você também pode especificar com que frequência as transações ocorrerão, o número de vezes em que as transações são criadas e quando as transações são lançadas.</span><span class="sxs-lookup"><span data-stu-id="0877a-115">You can also specify how often the transactions occur, the number of times that the transactions are created, and when the transactions are posted.</span></span> <span data-ttu-id="0877a-116">Depois que o esquema de competência foi criado, é possível usá-lo em qualquer um dos diários usando a função de competências do razão.</span><span class="sxs-lookup"><span data-stu-id="0877a-116">After the accrual scheme has been created, you can use it in some of the journals by using the Ledger accruals function.</span></span>

## <a name="ledger-accruals"></a><span data-ttu-id="0877a-117">Competências do razão</span><span class="sxs-lookup"><span data-stu-id="0877a-117">Ledger accruals</span></span>
<span data-ttu-id="0877a-118">Quando você insere um diário, é possível clicar em **Competências do razão** no menu **Funções**.</span><span class="sxs-lookup"><span data-stu-id="0877a-118">When you enter a journal, you can click **Ledger accruals** on the **Functions** menu.</span></span> <span data-ttu-id="0877a-119">Em seguida, quando você seleciona o esquema de competência, você verá o valor base do diário que será dividido durante o período, conforme determinado pelo esquema de competência.</span><span class="sxs-lookup"><span data-stu-id="0877a-119">Then, when you select the accrual scheme, you will see the base amount from the journal that will be spread over the period, as determined by the accrual scheme.</span></span> <span data-ttu-id="0877a-120">Por exemplo, se você pagar o seguro de um funcionário para todo o ano em janeiro e o valor for 12.000, você deve reconhecer as despesas todos os meses.</span><span class="sxs-lookup"><span data-stu-id="0877a-120">For example, if you pay an employee's insurance for the whole year in January, and the amount is 12,000, you must recognize that expense each month.</span></span> <span data-ttu-id="0877a-121">Você pode selecionar a data de início.</span><span class="sxs-lookup"><span data-stu-id="0877a-121">You can select the start date.</span></span> <span data-ttu-id="0877a-122">Você também pode especificar se o valor que é acumulado é baseado na conta ou na conta de compensação.</span><span class="sxs-lookup"><span data-stu-id="0877a-122">You can also specify whether the amount that is accrued is based on the account or the offset account.</span></span> <span data-ttu-id="0877a-123">Depois das seleções, clique em **Transações** para exibir todas as transações que foram criadas com base no esquema de competência.</span><span class="sxs-lookup"><span data-stu-id="0877a-123">After you make your selections, click **Transactions** to view all the transactions that have been created based on the accrual scheme.</span></span> <span data-ttu-id="0877a-124">Por exemplo, se você tiver 12.000 em despesas de seguro durante o ano, você verá 1.000 para cada mês.</span><span class="sxs-lookup"><span data-stu-id="0877a-124">For example, if you spread the 12,000 in insurance expenses over the year, you will see 1,000 for each month.</span></span> <span data-ttu-id="0877a-125">Depois de lançar o diário, você pode exibir as transações usando a página de consulta **Transações de comprovante**.</span><span class="sxs-lookup"><span data-stu-id="0877a-125">After you post the journal, you can view the transactions by using the **Voucher transactions** inquiry page.</span></span> <span data-ttu-id="0877a-126">Se não for possível aplicar um esquema de competência (por exemplo, quando uma fatura de ordem de venda ou uma fatura de ordem de compra for envolvida), você pode creditar o valor pago antecipadamente e debitar o valor de despesas.</span><span class="sxs-lookup"><span data-stu-id="0877a-126">If an accrual scheme can't be applied (for example, when a sales order invoice or purchase order invoice is involved), you can credit the prepaid amount and debit the expense amount.</span></span> <span data-ttu-id="0877a-127">Você pode selecionar **Contrapartida** ao aplicar o esquema de competência.</span><span class="sxs-lookup"><span data-stu-id="0877a-127">You can then select **Offset** when you apply the accrual scheme.</span></span>


<span data-ttu-id="0877a-128">Para obter mais informações, consulte [Criar esquemas de competência](tasks/create-accrual-schemes.md) e [Criar transações de competências do razão](tasks/create-ledger-accrual-transactions.md).</span><span class="sxs-lookup"><span data-stu-id="0877a-128">For more information, see [Create accrual schemes](tasks/create-accrual-schemes.md) and [Create ledger accrual transactions](tasks/create-ledger-accrual-transactions.md).</span></span>