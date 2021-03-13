---
title: Configurar uma entidade legal subsidiária para consolidação
description: Este tópico explica como trabalhar com planos de contas para empresas de consolidação.
author: jinniew
manager: AnnBe
ms.date: 10/30/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2020-10-31
ms.dyn365.ops.version: 8.0.1
ms.openlocfilehash: 4ffe0ac0b11a3f58ca4a893d8786f04b4067b270
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4975523"
---
# <a name="set-up-a-subsidiary-legal-entity-for-consolidation"></a><span data-ttu-id="3807f-103">Configurar uma entidade legal subsidiária para consolidação</span><span class="sxs-lookup"><span data-stu-id="3807f-103">Set up a subsidiary legal entity for consolidation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="3807f-104">O método usado para preparar contas subsidiárias para a consolidação depende, em partes, da extensão para a qual a estrutura do plano de contas na entidade legal subsidiária reflete o plano de contas na entidade legal consolidada.</span><span class="sxs-lookup"><span data-stu-id="3807f-104">The method that you use to prepare subsidiary accounts for consolidation depends in part on the extent to which the structure of the chart of accounts in the subsidiary legal entity reflects the chart of accounts in the consolidated legal entity.</span></span>

<span data-ttu-id="3807f-105">Antes de iniciar uma consolidação como parte do fechamento do período, execute as atividades preparatórias para o fechamento, mas não feche as contas das subsidiárias até que a consolidação esteja concluída.</span><span class="sxs-lookup"><span data-stu-id="3807f-105">Before you start a consolidation as part of period-end closing, complete the preparatory activities for the period-end closing, but don't close the subsidiary accounts until the consolidation is completed.</span></span> <span data-ttu-id="3807f-106">Para saber mais sobre o fechamento no fim do período, consulte [Fechar a contabilidade no fim do período](close-general-ledger-at-period-end.md) e [Fechar o ano fiscal](tasks/close-fiscal-year.md).</span><span class="sxs-lookup"><span data-stu-id="3807f-106">For more information about period-end closing, see [Close the general ledger at period end](close-general-ledger-at-period-end.md) and [Close the fiscal year](tasks/close-fiscal-year.md).</span></span>

> [!NOTE]
>  <span data-ttu-id="3807f-107">É recomendável usar o Management Reporter para Microsoft Dynamics 365 Finance para combinar os resultados financeiros para várias entidades legais em um formato consolidado.</span><span class="sxs-lookup"><span data-stu-id="3807f-107">We recommend that you use Management Reporter for Microsoft Dynamics 365 Finance to combine the financial results for multiple legal entities in a consolidated format.</span></span> <span data-ttu-id="3807f-108">O Management Reporter permite criar relatórios financeiros consolidados nas entidades legais, usar o Excel para importar dados de consolidação de outras fontes e traduzir os valores em qualquer número de moedas de relatório sem a necessidade de executar o processo de consolidação no Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="3807f-108">Management Reporter lets you create consolidated financial reports across legal entities, use Excel to import consolidation data from other sources, and translate amounts into any number of reporting currencies without having to run the consolidation process in Dynamics 365 Finance.</span></span>

## <a name="map-subsidiary-main-accounts-to-consolidated-main-accounts"></a><span data-ttu-id="3807f-109">Mapear as contas principais subsidiárias para as contas principais consolidadas</span><span class="sxs-lookup"><span data-stu-id="3807f-109">Map subsidiary main accounts to consolidated main accounts</span></span>

<span data-ttu-id="3807f-110">Se o plano de contas da entidade legal subsidiária não seguir o plano de contas na entidade legal consolidada, você poderá mapear as contas principais na subsidiária para as contas principais na entidade legal consolidada.</span><span class="sxs-lookup"><span data-stu-id="3807f-110">If the chart of accounts in the subsidiary legal entity doesn't follow the chart of accounts in the consolidated legal entity, you can map the main accounts in the subsidiary to the main accounts in the consolidated legal entity.</span></span>

1. <span data-ttu-id="3807f-111">Na *Entidade legal subsidiária*, vá para **Contabilidade \> Configuração** \> **Plano de contas \> Plano de contas**.</span><span class="sxs-lookup"><span data-stu-id="3807f-111">In the *subsidiary legal entity*, go to **General ledger \> Setup** \> **Chart of accounts \> Chart of accounts**.</span></span>
2. <span data-ttu-id="3807f-112">Selecione um plano de contas.</span><span class="sxs-lookup"><span data-stu-id="3807f-112">Select a chart of accounts.</span></span> <span data-ttu-id="3807f-113">Na guia rápida **Contas principais**, selecione uma conta principal e então selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="3807f-113">On the **Main accounts** FastTab, select a main account, and then select **Edit**.</span></span>
3. <span data-ttu-id="3807f-114">Selecione cada conta principal subsidiária que deve ser mapeada para consolidar uma conta principal.</span><span class="sxs-lookup"><span data-stu-id="3807f-114">Select each subsidiary main account that must be mapped to a consolidated main account.</span></span> <span data-ttu-id="3807f-115">Na guia rápida **Geral**, no campo **Conta de consolidação**, insira a conta da entidade legal consolidada para a qual o saldo ou as transações da conta principal subsidiária selecionada devem ser transferidos.</span><span class="sxs-lookup"><span data-stu-id="3807f-115">On the **General** FastTab, in the **Consolidation account** field, enter the account in the consolidated legal entity that the balance or transactions of the selected subsidiary main account must be transferred to.</span></span> <span data-ttu-id="3807f-116">Você pode inserir a mesma conta principal consolidada para várias contas subsidiárias.</span><span class="sxs-lookup"><span data-stu-id="3807f-116">You can enter the same consolidated main account for several subsidiary accounts.</span></span>

    > [!NOTE]
    > <span data-ttu-id="3807f-117">Se os tipos de conta principais das contas subsidiárias que estão mapeadas forem diferentes dos tipos de conta principais de contas na entidade legal consolidada, os valores das contas que tem um tipo de conta principal de **Total** serão substituídos durante a consolidação.</span><span class="sxs-lookup"><span data-stu-id="3807f-117">If the main account types of the subsidiary accounts that are mapped differ from the main account types of the accounts in the consolidated legal entity, the values of accounts that have a main account type of **Total** are overwritten during consolidation.</span></span>

4. <span data-ttu-id="3807f-118">Prepare relatórios e demonstrativos financeiros para a entidade legal consolidada que se baseiem em dimensões financeiras.</span><span class="sxs-lookup"><span data-stu-id="3807f-118">Prepare reports and financial statements for the consolidated legal entity that are based on financial dimensions.</span></span> <span data-ttu-id="3807f-119">Siga estas etapas para mapear as dimensões financeiras usadas nas contas da subsidiária para as dimensões financeiras na entidade legal consolidada:</span><span class="sxs-lookup"><span data-stu-id="3807f-119">Follow these steps to map the financial dimensions that are used in the subsidiary accounts to the financial dimensions in the consolidated legal entity:</span></span>

    1. <span data-ttu-id="3807f-120">Na *Entidade legal subsidiária*, vá para **Contabilidade \> Configuração \> Dimensões financeiras \> Dimensões financeiras**, selecione uma dimensão financeira e selecione **Valores da dimensão financeira**.</span><span class="sxs-lookup"><span data-stu-id="3807f-120">In the *subsidiary legal entity*, go to **General ledger \> Setup \> Financial dimensions \> Financial dimensions**, select a financial dimension, and then select **Financial dimension values**.</span></span>
    2. <span data-ttu-id="3807f-121">Selecione o valor da dimensão financeira para mapear para um valor da dimensão financeira na entidade legal consolidada.</span><span class="sxs-lookup"><span data-stu-id="3807f-121">Select the financial dimension value to map to a different financial dimension value in the consolidated legal entity.</span></span>
    3. <span data-ttu-id="3807f-122">Na guia rápida **Geral**, no campo **Dimensão do grupo**, insira a dimensão financeira na entidade legal consolidada.</span><span class="sxs-lookup"><span data-stu-id="3807f-122">On the **General** FastTab, in the **Group dimension** field, enter the financial dimension in the consolidated legal entity.</span></span> <span data-ttu-id="3807f-123">Durante a consolidação, essa dimensão financeira será atribuída a transações e saldos que usem a dimensão financeira selecionada na entidade legal subsidiária.</span><span class="sxs-lookup"><span data-stu-id="3807f-123">During consolidation, this financial dimension will be assigned to transactions and balances that use the selected financial dimension in the subsidiary legal entity.</span></span> <span data-ttu-id="3807f-124">As dimensões financeiras que você inserir aqui devem ser usadas na entidade legal consolidada.</span><span class="sxs-lookup"><span data-stu-id="3807f-124">The financial dimensions that you enter here must be used in the consolidated legal entity.</span></span> <span data-ttu-id="3807f-125">Você pode atribuir a dimensão financeira que é usada como a dimensão financeira do grupo em várias dimensões financeiras subsidiárias.</span><span class="sxs-lookup"><span data-stu-id="3807f-125">You can assign the financial dimension that is used as the group financial dimension to several subsidiary financial dimensions.</span></span>

5. <span data-ttu-id="3807f-126">Se você estiver fazendo uma consolidação online, siga estas etapas para garantir que as transferências ocorram como pretendidas:</span><span class="sxs-lookup"><span data-stu-id="3807f-126">If you're doing an online consolidation, follow these steps to ensure that the transfers occur as you intend:</span></span>

    1. <span data-ttu-id="3807f-127">Na *Entidade legal consolidada*, vá para **Contabilidade \> Periódico \> Consolidar \> Consolidar \[Exportar para\]** para abrir a página **Consolidar \[Online\]**.</span><span class="sxs-lookup"><span data-stu-id="3807f-127">In the *consolidated legal entity*, go to **General ledger \> Periodic \> Consolidate \> Consolidate \[Export to\]** to open the **Consolidate \[Online\]** page.</span></span>
    2. <span data-ttu-id="3807f-128">Na guia **Critérios**, marque a caixa de seleção **Usar conta de consolidação**.</span><span class="sxs-lookup"><span data-stu-id="3807f-128">On the **Criteria** tab, select the **Use consolidation account** check box.</span></span>
    3. <span data-ttu-id="3807f-129">Na guia **Dimensões financeiras**, selecione as dimensões financeiras apropriadas.</span><span class="sxs-lookup"><span data-stu-id="3807f-129">On the **Financial dimensions** tab, select the appropriate financial dimensions.</span></span>
    4. <span data-ttu-id="3807f-130">Para cada dimensão financeira que você selecionar, insira um número no campo **Ordem dos segmentos** para indicar a ordem em que as dimensões devem ser exibidas</span><span class="sxs-lookup"><span data-stu-id="3807f-130">For each financial dimension that you select, enter a number in the **Segment order** field to indicate the order that the dimensions should appear in.</span></span>

## <a name="maintain-the-same-chart-of-accounts-in-the-subsidiary-and-consolidated-legal-entities"></a><span data-ttu-id="3807f-131">Manter o mesmo plano de contas da entidade legal subsidiária e consolidada</span><span class="sxs-lookup"><span data-stu-id="3807f-131">Maintain the same chart of accounts in the subsidiary and consolidated legal entities</span></span>

<span data-ttu-id="3807f-132">As contas principais na entidade legal subsidiária podem ter o mesmo números de conta e a mesma estrutura para o plano de conta das contas principais na entidade legal consolidada.</span><span class="sxs-lookup"><span data-stu-id="3807f-132">The main accounts in the subsidiary legal entity might have the same account numbers and the same structure for the chart of accounts as the main accounts in the consolidated legal entity.</span></span> <span data-ttu-id="3807f-133">Nesse caso, não será necessário mapear manualmente as contas principais das subsidiárias para as contas principais na entidade legal consolidada.</span><span class="sxs-lookup"><span data-stu-id="3807f-133">In this case, you don't have to manually map the main accounts in the subsidiary to the main accounts in the consolidated legal entity.</span></span>

<span data-ttu-id="3807f-134">Antes de iniciar a consolidação, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="3807f-134">Before you start the consolidation, follow these steps.</span></span>

1. <span data-ttu-id="3807f-135">Na *Entidade legal consolidada*, vá para **Contabilidade \> Periódico \> Consolidar \> Consolidar \[Exportar para\]** para abrir a página **Consolidar \[Online\]**.</span><span class="sxs-lookup"><span data-stu-id="3807f-135">In the *consolidated legal entity*, go to **General ledger \> Periodic \> Consolidate \> Consolidate \[Export to\]** to open the **Consolidate \[Online\]** page.</span></span>
2. <span data-ttu-id="3807f-136">Marque a caixa de seleção **Usar conta de consolidação**.</span><span class="sxs-lookup"><span data-stu-id="3807f-136">Select the **Use consolidation account** check box.</span></span> <span data-ttu-id="3807f-137">Durante a consolidação, as transações e os saldos serão transferidos automaticamente para a conta corrente.</span><span class="sxs-lookup"><span data-stu-id="3807f-137">During consolidation, transactions and balances will automatically be transferred to the correct account.</span></span>

> [!NOTE]
> <span data-ttu-id="3807f-138">Se as contas não corresponderem, a consolidação será interrompida e você receberá uma mensagem.</span><span class="sxs-lookup"><span data-stu-id="3807f-138">If the accounts don't correspond, the consolidation stops, and you receive a message.</span></span>

## <a name="create-a-chart-of-accounts-for-the-consolidated-legal-entity-based-on-an-existing-chart-of-accounts"></a><span data-ttu-id="3807f-139">Criar um plano de contas para a entidade legal consolidada, com base em um plano de contas existente</span><span class="sxs-lookup"><span data-stu-id="3807f-139">Create a chart of accounts for the consolidated legal entity, based on an existing chart of accounts</span></span>

<span data-ttu-id="3807f-140">Você pode executar uma consolidação mesmo que um plano de contas ainda não tenha sido criado para a entidade legal consolidada.</span><span class="sxs-lookup"><span data-stu-id="3807f-140">You can do a consolidation even if a chart of accounts hasn't already been created in the consolidated legal entity.</span></span>

- <span data-ttu-id="3807f-141">Se tiver planejado a estrutura da conta que quer usar na entidade legal consolidada, você poderá mapear as contas subsidiárias a esta estrutura.</span><span class="sxs-lookup"><span data-stu-id="3807f-141">If you've planned the account structure that you want to use in the consolidated legal entity, you can map the subsidiary accounts to this structure.</span></span>
- <span data-ttu-id="3807f-142">Se você não mapear nenhuma conta subsidiária, as contas na entidade legal consolidada serão automaticamente criadas quando os dados subsidiários forem transferidos para a entidade legal consolidada.</span><span class="sxs-lookup"><span data-stu-id="3807f-142">If you don't map any subsidiary accounts, the accounts in the consolidated legal entity are automatically created when subsidiary data is transferred to the consolidated legal entity.</span></span> <span data-ttu-id="3807f-143">Essas contas são baseadas na conta principal.</span><span class="sxs-lookup"><span data-stu-id="3807f-143">These accounts are based on the main account.</span></span> <span data-ttu-id="3807f-144">Os dados subsequentes são acumulados nas contas na entidade legal consolidada que tem o mesmo número de conta que as contas subsidiárias.</span><span class="sxs-lookup"><span data-stu-id="3807f-144">Subsequent data is accumulated in accounts in the consolidated legal entity that have the same account number as the subsidiary accounts.</span></span>

<span data-ttu-id="3807f-145">Independentemente de você ter mapeado contas, desmarque a caixa de seleção **Usar conta de consolidação** na página **Consolidar** na entidade legal consolidada antes de executar esse tipo de consolidação.</span><span class="sxs-lookup"><span data-stu-id="3807f-145">Regardless of whether you've mapped accounts, clear the **Use consolidation account** check box on the **Consolidate** page in the consolidated legal entity before you run this type of consolidation.</span></span>

> [!NOTE]
> <span data-ttu-id="3807f-146">Você pode usar esse método para criar um plano de contas na entidade legal consolidada no plano de contas em uma das entidades legais subsidiárias.</span><span class="sxs-lookup"><span data-stu-id="3807f-146">You can use this method to create a chart of accounts in the consolidated legal entity from the chart of accounts in one of the subsidiary legal entities.</span></span> <span data-ttu-id="3807f-147">(Para obter mais informações, consulte [Grupos de contas de consolidação e contas adicionais de consolidação](../budgeting/consolidation-account-groups-consolidation-accounts.md).) Em seguida, atribua um princípio de conversão de consolidação apropriado a cada conta principal consolidada e execute a consolidação para todas as entidades legais subsidiárias.</span><span class="sxs-lookup"><span data-stu-id="3807f-147">(For more information, see [Consolidation account groups and additional consolidation accounts](../budgeting/consolidation-account-groups-consolidation-accounts.md).) Then assign an appropriate consolidation conversion principle to each consolidated main account, and run the consolidation for all the subsidiary legal entities.</span></span>