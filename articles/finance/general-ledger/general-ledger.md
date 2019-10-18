---
title: Visão geral da contabilidade e de relatórios financeiros
description: Use a Contabilidade para definir e gerenciar os registros financeiros da entidade legal.
author: ShylaThompson
manager: AnnBe
ms.date: 08/31/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: GeneralJournalEntryWorkspace
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 65431
ms.assetid: d2c604df-daae-42cd-82d9-c80e3dee4a60
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c0e795e641314b4ef81f8972aadf597721995fcc
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2186523"
---
# <a name="general-ledger-overview"></a><span data-ttu-id="eab08-103">Visão geral da contabilidade</span><span class="sxs-lookup"><span data-stu-id="eab08-103">General ledger overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="eab08-104">Use a Contabilidade para definir e gerenciar os registros financeiros da entidade legal.</span><span class="sxs-lookup"><span data-stu-id="eab08-104">Use General ledger to define and manage the legal entity’s financial records.</span></span> <span data-ttu-id="eab08-105">A contabilidade é um registro de entradas de débito e crédito.</span><span class="sxs-lookup"><span data-stu-id="eab08-105">The general ledger is a register of debit and credit entries.</span></span> <span data-ttu-id="eab08-106">Essas entradas são classificadas usando as contas listadas em um plano de contas.</span><span class="sxs-lookup"><span data-stu-id="eab08-106">These entries are classified using the accounts that are listed in a chart of accounts.</span></span> 

 - [<span data-ttu-id="eab08-107">Planejar seu plano de contas</span><span class="sxs-lookup"><span data-stu-id="eab08-107">Plan your chart of accounts</span></span>](plan-chart-of-accounts.md)
 - [<span data-ttu-id="eab08-108">Tipos de conta principal</span><span class="sxs-lookup"><span data-stu-id="eab08-108">Main account types</span></span>](main-account-types.md)

<span data-ttu-id="eab08-109">Você pode alocar, ou distribuir, valores monetários para uma ou mais contas ou combinações de contas e dimensões com base nas regras de alocação.</span><span class="sxs-lookup"><span data-stu-id="eab08-109">You can allocate, or distribute, monetary amounts to one or more accounts or account and dimension combinations based on allocation rules.</span></span> <span data-ttu-id="eab08-110">Há dois tipos de alocação: fixa e variável.</span><span class="sxs-lookup"><span data-stu-id="eab08-110">There are two types of allocations: fixed and variable.</span></span> <span data-ttu-id="eab08-111">Você também pode liquidar transações entre contas contábeis e reavaliar valores monetários.</span><span class="sxs-lookup"><span data-stu-id="eab08-111">You can also settle transactions between ledger accounts and revalue currency amounts.</span></span> <span data-ttu-id="eab08-112">No fim de um ano fiscal, você deve gerar transações de fechamento e preparar suas contas para o próximo ano fiscal.</span><span class="sxs-lookup"><span data-stu-id="eab08-112">At the end of a fiscal year, you must generate closing transactions and prepare your accounts for the next fiscal year.</span></span> <span data-ttu-id="eab08-113">Você pode usar a funcionalidade de consolidação para combinar os resultados financeiros para várias entidades legais subsidiárias nos resultados de uma só organização consolidada.</span><span class="sxs-lookup"><span data-stu-id="eab08-113">You can use the consolidation functionality to combine the financial results for several subsidiary legal entities into results for a single, consolidated organization.</span></span> <span data-ttu-id="eab08-114">As subsidiárias podem estar no mesmo banco de dados ou em bancos de dados separados.</span><span class="sxs-lookup"><span data-stu-id="eab08-114">The subsidiaries can be in the same database or in separate databases.</span></span>

- [<span data-ttu-id="eab08-115">Visão geral de consolidação de eliminação</span><span class="sxs-lookup"><span data-stu-id="eab08-115">Consolidation and elimination overview</span></span>](../budgeting/consolidation-elimination-overview.md)
- [<span data-ttu-id="eab08-116">Saldos de conta contábil</span><span class="sxs-lookup"><span data-stu-id="eab08-116">General ledger account balances</span></span>](general-ledger-account-balances.md)
- [<span data-ttu-id="eab08-117">Dimensões financeiras</span><span class="sxs-lookup"><span data-stu-id="eab08-117">Financial dimensions</span></span>](financial-dimensions.md)

<span data-ttu-id="eab08-118">[![Processo de negócios](./media/GL-process.PNG)](./media/GL-process.PNG)</span><span class="sxs-lookup"><span data-stu-id="eab08-118">[![Business process](./media/GL-process.PNG)](./media/GL-process.PNG)</span></span>

## <a name="sales-tax"></a><span data-ttu-id="eab08-119">Imposto</span><span class="sxs-lookup"><span data-stu-id="eab08-119">Sales tax</span></span>
<span data-ttu-id="eab08-120">Cada empresa recolhe e paga impostos a várias autoridades fiscais.</span><span class="sxs-lookup"><span data-stu-id="eab08-120">Every company collects and pays taxes to various tax authorities.</span></span> <span data-ttu-id="eab08-121">As regras e as taxas variam por país/região, estado, região e cidade.</span><span class="sxs-lookup"><span data-stu-id="eab08-121">The rules and rates vary by country/region, state, county, and city.</span></span>
<span data-ttu-id="eab08-122">Além disso, as regras devem ser atualizadas periodicamente quando as autoridades fiscais alterarem seus requisitos.</span><span class="sxs-lookup"><span data-stu-id="eab08-122">In addition, the rules must be updated periodically when tax authorities change their requirements.</span></span> <span data-ttu-id="eab08-123">Os códigos de imposto contêm as informações básicas sobre o quanto você recolhe e paga às autoridades.</span><span class="sxs-lookup"><span data-stu-id="eab08-123">Sales tax codes contain the basic information about how much you collect and pay to the authorities.</span></span> <span data-ttu-id="eab08-124">Ao configurar códigos de imposto, defina valores ou porcentagens que devem ser recolhidos.</span><span class="sxs-lookup"><span data-stu-id="eab08-124">When you set up sales tax codes, you define the amounts or percentages that must be collected.</span></span> <span data-ttu-id="eab08-125">Também é possível definir vários métodos pelo qual esses valores ou porcentagens são aplicados aos valores da transação.</span><span class="sxs-lookup"><span data-stu-id="eab08-125">You also define the various methods by which those amounts or percentages are applied to transaction amounts.</span></span> <span data-ttu-id="eab08-126">Os tópicos desta seção fornecem informações sobre como configurar os códigos de imposto para os métodos e as taxas que as autoridades fiscais exigem.</span><span class="sxs-lookup"><span data-stu-id="eab08-126">The topics in this section provide information about how to set up sales tax codes for the methods and rates that your tax authorities require.</span></span>

 - [<span data-ttu-id="eab08-127">Visão geral de imposto</span><span class="sxs-lookup"><span data-stu-id="eab08-127">Sales tax overview</span></span>](indirect-taxes-overview.md)
 - [<span data-ttu-id="eab08-128">Determinando as alíquotas de imposto com base nos campos Base marginal e Métodos de cálculo</span><span class="sxs-lookup"><span data-stu-id="eab08-128">Sales tax rates based on the Marginal base and Calculation methods</span></span>](marginal-base-field.md)
 - [<span data-ttu-id="eab08-129">Pagamentos de impostos e regras de arredondamento</span><span class="sxs-lookup"><span data-stu-id="eab08-129">Sales tax payments and rounding rules</span></span>](round-sales-tax-payments.md)


## <a name="additional-resources"></a><span data-ttu-id="eab08-130">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="eab08-130">Additional resources</span></span>

#### <a name="whats-new-and-in-development"></a><span data-ttu-id="eab08-131">Novidades e o que está em desenvolvimento</span><span class="sxs-lookup"><span data-stu-id="eab08-131">What's new and in development</span></span>

<span data-ttu-id="eab08-132">Acesse as [Notas de versão do Microsoft Dynamics 365](https://go.microsoft.com/fwlink/?linkid=2010158) para ver quais novos recursos foram planejados.</span><span class="sxs-lookup"><span data-stu-id="eab08-132">Go to the [Microsoft Dynamics 365 Release Notes](https://go.microsoft.com/fwlink/?linkid=2010158) to see what new features have been planned.</span></span> 

#### <a name="blogs"></a><span data-ttu-id="eab08-133">Blogs</span><span class="sxs-lookup"><span data-stu-id="eab08-133">Blogs</span></span>

<span data-ttu-id="eab08-134">Você encontra opiniões, notícias e outras informações no [Blog do Microsoft Dynamics 365](https://community.dynamics.com/b/msftdynamicsblog?c=Enterprise) e no [Blog do Microsoft Dynamics 365 Finance and Operations - Financials](https://community.dynamics.com/365/financeandoperations/b/financials).</span><span class="sxs-lookup"><span data-stu-id="eab08-134">You can find opinions, news, and other information on the [Microsoft Dynamics 365 blog](https://community.dynamics.com/b/msftdynamicsblog?c=Enterprise) and the [Microsoft Dynamics 365 Finance and Operations - Financials blog](https://community.dynamics.com/365/financeandoperations/b/financials).</span></span>

<span data-ttu-id="eab08-135">O [Blog da Comunidade de Parceiros do Microsoft Dynamics Operations](https://community.dynamics.com/partner/b/operationspartnercommunityblog) fornece aos Parceiros do Microsoft Dynamics um recurso único para saberem mais sobre as novidades e as tendências do MBS Operations.</span><span class="sxs-lookup"><span data-stu-id="eab08-135">The [Microsoft Dynamics Operations Partner Community Blog](https://community.dynamics.com/partner/b/operationspartnercommunityblog) gives Microsoft Dynamics Partners a single resource where they can learn what is new and trending in MBS Operations.</span></span>

### <a name="videos"></a><span data-ttu-id="eab08-136">Vídeos</span><span class="sxs-lookup"><span data-stu-id="eab08-136">Videos</span></span>

<span data-ttu-id="eab08-137">Confira os vídeos de instruções que agora estão disponíveis no [canal do Microsoft Dynamics 365 no YouTube](https://www.youtube.com/channel/UCJGCg4rB3QSs8y_1FquelBQ).</span><span class="sxs-lookup"><span data-stu-id="eab08-137">Check out the how-to videos that are now available on the [Microsoft Dynamics 365 YouTube Channel](https://www.youtube.com/channel/UCJGCg4rB3QSs8y_1FquelBQ).</span></span>

#### <a name="community-blogs"></a><span data-ttu-id="eab08-138">Blogs da comunidade</span><span class="sxs-lookup"><span data-stu-id="eab08-138">Community blogs</span></span>

- [<span data-ttu-id="eab08-139">O que você deve saber sobre o razão no Dynamics 365 for Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="eab08-139">What you should know about ledger in Dynamics 365 for Finance and Operations</span></span>](https://financefunction.tech/2018/04/29/what-you-should-know-about-ledger-in-dynamics-365-for-finance-and-operations)

