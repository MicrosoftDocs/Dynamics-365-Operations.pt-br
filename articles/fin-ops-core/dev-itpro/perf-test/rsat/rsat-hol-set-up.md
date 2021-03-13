---
title: Tutorial Configurar e instalar a Regression Suite Automation Tool
description: Este tópico é um tutorial que mostra como configurar e instalar a Regression Suite Automation Tool (RSAT).
author: robinarh
manager: AnnBe
ms.date: 09/20/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ROBOTS: NOINDEX, NOFOLLOW
audience: Application User, Developer, IT Pro
ms.reviewer: rhaertle
ms.custom: 21761, NotInToc
ms.search.region: Global
ms.author: rhaertle
ms.search.validFrom: 2019-05-30
ms.dyn365.ops.version: AX 7.0.0, Operations
ms.openlocfilehash: 46115dc4a46be951517265197f76637ad3e63b78
ms.sourcegitcommit: b337b647a1be4908fc361fb6d962e96a69f301a9
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/21/2021
ms.locfileid: "5036696"
---
# <a name="set-up-and-install-regression-suite-automation-tool-tutorial"></a><span data-ttu-id="b31f1-103">Tutorial Configurar e instalar a Regression Suite Automation Tool</span><span class="sxs-lookup"><span data-stu-id="b31f1-103">Set up and install Regression suite automation tool tutorial</span></span>

<span data-ttu-id="b31f1-104">Este tópico é um tutorial que o ajuda a configurar e iniciar a RSAT e as ferramentas associadas usando a RSAT.</span><span class="sxs-lookup"><span data-stu-id="b31f1-104">This topic is a tutorial that helps you get setup and get started with RSAT and the tools associated with using RSAT.</span></span>

[!include [banner](../../includes/banner.md)]

> [!NOTE]
> <span data-ttu-id="b31f1-105">Use as ferramentas do navegador da internet para fazer download e salvar esta página no formato PDF.</span><span class="sxs-lookup"><span data-stu-id="b31f1-105">Use your internet browser tools to download and save this page in PDF format.</span></span>

## <a name="key-concepts"></a><span data-ttu-id="b31f1-106">Conceitos principais</span><span class="sxs-lookup"><span data-stu-id="b31f1-106">Key concepts</span></span>

- <span data-ttu-id="b31f1-107">Compreender a instalação e configuração de pré-requisitos necessárias para várias solicitações de emprego que suportam a Regression Suite Automation Tool (RSAT).</span><span class="sxs-lookup"><span data-stu-id="b31f1-107">Understand the installation and prerequisite setup that are required for the various applications that support Regression suite automation tool (RSAT).</span></span>
- <span data-ttu-id="b31f1-108">Entender como o recurso Gravador de tarefas, junto com o Lifecycle Services (LCS) do Microsoft Dynamics e o Microsoft Azure DevOps, permite que você crie, configure, execute, investigue e relate casos de teste.</span><span class="sxs-lookup"><span data-stu-id="b31f1-108">Understand how the Task recorder feature, together with Microsoft Dynamics Lifecycle Services (LCS) and Microsoft Azure DevOps, let you create, configure, run, investigate, and report on test cases.</span></span>
- <span data-ttu-id="b31f1-109">Capacitar usuários funcionais para registrar tarefas comerciais usando o Gravador de tarefas e, em seguida, converter as gravações de tarefas em um conjunto de testes automatizados, sem ter que gravar o código-fonte.</span><span class="sxs-lookup"><span data-stu-id="b31f1-109">Empower functional users to record business tasks by using Task recorder, and then convert the task recordings into a suite of automated tests, without having to write source code.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="b31f1-110">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="b31f1-110">Before you begin</span></span>

### <a name="prerequisites"></a><span data-ttu-id="b31f1-111">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="b31f1-111">Prerequisites</span></span>

- <span data-ttu-id="b31f1-112">Um ambiente que execute a versão 10.0 (abril de 2019) ou posterior do Microsoft Dynamics 365 for Finance and Operations é necessário para este tutorial.</span><span class="sxs-lookup"><span data-stu-id="b31f1-112">An environment that runs Microsoft Dynamics 365 for Finance and Operations version 10.0 (April 2019) or later is required for this tutorial.</span></span> <span data-ttu-id="b31f1-113">Para os clientes que usam o Microsoft Dynamics 365 for Finance and Operations, Enterprise edition 7.3, a atualização da plataforma (PU20) ou posterior também é suportada.</span><span class="sxs-lookup"><span data-stu-id="b31f1-113">For customers who are using Microsoft Dynamics 365 for Finance and Operations, Enterprise edition 7.3, Platform update 20 (PU20) or later is also supported.</span></span>
- <span data-ttu-id="b31f1-114">O usuário deve ter direitos de administrador no ambiente.</span><span class="sxs-lookup"><span data-stu-id="b31f1-114">The user must have admin rights to the environment.</span></span>
- <span data-ttu-id="b31f1-115">Você deve ter acesso ao LCS e ao Azure DevOps (anteriormente chamado de Microsoft Visual Studio Team Services \[VSTS\]) do locatário do cliente.</span><span class="sxs-lookup"><span data-stu-id="b31f1-115">You must have access to the customer tenant LCS and Azure DevOps (previously known as Microsoft Visual Studio Team Services \[VSTS\]).</span></span>
- <span data-ttu-id="b31f1-116">O usuário que está criando e gerenciando conjuntos de testes deve ter uma licença dos Planos de Teste ou do Gerenciador de Testes do Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="b31f1-116">The user that is creating and managing tests suites must have an Azure DevOps Test Plans or Test Manager license.</span></span> <span data-ttu-id="b31f1-117">As seguintes licenças também fornecerão acesso aos Planos de Teste:</span><span class="sxs-lookup"><span data-stu-id="b31f1-117">The following licenses will also give you access to Test Plans:</span></span>
    - <span data-ttu-id="b31f1-118">Licença do Visual Studio Enterprise</span><span class="sxs-lookup"><span data-stu-id="b31f1-118">Visual Studio Enterprise license</span></span>
    - <span data-ttu-id="b31f1-119">Licença do Visual Studio Test Professional</span><span class="sxs-lookup"><span data-stu-id="b31f1-119">Visual Studio Test Professional license</span></span>
    - <span data-ttu-id="b31f1-120">Licença de assinante das Plataformas MSDN</span><span class="sxs-lookup"><span data-stu-id="b31f1-120">MSDN Platforms subscriber license</span></span>
- <span data-ttu-id="b31f1-121">O RSAT deve ter acesso ao ambiente de teste através de um navegador da Web.</span><span class="sxs-lookup"><span data-stu-id="b31f1-121">RSAT must have access to the test environment via a web browser.</span></span>
- <span data-ttu-id="b31f1-122">Para gerar e editar os parâmetros de teste, você deve ter o Microsoft Excel instalado.</span><span class="sxs-lookup"><span data-stu-id="b31f1-122">To generate and edit test parameters, you must have Microsoft Excel installed.</span></span>

## <a name="configure-azure-devops"></a><span data-ttu-id="b31f1-123">Configurar o Azure DevOps</span><span class="sxs-lookup"><span data-stu-id="b31f1-123">Configure Azure DevOps</span></span>

### <a name="user-eligibility"></a><span data-ttu-id="b31f1-124">Qualificação do usuário</span><span class="sxs-lookup"><span data-stu-id="b31f1-124">User eligibility</span></span>

<span data-ttu-id="b31f1-125">Certifique-se de que o usuário foi criado no Azure DevOps e tem um nível de assinatura que fornecerá acesso aos Planos de Teste do Azure.</span><span class="sxs-lookup"><span data-stu-id="b31f1-125">Make sure that the user is created in Azure DevOps and has a subscription level that provides access to Azure Test Plans.</span></span> <span data-ttu-id="b31f1-126">Uma licença dos Planos de Teste do Azure DevOps é obrigatória somente se o usuário criar e gerenciar casos de teste (isto é, nem todos os usuários de RSAT precisam dessa licença).</span><span class="sxs-lookup"><span data-stu-id="b31f1-126">An Azure DevOps Test Plans license is required only if the user will create and manage test cases (that is, not all RSAT users require this license).</span></span> <span data-ttu-id="b31f1-127">Para obter informações sobre os requisitos de licença, consulte [Requisitos de licença](https://docs.microsoft.com/azure/devops/test/manual-test-permissions#license-requirements).</span><span class="sxs-lookup"><span data-stu-id="b31f1-127">For information about the license requirements, see [License requirements](https://docs.microsoft.com/azure/devops/test/manual-test-permissions#license-requirements).</span></span>

### <a name="create-a-new-azure-devops-project"></a><span data-ttu-id="b31f1-128">Criar um novo projeto do Azure DevOps</span><span class="sxs-lookup"><span data-stu-id="b31f1-128">Create a new Azure DevOps project</span></span>

<span data-ttu-id="b31f1-129">O RSAT usa o Azure Devops para gerenciamento de conjunto de teste e de caso de teste, geração de relatórios e investigação de resultados da execução do teste.</span><span class="sxs-lookup"><span data-stu-id="b31f1-129">RSAT uses Azure Devops for test case and test suite management, reporting, and investigating test run results.</span></span>

> [!NOTE]
> <span data-ttu-id="b31f1-130">Você pode usar um projeto existente do Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="b31f1-130">You can use an existing Azure DevOps project.</span></span> <span data-ttu-id="b31f1-131">Porém, se seu projeto do Azure DevOps existente for configurado de forma que tenha um modelo personalizado, você receberá um erro "Falha de Sincronização de VSTS" quando você sincronizar os casos de teste do Modelador de processo de negócios (BPM) para o Azure DevOps (consulte a seção [Testar a sincronização do BPM para Azure DevOps](#test-the-synchronization-from-bpm-to-azure-devops)).</span><span class="sxs-lookup"><span data-stu-id="b31f1-131">However, if your existing Azure DevOps project is set up so that it has a custom template, you will receive a "VSTS Sync Failure" error when you sync test cases from Business process modeler (BPM) to Azure DevOps (see the [Test the synchronization from BPM to Azure DevOps](#test-the-synchronization-from-bpm-to-azure-devops) section).</span></span> <span data-ttu-id="b31f1-132">Se as práticas recomendadas a seguir forem seguidas para o modelo personalizado, você poderá sincronizar os casos de teste para o Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="b31f1-132">If the following best practices have been followed for the custom template, you will be able to sync the test cases to Azure DevOps.</span></span> <span data-ttu-id="b31f1-133">(Essas práticas recomendadas são listadas na mensagem de erro).</span><span class="sxs-lookup"><span data-stu-id="b31f1-133">(These best practices are listed in the error message.)</span></span>

- <span data-ttu-id="b31f1-134">Não excluir nenhum tipo de item de trabalho ou campos integrados.</span><span class="sxs-lookup"><span data-stu-id="b31f1-134">Do not delete any work item types or out-of-the-box fields.</span></span>
- <span data-ttu-id="b31f1-135">Não excluir nenhum estado de um tipo de item de trabalho.</span><span class="sxs-lookup"><span data-stu-id="b31f1-135">Do not delete any state of a work item type.</span></span>
- <span data-ttu-id="b31f1-136">Não adicionar nenhum campo necessário a um tipo de item de trabalho.</span><span class="sxs-lookup"><span data-stu-id="b31f1-136">Do not add any required fields to a work item type.</span></span>

![Mensagem de erro com uma lista de práticas recomendadas](./media/setup_rsa_tool_02.png)

<span data-ttu-id="b31f1-138">Caso contrário, para este tutorial, recomendamos que você crie um novo projeto do Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="b31f1-138">Otherwise, for this tutorial, we recommend that you create a new Azure DevOps project.</span></span> <span data-ttu-id="b31f1-139">Para obter mais informações, consulte [Problemas ao sincronizar BPM usando um modelo do processo do Azure DevOps (VSTS) personalizado](https://blogs.msdn.microsoft.com/lcs/2018/11/28/issues-when-syncing-to-bpm-using-a-custom-azure-devops-vsts-process-template/).</span><span class="sxs-lookup"><span data-stu-id="b31f1-139">For more information, see [Issues when syncing to BPM using a custom Azure DevOps (VSTS) process template](https://blogs.msdn.microsoft.com/lcs/2018/11/28/issues-when-syncing-to-bpm-using-a-custom-azure-devops-vsts-process-template/).</span></span>

1. <span data-ttu-id="b31f1-140">Abra a URL do Azure DevOps (`https://dev.azure.com/<Azure DevOps Name>`).</span><span class="sxs-lookup"><span data-stu-id="b31f1-140">Open the Azure DevOps URL (`https://dev.azure.com/<Azure DevOps Name>`).</span></span>
2. <span data-ttu-id="b31f1-141">Selecione **Criar projeto** no canto superior direito da página Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="b31f1-141">Select **Create project** in the upper-right corner of the Azure DevOps page.</span></span>

    ![Botão Criar projeto](./media/setup_rsa_tool_03.png)

3. <span data-ttu-id="b31f1-143">Preencha os seguintes campos e, em seguida, selecione **Criar**:</span><span class="sxs-lookup"><span data-stu-id="b31f1-143">Fill in the following fields, and then select **Create**:</span></span>

    - <span data-ttu-id="b31f1-144">**Nome do Projeto**</span><span class="sxs-lookup"><span data-stu-id="b31f1-144">**Project name**</span></span>
    - <span data-ttu-id="b31f1-145">**Controle de versão** – Selecione **Controle de Versão do Team Foundation**.</span><span class="sxs-lookup"><span data-stu-id="b31f1-145">**Version control** – Select **Team Foundation Version Control**.</span></span> <span data-ttu-id="b31f1-146">Observe que a opção padrão, **Git**, não é suportada.</span><span class="sxs-lookup"><span data-stu-id="b31f1-146">Note that the default option, **Git**, isn't supported.</span></span>
    - <span data-ttu-id="b31f1-147">**Processo do item de trabalho**</span><span class="sxs-lookup"><span data-stu-id="b31f1-147">**Work item process**</span></span>

    ![Caixa de diálogo Criar novo projeto](./media/setup_rsa_tool_04.png)

### <a name="create-a-personal-access-token"></a><span data-ttu-id="b31f1-149">Criar um token de acesso pessoal</span><span class="sxs-lookup"><span data-stu-id="b31f1-149">Create a personal access token</span></span>

<span data-ttu-id="b31f1-150">Neste tutorial você usará o Modelador de Processo de Negócios (BPM) do LCS para criar uma biblioteca de casos de teste e sincronizar seus casos de teste com o Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="b31f1-150">In this tutorial, you will use the LCS Business Process Modeler (BPM) to create a test case library and synchronize your test cases with Azure DevOps.</span></span> <span data-ttu-id="b31f1-151">Você precisará de um token de acesso pessoal para sincronizar o BPM com o Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="b31f1-151">You will need a personal access token to sync BPM with Azure DevOps.</span></span>

1. <span data-ttu-id="b31f1-152">Selecione o ícone de perfil no canto superior direito da página de seu projeto do Azure DevOps e, seguida, selecione **Segurança**.</span><span class="sxs-lookup"><span data-stu-id="b31f1-152">Select the profile icon in the upper-right corner of the page for your Azure DevOps project, and then select **Security**.</span></span>

    ![Comando de segurança](./media/setup_rsa_tool_05.png)

2. <span data-ttu-id="b31f1-154">No painel esquerdo, em **Segurança**, selecione **Tokens de acesso pessoal**.</span><span class="sxs-lookup"><span data-stu-id="b31f1-154">In the left pane, under **Security**, select **Personal access tokens**.</span></span> <span data-ttu-id="b31f1-155">Em seguida, selecione **Novo Token**.</span><span class="sxs-lookup"><span data-stu-id="b31f1-155">Then select **New Token**.</span></span>

    ![O botão Novo Token na guia Tokens de acesso pessoal nas Configurações de usuário](./media/setup_rsa_tool_06.png)

3. <span data-ttu-id="b31f1-157">Preencha os seguintes campos e, em seguida, selecione **Criar**:</span><span class="sxs-lookup"><span data-stu-id="b31f1-157">Fill in the following fields, and then select **Create**:</span></span>

    - <span data-ttu-id="b31f1-158">**Nome**</span><span class="sxs-lookup"><span data-stu-id="b31f1-158">**Name**</span></span>
    - <span data-ttu-id="b31f1-159">**Vencimento (UTC)** – Selecione **Definição personalizada**, e depois use o seletor de data para selecionar a última data disponível.</span><span class="sxs-lookup"><span data-stu-id="b31f1-159">**Expiration (UTC)** – Select **Custom defined**, and then use the date picker to select the last available date.</span></span>
    - <span data-ttu-id="b31f1-160">**Escopos** – Selecione a opção **Acesso total**.</span><span class="sxs-lookup"><span data-stu-id="b31f1-160">**Scopes** – Select the **Full access** option.</span></span>

    ![Caixa de diálogo Criar um novo token de acesso pessoal](./media/setup_rsa_tool_07.png)

    > [!NOTE]
    > <span data-ttu-id="b31f1-162">Faça uma anotação do token de acesso pessoal que foi criado.</span><span class="sxs-lookup"><span data-stu-id="b31f1-162">Make a note of the personal access token that is created.</span></span> <span data-ttu-id="b31f1-163">Você precisará mais tarde quando configurar a configuração do RSAT.</span><span class="sxs-lookup"><span data-stu-id="b31f1-163">You will need it later when you set up the RSAT configuration.</span></span>

    ![Token de acesso pessoal](./media/setup_rsa_tool_08.png)

## <a name="configure-the-lcs-project"></a><span data-ttu-id="b31f1-165">Configurar o projeto LCS</span><span class="sxs-lookup"><span data-stu-id="b31f1-165">Configure the LCS project</span></span>

<span data-ttu-id="b31f1-166">É necessário um projeto do Lifecycle Services (LCS) para sua biblioteca de teste mestre.</span><span class="sxs-lookup"><span data-stu-id="b31f1-166">You need a Lifecycle Services (LCS) project for your master test library.</span></span> <span data-ttu-id="b31f1-167">O Modelador de processo de negócios (BPM) de LCS é usado como a biblioteca mestre para seus casos de teste.</span><span class="sxs-lookup"><span data-stu-id="b31f1-167">The LCS Business Process Modeler (BPM) is used as the master library for your test cases.</span></span> <span data-ttu-id="b31f1-168">O BPM é usado para gerenciar e distribuir bibliotecas de teste em projetos de LCS.</span><span class="sxs-lookup"><span data-stu-id="b31f1-168">BPM is used to manage and distribute test libraries across LCS projects.</span></span> <span data-ttu-id="b31f1-169">Por exemplo, um parceiro Microsoft ou fornecedor de software independente (ISV) que cria bibliotecas de testes irá liberar casos de testes na forma de bibliotecas BPM.</span><span class="sxs-lookup"><span data-stu-id="b31f1-169">For example, a Microsoft partner or independent software vendor (ISV) building test libraries will release test cases in the form of BPM libraries.</span></span> <span data-ttu-id="b31f1-170">No BPM, os casos de teste são organizados por processo comercial.</span><span class="sxs-lookup"><span data-stu-id="b31f1-170">In BPM, test cases are organized by business process.</span></span> <span data-ttu-id="b31f1-171">O BPM não define a ordem de execução ou frequência de aprovação de seu teste.</span><span class="sxs-lookup"><span data-stu-id="b31f1-171">BPM doesn't define the execution order or frequency of your test pass.</span></span> <span data-ttu-id="b31f1-172">Esses detalhes são gerenciados no Azure DevOps, conforme descrito posteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="b31f1-172">These details are managed in Azure DevOps, as described later in this topic.</span></span>  

<span data-ttu-id="b31f1-173">Para o projeto de LCS, você pode usar uma implementação do cliente existente ou um projeto do parceiro.</span><span class="sxs-lookup"><span data-stu-id="b31f1-173">For your LCS project, you can use an existing customer implementation or partner project.</span></span>

### <a name="update-the-lcs-language"></a><span data-ttu-id="b31f1-174">Atualizar o idioma LCS</span><span class="sxs-lookup"><span data-stu-id="b31f1-174">Update the LCS language</span></span>

> [!NOTE]
> <span data-ttu-id="b31f1-175">Para a interface do usuário (IU) mostrar corretamente os processos empresariais, o idioma preferido de LCS deve ser definido como **Inglês (Estados Unidos)**.</span><span class="sxs-lookup"><span data-stu-id="b31f1-175">For the user interface (UI) to correctly show business processes, the LCS preferred language must be set to **English (United States)**.</span></span>

1. <span data-ttu-id="b31f1-176">Vá para o projeto de implementação de LCS.</span><span class="sxs-lookup"><span data-stu-id="b31f1-176">Go to the LCS implementation project.</span></span>
2. <span data-ttu-id="b31f1-177">Selecione o botão **Configurações** (o símbolo de engrenagem) no canto superior direito e depois **Preferência de idioma**.</span><span class="sxs-lookup"><span data-stu-id="b31f1-177">Select the **Settings** button (the gear symbol) in the upper-right corner, and then select **Language preference**.</span></span>

    ![Atualizar preferência de idioma](./media/setup_rsa_tool_09.png)

3. <span data-ttu-id="b31f1-179">No campo **Idioma preferido** , selecione **Inglês (Estados Unidos)** e **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="b31f1-179">In the **Preferred language** field, select **English (United States)**, and then select **Save**.</span></span>

    ![Guia Preferência de idioma nas Configurações do usuário](./media/setup_rsa_tool_10.png)

### <a name="configure-lcs-to-connect-to-the-azure-devops-project"></a><span data-ttu-id="b31f1-181">Configurar o LCS para conectar-se ao projeto Azure DevOps</span><span class="sxs-lookup"><span data-stu-id="b31f1-181">Configure LCS to connect to the Azure DevOps project</span></span>

<span data-ttu-id="b31f1-182">Se você criou um novo projeto Azure DevOps anteriormente, configure o projeto LCS para conectar-se a ele.</span><span class="sxs-lookup"><span data-stu-id="b31f1-182">If you created a new Azure DevOps project earlier, configure the LCS project to connect to it.</span></span> <span data-ttu-id="b31f1-183">Caso contrário, se seu projeto LCS já estiver conectado ao seu projeto Azure DevOps, você pode continuar na próxima seção.</span><span class="sxs-lookup"><span data-stu-id="b31f1-183">Otherwise, if your LCS project is already connected to your Azure DevOps project, you can continue to the next section.</span></span>

1. <span data-ttu-id="b31f1-184">Vá para o projeto de implementação de LCS.</span><span class="sxs-lookup"><span data-stu-id="b31f1-184">Go to the LCS implementation project.</span></span>
2. <span data-ttu-id="b31f1-185">Selecione o botão **Menu** e, em seguida, **Configurações do projeto**.</span><span class="sxs-lookup"><span data-stu-id="b31f1-185">Select the **Menu** button, and then select **Project settings**.</span></span>

    ![Comando das configurações do projeto](./media/setup_rsa_tool_11.png)

3. <span data-ttu-id="b31f1-187">No painel esquerdo, selecione **Visual Studio Team Services** e **Instalar o Visual Studio Team Services**.</span><span class="sxs-lookup"><span data-stu-id="b31f1-187">In the left pane, select **Visual Studio Team Services**, and then select **Setup Visual Studio Team Services**.</span></span>

    ![Guia Visual Studio Team Services nas Configurações do projeto](./media/setup_rsa_tool_12.png)

4. <span data-ttu-id="b31f1-189">No campo **URL do site do Azure DevOps**, informe a URL do site do Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="b31f1-189">In the **Azure DevOps site URL** field, enter the URL of the Azure DevOps site.</span></span> <span data-ttu-id="b31f1-190">No campo **Token de acesso pessoal** , insira o token de acesso pessoal que foi criado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="b31f1-190">In the **Personal access token** field, enter the personal access token that was created earlier.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b31f1-191">Apesar de o VSTS agora ser conhecido como Azure DevOps, para conectar o LCS ao seu projeto Azure DevOps, use a URL antiga.</span><span class="sxs-lookup"><span data-stu-id="b31f1-191">Although VSTS is now known as Azure DevOps, to connect LCS to your Azure DevOps project, use the old URL.</span></span> <span data-ttu-id="b31f1-192">Por exemplo, a URL do Azure DevOps usada neste tutorial é `https://dev.azure.com/D365FOFastTrack/`.</span><span class="sxs-lookup"><span data-stu-id="b31f1-192">For example, the Azure DevOps URL that is used in this tutorial is `https://dev.azure.com/D365FOFastTrack/`.</span></span> <span data-ttu-id="b31f1-193">Porém, na ilustração a seguir, é inserida como `https://D365FOFastTrack.visualstudio.com/`.</span><span class="sxs-lookup"><span data-stu-id="b31f1-193">However, in the following illustration, it's entered as `https://D365FOFastTrack.visualstudio.com/`.</span></span>

    ![Etapa 1 na Instalação do Visual Studio Team Services](./media/setup_rsa_tool_13.png)

5. <span data-ttu-id="b31f1-195">Selecione **Continuar**.</span><span class="sxs-lookup"><span data-stu-id="b31f1-195">Select **Continue**.</span></span>
6. <span data-ttu-id="b31f1-196">No campo **Projeto do Visual Studio Team Services**, selecione o projeto do VSTS no site selecionado para vincular-se ao projeto do LCS.</span><span class="sxs-lookup"><span data-stu-id="b31f1-196">In the **Visual Studio Team Services project** field, select the VSTS project on the selected site to link with the LCS project.</span></span> <span data-ttu-id="b31f1-197">O campo **Modelo do processo** é definido como **Agile**, por padrão.</span><span class="sxs-lookup"><span data-stu-id="b31f1-197">The **Process template** field is set to **Agile** by default.</span></span> <span data-ttu-id="b31f1-198">Para obter um modelo personalizado, revise a orientação de prática recomendada na seção [Criar um novo projeto do Azure DevOps](#create-a-new-azure-devops-project).</span><span class="sxs-lookup"><span data-stu-id="b31f1-198">For a custom template, review the best practice guidance in the [Create a new Azure DevOps project](#create-a-new-azure-devops-project) section.</span></span> <span data-ttu-id="b31f1-199">Em seguida, selecione **Continuar**.</span><span class="sxs-lookup"><span data-stu-id="b31f1-199">Then select **Continue**.</span></span>

    ![Etapa 2 na Instalação do Visual Studio Team Services](./media/setup_rsa_tool_14.png)

7. <span data-ttu-id="b31f1-201">Revise suas configurações e selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="b31f1-201">Review your settings, and then select **Save**.</span></span>

    ![Etapa 3 na Instalação do Visual Studio Team Services](./media/setup_rsa_tool_15.png)

8. <span data-ttu-id="b31f1-203">Selecione **Autorizar** para autorizar o LCS a acessar o site do Azure DevOps configurado em seu nome e ativar os recursos que integram-se ao VSTS.</span><span class="sxs-lookup"><span data-stu-id="b31f1-203">Select **Authorize** to authorize LCS to access the configured Azure DevOps site on your behalf and to turn on features that integrate with VSTS.</span></span>

    ![Botão Autorizar](./media/setup_rsa_tool_16.png)

9. <span data-ttu-id="b31f1-205">Uma caixa de mensagem é exibida que informa: "Você está prestes a ser redirecionado para um site externo para autorizar o LCS a se conectar ao Visual Studio Team Services em seu nome.</span><span class="sxs-lookup"><span data-stu-id="b31f1-205">A message box appears that states, "You are about to be redirected to an eternal site to authorize LCS to connect to Visual Studio Team Services on your behalf.</span></span> <span data-ttu-id="b31f1-206">Deseja continuar?"</span><span class="sxs-lookup"><span data-stu-id="b31f1-206">Proceed?"</span></span> <span data-ttu-id="b31f1-207">Selecione **Sim**.</span><span class="sxs-lookup"><span data-stu-id="b31f1-207">Select **Yes**.</span></span>

    ![Caixa de mensagem](./media/setup_rsa_tool_17.png)

10. <span data-ttu-id="b31f1-209">Selecione **Aceitar**.</span><span class="sxs-lookup"><span data-stu-id="b31f1-209">Select **Accept**.</span></span>

    ![Autorizando acesso](./media/setup_rsa_tool_18.png)

11. <span data-ttu-id="b31f1-211">Se estiver autorizado como usuário, a IU deverá retornar à página de configurações do projeto LCS.</span><span class="sxs-lookup"><span data-stu-id="b31f1-211">If you're authorized as a user, the UI should you return to the LCS project settings page.</span></span>

    ![Usuário autorizado](./media/setup_rsa_tool_19.png)

### <a name="create-a-new-bpm-library"></a><span data-ttu-id="b31f1-213">Criar uma nova biblioteca do BPM</span><span class="sxs-lookup"><span data-stu-id="b31f1-213">Create a new BPM library</span></span>

1. <span data-ttu-id="b31f1-214">Vá para o projeto de implementação de LCS.</span><span class="sxs-lookup"><span data-stu-id="b31f1-214">Go to the LCS implementation project.</span></span>
2. <span data-ttu-id="b31f1-215">Selecione o botão **Menu** e, em seguida, **Modelador de processo de negócios**.</span><span class="sxs-lookup"><span data-stu-id="b31f1-215">Select the **Menu** button, and then select **Business process modeler**.</span></span>

    ![Comando do Modelador de processo de negócios](./media/setup_rsa_tool_20.png)

3. <span data-ttu-id="b31f1-217">Selecione **Nova biblioteca**.</span><span class="sxs-lookup"><span data-stu-id="b31f1-217">Select **New library**.</span></span>

    ![Botão Nova biblioteca](./media/setup_rsa_tool_21.png)

4. <span data-ttu-id="b31f1-219">No campo **Nome da biblioteca** , insira um nome e, em seguida, selecione **Criar**.</span><span class="sxs-lookup"><span data-stu-id="b31f1-219">In the **Library name** field, enter a name, and then select **Create**.</span></span> <span data-ttu-id="b31f1-220">Para este tutorial, nomeie a biblioteca BPM **RSAT**.</span><span class="sxs-lookup"><span data-stu-id="b31f1-220">For this tutorial, name the BPM library **RSAT**.</span></span>

    ![Caixa de diálogo Criar nova biblioteca](./media/setup_rsa_tool_22.png)

5. <span data-ttu-id="b31f1-222">Abra a nova biblioteca do BPM **RSAT**.</span><span class="sxs-lookup"><span data-stu-id="b31f1-222">Open the new **RSAT** BPM library.</span></span>
6. <span data-ttu-id="b31f1-223">Selecione o processo **Processo de Negócios do Exemplo Principal** e, em seguida, à direita selecione **Modo de edição**.</span><span class="sxs-lookup"><span data-stu-id="b31f1-223">Select the **Sample Core Business Process** process, and then, on the right, select **Edit mode**.</span></span>

    ![Botão Modo de edição](./media/setup_rsa_tool_23.png)

7. <span data-ttu-id="b31f1-225">Alterar o valor dos campos **Nome** e **Descrição** para **Criar um produto**.</span><span class="sxs-lookup"><span data-stu-id="b31f1-225">Change the value of both the **Name** field and the **Description** field to **Create a product**.</span></span> <span data-ttu-id="b31f1-226">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="b31f1-226">Then select **Save**.</span></span>

    ![Campos Nome e Descrição](./media/setup_rsa_tool_24.png)

## <a name="environment"></a><span data-ttu-id="b31f1-228">Ambiente</span><span class="sxs-lookup"><span data-stu-id="b31f1-228">Environment</span></span>

### <a name="version-requirement"></a><span data-ttu-id="b31f1-229">Requisito da versão</span><span class="sxs-lookup"><span data-stu-id="b31f1-229">Version requirement</span></span>

<span data-ttu-id="b31f1-230">É necessário um ambiente de área restrita ou de teste que execute a versão 10.</span><span class="sxs-lookup"><span data-stu-id="b31f1-230">A test or sandbox environment that runs version 10 is required.</span></span> <span data-ttu-id="b31f1-231">Para clientes que estão usando a versão 7.3, a atualização da plataforma 20 ou superior também é suportada.</span><span class="sxs-lookup"><span data-stu-id="b31f1-231">For customers that are using version 7.3, Platform update 20 or later is also supported.</span></span>

> [!NOTE]
> <span data-ttu-id="b31f1-232">O RSAT deve ter acesso ao seu ambiente de teste através de um navegador da Web.</span><span class="sxs-lookup"><span data-stu-id="b31f1-232">RSAT must have access to your test environment via a web browser.</span></span>

### <a name="user-criteria"></a><span data-ttu-id="b31f1-233">Critérios do usuário</span><span class="sxs-lookup"><span data-stu-id="b31f1-233">User criteria</span></span>

<span data-ttu-id="b31f1-234">O usuário deve ter direitos de administrador neste ambiente.</span><span class="sxs-lookup"><span data-stu-id="b31f1-234">The user must have admin rights to this environment.</span></span>

### <a name="set-up-help-settings-to-connect-with-lcs"></a><span data-ttu-id="b31f1-235">Definir configurações de Ajuda para conectar-se ao LCS</span><span class="sxs-lookup"><span data-stu-id="b31f1-235">Set up Help settings to connect with LCS</span></span>

<span data-ttu-id="b31f1-236">Esta etapa é necessária para a conexão com o LCS, de forma que as gravações de tarefas possam ser salvas na biblioteca do BPM apropriada no LCS, por meio do cliente.</span><span class="sxs-lookup"><span data-stu-id="b31f1-236">This step is required in order to connect with LCS so that task recordings can be saved to the appropriate BPM library in LCS through the client.</span></span>

1. <span data-ttu-id="b31f1-237">Abra o cliente.</span><span class="sxs-lookup"><span data-stu-id="b31f1-237">Open the client.</span></span>
2. <span data-ttu-id="b31f1-238">Vá para **Administração do Sistema \> Configuração \> Parâmetros do sistema**.</span><span class="sxs-lookup"><span data-stu-id="b31f1-238">Go to **System Administration \> Setup \> System parameters**.</span></span>
3. <span data-ttu-id="b31f1-239">Na guia **Ajuda**, no campo **Configuração de ajuda do Lifecycle Services**, selecione o projeto LCS relevante (**RSAT** para este tutorial).</span><span class="sxs-lookup"><span data-stu-id="b31f1-239">On the **Help** tab, in the **Lifecycle Services help configuration** field, select the relevant LCS project (**RSAT** for this tutorial).</span></span>

    ![Campo da ajuda do Lifecycle Services na guia Ajuda](./media/setup_rsa_tool_25.png)

    <span data-ttu-id="b31f1-241">As bibliotecas de BPM são preenchidas no projeto LCS apropriado.</span><span class="sxs-lookup"><span data-stu-id="b31f1-241">BPM libraries are filled in under the appropriate LCS project.</span></span>

4. <span data-ttu-id="b31f1-242">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="b31f1-242">Select **Save**.</span></span>
5. <span data-ttu-id="b31f1-243">Pode ser necessário atualizar o navegador para ver o conteúdo da Ajuda atualizado.</span><span class="sxs-lookup"><span data-stu-id="b31f1-243">You might have to refresh the browser to see the updated Help content.</span></span>

    ![Notificação sobre como atualizar o navegador](./media/setup_rsa_tool_26.png)

## <a name="task-recordings"></a><span data-ttu-id="b31f1-245">Gravações de tarefas</span><span class="sxs-lookup"><span data-stu-id="b31f1-245">Task recordings</span></span>

> [!NOTE]
> <span data-ttu-id="b31f1-246">Verifique se todas as suas gravações de tarefas começam no painel principal.</span><span class="sxs-lookup"><span data-stu-id="b31f1-246">Make sure that all your task recordings start on the main dashboard.</span></span> <span data-ttu-id="b31f1-247">Mantenha gravações individuais curtas e concentre-se em uma tarefa de negócios, como criar uma ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="b31f1-247">Keep individual recordings short, and focus on one business task, such as creating a sales order.</span></span>

### <a name="create-a-task-recording-and-save-it-to-the-bpm-library"></a><span data-ttu-id="b31f1-248">Crie uma gravação de tarefas e salve-a na biblioteca do BPM</span><span class="sxs-lookup"><span data-stu-id="b31f1-248">Create a task recording and save it to the BPM library</span></span>

<span data-ttu-id="b31f1-249">Crie uma gravação de tarefas correspondente que você possa anexar ao processo de negócios simples que foi criado na nova biblioteca do BPM.</span><span class="sxs-lookup"><span data-stu-id="b31f1-249">Create a corresponding task recording that you can attach to the simple business process that was created in the new BPM library.</span></span>

1. <span data-ttu-id="b31f1-250">Abra o cliente.</span><span class="sxs-lookup"><span data-stu-id="b31f1-250">Open the client.</span></span>
2. <span data-ttu-id="b31f1-251">No painel principal, selecione o botão **Configurações** (o símbolo de engrenagem) e, em seguida, **Gravador de Tarefas**.</span><span class="sxs-lookup"><span data-stu-id="b31f1-251">On the main dashboard, select the **Settings** button (the gear symbol), and then select **Task recorder**.</span></span>

    ![Selecionar o Gravador de tarefas no menu Configurações](./media/setup_rsa_tool_27.png)

3. <span data-ttu-id="b31f1-253">Selecione **Criar gravação**.</span><span class="sxs-lookup"><span data-stu-id="b31f1-253">Select **Create recording**.</span></span>

    ![Botão Criar gravação](./media/setup_rsa_tool_28.png)

4. <span data-ttu-id="b31f1-255">Preencha os campos **Nome da gravação** e **Descrição da gravação** e selecione **Iniciar**.</span><span class="sxs-lookup"><span data-stu-id="b31f1-255">Fill in the **Recording name** and **Recording description** fields, and then select **Start**.</span></span>

    ![Campos Nome da gravação e Descrição da gravação](./media/setup_rsa_tool_29.png)

5. <span data-ttu-id="b31f1-257">Registre as etapas para criar um produto.</span><span class="sxs-lookup"><span data-stu-id="b31f1-257">Record the steps for creating a product.</span></span> <span data-ttu-id="b31f1-258">Quando terminar, selecione **Parar** para parar a gravação.</span><span class="sxs-lookup"><span data-stu-id="b31f1-258">When you've finished, select **Stop** to stop recording.</span></span>

    ![Etapas para criar um produto](./media/setup_rsa_tool_30.png)

6. <span data-ttu-id="b31f1-260">Selecione **Salvar no Lifecycle Services**.</span><span class="sxs-lookup"><span data-stu-id="b31f1-260">Select **Save to Lifecycle Services**.</span></span>

    ![Salvar a gravação de tarefas no Lifecycle Services](./media/setup_rsa_tool_31.png)

    <span data-ttu-id="b31f1-262">As informações da biblioteca são carregadas do LCS.</span><span class="sxs-lookup"><span data-stu-id="b31f1-262">Library information is loaded from LCS.</span></span>

    ![Carregar informações da biblioteca](./media/setup_rsa_tool_32.png)

7. <span data-ttu-id="b31f1-264">Selecione a biblioteca do BPM para associar à gravação de tarefas.</span><span class="sxs-lookup"><span data-stu-id="b31f1-264">Select the BPM library to associate the task recording with.</span></span> <span data-ttu-id="b31f1-265">Para este tutorial, selecione a biblioteca **RSAT** do BPM que foi criada anteriormente e o processo de negócios **Criar um produto**.</span><span class="sxs-lookup"><span data-stu-id="b31f1-265">For this tutorial, select the **RSAT** BPM library that was created earlier and the **Create a product** business process under it.</span></span> <span data-ttu-id="b31f1-266">Em seguida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="b31f1-266">Then select **OK**.</span></span>

    ![Associando a gravação de tarefas com uma biblioteca do BPM e um processo de negócios](./media/setup_rsa_tool_33.png)

    <span data-ttu-id="b31f1-268">É exibida uma mensagem "Lifecycle Services salvo com sucesso".</span><span class="sxs-lookup"><span data-stu-id="b31f1-268">A "Saving to Lifecycle Services was successful" message appears.</span></span>

    ![Mensagem sobre gravação ao LCS bem-sucedida](./media/setup_rsa_tool_34.png)

8. <span data-ttu-id="b31f1-270">Se quiser salvar a gravação de tarefas localmente e, em seguida, fazer upload dela para o BPM através do LCS, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="b31f1-270">If you want to save the task recording locally and then upload it to BPM through LCS, follow these steps:</span></span>

    1. <span data-ttu-id="b31f1-271">Depois que a gravação for concluída, selecione **Salvar neste PC**.</span><span class="sxs-lookup"><span data-stu-id="b31f1-271">After the recording is completed, select **Save to this PC**.</span></span>

        ![Salvar neste computador](./media/setup_rsa_tool_35.png)

    2. <span data-ttu-id="b31f1-273">Na barra de Notificação do navegador, selecione **Salvar** ou **Salvar como** para salvar o arquivo em seu computador local.</span><span class="sxs-lookup"><span data-stu-id="b31f1-273">In the browser's Notification bar, select **Save** or **Save As** to save the file on your local computer.</span></span>

        ![Barra de notificação](./media/setup_rsa_tool_36.png)

    3. <span data-ttu-id="b31f1-275">Vá para a biblioteca **RSAT** do BPM e selecione o processo de negócios em que salvará a gravação de tarefas.</span><span class="sxs-lookup"><span data-stu-id="b31f1-275">Go to the **RSAT** BPM library, and select the business process to save the task recording against.</span></span>
    4. <span data-ttu-id="b31f1-276">Na guia **Visão geral** , selecione **Carregar**.</span><span class="sxs-lookup"><span data-stu-id="b31f1-276">On the **Overview** tab, select **Upload**.</span></span>

        ![Botão Carregar](./media/setup_rsa_tool_37.png)

    5. <span data-ttu-id="b31f1-278">Selecione **Procurar** e o arquivo .axtr salvo anteriormente.</span><span class="sxs-lookup"><span data-stu-id="b31f1-278">Select **Browse**, and select the .axtr file that you saved earlier.</span></span> <span data-ttu-id="b31f1-279">Depois, selecione **Carregar**.</span><span class="sxs-lookup"><span data-stu-id="b31f1-279">Then select **Upload**.</span></span>

        ![Selecione o arquivo .axtr para carregar](./media/setup_rsa_tool_38.png)

### <a name="test-the-synchronization-from-bpm-to-azure-devops"></a><span data-ttu-id="b31f1-281">Testar a sincronização do BPM para o Azure DevOps</span><span class="sxs-lookup"><span data-stu-id="b31f1-281">Test the synchronization from BPM to Azure DevOps</span></span>

<span data-ttu-id="b31f1-282">Agora que uma gravação de tarefas está vinculada ao processo de negócios, você deve validar se o processo de negócios e a gravação de tarefas associada podem ser sincronizados ao Azure DevOps como um recurso e um caso de teste (respectivamente), usando o recurso de sincronização do VSTS no LCS.</span><span class="sxs-lookup"><span data-stu-id="b31f1-282">Now that a task recording is attached to the business process, you must validate that the business process and the associated task recording can be synced to Azure DevOps as a feature and a test case (respectively) by using the VSTS sync feature in LCS.</span></span>

> [!NOTE]
> <span data-ttu-id="b31f1-283">O tipo de item de trabalho correspondente que é criado no Azure DevOps irá variar, dependendo do modelo do processo selecionado quando você configurou o projeto LCS com o Azure DevOps, conforme descrito na seção [Criar um novo projeto do Azure DevOps](#create-a-new-azure-devops-project).</span><span class="sxs-lookup"><span data-stu-id="b31f1-283">The corresponding work item type that is created in Azure DevOps will vary, depending on the process template that you selected when you configured the LCS project with Azure DevOps, as described in the [Create a new Azure DevOps project](#create-a-new-azure-devops-project) section.</span></span>

1. <span data-ttu-id="b31f1-284">Vá para a biblioteca BPM e abra a biblioteca **RSAT** criada anteriormente.</span><span class="sxs-lookup"><span data-stu-id="b31f1-284">Go to the BPM library, and open the **RSAT** library that you created earlier.</span></span>
2. <span data-ttu-id="b31f1-285">Selecione o botão de reticências (**...**) e depois **Sincronização de VSTS**.</span><span class="sxs-lookup"><span data-stu-id="b31f1-285">Select the ellipsis button (**...**), and select **VSTS sync**.</span></span>

    ![Comando de sincronização de VSTS no menu de reticências](./media/setup_rsa_tool_39.png)

    <span data-ttu-id="b31f1-287">Depois que a sincronização de VSTS for concluída, uma guia **Requisitos** aparecerá no lado esquerdo e incluirá o item de trabalho do Azure DevOps correspondente.</span><span class="sxs-lookup"><span data-stu-id="b31f1-287">After VSTS sync is completed, a **Requirements** tab appears on the left side and includes the corresponding Azure DevOps work item.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b31f1-288">O item de trabalho criado no Azure DevOps terá o nome da biblioteca do BPM como o prefixo do título.</span><span class="sxs-lookup"><span data-stu-id="b31f1-288">The work item that is created in Azure DevOps will have the BPM library name as the title prefix.</span></span>

    ![Guia Requisitos](./media/setup_rsa_tool_40.png)

3. <span data-ttu-id="b31f1-290">Atualize a página.</span><span class="sxs-lookup"><span data-stu-id="b31f1-290">Refresh the page.</span></span>
4. <span data-ttu-id="b31f1-291">Selecione o botão de reticências (**...**). Você verá uma opção adicional, **Sincronizar casos de teste**.</span><span class="sxs-lookup"><span data-stu-id="b31f1-291">Select the ellipsis button (**...**). You will see an additional option, **Sync test cases**.</span></span> <span data-ttu-id="b31f1-292">Selecione esta opção.</span><span class="sxs-lookup"><span data-stu-id="b31f1-292">Select this option.</span></span>

    ![Comando Sincronizar casos de teste no menu de reticências](./media/setup_rsa_tool_41.png)

    > [!NOTE]
    > <span data-ttu-id="b31f1-294">Se a opção **Sincronizar casos de teste** não estiver disponível depois que você atualizar a página, vá para a página principal do BPM e selecione **Sincronizar casos de teste** para toda a biblioteca.</span><span class="sxs-lookup"><span data-stu-id="b31f1-294">If the **Sync test cases** option isn't available after you refresh the page, go to main page for BPM, and select **Sync test cases** for the whole library itself.</span></span> <span data-ttu-id="b31f1-295">Assim, você força eficientemente uma sincronização para toda a biblioteca.</span><span class="sxs-lookup"><span data-stu-id="b31f1-295">In this way, you effectively force a synchronization for the whole library.</span></span>
    >
    > ![Selecionar Sincronizar casos de teste para toda a biblioteca](./media/setup_rsa_tool_42.png)

    <span data-ttu-id="b31f1-297">Depois que Sincronizar casos de teste for concluída, um novo caso de teste será criado na guia **Requisitos**.</span><span class="sxs-lookup"><span data-stu-id="b31f1-297">After Sync test cases is completed, a new test case is created on the **Requirements** tab.</span></span>

    ![Novo caso de teste na guia Requisitos](./media/setup_rsa_tool_43.png)

5. <span data-ttu-id="b31f1-299">Vá para seu projeto do Azure DevOps e selecione **Quadros \> Itens de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="b31f1-299">Go to your Azure DevOps project, and select **Boards \> Work Items**.</span></span>

    ![Comandos Itens de Trabalho nos Quadros](./media/setup_rsa_tool_44.png)

6. <span data-ttu-id="b31f1-301">Validar se existe o item de trabalho e o caso de teste que você criou através da sincronização do BPM.</span><span class="sxs-lookup"><span data-stu-id="b31f1-301">Validate that the work item and test case that you created through BPM synchronization exist.</span></span>

    ![Item de trabalho e caso de teste](./media/setup_rsa_tool_45.png)

## <a name="install-and-configure-rsat"></a><span data-ttu-id="b31f1-303">Instalar e Configurar o RSAT</span><span class="sxs-lookup"><span data-stu-id="b31f1-303">Install and Configure RSAT</span></span>

<span data-ttu-id="b31f1-304">O RSAT pode ser instalado em qualquer computador que execute o Windows 10 e que possa conectar-se ao ambiente através de um navegador da Web (Internet Explorer ou Google Chrome).</span><span class="sxs-lookup"><span data-stu-id="b31f1-304">RSAT can be installed on any computer that runs Windows 10 and that can connect to the environment via a web browser (Internet Explorer or Google Chrome).</span></span>

> [!NOTE]
> <span data-ttu-id="b31f1-305">Antes de instalar uma nova versão de ferramenta, recomendamos que você desinstale a versão anterior.</span><span class="sxs-lookup"><span data-stu-id="b31f1-305">Before you install a new version of the tool, we recommend that you uninstall the previous version.</span></span>

### <a name="install-an-authentication-certificate"></a><span data-ttu-id="b31f1-306">Instalar um certificado de autenticação</span><span class="sxs-lookup"><span data-stu-id="b31f1-306">Install an authentication certificate</span></span>

<span data-ttu-id="b31f1-307">Para habilitar a autenticação, você deve gerar e instalar um certificado no mesmo computador que o RSAT está sendo executado.</span><span class="sxs-lookup"><span data-stu-id="b31f1-307">To enable authentication, you must generate and install a certificate on the same computer that RSAT is running on.</span></span>

#### <a name="generate-a-certificate"></a><span data-ttu-id="b31f1-308">Gerar um certificado</span><span class="sxs-lookup"><span data-stu-id="b31f1-308">Generate a certificate</span></span>

1. <span data-ttu-id="b31f1-309">Para gerar um arquivo do certificado, abra a janela do Microsoft Windows PowerShell como administrador e execute o seguinte comando.</span><span class="sxs-lookup"><span data-stu-id="b31f1-309">To generate a certificate file, open a Microsoft Windows PowerShell window as an admin, and run the following command.</span></span>

    ```powershell
    $certificate = New-SelfSignedCertificate -dnsname 127.0.0.1 -CertStoreLocation cert:\LocalMachine\My -FriendlyName "D365 Automated testing certificate" -Provider "Microsoft Strong Cryptographic Provider"
    ```

2. <span data-ttu-id="b31f1-310">Abra o gerenciador de certificados inserindo **certlm.msc** na caixa de diálogo **Executar** e confirme se o **Certificado de teste automatizado D365** foi criado em **Certificados \> Pessoais**.</span><span class="sxs-lookup"><span data-stu-id="b31f1-310">Open certificate manager by entering **certlm.msc** in the **Run** dialog box, and confirm that the **D365 Automated testing certificate** certificate is created under **Personal \> Certificates**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b31f1-311">Certifique-se de inserir **certlm.msc**, não **certmgr.msc** porque os certificados estão armazenados no computador local.</span><span class="sxs-lookup"><span data-stu-id="b31f1-311">Be sure to enter **certlm.msc**, not **certmgr.msc**, because the certificates are stored on the local computer.</span></span>

    ![Certificado de teste automatizado D365](./media/setup_rsa_tool_46.png)

3. <span data-ttu-id="b31f1-313">Clique com o botão direito do mouse no certificado e, em seguida, selecione **Copiar**.</span><span class="sxs-lookup"><span data-stu-id="b31f1-313">Right-click the certificate, and then select **Copy**.</span></span>
4. <span data-ttu-id="b31f1-314">Vá para **Autoridades de certificação raiz confiáveis \> Certificados**.</span><span class="sxs-lookup"><span data-stu-id="b31f1-314">Go to **Trusted Root Certification Authorities \> Certificates**.</span></span>

    ![Pasta Certificados na pasta Autoridades de certificação raiz confiáveis](./media/setup_rsa_tool_47.png)

5. <span data-ttu-id="b31f1-316">No menu **Ação**, selecione **Colar** para copiar o certificado no local **Autoridades de certificação raiz confiáveis**.</span><span class="sxs-lookup"><span data-stu-id="b31f1-316">On the **Action** menu, select **Paste** to copy the certificate to the **Trusted Root Certification Authorities** location.</span></span>

    ![Comando Colar no menu Ação](./media/setup_rsa_tool_48.png)

6. <span data-ttu-id="b31f1-318">Para obter a impressão digital do certificado instalado, mas sem espaços ou caracteres especiais, abra a janela do Windows PowerShell como um administrador e execute os seguintes comandos.</span><span class="sxs-lookup"><span data-stu-id="b31f1-318">To get the thumbprint of the installed certificate, but without spaces or special characters, open a Windows PowerShell window as an admin, and run the following commands.</span></span>

    ```powershell
    cd Cert:\LocalMachine\My

    Get-ChildItem | Where-Object { $_.Subject -like "CN=127.0.0.1" }
    ```

    > [!NOTE]
    > <span data-ttu-id="b31f1-319">Salve a impressão digital porque você precisará dela posteriormente quando atualizar os arquivos .wif para o Application Object Server (AOS) e defina a configuração de RSAT.</span><span class="sxs-lookup"><span data-stu-id="b31f1-319">Save the thumbprint, because you will need it later when you update the .wif files for Application Object Server (AOS) and set up the RSAT configuration.</span></span>

#### <a name="configure-the-aos-computer-to-trust-the-connection"></a><span data-ttu-id="b31f1-320">Configure o computador AOS para confiar na conexão</span><span class="sxs-lookup"><span data-stu-id="b31f1-320">Configure the AOS computer to trust the connection</span></span>

> [!NOTE]
> <span data-ttu-id="b31f1-321">Se o ambiente for um ambiente de Camada 2+, a impressão digital do certificado deverá ser atualizada no arquivo wif.config para **todos** os computadores AOS do ambiente.</span><span class="sxs-lookup"><span data-stu-id="b31f1-321">If the environment is a Tier 2+ environment, the certificate thumbprint must be updated in the wif.config file for **all** AOS computers for the environment.</span></span>

1. <span data-ttu-id="b31f1-322">Estabeleça uma conexão do Remote Desktop Protocol (RDP) para o computador AOS.</span><span class="sxs-lookup"><span data-stu-id="b31f1-322">Establish a Remote Desktop Protocol (RDP) connection to the AOS computer.</span></span> <span data-ttu-id="b31f1-323">Os detalhes de entrada estão disponíveis na página detalhes do ambiente no LCS.</span><span class="sxs-lookup"><span data-stu-id="b31f1-323">Sign-in details are available on the environment details page in LCS.</span></span>
2. <span data-ttu-id="b31f1-324">Abra o Microsoft Internet Information Services (IIS) e localize o **AOSService** na lista de sites.</span><span class="sxs-lookup"><span data-stu-id="b31f1-324">Open Microsoft Internet Information Services (IIS), and find **AOSService** in the list of sites.</span></span>

    ![AOSService na lista de sites](./media/setup_rsa_tool_49.png)

3. <span data-ttu-id="b31f1-326">Clique com o botão direito do mouse em **Explorar** para abrir a pasta **\<Drive\>: \\AosService\\WebRoot**.</span><span class="sxs-lookup"><span data-stu-id="b31f1-326">Right-click **Explore** to open the **\<Drive\>: \\AosService\\WebRoot** folder.</span></span> <span data-ttu-id="b31f1-327">Localize o arquivo **wif.config**.</span><span class="sxs-lookup"><span data-stu-id="b31f1-327">Find the **wif.config** file.</span></span>

    ![Arquivo Wif.config na pasta Webroot](./media/setup_rsa_tool_50.png)

4. <span data-ttu-id="b31f1-329">Atualize o arquivo **wif.config** adicionando uma nova entrada de autoridade em seu certificado e no nome da autoridade, conforme mostrado no exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="b31f1-329">Update the **wif.config** file by adding a new authority entry for your certificate and authority name, as shown in the following example.</span></span>

    ```Xml
    <issuerNameRegistry type="Microsoft.Dynamics.AX.Security.SharedUtility.AxIssuerNameRegistry,Microsoft.Dynamics.AX.Security.SharedUtility">
        <authority name="CN=127.0.0.1">
            <keys>
                <add thumbprint="xxxxxxxxxxxxxxxxxxxx" />
                <add thumbprint="xxxxxxxxxxxxxxxxxxxx" />
            </keys>
            <validIssuers>
                <add name="CN=127.0.0.1" />
            </validIssuers>
        </authority>
    ```

    > [!NOTE]
    > <span data-ttu-id="b31f1-330">Se vários usuários estiverem usando o mesmo aplicativo, cada usuário deverá gerar impressões digitais separadas e cada uma dessas impressões deverá ser adicionada à seção **\<keys\>**.</span><span class="sxs-lookup"><span data-stu-id="b31f1-330">If multiple users are using the same application, each user must generate separate thumbprints, and each of those thumbprints must be added in the **\<keys\>** section.</span></span>

5. <span data-ttu-id="b31f1-331">Se houver mais de um computador AOS, repita as etapas 3 a 4 para cada computador adicional.</span><span class="sxs-lookup"><span data-stu-id="b31f1-331">If there is more than one AOS computer, repeat steps 3 through 4 for each additional computer.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b31f1-332">Ao contrário dos ambientes da Camada 2, os novos ambientes da Camada 2 são implantados com duas instâncias do AOS.</span><span class="sxs-lookup"><span data-stu-id="b31f1-332">Unlike older Tier 2 environments, new Tier 2 environments are deployed with two AOS instances.</span></span>

6. <span data-ttu-id="b31f1-333">Execute **iisreset** em todos os computadores AOS.</span><span class="sxs-lookup"><span data-stu-id="b31f1-333">Run **iisreset** on all the AOS computers.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b31f1-334">Se você não tiver direitos administrativos para executar o **iisreset** em um computador Camada 1, na página detalhes do Ambiente na LCS, selecione Manter > Reiniciar serviços.</span><span class="sxs-lookup"><span data-stu-id="b31f1-334">If you don't have admin rights to run **iisreset** on a Tier 1 computer, on the Environment details page in LCS, select Maintain > Restart services.</span></span>

#### <a name="tier-2-environment"></a><span data-ttu-id="b31f1-335">Ambiente da Camada 2+</span><span class="sxs-lookup"><span data-stu-id="b31f1-335">Tier 2+ environment</span></span>

<span data-ttu-id="b31f1-336">Se um ambiente de Camada 2+ (área restrita ou superior do Teste de Aceitação Padrão) for usado, verifique ou defina a seguinte configuração de registro no computador onde o RSAT está instalado.</span><span class="sxs-lookup"><span data-stu-id="b31f1-336">If a Tier 2+ (Standard Acceptance Test sandbox or higher) environment is used, verify or set the following registry setting on the computer where RSAT is installed.</span></span> <span data-ttu-id="b31f1-337">Essa etapa é necessária porque ajuda a evitar erros de conexão RSAT ou de autenticação.</span><span class="sxs-lookup"><span data-stu-id="b31f1-337">This step is required because it helps you avoid authentication or RSAT connection errors.</span></span>

```PowerShell
if ((Test-Path HKLM:\SOFTWARE\Wow6432Node\Microsoft\.NETFramework\v4.0.30319))
{
    Set-ItemProperty HKLM:\SOFTWARE\Wow6432Node\Microsoft\.NETFramework\v4.0.30319 -Name SchUseStrongCrypto -Value 1 -Type dword -Force -Confirm:$false
}
```

### <a name="install-rsat"></a><span data-ttu-id="b31f1-338">Instalar RSAT</span><span class="sxs-lookup"><span data-stu-id="b31f1-338">Install RSAT</span></span>

1. <span data-ttu-id="b31f1-339">Vá para o <https://www.microsoft.com/download/details.aspx?id=57357> e selecione **Baixar**.</span><span class="sxs-lookup"><span data-stu-id="b31f1-339">Go to <https://www.microsoft.com/download/details.aspx?id=57357>, and select **Download**.</span></span>
2. <span data-ttu-id="b31f1-340">Selecione todos os arquivos e depois **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="b31f1-340">Select all the files, and then select **Next**.</span></span>

    ![Selecionando todos os arquivos](./media/setup_rsa_tool_51.png)

3. <span data-ttu-id="b31f1-342">Clique duas vezes no pacote .msi para executar o instalador.</span><span class="sxs-lookup"><span data-stu-id="b31f1-342">Double-click the .msi package to run the installer.</span></span> <span data-ttu-id="b31f1-343">Em seguida, quando a instalação for concluída, selecione **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="b31f1-343">Then, when the installation is completed, select **Finish**.</span></span>

    ![Arquivo do Instalador do RSAT](./media/setup_rsa_tool_52.png)

### <a name="install-selenium-and-browser-drivers"></a><span data-ttu-id="b31f1-345">Instalar Selenium e drivers dos navegadores</span><span class="sxs-lookup"><span data-stu-id="b31f1-345">Install Selenium and browser drivers</span></span>

<span data-ttu-id="b31f1-346">Em versões anteriores do RSAT, você teve que instalar o Selenium e os drivers do navegador.</span><span class="sxs-lookup"><span data-stu-id="b31f1-346">In older versions of RSAT, you had to install Selenium and browser drivers.</span></span> <span data-ttu-id="b31f1-347">Não é mais necessário instalar esses drivers porque eles são instalados automaticamente.</span><span class="sxs-lookup"><span data-stu-id="b31f1-347">You no longer have to install these drivers because they are automatically installed.</span></span>

1. <span data-ttu-id="b31f1-348">Na primeira vez que você abrir o RSAT, será solicitado que você baixe automaticamente e instale o Selenium.</span><span class="sxs-lookup"><span data-stu-id="b31f1-348">The first time that you open RSAT, you're prompted to automatically download and install Selenium.</span></span> <span data-ttu-id="b31f1-349">Para obter mais informações, consulte a seção [Configurar RSAT](#configure-rsat).</span><span class="sxs-lookup"><span data-stu-id="b31f1-349">For more information, see the [Configure RSAT](#configure-rsat) section.</span></span>
2. <span data-ttu-id="b31f1-350">Antes de executar um caso de teste, será solicitado que você baixe automaticamente e instale o driver do navegador que corresponde ao navegador padrão selecionado na configuração do RSAT.</span><span class="sxs-lookup"><span data-stu-id="b31f1-350">Before you can run a test case, you're prompted to automatically download and install the browser driver that corresponds to the default browser that is selected in the RSAT configuration.</span></span> <span data-ttu-id="b31f1-351">Para obter mais informações, consulte a seção [Carregar e executar casos de teste](#load-and-run-test-cases).</span><span class="sxs-lookup"><span data-stu-id="b31f1-351">For more information, see the [Load and run test cases](#load-and-run-test-cases) section.</span></span>

## <a name="get-started-with-rsat"></a><span data-ttu-id="b31f1-352">Começar a usar o RSAT</span><span class="sxs-lookup"><span data-stu-id="b31f1-352">Get started with RSAT</span></span>

### <a name="create-a-test-plan-and-test-suites"></a><span data-ttu-id="b31f1-353">Crie um plano de teste e conjuntos de testes</span><span class="sxs-lookup"><span data-stu-id="b31f1-353">Create a test plan and test suites</span></span>

1. <span data-ttu-id="b31f1-354">Vá para o projeto Azure DevOps e selecione **Planos de Teste**.</span><span class="sxs-lookup"><span data-stu-id="b31f1-354">Go to the Azure DevOps project, and select **Test Plans**.</span></span>

    ![Comando Planos de teste](./media/setup_rsa_tool_53.png)

2. <span data-ttu-id="b31f1-356">Selecione **Novo Plano de Teste**.</span><span class="sxs-lookup"><span data-stu-id="b31f1-356">Select **New Test Plan**.</span></span>

    ![Botão Novo Plano de Teste](./media/setup_rsa_tool_54.png)

3. <span data-ttu-id="b31f1-358">Preencha o campo **Nome** e, em seguida, selecione **Criar**.</span><span class="sxs-lookup"><span data-stu-id="b31f1-358">Fill in the **Name** field, and then select **Create**.</span></span> <span data-ttu-id="b31f1-359">Para este tutorial, nomeie o plano de teste como **Plano de Teste RSAT**.</span><span class="sxs-lookup"><span data-stu-id="b31f1-359">For this tutorial, name the test plan **RSAT Test Plan**.</span></span>

    ![Caixa de diálogo Novo Plano de Teste](./media/setup_rsa_tool_55.png)

4. <span data-ttu-id="b31f1-361">Selecione o sinal de adição (**+**) e, em seguida, selecione **Conjunto estático** para criar um conjunto estático no novo plano de teste.</span><span class="sxs-lookup"><span data-stu-id="b31f1-361">Select the plus sign (**+**), and then select **Static suite** to create a static suite under the new test plan.</span></span> <span data-ttu-id="b31f1-362">Nomeie o novo conjunto de teste **T01 – Fabricar para Armazenar**.</span><span class="sxs-lookup"><span data-stu-id="b31f1-362">Name the new test suite **T01 – Make to Stock**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b31f1-363">Você também pode criar um pacote com base na consulta, se quiser que os novos casos de teste do BPM sejam incluídos automaticamente no conjunto de testes do RSAT.</span><span class="sxs-lookup"><span data-stu-id="b31f1-363">You can also create a query-based suite, if you want the new test cases from BPM to be automatically pulled into the RSAT test suite.</span></span>

    ![Criando um conjunto estático](./media/setup_rsa_tool_56.png)

### <a name="attach-test-cases-to-test-suites"></a><span data-ttu-id="b31f1-365">Anexar casos de teste aos conjuntos de testes</span><span class="sxs-lookup"><span data-stu-id="b31f1-365">Attach test cases to test suites</span></span>

1. <span data-ttu-id="b31f1-366">Selecionar **Adicionar existente** no lado direito para adicionar os casos de teste existentes ao conjunto de testes.</span><span class="sxs-lookup"><span data-stu-id="b31f1-366">Select **Add existing** on the right side to add existing test cases to the test suite.</span></span>

    ![Botão Adicionar existente](./media/setup_rsa_tool_57.png)

2. <span data-ttu-id="b31f1-368">Na página **Adicionar casos de teste ao conjunto**, selecione **Executar consulta** e, em seguida, selecione o caso de teste para adicionar ao conjunto de testes.</span><span class="sxs-lookup"><span data-stu-id="b31f1-368">On the **Add test cases to suite** page, select **Run query**, and then select the test case to add to the test suite.</span></span> <span data-ttu-id="b31f1-369">Para este tutorial, selecione o caso de teste **Criar um novo produto**.</span><span class="sxs-lookup"><span data-stu-id="b31f1-369">For this tutorial, select the **Create a new product** test case.</span></span> <span data-ttu-id="b31f1-370">Em seguida, selecione **Adicionar casos de teste** no canto inferior direito da página (este botão não é mostrado na ilustração a seguir).</span><span class="sxs-lookup"><span data-stu-id="b31f1-370">Then select **Add test cases** in the lower-right corner of the page (this button isn't shown in the following illustration).</span></span>

    ![Botão Executar consulta](./media/setup_rsa_tool_58.png)

    <span data-ttu-id="b31f1-372">O caso de teste é adicionado ao conjunto de testes **T01-Fabricar para Armazenar**.</span><span class="sxs-lookup"><span data-stu-id="b31f1-372">The test case is added to the **T01-Make to Stock** test suite.</span></span>

    ![Caso de teste adicionado ao conjunto de teste](./media/setup_rsa_tool_59.png)

### <a name="configure-rsat"></a><span data-ttu-id="b31f1-374">Configurar RSAT</span><span class="sxs-lookup"><span data-stu-id="b31f1-374">Configure RSAT</span></span>

1. <span data-ttu-id="b31f1-375">Abrir RSAT.</span><span class="sxs-lookup"><span data-stu-id="b31f1-375">Open RSAT.</span></span>

    ![Ícone de RSAT](./media/setup_rsa_tool_60.png)

2. <span data-ttu-id="b31f1-377">Você receberá uma mensagem de aviso que informa “, O Regression Suite Automation Tool requer o Selenium. Deseja baixá-lo e instalá-lo automaticamente?"</span><span class="sxs-lookup"><span data-stu-id="b31f1-377">You receive a warning message that states, "The Regression Suite Automation Tool requires Selenium, do you want to automatically download and install it now?"</span></span> <span data-ttu-id="b31f1-378">Selecione **Sim**.</span><span class="sxs-lookup"><span data-stu-id="b31f1-378">Select **Yes**.</span></span>

    ![Mensagem de aviso de que o Regression Suite Automation Tool requer o Selenium](./media/setup_rsa_tool_61.png)

3. <span data-ttu-id="b31f1-380">Selecione o botão **Configurações** (o símbolo de engrenagem) no canto superior direito e, em seguida, na caixa de diálogo que aparece, preencha os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="b31f1-380">Select the **Settings** button (the gear symbol) in the upper-right corner, and then, in the dialog box that appears, fill in the following fields:</span></span>

    - <span data-ttu-id="b31f1-381">**Url do Azure DevOps** – Insira o URL do seu projeto Azure DevOps, como, por exemplo, `https://yourAzureDevOpsUrlHere.visualStudio.com`.</span><span class="sxs-lookup"><span data-stu-id="b31f1-381">**Azure DevOps Url** – Enter the URL of your Azure DevOps project, such as `https://yourAzureDevOpsUrlHere.visualStudio.com`.</span></span>
    - <span data-ttu-id="b31f1-382">**Token de Acesso** – Insira o token de acesso que permite que a ferramenta conecte-se ao Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="b31f1-382">**Access Token** – Enter the access token that lets the tool connect to Azure DevOps.</span></span> <span data-ttu-id="b31f1-383">Use o token de acesso pessoal criado anteriormente neste tutorial.</span><span class="sxs-lookup"><span data-stu-id="b31f1-383">Use the personal access token that you created earlier in this tutorial.</span></span> <span data-ttu-id="b31f1-384">Para obter mais informações, consulte [Autenticar acesso com tokens de acesso pessoal](https://www.visualstudio.com/docs/setup-admin/team-services/use-personal-access-tokens-to-authenticate).</span><span class="sxs-lookup"><span data-stu-id="b31f1-384">For more information, see [Authenticate access with personal access tokens](https://www.visualstudio.com/docs/setup-admin/team-services/use-personal-access-tokens-to-authenticate).</span></span>
    - <span data-ttu-id="b31f1-385">**Nome do Projeto** – Selecione o nome do seu projeto do Azure DevOps .</span><span class="sxs-lookup"><span data-stu-id="b31f1-385">**Project Name** – Select the name of your Azure DevOps project.</span></span>
    - <span data-ttu-id="b31f1-386">**Plano de Teste** – Selecione o plano de teste do Azure DevOps que contém os casos de teste.</span><span class="sxs-lookup"><span data-stu-id="b31f1-386">**Test Plan** – Select the Azure DevOps test plan that contains your test cases.</span></span> <span data-ttu-id="b31f1-387">Para obter mais informações, consulte [Criar planos de teste e conjuntos de teste](https://www.visualstudio.com/docs/test/manual-exploratory-testing/getting-started/create-a-test-plan).</span><span class="sxs-lookup"><span data-stu-id="b31f1-387">For more information, see [Create test plans and test suites](https://www.visualstudio.com/docs/test/manual-exploratory-testing/getting-started/create-a-test-plan).</span></span> <span data-ttu-id="b31f1-388">Após selecionar um plano de teste, selecione **Conexão de Teste** para testar sua conexão ao Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="b31f1-388">After you select a test plan, select **Test Connection** to test your connection to Azure DevOps.</span></span>
    - <span data-ttu-id="b31f1-389">**Nome do host** – insira o nome do host do ambiente de teste, como **\<myaos\>.cloudax.dynamics.com**.</span><span class="sxs-lookup"><span data-stu-id="b31f1-389">**Hostname** – Enter the host name of the test environment, such as **\<myaos\>.cloudax.dynamics.com**.</span></span> <span data-ttu-id="b31f1-390">Não inclua o prefixo **https://** ou **http://**.</span><span class="sxs-lookup"><span data-stu-id="b31f1-390">Don't include the **https://** or **http://** prefix.</span></span>
    - <span data-ttu-id="b31f1-391">**Nome do host do SOAP** – Insira o nome do host do SOAP do ambiente de teste.</span><span class="sxs-lookup"><span data-stu-id="b31f1-391">**SOAP Hostname** – Enter the SOAP host name of the test environment.</span></span> <span data-ttu-id="b31f1-392">Geralmente, o nome do host do SOAP é igual ao nome do host, mas tem um sufixo **soap** .</span><span class="sxs-lookup"><span data-stu-id="b31f1-392">Typically, the SOAP host name is the same as the host name, but it has a **soap** suffix.</span></span> <span data-ttu-id="b31f1-393">Veja um exemplo: **\<myaos\>soap.cloudax.dynamics.com**.</span><span class="sxs-lookup"><span data-stu-id="b31f1-393">Here is an example: **\<myaos\>soap.cloudax.dynamics.com**.</span></span> <span data-ttu-id="b31f1-394">Não inclua o prefixo **https://** ou **http://**.</span><span class="sxs-lookup"><span data-stu-id="b31f1-394">Don't include the **https://** or **http://** prefix.</span></span>

        > [!NOTE]
        > <span data-ttu-id="b31f1-395">Para localizar o nome do host e o nome do host do SOAP, abra o Gerenciador do IIS, clique com o botão direito do mouse em **Sites \> AOSService** e, em seguida, selecione **Editar associações**.</span><span class="sxs-lookup"><span data-stu-id="b31f1-395">To find the host name and SOAP host name, open IIS Manager, right-click **Sites \> AOSService**, and then select **Edit bindings**.</span></span> <span data-ttu-id="b31f1-396">Os valores da coluna **Nome do Host** fornecem o nome do host e o nome do host do SOAP (o nome do host do SOAP tem o sufixo **soap** na URL).</span><span class="sxs-lookup"><span data-stu-id="b31f1-396">The values in the **Host Name** column give you the host name and SOAP host name (the SOAP host name has the suffix **soap** in the URL).</span></span>

        ![Nome do host e nome do host do SOAP na coluna Nome do Host](./media/setup_rsa_tool_63.png)

    - <span data-ttu-id="b31f1-398">**Nome do usuário administrador** – Insira o endereço de email de um usuário administrador no ambiente de teste.</span><span class="sxs-lookup"><span data-stu-id="b31f1-398">**Admin user name** – Enter the email address of an admin user in the test environment.</span></span>
    - <span data-ttu-id="b31f1-399">**Impressão digital** – Insira a impressão digital do certificado de autenticação, conforme descrito anteriormente neste tutorial.</span><span class="sxs-lookup"><span data-stu-id="b31f1-399">**Thumbprint** – Enter the thumbprint of the authentication certificate, as described earlier in this tutorial.</span></span>
    - <span data-ttu-id="b31f1-400">**Diretório de trabalho** – Especifique o local de pasta para armazenar arquivos de automação de teste, como arquivos de dados de teste do Excel.</span><span class="sxs-lookup"><span data-stu-id="b31f1-400">**Working directory** – Specify the folder location for storing test automation files, such as Excel test data files.</span></span> <span data-ttu-id="b31f1-401">Por exemplo, informe ou selecione **C:\\Temp\\RegressionTool**.</span><span class="sxs-lookup"><span data-stu-id="b31f1-401">For example, enter or select **C:\\Temp\\RegressionTool**.</span></span>

        > [!NOTE]
        > <span data-ttu-id="b31f1-402">Se o nome da pasta tiver espaços, a execução falhará porque a pasta não poderá ser encontrada.</span><span class="sxs-lookup"><span data-stu-id="b31f1-402">If the name of the folder has spaces, execution will fail because the folder can't be found.</span></span> <span data-ttu-id="b31f1-403">Este é um problema conhecido e deverá ser corrigido na versão mais recente da ferramenta.</span><span class="sxs-lookup"><span data-stu-id="b31f1-403">This issue is a known issue and should be fixed in the latest version of the tool.</span></span>

    - <span data-ttu-id="b31f1-404">**Navegador padrão** – Selecione **Internet Explorer** ou **Google Chrome**.</span><span class="sxs-lookup"><span data-stu-id="b31f1-404">**Default browser** – Select either **Internet Explorer** or **Google Chrome**.</span></span> <span data-ttu-id="b31f1-405">Certifique-se de que os drivers do navegador apropriados foram instalados.</span><span class="sxs-lookup"><span data-stu-id="b31f1-405">Make sure that the appropriate browser drivers have been installed.</span></span>
    - <span data-ttu-id="b31f1-406">**Testar tempo limite da execução** – Especifique o tempo limite, em minutos, para execuções de teste.</span><span class="sxs-lookup"><span data-stu-id="b31f1-406">**Test run timeout** – Specify the time-out period, in minutes, for test runs.</span></span> <span data-ttu-id="b31f1-407">Quando o tempo limite passar, todas as janelas ativas serão fechadas e os casos de teste pendentes falharão.</span><span class="sxs-lookup"><span data-stu-id="b31f1-407">When the time-out period elapses, all active windows are closed, and pending test cases fail.</span></span>
    - <span data-ttu-id="b31f1-408">**Testar tempo limite da ação** – Este campo controla o período, em minutos, para solicitações do servidor do ambiente do Finance and Operation.</span><span class="sxs-lookup"><span data-stu-id="b31f1-408">**Test action timeout** – This field controls the time-out period, in minutes, for Finance and Operation environment server requests.</span></span> <span data-ttu-id="b31f1-409">Geralmente, o valor padrão (2 minutos) deve ser suficiente.</span><span class="sxs-lookup"><span data-stu-id="b31f1-409">Usually, the default value (2 minutes) should be enough.</span></span> <span data-ttu-id="b31f1-410">Porém, para ambientes mais lentos, talvez você queira aumentar o valor, houver erros relacionados aos tempos limite.</span><span class="sxs-lookup"><span data-stu-id="b31f1-410">However, for slower environments, you might want to increase the value if errors that are related to time-outs occur.</span></span>
    - <span data-ttu-id="b31f1-411">**Nome da empresa** – Insira o nome da empresa a ser usada como a empresa padrão quando os arquivos de parâmetros do Excel forem criados.</span><span class="sxs-lookup"><span data-stu-id="b31f1-411">**Company name** – Enter the company name to use as your default company when Excel parameter files are created.</span></span> <span data-ttu-id="b31f1-412">Você pode alterar a empresa posteriormente, editando o arquivo de parâmetros do Excel.</span><span class="sxs-lookup"><span data-stu-id="b31f1-412">You can change the company later by editing the Excel parameter file.</span></span>

    ![Caixa de diálogo Configurações](./media/setup_rsa_tool_62.png)

4. <span data-ttu-id="b31f1-414">Selecione **Aplicar** para aplicar e salvar suas configurações.</span><span class="sxs-lookup"><span data-stu-id="b31f1-414">Select **Apply** to apply and save your settings.</span></span>

    <span data-ttu-id="b31f1-415">Para salvar suas configurações atuais em um arquivo de configuração em seu computador, selecione **Salvar como**.</span><span class="sxs-lookup"><span data-stu-id="b31f1-415">To save your current settings to a configuration file on your computer, select **Save as**.</span></span> <span data-ttu-id="b31f1-416">Para restaurar suas configurações de um arquivo de configuração em seu computador, selecione **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="b31f1-416">To restore your settings from a configuration file on your computer, select **Open**.</span></span>

5. <span data-ttu-id="b31f1-417">Selecione **Fechar** para fechar a caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="b31f1-417">Select **Close** to close the dialog box.</span></span>

### <a name="load-and-run-test-cases"></a><span data-ttu-id="b31f1-418">Carregar e executar casos de teste</span><span class="sxs-lookup"><span data-stu-id="b31f1-418">Load and run test cases</span></span>

1. <span data-ttu-id="b31f1-419">Selecione **Carregar** para carregar o plano de teste **Plano de Teste de RSAT** do projeto Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="b31f1-419">Select **Load** to load the **RSAT Test Plan** test plan from the Azure DevOps project.</span></span>

    ![Botão Carregar](./media/setup_rsa_tool_64.png)

2. <span data-ttu-id="b31f1-421">Selecione o caso de teste **Criar um novo produto** do conjunto de testes e selecione **Novo \> Gerar arquivos de Parâmetro e Execução de Teste**.</span><span class="sxs-lookup"><span data-stu-id="b31f1-421">Select the **Create a new product** test case from the test suite, and then select **New \> Generate Test Execution and Parameter files**.</span></span>

    ![Comando Gerar Arquivos de parâmetros e Execução de Teste no menu Novo](./media/setup_rsa_tool_65.png)

    <span data-ttu-id="b31f1-423">O arquivo de parâmetros do Excel é criado na pasta local especificada na configuração de RSAT (por exemplo, **C:\\Temp\\RegressionTool**).</span><span class="sxs-lookup"><span data-stu-id="b31f1-423">The Excel parameter file is created in the local folder that you specified in the RSAT configuration (for example, **C:\\Temp\\RegressionTool**).</span></span>

    ![Arquivo de parâmetro do Excel criado](./media/setup_rsa_tool_66.png)

3. <span data-ttu-id="b31f1-425">Se quiser salvar os arquivos de parâmetro, selecione **Carregar**.</span><span class="sxs-lookup"><span data-stu-id="b31f1-425">If you want to save the parameter files, select **Upload**.</span></span> <span data-ttu-id="b31f1-426">Os arquivos de automação de teste de todos os casos de teste selecionados são carregados para o Azure DevOps para uso futuro.</span><span class="sxs-lookup"><span data-stu-id="b31f1-426">Test automation files of all selected test cases are uploaded to Azure DevOps for future use.</span></span> <span data-ttu-id="b31f1-427">(Esses arquivos incluem os arquivos de parâmetro de teste do Excel).</span><span class="sxs-lookup"><span data-stu-id="b31f1-427">(These files include Excel test parameter files.)</span></span>

    <span data-ttu-id="b31f1-428">Dessa forma, você pode selecionar **Carregar** para carregar os arquivos de parâmetro (e arquivos de automação) do caso de teste diretamente do Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="b31f1-428">In this way, you can select **Load** to load the parameter files (and automation files) from the test case directly from Azure DevOps.</span></span> <span data-ttu-id="b31f1-429">Você não precisa gerar novamente os arquivos de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="b31f1-429">You don't have to regenerate the parameter files.</span></span> <span data-ttu-id="b31f1-430">Esta abordagem se tornará importante posteriormente, quando você quiser manter as alterações no arquivo de parâmetro e não quiser que elas sejam substituídas.</span><span class="sxs-lookup"><span data-stu-id="b31f1-430">This approach will become important later, when you want to keep the modifications in the parameter file and don't want them to be overwritten.</span></span>

4. <span data-ttu-id="b31f1-431">Para verificar se os arquivos de automação e os arquivos de parâmetros foram salvos no Azure DevOps, vá para o projeto Azure DevOps, selecione **Quadros \> Itens de trabalho** e selecione o caso de teste **Criar um novo produto**.</span><span class="sxs-lookup"><span data-stu-id="b31f1-431">To verify that the automation files and parameter files are saved to Azure DevOps, go to the Azure DevOps project, select **Boards \> Work Items**, and select the **Create a new product** test case.</span></span> <span data-ttu-id="b31f1-432">Na guia **Anexos** , você deverá visualizar quatro arquivos:</span><span class="sxs-lookup"><span data-stu-id="b31f1-432">On the **Attachments** tab, you should see four files:</span></span>

    - <span data-ttu-id="b31f1-433">**.cs** – C\# arquivo de automação</span><span class="sxs-lookup"><span data-stu-id="b31f1-433">**.cs** – C\# automation file</span></span>
    - <span data-ttu-id="b31f1-434">**.dll** – Arquivo de automação compilado como uma montagem</span><span class="sxs-lookup"><span data-stu-id="b31f1-434">**.dll** – Compiled automation file as an assembly</span></span>
    - <span data-ttu-id="b31f1-435">**.xlsx** – Arquivo de parâmetros do Excel</span><span class="sxs-lookup"><span data-stu-id="b31f1-435">**.xlsx** – Excel parameter file</span></span>
    - <span data-ttu-id="b31f1-436">**.xml** – arquivo de gravação</span><span class="sxs-lookup"><span data-stu-id="b31f1-436">**.xml** – Recording file</span></span>

    ![Arquivos na guia Anexos](./media/setup_rsa_tool_67.png)

5. <span data-ttu-id="b31f1-438">Selecione o caso de teste a ser executado e, em seguida, **Executar**.</span><span class="sxs-lookup"><span data-stu-id="b31f1-438">Select the test case to run, and then select **Run**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b31f1-439">Antes de executar os casos de teste, se estiver usando o Internet Explorer como o navegador, certifique-se de que a resolução da área de trabalho está definida como **100%** em **Configurações de Vídeo do Windows \> Ajustar escala e layout**.</span><span class="sxs-lookup"><span data-stu-id="b31f1-439">Before you run test cases, if you're using Internet Explorer as the browser, make sure that your desktop resolution is set to **100%** at **Windows Display settings \> Scale and layout**.</span></span> <span data-ttu-id="b31f1-440">Se você não puder alterar essa configuração em uma máquina virtual (VM), altere-a no cliente (laptop) do qual você está tentando acessar a VM.</span><span class="sxs-lookup"><span data-stu-id="b31f1-440">If you can't change this setting on a virtual machine (VM), change it on the client (laptop) that you're trying to access the VM from.</span></span> <span data-ttu-id="b31f1-441">As configurações da resolução serão então herdadas pelas configurações de exibição da VM.</span><span class="sxs-lookup"><span data-stu-id="b31f1-441">The resolution settings will then be inherited by the VM display settings.</span></span>

    ![Resolução da área de trabalho definida como 100%](./media/setup_rsa_tool_68.png)

6. <span data-ttu-id="b31f1-443">Se os drivers do navegador não estiverem instalados no sistema, você receberá uma mensagem de aviso que informará, "Esta operação requer o driver do \<browser name\>.</span><span class="sxs-lookup"><span data-stu-id="b31f1-443">If the browser drivers aren't installed in the system, you receive a warning message that states, "This operation requires the \<browser name\> driver.</span></span> <span data-ttu-id="b31f1-444">Deseja baixá-lo e instalá-lo automaticamente?"</span><span class="sxs-lookup"><span data-stu-id="b31f1-444">Do you want to automatically downloads and install it now?"</span></span> <span data-ttu-id="b31f1-445">Selecione **Sim**.</span><span class="sxs-lookup"><span data-stu-id="b31f1-445">Select **Yes**.</span></span>

    ![Mensagem de aviso do Internet Explorer](./media/setup_rsa_tool_69.png)

    ![Mensagem de aviso do Chrome](./media/setup_rsa_tool_70.png)

    > [!NOTE]
    > <span data-ttu-id="b31f1-448">Se estiver usando o Chrome como o navegador e receber uma mensagem de erro que informa que a sessão não foi criada porque a versão do Chrome não está correta, baixe o driver do Chrome mais recente do <http://chromedriver.chromium.org/downloads> para a pasta **C:\\Arquivos de Programas (x86)\\Regression Suite Automation Tool\\Common\\External\\Selenium**.</span><span class="sxs-lookup"><span data-stu-id="b31f1-448">If you're using Chrome as the browser and receive an error message that states that the session wasn't created because the Chrome version isn't correct, download the latest Chrome driver from <http://chromedriver.chromium.org/downloads> to the **C:\\Program Files (x86)\\Regression Suite Automation Tool\\Common\\External\\Selenium** folder.</span></span>

    ![Mensagem de erro do Chrome](./media/setup_rsa_tool_71.png)

    <span data-ttu-id="b31f1-450">O caso de teste é executado e o campo **Resultado** é atualizado.</span><span class="sxs-lookup"><span data-stu-id="b31f1-450">The test case is run, and the **Result** field is updated.</span></span>

    ![Campo Resultado Atualizado](./media/setup_rsa_tool_72.png)

    <span data-ttu-id="b31f1-452">Se você seguiu este tutorial como está escrito, o caso de teste **Criar um novo produto** falhará porque a gravação da tarefa para criar um produto salvou o nome do produto como um valor codificado.</span><span class="sxs-lookup"><span data-stu-id="b31f1-452">If you've followed this tutorial as it's written, the **Create a new product** test case will fail, because the task recording for creating a product saved the product name as a hard-coded value.</span></span> <span data-ttu-id="b31f1-453">Se você executar novamente o mesmo caso de teste, deverá receber uma mensagem de erro, porque o produto já existe.</span><span class="sxs-lookup"><span data-stu-id="b31f1-453">If you rerun the same test case, you should receive an error message, because the product already exists.</span></span>

    ![Campo Resultado definido como Com Falha](./media/setup_rsa_tool_72.png)

### <a name="view-the-test-results"></a><span data-ttu-id="b31f1-455">Exibir os resultados do teste</span><span class="sxs-lookup"><span data-stu-id="b31f1-455">View the test results</span></span>

1. <span data-ttu-id="b31f1-456">Clique duas vezes no caso de teste com falha.</span><span class="sxs-lookup"><span data-stu-id="b31f1-456">Double-click the failed test case.</span></span>

    <span data-ttu-id="b31f1-457">Você receberá uma mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="b31f1-457">You receive an error message.</span></span>

    ![Mensagem de erro](./media/setup_rsa_tool_73.png)

2. <span data-ttu-id="b31f1-459">Selecione **Detalhes** para exibir a mensagem de erro inteira.</span><span class="sxs-lookup"><span data-stu-id="b31f1-459">Select **Details** to view the whole error message.</span></span>

    ![Mensagem de erro inteira](./media/setup_rsa_tool_74.png)

3. <span data-ttu-id="b31f1-461">Para exibir uma versão detalhada da mensagem de erro no Azure DevOps, selecione **Abrir no Azure DevOps**.</span><span class="sxs-lookup"><span data-stu-id="b31f1-461">To view a detailed version of the error message in Azure DevOps, select **Open in Azure DevOps**.</span></span> <span data-ttu-id="b31f1-462">No Azure DevOps, você pode exibir o status do caso de teste e a mensagem de erro detalhada.</span><span class="sxs-lookup"><span data-stu-id="b31f1-462">In Azure DevOps, you can view the status of the test case and the detailed error message.</span></span>

    ![Mensagem de erro detalhada no Azure DevOps](./media/setup_rsa_tool_75.png)

4. <span data-ttu-id="b31f1-464">Para exibir os resultados de teste diretamente no projeto do Azure DevOps , vá para **Planos de Teste \> Planos de Teste \> Execuções**.</span><span class="sxs-lookup"><span data-stu-id="b31f1-464">To view the test results directly in the Azure DevOps project, go to **Test Plans \> Test Plans \> Runs**.</span></span> <span data-ttu-id="b31f1-465">Clique duas vezes na execução do teste na qual você deseja ver mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="b31f1-465">Double-click the test run that you want to see more details for.</span></span>

    ![Lista de execuções de testes no Azure DevOps](./media/setup_rsa_tool_76.png)

5. <span data-ttu-id="b31f1-467">A guia **Resumo de execução** indica que o caso de teste falhou, mas não fornece a mensagem de erro real.</span><span class="sxs-lookup"><span data-stu-id="b31f1-467">The **Run summary** tab indicates that the test case failed, but it doesn't provide the actual error message.</span></span> <span data-ttu-id="b31f1-468">Para exibir a mensagem de erro detalhada, selecione a guia **Resultados do teste**.</span><span class="sxs-lookup"><span data-stu-id="b31f1-468">To view the detailed error message, select the **Test results** tab.</span></span>

    ![Guia Resumo de execução](./media/setup_rsa_tool_77.png)

    <span data-ttu-id="b31f1-470">A guia **Resultados de teste** fornece informações do caso de teste, junto com o resultado a mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="b31f1-470">The **Test results** tab provides the test case information, together with the outcome and the error message.</span></span>

    ![Guia Resultados do teste](./media/setup_rsa_tool_78.png)

6. <span data-ttu-id="b31f1-472">Clique duas vezes no registro relevante para exibir a mensagem de erro detalhada.</span><span class="sxs-lookup"><span data-stu-id="b31f1-472">Double-click the relevant record to view the detailed error message.</span></span>

    ![Mensagem de erro detalhada](./media/setup_rsa_tool_79.png)

    > [!NOTE]
    > <span data-ttu-id="b31f1-474">Todas as mensagens de erro também estão disponíveis localmente em **C:\\Usuários\\\$YourUserName\\AppData\\Roaming\\regressionTool\\errormsg-.txt**.</span><span class="sxs-lookup"><span data-stu-id="b31f1-474">All error messages are also available locally in **C:\\Users\\\$YourUserName\\AppData\\Roaming\\regressionTool\\errormsg-.txt**.</span></span>

7. <span data-ttu-id="b31f1-475">Também é possível exportar os resultados de execução do teste do nível do plano de teste, selecionando **Exportar**.</span><span class="sxs-lookup"><span data-stu-id="b31f1-475">You can also export the test run results from the test plan level by selecting **Export**.</span></span>

    ![Exportando um plano de teste](./media/setup_rsa_tool_80.png)

### <a name="modify-the-excel-parameter-file"></a><span data-ttu-id="b31f1-477">Modifique o arquivo de parâmetro do Excel</span><span class="sxs-lookup"><span data-stu-id="b31f1-477">Modify the Excel parameter file</span></span>

1. <span data-ttu-id="b31f1-478">Abra o RSAT.</span><span class="sxs-lookup"><span data-stu-id="b31f1-478">Open RSAT.</span></span>
2. <span data-ttu-id="b31f1-479">Selecione o caso de teste e, em seguida, selecione **Editar** para abrir o arquivo de parâmetro do Excel.</span><span class="sxs-lookup"><span data-stu-id="b31f1-479">Select the test case, and then select **Edit** to open the Excel parameter file.</span></span>

    <span data-ttu-id="b31f1-480">Na folha **EcoResProductCreate**, observe que o valor do campo **Número do produto** está codificado.</span><span class="sxs-lookup"><span data-stu-id="b31f1-480">On the **EcoResProductCreate** sheet, notice that the value of the **Product number** field is hard-coded.</span></span> <span data-ttu-id="b31f1-481">Você deve atualizar este campo para um novo número de produto antes de executar o caso de teste novamente.</span><span class="sxs-lookup"><span data-stu-id="b31f1-481">You must update this field to a new product number before you run the test case again.</span></span>

3. <span data-ttu-id="b31f1-482">Para gerar um número exclusivo de produto para cada execução sem precisar reabrir o arquivo de parâmetros do Excel e atualizar manualmente o número do produto todas as vezes, use a seguinte fórmula do Excel.</span><span class="sxs-lookup"><span data-stu-id="b31f1-482">To generate a unique product number for each run without having to reopen the Excel parameter file and manually update the product number every time, use the following Excel formula.</span></span>

    ```vba
    ="RSAT_"&TEXT(NOW(),"yyymmddhhmm")
    ```

    > [!NOTE]
    > <span data-ttu-id="b31f1-483">Além da guia **Geral**, o arquivo de parâmetros do Excel contém uma guia de dados para cada página do formulário que o caso de teste visita.</span><span class="sxs-lookup"><span data-stu-id="b31f1-483">In addition to the **General** tab, the Excel parameter file contains a data tab for every form page the test case visits.</span></span>

    ![Campo Número do produto](./media/setup_rsa_tool_81.png)

4. <span data-ttu-id="b31f1-485">Selecione **Salvar** e feche a pasta de trabalho do Excel.</span><span class="sxs-lookup"><span data-stu-id="b31f1-485">Select **Save**, and then close the Excel workbook.</span></span>
5. <span data-ttu-id="b31f1-486">Selecione **Carregar** para salvar o arquivo de parâmetros do Excel para o Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="b31f1-486">Select **Upload** to save the Excel parameter file to Azure DevOps.</span></span>

    ![Mensagem de carregamento bem-sucedido](./media/setup_rsa_tool_82.png)

    > [!NOTE]
    > <span data-ttu-id="b31f1-488">Para executar casos de teste em um contexto de usuário específico, informe o ID do e-mail do usuário no campo **Testar Usuário** na guia **Geral** do arquivo de parâmetros do Excel.</span><span class="sxs-lookup"><span data-stu-id="b31f1-488">To run test cases in a specific user context, enter the user's email ID in the **Test User** field on the **General** tab of the Excel parameter file.</span></span> <span data-ttu-id="b31f1-489">Na versão mais recente do RSAT, o layout dos campos no arquivo de parâmetros do Excel foi atualizado, mas o conceito permanece o mesmo.</span><span class="sxs-lookup"><span data-stu-id="b31f1-489">In the latest version of RSAT, the layout of the fields in the Excel parameter file has been updated, but the concept remains the same.</span></span>
    >
    > ![Campo Testar Usuário](./media/setup_rsa_tool_83.png)

### <a name="validate-the-results"></a><span data-ttu-id="b31f1-491">Validar os resultados</span><span class="sxs-lookup"><span data-stu-id="b31f1-491">Validate the results</span></span>

- <span data-ttu-id="b31f1-492">Selecione **Executar** para executar novamente o caso de teste e verificar se o caso de teste foi aprovado.</span><span class="sxs-lookup"><span data-stu-id="b31f1-492">Select **Run** to rerun the test case, and verify that the test case has passed.</span></span> <span data-ttu-id="b31f1-493">Você pode exibir os resultados de teste, conforme descrito na seção [Exibir os resultados de teste](#view-the-test-results).</span><span class="sxs-lookup"><span data-stu-id="b31f1-493">You can view the test results as described in the [View the test results](#view-the-test-results) section.</span></span>

    ![Campo Resultado definido como Aprovado](./media/setup_rsa_tool_84.png)

### <a name="chaining-of-test-cases"></a><span data-ttu-id="b31f1-495">Encadeamento dos casos de testes</span><span class="sxs-lookup"><span data-stu-id="b31f1-495">Chaining of test cases</span></span>

<span data-ttu-id="b31f1-496">Um recurso-chave de RSAT é o encadeamento dos casos de teste (isto é, a capacidade de um teste aprovar valores para outros testes).</span><span class="sxs-lookup"><span data-stu-id="b31f1-496">One key feature of RSAT is the chaining of test cases (that is, the capability of a test to pass values to other tests).</span></span> <span data-ttu-id="b31f1-497">Os casos de teste são executados de acordo com sua ordem definida no plano de teste do Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="b31f1-497">Test cases are run according to their defined order in the Azure DevOps test plan.</span></span> <span data-ttu-id="b31f1-498">(Essa ordem também pode ser atualizada na própria ferramenta de teste.) Portanto, se você quiser passar variáveis de um caso de teste para outro, é muito importante que os testes estejam na ordem correta.</span><span class="sxs-lookup"><span data-stu-id="b31f1-498">(This order can also be updated in the test tool itself.) Therefore, if you want to pass variables from one test case to another, it's very important that the tests be in the correct order.</span></span>

<span data-ttu-id="b31f1-499">Nesta seção, você criará uma variável salva no primeiro caso de teste, criará um segundo caso de teste e transmitirá a variável salva do primeiro caso de teste para o segundo caso de teste.</span><span class="sxs-lookup"><span data-stu-id="b31f1-499">In this section, you will create a saved variable in the first test case, create a second test case, and pass the saved variable from the first test case to the second test case.</span></span> <span data-ttu-id="b31f1-500">Em seguida, você executará os casos de teste como um caso de teste encadeado no RSAT.</span><span class="sxs-lookup"><span data-stu-id="b31f1-500">You will then run the test cases as a chained test case in RSAT.</span></span>

#### <a name="modify-an-existing-task-recording-to-create-a-saved-variable"></a><span data-ttu-id="b31f1-501">Modificar uma gravação de tarefas existente para criar uma variável salva</span><span class="sxs-lookup"><span data-stu-id="b31f1-501">Modify an existing task recording to create a saved variable</span></span>

1. <span data-ttu-id="b31f1-502">Abra o cliente.</span><span class="sxs-lookup"><span data-stu-id="b31f1-502">Open the client.</span></span>
2. <span data-ttu-id="b31f1-503">Selecione o botão **Configurações** (o símbolo da engrenagem) e depois, selecione **Gravador de tarefas**.</span><span class="sxs-lookup"><span data-stu-id="b31f1-503">Select the **Settings** button (the gear symbol), and then select **Task recorder**.</span></span>
3. <span data-ttu-id="b31f1-504">Selecione **Editar Gravação**.</span><span class="sxs-lookup"><span data-stu-id="b31f1-504">Select **Edit Recording**.</span></span>

    ![Botão Editar Gravação](./media/setup_rsa_tool_85.png)

4. <span data-ttu-id="b31f1-506">Selecione **Abrir do Lifecycle Services**.</span><span class="sxs-lookup"><span data-stu-id="b31f1-506">Select **Open from Lifecycle Services**.</span></span>

    ![Botão Abrir do Lifecycle Services](./media/setup_rsa_tool_86.png)

5. <span data-ttu-id="b31f1-508">Escolha **Selecione a biblioteca Lifecycle Services**.</span><span class="sxs-lookup"><span data-stu-id="b31f1-508">Select **Select the Lifecycle Services library**.</span></span>

    ![Botão Selecione a biblioteca Lifecycle Services](./media/setup_rsa_tool_87.png)

    <span data-ttu-id="b31f1-510">As bibliotecas de BPM são carregadas do LCS.</span><span class="sxs-lookup"><span data-stu-id="b31f1-510">BPM libraries are loaded from LCS.</span></span>

    ![Carregar bibliotecas de BPM](./media/setup_rsa_tool_88.png)

6. <span data-ttu-id="b31f1-512">Depois que as bibliotecas de BPM forem carregadas do LCS, selecione a biblioteca **RSAT** de BPM e o processo de negócios **Criar um novo produto** que tem a gravação de tarefas associada a ele.</span><span class="sxs-lookup"><span data-stu-id="b31f1-512">After the BPM libraries are loaded from LCS, select the **RSAT** BPM library and the **Create a new product** business process that the task recording was associated with.</span></span> <span data-ttu-id="b31f1-513">Em seguida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="b31f1-513">Then select **OK**.</span></span>

    ![Selecionando uma biblioteca de BPM e um processo de negócios](./media/setup_rsa_tool_89.png)

7. <span data-ttu-id="b31f1-515">O nome da gravação de tarefas apropriada é inserido no campo **Nome da gravação**.</span><span class="sxs-lookup"><span data-stu-id="b31f1-515">The name of the appropriate task recording is entered in the **Recording name** field.</span></span> <span data-ttu-id="b31f1-516">Selecione **Iniciar**.</span><span class="sxs-lookup"><span data-stu-id="b31f1-516">Select **Start**.</span></span>

    ![Nome da gravação de tarefas no campo Nome da gravação](./media/setup_rsa_tool_90.png)

8. <span data-ttu-id="b31f1-518">Vá para **Gerenciamento de informações do produto \> Produtos** e selecione **Novo** para abrir a página onde a gravação de tarefas original, **Criar um produto**, foi gravada.</span><span class="sxs-lookup"><span data-stu-id="b31f1-518">Go to **Product information management \> Products**, and select **New** to open the page where the original task recording, **Create a product**, was recorded.</span></span>
9. <span data-ttu-id="b31f1-519">Selecione **Inserir etapa**.</span><span class="sxs-lookup"><span data-stu-id="b31f1-519">Select **Insert step**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b31f1-520">A nova etapa é inserida **depois** da etapa selecionada no painel.</span><span class="sxs-lookup"><span data-stu-id="b31f1-520">The new step is inserted **after** the step that you selected in the pane.</span></span>

    ![Botão Inserir etapa](./media/setup_rsa_tool_91.png)

10. <span data-ttu-id="b31f1-522">Clique com o botão direito do mouse no campo **Número do produto** e selecione **Gravador de tarefas \> Copiar**.</span><span class="sxs-lookup"><span data-stu-id="b31f1-522">Right-click the **Product number** field, and then select **Task recorder \> Copy**.</span></span>

    ![Comando Copiar](./media/setup_rsa_tool_92.png)

11. <span data-ttu-id="b31f1-524">Uma nova etapa será adicionado ao painel.</span><span class="sxs-lookup"><span data-stu-id="b31f1-524">A new step is added in the pane.</span></span> <span data-ttu-id="b31f1-525">Anote o valor do campo **Número do produto**, porque você precisará dele posteriormente.</span><span class="sxs-lookup"><span data-stu-id="b31f1-525">Make a note of the value in the **Product number** field, because you will need it later.</span></span>

    ![Nova etapa adicionada](./media/setup_rsa_tool_93.png)

12. <span data-ttu-id="b31f1-527">Selecione **Edição concluída**.</span><span class="sxs-lookup"><span data-stu-id="b31f1-527">Select **Done editing**.</span></span>
13. <span data-ttu-id="b31f1-528">Selecione **Salvar no Lifecycle Services** e associe a nova gravação de tarefas à mesma biblioteca de BPM e ao processo de negócios ao qual a gravação de tarefa original estava associada.</span><span class="sxs-lookup"><span data-stu-id="b31f1-528">Select **Save to Lifecycle Services**, and associate the new task recording with the same BPM library and business process that the original task recording was associated with.</span></span> <span data-ttu-id="b31f1-529">Para obter mais informações, consulte a seção [Criar uma gravação de tarefas e salvá-la na biblioteca do BPM](#create-a-task-recording-and-save-it-to-the-bpm-library).</span><span class="sxs-lookup"><span data-stu-id="b31f1-529">For more information, see the [Create a task recording and save it to the BPM library](#create-a-task-recording-and-save-it-to-the-bpm-library) section.</span></span>
14. <span data-ttu-id="b31f1-530">Vá para a biblioteca BPM e selecione **Sincronizar casos de teste** para substituir a gravação de tarefas que está vinculada ao caso de teste no Azure DevOps, conforme descrito na seção [Testar a sincronização do BPM para o Azure DevOps](#test-the-synchronization-from-bpm-to-azure-devops).</span><span class="sxs-lookup"><span data-stu-id="b31f1-530">Go to the BPM library, and select **Sync testcases** to overwrite the task recording that is attached to the test case in Azure DevOps, as described in the [Test the synchronization from BPM to Azure DevOps](#test-the-synchronization-from-bpm-to-azure-devops) section.</span></span>
15. <span data-ttu-id="b31f1-531">Abra o RSAT e selecione **Carregar** para recarregar todos os casos de teste no conjunto de testes.</span><span class="sxs-lookup"><span data-stu-id="b31f1-531">Open RSAT, and select **Load** to reload all the test cases in the test suite.</span></span> <span data-ttu-id="b31f1-532">Você deve gerar novamente os arquivos de parâmetro e automação para o caso de teste apropriado, selecionando o caso de teste e **Novo \> Gerar Arquivos de parâmetros e Execução de Teste**, conforme descrito na seção [Carregar e executar casos de teste](#load-and-run-test-cases).</span><span class="sxs-lookup"><span data-stu-id="b31f1-532">You must regenerate the automation and parameter files for the appropriate test case by selecting the test case and then selecting **New \> Generate Test Execution and Parameter files**, as described in the [Load and run test cases](#load-and-run-test-cases) section.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b31f1-533">Se o arquivo de parâmetros do Excel ficou aberto, a regeneração falhará.</span><span class="sxs-lookup"><span data-stu-id="b31f1-533">If the Excel parameter file was left open, regeneration will fail.</span></span> <span data-ttu-id="b31f1-534">Portanto, certifique-se de que o arquivo de parâmetros do Excel para o caso de teste está fechado antes de gerar o novo arquivo de parâmetros do Excel.</span><span class="sxs-lookup"><span data-stu-id="b31f1-534">Therefore, make sure that the Excel parameter file for the test case is closed before you generate the new Excel parameter file.</span></span>

16. <span data-ttu-id="b31f1-535">Selecione **Editar** para abrir o novo arquivo de parâmetros do Excel.</span><span class="sxs-lookup"><span data-stu-id="b31f1-535">Select **Edit** to open the new Excel parameter file.</span></span> <span data-ttu-id="b31f1-536">Você verá uma nova entrada **Variável salva** na linha 9.</span><span class="sxs-lookup"><span data-stu-id="b31f1-536">You will see a new **Saved variable** entry on line 9.</span></span> <span data-ttu-id="b31f1-537">Esta variável, **{{EcoResProductCreate\_Identification\_ProductNumber\_Copy}}** é salva no arquivo XML de gravação de tarefas e pode ser usada nos testes subsequentes.</span><span class="sxs-lookup"><span data-stu-id="b31f1-537">This variable, **{{EcoResProductCreate\_Identification\_ProductNumber\_Copy}}**, is saved in the task recording's XML file and can be used in subsequent tests.</span></span>

    ![Entrada de variável salva](./media/setup_rsa_tool_94.png)

#### <a name="create-a-new-test-case"></a><span data-ttu-id="b31f1-539">Criar um novo caso de teste</span><span class="sxs-lookup"><span data-stu-id="b31f1-539">Create a new test case</span></span>

1. <span data-ttu-id="b31f1-540">Vá para biblioteca **RSAT** do BPM.</span><span class="sxs-lookup"><span data-stu-id="b31f1-540">Go to the **RSAT** BPM library.</span></span>
2. <span data-ttu-id="b31f1-541">Selecione o processo **Processo de Negócios Suporte de Exemplo** e, em seguida, no lado direito selecione **Modo de edição**.</span><span class="sxs-lookup"><span data-stu-id="b31f1-541">Select the **Sample Support Business Process** process, and then, on the right, select **Edit mode**.</span></span>
3. <span data-ttu-id="b31f1-542">Altere o valor do campo **Nome** e **Descrição** para **Liberar um produto**.</span><span class="sxs-lookup"><span data-stu-id="b31f1-542">Change the value of both the **Name** field and the **Description** field to **Release a product**.</span></span> <span data-ttu-id="b31f1-543">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="b31f1-543">Then select **Save**.</span></span>

    ![Nome e descrição alterados para Liberar um produto](./media/setup_rsa_tool_95.png)

#### <a name="create-a-new-task-recording-that-has-a-validate-function"></a><span data-ttu-id="b31f1-545">Criar uma nova gravação de tarefas que tenha a função Validar</span><span class="sxs-lookup"><span data-stu-id="b31f1-545">Create a new task recording that has a Validate function</span></span>

- <span data-ttu-id="b31f1-546">Criar uma gravação de tarefas para liberar o produto que foi criado anteriormente para a entidade legal USRT.</span><span class="sxs-lookup"><span data-stu-id="b31f1-546">Create a task recording to release the product that was created earlier to the USRT legal entity.</span></span> <span data-ttu-id="b31f1-547">Para obter mais informações, consulte a seção [Criar uma gravação de tarefas e salvá-la na biblioteca do BPM](#create-a-task-recording-and-save-it-to-the-bpm-library).</span><span class="sxs-lookup"><span data-stu-id="b31f1-547">For more information, see the [Create a task recording and save it to the BPM library](#create-a-task-recording-and-save-it-to-the-bpm-library) section.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b31f1-548">Para casos de testes encadeados, sempre recomendamos que você localize ou filtre o registro que precisa *digitando manualmente o valor do campo*.</span><span class="sxs-lookup"><span data-stu-id="b31f1-548">For chained test cases, we always recommend that you find or filter for the record that you require by *manually typing the value of the field*.</span></span> <span data-ttu-id="b31f1-549">Dessa forma, a ferramenta pode determinar o registro de que a ação deve ser tomada, no caso de teste subsequente.</span><span class="sxs-lookup"><span data-stu-id="b31f1-549">In that way, the tool can determine the record that the action must be taken against in the subsequent test case.</span></span>

    ![Nova gravação de tarefas que tem uma função Validar](./media/setup_rsa_tool_96.png)

    <span data-ttu-id="b31f1-551">Como mostra a ilustração anterior, após o produto ser encontrado usando o Filtro Rápido, mas antes de selecionar **Liberar produtos**, você valida o valor do campo **Número do produto** para certificar-se de que o ID do produto é o ID do produto que foi criado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="b31f1-551">As the preceding illustration shows, after the product is found by using the Quick Filter, but before you select **Release products**, you validate the value of the **Product number** field to make sure that the product ID is the product ID that was created earlier.</span></span> <span data-ttu-id="b31f1-552">Para validar o valor, clique com o botão direito no campo **Número do produto** e, em seguida, selecione **Gravador de tarefas \> Validar \> Valor Atual**.</span><span class="sxs-lookup"><span data-stu-id="b31f1-552">To validate the value, right-click the **Product number** field, and then select **Task recorder \> Validate \> Current Value**.</span></span>

    ![Validando o valor atual](./media/setup_rsa_tool_97.png)

#### <a name="save-the-task-recording-to-bpm"></a><span data-ttu-id="b31f1-554">Salve a gravação de tarefas para o BPM</span><span class="sxs-lookup"><span data-stu-id="b31f1-554">Save the task recording to BPM</span></span>

1. <span data-ttu-id="b31f1-555">Depois que a gravação de tarefas for concluída, selecione **Salvar no Lifecycle Services**.</span><span class="sxs-lookup"><span data-stu-id="b31f1-555">After the task recording is completed, select **Save to Lifecycle Services**.</span></span>

    ![Salvar a gravação de tarefas concluídas no Lifecycle Services](./media/setup_rsa_tool_98.png)

2. <span data-ttu-id="b31f1-557">As informações da biblioteca são carregadas do LCS.</span><span class="sxs-lookup"><span data-stu-id="b31f1-557">Library information is loaded from LCS.</span></span>

    ![Carregar informações da biblioteca do LCS](./media/setup_rsa_tool_99.png)

3. <span data-ttu-id="b31f1-559">Selecione a biblioteca do BPM para associar à gravação de tarefas.</span><span class="sxs-lookup"><span data-stu-id="b31f1-559">Select the BPM library to associate the task recording with.</span></span> <span data-ttu-id="b31f1-560">Para este tutorial, selecione a biblioteca **RSAT** do BPM que foi criada anteriormente e o processo de negócios **Liberar um produto**.</span><span class="sxs-lookup"><span data-stu-id="b31f1-560">For this tutorial, select the **RSAT** BPM library that was created earlier and the **Release a product** business process under it.</span></span> <span data-ttu-id="b31f1-561">Em seguida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="b31f1-561">Then select **OK**.</span></span>

#### <a name="sync-bpm-to-azure-devops"></a><span data-ttu-id="b31f1-562">Sincronizar BPM ao Azure DevOps</span><span class="sxs-lookup"><span data-stu-id="b31f1-562">Sync BPM to Azure DevOps</span></span>

1. <span data-ttu-id="b31f1-563">Vá para a biblioteca BPM e abra a biblioteca **RSAT**.</span><span class="sxs-lookup"><span data-stu-id="b31f1-563">Go to the BPM library, and open the **RSAT** library.</span></span>
2. <span data-ttu-id="b31f1-564">Selecione **Sincronização de VSTS** e, em seguida, **Sincronizar casos de teste**.</span><span class="sxs-lookup"><span data-stu-id="b31f1-564">Select **VSTS sync** and then **Sync test cases**.</span></span> <span data-ttu-id="b31f1-565">Para obter mais informações, consulte a seção [Testar a sincronização do BPM para o Azure DevOps](#test-the-synchronization-from-bpm-to-azure-devops).</span><span class="sxs-lookup"><span data-stu-id="b31f1-565">For more information, see the [Test the synchronization from BPM to Azure DevOps](#test-the-synchronization-from-bpm-to-azure-devops) section.</span></span>

    <span data-ttu-id="b31f1-566">Depois que a sincronização for concluída, o novo item de trabalho e o caso de teste correspondente para o processo de negócios **Liberar um produto** aparece no Azure DevOps em **Quadros \> Itens de Trabalho**.</span><span class="sxs-lookup"><span data-stu-id="b31f1-566">After the synchronization is completed, the new work item and the corresponding test case for the **Release a product** business process appear in Azure DevOps at **Boards \> Work Items**.</span></span>

#### <a name="add-the-new-test-case-to-the-existing-test-suite"></a><span data-ttu-id="b31f1-567">Adicione o novo caso de teste ao conjunto de testes existente</span><span class="sxs-lookup"><span data-stu-id="b31f1-567">Add the new test case to the existing test suite</span></span>

1. <span data-ttu-id="b31f1-568">Vá para **Planos de teste \> Planos de teste** e selecione o **Plano de Teste de RSAT**.</span><span class="sxs-lookup"><span data-stu-id="b31f1-568">Go to **Test plans \> Test plans**, and select the **RSAT Test Plan** plan.</span></span>
2. <span data-ttu-id="b31f1-569">Selecione **Adicionar existente**.</span><span class="sxs-lookup"><span data-stu-id="b31f1-569">Select **Add existing**.</span></span>
3. <span data-ttu-id="b31f1-570">Na página **Adicionar casos de teste ao conjunto**, selecione **Executar consulta**.</span><span class="sxs-lookup"><span data-stu-id="b31f1-570">On the **Add test cases to suite** page, select **Run query**.</span></span>
4. <span data-ttu-id="b31f1-571">Selecione o novo caso de teste que foi criado para **Liberar um produto** e selecione **Adicionar casos de teste** no canto inferior direito da página (este botão não é mostrado na ilustração a seguir).</span><span class="sxs-lookup"><span data-stu-id="b31f1-571">Select the new test case that was created for **Release a product**, and then select **Add test cases** in the lower-right corner of the page (this button isn't shown in the following illustration).</span></span>

    ![Adicione os casos de teste á página do conjunto](./media/setup_rsa_tool_100.png)

    <span data-ttu-id="b31f1-573">O conjunto de testes agora tem dois casos de teste.</span><span class="sxs-lookup"><span data-stu-id="b31f1-573">The test suite now has two test cases.</span></span>

    ![Dois casos de teste no conjunto de testes](./media/setup_rsa_tool_101.png)

#### <a name="load-test-cases-into-rsat"></a><span data-ttu-id="b31f1-575">Carregar casos de teste no RSAT</span><span class="sxs-lookup"><span data-stu-id="b31f1-575">Load test cases into RSAT</span></span>

1. <span data-ttu-id="b31f1-576">Abra o RSAT e selecione **Carregar**.</span><span class="sxs-lookup"><span data-stu-id="b31f1-576">Open RSAT, and select **Load**.</span></span>
2. <span data-ttu-id="b31f1-577">Os casos de testes são carregados e você recebe um aviso que informa, "Esta ação substituirá os arquivos de dados de teste do Excel, as alterações locais serão perdidas.</span><span class="sxs-lookup"><span data-stu-id="b31f1-577">The test cases are loaded, and you receive a warning that states, "This action will overwrite Excel test data files, local changes will be lost.</span></span> <span data-ttu-id="b31f1-578">Deseja continuar?"</span><span class="sxs-lookup"><span data-stu-id="b31f1-578">Do you want to proceed?"</span></span> <span data-ttu-id="b31f1-579">Selecione **Sim** para atualizar os arquivos de parâmetros do Excel no sistema local, mas não nos arquivos de parâmetros do Excel que foram carregados para o Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="b31f1-579">Select **Yes** to update the Excel parameter files in the local system but not the Excel parameter files that were uploaded to Azure DevOps.</span></span>

    ![Esta ação substituirá os arquivos de dados de teste do Excel](./media/setup_rsa_tool_102.png)

    <span data-ttu-id="b31f1-581">Os dois casos de teste são carregados, junto com o arquivo de parâmetros do Excel para o primeiro caso de teste.</span><span class="sxs-lookup"><span data-stu-id="b31f1-581">Both the test cases are loaded, together with the Excel parameter file for the first test case.</span></span> <span data-ttu-id="b31f1-582">Como você selecionou **Carregar** na última execução, os arquivos de parâmetro são extraídos do Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="b31f1-582">Because you selected **Upload** in the last run, the parameter files are pulled from Azure DevOps.</span></span>

    ![Casos de teste carregados](./media/setup_rsa_tool_103.png)

3. <span data-ttu-id="b31f1-584">Selecione somente o segundo caso de teste e depois **Novo \> Gerar arquivos de parâmetros e execução de teste**.</span><span class="sxs-lookup"><span data-stu-id="b31f1-584">Select only the second test case, and then select **New \> Generate test execution and parameter files**.</span></span>

#### <a name="edit-the-excel-parameter-file"></a><span data-ttu-id="b31f1-585">Edite o arquivo de parâmetros do Excel</span><span class="sxs-lookup"><span data-stu-id="b31f1-585">Edit the Excel parameter file</span></span>

1. <span data-ttu-id="b31f1-586">Selecione somente o segundo caso de teste e depois selecione **Editar** para abrir o arquivo de parâmetros do Excel correspondente.</span><span class="sxs-lookup"><span data-stu-id="b31f1-586">Select only the second test case, and then select **Edit** to open the corresponding Excel parameter file.</span></span>
2. <span data-ttu-id="b31f1-587">Copie a variável salva **{{EcoResProductCreate\_Identification\_ProductNumber\_Copy}}** (consulte a seção [Modificar uma gravação de tarefas existente para criar uma variável salva](#modify-an-existing-task-recording-to-create-a-saved-variable)) do primeiro caso de teste para todos os campos onde o número do produto é usado.</span><span class="sxs-lookup"><span data-stu-id="b31f1-587">Copy the **{{EcoResProductCreate\_Identification\_ProductNumber\_Copy}}** saved variable (see the [Modify an existing task recording to create a saved variable](#modify-an-existing-task-recording-to-create-a-saved-variable) section) from the first test case into all the fields where the product number is used.</span></span> <span data-ttu-id="b31f1-588">Neste caso, você copia a variável para os campos **Número do produto** e **Validar Número do produto** na folha **EcoResProductListPage**.</span><span class="sxs-lookup"><span data-stu-id="b31f1-588">In this case, you copy the variable into the **Product number** and **Validate Product number** fields on the **EcoResProductListPage** sheet.</span></span>

    ![Campos Número do produto e Validar Número do produto](./media/setup_rsa_tool_104.png)

    > [!NOTE]
    > <span data-ttu-id="b31f1-590">Variáveis podem ser transmitidos entre testes somente durante a mesma execução de testes.</span><span class="sxs-lookup"><span data-stu-id="b31f1-590">Variables can be passed between tests only during the same test run.</span></span> <span data-ttu-id="b31f1-591">Os nomes de variáveis devem corresponder exatamente.</span><span class="sxs-lookup"><span data-stu-id="b31f1-591">The names of the variables must match exactly.</span></span>

3. <span data-ttu-id="b31f1-592">Selecione **Salvar** e feche a pasta de trabalho do Excel.</span><span class="sxs-lookup"><span data-stu-id="b31f1-592">Select **Save**, and then close the Excel workbook.</span></span>
4. <span data-ttu-id="b31f1-593">Selecione **Carregar** para salvar as alterações feitas no arquivo de parâmetros do Excel.</span><span class="sxs-lookup"><span data-stu-id="b31f1-593">Select **Upload** to save the changes that you made to the Excel parameter file.</span></span>

#### <a name="run-the-chained-test-cases"></a><span data-ttu-id="b31f1-594">Execute os casos de teste encadeados</span><span class="sxs-lookup"><span data-stu-id="b31f1-594">Run the chained test cases</span></span>

1. <span data-ttu-id="b31f1-595">Selecione os dois casos de teste e selecione **Executar**.</span><span class="sxs-lookup"><span data-stu-id="b31f1-595">Select both the test cases, and then select **Run**.</span></span>
2. <span data-ttu-id="b31f1-596">Verifique se os dois casos de teste foram transmitidos.</span><span class="sxs-lookup"><span data-stu-id="b31f1-596">Verify that both test cases have passed.</span></span>

    ![Campo de resultado definido como transmitido para os dois casos de teste](./media/setup_rsa_tool_105.png)
