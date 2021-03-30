---
title: Configurar períodos de liquidação do imposto
description: Este tópico explica como configurar períodos de liquidação de imposto no Dynamics 365 Finance.
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
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e2e5340150623057e233ed0acf487c42c61deba2
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5222110"
---
# <a name="set-up-sales-tax-settlement-periods"></a><span data-ttu-id="1b746-103">Configurar períodos de liquidação do imposto</span><span class="sxs-lookup"><span data-stu-id="1b746-103">Set up sales tax settlement periods</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="1b746-104">Este tópico explica como configurar períodos de liquidação do imposto.</span><span class="sxs-lookup"><span data-stu-id="1b746-104">This topic explains how to set up sales tax settlement periods.</span></span> <span data-ttu-id="1b746-105">Períodos de liquidação de impostos contêm informações sobre os intervalos de período para os quais os impostos precisam ser relatados e pagos.</span><span class="sxs-lookup"><span data-stu-id="1b746-105">Sales tax settlement periods contain information about the period intervals for which sales tax needs to be reported and paid.</span></span> <span data-ttu-id="1b746-106">Um processo de pagamento pode ser executado por um período de liquidação para um intervalo de datas específico.</span><span class="sxs-lookup"><span data-stu-id="1b746-106">A settlement process can be run for a settlement period for a specific date interval.</span></span> <span data-ttu-id="1b746-107">Todos os códigos de imposto associados ao período de liquidação serão liquidados.</span><span class="sxs-lookup"><span data-stu-id="1b746-107">All tax codes associated with the settlement period will be settled.</span></span> <span data-ttu-id="1b746-108">Dependendo da configuração da autoridade de impostos sobre vendas relacionada, a obrigação fiscal é lançada a um fornecedor ou em uma conta contábil.</span><span class="sxs-lookup"><span data-stu-id="1b746-108">Depending on the set up of the related Sales tax authority, the tax liability is posted either to a vendor or a General ledger account.</span></span>

<span data-ttu-id="1b746-109">Esta tarefa usa a empresa de demonstração USMF.</span><span class="sxs-lookup"><span data-stu-id="1b746-109">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="1b746-110">No painel de navegação, acesse **Módulos > Imposto > Impostos indiretos > Impostos > Períodos de liquidação de imposto**.</span><span class="sxs-lookup"><span data-stu-id="1b746-110">In the navigation pane, go to **Modules > Tax > Indirect taxes > Sales tax > Sales tax settlement periods**.</span></span>
2. <span data-ttu-id="1b746-111">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="1b746-111">Select **New**.</span></span>
3. <span data-ttu-id="1b746-112">No campo de **Período de liquidação**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="1b746-112">In the **Settlement period** field, type a value.</span></span>
4. <span data-ttu-id="1b746-113">No campo **Descrição**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="1b746-113">In the **Description** field, type a value.</span></span>
5. <span data-ttu-id="1b746-114">No campo **Autoridade**, selecione a autoridade do imposto sobre vendas que recebe os relatórios e os pagamentos relacionados que são criados para o período de liquidação.</span><span class="sxs-lookup"><span data-stu-id="1b746-114">In the **Authority** field, select the sales tax authority that receives the reports and the payments that are created for the settlement period.</span></span>
6. <span data-ttu-id="1b746-115">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="1b746-115">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="1b746-116">No campo **Termos de pagamento**, selecione o registro desejado no menu suspenso.</span><span class="sxs-lookup"><span data-stu-id="1b746-116">In the **Terms of payment** field, select the desired record in the drop-down menu.</span></span> <span data-ttu-id="1b746-117">A autoridade do imposto sobre vendas relacionada pode ser configurada como um fornecedor e a liquidação do imposto sobre vendas criará uma nota fiscal de fornecedor aberta.</span><span class="sxs-lookup"><span data-stu-id="1b746-117">The related Sales tax authority can be set up as a vendor and the Sales tax settlement will create an open vendor invoice.</span></span> <span data-ttu-id="1b746-118">Os Termos de pagamento definem a Data de vencimento para a fatura de fornecedor aberta.</span><span class="sxs-lookup"><span data-stu-id="1b746-118">The Terms of payment defines the Due date for the open vendor invoice.</span></span>  
8. <span data-ttu-id="1b746-119">Selecione o tipo de intervalos de período de liquidação.</span><span class="sxs-lookup"><span data-stu-id="1b746-119">Select a type for the settlement period intervals.</span></span>
9. <span data-ttu-id="1b746-120">Insira o número das Unidades de intervalo de período por período.</span><span class="sxs-lookup"><span data-stu-id="1b746-120">Enter the number of Period interval units per period.</span></span> <span data-ttu-id="1b746-121">Por exemplo, um trimestre tem 3 meses.</span><span class="sxs-lookup"><span data-stu-id="1b746-121">For example, a quarter has 3 months.</span></span>
10. <span data-ttu-id="1b746-122">Marque ou desmarque o **Usar processamento em lotes para liquidação de imposto**.</span><span class="sxs-lookup"><span data-stu-id="1b746-122">Select or clear the **Use batch processing for sales tax settlement** check box.</span></span> <span data-ttu-id="1b746-123">O processo de liquidação para o período de liquidação pode ser processado como trabalhos em lotes no plano de fundo.</span><span class="sxs-lookup"><span data-stu-id="1b746-123">The settlement process for the settlement period can be processed as batch job in the background.</span></span> <span data-ttu-id="1b746-124">Isso é recomendável para um grande número de transações de imposto em um intervalo de períodos.</span><span class="sxs-lookup"><span data-stu-id="1b746-124">This is recommended for a large number of tax transactions within a period interval.</span></span>  
    > [!NOTE]
    > <span data-ttu-id="1b746-125">No momento, isso não tem suporte na Espanha, no Japão e nos Países Baixos.</span><span class="sxs-lookup"><span data-stu-id="1b746-125">Currently this is not supported in Spain, Japan, and the Netherlands.</span></span>
11. <span data-ttu-id="1b746-126">Marque ou desmarque a caixa de seleção **Impedir a geração de transações de impostos de contrapartida**.</span><span class="sxs-lookup"><span data-stu-id="1b746-126">Select or clear the **Prevent generating offset tax transactions** check box.</span></span> <span data-ttu-id="1b746-127">Por padrão, o sistema gera transações de impostos de contrapartida durante o processo de liquidação, o que pode causar um problema de desempenho se houver um grande número de transações de imposto durante um intervalo de período.</span><span class="sxs-lookup"><span data-stu-id="1b746-127">By default, the system generates offset tax transactions during the settlement process, which cause can performance issue if there are a large number of tax transactions within a period interval.</span></span> <span data-ttu-id="1b746-128">Marque essa caixa de seleção para impedir a geração de transações de impostos de contrapartida.</span><span class="sxs-lookup"><span data-stu-id="1b746-128">Select this check box to prevent generating offset tax transactions.</span></span>
12. <span data-ttu-id="1b746-129">Expanda a guia **Intervalos de períodos**.</span><span class="sxs-lookup"><span data-stu-id="1b746-129">Expand the **Period intervals** tab.</span></span>
13. <span data-ttu-id="1b746-130">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="1b746-130">Select **Add**.</span></span>
14. <span data-ttu-id="1b746-131">No campo **Data inicial** na nova linha, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="1b746-131">In the **From date** field in the new row, enter a date.</span></span>
15. <span data-ttu-id="1b746-132">No campo **Data final**, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="1b746-132">In the **To date** field, enter a date.</span></span>
16. <span data-ttu-id="1b746-133">Selecione **Novo intervalo do período**.</span><span class="sxs-lookup"><span data-stu-id="1b746-133">Select **New period interval**.</span></span> <span data-ttu-id="1b746-134">Depois que o primeiro intervalo de período tiver sido inserido, os novos períodos podem ser criados automaticamente.</span><span class="sxs-lookup"><span data-stu-id="1b746-134">Once the first period interval has been entered, new periods can be created automatically.</span></span> <span data-ttu-id="1b746-135">Você pode voltar e adicionar novos intervalos de período conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="1b746-135">You can come back and add new period intervals as required.</span></span>  
17. <span data-ttu-id="1b746-136">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="1b746-136">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]