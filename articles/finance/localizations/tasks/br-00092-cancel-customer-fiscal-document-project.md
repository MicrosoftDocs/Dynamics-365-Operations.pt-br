---
title: Cancelar uma nota fiscal de cliente (projeto) (Brasil)
description: É possível cancelar uma fatura de cliente para um projeto.
author: sndray
manager: AnnBe
ms.date: 06/26/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Brazil
ms.author: sndray
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 489f25898d6fbbf744e75c99189daca3d4ffeabe
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4408469"
---
# <a name="cancel-a-customer-fiscal-document-project-brazil"></a><span data-ttu-id="83a67-103">Cancelar uma nota fiscal de cliente (projeto) (Brasil)</span><span class="sxs-lookup"><span data-stu-id="83a67-103">Cancel a customer fiscal document (project) (Brazil)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="83a67-104">É possível cancelar uma fatura de cliente para um projeto.</span><span class="sxs-lookup"><span data-stu-id="83a67-104">You can cancel a customer invoice for a project.</span></span> <span data-ttu-id="83a67-105">Ao cancelar uma fatura de projeto, uma fatura de projeto negativa é criada.</span><span class="sxs-lookup"><span data-stu-id="83a67-105">When you cancel a project invoice, a negative project invoice is created.</span></span> <span data-ttu-id="83a67-106">Ao lançar a fatura de projeto negativa, as faturas de projeto originais e negativas são marcadas como canceladas e todas as transações contábeis e financeiras são revertidas.</span><span class="sxs-lookup"><span data-stu-id="83a67-106">When you post the negative project invoice, the original and negative project invoices are marked as canceled, and all the ledger and financial transactions are reversed.</span></span> <span data-ttu-id="83a67-107">A transação original é informada como cancelada nos livros fiscais, mas a transação negativa não é informada nos livros fiscais.</span><span class="sxs-lookup"><span data-stu-id="83a67-107">The original transaction is reported as canceled in the fiscal books, but the negative transaction isn't reported in the fiscal books.</span></span> <span data-ttu-id="83a67-108">Não é possível cancelar uma fatura de projeto que está liquidada parcialmente ou completamente.</span><span class="sxs-lookup"><span data-stu-id="83a67-108">You can't cancel a project invoice that is partially or fully settled.</span></span> <span data-ttu-id="83a67-109">Além de isso, não é possível cancelar uma fatura de projeto, se a data de lançamento da fatura cair em um período fiscal que está fechado.</span><span class="sxs-lookup"><span data-stu-id="83a67-109">Additionally, you can't cancel a project invoice if the posting date of the invoice is in a fiscal period that is closed.</span></span> <span data-ttu-id="83a67-110">Esta tarefa usa a empresa de demonstração BRMF.</span><span class="sxs-lookup"><span data-stu-id="83a67-110">This task uses the BRMF demo company.</span></span>

1. <span data-ttu-id="83a67-111">Vá para Gerenciamento e contabilidade de projeto > Projetos > Todos os projetos.</span><span class="sxs-lookup"><span data-stu-id="83a67-111">Go to Project management and accounting > Projects > All projects.</span></span>
2. <span data-ttu-id="83a67-112">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="83a67-112">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="83a67-113">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="83a67-113">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="83a67-114">Clique em Diário de faturas.</span><span class="sxs-lookup"><span data-stu-id="83a67-114">Click Invoice journals.</span></span>
5. <span data-ttu-id="83a67-115">Use o Filtro Rápido para localizar registros.</span><span class="sxs-lookup"><span data-stu-id="83a67-115">Use the Quick Filter to find records.</span></span> <span data-ttu-id="83a67-116">Por exemplo, filtre o campo Fatura com um valor de '04000006'.</span><span class="sxs-lookup"><span data-stu-id="83a67-116">For example, filter on the Invoice field with a value of '04000006'.</span></span>
6. <span data-ttu-id="83a67-117">Clique em Cancelamento de fatura.</span><span class="sxs-lookup"><span data-stu-id="83a67-117">Click Invoice cancellation.</span></span>
7. <span data-ttu-id="83a67-118">Clique em Sim.</span><span class="sxs-lookup"><span data-stu-id="83a67-118">Click Yes.</span></span>
8. <span data-ttu-id="83a67-119">No campo Código de motivo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="83a67-119">In the Reason code field, enter or select a value.</span></span>
9. <span data-ttu-id="83a67-120">No campo Data de cancelamento da fatura, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="83a67-120">In the Canceling invoice date field, enter a date.</span></span>
10. <span data-ttu-id="83a67-121">Clique em Cancelar fatura do projeto.</span><span class="sxs-lookup"><span data-stu-id="83a67-121">Click Cancel project invoice.</span></span>
11. <span data-ttu-id="83a67-122">Selecione Não no campo Imprimir fatura.</span><span class="sxs-lookup"><span data-stu-id="83a67-122">Select No in the Print invoice field.</span></span>
12. <span data-ttu-id="83a67-123">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="83a67-123">Click OK.</span></span>
13. <span data-ttu-id="83a67-124">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="83a67-124">Click OK.</span></span>
14. <span data-ttu-id="83a67-125">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="83a67-125">Close the page.</span></span>

