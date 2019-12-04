---
title: Crédito e cobranças em Contas a receber
description: As informações de cobranças de contas a receber são gerenciadas em uma exibição central usando a página Cobranças do Microsoft Dynamics 365 Finance. Os gerentes de Crédito e cobranças podem usar essa exibição central para gerenciar cobranças. Os agentes de cobranças podem iniciar o processo de cobranças a partir das listas de clientes que são geradas usando critérios de cobrança predefinidos ou da página Clientes.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 10/26/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustAgingSnapshot, CustBankAccounts, CustCollections, CustCollectionsActivitiesListPage, CustCollectionsAgent, CustCollectionsCaseListPage, CustCollectionsPool, CustCollectionsPoolsListPage, CustTable
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 3061
ms.assetid: fd851520-8d93-434b-845b-be127d6ac3a6
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 471de43bc0d171e60100613a6d779a249cd9e92f
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2189168"
---
# <a name="credit-and-collections-in-accounts-receivable"></a><span data-ttu-id="3f785-105">Crédito e cobranças em Contas a receber</span><span class="sxs-lookup"><span data-stu-id="3f785-105">Credit and collections in Accounts receivable</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="3f785-106">As informações de cobranças de contas a receber são gerenciadas em uma exibição central usando a página Cobranças do Microsoft Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="3f785-106">Accounts receivable collections information is managed in one central view using the Microsoft Dynamics 365 Finance Collections page.</span></span> <span data-ttu-id="3f785-107">Os gerentes de Crédito e cobranças podem usar essa exibição central para gerenciar cobranças.</span><span class="sxs-lookup"><span data-stu-id="3f785-107">Credit and collections managers can use this central view to manage collections.</span></span> <span data-ttu-id="3f785-108">Os agentes de cobranças podem iniciar o processo de cobranças a partir das listas de clientes que são geradas usando critérios de cobrança predefinidos ou da página Clientes.</span><span class="sxs-lookup"><span data-stu-id="3f785-108">Collections agents can begin the collections process from customer lists that are generated by using predefined collection criteria, or from the Customers page.</span></span>

<span data-ttu-id="3f785-109">Antes de começar a configurar ou trabalhar com cobranças, você deve entender os seguintes conceitos:</span><span class="sxs-lookup"><span data-stu-id="3f785-109">Before you begin to set up or work with collections, you should understand the following concepts:</span></span>
-   <span data-ttu-id="3f785-110">Os instantâneos de classificação por vencimento de clientes contêm informações classificadas por vencimento do saldo em um ponto no tempo</span><span class="sxs-lookup"><span data-stu-id="3f785-110">Customer aging snapshots contain aged balance information at a point in time</span></span>
-   <span data-ttu-id="3f785-111">Os grupos de clientes de cobranças ajudam você a organizar seu trabalho</span><span class="sxs-lookup"><span data-stu-id="3f785-111">Collections customer pools help you organize your work</span></span>
-   <span data-ttu-id="3f785-112">Os agentes de cobranças podem ter seus próprios grupos de clientes</span><span class="sxs-lookup"><span data-stu-id="3f785-112">Collections agents can have their own customer pools</span></span>
-   <span data-ttu-id="3f785-113">As páginas de lista organizam clientes, atividades e casos de cobranças</span><span class="sxs-lookup"><span data-stu-id="3f785-113">List pages organize collections customers, activities, and cases</span></span>
-   <span data-ttu-id="3f785-114">Todas as informações de cobranças de um cliente estão em uma página e você pode agir com base nessa página</span><span class="sxs-lookup"><span data-stu-id="3f785-114">All collections information for a customer is on one page and you can take action from that page</span></span>
-   <span data-ttu-id="3f785-115">Renunciar, reaplicar ou reverter juros e taxas podem ser concluídos em uma etapa</span><span class="sxs-lookup"><span data-stu-id="3f785-115">Waive, reinstate, or reverse interest and fees can be done in one step</span></span>
-   <span data-ttu-id="3f785-116">Criar transações de baixa pode ser concluído em uma etapa</span><span class="sxs-lookup"><span data-stu-id="3f785-116">Create write-off transactions can be done in one step</span></span>
-   <span data-ttu-id="3f785-117">Processar pagamentos NSF (insuficiência de fundos) pode ser concluído em uma etapa</span><span class="sxs-lookup"><span data-stu-id="3f785-117">Process not sufficient funds (NSF) payments can be done in one step</span></span>

<span data-ttu-id="3f785-118">As seções a seguir descrevem cada conceito.</span><span class="sxs-lookup"><span data-stu-id="3f785-118">The following sections describe each concept.</span></span>

## <a name="customer-aging-snapshots"></a><span data-ttu-id="3f785-119">Instantâneo de classificação por vencimento de cliente </span><span class="sxs-lookup"><span data-stu-id="3f785-119">Customer aging snapshots</span></span>
<span data-ttu-id="3f785-120">Um instantâneo de classificação por vencimento contém os saldos classificados por vencimento calculados para um cliente em determinado momento.</span><span class="sxs-lookup"><span data-stu-id="3f785-120">An aging snapshot contains the calculated aged balances for a customer at a point in time.</span></span> <span data-ttu-id="3f785-121">As informações são exibidas na página Lista de saldos classificados por vencimento e na página Cobranças.</span><span class="sxs-lookup"><span data-stu-id="3f785-121">This information is displayed on the Aged balances list page and on the Collections page.</span></span> <span data-ttu-id="3f785-122">Um instantâneo de classificação por vencimento deve ser criado para que você possa exibir as informações nas páginas de listagem Cobranças.</span><span class="sxs-lookup"><span data-stu-id="3f785-122">An aging snapshot must be created before you can view information on the Collections list pages.</span></span> 

<span data-ttu-id="3f785-123">Para cada cliente, um instantâneo de classificação por vencimento contém um cabeçalho do instantâneo de classificação por vencimento e os registros de detalhes que correspondem a cada período de classificação por vencimento na definição do período de classificação por vencimento.</span><span class="sxs-lookup"><span data-stu-id="3f785-123">For each customer, an aging snapshot contains an aging snapshot header and detail records that correspond to each aging period in the aging period definition.</span></span> 

<span data-ttu-id="3f785-124">O cabeçalho do instantâneo de classificação por vencimento contém o valor total devido, o limite de crédito, o valor da guia de remessa, o valor da ordem de venda, o número de transações contestadas e o valor total das transações contestadas para a conta do cliente.</span><span class="sxs-lookup"><span data-stu-id="3f785-124">The aging snapshot header contains the total amount due, credit limit, packing slip amount, sales order amount, number of disputed transactions, and total amount of the disputed transactions for the customer account.</span></span> <span data-ttu-id="3f785-125">Todas as transações do cliente são incluídas no cálculo desses valores.</span><span class="sxs-lookup"><span data-stu-id="3f785-125">All transactions for the customer are included in the calculation of these amounts.</span></span> <span data-ttu-id="3f785-126">O valor total devido, o limite de crédito, o valor da guia de remessa e o valor da ordem de venda são exibidos no Quadro de Fatos Informações de Crédito da página Cobranças.</span><span class="sxs-lookup"><span data-stu-id="3f785-126">The total amount due, credit limit, packing slip amount, and sales order amount are shown in the Credit information FactBox on the Collections page.</span></span> 

<span data-ttu-id="3f785-127">Para cada período de classificação por vencimento na definição do período de classificação por vencimento, um registro de detalhes do instantâneo de classificação por vencimento é criado.</span><span class="sxs-lookup"><span data-stu-id="3f785-127">For each aging period in the aging period definition, an aging snapshot detail record is created.</span></span> <span data-ttu-id="3f785-128">Cada registro de detalhes do instantâneo de classificação por vencimento contém a ID do período de classificação por vencimento e o valor total das transações com datas que estão no período de classificação por vencimento.</span><span class="sxs-lookup"><span data-stu-id="3f785-128">Each aging snapshot detail record contains the aging period ID and the total amount of the transactions with dates that are in the aging period.</span></span> <span data-ttu-id="3f785-129">As transações são atribuídas a um período de classificação por vencimento, como 30 dias de atraso.</span><span class="sxs-lookup"><span data-stu-id="3f785-129">Transactions are assigned to an aging period, such as 30 days past due.</span></span> <span data-ttu-id="3f785-130">A data é relativa à Classificação por vencimento a partir da data que é especificada quando você cria o instantâneo de classificação por vencimento.</span><span class="sxs-lookup"><span data-stu-id="3f785-130">The date is relative to the Aging as of date that is specified when you create the aging snapshot.</span></span> <span data-ttu-id="3f785-131">As informações são mostradas na página Lista de saldos classificados por vencimento no Quadro de Fatos Saldos classificados por vencimento na página Cobranças.</span><span class="sxs-lookup"><span data-stu-id="3f785-131">This information is shown on the Aged balances list page and in the Aged balances FactBox on the Collections page.</span></span>

## <a name="collections-customer-pools"></a><span data-ttu-id="3f785-132"> Grupos de clientes de cobranças </span><span class="sxs-lookup"><span data-stu-id="3f785-132">Collections customer pools</span></span>
<span data-ttu-id="3f785-133">Os grupos de clientes são consultas que definem um grupo de registros de clientes que podem ser exibidos e gerenciados para cobranças ou processos de classificação por vencimento.</span><span class="sxs-lookup"><span data-stu-id="3f785-133">Customer pools are queries that define a group of customer records that can be displayed and managed for collections or aging processes.</span></span> <span data-ttu-id="3f785-134">Use os grupos de clientes para filtrar informações nas página de listagem Saldos classificados por vencimento, Atividades de cobrança e Casos de cobrança.</span><span class="sxs-lookup"><span data-stu-id="3f785-134">Use customer pools to filter information on the Aged balances, Collections activities, and Collections cases list pages.</span></span> <span data-ttu-id="3f785-135">Você também usa grupos de clientes para filtrar as contas de clientes que são incluídas quando os instantâneos de classificação por vencimento são criados.</span><span class="sxs-lookup"><span data-stu-id="3f785-135">You also use customer pools to filter the customer accounts that are included when aging snapshots are created.</span></span>

## <a name="collections-agents"></a><span data-ttu-id="3f785-136">Agentes de cobranças</span><span class="sxs-lookup"><span data-stu-id="3f785-136">Collections agents</span></span>
<span data-ttu-id="3f785-137">Por padrão, os usuários podem exibir todas as informações de clientes nas páginas de lista de cobranças.</span><span class="sxs-lookup"><span data-stu-id="3f785-137">By default, users can view all customer information on collections list pages.</span></span> <span data-ttu-id="3f785-138">Você pode usar registros de agente de cobranças para determinar os grupos de clientes que estão disponíveis para filtrar as informações nas páginas de lista de cobranças e na página Cobranças.</span><span class="sxs-lookup"><span data-stu-id="3f785-138">You can use collections agent records to determine the customer pools that are available to filter information on the collections list pages and on the Collections page.</span></span> 

<span data-ttu-id="3f785-139">Um agente de cobranças é a pessoa que trabalha com clientes para ter certeza de que os pagamentos serão cobrados em tempo hábil.</span><span class="sxs-lookup"><span data-stu-id="3f785-139">A collections agent is a person who works with customers to make sure that payments are collected in a timely manner.</span></span> <span data-ttu-id="3f785-140">Os agentes de cobranças são funcionários atribuídos a usuários na página Configuração de usuário.</span><span class="sxs-lookup"><span data-stu-id="3f785-140">Collections agents are workers who are assigned to users in the User setup page.</span></span>

## <a name="collections-list-pages"></a><span data-ttu-id="3f785-141"> Páginas de listagem Cobranças </span><span class="sxs-lookup"><span data-stu-id="3f785-141">Collections list pages</span></span>
<span data-ttu-id="3f785-142">As seguintes páginas de lista ajudam você a organizar as informações de cobrança.</span><span class="sxs-lookup"><span data-stu-id="3f785-142">The following list pages help you organize collections information.</span></span>
-   <span data-ttu-id="3f785-143">Saldos classificados por vencimento – as colunas na página de listagem exibem saldos do cliente e valores antigos no período de classificação por vencimento.</span><span class="sxs-lookup"><span data-stu-id="3f785-143">Aged balances – The columns on the list page display customer balances and aged amounts by aging period.</span></span> <span data-ttu-id="3f785-144">Essas informações ficam armazenadas em um instantâneo de classificação por vencimento.</span><span class="sxs-lookup"><span data-stu-id="3f785-144">This information is stored in an aging snapshot.</span></span> <span data-ttu-id="3f785-145">Os períodos de classificação por vencimento são determinados pela definição do período de classificação por vencimento usada.</span><span class="sxs-lookup"><span data-stu-id="3f785-145">The aging periods are determined by the aging period definition that is used.</span></span> <span data-ttu-id="3f785-146">A definição do período de classificação por vencimento é tirada do grupo de clientes, se tiver sido especificada para a consulta de grupo.</span><span class="sxs-lookup"><span data-stu-id="3f785-146">The aging period definition is taken from the customer pool, if one was specified for the pool query.</span></span> <span data-ttu-id="3f785-147">Se o grupo não tiver uma definição do período de classificação por vencimento, a definição do período de classificação por vencimento padrão especificada na página Parâmetros de contas a receber será usada.</span><span class="sxs-lookup"><span data-stu-id="3f785-147">If the pool does not have an aging period definition, the default aging period definition that is specified in the Accounts receivable parameters page is used.</span></span> <span data-ttu-id="3f785-148">Se nenhuma definição do período de classificação por vencimento padrão for especificada, será usada a primeira definição do período de classificação por vencimento na página Definições do período de classificação por vencimento.</span><span class="sxs-lookup"><span data-stu-id="3f785-148">If no default aging period definition is specified, the first aging period definition in the Aging period definitions page is used.</span></span>
-   <span data-ttu-id="3f785-149">Atividades de cobranças – as colunas na página de lista exibem as atividades que são identificadas como atividades de cobranças.</span><span class="sxs-lookup"><span data-stu-id="3f785-149">Collections activities – The columns on the list page display activities that are identified as collections activities.</span></span> <span data-ttu-id="3f785-150">Essas atividades são criadas usando a página Cobranças.</span><span class="sxs-lookup"><span data-stu-id="3f785-150">These activities are created by using the Collections page.</span></span> <span data-ttu-id="3f785-151">Use atividades para rastrear o trabalho que você relacionou às cobranças.</span><span class="sxs-lookup"><span data-stu-id="3f785-151">Use activities to track the work that you do related to collections.</span></span>
-   <span data-ttu-id="3f785-152">Casos de cobranças – as colunas na página de lista exibem informações para casos que têm uma categoria de caso com um tipo de caso Cobranças.</span><span class="sxs-lookup"><span data-stu-id="3f785-152">Collections cases – The columns on the list page display information for cases that have a case category with a case type of Collections.</span></span>

> [!NOTE]
> <span data-ttu-id="3f785-153">Um instantâneo de classificação por vencimento deve ser criado para que você possa exibir as informações nessas páginas de lista.</span><span class="sxs-lookup"><span data-stu-id="3f785-153">An aging snapshot must be created before you can view information on these list pages.</span></span> <span data-ttu-id="3f785-154">As informações são exibidas somente para os clientes que o instantâneo de classificação por vencimento foi criado.</span><span class="sxs-lookup"><span data-stu-id="3f785-154">Information is displayed only for customers for whom an aging snapshot has been created.</span></span> <span data-ttu-id="3f785-155">Os registros que são mostrados na página de lista podem ser filtrados adicionalmente, da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="3f785-155">The records that are shown on the list page can be additionally filtered, as follows:</span></span>
> <li><span data-ttu-id="3f785-156">Por padrão, um usuário do Finance and Operations tem acesso a todos os clientes com um instantâneo de classificação por vencimento.</span><span class="sxs-lookup"><span data-stu-id="3f785-156">By default, a Finance and Operations user has access to all customers who have an aging snapshot.</span></span></li>
> <li><span data-ttu-id="3f785-157">Se os grupos de clientes existem, um usuário deve ser configurado como um agente de cobranças para usar os grupos para filtrar as informações nas páginas de lista de cobranças.</span><span class="sxs-lookup"><span data-stu-id="3f785-157">If customer pools exist, a user must be set up as a collections agent to use the pools to filter information on the collections list pages.</span></span> <span data-ttu-id="3f785-158">As informações são limitadas aos clientes incluídos no grupo de clientes selecionado.</span><span class="sxs-lookup"><span data-stu-id="3f785-158">Information is limited to the customers who are included in the selected customer pool.</span></span></li>
> <li><span data-ttu-id="3f785-159">Se um usuário estiver configurado como um agente de cobranças, apenas os grupos selecionados para esse agente de cobranças estarão disponíveis na página de lista.</span><span class="sxs-lookup"><span data-stu-id="3f785-159">If a user is set up as a collections agent, only the pools that are selected for that collections agent are available on the list page.</span></span> <span data-ttu-id="3f785-160">Se o botão de alternância Permitir que o agente exiba todos os grupos de clientes estiver selecionado na página Agente de cobranças do agente de cobranças, todos os grupos estarão disponíveis para esse agente.</span><span class="sxs-lookup"><span data-stu-id="3f785-160">If the Allow agent to view all customer pools toggle is selected in the Collections agent page for the collections agent, all pools are available for that agent.</span></span></li>


## <a name="collections-page"></a><span data-ttu-id="3f785-161"> Página Cobranças</span><span class="sxs-lookup"><span data-stu-id="3f785-161">Collections page</span></span>
<span data-ttu-id="3f785-162">Use a página Cobranças para exibir, gerenciar e adotar uma ação nas informações, atividades e casos de cobranças para um cliente.</span><span class="sxs-lookup"><span data-stu-id="3f785-162">Use the Collections page to view, manage, and take action on collections information, activities, and cases for a customer.</span></span> 

<span data-ttu-id="3f785-163">O painel superior exibe as ocorrências do cliente selecionado.</span><span class="sxs-lookup"><span data-stu-id="3f785-163">The upper pane displays cases for the selected customer.</span></span> <span data-ttu-id="3f785-164">O painel central exibe as transações do cliente selecionado.</span><span class="sxs-lookup"><span data-stu-id="3f785-164">The middle pane displays transactions for the customer.</span></span> <span data-ttu-id="3f785-165">O painel inferior exibe atividades para o cliente.</span><span class="sxs-lookup"><span data-stu-id="3f785-165">The lower pane displays activities for the customer.</span></span> <span data-ttu-id="3f785-166">Você pode criar casos de cobranças para controlar as informações de cobranças para uma ou mais transações e atividades.</span><span class="sxs-lookup"><span data-stu-id="3f785-166">You can create collections cases to track collections information for one or more transactions and activities.</span></span> <span data-ttu-id="3f785-167">As informações nos painéis superior e inferior podem ser filtradas por caso.</span><span class="sxs-lookup"><span data-stu-id="3f785-167">The information in the upper and lower panes can be filtered by case.</span></span> 

<span data-ttu-id="3f785-168">Os Quadros de Fatos exibem saldos classificados por vencimento e informações de limite de crédito para o cliente selecionado.</span><span class="sxs-lookup"><span data-stu-id="3f785-168">FactBoxes display aged balances and credit limit information for the selected customer.</span></span> <span data-ttu-id="3f785-169">Essas informações ficam armazenadas no instantâneo de classificação por vencimento.</span><span class="sxs-lookup"><span data-stu-id="3f785-169">This information is stored in the aging snapshot.</span></span> <span data-ttu-id="3f785-170">Se necessário, você pode atualizar o instantâneo de classificação por vencimento com informações atuais.</span><span class="sxs-lookup"><span data-stu-id="3f785-170">If necessary, you can update the aging snapshot with current information.</span></span> 

<span data-ttu-id="3f785-171">O Painel de Ação contém os botões que exibem informações relacionadas para o cliente, o caso, a transação ou a atividade selecionada.</span><span class="sxs-lookup"><span data-stu-id="3f785-171">The Action Pane contains buttons that display related information for the selected customer, case, transaction, or activity.</span></span> <span data-ttu-id="3f785-172">Você também pode executar ações comuns, como alterar o status de cobranças de uma transação, enviar correspondência por email por meio da integração com seu provedor de email, reembolsar clientes, processar pagamentos NSF e dar baixa em saldos não cobráveis.</span><span class="sxs-lookup"><span data-stu-id="3f785-172">You can also perform common actions such as changing the collections status of a transaction, sending email correspondence through the integration with your email provider, reimbursing customers, processing NSF payments, and writing off uncollectible balances.</span></span>

## <a name="waive-reinstate-or-reverse-interest-and-fees"></a><span data-ttu-id="3f785-173"> Cancelar, restabelecer ou estornar juros ou taxas </span><span class="sxs-lookup"><span data-stu-id="3f785-173">Waive, reinstate, or reverse interest and fees</span></span>
<span data-ttu-id="3f785-174">Você pode renunciar, reaplicar ou reverter notas de juros completas, ou taxas e juros de transação que fazem parte das notas de juros.</span><span class="sxs-lookup"><span data-stu-id="3f785-174">You can waive, reinstate, or reverse complete interest notes, or fees and transaction interest that are a part of interest notes.</span></span> <span data-ttu-id="3f785-175">Você pode fazer isso na guia Coletar do Painel de Ação na página de listagem Todos os clientes ao clicar em Nota de juros, em Juros da transação ou em Taxa.</span><span class="sxs-lookup"><span data-stu-id="3f785-175">You can do this from the Collect tab on the Action Pane on the All customers list page by clicking Interest note, Transaction interest, or Fee.</span></span> 

<span data-ttu-id="3f785-176">Esses ajustes afetam somente as notas de juros e os juros e as taxas que elas incluem.</span><span class="sxs-lookup"><span data-stu-id="3f785-176">These adjustments affect only interest notes, and the interest and fees that they include.</span></span> <span data-ttu-id="3f785-177">Use as etapas descritas na seção “Criar transações de baixa em uma etapa” para dar baixa de todos os encargos devidos por um cliente.</span><span class="sxs-lookup"><span data-stu-id="3f785-177">Use the steps in the “Create write-off transactions in one step” section to write off all of the charges that a customer owes.</span></span>

<span data-ttu-id="3f785-178">Para obter mais informações, consulte [Criar um código de juros com um intervalo](tasks/create-interest-code-range.md) e [Processar juros](tasks/process-interest.md).</span><span class="sxs-lookup"><span data-stu-id="3f785-178">For more information see, [Create an interest code with a range](tasks/create-interest-code-range.md) and [Process interest](tasks/process-interest.md).</span></span> 

## <a name="create-writeoff-transactions"></a><span data-ttu-id="3f785-179">Criar transações de baixa</span><span class="sxs-lookup"><span data-stu-id="3f785-179">Create writeoff transactions</span></span>
<span data-ttu-id="3f785-180">Você pode dar baixa em dívidas perdidas ao clicar em Dar baixa no formulário Cobranças e nas páginas de listagem Saldos classificados por vencimento., Clientes e Faturas de cliente abertas.</span><span class="sxs-lookup"><span data-stu-id="3f785-180">You can write off bad debts by clicking Write off in the Collections form, and on the Aged balances, Customers, and Open customer invoices list pages.</span></span> 

<span data-ttu-id="3f785-181">Quando você dá baixa nas transações de um cliente, todas as transações correspondentes são marcadas automaticamente para liquidação.</span><span class="sxs-lookup"><span data-stu-id="3f785-181">When you write off transactions for a customer, all transactions for the customer are automatically marked for settlement.</span></span> <span data-ttu-id="3f785-182">O valor da baixa depende do valor líquido das transações marcadas.</span><span class="sxs-lookup"><span data-stu-id="3f785-182">The amount that is written off depends on the net amount of the marked transactions.</span></span> <span data-ttu-id="3f785-183">A transação de baixa é criada em um diário geral e pode conter até três tipos de linhas de diário.</span><span class="sxs-lookup"><span data-stu-id="3f785-183">The write-off transaction is created in a general journal and can contain up to three types of journal lines.</span></span>

-   <span data-ttu-id="3f785-184">O primeiro tipo de linha do diário contém a entrada de baixa do cliente.</span><span class="sxs-lookup"><span data-stu-id="3f785-184">The first type of journal line contains the customer write-off entry.</span></span> <span data-ttu-id="3f785-185">Se as transações marcadas contiverem várias combinações de código de moeda, dimensão e perfil de lançamento, uma linha de diário separada será criada para cada combinação.</span><span class="sxs-lookup"><span data-stu-id="3f785-185">If the marked transactions contain multiple combinations of currency code, dimension, and posting profile, a separate journal line is created for each combination.</span></span>
-   <span data-ttu-id="3f785-186">O segundo tipo de linha do diário contém a entrada de baixa de contabilidade.</span><span class="sxs-lookup"><span data-stu-id="3f785-186">The second type of journal line contains the general ledger write-off entry.</span></span> <span data-ttu-id="3f785-187">Se as transações marcadas contiverem várias combinações de código de moeda, dimensão e perfil de lançamento, uma linha de diário separada será criada para cada combinação.</span><span class="sxs-lookup"><span data-stu-id="3f785-187">If the marked transactions contain multiple combinations of currency code, dimension, and posting profile, a separate journal line is created for each combination.</span></span>
-   <span data-ttu-id="3f785-188">O terceiro tipo de linha do diário contém as informações de baixa de contabilidade para impostos.</span><span class="sxs-lookup"><span data-stu-id="3f785-188">The third type of journal line contains the general ledger write-off information for sales taxes.</span></span> <span data-ttu-id="3f785-189">Essa linha do diário só será criada se o botão de alternância Imposto separado for selecionado na página Parâmetros de contas a receber.</span><span class="sxs-lookup"><span data-stu-id="3f785-189">This journal line is created only if the Separate sales tax toggle is selected in the Accounts receivable parameters page.</span></span> <span data-ttu-id="3f785-190">Se as transações marcadas contiverem várias combinações de contas a pagar de imposto, dimensão e código de imposto, uma linha de diário separada será criada para cada combinação.</span><span class="sxs-lookup"><span data-stu-id="3f785-190">If the marked transactions contain multiple combinations of sales tax payable account, dimension, and sales tax code, a separate journal line is created for each combination.</span></span>

<span data-ttu-id="3f785-191">A transação de baixa é criada na moeda da transação.</span><span class="sxs-lookup"><span data-stu-id="3f785-191">The write-off transaction is created in the transaction currency.</span></span>

<span data-ttu-id="3f785-192">Para obter mais informações, consulte [Criar um diário de baixa para um cliente](tasks/create-write-off-journal-customer.md).</span><span class="sxs-lookup"><span data-stu-id="3f785-192">For more information see, [Create a write-off journal for a customer](tasks/create-write-off-journal-customer.md).</span></span>

<a name="process-not-sufficient-funds-nsf-payments"></a><span data-ttu-id="3f785-193">Processar pagamento de insuficiência de fundos (NSF) </span><span class="sxs-lookup"><span data-stu-id="3f785-193">Process not sufficient funds (NSF) payments</span></span> 
--------------------------------------------

<span data-ttu-id="3f785-194">Você pode processar pagamentos NSF ao clicar em Pagamento NSF na página Cobranças.</span><span class="sxs-lookup"><span data-stu-id="3f785-194">You can process NSF payments by clicking NSF payment in the Collections page.</span></span> <span data-ttu-id="3f785-195">Quando você clica nesse botão, o pagamento é cancelado.</span><span class="sxs-lookup"><span data-stu-id="3f785-195">When you click this button, the payment is canceled.</span></span> <span data-ttu-id="3f785-196">Se uma taxa de NSF for aplica ao cliente, uma transação de encargo será criada em um diário de pagamento.</span><span class="sxs-lookup"><span data-stu-id="3f785-196">If an NSF fee applies for the customer, a charge transaction is created in a payment journal.</span></span> <span data-ttu-id="3f785-197">O valor da taxa é baseado nas configurações de encargos automáticos.</span><span class="sxs-lookup"><span data-stu-id="3f785-197">The fee amount is based on the settings for the automatic charges.</span></span> <span data-ttu-id="3f785-198">Os encargos automáticas que se aplicam aos pagamentos NSF são especificados pelo grupo de encargos selecionado na página Contas bancárias para a conta bancária afetada.</span><span class="sxs-lookup"><span data-stu-id="3f785-198">The automatic charges that apply for NSF payments are specified by the charges group that is selected in the Bank accounts page for the affected bank account.</span></span>




