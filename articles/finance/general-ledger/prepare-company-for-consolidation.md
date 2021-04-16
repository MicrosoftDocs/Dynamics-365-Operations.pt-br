---
title: Preparar uma entidade legal para o processo de consolidação
description: Durante uma consolidação, você reúne transações de vários conjuntos de contas de entidade legal em um único conjunto de contas de entidade legal. Este tópico explica como preparar uma entidade legal para uma consolidação.
author: jinniew
ms.date: 10/30/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2018-10-30
ms.dyn365.ops.version: 8.0.1
ms.openlocfilehash: 6f718bef3b1b07d3bb03dbf6acbf1cdf58aa7b8a
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5815467"
---
# <a name="prepare-a-legal-entity-for-the-consolidation-process"></a><span data-ttu-id="9b679-104">Preparar uma entidade legal para o processo de consolidação</span><span class="sxs-lookup"><span data-stu-id="9b679-104">Prepare a legal entity for the consolidation process</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9b679-105">Durante uma consolidação, você reúne transações de vários conjuntos de contas de entidade legal em um único conjunto de contas de entidade legal.</span><span class="sxs-lookup"><span data-stu-id="9b679-105">During a consolidation, you gather transactions from several sets of legal entity accounts into a single set of legal entity accounts.</span></span> <span data-ttu-id="9b679-106">Este tópico explica como preparar uma entidade legal para uma consolidação.</span><span class="sxs-lookup"><span data-stu-id="9b679-106">This topic explains how to prepare a legal entity for a consolidation.</span></span>

> [!NOTE]
> <span data-ttu-id="9b679-107">É recomendável usar o Management Reporter para Microsoft Dynamics 365 Finance para combinar os resultados financeiros para várias entidades legais em um formato consolidado.</span><span class="sxs-lookup"><span data-stu-id="9b679-107">We recommend that you use Management Reporter for Microsoft Dynamics 365 Finance to combine the financial results for multiple legal entities in a consolidated format.</span></span> <span data-ttu-id="9b679-108">O Management Reporter permite criar relatórios financeiros consolidados nas entidades legais, usar o Excel para importar dados de consolidação de outras fontes e traduzir os valores em qualquer número de moedas de relatório sem a necessidade de executar o processo de consolidação no Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="9b679-108">Management Reporter lets you create consolidated financial reports across legal entities, use Excel to import consolidation data from other sources, and translate amounts into any number of reporting currencies without having to run the consolidation process in Dynamics 365 Finance.</span></span>

<span data-ttu-id="9b679-109">É possível imprimir relatórios, como demonstrativos financeiros, da entidade legal consolidada.</span><span class="sxs-lookup"><span data-stu-id="9b679-109">You can print reports, such as financial statements, from the consolidated legal entity.</span></span> <span data-ttu-id="9b679-110">No entanto, não é possível usar a entidade legal consolidada para transações diárias.</span><span class="sxs-lookup"><span data-stu-id="9b679-110">However, you can't use the consolidated legal entity for daily transactions.</span></span>

<span data-ttu-id="9b679-111">Você pode consolidar dados das entidades legais que usam bancos de dados que não são a entidade legal consolidada.</span><span class="sxs-lookup"><span data-stu-id="9b679-111">You can consolidate data from legal entities that use different databases than the consolidated legal entity.</span></span> <span data-ttu-id="9b679-112">Esse processo de consolidação é conhecido como uma *consolidação de importação*.</span><span class="sxs-lookup"><span data-stu-id="9b679-112">This consolidation process is referred to as an *import consolidation*.</span></span> <span data-ttu-id="9b679-113">Como alternativa, as entidades legais podem usar o mesmo banco de dados que a entidade legal consolidada.</span><span class="sxs-lookup"><span data-stu-id="9b679-113">Alternatively, the legal entities can use the same database as the consolidated legal entity.</span></span> <span data-ttu-id="9b679-114">Esse processo de consolidação é conhecido como uma *consolidação online*.</span><span class="sxs-lookup"><span data-stu-id="9b679-114">This consolidation process is referred to as an *online consolidation*.</span></span>

<span data-ttu-id="9b679-115">A entidade legal consolidada coleta os resultados e saldos das subsidiárias.</span><span class="sxs-lookup"><span data-stu-id="9b679-115">The consolidated legal entity collects the results and balances of the subsidiaries.</span></span> <span data-ttu-id="9b679-116">Para preparar uma entidade legal consolidada para uma consolidação, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="9b679-116">To prepare a consolidated legal entity for a consolidation, follow these steps.</span></span>

1. <span data-ttu-id="9b679-117">Vá para **Contabilidade \> Configuração \> Organização \> Entidades legais**.</span><span class="sxs-lookup"><span data-stu-id="9b679-117">Go to **General ledger \> Setup \> Organization \> Legal entities**.</span></span>
2. <span data-ttu-id="9b679-118">Selecione **Novo** para criar a entidade legal que será a entidade legal consolidada.</span><span class="sxs-lookup"><span data-stu-id="9b679-118">Select **New** to create the legal entity that will be the consolidated legal entity.</span></span>
3. <span data-ttu-id="9b679-119">Marque a caixa de seleção **Usar para processo de consolidação financeira** e insira informações sobre a entidade legal consolidada.</span><span class="sxs-lookup"><span data-stu-id="9b679-119">Select the **Use for financial consolidation process** check box, and then enter information about the consolidated legal entity.</span></span> <span data-ttu-id="9b679-120">Insira essas informações exatamente como deseja que apareçam nos demonstrativos financeiros da entidade legal consolidada.</span><span class="sxs-lookup"><span data-stu-id="9b679-120">Be sure to enter this information exactly as you want it to appear on financial statements for the consolidated legal entity.</span></span>
4. <span data-ttu-id="9b679-121">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="9b679-121">Close the page.</span></span>
5. <span data-ttu-id="9b679-122">Selecione a entidade legal consolidada no campo do canto superior direito da página e, depois, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="9b679-122">Select the consolidated legal entity in the field in the upper-right corner of the page, and then select **OK**.</span></span>
6. <span data-ttu-id="9b679-123">Vá para **Contabilidade \> Configuração \> Razão**.</span><span class="sxs-lookup"><span data-stu-id="9b679-123">Go to **General ledger \> Setup \> Ledger**.</span></span>
7. <span data-ttu-id="9b679-124">Selecione o plano de contas, o calendário fiscal, a moeda contábil, uma moeda de relatório opcional e o tipo de taxa de câmbio padrão para a entidade legal consolidada.</span><span class="sxs-lookup"><span data-stu-id="9b679-124">Select the chart of accounts, the fiscal calendar, the accounting currency, an optional reporting currency, and the default type of exchange rate for the consolidated legal entity.</span></span> 
8. <span data-ttu-id="9b679-125">Acesse **Contabilidade \> Configuração \> Moedas \> Taxas de câmbio de moedas**.</span><span class="sxs-lookup"><span data-stu-id="9b679-125">Go to **General ledger \> Setup \> Currency \> Currency exchange rates**.</span></span>
9. <span data-ttu-id="9b679-126">Configure as taxas de câmbio de moedas nos períodos relevantes para as moedas das entidades legais de subsidiárias.</span><span class="sxs-lookup"><span data-stu-id="9b679-126">Set up currency exchange rates in relevant periods for the currencies of the subsidiary legal entities.</span></span>
10. <span data-ttu-id="9b679-127">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="9b679-127">Close the page.</span></span>
11. <span data-ttu-id="9b679-128">Se a entidade legal consolidada tiver subsidiárias que usem moedas estrangeiras, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="9b679-128">If the consolidated legal entity has subsidiaries that use foreign currencies, follow these steps:</span></span>

    1. <span data-ttu-id="9b679-129">Acesse **Contabilidade \> Configuração \> Lançamento \> Contas para transações automáticas**.</span><span class="sxs-lookup"><span data-stu-id="9b679-129">Go to **General ledger \> Setup \> Posting \> Accounts for automatic transactions**.</span></span>
    2. <span data-ttu-id="9b679-130">No campo **Tipo de lançamento**, selecione uma conta apropriada:</span><span class="sxs-lookup"><span data-stu-id="9b679-130">In the **Posting type** field, select an appropriate account:</span></span>

        - <span data-ttu-id="9b679-131">Se a entidade legal tiver subsidiárias estrangeiras que sejam financeira ou operacionalmente interdependentes da entidade legal pai, selecione uma conta apropriada para o tipo de lançamento **Conta de lucros e perdas para diferenças de consolidação**.</span><span class="sxs-lookup"><span data-stu-id="9b679-131">If the legal entity has foreign subsidiaries that are financially or operationally interdependent with the parent legal entity, select an appropriate account for the **Profit and loss account for consolidation differences** posting type.</span></span>
        - <span data-ttu-id="9b679-132">Se estiver consolidando uma subsidiária que seja financeira ou operacionalmente independente da entidade legal principal, ou uma entidade legal que contenha os resultados de várias subsidiárias que sejam financeira ou operacionalmente independentes da entidade legal principal, e se estiver usando métodos de conversão para consolidar os dados, selecione uma conta apropriada para o tipo de lançamento **Conta de saldo para diferenças de consolidação**.</span><span class="sxs-lookup"><span data-stu-id="9b679-132">If you're consolidating a subsidiary that is financially and operationally independent of the parent legal entity, or a legal entity that contains the results of several subsidiaries that are financially and operationally independent of the parent legal entity, and if you're using translation methods to consolidate the data, select an appropriate account for the **Balance account for consolidation differences** posting type.</span></span>

    3. <span data-ttu-id="9b679-133">No campo **Conta principal**, selecione as contas principais que devem ser usadas para ajustes de reavaliação de moeda estrangeira.</span><span class="sxs-lookup"><span data-stu-id="9b679-133">In the **Main account** field, select the main accounts that should be used for foreign currency revaluation adjustments.</span></span>
    4. <span data-ttu-id="9b679-134">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="9b679-134">Close the page.</span></span>

    <span data-ttu-id="9b679-135">Ao criar a entidade legal consolidada antecipadamente em um período, você poderá reavaliar os valores de moeda estrangeira à medida que as taxas de câmbio mudarem durante o período de consolidação.</span><span class="sxs-lookup"><span data-stu-id="9b679-135">If you create the consolidated legal entity early in a period, you can revalue foreign currency amounts as exchange rates change during the consolidation period.</span></span>

<span data-ttu-id="9b679-136">A entidade legal consolidada agora está configurada para o trabalho periódico **Consolidar**.</span><span class="sxs-lookup"><span data-stu-id="9b679-136">The consolidated legal entity is now set up for the **Consolidate** periodic job.</span></span> <span data-ttu-id="9b679-137">Você pode fazer uma consolidação de importação ou uma consolidação online.</span><span class="sxs-lookup"><span data-stu-id="9b679-137">You can do either an import consolidation or an online consolidation.</span></span>

- <span data-ttu-id="9b679-138">Para fazer uma consolidação de importação, acesse **Contabilidade \> Periódico \> Consolidar \> Consolidar \[importar de\]**.</span><span class="sxs-lookup"><span data-stu-id="9b679-138">To do an import consolidation, go to **General ledger \> Periodic \> Consolidate \> Consolidate \[Import from\]**.</span></span>
- <span data-ttu-id="9b679-139">Para fazer uma consolidação online, acesse **Contabilidade \> Periódico \> Consolidar \> Consolidar \[Online\]**.</span><span class="sxs-lookup"><span data-stu-id="9b679-139">To do an online consolidation, go to **General ledger \> Periodic \> Consolidate \> Consolidate \[Online\]**.</span></span>

> [!NOTE]
> <span data-ttu-id="9b679-140">Para poder processar a consolidação, prepare as entidades legais subsidiárias para a consolidação.</span><span class="sxs-lookup"><span data-stu-id="9b679-140">Before you can process the consolidation, you must prepare the subsidiary legal entities for consolidation.</span></span> <span data-ttu-id="9b679-141">Para obter mais informações, consulte [Configurar uma entidade legal subsidiária para consolidação](set-up-subsidiary-company-for-consolidation.md).</span><span class="sxs-lookup"><span data-stu-id="9b679-141">For more information, see [Set up a subsidiary legal entity for consolidation](set-up-subsidiary-company-for-consolidation.md).</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]