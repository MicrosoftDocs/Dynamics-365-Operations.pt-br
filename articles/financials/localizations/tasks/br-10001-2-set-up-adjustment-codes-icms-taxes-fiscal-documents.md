--- 
title: "Configurar códigos de ajuste para impostos ICMS em notas fiscais (Brasil)"
description: "Você pode criar códigos de ajuste de imposto para ajustar manualmente valores do ICMS em notas fiscais."
author: sndray
manager: AnnBe
ms.date: 06/26/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Brazil
ms.author: sndray
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 1a4a7ca6de4849ab373d494e84a7318f0b22f43b
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---
# <a name="set-up-adjustment-codes-for-icms-taxes-on-fiscal-documents-brazil"></a><span data-ttu-id="3ef67-103">Configurar códigos de ajuste para impostos ICMS em notas fiscais (Brasil)</span><span class="sxs-lookup"><span data-stu-id="3ef67-103">Set up adjustment codes for ICMS taxes on fiscal documents (Brazil)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="3ef67-104">Você pode criar códigos de ajuste de imposto para ajustar manualmente valores do ICMS em notas fiscais.</span><span class="sxs-lookup"><span data-stu-id="3ef67-104">You can create tax adjustment codes to manually adjust ICMS tax amounts on fiscal documents.</span></span>

<span data-ttu-id="3ef67-105">Quando o arquivo fiscal SPED é gerado, o registro C197 inclui informações sobre ajustes manuais de impostos sobre valor do ICMS do documento fiscal.</span><span class="sxs-lookup"><span data-stu-id="3ef67-105">When the SPED Fiscal file is generated, record C197 includes the information about manual tax adjustments over the fiscal document's ICMS tax amount.</span></span> <span data-ttu-id="3ef67-106">Esses ajustes em notas fiscais podem ser necessários devido a um adiamento, suspensão, diferenças em taxas de impostos, antecipação e outras situações de exceção do imposto ICMS.</span><span class="sxs-lookup"><span data-stu-id="3ef67-106">These adjustments on fiscal documents might be required because of deferral, suspension, differences in tax rates, anticipation, and other situations of exception in ICMS tax.</span></span> <span data-ttu-id="3ef67-107">Esta tarefa usa a empresa de demonstração BRMF.</span><span class="sxs-lookup"><span data-stu-id="3ef67-107">This task uses the BRMF demo company.</span></span>

1. <span data-ttu-id="3ef67-108">Vá para Livros fiscais > Configuração > Códigos de ajuste de imposto > Ajuste e informações para documentos fiscais.</span><span class="sxs-lookup"><span data-stu-id="3ef67-108">Go to Fiscal books > Setup > Tax adjustment codes > Adjustment and information for fiscal documents.</span></span>
2. <span data-ttu-id="3ef67-109">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="3ef67-109">Click New.</span></span>
3. <span data-ttu-id="3ef67-110">No campo Identificação, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="3ef67-110">In the Identification field, type a value.</span></span>
4. <span data-ttu-id="3ef67-111">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="3ef67-111">In the Description field, type a value.</span></span>
5. <span data-ttu-id="3ef67-112">No campo Tipo de imposto, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="3ef67-112">In the Tax type field, select an option.</span></span>
6. <span data-ttu-id="3ef67-113">No campo Estado, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="3ef67-113">In the State field, enter or select a value.</span></span>
7. <span data-ttu-id="3ef67-114">No campo Classificação, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="3ef67-114">In the Classification field, select an option.</span></span>
8. <span data-ttu-id="3ef67-115">No campo Tipo de apuração, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="3ef67-115">In the Assessment type field, select an option.</span></span>
9. <span data-ttu-id="3ef67-116">No campo Responsabilidade, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="3ef67-116">In the Responsibility field, select an option.</span></span>
10. <span data-ttu-id="3ef67-117">No campo Tipo de pagamento de imposto, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="3ef67-117">In the Tax payment type field, select an option.</span></span>
11. <span data-ttu-id="3ef67-118">No campo Código de ocorrência, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="3ef67-118">In the Occurrence code field, type a value.</span></span>
12. <span data-ttu-id="3ef67-119">No campo Válido a Partir da Data, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="3ef67-119">In the Valid From Date field, enter a date.</span></span>
13. <span data-ttu-id="3ef67-120">Expanda a seção Lançamento.</span><span class="sxs-lookup"><span data-stu-id="3ef67-120">Expand the Posting section.</span></span>
14. <span data-ttu-id="3ef67-121">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="3ef67-121">Click New.</span></span>
15. <span data-ttu-id="3ef67-122">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="3ef67-122">In the list, mark the selected row.</span></span>
16. <span data-ttu-id="3ef67-123">No campo Contas da empresa, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="3ef67-123">In the Company accounts field, enter or select a value.</span></span>
17. <span data-ttu-id="3ef67-124">No campo Código de impostos sobre vendas, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="3ef67-124">In the Sales tax code field, enter or select a value.</span></span>
18. <span data-ttu-id="3ef67-125">No campo Conta principal, especifique os valores desejados.</span><span class="sxs-lookup"><span data-stu-id="3ef67-125">In the Main account field, specify the desired values.</span></span>
19. <span data-ttu-id="3ef67-126">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="3ef67-126">Click Save.</span></span>
20. <span data-ttu-id="3ef67-127">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="3ef67-127">Close the page.</span></span>

