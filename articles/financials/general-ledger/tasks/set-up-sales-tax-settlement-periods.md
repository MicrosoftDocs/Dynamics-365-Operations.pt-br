---
title: Configurar períodos de liquidação do imposto
description: Períodos de liquidação de impostos contêm informações sobre os intervalos de período para os quais os impostos precisam ser relatados e pagos.
author: twheeloc
manager: AnnBe
ms.date: 08/05/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxPeriod
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8304d9e8997a5d31740ee1203aa4bf0603014056
ms.sourcegitcommit: d0fa8d0140fa81029527edb317623c1a7737c593
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2019
ms.locfileid: "1862979"
---
# <a name="set-up-sales-tax-settlement-periods"></a><span data-ttu-id="4f255-103">Configurar períodos de liquidação do imposto</span><span class="sxs-lookup"><span data-stu-id="4f255-103">Set up sales tax settlement periods</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="4f255-104">Períodos de liquidação de impostos contêm informações sobre os intervalos de período para os quais os impostos precisam ser relatados e pagos.</span><span class="sxs-lookup"><span data-stu-id="4f255-104">Sales tax settlement periods contain information about the period intervals for which sales tax needs to be reported and paid.</span></span> <span data-ttu-id="4f255-105">Um processo de pagamento pode ser executado por um período de liquidação para um intervalo de datas específico.</span><span class="sxs-lookup"><span data-stu-id="4f255-105">A settlement process can be run for a settlement period for a specific date interval.</span></span> <span data-ttu-id="4f255-106">Todos os códigos de imposto associados ao período de liquidação serão liquidados.</span><span class="sxs-lookup"><span data-stu-id="4f255-106">All tax codes associated with the settlement period will be settled.</span></span> <span data-ttu-id="4f255-107">Dependendo da configuração da autoridade de impostos sobre vendas relacionada, a obrigação fiscal é lançada a um fornecedor ou em uma conta contábil.</span><span class="sxs-lookup"><span data-stu-id="4f255-107">Depending on the set up of the related Sales tax authority, the tax liability is posted either to a vendor or a General ledger account.</span></span>



<span data-ttu-id="4f255-108">Esta tarefa usa a empresa de demonstração USMF.</span><span class="sxs-lookup"><span data-stu-id="4f255-108">This task uses the USMF demo company.</span></span>



1. <span data-ttu-id="4f255-109">Vá para Imposto > Impostos indiretos > Imposto sobre vendas > Períodos de liquidação de impostos sobre vendas.</span><span class="sxs-lookup"><span data-stu-id="4f255-109">Go to Tax > Indirect taxes > Sales tax > Sales tax settlement periods.</span></span>
2. <span data-ttu-id="4f255-110">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="4f255-110">Click New.</span></span>
3. <span data-ttu-id="4f255-111">No campo de Período de liquidação, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="4f255-111">In the Settlement period field, type a value.</span></span>
4. <span data-ttu-id="4f255-112">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="4f255-112">In the Description field, type a value.</span></span>
5. <span data-ttu-id="4f255-113">No campo Autoridade, selecione a autoridade do imposto sobre vendas que recebe os relatórios e os pagamentos relacionados que são criados para o período de liquidação.</span><span class="sxs-lookup"><span data-stu-id="4f255-113">In the Authority field, select the sales tax authority that receives the reports and the payments that are created for the settlement period.</span></span>
6. <span data-ttu-id="4f255-114">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="4f255-114">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="4f255-115">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="4f255-115">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="4f255-116">No campo Termos de pagamento, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="4f255-116">In the Terms of payment field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="4f255-117">A autoridade do imposto sobre vendas relacionada pode ser configurada como um fornecedor e a liquidação do imposto sobre vendas criará uma nota fiscal de fornecedor aberta.</span><span class="sxs-lookup"><span data-stu-id="4f255-117">The related Sales tax authority can be set up as a vendor and the Sales tax settlement will create an open vendor invoice.</span></span> <span data-ttu-id="4f255-118">Os Termos de pagamento definem a Data de vencimento para a fatura de fornecedor aberta.</span><span class="sxs-lookup"><span data-stu-id="4f255-118">The Terms of payment defines the Due date for the open vendor invoice.</span></span>  
9. <span data-ttu-id="4f255-119">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="4f255-119">In the list, find and select the desired record.</span></span>
10. <span data-ttu-id="4f255-120">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="4f255-120">In the list, click the link in the selected row.</span></span>
11. <span data-ttu-id="4f255-121">Selecione o tipo de intervalos de período de liquidação.</span><span class="sxs-lookup"><span data-stu-id="4f255-121">Select a type for the settlement period intervals.</span></span>
12. <span data-ttu-id="4f255-122">Insira o número das Unidades de intervalo de período por período.</span><span class="sxs-lookup"><span data-stu-id="4f255-122">Enter the number of Period interval units per period.</span></span> <span data-ttu-id="4f255-123">Por exemplo, um trimestre tem 3 meses.</span><span class="sxs-lookup"><span data-stu-id="4f255-123">For example, a quarter has 3 months.</span></span>
13. <span data-ttu-id="4f255-124">Marque ou desmarque o processamento em lotes de uso da caixa de seleção de liquidação do imposto sobre vendas.</span><span class="sxs-lookup"><span data-stu-id="4f255-124">Select or clear the Use batch processing for sales tax settlement check box.</span></span>
    * <span data-ttu-id="4f255-125">O processo de liquidação para o período de liquidação pode ser processado como trabalhos em lotes no plano de fundo.</span><span class="sxs-lookup"><span data-stu-id="4f255-125">The settlement process for the settlement period can be processed as batch job in the background.</span></span> <span data-ttu-id="4f255-126">Isso é recomendável para um grande número de transações de imposto em um intervalo de períodos.</span><span class="sxs-lookup"><span data-stu-id="4f255-126">This is recommended for a large number of tax transactions within a period interval.</span></span>  
    > [!NOTE]
    > <span data-ttu-id="4f255-127">No momento, isso não tem suporte na Áustria, Bélgica, Espanha, Itália, no Japão e nos Países Baixos.</span><span class="sxs-lookup"><span data-stu-id="4f255-127">Currently this is not supported in Austria, Belgium, Spain, Italy, Japan, and the Netherlands.</span></span>
14. <span data-ttu-id="4f255-128">Marque ou desmarque a caixa de seleção Impedir a geração de transações de impostos de contrapartida.</span><span class="sxs-lookup"><span data-stu-id="4f255-128">Select or clear the Prevent generating offset tax transactions check box.</span></span>
    * <span data-ttu-id="4f255-129">Por padrão, o sistema gera transações de impostos de contrapartida durante o processo de liquidação, o que pode causar um problema de desempenho se houver um grande número de transações de imposto durante um intervalo de período.</span><span class="sxs-lookup"><span data-stu-id="4f255-129">By default, the system generates offset tax transactions during the settlement process, which cause can performance issue if there are a large number of tax transactions within a period interval.</span></span> <span data-ttu-id="4f255-130">Marque essa caixa de seleção para impedir a geração de transações de impostos de contrapartida.</span><span class="sxs-lookup"><span data-stu-id="4f255-130">Select this check box to prevent generating offset tax transactions.</span></span>
15. <span data-ttu-id="4f255-131">Expanda a guia dos intervalos de períodos.</span><span class="sxs-lookup"><span data-stu-id="4f255-131">Expand the Period intervals tab.</span></span>
16. <span data-ttu-id="4f255-132">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="4f255-132">Click Add.</span></span>
17. <span data-ttu-id="4f255-133">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="4f255-133">In the list, mark the selected row.</span></span>
18. <span data-ttu-id="4f255-134">No campo De data, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="4f255-134">In the From date field, enter a date.</span></span>
19. <span data-ttu-id="4f255-135">No campo Para data, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="4f255-135">In the To date field, enter a date.</span></span>
20. <span data-ttu-id="4f255-136">Clique em Novo intervalo do período.</span><span class="sxs-lookup"><span data-stu-id="4f255-136">Click New period interval.</span></span>
    * <span data-ttu-id="4f255-137">Depois que o primeiro intervalo de período tiver sido inserido, os novos períodos podem ser criados automaticamente.</span><span class="sxs-lookup"><span data-stu-id="4f255-137">Once the first period interval has been entered, new periods can be created automatically.</span></span> <span data-ttu-id="4f255-138">Você pode voltar e adicionar novos intervalos de período conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="4f255-138">You can come back and add new period intervals as required.</span></span>  
21. <span data-ttu-id="4f255-139">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="4f255-139">Close the page.</span></span>

