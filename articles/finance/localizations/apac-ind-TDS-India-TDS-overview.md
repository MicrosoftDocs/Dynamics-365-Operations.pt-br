---
title: Visão geral do Imposto Deduzido na Origem (TDS) da Índia
description: Este tópico fornece informações detalhadas sobre o Imposto Deduzido na Origem (TDS) da Índia. A documentação do TDS aborda a funcionalidade desse recurso.
author: kailiang
ms.date: 03/19/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-03-19
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 28ee843036e11bd37b97a065ce53d2eb860c79d9
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023041"
---
# <a name="indian-tax-deducted-at-source-tds-overview"></a><span data-ttu-id="f081b-104">Visão geral do Imposto Deduzido na Origem (TDS) da Índia</span><span class="sxs-lookup"><span data-stu-id="f081b-104">Indian Tax Deducted at Source (TDS) overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f081b-105">Este tópico fornece informações detalhadas sobre o Imposto Deduzido na Origem (TDS) da Índia.</span><span class="sxs-lookup"><span data-stu-id="f081b-105">This topic provides detailed information about Indian Tax Deducted at Source (TDS).</span></span>

<span data-ttu-id="f081b-106">A documentação do TDS aborda a funcionalidade desse recurso.</span><span class="sxs-lookup"><span data-stu-id="f081b-106">The TDS documentation covers the functionality of this capability.</span></span> <span data-ttu-id="f081b-107">Também explica como fazer a configuração básica do TDS, calcular o TDS nas transações, concluir o processo de liquidação do TDS, registrar os números dos certificados do TDS e gerar consultas do TDS, declarações do TDS e certificados do TDS.</span><span class="sxs-lookup"><span data-stu-id="f081b-107">It also explains how to do the basic setup for TDS, calculate TDS on transactions, complete the TDS settlement process, record TDS certificate numbers, and generate TDS inquiries, TDS statements, and TDS certificates.</span></span> <span data-ttu-id="f081b-108">A documentação inclui os seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="f081b-108">The documentation includes the following topics:</span></span>

- [<span data-ttu-id="f081b-109">Configuração básica do TDS</span><span class="sxs-lookup"><span data-stu-id="f081b-109">Basic setup for TDS</span></span>](apac-ind-TDS-TDS-ledger-accounts-setup.md)
- [<span data-ttu-id="f081b-110">Designer de fórmulas e funcionalidade de limite usada para cálculo do TDS</span><span class="sxs-lookup"><span data-stu-id="f081b-110">Formula designer and threshold limit functionality used for TDS calculation</span></span>](apac-ind-TDS-Formula-designer.md)
- [<span data-ttu-id="f081b-111">Cálculo do TDS em faturas, pagamentos, notas promissórias e transações entre empresas</span><span class="sxs-lookup"><span data-stu-id="f081b-111">Calculation of TDS on invoices, payments, promissory notes, and intercompany transactions</span></span>](apac-ind-TDS-Calculate-TDS-on-invoices-using-journals.md)
- [<span data-ttu-id="f081b-112">Processo de liquidação de TDS periódico e liquidação de valores de TDS para fornecedores de autoridade TDS</span><span class="sxs-lookup"><span data-stu-id="f081b-112">Periodic TDS settlement process and settlement of TDS amounts to TDS authority vendors</span></span>](apac-ind-TDS-Run-the-periodic-TDS-settlement-process.md)
- [<span data-ttu-id="f081b-113">Registro e atualização de números e datas de certificados de TDS</span><span class="sxs-lookup"><span data-stu-id="f081b-113">Recording and updating TDS certificate numbers and dates</span></span>](apac-ind-TDS-Record-TDS-concession-certificate-numbers.md)

## <a name="introduction-to-tds"></a><span data-ttu-id="f081b-114">Introdução ao TDS</span><span class="sxs-lookup"><span data-stu-id="f081b-114">Introduction to TDS</span></span>

<span data-ttu-id="f081b-115">De acordo com a Lei do Imposto de Renda de 1961, o imposto de renda é deduzido na fonte pelo destinatário do serviço no momento do pagamento antecipado ou da contabilidade do crédito, o que ocorrer primeiro.</span><span class="sxs-lookup"><span data-stu-id="f081b-115">Per the Income tax Act, 1961, income tax is deducted at the source by the receiver of the service at the time of advance payment or accounting of credit, whichever occurs first.</span></span> <span data-ttu-id="f081b-116">Quem efetua o pagamento deve deduzir o valor do imposto e pagar somente o saldo líquido ao prestador do serviço.</span><span class="sxs-lookup"><span data-stu-id="f081b-116">The person who makes the payment must deduct the tax amount and pay only the net balance to the provider of the service.</span></span> <span data-ttu-id="f081b-117">O TDS é aplicado em serviços que o governo especifica e o imposto é deduzido usando as taxas que o governo especifica para um período.</span><span class="sxs-lookup"><span data-stu-id="f081b-117">TDS is applied on services that the government specifies, and the tax is deducted by using the rates that the government specifies for a period.</span></span> <span data-ttu-id="f081b-118">A taxa de dedução é baseada no status da entidade que recebe o pagamento ou fornece o serviço.</span><span class="sxs-lookup"><span data-stu-id="f081b-118">The rate of deduction is based on the status of the entity that receives the payment or provides the service.</span></span> <span data-ttu-id="f081b-119">Os status incluem **Individual**, **Família indivisa hindu** (**HUF**), **Empresa**, **Firma**, **Associação de pessoas** (**AOP**), **Corpo de indivíduos** (**BOI**) e **Autoridade local**.</span><span class="sxs-lookup"><span data-stu-id="f081b-119">Statuses include **Individual**, **Hindu Undivided Family** (**HUF**), **Company**, **Firm**, **Association of Persons** (**AOP**), **Body of Individuals** (**BOI**), and **Local authority**.</span></span>

<span data-ttu-id="f081b-120">As seções a seguir listam os serviços aos quais o TDS é aplicado, conforme especificado pelo Governo da Índia.</span><span class="sxs-lookup"><span data-stu-id="f081b-120">The following sections list the services that TDS is applied on, as specified by the Government of India.</span></span>

<span data-ttu-id="f081b-121">**Residentes**</span><span class="sxs-lookup"><span data-stu-id="f081b-121">**Residents**</span></span>

- <span data-ttu-id="f081b-122">Renda de salários (na seção 192)</span><span class="sxs-lookup"><span data-stu-id="f081b-122">Income from salaries (Under section 192)</span></span>
- <span data-ttu-id="f081b-123">Renda de juros sobre valores (na seção 193)</span><span class="sxs-lookup"><span data-stu-id="f081b-123">Income from interest on securities (Under section 193)</span></span>
- <span data-ttu-id="f081b-124">Renda por dividendos (na seção 194)</span><span class="sxs-lookup"><span data-stu-id="f081b-124">Income from dividend (Under section 194)</span></span>
- <span data-ttu-id="f081b-125">Renda por juros (na seção 194A)</span><span class="sxs-lookup"><span data-stu-id="f081b-125">Income from interest (Under section 194A)</span></span>
- <span data-ttu-id="f081b-126">Renda por loterias ou jogos (na seção 194B)</span><span class="sxs-lookup"><span data-stu-id="f081b-126">Income from lotteries or puzzles (Under section 194B)</span></span>
- <span data-ttu-id="f081b-127">Ganhos com corridas de cavalos etc. (na seção 194BB)</span><span class="sxs-lookup"><span data-stu-id="f081b-127">Winning from horse races etc. (Under section 194BB)</span></span>
- <span data-ttu-id="f081b-128">Prestadores de serviço e subcontratados (na seção 194C)</span><span class="sxs-lookup"><span data-stu-id="f081b-128">Contractors and sub-contractors (Under section 194C)</span></span>
- <span data-ttu-id="f081b-129">Comissão de seguro (na seção 194D)</span><span class="sxs-lookup"><span data-stu-id="f081b-129">Insurance commission (Under section 194D)</span></span>
- <span data-ttu-id="f081b-130">Renda por depósito no esquema de poupança nacional (na seção 194EE)</span><span class="sxs-lookup"><span data-stu-id="f081b-130">Income from deposit under national saving scheme (Under section 194EE)</span></span>
- <span data-ttu-id="f081b-131">Renda por fundo mútuo ou UTI (na seção 194F)</span><span class="sxs-lookup"><span data-stu-id="f081b-131">Income from mutual fund or UTI (Under section 194F)</span></span>
- <span data-ttu-id="f081b-132">Comissão, remuneração, prêmio etc., à venda ou loteria (na seção 194G)</span><span class="sxs-lookup"><span data-stu-id="f081b-132">Commission, Remuneration, Prize etc., on sale or lottery (Under section 194G)</span></span>
- <span data-ttu-id="f081b-133">Pagamento de comissão ou corretora (na seção 194H)</span><span class="sxs-lookup"><span data-stu-id="f081b-133">Payment of Commission or brokerage (Under section 194H)</span></span>
- <span data-ttu-id="f081b-134">Aluguel (na seção 194I)</span><span class="sxs-lookup"><span data-stu-id="f081b-134">Rent (Under section 194I)</span></span>
- <span data-ttu-id="f081b-135">Serviço profissional (na seção 194J)</span><span class="sxs-lookup"><span data-stu-id="f081b-135">Professional service (Under section 194J)</span></span>
- <span data-ttu-id="f081b-136">Renda por unidades (na seção 194K)</span><span class="sxs-lookup"><span data-stu-id="f081b-136">Income from Units (Under section 194K)</span></span>
- <span data-ttu-id="f081b-137">Pagamento de compensação na aquisição de certos bens imóveis (na seção 194LA)</span><span class="sxs-lookup"><span data-stu-id="f081b-137">Payment of compensation on acquisition of certain immovable property (Under section 194LA)</span></span>

<span data-ttu-id="f081b-138">**Não residentes**</span><span class="sxs-lookup"><span data-stu-id="f081b-138">**Non-residents**</span></span>

- <span data-ttu-id="f081b-139">Pagamentos a esportistas não residentes ou associações esportivas (na secção 194E)</span><span class="sxs-lookup"><span data-stu-id="f081b-139">Payments to Non-resident sportsmen or sports association (Under section 194E)</span></span>
- <span data-ttu-id="f081b-140">Outras somas (na seção 195)</span><span class="sxs-lookup"><span data-stu-id="f081b-140">Other sums (Under section 195)</span></span>
- <span data-ttu-id="f081b-141">Renda em relação a unidades de não residentes (na seção 196A)</span><span class="sxs-lookup"><span data-stu-id="f081b-141">Income in respect of units of non-residents (Under section 196A)</span></span>

    - <span data-ttu-id="f081b-142">Renda por títulos em moeda estrangeira ou ações da empresa indiana (na seção 196C)</span><span class="sxs-lookup"><span data-stu-id="f081b-142">Income from foreign currency bonds or shares of Indian Company (Under section 196C)</span></span>
    - <span data-ttu-id="f081b-143">Receitas de investidores institucionais estrangeiros de valores (na seção 196D)</span><span class="sxs-lookup"><span data-stu-id="f081b-143">Incomes of foreign institutional investors from securities (Under section 196D)</span></span>
    - <span data-ttu-id="f081b-144">Salário e todas as outras rendas positivas em qualquer categoria de renda (na seção 192)</span><span class="sxs-lookup"><span data-stu-id="f081b-144">Salary and all other positive incomes under any head on income (Section 192)</span></span>
    - <span data-ttu-id="f081b-145">Juros sobre valores (na seção 193)</span><span class="sxs-lookup"><span data-stu-id="f081b-145">Interest on securities (Section 193)</span></span>
    - <span data-ttu-id="f081b-146">Juros que não sejam juros sobre valores (na seção 194A)</span><span class="sxs-lookup"><span data-stu-id="f081b-146">Interest other than interest on securities (Section 194A)</span></span>
    - <span data-ttu-id="f081b-147">Pagamentos a prestadores de serviço e subcontratados (na seção 194C)</span><span class="sxs-lookup"><span data-stu-id="f081b-147">Payments to contractors and sub-contractors (Section 194C)</span></span>
    - <span data-ttu-id="f081b-148">Ganhos com loteria ou palavras cruzadas (na seção 194B)</span><span class="sxs-lookup"><span data-stu-id="f081b-148">Winnings from Lottery or crossword puzzles (Section 194B)</span></span>
    - <span data-ttu-id="f081b-149">Ganhos com corridas de cavalos (na seção 194BB)</span><span class="sxs-lookup"><span data-stu-id="f081b-149">Winnings from horse races (Section 194BB)</span></span>
    - <span data-ttu-id="f081b-150">Comissão de seguros cobrindo todos os pagamentos para aquisição de negócios de seguros (na seção 194D)</span><span class="sxs-lookup"><span data-stu-id="f081b-150">Insurance Commission covering all payments for procuring Insurance business (Section 194D)</span></span>
    - <span data-ttu-id="f081b-151">Quaisquer juros, exceto juros sobre valores a pagar a não residentes que não sejam uma empresa ou a uma empresa estrangeira (na seção 195)</span><span class="sxs-lookup"><span data-stu-id="f081b-151">Any interest other than interest on securities payable to non-residents not being a company or to a foreign company (Section 195)</span></span>
    - <span data-ttu-id="f081b-152">Pagamento a esportista não residente, incluindo atleta ou associação ou instituição esportiva.</span><span class="sxs-lookup"><span data-stu-id="f081b-152">Payment to non-resident sportsman including athlete or sports association or institution.</span></span> <span data-ttu-id="f081b-153">No caso de esportista não residente, pagamentos relativos a anúncios, bem como artigos sobre qualquer jogo/esporte na Índia em jornais, revistas etc.</span><span class="sxs-lookup"><span data-stu-id="f081b-153">In case of non-resident sportsman, payments in respect of advertisements as well as articles on any game/sports in India in newspapers, magazines, and so.</span></span> <span data-ttu-id="f081b-154">está incluído (seção 194E)</span><span class="sxs-lookup"><span data-stu-id="f081b-154">is included (Section 194E)</span></span>
    - <span data-ttu-id="f081b-155">Pagamento em relação a depósitos no NSS \[esquema de poupança nacional\] (seção 194EE)</span><span class="sxs-lookup"><span data-stu-id="f081b-155">Payment in respect of deposits under NSS \[National Savings Scheme\] (Section 194EE)</span></span>
    - <span data-ttu-id="f081b-156">Pagamento por conta de recompra de unidades por fundo mútuo ou UTI (seção 194F)</span><span class="sxs-lookup"><span data-stu-id="f081b-156">Payment on account of repurchase of Units by Mutual Fund or UTI (Section 194F)</span></span>
    - <span data-ttu-id="f081b-157">Pagamento de comissão ou corretora (seção 194H)</span><span class="sxs-lookup"><span data-stu-id="f081b-157">Payment for Commission or brokerage (Section 194H)</span></span>
    - <span data-ttu-id="f081b-158">Pagamento de aluguel (seção 194I)</span><span class="sxs-lookup"><span data-stu-id="f081b-158">Payment of rent (Section 194I)</span></span>
    - <span data-ttu-id="f081b-159">Pagamento de taxas por serviços profissionais ou técnicos (seção 194J)</span><span class="sxs-lookup"><span data-stu-id="f081b-159">Payment of fees for professional or technical services (Section 194J)</span></span>
    - <span data-ttu-id="f081b-160">Comissão para Stockiest, distribuidores, compradores e vendedores de bilhetes de loteria, incluindo remuneração ou prêmio em tais bilhetes (seção 194G)</span><span class="sxs-lookup"><span data-stu-id="f081b-160">Commission to Stockiest, distributors, buyers and sellers of Lottery tickets including remuneration or prize on such tickets (Section 194G)</span></span>
    - <span data-ttu-id="f081b-161">Renda por unidades compradas em moeda estrangeira ou ganho de capital de longo prazo decorrente da transferência de tais unidades compradas em moeda estrangeira (seção 196B)</span><span class="sxs-lookup"><span data-stu-id="f081b-161">Income from Units purchased in foreign currency or long-term capital gain arising from the transfer of such Units purchased in foreign currency (Section 196B)</span></span>
    - <span data-ttu-id="f081b-162">Pagamento de qualquer renda a não residentes a respeito de juros ou dividendos sobre valores e ações (seção 196C)</span><span class="sxs-lookup"><span data-stu-id="f081b-162">Payment of any income to non-residents in respect of interest or dividend on bonds and shares (Section 196C)</span></span>

<span data-ttu-id="f081b-163">O TDS é calculado sobre compras, vendas, devoluções de vendas, notas de crédito, aquisições de ativos fixos, pré-pagamentos, pagamentos antecipados, notas promissórias, imposto de obra e transações entre empresas.</span><span class="sxs-lookup"><span data-stu-id="f081b-163">TDS is calculated on purchases, sales, sales returns, credit notes, fixed asset acquisitions, prepayments, advance payments, promissory notes, works tax, and intercompany transactions.</span></span>

> [!NOTE]
> <span data-ttu-id="f081b-164">No cenário fiscal atual da Índia, o TDS não é calculado sobre as transações de vendas.</span><span class="sxs-lookup"><span data-stu-id="f081b-164">In the current Indian tax scenario, TDS isn't calculated on sales transactions.</span></span> <span data-ttu-id="f081b-165">Contudo, o sistema inclui uma provisão para calcular o TDS recuperável em transações de vendas, especialmente para transações entre empresas.</span><span class="sxs-lookup"><span data-stu-id="f081b-165">However, the system includes a provision to calculate TDS recoverable on sales transactions, especially for intercompany transactions.</span></span>

<span data-ttu-id="f081b-166">O cálculo do TDS sempre considera o limite e o limite de exceção que são definidos para o componente TDS.</span><span class="sxs-lookup"><span data-stu-id="f081b-166">The calculation of TDS always considers the threshold and the exception threshold that are defined for the TDS component.</span></span>

<span data-ttu-id="f081b-167">O processo de liquidação de TDS periódico deve ser executado e os pagamentos de TDS devem ser liquidados para fornecedores de autoridade TDS.</span><span class="sxs-lookup"><span data-stu-id="f081b-167">The periodic TDS settlement process must be run, and the TDS payments must be settled to TDS authority vendors.</span></span>

<span data-ttu-id="f081b-168">Os números e datas dos certificados de TDS recebidos de fornecedores ou clientes podem ser registrados e atualizados.</span><span class="sxs-lookup"><span data-stu-id="f081b-168">The certificate numbers and dates for TDS certificates that are received from vendors or customers can be recorded and updated.</span></span> <span data-ttu-id="f081b-169">Além disso, as declarações trimestrais do Formulário 26Q e do Formulário 27Q e o certificado do Formulário 16A para TDS podem ser gerados no Finance.</span><span class="sxs-lookup"><span data-stu-id="f081b-169">Additionally, Form 26Q and Form 27Q quarterly statements, and the Form 16A certificate for TDS, can be generated in Finance.</span></span>

## <a name="setting-up-and-working-with-tds"></a><span data-ttu-id="f081b-170">Configuração e trabalho com TDS</span><span class="sxs-lookup"><span data-stu-id="f081b-170">Setting up and working with TDS</span></span>

<span data-ttu-id="f081b-171">Aqui está uma visão geral do processo para configurar e trabalhar com o TDS:</span><span class="sxs-lookup"><span data-stu-id="f081b-171">Here is an overview of the process for setting up and working with TDS:</span></span>

1. <span data-ttu-id="f081b-172">**Configuração de TDS:**</span><span class="sxs-lookup"><span data-stu-id="f081b-172">**TDS setup:**</span></span>

    - <span data-ttu-id="f081b-173">Configuração de parâmetros:</span><span class="sxs-lookup"><span data-stu-id="f081b-173">Parameter setup:</span></span>

        - <span data-ttu-id="f081b-174">Em Parâmetros da contabilidade, ative os parâmetros relacionados ao TDS.</span><span class="sxs-lookup"><span data-stu-id="f081b-174">In General ledger parameters, activate parameters that are related to TDS.</span></span>
        - <span data-ttu-id="f081b-175">Em Parâmetros da contabilidade, configure a sequência numérica para pagamentos de impostos retidos na fonte.</span><span class="sxs-lookup"><span data-stu-id="f081b-175">In General ledger parameters, set up the number sequence for withholding tax payments.</span></span>
        - <span data-ttu-id="f081b-176">Configure parâmetros em Contas a pagar e em Contas a receber.</span><span class="sxs-lookup"><span data-stu-id="f081b-176">Set up parameters in Accounts payable and Accounts receivable.</span></span>

    - <span data-ttu-id="f081b-177">Configuração básica:</span><span class="sxs-lookup"><span data-stu-id="f081b-177">Basic setup:</span></span>

        - <span data-ttu-id="f081b-178">Configure os números de registro do TDS para uma empresa, clientes e fornecedores.</span><span class="sxs-lookup"><span data-stu-id="f081b-178">Set up TDS registration numbers for a company, customers, and vendors.</span></span>
        - <span data-ttu-id="f081b-179">Configure grupos de componentes de TDS.</span><span class="sxs-lookup"><span data-stu-id="f081b-179">Set up TDS component groups.</span></span>
        - <span data-ttu-id="f081b-180">Configure os componentes do TDS, anexe grupos de componentes do TDS a eles e defina o limite e o limite de exceção para eles.</span><span class="sxs-lookup"><span data-stu-id="f081b-180">Set up TDS components, attach TDS component groups to them, and define the threshold and exception threshold for them.</span></span>
        - <span data-ttu-id="f081b-181">Configure autoridades TDS.</span><span class="sxs-lookup"><span data-stu-id="f081b-181">Set up TDS authorities.</span></span>
        - <span data-ttu-id="f081b-182">Configure os períodos de liquidação do TDS.</span><span class="sxs-lookup"><span data-stu-id="f081b-182">Set up TDS settlement periods.</span></span>
        - <span data-ttu-id="f081b-183">Configure os códigos de imposto do TDS e anexe os componentes do TDS a eles.</span><span class="sxs-lookup"><span data-stu-id="f081b-183">Set up TDS tax codes, and attach TDS components to them.</span></span>
        - <span data-ttu-id="f081b-184">Configure grupos de impostos TDS e anexe códigos de impostos TDS a eles.</span><span class="sxs-lookup"><span data-stu-id="f081b-184">Set up TDS tax groups, and attach TDS tax codes to them.</span></span>
        - <span data-ttu-id="f081b-185">No designer de fórmulas, defina uma fórmula para calcular o TDS para um grupo de TDS.</span><span class="sxs-lookup"><span data-stu-id="f081b-185">In the formula designer, define a formula to calculate TDS for a TDS group.</span></span>
        - <span data-ttu-id="f081b-186">Registre os números dos certificados de concessão de TDS.</span><span class="sxs-lookup"><span data-stu-id="f081b-186">Record TDS concession certificate numbers.</span></span>

    - <span data-ttu-id="f081b-187">Contas contábeis e configuração da empresa:</span><span class="sxs-lookup"><span data-stu-id="f081b-187">Ledger accounts and company setup:</span></span>

        - <span data-ttu-id="f081b-188">Configure contas contábeis a pagar e a receber de TDS.</span><span class="sxs-lookup"><span data-stu-id="f081b-188">Set up TDS payable and receivable ledger accounts.</span></span>
        - <span data-ttu-id="f081b-189">Configure um número de conta de cobrança e dedução de imposto (TAN) e uma categoria de tipo de dedutor para a empresa.</span><span class="sxs-lookup"><span data-stu-id="f081b-189">Set up a Tax Deduction and Collection Account Number (TAN) and a deductor type category for the company.</span></span>

    - <span data-ttu-id="f081b-190">Outra configuração:</span><span class="sxs-lookup"><span data-stu-id="f081b-190">Other setup:</span></span>

        - <span data-ttu-id="f081b-191">Configure uma programação de pagamento que inclua a alocação de TDS.</span><span class="sxs-lookup"><span data-stu-id="f081b-191">Set up a payment schedule that includes TDS allocation.</span></span>
        - <span data-ttu-id="f081b-192">Configure um tipo de taxa de pagamento para pagamentos à autoridade TDS.</span><span class="sxs-lookup"><span data-stu-id="f081b-192">Set up a payment fee type for payments to the TDS authority.</span></span>
        - <span data-ttu-id="f081b-193">Configure informações sobre grupos TDS, números de contas permanentes (PANs) e TANs para fornecedores e clientes.</span><span class="sxs-lookup"><span data-stu-id="f081b-193">Set up information about TDS groups, permanent account numbers (PANs), and TANs for vendors and customers.</span></span>

2. <span data-ttu-id="f081b-194">**Cálculo do TDS nas transações:**</span><span class="sxs-lookup"><span data-stu-id="f081b-194">**Calculation of TDS in transactions:**</span></span>

    - <span data-ttu-id="f081b-195">Faturas e pagamentos</span><span class="sxs-lookup"><span data-stu-id="f081b-195">Invoices and payments</span></span>
    - <span data-ttu-id="f081b-196">Notas Promissórias</span><span class="sxs-lookup"><span data-stu-id="f081b-196">Promissory notes</span></span>
    - <span data-ttu-id="f081b-197">Pagamentos antecipados</span><span class="sxs-lookup"><span data-stu-id="f081b-197">Advance payments</span></span>
    - <span data-ttu-id="f081b-198">Pagamentos Antecipados</span><span class="sxs-lookup"><span data-stu-id="f081b-198">Prepayments</span></span>

3. <span data-ttu-id="f081b-199">**Liquidação de TDS:**</span><span class="sxs-lookup"><span data-stu-id="f081b-199">**TDS settlement:**</span></span>

    - <span data-ttu-id="f081b-200">Processo de liquidação de TDS periódico</span><span class="sxs-lookup"><span data-stu-id="f081b-200">Periodic TDS settlement process</span></span>
    - <span data-ttu-id="f081b-201">Liquidação de pagamentos de TDS para fornecedores da autoridade TDS e criação de challan TDS</span><span class="sxs-lookup"><span data-stu-id="f081b-201">Settlement of TDS payments to TDS authority vendors and generation of TDS challan</span></span>

4. <span data-ttu-id="f081b-202">**Consultas, declarações e certificado de TDS:**</span><span class="sxs-lookup"><span data-stu-id="f081b-202">**TDS inquiries, statements, and certificate:**</span></span>

    - <span data-ttu-id="f081b-203">Registre e atualize os números e datas dos certificados de TDS.</span><span class="sxs-lookup"><span data-stu-id="f081b-203">Record and update TDS certificate numbers and dates.</span></span>
    - <span data-ttu-id="f081b-204">Gere uma consulta de TDS e uma consulta de TDS publicada.</span><span class="sxs-lookup"><span data-stu-id="f081b-204">Generate a TDS inquiry and a posted TDS inquiry.</span></span>
    - <span data-ttu-id="f081b-205">Gere o Formulário 27A, o Formulário 26Q e o Formulário 27Q TDS e extratos trimestrais do e-TDS.</span><span class="sxs-lookup"><span data-stu-id="f081b-205">Generate Form 27A, Form 26Q, and Form 27Q TDS and e-TDS quarterly statements.</span></span>
    - <span data-ttu-id="f081b-206">Gere um certificado Formulário 16A TDS.</span><span class="sxs-lookup"><span data-stu-id="f081b-206">Generate a Form 16A TDS certificate.</span></span>
