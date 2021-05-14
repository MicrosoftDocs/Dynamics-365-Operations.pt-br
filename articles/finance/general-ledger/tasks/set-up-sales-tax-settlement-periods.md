---
title: Configurar períodos de liquidação do imposto
description: Este tópico explica como configurar períodos de liquidação de imposto no Dynamics 365 Finance.
author: twheeloc
ms.date: 08/05/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TaxPeriod
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 83587df3963d215fec020150e6b707e431c1b6eb
ms.sourcegitcommit: ab3f5d0da6eb0177bbad720e73c58926d686f168
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/26/2021
ms.locfileid: "5944768"
---
# <a name="set-up-sales-tax-settlement-periods"></a><span data-ttu-id="cf485-103">Configurar períodos de liquidação do imposto</span><span class="sxs-lookup"><span data-stu-id="cf485-103">Set up sales tax settlement periods</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="cf485-104">Este tópico explica como configurar períodos de liquidação do imposto.</span><span class="sxs-lookup"><span data-stu-id="cf485-104">This topic explains how to set up sales tax settlement periods.</span></span> <span data-ttu-id="cf485-105">Períodos de liquidação de impostos contêm informações sobre os intervalos de período para os quais os impostos precisam ser relatados e pagos.</span><span class="sxs-lookup"><span data-stu-id="cf485-105">Sales tax settlement periods contain information about the period intervals for which sales tax needs to be reported and paid.</span></span> <span data-ttu-id="cf485-106">Um processo de pagamento pode ser executado por um período de liquidação para um intervalo de datas específico.</span><span class="sxs-lookup"><span data-stu-id="cf485-106">A settlement process can be run for a settlement period for a specific date interval.</span></span> <span data-ttu-id="cf485-107">Todos os códigos de imposto associados ao período de liquidação serão liquidados.</span><span class="sxs-lookup"><span data-stu-id="cf485-107">All tax codes associated with the settlement period will be settled.</span></span> <span data-ttu-id="cf485-108">Dependendo da configuração da autoridade de impostos sobre vendas relacionada, a obrigação fiscal é lançada a um fornecedor ou em uma conta contábil.</span><span class="sxs-lookup"><span data-stu-id="cf485-108">Depending on the set up of the related Sales tax authority, the tax liability is posted either to a vendor or a General ledger account.</span></span>

<span data-ttu-id="cf485-109">Esta tarefa usa a empresa de demonstração USMF.</span><span class="sxs-lookup"><span data-stu-id="cf485-109">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="cf485-110">No painel de navegação, acesse **Módulos > Imposto > Impostos indiretos > Impostos > Períodos de liquidação de imposto**.</span><span class="sxs-lookup"><span data-stu-id="cf485-110">In the navigation pane, go to **Modules > Tax > Indirect taxes > Sales tax > Sales tax settlement periods**.</span></span>
2. <span data-ttu-id="cf485-111">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="cf485-111">Select **New**.</span></span>
3. <span data-ttu-id="cf485-112">No campo de **Período de liquidação**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="cf485-112">In the **Settlement period** field, type a value.</span></span>
4. <span data-ttu-id="cf485-113">No campo **Descrição**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="cf485-113">In the **Description** field, type a value.</span></span>
5. <span data-ttu-id="cf485-114">No campo **Autoridade**, selecione a autoridade do imposto sobre vendas que recebe os relatórios e os pagamentos relacionados que são criados para o período de liquidação.</span><span class="sxs-lookup"><span data-stu-id="cf485-114">In the **Authority** field, select the sales tax authority that receives the reports and the payments that are created for the settlement period.</span></span>
6. <span data-ttu-id="cf485-115">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="cf485-115">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="cf485-116">No campo **Termos de pagamento**, selecione o registro desejado no menu suspenso.</span><span class="sxs-lookup"><span data-stu-id="cf485-116">In the **Terms of payment** field, select the desired record in the drop-down menu.</span></span> <span data-ttu-id="cf485-117">A autoridade do imposto sobre vendas relacionada pode ser configurada como um fornecedor e a liquidação do imposto sobre vendas criará uma nota fiscal de fornecedor aberta.</span><span class="sxs-lookup"><span data-stu-id="cf485-117">The related Sales tax authority can be set up as a vendor and the Sales tax settlement will create an open vendor invoice.</span></span> <span data-ttu-id="cf485-118">Os Termos de pagamento definem a Data de vencimento para a fatura de fornecedor aberta.</span><span class="sxs-lookup"><span data-stu-id="cf485-118">The Terms of payment defines the Due date for the open vendor invoice.</span></span>  
8. <span data-ttu-id="cf485-119">Selecione o tipo de intervalos de período de liquidação.</span><span class="sxs-lookup"><span data-stu-id="cf485-119">Select a type for the settlement period intervals.</span></span>
9. <span data-ttu-id="cf485-120">Insira o número das Unidades de intervalo de período por período.</span><span class="sxs-lookup"><span data-stu-id="cf485-120">Enter the number of Period interval units per period.</span></span> <span data-ttu-id="cf485-121">Por exemplo, um trimestre tem 3 meses.</span><span class="sxs-lookup"><span data-stu-id="cf485-121">For example, a quarter has 3 months.</span></span>
10. <span data-ttu-id="cf485-122">Marque ou desmarque o **Usar processamento em lotes para liquidação de imposto**.</span><span class="sxs-lookup"><span data-stu-id="cf485-122">Select or clear the **Use batch processing for sales tax settlement** check box.</span></span> <span data-ttu-id="cf485-123">O processo de liquidação para o período de liquidação pode ser processado como trabalhos em lotes no plano de fundo.</span><span class="sxs-lookup"><span data-stu-id="cf485-123">The settlement process for the settlement period can be processed as batch job in the background.</span></span> <span data-ttu-id="cf485-124">Isso é recomendável para um grande número de transações de imposto em um intervalo de períodos.</span><span class="sxs-lookup"><span data-stu-id="cf485-124">This is recommended for a large number of tax transactions within a period interval.</span></span>
11. <span data-ttu-id="cf485-125">Marque ou desmarque a caixa de seleção **Impedir a geração de transações de impostos de contrapartida**.</span><span class="sxs-lookup"><span data-stu-id="cf485-125">Select or clear the **Prevent generating offset tax transactions** check box.</span></span> <span data-ttu-id="cf485-126">Por padrão, o sistema gera transações de impostos de contrapartida durante o processo de liquidação, o que pode causar um problema de desempenho se houver um grande número de transações de imposto durante um intervalo de período.</span><span class="sxs-lookup"><span data-stu-id="cf485-126">By default, the system generates offset tax transactions during the settlement process, which cause can performance issue if there are a large number of tax transactions within a period interval.</span></span> <span data-ttu-id="cf485-127">Marque essa caixa de seleção para impedir a geração de transações de impostos de contrapartida.</span><span class="sxs-lookup"><span data-stu-id="cf485-127">Select this check box to prevent generating offset tax transactions.</span></span>
12. <span data-ttu-id="cf485-128">Expanda a guia **Intervalos de períodos**.</span><span class="sxs-lookup"><span data-stu-id="cf485-128">Expand the **Period intervals** tab.</span></span>
13. <span data-ttu-id="cf485-129">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="cf485-129">Select **Add**.</span></span>
14. <span data-ttu-id="cf485-130">No campo **Data inicial** na nova linha, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="cf485-130">In the **From date** field in the new row, enter a date.</span></span>
15. <span data-ttu-id="cf485-131">No campo **Data final**, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="cf485-131">In the **To date** field, enter a date.</span></span>
16. <span data-ttu-id="cf485-132">Selecione **Novo intervalo do período**.</span><span class="sxs-lookup"><span data-stu-id="cf485-132">Select **New period interval**.</span></span> <span data-ttu-id="cf485-133">Depois que o primeiro intervalo de período tiver sido inserido, os novos períodos podem ser criados automaticamente.</span><span class="sxs-lookup"><span data-stu-id="cf485-133">Once the first period interval has been entered, new periods can be created automatically.</span></span> <span data-ttu-id="cf485-134">Você pode voltar e adicionar novos intervalos de período conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="cf485-134">You can come back and add new period intervals as required.</span></span>  
17. <span data-ttu-id="cf485-135">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="cf485-135">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
