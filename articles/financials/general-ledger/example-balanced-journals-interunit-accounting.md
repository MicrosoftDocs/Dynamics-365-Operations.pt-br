---
title: Entradas balanceadas para a contabilidade interunidade
description: "Este artigo mostra como um diário é automaticamente balanceado quando uma dimensão financeira de balanceamento estiver marcada na página do razão."
author: twheeloc
manager: AnnBe
ms.date: 10/30/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerParameters
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 15791
ms.assetid: 301bd80e-f8b1-4f12-8194-e6d7de736084
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 208b61d9774c2594767cec4733efc552a30da5cc
ms.contentlocale: pt-br
ms.lasthandoff: 05/08/2018

---

# <a name="balanced-journals-for-interunit-accounting"></a><span data-ttu-id="dcd65-103">Entradas balanceadas para a contabilidade interunidade</span><span class="sxs-lookup"><span data-stu-id="dcd65-103">Balanced journals for interunit accounting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="dcd65-104">Este artigo mostra como um diário é automaticamente balanceado quando uma dimensão financeira de balanceamento estiver marcada na página do razão.</span><span class="sxs-lookup"><span data-stu-id="dcd65-104">This article shows how a journal is automatically balanced when a balancing financial dimension is selected on the Ledger page.</span></span> 

<span data-ttu-id="dcd65-105">Se as entradas de conta não estiverem equilibradas no nível dos valores de dimensão financeira, entradas adicionais de conta serão criadas automaticamente para equilibrar a entrada.</span><span class="sxs-lookup"><span data-stu-id="dcd65-105">If account entries don't balance at the level of the financial dimension values, additional account entries are created automatically to balance the journal.</span></span> <span data-ttu-id="dcd65-106">Essas entradas de conta usam os tipos de contabilidade **Interunidade - débito** e**Interunidade - crédito** na página **Contas para transações automáticas** para determinar a conta principal.</span><span class="sxs-lookup"><span data-stu-id="dcd65-106">These account entries use the **Interunit - debit** and **Interunit - credit** posting types on the **Accounts for automatic transactions** page to determine the main account.</span></span> <span data-ttu-id="dcd65-107">Por exemplo, a unidade de negócios, que é o segundo segmento da conta contábil, é selecionada como a dimensão financeira de balanço, e as entradas contábeis a seguir estão prestes a serem criadas.</span><span class="sxs-lookup"><span data-stu-id="dcd65-107">For example, Business Unit, which is the second segment of the ledger account, is selected as the balancing financial dimension, and the following accounting entries are about to be created.</span></span>

|                      |           |
|----------------------|-----------|
| <span data-ttu-id="dcd65-108">6100 – MSP – OU\_256</span><span class="sxs-lookup"><span data-stu-id="dcd65-108">6100 – MSP – OU\_256</span></span> | <span data-ttu-id="dcd65-109">100.00 DR</span><span class="sxs-lookup"><span data-stu-id="dcd65-109">100.00 DR</span></span> |
| <span data-ttu-id="dcd65-110">6100 – NY – OU\_249</span><span class="sxs-lookup"><span data-stu-id="dcd65-110">6100 – NY – OU\_249</span></span>  | <span data-ttu-id="dcd65-111">100.00 DR</span><span class="sxs-lookup"><span data-stu-id="dcd65-111">100.00 DR</span></span> |
| <span data-ttu-id="dcd65-112">2100 – MSP – OU\_256</span><span class="sxs-lookup"><span data-stu-id="dcd65-112">2100 – MSP – OU\_256</span></span> | <span data-ttu-id="dcd65-113">200.00 CR</span><span class="sxs-lookup"><span data-stu-id="dcd65-113">200.00 CR</span></span> |

<span data-ttu-id="dcd65-114">Neste caso, os seguintes saldos são determinados:</span><span class="sxs-lookup"><span data-stu-id="dcd65-114">In this case, the following balances are determined:</span></span>

-   <span data-ttu-id="dcd65-115">Para unidade de negócios, MSP = 100.00 CR</span><span class="sxs-lookup"><span data-stu-id="dcd65-115">For Business Unit MSP = 100.00 CR</span></span>
-   <span data-ttu-id="dcd65-116">Para unidade de negócios, NY = 100.00 DR</span><span class="sxs-lookup"><span data-stu-id="dcd65-116">For Business Unit NY = 100.00 DR</span></span>

<span data-ttu-id="dcd65-117">No entanto, as seguintes entradas contábeis são criadas automaticamente para conferir a entrada no nível de valores de dimensão financeira.</span><span class="sxs-lookup"><span data-stu-id="dcd65-117">Therefore, the following accounting entries are created automatically to balance the  journal at the level of the financial dimension values.</span></span>

|                                   |           |
|-----------------------------------|-----------|
| <span data-ttu-id="dcd65-118">(Interunidade - débito) – OU\_256</span><span class="sxs-lookup"><span data-stu-id="dcd65-118">(Interunit Debit) – MSP – OU\_256</span></span> | <span data-ttu-id="dcd65-119">100.00 DR</span><span class="sxs-lookup"><span data-stu-id="dcd65-119">100.00 DR</span></span> |
| <span data-ttu-id="dcd65-120">(Interunidade - Crédito) – NY – OU\_249</span><span class="sxs-lookup"><span data-stu-id="dcd65-120">(Interunit Credit) – NY – OU\_249</span></span> | <span data-ttu-id="dcd65-121">100.00 CR</span><span class="sxs-lookup"><span data-stu-id="dcd65-121">100.00 CR</span></span> |






