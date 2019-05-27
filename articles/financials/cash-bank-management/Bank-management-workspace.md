---
title: Espaço de trabalho de gerenciamento bancário
description: Este tópico fornece informações sobre o espaço de trabalho de gerenciamento de banco. Este espaço de trabalho mostra informações relacionadas às contas bancárias da empresa, e inclui uma exibição de Resumo e uma pagina de análise. A exibição de Resumo mostra quadros resumidos, informações de conta bancária, um gráfico do saldo e informações relacionadas. A página de análise usa os recursos do Microsoft Power BI para mostrar os visuais relacionados a saldos da conta bancária.
author: saraschi2
manager: AnnBe
ms.date: 01/12/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankTreasurerWorkspace
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: fdc0d1e5ea02cdcff9f7f5ede4ab685f54365698
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1547947"
---
# <a name="bank-management-workspace"></a><span data-ttu-id="51b6f-106">​Espaço de trabalho de gerenciamento bancário​</span><span class="sxs-lookup"><span data-stu-id="51b6f-106">Bank management workspace</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="51b6f-107">O espaço de trabalho **Gerenciamento de banco** mostra informações relacionadas a contas bancárias da empresa.</span><span class="sxs-lookup"><span data-stu-id="51b6f-107">The **Bank management** workspace shows information that is related to company bank accounts.</span></span> <span data-ttu-id="51b6f-108">Esta área de trabalho inclui uma visualização **Resumo** e uma página **Análise**.</span><span class="sxs-lookup"><span data-stu-id="51b6f-108">This workspace includes a **Summary** view and an **Analytics** page.</span></span> <span data-ttu-id="51b6f-109">A exibição **Resumo** mostra quadros resumidos, informações de conta bancária, um gráfico do saldo e informações relacionadas.</span><span class="sxs-lookup"><span data-stu-id="51b6f-109">The **Summary** view shows summary tiles, bank account information, a balance chart, and related information.</span></span> <span data-ttu-id="51b6f-110">A página **Análise** usa os recursos do Microsoft Power BI para mostrar os visuais relacionados a saldos da conta bancária.</span><span class="sxs-lookup"><span data-stu-id="51b6f-110">The **Analytics** page uses the capabilities of Microsoft Power BI to show visuals that are related to bank account balances.</span></span>

## <a name="summary-view"></a><span data-ttu-id="51b6f-111">Exibição de resumo</span><span class="sxs-lookup"><span data-stu-id="51b6f-111">Summary view</span></span>

### <a name="summary"></a><span data-ttu-id="51b6f-112">Resumo</span><span class="sxs-lookup"><span data-stu-id="51b6f-112">Summary</span></span>

<span data-ttu-id="51b6f-113">Os quadros na seção **Resumo** fornecem uma visão geral das contas bancárias e fornecem acesso rápido às páginas que você precisa usar com mais frequência.</span><span class="sxs-lookup"><span data-stu-id="51b6f-113">The tiles in the **Summary** section give an overview of your bank accounts and provide quick access to the pages that you most often have to use.</span></span> <span data-ttu-id="51b6f-114">As informações de reconciliação bancária são específicas à funcionalidade avançada de reconciliação bancária.</span><span class="sxs-lookup"><span data-stu-id="51b6f-114">The bank reconciliation information is specific to the Advanced bank reconciliation functionality.</span></span> <span data-ttu-id="51b6f-115">As informações são incluídas somente para as contas bancárias que têm a opção **Reconciliação bancária avançada** definida como **Sim** na **Conta bancária**.</span><span class="sxs-lookup"><span data-stu-id="51b6f-115">Information is included only for those bank accounts that have the **Advanced bank reconciliation** option set to **Yes** on the **Bank account** page.</span></span> <span data-ttu-id="51b6f-116">Da seção **Resumo**, você pode importar arquivos eletrônicos bancários para contas bancárias em todas as entidades legais.</span><span class="sxs-lookup"><span data-stu-id="51b6f-116">From the **Summary** section, you can import electronic bank files for bank accounts across all legal entities.</span></span>

### <a name="bank-accounts"></a><span data-ttu-id="51b6f-117">Contas Bancárias</span><span class="sxs-lookup"><span data-stu-id="51b6f-117">Bank accounts</span></span>

<span data-ttu-id="51b6f-118">Cada conta bancária na entidade legal é representada por um cartão na seção **Contas bancárias**.</span><span class="sxs-lookup"><span data-stu-id="51b6f-118">Each bank account in the legal entity is represented by a card in the **Bank accounts** section.</span></span> <span data-ttu-id="51b6f-119">O saldo atual é mostrado e você pode fazer busca detalhada em transações que compõem o valor do saldo do resumo.</span><span class="sxs-lookup"><span data-stu-id="51b6f-119">The current balance is shown, and you can drill down to the transactions that make up that summary balance amount.</span></span> <span data-ttu-id="51b6f-120">O valor **Transações de transição** permite que você faça uma busca detalhada nas transações que compõem o valor de resumo.</span><span class="sxs-lookup"><span data-stu-id="51b6f-120">The **Bridged transactions** amount also lets you drill down to the transactions that make up that summary amount.</span></span> <span data-ttu-id="51b6f-121">As transações de transição são todas as transações pendentes que foram lançadas usando a funcionalidade de transição, mas que ainda não foram liberadas.</span><span class="sxs-lookup"><span data-stu-id="51b6f-121">Bridged transactions are any pending transactions that have been posted by using bridging functionality, but that haven't yet been cleared.</span></span> <span data-ttu-id="51b6f-122">O valor **Saldo pendente** é o saldo atual menor o de transição, ou transações pendentes.</span><span class="sxs-lookup"><span data-stu-id="51b6f-122">The **Pending balance** amount is the current balance minus the bridged, or pending, transactions.</span></span>

<span data-ttu-id="51b6f-123">O cartão também mostra quando a conta bancária foi reconciliada pela última vez.</span><span class="sxs-lookup"><span data-stu-id="51b6f-123">The card also shows when the bank account was last reconciled.</span></span> <span data-ttu-id="51b6f-124">Essa informações é exibida apenas se a reconciliação bancária avançada for habilitada para a conta bancária.</span><span class="sxs-lookup"><span data-stu-id="51b6f-124">This information is shown only if Advanced bank reconciliation is enabled for the bank account.</span></span>

### <a name="balance"></a><span data-ttu-id="51b6f-125">Saldo</span><span class="sxs-lookup"><span data-stu-id="51b6f-125">Balance</span></span>

<span data-ttu-id="51b6f-126">O gráfico **Saldo** mostra as informações de histórico do saldo da conta bancária selecionada na seção **Contas bancárias** ou um resumo das informações de histórico do saldo de todas as contas bancárias na entidade legal.</span><span class="sxs-lookup"><span data-stu-id="51b6f-126">The **Balance** chart shows either historic balance information for the bank account that is selected in the **Bank accounts** section or a summary of historic balance information for all bank accounts in the legal entity.</span></span> <span data-ttu-id="51b6f-127">Essa informação está disponível para vários períodos: a semana atual, o mês atual, o ano atual, os últimos cinco anos, e todos os períodos (o histórico completo da conta bancária).</span><span class="sxs-lookup"><span data-stu-id="51b6f-127">This information is available for various periods: the current week, the current month, the current year, the last five years, and all periods (the full history of the bank account).</span></span> 

<span data-ttu-id="51b6f-128">Se você estiver exibindo o gráfico **Saldo** para uma única conta, os saldos do histórico serão exibidos na moeda da conta bancária.</span><span class="sxs-lookup"><span data-stu-id="51b6f-128">If you're viewing the **Balance** chart for a single bank account, the historic balances are shown in the bank account currency.</span></span> <span data-ttu-id="51b6f-129">Se você estiver exibindo o gráfico de todas as contas bancárias na entidade legal, os saldos do histórico serão mostrados na moeda contábil.</span><span class="sxs-lookup"><span data-stu-id="51b6f-129">If you're viewing the chart for all bank accounts in the legal entity, the historic balances are shown in the accounting currency.</span></span>

<span data-ttu-id="51b6f-130">As informações sobre quando os dados foram atualizados pela última vez aparecem na parte superior do gráfico.</span><span class="sxs-lookup"><span data-stu-id="51b6f-130">Information about when the data was last updated appears at the top of the chart.</span></span> <span data-ttu-id="51b6f-131">Você poderá atualizar os dados como necessário.</span><span class="sxs-lookup"><span data-stu-id="51b6f-131">You can update the data as you require.</span></span>

### <a name="related-information"></a><span data-ttu-id="51b6f-132">Informações Relacionadas</span><span class="sxs-lookup"><span data-stu-id="51b6f-132">Related information</span></span>

<span data-ttu-id="51b6f-133">Na seção **Informações relacionadas**, você pode abrir a página **Diário geral** para concluir as transferências bancárias.</span><span class="sxs-lookup"><span data-stu-id="51b6f-133">From the **Related information** section, you can open the **General journal** page to complete bank transfers.</span></span> <span data-ttu-id="51b6f-134">Você também pode abrir rapidamente as páginas **Transações bancárias** e **Transações de transição**.</span><span class="sxs-lookup"><span data-stu-id="51b6f-134">You can also quickly open the **Bank transactions** and **Bridged transactions** pages.</span></span>

## <a name="analytics-view"></a><span data-ttu-id="51b6f-135">Exibição de análise</span><span class="sxs-lookup"><span data-stu-id="51b6f-135">Analytics view</span></span>

<span data-ttu-id="51b6f-136">A página **Análise** fornece métricas importante sobre contas bancárias da empresa atual.</span><span class="sxs-lookup"><span data-stu-id="51b6f-136">The **Analytics** page provides important metrics about the bank accounts in the current company.</span></span> <span data-ttu-id="51b6f-137">As seguintes visualizações estão disponíveis na página:</span><span class="sxs-lookup"><span data-stu-id="51b6f-137">The following visualizations are available on the page:</span></span>

-   <span data-ttu-id="51b6f-138">Saldo bancário total na moeda do sistema</span><span class="sxs-lookup"><span data-stu-id="51b6f-138">Total bank balance in system currency</span></span>
-   <span data-ttu-id="51b6f-139">Saldo por entidade legal</span><span class="sxs-lookup"><span data-stu-id="51b6f-139">Balance by legal entity</span></span>
-   <span data-ttu-id="51b6f-140">Saldo real de hoje vs previsto na moeda da conta bancária</span><span class="sxs-lookup"><span data-stu-id="51b6f-140">Today’s actual vs forecasted balance in bank account currency</span></span>
-   <span data-ttu-id="51b6f-141">Saldo por conta bancária</span><span class="sxs-lookup"><span data-stu-id="51b6f-141">Balance by bank account</span></span>
-   <span data-ttu-id="51b6f-142">Saldo por moeda</span><span class="sxs-lookup"><span data-stu-id="51b6f-142">Balance by currency</span></span>

<span data-ttu-id="51b6f-143">Você pode exibir a análise do banco em todas as empresas do espaço trabalho **Visão geral de caixa – todas as empresas**.</span><span class="sxs-lookup"><span data-stu-id="51b6f-143">You can view bank analytics across all companies from the **Cash overview – all companies** workspace.</span></span>
