---
title: ER Projetar modelo de dados de domínio específico
description: Este tópico descreve como criar uma nova configuração de relatório eletrônico (ER) que contém um modelo de dados para documentos de pagamento eletrônico.
author: NickSelin
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERSolutionCreateDropDialog, ERDataModelDesigner, ERDataModelContentsItemCreationDialog, ERDataContainerDescriptorReferenceSwitchDialog
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 351c5a6624f7ee912c507a9f74324f4c8f61166b
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5755025"
---
# <a name="er-design-domain-specific-data-model"></a><span data-ttu-id="4fb04-103">ER Projetar modelo de dados de domínio específico</span><span class="sxs-lookup"><span data-stu-id="4fb04-103">ER Design domain specific data model</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="4fb04-104">As etapas a seguir explicam como um usuário no papel de Administrador do Sistema ou Desenvolvedor de Relatório Eletrônico pode criar uma nova configuração de Relatório Eletrônico (RE) que contem um modelo de dados para os documentos de pagamento eletrônico.</span><span class="sxs-lookup"><span data-stu-id="4fb04-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can create a new Electronic reporting (ER) configuration that contains a data model for electronic payment documents.</span></span> <span data-ttu-id="4fb04-105">Esse modelo de dados será usado posteriormente como uma fonte de dados quando você criar o formato dos documentos de pagamento.</span><span class="sxs-lookup"><span data-stu-id="4fb04-105">This data model will later be used as a data source when you create the format of the payment documents.</span></span>

<span data-ttu-id="4fb04-106">Neste exemplo, será criado uma configuração para a empresa de exemplo, Litware, Inc. Essas etapas podem ser executadas em qualquer empresa, uma vez que configurações de ER são compartilhadas entre todas as empresas.</span><span class="sxs-lookup"><span data-stu-id="4fb04-106">In this example, you will create a configuration for sample company, Litware, Inc. These steps can be performed in any company as ER configurations are shared among companies.</span></span> <span data-ttu-id="4fb04-107">Para completar essas etapas, você deve primeiro completar as etapas do procedimento "Criar um provedor de configuração e marcá-lo como ativo".</span><span class="sxs-lookup"><span data-stu-id="4fb04-107">To complete these steps, you must first complete the steps in the "Create a configuration provider and mark it as active" procedure.</span></span>

1. <span data-ttu-id="4fb04-108">Ir para Administração da organização > Espaços de trabalho > Relatório eletrônico.</span><span class="sxs-lookup"><span data-stu-id="4fb04-108">Go to Organization administration > Workspaces > Electronic reporting.</span></span>

    <span data-ttu-id="4fb04-109">Selecione o provedor de configuração para a empresa de exemplo, "Litware, Inc."</span><span class="sxs-lookup"><span data-stu-id="4fb04-109">Select the configuration provider for sample company, 'Litware, Inc.'</span></span> <span data-ttu-id="4fb04-110">Se não visualizar este provedor de configuração, você deve primeiro concluir as etapas do procedimento "Criar um provedor de configuração e marcá-lo como ativo".</span><span class="sxs-lookup"><span data-stu-id="4fb04-110">If you don't see this configuration provider, you must first complete the steps in the "Create a configuration provider and mark it as active" procedure.</span></span>  
    
2. <span data-ttu-id="4fb04-111">Clique em Configurações de relatórios.</span><span class="sxs-lookup"><span data-stu-id="4fb04-111">Click Reporting configurations.</span></span>

    <span data-ttu-id="4fb04-112">Você irá criar uma configuração que contém um modelo de dados para documentos de pagamento eletrônico.</span><span class="sxs-lookup"><span data-stu-id="4fb04-112">You will create a configuration that contains a data model for electronic payment documents.</span></span> <span data-ttu-id="4fb04-113">Este modelo de dados será usado posteriormente como uma base de dados quando você criar o formato para os documentos de pagamento.</span><span class="sxs-lookup"><span data-stu-id="4fb04-113">This data model will be used later as a data source when you create the format for the payment documents.</span></span>  

## <a name="create-a-new-data-model-configuration"></a><span data-ttu-id="4fb04-114">Criar uma nova configuração de modelo de dados</span><span class="sxs-lookup"><span data-stu-id="4fb04-114">Create a new data model configuration</span></span>
1. <span data-ttu-id="4fb04-115">Clique em Criar configuração para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="4fb04-115">Click Create configuration to open the drop dialog.</span></span>
2. <span data-ttu-id="4fb04-116">No campo Nome, digite 'Pagamentos (modelo simplificado)'.</span><span class="sxs-lookup"><span data-stu-id="4fb04-116">In the Name field, type 'Payments (simplified model)'.</span></span>
3. <span data-ttu-id="4fb04-117">No campo Descrição, digite 'Configuração do modelo de pagamento'.</span><span class="sxs-lookup"><span data-stu-id="4fb04-117">In the Description field, type 'Payment model configuration'.</span></span>

    <span data-ttu-id="4fb04-118">O provedor de configuração ativo é automaticamente inserido aqui.</span><span class="sxs-lookup"><span data-stu-id="4fb04-118">The active configuration provider is automatically entered here.</span></span> <span data-ttu-id="4fb04-119">Este provedor será capaz de manter essa configuração.</span><span class="sxs-lookup"><span data-stu-id="4fb04-119">This provider will be able to maintain this configuration.</span></span> <span data-ttu-id="4fb04-120">Outros provedores podem usar esta configuração, mas não poderão mantê-la.</span><span class="sxs-lookup"><span data-stu-id="4fb04-120">Other providers can use this configuration, but will not be able to maintain it.</span></span>  

4. <span data-ttu-id="4fb04-121">Clique no botão "Criar configuração" para completar a tarefa de criação de configuração</span><span class="sxs-lookup"><span data-stu-id="4fb04-121">Click 'Create configuration' button to complete the configuration creation task</span></span>

## <a name="create-a-data-model"></a><span data-ttu-id="4fb04-122">Criar um modelo de dados</span><span class="sxs-lookup"><span data-stu-id="4fb04-122">Create a data model</span></span>
<span data-ttu-id="4fb04-123">Você está criando um novo modelo de dados para a configuração selecionada.</span><span class="sxs-lookup"><span data-stu-id="4fb04-123">You're creating a new data model for the selected configuration.</span></span> <span data-ttu-id="4fb04-124">Essa versão de configuração terá um status de Rascunho.</span><span class="sxs-lookup"><span data-stu-id="4fb04-124">This configuration version will have a status of Draft.</span></span>  
1. <span data-ttu-id="4fb04-125">Clique em Designer.</span><span class="sxs-lookup"><span data-stu-id="4fb04-125">Click Designer.</span></span>

## <a name="define-the-structure-of-a-party-participating-in-a-payment-process"></a><span data-ttu-id="4fb04-126">Definir a estrutura de participação de um participante em um processo de pagamento</span><span class="sxs-lookup"><span data-stu-id="4fb04-126">Define the structure of a party participating in a payment process</span></span>
1. <span data-ttu-id="4fb04-127">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="4fb04-127">Click New to open the drop dialog.</span></span>
2. <span data-ttu-id="4fb04-128">No campo Nome, digite "Participante".</span><span class="sxs-lookup"><span data-stu-id="4fb04-128">In the Name field, type 'Party'.</span></span>
3. <span data-ttu-id="4fb04-129">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="4fb04-129">Click Add.</span></span>
4. <span data-ttu-id="4fb04-130">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="4fb04-130">Click New to open the drop dialog.</span></span>
5. <span data-ttu-id="4fb04-131">No campo Nome, digite 'Nome'.</span><span class="sxs-lookup"><span data-stu-id="4fb04-131">In the Name field, type 'Name'.</span></span>
6. <span data-ttu-id="4fb04-132">No campo Tipo de item, selecione 'String'.</span><span class="sxs-lookup"><span data-stu-id="4fb04-132">In the Item type field, select 'String'.</span></span>
7. <span data-ttu-id="4fb04-133">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="4fb04-133">Click Add.</span></span>
8. <span data-ttu-id="4fb04-134">No campo Encontrar, digite "Participante".</span><span class="sxs-lookup"><span data-stu-id="4fb04-134">In the Find field, type 'Party'.</span></span>
9. <span data-ttu-id="4fb04-135">Clique em Localizar anterior.</span><span class="sxs-lookup"><span data-stu-id="4fb04-135">Click Find previous.</span></span>

## <a name="define-the-bank-structure-for-this-model"></a><span data-ttu-id="4fb04-136">Definir a estrutura do banco para este modelo</span><span class="sxs-lookup"><span data-stu-id="4fb04-136">Define the bank structure for this model</span></span>
1. <span data-ttu-id="4fb04-137">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="4fb04-137">Click New to open the drop dialog.</span></span>
2. <span data-ttu-id="4fb04-138">No campo Nome, digite 'Agente'.</span><span class="sxs-lookup"><span data-stu-id="4fb04-138">In the Name field, type 'Agent'.</span></span>
3. <span data-ttu-id="4fb04-139">No campo Tipo de item, selecione 'Registro'.</span><span class="sxs-lookup"><span data-stu-id="4fb04-139">In the Item type field, select 'Record'.</span></span>
4. <span data-ttu-id="4fb04-140">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="4fb04-140">Click Add.</span></span>
5. <span data-ttu-id="4fb04-141">No campo Descrição, insira "Instituição financeira (por exemplo, um banco) que mantém uma conta para o participante (devedor/credor).".</span><span class="sxs-lookup"><span data-stu-id="4fb04-141">In the Description field, enter 'Financial institution (for instance, a bank) servicing an account for the party (debtor/creditor).'.</span></span>

    <span data-ttu-id="4fb04-142">Instituição financeira (por exemplo, um banco) que mantém uma conta para o participante (devedor/credor).</span><span class="sxs-lookup"><span data-stu-id="4fb04-142">Financial institution (for instance, a bank) servicing an account for the party (debtor/creditor).</span></span>  

6. <span data-ttu-id="4fb04-143">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="4fb04-143">Click New to open the drop dialog.</span></span>
7. <span data-ttu-id="4fb04-144">No campo Nome, digite 'Nome'.</span><span class="sxs-lookup"><span data-stu-id="4fb04-144">In the Name field, type 'Name'.</span></span> 
8. <span data-ttu-id="4fb04-145">No campo Tipo de item, selecione 'String'.</span><span class="sxs-lookup"><span data-stu-id="4fb04-145">In the Item type field, select 'String'.</span></span>
9. <span data-ttu-id="4fb04-146">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="4fb04-146">Click Add.</span></span>
10. <span data-ttu-id="4fb04-147">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="4fb04-147">Click New to open the drop dialog.</span></span>
11. <span data-ttu-id="4fb04-148">No campo Nome, digite 'SWIFT'.</span><span class="sxs-lookup"><span data-stu-id="4fb04-148">In the Name field, type 'SWIFT'.</span></span>
12. <span data-ttu-id="4fb04-149">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="4fb04-149">Click Add.</span></span>
13. <span data-ttu-id="4fb04-150">No campo Descrição, insira "Código de identificação do banco".</span><span class="sxs-lookup"><span data-stu-id="4fb04-150">In the Description field, enter 'Bank identification code'.</span></span> 
14. <span data-ttu-id="4fb04-151">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="4fb04-151">Click New to open the drop dialog.</span></span>
15. <span data-ttu-id="4fb04-152">No campo Nome, digite 'Número Identificador do banco'.</span><span class="sxs-lookup"><span data-stu-id="4fb04-152">In the Name field, type 'RoutingNumber'.</span></span>
16. <span data-ttu-id="4fb04-153">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="4fb04-153">Click Add.</span></span>
17. <span data-ttu-id="4fb04-154">No campo Descrição, insira "Número identificador do banco".</span><span class="sxs-lookup"><span data-stu-id="4fb04-154">In the Description field, enter 'Routing number'.</span></span>
18. <span data-ttu-id="4fb04-155">Clique em Localizar anterior.</span><span class="sxs-lookup"><span data-stu-id="4fb04-155">Click Find previous.</span></span>

## <a name="define-the-bank-account-structure-for-this-model"></a><span data-ttu-id="4fb04-156">Definir a estrutura da conta bancária para este modelo</span><span class="sxs-lookup"><span data-stu-id="4fb04-156">Define the bank account structure for this model</span></span>
1. <span data-ttu-id="4fb04-157">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="4fb04-157">Click New to open the drop dialog.</span></span>
2. <span data-ttu-id="4fb04-158">No campo Nome, digite 'Conta'.</span><span class="sxs-lookup"><span data-stu-id="4fb04-158">In the Name field, type 'Account'.</span></span> 
3. <span data-ttu-id="4fb04-159">No campo Tipo de item, selecione 'Registro'.</span><span class="sxs-lookup"><span data-stu-id="4fb04-159">In the Item type field, select 'Record'.</span></span>
4. <span data-ttu-id="4fb04-160">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="4fb04-160">Click Add.</span></span>
5. <span data-ttu-id="4fb04-161">No campo Descrição, insira "Identificação de uma conta do participante em uma instituição financeira (por exemplo, um banco)".</span><span class="sxs-lookup"><span data-stu-id="4fb04-161">In the Description field, enter 'Identification of an account of a party in a financial institution (for instance, a bank).'.</span></span>

    <span data-ttu-id="4fb04-162">Identificação de uma conta do participante em uma instituição financeira (por exemplo, um banco).</span><span class="sxs-lookup"><span data-stu-id="4fb04-162">Identification of an account of a party in a financial institution (for instance, a bank).</span></span>  

6. <span data-ttu-id="4fb04-163">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="4fb04-163">Click New to open the drop dialog.</span></span>
7. <span data-ttu-id="4fb04-164">No campo Nome, digite 'Moeda'.</span><span class="sxs-lookup"><span data-stu-id="4fb04-164">In the Name field, type 'Currency'.</span></span> 
8. <span data-ttu-id="4fb04-165">No campo Tipo de item, selecione 'String'.</span><span class="sxs-lookup"><span data-stu-id="4fb04-165">In the Item type field, select 'String'.</span></span>
9. <span data-ttu-id="4fb04-166">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="4fb04-166">Click Add.</span></span>
10. <span data-ttu-id="4fb04-167">No campo Descrição, insira "Código de moeda".</span><span class="sxs-lookup"><span data-stu-id="4fb04-167">In the Description field, enter 'Currency code'.</span></span>
11. <span data-ttu-id="4fb04-168">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="4fb04-168">Click New to open the drop dialog.</span></span>
12. <span data-ttu-id="4fb04-169">No campo Nome, digite 'Número'.</span><span class="sxs-lookup"><span data-stu-id="4fb04-169">In the Name field, type 'Number'.</span></span> 
13. <span data-ttu-id="4fb04-170">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="4fb04-170">Click Add.</span></span>
14. <span data-ttu-id="4fb04-171">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="4fb04-171">Click New to open the drop dialog.</span></span>
15. <span data-ttu-id="4fb04-172">No campo Nome, digite 'IBAN'.</span><span class="sxs-lookup"><span data-stu-id="4fb04-172">In the Name field, type 'IBAN'.</span></span> 
16. <span data-ttu-id="4fb04-173">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="4fb04-173">Click Add.</span></span>
17. <span data-ttu-id="4fb04-174">No campo Descrição, insira "Número de conta bancária internacional".</span><span class="sxs-lookup"><span data-stu-id="4fb04-174">In the Description field, enter 'International bank account number'.</span></span>

## <a name="define-the-payment-message-structure-for-credit-transfer-payment-type"></a><span data-ttu-id="4fb04-175">Definir a estrutura de mensagem de pagamento para o tipo de pagamento de transferência de crédito</span><span class="sxs-lookup"><span data-stu-id="4fb04-175">Define the payment message structure for credit transfer payment type</span></span>
1. <span data-ttu-id="4fb04-176">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="4fb04-176">Click New to open the drop dialog.</span></span>
2. <span data-ttu-id="4fb04-177">No campo Novo nó como um, insira "Raiz do modelo".</span><span class="sxs-lookup"><span data-stu-id="4fb04-177">In the New node as a field, enter 'Model root'.</span></span>
3. <span data-ttu-id="4fb04-178">No campo Nome, digite 'Início da Transferência de Crédito do Cliente'.</span><span class="sxs-lookup"><span data-stu-id="4fb04-178">In the Name field, type 'CustomerCreditTransferInitiation'.</span></span>
4. <span data-ttu-id="4fb04-179">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="4fb04-179">Click Add.</span></span>
5. <span data-ttu-id="4fb04-180">No campo Encontrar, digite "CustomerCreditTransferInitiation".</span><span class="sxs-lookup"><span data-stu-id="4fb04-180">In the Find field, type 'CustomerCreditTransferInitiation'.</span></span> 
6. <span data-ttu-id="4fb04-181">Clique em Localizar anterior.</span><span class="sxs-lookup"><span data-stu-id="4fb04-181">Click Find previous.</span></span>
7. <span data-ttu-id="4fb04-182">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="4fb04-182">Click New to open the drop dialog.</span></span>
8. <span data-ttu-id="4fb04-183">No campo Nome, digite 'Identificação da Mensagem'.</span><span class="sxs-lookup"><span data-stu-id="4fb04-183">In the Name field, type 'MessageIdentification'.</span></span> 
9. <span data-ttu-id="4fb04-184">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="4fb04-184">Click Add.</span></span>
10. <span data-ttu-id="4fb04-185">No campo Descrição, insira "A referência ponto a ponto definida pelo participante instrutor (e enviada ao próximo participante) para identificar uma mensagem".</span><span class="sxs-lookup"><span data-stu-id="4fb04-185">In the Description field, enter 'The point-to-point reference assigned by the instructing party (and sent to the next party) to identify a message.'.</span></span>

    <span data-ttu-id="4fb04-186">A referência ponto a ponto atribuída pela parte instrutora (e enviada para o próximo participante) para identificar uma mensagem.</span><span class="sxs-lookup"><span data-stu-id="4fb04-186">The point-to-point reference assigned by the instructing party (and sent to the next party) to identify a message.</span></span>  

11. <span data-ttu-id="4fb04-187">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="4fb04-187">Click New to open the drop dialog.</span></span>
12. <span data-ttu-id="4fb04-188">No campo Nome, digite 'ProcessamentoDataHora'.</span><span class="sxs-lookup"><span data-stu-id="4fb04-188">In the Name field, type 'ProcessingDateTime'.</span></span>
13. <span data-ttu-id="4fb04-189">No campo Tipo de item, selecione 'DataHora'.</span><span class="sxs-lookup"><span data-stu-id="4fb04-189">In the Item type field, select 'DateTime'.</span></span>
14. <span data-ttu-id="4fb04-190">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="4fb04-190">Click Add.</span></span>
15. <span data-ttu-id="4fb04-191">No campo Descrição, insira "Data e hora em que a mensagem de pagamento foi criada".</span><span class="sxs-lookup"><span data-stu-id="4fb04-191">In the Description field, enter 'Date and time at which the payment message was created.'.</span></span> 
16. <span data-ttu-id="4fb04-192">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="4fb04-192">Click New to open the drop dialog.</span></span>

    <span data-ttu-id="4fb04-193">Defina a estrutura da transação de pagamento para este modelo.</span><span class="sxs-lookup"><span data-stu-id="4fb04-193">Define the payment transaction structure for this model.</span></span>  

17. <span data-ttu-id="4fb04-194">No campo Nome, digite 'Pagamentos'.</span><span class="sxs-lookup"><span data-stu-id="4fb04-194">In the Name field, type 'Payments'.</span></span>
18. <span data-ttu-id="4fb04-195">No campo Tipo de item, selecione 'Lista de Registro'.</span><span class="sxs-lookup"><span data-stu-id="4fb04-195">In the Item type field, select 'Record list'.</span></span>
19. <span data-ttu-id="4fb04-196">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="4fb04-196">Click Add.</span></span>
20. <span data-ttu-id="4fb04-197">No campo Descrição, insira 'Linhas de pagamento da mensagem atual'.</span><span class="sxs-lookup"><span data-stu-id="4fb04-197">In the Description field, enter 'Payment lines of the current message'.</span></span>
21. <span data-ttu-id="4fb04-198">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="4fb04-198">Click New to open the drop dialog.</span></span>
22. <span data-ttu-id="4fb04-199">No campo Nome, digite 'Credor'.</span><span class="sxs-lookup"><span data-stu-id="4fb04-199">In the Name field, type 'Creditor'.</span></span> 
23. <span data-ttu-id="4fb04-200">No campo Tipo de item, selecione 'Registro'.</span><span class="sxs-lookup"><span data-stu-id="4fb04-200">In the Item type field, select 'Record'.</span></span>
24. <span data-ttu-id="4fb04-201">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="4fb04-201">Click Add.</span></span>
25. <span data-ttu-id="4fb04-202">No campo Descrição, insira "Participante ao qual um valor em dinheiro é devido".</span><span class="sxs-lookup"><span data-stu-id="4fb04-202">In the Description field, enter 'Party to which an amount of money is due.'.</span></span> 
26. <span data-ttu-id="4fb04-203">Clique em Alternar referência de item.</span><span class="sxs-lookup"><span data-stu-id="4fb04-203">Click Switch item reference.</span></span>
27. <span data-ttu-id="4fb04-204">No campo Encontrar, digite "Participante".</span><span class="sxs-lookup"><span data-stu-id="4fb04-204">In the Find field, type 'Party'.</span></span>
28. <span data-ttu-id="4fb04-205">Clique em Localizar próximo.</span><span class="sxs-lookup"><span data-stu-id="4fb04-205">Click Find next.</span></span>
29. <span data-ttu-id="4fb04-206">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="4fb04-206">Click OK.</span></span>
30. <span data-ttu-id="4fb04-207">No campo Encontrar, digite "Pagamentos".</span><span class="sxs-lookup"><span data-stu-id="4fb04-207">In the Find field, type 'Payments'.</span></span>
31. <span data-ttu-id="4fb04-208">Clique em Localizar próximo.</span><span class="sxs-lookup"><span data-stu-id="4fb04-208">Click Find next.</span></span>
32. <span data-ttu-id="4fb04-209">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="4fb04-209">Click New to open the drop dialog.</span></span>
33. <span data-ttu-id="4fb04-210">No campo Nome, digite 'Devedor'.</span><span class="sxs-lookup"><span data-stu-id="4fb04-210">In the Name field, type 'Debtor'.</span></span> 
34. <span data-ttu-id="4fb04-211">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="4fb04-211">Click Add.</span></span>
35. <span data-ttu-id="4fb04-212">No campo Descrição, insira "Participante que deve um valor em dinheiro ao credor (definitivo)".</span><span class="sxs-lookup"><span data-stu-id="4fb04-212">In the Description field, enter 'Party that owes an amount of money to the (ultimate) creditor.'.</span></span>
36. <span data-ttu-id="4fb04-213">Clique em Alternar referência de item.</span><span class="sxs-lookup"><span data-stu-id="4fb04-213">Click Switch item reference.</span></span>
37. <span data-ttu-id="4fb04-214">No campo Encontrar, digite "Participante".</span><span class="sxs-lookup"><span data-stu-id="4fb04-214">In the Find field, type 'Party'.</span></span>
38. <span data-ttu-id="4fb04-215">Clique em Localizar próximo.</span><span class="sxs-lookup"><span data-stu-id="4fb04-215">Click Find next.</span></span>
39. <span data-ttu-id="4fb04-216">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="4fb04-216">Click OK.</span></span>
40. <span data-ttu-id="4fb04-217">Clique em Localizar próximo.</span><span class="sxs-lookup"><span data-stu-id="4fb04-217">Click Find next.</span></span>
41. <span data-ttu-id="4fb04-218">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="4fb04-218">Click New to open the drop dialog.</span></span>
42. <span data-ttu-id="4fb04-219">No campo Nome, digite 'Descrição'.</span><span class="sxs-lookup"><span data-stu-id="4fb04-219">In the Name field, type 'Description'.</span></span>
43. <span data-ttu-id="4fb04-220">No campo Tipo de item, selecione 'String'.</span><span class="sxs-lookup"><span data-stu-id="4fb04-220">In the Item type field, select 'String'.</span></span>
44. <span data-ttu-id="4fb04-221">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="4fb04-221">Click Add.</span></span>
45. <span data-ttu-id="4fb04-222">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="4fb04-222">Click New to open the drop dialog.</span></span>
46. <span data-ttu-id="4fb04-223">No campo Nome, digite 'Moeda'.</span><span class="sxs-lookup"><span data-stu-id="4fb04-223">In the Name field, type 'Currency'.</span></span>
47. <span data-ttu-id="4fb04-224">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="4fb04-224">Click Add.</span></span>
48. <span data-ttu-id="4fb04-225">No campo Descrição, insira "Código de moeda".</span><span class="sxs-lookup"><span data-stu-id="4fb04-225">In the Description field, enter 'Currency code'.</span></span>
49. <span data-ttu-id="4fb04-226">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="4fb04-226">Click New to open the drop dialog.</span></span>
50. <span data-ttu-id="4fb04-227">No campo Nome, digite 'Data da Transação'.</span><span class="sxs-lookup"><span data-stu-id="4fb04-227">In the Name field, type 'TransactionDate'.</span></span> 
51. <span data-ttu-id="4fb04-228">No campo Tipo de item, selecione 'Data'.</span><span class="sxs-lookup"><span data-stu-id="4fb04-228">In the Item type field, select 'Date'.</span></span>
52. <span data-ttu-id="4fb04-229">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="4fb04-229">Click Add.</span></span>
53. <span data-ttu-id="4fb04-230">No campo Descrição, insira "Data da transação".</span><span class="sxs-lookup"><span data-stu-id="4fb04-230">In the Description field, enter 'Transaction date'.</span></span> 
54. <span data-ttu-id="4fb04-231">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="4fb04-231">Click New to open the drop dialog.</span></span>
55. <span data-ttu-id="4fb04-232">No campo Nome, digite 'Quantia Indicada'.</span><span class="sxs-lookup"><span data-stu-id="4fb04-232">In the Name field, type 'InstructedAmount'.</span></span>  
56. <span data-ttu-id="4fb04-233">No campo Tipo de item, selecione 'Real'.</span><span class="sxs-lookup"><span data-stu-id="4fb04-233">In the Item type field, select 'Real'.</span></span>
57. <span data-ttu-id="4fb04-234">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="4fb04-234">Click Add.</span></span>
58. <span data-ttu-id="4fb04-235">No campo Descrição, insira "O valor em dinheiro a ser movimentado entre o devedor e o credor, antes da dedução dos encargos".</span><span class="sxs-lookup"><span data-stu-id="4fb04-235">In the Description field, enter 'The amount of money to be moved between the debtor and creditor, before deduction of charges.</span></span> <span data-ttu-id="4fb04-236">O valor deve ser expresso na moeda definida pela parte que inicializou a transação.'.</span><span class="sxs-lookup"><span data-stu-id="4fb04-236">The amount should be expressed in the currency as ordered by the initiating party.'.</span></span>

    <span data-ttu-id="4fb04-237">O valor em dinheiro a ser movido entre o devedor e o credor, antes da dedução dos encargos.</span><span class="sxs-lookup"><span data-stu-id="4fb04-237">The amount of money to be moved between the debtor and creditor, before deduction of charges.</span></span> <span data-ttu-id="4fb04-238">O valor deve ser expresso na moeda definida pela parte que inicializou a transação.</span><span class="sxs-lookup"><span data-stu-id="4fb04-238">The amount should be expressed in the currency as ordered by the initiating party.</span></span>  

59. <span data-ttu-id="4fb04-239">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="4fb04-239">Click New to open the drop dialog.</span></span>
60. <span data-ttu-id="4fb04-240">No campo Nome, digite 'End2EndID'.</span><span class="sxs-lookup"><span data-stu-id="4fb04-240">In the Name field, type 'End2EndID'.</span></span> 
61. <span data-ttu-id="4fb04-241">No campo Tipo de item, selecione 'String'.</span><span class="sxs-lookup"><span data-stu-id="4fb04-241">In the Item type field, select 'String'.</span></span>
62. <span data-ttu-id="4fb04-242">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="4fb04-242">Click Add.</span></span>
63. <span data-ttu-id="4fb04-243">No campo Descrição, insira "A identificação exclusiva atribuída pelo participante que inicializou a transação".</span><span class="sxs-lookup"><span data-stu-id="4fb04-243">In the Description field, enter 'The unique identification assigned by the initiating party.</span></span> <span data-ttu-id="4fb04-244">Essa identificação é transmitida, inalterada, ao longo de toda a cadeia ponto-a-ponto.'.</span><span class="sxs-lookup"><span data-stu-id="4fb04-244">This identification is passed on, unchanged, throughout the entire end-to-end chain.'.</span></span> 
64. <span data-ttu-id="4fb04-245">No campo Nome, digite 'Modelo de Pagamento'.</span><span class="sxs-lookup"><span data-stu-id="4fb04-245">In the Name field, type 'PaymentModel'.</span></span>

    <span data-ttu-id="4fb04-246">O nome do PaymentModel se alinha a interfaces predefinidas de formulários de pagamento.</span><span class="sxs-lookup"><span data-stu-id="4fb04-246">The PaymentModel name aligns with predefined interfaces of payment forms.</span></span>  

65. <span data-ttu-id="4fb04-247">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="4fb04-247">Click Save.</span></span>
66. <span data-ttu-id="4fb04-248">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="4fb04-248">Close the page.</span></span>



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]