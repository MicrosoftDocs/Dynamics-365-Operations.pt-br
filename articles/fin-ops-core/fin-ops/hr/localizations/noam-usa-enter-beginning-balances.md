---
title: Inserir saldos iniciais de folha de pagamento
description: Este tópico descreve as etapas para inserir saldos iniciais para códigos de ganhos, deduções, benefícios e impostos. Essas informações são importantes para que os Parceiros migrem ou transfiram dados de outro sistema para uma nova implementação de folha de pagamento.
author: kherr75
manager: AnnBe
ms.date: 04/24/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 20931
ms.assetid: b48b1cb2-6e66-467e-9c0e-09b6a4aeb9fe
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2017-07-01
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4cab844e190140d2c3b605c9a1490d33a6f383ee
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2176530"
---
# <a name="enter-payroll-beginning-balances"></a><span data-ttu-id="0f674-104">Inserir saldos iniciais de folha de pagamento</span><span class="sxs-lookup"><span data-stu-id="0f674-104">Enter payroll beginning balances</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="0f674-105">Este tópico descreve as etapas para inserir saldos iniciais para códigos de ganhos, deduções, benefícios e impostos.</span><span class="sxs-lookup"><span data-stu-id="0f674-105">The topic describes the steps for entering beginning balances for earning codes, deductions, benefits, and taxes.</span></span> <span data-ttu-id="0f674-106">Essas informações são importantes para parceiros que transferem dados de outro sistema para uma nova implementação de folha de pagamento.</span><span class="sxs-lookup"><span data-stu-id="0f674-106">This information is valuable for partners who transfer data for a new Payroll implementation from another system.</span></span> <span data-ttu-id="0f674-107">Para se preparar para inserir saldos iniciais de folha de pagamento, nós verificamos as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="0f674-107">To prepare to enter beginning payroll balances, we verify the following information:</span></span>

- <span data-ttu-id="0f674-108">Os registros de funcionários são inseridos e estão disponíveis no sistema</span><span class="sxs-lookup"><span data-stu-id="0f674-108">Employee records are entered and available in the system</span></span>
- <span data-ttu-id="0f674-109">Os dados a seguir estão configurados e atribuídos aos funcionários:</span><span class="sxs-lookup"><span data-stu-id="0f674-109">The following data is set up and assigned to employees:</span></span>

    - <span data-ttu-id="0f674-110">Ciclos de pagamento e períodos de pagamento</span><span class="sxs-lookup"><span data-stu-id="0f674-110">Pay cycles and pay periods</span></span>
    - <span data-ttu-id="0f674-111">Códigos de ganhos</span><span class="sxs-lookup"><span data-stu-id="0f674-111">Earning codes</span></span>
    - <span data-ttu-id="0f674-112">Impostos</span><span class="sxs-lookup"><span data-stu-id="0f674-112">Taxes</span></span>
    - <span data-ttu-id="0f674-113">Benefícios e Deduções</span><span class="sxs-lookup"><span data-stu-id="0f674-113">Benefits and deductions</span></span>

- <span data-ttu-id="0f674-114">A empresa deve ter escolhido uma data em que os saldos iniciais de folha de pagamento podem ser definidos.</span><span class="sxs-lookup"><span data-stu-id="0f674-114">The company should have chosen a date where payroll beginning balances can be set.</span></span>
- <span data-ttu-id="0f674-115">As informações foram coletadas sobre todos os ganhos, benefícios/deduções, contribuições de benefícios, impostos de funcionários e impostos de empregadores, bem como os seus valores acumulados no ano referente ao sistema herdado.</span><span class="sxs-lookup"><span data-stu-id="0f674-115">Information were gathered on all earnings, benefits/deductions, benefit contributions, employee taxes, and employer taxes and their YTD amounts from the legacy system.</span></span>

<span data-ttu-id="0f674-116">Na medida em que você planeja inserir os saldos iniciais, considere a forma como os dados precisam ser detalhados.</span><span class="sxs-lookup"><span data-stu-id="0f674-116">As you plan to enter beginning balances, consider how detailed the data needs to be.</span></span> <span data-ttu-id="0f674-117">A maioria das empresas insere um valor acumulado único e consolidado.</span><span class="sxs-lookup"><span data-stu-id="0f674-117">Most businesses enter a single, consolidated year-to-date amount.</span></span> <span data-ttu-id="0f674-118">Entretanto caso seja necessário informações mais detalhadas, os saldos podem ser inseridos em incrementos trimestrais.</span><span class="sxs-lookup"><span data-stu-id="0f674-118">However if more detailed information is needed, balances can be entered in quarterly increments.</span></span> <span data-ttu-id="0f674-119">Decidir o nível de detalhes necessário determina quantos demonstrativos manuais de pagamento devem ser criados para cada trabalhador.</span><span class="sxs-lookup"><span data-stu-id="0f674-119">Deciding the level of detail that's needed determines how many manual pay statements must be created for each worker.</span></span> <span data-ttu-id="0f674-120">Para um único valor acumulado, somente um demonstrativo manual é necessário para cada funcionário.</span><span class="sxs-lookup"><span data-stu-id="0f674-120">For a single year-to-date amount, only one manual statement is needed for each employee.</span></span> <span data-ttu-id="0f674-121">Para isso, use os valores acumulados do demonstrativo de pagamento final do sistema anterior como o valor inserido no novo sistema de folha de pagamento.</span><span class="sxs-lookup"><span data-stu-id="0f674-121">To do this use year-to-date amounts from the final pay statement from the previous system as the amount entered in the new payroll system.</span></span>

<span data-ttu-id="0f674-122">O exemplo a seguir mostra como você pode inserir os saldos iniciais da folha de pagamento dos funcionários, incluindo códigos de ganhos, benefícios/deduções e impostos.</span><span class="sxs-lookup"><span data-stu-id="0f674-122">The following example shows how you can enter employee payroll beginning balances, including earning codes, benefits/deductions, and taxes.</span></span> <span data-ttu-id="0f674-123">Em um exemplo do mundo real, você teria um item de linha para cada código de ganhos, dedução de benefícios, contribuição para benefícios, imposto de funcionário e imposto de empregador, sendo o valor inserido o valor acumulado no ano.</span><span class="sxs-lookup"><span data-stu-id="0f674-123">In a real-world example you would have a line item for each earning code, benefit deduction, benefit contribution, employee tax and employer tax with the amount entered being the year-to-date amount.</span></span> <span data-ttu-id="0f674-124">Usando a lista de códigos e valores, siga as etapas para criar um demonstrativo manual de ganhos e pagamentos com contabilidade desabilitada para obter saldos iniciais para fins de folha de pagamento.</span><span class="sxs-lookup"><span data-stu-id="0f674-124">Using that list of codes and amounts, follow the steps for creating a manual earning and pay statement with accounting disabled to bring over beginning balances for payroll purposes.</span></span> <span data-ttu-id="0f674-125">Você desabilita a contabilidade por não desejar lançar esse demonstrativo de pagamento inicial na contabilidade.</span><span class="sxs-lookup"><span data-stu-id="0f674-125">You disable accounting because you won't want to post this beginning balance pay statement to your general ledger.</span></span> <span data-ttu-id="0f674-126">Isso foi feito no sistema herdado e virá para o novo sistema quando você definir os saldos iniciais na contabilidade.</span><span class="sxs-lookup"><span data-stu-id="0f674-126">That was done in the legacy system and will come over to the new system when you set beginning balances in General ledger.</span></span>

### <a name="a-how-to-set-up-earnings-codes-to-be-used-on-payroll-beginning-balances"></a><span data-ttu-id="0f674-127">A.</span><span class="sxs-lookup"><span data-stu-id="0f674-127">A.</span></span> <span data-ttu-id="0f674-128">Como configurar códigos de ganhos a serem usados nos saldos iniciais de folha de pagamento</span><span class="sxs-lookup"><span data-stu-id="0f674-128">How to set up earnings codes to be used on payroll beginning balances</span></span>

<span data-ttu-id="0f674-129">Ao inserir os saldos iniciais de folha de pagamento, certifique-se de que os códigos de ganhos que serão utilizados estão configurados com a opção “Permitir edição das taxas do demonstrativo de ganhos" habilitada.</span><span class="sxs-lookup"><span data-stu-id="0f674-129">When you enter payroll beginning balances, be sure the earning codes that you will be using are configured with the "Allow editing of earning statement rates" option enabled.</span></span> <span data-ttu-id="0f674-130">Isso permitirá que você digite manualmente o valor do sistema herdado.</span><span class="sxs-lookup"><span data-stu-id="0f674-130">This will allow you to manually key the amount from the legacy system.</span></span> 

### <a name="b-create-earnings-statement-for-an-employee-to-have-a-beginning-balance"></a><span data-ttu-id="0f674-131">B.</span><span class="sxs-lookup"><span data-stu-id="0f674-131">B.</span></span> <span data-ttu-id="0f674-132">Criar demonstrativo de ganhos para que um funcionário tenha um saldo inicial</span><span class="sxs-lookup"><span data-stu-id="0f674-132">Create earnings statement for an employee to have a beginning balance</span></span>

<span data-ttu-id="0f674-133">Esta etapa cria manualmente um demonstrativo de ganhos para cada trabalhador pelo último período de pagamento do sistema herdado, o que cria as linhas de demonstrativo de ganhos no novo sistema de folha de pagamento.</span><span class="sxs-lookup"><span data-stu-id="0f674-133">This step manually creates an earnings statement for each worker for the last pay period of the legacy system, which creates the earning statement lines in the new payroll system.</span></span> <span data-ttu-id="0f674-134">Insira uma linha por código de ganhos e o valor e as horas acumulados no ano.</span><span class="sxs-lookup"><span data-stu-id="0f674-134">Enter one line per earning code and the YTD amount and hours.</span></span> <span data-ttu-id="0f674-135">As etapas de amostra são as seguintes:</span><span class="sxs-lookup"><span data-stu-id="0f674-135">The sample steps are as follows:</span></span>

1. <span data-ttu-id="0f674-136">Abra a página **Todos os demonstrativos de ganhos** e clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="0f674-136">Open the **All earnings statements** page and click **New**.</span></span>

    <span data-ttu-id="0f674-137">Insira os itens a seguir:</span><span class="sxs-lookup"><span data-stu-id="0f674-137">Enter the following:</span></span> 

    | <span data-ttu-id="0f674-138">Campo</span><span class="sxs-lookup"><span data-stu-id="0f674-138">Field</span></span>      | <span data-ttu-id="0f674-139">Alíquota</span><span class="sxs-lookup"><span data-stu-id="0f674-139">Value</span></span>                 |
    |------------|-----------------------|
    | <span data-ttu-id="0f674-140">Trabalhador</span><span class="sxs-lookup"><span data-stu-id="0f674-140">Worker</span></span>     | <span data-ttu-id="0f674-141">Michael Redmond</span><span class="sxs-lookup"><span data-stu-id="0f674-141">Michael Redmond</span></span>       |
    | <span data-ttu-id="0f674-142">Ciclo de pagamento</span><span class="sxs-lookup"><span data-stu-id="0f674-142">Pay cycle</span></span>  | <span data-ttu-id="0f674-143">sm</span><span class="sxs-lookup"><span data-stu-id="0f674-143">sm</span></span>                    |
    | <span data-ttu-id="0f674-144">Período de pagamento</span><span class="sxs-lookup"><span data-stu-id="0f674-144">Pay period</span></span> | <span data-ttu-id="0f674-145">16/6/2017 - 30/6/2017</span><span class="sxs-lookup"><span data-stu-id="0f674-145">6/16/2017 - 6/30/2017</span></span> |

2. <span data-ttu-id="0f674-146">Na guia **Linha do demonstrativo de ganhos**, insira o seguinte:</span><span class="sxs-lookup"><span data-stu-id="0f674-146">In the **Earnings statement line** tab, enter the following:</span></span>

    <span data-ttu-id="0f674-147">Linha 1: guia **Linha do demonstrativo de ganhos**</span><span class="sxs-lookup"><span data-stu-id="0f674-147">Line 1: **Earning statement line** tab</span></span>

    | <span data-ttu-id="0f674-148">Campo</span><span class="sxs-lookup"><span data-stu-id="0f674-148">Field</span></span>            | <span data-ttu-id="0f674-149">Alíquota</span><span class="sxs-lookup"><span data-stu-id="0f674-149">Value</span></span>       |
    |------------------|-------------|
    | <span data-ttu-id="0f674-150">Código de ganhos</span><span class="sxs-lookup"><span data-stu-id="0f674-150">Earnings code</span></span>    | <span data-ttu-id="0f674-151">Pagamento regular</span><span class="sxs-lookup"><span data-stu-id="0f674-151">Regular pay</span></span> |
    | <span data-ttu-id="0f674-152">Quantidade</span><span class="sxs-lookup"><span data-stu-id="0f674-152">Quantity</span></span>         | <span data-ttu-id="0f674-153">1.00</span><span class="sxs-lookup"><span data-stu-id="0f674-153">1.00</span></span>        |
    | <span data-ttu-id="0f674-154">Taxa</span><span class="sxs-lookup"><span data-stu-id="0f674-154">Rate</span></span>             | <span data-ttu-id="0f674-155">30,000</span><span class="sxs-lookup"><span data-stu-id="0f674-155">30,000</span></span>      |
    | <span data-ttu-id="0f674-156">Guia Detalhes da linha</span><span class="sxs-lookup"><span data-stu-id="0f674-156">Line details tab</span></span> |             |
    | <span data-ttu-id="0f674-157">Manual</span><span class="sxs-lookup"><span data-stu-id="0f674-157">Manual</span></span>           | <span data-ttu-id="0f674-158">(marcado)</span><span class="sxs-lookup"><span data-stu-id="0f674-158">(marked)</span></span>    |

    <span data-ttu-id="0f674-159">Linha 2: guia **Linha do demonstrativo de ganhos**</span><span class="sxs-lookup"><span data-stu-id="0f674-159">Line 2: **Earning statement line** tab</span></span>

    | <span data-ttu-id="0f674-160">Campo</span><span class="sxs-lookup"><span data-stu-id="0f674-160">Field</span></span>            | <span data-ttu-id="0f674-161">Alíquota</span><span class="sxs-lookup"><span data-stu-id="0f674-161">Value</span></span>    |
    |------------------|----------|
    | <span data-ttu-id="0f674-162">Código de ganhos</span><span class="sxs-lookup"><span data-stu-id="0f674-162">Earnings code</span></span>    | <span data-ttu-id="0f674-163">Bônus</span><span class="sxs-lookup"><span data-stu-id="0f674-163">Bonus</span></span>    |
    | <span data-ttu-id="0f674-164">Quantidade</span><span class="sxs-lookup"><span data-stu-id="0f674-164">Quantity</span></span>         | <span data-ttu-id="0f674-165">1.0000</span><span class="sxs-lookup"><span data-stu-id="0f674-165">1.0000</span></span>   |
    | <span data-ttu-id="0f674-166">Taxa</span><span class="sxs-lookup"><span data-stu-id="0f674-166">Rate</span></span>             | <span data-ttu-id="0f674-167">4250.00</span><span class="sxs-lookup"><span data-stu-id="0f674-167">4250.00</span></span>  |
    | <span data-ttu-id="0f674-168">Guia Detalhes da linha</span><span class="sxs-lookup"><span data-stu-id="0f674-168">Line details tab</span></span> |          |
    | <span data-ttu-id="0f674-169">Manual</span><span class="sxs-lookup"><span data-stu-id="0f674-169">Manual</span></span>           | <span data-ttu-id="0f674-170">(marcado)</span><span class="sxs-lookup"><span data-stu-id="0f674-170">(marked)</span></span> |

    <span data-ttu-id="0f674-171">Linha 3: guia **Linha do demonstrativo de ganhos**</span><span class="sxs-lookup"><span data-stu-id="0f674-171">Line 3: **Earning statement line** tab</span></span>

    | <span data-ttu-id="0f674-172">Campo</span><span class="sxs-lookup"><span data-stu-id="0f674-172">Field</span></span>           | <span data-ttu-id="0f674-173">Alíquota</span><span class="sxs-lookup"><span data-stu-id="0f674-173">Value</span></span>      |
    |-----------------|------------|
    | <span data-ttu-id="0f674-174">Código de ganhos</span><span class="sxs-lookup"><span data-stu-id="0f674-174">Earnings code</span></span>   | <span data-ttu-id="0f674-175">Comissão</span><span class="sxs-lookup"><span data-stu-id="0f674-175">Commission</span></span> |
    | <span data-ttu-id="0f674-176">Quantidade</span><span class="sxs-lookup"><span data-stu-id="0f674-176">Quantity</span></span>        | <span data-ttu-id="0f674-177">1.0000</span><span class="sxs-lookup"><span data-stu-id="0f674-177">1.0000</span></span>     |
    | <span data-ttu-id="0f674-178">Taxa</span><span class="sxs-lookup"><span data-stu-id="0f674-178">Rate</span></span>            | <span data-ttu-id="0f674-179">!,299,00</span><span class="sxs-lookup"><span data-stu-id="0f674-179">!,299.00</span></span>   |
    | <span data-ttu-id="0f674-180">Taxa</span><span class="sxs-lookup"><span data-stu-id="0f674-180">Rate</span></span>            | <span data-ttu-id="0f674-181">1.299,00</span><span class="sxs-lookup"><span data-stu-id="0f674-181">1,299.00</span></span>   |
    | <span data-ttu-id="0f674-182">Guia Detalhe da linha</span><span class="sxs-lookup"><span data-stu-id="0f674-182">Line detail tab</span></span> |            |
    | <span data-ttu-id="0f674-183">Manual</span><span class="sxs-lookup"><span data-stu-id="0f674-183">Manual</span></span>          | <span data-ttu-id="0f674-184">(Marcado)</span><span class="sxs-lookup"><span data-stu-id="0f674-184">(Marked)</span></span>   |

    > [!NOTE]
    > <span data-ttu-id="0f674-185">A configuração do controle deslizante **Manual** como **Sim** na guia **Detalhes da Linha** para cada linha de declaração de ganhos é fundamental para a inserção dos saldos iniciais de folha de pagamento para cada trabalhador.</span><span class="sxs-lookup"><span data-stu-id="0f674-185">Setting the **Manual** slider to **Yes** in the **Line Details** tab for each earnings statement line is key to have payroll beginning balances entered for each worker.</span></span>

3. <span data-ttu-id="0f674-186">No painel **Ação**, clique em **Liberar demonstrativo de ganhos** USA-FED-ER-FICA.</span><span class="sxs-lookup"><span data-stu-id="0f674-186">On the **Action** pane, click **Release earnings statement** USA-FED-ER-FICA.</span></span>
4. <span data-ttu-id="0f674-187">No painel **Ação**, clique em **Demonstrativo de pagamento** para abrir a página **Gerar demonstrativos de pagamento** e definir o seguinte:</span><span class="sxs-lookup"><span data-stu-id="0f674-187">On the **Action** pane click **Pay statement** to open the **Generate pay statements** page and set the following:</span></span>

    | <span data-ttu-id="0f674-188">Campo</span><span class="sxs-lookup"><span data-stu-id="0f674-188">Field</span></span>              | <span data-ttu-id="0f674-189">Alíquota</span><span class="sxs-lookup"><span data-stu-id="0f674-189">Value</span></span>     |
    |--------------------|-----------|
    | <span data-ttu-id="0f674-190">Data de pagamento</span><span class="sxs-lookup"><span data-stu-id="0f674-190">Payment date</span></span>       | <span data-ttu-id="0f674-191">30/6/2017</span><span class="sxs-lookup"><span data-stu-id="0f674-191">6/30/2017</span></span> |
    | <span data-ttu-id="0f674-192">Tipo de execução de pagamento</span><span class="sxs-lookup"><span data-stu-id="0f674-192">Payment run type</span></span>   | <span data-ttu-id="0f674-193">Manual</span><span class="sxs-lookup"><span data-stu-id="0f674-193">Manual</span></span>    |
    | <span data-ttu-id="0f674-194">Desabilitar contabilidade</span><span class="sxs-lookup"><span data-stu-id="0f674-194">Disable accounting</span></span> |   <span data-ttu-id="0f674-195">Sim</span><span class="sxs-lookup"><span data-stu-id="0f674-195">Yes</span></span>     |

    > [!NOTE] 
    > <span data-ttu-id="0f674-196">Isso só está disponível quando o tipo de execução de pagamento é manual e o usuário deseja desabilitar a contabilidade na execução de pagamento</span><span class="sxs-lookup"><span data-stu-id="0f674-196">This is only available when the payment run type is manual and wherein the user want to disable accounting on the pay run.</span></span>

    <span data-ttu-id="0f674-197">Clique em **OK** e feche o **Log de Informações**.</span><span class="sxs-lookup"><span data-stu-id="0f674-197">Click **OK** and close the **Infolog**.</span></span>

#### <a name="why-the-disable-accounting-slider-needs-to-set-to-yes-when-generating-pay-statements"></a><span data-ttu-id="0f674-198">Por que o controle deslizante Desabilitar Contabilidade precisa estar definido como Sim durante a geração de demonstrativos de pagamento?</span><span class="sxs-lookup"><span data-stu-id="0f674-198">Why the Disable Accounting slider needs to set to Yes when generating pay statements?</span></span>

<span data-ttu-id="0f674-199">A configuração do controle deslizante como **Sim** impede que as linhas do demonstrativo de pagamento sejam distribuídas na Contabilidade.</span><span class="sxs-lookup"><span data-stu-id="0f674-199">Setting the slider to **Yes** prevents lines in the pay statement from being districuted to General ledger.</span></span> <span data-ttu-id="0f674-200">Os valores da contabilidade eram atualizados antes da inserção dos saldos de conta do sistema herdado.</span><span class="sxs-lookup"><span data-stu-id="0f674-200">General ledger amounts were updating earlier when account balances from the legacy system were entered.</span></span> <span data-ttu-id="0f674-201">A inserção dos saldos iniciais na Folha de pagamento permite gerar relatórios que incluem informações de anos anteriores, bem como para identificar limites para fins de benefício e de imposto.</span><span class="sxs-lookup"><span data-stu-id="0f674-201">Entering beginning balances for Payroll lets you generate reports that include information from prior years, as well as for identifying limits for benefit and tax purposes.</span></span>

### <a name="c-create-pay-statements-for-employees"></a><span data-ttu-id="0f674-202">C.</span><span class="sxs-lookup"><span data-stu-id="0f674-202">C.</span></span> <span data-ttu-id="0f674-203">Gerar demonstrativos de pagamento para funcionários</span><span class="sxs-lookup"><span data-stu-id="0f674-203">Create pay statements for employees</span></span>

<span data-ttu-id="0f674-204">Depois de gerar demonstrativos de pagamento com saldos iniciais, você deve verificar se os demonstrativos de pagamento refletem com precisão os dados da folha de pagamento.</span><span class="sxs-lookup"><span data-stu-id="0f674-204">After you generate pay statements that have beginning balances, you must verify that the pay statements accurately reflect payroll data.</span></span> <span data-ttu-id="0f674-205">Você também deve atualizar manualmente as informações de benefícios e impostos para correspondam aos valores no sistema de folha de pagamento anterior.</span><span class="sxs-lookup"><span data-stu-id="0f674-205">You must also manually update the benefit and taxes information to match the values in the previous payroll system.</span></span> <span data-ttu-id="0f674-206">Depois de verificar que os valores do sistema de folha de pagamento anterior correspondem aos valores dos demonstrativos de pagamento atuais, você deve finalizar os demonstrativos de pagamento.</span><span class="sxs-lookup"><span data-stu-id="0f674-206">After you verify that the amounts from the previous payroll system match the amounts on the current pay statements, you must finalize the pay statements.</span></span>

1. <span data-ttu-id="0f674-207">Abra a página **Todos os demonstrativos de pagamento**.</span><span class="sxs-lookup"><span data-stu-id="0f674-207">Open the **All pay statements** page.</span></span>
2. <span data-ttu-id="0f674-208">Destaque o último demonstrativo de pagamento gerado para Michael Redmond</span><span class="sxs-lookup"><span data-stu-id="0f674-208">Highlight the last generated pay statement for Michael Redmond</span></span>
3. <span data-ttu-id="0f674-209">Clique em **Editar** para abrir a página **Demonstrativo de pagamento**.</span><span class="sxs-lookup"><span data-stu-id="0f674-209">Click **Edit** to open the **Pay statement** page.</span></span>
4. <span data-ttu-id="0f674-210">Abra a guia **Deduções de benefício** e insira o seguinte:</span><span class="sxs-lookup"><span data-stu-id="0f674-210">Open the **Benefit deductions** tab and enter the following:</span></span>

    | <span data-ttu-id="0f674-211">Campo</span><span class="sxs-lookup"><span data-stu-id="0f674-211">Field</span></span>             | <span data-ttu-id="0f674-212">Alíquota</span><span class="sxs-lookup"><span data-stu-id="0f674-212">Value</span></span>            |
    |-------------------|------------------|
    | <span data-ttu-id="0f674-213">Benefício</span><span class="sxs-lookup"><span data-stu-id="0f674-213">Benefit</span></span>           | <span data-ttu-id="0f674-214">Valor da dedução</span><span class="sxs-lookup"><span data-stu-id="0f674-214">Deduction amount</span></span> |
    | <span data-ttu-id="0f674-215">401K</span><span class="sxs-lookup"><span data-stu-id="0f674-215">401K</span></span>              | <span data-ttu-id="0f674-216">Participar</span><span class="sxs-lookup"><span data-stu-id="0f674-216">Participate</span></span>      |
    | <span data-ttu-id="0f674-217">Plano odontológico</span><span class="sxs-lookup"><span data-stu-id="0f674-217">Dental</span></span>            | <span data-ttu-id="0f674-218">SubSp</span><span class="sxs-lookup"><span data-stu-id="0f674-218">SubSp</span></span>            |
    | <span data-ttu-id="0f674-219">Despesas com o dependente</span><span class="sxs-lookup"><span data-stu-id="0f674-219">Dep care spending</span></span> | <span data-ttu-id="0f674-220">Participar</span><span class="sxs-lookup"><span data-stu-id="0f674-220">Participate</span></span>      |
    | <span data-ttu-id="0f674-221">Visão</span><span class="sxs-lookup"><span data-stu-id="0f674-221">Vision</span></span>            | <span data-ttu-id="0f674-222">SupSp</span><span class="sxs-lookup"><span data-stu-id="0f674-222">SupSp</span></span>            |

5. <span data-ttu-id="0f674-223">Na guia **Contribuições para benefícios**, insira o seguinte:</span><span class="sxs-lookup"><span data-stu-id="0f674-223">In the **Benefit contributions** tab and enter the following:</span></span>

    | <span data-ttu-id="0f674-224">Campo</span><span class="sxs-lookup"><span data-stu-id="0f674-224">Field</span></span>   | <span data-ttu-id="0f674-225">Alíquota</span><span class="sxs-lookup"><span data-stu-id="0f674-225">Value</span></span>               |
    |---------|---------------------|
    | <span data-ttu-id="0f674-226">Benefício</span><span class="sxs-lookup"><span data-stu-id="0f674-226">Benefit</span></span> | <span data-ttu-id="0f674-227">Valor de contribuição</span><span class="sxs-lookup"><span data-stu-id="0f674-227">Contribution amount</span></span> |
    | <span data-ttu-id="0f674-228">401K</span><span class="sxs-lookup"><span data-stu-id="0f674-228">401K</span></span>    | <span data-ttu-id="0f674-229">Participar</span><span class="sxs-lookup"><span data-stu-id="0f674-229">Participate</span></span>         |
    | <span data-ttu-id="0f674-230">Plano odontológico</span><span class="sxs-lookup"><span data-stu-id="0f674-230">Dental</span></span>  | <span data-ttu-id="0f674-231">SubSp</span><span class="sxs-lookup"><span data-stu-id="0f674-231">SubSp</span></span>               |
    | <span data-ttu-id="0f674-232">Visão</span><span class="sxs-lookup"><span data-stu-id="0f674-232">Vision</span></span>  | <span data-ttu-id="0f674-233">SubSp</span><span class="sxs-lookup"><span data-stu-id="0f674-233">SubSp</span></span>               |

6. <span data-ttu-id="0f674-234">Na guia **Deduções de imposto**, insira o seguinte:</span><span class="sxs-lookup"><span data-stu-id="0f674-234">In the **Tax deductions** tab, enter the following:</span></span>

    | <span data-ttu-id="0f674-235">Campo</span><span class="sxs-lookup"><span data-stu-id="0f674-235">Field</span></span>           | <span data-ttu-id="0f674-236">Alíquota</span><span class="sxs-lookup"><span data-stu-id="0f674-236">Value</span></span>            |
    |-----------------|------------------|
    | <span data-ttu-id="0f674-237">Código do Imposto</span><span class="sxs-lookup"><span data-stu-id="0f674-237">Tax code</span></span>        | <span data-ttu-id="0f674-238">Valor da dedução</span><span class="sxs-lookup"><span data-stu-id="0f674-238">Deduction amount</span></span> |
    | <span data-ttu-id="0f674-239">USA-FED-ER-FICA</span><span class="sxs-lookup"><span data-stu-id="0f674-239">USA-FED-ER-FICA</span></span> | <span data-ttu-id="0f674-240">1600.00</span><span class="sxs-lookup"><span data-stu-id="0f674-240">1600.00</span></span>          |
    | <span data-ttu-id="0f674-241">USA-FED-ER-MEDI</span><span class="sxs-lookup"><span data-stu-id="0f674-241">USA-FED-ER-MEDI</span></span> | <span data-ttu-id="0f674-242">825.75</span><span class="sxs-lookup"><span data-stu-id="0f674-242">825.75</span></span>           |

7. <span data-ttu-id="0f674-243">Na guia **Contribuições de imposto**, insira o seguinte:</span><span class="sxs-lookup"><span data-stu-id="0f674-243">In the **Tax contributions** tab enter the following:</span></span>
8. <span data-ttu-id="0f674-244">Clique em **Calcular**.</span><span class="sxs-lookup"><span data-stu-id="0f674-244">Click **Calculate**.</span></span>

    > [!IMPORTANT] 
    > <span data-ttu-id="0f674-245">Valide os totais do demonstrativo de pagamento ao trabalhador correspondentes ao acumulado do sistema herdado.</span><span class="sxs-lookup"><span data-stu-id="0f674-245">Validate the totals of the pay statement that they match the YTD of the legacy system for the worker.</span></span> <span data-ttu-id="0f674-246">Você pode querer adiar a finalização na próxima etapa para fazer uma validação geral de todos os demonstrativos de pagamento acumulados.</span><span class="sxs-lookup"><span data-stu-id="0f674-246">You may want to hold off on finalizing in the next step to do some overall validating of all pay statements in aggregate.</span></span> <span data-ttu-id="0f674-247">Após a validação, reexamine todos os demonstrativos de pagamento e faça a finalização.</span><span class="sxs-lookup"><span data-stu-id="0f674-247">Once validated run through all the pay statements and finalize them.</span></span>

<span data-ttu-id="0f674-248">O mesmo processo pode ser feito em incrementos trimestrais, se necessário, para os trimestres anteriores de cada ano.</span><span class="sxs-lookup"><span data-stu-id="0f674-248">The same process can be done in quarter increments if necessary for all prior quarters in each year.</span></span> <span data-ttu-id="0f674-249">Isso só é necessário se o cliente precisar conferir os dados por trimestre sem retornar ao sistema herdado.</span><span class="sxs-lookup"><span data-stu-id="0f674-249">This is only needed if the customer needs to see the data by quarter without going back to the legacy system.</span></span>

## <a name="if-you-make-a-mistake-entering-beginning-balances-for-an-employee"></a><span data-ttu-id="0f674-250">Se você cometer um erro ao inserir saldos iniciais para um funcionário</span><span class="sxs-lookup"><span data-stu-id="0f674-250">If you make a mistake Entering Beginning Balances for an Employee</span></span>

<span data-ttu-id="0f674-251">É possível reverter e inserir novamente as transações.</span><span class="sxs-lookup"><span data-stu-id="0f674-251">It is possible to reverse and reenter transactions.</span></span> <span data-ttu-id="0f674-252">Para reverter a transação, tudo o que deve fazer é concluir as etapas a seguir na página **Todos os demonstrativos de pagamento**.</span><span class="sxs-lookup"><span data-stu-id="0f674-252">To reverse the transaction, all you have to do is to complete the follow steps on the **All pay statements** page.</span></span>

1. <span data-ttu-id="0f674-253">Clique em **Reverter**.</span><span class="sxs-lookup"><span data-stu-id="0f674-253">Click **Reverse**.</span></span>
2. <span data-ttu-id="0f674-254">Clique em **Sim** quando a mensagem “Quando você reverte este demonstrativo de pagamento, uma reversão de demonstrativo de pagamento é criada para compensar este demonstrativo de pagamento.</span><span class="sxs-lookup"><span data-stu-id="0f674-254">Click **Yes** when the message "When you reverse this pay statement, a reversing pay statement will be created to offset this pay statement.</span></span> <span data-ttu-id="0f674-255">Não é possível editar os demonstrativos de pagamento.</span><span class="sxs-lookup"><span data-stu-id="0f674-255">Neither pay statement can be edited.</span></span> <span data-ttu-id="0f674-256">Deseja reverter este demonstrativo de pagamento?”</span><span class="sxs-lookup"><span data-stu-id="0f674-256">Do you want to reverse this pay statement?"</span></span> <span data-ttu-id="0f674-257">for exibida.</span><span class="sxs-lookup"><span data-stu-id="0f674-257">displays.</span></span> 

<span data-ttu-id="0f674-258">Depois de reverter o demonstrativo de pagamento, você poderá gerar um novo demonstrativo de pagamento para o trabalhador a partir da declaração de ganhos criada anteriormente.</span><span class="sxs-lookup"><span data-stu-id="0f674-258">After you reverse the pay statement, you can generate a new pay statement for the worker from the earnings statement that you created previously.</span></span> <span data-ttu-id="0f674-259">Corrija qualquer linha incorreta na declaração de ganhos antes de gerar o novo demonstrativo de pagamento e então gere novos demonstrativos de pagamento com os valores corretos.</span><span class="sxs-lookup"><span data-stu-id="0f674-259">Be sure to fix any incorrect lines on the earnings statement before you generate the new pay statement, and then generate new pay statements with the correct amounts.</span></span> 