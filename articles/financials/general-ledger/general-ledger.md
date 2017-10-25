---
title: "Página inicial da contabilidade e relatórios financeiros"
description: Use a Contabilidade para definir e gerenciar os registros financeiros da entidade legal.
author: twheeloc
manager: AnnBe
ms.date: 08/31/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 65431
ms.assetid: d2c604df-daae-42cd-82d9-c80e3dee4a60
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: fc8102d945faf9ad533f57ec1a45b0e0dc344963
ms.openlocfilehash: 2f52f4afbdd90b3f6a9a42f0fc85c3e083f0cf30
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---

# <a name="general-ledger"></a><span data-ttu-id="7a099-103">Contabilidade</span><span class="sxs-lookup"><span data-stu-id="7a099-103">General ledger</span></span> 

[!include[banner](../includes/banner.md)]


<span data-ttu-id="7a099-104">Use a Contabilidade para definir e gerenciar os registros financeiros da entidade legal.</span><span class="sxs-lookup"><span data-stu-id="7a099-104">Use General ledger to define and manage the legal entity’s financial records.</span></span> <span data-ttu-id="7a099-105">A contabilidade é um registro de entradas de débito e crédito.</span><span class="sxs-lookup"><span data-stu-id="7a099-105">The general ledger is a register of debit and credit entries.</span></span> <span data-ttu-id="7a099-106">Essas entradas são classificadas usando as contas listadas em um plano de contas.</span><span class="sxs-lookup"><span data-stu-id="7a099-106">These entries are classified using the accounts that are listed in a chart of accounts.</span></span> 

 - [<span data-ttu-id="7a099-107">Planejar seu plano de contas</span><span class="sxs-lookup"><span data-stu-id="7a099-107">Plan your chart of accounts</span></span>](plan-chart-of-accounts.md)
 - [<span data-ttu-id="7a099-108">Tipos de conta principal</span><span class="sxs-lookup"><span data-stu-id="7a099-108">Main account types</span></span>](main-account-types.md)

<span data-ttu-id="7a099-109">Você pode alocar, ou distribuir, valores monetários para uma ou mais contas ou combinações de contas e dimensões com base nas regras de alocação.</span><span class="sxs-lookup"><span data-stu-id="7a099-109">You can allocate, or distribute, monetary amounts to one or more accounts or account and dimension combinations based on allocation rules.</span></span> <span data-ttu-id="7a099-110">Há dois tipos de alocação: fixa e variável.</span><span class="sxs-lookup"><span data-stu-id="7a099-110">There are two types of allocations: fixed and variable.</span></span> <span data-ttu-id="7a099-111">Você também pode liquidar transações entre contas contábeis e reavaliar valores monetários.</span><span class="sxs-lookup"><span data-stu-id="7a099-111">You can also settle transactions between ledger accounts and revalue currency amounts.</span></span> <span data-ttu-id="7a099-112">No fim de um ano fiscal, você deve gerar transações de fechamento e preparar suas contas para o próximo ano fiscal.</span><span class="sxs-lookup"><span data-stu-id="7a099-112">At the end of a fiscal year, you must generate closing transactions and prepare your accounts for the next fiscal year.</span></span> <span data-ttu-id="7a099-113">Você pode usar a funcionalidade de consolidação para combinar os resultados financeiros para várias entidades legais subsidiárias nos resultados de uma só organização consolidada.</span><span class="sxs-lookup"><span data-stu-id="7a099-113">You can use the consolidation functionality to combine the financial results for several subsidiary legal entities into results for a single, consolidated organization.</span></span> <span data-ttu-id="7a099-114">As subsidiárias podem estar no mesmo banco de dados do Microsoft Dynamics 365 for Finance and Operations ou em bancos de dados separados.</span><span class="sxs-lookup"><span data-stu-id="7a099-114">The subsidiaries can be in the same Microsoft Dynamics 365 for Finance and Operations database or in separate databases.</span></span>

- [<span data-ttu-id="7a099-115">Visão geral de consolidação de eliminação</span><span class="sxs-lookup"><span data-stu-id="7a099-115">Consolidation and elimination overview</span></span>](../budgeting/consolidation-elimination-overview.md)
- [<span data-ttu-id="7a099-116">Saldos de conta contábil</span><span class="sxs-lookup"><span data-stu-id="7a099-116">General ledger account balances</span></span>](general-ledger-account-balances.md)
- [<span data-ttu-id="7a099-117">Dimensões financeiras</span><span class="sxs-lookup"><span data-stu-id="7a099-117">Financial dimensions</span></span>](financial-dimensions.md)

<span data-ttu-id="7a099-118">[![Processo de negócios](./media/GL-process.PNG)](./media/GL-process.PNG)</span><span class="sxs-lookup"><span data-stu-id="7a099-118">[![Business process](./media/GL-process.PNG)](./media/GL-process.PNG)</span></span>

# <a name="sales-tax"></a><span data-ttu-id="7a099-119">Imposto</span><span class="sxs-lookup"><span data-stu-id="7a099-119">Sales tax</span></span>
<span data-ttu-id="7a099-120">Cada empresa recolhe e paga impostos a várias autoridades fiscais.</span><span class="sxs-lookup"><span data-stu-id="7a099-120">Every company collects and pays taxes to various tax authorities.</span></span> <span data-ttu-id="7a099-121">As regras e as taxas variam por país/região, estado, região e cidade.</span><span class="sxs-lookup"><span data-stu-id="7a099-121">The rules and rates vary by country/region, state, county, and city.</span></span>
<span data-ttu-id="7a099-122">Além disso, as regras devem ser atualizadas periodicamente quando as autoridades fiscais alterarem seus requisitos.</span><span class="sxs-lookup"><span data-stu-id="7a099-122">In addition, the rules must be updated periodically when tax authorities change their requirements.</span></span> <span data-ttu-id="7a099-123">Os códigos de imposto contêm as informações básicas sobre o quanto você recolhe e paga às autoridades.</span><span class="sxs-lookup"><span data-stu-id="7a099-123">Sales tax codes contain the basic information about how much you collect and pay to the authorities.</span></span> <span data-ttu-id="7a099-124">Ao configurar códigos de imposto, defina valores ou porcentagens que devem ser recolhidos.</span><span class="sxs-lookup"><span data-stu-id="7a099-124">When you set up sales tax codes, you define the amounts or percentages that must be collected.</span></span> <span data-ttu-id="7a099-125">Também é possível definir vários métodos pelo qual esses valores ou porcentagens são aplicados aos valores da transação.</span><span class="sxs-lookup"><span data-stu-id="7a099-125">You also define the various methods by which those amounts or percentages are applied to transaction amounts.</span></span> <span data-ttu-id="7a099-126">Os tópicos desta seção fornecem informações sobre como configurar os códigos de imposto para os métodos e as taxas que as autoridades fiscais exigem.</span><span class="sxs-lookup"><span data-stu-id="7a099-126">The topics in this section provide information about how to set up sales tax codes for the methods and rates that your tax authorities require.</span></span>

 - [<span data-ttu-id="7a099-127">Visão geral de imposto</span><span class="sxs-lookup"><span data-stu-id="7a099-127">Sales tax overview</span></span>](indirect-taxes-overview.md)
 - [<span data-ttu-id="7a099-128">Determinando as alíquotas de imposto com base nos campos Base marginal e Métodos de cálculo</span><span class="sxs-lookup"><span data-stu-id="7a099-128">Sales tax rates based on the Marginal base and Calculation methods</span></span>](marginal-base-field.md)
 - [<span data-ttu-id="7a099-129">Pagamentos de impostos e regras de arredondamento</span><span class="sxs-lookup"><span data-stu-id="7a099-129">Sales tax payments and rounding rules</span></span>](round-sales-tax-payments.md)


### <a name="additional-resources"></a><span data-ttu-id="7a099-130">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="7a099-130">Additional resources</span></span>

#### <a name="whats-new-and-in-development"></a><span data-ttu-id="7a099-131">Novidades e o que está em desenvolvimento</span><span class="sxs-lookup"><span data-stu-id="7a099-131">What's new and in development</span></span>

<span data-ttu-id="7a099-132">Visite o [Microsoft Dynamics 365 Roadmap](https://roadmap.dynamics.com/) para conferir os novos recursos que foram liberados e os novos recursos em desenvolvimento.</span><span class="sxs-lookup"><span data-stu-id="7a099-132">Go to the [Microsoft Dynamics 365 Roadmap](https://roadmap.dynamics.com/) to see what new features have been released and what new features are in development.</span></span> 

#### <a name="blogs"></a><span data-ttu-id="7a099-133">Blogs</span><span class="sxs-lookup"><span data-stu-id="7a099-133">Blogs</span></span>

<span data-ttu-id="7a099-134">Você encontra opiniões, notícias, além de informações sobre Contas a pagar e outras soluções no [blog do Microsoft Dynamics 365](https://community.dynamics.com/b/msftdynamicsblog?c=Enterprise).</span><span class="sxs-lookup"><span data-stu-id="7a099-134">You can find opinions, news, and other information about Accounts payable and other solutions on the [Microsoft Dynamics 365 blog](https://community.dynamics.com/b/msftdynamicsblog?c=Enterprise).</span></span>

<span data-ttu-id="7a099-135">Há muitas postagens sobre Contabilidade no [blog da equipe do produto Microsoft Dynamics AX](https://blogs.msdn.microsoft.com/dax/).</span><span class="sxs-lookup"><span data-stu-id="7a099-135">There are many posts about General ledger on the [Microsoft Dynamics AX product team blog](https://blogs.msdn.microsoft.com/dax/).</span></span> <span data-ttu-id="7a099-136">Embora algumas dessas postagens tenham sido escritas para a versão anterior de Contabilidade, os mesmos conceitos ainda se aplicam, e os procedimentos também são semelhantes na versão atual.</span><span class="sxs-lookup"><span data-stu-id="7a099-136">Although some of these posts were written for the previous version of General ledger, the same concepts still apply, and the procedures are also similar in the current version.</span></span>

<span data-ttu-id="7a099-137">O [blog da Comunidade de Parceiros do Microsoft Dynamics Operations](https://community.dynamics.com/partner/b/operationspartnercommunityblog) fornece aos Parceiros do Microsoft Dynamics um recurso único por meio do qual podem saber mais sobre as novidades e as tendências do MBS Operations.</span><span class="sxs-lookup"><span data-stu-id="7a099-137">The [Microsoft Dynamics Operations Partner Community Blog](https://community.dynamics.com/partner/b/operationspartnercommunityblog) gives Microsoft Dynamics Partners a single resource where they can learn what is new and trending in MBS Operations.</span></span>

#### <a name="task-guides"></a><span data-ttu-id="7a099-138">Guias de tarefas</span><span class="sxs-lookup"><span data-stu-id="7a099-138">Task guides</span></span>
<span data-ttu-id="7a099-139">Há ajuda adicional disponível como guias de tarefas dentro do Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="7a099-139">Additional help is available as task guides inside Finance and Operations.</span></span> <span data-ttu-id="7a099-140">Para acessar os guias de tarefas, clique no botão Ajuda em qualquer página.</span><span class="sxs-lookup"><span data-stu-id="7a099-140">To access task guides, click the Help button on any page.</span></span>

#### <a name="videos"></a><span data-ttu-id="7a099-141">Vídeos</span><span class="sxs-lookup"><span data-stu-id="7a099-141">Videos</span></span>

<span data-ttu-id="7a099-142">Confira os vídeos de instruções que agora estão disponíveis no [canal do Microsoft Dynamics 365 no YouTube](https://www.youtube.com/channel/UCJGCg4rB3QSs8y_1FquelBQ).</span><span class="sxs-lookup"><span data-stu-id="7a099-142">Check out the how-to videos that are now available on the [Microsoft Dynamics 365 YouTube Channel](https://www.youtube.com/channel/UCJGCg4rB3QSs8y_1FquelBQ).</span></span>

