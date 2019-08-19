---
title: Fechar o ano fiscal
description: Este procedimento aborda o processo de fechamento do exercício que transfere saldos para um novo ano fiscal.
author: aprilolson
manager: AnnBe
ms.date: 07/11/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerParameters, LedgerFiscalCloseGroup, LedgerFiscalCloseAddLedger, SysLookupMultiSelectGrid, LedgerFiscalCloseRunGroup
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c12f0842f6e8edf3b51d12d0e008eb09acf8c374
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1834917"
---
# <a name="close-the-fiscal-year"></a><span data-ttu-id="d06ea-103">Fechar o ano fiscal</span><span class="sxs-lookup"><span data-stu-id="d06ea-103">Close the fiscal year</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="d06ea-104">Este procedimento aborda o processo de fechamento do exercício que transfere saldos para um novo ano fiscal.</span><span class="sxs-lookup"><span data-stu-id="d06ea-104">This procedure steps through the year end close process that transfers balances to a new fiscal year.</span></span>


## <a name="validate-year-end-close-parameters"></a><span data-ttu-id="d06ea-105">Valide os parâmetros próximos de final de ano</span><span class="sxs-lookup"><span data-stu-id="d06ea-105">Validate year-end close parameters</span></span>
1. <span data-ttu-id="d06ea-106">Vá para **Painel de navegação > Módulos> Contabilidade > Configuração do razão > Parâmetros da contabilidade**.</span><span class="sxs-lookup"><span data-stu-id="d06ea-106">Go to **Navigation pane > Modules > General ledger > Ledger setup > General ledger parameters**.</span></span>
2. <span data-ttu-id="d06ea-107">Expandir a seção **Fechamento do ano fiscal**.</span><span class="sxs-lookup"><span data-stu-id="d06ea-107">Expand the **Fiscal year close** section.</span></span>
3. <span data-ttu-id="d06ea-108">Selecione 'Sim' ou 'Não' para a opção **Excluir transações de fechamento de ano durante a transferência**.</span><span class="sxs-lookup"><span data-stu-id="d06ea-108">Select 'Yes' or 'No' for the **Delete close-of-year transactions during transfer** option.</span></span>
    
    <span data-ttu-id="d06ea-109">Se o ano fiscal tiver sido fechado e o fechamento de fim de ano estiver sendo executado novamente, essa configuração é importante.</span><span class="sxs-lookup"><span data-stu-id="d06ea-109">If the fiscal year has already been closed and the year-end close is being run again, this setting is important.</span></span> <span data-ttu-id="d06ea-110">Se definido para Sim, o comprovante do fechamento anterior de final de ano será excluído, e um novo comprovante será criado para todas as contas que iniciam saldos.</span><span class="sxs-lookup"><span data-stu-id="d06ea-110">If set to Yes, the voucher for the previous year-end close will be deleted, and a new voucher will be created for all accounts beginning balances.</span></span> <span data-ttu-id="d06ea-111">Se definido para Não, nenhum comprovante anterior permanecerá e um novo comprovante será criada apenas para as entradas de ajuste lançadas após o fechamento do final do ano.</span><span class="sxs-lookup"><span data-stu-id="d06ea-111">If set to No, the previous voucher will remain and a new voucher will only be created for adjusting entries that were posted after the last year-end close.</span></span>

4. <span data-ttu-id="d06ea-112">Selecione 'Sim' ou 'Não' para a opção **Criar transações de fechamento durante a transferência**.</span><span class="sxs-lookup"><span data-stu-id="d06ea-112">Select 'Yes' or 'No' for the **Create closing transactions during transfer** option.</span></span>

    <span data-ttu-id="d06ea-113">Se definido como Sim, duas transações são criadas.</span><span class="sxs-lookup"><span data-stu-id="d06ea-113">If set to Yes, two transactions are created.</span></span> <span data-ttu-id="d06ea-114">Um comprovante é criado no ano fiscal que está sendo fechado para reduzir os saldos de contas contábeis de P&L a zero, e um segundo comprovante é criado no próximo ano fiscal para os saldos iniciais.</span><span class="sxs-lookup"><span data-stu-id="d06ea-114">One voucher is created in the fiscal year being closed to bring the balances of the P&L ledger accounts down to zero and a second voucher is created in the next fiscal year for the beginning balances.</span></span> <span data-ttu-id="d06ea-115">Se definido para Não, um único comprovante é criado no próximo ano fiscal para o início dos saldos.</span><span class="sxs-lookup"><span data-stu-id="d06ea-115">If set to No, a single voucher is created in the next fiscal year for the beginning balances.</span></span>  

5. <span data-ttu-id="d06ea-116">Selecione 'Sim' ou 'Não' para a opção **Definir status de ano fiscal como permanentemente fechado**.</span><span class="sxs-lookup"><span data-stu-id="d06ea-116">Select 'Yes' or 'No' for the **Set fiscal year status to permanently closed** option.</span></span>

    <span data-ttu-id="d06ea-117">Se estiver definido para Sim, o status do ano fiscal será definido como Permanentemente fechado.</span><span class="sxs-lookup"><span data-stu-id="d06ea-117">If set to Yes, the fiscal year status will be set to Permanently closed.</span></span>  <span data-ttu-id="d06ea-118">Como um ano permanentemente fechado não pode ser reaberto, é uma prática recomendada definir esta opção como não.</span><span class="sxs-lookup"><span data-stu-id="d06ea-118">Because a permanently closed year cannot be reopened, it would be a best practice to set this option to No.</span></span>  

6. <span data-ttu-id="d06ea-119">Selecione 'Sim' ou 'Não' para a opção **Número de comprovante deve ser preenchido durante o fechamento do exercício**.</span><span class="sxs-lookup"><span data-stu-id="d06ea-119">Select 'Yes' or 'No' for the **Voucher number must be filled in during the year end close** option.</span></span>

    <span data-ttu-id="d06ea-120">Se definido como Sim, um número de comprovante deverá ser inserido manualmente durante o processo de fechamento do ano.</span><span class="sxs-lookup"><span data-stu-id="d06ea-120">If set to Yes, a voucher number must be manually entered during the year end close process.</span></span> <span data-ttu-id="d06ea-121">Uma sequência numérica não será usada para gerar esse número de comprovante.</span><span class="sxs-lookup"><span data-stu-id="d06ea-121">A number sequence is not used to generate this voucher number.</span></span> <span data-ttu-id="d06ea-122">É uma melhor prática defini-lo para Sim.</span><span class="sxs-lookup"><span data-stu-id="d06ea-122">It's a best practice to set this to Yes.</span></span>  

7. <span data-ttu-id="d06ea-123">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="d06ea-123">Close the page.</span></span>
8. <span data-ttu-id="d06ea-124">Vá para **Contabilidade > Fechamento de período > Fechamento do exercício**.</span><span class="sxs-lookup"><span data-stu-id="d06ea-124">Go to **General ledger > Period close > Year end close**.</span></span>
9. <span data-ttu-id="d06ea-125">Clique em **Novo** para criar um modelo de fechamento do exercício.</span><span class="sxs-lookup"><span data-stu-id="d06ea-125">Click **New** to create a year-end close template.</span></span>

    <span data-ttu-id="d06ea-126">Um modelo podem ser criados para um grupo de entidades legais em que executa o fechamento de fim de ano.</span><span class="sxs-lookup"><span data-stu-id="d06ea-126">A template can be created for a group of legal entities for which to run the year-end close.</span></span> <span data-ttu-id="d06ea-127">Esse método pode ser reutilizado todos os anos.</span><span class="sxs-lookup"><span data-stu-id="d06ea-127">This template can be reused year after year.</span></span>  

10. <span data-ttu-id="d06ea-128">No campo **Nome do grupo**, insira um nome do modelo de fechamento do exercício.</span><span class="sxs-lookup"><span data-stu-id="d06ea-128">In the **Group name** field, enter a year-end close template name..</span></span>
11. <span data-ttu-id="d06ea-129">No campo **Calendário fiscal**, selecione o ano fiscal para o qual o modelo será criado.</span><span class="sxs-lookup"><span data-stu-id="d06ea-129">In the **Fiscal calendar** field, select the fiscal year for which the template will be created.</span></span>

    <span data-ttu-id="d06ea-130">Apenas as entidades legais que usam o mesmo ano fiscal podem ser agrupadas no modelo de fechamento de fim de ano.</span><span class="sxs-lookup"><span data-stu-id="d06ea-130">Only legal entities which use the same fiscal year can be grouped together in the year-end close template.</span></span> <span data-ttu-id="d06ea-131">Isso porque o fechamento de anos é feito por um ano fiscal, sem uma data.</span><span class="sxs-lookup"><span data-stu-id="d06ea-131">This is because the year end close is done by selecting a fiscal year, not a date.</span></span>  

12. <span data-ttu-id="d06ea-132">No **Painel de ação**, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="d06ea-132">On the **Action pane**, click **Save**.</span></span>
13. <span data-ttu-id="d06ea-133">Na seção **Entidades legais**, clique em **Adicionar** para selecionar as entidades legais para este modelo.</span><span class="sxs-lookup"><span data-stu-id="d06ea-133">In the **Legal entities** section, click **Add** to select the legal entities for this template.</span></span>
    
    <span data-ttu-id="d06ea-134">As entidades legais podem ser adicionadas às entidades legais ou selecionando uma hierarquia organizacional.</span><span class="sxs-lookup"><span data-stu-id="d06ea-134">Legal entities can be added by either selecting the legal entities or by selecting an organizational hierarchy.</span></span>  <span data-ttu-id="d06ea-135">Apenas as entidades legais com a hierarquia organizacional com o mesmo calendário fiscal selecionado serão adicionadas.</span><span class="sxs-lookup"><span data-stu-id="d06ea-135">Only legal entities with the organizational hierarchy with the same fiscal calendar selected will be added.</span></span>  

14. <span data-ttu-id="d06ea-136">Selecione as entidades legais ou a hierarquia organizacional.</span><span class="sxs-lookup"><span data-stu-id="d06ea-136">Select either the legal entities or the organizational hierarchy.</span></span>
15. <span data-ttu-id="d06ea-137">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="d06ea-137">Click **OK**.</span></span>
16. <span data-ttu-id="d06ea-138">Selecione 'Sim' ou 'Não' em **Transferir dimensão de balanço**.</span><span class="sxs-lookup"><span data-stu-id="d06ea-138">Select 'Yes' or 'No' in the **Transfer balance sheet dimension**.</span></span>

    <span data-ttu-id="d06ea-139">É uma prática recomendada definir esta opção como Sim para Contas de balanço.</span><span class="sxs-lookup"><span data-stu-id="d06ea-139">It's best practice to set this option to Yes for Balance sheet accounts.</span></span> <span data-ttu-id="d06ea-140">Isso manterá abertas as dimensões financeiras em transações lançadas quando criar o saldo inicial para as contas de balanço.</span><span class="sxs-lookup"><span data-stu-id="d06ea-140">This will maintain the financial dimensions on posted transactions when creating the beginning balances for the balance sheet accounts.</span></span> <span data-ttu-id="d06ea-141">Para contas de lucros e perdas, pode optar por manter dimensões financeiras (Fechar tudo) quando os saldos serão movidos a ganhos retidos ou selecionar para que as dimensões financeiras substituir por um valor diferente de dimensão (Fechar único)</span><span class="sxs-lookup"><span data-stu-id="d06ea-141">For profit and loss accounts, you can select to maintain the financial dimensions (Close all) when the balances are moved to Retained earnings or you can select to have the financial dimensions replaced with a different dimension value (Close single).</span></span> <span data-ttu-id="d06ea-142">Se você optar fechamento único, defina um valor de dimensão específico para cada dimensão ou mesmo escolha para deixá-la em branco.</span><span class="sxs-lookup"><span data-stu-id="d06ea-142">If you choose Close single, you can define a specific dimension value for each dimension or even choose to leave it blank.</span></span>  

17. <span data-ttu-id="d06ea-143">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="d06ea-143">Click **Save**.</span></span>
18. <span data-ttu-id="d06ea-144">Inicie o fechamento do exercício escolhendo **Executar fechamento de ano fiscal** no **Painel de Ação**.</span><span class="sxs-lookup"><span data-stu-id="d06ea-144">Start the year-end close by choosing **Run fiscal close** on the **Action Pane**.</span></span> <span data-ttu-id="d06ea-145">O prazo final de ano será executado para o modelo selecionado.</span><span class="sxs-lookup"><span data-stu-id="d06ea-145">The year-end close will be run for the selected template.</span></span>  
19. <span data-ttu-id="d06ea-146">Selecione tudo ou um subgrupo de entidades legais do modelo em que executa o fechamento de fim de ano.</span><span class="sxs-lookup"><span data-stu-id="d06ea-146">Select all or a subset of legal entities from the template for which to run the year-end close.</span></span>

    <span data-ttu-id="d06ea-147">Ao executar pela primeira vez o fechamento do exercício, para obter saldos iniciais, a maioria das organizações podem optar por executar o fechamento do exercício para todas as entidades legais no modelo.</span><span class="sxs-lookup"><span data-stu-id="d06ea-147">When first running the year-end close, to get beginning balance,s most organizations may choose to run the year-end close for all legal entities within the template.</span></span> <span data-ttu-id="d06ea-148">Se as entradas de ajuste são realizadas após isso, selecione executar o final do ano seguinte para apenas as entidades legais com ajustes.</span><span class="sxs-lookup"><span data-stu-id="d06ea-148">If adjusting entries are made after that, you may choose to run the year-end close for only the legal entities that have adjustments.</span></span>  

20. <span data-ttu-id="d06ea-149">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="d06ea-149">Click **OK**.</span></span>
21. <span data-ttu-id="d06ea-150">Selecione o ano fiscal para o qual executar o fechamento de fim de ano.</span><span class="sxs-lookup"><span data-stu-id="d06ea-150">Select the fiscal year for which to run the year-end close.</span></span>
22. <span data-ttu-id="d06ea-151">No **campo Comprovante**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="d06ea-151">In the **Voucher field**, type a value.</span></span> <span data-ttu-id="d06ea-152">É uma prática recomendada incluir o ano fiscal no número de comprovante para facilitar a localização do comprovante de fechamento do exercício que é criado.</span><span class="sxs-lookup"><span data-stu-id="d06ea-152">It's best practice to include the fiscal year in the voucher number, to make it easier to find the year-end close voucher that is created.</span></span>  
23. <span data-ttu-id="d06ea-153">O fechamento do ano final padrão para executar o lote.</span><span class="sxs-lookup"><span data-stu-id="d06ea-153">The year-end close defaults to run in batch.</span></span> <span data-ttu-id="d06ea-154">É uma prática recomendada executar processos longos no modo de lote.</span><span class="sxs-lookup"><span data-stu-id="d06ea-154">It's best practice for long-running processes to run in batch mode.</span></span> <span data-ttu-id="d06ea-155">Geralmente é um desses processos, por isso o padrão é usar o modo de lote.</span><span class="sxs-lookup"><span data-stu-id="d06ea-155">This is typically one of those processes, which is why the default is to use batch mode.</span></span>  
24. <span data-ttu-id="d06ea-156">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="d06ea-156">Click **OK**.</span></span>

