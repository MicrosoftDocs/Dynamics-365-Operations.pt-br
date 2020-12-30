---
title: Entradas balanceadas para a contabilidade interunidade
description: Este artigo mostra como um diário é automaticamente balanceado quando uma dimensão financeira de balanceamento estiver marcada na página do razão.
author: ShylaThompson
manager: AnnBe
ms.date: 10/30/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerParameters
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 15791
ms.assetid: 301bd80e-f8b1-4f12-8194-e6d7de736084
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e84d96b5467b38e07a9ed31f142c27b638289284
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4440238"
---
# <a name="balanced-journals-for-interunit-accounting"></a><span data-ttu-id="9c477-103">Entradas balanceadas para a contabilidade interunidade</span><span class="sxs-lookup"><span data-stu-id="9c477-103">Balanced journals for interunit accounting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9c477-104">Este artigo mostra como um diário é automaticamente balanceado quando uma dimensão financeira de balanceamento estiver marcada na página do razão.</span><span class="sxs-lookup"><span data-stu-id="9c477-104">This article shows how a journal is automatically balanced when a balancing financial dimension is selected on the Ledger page.</span></span> 

<span data-ttu-id="9c477-105">Se as entradas de conta não estiverem equilibradas no nível dos valores de dimensão financeira, entradas adicionais de conta serão criadas automaticamente para equilibrar a entrada.</span><span class="sxs-lookup"><span data-stu-id="9c477-105">If account entries don't balance at the level of the financial dimension values, additional account entries are created automatically to balance the journal.</span></span> <span data-ttu-id="9c477-106">Essas entradas de conta usam os tipos de contabilidade **Interunidade - débito** e **Interunidade - crédito** na página **Contas para transações automáticas** para determinar a conta principal.</span><span class="sxs-lookup"><span data-stu-id="9c477-106">These account entries use the **Interunit - debit** and **Interunit - credit** posting types on the **Accounts for automatic transactions** page to determine the main account.</span></span> <span data-ttu-id="9c477-107">Por exemplo, a unidade de negócios, que é o segundo segmento da conta contábil, é selecionada como a dimensão financeira de balanço, e as entradas contábeis a seguir estão prestes a serem criadas.</span><span class="sxs-lookup"><span data-stu-id="9c477-107">For example, Business Unit, which is the second segment of the ledger account, is selected as the balancing financial dimension, and the following accounting entries are about to be created.</span></span>

|                      |           |
|----------------------|-----------|
| <span data-ttu-id="9c477-108">6100 – MSP – OU\_256</span><span class="sxs-lookup"><span data-stu-id="9c477-108">6100 – MSP – OU\_256</span></span> | <span data-ttu-id="9c477-109">100.00 DR</span><span class="sxs-lookup"><span data-stu-id="9c477-109">100.00 DR</span></span> |
| <span data-ttu-id="9c477-110">6100 – NY – OU\_249</span><span class="sxs-lookup"><span data-stu-id="9c477-110">6100 – NY – OU\_249</span></span>  | <span data-ttu-id="9c477-111">100.00 DR</span><span class="sxs-lookup"><span data-stu-id="9c477-111">100.00 DR</span></span> |
| <span data-ttu-id="9c477-112">2100 – MSP – OU\_256</span><span class="sxs-lookup"><span data-stu-id="9c477-112">2100 – MSP – OU\_256</span></span> | <span data-ttu-id="9c477-113">200.00 CR</span><span class="sxs-lookup"><span data-stu-id="9c477-113">200.00 CR</span></span> |

<span data-ttu-id="9c477-114">Neste caso, os seguintes saldos são determinados:</span><span class="sxs-lookup"><span data-stu-id="9c477-114">In this case, the following balances are determined:</span></span>

-   <span data-ttu-id="9c477-115">Para unidade de negócios, MSP = 100.00 CR</span><span class="sxs-lookup"><span data-stu-id="9c477-115">For Business Unit MSP = 100.00 CR</span></span>
-   <span data-ttu-id="9c477-116">Para unidade de negócios, NY = 100.00 DR</span><span class="sxs-lookup"><span data-stu-id="9c477-116">For Business Unit NY = 100.00 DR</span></span>

<span data-ttu-id="9c477-117">No entanto, as seguintes entradas contábeis são criadas automaticamente para conferir a entrada no nível de valores de dimensão financeira.</span><span class="sxs-lookup"><span data-stu-id="9c477-117">Therefore, the following accounting entries are created automatically to balance the  journal at the level of the financial dimension values.</span></span>

|                                   |           |
|-----------------------------------|-----------|
| <span data-ttu-id="9c477-118">(Interunidade - débito) – OU\_256</span><span class="sxs-lookup"><span data-stu-id="9c477-118">(Interunit Debit) – MSP – OU\_256</span></span> | <span data-ttu-id="9c477-119">100.00 DR</span><span class="sxs-lookup"><span data-stu-id="9c477-119">100.00 DR</span></span> |
| <span data-ttu-id="9c477-120">(Interunidade - Crédito) – NY – OU\_249</span><span class="sxs-lookup"><span data-stu-id="9c477-120">(Interunit Credit) – NY – OU\_249</span></span> | <span data-ttu-id="9c477-121">100.00 CR</span><span class="sxs-lookup"><span data-stu-id="9c477-121">100.00 CR</span></span> |





