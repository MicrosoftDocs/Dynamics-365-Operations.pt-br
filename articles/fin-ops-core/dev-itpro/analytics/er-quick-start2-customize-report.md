---
title: Ajustar um formato de ER para gerar um documento eletrônico personalizado
description: Este tópico explica como ajustar um formato de relatório eletrônico (ER) fornecido pela Microsoft para gerar um documento eletrônico personalizado.
author: NickSelin
ms.date: 06/22/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERParameters, ERDataModelDesigner, ERModelMappingTable, ERModelMappingDesigner, EROperationDesigner, ERVendorTable
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 60b318ab03bc1bb47517a206e8b2afd9c13cf273
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/13/2021
ms.locfileid: "5891710"
---
# <a name="adjust-an-er-format-to-generate-a-custom-electronic-document"></a><span data-ttu-id="d4bff-103">Ajustar um formato de ER para gerar um documento eletrônico personalizado</span><span class="sxs-lookup"><span data-stu-id="d4bff-103">Adjust an ER format to generate a custom electronic document</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="d4bff-104">Os procedimentos descritos neste tópico explicam como um usuário que tem a função de Administrador do Sistema ou de Consultor Funcional de Relatório Eletrônico pode executar estas tarefas:</span><span class="sxs-lookup"><span data-stu-id="d4bff-104">The procedures in this topic explain how a user in the System Administrator or Electronic Reporting Functional Consultant role can perform these tasks:</span></span>

- <span data-ttu-id="d4bff-105">Configurar parâmetros para a [estrutura de relatórios eletrônicos (ER)](general-electronic-reporting.md).</span><span class="sxs-lookup"><span data-stu-id="d4bff-105">Configure parameters for the [Electronic reporting (ER) framework](general-electronic-reporting.md).</span></span>
- <span data-ttu-id="d4bff-106">Importar as configurações de ER fornecidas pela Microsoft e utilizadas para gerar um arquivo de pagamento enquanto um [pagamento de fornecedor](../../../finance/cash-bank-management/tasks/vendor-payment-overview.md) está sendo processado.</span><span class="sxs-lookup"><span data-stu-id="d4bff-106">Import ER configurations that are provided by Microsoft and used to generate a payment file while a [vendor payment](../../../finance/cash-bank-management/tasks/vendor-payment-overview.md) is being processed.</span></span>
- <span data-ttu-id="d4bff-107">Criar uma versão personalizada de uma configuração do formato de ER padrão fornecida pela Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d4bff-107">Create a custom version of a standard ER format configuration that is provided by Microsoft.</span></span>
- <span data-ttu-id="d4bff-108">Modificar a configuração do formato de ER personalizado para gerar arquivos de pagamento que atendam aos requisitos de um determinado banco.</span><span class="sxs-lookup"><span data-stu-id="d4bff-108">Modify the custom ER format configuration so that it generates payment files that meets the requirements of a specific bank.</span></span>
- <span data-ttu-id="d4bff-109">Adotar as alterações feitas na configuração do formato de ER padrão na configuração do formato de ER personalizado.</span><span class="sxs-lookup"><span data-stu-id="d4bff-109">Adopt changes that are made to the standard ER format configuration in the custom ER format configuration.</span></span>

<span data-ttu-id="d4bff-110">Todos os procedimentos a seguir podem ser feitos na empresa **GBSI**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-110">All the following procedures can be done in the **GBSI** company.</span></span> <span data-ttu-id="d4bff-111">Nenhum código é necessário.</span><span class="sxs-lookup"><span data-stu-id="d4bff-111">No coding is required.</span></span>

- [<span data-ttu-id="d4bff-112">Configurar a estrutura de ER</span><span class="sxs-lookup"><span data-stu-id="d4bff-112">Configure the ER framework</span></span>](#ConfigureFramework)

    - [<span data-ttu-id="d4bff-113">Configurar parâmetros de ER</span><span class="sxs-lookup"><span data-stu-id="d4bff-113">Configure ER parameters</span></span>](#ConfigureParameters)
    - [<span data-ttu-id="d4bff-114">Ativar um provedor de configuração de ER</span><span class="sxs-lookup"><span data-stu-id="d4bff-114">Activate an ER configuration provider</span></span>](#ActivateProvider)

        - [<span data-ttu-id="d4bff-115">Examinar a lista de provedores de configuração de ER</span><span class="sxs-lookup"><span data-stu-id="d4bff-115">Review the list of ER configuration providers</span></span>](#ReviewProvidersList)
        - [<span data-ttu-id="d4bff-116">Adicionar um novo provedor de configuração de ER</span><span class="sxs-lookup"><span data-stu-id="d4bff-116">Add a new ER configuration provider</span></span>](#ActivateProvider)
        - [<span data-ttu-id="d4bff-117">Ativar um provedor de configuração de ER</span><span class="sxs-lookup"><span data-stu-id="d4bff-117">Activate an ER configuration provider</span></span>](#ActivateAddedProvider)

- [<span data-ttu-id="d4bff-118">Importar as configurações do formato de ER padrão</span><span class="sxs-lookup"><span data-stu-id="d4bff-118">Import the standard ER format configurations</span></span>](#ImportERSolution1)

    - [<span data-ttu-id="d4bff-119">Importar as configurações de ER padrão</span><span class="sxs-lookup"><span data-stu-id="d4bff-119">Import the standard ER configurations</span></span>](#ImportERFormat1)
    - [<span data-ttu-id="d4bff-120">Examinar as configurações de ER importadas</span><span class="sxs-lookup"><span data-stu-id="d4bff-120">Review the imported ER configurations</span></span>](#ReviewImportedERSolution)

- [<span data-ttu-id="d4bff-121">Preparar um pagamento de fornecedor para processamento</span><span class="sxs-lookup"><span data-stu-id="d4bff-121">Prepare a vendor payment for processing</span></span>](#PrepareVendorPayment)

    - [<span data-ttu-id="d4bff-122">Adicionar informações bancárias de uma conta de fornecedor</span><span class="sxs-lookup"><span data-stu-id="d4bff-122">Add bank information for a vendor account</span></span>](#AddBankAccount)
    - [<span data-ttu-id="d4bff-123">Inserir um pagamento de fornecedor</span><span class="sxs-lookup"><span data-stu-id="d4bff-123">Enter a vendor payment</span></span>](#EnterVendorPayment)

- [<span data-ttu-id="d4bff-124">Processar um pagamento de fornecedor usando o formato de ER padrão</span><span class="sxs-lookup"><span data-stu-id="d4bff-124">Process a vendor payment by using the standard ER format</span></span>](#ProcessVendorPayment1)

    - [<span data-ttu-id="d4bff-125">Configurar o método de pagamento eletrônico</span><span class="sxs-lookup"><span data-stu-id="d4bff-125">Set up the electronic payment method</span></span>](#ConfigureMethodOfPayment1)
    - [<span data-ttu-id="d4bff-126">Processar um pagamento de fornecedor</span><span class="sxs-lookup"><span data-stu-id="d4bff-126">Process a vendor payment</span></span>](#ProcessPayment1)

- [<span data-ttu-id="d4bff-127">Personalizar o formato de ER padrão</span><span class="sxs-lookup"><span data-stu-id="d4bff-127">Customize the standard ER format</span></span>](#CustomizeProvidedFormat)

    - [<span data-ttu-id="d4bff-128">Criar uma formato personalizado</span><span class="sxs-lookup"><span data-stu-id="d4bff-128">Create a custom format</span></span>](#DeriveProvidedFormat)
    - [<span data-ttu-id="d4bff-129">Editar uma formato personalizado</span><span class="sxs-lookup"><span data-stu-id="d4bff-129">Edit a custom format</span></span>](#ConfigureDerivedFormat)
    - [<span data-ttu-id="d4bff-130">Marcar um formato personalizado como executável</span><span class="sxs-lookup"><span data-stu-id="d4bff-130">Mark a custom format as runnable</span></span>](#MarkFormatRunnable)

- [<span data-ttu-id="d4bff-131">Processar um pagamento de fornecedor usando o formato de ER personalizado</span><span class="sxs-lookup"><span data-stu-id="d4bff-131">Process a vendor payment by using the custom ER format</span></span>](#ProcessVendorPayment2)

    - [<span data-ttu-id="d4bff-132">Configurar o método de pagamento eletrônico</span><span class="sxs-lookup"><span data-stu-id="d4bff-132">Set up the electronic payment method</span></span>](#ConfigureMethodOfPayment2)
    - [<span data-ttu-id="d4bff-133">Processar um pagamento de fornecedor</span><span class="sxs-lookup"><span data-stu-id="d4bff-133">Process a vendor payment</span></span>](#ProcessPayment2)

- [<span data-ttu-id="d4bff-134">Importar novas versões das configurações do formato de ER padrão</span><span class="sxs-lookup"><span data-stu-id="d4bff-134">Import new versions of the standard ER format configurations</span></span>](#ImportERSolution2)

    - [<span data-ttu-id="d4bff-135">Importar novas versões das configurações de ER padrão</span><span class="sxs-lookup"><span data-stu-id="d4bff-135">Import new versions of the standard ER configurations</span></span>](#ImportERFormat2)
    - [<span data-ttu-id="d4bff-136">Examinar as configurações do formato de ER importado</span><span class="sxs-lookup"><span data-stu-id="d4bff-136">Review the imported ER format configurations</span></span>](#ReviewImportedERFormat)

- [<span data-ttu-id="d4bff-137">Adotar as alterações na nova versão de um formato importado em um formato personalizado</span><span class="sxs-lookup"><span data-stu-id="d4bff-137">Adopt the changes in the new version of an imported format in a custom format</span></span>](#AdoptNewBaseVersion)

    - [<span data-ttu-id="d4bff-138">Concluir a versão de rascunho atual de um formato personalizado</span><span class="sxs-lookup"><span data-stu-id="d4bff-138">Complete the current draft version of a custom format</span></span>](#CompleteDerivedFormat)
    - [<span data-ttu-id="d4bff-139">Trocar base de um formato personalizado para uma nova versão base</span><span class="sxs-lookup"><span data-stu-id="d4bff-139">Rebase a custom format to a new base version</span></span>](#RebaseDerivedFormat)
    - [<span data-ttu-id="d4bff-140">Processar um pagamento de fornecedor usando o formato de ER com troca de base</span><span class="sxs-lookup"><span data-stu-id="d4bff-140">Process a vendor payment by using a rebased ER format</span></span>](#ProcessPayment3)

- [<span data-ttu-id="d4bff-141">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="d4bff-141">Additional resources</span></span>](#References)

## <a name="configure-the-er-framework"></a><a id="ConfigureFramework"></a><span data-ttu-id="d4bff-142">Configurar a estrutura de ER</span><span class="sxs-lookup"><span data-stu-id="d4bff-142">Configure the ER framework</span></span>

<span data-ttu-id="d4bff-143">Como usuário na função de Consultor Funcional de Relatório Eletrônico, você deve configurar o conjunto mínimo de parâmetros de ER antes de começar a usar a estrutura de ER para criar uma versão personalizada de um formato de ER padrão.</span><span class="sxs-lookup"><span data-stu-id="d4bff-143">As a user in the Electronic Reporting Functional Consultant role, you must configure the minimal set of ER parameters before you can start to use the ER framework to design a custom version of a standard ER format.</span></span>

### <a name="configure-er-parameters"></a><a id="ConfigureParameters"></a><span data-ttu-id="d4bff-144">Configurar parâmetros de ER</span><span class="sxs-lookup"><span data-stu-id="d4bff-144">Configure ER parameters</span></span>

1. <span data-ttu-id="d4bff-145">Vá para **Administração da organização** \> **Espaços de trabalho** \> **Relatório eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-145">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="d4bff-146">Na página **Configurações de localização**, na seção **Links relacionados**, selecione **Parâmetros de relatório eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-146">On the **Localization configurations** page, in the **Related links** section, select **Electronic reporting parameters**.</span></span>
3. <span data-ttu-id="d4bff-147">Na página **Parâmetros de relatório eletrônico**, na guia **Geral**, defina a opção **Habilitar modo de design** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-147">On the **Electronic reporting parameters** page, on the **General** tab, set the **Enable design mode** option to **Yes**.</span></span>
4. <span data-ttu-id="d4bff-148">Na guia **Anexos**, defina os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="d4bff-148">On the **Attachments** tab, set the following parameters:</span></span>

    - <span data-ttu-id="d4bff-149">No campo **Configurações**, selecione o tipo **Arquivo** para a empresa **USMF**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-149">In the **Configurations** field, select the **File** type for the **USMF** company.</span></span>
    - <span data-ttu-id="d4bff-150">Nos campos **Arquivo de trabalho**, **Temporário**, **Linha de base** e **Outros**, selecione o tipo **Arquivo**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-150">In the **Job archive**, **Temporary**, **Baseline**, and **Others** fields, select the **File** type.</span></span>

<span data-ttu-id="d4bff-151">Para obter mais informações sobre parâmetros de ER, consulte [Configurar a estrutura de ER](electronic-reporting-er-configure-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="d4bff-151">For more information about ER parameters, see [Configure the ER framework](electronic-reporting-er-configure-parameters.md).</span></span>

### <a name="activate-an-er-configuration-provider"></a><a id="ActivateProvider"></a><span data-ttu-id="d4bff-152">Ativar um provedor de configuração de ER</span><span class="sxs-lookup"><span data-stu-id="d4bff-152">Activate an ER configuration provider</span></span>

<span data-ttu-id="d4bff-153">Toda configuração de ER adicionada é marcada como pertencente a um provedor de configuração de ER.</span><span class="sxs-lookup"><span data-stu-id="d4bff-153">Every ER configuration that is added is marked as owned by an ER configuration provider.</span></span> <span data-ttu-id="d4bff-154">O provedor de configuração de ER ativado no espaço de trabalho **Relatório eletrônico** é usado para essa finalidade.</span><span class="sxs-lookup"><span data-stu-id="d4bff-154">The ER configuration provider that is activated in the **Electronic reporting** workspace is used for this purpose.</span></span> <span data-ttu-id="d4bff-155">Por isso você deve ativar um provedor de configuração de ER no espaço de trabalho **Relatório eletrônico** antes de começar a adicionar ou editar configurações de ER.</span><span class="sxs-lookup"><span data-stu-id="d4bff-155">Therefore, you must activate an ER configuration provider in the **Electronic reporting** workspace before you start to add or edit ER configurations.</span></span>

> [!NOTE]
> <span data-ttu-id="d4bff-156">Somente o proprietário de uma configuração de ER pode editá-la.</span><span class="sxs-lookup"><span data-stu-id="d4bff-156">Only the owner of an ER configuration can edit it.</span></span> <span data-ttu-id="d4bff-157">Assim, para que uma configuração de ER possa ser editada, o provedor de configuração de ER apropriado deve estar ativado no espaço de trabalho **Relatório eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-157">Therefore, before an ER configuration can be edited, the appropriate ER configuration provider must be activated in the **Electronic reporting** workspace.</span></span>

#### <a name="review-the-list-of-er-configuration-providers"></a><a id="ReviewProvidersList"></a><span data-ttu-id="d4bff-158">Examinar a lista de provedores de configuração de ER</span><span class="sxs-lookup"><span data-stu-id="d4bff-158">Review the list of ER configuration providers</span></span>

1. <span data-ttu-id="d4bff-159">Vá para **Administração da organização** \> **Espaços de trabalho** \> **Relatório eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-159">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="d4bff-160">Na página **Configurações de localização**, na seção **Links relacionados**, selecione **Provedores de configuração**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-160">On the **Localization configurations** page, in the **Related links** section, select **Configuration providers**.</span></span>
3. <span data-ttu-id="d4bff-161">Na página **Tabela de provedores de configuração**, cada registro de provedor tem um nome e uma URL exclusivos.</span><span class="sxs-lookup"><span data-stu-id="d4bff-161">On the **Configuration provider table** page, each provider record has a unique name and URL.</span></span> <span data-ttu-id="d4bff-162">Examine o conteúdo dessa página.</span><span class="sxs-lookup"><span data-stu-id="d4bff-162">Review the contents of this page.</span></span> <span data-ttu-id="d4bff-163">Se já existir um registro para **Litware, Ltda.** (`https://www.litware.com`), ignore o próximo procedimento, [Adicionar um novo provedor de configuração de ER](#ActivateProvider).</span><span class="sxs-lookup"><span data-stu-id="d4bff-163">If a record for **Litware, Inc.** (`https://www.litware.com`) already exists, skip the next procedure, [Add a new ER configuration provider](#ActivateProvider).</span></span>

#### <a name="add-a-new-er-configuration-provider"></a><a id="ActivateProvider"></a><span data-ttu-id="d4bff-164">Adicionar um novo provedor de configuração de ER</span><span class="sxs-lookup"><span data-stu-id="d4bff-164">Add a new ER configuration provider</span></span>

1. <span data-ttu-id="d4bff-165">Vá para **Administração da organização** \> **Espaços de trabalho** \> **Relatório eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-165">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="d4bff-166">Na página **Configurações de localização**, na seção **Links relacionados**, selecione **Provedores de configuração**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-166">On the **Localization configurations** page, in the **Related links** section, select **Configuration providers**.</span></span>
3. <span data-ttu-id="d4bff-167">Na página **Provedores de configuração**, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-167">On the **Configuration providers** page, select **New**.</span></span>
4. <span data-ttu-id="d4bff-168">No campo **Nome**, insira **Litware, Ltda.**</span><span class="sxs-lookup"><span data-stu-id="d4bff-168">In the **Name** field, enter **Litware, Inc.**</span></span>
5. <span data-ttu-id="d4bff-169">No campo **Endereço na Internet**, insira `https://www.litware.com`.</span><span class="sxs-lookup"><span data-stu-id="d4bff-169">In the **Internet address** field, enter `https://www.litware.com`.</span></span>
6. <span data-ttu-id="d4bff-170">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-170">Select **Save**.</span></span>

#### <a name="activate-an-er-configuration-provider"></a><a id="ActivateAddedProvider"></a><span data-ttu-id="d4bff-171">Ativar um provedor de configuração de ER</span><span class="sxs-lookup"><span data-stu-id="d4bff-171">Activate an ER configuration provider</span></span>

1. <span data-ttu-id="d4bff-172">Vá para **Administração da organização** \> **Espaços de trabalho** \> **Relatório eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-172">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="d4bff-173">Na página **Configurações de localização**, na seção **Provedores de configuração**, selecione o bloco **Litware, Ltda.** e, depois, **Definir como ativo**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-173">On the **Localization configurations** page, in the **Configuration providers** section, select the **Litware, Inc.** tile, and then select **Set active**.</span></span>

<span data-ttu-id="d4bff-174">Para obter mais informações sobre provedores de configuração de ER, consulte [Criar provedores de configuração e marcá-los como ativos](tasks/er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="d4bff-174">For more information about ER configuration providers, see [Create configuration providers and mark them as active](tasks/er-configuration-provider-mark-it-active-2016-11.md).</span></span>

## <a name="import-the-standard-er-format-configurations"></a><a id="ImportERSolution1"></a><span data-ttu-id="d4bff-175">Importar as configurações do formato de ER padrão</span><span class="sxs-lookup"><span data-stu-id="d4bff-175">Import the standard ER format configurations</span></span>

### <a name="import-the-standard-er-configurations"></a><a id="ImportERFormat1"></a><span data-ttu-id="d4bff-176">Importar as configurações de ER padrão</span><span class="sxs-lookup"><span data-stu-id="d4bff-176">Import the standard ER configurations</span></span>

<span data-ttu-id="d4bff-177">Para adicionar as configurações de ER padrão à instância atual do Microsoft Dynamics 365 Finance, você deve importá-las do [repositório](general-electronic-reporting.md#Repository) de ER configurado para essa instância.</span><span class="sxs-lookup"><span data-stu-id="d4bff-177">To add the standard ER configurations to your current instance of Microsoft Dynamics 365 Finance, you must import them from the ER [repository](general-electronic-reporting.md#Repository) that was configured for that instance.</span></span>

1. <span data-ttu-id="d4bff-178">Vá para **Administração da organização** \> **Espaços de trabalho** \> **Relatório eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-178">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="d4bff-179">Na página **Configurações de localização**, na seção **Provedores de configuração**, selecione o bloco **Microsoft** e, depois, selecione **Repositórios** para ver a lista de repositórios do provedor Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d4bff-179">On the **Localization configurations** page, in the **Configuration providers** section, select the **Microsoft** tile, and then select **Repositories** to view the list of repositories for the Microsoft provider.</span></span>
3. <span data-ttu-id="d4bff-180">Na página **Repositórios de configuração**, selecione o repositório do tipo **Global** e, depois, selecione **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-180">On the **Configuration repositories** page, select the repository of the **Global** type, and then select **Open**.</span></span> <span data-ttu-id="d4bff-181">Se você precisar de autorização para se conectar ao Regulatory Configuration Service, siga as instruções de autorização.</span><span class="sxs-lookup"><span data-stu-id="d4bff-181">If you're prompted for authorization to connect to Regulatory Configuration Service, follow the authorization instructions.</span></span>
4. <span data-ttu-id="d4bff-182">Na página **Repositório de configuração**, na árvore de configuração no painel esquerdo, selecione a configuração de formato **BACS (Reino Unido)**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-182">On the **Configuration repository** page, in the configuration tree in the left pane, select the **BACS (UK)** format configuration.</span></span>
5. <span data-ttu-id="d4bff-183">Na FastTab **Versões**, selecione a versão **1.1** da configuração do formato de ER selecionada.</span><span class="sxs-lookup"><span data-stu-id="d4bff-183">On the **Versions** FastTab, select version **1.1** of the selected ER format configuration.</span></span>
6. <span data-ttu-id="d4bff-184">Selecione **Importar** para baixar a versão selecionada do repositório global para a instância atual do Finance.</span><span class="sxs-lookup"><span data-stu-id="d4bff-184">Select **Import** to download the selected version from the Global repository to the current Finance instance.</span></span>

![Página do repositório de configuração](./media/er-quick-start2-import-solution1.png)

> [!TIP]
> <span data-ttu-id="d4bff-186">Se você tiver problemas para acessar o [repositório global](er-download-configurations-global-repo.md), poderá [baixar configurações](download-electronic-reporting-configuration-lcs.md) do Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="d4bff-186">If you have trouble accessing the [Global repository](er-download-configurations-global-repo.md), you can [download configurations](download-electronic-reporting-configuration-lcs.md) from Microsoft Dynamics Lifecycle Services (LCS) instead.</span></span>

### <a name="review-the-imported-er-configurations"></a><a id="ReviewImportedERSolution"></a><span data-ttu-id="d4bff-187">Examinar as configurações de ER importadas</span><span class="sxs-lookup"><span data-stu-id="d4bff-187">Review the imported ER configurations</span></span>

1. <span data-ttu-id="d4bff-188">Vá para **Administração da organização** \> **Espaços de trabalho** \> **Relatório eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-188">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="d4bff-189">Na página **Configurações de localização**, na seção **Configurações**, selecione o título **Configurações de relatórios**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-189">On the **Localization configurations** page, in the **Configurations** section, select the **Reporting configurations** tile.</span></span>
3. <span data-ttu-id="d4bff-190">Na página **Configurações**, na árvore de configuração no painel esquerdo, expanda **Modelo de pagamento**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-190">On the **Configurations** page, in the configuration tree in the left pane, expand **Payment model**.</span></span>
4. <span data-ttu-id="d4bff-191">Observe que, além do formato de ER **BACS (Reino Unido)** selecionado, outras configurações de ER necessárias foram importadas.</span><span class="sxs-lookup"><span data-stu-id="d4bff-191">Notice that, in addition to the selected **BACS (UK)** ER format, other required ER configurations were imported.</span></span> <span data-ttu-id="d4bff-192">Verifique se as seguintes configurações de ER estão disponíveis na árvore de configuração:</span><span class="sxs-lookup"><span data-stu-id="d4bff-192">Make sure that the following ER configurations are available in the configuration tree:</span></span>

    - <span data-ttu-id="d4bff-193">**Modelo de pagamento** – Esta configuração contém o componente de ER [modelo de dados](general-electronic-reporting.md#data-model-and-model-mapping-components) que representa a estrutura de dados do domínio corporativo de pagamento.</span><span class="sxs-lookup"><span data-stu-id="d4bff-193">**Payment model** – This configuration contains the [data model](general-electronic-reporting.md#data-model-and-model-mapping-components) ER component that represents the data structure of the payment business domain.</span></span>
    - <span data-ttu-id="d4bff-194">**Mapeamento de modelos de pagamento 1611** – Esta configuração contém o componente de ER [mapeamento de modelos](general-electronic-reporting.md#data-model-and-model-mapping-components) que descreve como o modelo de dados é preenchido com dados de aplicativos em tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="d4bff-194">**Payment model mapping 1611** – This configuration contains the [model mapping](general-electronic-reporting.md#data-model-and-model-mapping-components) ER component that describes how the data model is filled in with application data at runtime.</span></span>
    - <span data-ttu-id="d4bff-195">**BACS (Reino Unido)** – Esta configuração contém os componentes de ER [formato](general-electronic-reporting.md#FormatComponentOutbound) e mapeamento de formato.</span><span class="sxs-lookup"><span data-stu-id="d4bff-195">**BACS (UK)** – This configuration contains the [format](general-electronic-reporting.md#FormatComponentOutbound) and format mapping ER components.</span></span> <span data-ttu-id="d4bff-196">O componente de formato especifica o layout do relatório.</span><span class="sxs-lookup"><span data-stu-id="d4bff-196">The format component specifies the report layout.</span></span> <span data-ttu-id="d4bff-197">O componente mapeamento de formato contém a fonte de dados do modelo e especifica como o layout do relatório é preenchido usando essa fonte de dados no tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="d4bff-197">The format mapping component contains the model data source and specifies how the report layout is filled in by using this data source at runtime.</span></span>

![Página Configurações](./media/er-quick-start2-imported-solution1.png)

## <a name="prepare-a-vendor-payment-for-processing"></a><a id="PrepareVendorPayment"></a><span data-ttu-id="d4bff-199">Preparar um pagamento de fornecedor para processamento</span><span class="sxs-lookup"><span data-stu-id="d4bff-199">Prepare a vendor payment for processing</span></span>

### <a name="add-bank-information-for-a-vendor-account"></a><a id="AddBankAccount"></a><span data-ttu-id="d4bff-200">Adicionar informações bancárias de uma conta de fornecedor</span><span class="sxs-lookup"><span data-stu-id="d4bff-200">Add bank information for a vendor account</span></span>

<span data-ttu-id="d4bff-201">Você deve adicionar as informações bancárias de uma conta de fornecedor que será mencionada posteriormente em um pagamento registrado.</span><span class="sxs-lookup"><span data-stu-id="d4bff-201">You must add bank information for a vendor account that will be referred to later in a registered payment.</span></span>

1. <span data-ttu-id="d4bff-202">Acesse **Contas a pagar** \> **Fornecedores** \> **Todos os fornecedores**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-202">Go to **Accounts payable** \> **Vendors** \> **All vendors**.</span></span>
2. <span data-ttu-id="d4bff-203">Na página **Todos os fornecedores**, selecione a conta de fornecedor **GB_SI_000001** e, depois, no Painel de Ação, na guia **Fornecedor**, no grupo **Configurar**, selecione **Contas bancárias**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-203">On the **All vendors** page, select the **GB_SI_000001** vendor account, and then, on the Action Pane, on the **Vendor** tab, in the **Set up** group, select **Bank accounts**.</span></span>
3. <span data-ttu-id="d4bff-204">Na página **Contas bancárias do fornecedor**, selecione **Novo** e insira as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="d4bff-204">On the **Vendor bank accounts** page, select **New**, and then enter the following information:</span></span>

    1. <span data-ttu-id="d4bff-205">No campo **Conta bancária**, insira **GBP OPER**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-205">In the **Bank account** field, enter **GBP OPER**.</span></span>
    2. <span data-ttu-id="d4bff-206">No campo **Grupos bancários**, selecione **BankGBP**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-206">In the **Bank groups** field, select **BankGBP**.</span></span>
    3. <span data-ttu-id="d4bff-207">No campo **Número da conta bancária**, insira **202015**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-207">In the **Bank account number** field, enter **202015**.</span></span>
    4. <span data-ttu-id="d4bff-208">No campo **Código SWIFT**, insira <a id="DefineSWIFTCode"></a>**CHASDEFXXXX**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-208">In the **SWIFT code** field, enter <a id="DefineSWIFTCode"></a>**CHASDEFXXXX**.</span></span>
    5. <span data-ttu-id="d4bff-209">No campo **IBAN**, insira **GB33BUKB20201555555555**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-209">In the **IBAN** field, enter **GB33BUKB20201555555555**.</span></span>
    6. <span data-ttu-id="d4bff-210">No campo **Número identificador do banco**, mantenha o valor padrão, <a id="DefineRoutingNumber"></a>**123456**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-210">In the **Routing number** field, keep the default value, <a id="DefineRoutingNumber"></a>**123456**.</span></span>

    ![Página Contas bancárias do fornecedor](./media/er-quick-start2-bank-account.png)

4. <span data-ttu-id="d4bff-212">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-212">Select **Save**.</span></span>
5. <span data-ttu-id="d4bff-213">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="d4bff-213">Close the page.</span></span>
6. <span data-ttu-id="d4bff-214">Na página **Todos os fornecedores**, abra a conta do fornecedor **GB_SI_000001**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-214">On the **All vendors** page, open the **GB_SI_000001** vendor account.</span></span>
7. <span data-ttu-id="d4bff-215">Na página de detalhes do fornecedor, selecione **Editar** para tornar a página editável, se necessário.</span><span class="sxs-lookup"><span data-stu-id="d4bff-215">On the vendor details page, select **Edit** to make the page editable, if required.</span></span>
8. <span data-ttu-id="d4bff-216">Na FastTab **Pagamento** , no campo **Conta bancária**, selecione **GBP OPER**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-216">On the **Payment** FastTab, in the **Bank account** field, select **GBP OPER**.</span></span>

    ![Página Detalhes do fornecedor](./media/er-quick-start2-bank-account-reference.png)

9. <span data-ttu-id="d4bff-218">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-218">Select **Save**.</span></span>
10. <span data-ttu-id="d4bff-219">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="d4bff-219">Close the page.</span></span>

### <a name="enter-a-vendor-payment"></a><a id="EnterVendorPayment"></a><span data-ttu-id="d4bff-220">Inserir um pagamento de fornecedor</span><span class="sxs-lookup"><span data-stu-id="d4bff-220">Enter a vendor payment</span></span>

<span data-ttu-id="d4bff-221">Você deve inserir um novo pagamento de fornecedor usando uma [proposta de pagamento](../../../finance/accounts-payable/create-vendor-payments-payment-proposal.md).</span><span class="sxs-lookup"><span data-stu-id="d4bff-221">You must enter a new vendor payment by using a [payment proposal](../../../finance/accounts-payable/create-vendor-payments-payment-proposal.md).</span></span>

1. <span data-ttu-id="d4bff-222">Vá para **Contas a pagar** \> **Pagamentos** \> **Diário de pagamentos do fornecedor**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-222">Go to **Accounts payable** \> **Payments** \> **Vendor payment journal**.</span></span>
2. <span data-ttu-id="d4bff-223">Na página **Diário de pagamentos do fornecedor**, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-223">On the **Vendor payment journal** page, select **New**.</span></span>
3. <span data-ttu-id="d4bff-224">No campo **Nome**, selecione **VendPay**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-224">In the **Name** field, select **VendPay**.</span></span>
4. <span data-ttu-id="d4bff-225">Selecione **Linhas**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-225">Select **Lines**.</span></span>
5. <span data-ttu-id="d4bff-226">Selecione **Proposta de pagamento** \> **Criar proposta de pagamento**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-226">Select **Payment proposal** \> **Create payment proposal**.</span></span>
6. <span data-ttu-id="d4bff-227">Na caixa de diálogo **Proposta de pagamento de fornecedor**, configure as condições para filtrar registros somente da conta de fornecedor **GB_SI_000001** e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-227">In the **Vendor payment proposal** dialog box, configure conditions to filter for records for the **GB_SI_000001** vendor account only, and then select **OK**.</span></span>
7. <span data-ttu-id="d4bff-228">Selecione a linha da fatura **00000007_Inv** e, depois, selecione **Criar pagamento**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-228">Select the line for the **00000007_Inv** invoice, and then select **Create payment**.</span></span>

    ![Caixa de diálogo Proposta de pagamento de fornecedor](./media/er-quick-start2-payment-proposal.png)

8. <span data-ttu-id="d4bff-230">Verifique se o pagamento inserido está configurado para usar o método de pagamento **Eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-230">Verify that the payment that is entered is configured to use the **Electronic** method of payment.</span></span>

    ![Página Pagamentos de fornecedor](./media/er-quick-start2-payment-line.png)

## <a name="process-a-vendor-payment-by-using-the-standard-er-format"></a><a id="ProcessVendorPayment1"></a><span data-ttu-id="d4bff-232">Processar um pagamento de fornecedor usando o formato de ER padrão</span><span class="sxs-lookup"><span data-stu-id="d4bff-232">Process a vendor payment by using the standard ER format</span></span>

### <a name="set-up-the-electronic-payment-method"></a><a id="ConfigureMethodOfPayment1"></a><span data-ttu-id="d4bff-233">Configurar o método de pagamento eletrônico</span><span class="sxs-lookup"><span data-stu-id="d4bff-233">Set up the electronic payment method</span></span>

<span data-ttu-id="d4bff-234">Você deve configurar o método de pagamento eletrônico para que ele use a configuração do formato de ER importado.</span><span class="sxs-lookup"><span data-stu-id="d4bff-234">You must configure the electronic method of payment so that it uses the imported ER format configuration.</span></span>

1. <span data-ttu-id="d4bff-235">Vá para **Contas a pagar** \> **Configuração de pagamento** \> **Métodos de pagamento**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-235">Go to **Accounts payable** \> **Payment setup** \> **Methods of payment**.</span></span>
2. <span data-ttu-id="d4bff-236">Na página **Métodos de pagamento - Fornecedores**, selecione o método de pagamento **Eletrônico** no painel esquerdo.</span><span class="sxs-lookup"><span data-stu-id="d4bff-236">On the **Methods of payment - vendors** page, select the **Electronic** method of payment in the left pane.</span></span>
3. <span data-ttu-id="d4bff-237">Selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-237">Select **Edit**.</span></span>
4. <span data-ttu-id="d4bff-238">Na FastTab **Formatos de arquivo**, defina a opção **Formato de exportação eletrônico geral** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-238">On the **File formats** FastTab, set the **General electronic Export format** option to **Yes**.</span></span>
5. <span data-ttu-id="d4bff-239">No campo **Exportar configuração de formato**, selecione a configuração de formato **BACS (Reino Unido)**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-239">In the **Export format configuration** field, select the **BACS (UK)** format configuration.</span></span>

    ![Página Métodos de pagamento - Fornecedores](./media/er-quick-start2-method-of-payment1.png)

6. <span data-ttu-id="d4bff-241">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-241">Select **Save**.</span></span>

### <a name="process-a-vendor-payment"></a><a id="ProcessPayment1"></a><span data-ttu-id="d4bff-242">Processar um pagamento de fornecedor</span><span class="sxs-lookup"><span data-stu-id="d4bff-242">Process a vendor payment</span></span>

1. <span data-ttu-id="d4bff-243">Vá para **Contas a pagar** \> **Pagamentos** \> **Diário de pagamentos do fornecedor**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-243">Go to **Accounts payable** \> **Payments** \> **Vendor payment journal**.</span></span>
2. <span data-ttu-id="d4bff-244">Na página **Diário de pagamentos do fornecedor**, selecione o diário de pagamento adicionado inicialmente e, depois, **Linhas**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-244">On the **Vendor payment journal** page, select the payment journal that you added earlier, and then select **Lines**.</span></span>
3. <span data-ttu-id="d4bff-245">Na página **Pagamentos de fornecedores**, selecione **Gerar pagamentos**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-245">On the **Vendor payments** page, select **Generate payments**.</span></span>
4. <span data-ttu-id="d4bff-246">Na caixa de diálogo **Gerar pagamentos**, insira as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="d4bff-246">In the **Generate payments** dialog box, enter the following information:</span></span>

    - <span data-ttu-id="d4bff-247">No campo **Método de pagamento**, selecione **Eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-247">In the **Method of payment** field, select **Electronic**.</span></span>
    - <span data-ttu-id="d4bff-248">No campo **Conta bancária**, selecione **GBSI OPER**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-248">In the **Bank account** field, select **GBSI OPER**.</span></span>

5. <span data-ttu-id="d4bff-249">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-249">Select **OK**.</span></span>
6. <span data-ttu-id="d4bff-250">Na caixa de diálogo **Parâmetros de relatório eletrônico**, defina a opção **Imprimir relatório de controle** como **Sim** e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-250">In the **Electronic report parameters** dialog box, set the **Print control report** option to **Yes**, and then select **OK**.</span></span>

    ![Página Parâmetros de relatório eletrônico](./media/er-quick-start2-payment-dialog1.png)

    > [!NOTE]
    > <span data-ttu-id="d4bff-252">Além do arquivo de pagamento, agora é possível gerar o relatório de controle.</span><span class="sxs-lookup"><span data-stu-id="d4bff-252">In addition to the payment file, you can now generate the control report.</span></span>

7. <span data-ttu-id="d4bff-253">Baixe o arquivo zip e extraia os seguintes arquivos dele:</span><span class="sxs-lookup"><span data-stu-id="d4bff-253">Download the zip file, and then extract the following files from it:</span></span>

    - <span data-ttu-id="d4bff-254">O relatório de controle no formato Excel</span><span class="sxs-lookup"><span data-stu-id="d4bff-254">The control report in Excel format</span></span>
    - <span data-ttu-id="d4bff-255">O arquivo de pagamento no formato TXT</span><span class="sxs-lookup"><span data-stu-id="d4bff-255">The payment file in TXT format</span></span>

        <span data-ttu-id="d4bff-256">Observe que, de acordo com a [estrutura](#PositionRoutingNumber) do formato de ER fornecido, a linha de pagamento no arquivo gerado começa com o número identificador do banco que foi [definido](#DefineRoutingNumber) para a conta bancária configurada.</span><span class="sxs-lookup"><span data-stu-id="d4bff-256">Notice that, in accordance with the [structure](#PositionRoutingNumber) of the provided ER format, the payment line in the generated file starts with the routing number that was [defined](#DefineRoutingNumber) for the configured bank account.</span></span>

        ![Arquivo de pagamento no formato TXT](./media/er-quick-start2-payment-file1.png)

## <a name="customize-the-standard-er-format"></a><a id="CustomizeProvidedFormat"></a><span data-ttu-id="d4bff-258">Personalizar o formato de ER padrão</span><span class="sxs-lookup"><span data-stu-id="d4bff-258">Customize the standard ER format</span></span>

<span data-ttu-id="d4bff-259">Para o exemplo mostrado nesta seção, você quer usar as configurações de ER fornecidas pela Microsoft para gerar arquivos de pagamento de fornecedor no formato BACS, mas deve adicionar uma personalização para dar suporte aos requisitos de um banco específico.</span><span class="sxs-lookup"><span data-stu-id="d4bff-259">For the example that is shown in this section, you want to use the ER configurations that are provided by Microsoft to generate vendor payment files in BACS format, but you must add a customization to support the requirements of a specific bank.</span></span> <span data-ttu-id="d4bff-260">Você também quer poder atualizar o formato personalizado quando novas versões das configurações de ER são disponibilizadas.</span><span class="sxs-lookup"><span data-stu-id="d4bff-260">You also want to be able to upgrade your custom format when new versions of ER configurations become available.</span></span> <span data-ttu-id="d4bff-261">No entanto, você quer atualizar pelo menor custo.</span><span class="sxs-lookup"><span data-stu-id="d4bff-261">However, you want to be able to do the upgrade at the lowest cost.</span></span>

<span data-ttu-id="d4bff-262">Neste caso, como representante da Litware, Ltda., você deve criar (derivar) uma nova configuração do formato de ER usando como base a configuração **BACS (Reino Unido)** fornecida pela Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d4bff-262">In this case, as the representative of Litware, Inc., you must create (derive) a new ER format configuration by using the **BACS (UK)** Microsoft-provided configuration as a base.</span></span>

### <a name="create-a-custom-format"></a><a id="DeriveProvidedFormat"></a><span data-ttu-id="d4bff-263">Criar uma formato personalizado</span><span class="sxs-lookup"><span data-stu-id="d4bff-263">Create a custom format</span></span>

1. <span data-ttu-id="d4bff-264">Vá para **Administração da organização** \> **Relatório eletrônico** \> **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-264">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="d4bff-265">Na página **Configurações**, na árvore de configuração no painel esquerdo, expanda **Modelo de pagamento** e selecione **BACS (Reino Unido)**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-265">On the **Configurations** page, in the configuration tree in the left pane, expand **Payment model**, and then select **BACS (UK)**.</span></span> <span data-ttu-id="d4bff-266">A Litware, Ltda. usará a versão 1.1 dessa configuração do formato de ER como base para a versão personalizada.</span><span class="sxs-lookup"><span data-stu-id="d4bff-266">Litware, Inc. will use version 1.1 of this ER format configuration as the base for the custom version.</span></span>
3. <span data-ttu-id="d4bff-267">Selecione **Criar configuração** para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="d4bff-267">Select **Create configuration** to open the drop-down dialog box.</span></span> <span data-ttu-id="d4bff-268">Você pode usar essa caixa de diálogo para criar uma nova configuração para um formato de pagamento personalizado.</span><span class="sxs-lookup"><span data-stu-id="d4bff-268">You can use this dialog box to create a new configuration for a custom payment format.</span></span>
4. <span data-ttu-id="d4bff-269">No grupo de campos **Novo**, selecione a opção **Derivar de Nome: BACS (Reino Unido), Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-269">In the **New** field group, select the **Derive from Name: BACS (UK), Microsoft** option.</span></span>
5. <span data-ttu-id="d4bff-270">No campo **Nome**, insira **BACS (personalizado do Reino Unido)**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-270">In the **Name** field, enter **BACS (UK custom)**.</span></span>

    ![Caixa de diálogo suspensa Criar configuração](./media/er-quick-start2-add-derived-format.png)

6. <span data-ttu-id="d4bff-272">Selecione **Criar configuração**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-272">Select **Create configuration**.</span></span>

<span data-ttu-id="d4bff-273">A versão 1.1.1 da configuração do formato de ER **BACS (personalizado do Reino Unido)** foi criada.</span><span class="sxs-lookup"><span data-stu-id="d4bff-273">Version 1.1.1 of the **BACS (UK custom)** ER format configuration is created.</span></span> <span data-ttu-id="d4bff-274">Essa versão tem um [status](general-electronic-reporting.md#component-versioning) de **Rascunho** e pode ser editada.</span><span class="sxs-lookup"><span data-stu-id="d4bff-274">This version has a [status](general-electronic-reporting.md#component-versioning) of **Draft** and can be edited.</span></span> <span data-ttu-id="d4bff-275">O conteúdo atual do formato de ER personalizado corresponde ao conteúdo do formato fornecido pela Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d4bff-275">The current content of your custom ER format matches the content of the format that is provided by Microsoft.</span></span>

![Página Configurações](./media/er-quick-start2-derived-format-configuration1.png)

### <a name="edit-a-custom-format"></a><a id="ConfigureDerivedFormat"></a><span data-ttu-id="d4bff-277">Editar uma formato personalizado</span><span class="sxs-lookup"><span data-stu-id="d4bff-277">Edit a custom format</span></span>

<span data-ttu-id="d4bff-278">Você deve configurar um formato personalizado de modo que ele atenda a requisitos específicos do banco.</span><span class="sxs-lookup"><span data-stu-id="d4bff-278">You must configure your custom format so that it meets bank-specific requirements.</span></span> <span data-ttu-id="d4bff-279">Por exemplo, um banco pode exigir que os arquivos de pagamento gerados incluam o código SWIFT (Society for Worldwide Interbank Financial Telecommunication) de um banco que tem a função de agente no pagamento de fornecedor processado.</span><span class="sxs-lookup"><span data-stu-id="d4bff-279">For example, a bank might require that payment files that are generated include the Society for Worldwide Interbank Financial Telecommunication (SWIFT) code of a bank that is assigned the agent role in the processed vendor payment.</span></span> <span data-ttu-id="d4bff-280">Os códigos SWIFT são códigos bancários internacionais que identificam bancos específicos em todo o mundo.</span><span class="sxs-lookup"><span data-stu-id="d4bff-280">SWIFT codes are international bank codes that identify specific banks worldwide.</span></span> <span data-ttu-id="d4bff-281">Também são conhecidos como códigos identificadores bancários (BICs).</span><span class="sxs-lookup"><span data-stu-id="d4bff-281">They are also known as Bank Identifier Codes (BICs).</span></span> <span data-ttu-id="d4bff-282">O código SWIFT deve ter 11 caracteres e deve ser inserido no início de cada linha de pagamento em um arquivo de pagamento gerado.</span><span class="sxs-lookup"><span data-stu-id="d4bff-282">The SWIFT code must be 11 characters long, and it must be entered at the beginning of every payment line in a generated payment file.</span></span>

1. <span data-ttu-id="d4bff-283">Vá para **Administração da organização** \> **Relatório eletrônico** \> **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-283">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="d4bff-284">Na página **Configurações**, na árvore de configuração no painel esquerdo, expanda **Modelo de pagamento** e selecione **BACS (personalizado do Reino Unido)**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-284">On the **Configurations** page, in the configuration tree in the left pane, expand **Payment model**, and then select **BACS (UK custom)**.</span></span>
3. <span data-ttu-id="d4bff-285">Na FastTab **Versões**, selecione a versão **1.1.1** da configuração selecionada.</span><span class="sxs-lookup"><span data-stu-id="d4bff-285">On the **Versions** FastTab, select version **1.1.1** of the selected configuration.</span></span>
4. <span data-ttu-id="d4bff-286">Selecione **Designer**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-286">Select **Designer**.</span></span>
5. <span data-ttu-id="d4bff-287">Na página **Designer de formato**, selecione **Mostrar detalhes** para ver mais informações sobre os elementos de formato.</span><span class="sxs-lookup"><span data-stu-id="d4bff-287">On the **Format designer** page, select **Show details** to view more information about the format elements.</span></span>
6. <span data-ttu-id="d4bff-288">Expanda e examine os seguintes elementos:</span><span class="sxs-lookup"><span data-stu-id="d4bff-288">Expand and review the following elements:</span></span>

    - <span data-ttu-id="d4bff-289">O elemento **BACSReportsFolder** do tipo **Pasta**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-289">The **BACSReportsFolder** element of the **Folder** type.</span></span> <span data-ttu-id="d4bff-290">Esse elemento é usado para gerar saída no formato ZIP.</span><span class="sxs-lookup"><span data-stu-id="d4bff-290">This element is used to generate output in ZIP format.</span></span>
    - <span data-ttu-id="d4bff-291">O elemento **arquivo** do tipo **Arquivo**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-291">The **file** element of the **File** type.</span></span> <span data-ttu-id="d4bff-292">Esse elemento é usado para gerar um arquivo de pagamento no formato TXT.</span><span class="sxs-lookup"><span data-stu-id="d4bff-292">This element is used to generate a payment file in TXT format.</span></span>
    - <span data-ttu-id="d4bff-293">O elemento **transações** do tipo **Sequência**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-293">The **transactions** element of the **Sequence** type.</span></span> <span data-ttu-id="d4bff-294">Esse elemento é usado para gerar uma única linha de pagamento em um arquivo de pagamento.</span><span class="sxs-lookup"><span data-stu-id="d4bff-294">This element is used to generate a single payment line in a payment file.</span></span>
    - <span data-ttu-id="d4bff-295">O elemento **transação** do tipo **Sequência**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-295">The **transaction** element of the **Sequence** type.</span></span> <span data-ttu-id="d4bff-296">Esse elemento é usado para gerar campos individuais de uma única linha de pagamento.</span><span class="sxs-lookup"><span data-stu-id="d4bff-296">This element is used to generate individual fields of a single payment line.</span></span>

7. <span data-ttu-id="d4bff-297">Selecione o elemento **transação**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-297">Select the **transaction** element.</span></span>

    ![Elemento transação no designer de operações de ER](./media/er-quick-start2-derived-format0.png)

    > [!NOTE]
    > <span data-ttu-id="d4bff-299">O relatório fornecido é configurado de forma que <a id="PositionRoutingNumber"></a>todas as linhas de pagamento comecem com o número identificador do banco.</span><span class="sxs-lookup"><span data-stu-id="d4bff-299">The provided report is configured so that <a id="PositionRoutingNumber"></a>every payment line starts with the bank routing number.</span></span> <span data-ttu-id="d4bff-300">O elemento de formato **vendBankRouteNum** é usado para essa finalidade.</span><span class="sxs-lookup"><span data-stu-id="d4bff-300">The **vendBankRouteNum** format element is used for this purpose.</span></span> 

8. <span data-ttu-id="d4bff-301">Selecione **Adicionar** e, depois, selecione o tipo **Texto\\Sequência de caracteres** do elemento de formato que você está adicionando:</span><span class="sxs-lookup"><span data-stu-id="d4bff-301">Select **Add**, and then select the **Text\\String** type of the format element that you're adding:</span></span>

    1. <span data-ttu-id="d4bff-302">No campo **Nome**, insira **vendBankSWIFT**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-302">In the **Name** field, enter **vendBankSWIFT**.</span></span>
    2. <span data-ttu-id="d4bff-303">No campo **Comprimento mínimo**, insira **"11**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-303">In the **Minimum length** field, enter **11**.</span></span>
    3. <span data-ttu-id="d4bff-304">No campo **Comprimento máximo**, insira **11**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-304">In the **Maximum length** field, enter **11**.</span></span>
    4. <span data-ttu-id="d4bff-305">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-305">Select **OK**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d4bff-306">O elemento **vendBankSWIFT** será usado para inserir o código SWIFT de um banco de fornecedor nos arquivos gerados.</span><span class="sxs-lookup"><span data-stu-id="d4bff-306">The **vendBankSWIFT** element will be used to enter the SWIFT code of a vendor bank in generated files.</span></span>

9. <span data-ttu-id="d4bff-307">Na árvore de estrutura de formato, selecione **vendBankSWIFT**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-307">In the format structure tree, select **vendBankSWIFT**.</span></span>
10. <span data-ttu-id="d4bff-308">Selecione **Mover para cima** para mover o elemento de formato selecionado um nível acima.</span><span class="sxs-lookup"><span data-stu-id="d4bff-308">Select **Move up** to move the selected format element up one level.</span></span> <span data-ttu-id="d4bff-309">Repita esta etapa até que o elemento **vendBankSWIFT** seja o <a id="PositionSWIFTCode"></a>primeiro elemento no elemento pai **transação**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-309">Repeat this step until the **vendBankSWIFT** element is the <a id="PositionSWIFTCode"></a>first element under the parent **transaction** element.</span></span>

    ![VendBankSWIFT como o primeiro elemento em transação no designer de operações de ER](./media/er-quick-start2-derived-format1.png)

11. <span data-ttu-id="d4bff-311">Enquanto **vendBankSWIFT** ainda estiver selecionado na árvore de estrutura de formato, selecione a guia **Mapeamento** e expanda a fonte de dados **modelo**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-311">While the **vendBankSWIFT** is still selected in the format structure tree, select the **Mapping** tab, and then expand the **model** data source.</span></span>
12. <span data-ttu-id="d4bff-312">Expanda **model.Payment** \> **model.Payment.CreditorAgent** e selecione o campo de fonte de dados **model.Payment.CreditorAgent.BICFI**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-312">Expand **model.Payment** \> **model.Payment.CreditorAgent**, and select the **model.Payment.CreditorAgent.BICFI** data source field.</span></span> <span data-ttu-id="d4bff-313">Este campo de fonte de dados expõe o código SWIFT de um banco de fornecedor ao qual foi atribuída a função de agente no pagamento de fornecedor processado.</span><span class="sxs-lookup"><span data-stu-id="d4bff-313">This data source field exposes the SWIFT code of a vendor bank that is assigned the agent role in the processed vendor payment.</span></span>
13. <span data-ttu-id="d4bff-314">Selecione **Associar**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-314">Select **Bind**.</span></span> <span data-ttu-id="d4bff-315">Agora o elemento de formato **vendBankSWIFT** está associado ao campo de fonte de dados **model.Payment.CreditorAgent.BICFI**, de forma que os códigos SWIFT serão inseridos nos arquivos de pagamento gerados.</span><span class="sxs-lookup"><span data-stu-id="d4bff-315">The **vendBankSWIFT** format element is now bound with the **model.Payment.CreditorAgent.BICFI** data source field, so that SWIFT codes will be entered in generated payment files.</span></span>

    ![Elemento de formato vendBankSWIFT associado ao campo de fonte de dados model.Payment.CreditorAgent.BICFI no designer de operações de ER](./media/er-quick-start2-derived-format2.png)

14. <span data-ttu-id="d4bff-317">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-317">Select **Save**.</span></span>
15. <span data-ttu-id="d4bff-318">Feche a página do designer.</span><span class="sxs-lookup"><span data-stu-id="d4bff-318">Close the designer page.</span></span>

### <a name="mark-a-custom-format-as-runnable"></a><a id="MarkFormatRunnable"></a><span data-ttu-id="d4bff-319">Marcar um formato personalizado como executável</span><span class="sxs-lookup"><span data-stu-id="d4bff-319">Mark a custom format as runnable</span></span>

<span data-ttu-id="d4bff-320">Agora que a primeira versão do formato personalizado foi criada e tem o status de **Rascunho**, você pode executá-la para fins de teste.</span><span class="sxs-lookup"><span data-stu-id="d4bff-320">Now that the first version of your custom format has been created and has a status of **Draft**, you can run it for testing purposes.</span></span> <span data-ttu-id="d4bff-321">Para executar o relatório, você deve processar um pagamento de fornecedor usando o método de pagamento que se refere ao seu formato de ER personalizado.</span><span class="sxs-lookup"><span data-stu-id="d4bff-321">To run the report, you must process a vendor payment by using the payment method that refers to your custom ER format.</span></span> <span data-ttu-id="d4bff-322">Por padrão, quando você chama um formato de ER no aplicativo, somente as versões que têm o status **Concluída** ou **Compartilhada** são [consideradas](general-electronic-reporting.md#component-versioning).</span><span class="sxs-lookup"><span data-stu-id="d4bff-322">By default, when you call an ER format from the application, only versions that have a status of **Completed** or **Shared** are [considered](general-electronic-reporting.md#component-versioning).</span></span> <span data-ttu-id="d4bff-323">Esse comportamento ajuda a impedir que formatos de ER com designs não concluídos sejam utilizados.</span><span class="sxs-lookup"><span data-stu-id="d4bff-323">This behavior helps prevent ER formats that have unfinished designs from being used.</span></span> <span data-ttu-id="d4bff-324">No entanto, para as execuções de teste, você pode forçar o aplicativo a usar a versão do seu formato de ER que tem o status de **Rascunho**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-324">However, for your test runs, you can force the application to use the version of your ER format that has a status of **Draft**.</span></span> <span data-ttu-id="d4bff-325">Dessa forma, é possível ajustar a versão do formato atual se modificações forem necessárias.</span><span class="sxs-lookup"><span data-stu-id="d4bff-325">In this way, you can adjust the current format version if any modifications are required.</span></span> <span data-ttu-id="d4bff-326">Para obter mais informações, consulte [Aplicabilidade](electronic-reporting-destinations.md#applicability).</span><span class="sxs-lookup"><span data-stu-id="d4bff-326">For more information, see [Applicability](electronic-reporting-destinations.md#applicability).</span></span>

<span data-ttu-id="d4bff-327">Para usar a versão de rascunho de um formato de ER, você deve marcar o formato de ER explicitamente.</span><span class="sxs-lookup"><span data-stu-id="d4bff-327">To use the draft version of an ER format, you must explicitly mark the ER format.</span></span>

1. <span data-ttu-id="d4bff-328">Vá para **Administração da organização** \> **Relatório eletrônico** \> **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-328">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="d4bff-329">Na página **Configurações**, no Painel Ação, na guia **Configurações**, no grupo **Configurações avançadas**, selecione **Parâmetros de usuário**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-329">On the **Configurations** page, on the Action Pane, on the **Configurations** tab, in the **Advanced settings** group, select **User parameters**.</span></span>
3. <span data-ttu-id="d4bff-330">Na caixa de diálogo **Parâmetros de usuário**, defina a opção **Executar configurações** como **Sim** e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-330">In the **User parameters** dialog box, set the **Run settings** option to **Yes**, and then select **OK**.</span></span>
4. <span data-ttu-id="d4bff-331">Selecione **Editar** para tornar a página atual editável, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="d4bff-331">Select **Edit** to make the current page editable, as required.</span></span>
5. <span data-ttu-id="d4bff-332">Na árvore de configuração no painel esquerdo, selecione **BACS (personalizado do Reino Unido)**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-332">In the configuration tree in the left pane, select **BACS (UK custom)**.</span></span>
6. <span data-ttu-id="d4bff-333">Defina a opção **Executar Rascunho** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-333">Set the **Run Draft** option to **Yes**.</span></span>

    ![Opção Executar Rascunho na página Configurações](./media/er-quick-start2-derived-format-configuration2.png)

## <a name="process-a-vendor-payment-by-using-the-custom-er-format"></a><a id="ProcessVendorPayment2"></a><span data-ttu-id="d4bff-335">Processar um pagamento de fornecedor usando o formato de ER personalizado</span><span class="sxs-lookup"><span data-stu-id="d4bff-335">Process a vendor payment by using the custom ER format</span></span>

### <a name="set-up-the-electronic-payment-method"></a><a id="ConfigureMethodOfPayment2"></a><span data-ttu-id="d4bff-336">Configurar o método de pagamento eletrônico</span><span class="sxs-lookup"><span data-stu-id="d4bff-336">Set up the electronic payment method</span></span>

<span data-ttu-id="d4bff-337">Você deve configurar o método de pagamento eletrônico para que seu formato de ER personalizado seja usado para processar pagamentos de fornecedor.</span><span class="sxs-lookup"><span data-stu-id="d4bff-337">You must configure the electronic method of payment so that your custom ER format is used to process vendor payments.</span></span>

1. <span data-ttu-id="d4bff-338">Vá para **Contas a pagar** \> **Configuração de pagamento** \> **Métodos de pagamento**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-338">Go to **Accounts payable** \> **Payment setup** \> **Methods of payment**.</span></span>
2. <span data-ttu-id="d4bff-339">Na página **Métodos de pagamento - Fornecedores**, selecione o método de pagamento **Eletrônico** no painel esquerdo.</span><span class="sxs-lookup"><span data-stu-id="d4bff-339">On the **Methods of payment - vendors** page, select the **Electronic** method of payment in the left pane.</span></span>
3. <span data-ttu-id="d4bff-340">Selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-340">Select **Edit**.</span></span>
4. <span data-ttu-id="d4bff-341">Na FastTab **Formato de arquivo**, defina a opção **Formato de exportação eletrônico geral** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-341">On the **File format** FastTab, set the **General electronic export format** option to **Yes**.</span></span>
5. <span data-ttu-id="d4bff-342">No campo **Exportar configuração de formato**, selecione a configuração de formato **BACS (personalizado do Reino Unido)**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-342">In the **Export format configuration** field, select the **BACS (UK custom)** format configuration.</span></span>

    ![Página Métodos de pagamento - Fornecedores](./media/er-quick-start2-method-of-payment2.png)

6. <span data-ttu-id="d4bff-344">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-344">Select **Save**.</span></span>

### <a name="process-a-vendor-payment"></a><a id="ProcessPayment2"></a><span data-ttu-id="d4bff-345">Processar um pagamento de fornecedor</span><span class="sxs-lookup"><span data-stu-id="d4bff-345">Process a vendor payment</span></span>

1. <span data-ttu-id="d4bff-346">Vá para **Contas a pagar** \> **Pagamentos** \> **Diário de pagamentos do fornecedor**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-346">Go to **Accounts payable** \> **Payments** \> **Vendor payment journal**.</span></span>
2. <span data-ttu-id="d4bff-347">Na página **Diário de pagamentos do fornecedor**, selecione o diário de pagamento que você criou anteriormente.</span><span class="sxs-lookup"><span data-stu-id="d4bff-347">On the **Vendor payment journal** page, select the payment journal that you created earlier.</span></span>
3. <span data-ttu-id="d4bff-348">Selecione **Linhas**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-348">Select **Lines**.</span></span>
4. <span data-ttu-id="d4bff-349">Na página **Pagamentos de fornecedores**, acima da grade, selecione **Status do pagamento** \> **Nenhum**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-349">On the **Vendor payments** page, above the grid, select **Payment status** \> **None**.</span></span>
5. <span data-ttu-id="d4bff-350">Selecione **Gerar pagamento**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-350">Select **Generate payment**.</span></span>
6. <span data-ttu-id="d4bff-351">Na caixa de diálogo **Gerar pagamentos**, insira as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="d4bff-351">In the **Generate payments** dialog box, enter the following information:</span></span>

    - <span data-ttu-id="d4bff-352">No campo **Método de pagamento**, selecione **Eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-352">In the **Method of payment** field, select **Electronic**.</span></span>
    - <span data-ttu-id="d4bff-353">No campo **Conta bancária**, selecione **GBSI OPER**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-353">In the **Bank account** field, select **GBSI OPER**.</span></span>

7. <span data-ttu-id="d4bff-354">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-354">Select **OK**.</span></span>
8. <span data-ttu-id="d4bff-355">Na caixa de diálogo **Parâmetros de relatório eletrônico**, defina a opção **Imprimir relatório de controle** como **Sim** e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-355">In the **Electronic report parameters** dialog box, set the **Print control report** option to **Yes**, and then select **OK**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d4bff-356">Além do arquivo de pagamento, você só pode gerar o relatório de controle.</span><span class="sxs-lookup"><span data-stu-id="d4bff-356">In addition to the payment file, you can generate only the control report.</span></span>

9. <span data-ttu-id="d4bff-357">Baixe o arquivo zip e extraia os seguintes arquivos dele:</span><span class="sxs-lookup"><span data-stu-id="d4bff-357">Download the zip file, and then extract the following files from it:</span></span>

    - <span data-ttu-id="d4bff-358">O relatório de controle no formato Excel</span><span class="sxs-lookup"><span data-stu-id="d4bff-358">The control report in Excel format</span></span>
    - <span data-ttu-id="d4bff-359">O arquivo de pagamento no formato TXT</span><span class="sxs-lookup"><span data-stu-id="d4bff-359">The payment file in TXT format</span></span>

        <span data-ttu-id="d4bff-360">Observe que, de acordo com a estrutura do seu formato de ER personalizado, agora a linha de pagamento no arquivo gerado [começa](#PositionSWIFTCode) com o código Swift que foi [inserido](#DefineSWIFTCode) para a conta bancária do fornecedor cujo pagamento foi processado.</span><span class="sxs-lookup"><span data-stu-id="d4bff-360">Notice that, in accordance with the structure of your custom ER format, the payment line in the generated file now [starts](#PositionSWIFTCode) with the SWIFT code that was [entered](#DefineSWIFTCode) for the bank account of the vendor whose payment has been processed.</span></span>

        ![Arquivo de pagamento no formato TXT](./media/er-quick-start2-payment-file2.png)

## <a name="import-new-versions-of-the-standard-er-format-configurations"></a><a id="ImportERSolution2"></a><span data-ttu-id="d4bff-362">Importar novas versões das configurações do formato de ER padrão</span><span class="sxs-lookup"><span data-stu-id="d4bff-362">Import new versions of the standard ER format configurations</span></span>

<span data-ttu-id="d4bff-363">Para o exemplo mostrado nesta seção, você recebe uma notificação sobre o artigo da Base de Dados de Conhecimento [KB3763330](https://fix.lcs.dynamics.com/Issue/Details?kb=3182046).</span><span class="sxs-lookup"><span data-stu-id="d4bff-363">For the example that is shown in this section, you receive a notification about Knowledge Base article [KB3763330](https://fix.lcs.dynamics.com/Issue/Details?kb=3182046).</span></span> <span data-ttu-id="d4bff-364">Essa notificação informa sobre a nova versão do formato de ER **BACS (Reino Unido)** publicada pela Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d4bff-364">This notification informs you about the new version of the **BACS (UK)** ER format that has been published by Microsoft.</span></span> <span data-ttu-id="d4bff-365">Além do relatório de controle, essa nova versão permite que os usuários gerem o relatório de aviso de pagamento e o relatório de nota de participação enquanto um pagamento de fornecedor estiver sendo processado.</span><span class="sxs-lookup"><span data-stu-id="d4bff-365">In addition to the control report, this new version lets users generate the payment advice report and the attending note report while a vendor payment is being processed.</span></span> <span data-ttu-id="d4bff-366">Você quer começar a usar essa funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="d4bff-366">You want to start to use that functionality.</span></span>

### <a name="import-new-versions-of-the-standard-er-configurations"></a><a id="ImportERFormat2"></a><span data-ttu-id="d4bff-367">Importar novas versões das configurações de ER padrão</span><span class="sxs-lookup"><span data-stu-id="d4bff-367">Import new versions of the standard ER configurations</span></span>

<span data-ttu-id="d4bff-368">Para adicionar novas versões das configurações de ER à instância atual do Finance, você deve importá-las do [repositório](general-electronic-reporting.md#Repository) de ER que configurou.</span><span class="sxs-lookup"><span data-stu-id="d4bff-368">To add new versions of the ER configurations to the current Finance instance, you must import them from the ER [repository](general-electronic-reporting.md#Repository) that you've configured.</span></span>

1. <span data-ttu-id="d4bff-369">Vá para **Administração da organização** \> **Espaços de trabalho** \> **Relatório eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-369">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="d4bff-370">Na página **Configurações de localização**, na seção **Provedores de configuração**, selecione o bloco **Microsoft** e, depois, selecione **Repositórios** para ver a lista de repositórios do provedor Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d4bff-370">On the **Localization configurations** page, in the **Configuration providers** section, select the **Microsoft** tile, and then select **Repositories** to view the list of repositories for the Microsoft provider.</span></span>
3. <span data-ttu-id="d4bff-371">Na página **Repositórios de configuração**, selecione o repositório do tipo **Global** e, depois, selecione **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-371">On the **Configuration repositories** page, select the repository of the **Global** type, and then select **Open**.</span></span> <span data-ttu-id="d4bff-372">Se você precisar de autorização para se conectar ao Regulatory Configuration Service, siga as instruções de autorização.</span><span class="sxs-lookup"><span data-stu-id="d4bff-372">If you're prompted for authorization to connect to Regulatory Configuration Service, follow the authorization instructions.</span></span>
4. <span data-ttu-id="d4bff-373">Na página **Repositório de configuração**, na árvore de configuração no painel esquerdo, selecione a configuração de formato **BACS (Reino Unido)**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-373">On the **Configuration repository** page, in the configuration tree in the left pane, select the **BACS (UK)** format configuration.</span></span>
5. <span data-ttu-id="d4bff-374">Na FastTab **Versões**, selecione a versão **3.3** da configuração do formato de ER selecionada.</span><span class="sxs-lookup"><span data-stu-id="d4bff-374">On the **Versions** FastTab, select version **3.3** of the selected ER format configuration.</span></span>
6. <span data-ttu-id="d4bff-375">Selecione **Importar** para baixar a versão selecionada do repositório global para a instância atual do Finance.</span><span class="sxs-lookup"><span data-stu-id="d4bff-375">Select **Import** to download the selected version from the Global repository to the current Finance instance.</span></span>

![Página do repositório de configuração](./media/er-quick-start2-import-solution2.png)

> [!TIP]
> <span data-ttu-id="d4bff-377">Se você tiver problemas para acessar o [repositório global](er-download-configurations-global-repo.md), poderá [baixar configurações](download-electronic-reporting-configuration-lcs.md) do LCS.</span><span class="sxs-lookup"><span data-stu-id="d4bff-377">If you have trouble accessing the [Global repository](er-download-configurations-global-repo.md), you can [download configurations](download-electronic-reporting-configuration-lcs.md) from LCS instead.</span></span>

### <a name="review-the-imported-er-format-configurations"></a><a id="ReviewImportedERFormat"></a><span data-ttu-id="d4bff-378">Examinar as configurações do formato de ER importado</span><span class="sxs-lookup"><span data-stu-id="d4bff-378">Review the imported ER format configurations</span></span>

1. <span data-ttu-id="d4bff-379">Vá para **Administração da organização** \> **Espaços de trabalho** \> **Relatório eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-379">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="d4bff-380">Na página **Configurações de localização**, na seção **Configurações**, selecione o título **Configurações de relatórios**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-380">On the **Localization configurations** page, in the **Configurations** section, select the **Reporting configurations** tile.</span></span>
3. <span data-ttu-id="d4bff-381">Na página **Configurações**, na árvore de configuração no painel esquerdo, expanda **Modelo de pagamento** e selecione **BACS (Reino Unido)**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-381">On the **Configurations** page, in the configuration tree in the left pane, expand **Payment model**, and then select **BACS (UK)**.</span></span>
4. <span data-ttu-id="d4bff-382">Na Guia Rápida **Versões**, selecione a versão **3.3**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-382">On the **Versions** FastTab, select version **3.3**.</span></span>
5. <span data-ttu-id="d4bff-383">Selecione **Designer**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-383">Select **Designer**.</span></span>
6. <span data-ttu-id="d4bff-384">Na página **Designer de formato**, expanda o elemento de formato **BACSReportsFolder**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-384">On the **Format designer** page, expand the **BACSReportsFolder** format element.</span></span>
7.  <span data-ttu-id="d4bff-385">Observe que a versão 3.3 contém o elemento de formato **PaymentAdviceReport** usado para gerar um relatório de aviso de pagamento quando um pagamento de fornecedor é processado.</span><span class="sxs-lookup"><span data-stu-id="d4bff-385">Notice that version 3.3 contains the **PaymentAdviceReport** format element that is used to generate a payment advice report when a vendor payment is processed.</span></span>

    ![Elemento de formato PaymentAdviceReport no designer de operações de ER](./media/er-quick-start2-imported-solution2.png)

8. <span data-ttu-id="d4bff-387">Feche a página do designer.</span><span class="sxs-lookup"><span data-stu-id="d4bff-387">Close the designer page.</span></span>

## <a name="adopt-the-changes-in-the-new-version-of-an-imported-format-in-a-custom-format"></a><a id="AdoptNewBaseVersion"></a><span data-ttu-id="d4bff-388">Adotar as alterações na nova versão de um formato importado em um formato personalizado</span><span class="sxs-lookup"><span data-stu-id="d4bff-388">Adopt the changes in the new version of an imported format in a custom format</span></span>

### <a name="complete-the-current-draft-version-of-a-custom-format"></a><a id="CompleteDerivedFormat"></a><span data-ttu-id="d4bff-389">Concluir a versão de rascunho atual de um formato personalizado</span><span class="sxs-lookup"><span data-stu-id="d4bff-389">Complete the current draft version of a custom format</span></span>

<span data-ttu-id="d4bff-390">Se você quiser manter o estado atual do seu formato personalizado, conclua a versão de rascunho 1.1.1 alterando o status de **Rascunho** para **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-390">If you want to keep the current state of your custom format, complete the draft version 1.1.1 by changing its status from **Draft** to **Completed**.</span></span>

1. <span data-ttu-id="d4bff-391">Vá para **Administração da organização** \> **Espaços de trabalho** \> **Relatório eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-391">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="d4bff-392">Na página **Configurações de localização**, na seção **Configurações**, selecione o título **Configurações de relatórios**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-392">On the **Localization configurations** page, in the **Configurations** section, select the **Reporting configurations** tile.</span></span>
3. <span data-ttu-id="d4bff-393">Na página **Configurações**, na árvore de configuração no painel esquerdo, expanda **Modelo de pagamento**, expanda **BACS (Reino Unido)** e selecione **BACS (personalizado do Reino Unido)**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-393">On the **Configurations** page, in the configuration tree in the left pane, expand **Payment model**, expand **BACS (UK)**, and then select **BACS (UK custom)**.</span></span>
4. <span data-ttu-id="d4bff-394">Na FastTab **Versões**, selecione **Alterar status** \> **Concluído** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-394">On the **Versions** FastTab, select **Change status** \> **Complete**, and then select **OK**.</span></span>

<span data-ttu-id="d4bff-395">O status da versão 1.1.1 muda de **Rascunho** para **Concluído** e a versão se torna somente leitura.</span><span class="sxs-lookup"><span data-stu-id="d4bff-395">The status of version 1.1.1 is changed from **Draft** to **Completed**, and the version becomes read-only.</span></span> <span data-ttu-id="d4bff-396">Uma nova versão editável, 1.1.2, foi adicionada e tem o status de **Rascunho**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-396">A new editable version, 1.1.2, has been added and has a status of **Draft**.</span></span> <span data-ttu-id="d4bff-397">Você pode usar essa versão para fazer outras alterações no formato de ER personalizado.</span><span class="sxs-lookup"><span data-stu-id="d4bff-397">You can use this version to make further changes in your custom ER format.</span></span>

### <a name="rebase-a-custom-format-to-a-new-base-version"></a><a id="RebaseDerivedFormat"></a><span data-ttu-id="d4bff-398">Trocar base de um formato personalizado para uma nova versão base</span><span class="sxs-lookup"><span data-stu-id="d4bff-398">Rebase a custom format to a new base version</span></span>

<span data-ttu-id="d4bff-399">Para começar a usar a nova funcionalidade da versão 3.3 do formato **BACS (Reino Unido)** na sua personalização, você deve alterar a versão de configuração base da configuração personalizada, **BACS (personalizado do Reino Unido)**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-399">To start to use the new functionality of version 3.3 of the **BACS (UK)** format in your customization, you must change the base configuration version for the custom configuration, **BACS (UK custom)**.</span></span> <span data-ttu-id="d4bff-400">Esse processo é conhecido como [troca de base](general-electronic-reporting.md#upgrading-a-format-selecting-a-new-version-of-base-format-rebase).</span><span class="sxs-lookup"><span data-stu-id="d4bff-400">This process is known as [rebasing](general-electronic-reporting.md#upgrading-a-format-selecting-a-new-version-of-base-format-rebase).</span></span> <span data-ttu-id="d4bff-401">Em vez da versão 1.1 de **BACS (Reino Unido)**, use a versão 3.3.</span><span class="sxs-lookup"><span data-stu-id="d4bff-401">Instead of version 1.1 of **BACS (UK)**, use version 3.3.</span></span>

1. <span data-ttu-id="d4bff-402">Vá para **Administração da organização** \> **Relatório eletrônico** \> **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-402">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="d4bff-403">Na página **Configurações**, na árvore de configuração no painel esquerdo, expanda **Modelo de pagamento** e selecione **BACS (personalizado do Reino Unido)**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-403">On the **Configurations** page, in the configuration tree in the left pane, expand **Payment model**, and then select **BACS (UK custom)**.</span></span>
3. <span data-ttu-id="d4bff-404">Na FastTab **Versões**, selecione a versão **1.1.2** e, depois, **Trocar base**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-404">On the **Versions** FastTab, select version **1.1.2**, and then select **Rebase**.</span></span>
4. <span data-ttu-id="d4bff-405">Na caixa de diálogo **Trocar base**, no campo **Versão de destino**, selecione a versão **3.3** da configuração base para aplicá-la como a nova base e usá-la para atualizar a configuração.</span><span class="sxs-lookup"><span data-stu-id="d4bff-405">In the **Rebase** dialog box, in the **Target version** field, select version **3.3** of the base configuration to apply it as the new base and use it to update the configuration.</span></span>

    ![Caixa de diálogo Trocar base](./media/er-quick-start2-rebase1.png)

5. <span data-ttu-id="d4bff-407">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-407">Select **OK**.</span></span>
6. <span data-ttu-id="d4bff-408">Observe que o número da versão de rascunho foi alterado de **1.1.2** para **3.3.2** para refletir a mudança na versão base.</span><span class="sxs-lookup"><span data-stu-id="d4bff-408">Notice that the number of the draft version has been changed from **1.1.2** to **3.3.2** to reflect the change in the base version.</span></span>

    <span data-ttu-id="d4bff-409">Quando a versão personalizada e uma nova versão base são mescladas, podem surgir alguns conflitos por causa de alterações no formato que não podem ser mescladas automaticamente.</span><span class="sxs-lookup"><span data-stu-id="d4bff-409">When the custom version and a new base version are merged, some conflicts might be discovered because of format changes that can't be merged automatically.</span></span>

    ![Configuração de base trocada com conflitos na página Configurações](./media/er-quick-start2-rebase2.png)

    <span data-ttu-id="d4bff-411">Se forem detectados conflitos, eles deverão ser resolvidos manualmente no designer de formato.</span><span class="sxs-lookup"><span data-stu-id="d4bff-411">If conflicts are discovered, they must be manually resolved in the format designer.</span></span>

7. <span data-ttu-id="d4bff-412">Na Guia Rápida **Versões**, selecione a versão **3.3.2**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-412">On the **Versions** FastTab, select version **3.3.2**.</span></span>
8. <span data-ttu-id="d4bff-413">Selecione **Designer**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-413">Select **Designer**.</span></span>
9. <span data-ttu-id="d4bff-414">Na página **Designer de formato**, na FastTab **Detalhes**, selecione um registro de conflito de troca de base e selecione **Aplicar valor base**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-414">On the **Format designer** page, on the **Details** FastTab, select a rebase conflict record, and then select **Apply base value**.</span></span>

    ![Registro de conflito de troca de base no designer de operações de ER](./media/er-quick-start2-rebase3.png)

10. <span data-ttu-id="d4bff-416">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-416">Select **Save**.</span></span>

    <span data-ttu-id="d4bff-417">O registro do conflito de troca de base não deve mais aparecer na FastTab **Detalhes**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-417">The rebase conflict record should no longer appear on the **Details** FastTab.</span></span>

    ![Conflito resolvido no designer de operações de ER](./media/er-quick-start2-rebase4.png)

    > [!NOTE]
    > <span data-ttu-id="d4bff-419">Você resolveu o conflito confirmando que a versão 3 do modelo base deve ser usada neste formato de ER.</span><span class="sxs-lookup"><span data-stu-id="d4bff-419">You resolved the conflict by confirming that version 3 of the base model must be used in this ER format.</span></span>

11. <span data-ttu-id="d4bff-420">Expanda **BACSReportsFolder** \> **arquivo** \> **transações** \> **transação**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-420">Expand **BACSReportsFolder** \> **file** \> **transactions** \> **transaction**.</span></span>
12. <span data-ttu-id="d4bff-421">Na guia **Mapeamento**, observe que a versão 3.3.2 do seu formato de ER personalizado contém sua personalização (o elemento de formato **vendBankSWIFT** e sua associação) e a nova funcionalidade da versão 3.3 do formato de ER base fornecido pela Microsoft (o elemento de formato **PaymentAdviceReport** junto com os elementos aninhados e associações configuradas).</span><span class="sxs-lookup"><span data-stu-id="d4bff-421">On the **Mapping** tab, notice that version 3.3.2 of your custom ER format contains both your customization (the **vendBankSWIFT** format element and its binding) and the new functionality of version 3.3 of the base ER format that was provided by Microsoft (the **PaymentAdviceReport** format element together with its nested elements and configured bindings).</span></span> <span data-ttu-id="d4bff-422">Com apenas alguns cliques do mouse, você adotou as modificações de uma nova versão base mesclando-as com sua personalização.</span><span class="sxs-lookup"><span data-stu-id="d4bff-422">In just a few mouse clicks, you adopted the modifications of a new base version by merging them with your customization.</span></span>

    ![Formato mesclado no designer de operações de ER](./media/er-quick-start2-rebase5.png)

13. <span data-ttu-id="d4bff-424">Feche a página do designer.</span><span class="sxs-lookup"><span data-stu-id="d4bff-424">Close the designer page.</span></span>

> [!NOTE]
> <span data-ttu-id="d4bff-425">A ação de troca de base é reversível.</span><span class="sxs-lookup"><span data-stu-id="d4bff-425">The rebase action is reversible.</span></span> <span data-ttu-id="d4bff-426">Para cancelar essa troca de base, selecione a versão **1.1.1** do formato **BACS (personalizado do Reino Unido)** na FastTab **Versões** e selecione **Obter esta versão**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-426">To cancel this rebase, select version **1.1.1** of the **BACS (UK custom)** format on the **Versions** FastTab, and then select **Get this version**.</span></span> <span data-ttu-id="d4bff-427">A versão 3.3.2 será renumerada para 1.1.2, e o conteúdo da versão de rascunho 1.1.2 será compatível com o conteúdo da versão 1.1.1.</span><span class="sxs-lookup"><span data-stu-id="d4bff-427">Version 3.3.2 will then be renumbered 1.1.2, and the content of draft version 1.1.2 will match the content of version 1.1.1.</span></span>

### <a name="process-a-vendor-payment-by-using-a-rebased-er-format"></a><a id="ProcessPayment3"></a><span data-ttu-id="d4bff-428">Processar um pagamento de fornecedor usando o formato de ER com troca de base</span><span class="sxs-lookup"><span data-stu-id="d4bff-428">Process a vendor payment by using a rebased ER format</span></span>

1. <span data-ttu-id="d4bff-429">Vá para **Contas a pagar** \> **Pagamentos** \> **Diário de pagamentos do fornecedor**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-429">Go to **Accounts payable** \> **Payments** \> **Vendor payment journal**.</span></span>
2. <span data-ttu-id="d4bff-430">Na página **Diário de pagamentos do fornecedor**, selecione o diário de pagamento que você criou anteriormente.</span><span class="sxs-lookup"><span data-stu-id="d4bff-430">On the **Vendor payment journal** page, select the payment journal that you created earlier.</span></span>
3. <span data-ttu-id="d4bff-431">Selecione **Linhas**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-431">Select **Lines**.</span></span>
4. <span data-ttu-id="d4bff-432">Na página **Pagamentos de fornecedores**, acima da grade, selecione **Status do pagamento** \> **Nenhum**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-432">On the **Vendor payments** page, above the grid, select **Payment status** \> **None**.</span></span>
5. <span data-ttu-id="d4bff-433">Selecione **Gerar pagamento**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-433">Select **Generate payment**.</span></span>
6. <span data-ttu-id="d4bff-434">Na caixa de diálogo **Gerar pagamentos**, insira as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="d4bff-434">In the **Generate payments** dialog box, enter the following information:</span></span>

    - <span data-ttu-id="d4bff-435">No campo **Método de pagamento**, selecione **Eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-435">In the **Method of payment** field, select **Electronic**.</span></span>
    - <span data-ttu-id="d4bff-436">No campo **Conta bancária**, selecione **GBSI OPER**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-436">In the **Bank account** field, select **GBSI OPER**.</span></span>

7. <span data-ttu-id="d4bff-437">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-437">Select **OK**.</span></span>
8. <span data-ttu-id="d4bff-438">Na caixa de diálogo **Parâmetros de relatório eletrônico**, insira as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="d4bff-438">In the **Electronic report parameters** dialog box, enter the following information:</span></span>

    - <span data-ttu-id="d4bff-439">Defina a opção **Imprimir relatório de controle** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-439">Set the **Print control report** option to **Yes**.</span></span>
    - <span data-ttu-id="d4bff-440">Defina a opção **Imprimir aviso de pagamento** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-440">Set the **Print payment advice** option to **Yes**.</span></span>

    ![Caixa de diálogo Parâmetros de Relatório eletrônico](./media/er-quick-start2-payment-dialog2.png)

    > [!NOTE]
    > <span data-ttu-id="d4bff-442">Além do arquivo de pagamento, agora é possível gerar o relatório de controle e o relatório de aviso de pagamento.</span><span class="sxs-lookup"><span data-stu-id="d4bff-442">In addition to the payment file, you can now generate both the control report and the payment advice report.</span></span>

9. <span data-ttu-id="d4bff-443">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="d4bff-443">Select **OK**.</span></span>
10. <span data-ttu-id="d4bff-444">Baixe o arquivo zip e extraia os seguintes arquivos dele:</span><span class="sxs-lookup"><span data-stu-id="d4bff-444">Download the zip file, and then extract the following files from it:</span></span>

    - <span data-ttu-id="d4bff-445">O relatório de controle no formato Excel</span><span class="sxs-lookup"><span data-stu-id="d4bff-445">The control report in Excel format</span></span>
    - <span data-ttu-id="d4bff-446">O relatório de aviso de pagamento no formato Excel</span><span class="sxs-lookup"><span data-stu-id="d4bff-446">The payment advice report in Excel format</span></span>

        ![Relatório de aviso de pagamento no formato Excel](./media/er-quick-start2-payment-advice-report.png)

    - <span data-ttu-id="d4bff-448">O arquivo de pagamento no formato TXT</span><span class="sxs-lookup"><span data-stu-id="d4bff-448">The payment file in TXT format</span></span>

        <span data-ttu-id="d4bff-449">Observe que a linha de pagamento no arquivo gerado começa com o código Swift que foi inserido para a conta bancária de um fornecedor cujo pagamento foi processado.</span><span class="sxs-lookup"><span data-stu-id="d4bff-449">Notice that the payment line in the generated file starts  with the SWIFT code that was entered for the bank account of a vendor whose payment has been processed.</span></span>

        ![Arquivo de pagamento no formato TXT](./media/er-quick-start2-payment-file3.png)

## <a name="additional-resources"></a><a id="References"></a><span data-ttu-id="d4bff-451">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="d4bff-451">Additional resources</span></span>

- [<span data-ttu-id="d4bff-452">Visão geral do Relatório Eletrônico</span><span class="sxs-lookup"><span data-stu-id="d4bff-452">Electronic Reporting overview</span></span>](general-electronic-reporting.md)
- [<span data-ttu-id="d4bff-453">Baixar configurações de ER do Lifecycle Services</span><span class="sxs-lookup"><span data-stu-id="d4bff-453">Download ER configurations from Lifecycle Services</span></span>](download-electronic-reporting-configuration-lcs.md)
- [<span data-ttu-id="d4bff-454">Baixar configurações de ER do repositório global de serviço de configuração</span><span class="sxs-lookup"><span data-stu-id="d4bff-454">Download ER configurations from Global repository of Configuration service</span></span>](er-download-configurations-global-repo.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]