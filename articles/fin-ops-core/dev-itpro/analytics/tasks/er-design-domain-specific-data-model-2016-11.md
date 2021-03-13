---
title: ER Projetar modelo de dados de domínio específico
description: Este tópico descreve como criar uma nova configuração de relatório eletrônico (ER) que contém um modelo de dados para documentos de pagamento eletrônico.
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
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1eb2c6e5b5f186fb6db7c32a9982807274e5ea1b
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/30/2021
ms.locfileid: "5092682"
---
# <a name="er-design-domain-specific-data-model"></a><span data-ttu-id="91e33-103">ER Projetar modelo de dados de domínio específico</span><span class="sxs-lookup"><span data-stu-id="91e33-103">ER Design domain specific data model</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="91e33-104">As etapas a seguir explicam como um usuário no papel de Administrador do Sistema ou Desenvolvedor de Relatório Eletrônico pode criar uma nova configuração de Relatório Eletrônico (RE) que contem um modelo de dados para os documentos de pagamento eletrônico.</span><span class="sxs-lookup"><span data-stu-id="91e33-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can create a new Electronic reporting (ER) configuration that contains a data model for electronic payment documents.</span></span> <span data-ttu-id="91e33-105">Esse modelo de dados será usado posteriormente como uma fonte de dados quando você criar o formato dos documentos de pagamento.</span><span class="sxs-lookup"><span data-stu-id="91e33-105">This data model will later be used as a data source when you create the format of the payment documents.</span></span>

<span data-ttu-id="91e33-106">Neste exemplo, será criado uma configuração para a empresa de exemplo, Litware, Inc. Essas etapas podem ser executadas em qualquer empresa, uma vez que configurações de ER são compartilhadas entre todas as empresas.</span><span class="sxs-lookup"><span data-stu-id="91e33-106">In this example, you will create a configuration for sample company, Litware, Inc. These steps can be performed in any company as ER configurations are shared among companies.</span></span> <span data-ttu-id="91e33-107">Para completar essas etapas, você deve primeiro completar as etapas do procedimento "Criar um provedor de configuração e marcá-lo como ativo".</span><span class="sxs-lookup"><span data-stu-id="91e33-107">To complete these steps, you must first complete the steps in the "Create a configuration provider and mark it as active" procedure.</span></span>

1. <span data-ttu-id="91e33-108">Ir para Administração da organização > Espaços de trabalho > Relatório eletrônico.</span><span class="sxs-lookup"><span data-stu-id="91e33-108">Go to Organization administration > Workspaces > Electronic reporting.</span></span>

    <span data-ttu-id="91e33-109">Selecione o provedor de configuração para a empresa de exemplo, "Litware, Inc."</span><span class="sxs-lookup"><span data-stu-id="91e33-109">Select the configuration provider for sample company, 'Litware, Inc.'</span></span> <span data-ttu-id="91e33-110">Se não visualizar este provedor de configuração, você deve primeiro concluir as etapas do procedimento "Criar um provedor de configuração e marcá-lo como ativo".</span><span class="sxs-lookup"><span data-stu-id="91e33-110">If you don't see this configuration provider, you must first complete the steps in the "Create a configuration provider and mark it as active" procedure.</span></span>  
    
2. <span data-ttu-id="91e33-111">Clique em Configurações de relatórios.</span><span class="sxs-lookup"><span data-stu-id="91e33-111">Click Reporting configurations.</span></span>

    <span data-ttu-id="91e33-112">Você irá criar uma configuração que contém um modelo de dados para documentos de pagamento eletrônico.</span><span class="sxs-lookup"><span data-stu-id="91e33-112">You will create a configuration that contains a data model for electronic payment documents.</span></span> <span data-ttu-id="91e33-113">Este modelo de dados será usado posteriormente como uma base de dados quando você criar o formato para os documentos de pagamento.</span><span class="sxs-lookup"><span data-stu-id="91e33-113">This data model will be used later as a data source when you create the format for the payment documents.</span></span>  

## <a name="create-a-new-data-model-configuration"></a><span data-ttu-id="91e33-114">Criar uma nova configuração de modelo de dados</span><span class="sxs-lookup"><span data-stu-id="91e33-114">Create a new data model configuration</span></span>
1. <span data-ttu-id="91e33-115">Clique em Criar configuração para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="91e33-115">Click Create configuration to open the drop dialog.</span></span>
2. <span data-ttu-id="91e33-116">No campo Nome, digite 'Pagamentos (modelo simplificado)'.</span><span class="sxs-lookup"><span data-stu-id="91e33-116">In the Name field, type 'Payments (simplified model)'.</span></span>
3. <span data-ttu-id="91e33-117">No campo Descrição, digite 'Configuração do modelo de pagamento'.</span><span class="sxs-lookup"><span data-stu-id="91e33-117">In the Description field, type 'Payment model configuration'.</span></span>

    <span data-ttu-id="91e33-118">O provedor de configuração ativo é automaticamente inserido aqui.</span><span class="sxs-lookup"><span data-stu-id="91e33-118">The active configuration provider is automatically entered here.</span></span> <span data-ttu-id="91e33-119">Este provedor será capaz de manter essa configuração.</span><span class="sxs-lookup"><span data-stu-id="91e33-119">This provider will be able to maintain this configuration.</span></span> <span data-ttu-id="91e33-120">Outros provedores podem usar esta configuração, mas não poderão mantê-la.</span><span class="sxs-lookup"><span data-stu-id="91e33-120">Other providers can use this configuration, but will not be able to maintain it.</span></span>  

4. <span data-ttu-id="91e33-121">Clique no botão "Criar configuração" para completar a tarefa de criação de configuração</span><span class="sxs-lookup"><span data-stu-id="91e33-121">Click 'Create configuration' button to complete the configuration creation task</span></span>

## <a name="create-a-data-model"></a><span data-ttu-id="91e33-122">Criar um modelo de dados</span><span class="sxs-lookup"><span data-stu-id="91e33-122">Create a data model</span></span>
<span data-ttu-id="91e33-123">Você está criando um novo modelo de dados para a configuração selecionada.</span><span class="sxs-lookup"><span data-stu-id="91e33-123">You're creating a new data model for the selected configuration.</span></span> <span data-ttu-id="91e33-124">Essa versão de configuração terá um status de Rascunho.</span><span class="sxs-lookup"><span data-stu-id="91e33-124">This configuration version will have a status of Draft.</span></span>  
1. <span data-ttu-id="91e33-125">Clique em Designer.</span><span class="sxs-lookup"><span data-stu-id="91e33-125">Click Designer.</span></span>

## <a name="define-the-structure-of-a-party-participating-in-a-payment-process"></a><span data-ttu-id="91e33-126">Definir a estrutura de participação de um participante em um processo de pagamento</span><span class="sxs-lookup"><span data-stu-id="91e33-126">Define the structure of a party participating in a payment process</span></span>
1. <span data-ttu-id="91e33-127">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="91e33-127">Click New to open the drop dialog.</span></span>
2. <span data-ttu-id="91e33-128">No campo Nome, digite "Participante".</span><span class="sxs-lookup"><span data-stu-id="91e33-128">In the Name field, type 'Party'.</span></span>
3. <span data-ttu-id="91e33-129">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="91e33-129">Click Add.</span></span>
4. <span data-ttu-id="91e33-130">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="91e33-130">Click New to open the drop dialog.</span></span>
5. <span data-ttu-id="91e33-131">No campo Nome, digite 'Nome'.</span><span class="sxs-lookup"><span data-stu-id="91e33-131">In the Name field, type 'Name'.</span></span>
6. <span data-ttu-id="91e33-132">No campo Tipo de item, selecione 'String'.</span><span class="sxs-lookup"><span data-stu-id="91e33-132">In the Item type field, select 'String'.</span></span>
7. <span data-ttu-id="91e33-133">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="91e33-133">Click Add.</span></span>
8. <span data-ttu-id="91e33-134">No campo Encontrar, digite "Participante".</span><span class="sxs-lookup"><span data-stu-id="91e33-134">In the Find field, type 'Party'.</span></span>
9. <span data-ttu-id="91e33-135">Clique em Localizar anterior.</span><span class="sxs-lookup"><span data-stu-id="91e33-135">Click Find previous.</span></span>

## <a name="define-the-bank-structure-for-this-model"></a><span data-ttu-id="91e33-136">Definir a estrutura do banco para este modelo</span><span class="sxs-lookup"><span data-stu-id="91e33-136">Define the bank structure for this model</span></span>
1. <span data-ttu-id="91e33-137">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="91e33-137">Click New to open the drop dialog.</span></span>
2. <span data-ttu-id="91e33-138">No campo Nome, digite 'Agente'.</span><span class="sxs-lookup"><span data-stu-id="91e33-138">In the Name field, type 'Agent'.</span></span>
3. <span data-ttu-id="91e33-139">No campo Tipo de item, selecione 'Registro'.</span><span class="sxs-lookup"><span data-stu-id="91e33-139">In the Item type field, select 'Record'.</span></span>
4. <span data-ttu-id="91e33-140">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="91e33-140">Click Add.</span></span>
5. <span data-ttu-id="91e33-141">No campo Descrição, insira "Instituição financeira (por exemplo, um banco) que mantém uma conta para o participante (devedor/credor).".</span><span class="sxs-lookup"><span data-stu-id="91e33-141">In the Description field, enter 'Financial institution (for instance, a bank) servicing an account for the party (debtor/creditor).'.</span></span>

    <span data-ttu-id="91e33-142">Instituição financeira (por exemplo, um banco) que mantém uma conta para o participante (devedor/credor).</span><span class="sxs-lookup"><span data-stu-id="91e33-142">Financial institution (for instance, a bank) servicing an account for the party (debtor/creditor).</span></span>  

6. <span data-ttu-id="91e33-143">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="91e33-143">Click New to open the drop dialog.</span></span>
7. <span data-ttu-id="91e33-144">No campo Nome, digite 'Nome'.</span><span class="sxs-lookup"><span data-stu-id="91e33-144">In the Name field, type 'Name'.</span></span> 
8. <span data-ttu-id="91e33-145">No campo Tipo de item, selecione 'String'.</span><span class="sxs-lookup"><span data-stu-id="91e33-145">In the Item type field, select 'String'.</span></span>
9. <span data-ttu-id="91e33-146">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="91e33-146">Click Add.</span></span>
10. <span data-ttu-id="91e33-147">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="91e33-147">Click New to open the drop dialog.</span></span>
11. <span data-ttu-id="91e33-148">No campo Nome, digite 'SWIFT'.</span><span class="sxs-lookup"><span data-stu-id="91e33-148">In the Name field, type 'SWIFT'.</span></span>
12. <span data-ttu-id="91e33-149">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="91e33-149">Click Add.</span></span>
13. <span data-ttu-id="91e33-150">No campo Descrição, insira "Código de identificação do banco".</span><span class="sxs-lookup"><span data-stu-id="91e33-150">In the Description field, enter 'Bank identification code'.</span></span> 
14. <span data-ttu-id="91e33-151">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="91e33-151">Click New to open the drop dialog.</span></span>
15. <span data-ttu-id="91e33-152">No campo Nome, digite 'Número Identificador do banco'.</span><span class="sxs-lookup"><span data-stu-id="91e33-152">In the Name field, type 'RoutingNumber'.</span></span>
16. <span data-ttu-id="91e33-153">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="91e33-153">Click Add.</span></span>
17. <span data-ttu-id="91e33-154">No campo Descrição, insira "Número identificador do banco".</span><span class="sxs-lookup"><span data-stu-id="91e33-154">In the Description field, enter 'Routing number'.</span></span>
18. <span data-ttu-id="91e33-155">Clique em Localizar anterior.</span><span class="sxs-lookup"><span data-stu-id="91e33-155">Click Find previous.</span></span>

## <a name="define-the-bank-account-structure-for-this-model"></a><span data-ttu-id="91e33-156">Definir a estrutura da conta bancária para este modelo</span><span class="sxs-lookup"><span data-stu-id="91e33-156">Define the bank account structure for this model</span></span>
1. <span data-ttu-id="91e33-157">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="91e33-157">Click New to open the drop dialog.</span></span>
2. <span data-ttu-id="91e33-158">No campo Nome, digite 'Conta'.</span><span class="sxs-lookup"><span data-stu-id="91e33-158">In the Name field, type 'Account'.</span></span> 
3. <span data-ttu-id="91e33-159">No campo Tipo de item, selecione 'Registro'.</span><span class="sxs-lookup"><span data-stu-id="91e33-159">In the Item type field, select 'Record'.</span></span>
4. <span data-ttu-id="91e33-160">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="91e33-160">Click Add.</span></span>
5. <span data-ttu-id="91e33-161">No campo Descrição, insira "Identificação de uma conta do participante em uma instituição financeira (por exemplo, um banco)".</span><span class="sxs-lookup"><span data-stu-id="91e33-161">In the Description field, enter 'Identification of an account of a party in a financial institution (for instance, a bank).'.</span></span>

    <span data-ttu-id="91e33-162">Identificação de uma conta do participante em uma instituição financeira (por exemplo, um banco).</span><span class="sxs-lookup"><span data-stu-id="91e33-162">Identification of an account of a party in a financial institution (for instance, a bank).</span></span>  

6. <span data-ttu-id="91e33-163">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="91e33-163">Click New to open the drop dialog.</span></span>
7. <span data-ttu-id="91e33-164">No campo Nome, digite 'Moeda'.</span><span class="sxs-lookup"><span data-stu-id="91e33-164">In the Name field, type 'Currency'.</span></span> 
8. <span data-ttu-id="91e33-165">No campo Tipo de item, selecione 'String'.</span><span class="sxs-lookup"><span data-stu-id="91e33-165">In the Item type field, select 'String'.</span></span>
9. <span data-ttu-id="91e33-166">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="91e33-166">Click Add.</span></span>
10. <span data-ttu-id="91e33-167">No campo Descrição, insira "Código de moeda".</span><span class="sxs-lookup"><span data-stu-id="91e33-167">In the Description field, enter 'Currency code'.</span></span>
11. <span data-ttu-id="91e33-168">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="91e33-168">Click New to open the drop dialog.</span></span>
12. <span data-ttu-id="91e33-169">No campo Nome, digite 'Número'.</span><span class="sxs-lookup"><span data-stu-id="91e33-169">In the Name field, type 'Number'.</span></span> 
13. <span data-ttu-id="91e33-170">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="91e33-170">Click Add.</span></span>
14. <span data-ttu-id="91e33-171">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="91e33-171">Click New to open the drop dialog.</span></span>
15. <span data-ttu-id="91e33-172">No campo Nome, digite 'IBAN'.</span><span class="sxs-lookup"><span data-stu-id="91e33-172">In the Name field, type 'IBAN'.</span></span> 
16. <span data-ttu-id="91e33-173">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="91e33-173">Click Add.</span></span>
17. <span data-ttu-id="91e33-174">No campo Descrição, insira "Número de conta bancária internacional".</span><span class="sxs-lookup"><span data-stu-id="91e33-174">In the Description field, enter 'International bank account number'.</span></span>

## <a name="define-the-payment-message-structure-for-credit-transfer-payment-type"></a><span data-ttu-id="91e33-175">Definir a estrutura de mensagem de pagamento para o tipo de pagamento de transferência de crédito</span><span class="sxs-lookup"><span data-stu-id="91e33-175">Define the payment message structure for credit transfer payment type</span></span>
1. <span data-ttu-id="91e33-176">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="91e33-176">Click New to open the drop dialog.</span></span>
2. <span data-ttu-id="91e33-177">No campo Novo nó como um, insira "Raiz do modelo".</span><span class="sxs-lookup"><span data-stu-id="91e33-177">In the New node as a field, enter 'Model root'.</span></span>
3. <span data-ttu-id="91e33-178">No campo Nome, digite 'Início da Transferência de Crédito do Cliente'.</span><span class="sxs-lookup"><span data-stu-id="91e33-178">In the Name field, type 'CustomerCreditTransferInitiation'.</span></span>
4. <span data-ttu-id="91e33-179">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="91e33-179">Click Add.</span></span>
5. <span data-ttu-id="91e33-180">No campo Encontrar, digite "CustomerCreditTransferInitiation".</span><span class="sxs-lookup"><span data-stu-id="91e33-180">In the Find field, type 'CustomerCreditTransferInitiation'.</span></span> 
6. <span data-ttu-id="91e33-181">Clique em Localizar anterior.</span><span class="sxs-lookup"><span data-stu-id="91e33-181">Click Find previous.</span></span>
7. <span data-ttu-id="91e33-182">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="91e33-182">Click New to open the drop dialog.</span></span>
8. <span data-ttu-id="91e33-183">No campo Nome, digite 'Identificação da Mensagem'.</span><span class="sxs-lookup"><span data-stu-id="91e33-183">In the Name field, type 'MessageIdentification'.</span></span> 
9. <span data-ttu-id="91e33-184">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="91e33-184">Click Add.</span></span>
10. <span data-ttu-id="91e33-185">No campo Descrição, insira "A referência ponto a ponto definida pelo participante instrutor (e enviada ao próximo participante) para identificar uma mensagem".</span><span class="sxs-lookup"><span data-stu-id="91e33-185">In the Description field, enter 'The point-to-point reference assigned by the instructing party (and sent to the next party) to identify a message.'.</span></span>

    <span data-ttu-id="91e33-186">A referência ponto a ponto atribuída pela parte instrutora (e enviada para o próximo participante) para identificar uma mensagem.</span><span class="sxs-lookup"><span data-stu-id="91e33-186">The point-to-point reference assigned by the instructing party (and sent to the next party) to identify a message.</span></span>  

11. <span data-ttu-id="91e33-187">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="91e33-187">Click New to open the drop dialog.</span></span>
12. <span data-ttu-id="91e33-188">No campo Nome, digite 'ProcessamentoDataHora'.</span><span class="sxs-lookup"><span data-stu-id="91e33-188">In the Name field, type 'ProcessingDateTime'.</span></span>
13. <span data-ttu-id="91e33-189">No campo Tipo de item, selecione 'DataHora'.</span><span class="sxs-lookup"><span data-stu-id="91e33-189">In the Item type field, select 'DateTime'.</span></span>
14. <span data-ttu-id="91e33-190">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="91e33-190">Click Add.</span></span>
15. <span data-ttu-id="91e33-191">No campo Descrição, insira "Data e hora em que a mensagem de pagamento foi criada".</span><span class="sxs-lookup"><span data-stu-id="91e33-191">In the Description field, enter 'Date and time at which the payment message was created.'.</span></span> 
16. <span data-ttu-id="91e33-192">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="91e33-192">Click New to open the drop dialog.</span></span>

    <span data-ttu-id="91e33-193">Defina a estrutura da transação de pagamento para este modelo.</span><span class="sxs-lookup"><span data-stu-id="91e33-193">Define the payment transaction structure for this model.</span></span>  

17. <span data-ttu-id="91e33-194">No campo Nome, digite 'Pagamentos'.</span><span class="sxs-lookup"><span data-stu-id="91e33-194">In the Name field, type 'Payments'.</span></span>
18. <span data-ttu-id="91e33-195">No campo Tipo de item, selecione 'Lista de Registro'.</span><span class="sxs-lookup"><span data-stu-id="91e33-195">In the Item type field, select 'Record list'.</span></span>
19. <span data-ttu-id="91e33-196">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="91e33-196">Click Add.</span></span>
20. <span data-ttu-id="91e33-197">No campo Descrição, insira 'Linhas de pagamento da mensagem atual'.</span><span class="sxs-lookup"><span data-stu-id="91e33-197">In the Description field, enter 'Payment lines of the current message'.</span></span>
21. <span data-ttu-id="91e33-198">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="91e33-198">Click New to open the drop dialog.</span></span>
22. <span data-ttu-id="91e33-199">No campo Nome, digite 'Credor'.</span><span class="sxs-lookup"><span data-stu-id="91e33-199">In the Name field, type 'Creditor'.</span></span> 
23. <span data-ttu-id="91e33-200">No campo Tipo de item, selecione 'Registro'.</span><span class="sxs-lookup"><span data-stu-id="91e33-200">In the Item type field, select 'Record'.</span></span>
24. <span data-ttu-id="91e33-201">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="91e33-201">Click Add.</span></span>
25. <span data-ttu-id="91e33-202">No campo Descrição, insira "Participante ao qual um valor em dinheiro é devido".</span><span class="sxs-lookup"><span data-stu-id="91e33-202">In the Description field, enter 'Party to which an amount of money is due.'.</span></span> 
26. <span data-ttu-id="91e33-203">Clique em Alternar referência de item.</span><span class="sxs-lookup"><span data-stu-id="91e33-203">Click Switch item reference.</span></span>
27. <span data-ttu-id="91e33-204">No campo Encontrar, digite "Participante".</span><span class="sxs-lookup"><span data-stu-id="91e33-204">In the Find field, type 'Party'.</span></span>
28. <span data-ttu-id="91e33-205">Clique em Localizar próximo.</span><span class="sxs-lookup"><span data-stu-id="91e33-205">Click Find next.</span></span>
29. <span data-ttu-id="91e33-206">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="91e33-206">Click OK.</span></span>
30. <span data-ttu-id="91e33-207">No campo Encontrar, digite "Pagamentos".</span><span class="sxs-lookup"><span data-stu-id="91e33-207">In the Find field, type 'Payments'.</span></span>
31. <span data-ttu-id="91e33-208">Clique em Localizar próximo.</span><span class="sxs-lookup"><span data-stu-id="91e33-208">Click Find next.</span></span>
32. <span data-ttu-id="91e33-209">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="91e33-209">Click New to open the drop dialog.</span></span>
33. <span data-ttu-id="91e33-210">No campo Nome, digite 'Devedor'.</span><span class="sxs-lookup"><span data-stu-id="91e33-210">In the Name field, type 'Debtor'.</span></span> 
34. <span data-ttu-id="91e33-211">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="91e33-211">Click Add.</span></span>
35. <span data-ttu-id="91e33-212">No campo Descrição, insira "Participante que deve um valor em dinheiro ao credor (definitivo)".</span><span class="sxs-lookup"><span data-stu-id="91e33-212">In the Description field, enter 'Party that owes an amount of money to the (ultimate) creditor.'.</span></span>
36. <span data-ttu-id="91e33-213">Clique em Alternar referência de item.</span><span class="sxs-lookup"><span data-stu-id="91e33-213">Click Switch item reference.</span></span>
37. <span data-ttu-id="91e33-214">No campo Encontrar, digite "Participante".</span><span class="sxs-lookup"><span data-stu-id="91e33-214">In the Find field, type 'Party'.</span></span>
38. <span data-ttu-id="91e33-215">Clique em Localizar próximo.</span><span class="sxs-lookup"><span data-stu-id="91e33-215">Click Find next.</span></span>
39. <span data-ttu-id="91e33-216">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="91e33-216">Click OK.</span></span>
40. <span data-ttu-id="91e33-217">Clique em Localizar próximo.</span><span class="sxs-lookup"><span data-stu-id="91e33-217">Click Find next.</span></span>
41. <span data-ttu-id="91e33-218">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="91e33-218">Click New to open the drop dialog.</span></span>
42. <span data-ttu-id="91e33-219">No campo Nome, digite 'Descrição'.</span><span class="sxs-lookup"><span data-stu-id="91e33-219">In the Name field, type 'Description'.</span></span>
43. <span data-ttu-id="91e33-220">No campo Tipo de item, selecione 'String'.</span><span class="sxs-lookup"><span data-stu-id="91e33-220">In the Item type field, select 'String'.</span></span>
44. <span data-ttu-id="91e33-221">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="91e33-221">Click Add.</span></span>
45. <span data-ttu-id="91e33-222">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="91e33-222">Click New to open the drop dialog.</span></span>
46. <span data-ttu-id="91e33-223">No campo Nome, digite 'Moeda'.</span><span class="sxs-lookup"><span data-stu-id="91e33-223">In the Name field, type 'Currency'.</span></span>
47. <span data-ttu-id="91e33-224">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="91e33-224">Click Add.</span></span>
48. <span data-ttu-id="91e33-225">No campo Descrição, insira "Código de moeda".</span><span class="sxs-lookup"><span data-stu-id="91e33-225">In the Description field, enter 'Currency code'.</span></span>
49. <span data-ttu-id="91e33-226">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="91e33-226">Click New to open the drop dialog.</span></span>
50. <span data-ttu-id="91e33-227">No campo Nome, digite 'Data da Transação'.</span><span class="sxs-lookup"><span data-stu-id="91e33-227">In the Name field, type 'TransactionDate'.</span></span> 
51. <span data-ttu-id="91e33-228">No campo Tipo de item, selecione 'Data'.</span><span class="sxs-lookup"><span data-stu-id="91e33-228">In the Item type field, select 'Date'.</span></span>
52. <span data-ttu-id="91e33-229">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="91e33-229">Click Add.</span></span>
53. <span data-ttu-id="91e33-230">No campo Descrição, insira "Data da transação".</span><span class="sxs-lookup"><span data-stu-id="91e33-230">In the Description field, enter 'Transaction date'.</span></span> 
54. <span data-ttu-id="91e33-231">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="91e33-231">Click New to open the drop dialog.</span></span>
55. <span data-ttu-id="91e33-232">No campo Nome, digite 'Quantia Indicada'.</span><span class="sxs-lookup"><span data-stu-id="91e33-232">In the Name field, type 'InstructedAmount'.</span></span>  
56. <span data-ttu-id="91e33-233">No campo Tipo de item, selecione 'Real'.</span><span class="sxs-lookup"><span data-stu-id="91e33-233">In the Item type field, select 'Real'.</span></span>
57. <span data-ttu-id="91e33-234">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="91e33-234">Click Add.</span></span>
58. <span data-ttu-id="91e33-235">No campo Descrição, insira "O valor em dinheiro a ser movimentado entre o devedor e o credor, antes da dedução dos encargos".</span><span class="sxs-lookup"><span data-stu-id="91e33-235">In the Description field, enter 'The amount of money to be moved between the debtor and creditor, before deduction of charges.</span></span> <span data-ttu-id="91e33-236">O valor deve ser expresso na moeda definida pela parte que inicializou a transação.'.</span><span class="sxs-lookup"><span data-stu-id="91e33-236">The amount should be expressed in the currency as ordered by the initiating party.'.</span></span>

    <span data-ttu-id="91e33-237">O valor em dinheiro a ser movido entre o devedor e o credor, antes da dedução dos encargos.</span><span class="sxs-lookup"><span data-stu-id="91e33-237">The amount of money to be moved between the debtor and creditor, before deduction of charges.</span></span> <span data-ttu-id="91e33-238">O valor deve ser expresso na moeda definida pela parte que inicializou a transação.</span><span class="sxs-lookup"><span data-stu-id="91e33-238">The amount should be expressed in the currency as ordered by the initiating party.</span></span>  

59. <span data-ttu-id="91e33-239">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="91e33-239">Click New to open the drop dialog.</span></span>
60. <span data-ttu-id="91e33-240">No campo Nome, digite 'End2EndID'.</span><span class="sxs-lookup"><span data-stu-id="91e33-240">In the Name field, type 'End2EndID'.</span></span> 
61. <span data-ttu-id="91e33-241">No campo Tipo de item, selecione 'String'.</span><span class="sxs-lookup"><span data-stu-id="91e33-241">In the Item type field, select 'String'.</span></span>
62. <span data-ttu-id="91e33-242">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="91e33-242">Click Add.</span></span>
63. <span data-ttu-id="91e33-243">No campo Descrição, insira "A identificação exclusiva atribuída pelo participante que inicializou a transação".</span><span class="sxs-lookup"><span data-stu-id="91e33-243">In the Description field, enter 'The unique identification assigned by the initiating party.</span></span> <span data-ttu-id="91e33-244">Essa identificação é transmitida, inalterada, ao longo de toda a cadeia ponto-a-ponto.'.</span><span class="sxs-lookup"><span data-stu-id="91e33-244">This identification is passed on, unchanged, throughout the entire end-to-end chain.'.</span></span> 
64. <span data-ttu-id="91e33-245">No campo Nome, digite 'Modelo de Pagamento'.</span><span class="sxs-lookup"><span data-stu-id="91e33-245">In the Name field, type 'PaymentModel'.</span></span>

    <span data-ttu-id="91e33-246">O nome do PaymentModel se alinha a interfaces predefinidas de formulários de pagamento.</span><span class="sxs-lookup"><span data-stu-id="91e33-246">The PaymentModel name aligns with predefined interfaces of payment forms.</span></span>  

65. <span data-ttu-id="91e33-247">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="91e33-247">Click Save.</span></span>
66. <span data-ttu-id="91e33-248">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="91e33-248">Close the page.</span></span>

