---
title: Introdução ao complemento de faturamento eletrônico para a Itália
description: Este tópico fornece informações que ajudarão você a começar a usar o complemento de faturamento eletrônico para o Itália no Microsoft Dynamics 365 Finance e no Dynamics 365 Supply Chain Management.
author: gionoder
manager: AnnBe
ms.date: 09/22/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 9c50000c98bdde2c9da43b3110686aa5d01e8081
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5259211"
---
# <a name="get-started-with-the-electronic-invoicing-add-on-for-italy"></a><span data-ttu-id="00907-103">Introdução ao complemento de faturamento eletrônico para a Itália</span><span class="sxs-lookup"><span data-stu-id="00907-103">Get started with the Electronic invoicing add-on for Italy</span></span>

[!include [banner](../includes/banner.md)]


> [!IMPORTANT]
> <span data-ttu-id="00907-104">O complemento eletrônico de faturamento para a Itália talvez não ofereça suporte no momento a todas as funções disponíveis para faturas eletrônicas no Microsoft Dynamics 365 Finance e no Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="00907-104">The Electronic invoicing add-on for Italy might not currently support all the functions that are available for electronic invoices in Microsoft Dynamics 365 Finance and Dynamics 365 Supply Chain Management.</span></span> 

<span data-ttu-id="00907-105">Este tópico fornece informações que ajudarão você a começar a usar o complemento de faturamento eletrônico para a Itália.</span><span class="sxs-lookup"><span data-stu-id="00907-105">This topic provides information that will help you get started with the Electronic invoicing add-on for Italy.</span></span> <span data-ttu-id="00907-106">Ele o orienta você pelas etapas de configuração que dependem do país para os Regulatory Configuration Services (RCS) e no Finance.</span><span class="sxs-lookup"><span data-stu-id="00907-106">It guides you through the configuration steps that are country-dependent in Regulatory Configuration Services (RCS) and Finance.</span></span> <span data-ttu-id="00907-107">Ele também o orienta durante o processo de envio de faturas eletrônicas geradas no formato **FatturaPA** específico da Itália pelo serviço e explica como revisar os resultados do processamento.</span><span class="sxs-lookup"><span data-stu-id="00907-107">It also guides you through the process for submitting electronic invoices that are generated in the Italy-specific **FatturaPA** format through the service, and it explains how to review the results of processing.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="00907-108">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="00907-108">Prerequisites</span></span>

<span data-ttu-id="00907-109">Antes de concluir as etapas deste tópico, você deve concluir as etapas em [Introdução ao complemento do faturamento eletrônico](e-invoicing-get-started.md).</span><span class="sxs-lookup"><span data-stu-id="00907-109">Before you complete the steps in this topic, you must complete the steps in [Get started with the Electronic invoicing add-on](e-invoicing-get-started.md).</span></span>

## <a name="rcs-setup"></a><span data-ttu-id="00907-110">Configuração do RCS</span><span class="sxs-lookup"><span data-stu-id="00907-110">RCS setup</span></span>

<span data-ttu-id="00907-111">Durante a configuração do RCS, você concluirá estas tarefas:</span><span class="sxs-lookup"><span data-stu-id="00907-111">During the RCS setup, you will complete these tasks:</span></span>

1. <span data-ttu-id="00907-112">Importe o recurso de faturamento eletrônico para a exportação de faturas eletrônicas de clientes no formato **FatturaPA**.</span><span class="sxs-lookup"><span data-stu-id="00907-112">Import the e-Invoicing feature for the export of customer electronic invoices in the **FatturaPA** format.</span></span>
2. <span data-ttu-id="00907-113">Examine as configurações de formato necessárias para gerar, enviar e receber respostas sobre faturas eletrônicas.</span><span class="sxs-lookup"><span data-stu-id="00907-113">Review the format configurations that are required to generate, submit, and receive responses about electronic invoices.</span></span>
3. <span data-ttu-id="00907-114">Configure os eventos que dão suporte a cenários de envio de fatura eletrônica.</span><span class="sxs-lookup"><span data-stu-id="00907-114">Configure the events that support the electronic invoice submission scenarios.</span></span>
4. <span data-ttu-id="00907-115">Publique o recurso de faturamento eletrônica.</span><span class="sxs-lookup"><span data-stu-id="00907-115">Publish the e-Invoicing feature.</span></span>

> [!NOTE]
> <span data-ttu-id="00907-116">O "recurso de faturamento eletrônico" é o nome genérico do recurso configurado e publicado para consumir o servidor do complemento de faturamento eletrônico.</span><span class="sxs-lookup"><span data-stu-id="00907-116">"The e-Invoicing feature" is the generic name for the resource that is configured and published to consume the Electronic invoicing add-on server.</span></span> <span data-ttu-id="00907-117">Neste caso, a exportação de faturas eletrônicas de clientes é o recurso de faturamento eletrônico que você configurará.</span><span class="sxs-lookup"><span data-stu-id="00907-117">In this case, the export of customer electronic invoices is the e-Invoicing feature that you will set up.</span></span>

## <a name="import-the-e-invoicing-feature"></a><span data-ttu-id="00907-118">Importar o recurso de faturamento eletrônico</span><span class="sxs-lookup"><span data-stu-id="00907-118">Import the e-Invoicing feature</span></span>

1. <span data-ttu-id="00907-119">Entre em sua conta do RCS.</span><span class="sxs-lookup"><span data-stu-id="00907-119">Sign in to your RCS account.</span></span>
2. <span data-ttu-id="00907-120">No espaço de trabalho **Recursos de globalização**, na seção **Recursos**, selecione o bloco **Faturamento eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="00907-120">In the **Globalization features** workspace, in the **Features** section, select the **e-Invoicing** tile.</span></span>
3. <span data-ttu-id="00907-121">Na página **Recursos de faturamento eletrônico**, selecione **Importar** para importar o recurso de faturamento eletrônico do Repositório global.</span><span class="sxs-lookup"><span data-stu-id="00907-121">On the **e-Invoicing Features** page, select **Import** to import the e-Invoicing feature from the Global repository.</span></span>

    > [!NOTE]
    > <span data-ttu-id="00907-122">Se você não vir a lista de recursos disponíveis, selecione **Sincronizar**.</span><span class="sxs-lookup"><span data-stu-id="00907-122">If you don't see the list of available features, select **Synchronize**.</span></span> 

4. <span data-ttu-id="00907-123">Selecione o recurso **Exportação de Faturas Eletrônicas (TI)** e, em seguida, selecione **Importar**.</span><span class="sxs-lookup"><span data-stu-id="00907-123">Select the **e-Invoices Export (IT)** feature, and then select **Import**.</span></span>

![Importa o recurso de exportação de faturas eletrônicas (TI)](media/e-Invoicing-services-get-started-ITA-Select-Import-e-Invoicing-feature.png)

<span data-ttu-id="00907-125">Quando você importa o recurso **Exportação de faturas eletrônicas (TI)** do Repositório global, todas as configurações descritas nas próximas seções também são importadas.</span><span class="sxs-lookup"><span data-stu-id="00907-125">When you import the **e-Invoices Export (IT)** feature from the Global repository, all the settings that are described in the next sections are also imported.</span></span>

## <a name="create-a-new-version-of-the-e-invoices-export-it-feature"></a><span data-ttu-id="00907-126">Criar uma nova versão do recurso Exportação de Faturas Eletrônicas (TI)</span><span class="sxs-lookup"><span data-stu-id="00907-126">Create a new version of the e-Invoices Export (IT) feature</span></span>

1. <span data-ttu-id="00907-127">Na página **Recursos de faturamento eletrônico**, na guia **Versões**, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="00907-127">On the **e-Invoicing Features** page, on the **Versions** tab, select **New**.</span></span> 

    ![Adicionar uma nova versão do recurso de faturamento eletrônico](media/e-Invoicing-services-get-started-ITA-Select-New-e-Invoicing-feature-version.png)

    <span data-ttu-id="00907-129">Em seguida, você configurará os formatos ER (relatório eletrônico) associados ao recurso de faturamento eletrônico.</span><span class="sxs-lookup"><span data-stu-id="00907-129">Next, you will configure the Electronic reporting (ER) formats that are associated with the e-Invoicing feature.</span></span>

2. <span data-ttu-id="00907-130">Na guia **Configurações**, selecione **Adicionar** para gerenciar as versões de configuração.</span><span class="sxs-lookup"><span data-stu-id="00907-130">On the **Configurations** tab, select **Add** to manage the configuration versions.</span></span>

    ![Gerenciar as versões de configuração do recurso de faturamento eletrônico](media/e-Invoicing-services-get-started-ITA-Manage-e-Invoicing-feature-configurations.png)

    <span data-ttu-id="00907-132">Nesta etapa, você está adicionando e configurando os formatos ER de arquivos diferentes que são usados para exportar faturas eletrônicas italianas.</span><span class="sxs-lookup"><span data-stu-id="00907-132">In this step, you're adding and configuring the ER formats of different files that are used to export Italian e-invoices.</span></span> <span data-ttu-id="00907-133">Para faturas eletrônicas italianas FatturaPA, use as seguintes configurações padrão ou as configurações personalizadas reais usadas para faturamento eletrônico:</span><span class="sxs-lookup"><span data-stu-id="00907-133">For Italian FatturaPA e-invoices, use either the following standard configurations or the actual customized configurations that you use for e-invoicing:</span></span>

    - <span data-ttu-id="00907-134">Fatura de venda (TI)</span><span class="sxs-lookup"><span data-stu-id="00907-134">Sales invoice (IT)</span></span>
    - <span data-ttu-id="00907-135">Fatura de projeto (TI)</span><span class="sxs-lookup"><span data-stu-id="00907-135">Project invoice (IT)</span></span>

    <span data-ttu-id="00907-136">Quando você cria um recurso de faturamento eletrônico que deriva de outro recurso de faturamento eletrônico, todos os formatos ER são herdados do recurso original.</span><span class="sxs-lookup"><span data-stu-id="00907-136">When you create an e-Invoicing feature that is derived from another e-Invoicing feature, all ER formats are inherited from the original feature.</span></span>

3. <span data-ttu-id="00907-137">Selecione uma configuração de arquivo de formato ER específica.</span><span class="sxs-lookup"><span data-stu-id="00907-137">Select a specific ER format file configuration.</span></span>
4. <span data-ttu-id="00907-138">Selecione **Editar** ou **Exibir** para abrir a página **Designer de formato**.</span><span class="sxs-lookup"><span data-stu-id="00907-138">Select **Edit** or **View** to open the **Format designer** page.</span></span>

    ![Abrir a página Designer de formato](media/e-Invoicing-services-get-started-ITA-Configuration-ER-format-designer.png)

5. <span data-ttu-id="00907-140">Use a página **Designer de formato** para editar e exibir as configurações do arquivo de formato ER.</span><span class="sxs-lookup"><span data-stu-id="00907-140">Use the **Format designer** page to edit and view the ER format file configurations.</span></span>

    ![Página do designer de formatos](media/e-Invoicing-services-get-started-ITA-ER-format-designer.png)

## <a name="manage-the-e-invoicing-feature-setups"></a><span data-ttu-id="00907-142">Gerenciar as configurações do recurso de faturamento eletrônico</span><span class="sxs-lookup"><span data-stu-id="00907-142">Manage the e-Invoicing feature setups</span></span>

- <span data-ttu-id="00907-143">Na página **Recursos de faturamento eletrônico**, na guia **Configurações**, selecione **Adicionar**, **Excluir** ou **Editar** para gerenciar as configurações do recurso de faturamento eletrônico.</span><span class="sxs-lookup"><span data-stu-id="00907-143">On the **e-Invoicing Features** page, on the **Setups** tab, select **Add**, **Delete**, or **Edit** to manage the e-Invoicing feature setups.</span></span>

![Gerenciar as configurações do recurso de faturamento eletrônico](media/e-Invoicing-services-get-started-ITA-Manage-e-Invoicing-feature-setup.png)

<span data-ttu-id="00907-145">Nesta etapa, você configura os eventos aplicáveis a faturas eletrônicas, incluindo a geração de arquivos de saída XML no formato **FatturaPA** e na assinatura digital (se necessário).</span><span class="sxs-lookup"><span data-stu-id="00907-145">In this step, you configure the events that are applicable to electronic invoices, including generation of the XML output files in **FatturaPA** format and digital signing (if required).</span></span>

### <a name="configure-the-sales-invoice-feature-setup"></a><span data-ttu-id="00907-146">Definir a configuração do recurso de fatura de venda</span><span class="sxs-lookup"><span data-stu-id="00907-146">Configure the Sales invoice feature setup</span></span>

1. <span data-ttu-id="00907-147">Na página **Recursos de faturamento eletrônico**, na guia **Configurações**, na coluna **Configuração do recurso**, selecione **Fatura de venda**.</span><span class="sxs-lookup"><span data-stu-id="00907-147">On the **e-Invoicing Features** page, on the **Setups** tab, in the **Feature setup** column, select **Sales invoice**.</span></span>
2. <span data-ttu-id="00907-148">Selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="00907-148">Select **Edit**.</span></span>
3. <span data-ttu-id="00907-149">Na página **Configuração de versão do recurso**, selecione a guia **Ações** para gerenciar a lista de ações.</span><span class="sxs-lookup"><span data-stu-id="00907-149">On the **Feature version setup** page, select the **Actions** tab to manage the list of actions.</span></span> <span data-ttu-id="00907-150">As ações definem uma lista de operações que devem ser executadas na ordem sequencial para realizar a execução total do evento.</span><span class="sxs-lookup"><span data-stu-id="00907-150">Actions define a list of operations that must be run in sequential order to accomplish full execution of the event.</span></span>

    ![Guia Ações](media/e-Invoicing-services-get-started-ITA-Select-Actions.png)

    | <span data-ttu-id="00907-152">ID de ação</span><span class="sxs-lookup"><span data-stu-id="00907-152">Action ID</span></span> | <span data-ttu-id="00907-153">Nome da ação</span><span class="sxs-lookup"><span data-stu-id="00907-153">Action name</span></span>        | <span data-ttu-id="00907-154">Descrição da ação</span><span class="sxs-lookup"><span data-stu-id="00907-154">Action description</span></span>                                     |
    |-----------|--------------------|--------------------------------------------------------|
    | <span data-ttu-id="00907-155">1</span><span class="sxs-lookup"><span data-stu-id="00907-155">1</span></span>         | <span data-ttu-id="00907-156">Transformar documento</span><span class="sxs-lookup"><span data-stu-id="00907-156">Transform document</span></span> | <span data-ttu-id="00907-157">Crie o arquivo XML de faturamento eletrônico no formato **FatturaPA**.</span><span class="sxs-lookup"><span data-stu-id="00907-157">Create the e-invoice XML file in **FatturaPA** format.</span></span> |
    | <span data-ttu-id="00907-158">2</span><span class="sxs-lookup"><span data-stu-id="00907-158">2</span></span>         | <span data-ttu-id="00907-159">Assinar documento</span><span class="sxs-lookup"><span data-stu-id="00907-159">Sign document</span></span>      | <span data-ttu-id="00907-160">Aplique uma assinatura digital ao arquivo XML.</span><span class="sxs-lookup"><span data-stu-id="00907-160">Apply a digital signature to the XML file.</span></span>             |

4. <span data-ttu-id="00907-161">Selecione a guia **Regras de aplicabilidade** para exibir e manter as regras de aplicabilidade.</span><span class="sxs-lookup"><span data-stu-id="00907-161">Select the **Applicability rules** tab to view and maintain the applicability rules.</span></span> <span data-ttu-id="00907-162">As regras de aplicabilidade definem o contexto em que a ação será executada.</span><span class="sxs-lookup"><span data-stu-id="00907-162">Applicability rules define the context where the action will be run.</span></span>

    ![Guia Regras de aplicabilidade](media/e-Invoicing-services-get-started-ITA-Select-Applicability-rules.png)

5. <span data-ttu-id="00907-164">Selecione a guia **Variáveis** para exibir e manter as variáveis.</span><span class="sxs-lookup"><span data-stu-id="00907-164">Select the **Variables** tab to view and maintain the variables.</span></span>

    ![Guia Variáveis](media/e-Invoicing-services-get-started-ITA-Select-Variables.png)

6. <span data-ttu-id="00907-166">Defina as variáveis públicas necessárias para executar as ações.</span><span class="sxs-lookup"><span data-stu-id="00907-166">Define the public variables that are required to run the actions.</span></span>

### <a name="configure-the-project-invoice-feature-setup"></a><span data-ttu-id="00907-167">Definir a configuração do recurso de fatura do projeto</span><span class="sxs-lookup"><span data-stu-id="00907-167">Configure the Project invoice feature setup</span></span> 

<span data-ttu-id="00907-168">As etapas e as configurações necessárias para definir a configuração do recurso **Fatura do projeto** são semelhantes às etapas e definições de configuração do recurso **Fatura de venda**.</span><span class="sxs-lookup"><span data-stu-id="00907-168">The steps and settings that are required to configure the **Project invoice** feature setup are very similar to the steps and settings for the **Sales invoice** feature setup.</span></span> <span data-ttu-id="00907-169">Ao trabalhar com faturas de projeto, consulte os procedimentos para faturas de vendas.</span><span class="sxs-lookup"><span data-stu-id="00907-169">When you work with project invoices, see the procedures for sales invoices.</span></span>

## <a name="assign-the-e-invoicing-feature-to-the-environment"></a><span data-ttu-id="00907-170">Atribuir o recurso de faturamento eletrônico ao ambiente</span><span class="sxs-lookup"><span data-stu-id="00907-170">Assign the e-Invoicing feature to the environment</span></span>

1. <span data-ttu-id="00907-171">Na página **Recursos de faturamento eletrônico**, na guia **Ambientes**, selecione **Habilitar**.</span><span class="sxs-lookup"><span data-stu-id="00907-171">On the **e-Invoicing Features** page, on the **Environments** tab, select **Enable**.</span></span>
2. <span data-ttu-id="00907-172">No campo **Ambiente**, selecione o ambiente.</span><span class="sxs-lookup"><span data-stu-id="00907-172">In the **Environment** field, select the environment.</span></span>
3. <span data-ttu-id="00907-173">No campo **Efetivo a partir de**, selecione a data em que o ambiente deve entrar em vigor.</span><span class="sxs-lookup"><span data-stu-id="00907-173">In the **Effective from** field, select the date when the environment should become effective.</span></span>
4. <span data-ttu-id="00907-174">Selecione **Habilitar**.</span><span class="sxs-lookup"><span data-stu-id="00907-174">Select **Enable**.</span></span> 

![Habilitar o ambiente de faturamento eletrônico](media/e-Invoicing-services-get-started-ITA-Enable-e-Invoicing-environment.png)

## <a name="publish-the-e-invoicing-feature"></a><span data-ttu-id="00907-176">Publicar o recurso de faturamento eletrônico</span><span class="sxs-lookup"><span data-stu-id="00907-176">Publish the e-invoicing feature</span></span>

<span data-ttu-id="00907-177">Você pode publicar o recurso de faturamento eletrônico alterando o status da versão para **Concluído** ou **Publicado**.</span><span class="sxs-lookup"><span data-stu-id="00907-177">You can publish the e-Invoicing feature by changing the version status to **Completed** or **Published**.</span></span>

### <a name="change-the-version-status-to-completed"></a><span data-ttu-id="00907-178">Alterar o status da versão para Concluído</span><span class="sxs-lookup"><span data-stu-id="00907-178">Change the version status to Completed</span></span>

1. <span data-ttu-id="00907-179">Na página **Recursos de faturamento eletrônico**, na guia **Versões**, selecione a versão do recurso de faturamento eletrônico que tem o status **Rascunho**.</span><span class="sxs-lookup"><span data-stu-id="00907-179">On the **e-Invoicing Features** page, on the **Versions** tab, select the version of the e-Invoicing feature that has a status of **Draft**.</span></span>
2. <span data-ttu-id="00907-180">Selecione **Alterar status \> Concluir**.</span><span class="sxs-lookup"><span data-stu-id="00907-180">Select **Change status \> Complete**.</span></span> 

### <a name="change-the-version-status-to-published"></a><span data-ttu-id="00907-181">Alterar o status da versão para Publicado</span><span class="sxs-lookup"><span data-stu-id="00907-181">Change the version status to Published</span></span> 

1. <span data-ttu-id="00907-182">Na página **Recursos de faturamento eletrônico**, na guia **Versões**, selecione a versão do recurso de faturamento eletrônico que tem o status **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="00907-182">On the **e-Invoicing Features** page, on the **Versions** tab, select the version of the e-Invoicing feature that has a status of **Completed**.</span></span>
2. <span data-ttu-id="00907-183">Selecione **Alterar status \> Publicar**.</span><span class="sxs-lookup"><span data-stu-id="00907-183">Select **Change status \> Publish**.</span></span>

![Alterar o status do recurso de faturamento eletrônico](media/e-Invoicing-services-get-started-ITA-Change-status-of-e-Invoicing-feature.png)

## <a name="set-up-the-electronic-invoicing-add-on-integration-in-finance"></a><span data-ttu-id="00907-185">Configurar a integração do complemento de faturamento eletrônico no Finance</span><span class="sxs-lookup"><span data-stu-id="00907-185">Set up the Electronic invoicing add-on integration in Finance</span></span>

<span data-ttu-id="00907-186">Durante a configuração do Finance, você concluirá estas tarefas:</span><span class="sxs-lookup"><span data-stu-id="00907-186">During the setup of Finance, you will complete these tasks:</span></span>

1. <span data-ttu-id="00907-187">Importe o modelo de dados ER, o mapeamento do modelo de dados ER e as configurações de contexto para faturas eletrônicas FatturaPA.</span><span class="sxs-lookup"><span data-stu-id="00907-187">Import the ER data model, the ER data model mapping, and the context configurations for FatturaPA e-invoices.</span></span>
2. <span data-ttu-id="00907-188">Configure o certificado necessário para assinar digitalmente faturas eletrônicas italianas.</span><span class="sxs-lookup"><span data-stu-id="00907-188">Configure the certificate that is required to digitally sign Italian e-invoices.</span></span>

### <a name="import-the-er-data-model-data-model-mapping-and-formats"></a><span data-ttu-id="00907-189">Importar o modelo de dados ER, mapeamento de modelos de dados e formatos</span><span class="sxs-lookup"><span data-stu-id="00907-189">Import the ER data model, data model mapping, and formats</span></span>

1. <span data-ttu-id="00907-190">No espaço de trabalho **Relatório eletrônico**, verifique se o provedor de configuração do **Serviço de Documento Comercial** está definido como **Ativo**.</span><span class="sxs-lookup"><span data-stu-id="00907-190">In the **Electronic reporting** workspace, verify that the **Business Document Service** configuration provider is set to **Active**.</span></span>
2. <span data-ttu-id="00907-191">Selecione **Repositórios**.</span><span class="sxs-lookup"><span data-stu-id="00907-191">Select **Repositories**.</span></span>
3. <span data-ttu-id="00907-192">Selecione **Recurso global \> Abrir**.</span><span class="sxs-lookup"><span data-stu-id="00907-192">Select **Global resource \> Open**.</span></span>
4. <span data-ttu-id="00907-193">Importar **Modelo de fatura**, **Mapeamento de modelo de fatura** e **Modelo de contexto de fatura de cliente**.</span><span class="sxs-lookup"><span data-stu-id="00907-193">Import **Invoice model**, **Invoice model mapping**, and **Customer invoice context model**.</span></span>

#### <a name="turn-on-the-feature-for-exporting-customer-electronic-invoices-for-italy"></a><span data-ttu-id="00907-194">Ative o recurso para exportar faturas eletrônicas de clientes para a Itália</span><span class="sxs-lookup"><span data-stu-id="00907-194">Turn on the feature for exporting customer electronic invoices for Italy</span></span>

1. <span data-ttu-id="00907-195">Vá para **Administração da organização \> Configuração \> Parâmetros de documentos eletrônicos**.</span><span class="sxs-lookup"><span data-stu-id="00907-195">Go to **Organization administration \> Setup \> Electronic document parameters**.</span></span>
2. <span data-ttu-id="00907-196">Na guia **Recursos**, marque a caixa de seleção **Habilitado** na linha para a referência do recurso **IT00036**.</span><span class="sxs-lookup"><span data-stu-id="00907-196">On the **Features** tab, select the **Enabled** check box in the row for feature reference **IT00036**.</span></span>

![Ativar o recurso FatturaPA](media/e-Invoicing-services-get-started-ITA-Enable-FatturaPA-feature.png)

#### <a name="configure-electronic-documents"></a><span data-ttu-id="00907-198">Configurar documentos eletrônicos</span><span class="sxs-lookup"><span data-stu-id="00907-198">Configure electronic documents</span></span>

1. <span data-ttu-id="00907-199">Vá para **Administração da organização \> Configuração \> Parâmetros de documentos eletrônicos**.</span><span class="sxs-lookup"><span data-stu-id="00907-199">Go to **Organization administration \> Setup \> Electronic document parameters**.</span></span>
2. <span data-ttu-id="00907-200">Na guia **Documento eletrônico**, selecione **Adicionar** e insira as tabelas necessárias para gerar faturas eletrônicas italianas:</span><span class="sxs-lookup"><span data-stu-id="00907-200">On the **Electronic document** tab, select **Add**, and enter the tables that are required to generate Italian e-invoices:</span></span>

    - <span data-ttu-id="00907-201">**Nome da tabela:** diário de fatura do cliente</span><span class="sxs-lookup"><span data-stu-id="00907-201">**Table name:** Customer invoice journal</span></span>
    - <span data-ttu-id="00907-202">**Nome da tabela:** fatura do projeto</span><span class="sxs-lookup"><span data-stu-id="00907-202">**Table name:** Project invoice</span></span>

3. <span data-ttu-id="00907-203">Para cada tabela, defina um contexto de documento relacionado:</span><span class="sxs-lookup"><span data-stu-id="00907-203">For each table, define a related document context:</span></span>

    - <span data-ttu-id="00907-204">Para o **Diário de faturas de clientes**, selecione **Contexto de fatura de cliente**.</span><span class="sxs-lookup"><span data-stu-id="00907-204">For **Customer invoice journal**, select **Customer invoice context**.</span></span>
    - <span data-ttu-id="00907-205">Para **Fatura de projeto**, selecione **Contexto de fatura de projeto**.</span><span class="sxs-lookup"><span data-stu-id="00907-205">For **Project invoice**, select **Project invoice context**.</span></span>

![Configurar tipos de resposta](media/e-Invoicing-services-get-started-ITA-Set-up-response-types.png)

## <a name="electronic-invoice-processing"></a><span data-ttu-id="00907-207">Processamento de fatura eletrônica</span><span class="sxs-lookup"><span data-stu-id="00907-207">Electronic invoice processing</span></span>

<span data-ttu-id="00907-208">Durante o processamento no Finance, você concluirá estas tarefas:</span><span class="sxs-lookup"><span data-stu-id="00907-208">During processing in Finance, you will complete these tasks:</span></span>

1. <span data-ttu-id="00907-209">Gerar faturas eletrônicas italianas por meio do complemento de faturamento eletrônico</span><span class="sxs-lookup"><span data-stu-id="00907-209">Generate Italian e-invoices through the Electronic invoicing add-on</span></span>
2. <span data-ttu-id="00907-210">Exibir os logs de execução e revisar os resultados do processamento</span><span class="sxs-lookup"><span data-stu-id="00907-210">View the execution logs and review the results of processing</span></span>

### <a name="generate-electronic-invoices"></a><span data-ttu-id="00907-211">Gerar faturas eletrônicas</span><span class="sxs-lookup"><span data-stu-id="00907-211">Generate electronic invoices</span></span>

<span data-ttu-id="00907-212">Depois que você ativar os recursos **Integração do complemento de faturamento eletrônico configurável** e **IT00036**, o processo antigo do Finance para gerar faturas eletrônicas italianas não poderá mais ser usado.</span><span class="sxs-lookup"><span data-stu-id="00907-212">After you turn on the **Configurable Electronic invoicing add-on integration** feature and activate the **IT00036** feature, the old Finance process for generating Italian e-invoices can no longer be used.</span></span> <span data-ttu-id="00907-213">Ele é substituído por um novo processo chamado **Enviar documentos eletrônicos**.</span><span class="sxs-lookup"><span data-stu-id="00907-213">It's replaced by a new process that is named **Submit electronic documents**.</span></span>

<span data-ttu-id="00907-214">Você pode enviar os documentos manualmente, com base na demanda de documentos de fatura eletrônica.</span><span class="sxs-lookup"><span data-stu-id="00907-214">You can submit the documents manually, based on your demand for e-invoice documents.</span></span>

> [!NOTE]
> <span data-ttu-id="00907-215">Antes de continuar, verifique se a configuração necessária para as faturas eletrônicas italianas foi concluída.</span><span class="sxs-lookup"><span data-stu-id="00907-215">Before you continue, verify that the setup that is required for Italian e-invoices was completed.</span></span> <span data-ttu-id="00907-216">Para obter mais informações, consulte [Faturas eletrônicas do cliente](https://docs.microsoft.com/dynamics365/finance/localizations/emea-ita-e-invoices).</span><span class="sxs-lookup"><span data-stu-id="00907-216">For more information, see [Customer electronic invoices](https://docs.microsoft.com/dynamics365/finance/localizations/emea-ita-e-invoices).</span></span> <span data-ttu-id="00907-217">Lembre-se de que algumas das etapas de configuração descritas nesse tópico podem não estar disponíveis devido à ativação do complemento de faturamento eletrônico.</span><span class="sxs-lookup"><span data-stu-id="00907-217">Be aware that some of the setup steps that are described in that topic might be unavailable because of Electronic invoicing add-on activation.</span></span>

1. <span data-ttu-id="00907-218">Vá para **Administração da organização \> Periódico \> Documentos eletrônicos \> Enviar documentos eletrônicos**.</span><span class="sxs-lookup"><span data-stu-id="00907-218">Go to **Organization administration \> Periodic \> Electronic documents \> Submit electronic documents**.</span></span>
2. <span data-ttu-id="00907-219">Para o primeiro envio de qualquer documento, defina a opção **Reenviar documentos** como **Não**.</span><span class="sxs-lookup"><span data-stu-id="00907-219">For the first submission of any document, set the **Resubmit documents** option to **No**.</span></span> <span data-ttu-id="00907-220">Se você precisar reenviar um documento pelo serviço, defina esta opção como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="00907-220">If you must resubmit a document through the service, set this option to **Yes**.</span></span>
3. <span data-ttu-id="00907-221">Na Guia Rápida **Registros a serem incluídos**, selecione **Filtrar** para abrir a caixa de diálogo **Consulta**, na qual você pode criar uma consulta para selecionar documentos para envio.</span><span class="sxs-lookup"><span data-stu-id="00907-221">On the **Records to include** FastTab, select **Filter** to open the **Inquiry** dialog box, where you can build a query to select documents for submission.</span></span>

![Caixa de diálogo Enviar documentos eletrônicos](media/e-Invoicing-services-get-started-ITA-Submission-form.png)

#### <a name="filter-query"></a><span data-ttu-id="00907-223">Consulta de filtro</span><span class="sxs-lookup"><span data-stu-id="00907-223">Filter query</span></span>

1. <span data-ttu-id="00907-224">Na caixa de diálogo **Consulta**, configure as condições de filtragem para as faturas de venda e de projeto, ou deixe as condições em branco para incluir todas as faturas não enviadas.</span><span class="sxs-lookup"><span data-stu-id="00907-224">In the **Inquiry** dialog box, configure the filtering conditions for both sales invoices and project invoices, or leave the conditions blank to include all unsubmitted invoices.</span></span>

    ![Configurar critérios de filtro de envio](media/e-Invoicing-services-get-started-ITA-Set-up-Submission-filter-criteria.png)

2. <span data-ttu-id="00907-226">Selecione **OK** para fechar a caixa de diálogo **Consulta**.</span><span class="sxs-lookup"><span data-stu-id="00907-226">Select **OK** to close the **Inquiry** dialog box.</span></span>
3. <span data-ttu-id="00907-227">Selecione **OK** para enviar os documentos selecionados.</span><span class="sxs-lookup"><span data-stu-id="00907-227">Select **OK** submit the selected documents.</span></span>

> <span data-ttu-id="00907-228">![OBSERVAÇÃO] Na primeira tentativa de enviar um documento pelo serviço, você será solicitado a confirmar a conexão com o complemento do faturamento eletrônico.</span><span class="sxs-lookup"><span data-stu-id="00907-228">![NOTE] During your first attempt to submit a document through the service, you will be prompted to confirm the connection with the Electronic invoicing add-on.</span></span> <span data-ttu-id="00907-229">Selecione **Clique aqui para se conectar ao serviço de envio de documentos eletrônicos**.</span><span class="sxs-lookup"><span data-stu-id="00907-229">Select **Click here to connect to Electronic Document Submission Service**.</span></span>

#### <a name="view-submission-logs"></a><span data-ttu-id="00907-230">Exibir logs de envio</span><span class="sxs-lookup"><span data-stu-id="00907-230">View submission logs</span></span>

<span data-ttu-id="00907-231">Você pode exibir os logs de envio para todos os documentos enviados.</span><span class="sxs-lookup"><span data-stu-id="00907-231">You can view the submission logs for all submitted documents.</span></span>

1. <span data-ttu-id="00907-232">Vá para **Administração da organização \> Periódico \> Documentos eletrônicos \> Log de envio de documentos eletrônicos**.</span><span class="sxs-lookup"><span data-stu-id="00907-232">Go to **Organization administration \> Periodic \> Electronic documents \> Electronic document submission log**.</span></span>
2. <span data-ttu-id="00907-233">No campo **Tipo de documento**, selecione **Diário de faturas de clientes** ou **Fatura de projeto** para filtrar os documentos eletrônicos necessários.</span><span class="sxs-lookup"><span data-stu-id="00907-233">In the **Document type** field, select **Customer invoice journal** or **Project invoice** to filter for the required electronic documents.</span></span>

    ![Selecionar um tipo de documento para exibir os logs de envio](media/e-Invoicing-services-get-started-ITA-Select-Document-type-for-viewing-submission-log.png)

    <span data-ttu-id="00907-235">O valor mostrado na coluna **Status do envio** representa o status do processo de envio.</span><span class="sxs-lookup"><span data-stu-id="00907-235">The value that is shown in the **Submission status** column represents the status of the submission process.</span></span> <span data-ttu-id="00907-236">Ele indica se o processo foi executado como configurado e se uma ação adicional é necessária.</span><span class="sxs-lookup"><span data-stu-id="00907-236">It indicates whether the process ran as configured and whether additional action is required.</span></span>

3. <span data-ttu-id="00907-237">No Painel de Ações, selecione **Consultas \> Detalhes de envio** para exibir os detalhes dos logs de execução de envio.</span><span class="sxs-lookup"><span data-stu-id="00907-237">On the Action Pane, select **Inquiries \> Submission details** to view the details of the submission execution logs.</span></span>

    ![Exibir os detalhes do log de envio](media/e-Invoicing-services-get-started-ITA-View-Submission-log-details.png)

4. <span data-ttu-id="00907-239">Na Guia Rápida **Ações de processamento**, você pode exibir o log de execução para as ações configuradas na versão do recurso que foi configurada no RCS.</span><span class="sxs-lookup"><span data-stu-id="00907-239">On the **Processing actions** FastTab, you can view the execution log for the actions that are configured in the feature version that was set up in RCS.</span></span> <span data-ttu-id="00907-240">A coluna **Status** mostra se a ação foi executada com êxito.</span><span class="sxs-lookup"><span data-stu-id="00907-240">The **Status** column shows whether the action was successfully run.</span></span>
5. <span data-ttu-id="00907-241">Na Guia Rápida **Arquivos de ação**, você pode exibir os arquivos intermediários que foram gerados durante a execução das ações.</span><span class="sxs-lookup"><span data-stu-id="00907-241">On the **Action files** FastTab, you can view the intermediate files that were generated during execution of the actions.</span></span> <span data-ttu-id="00907-242">Você pode selecionar **Exibir** para baixar o arquivo XML de saída no formato **FatturaPA** e exibir o conteúdo.</span><span class="sxs-lookup"><span data-stu-id="00907-242">You can select **View** to download the output XML file in **FatturaPA** format and view its content.</span></span>

## <a name="related-topics"></a><span data-ttu-id="00907-243">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="00907-243">Related topics</span></span>

- [<span data-ttu-id="00907-244">Visão geral do complemento de faturamento eletrônico</span><span class="sxs-lookup"><span data-stu-id="00907-244">Electronic invoicing add-on overview</span></span>](e-invoicing-service-overview.md)
- [<span data-ttu-id="00907-245">Introdução ao complemento de faturamento eletrônico</span><span class="sxs-lookup"><span data-stu-id="00907-245">Get started with the Electronic invoicing add-on</span></span>](e-invoicing-get-started.md)
- [<span data-ttu-id="00907-246">Configurar o complemento de faturamento eletrônico</span><span class="sxs-lookup"><span data-stu-id="00907-246">Set up the Electronic invoicing add-on</span></span>](e-invoicing-setup.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]