---
title: ER Projetar modelo de dados de domínio específico
description: As etapas a seguir explicam como um usuário no papel de Administrador do Sistema ou Desenvolvedor de Relatório Eletrônico pode criar uma nova configuração de Relatório Eletrônico (RE) que contem um modelo de dados para os documentos de pagamento eletrônico.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERSolutionCreateDropDialog, ERDataModelDesigner, ERDataModelContentsItemCreationDialog, ERDataContainerDescriptorReferenceSwitchDialog
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0d66cc69da08478ceb931fab594da51bafcacc38
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2185074"
---
# <a name="er-design-domain-specific-data-model"></a><span data-ttu-id="40e8a-103">ER Projetar modelo de dados de domínio específico</span><span class="sxs-lookup"><span data-stu-id="40e8a-103">ER Design domain specific data model</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="40e8a-104">As etapas a seguir explicam como um usuário no papel de Administrador do Sistema ou Desenvolvedor de Relatório Eletrônico pode criar uma nova configuração de Relatório Eletrônico (RE) que contem um modelo de dados para os documentos de pagamento eletrônico.</span><span class="sxs-lookup"><span data-stu-id="40e8a-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can create a new Electronic reporting (ER) configuration that contains a data model for electronic payment documents.</span></span> <span data-ttu-id="40e8a-105">Esse modelo de dados será usado posteriormente como uma fonte de dados quando você criar o formato dos documentos de pagamento.</span><span class="sxs-lookup"><span data-stu-id="40e8a-105">This data model will later be used as a data source when you create the format of the payment documents.</span></span>



<span data-ttu-id="40e8a-106">Neste exemplo, será criado uma configuração para a empresa de exemplo, Litware, Inc. Essas etapas podem ser executadas em qualquer empresa, uma vez que configurações de ER são compartilhadas entre todas as empresas.</span><span class="sxs-lookup"><span data-stu-id="40e8a-106">In this example, you will create a configuration for sample company, Litware, Inc. These steps can be performed in any company as ER configurations are shared among companies.</span></span> <span data-ttu-id="40e8a-107">Para completar essas etapas, você deve primeiro completar as etapas do procedimento “Criar um provedor de configuração e marcá-lo como ativo“.</span><span class="sxs-lookup"><span data-stu-id="40e8a-107">To complete these steps, you must first complete the steps in the “Create a configuration provider and mark it as active” procedure.</span></span>

1. <span data-ttu-id="40e8a-108">Ir para Administração da organização > Espaços de trabalho > Relatório eletrônico.</span><span class="sxs-lookup"><span data-stu-id="40e8a-108">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
    * <span data-ttu-id="40e8a-109">Selecione o provedor de configuração para a empresa de exemplo, "Litware, Inc."</span><span class="sxs-lookup"><span data-stu-id="40e8a-109">Select the configuration provider for sample company, ‘Litware, Inc.’</span></span> <span data-ttu-id="40e8a-110">Se você não visualizar o provedor de configuração, você deve primeiro concluir as etapas do procedimento “Criar um provedor de configuração e marcá-lo como ativo“.</span><span class="sxs-lookup"><span data-stu-id="40e8a-110">If you don’t see this configuration provider, you must first complete the steps in the “Create a configuration provider and mark it as active” procedure.</span></span>  
2. <span data-ttu-id="40e8a-111">Clique em Configurações de relatórios.</span><span class="sxs-lookup"><span data-stu-id="40e8a-111">Click Reporting configurations.</span></span>
    * <span data-ttu-id="40e8a-112">Você irá criar uma configuração que contém um modelo de dados para documentos de pagamento eletrônico.</span><span class="sxs-lookup"><span data-stu-id="40e8a-112">You will create a configuration that contains a data model for electronic payment documents.</span></span> <span data-ttu-id="40e8a-113">Este modelo de dados será usado posteriormente como uma base de dados quando você criar o formato para os documentos de pagamento.</span><span class="sxs-lookup"><span data-stu-id="40e8a-113">This data model will be used later as a data source when you create the format for the payment documents.</span></span>  

## <a name="create-a-new-data-model-configuration"></a><span data-ttu-id="40e8a-114">Criar uma nova configuração de modelo de dados</span><span class="sxs-lookup"><span data-stu-id="40e8a-114">Create a new data model configuration</span></span>
1. <span data-ttu-id="40e8a-115">Clique em Criar configuração para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="40e8a-115">Click Create configuration to open the drop dialog.</span></span>
2. <span data-ttu-id="40e8a-116">No campo Nome, digite 'Pagamentos (modelo simplificado)'.</span><span class="sxs-lookup"><span data-stu-id="40e8a-116">In the Name field, type 'Payments (simplified model)'.</span></span>
    * <span data-ttu-id="40e8a-117">Pagamentos (modelo simplificado)</span><span class="sxs-lookup"><span data-stu-id="40e8a-117">Payments (simplified model)</span></span>  
3. <span data-ttu-id="40e8a-118">No campo Descrição, digite 'Configuração do modelo de pagamento'.</span><span class="sxs-lookup"><span data-stu-id="40e8a-118">In the Description field, type 'Payment model configuration'.</span></span>
    * <span data-ttu-id="40e8a-119">Configuração do modelo de pagamento</span><span class="sxs-lookup"><span data-stu-id="40e8a-119">Payment model configuration</span></span>  
    * <span data-ttu-id="40e8a-120">O provedor de configuração ativo é automaticamente inserido aqui.</span><span class="sxs-lookup"><span data-stu-id="40e8a-120">The active configuration provider is automatically entered here.</span></span> <span data-ttu-id="40e8a-121">Este provedor será capaz de manter essa configuração.</span><span class="sxs-lookup"><span data-stu-id="40e8a-121">This provider will be able to maintain this configuration.</span></span> <span data-ttu-id="40e8a-122">Outros provedores podem usar esta configuração, mas não poderão mantê-la.</span><span class="sxs-lookup"><span data-stu-id="40e8a-122">Other providers can use this configuration, but will not be able to maintain it.</span></span>  
4. <span data-ttu-id="40e8a-123">Clique no botão 'Criar configuração' para completar a tarefa de criação de configuração</span><span class="sxs-lookup"><span data-stu-id="40e8a-123">Click ‘Create configuration’ button to complete the configuration creation task</span></span>

## <a name="create-a-data-model"></a><span data-ttu-id="40e8a-124">Criar um modelo de dados</span><span class="sxs-lookup"><span data-stu-id="40e8a-124">Create a data model</span></span>
    * <span data-ttu-id="40e8a-125">Você está criando um novo modelo de dados para a configuração selecionada.</span><span class="sxs-lookup"><span data-stu-id="40e8a-125">You're creating a new data model for the selected configuration.</span></span> <span data-ttu-id="40e8a-126">Essa versão de configuração terá um status de Rascunho.</span><span class="sxs-lookup"><span data-stu-id="40e8a-126">This configuration version will have a status of Draft.</span></span>  
1. <span data-ttu-id="40e8a-127">Clique em Designer.</span><span class="sxs-lookup"><span data-stu-id="40e8a-127">Click Designer.</span></span>

## <a name="define-the-structure-of-a-party-participating-in-a-payment-process"></a><span data-ttu-id="40e8a-128">Definir a estrutura de participação de um participante em um processo de pagamento</span><span class="sxs-lookup"><span data-stu-id="40e8a-128">Define the structure of a party participating in a payment process</span></span>
1. <span data-ttu-id="40e8a-129">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="40e8a-129">Click New to open the drop dialog.</span></span>
2. <span data-ttu-id="40e8a-130">No campo Nome, digite "Participante".</span><span class="sxs-lookup"><span data-stu-id="40e8a-130">In the Name field, type 'Party'.</span></span>
    * <span data-ttu-id="40e8a-131">Participante</span><span class="sxs-lookup"><span data-stu-id="40e8a-131">Party</span></span>  
3. <span data-ttu-id="40e8a-132">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="40e8a-132">Click Add.</span></span>
4. <span data-ttu-id="40e8a-133">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="40e8a-133">Click New to open the drop dialog.</span></span>
5. <span data-ttu-id="40e8a-134">No campo Nome, digite 'Nome'.</span><span class="sxs-lookup"><span data-stu-id="40e8a-134">In the Name field, type 'Name'.</span></span>
    * <span data-ttu-id="40e8a-135">Nome</span><span class="sxs-lookup"><span data-stu-id="40e8a-135">Name</span></span>  
6. <span data-ttu-id="40e8a-136">No campo Tipo de item, selecione 'String'.</span><span class="sxs-lookup"><span data-stu-id="40e8a-136">In the Item type field, select 'String'.</span></span>
7. <span data-ttu-id="40e8a-137">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="40e8a-137">Click Add.</span></span>
8. <span data-ttu-id="40e8a-138">No campo Encontrar, digite "Participante".</span><span class="sxs-lookup"><span data-stu-id="40e8a-138">In the Find field, type 'Party'.</span></span>
    * <span data-ttu-id="40e8a-139">Participante</span><span class="sxs-lookup"><span data-stu-id="40e8a-139">Party</span></span>  
9. <span data-ttu-id="40e8a-140">Clique em Localizar anterior.</span><span class="sxs-lookup"><span data-stu-id="40e8a-140">Click Find previous.</span></span>

## <a name="define-the-bank-structure-for-this-model"></a><span data-ttu-id="40e8a-141">Definir a estrutura do banco para este modelo</span><span class="sxs-lookup"><span data-stu-id="40e8a-141">Define the bank structure for this model</span></span>
1. <span data-ttu-id="40e8a-142">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="40e8a-142">Click New to open the drop dialog.</span></span>
2. <span data-ttu-id="40e8a-143">No campo Nome, digite 'Agente'.</span><span class="sxs-lookup"><span data-stu-id="40e8a-143">In the Name field, type 'Agent'.</span></span>
    * <span data-ttu-id="40e8a-144">Agente</span><span class="sxs-lookup"><span data-stu-id="40e8a-144">Agent</span></span>  
3. <span data-ttu-id="40e8a-145">No campo Tipo de item, selecione 'Registro'.</span><span class="sxs-lookup"><span data-stu-id="40e8a-145">In the Item type field, select 'Record'.</span></span>
4. <span data-ttu-id="40e8a-146">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="40e8a-146">Click Add.</span></span>
5. <span data-ttu-id="40e8a-147">No campo Descrição, insira "Instituição financeira (por exemplo, um banco) que mantém uma conta para o participante (devedor/credor).".</span><span class="sxs-lookup"><span data-stu-id="40e8a-147">In the Description field, enter 'Financial institution (for instance, a bank) servicing an account for the party (debtor/creditor).'.</span></span>
    * <span data-ttu-id="40e8a-148">Instituição financeira (por exemplo, um banco) que mantém uma conta para o participante (devedor/credor).</span><span class="sxs-lookup"><span data-stu-id="40e8a-148">Financial institution (for instance, a bank) servicing an account for the party (debtor/creditor).</span></span>  
6. <span data-ttu-id="40e8a-149">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="40e8a-149">Click New to open the drop dialog.</span></span>
7. <span data-ttu-id="40e8a-150">No campo Nome, digite 'Nome'.</span><span class="sxs-lookup"><span data-stu-id="40e8a-150">In the Name field, type 'Name'.</span></span>
    * <span data-ttu-id="40e8a-151">Nome</span><span class="sxs-lookup"><span data-stu-id="40e8a-151">Name</span></span>  
8. <span data-ttu-id="40e8a-152">No campo Tipo de item, selecione 'String'.</span><span class="sxs-lookup"><span data-stu-id="40e8a-152">In the Item type field, select 'String'.</span></span>
9. <span data-ttu-id="40e8a-153">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="40e8a-153">Click Add.</span></span>
10. <span data-ttu-id="40e8a-154">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="40e8a-154">Click New to open the drop dialog.</span></span>
11. <span data-ttu-id="40e8a-155">No campo Nome, digite 'SWIFT'.</span><span class="sxs-lookup"><span data-stu-id="40e8a-155">In the Name field, type 'SWIFT'.</span></span>
    * <span data-ttu-id="40e8a-156">SWIFT</span><span class="sxs-lookup"><span data-stu-id="40e8a-156">SWIFT</span></span>  
12. <span data-ttu-id="40e8a-157">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="40e8a-157">Click Add.</span></span>
13. <span data-ttu-id="40e8a-158">No campo Descrição, insira "Código de identificação do banco".</span><span class="sxs-lookup"><span data-stu-id="40e8a-158">In the Description field, enter 'Bank identification code'.</span></span>
    * <span data-ttu-id="40e8a-159">Código de identificação do banco</span><span class="sxs-lookup"><span data-stu-id="40e8a-159">Bank identification code</span></span>  
14. <span data-ttu-id="40e8a-160">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="40e8a-160">Click New to open the drop dialog.</span></span>
15. <span data-ttu-id="40e8a-161">No campo Nome, digite 'Número Identificador do banco'.</span><span class="sxs-lookup"><span data-stu-id="40e8a-161">In the Name field, type 'RoutingNumber'.</span></span>
    * <span data-ttu-id="40e8a-162">Número identificador do banco</span><span class="sxs-lookup"><span data-stu-id="40e8a-162">RoutingNumber</span></span>  
16. <span data-ttu-id="40e8a-163">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="40e8a-163">Click Add.</span></span>
17. <span data-ttu-id="40e8a-164">No campo Descrição, insira "Número identificador do banco".</span><span class="sxs-lookup"><span data-stu-id="40e8a-164">In the Description field, enter 'Routing number'.</span></span>
    * <span data-ttu-id="40e8a-165">Número do banco</span><span class="sxs-lookup"><span data-stu-id="40e8a-165">Routing number</span></span>  
18. <span data-ttu-id="40e8a-166">Clique em Localizar anterior.</span><span class="sxs-lookup"><span data-stu-id="40e8a-166">Click Find previous.</span></span>

## <a name="define-the-bank-account-structure-for-this-model"></a><span data-ttu-id="40e8a-167">Definir a estrutura da conta bancária para este modelo</span><span class="sxs-lookup"><span data-stu-id="40e8a-167">Define the bank account structure for this model</span></span>
1. <span data-ttu-id="40e8a-168">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="40e8a-168">Click New to open the drop dialog.</span></span>
2. <span data-ttu-id="40e8a-169">No campo Nome, digite 'Conta'.</span><span class="sxs-lookup"><span data-stu-id="40e8a-169">In the Name field, type 'Account'.</span></span>
    * <span data-ttu-id="40e8a-170">Conta</span><span class="sxs-lookup"><span data-stu-id="40e8a-170">Account</span></span>  
3. <span data-ttu-id="40e8a-171">No campo Tipo de item, selecione 'Registro'.</span><span class="sxs-lookup"><span data-stu-id="40e8a-171">In the Item type field, select 'Record'.</span></span>
4. <span data-ttu-id="40e8a-172">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="40e8a-172">Click Add.</span></span>
5. <span data-ttu-id="40e8a-173">No campo Descrição, insira "Identificação de uma conta do participante em uma instituição financeira (por exemplo, um banco)".</span><span class="sxs-lookup"><span data-stu-id="40e8a-173">In the Description field, enter 'Identification of an account of a party in a financial institution (for instance, a bank).'.</span></span>
    * <span data-ttu-id="40e8a-174">Identificação de uma conta do participante em uma instituição financeira (por exemplo, um banco).</span><span class="sxs-lookup"><span data-stu-id="40e8a-174">Identification of an account of a party in a financial institution (for instance, a bank).</span></span>  
6. <span data-ttu-id="40e8a-175">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="40e8a-175">Click New to open the drop dialog.</span></span>
7. <span data-ttu-id="40e8a-176">No campo Nome, digite 'Moeda'.</span><span class="sxs-lookup"><span data-stu-id="40e8a-176">In the Name field, type 'Currency'.</span></span>
    * <span data-ttu-id="40e8a-177">Moeda</span><span class="sxs-lookup"><span data-stu-id="40e8a-177">Currency</span></span>  
8. <span data-ttu-id="40e8a-178">No campo Tipo de item, selecione 'String'.</span><span class="sxs-lookup"><span data-stu-id="40e8a-178">In the Item type field, select 'String'.</span></span>
9. <span data-ttu-id="40e8a-179">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="40e8a-179">Click Add.</span></span>
10. <span data-ttu-id="40e8a-180">No campo Descrição, insira "Código de moeda".</span><span class="sxs-lookup"><span data-stu-id="40e8a-180">In the Description field, enter 'Currency code'.</span></span>
    * <span data-ttu-id="40e8a-181">Código de Moeda</span><span class="sxs-lookup"><span data-stu-id="40e8a-181">Currency code</span></span>  
11. <span data-ttu-id="40e8a-182">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="40e8a-182">Click New to open the drop dialog.</span></span>
12. <span data-ttu-id="40e8a-183">No campo Nome, digite 'Número'.</span><span class="sxs-lookup"><span data-stu-id="40e8a-183">In the Name field, type 'Number'.</span></span>
    * <span data-ttu-id="40e8a-184">Número</span><span class="sxs-lookup"><span data-stu-id="40e8a-184">Number</span></span>  
13. <span data-ttu-id="40e8a-185">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="40e8a-185">Click Add.</span></span>
14. <span data-ttu-id="40e8a-186">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="40e8a-186">Click New to open the drop dialog.</span></span>
15. <span data-ttu-id="40e8a-187">No campo Nome, digite 'IBAN'.</span><span class="sxs-lookup"><span data-stu-id="40e8a-187">In the Name field, type 'IBAN'.</span></span>
    * <span data-ttu-id="40e8a-188">IBAN</span><span class="sxs-lookup"><span data-stu-id="40e8a-188">IBAN</span></span>  
16. <span data-ttu-id="40e8a-189">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="40e8a-189">Click Add.</span></span>
17. <span data-ttu-id="40e8a-190">No campo Descrição, insira "Número de conta bancária internacional".</span><span class="sxs-lookup"><span data-stu-id="40e8a-190">In the Description field, enter 'International bank account number'.</span></span>
    * <span data-ttu-id="40e8a-191">Número de conta bancária internacional</span><span class="sxs-lookup"><span data-stu-id="40e8a-191">International bank account number</span></span>  

## <a name="define-the-payment-message-structure-for-credit-transfer-payment-type"></a><span data-ttu-id="40e8a-192">Definir a estrutura de mensagem de pagamento para o tipo de pagamento de transferência de crédito</span><span class="sxs-lookup"><span data-stu-id="40e8a-192">Define the payment message structure for credit transfer payment type</span></span>
1. <span data-ttu-id="40e8a-193">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="40e8a-193">Click New to open the drop dialog.</span></span>
2. <span data-ttu-id="40e8a-194">No campo Novo nó como um, insira "Raiz do modelo".</span><span class="sxs-lookup"><span data-stu-id="40e8a-194">In the New node as a field, enter 'Model root'.</span></span>
3. <span data-ttu-id="40e8a-195">No campo Nome, digite 'Início da Transferência de Crédito do Cliente'.</span><span class="sxs-lookup"><span data-stu-id="40e8a-195">In the Name field, type 'CustomerCreditTransferInitiation'.</span></span>
    * <span data-ttu-id="40e8a-196">Início da Transferência de Crédito do Cliente</span><span class="sxs-lookup"><span data-stu-id="40e8a-196">CustomerCreditTransferInitiation</span></span>  
4. <span data-ttu-id="40e8a-197">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="40e8a-197">Click Add.</span></span>
5. <span data-ttu-id="40e8a-198">No campo Encontrar, digite "CustomerCreditTransferInitiation".</span><span class="sxs-lookup"><span data-stu-id="40e8a-198">In the Find field, type 'CustomerCreditTransferInitiation'.</span></span>
    * <span data-ttu-id="40e8a-199">Início da Transferência de Crédito do Cliente</span><span class="sxs-lookup"><span data-stu-id="40e8a-199">CustomerCreditTransferInitiation</span></span>  
6. <span data-ttu-id="40e8a-200">Clique em Localizar anterior.</span><span class="sxs-lookup"><span data-stu-id="40e8a-200">Click Find previous.</span></span>
7. <span data-ttu-id="40e8a-201">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="40e8a-201">Click New to open the drop dialog.</span></span>
8. <span data-ttu-id="40e8a-202">No campo Nome, digite 'Identificação da Mensagem'.</span><span class="sxs-lookup"><span data-stu-id="40e8a-202">In the Name field, type 'MessageIdentification'.</span></span>
    * <span data-ttu-id="40e8a-203">Identificação da Mensagem</span><span class="sxs-lookup"><span data-stu-id="40e8a-203">MessageIdentification</span></span>  
9. <span data-ttu-id="40e8a-204">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="40e8a-204">Click Add.</span></span>
10. <span data-ttu-id="40e8a-205">No campo Descrição, insira "A referência ponto a ponto definida pelo participante instrutor (e enviada ao próximo participante) para identificar uma mensagem".</span><span class="sxs-lookup"><span data-stu-id="40e8a-205">In the Description field, enter 'The point-to-point reference assigned by the instructing party (and sent to the next party) to identify a message.'.</span></span>
    * <span data-ttu-id="40e8a-206">A referência ponto a ponto atribuída pela parte instrutora (e enviada para o próximo participante) para identificar uma mensagem.</span><span class="sxs-lookup"><span data-stu-id="40e8a-206">The point-to-point reference assigned by the instructing party (and sent to the next party) to identify a message.</span></span>  
11. <span data-ttu-id="40e8a-207">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="40e8a-207">Click New to open the drop dialog.</span></span>
12. <span data-ttu-id="40e8a-208">No campo Nome, digite 'ProcessamentoDataHora'.</span><span class="sxs-lookup"><span data-stu-id="40e8a-208">In the Name field, type 'ProcessingDateTime'.</span></span>
    * <span data-ttu-id="40e8a-209">ProcessamentoDataHora</span><span class="sxs-lookup"><span data-stu-id="40e8a-209">ProcessingDateTime</span></span>  
13. <span data-ttu-id="40e8a-210">No campo Tipo de item, selecione 'DataHora'.</span><span class="sxs-lookup"><span data-stu-id="40e8a-210">In the Item type field, select 'DateTime'.</span></span>
14. <span data-ttu-id="40e8a-211">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="40e8a-211">Click Add.</span></span>
15. <span data-ttu-id="40e8a-212">No campo Descrição, insira "Data e hora em que a mensagem de pagamento foi criada".</span><span class="sxs-lookup"><span data-stu-id="40e8a-212">In the Description field, enter 'Date and time at which the payment message was created.'.</span></span>
    * <span data-ttu-id="40e8a-213">Data e hora em que a mensagem foi criada.</span><span class="sxs-lookup"><span data-stu-id="40e8a-213">Date and time at which the payment message was created.</span></span>  
16. <span data-ttu-id="40e8a-214">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="40e8a-214">Click New to open the drop dialog.</span></span>
    * <span data-ttu-id="40e8a-215">Defina a estrutura da transação de pagamento para este modelo.</span><span class="sxs-lookup"><span data-stu-id="40e8a-215">Define the payment transaction structure for this model.</span></span>  
17. <span data-ttu-id="40e8a-216">No campo Nome, digite 'Pagamentos'.</span><span class="sxs-lookup"><span data-stu-id="40e8a-216">In the Name field, type 'Payments'.</span></span>
    * <span data-ttu-id="40e8a-217">Pagamentos</span><span class="sxs-lookup"><span data-stu-id="40e8a-217">Payments</span></span>  
18. <span data-ttu-id="40e8a-218">No campo Tipo de item, selecione 'Lista de Registro'.</span><span class="sxs-lookup"><span data-stu-id="40e8a-218">In the Item type field, select 'Record list'.</span></span>
19. <span data-ttu-id="40e8a-219">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="40e8a-219">Click Add.</span></span>
20. <span data-ttu-id="40e8a-220">No campo Descrição, insira 'Linhas de pagamento da mensagem atual'.</span><span class="sxs-lookup"><span data-stu-id="40e8a-220">In the Description field, enter 'Payment lines of the current message'.</span></span>
    * <span data-ttu-id="40e8a-221">Linhas de pagamento da mensagem atual</span><span class="sxs-lookup"><span data-stu-id="40e8a-221">Payment lines of the current message</span></span>  
21. <span data-ttu-id="40e8a-222">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="40e8a-222">Click New to open the drop dialog.</span></span>
22. <span data-ttu-id="40e8a-223">No campo Nome, digite 'Credor'.</span><span class="sxs-lookup"><span data-stu-id="40e8a-223">In the Name field, type 'Creditor'.</span></span>
    * <span data-ttu-id="40e8a-224">Credor</span><span class="sxs-lookup"><span data-stu-id="40e8a-224">Creditor</span></span>  
23. <span data-ttu-id="40e8a-225">No campo Tipo de item, selecione 'Registro'.</span><span class="sxs-lookup"><span data-stu-id="40e8a-225">In the Item type field, select 'Record'.</span></span>
24. <span data-ttu-id="40e8a-226">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="40e8a-226">Click Add.</span></span>
25. <span data-ttu-id="40e8a-227">No campo Descrição, insira "Participante ao qual um valor em dinheiro é devido".</span><span class="sxs-lookup"><span data-stu-id="40e8a-227">In the Description field, enter 'Party to which an amount of money is due.'.</span></span>
    * <span data-ttu-id="40e8a-228">Participante ao qual um valor em dinheiro é devido.</span><span class="sxs-lookup"><span data-stu-id="40e8a-228">Party to which an amount of money is due.</span></span>  
26. <span data-ttu-id="40e8a-229">Clique em Alternar referência de item.</span><span class="sxs-lookup"><span data-stu-id="40e8a-229">Click Switch item reference.</span></span>
27. <span data-ttu-id="40e8a-230">No campo Encontrar, digite "Participante".</span><span class="sxs-lookup"><span data-stu-id="40e8a-230">In the Find field, type 'Party'.</span></span>
    * <span data-ttu-id="40e8a-231">Participante</span><span class="sxs-lookup"><span data-stu-id="40e8a-231">Party</span></span>  
28. <span data-ttu-id="40e8a-232">Clique em Localizar próximo.</span><span class="sxs-lookup"><span data-stu-id="40e8a-232">Click Find next.</span></span>
29. <span data-ttu-id="40e8a-233">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="40e8a-233">Click OK.</span></span>
30. <span data-ttu-id="40e8a-234">No campo Encontrar, digite "Pagamentos".</span><span class="sxs-lookup"><span data-stu-id="40e8a-234">In the Find field, type 'Payments'.</span></span>
    * <span data-ttu-id="40e8a-235">Pagamentos</span><span class="sxs-lookup"><span data-stu-id="40e8a-235">Payments</span></span>  
31. <span data-ttu-id="40e8a-236">Clique em Localizar próximo.</span><span class="sxs-lookup"><span data-stu-id="40e8a-236">Click Find next.</span></span>
32. <span data-ttu-id="40e8a-237">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="40e8a-237">Click New to open the drop dialog.</span></span>
33. <span data-ttu-id="40e8a-238">No campo Nome, digite 'Devedor'.</span><span class="sxs-lookup"><span data-stu-id="40e8a-238">In the Name field, type 'Debtor'.</span></span>
    * <span data-ttu-id="40e8a-239">Devedor</span><span class="sxs-lookup"><span data-stu-id="40e8a-239">Debtor</span></span>  
34. <span data-ttu-id="40e8a-240">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="40e8a-240">Click Add.</span></span>
35. <span data-ttu-id="40e8a-241">No campo Descrição, insira "Participante que deve um valor em dinheiro ao credor (definitivo)".</span><span class="sxs-lookup"><span data-stu-id="40e8a-241">In the Description field, enter 'Party that owes an amount of money to the (ultimate) creditor.'.</span></span>
    * <span data-ttu-id="40e8a-242">Participante que deve um valor em dinheiro ao credor (definitivo).</span><span class="sxs-lookup"><span data-stu-id="40e8a-242">Party that owes an amount of money to the (ultimate) creditor.</span></span>  
36. <span data-ttu-id="40e8a-243">Clique em Alternar referência de item.</span><span class="sxs-lookup"><span data-stu-id="40e8a-243">Click Switch item reference.</span></span>
37. <span data-ttu-id="40e8a-244">No campo Encontrar, digite "Participante".</span><span class="sxs-lookup"><span data-stu-id="40e8a-244">In the Find field, type 'Party'.</span></span>
    * <span data-ttu-id="40e8a-245">Participante</span><span class="sxs-lookup"><span data-stu-id="40e8a-245">Party</span></span>  
38. <span data-ttu-id="40e8a-246">Clique em Localizar próximo.</span><span class="sxs-lookup"><span data-stu-id="40e8a-246">Click Find next.</span></span>
39. <span data-ttu-id="40e8a-247">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="40e8a-247">Click OK.</span></span>
40. <span data-ttu-id="40e8a-248">Clique em Localizar próximo.</span><span class="sxs-lookup"><span data-stu-id="40e8a-248">Click Find next.</span></span>
41. <span data-ttu-id="40e8a-249">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="40e8a-249">Click New to open the drop dialog.</span></span>
42. <span data-ttu-id="40e8a-250">No campo Nome, digite 'Descrição'.</span><span class="sxs-lookup"><span data-stu-id="40e8a-250">In the Name field, type 'Description'.</span></span>
    * <span data-ttu-id="40e8a-251">descrição</span><span class="sxs-lookup"><span data-stu-id="40e8a-251">Description</span></span>  
43. <span data-ttu-id="40e8a-252">No campo Tipo de item, selecione 'String'.</span><span class="sxs-lookup"><span data-stu-id="40e8a-252">In the Item type field, select 'String'.</span></span>
44. <span data-ttu-id="40e8a-253">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="40e8a-253">Click Add.</span></span>
45. <span data-ttu-id="40e8a-254">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="40e8a-254">Click New to open the drop dialog.</span></span>
46. <span data-ttu-id="40e8a-255">No campo Nome, digite 'Moeda'.</span><span class="sxs-lookup"><span data-stu-id="40e8a-255">In the Name field, type 'Currency'.</span></span>
    * <span data-ttu-id="40e8a-256">Moeda</span><span class="sxs-lookup"><span data-stu-id="40e8a-256">Currency</span></span>  
47. <span data-ttu-id="40e8a-257">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="40e8a-257">Click Add.</span></span>
48. <span data-ttu-id="40e8a-258">No campo Descrição, insira "Código de moeda".</span><span class="sxs-lookup"><span data-stu-id="40e8a-258">In the Description field, enter 'Currency code'.</span></span>
    * <span data-ttu-id="40e8a-259">Código de Moeda</span><span class="sxs-lookup"><span data-stu-id="40e8a-259">Currency code</span></span>  
49. <span data-ttu-id="40e8a-260">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="40e8a-260">Click New to open the drop dialog.</span></span>
50. <span data-ttu-id="40e8a-261">No campo Nome, digite 'Data da Transação'.</span><span class="sxs-lookup"><span data-stu-id="40e8a-261">In the Name field, type 'TransactionDate'.</span></span>
    * <span data-ttu-id="40e8a-262">Data da Transação</span><span class="sxs-lookup"><span data-stu-id="40e8a-262">TransactionDate</span></span>  
51. <span data-ttu-id="40e8a-263">No campo Tipo de item, selecione 'Data'.</span><span class="sxs-lookup"><span data-stu-id="40e8a-263">In the Item type field, select 'Date'.</span></span>
52. <span data-ttu-id="40e8a-264">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="40e8a-264">Click Add.</span></span>
53. <span data-ttu-id="40e8a-265">No campo Descrição, insira "Data da transação".</span><span class="sxs-lookup"><span data-stu-id="40e8a-265">In the Description field, enter 'Transaction date'.</span></span>
    * <span data-ttu-id="40e8a-266">Data da transação</span><span class="sxs-lookup"><span data-stu-id="40e8a-266">Transaction date</span></span>  
54. <span data-ttu-id="40e8a-267">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="40e8a-267">Click New to open the drop dialog.</span></span>
55. <span data-ttu-id="40e8a-268">No campo Nome, digite 'Quantia Indicada'.</span><span class="sxs-lookup"><span data-stu-id="40e8a-268">In the Name field, type 'InstructedAmount'.</span></span>
    * <span data-ttu-id="40e8a-269">Valor Instruído</span><span class="sxs-lookup"><span data-stu-id="40e8a-269">InstructedAmount</span></span>  
56. <span data-ttu-id="40e8a-270">No campo Tipo de item, selecione 'Real'.</span><span class="sxs-lookup"><span data-stu-id="40e8a-270">In the Item type field, select 'Real'.</span></span>
57. <span data-ttu-id="40e8a-271">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="40e8a-271">Click Add.</span></span>
58. <span data-ttu-id="40e8a-272">No campo Descrição, insira "O valor em dinheiro a ser movimentado entre o devedor e o credor, antes da dedução dos encargos".</span><span class="sxs-lookup"><span data-stu-id="40e8a-272">In the Description field, enter 'The amount of money to be moved between the debtor and creditor, before deduction of charges.</span></span> <span data-ttu-id="40e8a-273">O valor deve ser expresso na moeda definida pela parte que inicializou a transação.'.</span><span class="sxs-lookup"><span data-stu-id="40e8a-273">The amount should be expressed in the currency as ordered by the initiating party.'.</span></span>
    * <span data-ttu-id="40e8a-274">O valor em dinheiro a ser movido entre o devedor e o credor, antes da dedução dos encargos.</span><span class="sxs-lookup"><span data-stu-id="40e8a-274">The amount of money to be moved between the debtor and creditor, before deduction of charges.</span></span> <span data-ttu-id="40e8a-275">O valor deve ser expresso na moeda definida pela parte que inicializou a transação.</span><span class="sxs-lookup"><span data-stu-id="40e8a-275">The amount should be expressed in the currency as ordered by the initiating party.</span></span>  
59. <span data-ttu-id="40e8a-276">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="40e8a-276">Click New to open the drop dialog.</span></span>
60. <span data-ttu-id="40e8a-277">No campo Nome, digite 'End2EndID'.</span><span class="sxs-lookup"><span data-stu-id="40e8a-277">In the Name field, type 'End2EndID'.</span></span>
    * <span data-ttu-id="40e8a-278">End2EndID</span><span class="sxs-lookup"><span data-stu-id="40e8a-278">End2EndID</span></span>  
61. <span data-ttu-id="40e8a-279">No campo Tipo de item, selecione 'String'.</span><span class="sxs-lookup"><span data-stu-id="40e8a-279">In the Item type field, select 'String'.</span></span>
62. <span data-ttu-id="40e8a-280">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="40e8a-280">Click Add.</span></span>
63. <span data-ttu-id="40e8a-281">No campo Descrição, insira "A identificação exclusiva atribuída pelo participante que inicializou a transação".</span><span class="sxs-lookup"><span data-stu-id="40e8a-281">In the Description field, enter 'The unique identification assigned by the initiating party.</span></span> <span data-ttu-id="40e8a-282">Essa identificação é transmitida, inalterada, ao longo de toda a cadeia ponto-a-ponto.'.</span><span class="sxs-lookup"><span data-stu-id="40e8a-282">This identification is passed on, unchanged, throughout the entire end-to-end chain.'.</span></span>
    * <span data-ttu-id="40e8a-283">A identificação exclusiva designada pela parte que inicializou a transação.</span><span class="sxs-lookup"><span data-stu-id="40e8a-283">The unique identification assigned by the initiating party.</span></span> <span data-ttu-id="40e8a-284">Essa identificação é transmitida, inalterada, ao longo de toda a cadeia ponto-a-ponto.</span><span class="sxs-lookup"><span data-stu-id="40e8a-284">This identification is passed on, unchanged, throughout the entire end-to-end chain.</span></span>  
64. <span data-ttu-id="40e8a-285">No campo Nome, digite 'Modelo de Pagamento'.</span><span class="sxs-lookup"><span data-stu-id="40e8a-285">In the Name field, type 'PaymentModel'.</span></span>
    * <span data-ttu-id="40e8a-286">O nome do PaymentModel se alinha a interfaces predefinidas de formulários de pagamento.</span><span class="sxs-lookup"><span data-stu-id="40e8a-286">The PaymentModel name aligns with predefined interfaces of payment forms.</span></span>  
65. <span data-ttu-id="40e8a-287">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="40e8a-287">Click Save.</span></span>
66. <span data-ttu-id="40e8a-288">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="40e8a-288">Close the page.</span></span>

