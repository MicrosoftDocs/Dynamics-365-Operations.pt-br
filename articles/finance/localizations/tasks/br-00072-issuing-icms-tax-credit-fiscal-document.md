---
title: Emitir notas fiscais de crédito de imposto ICMS (Brasil)
description: Você pode criar uma nota fiscal de transferência ou apropriação de imposto e gerar uma nota fiscal eletrônica (NF-e).
author: sndray
manager: AnnBe
ms.date: 06/24/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Brazil
ms.search.industry: Manufacturing;Distribution;Service industries
ms.author: sndray
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e97ed469811c03c28d043ce9bab8ba0394447584
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2183865"
---
# <a name="issue-icms-tax-credit-fiscal-documents-brazil"></a><span data-ttu-id="5fadc-103">Emitir notas fiscais de crédito de imposto ICMS (Brasil)</span><span class="sxs-lookup"><span data-stu-id="5fadc-103">Issue ICMS tax credit fiscal documents (Brazil)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="5fadc-104">Você pode criar uma nota fiscal de transferência ou apropriação de imposto e gerar uma nota fiscal eletrônica (NF-e).</span><span class="sxs-lookup"><span data-stu-id="5fadc-104">You can create a new tax fiscal document and generate a Nota Fiscal eletrônica (NF-e).</span></span> <span data-ttu-id="5fadc-105">Quando você lança o documento, uma mensagem XML da NF-e é gerada e enviada para a Secretaria da Fazenda (SEFAZ).</span><span class="sxs-lookup"><span data-stu-id="5fadc-105">When you post the document, an NF-e XML message is generated and submitted to the Secretaria da Fazenda (SEFAZ).</span></span> <span data-ttu-id="5fadc-106">Esta tarefa usa a empresa de demonstração BRMF.</span><span class="sxs-lookup"><span data-stu-id="5fadc-106">This task uses the BRMF demo company.</span></span>

1. <span data-ttu-id="5fadc-107">Vá para Contabilidade > Entradas de diário > Todas as notas fiscais de transferência ou apropriação de imposto.</span><span class="sxs-lookup"><span data-stu-id="5fadc-107">Go to General ledger > Journal entries > All tax fiscal documents.</span></span>
2. <span data-ttu-id="5fadc-108">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="5fadc-108">Click New.</span></span>
3. <span data-ttu-id="5fadc-109">No campo Tipo de documento fiscal de transferência ou apropriação de imposto, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="5fadc-109">In the Tax fiscal document type field, select an option.</span></span>
    * <span data-ttu-id="5fadc-110">Selecione o tipo de nota fiscal de transferência de impostos, a transferência de imposto ICMS entre estabelecimentos fiscais ou prestação de crédito de importo de ICMS.</span><span class="sxs-lookup"><span data-stu-id="5fadc-110">Select the type of tax transfer fiscal document, either ICMS tax transfer between fiscal establishments or ICMS tax credit installment.</span></span>  
4. <span data-ttu-id="5fadc-111">No campo ID do estabelecimento fiscal, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="5fadc-111">In the Fiscal establishment ID field, enter or select a value.</span></span>
5. <span data-ttu-id="5fadc-112">No campo Tipo de conta, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="5fadc-112">In the Account type field, select an option.</span></span>
    * <span data-ttu-id="5fadc-113">Ao fazer transferência de imposto ICMS, selecione um fornecedor para receber o crédito de impostos de outro estabelecimento fiscal ou selecione um cliente para transferir o crédito de impostos para outro estabelecimento fiscal.</span><span class="sxs-lookup"><span data-stu-id="5fadc-113">While you're doing an ICMS tax transfer, select a vendor to receive the tax credit from another fiscal establishment, or select a customer to transfer the tax credit to another fiscal establishment.</span></span>  
6. <span data-ttu-id="5fadc-114">No campo Número de conta, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="5fadc-114">In the Account number field, enter or select a value.</span></span>
    * <span data-ttu-id="5fadc-115">O estabelecimento fiscal deve ser um fornecedor ou cliente.</span><span class="sxs-lookup"><span data-stu-id="5fadc-115">The fiscal establishment must be a vendor or customer.</span></span>  
7. <span data-ttu-id="5fadc-116">No campo Modelo do documento, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="5fadc-116">In the Document model field, enter or select a value.</span></span>
8. <span data-ttu-id="5fadc-117">No campo Chave de acesso, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="5fadc-117">In the Access key field, type a value.</span></span>
9. <span data-ttu-id="5fadc-118">No campo Data, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="5fadc-118">In the Date field, enter a date.</span></span>
10. <span data-ttu-id="5fadc-119">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="5fadc-119">Click Save.</span></span>
11. <span data-ttu-id="5fadc-120">Clique em Adicionar linha.</span><span class="sxs-lookup"><span data-stu-id="5fadc-120">Click Add line.</span></span>
12. <span data-ttu-id="5fadc-121">No campo Descrição do item, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="5fadc-121">In the Item description field, type a value.</span></span>
13. <span data-ttu-id="5fadc-122">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="5fadc-122">In the list, mark the selected row.</span></span>
14. <span data-ttu-id="5fadc-123">No campo CFOP, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="5fadc-123">In the CFOP field, enter or select a value.</span></span>
15. <span data-ttu-id="5fadc-124">No campo Código de impostos sobre vendas, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="5fadc-124">In the Sales tax code field, enter or select a value.</span></span>
16. <span data-ttu-id="5fadc-125">No campo Valor, insira um número.</span><span class="sxs-lookup"><span data-stu-id="5fadc-125">In the Amount field, enter a number.</span></span>
17. <span data-ttu-id="5fadc-126">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="5fadc-126">Click Save.</span></span>
18. <span data-ttu-id="5fadc-127">Clique em Lançar.</span><span class="sxs-lookup"><span data-stu-id="5fadc-127">Click Post.</span></span>
19. <span data-ttu-id="5fadc-128">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="5fadc-128">Click OK.</span></span>
20. <span data-ttu-id="5fadc-129">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="5fadc-129">Close the page.</span></span>
21. <span data-ttu-id="5fadc-130">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="5fadc-130">Close the page.</span></span>

