---
title: Criar esquemas de competência
description: Este guia de tarefas aborda a criação de um esquema de competência.
author: aprilolson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerAccrualTable
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ce96ccfb0dc3e4a723af967147dae93772c5b44f
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1553122"
---
# <a name="create-accrual-schemes"></a><span data-ttu-id="24822-103">Criar esquemas de competência</span><span class="sxs-lookup"><span data-stu-id="24822-103">Create accrual schemes</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="24822-104">Este guia de tarefas aborda a criação de um esquema de competência.</span><span class="sxs-lookup"><span data-stu-id="24822-104">This task guide steps through creating an accrual scheme.</span></span> <span data-ttu-id="24822-105">Esta tarefa usa a empresa de demonstração USMF.</span><span class="sxs-lookup"><span data-stu-id="24822-105">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="24822-106">Vá para Contabilidade > Configuração do diário > Esquemas de competência.</span><span class="sxs-lookup"><span data-stu-id="24822-106">Go to General ledger > Journal setup > Accrual schemes.</span></span>
2. <span data-ttu-id="24822-107">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="24822-107">Click New.</span></span>
3. <span data-ttu-id="24822-108">No campo Identificação de competência, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="24822-108">In the Accrual identification field, type a value.</span></span>
4. <span data-ttu-id="24822-109">No campo Descrição do esquema de competência, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="24822-109">In the Description of accrual scheme field, type a value.</span></span>
5. <span data-ttu-id="24822-110">No campo Débito, especifique os valores desejados.</span><span class="sxs-lookup"><span data-stu-id="24822-110">In the Debit field, specify the desired values.</span></span>
    * <span data-ttu-id="24822-111">A conta principal definida substituirá a conta principal de débito na linha de comprovante do diário, bem como será usada para o estorno do diferimento com base nas transações de competência do razão.</span><span class="sxs-lookup"><span data-stu-id="24822-111">The main account defined will replace the debit main account on the journal voucher line and it will also be used for the reversal of the deferral based on the ledger accrual transactions.</span></span>  
6. <span data-ttu-id="24822-112">No campo Crédito, especifique os valores desejados.</span><span class="sxs-lookup"><span data-stu-id="24822-112">In the Credit field, specify the desired values.</span></span>
    * <span data-ttu-id="24822-113">A conta principal definida substituirá a conta principal de crédito na linha de comprovante do diário, bem como será usada para o estorno do diferimento com base nas transações de competência do razão.</span><span class="sxs-lookup"><span data-stu-id="24822-113">The main account defined will replace the credit main account on the journal voucher line and it will also be used for the reversal of the deferral based on the ledger accrual transactions.</span></span>  
7. <span data-ttu-id="24822-114">No campo Comprovante, selecione como deseja que o comprovante seja determinado quando as transações são lançadas.</span><span class="sxs-lookup"><span data-stu-id="24822-114">In the Voucher field, select how you want the voucher determined when the transactions are posted.</span></span>
8. <span data-ttu-id="24822-115">No campo Descrição, digite um valor para descrever as transações que serão lançadas.</span><span class="sxs-lookup"><span data-stu-id="24822-115">In the Description field, type a value to describe the transactions that will be posted.</span></span>
9. <span data-ttu-id="24822-116">No campo Frequência do período, selecione a frequência com que as transações devem ocorrer.</span><span class="sxs-lookup"><span data-stu-id="24822-116">In the Period frequency field, select how often the transactions should occur.</span></span>
10. <span data-ttu-id="24822-117">No campo Número de ocorrências por período, insira um número.</span><span class="sxs-lookup"><span data-stu-id="24822-117">In the Number of occurrences by period field, enter a number.</span></span>
11. <span data-ttu-id="24822-118">No campo Lançar transações, selecione quando as transações devem ser lançadas, como Mensalmente.</span><span class="sxs-lookup"><span data-stu-id="24822-118">In the Post transactions field, select when the transactions should be posted, such as Monthly.</span></span>

