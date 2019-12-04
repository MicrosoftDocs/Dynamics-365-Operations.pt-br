---
title: Reavaliação de moeda estrangeira para Contas a pagar e Contas a receber
description: As flutuações nas taxas de câmbio fazem com que o valor teórico (valor contábil) de transações abertas em moedas estrangeiras varie ao longo do tempo. Este artigo oferece informações sobre o processo de reavaliação de moeda estrangeira executado para atualizar o valor de transação abertas em Contas a pagar e em Contas a receber.
author: kweekley
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustExchRateAdjustment, VendExchRateAdjustment
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 14211
ms.assetid: defb1ea5-1f3e-4859-87d8-3f9954d3f388
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fb7a101fa9ef84ec3873bcd8054b8198db8d58c9
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2188386"
---
# <a name="foreign-currency-revaluation-for-accounts-payable-and-accounts-receivable"></a><span data-ttu-id="4cf31-104">Reavaliação de moeda estrangeira para Contas a pagar e Contas a receber</span><span class="sxs-lookup"><span data-stu-id="4cf31-104">Foreign currency revaluation for Accounts payable and Accounts receivable</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4cf31-105">As flutuações nas taxas de câmbio fazem com que o valor teórico (valor contábil) de transações abertas em moedas estrangeiras varie ao longo do tempo.</span><span class="sxs-lookup"><span data-stu-id="4cf31-105">Fluctuations in exchange rates cause the theoretical value (book value) of open transactions in foreign currencies to vary over time.</span></span> <span data-ttu-id="4cf31-106">Este artigo oferece informações sobre o processo de reavaliação de moeda estrangeira executado para atualizar o valor de transação abertas em Contas a pagar e em Contas a receber.</span><span class="sxs-lookup"><span data-stu-id="4cf31-106">This article provides information about the foreign currency revaluation process that you run to update the value of open transactions in Accounts payable and Accounts receivable.</span></span> 

<span data-ttu-id="4cf31-107">O valor teórico, ou valor contábil, de transações de fornecedor abertas em moedas estrangeiras varia ao longo do tempo por causa de flutuações em taxas de câmbio.</span><span class="sxs-lookup"><span data-stu-id="4cf31-107">The theoretical value, or book value, of open transactions in foreign currencies varies over time because of fluctuations in exchange rates.</span></span> <span data-ttu-id="4cf31-108">Para atualizar o valor de transação abertas em Contas a pagar e em Contas a receber, execute o processo de reavaliação de moeda estrangeira.</span><span class="sxs-lookup"><span data-stu-id="4cf31-108">To update the value of open transactions in Accounts payable and Accounts receivable, run the foreign currency revaluation process.</span></span> <span data-ttu-id="4cf31-109">A reavaliação de moeda estrangeira pode ser executada para Contas a pagar e Contas a receber.</span><span class="sxs-lookup"><span data-stu-id="4cf31-109">Foreign currency revaluation can be run for both Accounts payable and Accounts receivable.</span></span> <span data-ttu-id="4cf31-110">O processo usa uma nova taxa de câmbio para reavaliar valores abertos, ou valores não liquidados, em uma data especificada.</span><span class="sxs-lookup"><span data-stu-id="4cf31-110">The process uses a new exchange rate to revalue the open amounts, or not settled amounts, on a specified date.</span></span> <span data-ttu-id="4cf31-111">As diferenças entre as quantias originais lançadas e as quantias reavaliadas causarão lucro ou perda não realizada para cada transação aberta.</span><span class="sxs-lookup"><span data-stu-id="4cf31-111">The differences between the original posted amounts and the revalued amounts will cause an unrealized gain or loss for each open transaction.</span></span> <span data-ttu-id="4cf31-112">Os sub-razões de Contas a pagar e de Contas a receber são então atualizados para refletirem o lucro ou a perda não realizado, e uma entrada contábil é lançada na Contabilidade.</span><span class="sxs-lookup"><span data-stu-id="4cf31-112">The Accounts payable and Accounts receivable subledgers are then updated to reflect the unrealized gain or loss, and an accounting entry is posted to General ledger.</span></span>

## <a name="simulate-a-foreign-currency-revaluation"></a><span data-ttu-id="4cf31-113">Simular uma reavaliação de moeda estrangeira</span><span class="sxs-lookup"><span data-stu-id="4cf31-113">Simulate a foreign currency revaluation</span></span>
<span data-ttu-id="4cf31-114">Antes que você reavalie valores em moeda estrangeira em transações de cliente abertas para uma data específica, é possível executar um relatório da reavaliação em moeda estrangeira para a mesma data e método.</span><span class="sxs-lookup"><span data-stu-id="4cf31-114">Before you revalue foreign currency amounts on open transactions, you can run a simulation report of the foreign currency revaluation for the same date and method.</span></span> <span data-ttu-id="4cf31-115">Para executar o relatório de simulação, na página **Reavaliação de moeda estrangeira**, clique no botão **Simulação**.</span><span class="sxs-lookup"><span data-stu-id="4cf31-115">To run the simulation report, on the **Foreign currency revaluation** page, click the **Simulation** button.</span></span> <span data-ttu-id="4cf31-116">O relatório fornece uma visualização do valor do lucro ou da perda não realizado nos parâmetros definidos para a simulação.</span><span class="sxs-lookup"><span data-stu-id="4cf31-116">The report provides a preview of the unrealized gain or loss amount, based on the parameters that are defined for the simulation.</span></span>

## <a name="process-a-foreign-currency-revaluation"></a><span data-ttu-id="4cf31-117">Processar uma reavaliação de moeda estrangeira</span><span class="sxs-lookup"><span data-stu-id="4cf31-117">Process a foreign currency revaluation</span></span>
<span data-ttu-id="4cf31-118">Use a página **Reavaliação de moeda estrangeira** nas **Tarefas periódicas** para reavaliar as transações abertas.</span><span class="sxs-lookup"><span data-stu-id="4cf31-118">Use the **Foreign currency revaluation** page under **Periodic tasks** to revalue open transactions.</span></span> <span data-ttu-id="4cf31-119">Você pode executar o processo em tempo real ou agendá-lo para execução usando um lote.</span><span class="sxs-lookup"><span data-stu-id="4cf31-119">You can run the process in real time or schedule it to run by using a batch.</span></span> <span data-ttu-id="4cf31-120">Quando você definir as configurações para o processo de reavaliação, verifique se deseja imprimir um relatório dos resultados</span><span class="sxs-lookup"><span data-stu-id="4cf31-120">When you define the settings for the revaluation process, be sure to verify whether you want to print a report of the results.</span></span> <span data-ttu-id="4cf31-121">O relatório de reavaliação não pode ser reimpresso depois que o processo for concluído.</span><span class="sxs-lookup"><span data-stu-id="4cf31-121">The revaluation report can't be reprinted after the process is completed.</span></span> <span data-ttu-id="4cf31-122">Se você gerar o relatório de reavaliação de moeda estrangeira, ele mostrará vários saldos no nível do cliente/fornecedor e no nível da moeda:</span><span class="sxs-lookup"><span data-stu-id="4cf31-122">If you generate the foreign currency revaluation report, it will show various balances at the customer/vendor level and the currency level:</span></span>

-   <span data-ttu-id="4cf31-123">Os saldos de clientes ou de fornecedores com transações de moeda estrangeira que foram reavaliados.</span><span class="sxs-lookup"><span data-stu-id="4cf31-123">The balances of customers or vendors that have foreign currency transactions that have been revalued.</span></span> <span data-ttu-id="4cf31-124">Os saldos a seguir são mostrados:</span><span class="sxs-lookup"><span data-stu-id="4cf31-124">The following balances are shown:</span></span>
    -   <span data-ttu-id="4cf31-125">O saldo total original na moeda estrangeira.</span><span class="sxs-lookup"><span data-stu-id="4cf31-125">The total original balance in the foreign currency.</span></span>
    -   <span data-ttu-id="4cf31-126">O valor total de moeda estrangeira na moeda contábil como na reavaliação anterior.</span><span class="sxs-lookup"><span data-stu-id="4cf31-126">The total foreign currency amount in the accounting currency, as of the previous revaluation.</span></span>
    -   <span data-ttu-id="4cf31-127">O valor total de moeda estrangeira na moeda contábil como na reavaliação atual.</span><span class="sxs-lookup"><span data-stu-id="4cf31-127">The total foreign currency amount in the accounting currency, as of the current revaluation.</span></span>
    -   <span data-ttu-id="4cf31-128">A diferença entre a reavaliação anterior e atual.</span><span class="sxs-lookup"><span data-stu-id="4cf31-128">The difference between the previous and current revaluation.</span></span> <span data-ttu-id="4cf31-129">Essa diferença é o lucro ou a perda não realizado adicional.</span><span class="sxs-lookup"><span data-stu-id="4cf31-129">This difference is the additional unrealized gain or loss.</span></span>
-   <span data-ttu-id="4cf31-130">O lucro ou a perda não realizado total para cada moeda.</span><span class="sxs-lookup"><span data-stu-id="4cf31-130">The total unrealized gain or loss for each currency.</span></span>

<span data-ttu-id="4cf31-131">Um registro é mantido sempre que você execute uma reavaliação de moeda estrangeira.</span><span class="sxs-lookup"><span data-stu-id="4cf31-131">A record is kept every time that you run a foreign currency revaluation.</span></span> <span data-ttu-id="4cf31-132">No registro da página **Avaliação de moeda estrangeira**, selecione **Transações** para exibir a lista detalhada de transações criadas por causa da reavaliação.</span><span class="sxs-lookup"><span data-stu-id="4cf31-132">From the record on the **Foreign currency valuation** page, select **Transactions** to view the detailed list of transactions that were created because of the revaluation.</span></span> <span data-ttu-id="4cf31-133">Cada transação de comprovante representa a transação aberta que foi reavaliada.</span><span class="sxs-lookup"><span data-stu-id="4cf31-133">Each voucher transaction represents the open transaction that was revalued.</span></span> <span data-ttu-id="4cf31-134">Se uma transação aberta tiver sido reavaliada mais de uma vez, você verá dois registros que usam o mesmo comprovante.</span><span class="sxs-lookup"><span data-stu-id="4cf31-134">If an open transaction was revalued more than one time, you will see two records that use the same voucher.</span></span> <span data-ttu-id="4cf31-135">Um registro será para reversão de lucro ou perda não realizado anterior, e outro registro será para o novo lucro ou perda não realizado.</span><span class="sxs-lookup"><span data-stu-id="4cf31-135">One record will be for the reversal of the previous unrealized gain or loss, and the other record will be for the new unrealized gain or loss.</span></span> <span data-ttu-id="4cf31-136">Para executar o processo de reavaliação, clique no botão **Reavaliação de moeda estrangeira**.</span><span class="sxs-lookup"><span data-stu-id="4cf31-136">To run the revaluation process, click the **Foreign currency revaluation** button.</span></span> <span data-ttu-id="4cf31-137">Defina as configurações apropriadas para os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="4cf31-137">Define appropriate settings for the following parameters:</span></span>

-   <span data-ttu-id="4cf31-138">**Método** – o método usado no trabalho de reavaliação de moeda estrangeira selecionado:</span><span class="sxs-lookup"><span data-stu-id="4cf31-138">**Method** – The method that is used in the selected foreign currency revaluation job:</span></span>
    -   <span data-ttu-id="4cf31-139">**Padrão** – os trabalhos de reavaliação de moeda estrangeira são lançados independentemente de o resultado ser lucro ou perda.</span><span class="sxs-lookup"><span data-stu-id="4cf31-139">**Standard** – Foreign currency revaluation jobs are posted, regardless of whether the result is a profit or a loss.</span></span>
    -   <span data-ttu-id="4cf31-140">**Mínimo**– os trabalhos de reavaliação de moeda estrangeira só serão lançados se o resultado for uma perda.</span><span class="sxs-lookup"><span data-stu-id="4cf31-140">**Minimum** – Foreign currency revaluation jobs are posted only if the result is a loss.</span></span>
    -   <span data-ttu-id="4cf31-141">**Data da fatura** – os trabalhos de reavaliação de moeda estrangeira usam a taxa de câmbio original das transações, que são reavaliadas para seu valor original na moeda contábil.</span><span class="sxs-lookup"><span data-stu-id="4cf31-141">**Invoice date** – Foreign currency revaluation jobs use the original exchange rate of the transactions, which are revalued to their original value in the accounting currency.</span></span> <span data-ttu-id="4cf31-142">O efeito de qualquer reavaliação de moeda estrangeira prévia é cancelado.</span><span class="sxs-lookup"><span data-stu-id="4cf31-142">The effect of any prior foreign currency revaluation is canceled.</span></span>
-   <span data-ttu-id="4cf31-143">**Data considerada** – a data em que todas as transações que possuem valores em aberto (não liquidados) nessa data são encontradas.</span><span class="sxs-lookup"><span data-stu-id="4cf31-143">**Considered date** – The date when all transactions that have open (not settled) amounts on that date are found.</span></span> <span data-ttu-id="4cf31-144">Os valores de moeda estrangeira são reavaliados usando as taxas de câmbio inseridas na página **Taxas de câmbio de moeda** para a data considerada.</span><span class="sxs-lookup"><span data-stu-id="4cf31-144">Foreign currency amounts are revalued by using the exchange rates that are entered on the **Currency exchange rates** page for the considered date.</span></span> <span data-ttu-id="4cf31-145">Quando os valores de moeda estrangeira são reavaliados em uma data específica, essa data será a data da última de reavaliação em moeda estrangeira para as transações ajustadas.</span><span class="sxs-lookup"><span data-stu-id="4cf31-145">When foreign currency amounts are revalued on a considered date, this date becomes the last foreign currency revaluation date for the transactions that are adjusted.</span></span> <span data-ttu-id="4cf31-146">Se você decidir executar uma reavaliação de moeda estrangeira para uma data específica que seja anterior à data da última reavaliação de moeda estrangeira em transações que já tenham sido ajustadas, o trabalho periódico não ajustará as transações que estiverem em aberto na data específica anterior, mas que tiverem uma data mais recente para a reavaliação de moeda estrangeira não serão ajustadas pelo trabalho periódico.</span><span class="sxs-lookup"><span data-stu-id="4cf31-146">If you run foreign currency revaluation for a considered date that is earlier than the last foreign currency revaluation date on transactions that have already been adjusted, the periodic job doesn't adjust transactions that are open on the earlier considered date, but that have a more recent last foreign currency revaluation date.</span></span>
-   <span data-ttu-id="4cf31-147">**Data da taxa** – a data que determina a taxa de câmbio usada na reavaliação de moeda estrangeira.</span><span class="sxs-lookup"><span data-stu-id="4cf31-147">**Date of rate** – The date that determines the exchange rate that is used in the foreign currency revaluation.</span></span>
-   <span data-ttu-id="4cf31-148">**Usar o perfil de lançamentos de** – o perfil de lançamento usado para inserir a conta principal padrão para Contas a receber ou Contas a pagar para as entradas contábeis das transações de reavaliação de moeda estrangeira:</span><span class="sxs-lookup"><span data-stu-id="4cf31-148">**Use posting profile from** – The posting profile that is used to enter the default main account for Accounts receivable or Accounts payable for the accounting entries of the  foreign currency revaluation transactions:</span></span>
    -   <span data-ttu-id="4cf31-149">**Lançamento** – o perfil de lançamento da transação do cliente é usado.</span><span class="sxs-lookup"><span data-stu-id="4cf31-149">**Posting** – The posting profile of the customer transaction is used.</span></span>
    -   <span data-ttu-id="4cf31-150">**Selecionar** - insira o perfil de lançamento no campo **Perfil de lançamento**.</span><span class="sxs-lookup"><span data-stu-id="4cf31-150">**Select** – Enter the posting profile in the **Posting profile** field.</span></span>
-   <span data-ttu-id="4cf31-151">**Perfil de lançamento** – Se **Selecionar** estiver escolhido no campo **Usar perfil de lançamentos de**, o perfil de lançamento inserido nesse campo determinará o perfil de lançamento das transações de reavaliação de moeda estrangeira.</span><span class="sxs-lookup"><span data-stu-id="4cf31-151">**Posting profile** – If **Select** is selected in the **Use posting profile from** field, the posting profile that you enter in this field determines the posting profile of the foreign currency revaluation transactions.</span></span>
-   <span data-ttu-id="4cf31-152">**Dimensões financeiras** – as dimensões financeiras lançadas nas entradas contábeis das transações de reavaliação de moeda estrangeira:</span><span class="sxs-lookup"><span data-stu-id="4cf31-152">**Financial dimensions** – The financial dimensions that are posted on the accounting entries of the foreign currency revaluation transactions:</span></span>
    -   <span data-ttu-id="4cf31-153">**Nenhuma** – nenhuma dimensão financeira é lançada.</span><span class="sxs-lookup"><span data-stu-id="4cf31-153">**None** – No financial dimensions are posted.</span></span> <span data-ttu-id="4cf31-154">Se você tiver uma dimensão financeira exigida na estrutura da conta, o processo de reavaliação ainda será executado e criará as entradas contábeis sem dimensões financeiras.</span><span class="sxs-lookup"><span data-stu-id="4cf31-154">If you have a required financial dimension in your account structure, the revaluation process is still run and creates accounting entries that have no financial dimensions.</span></span> <span data-ttu-id="4cf31-155">Você receberá uma mensagem de aviso primeiro para depois poder cancelar a reavaliação.</span><span class="sxs-lookup"><span data-stu-id="4cf31-155">You will receive a warning message first, so that you can cancel the revaluation.</span></span>
    -   <span data-ttu-id="4cf31-156">**Tabela** – as dimensões financeiras da conta do cliente ou na conta do fornecedor são lançadas nas transações de reavaliação de moeda estrangeira.</span><span class="sxs-lookup"><span data-stu-id="4cf31-156">**Table** – The financial dimensions of the customer account or vendor account are posted on the foreign currency revaluation transactions.</span></span>
    -   <span data-ttu-id="4cf31-157">**Lançamento** – as dimensões financeiras da transação que estão sendo reavaliadas são lançadas nas transações de reavaliação de moeda estrangeira.</span><span class="sxs-lookup"><span data-stu-id="4cf31-157">**Posting** – The financial dimensions of the transaction that is being revalued are posted on the foreign currency revaluation transactions.</span></span> <span data-ttu-id="4cf31-158">Por padrão, as dimensões financeiras da conta contábil AR/AP da transação original serão usadas para a conta principal AR/AP da transação de reavaliação, e as dimensões financeiras da conta contábil de despesa/ativo/receita da transação original serão usadas para a conta principal de lucros/perdas não realizados da transação de reavaliação.</span><span class="sxs-lookup"><span data-stu-id="4cf31-158">By default, the financial dimensions from the original transaction's AR/AP ledger account will be used for the revaluation transaction's AR/AP main account, and the financial dimensions from the original transaction's expense/asset/revenue ledger account will be used for the revaluation transaction's unrealized gain/loss main account.</span></span>



