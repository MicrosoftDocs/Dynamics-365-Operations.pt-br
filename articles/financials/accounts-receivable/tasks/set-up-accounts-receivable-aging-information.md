---
title: Configurar e gerar informações de classificação por vencimento de contas a receber
description: Esta guia ajudará a configurar uma definição do período de classificação por vencimento, para classificar por vencimento saldos do cliente e saldos de exibição na lista de saldos classificados por vencimento, além da página das coleções.
author: mikefalkner
manager: AnnBe
ms.date: 07/11/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustVendReportInterval, CustAgingSnapshot, CustCollectionsPoolsListPage, CustCollections
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mfalkner
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 77b5dd5feb16cc3bd6d64b6520cc47087c5b5224
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1834358"
---
# <a name="set-up-and-generate-accounts-receivable-aging-information"></a><span data-ttu-id="b0e2e-103">Configurar e gerar informações de classificação por vencimento de contas a receber</span><span class="sxs-lookup"><span data-stu-id="b0e2e-103">Set up and generate accounts receivable aging information</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="b0e2e-104">Esta guia ajudará a configurar uma definição do período de classificação por vencimento, para classificar por vencimento saldos do cliente e saldos de exibição na lista de saldos classificados por vencimento, além da página das coleções.</span><span class="sxs-lookup"><span data-stu-id="b0e2e-104">This guide will help you set up an aging period definition, age customer balances, and view balances in the Aged balance list and the Collections page.</span></span> <span data-ttu-id="b0e2e-105">Este registro usa a empresa de dados de demonstração USMF.</span><span class="sxs-lookup"><span data-stu-id="b0e2e-105">This recording uses the USMF demo company.</span></span>


## <a name="create-an-aging-period-definition"></a><span data-ttu-id="b0e2e-106">Crie uma definição de período de classificação por vencimento</span><span class="sxs-lookup"><span data-stu-id="b0e2e-106">Create an aging period definition</span></span>
1. <span data-ttu-id="b0e2e-107">Vá para **Painel de navegação > Módulos > Crédito e coleções > Configuração > Definições de período de classificação por vencimento**.</span><span class="sxs-lookup"><span data-stu-id="b0e2e-107">Go to **Navigation pane > Modules > Credit and collections > Setup > Aging period definitions**.</span></span>
2. <span data-ttu-id="b0e2e-108">Clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="b0e2e-108">Click **New**.</span></span>
3. <span data-ttu-id="b0e2e-109">No campo **Definição do período de classificação por vencimento**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="b0e2e-109">In the **Aging period definition** field, type a value.</span></span>
4. <span data-ttu-id="b0e2e-110">No campo **Descrição**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="b0e2e-110">In the **Description** field, type a value.</span></span>
5. <span data-ttu-id="b0e2e-111">Clique em **Adicionar abaixo** para inserir um novo período de classificação por vencimento.</span><span class="sxs-lookup"><span data-stu-id="b0e2e-111">Click **Add below** to insert a new aging period.</span></span>
6. <span data-ttu-id="b0e2e-112">No campo **Período**, insira a descrição a ser mostrada no relatório de classificação por vencimento.</span><span class="sxs-lookup"><span data-stu-id="b0e2e-112">In the **Period** field, enter the description to show on aging reports.</span></span>
7. <span data-ttu-id="b0e2e-113">No campo **Unidade**, insira um número.</span><span class="sxs-lookup"><span data-stu-id="b0e2e-113">In the **Unit** field, enter a number.</span></span>
8. <span data-ttu-id="b0e2e-114">No campo **Intervalo**, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="b0e2e-114">In the **Interval** field, select an option.</span></span> <span data-ttu-id="b0e2e-115">O período do razão no período corresponde ao calendário do razão.</span><span class="sxs-lookup"><span data-stu-id="b0e2e-115">Ledger period matches the period to your ledger calendar.</span></span> <span data-ttu-id="b0e2e-116">O dia, a semana, o mês, trimestre e o ano definem o tamanho do intervalo por tipo de data.</span><span class="sxs-lookup"><span data-stu-id="b0e2e-116">Day, week, month, quarter and years define the size of the interval by date type.</span></span> <span data-ttu-id="b0e2e-117">Ilimitado seleciona todas as transações antes ou depois do período anterior, caso seja o primeiro período ou o último.</span><span class="sxs-lookup"><span data-stu-id="b0e2e-117">Unlimited selects all transactions before or after the previous period, depending on whether it is the first or last period.</span></span>  
9. <span data-ttu-id="b0e2e-118">No campo **Indicador de classificação por vencimento**, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="b0e2e-118">In the **Aging indicator** field, select an option.</span></span>
10. <span data-ttu-id="b0e2e-119">Selecione o período na parte superior da grade.</span><span class="sxs-lookup"><span data-stu-id="b0e2e-119">Select the period at the top of the grid.</span></span> <span data-ttu-id="b0e2e-120">Atualize a descrição para descrever o mais antigo na definição do período de classificação por vencimento</span><span class="sxs-lookup"><span data-stu-id="b0e2e-120">Update the description to describe the oldest period in the aging period definition</span></span>
11. <span data-ttu-id="b0e2e-121">No campo **Período**, insira a nova descrição do período de classificação por vencimento.</span><span class="sxs-lookup"><span data-stu-id="b0e2e-121">In the **Period** field, enter the new description of the aging period.</span></span>
12. <span data-ttu-id="b0e2e-122">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="b0e2e-122">Close the page.</span></span>

## <a name="age-the-balances"></a><span data-ttu-id="b0e2e-123">Saldos com vencimento</span><span class="sxs-lookup"><span data-stu-id="b0e2e-123">Age the balances</span></span>
1. <span data-ttu-id="b0e2e-124">Vá para **Crédito e coleções > Tarefas periódicas > Classificar saldos de cliente por vencimento**.</span><span class="sxs-lookup"><span data-stu-id="b0e2e-124">Go to **Credit and collections > Periodic tasks > Age customer balances**.</span></span>
2. <span data-ttu-id="b0e2e-125">No campo **Definição do período de classificação por vencimento**, selecione a definição do período de classificação por vencimento que você criou.</span><span class="sxs-lookup"><span data-stu-id="b0e2e-125">In the **Aging period definition** field, select the aging period definition that you created.</span></span>
    + <span data-ttu-id="b0e2e-126">Você pode ter um instantâneo ativo para cada definição do período de classificação por vencimento.</span><span class="sxs-lookup"><span data-stu-id="b0e2e-126">You can have one active snapshot for each aging period definition.</span></span>  
    + <span data-ttu-id="b0e2e-127">Todas os clientes são processados por padrão.</span><span class="sxs-lookup"><span data-stu-id="b0e2e-127">All customers are processed by default.</span></span> <span data-ttu-id="b0e2e-128">Você pode usar essa seleção para calcular um único grupo de conjuntos de clientes.</span><span class="sxs-lookup"><span data-stu-id="b0e2e-128">You can use this selection to calculate a single collections pool of customers.</span></span>  
    + <span data-ttu-id="b0e2e-129">Selecione a data da transação que será usada para a classificação por vencimento.</span><span class="sxs-lookup"><span data-stu-id="b0e2e-129">Select the date from the transaction that you will use for the aging.</span></span>  
    + <span data-ttu-id="b0e2e-130">Selecione a data “a partir de”para classificação de vencimento.</span><span class="sxs-lookup"><span data-stu-id="b0e2e-130">Select an "as of" date for aging.</span></span> <span data-ttu-id="b0e2e-131">O padrão é a data atual, mas se você alterar este campo à data selecionada, você poderá escolher a data desejada.</span><span class="sxs-lookup"><span data-stu-id="b0e2e-131">The default is today but, if you change this field to Selected date, you will be able to pick the date that you want.</span></span> <span data-ttu-id="b0e2e-132">Para processamento em lotes, use a data de hoje.</span><span class="sxs-lookup"><span data-stu-id="b0e2e-132">For batch processing, use Today's date.</span></span>  
3. <span data-ttu-id="b0e2e-133">Expanda o intervalo de **Empresa**.</span><span class="sxs-lookup"><span data-stu-id="b0e2e-133">Expand the **Company** range.</span></span> <span data-ttu-id="b0e2e-134">Você pode selecionar as empresas que serão incluídas no instantâneo.</span><span class="sxs-lookup"><span data-stu-id="b0e2e-134">You can select the companies that will be included in the snapshot.</span></span> <span data-ttu-id="b0e2e-135">A empresa atual é selecionada por padrão.</span><span class="sxs-lookup"><span data-stu-id="b0e2e-135">The current company is selected by default.</span></span>
4. <span data-ttu-id="b0e2e-136">Clique em **OK** para processar o instantâneo.</span><span class="sxs-lookup"><span data-stu-id="b0e2e-136">Click **Ok** to process the snapshot.</span></span> <span data-ttu-id="b0e2e-137">Levará algum tempo para que o controle deslizante desapareça e verifique o centro da mensagem para uma mensagem.</span><span class="sxs-lookup"><span data-stu-id="b0e2e-137">It will take some time so wait for the slider to disappear and check the message center for a message.</span></span>

## <a name="view-the-balances-on-the-aged-balances-list-and-on-the-collection-page"></a><span data-ttu-id="b0e2e-138">Exibir os saldos na lista de saldos classificados por vencimento e na página de cobrança</span><span class="sxs-lookup"><span data-stu-id="b0e2e-138">View the balances on the Aged balances list and on the Collection page</span></span>
1. <span data-ttu-id="b0e2e-139">Vá para **Crédito e coleções > Cobranças > Saldos antigos**.</span><span class="sxs-lookup"><span data-stu-id="b0e2e-139">Go to **Credit and collections > Collections > Aged balances**.</span></span> <span data-ttu-id="b0e2e-140">A página de listagem mostra os saldos do cliente.</span><span class="sxs-lookup"><span data-stu-id="b0e2e-140">The list page shows the balances for the customer.</span></span> <span data-ttu-id="b0e2e-141">O ícone classificação por vencimento mostra o período de classificação por vencimento da transação mais antigo.</span><span class="sxs-lookup"><span data-stu-id="b0e2e-141">The aging icon shows the aging period for the oldest transaction.</span></span>  
2. <span data-ttu-id="b0e2e-142">Selecione um cliente com um saldo.</span><span class="sxs-lookup"><span data-stu-id="b0e2e-142">Select a customer with a balance.</span></span>
3. <span data-ttu-id="b0e2e-143">Expanda a área da caixa de dados **Classificação por vencimento** para exibir os saldos classificados por vencimento.</span><span class="sxs-lookup"><span data-stu-id="b0e2e-143">Expand the **Aging fact** box area to view the aged balances.</span></span> <span data-ttu-id="b0e2e-144">A definição do período de classificação por vencimento da caixa de fatos são tiradas da definição do período de classificação por vencimento padrão especificado nos parâmetros.</span><span class="sxs-lookup"><span data-stu-id="b0e2e-144">The aging period definition for the fact box is taken from the default aging period definition specified in the parameters.</span></span> <span data-ttu-id="b0e2e-145">Você pode alterá-la usando o menu Coletar.</span><span class="sxs-lookup"><span data-stu-id="b0e2e-145">You can change it using the Collect menu.</span></span>  

