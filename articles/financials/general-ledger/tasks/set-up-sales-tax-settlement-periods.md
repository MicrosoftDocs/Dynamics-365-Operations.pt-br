--- 
title: "Configurar períodos de liquidação do imposto"
description: "Períodos de liquidação de impostos contêm informações sobre os intervalos de período para os quais os impostos precisam ser relatados e pagos."
author: twheeloc
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: TaxPeriod
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: fbe31ee6a66733087677f8083c1047552d4ecffc
ms.contentlocale: pt-br
ms.lasthandoff: 09/14/2018

---
# <a name="set-up-sales-tax-settlement-periods"></a><span data-ttu-id="79ddd-103">Configurar períodos de liquidação do imposto</span><span class="sxs-lookup"><span data-stu-id="79ddd-103">Set up sales tax settlement periods</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="79ddd-104">Períodos de liquidação de impostos contêm informações sobre os intervalos de período para os quais os impostos precisam ser relatados e pagos.</span><span class="sxs-lookup"><span data-stu-id="79ddd-104">Sales tax settlement periods contain information about the period intervals for which sales tax needs to be reported and paid.</span></span> <span data-ttu-id="79ddd-105">Um processo de pagamento pode ser executado por um período de liquidação para um intervalo de datas específico.</span><span class="sxs-lookup"><span data-stu-id="79ddd-105">A settlement process can be run for a settlement period for a specific date interval.</span></span> <span data-ttu-id="79ddd-106">Todos os códigos de imposto associados ao período de liquidação serão liquidados.</span><span class="sxs-lookup"><span data-stu-id="79ddd-106">All tax codes associated with the settlement period will be settled.</span></span> <span data-ttu-id="79ddd-107">Dependendo da configuração da autoridade de impostos sobre vendas relacionada, a obrigação fiscal é lançada a um fornecedor ou em uma conta contábil.</span><span class="sxs-lookup"><span data-stu-id="79ddd-107">Depending on the set up of the related Sales tax authority, the tax liability is posted either to a vendor or a General ledger account.</span></span>



<span data-ttu-id="79ddd-108">Esta tarefa usa a empresa de demonstração USMF.</span><span class="sxs-lookup"><span data-stu-id="79ddd-108">This task uses the USMF demo company.</span></span>



1. <span data-ttu-id="79ddd-109">Vá para Imposto > Impostos indiretos > Imposto sobre vendas > Períodos de liquidação de impostos sobre vendas.</span><span class="sxs-lookup"><span data-stu-id="79ddd-109">Go to Tax > Indirect taxes > Sales tax > Sales tax settlement periods.</span></span>
2. <span data-ttu-id="79ddd-110">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="79ddd-110">Click New.</span></span>
3. <span data-ttu-id="79ddd-111">No campo de Período de liquidação, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="79ddd-111">In the Settlement period field, type a value.</span></span>
4. <span data-ttu-id="79ddd-112">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="79ddd-112">In the Description field, type a value.</span></span>
5. <span data-ttu-id="79ddd-113">No campo Autoridade, selecione a autoridade do imposto sobre vendas que recebe os relatórios e os pagamentos relacionados que são criados para o período de liquidação.</span><span class="sxs-lookup"><span data-stu-id="79ddd-113">In the Authority field, select the sales tax authority that receives the reports and the payments that are created for the settlement period.</span></span>
6. <span data-ttu-id="79ddd-114">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="79ddd-114">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="79ddd-115">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="79ddd-115">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="79ddd-116">No campo Termos de pagamento, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="79ddd-116">In the Terms of payment field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="79ddd-117">A autoridade do imposto sobre vendas relacionada pode ser configurada como um fornecedor e a liquidação do imposto sobre vendas criará uma nota fiscal de fornecedor aberta.</span><span class="sxs-lookup"><span data-stu-id="79ddd-117">The related Sales tax authority can be set up as a vendor and the Sales tax settlement will create an open vendor invoice.</span></span> <span data-ttu-id="79ddd-118">Os Termos de pagamento definem a Data de vencimento para a fatura de fornecedor aberta.</span><span class="sxs-lookup"><span data-stu-id="79ddd-118">The Terms of payment defines the Due date for the open vendor invoice.</span></span>  
9. <span data-ttu-id="79ddd-119">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="79ddd-119">In the list, find and select the desired record.</span></span>
10. <span data-ttu-id="79ddd-120">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="79ddd-120">In the list, click the link in the selected row.</span></span>
11. <span data-ttu-id="79ddd-121">Selecione o tipo de intervalos de período de liquidação.</span><span class="sxs-lookup"><span data-stu-id="79ddd-121">Select a type for the settlement period intervals.</span></span>
12. <span data-ttu-id="79ddd-122">Insira o número das Unidades de intervalo de período por período.</span><span class="sxs-lookup"><span data-stu-id="79ddd-122">Enter the number of Period interval units per period.</span></span> <span data-ttu-id="79ddd-123">Por exemplo, um trimestre tem 3 meses.</span><span class="sxs-lookup"><span data-stu-id="79ddd-123">For example, a quarter has 3 months.</span></span>
13. <span data-ttu-id="79ddd-124">Marque ou desmarque o processamento em lotes de uso da caixa de seleção de liquidação do imposto sobre vendas.</span><span class="sxs-lookup"><span data-stu-id="79ddd-124">Select or clear the Use batch processing for sales tax settlement check box.</span></span>
    * <span data-ttu-id="79ddd-125">O processo de liquidação para o período de liquidação pode ser processado como trabalhos em lotes no plano de fundo.</span><span class="sxs-lookup"><span data-stu-id="79ddd-125">The settlement process for the settlement period can be processed as batch job in the background.</span></span> <span data-ttu-id="79ddd-126">Isso é recomendável para um grande número de transações de imposto em um intervalo de períodos.</span><span class="sxs-lookup"><span data-stu-id="79ddd-126">This is recommended for a large number of tax transactions within a period interval.</span></span>  
14. <span data-ttu-id="79ddd-127">Expanda a guia dos intervalos de períodos.</span><span class="sxs-lookup"><span data-stu-id="79ddd-127">Expand the Period intervals tab.</span></span>
15. <span data-ttu-id="79ddd-128">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="79ddd-128">Click Add.</span></span>
16. <span data-ttu-id="79ddd-129">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="79ddd-129">In the list, mark the selected row.</span></span>
17. <span data-ttu-id="79ddd-130">No campo De data, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="79ddd-130">In the From date field, enter a date.</span></span>
18. <span data-ttu-id="79ddd-131">No campo Para data, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="79ddd-131">In the To date field, enter a date.</span></span>
19. <span data-ttu-id="79ddd-132">Clique em Novo intervalo do período.</span><span class="sxs-lookup"><span data-stu-id="79ddd-132">Click New period interval.</span></span>
    * <span data-ttu-id="79ddd-133">Depois que o primeiro intervalo de período tiver sido inserido, os novos períodos podem ser criados automaticamente.</span><span class="sxs-lookup"><span data-stu-id="79ddd-133">Once the first period interval has been entered, new periods can be created automatically.</span></span> <span data-ttu-id="79ddd-134">Você pode voltar e adicionar novos intervalos de período conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="79ddd-134">You can come back and add new period intervals as required.</span></span>  
20. <span data-ttu-id="79ddd-135">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="79ddd-135">Close the page.</span></span>


