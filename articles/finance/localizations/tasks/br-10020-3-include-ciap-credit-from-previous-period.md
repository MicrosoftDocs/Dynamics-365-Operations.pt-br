---
title: Incluir o crédito CIAP de um período anterior (Brasil)
description: Use a página Transações de ativo fixo do CIAP para criar parcelas de crédito CIAP.
author: sndray
manager: AnnBe
ms.date: 06/26/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Brazil
ms.author: sndray
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 18a8c5387e8a7b96ae43b6a7e54dcd6c3d436dcf
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5236682"
---
# <a name="include-ciap-credit-from-a-previous-period-brazil"></a><span data-ttu-id="59696-103">Incluir o crédito CIAP de um período anterior (Brasil)</span><span class="sxs-lookup"><span data-stu-id="59696-103">Include CIAP credit from a previous period (Brazil)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="59696-104">Use a página Transações de ativo fixo do CIAP para criar parcelas de crédito CIAP.</span><span class="sxs-lookup"><span data-stu-id="59696-104">Use the CIAP fixed asset transactions page to create CIAP credit installments.</span></span> <span data-ttu-id="59696-105">Se uma parcela do CIAP não foi incluída em um período de escrituração anterior, uma parcela deverá ser criada de maneira que ela seja processada no período de escrituração atual, como uma apuração do imposto ICMS.</span><span class="sxs-lookup"><span data-stu-id="59696-105">If a CIAP installment wasn't included in a previous booking period, an installment must be created, so that the installment is processed as an ICMS tax assessment in the current booking period.</span></span> <span data-ttu-id="59696-106">Esta tarefa usa a empresa de demonstração BRMF.</span><span class="sxs-lookup"><span data-stu-id="59696-106">This task uses the BRMF demo company.</span></span>

1. <span data-ttu-id="59696-107">Vá para Livros fiscais > Comum > Período de escrituração.</span><span class="sxs-lookup"><span data-stu-id="59696-107">Go to Fiscal books > Common > Booking period.</span></span>
2. <span data-ttu-id="59696-108">Clique em Criar novo período de escrituração para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="59696-108">Click Create new booking period to open the drop dialog.</span></span>
3. <span data-ttu-id="59696-109">No campo Estabelecimento fiscal, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="59696-109">In the Fiscal establishment field, enter or select a value.</span></span>
4. <span data-ttu-id="59696-110">No campo Mês, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="59696-110">In the Month field, select an option.</span></span>
5. <span data-ttu-id="59696-111">No campo Ano, insira um número.</span><span class="sxs-lookup"><span data-stu-id="59696-111">In the Year field, enter a number.</span></span>
6. <span data-ttu-id="59696-112">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="59696-112">Click OK.</span></span>
7. <span data-ttu-id="59696-113">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="59696-113">In the list, mark the selected row.</span></span>
8. <span data-ttu-id="59696-114">Clicar em ICMS.</span><span class="sxs-lookup"><span data-stu-id="59696-114">Click ICMS.</span></span>
9. <span data-ttu-id="59696-115">Clique em Apuração de imposto ICMS para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="59696-115">Click ICMS tax assessment to open the drop dialog.</span></span>
10. <span data-ttu-id="59696-116">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="59696-116">Click OK.</span></span>
11. <span data-ttu-id="59696-117">Clique em Apuração do CIAP.</span><span class="sxs-lookup"><span data-stu-id="59696-117">Click CIAP assessment.</span></span>
12. <span data-ttu-id="59696-118">Clique em Adicionar linha.</span><span class="sxs-lookup"><span data-stu-id="59696-118">Click Add line.</span></span>
13. <span data-ttu-id="59696-119">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="59696-119">In the list, mark the selected row.</span></span>
14. <span data-ttu-id="59696-120">No campo ID de ativo do CIAP, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="59696-120">In the CIAP asset ID field, enter or select a value.</span></span>
15. <span data-ttu-id="59696-121">No campo Data, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="59696-121">In the Date field, enter a date.</span></span>
16. <span data-ttu-id="59696-122">No campo Tipo de transação, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="59696-122">In the Transaction type field, select an option.</span></span>
    * <span data-ttu-id="59696-123">Selecione Crédito de parcela do ICMS.</span><span class="sxs-lookup"><span data-stu-id="59696-123">Select Credit of ICMS installment.</span></span>  
17. <span data-ttu-id="59696-124">No campo Número da parcela, insira um número.</span><span class="sxs-lookup"><span data-stu-id="59696-124">In the Installment number field, enter a number.</span></span>
18. <span data-ttu-id="59696-125">No campo Valor da parcela, insira um número.</span><span class="sxs-lookup"><span data-stu-id="59696-125">In the Installment amount field, enter a number.</span></span>
19. <span data-ttu-id="59696-126">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="59696-126">Click Save.</span></span>
20. <span data-ttu-id="59696-127">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="59696-127">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]