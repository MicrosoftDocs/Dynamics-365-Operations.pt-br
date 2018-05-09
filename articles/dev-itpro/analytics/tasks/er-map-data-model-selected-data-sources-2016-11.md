--- 
title: "Mapear um modelo de dados para fontes de dados selecionadas para relatório eletrônico (ER)"
description: "As etapas a seguir explicam como um usuário na função de Administrador do Sistema ou Desenvolvedor de Relatórios Eletrônicos pode mapear um modelo de dados de ER a fontes de dados selecionadas do Dynamics 365 for Finance and Operations, Enterprise edition (novembro, 2016)."
author: NickSelin
manager: AnnBe
ms.date: 01/16/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 2881a3cb27a3be4778c9edd4c8a01f9cbcd79f63
ms.contentlocale: pt-br
ms.lasthandoff: 05/08/2018

---
# <a name="map-a-data-model-to-selected-data-sources-for-electronic-reporting-er"></a><span data-ttu-id="8bea3-103">Mapear um modelo de dados para fontes de dados selecionadas para relatório eletrônico (ER)</span><span class="sxs-lookup"><span data-stu-id="8bea3-103">Map a data model to selected data sources for electronic reporting (ER)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="8bea3-104">As etapas a seguir explicam como um usuário na função de Administrador do Sistema ou Desenvolvedor de Relatórios Eletrônicos pode mapear um modelo de dados de ER a fontes de dados selecionadas do Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="8bea3-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can map an Electronic reporting (ER) data model to selected Dynamics 365 for Finance and Operations data sources.</span></span> <span data-ttu-id="8bea3-105">Esse mapeamento de modelo será usado posteriormente como uma fonte de dados em uma configuração de formato que será usada para gerenciar documentos de pagamento eletrônico.</span><span class="sxs-lookup"><span data-stu-id="8bea3-105">This model mapping will later be used as a data source in a format configuration that will be used to manage electronic payment documents.</span></span> <span data-ttu-id="8bea3-106">Neste exemplo, você mapeia um modelo de dados para a empresa exemplo, Litware, Inc., em fontes de dados.</span><span class="sxs-lookup"><span data-stu-id="8bea3-106">In this example, you map a data model for sample company, Litware, Inc. to data sources.</span></span> <span data-ttu-id="8bea3-107">Para concluir essas etapas, você deve primeiro concluir as etapas do procedimento 'Selecionar fontes de dados para mapeamento de modelo'.</span><span class="sxs-lookup"><span data-stu-id="8bea3-107">To complete these steps, you must first complete the steps in the “Select data sources for model mapping” procedure.</span></span>


## <a name="open-er-configurations-tree"></a><span data-ttu-id="8bea3-108">Abra a árvore de Configurações de ER</span><span class="sxs-lookup"><span data-stu-id="8bea3-108">Open ER configurations tree</span></span>
1. <span data-ttu-id="8bea3-109">Ir para Administração da organização > Espaços de trabalho > Relatório eletrônico.</span><span class="sxs-lookup"><span data-stu-id="8bea3-109">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="8bea3-110">Clique em Configurações.</span><span class="sxs-lookup"><span data-stu-id="8bea3-110">Click Configurations.</span></span>

## <a name="select-created-model-mapping"></a><span data-ttu-id="8bea3-111">Selecione o mapeamento de modelo criado</span><span class="sxs-lookup"><span data-stu-id="8bea3-111">Select created model mapping</span></span>
1. <span data-ttu-id="8bea3-112">Na árvore, selecione 'Pagamentos (modelo simplificado)'.</span><span class="sxs-lookup"><span data-stu-id="8bea3-112">In the tree, select 'Payments (simplified model)'.</span></span>
    * <span data-ttu-id="8bea3-113">Verifique se a configuração do modelo “Pagamentos (modelo simplificado)“ foi criada antecipadamente.</span><span class="sxs-lookup"><span data-stu-id="8bea3-113">Make sure that the model configuration “Payments (simplified model)” has been created in advance.</span></span> <span data-ttu-id="8bea3-114">Caso contrário, pare agora e retorne após a conclusão da guia de tarefas "Criar uma nova configuração com modelo de dados do domínio selecionado"</span><span class="sxs-lookup"><span data-stu-id="8bea3-114">Otherwise, stop now and return after completion of the task guide ‘Create a new configuration with data model of the selected domain’.</span></span>  
2. <span data-ttu-id="8bea3-115">Clique em Designer de modelo.</span><span class="sxs-lookup"><span data-stu-id="8bea3-115">Click Model designer.</span></span>
3. <span data-ttu-id="8bea3-116">Clique em Mapear modelo para fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="8bea3-116">Click Map model to datasource.</span></span>
4. <span data-ttu-id="8bea3-117">Selecione o registro de 'Mapeamento CT'.</span><span class="sxs-lookup"><span data-stu-id="8bea3-117">Select the 'CT mapping' record.</span></span>
    * <span data-ttu-id="8bea3-118">Mapeamento do CT</span><span class="sxs-lookup"><span data-stu-id="8bea3-118">CT mapping</span></span>  

## <a name="bind-created-data-sources-to-data-model-elements"></a><span data-ttu-id="8bea3-119">Associe fontes de dados criadas a elementos do modelo de dados</span><span class="sxs-lookup"><span data-stu-id="8bea3-119">Bind created data sources to data model elements</span></span>
1. <span data-ttu-id="8bea3-120">Clique em Designer.</span><span class="sxs-lookup"><span data-stu-id="8bea3-120">Click Designer.</span></span>
2. <span data-ttu-id="8bea3-121">Na árvore, selecione 'Data e hora de processamento(ProcessingDateTime)'.</span><span class="sxs-lookup"><span data-stu-id="8bea3-121">In the tree, select 'Processing date & time(ProcessingDateTime)'.</span></span>
3. <span data-ttu-id="8bea3-122">Na árvore, selecione 'Data de processamento(DataHoraProcessamento)'.</span><span class="sxs-lookup"><span data-stu-id="8bea3-122">In the tree, select 'Processing date(ProcessingDateTime)'.</span></span>
4. <span data-ttu-id="8bea3-123">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="8bea3-123">Click Bind.</span></span>
5. <span data-ttu-id="8bea3-124">Na árvore, selecione 'Identificação de mensagem de pagamento(IdentificaçãoMensagem)'.</span><span class="sxs-lookup"><span data-stu-id="8bea3-124">In the tree, select 'Payment message identification(MessageIdentification)'.</span></span>
6. <span data-ttu-id="8bea3-125">Na árvore, expanda 'Transações'.</span><span class="sxs-lookup"><span data-stu-id="8bea3-125">In the tree, expand 'Transactions'.</span></span>
7. <span data-ttu-id="8bea3-126">Na árvore, selecione 'Transações\Número do lote do diário(JournalNum)'.</span><span class="sxs-lookup"><span data-stu-id="8bea3-126">In the tree, select 'Transactions\Journal batch number(JournalNum)'.</span></span>
8. <span data-ttu-id="8bea3-127">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="8bea3-127">Click Bind.</span></span>
9. <span data-ttu-id="8bea3-128">Na árvore, selecione 'Pagamentos'.</span><span class="sxs-lookup"><span data-stu-id="8bea3-128">In the tree, select 'Payments'.</span></span>
10. <span data-ttu-id="8bea3-129">Na árvore, selecione 'Transações'.</span><span class="sxs-lookup"><span data-stu-id="8bea3-129">In the tree, select 'Transactions'.</span></span>
11. <span data-ttu-id="8bea3-130">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="8bea3-130">Click Bind.</span></span>
12. <span data-ttu-id="8bea3-131">Na árvore, expanda 'Pagamentos = Transações'.</span><span class="sxs-lookup"><span data-stu-id="8bea3-131">In the tree, expand 'Payments= Transactions'.</span></span>
13. <span data-ttu-id="8bea3-132">Na árvore, expanda 'Pagamentos = Transações\Credor'.</span><span class="sxs-lookup"><span data-stu-id="8bea3-132">In the tree, expand 'Payments= Transactions\Creditor'.</span></span>
14. <span data-ttu-id="8bea3-133">Na árvore, expanda 'Pagamentos = Transações\Credor\Conta'.</span><span class="sxs-lookup"><span data-stu-id="8bea3-133">In the tree, expand 'Payments= Transactions\Creditor\Account'.</span></span>
15. <span data-ttu-id="8bea3-134">Na árvore, selecione 'Pagamentos = Transações\Credor\Conta\Código de moeda(Currency)'.</span><span class="sxs-lookup"><span data-stu-id="8bea3-134">In the tree, select 'Payments= Transactions\Creditor\Account\Currency code(Currency)'.</span></span>
16. <span data-ttu-id="8bea3-135">Na árvore, expanda 'Transações\vendBankAccountInTransactionCompany()'.</span><span class="sxs-lookup"><span data-stu-id="8bea3-135">In the tree, expand 'Transactions\vendBankAccountInTransactionCompany()'.</span></span>
17. <span data-ttu-id="8bea3-136">Na árvore, selecione 'Transações\vendBankAccountInTransactionCompany()\Moeda(CurrencyCode)'.</span><span class="sxs-lookup"><span data-stu-id="8bea3-136">In the tree, select 'Transactions\vendBankAccountInTransactionCompany()\Currency(CurrencyCode)'.</span></span>
18. <span data-ttu-id="8bea3-137">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="8bea3-137">Click Bind.</span></span>
19. <span data-ttu-id="8bea3-138">Na árvore, selecione 'Pagamentos = Transações\Credor\Conta\Código IBAN(IBAN)'.</span><span class="sxs-lookup"><span data-stu-id="8bea3-138">In the tree, select 'Payments= Transactions\Creditor\Account\IBAN code(IBAN)'.</span></span>
20. <span data-ttu-id="8bea3-139">Na árvore, selecione 'Transações\vendBankAccountInTransactionCompany()\IBAN(BankIBAN)'.</span><span class="sxs-lookup"><span data-stu-id="8bea3-139">In the tree, select 'Transactions\vendBankAccountInTransactionCompany()\IBAN(BankIBAN)'.</span></span>
21. <span data-ttu-id="8bea3-140">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="8bea3-140">Click Bind.</span></span>
22. <span data-ttu-id="8bea3-141">Na árvore, selecione 'Pagamentos = Transações\Credor\Conta\Número'.</span><span class="sxs-lookup"><span data-stu-id="8bea3-141">In the tree, select 'Payments= Transactions\Creditor\Account\Number'.</span></span>
23. <span data-ttu-id="8bea3-142">Na árvore, selecione 'Transações\vendBankAccountInTransactionCompany()\Número da conta bancária(AccountNum)'.</span><span class="sxs-lookup"><span data-stu-id="8bea3-142">In the tree, select 'Transactions\vendBankAccountInTransactionCompany()\Bank account number(AccountNum)'.</span></span>
24. <span data-ttu-id="8bea3-143">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="8bea3-143">Click Bind.</span></span>
25. <span data-ttu-id="8bea3-144">Na árvore, expanda 'Pagamentos = Transações\Credor\Agente'.</span><span class="sxs-lookup"><span data-stu-id="8bea3-144">In the tree, expand 'Payments= Transactions\Creditor\Agent'.</span></span>
26. <span data-ttu-id="8bea3-145">Na árvore, selecione 'Pagamentos = Transações\Credor\Agente\Nome'.</span><span class="sxs-lookup"><span data-stu-id="8bea3-145">In the tree, select 'Payments= Transactions\Creditor\Agent\Name'.</span></span>
27. <span data-ttu-id="8bea3-146">Na árvore, selecione 'Transações\vendBankAccountInTransactionCompany()\Nome'.</span><span class="sxs-lookup"><span data-stu-id="8bea3-146">In the tree, select 'Transactions\vendBankAccountInTransactionCompany()\Name'.</span></span>
28. <span data-ttu-id="8bea3-147">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="8bea3-147">Click Bind.</span></span>
29. <span data-ttu-id="8bea3-148">Na árvore, selecione 'Pagamentos = Transações\Credor\Agente\Número do banco(RoutingNumber)'.</span><span class="sxs-lookup"><span data-stu-id="8bea3-148">In the tree, select 'Payments= Transactions\Creditor\Agent\Routing number(RoutingNumber)'.</span></span>
30. <span data-ttu-id="8bea3-149">Na árvore, selecione 'Transações\vendBankAccountInTransactionCompany()\Número do banco(RegistrationNum)'.</span><span class="sxs-lookup"><span data-stu-id="8bea3-149">In the tree, select 'Transactions\vendBankAccountInTransactionCompany()\Routing number(RegistrationNum)'.</span></span>
31. <span data-ttu-id="8bea3-150">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="8bea3-150">Click Bind.</span></span>
32. <span data-ttu-id="8bea3-151">Na árvore, selecione 'Pagamentos = Transações\Credor\Agente\Código SWIFT(SWIFT)'.</span><span class="sxs-lookup"><span data-stu-id="8bea3-151">In the tree, select 'Payments= Transactions\Creditor\Agent\SWIFT code(SWIFT)'.</span></span>
33. <span data-ttu-id="8bea3-152">Na árvore, selecione 'Transações\vendBankAccountInTransactionCompany()\Código SWIFT(SWIFTNo)'.</span><span class="sxs-lookup"><span data-stu-id="8bea3-152">In the tree, select 'Transactions\vendBankAccountInTransactionCompany()\SWIFT code(SWIFTNo)'.</span></span>
34. <span data-ttu-id="8bea3-153">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="8bea3-153">Click Bind.</span></span>
35. <span data-ttu-id="8bea3-154">Na árvore, selecione 'Pagamentos = Transações\Credor\Nome'.</span><span class="sxs-lookup"><span data-stu-id="8bea3-154">In the tree, select 'Payments= Transactions\Creditor\Name'.</span></span>
36. <span data-ttu-id="8bea3-155">Na árvore, expanda 'Transações\fingVendTable()'.</span><span class="sxs-lookup"><span data-stu-id="8bea3-155">In the tree, expand 'Transactions\findVendTable()'.</span></span>
37. <span data-ttu-id="8bea3-156">Na árvore, selecione 'Transactions\findVendTable()\name()'.</span><span class="sxs-lookup"><span data-stu-id="8bea3-156">In the tree, select 'Transactions\findVendTable()\name()'.</span></span>
38. <span data-ttu-id="8bea3-157">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="8bea3-157">Click Bind.</span></span>
39. <span data-ttu-id="8bea3-158">Na árvore, selecione 'Pagamentos = Transações\Código de moeda(Currency)'.</span><span class="sxs-lookup"><span data-stu-id="8bea3-158">In the tree, select 'Payments= Transactions\Currency code(Currency)'.</span></span>
40. <span data-ttu-id="8bea3-159">Na árvore, expanda 'Transações\>Relações'.</span><span class="sxs-lookup"><span data-stu-id="8bea3-159">In the tree, expand 'Transactions\>Relations'.</span></span>
41. <span data-ttu-id="8bea3-160">Na árvore, expanda 'Transações\>Relações\Tabela de moedas(Currency)'.</span><span class="sxs-lookup"><span data-stu-id="8bea3-160">In the tree, expand 'Transactions\>Relations\Currency table(Currency)'.</span></span>
42. <span data-ttu-id="8bea3-161">Na árvore, selecione 'Transações\>Relações\Tabela de moedas(Currency)\Código de moeda(CurrencyCodeISO)'.</span><span class="sxs-lookup"><span data-stu-id="8bea3-161">In the tree, select 'Transactions\>Relations\Currency table(Currency)\Currency code(CurrencyCodeISO)'.</span></span>
43. <span data-ttu-id="8bea3-162">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="8bea3-162">Click Bind.</span></span>
44. <span data-ttu-id="8bea3-163">Na árvore, expanda 'Pagamentos = Transações\Devedor'.</span><span class="sxs-lookup"><span data-stu-id="8bea3-163">In the tree, expand 'Payments= Transactions\Debtor'.</span></span>
45. <span data-ttu-id="8bea3-164">Na árvore, expanda 'Pagamentos = Transações\Devedor\Conta'.</span><span class="sxs-lookup"><span data-stu-id="8bea3-164">In the tree, expand 'Payments= Transactions\Debtor\Account'.</span></span>
46. <span data-ttu-id="8bea3-165">Na árvore, selecione 'Pagamentos = Transações\Devedor\Conta\Código de moeda(Currency)'.</span><span class="sxs-lookup"><span data-stu-id="8bea3-165">In the tree, select 'Payments= Transactions\Debtor\Account\Currency code(Currency)'.</span></span>
47. <span data-ttu-id="8bea3-166">Na árvore, selecione 'Conta Bancária(BankAccount)'.</span><span class="sxs-lookup"><span data-stu-id="8bea3-166">In the tree, select 'Bank Account(BankAccount)'.</span></span>
48. <span data-ttu-id="8bea3-167">Na árvore, expanda 'Conta Bancária(BankAccount)'.</span><span class="sxs-lookup"><span data-stu-id="8bea3-167">In the tree, expand 'Bank Account(BankAccount)'.</span></span>
49. <span data-ttu-id="8bea3-168">Na árvore, selecione 'Conta Bancária(BankAccount)\Moeda(CurrencyCode)'.</span><span class="sxs-lookup"><span data-stu-id="8bea3-168">In the tree, select 'Bank Account(BankAccount)\Currency(CurrencyCode)'.</span></span>
50. <span data-ttu-id="8bea3-169">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="8bea3-169">Click Bind.</span></span>
51. <span data-ttu-id="8bea3-170">Na árvore, selecione 'Conta Bancária(BankAccount)\IBAN'.</span><span class="sxs-lookup"><span data-stu-id="8bea3-170">In the tree, select 'Bank Account(BankAccount)\IBAN'.</span></span>
52. <span data-ttu-id="8bea3-171">Na árvore, selecione 'Pagamentos = Transações\Devedor\Conta\Código IBAN(IBAN)'.</span><span class="sxs-lookup"><span data-stu-id="8bea3-171">In the tree, select 'Payments= Transactions\Debtor\Account\IBAN code(IBAN)'.</span></span>
53. <span data-ttu-id="8bea3-172">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="8bea3-172">Click Bind.</span></span>
54. <span data-ttu-id="8bea3-173">Na árvore, selecione 'Pagamentos = Transações\Devedor\Conta\Número'.</span><span class="sxs-lookup"><span data-stu-id="8bea3-173">In the tree, select 'Payments= Transactions\Debtor\Account\Number'.</span></span>
55. <span data-ttu-id="8bea3-174">Na árvore, selecione 'Conta Bancária(BankAccount)\Número da conta bancária(AccountNum)'.</span><span class="sxs-lookup"><span data-stu-id="8bea3-174">In the tree, select 'Bank Account(BankAccount)\Bank account number(AccountNum)'.</span></span>
56. <span data-ttu-id="8bea3-175">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="8bea3-175">Click Bind.</span></span>
57. <span data-ttu-id="8bea3-176">Na árvore, expanda 'Pagamentos = Transações\Devedor\Agente'.</span><span class="sxs-lookup"><span data-stu-id="8bea3-176">In the tree, expand 'Payments= Transactions\Debtor\Agent'.</span></span>
58. <span data-ttu-id="8bea3-177">Na árvore, selecione 'Pagamentos = Transações\Devedor\Agente\Nome'.</span><span class="sxs-lookup"><span data-stu-id="8bea3-177">In the tree, select 'Payments= Transactions\Debtor\Agent\Name'.</span></span>
59. <span data-ttu-id="8bea3-178">Na árvore, selecione 'Conta Bancária(BankAccount)\Nome'.</span><span class="sxs-lookup"><span data-stu-id="8bea3-178">In the tree, select 'Bank Account(BankAccount)\Name'.</span></span>
60. <span data-ttu-id="8bea3-179">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="8bea3-179">Click Bind.</span></span>
61. <span data-ttu-id="8bea3-180">Na árvore, selecione 'Pagamentos = Transações\Devedor\Agente\Número do banco(RoutingNumber)'.</span><span class="sxs-lookup"><span data-stu-id="8bea3-180">In the tree, select 'Payments= Transactions\Debtor\Agent\Routing number(RoutingNumber)'.</span></span>
62. <span data-ttu-id="8bea3-181">Na árvore, selecione 'Conta Bancária(BankAccount)\Número do banco(RegistrationNum)'.</span><span class="sxs-lookup"><span data-stu-id="8bea3-181">In the tree, select 'Bank Account(BankAccount)\Routing number(RegistrationNum)'.</span></span>
63. <span data-ttu-id="8bea3-182">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="8bea3-182">Click Bind.</span></span>
64. <span data-ttu-id="8bea3-183">Na árvore, selecione 'Pagamentos = Transações\Devedor\Agente\Código SWIFT(SWIFT)'.</span><span class="sxs-lookup"><span data-stu-id="8bea3-183">In the tree, select 'Payments= Transactions\Debtor\Agent\SWIFT code(SWIFT)'.</span></span>
65. <span data-ttu-id="8bea3-184">Na árvore, selecione 'Conta Bancária(BankAccount)\Código SWIFT(SWIFTNo)'.</span><span class="sxs-lookup"><span data-stu-id="8bea3-184">In the tree, select 'Bank Account(BankAccount)\SWIFT code(SWIFTNo)'.</span></span>
66. <span data-ttu-id="8bea3-185">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="8bea3-185">Click Bind.</span></span>
67. <span data-ttu-id="8bea3-186">Na árvore, selecione 'Pagamentos = Transações\Devedor\Nome'.</span><span class="sxs-lookup"><span data-stu-id="8bea3-186">In the tree, select 'Payments= Transactions\Debtor\Name'.</span></span>
68. <span data-ttu-id="8bea3-187">Na árvore, selecione 'Informações da empresa(Company)'.</span><span class="sxs-lookup"><span data-stu-id="8bea3-187">In the tree, select 'Company information(Company)'.</span></span>
69. <span data-ttu-id="8bea3-188">Na árvore, expanda 'Informações da empresa(Company)'.</span><span class="sxs-lookup"><span data-stu-id="8bea3-188">In the tree, expand 'Company information(Company)'.</span></span>
70. <span data-ttu-id="8bea3-189">Na árvore, selecione 'Informações da empresa(Company)\Nome'.</span><span class="sxs-lookup"><span data-stu-id="8bea3-189">In the tree, select 'Company information(Company)\Name'.</span></span>
71. <span data-ttu-id="8bea3-190">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="8bea3-190">Click Bind.</span></span>
72. <span data-ttu-id="8bea3-191">Na árvore, selecione 'Pagamentos = Transações\Descrição'.</span><span class="sxs-lookup"><span data-stu-id="8bea3-191">In the tree, select 'Payments= Transactions\Description'.</span></span>
73. <span data-ttu-id="8bea3-192">Na árvore, selecione 'Transações\Descrição(Txt)'.</span><span class="sxs-lookup"><span data-stu-id="8bea3-192">In the tree, select 'Transactions\Description(Txt)'.</span></span>
74. <span data-ttu-id="8bea3-193">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="8bea3-193">Click Bind.</span></span>
75. <span data-ttu-id="8bea3-194">Na árvore, selecione 'Pagamentos = Transações\Código de identificação ponto a ponto(End2EndID)'.</span><span class="sxs-lookup"><span data-stu-id="8bea3-194">In the tree, select 'Payments= Transactions\End to end identification code(End2EndID)'.</span></span>
76. <span data-ttu-id="8bea3-195">Na árvore, selecione 'Transações\$EndToEndID'.</span><span class="sxs-lookup"><span data-stu-id="8bea3-195">In the tree, select 'Transactions\$EndToEndID'.</span></span>
77. <span data-ttu-id="8bea3-196">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="8bea3-196">Click Bind.</span></span>
78. <span data-ttu-id="8bea3-197">Na árvore, selecione 'Pagamentos = Transações\Valor instruído(InstructedAmount)'.</span><span class="sxs-lookup"><span data-stu-id="8bea3-197">In the tree, select 'Payments= Transactions\Instructed amount(InstructedAmount)'.</span></span>
79. <span data-ttu-id="8bea3-198">Na árvore, selecione "Transações\$Valor".</span><span class="sxs-lookup"><span data-stu-id="8bea3-198">In the tree, select 'Transactions\$Amount'.</span></span>
80. <span data-ttu-id="8bea3-199">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="8bea3-199">Click Bind.</span></span>
81. <span data-ttu-id="8bea3-200">Na árvore, selecione 'Pagamentos = Transações\Data da transação(TransactionDate)'.</span><span class="sxs-lookup"><span data-stu-id="8bea3-200">In the tree, select 'Payments= Transactions\Transaction date(TransactionDate)'.</span></span>
82. <span data-ttu-id="8bea3-201">Na árvore, selecione 'Transações\Data(TransDate)'.</span><span class="sxs-lookup"><span data-stu-id="8bea3-201">In the tree, select 'Transactions\Date(TransDate)'.</span></span>
83. <span data-ttu-id="8bea3-202">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="8bea3-202">Click Bind.</span></span>

## <a name="validate-created-mapping"></a><span data-ttu-id="8bea3-203">Valide o mapeamento criado</span><span class="sxs-lookup"><span data-stu-id="8bea3-203">Validate created mapping</span></span>
1. <span data-ttu-id="8bea3-204">Clique em Validar.</span><span class="sxs-lookup"><span data-stu-id="8bea3-204">Click Validate.</span></span>
    * <span data-ttu-id="8bea3-205">Valide o novo mapeamento para garantir que todas as associações são aprovadas.</span><span class="sxs-lookup"><span data-stu-id="8bea3-205">Validate the new mapping to ensure that all bindings are okay.</span></span>  
2. <span data-ttu-id="8bea3-206">Clique na seta para expandir ou recolher a seção Lista de erros.</span><span class="sxs-lookup"><span data-stu-id="8bea3-206">Click the arrow to expand or collapse the Error List section.</span></span>
3. <span data-ttu-id="8bea3-207">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="8bea3-207">Click Save.</span></span>
4. <span data-ttu-id="8bea3-208">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="8bea3-208">Close the page.</span></span>
5. <span data-ttu-id="8bea3-209">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="8bea3-209">Close the page.</span></span>
6. <span data-ttu-id="8bea3-210">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="8bea3-210">Close the page.</span></span>

## <a name="change-the-status-of-the-current-version-of-model-configuration"></a><span data-ttu-id="8bea3-211">Altere o status da versão atual da configuração de modelo.</span><span class="sxs-lookup"><span data-stu-id="8bea3-211">Change the status of the current version of model configuration</span></span>
1. <span data-ttu-id="8bea3-212">Clique em Alterar status.</span><span class="sxs-lookup"><span data-stu-id="8bea3-212">Click Change status.</span></span>
    * <span data-ttu-id="8bea3-213">Altere o status da configuração do modelo criado - de Rascunho para Concluído para torná-lo disponível para design de formato de pagamento.</span><span class="sxs-lookup"><span data-stu-id="8bea3-213">Change the status of designed model configuration – from Draft to Completed to make it available for payment format design.</span></span>  
2. <span data-ttu-id="8bea3-214">Clique em Concluir.</span><span class="sxs-lookup"><span data-stu-id="8bea3-214">Click Complete.</span></span>
    * <span data-ttu-id="8bea3-215">Selecione Concluído.</span><span class="sxs-lookup"><span data-stu-id="8bea3-215">Select Complete.</span></span>  
3. <span data-ttu-id="8bea3-216">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="8bea3-216">In the Description field, type a value.</span></span>
    * <span data-ttu-id="8bea3-217">Por exemplo, "versão 1".</span><span class="sxs-lookup"><span data-stu-id="8bea3-217">For example, 'version 1'.</span></span>  
4. <span data-ttu-id="8bea3-218">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="8bea3-218">Click OK.</span></span>
5. <span data-ttu-id="8bea3-219">Selecione a versão concluída da configuração atual.</span><span class="sxs-lookup"><span data-stu-id="8bea3-219">Select the completed version of the current configuration.</span></span>
    * <span data-ttu-id="8bea3-220">Observe que a configuração criada será salva como versão 1 concluída.</span><span class="sxs-lookup"><span data-stu-id="8bea3-220">Note that the created configuration is saved as completed version 1.</span></span>  


