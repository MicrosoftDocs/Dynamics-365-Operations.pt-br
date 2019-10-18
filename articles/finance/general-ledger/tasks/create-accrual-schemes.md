---
title: Criar esquemas de competência
description: Este tópico explica como criar um esquema de competência.
author: aprilolson
manager: AnnBe
ms.date: 07/19/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerAccrualTable
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e8f8cf8546187ae1c65d4966887e1c5842dff431
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2175298"
---
# <a name="create-accrual-schemes"></a><span data-ttu-id="9698b-103">Criar esquemas de competência</span><span class="sxs-lookup"><span data-stu-id="9698b-103">Create accrual schemes</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="9698b-104">Este tópico explica como criar um esquema de competência.</span><span class="sxs-lookup"><span data-stu-id="9698b-104">This topic explains how to create an accrual scheme.</span></span> <span data-ttu-id="9698b-105">Esta tarefa usa a empresa de demonstração USMF.</span><span class="sxs-lookup"><span data-stu-id="9698b-105">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="9698b-106">Vá até **Painel de Navegação > Módulos > Contabilidade > Configuração do diário > Esquemas de competência**.</span><span class="sxs-lookup"><span data-stu-id="9698b-106">Go to **Navigation pane > Modules > General ledger > Journal setup > Accrual schemes**.</span></span>
2. <span data-ttu-id="9698b-107">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="9698b-107">Select **New**.</span></span>
3. <span data-ttu-id="9698b-108">No campo **Identificação de competência**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="9698b-108">In the **Accrual identification** field, type a value.</span></span>
4. <span data-ttu-id="9698b-109">No campo **Descrição do esquema de competência**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="9698b-109">In the **Description of accrual scheme** field, type a value.</span></span>
5. <span data-ttu-id="9698b-110">No campo **Débito**, especifique os valores desejados.</span><span class="sxs-lookup"><span data-stu-id="9698b-110">In the **Debit** field, specify the desired values.</span></span> <span data-ttu-id="9698b-111">A conta principal definida substituirá a conta principal de débito na linha de comprovante do diário, bem como será usada para o estorno do diferimento com base nas transações de competência do razão.</span><span class="sxs-lookup"><span data-stu-id="9698b-111">The main account defined will replace the debit main account on the journal voucher line and it will also be used for the reversal of the deferral based on the ledger accrual transactions.</span></span>  
6. <span data-ttu-id="9698b-112">No campo **Crédito**, especifique os valores desejados.</span><span class="sxs-lookup"><span data-stu-id="9698b-112">In the **Credit** field, specify the desired values.</span></span> <span data-ttu-id="9698b-113">A conta principal definida substituirá a conta principal de crédito na linha de comprovante do diário, bem como será usada para o estorno do diferimento com base nas transações de competência do razão.</span><span class="sxs-lookup"><span data-stu-id="9698b-113">The main account defined will replace the credit main account on the journal voucher line and it will also be used for the reversal of the deferral based on the ledger accrual transactions.</span></span>  
7. <span data-ttu-id="9698b-114">No campo **Comprovante**, selecione como deseja que o comprovante seja determinado quando as transações são lançadas.</span><span class="sxs-lookup"><span data-stu-id="9698b-114">In the **Voucher** field, select how you want the voucher determined when the transactions are posted.</span></span>
8. <span data-ttu-id="9698b-115">No campo **Descrição**, digite um valor para descrever as transações que serão lançadas.</span><span class="sxs-lookup"><span data-stu-id="9698b-115">In the **Description** field, type a value to describe the transactions that will be posted.</span></span>
9. <span data-ttu-id="9698b-116">No campo **Frequência do período**, selecione a frequência com que as transações devem ocorrer.</span><span class="sxs-lookup"><span data-stu-id="9698b-116">In the **Period frequency** field, select how often the transactions should occur.</span></span>
10. <span data-ttu-id="9698b-117">No campo **Número de ocorrências por período**, insira um número.</span><span class="sxs-lookup"><span data-stu-id="9698b-117">In the **Number of occurrences by period** field, enter a number.</span></span>
11. <span data-ttu-id="9698b-118">No campo **Lançar transações**, selecione quando as transações devem ser lançadas, como **Mensalmente**.</span><span class="sxs-lookup"><span data-stu-id="9698b-118">In the **Post transactions** field, select when the transactions should be posted, such as **Monthly**.</span></span>

