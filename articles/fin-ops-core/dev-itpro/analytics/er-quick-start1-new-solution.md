---
title: Criar uma nova solução ER para imprimir um relatório personalizado
description: Este tópico explica como criar uma solução de relatório eletrônico (ER) para imprimir um relatório personalizado.
author: NickSelin
ms.date: 08/10/2020
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
ms.openlocfilehash: 986beb6d46ac69192206c86fc3660c2e2345d6a9
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5743718"
---
# <a name="design-a-new-er-solution-to-print-a-custom-report"></a><span data-ttu-id="79c7c-103">Criar uma nova solução ER para imprimir um relatório personalizado</span><span class="sxs-lookup"><span data-stu-id="79c7c-103">Design a new ER solution to print a custom report</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="79c7c-104">As etapas a seguir explicam como um usuário no administrador do sistema, no desenvolvedor de relatórios eletrônicos ou na função consultor funcional de relatórios eletrônicos pode configurar parâmetros da estrutura ER, criar as configurações de ER necessárias de uma nova solução ER para acessar os dados de um domínio comercial específico e gerar um relatório personalizado no formato do Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="79c7c-104">The following steps explain how a user in the System Administrator, Electronic Reporting Developer, or Electronic Reporting Functional Consultant role can configure parameters of the ER framework, design the required ER configurations of a new ER solution to access the data of a particular business domain, and generate a custom report in Microsoft Office format.</span></span> <span data-ttu-id="79c7c-105">Essas etapas podem ser concluídas na empresa **USMF**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-105">These steps can be completed in the **USMF** company.</span></span>

- [<span data-ttu-id="79c7c-106">Configurar a estrutura de ER</span><span class="sxs-lookup"><span data-stu-id="79c7c-106">Configure the ER framework</span></span>](#ConfigureFramework)

    - [<span data-ttu-id="79c7c-107">Configurar parâmetros de ER</span><span class="sxs-lookup"><span data-stu-id="79c7c-107">Configure ER parameters</span></span>](#ConfigureParameters)
    - [<span data-ttu-id="79c7c-108">Ativar um provedor de configuração de ER</span><span class="sxs-lookup"><span data-stu-id="79c7c-108">Activate an ER configuration provider</span></span>](#ActivateProvider)

        - [<span data-ttu-id="79c7c-109">Examinar a lista de provedores de configuração de ER</span><span class="sxs-lookup"><span data-stu-id="79c7c-109">Review the list of ER configuration providers</span></span>](#ReviewProvidersList)
        - [<span data-ttu-id="79c7c-110">Adicionar um novo provedor de configuração de ER</span><span class="sxs-lookup"><span data-stu-id="79c7c-110">Add a new ER configuration provider</span></span>](#AddProvider)
        - [<span data-ttu-id="79c7c-111">Ativar um provedor de configuração de ER</span><span class="sxs-lookup"><span data-stu-id="79c7c-111">Activate an ER configuration provider</span></span>](#ActivateAddedProvider)

- [<span data-ttu-id="79c7c-112">Criar um modelo de dados de domínio específico</span><span class="sxs-lookup"><span data-stu-id="79c7c-112">Design a domain-specific data model</span></span>](#DesignModel)

    - [<span data-ttu-id="79c7c-113">Importar uma nova configuração de modelo de dados</span><span class="sxs-lookup"><span data-stu-id="79c7c-113">Import a new data model configuration</span></span>](#ImportDataModel)
    - [<span data-ttu-id="79c7c-114">Criar uma nova configuração de modelo de dados</span><span class="sxs-lookup"><span data-stu-id="79c7c-114">Create a new data model configuration</span></span>](#DesignDataModel)

        - [<span data-ttu-id="79c7c-115">Nomear o modelo de dados</span><span class="sxs-lookup"><span data-stu-id="79c7c-115">Name the data model</span></span>](#NameDataModel)
        - [<span data-ttu-id="79c7c-116">Adicionar campos de modelo de dados</span><span class="sxs-lookup"><span data-stu-id="79c7c-116">Add data model fields</span></span>](#FieldsEntry)
        - [<span data-ttu-id="79c7c-117">Concluir o design do modelo de dados</span><span class="sxs-lookup"><span data-stu-id="79c7c-117">Complete the design of the data model</span></span>](#CompleteDataModel)

- [<span data-ttu-id="79c7c-118">Criar um mapeamento de modelo para o modelo de dados configurado</span><span class="sxs-lookup"><span data-stu-id="79c7c-118">Design a model mapping for the configured data model</span></span>](#DesignMapping)

    - [<span data-ttu-id="79c7c-119">Importar uma nova configuração de mapeamento de modelo</span><span class="sxs-lookup"><span data-stu-id="79c7c-119">Import a new model mapping configuration</span></span>](#ImportModelMapping)
    - [<span data-ttu-id="79c7c-120">Crie uma nova configuração de mapeamento de modelo</span><span class="sxs-lookup"><span data-stu-id="79c7c-120">Create a new model mapping configuration</span></span>](#CreateModelMapping)

        - [<span data-ttu-id="79c7c-121">Criar um novo componente de mapeamento de modelos</span><span class="sxs-lookup"><span data-stu-id="79c7c-121">Design a new model mapping component</span></span>](#DesignMappingComponent)
        - [<span data-ttu-id="79c7c-122">Adicionar fontes de dados para acessar tabelas de aplicativos</span><span class="sxs-lookup"><span data-stu-id="79c7c-122">Add data sources to access application tables</span></span>](#AddMmDataSource1)
        - [<span data-ttu-id="79c7c-123">Adicionar fontes de dados para acessar enumerações de aplicativos</span><span class="sxs-lookup"><span data-stu-id="79c7c-123">Add data sources to access application enumerations</span></span>](#AddMmDataSource2)
        - [<span data-ttu-id="79c7c-124">Adicionar rótulos de ER para gerar um relatório em um idioma especificado</span><span class="sxs-lookup"><span data-stu-id="79c7c-124">Add ER labels to generate a report in a specified language</span></span>](#AddMmLabels)
        - [<span data-ttu-id="79c7c-125">Adicionar uma fonte de dados para transformar os resultados da comparação de valores de enumeração em um valor de texto</span><span class="sxs-lookup"><span data-stu-id="79c7c-125">Add a data source to transform the results of comparing enumeration values to a text value</span></span>](#AddMmDataSource3)
        - [<span data-ttu-id="79c7c-126">Associar fontes de dados a campos do modelo de dados</span><span class="sxs-lookup"><span data-stu-id="79c7c-126">Bind data sources to data model fields</span></span>](#AddMmBindings1)
        - [<span data-ttu-id="79c7c-127">Concluir o design de mapeamento do modelo</span><span class="sxs-lookup"><span data-stu-id="79c7c-127">Complete the design of the model mapping</span></span>](#CompleteModelMapping)

- [<span data-ttu-id="79c7c-128">Criar um modelo para um relatório personalizado</span><span class="sxs-lookup"><span data-stu-id="79c7c-128">Design a template for a custom report</span></span>](#DesignReportTemplate)
- [<span data-ttu-id="79c7c-129">Criar um formato</span><span class="sxs-lookup"><span data-stu-id="79c7c-129">Design a format</span></span>](#DesignFormat)

    - [<span data-ttu-id="79c7c-130">Importar uma configuração de formato criado</span><span class="sxs-lookup"><span data-stu-id="79c7c-130">Import a designed format configuration</span></span>](#FormatImport)
    - [<span data-ttu-id="79c7c-131">Criar uma nova configuração de formato</span><span class="sxs-lookup"><span data-stu-id="79c7c-131">Create a new format configuration</span></span>](#FormatCreate)

        - [<span data-ttu-id="79c7c-132">Importar um modelo do relatório</span><span class="sxs-lookup"><span data-stu-id="79c7c-132">Import a report template</span></span>](#ImportReportTemplate)
        - [<span data-ttu-id="79c7c-133">Configurar um formato</span><span class="sxs-lookup"><span data-stu-id="79c7c-133">Configure a format</span></span>](#ConfigureFormat)
        - [<span data-ttu-id="79c7c-134">Definir a associação de dados para um título de relatório</span><span class="sxs-lookup"><span data-stu-id="79c7c-134">Define the data binding for a report title</span></span>](#DefineFormatBindings)
        - [<span data-ttu-id="79c7c-135">Analisar a fonte de dados do modelo</span><span class="sxs-lookup"><span data-stu-id="79c7c-135">Review the model data source</span></span>](#ReviewModelDataSource)
        - [<span data-ttu-id="79c7c-136">Associar elementos a campos da fonte de dados</span><span class="sxs-lookup"><span data-stu-id="79c7c-136">Bind format elements to data source fields</span></span>](#BindFormatElements)

    - [<span data-ttu-id="79c7c-137">Executar um formato criado a partir de ER</span><span class="sxs-lookup"><span data-stu-id="79c7c-137">Run a designed format from ER</span></span>](#RunFormatFromER)

- [<span data-ttu-id="79c7c-138">Ajustar um formato criado</span><span class="sxs-lookup"><span data-stu-id="79c7c-138">Tune a designed format</span></span>](#TuneFormat)

    - [<span data-ttu-id="79c7c-139">Modificar um formato para alterar o nome de um documento gerado</span><span class="sxs-lookup"><span data-stu-id="79c7c-139">Modify a format to change the name of a generated document</span></span>](#ModifyToChangeName)
    - [<span data-ttu-id="79c7c-140">Modificar um formato para alterar a ordem das perguntas</span><span class="sxs-lookup"><span data-stu-id="79c7c-140">Modify a format to change the order of questions</span></span>](#ModifyToOrder)
    - [<span data-ttu-id="79c7c-141">Executar um formato modificado a partir de ER</span><span class="sxs-lookup"><span data-stu-id="79c7c-141">Run a modified format from ER</span></span>](#RunFormatFromER2)
    - [<span data-ttu-id="79c7c-142">Concluir a criação do formato</span><span class="sxs-lookup"><span data-stu-id="79c7c-142">Complete the format design</span></span>](#CompleteFormat)

- [<span data-ttu-id="79c7c-143">Desenvolver artefatos de aplicativos para chamar o relatório criado</span><span class="sxs-lookup"><span data-stu-id="79c7c-143">Develop application artefacts to call the designed report</span></span>](#DevelopCustomCode)

    - [<span data-ttu-id="79c7c-144">Modificar o código-fonte</span><span class="sxs-lookup"><span data-stu-id="79c7c-144">Modify source code</span></span>](#ModifySourceCode)

        - [<span data-ttu-id="79c7c-145">Adicionar uma classe de contrato de dados</span><span class="sxs-lookup"><span data-stu-id="79c7c-145">Add a data contract class</span></span>](#DataContractClass)
        - [<span data-ttu-id="79c7c-146">Adicionar uma classe do construtor de interface de usuário</span><span class="sxs-lookup"><span data-stu-id="79c7c-146">Add a UI builder class</span></span>](#UIBuilderClass)
        - [<span data-ttu-id="79c7c-147">Adicionar uma classe de provedor de dados</span><span class="sxs-lookup"><span data-stu-id="79c7c-147">Add a data provider class</span></span>](#DataProviderClass)
        - [<span data-ttu-id="79c7c-148">Adicionar um arquivo de rótulos</span><span class="sxs-lookup"><span data-stu-id="79c7c-148">Add a labels file</span></span>](#LabelsFile)
        - [<span data-ttu-id="79c7c-149">Adicionar uma classe de serviço de relatório</span><span class="sxs-lookup"><span data-stu-id="79c7c-149">Add a report service class</span></span>](#ServiceClass)
        - [<span data-ttu-id="79c7c-150">Adicionar uma classe de controlador de relatório</span><span class="sxs-lookup"><span data-stu-id="79c7c-150">Add a report controller class</span></span>](#ControllerClass)
        - [<span data-ttu-id="79c7c-151">Adicionar um item de menu</span><span class="sxs-lookup"><span data-stu-id="79c7c-151">Add a menu item</span></span>](#MenuItem)
        - [<span data-ttu-id="79c7c-152">Adicionar um item de menu a um menu</span><span class="sxs-lookup"><span data-stu-id="79c7c-152">Add a menu item to a menu</span></span>](#Menu)
        - [<span data-ttu-id="79c7c-153">Criar um projeto do Visual Studio</span><span class="sxs-lookup"><span data-stu-id="79c7c-153">Build a Visual Studio project</span></span>](#BuildVSProject)

    - [<span data-ttu-id="79c7c-154">Executar um formato do aplicativo</span><span class="sxs-lookup"><span data-stu-id="79c7c-154">Run a format from the application</span></span>](#RunFormatFromApp)

- [<span data-ttu-id="79c7c-155">Ajustar uma solução de ER criada</span><span class="sxs-lookup"><span data-stu-id="79c7c-155">Tune a designed ER solution</span></span>](#TuneSolution)

    - [<span data-ttu-id="79c7c-156">Modifique um mapeamento de modelo</span><span class="sxs-lookup"><span data-stu-id="79c7c-156">Modify a model mapping</span></span>](#ModifyModelMapping)

        - [<span data-ttu-id="79c7c-157">Adicionar fontes de dados para acessar um objeto de contrato de dados</span><span class="sxs-lookup"><span data-stu-id="79c7c-157">Add data sources to access a data contract object</span></span>](#AddDataSource1)
        - [<span data-ttu-id="79c7c-158">Adicionar uma fonte de dados para acessar registros de mapeamento de formato ER</span><span class="sxs-lookup"><span data-stu-id="79c7c-158">Add a data source to access ER format mapping records</span></span>](#AddDataSource2)
        - [<span data-ttu-id="79c7c-159">Adicionar uma fonte de dados para acessar um registro de mapeamento de formato de um formato de ER em execução</span><span class="sxs-lookup"><span data-stu-id="79c7c-159">Add a data source to access a format mapping record of a running ER format</span></span>](#AddDataSource3)
        - [<span data-ttu-id="79c7c-160">Inserir o nome do formato de ER em execução no modelo de dados</span><span class="sxs-lookup"><span data-stu-id="79c7c-160">Enter the name of the running ER format in the data model</span></span>](#AddBinding)
        - [<span data-ttu-id="79c7c-161">Concluir o design de mapeamento do modelo</span><span class="sxs-lookup"><span data-stu-id="79c7c-161">Complete the design of the model mapping</span></span>](#CompleteModelMapping2)

    - [<span data-ttu-id="79c7c-162">Modificar um formato</span><span class="sxs-lookup"><span data-stu-id="79c7c-162">Modify a format</span></span>](#ModifyFormat)

        - [<span data-ttu-id="79c7c-163">Adicionar um novo elemento de formato</span><span class="sxs-lookup"><span data-stu-id="79c7c-163">Add a new format element</span></span>](#AddFormatElement)
        - [<span data-ttu-id="79c7c-164">Vincular o elemento de formato adicionado</span><span class="sxs-lookup"><span data-stu-id="79c7c-164">Bind the added format element</span></span>](#BindAddedFormatElement)
        - [<span data-ttu-id="79c7c-165">Concluir a criação do formato</span><span class="sxs-lookup"><span data-stu-id="79c7c-165">Complete the format design</span></span>](#CompleteFormat2)

    - [<span data-ttu-id="79c7c-166">Executar um formato do aplicativo</span><span class="sxs-lookup"><span data-stu-id="79c7c-166">Run a format from the application</span></span>](#RunFormatFromApp2)
    - [<span data-ttu-id="79c7c-167">Executar um formato de ER</span><span class="sxs-lookup"><span data-stu-id="79c7c-167">Run a format from ER</span></span>](#RunFormatFromER3)
    - [<span data-ttu-id="79c7c-168">Configurar um destino de formato para versão prévia na tela</span><span class="sxs-lookup"><span data-stu-id="79c7c-168">Configure a format destination for on-screen preview</span></span>](#ConfigureDestination)
    - [<span data-ttu-id="79c7c-169">Executar um formato do aplicativo para visualizá-lo como um documento PDF</span><span class="sxs-lookup"><span data-stu-id="79c7c-169">Run a format from the application to preview it as a PDF document</span></span>](#RunFormatFromApp3)

- [<span data-ttu-id="79c7c-170">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="79c7c-170">Additional resources</span></span>](#References)

<span data-ttu-id="79c7c-171">Neste exemplo, você criará uma nova solução ER para o módulo [Questionário](https://docs.microsoft.com/dynamics365/human-resources/hr-learning-questionnaires).</span><span class="sxs-lookup"><span data-stu-id="79c7c-171">In this example, you will create a new ER solution for the [Questionnaire](https://docs.microsoft.com/dynamics365/human-resources/hr-learning-questionnaires) module.</span></span> <span data-ttu-id="79c7c-172">Essa nova solução ER permite criar um relatório usando uma planilha do Microsoft Excel como modelo.</span><span class="sxs-lookup"><span data-stu-id="79c7c-172">This new ER solution lets you design a report by using a Microsoft Excel worksheet as a template.</span></span> <span data-ttu-id="79c7c-173">Em seguida, você pode gerar o relatório **Questionário** no formato Excel ou PDF, além de gerar o relatório Serviços de Relatório do SQL Server (SSRS) existente.</span><span class="sxs-lookup"><span data-stu-id="79c7c-173">You can then generate the **Questionnaire** report in Excel or PDF format, in addition to generating the existing SQL Server Reporting Services (SSRS) report.</span></span> <span data-ttu-id="79c7c-174">Você também pode modificar o novo relatório posteriormente, quando solicitado.</span><span class="sxs-lookup"><span data-stu-id="79c7c-174">You can also modify the new report later, upon request.</span></span> <span data-ttu-id="79c7c-175">Nenhum código é necessário.</span><span class="sxs-lookup"><span data-stu-id="79c7c-175">No coding is required.</span></span>

1. <span data-ttu-id="79c7c-176">Para executar o relatório existente, vá para **Questionário** \> **Design** \> **Relatório Questionários**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-176">To run the existing report, go to **Questionnaire** \> **Design** \> **Questionnaires report**.</span></span>

    ![Seleção do item de menu do relatório Questionários no módulo Questionário para executar o relatório SSRS existente](./media/er-quick-start1-application-menu-origin.png)

2. <span data-ttu-id="79c7c-178">Na caixa de diálogo **Relatório Questionários**, especifique os critérios de seleção.</span><span class="sxs-lookup"><span data-stu-id="79c7c-178">In the **Questionnaires report** dialog box, specify selection criteria.</span></span> <span data-ttu-id="79c7c-179">Aplique um filtro para que o relatório inclua somente o questionário **SBCCrsExam**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-179">Apply a filter so that the report includes only the **SBCCrsExam** questionnaire.</span></span>

    ![Como especificar critérios de seleção na caixa de diálogo Relatório Questionários](./media/er-quick-start1-ssrs-report-dialog.png)

<span data-ttu-id="79c7c-181">A ilustração a seguir mostra a versão gerada do relatório SSRS para o questionário **SBCCrsExam**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-181">The following illustration shows the generated version of the SSRS report for the **SBCCrsExam** questionnaire.</span></span>

![Relatório SSRS gerado](./media/er-quick-start1-ssrs-report.png)

## <a name="configure-the-er-framework"></a><a name="ConfigureFramework"></a><span data-ttu-id="79c7c-183">Configurar a estrutura de ER</span><span class="sxs-lookup"><span data-stu-id="79c7c-183">Configure the ER framework</span></span>

<span data-ttu-id="79c7c-184">Como usuário na função de Desenvolvedor de Relatório Eletrônico, você deve configurar o conjunto mínimo de parâmetros de ER antes de começar a usar a estrutura de ER para criar uma nova solução ER.</span><span class="sxs-lookup"><span data-stu-id="79c7c-184">As a user in the Electronic Reporting Developer role, you must configure the minimal set of ER parameters before you can start to use the ER framework to design your new ER solution.</span></span>

### <a name="configure-er-parameters"></a><a name="ConfigureParameters"></a><span data-ttu-id="79c7c-185">Configurar parâmetros de ER</span><span class="sxs-lookup"><span data-stu-id="79c7c-185">Configure ER parameters</span></span>

1. <span data-ttu-id="79c7c-186">Vá para **Administração da organização** \> **Espaços de trabalho** \> **Relatório eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-186">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="79c7c-187">No espaço de trabalho **Relatório eletrônico**, selecione **Parâmetros de relatório eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-187">In the **Electronic reporting** workspace, select **Electronic reporting parameters**.</span></span>
3. <span data-ttu-id="79c7c-188">Na página **Parâmetros de relatório eletrônico**, na guia **Geral**, defina a opção **Habilitar modo de design** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-188">On the **Electronic reporting parameters** page, on the **General** tab, set the **Enable design mode** option to **Yes**.</span></span>
4. <span data-ttu-id="79c7c-189">Na guia **Anexos**, defina os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="79c7c-189">On the **Attachments** tab, set the following parameters:</span></span>

    - <span data-ttu-id="79c7c-190">Defina o campo **Configurações** como **Arquivo** para a empresa **USMF**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-190">Set the **Configurations** field to **File** for the **USMF** company.</span></span>
    - <span data-ttu-id="79c7c-191">Defina os campos **Arquivo de trabalho**, **Temporário**, **Linha de base** e **Outros** como **Arquivo**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-191">Set **Job archive**, **Temporary**, **Baseline**, and **Others** fields to **File**.</span></span>

<span data-ttu-id="79c7c-192">Para obter mais informações sobre parâmetros de ER, consulte [Configurar a estrutura de ER](electronic-reporting-er-configure-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="79c7c-192">For more information about ER parameters, see [Configure the ER framework](electronic-reporting-er-configure-parameters.md).</span></span>

### <a name="activate-an-er-configuration-provider"></a><a name="ActivateProvider"></a><span data-ttu-id="79c7c-193">Ativar um provedor de configuração de ER</span><span class="sxs-lookup"><span data-stu-id="79c7c-193">Activate an ER configuration provider</span></span>

<span data-ttu-id="79c7c-194">Toda configuração de ER é marcada como pertencente a um provedor de configuração de ER.</span><span class="sxs-lookup"><span data-stu-id="79c7c-194">Every ER configuration is marked as owned by an ER configuration provider.</span></span> <span data-ttu-id="79c7c-195">Por isso você deve ativar um provedor de configuração de ER no espaço de trabalho **Relatório eletrônico** antes de começar a adicionar ou editar configurações de ER.</span><span class="sxs-lookup"><span data-stu-id="79c7c-195">Therefore, you must activate an ER configuration provider in the **Electronic reporting** workspace before you start to add or edit any ER configurations.</span></span>

> [!NOTE]
> <span data-ttu-id="79c7c-196">Somente o proprietário de uma configuração de ER pode editá-la.</span><span class="sxs-lookup"><span data-stu-id="79c7c-196">Only the owner of an ER configuration can edit it.</span></span> <span data-ttu-id="79c7c-197">Assim, para que uma configuração de ER possa ser editada, o provedor de configuração de ER apropriado deve estar ativado no espaço de trabalho **Relatório eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-197">Therefore, before an ER configuration can be edited, the appropriate ER configuration provider must be activated in the **Electronic reporting** workspace.</span></span>

#### <a name="review-the-list-of-er-configuration-providers"></a><a name="ReviewProvidersList"></a><span data-ttu-id="79c7c-198">Examinar a lista de provedores de configuração de ER</span><span class="sxs-lookup"><span data-stu-id="79c7c-198">Review the list of ER configuration providers</span></span>

1. <span data-ttu-id="79c7c-199">Vá para **Administração da organização** \> **Espaços de trabalho** \> **Relatório eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-199">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="79c7c-200">No espaço de trabalho **Relatório eletrônico**, na seção **Links relacionados**, selecione **Provedores de configuração**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-200">In the **Electronic reporting** workspace, in the **Related links** section, select **Configuration providers**.</span></span>
3. <span data-ttu-id="79c7c-201">Na página **Provedores de configuração**, cada registro de provedor de configuração tem um nome e uma URL únicos.</span><span class="sxs-lookup"><span data-stu-id="79c7c-201">On the **Configuration providers** page, each configuration provider record has a unique name and URL.</span></span> <span data-ttu-id="79c7c-202">Examine o conteúdo dessa página.</span><span class="sxs-lookup"><span data-stu-id="79c7c-202">Review the contents of this page.</span></span> <span data-ttu-id="79c7c-203">Se já existir um registro para **Litware, Ltda.** (`https://www.litware.com`), ignore o próximo procedimento, [Adicionar um novo provedor de configuração de ER](#ActivateProvider).</span><span class="sxs-lookup"><span data-stu-id="79c7c-203">If a record for **Litware, Inc.** (`https://www.litware.com`) already exists, skip the next procedure, [Add a new ER configuration provider](#ActivateProvider).</span></span>

#### <a name="add-a-new-er-configuration-provider"></a><a name="AddProvider"></a><span data-ttu-id="79c7c-204">Adicionar um novo provedor de configuração de ER</span><span class="sxs-lookup"><span data-stu-id="79c7c-204">Add a new ER configuration provider</span></span>

1. <span data-ttu-id="79c7c-205">Na página **Provedores de configuração**, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-205">On the **Configuration providers** page, select **New**.</span></span>
2. <span data-ttu-id="79c7c-206">No campo **Nome**, insira **Litware, Ltda.**</span><span class="sxs-lookup"><span data-stu-id="79c7c-206">In the **Name** field, enter **Litware, Inc.**</span></span>
3. <span data-ttu-id="79c7c-207">No campo **Endereço na Internet**, insira `https://www.litware.com`.</span><span class="sxs-lookup"><span data-stu-id="79c7c-207">In the **Internet address** field, enter `https://www.litware.com`.</span></span>
4. <span data-ttu-id="79c7c-208">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-208">Select **Save**.</span></span>

#### <a name="activate-an-er-configuration-provider"></a><a name="ActivateAddedProvider"></a><span data-ttu-id="79c7c-209">Ativar um provedor de configuração de ER</span><span class="sxs-lookup"><span data-stu-id="79c7c-209">Activate an ER configuration provider</span></span>

1. <span data-ttu-id="79c7c-210">Vá para **Administração da organização** \> **Espaços de trabalho** \> **Relatório eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-210">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="79c7c-211">No espaço de trabalho **Relatório eletrônico**, selecione o provedor de configuração **Litware, Inc.**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-211">In the **Electronic reporting** workspace, select the **Litware, Inc.** configuration provider.</span></span>
3. <span data-ttu-id="79c7c-212">Selecione **Definir como ativo**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-212">Select **Set active**.</span></span>

<span data-ttu-id="79c7c-213">Para obter mais informações sobre provedores de configuração de ER, consulte [Criar provedores de configuração e marcá-los como ativos](tasks/er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="79c7c-213">For more information about ER configuration providers, see [Create configuration providers and mark them as active](tasks/er-configuration-provider-mark-it-active-2016-11.md).</span></span>

## <a name="design-a-domain-specific-data-model"></a><a name="DesignModel"></a><span data-ttu-id="79c7c-214">Criar um modelo de dados de domínio específico</span><span class="sxs-lookup"><span data-stu-id="79c7c-214">Design a domain-specific data model</span></span>

<span data-ttu-id="79c7c-215">Você deve criar uma nova configuração ER contendo um componente de [modelo de dados](general-electronic-reporting.md#data-model-and-model-mapping-components) para o domínio comercial do **Questionário**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-215">You must create a new ER configuration that contains a [data model](general-electronic-reporting.md#data-model-and-model-mapping-components) component for the **Questionnaire** business domain.</span></span> <span data-ttu-id="79c7c-216">Esse modelo de dados será usado posteriormente como uma fonte de dados quando você criar um formato ER para gerar o relatório **Questionário**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-216">This data model will later be used as a data source when you design an ER format to generate the **Questionnaire** report.</span></span>

<span data-ttu-id="79c7c-217">Ao concluir as etapas na seção [Importar uma nova configuração do modelo de dados](#ImportDataModel), você pode importar o modelo de dados necessário do arquivo XML fornecido.</span><span class="sxs-lookup"><span data-stu-id="79c7c-217">By completing the steps in the [Import a new data model configuration](#ImportDataModel) section, you can import the required data model from the provided XML file.</span></span> <span data-ttu-id="79c7c-218">Como alternativa, você pode concluir as etapas na seção [Criar uma nova configuração do modelo de dados](#DesignDataModel) para criar esse modelo de dados desde o início.</span><span class="sxs-lookup"><span data-stu-id="79c7c-218">Alternatively, you can complete the steps in the [Create a new data model configuration](#DesignDataModel) section to design this data model from scratch.</span></span>

### <a name="import-a-new-data-model-configuration"></a><a name="ImportDataModel"></a><span data-ttu-id="79c7c-219">Importar uma nova configuração de modelo de dados</span><span class="sxs-lookup"><span data-stu-id="79c7c-219">Import a new data model configuration</span></span>

1. <span data-ttu-id="79c7c-220">Baixe o arquivo [Questionnaires model.version.1.xml](https://go.microsoft.com/fwlink/?linkid=851448) e salve-o no computador local.</span><span class="sxs-lookup"><span data-stu-id="79c7c-220">Download the [Questionnaires model.version.1.xml](https://go.microsoft.com/fwlink/?linkid=851448) file, and save it to your local computer.</span></span>
2. <span data-ttu-id="79c7c-221">Vá para **Administração da organização** \> **Espaços de trabalho** \> **Relatório eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-221">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
3. <span data-ttu-id="79c7c-222">No espaço de trabalho **Relatório eletrônico**, selecione **Configurações de relatórios**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-222">In the **Electronic reporting** workspace, select **Reporting configurations**.</span></span>
4. <span data-ttu-id="79c7c-223">No Painel de Ação, selecione **Câmbio** \> **Carregar de arquivo XML**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-223">On the Action Pane, select **Exchange** \> **Load from XML file**.</span></span>
5. <span data-ttu-id="79c7c-224">Selecione **Procurar** e, depois, localize e selecione o arquivo **Questionnaires model.version.1.xml**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-224">Select **Browse**, and then find and select the **Questionnaires model.version.1.xml** file.</span></span>
6. <span data-ttu-id="79c7c-225">Selecione **OK** para importar a configuração.</span><span class="sxs-lookup"><span data-stu-id="79c7c-225">Select **OK** to import the configuration.</span></span>

<span data-ttu-id="79c7c-226">Para continuar, ignore o próximo procedimento, [Criar uma nova configuração de modelo de dados](#DesignDataModel).</span><span class="sxs-lookup"><span data-stu-id="79c7c-226">To continue, skip the next procedure, [Create a new data model configuration](#DesignDataModel).</span></span>

### <a name="create-a-new-data-model-configuration"></a><a name="DesignDataModel"></a><span data-ttu-id="79c7c-227">Criar uma nova configuração de modelo de dados</span><span class="sxs-lookup"><span data-stu-id="79c7c-227">Create a new data model configuration</span></span>

1. <span data-ttu-id="79c7c-228">Vá para **Administração da organização** \> **Espaços de trabalho** \> **Relatório eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-228">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="79c7c-229">No espaço de trabalho **Relatório eletrônico**, selecione **Configurações de relatórios**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-229">In the **Electronic reporting** workspace, select **Reporting configurations**.</span></span>
3. <span data-ttu-id="79c7c-230">Selecione **Criar configuração**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-230">Select **Create configuration**.</span></span>
4. <span data-ttu-id="79c7c-231">Na caixa de diálogo suspensa, no campo **Nome**, insira **Modelo de questionário**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-231">In the drop-down dialog box, in the **Name** field, enter **Questionnaire model**.</span></span>
5. <span data-ttu-id="79c7c-232">Selecione **Criar configuração** para criar a configuração.</span><span class="sxs-lookup"><span data-stu-id="79c7c-232">Select **Create configuration** to create the configuration.</span></span>

#### <a name="name-the-data-model"></a><a name="NameDataModel"></a><span data-ttu-id="79c7c-233">Nomear o modelo de dados</span><span class="sxs-lookup"><span data-stu-id="79c7c-233">Name the data model</span></span>

1. <span data-ttu-id="79c7c-234">Na página **Configurações**, na árvore de configurações, selecione **Modelo de questionário**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-234">On the **Configurations** page, in the configuration tree, select **Questionnaire model**.</span></span>
2. <span data-ttu-id="79c7c-235">Selecione **Designer**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-235">Select **Designer**.</span></span>
3. <span data-ttu-id="79c7c-236">Na página **Designer de modelo de dados**, na FastTab **Geral**, no campo **Nome**, insira <a name="DataModeName"></a>**Questionários**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-236">On the **Data model designer** page, on the **General** FastTab, in the **Name** field, enter <a name="DataModeName"></a>**Questionnaires**.</span></span>

#### <a name="add-new-data-model-fields"></a><a name="FieldsEntry"></a><span data-ttu-id="79c7c-237">Adicionar novos campos de modelo de dados</span><span class="sxs-lookup"><span data-stu-id="79c7c-237">Add new data model fields</span></span>

1. <span data-ttu-id="79c7c-238">Na página **Designer de modelo de dados**, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-238">On the **Data model designer** page, select **New**.</span></span>
2. <span data-ttu-id="79c7c-239">Na caixa de diálogo suspensa para adicionar um nó de modelo de dados, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="79c7c-239">In the drop-down dialog box for adding a data model node, follow these steps:</span></span>

    1. <span data-ttu-id="79c7c-240">Selecione **Raiz do modelo** como o tipo do novo nó.</span><span class="sxs-lookup"><span data-stu-id="79c7c-240">Select **Model root** as the type of the new node.</span></span>
    2. <span data-ttu-id="79c7c-241">No campo **Nome**, insira <a name="RootDefinitionName"></a>**Raiz**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-241">In the **Name** field, enter <a name="RootDefinitionName"></a>**Root**.</span></span>
    3. <span data-ttu-id="79c7c-242">Selecione **Adicionar** para adicionar o novo nó.</span><span class="sxs-lookup"><span data-stu-id="79c7c-242">Select **Add** to add the new node.</span></span>

    <span data-ttu-id="79c7c-243">Esse descritor raiz será usado para fornecer dados para o relatório **Questionário**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-243">This root descriptor will be used to provide data for the **Questionnaire** report.</span></span> <span data-ttu-id="79c7c-244">Um único modelo de dados pode ter vários descritores.</span><span class="sxs-lookup"><span data-stu-id="79c7c-244">A single data model can have multiple descriptors.</span></span> <span data-ttu-id="79c7c-245">Cada descritor pode ser especificado para um único formato ER, a fim de identificar os dados necessários para gerar o relatório.</span><span class="sxs-lookup"><span data-stu-id="79c7c-245">Each descriptor can be specified for a single ER format, to identify data that is required to generate the report.</span></span>

3. <span data-ttu-id="79c7c-246">Selecione **Novo** novamente e, na caixa de diálogo suspensa para adicionar um nó de modelo de dados, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="79c7c-246">Select **New** again, and then, in the drop-down dialog box for adding a data model node, follow these steps:</span></span>

    1. <span data-ttu-id="79c7c-247">Selecione **Filho de um nó ativo** como o tipo do novo nó.</span><span class="sxs-lookup"><span data-stu-id="79c7c-247">Select **Child of an active node** as the type of the new node.</span></span>
    2. <span data-ttu-id="79c7c-248">No campo **Nome**, insira **CompanyName**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-248">In the **Name** field, enter **CompanyName**.</span></span>
    3. <span data-ttu-id="79c7c-249">No campo **Tipo de item**, selecione **String**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-249">In the **Item type** field, select **String**.</span></span>
    4. <span data-ttu-id="79c7c-250">Selecione **Adicionar** para adicionar o novo campo.</span><span class="sxs-lookup"><span data-stu-id="79c7c-250">Select **Add** to add the new field.</span></span>

    <span data-ttu-id="79c7c-251">Este campo é necessário para passar o nome da empresa atual para um relatório ER que consome esse modelo de dados como uma fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="79c7c-251">This field is required to pass the name of the current company to an ER report that consumes this data model as a data source.</span></span>

4. <span data-ttu-id="79c7c-252">Selecione **Novo** novamente e, na caixa de diálogo suspensa para adicionar um nó de modelo de dados, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="79c7c-252">Select **New** again, and then, in the drop-down dialog box for adding a data model node, follow these steps:</span></span>

    1. <span data-ttu-id="79c7c-253">Selecione **Filho de um nó ativo** como o tipo do novo nó.</span><span class="sxs-lookup"><span data-stu-id="79c7c-253">Select **Child of an active node** as the type of the new node.</span></span>
    2. <span data-ttu-id="79c7c-254">No campo **Nome**, insira **Questionário**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-254">In the **Name** field, enter **Questionnaire**.</span></span>
    3. <span data-ttu-id="79c7c-255">No campo **Tipo de item**, selecione **Lista de registros**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-255">In the **Item type** field, select **Record list**.</span></span>
    4. <span data-ttu-id="79c7c-256">Selecione **Adicionar** para adicionar o novo campo.</span><span class="sxs-lookup"><span data-stu-id="79c7c-256">Select **Add** to add the new field.</span></span>

    <span data-ttu-id="79c7c-257">Este campo será usado para passar a lista de questionários para um relatório ER que consome esse modelo de dados como uma fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="79c7c-257">This field will be used to pass the list of questionnaires to an ER report that consumes this data model as a data source.</span></span>

5. <span data-ttu-id="79c7c-258">Selecione o nó **Questionário**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-258">Select the **Questionnaire** node.</span></span>
6. <span data-ttu-id="79c7c-259">Continue a adicionar os campos obrigatórios do modelo de dados editável da mesma forma até concluir a estrutura de modelo de dados a seguir.</span><span class="sxs-lookup"><span data-stu-id="79c7c-259">Continue to add the required fields of the editable data model in the same manner until you complete the following data model structure.</span></span>

    | <span data-ttu-id="79c7c-260">Caminho do campo</span><span class="sxs-lookup"><span data-stu-id="79c7c-260">Field path</span></span>                                                    | <span data-ttu-id="79c7c-261">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="79c7c-261">Data type</span></span>   | <span data-ttu-id="79c7c-262">Designação de campo/valor retornado</span><span class="sxs-lookup"><span data-stu-id="79c7c-262">Field designation/returned value</span></span> |
    |---------------------------------------------------------------|-------------|----------------------------------|
    | <span data-ttu-id="79c7c-263">Raiz</span><span class="sxs-lookup"><span data-stu-id="79c7c-263">Root</span></span>                                                          |             | <span data-ttu-id="79c7c-264">O ponto de referência para solicitar dados de questionário.</span><span class="sxs-lookup"><span data-stu-id="79c7c-264">The reference point to request questionnaire data.</span></span> |
    | <span data-ttu-id="79c7c-265">Raiz\\CompanyName</span><span class="sxs-lookup"><span data-stu-id="79c7c-265">Root\\CompanyName</span></span>                                             | <span data-ttu-id="79c7c-266">Sequência de caracteres</span><span class="sxs-lookup"><span data-stu-id="79c7c-266">String</span></span>      | <span data-ttu-id="79c7c-267">O nome da empresa atual.</span><span class="sxs-lookup"><span data-stu-id="79c7c-267">The name of the current company.</span></span> |
    | <span data-ttu-id="79c7c-268">Raiz\\ExecutionContext</span><span class="sxs-lookup"><span data-stu-id="79c7c-268">Root\\ExecutionContext</span></span>                                        | <span data-ttu-id="79c7c-269">Registrar</span><span class="sxs-lookup"><span data-stu-id="79c7c-269">Record</span></span>      | <span data-ttu-id="79c7c-270">Detalhes da execução de formato.</span><span class="sxs-lookup"><span data-stu-id="79c7c-270">Format execution details.</span></span> |
    | <span data-ttu-id="79c7c-271">Raiz\\ExecutionContext\\FormatName</span><span class="sxs-lookup"><span data-stu-id="79c7c-271">Root\\ExecutionContext\\FormatName</span></span>                            | <span data-ttu-id="79c7c-272">Sequência de caracteres</span><span class="sxs-lookup"><span data-stu-id="79c7c-272">String</span></span>      | <span data-ttu-id="79c7c-273">O nome do formato ER que está sendo executado.</span><span class="sxs-lookup"><span data-stu-id="79c7c-273">The name of the ER format that is being run.</span></span> |
    | <span data-ttu-id="79c7c-274">Raiz\\Questionário</span><span class="sxs-lookup"><span data-stu-id="79c7c-274">Root\\Questionnaire</span></span>                                           | <span data-ttu-id="79c7c-275">Registrar lista</span><span class="sxs-lookup"><span data-stu-id="79c7c-275">Record list</span></span> | <span data-ttu-id="79c7c-276">A lista de questionários</span><span class="sxs-lookup"><span data-stu-id="79c7c-276">The list of questionnaires</span></span> |
    | <span data-ttu-id="79c7c-277">Raiz\\Questionário\\Ativo</span><span class="sxs-lookup"><span data-stu-id="79c7c-277">Root\\Questionnaire\\Active</span></span>                                   | <span data-ttu-id="79c7c-278">Sequência de caracteres</span><span class="sxs-lookup"><span data-stu-id="79c7c-278">String</span></span>      | <span data-ttu-id="79c7c-279">O status do questionário atual.</span><span class="sxs-lookup"><span data-stu-id="79c7c-279">The status of the current questionnaire.</span></span> |
    | <span data-ttu-id="79c7c-280">Raiz\\Questionário\\Código</span><span class="sxs-lookup"><span data-stu-id="79c7c-280">Root\\Questionnaire\\Code</span></span>                                     | <span data-ttu-id="79c7c-281">Sequência de caracteres</span><span class="sxs-lookup"><span data-stu-id="79c7c-281">String</span></span>      | <span data-ttu-id="79c7c-282">O código do questionário atual.</span><span class="sxs-lookup"><span data-stu-id="79c7c-282">The code of the current questionnaire.</span></span> |
    | <span data-ttu-id="79c7c-283">Raiz\\Questionário\\Descrição</span><span class="sxs-lookup"><span data-stu-id="79c7c-283">Root\\Questionnaire\\Description</span></span>                              | <span data-ttu-id="79c7c-284">Sequência de caracteres</span><span class="sxs-lookup"><span data-stu-id="79c7c-284">String</span></span>      | <span data-ttu-id="79c7c-285">A descrição do questionário atual.</span><span class="sxs-lookup"><span data-stu-id="79c7c-285">The description of the current questionnaire.</span></span> |
    | <span data-ttu-id="79c7c-286">Raiz\\Questionário\\QuestionnaireType</span><span class="sxs-lookup"><span data-stu-id="79c7c-286">Root\\Questionnaire\\QuestionnaireType</span></span>                        | <span data-ttu-id="79c7c-287">Sequência de caracteres</span><span class="sxs-lookup"><span data-stu-id="79c7c-287">String</span></span>      | <span data-ttu-id="79c7c-288">O tipo do questionário atual.</span><span class="sxs-lookup"><span data-stu-id="79c7c-288">The type of the current questionnaire.</span></span> |
    | <span data-ttu-id="79c7c-289">Raiz\\Questionário\\QuestionOrder</span><span class="sxs-lookup"><span data-stu-id="79c7c-289">Root\\Questionnaire\\QuestionOrder</span></span>                            | <span data-ttu-id="79c7c-290">Sequência de caracteres</span><span class="sxs-lookup"><span data-stu-id="79c7c-290">String</span></span>      | <span data-ttu-id="79c7c-291">A ordem numérica do questionário atual.</span><span class="sxs-lookup"><span data-stu-id="79c7c-291">The numerical order of the current questionnaire.</span></span> |
    | <span data-ttu-id="79c7c-292">Raiz\\Questionário\\ResultsGroup</span><span class="sxs-lookup"><span data-stu-id="79c7c-292">Root\\Questionnaire\\ResultsGroup</span></span>                             | <span data-ttu-id="79c7c-293">Registrar</span><span class="sxs-lookup"><span data-stu-id="79c7c-293">Record</span></span>      | <span data-ttu-id="79c7c-294">As parâmetros de resultado do questionário atual.</span><span class="sxs-lookup"><span data-stu-id="79c7c-294">The result parameters of the current questionnaire.</span></span> |
    | <span data-ttu-id="79c7c-295">Raiz\\Questionário\\ResultsGroup\\Código</span><span class="sxs-lookup"><span data-stu-id="79c7c-295">Root\\Questionnaire\\ResultsGroup\\Code</span></span>                       | <span data-ttu-id="79c7c-296">Sequência de caracteres</span><span class="sxs-lookup"><span data-stu-id="79c7c-296">String</span></span>      | <span data-ttu-id="79c7c-297">O código de identificação do grupo de resultados atual.</span><span class="sxs-lookup"><span data-stu-id="79c7c-297">The identification code of the current result group.</span></span> |
    | <span data-ttu-id="79c7c-298">Raiz\\Questionário\\ResultsGroup\\Descrição</span><span class="sxs-lookup"><span data-stu-id="79c7c-298">Root\\Questionnaire\\ResultsGroup\\Description</span></span>                | <span data-ttu-id="79c7c-299">Sequência de caracteres</span><span class="sxs-lookup"><span data-stu-id="79c7c-299">String</span></span>      | <span data-ttu-id="79c7c-300">A descrição do grupo de resultados atual.</span><span class="sxs-lookup"><span data-stu-id="79c7c-300">The description of the current result group.</span></span> |
    | <span data-ttu-id="79c7c-301">Raiz\\Questionário\\ResultsGroup\\MaxNumberOfPoints</span><span class="sxs-lookup"><span data-stu-id="79c7c-301">Root\\Questionnaire\\ResultsGroup\\MaxNumberOfPoints</span></span>          | <span data-ttu-id="79c7c-302">Real</span><span class="sxs-lookup"><span data-stu-id="79c7c-302">Real</span></span>        | <span data-ttu-id="79c7c-303">O número máximo de pontos a ser obtido.</span><span class="sxs-lookup"><span data-stu-id="79c7c-303">The maximum number of points that could be earned.</span></span> |
    | <span data-ttu-id="79c7c-304">Raiz\\Questionário\\Pergunta</span><span class="sxs-lookup"><span data-stu-id="79c7c-304">Root\\Questionnaire\\Question</span></span>                                 | <span data-ttu-id="79c7c-305">Registrar lista</span><span class="sxs-lookup"><span data-stu-id="79c7c-305">Record list</span></span> | <span data-ttu-id="79c7c-306">A lista de perguntas do questionário atual.</span><span class="sxs-lookup"><span data-stu-id="79c7c-306">The list of questions for the current questionnaire.</span></span> |
    | <span data-ttu-id="79c7c-307">Raiz\\Questionário\\Pergunta\\CollectionSequenceNumber</span><span class="sxs-lookup"><span data-stu-id="79c7c-307">Root\\Questionnaire\\Question\\CollectionSequenceNumber</span></span>       | <span data-ttu-id="79c7c-308">Inteiro</span><span class="sxs-lookup"><span data-stu-id="79c7c-308">Integer</span></span>     | <span data-ttu-id="79c7c-309">O número de sequência da coleção de respostas atual.</span><span class="sxs-lookup"><span data-stu-id="79c7c-309">The sequence number of the current answer collection.</span></span> |
    | <span data-ttu-id="79c7c-310">Raiz\\Questionário\\Pergunta\\Id</span><span class="sxs-lookup"><span data-stu-id="79c7c-310">Root\\Questionnaire\\Question\\Id</span></span>                             | <span data-ttu-id="79c7c-311">Sequência de caracteres</span><span class="sxs-lookup"><span data-stu-id="79c7c-311">String</span></span>      | <span data-ttu-id="79c7c-312">O código de identificação da pergunta atual.</span><span class="sxs-lookup"><span data-stu-id="79c7c-312">The identification code of the current question.</span></span> |
    | <span data-ttu-id="79c7c-313">Raiz\\Questionário\\Pergunta\\MustBeCompleted</span><span class="sxs-lookup"><span data-stu-id="79c7c-313">Root\\Questionnaire\\Question\\MustBeCompleted</span></span>                | <span data-ttu-id="79c7c-314">Sequência de caracteres</span><span class="sxs-lookup"><span data-stu-id="79c7c-314">String</span></span>      | <span data-ttu-id="79c7c-315">Um sinalizador que indica se a pergunta atual deve ser respondida.</span><span class="sxs-lookup"><span data-stu-id="79c7c-315">A flag that indicates whether the current question must be answered.</span></span> |
    | <span data-ttu-id="79c7c-316">Raiz\\Questionário\\Pergunta\\PrimaryQuestion</span><span class="sxs-lookup"><span data-stu-id="79c7c-316">Root\\Questionnaire\\Question\\PrimaryQuestion</span></span>                | <span data-ttu-id="79c7c-317">Sequência de caracteres</span><span class="sxs-lookup"><span data-stu-id="79c7c-317">String</span></span>      | <span data-ttu-id="79c7c-318">Um sinalizador que indica se a pergunta atual é a principal.</span><span class="sxs-lookup"><span data-stu-id="79c7c-318">A flag that indicates whether the current question is primary.</span></span> |
    | <span data-ttu-id="79c7c-319">Raiz\\Questionário\\Pergunta\\SequenceNumber</span><span class="sxs-lookup"><span data-stu-id="79c7c-319">Root\\Questionnaire\\Question\\SequenceNumber</span></span>                 | <span data-ttu-id="79c7c-320">Inteiro</span><span class="sxs-lookup"><span data-stu-id="79c7c-320">Integer</span></span>     | <span data-ttu-id="79c7c-321">O número de sequência da pergunta atual.</span><span class="sxs-lookup"><span data-stu-id="79c7c-321">The sequence number of the current question.</span></span> |
    | <span data-ttu-id="79c7c-322">Raiz\\Questionário\\Pergunta\\Texto</span><span class="sxs-lookup"><span data-stu-id="79c7c-322">Root\\Questionnaire\\Question\\Text</span></span>                           | <span data-ttu-id="79c7c-323">Sequência de caracteres</span><span class="sxs-lookup"><span data-stu-id="79c7c-323">String</span></span>      | <span data-ttu-id="79c7c-324">O texto da pergunta atual.</span><span class="sxs-lookup"><span data-stu-id="79c7c-324">The text of the current question.</span></span> |
    | <span data-ttu-id="79c7c-325">Raiz\\Questionário\\Pergunta\\Resposta</span><span class="sxs-lookup"><span data-stu-id="79c7c-325">Root\\Questionnaire\\Question\\Answer</span></span>                         | <span data-ttu-id="79c7c-326">Registrar lista</span><span class="sxs-lookup"><span data-stu-id="79c7c-326">Record list</span></span> | <span data-ttu-id="79c7c-327">A lista de respostas para a pergunta atual.</span><span class="sxs-lookup"><span data-stu-id="79c7c-327">The list of answers for the current question.</span></span> |
    | <span data-ttu-id="79c7c-328">Raiz\\Questionário\\Pergunta\\Resposta\\CorrectAnswer</span><span class="sxs-lookup"><span data-stu-id="79c7c-328">Root\\Questionnaire\\Question\\Answer\\CorrectAnswer</span></span>          | <span data-ttu-id="79c7c-329">Sequência de caracteres</span><span class="sxs-lookup"><span data-stu-id="79c7c-329">String</span></span>      | <span data-ttu-id="79c7c-330">Um sinalizador que indica se a pergunta resposta atual está correta.</span><span class="sxs-lookup"><span data-stu-id="79c7c-330">A flag that indicates whether the current answer is correct.</span></span> |
    | <span data-ttu-id="79c7c-331">Raiz\\Questionário\\Pergunta\\Resposta\\Pontos</span><span class="sxs-lookup"><span data-stu-id="79c7c-331">Root\\Questionnaire\\Question\\Answer\\Points</span></span>                 | <span data-ttu-id="79c7c-332">Real</span><span class="sxs-lookup"><span data-stu-id="79c7c-332">Real</span></span>        | <span data-ttu-id="79c7c-333">Os pontos ganhos quando a resposta atual é selecionada.</span><span class="sxs-lookup"><span data-stu-id="79c7c-333">The points that are earned when the current answer is selected.</span></span> |
    | <span data-ttu-id="79c7c-334">Raiz\\Questionário\\Pergunta\\Resposta\\SequenceNumber</span><span class="sxs-lookup"><span data-stu-id="79c7c-334">Root\\Questionnaire\\Question\\Answer\\SequenceNumber</span></span>         | <span data-ttu-id="79c7c-335">Inteiro</span><span class="sxs-lookup"><span data-stu-id="79c7c-335">Integer</span></span>     | <span data-ttu-id="79c7c-336">O número de sequência da resposta atual.</span><span class="sxs-lookup"><span data-stu-id="79c7c-336">The sequence number of the current answer.</span></span> |
    | <span data-ttu-id="79c7c-337">Raiz\\Questionário\\Pergunta\\Resposta\\Texto</span><span class="sxs-lookup"><span data-stu-id="79c7c-337">Root\\Questionnaire\\Question\\Answer\\Text</span></span>                   | <span data-ttu-id="79c7c-338">Sequência de caracteres</span><span class="sxs-lookup"><span data-stu-id="79c7c-338">String</span></span>      | <span data-ttu-id="79c7c-339">O texto da resposta atual.</span><span class="sxs-lookup"><span data-stu-id="79c7c-339">The text of the current answer.</span></span> |

    <span data-ttu-id="79c7c-340">A ilustração a seguir mostra o modelo de dados editável preenchido na página **Designer do modelo de dados**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-340">The following illustration shows the completed editable data model on the **Data model designer** page.</span></span>

    ![Modelo de dados configurado no designer de modelos de dados ER](./media/er-quick-start1-model2.png)

7. <span data-ttu-id="79c7c-342">Salve as alterações.</span><span class="sxs-lookup"><span data-stu-id="79c7c-342">Save your changes.</span></span>
8. <span data-ttu-id="79c7c-343">Feche a página **Designer de modelo de dados**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-343">Close the **Data model designer** page.</span></span>

#### <a name="complete-the-design-of-the-data-model"></a><a name="CompleteDataModel"></a><span data-ttu-id="79c7c-344">Concluir o design do modelo de dados</span><span class="sxs-lookup"><span data-stu-id="79c7c-344">Complete the design of the data model</span></span>

1. <span data-ttu-id="79c7c-345">Vá para **Administração da organização** \> **Relatório eletrônico** \> **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-345">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="79c7c-346">Na página **Configurações**, na árvore de configurações, selecione **Modelo de questionário**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-346">On the **Configurations** page, in the configuration tree, select **Questionnaire model**.</span></span>
3. <span data-ttu-id="79c7c-347">Na FastTab **Versões**, selecione a versão de configuração com o status **Rascunho**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-347">On the **Versions** FastTab, select the configuration version that has a status of **Draft**.</span></span>
4. <span data-ttu-id="79c7c-348">Selecione **Alterar status** \> **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-348">Select **Change status** \> **Complete**.</span></span>

<span data-ttu-id="79c7c-349">O status da versão 1 dessa configuração é alterado de **Rascunho** para **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-349">The status of version 1 of this configuration is changed from **Draft** to **Completed**.</span></span> <span data-ttu-id="79c7c-350">A versão 1 não pode mais ser alterada.</span><span class="sxs-lookup"><span data-stu-id="79c7c-350">Version 1 can no longer be changed.</span></span> <span data-ttu-id="79c7c-351">Esta versão contém o modelo de dados configurado e pode ser usada como base para outras configurações de ER.</span><span class="sxs-lookup"><span data-stu-id="79c7c-351">This version contains the configured data model and can be used as the basis for other ER configurations.</span></span> <span data-ttu-id="79c7c-352">A versão 2 dessa configuração é criada e tem um status **Rascunho**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-352">Version 2 of this configuration is created and has a status of **Draft**.</span></span> <span data-ttu-id="79c7c-353">Você pode editar esta versão para ajustar o modelo de dados **Questionário**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-353">You can edit this version to adjust the **Questionnaire** data model.</span></span>

![Versões da configuração do ER editável na página Configurações](./media/er-quick-start1-model-configuration.png)

<span data-ttu-id="79c7c-355">Para obter mais informações sobre como usar versões para configurações de ER, consulte [Visão geral de relatório eletrônico (ER)](general-electronic-reporting.md#component-versioning).</span><span class="sxs-lookup"><span data-stu-id="79c7c-355">For more information about versioning for ER configurations, see [Electronic reporting (ER) overview](general-electronic-reporting.md#component-versioning).</span></span>

> [!NOTE]
> <span data-ttu-id="79c7c-356">O modelo de dados configurado é sua representação abstrata do domínio comercial de **Questionário** e não contém relações para artefatos que são específicos do Microsoft Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="79c7c-356">The configured data model is your abstract representation of the **Questionnaire** business domain and contains no relations to artefacts that are specific to Microsoft Dynamics 365 Finance.</span></span>

## <a name="design-a-model-mapping-for-the-configured-data-model"></a><a name="DesignMapping"></a><span data-ttu-id="79c7c-357">Criar um mapeamento de modelo para o modelo de dados configurado</span><span class="sxs-lookup"><span data-stu-id="79c7c-357">Design a model mapping for the configured data model</span></span>

<span data-ttu-id="79c7c-358">Como um usuário na função de desenvolvedor de relatório eletrônico, você deve criar uma nova configuração ER contendo um componente de [mapeamento de modelos](general-electronic-reporting.md#data-model-and-model-mapping-components) o modelo de dados **Questionário**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-358">As a user in the Electronic Reporting Developer role, you must create a new ER configuration that contains a [model mapping](general-electronic-reporting.md#data-model-and-model-mapping-components) component for the **Questionnaire** data model.</span></span> <span data-ttu-id="79c7c-359">Como esse componente implementa o modelo de dados configurado para o Finance, ele é específico do Finance.</span><span class="sxs-lookup"><span data-stu-id="79c7c-359">Because this component implements the configured data model for Finance, it's Finance-specific.</span></span> <span data-ttu-id="79c7c-360">Você deve configurar o componente de mapeamento de modelos para especificar os objetos de aplicativo que devem ser usados para preencher o modelo de dados configurado com os dados do aplicativo no tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="79c7c-360">You must configure the model mapping component to specify the application objects that must be used to fill in the configured data model with application data at runtime.</span></span> <span data-ttu-id="79c7c-361">Para concluir essa tarefa, você deve estar ciente dos detalhes da implementação da estrutura de dados do domínio comercial **Questionário** no Finance.</span><span class="sxs-lookup"><span data-stu-id="79c7c-361">To complete this task, you must be aware of the implementation details of the data structure of the **Questionnaire** business domain in Finance.</span></span>

<span data-ttu-id="79c7c-362">Ao concluir as etapas na seção [Importar uma nova configuração de mapeamento de modelo](#ImportModelMapping) a seguir, você pode importar a configuração de mapeamento de modelo necessário a partir do arquivo XML fornecido.</span><span class="sxs-lookup"><span data-stu-id="79c7c-362">By completing the steps in the [Import a new model mapping configuration](#ImportModelMapping) section that follows, you can import the required model mapping configuration from the provided XML file.</span></span> <span data-ttu-id="79c7c-363">Como alternativa, você pode concluir as etapas na seção [Criar uma nova configuração de mapeamento do modelo](#CreateModelMapping) para criar esse mapeamento de modelo do zero.</span><span class="sxs-lookup"><span data-stu-id="79c7c-363">Alternatively, you can complete the steps in the [Create a new model mapping configuration](#CreateModelMapping) section to design this model mapping from scratch.</span></span>

### <a name="import-a-new-model-mapping-configuration"></a><a name="ImportModelMapping"></a><span data-ttu-id="79c7c-364">Importar uma nova configuração de mapeamento de modelo</span><span class="sxs-lookup"><span data-stu-id="79c7c-364">Import a new model mapping configuration</span></span>

1. <span data-ttu-id="79c7c-365">Baixe o arquivo [Questionnaires mapping.version.1.1.xml](https://go.microsoft.com/fwlink/?linkid=851448) e salve-o no computador local.</span><span class="sxs-lookup"><span data-stu-id="79c7c-365">Download the [Questionnaires mapping.version.1.1.xml](https://go.microsoft.com/fwlink/?linkid=851448) file, and save it to your local computer.</span></span>
2. <span data-ttu-id="79c7c-366">Vá para **Administração da organização** \> **Espaços de trabalho** \> **Relatório eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-366">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
3. <span data-ttu-id="79c7c-367">No espaço de trabalho **Relatório eletrônico**, selecione **Configurações de relatórios**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-367">In the **Electronic reporting** workspace, select **Reporting configurations**.</span></span>
4. <span data-ttu-id="79c7c-368">No Painel de Ação, selecione **Câmbio** \> **Carregar de arquivo XML**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-368">On the Action Pane, select **Exchange** \> **Load from XML file**.</span></span>
5. <span data-ttu-id="79c7c-369">Selecione **Procurar** e, depois, localize e selecione o arquivo **Questionnaires mapping.version.1.1.xml**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-369">Select **Browse**, and then find and select the **Questionnaires mapping.version.1.1.xml** file.</span></span>
6. <span data-ttu-id="79c7c-370">Selecione **OK** para importar a configuração.</span><span class="sxs-lookup"><span data-stu-id="79c7c-370">Select **OK** to import the configuration.</span></span>

<span data-ttu-id="79c7c-371">Para continuar, ignore o próximo procedimento, [Criar uma nova configuração de mapeamento de modelo](#CreateModelMapping).</span><span class="sxs-lookup"><span data-stu-id="79c7c-371">To continue, skip the next procedure, [Create a new model mapping configuration](#CreateModelMapping).</span></span>

### <a name="create-a-new-model-mapping-configuration"></a><a name="CreateModelMapping"></a><span data-ttu-id="79c7c-372">Criar uma nova configuração de mapeamento de modelo</span><span class="sxs-lookup"><span data-stu-id="79c7c-372">Create a new model mapping configuration</span></span>

1. <span data-ttu-id="79c7c-373">Vá para **Administração da organização** \> **Relatório eletrônico** \> **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-373">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="79c7c-374">Na página **Configurações**, na árvore de configurações, selecione **Modelo de questionário**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-374">On the **Configurations** page, in the configuration tree, select **Questionnaire model**.</span></span>
3. <span data-ttu-id="79c7c-375">Selecione **Criar configuração**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-375">Select **Create configuration**.</span></span>
4. <span data-ttu-id="79c7c-376">Na caixa de diálogo suspensa, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="79c7c-376">In the drop-down dialog box, follow these steps:</span></span>

    1. <span data-ttu-id="79c7c-377">No campo **Novo**, selecione **Mapeamento de modelo baseado no modelo de dados Questionários**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-377">In the **New** field, select **Model Mapping based on data model Questionnaires**.</span></span>
    2. <span data-ttu-id="79c7c-378">No campo **Nome**, insira **Mapeamento de questionário**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-378">In the **Name** field, enter **Questionnaire mapping**.</span></span>
    3. <span data-ttu-id="79c7c-379">No campo **Definição do modelo de dados**, selecione a definição **Raiz**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-379">In the **Data model definition** field, select the **Root** definition.</span></span>
    4. <span data-ttu-id="79c7c-380">Selecione **Criar configuração** para criar a configuração.</span><span class="sxs-lookup"><span data-stu-id="79c7c-380">Select **Create configuration** to create the configuration.</span></span>

#### <a name="design-a-new-model-mapping-component"></a><a name="DesignMappingComponent"></a><span data-ttu-id="79c7c-381">Criar um novo componente de mapeamento de modelos</span><span class="sxs-lookup"><span data-stu-id="79c7c-381">Design a new model mapping component</span></span>

1. <span data-ttu-id="79c7c-382">Na página **Configurações**, na árvore de configurações, selecione **Mapeamento de questionário**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-382">On the **Configurations** page, in the configuration tree, select **Questionnaire mapping**.</span></span>
2. <span data-ttu-id="79c7c-383">Selecione **Designer** para abrir a lista de mapeamentos.</span><span class="sxs-lookup"><span data-stu-id="79c7c-383">Select **Designer** to open the list of mappings.</span></span>
3. <span data-ttu-id="79c7c-384">Selecione o mapeamento **Mapeamento de questionários** que foi adicionado automaticamente à definição **Raiz**</span><span class="sxs-lookup"><span data-stu-id="79c7c-384">Select the **Questionnaires mapping** mapping that was automatically added for the **Root** definition</span></span>
4. <span data-ttu-id="79c7c-385">Selecione **Designer** começar a configurar o mapeamento selecionado.</span><span class="sxs-lookup"><span data-stu-id="79c7c-385">Select **Designer** to start to configure the selected mapping.</span></span>

<span data-ttu-id="79c7c-386">Um novo mapeamento é adicionado automaticamente à definição **Raiz**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-386">A new mapping is automatically added for the **Root** definition.</span></span> <span data-ttu-id="79c7c-387">Esse mapeamento tem a direção **Para modelo**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-387">This mapping has the **To model** direction.</span></span> <span data-ttu-id="79c7c-388">Portanto, esse mapeamento pode ser usado para preencher um modelo de dados com os dados necessários.</span><span class="sxs-lookup"><span data-stu-id="79c7c-388">Therefore, this mapping can be used to fill in a data model with required data.</span></span>

#### <a name="add-data-sources-to-access-application-tables"></a><a name="AddMmDataSource1"></a><span data-ttu-id="79c7c-389">Adicionar fontes de dados para acessar tabelas de aplicativos</span><span class="sxs-lookup"><span data-stu-id="79c7c-389">Add data sources to access application tables</span></span>

<span data-ttu-id="79c7c-390">Você deve configurar fontes de dados para acessar as tabelas do aplicativo que contêm detalhes do questionário.</span><span class="sxs-lookup"><span data-stu-id="79c7c-390">You must configure data sources to access the application tables that contain questionnaire details.</span></span>

1. <span data-ttu-id="79c7c-391">Na página **Designer de mapeamento de modelo**, no painel **Tipos de fontes de dados**, selecione **Dynamics 365 for Operations\\Registros de tabela**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-391">On the **Model mapping designer** page, in the **Data source types** pane, select **Dynamics 365 for Operations\\Table records**.</span></span>
2. <span data-ttu-id="79c7c-392">Adicione uma nova fonte de dados que será usada para acessar a tabela KMCollection, em que cada registro representa um único questionário:</span><span class="sxs-lookup"><span data-stu-id="79c7c-392">Add a new data source that will be used to access the KMCollection table, where every record represents a single questionnaire:</span></span>

    1. <span data-ttu-id="79c7c-393">No painel **Fontes de dados**, selecione **Adicionar raiz**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-393">In the **Data sources** pane, select **Add root**.</span></span>
    2. <span data-ttu-id="79c7c-394">Na caixa de diálogo, no campo **Nome** , insira **Questionário**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-394">In dialog box, in the **Name** field, enter **Questionnaire**.</span></span>
    3. <span data-ttu-id="79c7c-395">No campo **Tabela**, insira **KMCollection**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-395">In the **Table** field, enter **KMCollection**.</span></span>
    4. <span data-ttu-id="79c7c-396">Defina a opção **Pedir consulta** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-396">Set the **Ask for query** option to **Yes**.</span></span> <span data-ttu-id="79c7c-397">Em seguida, será possível especificar opções de [filtragem](../../fin-ops/get-started/advanced-filtering-query-options.md) dessa tabela na caixa de diálogo consulta do sistema no runtime.</span><span class="sxs-lookup"><span data-stu-id="79c7c-397">You will then be able to specify [filtering](../../fin-ops/get-started/advanced-filtering-query-options.md) options for this table in the system query dialog box at runtime.</span></span>
    5. <span data-ttu-id="79c7c-398">Selecione **OK** para adicionar a nova fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="79c7c-398">Select **OK** to add the new data source.</span></span>

3. <span data-ttu-id="79c7c-399">No painel **Tipos de fonte de dados**, selecione **Dynamics 365 for Operations\\Registros de tabela**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-399">In the **Data source types** pane, select **Dynamics 365 for Operations\\Table records**.</span></span>
4. <span data-ttu-id="79c7c-400">Adicione uma nova fonte de dados que será usada para acessar a tabela KMQuestion, em que cada registro representa uma única pergunta em um questionário:</span><span class="sxs-lookup"><span data-stu-id="79c7c-400">Add a new data source that will be used to access the KMQuestion table, where every record represents a single question in a questionnaire:</span></span>

    1. <span data-ttu-id="79c7c-401">No painel **Fontes de dados**, selecione **Adicionar raiz**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-401">In the **Data sources** pane, select **Add root**.</span></span>
    2. <span data-ttu-id="79c7c-402">Na caixa de diálogo, no campo **Nome** , insira **Pergunta**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-402">In the dialog box, in the **Name** field, enter **Question**.</span></span>
    3. <span data-ttu-id="79c7c-403">No campo **Tabela**, insira **KMQuestion**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-403">In the **Table** field, enter **KMQuestion**.</span></span>
    4. <span data-ttu-id="79c7c-404">Selecione **OK** para adicionar a nova fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="79c7c-404">Select **OK** to add the new data source.</span></span>

5. <span data-ttu-id="79c7c-405">No painel **Tipos de fonte de dados**, selecione **Dynamics 365 for Operations\\Registros de tabela**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-405">In the **Data source types** pane, select **Dynamics 365 for Operations\\Table records**.</span></span>
6. <span data-ttu-id="79c7c-406">Adicione uma nova fonte de dados que será usada para acessar a tabela KMAnswer, em que cada registro representa uma única resposta a uma pergunta em um questionário:</span><span class="sxs-lookup"><span data-stu-id="79c7c-406">Add a new data source try that will be used to access the KMAnswer table, where every record represents a single answer to a question in a questionnaire:</span></span>

    1. <span data-ttu-id="79c7c-407">No painel **Fontes de dados**, selecione **Adicionar raiz**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-407">In the **Data sources** pane, select **Add root**.</span></span>
    2. <span data-ttu-id="79c7c-408">No campo **Nome**, insira **Resposta**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-408">In the **Name** field, enter **Answer**.</span></span>
    3. <span data-ttu-id="79c7c-409">No campo **Tabela**, insira **KMAnswer**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-409">In the **Table** field, enter **KMAnswer**.</span></span>
    4. <span data-ttu-id="79c7c-410">Selecione **OK** para adicionar a nova fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="79c7c-410">Select **OK** to add the new data source.</span></span>

7. <span data-ttu-id="79c7c-411">No painel **Tipos de fonte de dados**, selecione **Funções\\Campo calculado**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-411">In the **Data source types** pane, select **Functions\\Calculated field**.</span></span>
8. <span data-ttu-id="79c7c-412">Adicione um novo campo calculado que será usado para acessar um registro da tabela KMQuestionResultGroup a partir de cada registro da tabela KMCollection pai:</span><span class="sxs-lookup"><span data-stu-id="79c7c-412">Add a new calculated field that will be used to access a record of the KMQuestionResultGroup table from every record of the parent KMCollection table:</span></span>

    1. <span data-ttu-id="79c7c-413">No painel **Fontes de dados**, selecione **Questionário**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-413">In the **Data sources** pane, select **Questionnaire**.</span></span>
    2. <span data-ttu-id="79c7c-414">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-414">Select **Add**.</span></span>
    3. <span data-ttu-id="79c7c-415">Na caixa de diálogo, no campo **Nome** , insira **\$ResultGroup**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-415">In the dialog box, in the **Name** field, enter **\$ResultGroup**.</span></span>
    4. <span data-ttu-id="79c7c-416">Selecione **Editar fórmula**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-416">Select **Edit formula**.</span></span>
    5. <span data-ttu-id="79c7c-417">No [Editor de fórmula ER](general-electronic-reporting-formula-designer.md), no campo **Fórmula**, insira **FIRSTORNULL(\@."\<Relations'.KMQuestionResultGroup)** para usar o [caminho](er-formula-language.md#paths) da relação um para muitos entre as tabelas KMCollection e KMQuestionResultGroup.</span><span class="sxs-lookup"><span data-stu-id="79c7c-417">In the [ER formula editor](general-electronic-reporting-formula-designer.md), in the **Formula** field, enter **FIRSTORNULL(\@.'\<Relations'.KMQuestionResultGroup)** to use the [path](er-formula-language.md#paths) of the one-to-many relation between the KMCollection and KMQuestionResultGroup tables.</span></span>
    6. <span data-ttu-id="79c7c-418">Selecione **Salvar** e feche o editor de fórmula.</span><span class="sxs-lookup"><span data-stu-id="79c7c-418">Select **Save**, and close the formula editor.</span></span>
    7. <span data-ttu-id="79c7c-419">Selecione **OK** para adicionar o novo campo calculado.</span><span class="sxs-lookup"><span data-stu-id="79c7c-419">Select **OK** to add the new calculated field.</span></span>

9. <span data-ttu-id="79c7c-420">No painel **Tipos de fonte de dados**, selecione **Funções\\Campo calculado**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-420">In the **Data source types** pane, select **Functions\\Calculated field**.</span></span>
10. <span data-ttu-id="79c7c-421">Adicione um novo campo calculado que será usado para acessar registros de perguntas da tabela KMQuestion a partir de cada registro da tabela KMCollectionQuestion pai:</span><span class="sxs-lookup"><span data-stu-id="79c7c-421">Add a new calculated field that will be used to access question records of the KMQuestion table from every record of the parent KMCollectionQuestion table:</span></span>

    1. <span data-ttu-id="79c7c-422">No painel **Fontes de dados**, selecione **Questionário**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-422">In the **Data sources** pane, select **Questionnaire**.</span></span>
    2. <span data-ttu-id="79c7c-423">Expanda o nó **\<Relações** que contém relações um para muitos da tabela KMCollection.</span><span class="sxs-lookup"><span data-stu-id="79c7c-423">Expand the **\<Relations** node that contains one-to-many relations of the KMCollection table.</span></span>
    3. <span data-ttu-id="79c7c-424">Selecione a tabela **KMCollectionQuestion** relacionada e selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-424">Select the related **KMCollectionQuestion** table, and then select **Add**.</span></span>
    4. <span data-ttu-id="79c7c-425">Na caixa de diálogo, no campo **Nome** , insira **\$Pergunta**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-425">In the dialog box, in the **Name** field, enter **\$Question**.</span></span>
    5. <span data-ttu-id="79c7c-426">Selecione **Editar fórmula**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-426">Select **Edit formula**.</span></span>
    6. <span data-ttu-id="79c7c-427">No editor de fórmulas, no campo **Fórmula**, insira **FILTER(Question, Question.kmQuestionId = \@.kmQuestionId)** para retornar os registros de pergunta apropriados da tabela KMQuestion.</span><span class="sxs-lookup"><span data-stu-id="79c7c-427">In the formula editor, in the **Formula** field, enter **FIRSTORNULL (FILTER(Question, Question.kmQuestionId = \@.kmQuestionId))** to return the appropriate question records from the KMQuestion table.</span></span>
    7. <span data-ttu-id="79c7c-428">Selecione **Salvar** e feche o editor de fórmula.</span><span class="sxs-lookup"><span data-stu-id="79c7c-428">Select **Save**, and close the formula editor.</span></span>
    8. <span data-ttu-id="79c7c-429">Selecione **OK** para adicionar o novo campo calculado.</span><span class="sxs-lookup"><span data-stu-id="79c7c-429">Select **OK** to add the new calculated field.</span></span>

11. <span data-ttu-id="79c7c-430">No painel **Tipos de fonte de dados**, selecione **Funções\\Campo calculado**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-430">In the **Data source types** pane, select **Functions\\Calculated field**.</span></span>
12. <span data-ttu-id="79c7c-431">Adicione um novo campo calculado que será usado para acessar registros de resposta da tabela KMAnswer a partir de cada registro da tabela KMQuestion pai:</span><span class="sxs-lookup"><span data-stu-id="79c7c-431">Add a new calculated field that will be used to access answer records of the KMAnswer table from every record of the parent KMQuestion table:</span></span>

    1. <span data-ttu-id="79c7c-432">No painel **Fontes de dados**, selecione **Questionário.\<Relations.KMCollectionQuestion.\$Pergunta** e selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-432">In the **Data sources** pane, select **Questionnaire.\<Relations.KMCollectionQuestion.\$Question**, and then select **Add**.</span></span>
    2. <span data-ttu-id="79c7c-433">Na caixa de diálogo, no campo **Nome** , insira **\$Resposta**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-433">In the dialog box, in the **Name** field, enter **\$Answer**.</span></span>
    3. <span data-ttu-id="79c7c-434">Selecione **Editar fórmula**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-434">Select **Edit formula**.</span></span>
    4. <span data-ttu-id="79c7c-435">No editor de fórmulas, no campo **Fórmula**, insira **FILTER (Answer, Answer.kmAnswerCollectionId = \@.kmAnswerCollectionId)** para retornar os registros de resposta apropriados da tabela KMAnswer.</span><span class="sxs-lookup"><span data-stu-id="79c7c-435">In the formula editor, in the **Formula** field, enter **FILTER (Answer, Answer.kmAnswerCollectionId = \@.kmAnswerCollectionId)** to return the appropriate answer records from the KMAnswer table.</span></span>
    5. <span data-ttu-id="79c7c-436">Selecione **Salvar** e feche o editor de fórmula.</span><span class="sxs-lookup"><span data-stu-id="79c7c-436">Select **Save**, and close the formula editor.</span></span>
    6. <span data-ttu-id="79c7c-437">Selecione **OK** para adicionar o novo campo calculado.</span><span class="sxs-lookup"><span data-stu-id="79c7c-437">Select **OK** to add the new calculated field.</span></span>

13. <span data-ttu-id="79c7c-438">No painel **Tipos de fonte de dados**, selecione **Dynamics 365 for Operations\\Tabela**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-438">In the **Data source types** pane, select **Dynamics 365 for Operations\\Table**.</span></span>
14. <span data-ttu-id="79c7c-439">Adicione uma nova fonte de dados que será usada para acessar métodos da tabela CompanyInfo.</span><span class="sxs-lookup"><span data-stu-id="79c7c-439">Add a new data source that will be used to access methods of the CompanyInfo table.</span></span> <span data-ttu-id="79c7c-440">Observe que o método **find()** dessa tabela retorna um registro que representa uma empresa da atual instância de Finanças que este mapeamento é chamado nesse contexto.</span><span class="sxs-lookup"><span data-stu-id="79c7c-440">Note that the **find()** method of this table returns a record that represents a company of the current Finance instance that this mapping is called in the context of.</span></span>

    1. <span data-ttu-id="79c7c-441">No painel **Fontes de dados**, selecione **Adicionar raiz**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-441">In the **Data sources** pane, select **Add root**.</span></span>
    2. <span data-ttu-id="79c7c-442">Na caixa de diálogo, no campo **Nome** , insira **CompanyInfo**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-442">In the dialog box, in the **Name** field, enter **CompanyInfo**.</span></span>
    3. <span data-ttu-id="79c7c-443">No campo **Tabela**, insira **CompanyInfo**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-443">In the **Table** field, enter **CompanyInfo**.</span></span>
    4. <span data-ttu-id="79c7c-444">Selecione **OK** para adicionar a nova fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="79c7c-444">Select **OK** to add the new data source.</span></span>

#### <a name="add-data-sources-to-access-application-enumerations"></a><a name="AddMmDataSource2"></a><span data-ttu-id="79c7c-445">Adicionar fontes de dados para acessar enumerações de aplicativos</span><span class="sxs-lookup"><span data-stu-id="79c7c-445">Add data sources to access application enumerations</span></span>

<span data-ttu-id="79c7c-446">Você deve configurar fontes de dados para acessar enumerações de aplicativos e comparar valores com os valores dos campos do tipo **Enumeração** nas tabelas de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="79c7c-446">You must configure data sources to access application enumerations and compare their values with values of fields of the **Enumeration** type in the application tables.</span></span> <span data-ttu-id="79c7c-447">Você deve usar o resultado da comparação para preencher os campos adequados do modelo de dados.</span><span class="sxs-lookup"><span data-stu-id="79c7c-447">You must use the result of the comparison to fill in appropriate fields of the data model.</span></span>

1. <span data-ttu-id="79c7c-448">Na página **Designer de mapeamento de modelo**, no painel **Tipos de fontes de dados**, selecione **Dynamics 365 for Operations\\Enumeração**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-448">On the **Model mapping designer** page, in the **Data source types** pane, select **Dynamics 365 for Operations\\Enumeration**.</span></span>
2. <span data-ttu-id="79c7c-449">Adicione uma nova fonte de dados que será usada para acessar valores da enumeração **EnumAppNoYes**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-449">Add a new data source that will be used to access values of the **EnumAppNoYes** enumeration:</span></span>

    1. <span data-ttu-id="79c7c-450">No painel **Fontes de dados**, selecione **Adicionar raiz**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-450">In the **Data sources** pane, select **Add root**.</span></span>
    2. <span data-ttu-id="79c7c-451">Na caixa de diálogo, no campo **Nome** , insira **EnumAppNoYes**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-451">In the dialog box, in the **Name** field, enter **EnumAppNoYes**.</span></span>
    3. <span data-ttu-id="79c7c-452">No campo **Enumeração**, insira **NoYes**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-452">In the **Enumeration** field, enter **NoYes**.</span></span>
    4. <span data-ttu-id="79c7c-453">Selecione **OK** para adicionar a nova fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="79c7c-453">Select **OK** to add the new data source.</span></span>

3. <span data-ttu-id="79c7c-454">No painel **Tipos de fonte de dados**, selecione **Dynamics 365 for Operations\\Enumeração**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-454">In the **Data source types** pane, select **Dynamics 365 for Operations\\Enumeration**.</span></span>
4. <span data-ttu-id="79c7c-455">Adicione uma nova fonte de dados que será usada para acessar os valores da enumeração **KMCollectionQuestionMode**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-455">Add a new data source that will be used to access the values of the **KMCollectionQuestionMode** enumeration:</span></span>

    1. <span data-ttu-id="79c7c-456">No painel **Fontes de dados**, selecione **Adicionar raiz**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-456">In the **Data sources** pane, select **Add root**.</span></span>
    2. <span data-ttu-id="79c7c-457">Na caixa de diálogo, no campo **Nome**, insira **EnumAppQuestionOrder**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-457">In the dialog box, in the **Name** field, enter **EnumAppQuestionOrder**.</span></span>
    3. <span data-ttu-id="79c7c-458">No campo **Enumeração**, insira **KMCollectionQuestionMode**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-458">In the **Enumeration** field, enter **KMCollectionQuestionMode**.</span></span>
    4. <span data-ttu-id="79c7c-459">Selecione **OK** para adicionar a nova fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="79c7c-459">Select **OK** to add the new data source.</span></span>

#### <a name="add-er-labels-to-generate-a-report-in-a-specified-language"></a><a name="AddMmLabels"></a><span data-ttu-id="79c7c-460">Adicionar rótulos de ER para gerar um relatório em um idioma especificado</span><span class="sxs-lookup"><span data-stu-id="79c7c-460">Add ER labels to generate a report in a specified language</span></span>

<span data-ttu-id="79c7c-461">Você pode adicionar rótulos de ER para configurar algumas fontes de dados para retornar valores que dependam do idioma definido no contexto da chamada do mapeamento de modelos.</span><span class="sxs-lookup"><span data-stu-id="79c7c-461">You can add ER labels to configure some of your data sources to return values that depend on the language that is defined in the context of the model mapping's call.</span></span>

1. <span data-ttu-id="79c7c-462">Na página **Designer de mapeamento de modelo**, no painel **Fontes de dados**, selecione **Responder** e **Editar**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-462">On the **Model mapping designer** page, in the **Data sources** pane, select **Answer**, and then select **Edit**.</span></span>
2. <span data-ttu-id="79c7c-463">Ative o campo **Rótulo**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-463">Activate the **Label** field.</span></span>
3. <span data-ttu-id="79c7c-464">Selecione **Traduzir**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-464">Select **Translate**.</span></span>
4. <span data-ttu-id="79c7c-465">Na caixa de diálogo **Tradução de texto**, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="79c7c-465">In the **Text translation** dialog box, follow these steps:</span></span>

    1. <span data-ttu-id="79c7c-466">No campo **Id do rótulo**, insira **PositiveAnswer**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-466">In the **Label Id** field, enter **PositiveAnswer**.</span></span>
    2. <span data-ttu-id="79c7c-467">No campo **Texto no idioma padrão**, insira **Sim**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-467">In the **Text in default language** field, enter **Yes**.</span></span>
    3. <span data-ttu-id="79c7c-468">Selecione **Traduzir**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-468">Select **Translate**.</span></span>
    4. <span data-ttu-id="79c7c-469">No campo **Id do rótulo**, digite **NegativeAnswer**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-469">In the **Label Id** field, enter **NegativeAnswer**.</span></span>
    5. <span data-ttu-id="79c7c-470">No campo **Texto no idioma padrão**, insira **Não**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-470">In the **Text in default language** field, enter **No**.</span></span>
    6. <span data-ttu-id="79c7c-471">Selecione **Traduzir**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-471">Select **Translate**.</span></span>

5. <span data-ttu-id="79c7c-472">Feche a caixa de diálogo **Tradução de texto**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-472">Close the **Text translation** dialog box.</span></span>
6. <span data-ttu-id="79c7c-473">Selecione **Cancelar**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-473">Select **Cancel**.</span></span>

![Adição de rótulos de ER para o mapeamento de modelo editável](./media/er-quick-start1-adding-labels.png)

<span data-ttu-id="79c7c-475">Você inseriu rótulos de ER somente para o idioma padrão.</span><span class="sxs-lookup"><span data-stu-id="79c7c-475">You've entered ER labels only for the default language.</span></span> <span data-ttu-id="79c7c-476">Para obter informações sobre como os rótulos ER podem ser traduzidos para outros idiomas, consulte [Criar relatórios multilíngues](er-design-multilingual-reports.md).</span><span class="sxs-lookup"><span data-stu-id="79c7c-476">For information about how ER labels can be translated into other languages, see [Design multilingual reports](er-design-multilingual-reports.md).</span></span>

#### <a name="add-a-data-source-to-transform-the-results-of-comparing-enumeration-values-to-a-text-value"></a><a name="AddMmDataSource3"></a><span data-ttu-id="79c7c-477">Adicionar uma fonte de dados para transformar os resultados da comparação de valores de enumeração em um valor de texto</span><span class="sxs-lookup"><span data-stu-id="79c7c-477">Add a data source to transform the results of comparing enumeration values to a text value</span></span>

<span data-ttu-id="79c7c-478">Como você deve transformar os resultados da comparação entre valores de enumeração e valores de texto várias vezes para diferentes fontes, convém configurar essa lógica como uma única fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="79c7c-478">Because you must transform the results of the comparison between enumeration values and text values several times for difference sources, it's a good idea to configure this logic as a single data source.</span></span> <span data-ttu-id="79c7c-479">No entanto, para tornar essa fonte de dados reutilizável, você deve configurá-la como a fonte de dados parametrizada.</span><span class="sxs-lookup"><span data-stu-id="79c7c-479">However, to make this data source reusable, you must then configure it as the parametrized data source.</span></span> <span data-ttu-id="79c7c-480">Para obter mais informações, consulte [Suporte a chamadas parametrizadas de fontes de dados do ER do tipo do campo Calculado](er-calculated-field-type.md).</span><span class="sxs-lookup"><span data-stu-id="79c7c-480">For more information, see [Support parameterized calls of ER data sources of the Calculated field type](er-calculated-field-type.md).</span></span>

1. <span data-ttu-id="79c7c-481">Na página **Designer de mapeamento de modelo**, no painel **Tipos de fontes de dados**, selecione **Geral\\Contêiner vazio**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-481">On the **Model mapping designer** page, in the **Data source types** pane, select **General\\Empty container**.</span></span>
2. <span data-ttu-id="79c7c-482">Adicionar uma nova fonte de dados de contêiner:</span><span class="sxs-lookup"><span data-stu-id="79c7c-482">Add a new container data source:</span></span>

    1. <span data-ttu-id="79c7c-483">No painel **Fontes de dados**, selecione **Adicionar raiz**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-483">In the **Data sources** pane, select **Add root**.</span></span>
    2. <span data-ttu-id="79c7c-484">Na caixa de diálogo, no campo **Nome** , insira **Auxiliar**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-484">In the dialog box, in the **Name** field, enter **Helper**.</span></span>
    3. <span data-ttu-id="79c7c-485">Selecione **OK** para adicionar a nova fonte de dados de contêiner.</span><span class="sxs-lookup"><span data-stu-id="79c7c-485">Select **OK** to add the new container data source.</span></span>

3. <span data-ttu-id="79c7c-486">No painel **Tipos de fonte de dados**, selecione **Funções\\Campo calculado**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-486">In the **Data source types** pane, select **Functions\\Calculated field**.</span></span>
4. <span data-ttu-id="79c7c-487">Adicionar uma nova fonte de dados:</span><span class="sxs-lookup"><span data-stu-id="79c7c-487">Add a new data source:</span></span>

    1. <span data-ttu-id="79c7c-488">No painel **Fontes de dados**, selecione **Auxiliar**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-488">In the **Data sources** pane, select **Helper**.</span></span>
    2. <span data-ttu-id="79c7c-489">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-489">Select **Add**.</span></span>
    3. <span data-ttu-id="79c7c-490">Na caixa de diálogo suspensa, no campo **Nome** , insira **NoYesEnumToString**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-490">In the dialog box, in the **Name** field, enter **NoYesEnumToString**.</span></span>
    4. <span data-ttu-id="79c7c-491">Selecione **Editar fórmula**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-491">Select **Edit formula**.</span></span>
    5. <span data-ttu-id="79c7c-492">No editor de fórmulas, selecione **Parâmetros**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-492">In the formula editor, select **Parameters**.</span></span>
    6. <span data-ttu-id="79c7c-493">Siga estas etapas para especificar parâmetros para a expressão configurada:</span><span class="sxs-lookup"><span data-stu-id="79c7c-493">Follow these steps to specify parameters for the configured expression:</span></span>

        1. <span data-ttu-id="79c7c-494">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-494">Select **New**.</span></span>
        2. <span data-ttu-id="79c7c-495">Na caixa de diálogo, no campo **Nome** , insira **Argumento**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-495">In the dialog box, in the **Name** field, enter **Argument**.</span></span>
        3. <span data-ttu-id="79c7c-496">No campo **Tipo**, selecione o tipo de dados **Booliano**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-496">In the **Type** field, select the **Boolean** data type.</span></span>
        4. <span data-ttu-id="79c7c-497">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-497">Select **OK**.</span></span>

    7. <span data-ttu-id="79c7c-498">No campo **Fórmula**, insira **IF (Argument = true, \@"GER\_LABEL:PositiveAnswer", \@"GER\_LABEL:NegativeAnswer")** para retornar o texto do rótulo de ER apropriado, dependendo do idioma do contexto de execução e do valor do parâmetro especificado.</span><span class="sxs-lookup"><span data-stu-id="79c7c-498">In the **Formula** field, enter **IF (Argument = true, \@"GER\_LABEL:PositiveAnswer", \@"GER\_LABEL:NegativeAnswer")** to return the text of the appropriate ER label, depending on the language of the execution context and value of the specified parameter.</span></span>
    8. <span data-ttu-id="79c7c-499">Selecione **Salvar** e feche o editor de fórmula.</span><span class="sxs-lookup"><span data-stu-id="79c7c-499">Select **Save**, and close the formula editor.</span></span>
    9. <span data-ttu-id="79c7c-500">Selecione **OK** para adicionar a nova fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="79c7c-500">Select **OK** to add the new data source.</span></span>

![Mapeamento de modelo configurado no designer de mapeamento de modelos do ER](./media/er-quick-start1-added-data-sources.png)

#### <a name="bind-data-sources-to-data-model-fields"></a><a name="AddMmBindings1"></a><span data-ttu-id="79c7c-502">Associar fontes de dados a campos do modelo de dados</span><span class="sxs-lookup"><span data-stu-id="79c7c-502">Bind data sources to data model fields</span></span>

<span data-ttu-id="79c7c-503">Você deve vincular fontes de dados configuradas aos campos do modelo de dados para especificar como o modelo de dados será preenchido com os dados do aplicativo no tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="79c7c-503">You must bind the configured data sources to the fields of the data model to specify how the data model will by filled in with application data at runtime.</span></span>

1. <span data-ttu-id="79c7c-504">Na página **Designer de mapeamento de modelo**, no painel **Modelo de dados**, selecione **CompanyName**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-504">On the **Model mapping designer** page, in the **Data model** pane, select **CompanyName**.</span></span>
2. <span data-ttu-id="79c7c-505">No painel **Fontes de dados**, expanda **CompanyInfo** e siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="79c7c-505">In the **Data sources** pane, expand **CompanyInfo**, and then follow these steps:</span></span>

    1. <span data-ttu-id="79c7c-506">Expanda o nó **CompanyInfo.find()** que representa o método **find()** da tabela CompanyInfo.</span><span class="sxs-lookup"><span data-stu-id="79c7c-506">Expand the **CompanyInfo.find()** node that represents the **find()** method of the CompanyInfo table.</span></span>
    2. <span data-ttu-id="79c7c-507">Selecione **CompanyInfo.find().Name**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-507">Select **CompanyInfo.find().Name**.</span></span>
    3. <span data-ttu-id="79c7c-508">Selecione **Associar** para preencher o nome da empresa com o qual o mapeamento de modelo configurado é chamado no contexto de tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="79c7c-508">Select **Bind** to fill in the name of the company that the configured model mapping is called in the context of at runtime.</span></span>

3. <span data-ttu-id="79c7c-509">No painel **Modelo de dados**, selecione **Questionário**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-509">In the **Data model** pane, select **Questionnaire**.</span></span>
4. <span data-ttu-id="79c7c-510">No painel **Fontes de dados**, selecione **Questionário** e, depois, **Adicionar** para preencher registros de questionário.</span><span class="sxs-lookup"><span data-stu-id="79c7c-510">In the **Data sources** pane, select **Questionnaire**, and then select **Bind** to fill in questionnaire records.</span></span>
5. <span data-ttu-id="79c7c-511">No painel **Modelo de dados**, expanda **Questionário** e siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="79c7c-511">In the **Data model** pane, expand **Questionnaire**, and then follow these steps:</span></span>

    1. <span data-ttu-id="79c7c-512">No painel **Modelo de dados**, selecione **Ativo**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-512">In the **Data model** pane, select **Active**.</span></span>
    2. <span data-ttu-id="79c7c-513">No painel **Modelo de dados**, selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-513">In the **Data model** pane, select **Edit**.</span></span>
    3. <span data-ttu-id="79c7c-514">No campo **Fórmula**, insira **Helper.NoYesEnumToString (\@.Active = EnumAppNoYes.Yes)** para preencher o resultado dependente de texto e dependente do idioma da comparação entre valores de enumeração.</span><span class="sxs-lookup"><span data-stu-id="79c7c-514">In the **Formula** field, enter **Helper.NoYesEnumToString (\@.Active = EnumAppNoYes.Yes)** to fill the text-dependent and language-dependent result of the comparison between enumeration values.</span></span>

6. <span data-ttu-id="79c7c-515">Continue a associar fontes de dados a campos de modelo de dados da mesma maneira até atingir o resultado a seguir.</span><span class="sxs-lookup"><span data-stu-id="79c7c-515">Continue to bind data sources to data model fields in the same manner until you achieve the following result.</span></span>

    | <span data-ttu-id="79c7c-516">Caminho do campo</span><span class="sxs-lookup"><span data-stu-id="79c7c-516">Field path</span></span>                                              | <span data-ttu-id="79c7c-517">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="79c7c-517">Data type</span></span>   | <span data-ttu-id="79c7c-518">Ação</span><span class="sxs-lookup"><span data-stu-id="79c7c-518">Action</span></span> | <span data-ttu-id="79c7c-519">Expressão de associação</span><span class="sxs-lookup"><span data-stu-id="79c7c-519">Binding expression</span></span> |
    |---------------------------------------------------------|-------------|--------|--------------------|
    | <span data-ttu-id="79c7c-520">CompanyName</span><span class="sxs-lookup"><span data-stu-id="79c7c-520">CompanyName</span></span>                                             | <span data-ttu-id="79c7c-521">Sequência de caracteres</span><span class="sxs-lookup"><span data-stu-id="79c7c-521">String</span></span>      | <span data-ttu-id="79c7c-522">Associar</span><span class="sxs-lookup"><span data-stu-id="79c7c-522">Bind</span></span>   | <span data-ttu-id="79c7c-523">CompanyInfo.'find()'.Name</span><span class="sxs-lookup"><span data-stu-id="79c7c-523">CompanyInfo.'find()'.Name</span></span> |
    | <span data-ttu-id="79c7c-524">Questionário</span><span class="sxs-lookup"><span data-stu-id="79c7c-524">Questionnaire</span></span>                                           | <span data-ttu-id="79c7c-525">Registrar lista</span><span class="sxs-lookup"><span data-stu-id="79c7c-525">Record list</span></span> | <span data-ttu-id="79c7c-526">Associar</span><span class="sxs-lookup"><span data-stu-id="79c7c-526">Bind</span></span>   | <span data-ttu-id="79c7c-527">Questionário</span><span class="sxs-lookup"><span data-stu-id="79c7c-527">Questionnaire</span></span> |
    | <span data-ttu-id="79c7c-528">Questionário\\Ativo</span><span class="sxs-lookup"><span data-stu-id="79c7c-528">Questionnaire\\Active</span></span>                                   | <span data-ttu-id="79c7c-529">Sequência de caracteres</span><span class="sxs-lookup"><span data-stu-id="79c7c-529">String</span></span>      | <span data-ttu-id="79c7c-530">Edição</span><span class="sxs-lookup"><span data-stu-id="79c7c-530">Edit</span></span>   | <span data-ttu-id="79c7c-531">Helper.NoYesEnumToString(\@.active = EnumAppNoYes.Yes)</span><span class="sxs-lookup"><span data-stu-id="79c7c-531">Helper.NoYesEnumToString(\@.active = EnumAppNoYes.Yes)</span></span> |
    | <span data-ttu-id="79c7c-532">Questionário\\Código</span><span class="sxs-lookup"><span data-stu-id="79c7c-532">Questionnaire\\Code</span></span>                                     | <span data-ttu-id="79c7c-533">Sequência de caracteres</span><span class="sxs-lookup"><span data-stu-id="79c7c-533">String</span></span>      | <span data-ttu-id="79c7c-534">Associar</span><span class="sxs-lookup"><span data-stu-id="79c7c-534">Bind</span></span>   | <span data-ttu-id="79c7c-535">\@.kmCollectionId</span><span class="sxs-lookup"><span data-stu-id="79c7c-535">\@.kmCollectionId</span></span> |
    | <span data-ttu-id="79c7c-536">Questionário\\Descrição</span><span class="sxs-lookup"><span data-stu-id="79c7c-536">Questionnaire\\Description</span></span>                              | <span data-ttu-id="79c7c-537">Sequência de caracteres</span><span class="sxs-lookup"><span data-stu-id="79c7c-537">String</span></span>      | <span data-ttu-id="79c7c-538">Associar</span><span class="sxs-lookup"><span data-stu-id="79c7c-538">Bind</span></span>   | <span data-ttu-id="79c7c-539">\@.Description</span><span class="sxs-lookup"><span data-stu-id="79c7c-539">\@.Description</span></span> |
    | <span data-ttu-id="79c7c-540">Questionário\\QuestionnaireType</span><span class="sxs-lookup"><span data-stu-id="79c7c-540">Questionnaire\\QuestionnaireType</span></span>                        | <span data-ttu-id="79c7c-541">Sequência de caracteres</span><span class="sxs-lookup"><span data-stu-id="79c7c-541">String</span></span>      | <span data-ttu-id="79c7c-542">Associar</span><span class="sxs-lookup"><span data-stu-id="79c7c-542">Bind</span></span>   | <span data-ttu-id="79c7c-543">\@.'&gt;Relations'.kmCollectionTypeId.Description</span><span class="sxs-lookup"><span data-stu-id="79c7c-543">\@.'&gt;Relations'.kmCollectionTypeId.Description</span></span> |
    | <span data-ttu-id="79c7c-544">Questionário\\QuestionOrder</span><span class="sxs-lookup"><span data-stu-id="79c7c-544">Questionnaire\\QuestionOrder</span></span>                            | <span data-ttu-id="79c7c-545">Sequência de caracteres</span><span class="sxs-lookup"><span data-stu-id="79c7c-545">String</span></span>      | <span data-ttu-id="79c7c-546">Edição</span><span class="sxs-lookup"><span data-stu-id="79c7c-546">Edit</span></span>   | <span data-ttu-id="79c7c-547">CASE (\@.questionMode,</span><span class="sxs-lookup"><span data-stu-id="79c7c-547">CASE (\@.questionMode,</span></span><br><span data-ttu-id="79c7c-548">EnumAppQuestionOrder.Conditional, "Conditional",</span><span class="sxs-lookup"><span data-stu-id="79c7c-548">EnumAppQuestionOrder.Conditional, "Conditional",</span></span><br><span data-ttu-id="79c7c-549">EnumAppQuestionOrder.Random, "aleatório (porcentagem no questionário)",</span><span class="sxs-lookup"><span data-stu-id="79c7c-549">EnumAppQuestionOrder.Random, "Random (percentage in questionnaire)",</span></span><br><span data-ttu-id="79c7c-550">EnumAppQuestionOrder.RandomGroup, "aleatório (porcentagem no grupo de resultados)",</span><span class="sxs-lookup"><span data-stu-id="79c7c-550">EnumAppQuestionOrder.RandomGroup, "Random (percentage in result groups)",</span></span><br><span data-ttu-id="79c7c-551">EnumAppQuestionOrder.Sequence, "Sequencial",</span><span class="sxs-lookup"><span data-stu-id="79c7c-551">EnumAppQuestionOrder.Sequence, "Sequential",</span></span><br><span data-ttu-id="79c7c-552">"")</span><span class="sxs-lookup"><span data-stu-id="79c7c-552">"")</span></span> |
    | <span data-ttu-id="79c7c-553">Questionário\\ResultsGroup</span><span class="sxs-lookup"><span data-stu-id="79c7c-553">Questionnaire\\ResultsGroup</span></span>                             | <span data-ttu-id="79c7c-554">Registrar</span><span class="sxs-lookup"><span data-stu-id="79c7c-554">Record</span></span>      |        | |
    | <span data-ttu-id="79c7c-555">Questionário\\ResultsGroup\\Code</span><span class="sxs-lookup"><span data-stu-id="79c7c-555">Questionnaire\\ResultsGroup\\Code</span></span>                       | <span data-ttu-id="79c7c-556">Sequência de caracteres</span><span class="sxs-lookup"><span data-stu-id="79c7c-556">String</span></span>      | <span data-ttu-id="79c7c-557">Associar</span><span class="sxs-lookup"><span data-stu-id="79c7c-557">Bind</span></span>   | <span data-ttu-id="79c7c-558">\@.'\$ResultGroup'.kmQuestionResultGroupId</span><span class="sxs-lookup"><span data-stu-id="79c7c-558">\@.'\$ResultGroup'.kmQuestionResultGroupId</span></span> |
    | <span data-ttu-id="79c7c-559">Questionário\\ResultsGroup\\Descrição</span><span class="sxs-lookup"><span data-stu-id="79c7c-559">Questionnaire\\ResultsGroup\\Description</span></span>                | <span data-ttu-id="79c7c-560">Sequência de caracteres</span><span class="sxs-lookup"><span data-stu-id="79c7c-560">String</span></span>      | <span data-ttu-id="79c7c-561">Associar</span><span class="sxs-lookup"><span data-stu-id="79c7c-561">Bind</span></span>   | <span data-ttu-id="79c7c-562">\@.'\$ResultGroup'.description</span><span class="sxs-lookup"><span data-stu-id="79c7c-562">\@.'\$ResultGroup'.description</span></span> |
    | <span data-ttu-id="79c7c-563">Questionário\\ResultsGroup\\MaxNumberOfPoints</span><span class="sxs-lookup"><span data-stu-id="79c7c-563">Questionnaire\\ResultsGroup\\MaxNumberOfPoints</span></span>          | <span data-ttu-id="79c7c-564">Real</span><span class="sxs-lookup"><span data-stu-id="79c7c-564">Real</span></span>        | <span data-ttu-id="79c7c-565">Associar</span><span class="sxs-lookup"><span data-stu-id="79c7c-565">Bind</span></span>   | <span data-ttu-id="79c7c-566">\@.'\$ResultGroup'.maxPoint</span><span class="sxs-lookup"><span data-stu-id="79c7c-566">\@.'\$ResultGroup'.maxPoint</span></span> |
    | <span data-ttu-id="79c7c-567">Questionário\\Pergunta</span><span class="sxs-lookup"><span data-stu-id="79c7c-567">Questionnaire\\Question</span></span>                                 | <span data-ttu-id="79c7c-568">Registrar lista</span><span class="sxs-lookup"><span data-stu-id="79c7c-568">Record list</span></span> | <span data-ttu-id="79c7c-569">Associar</span><span class="sxs-lookup"><span data-stu-id="79c7c-569">Bind</span></span>   | <span data-ttu-id="79c7c-570">\@.'&lt;Relations'.KMCollectionQuestion</span><span class="sxs-lookup"><span data-stu-id="79c7c-570">\@.'&lt;Relations'.KMCollectionQuestion</span></span> |
    | <span data-ttu-id="79c7c-571">Questionário\\Pergunta\\CollectionSequenceNumber</span><span class="sxs-lookup"><span data-stu-id="79c7c-571">Questionnaire\\Question\\CollectionSequenceNumber</span></span>       | <span data-ttu-id="79c7c-572">Inteiro</span><span class="sxs-lookup"><span data-stu-id="79c7c-572">Integer</span></span>     | <span data-ttu-id="79c7c-573">Associar</span><span class="sxs-lookup"><span data-stu-id="79c7c-573">Bind</span></span>   | <span data-ttu-id="79c7c-574">\@.answerCollectionSequenceNumber</span><span class="sxs-lookup"><span data-stu-id="79c7c-574">\@.answerCollectionSequenceNumber</span></span> |
    | <span data-ttu-id="79c7c-575">Questionário\\Pergunta\\Id</span><span class="sxs-lookup"><span data-stu-id="79c7c-575">Questionnaire\\Question\\Id</span></span>                             | <span data-ttu-id="79c7c-576">Sequência de caracteres</span><span class="sxs-lookup"><span data-stu-id="79c7c-576">String</span></span>      | <span data-ttu-id="79c7c-577">Associar</span><span class="sxs-lookup"><span data-stu-id="79c7c-577">Bind</span></span>   | <span data-ttu-id="79c7c-578">\@.kmQuestionId</span><span class="sxs-lookup"><span data-stu-id="79c7c-578">\@.kmQuestionId</span></span> |
    | <span data-ttu-id="79c7c-579">Questionário\\Pergunta\\MustBeCompleted</span><span class="sxs-lookup"><span data-stu-id="79c7c-579">Questionnaire\\Question\\MustBeCompleted</span></span>                | <span data-ttu-id="79c7c-580">Sequência de caracteres</span><span class="sxs-lookup"><span data-stu-id="79c7c-580">String</span></span>      | <span data-ttu-id="79c7c-581">Edição</span><span class="sxs-lookup"><span data-stu-id="79c7c-581">Edit</span></span>   | <span data-ttu-id="79c7c-582">Helper.NoYesEnumToString(\@.mandatory = EnumAppNoYes.Yes)</span><span class="sxs-lookup"><span data-stu-id="79c7c-582">Helper.NoYesEnumToString(\@.mandatory = EnumAppNoYes.Yes)</span></span> |
    | <span data-ttu-id="79c7c-583">Questionário\\Pergunta\\PrimaryQuestion</span><span class="sxs-lookup"><span data-stu-id="79c7c-583">Questionnaire\\Question\\PrimaryQuestion</span></span>                | <span data-ttu-id="79c7c-584">Sequência de caracteres</span><span class="sxs-lookup"><span data-stu-id="79c7c-584">String</span></span>      | <span data-ttu-id="79c7c-585">Associar</span><span class="sxs-lookup"><span data-stu-id="79c7c-585">Bind</span></span>   | <span data-ttu-id="79c7c-586">\@.parentQuestionId</span><span class="sxs-lookup"><span data-stu-id="79c7c-586">\@.parentQuestionId</span></span> |
    | <span data-ttu-id="79c7c-587">Questionário\\Pergunta\\SequenceNumber</span><span class="sxs-lookup"><span data-stu-id="79c7c-587">Questionnaire\\Question\\SequenceNumber</span></span>                 | <span data-ttu-id="79c7c-588">Inteiro</span><span class="sxs-lookup"><span data-stu-id="79c7c-588">Integer</span></span>     | <span data-ttu-id="79c7c-589">Associar</span><span class="sxs-lookup"><span data-stu-id="79c7c-589">Bind</span></span>   | <span data-ttu-id="79c7c-590">\@.SequenceNumber</span><span class="sxs-lookup"><span data-stu-id="79c7c-590">\@.SequenceNumber</span></span> |
    | <span data-ttu-id="79c7c-591">Questionário\\Pergunta\\Texto</span><span class="sxs-lookup"><span data-stu-id="79c7c-591">Questionnaire\\Question\\Text</span></span>                           | <span data-ttu-id="79c7c-592">Sequência de caracteres</span><span class="sxs-lookup"><span data-stu-id="79c7c-592">String</span></span>      | <span data-ttu-id="79c7c-593">Associar</span><span class="sxs-lookup"><span data-stu-id="79c7c-593">Bind</span></span>   | <span data-ttu-id="79c7c-594">\@.'\$Question'.text</span><span class="sxs-lookup"><span data-stu-id="79c7c-594">\@.'\$Question'.text</span></span> |
    | <span data-ttu-id="79c7c-595">Questionário\\Pergunta\\Resposta</span><span class="sxs-lookup"><span data-stu-id="79c7c-595">Questionnaire\\Question\\Answer</span></span>                         | <span data-ttu-id="79c7c-596">Registrar lista</span><span class="sxs-lookup"><span data-stu-id="79c7c-596">Record list</span></span> | <span data-ttu-id="79c7c-597">Associar</span><span class="sxs-lookup"><span data-stu-id="79c7c-597">Bind</span></span>   | <span data-ttu-id="79c7c-598">\@.'\$Question'.'\$Answer'</span><span class="sxs-lookup"><span data-stu-id="79c7c-598">\@.'\$Question'.'\$Answer'</span></span> |
    | <span data-ttu-id="79c7c-599">Questionário\\Pergunta\\Resposta\\CorrectAnswer</span><span class="sxs-lookup"><span data-stu-id="79c7c-599">Questionnaire\\Question\\Answer\\CorrectAnswer</span></span>          | <span data-ttu-id="79c7c-600">Sequência de caracteres</span><span class="sxs-lookup"><span data-stu-id="79c7c-600">String</span></span>      | <span data-ttu-id="79c7c-601">Edição</span><span class="sxs-lookup"><span data-stu-id="79c7c-601">Edit</span></span>   | <span data-ttu-id="79c7c-602">Helper.NoYesEnumToString(\@.correctAnswer = EnumAppNoYes.Yes)</span><span class="sxs-lookup"><span data-stu-id="79c7c-602">Helper.NoYesEnumToString(\@.correctAnswer = EnumAppNoYes.Yes)</span></span> |
    | <span data-ttu-id="79c7c-603">Questionário\\Pergunta\\Resposta\\Pontos</span><span class="sxs-lookup"><span data-stu-id="79c7c-603">Questionnaire\\Question\\Answer\\Points</span></span>                 | <span data-ttu-id="79c7c-604">Real</span><span class="sxs-lookup"><span data-stu-id="79c7c-604">Real</span></span>        | <span data-ttu-id="79c7c-605">Associar</span><span class="sxs-lookup"><span data-stu-id="79c7c-605">Bind</span></span>   | <span data-ttu-id="79c7c-606">\@.point</span><span class="sxs-lookup"><span data-stu-id="79c7c-606">\@.point</span></span> |
    | <span data-ttu-id="79c7c-607">Questionário\\Pergunta\\Resposta\\SequenceNumber</span><span class="sxs-lookup"><span data-stu-id="79c7c-607">Questionnaire\\Question\\Answer\\SequenceNumber</span></span>         | <span data-ttu-id="79c7c-608">Inteiro</span><span class="sxs-lookup"><span data-stu-id="79c7c-608">Integer</span></span>     | <span data-ttu-id="79c7c-609">Associar</span><span class="sxs-lookup"><span data-stu-id="79c7c-609">Bind</span></span>   | <span data-ttu-id="79c7c-610">\@.sequenceNumber</span><span class="sxs-lookup"><span data-stu-id="79c7c-610">\@.sequenceNumber</span></span> |
    | <span data-ttu-id="79c7c-611">Questionário\\Pergunta\\Resposta\\Texto</span><span class="sxs-lookup"><span data-stu-id="79c7c-611">Questionnaire\\Question\\Answer\\Text</span></span>                   | <span data-ttu-id="79c7c-612">Sequência de caracteres</span><span class="sxs-lookup"><span data-stu-id="79c7c-612">String</span></span>      | <span data-ttu-id="79c7c-613">Associar</span><span class="sxs-lookup"><span data-stu-id="79c7c-613">Bind</span></span>   | <span data-ttu-id="79c7c-614">\@.text</span><span class="sxs-lookup"><span data-stu-id="79c7c-614">\@.text</span></span> |

    <span data-ttu-id="79c7c-615">A ilustração a seguir mostra o estado final do mapeamento de modelo configurado na página **Designer de mapeamento de modelo**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-615">The following illustration shows the final state of the configured model mapping on the **Model mapping designer** page.</span></span>

    ![Mapeamento de modelo totalmente configurado no designer de mapeamento de modelo do ER](./media/er-quick-start1-mapping2.png)

7. <span data-ttu-id="79c7c-617">Salve as alterações.</span><span class="sxs-lookup"><span data-stu-id="79c7c-617">Save your changes.</span></span>
8. <span data-ttu-id="79c7c-618">Feche a página **Designer de mapeamento de modelo**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-618">Close the **Model mapping designer** page.</span></span>

#### <a name="complete-the-design-of-the-model-mapping"></a><a name="CompleteModelMapping"></a><span data-ttu-id="79c7c-619">Concluir o design de mapeamento de modelo</span><span class="sxs-lookup"><span data-stu-id="79c7c-619">Complete the design of the model mapping</span></span>

1. <span data-ttu-id="79c7c-620">Vá para **Administração da organização** \> **Relatório eletrônico** \> **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-620">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="79c7c-621">Na página **Configurações**, na árvore de configurações, selecione **Mapeamento de questionário**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-621">On the **Configurations** page, in the configuration tree, select **Questionnaire mapping**.</span></span>
3. <span data-ttu-id="79c7c-622">Na FastTab **Versões**, selecione a versão de configuração com o status **Rascunho**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-622">On the **Versions** FastTab, select the configuration version that has a status of **Draft**.</span></span>
4. <span data-ttu-id="79c7c-623">Selecione **Alterar status** \> **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-623">Select **Change status** \> **Complete**.</span></span>

<span data-ttu-id="79c7c-624">O status da versão 1.1 dessa configuração é alterado de **Rascunho** para **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-624">The status of version 1.1 of this configuration is changed from **Draft** to **Completed**.</span></span> <span data-ttu-id="79c7c-625">A versão 1.1 não pode mais ser alterada.</span><span class="sxs-lookup"><span data-stu-id="79c7c-625">Version 1.1 can no longer be changed.</span></span> <span data-ttu-id="79c7c-626">Esta versão contém o mapeamento de modelo configurado e pode ser usada como base para outras configurações de ER.</span><span class="sxs-lookup"><span data-stu-id="79c7c-626">This version contains the configured model mapping and can be used as the basis for other ER configurations.</span></span> <span data-ttu-id="79c7c-627">A versão 1.2 dessa configuração é criada e tem um status **Rascunho**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-627">Version 1.2 of this configuration is created and has a status of **Draft**.</span></span> <span data-ttu-id="79c7c-628">Você pode editar esta versão para ajustar a configuração de **Mapeamento de questionário**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-628">You can edit this version to adjust the **Questionnaire mapping** configuration.</span></span>

![Versões da configuração do ER editável na página Configurações](./media/er-quick-start1-mapping-configuration.png)

> [!NOTE]
> <span data-ttu-id="79c7c-630">O mapeamento de modelo configurado é a implementação específica do Finance do modelo de dados abstratos que representa o domínio comercial de **Questionário**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-630">The configured model mapping is your Finance-specific implementation of the abstract data model that represents the **Questionnaire** business domain.</span></span>

## <a name="design-a-template-for-a-custom-report"></a><a name="DesignReportTemplate"></a><span data-ttu-id="79c7c-631">Criar um modelo para um relatório personalizado</span><span class="sxs-lookup"><span data-stu-id="79c7c-631">Design a template for a custom report</span></span>

<span data-ttu-id="79c7c-632">A estrutura de ER gera usa modelos predefinidos para gerar relatórios nos formatos do Microsoft Office (pastas de trabalho do Excel ou documentos do Word).</span><span class="sxs-lookup"><span data-stu-id="79c7c-632">The ER framework uses predefined templates to generate reports in Microsoft Office formats (Excel workbooks or Word documents).</span></span> <span data-ttu-id="79c7c-633">Enquanto o relatório necessário está sendo gerado, um modelo é preenchido com os dados necessários de acordo com o fluxo de dados configurado.</span><span class="sxs-lookup"><span data-stu-id="79c7c-633">While the required report is being generated, a template is filled in with required data according to the configured dataflow.</span></span> <span data-ttu-id="79c7c-634">Portanto, você deve primeiro criar um modelo para o relatório personalizado.</span><span class="sxs-lookup"><span data-stu-id="79c7c-634">Therefore, you must first design a template for your custom report.</span></span> <span data-ttu-id="79c7c-635">Esse modelo deve ser criado como uma pasta de trabalho do Excel cuja estrutura representa o layout de um relatório personalizado.</span><span class="sxs-lookup"><span data-stu-id="79c7c-635">This template must be designed as an Excel workbook, the structure of which represents the layout of a custom report.</span></span> <span data-ttu-id="79c7c-636">Você deve nomear todos os itens do Excel que pretende preencher com os dados necessários.</span><span class="sxs-lookup"><span data-stu-id="79c7c-636">You must name every Excel item that you plan to fill in with required data.</span></span>

1. <span data-ttu-id="79c7c-637">Baixe o arquivo [Questionnaires report template.xslx](https://go.microsoft.com/fwlink/?linkid=851448) e salve-o no computador local.</span><span class="sxs-lookup"><span data-stu-id="79c7c-637">Download the [Questionnaires report template.xslx](https://go.microsoft.com/fwlink/?linkid=851448) file, and save it to your local computer.</span></span>
2. <span data-ttu-id="79c7c-638">Abra o arquivo no Excel e revise a estrutura da pasta de trabalho.</span><span class="sxs-lookup"><span data-stu-id="79c7c-638">Open the file in Excel, and review the structure of the workbook.</span></span>

<span data-ttu-id="79c7c-639">Como mostra a ilustração a seguir, o modelo baixado foi projetado para imprimir questionários especificados que apresentam as perguntas de um questionário junto com as respostas apropriadas.</span><span class="sxs-lookup"><span data-stu-id="79c7c-639">As the following illustration shows, the downloaded template has been designed to print specified questionnaires that present a questionnaire's questions together with appropriate answers.</span></span>

![Modelo do Excel para imprimir questionários especificados](./media/er-quick-start1-template-layout.png)

<span data-ttu-id="79c7c-641">Os nomes do Excel foram adicionados a este modelo para preencher os detalhes do questionário.</span><span class="sxs-lookup"><span data-stu-id="79c7c-641">Excel names have been added to this template to fill in the questionnaire details.</span></span> <span data-ttu-id="79c7c-642">Você pode usar o Gerenciador de nomes para revisar os nomes do Excel.</span><span class="sxs-lookup"><span data-stu-id="79c7c-642">You can use Name Manager to review the Excel names.</span></span>

![Usando o Gerenciador de nomes para revisar nomes do Excel no modelo do Excel fornecido](./media/er-quick-start1-template-names.png)

<span data-ttu-id="79c7c-644">Os rótulos de relatório foram adicionados como texto fixo no idioma inglês.</span><span class="sxs-lookup"><span data-stu-id="79c7c-644">Report labels have been added as fixed text in the English language.</span></span> <span data-ttu-id="79c7c-645">Você pode substituir os rótulos de relatório por novos nomes do Excel que preenchem os rótulos com o texto dependente do idioma, usando os [rótulos](#AddMmLabels) do formato ER, como fez para expressões dependentes de idioma no mapeamento de modelo configurado.</span><span class="sxs-lookup"><span data-stu-id="79c7c-645">You can replace the report labels with new Excel names that fill in the labels with language-dependent text by using the ER format [labels](#AddMmLabels), as you did for language-dependent expressions in the configured model mapping.</span></span> <span data-ttu-id="79c7c-646">Nesse caso, os rótulos de ER devem ser adicionadas ao formato ER editável.</span><span class="sxs-lookup"><span data-stu-id="79c7c-646">In this case, ER labels must be added in the editable ER format.</span></span>

<span data-ttu-id="79c7c-647">Como mostra a ilustração a seguir, o cabeçalho do relatório personalizado foi especificado para habilitar a paginação do Excel.</span><span class="sxs-lookup"><span data-stu-id="79c7c-647">As the following illustration shows, the custom report header has been specified to enable Excel to do paging.</span></span>

![O cabeçalho do relatório personalizado no modelo do Excel fornecido](./media/er-quick-start1-template-header.png)

## <a name="design-a-format"></a><a name="DesignFormat"></a><span data-ttu-id="79c7c-649">Criar um formato</span><span class="sxs-lookup"><span data-stu-id="79c7c-649">Design a format</span></span>

<span data-ttu-id="79c7c-650">Como usuário na função de consultor funcional de relatório eletrônico, você deve criar uma nova configuração do ER contendo um componente de [formato](general-electronic-reporting.md#FormatComponentOutbound).</span><span class="sxs-lookup"><span data-stu-id="79c7c-650">As a user in the Electronic Reporting Functional Consultant role, you must create a new ER configuration that contains a [format](general-electronic-reporting.md#FormatComponentOutbound) component.</span></span> <span data-ttu-id="79c7c-651">Você deve configurar o componente de formato para especificar como um modelo de relatório será preenchido com dados necessários no tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="79c7c-651">You must configure the format component to specify how a report template will be filled in with required data at runtime.</span></span>

<span data-ttu-id="79c7c-652">Ao concluir as etapas na seção [Importar uma configuração de formato projetado](#FormatImport), você pode importar o formato necessário a partir do arquivo XML fornecido.</span><span class="sxs-lookup"><span data-stu-id="79c7c-652">By completing the steps in the [Import a designed format configuration](#FormatImport) section, you can import the required format from the provided XML file.</span></span> <span data-ttu-id="79c7c-653">Como alternativa, você pode concluir as etapas na seção [Criar uma nova configuração de formato](#FormatCreate) para criar esse formato do zero.</span><span class="sxs-lookup"><span data-stu-id="79c7c-653">Alternatively, you can complete the steps in the [Create a new format configuration](#FormatCreate) section to design this format from scratch.</span></span>

### <a name="import-a-designed-format-configuration"></a><a name="FormatImport"></a><span data-ttu-id="79c7c-654">Importar uma configuração de formato criado</span><span class="sxs-lookup"><span data-stu-id="79c7c-654">Import a designed format configuration</span></span>

1. <span data-ttu-id="79c7c-655">Baixe o arquivo [Questionnaires format.version.1.1.xml](https://go.microsoft.com/fwlink/?linkid=851448) e salve-o no computador local.</span><span class="sxs-lookup"><span data-stu-id="79c7c-655">Download the [Questionnaires format.version.1.1.xml](https://go.microsoft.com/fwlink/?linkid=851448) file, and save it to your local computer.</span></span>
2. <span data-ttu-id="79c7c-656">Vá para **Administração da organização** \> **Espaços de trabalho** \> **Relatório eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-656">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
3. <span data-ttu-id="79c7c-657">No espaço de trabalho **Relatório eletrônico**, selecione **Configurações de relatórios**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-657">In the **Electronic reporting** workspace, select **Reporting configurations**.</span></span>
4. <span data-ttu-id="79c7c-658">No Painel de Ações, selecione **Câmbio** \> **Carregar de arquivo XML**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-658">On the Action pane, Select **Exchange** \> **Load from XML file**.</span></span>
5. <span data-ttu-id="79c7c-659">Selecione **Procurar** e, depois, localize e selecione o arquivo **Questionnaires format.version.1.1.xml**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-659">Select **Browse**, and then find and select the **Questionnaires format.version.1.1.xml** file.</span></span>
6. <span data-ttu-id="79c7c-660">Selecione **OK** para importar a configuração.</span><span class="sxs-lookup"><span data-stu-id="79c7c-660">Select **OK** to import the configuration.</span></span>

<span data-ttu-id="79c7c-661">Para continuar, ignore o próximo procedimento, [Criar uma nova configuração de formato](#FormatCreate).</span><span class="sxs-lookup"><span data-stu-id="79c7c-661">To continue, skip the next procedure, [Create a new format configuration](#FormatCreate).</span></span>

### <a name="create-a-new-format-configuration"></a><a name="FormatCreate"></a><span data-ttu-id="79c7c-662">Criar uma nova configuração de formato</span><span class="sxs-lookup"><span data-stu-id="79c7c-662">Create a new format configuration</span></span>
 
1. <span data-ttu-id="79c7c-663">Vá para **Administração da organização** \> **Relatório eletrônico** \> **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-663">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="79c7c-664">Na página **Configurações**, na árvore de configurações, selecione **Modelo de questionário**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-664">On the **Configurations** page, in the configuration tree, select **Questionnaire model**.</span></span>
3. <span data-ttu-id="79c7c-665">Selecione **Criar configuração**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-665">Select **Create configuration**.</span></span>
4. <span data-ttu-id="79c7c-666">Na caixa de diálogo suspensa, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="79c7c-666">In the drop-down dialog box, follow these steps:</span></span>

    1. <span data-ttu-id="79c7c-667">No campo **Novo**, selecione **Formato baseado no modelo de dados Questionários**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-667">In the **New** field, select **Format based on data model Questionnaires**.</span></span>
    2. <span data-ttu-id="79c7c-668">No campo **Nome**, insira **Relatório de questionário**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-668">In the **Name** field, enter **Questionnaire report**.</span></span>
    3. <span data-ttu-id="79c7c-669">No campo **Versão de modelo de dados**, selecione **1**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-669">In the **Data model version** field, select **1**.</span></span>

        > [!NOTE]
        > - <span data-ttu-id="79c7c-670">Se você selecionar uma versão específica do modelo de dados básicos, a estrutura da versão correspondente do modelo de dados será apresentada como a estrutura da fonte de dados **Modelo** no formato criado.</span><span class="sxs-lookup"><span data-stu-id="79c7c-670">If you select a specific version of the base data model, the structure of the corresponding version of the data model will be presented to you as the structure of the **Model** data source in the format that is created.</span></span>
        > - <span data-ttu-id="79c7c-671">Este campo pode ser deixado em branco.</span><span class="sxs-lookup"><span data-stu-id="79c7c-671">You can leave this field blank.</span></span> <span data-ttu-id="79c7c-672">Nesse caso, a estrutura da versão de **Rascunho** do modelo de dados será apresentada como a estrutura da fonte de dados **Modelo** no formato criado.</span><span class="sxs-lookup"><span data-stu-id="79c7c-672">In that case, the structure of the **Draft** version of the data model will be presented to you as the structure of the **Model** data source in the format that is created.</span></span> <span data-ttu-id="79c7c-673">Em seguida, você pode ajustar o modelo e ver imediatamente esses ajustes no seu formato.</span><span class="sxs-lookup"><span data-stu-id="79c7c-673">You can then adjust your model and immediately see those adjustments in your format.</span></span> <span data-ttu-id="79c7c-674">Esta abordagem pode melhorar a eficiência do design da solução ER quando você configura o modelo de dados, o mapeamento de modelos e o formato simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="79c7c-674">This approach might improve the efficiency of ER solution design when you configure your data model, model mapping, and format simultaneously.</span></span>
        > - <span data-ttu-id="79c7c-675">Se você selecionar uma versão específica do modelo de dados básicos, poderá alternar para o uso da versão **Rascunho** posteriormente, ao começar a editar um formato.</span><span class="sxs-lookup"><span data-stu-id="79c7c-675">If you select a specific version of the base data model, you can switch to using the **Draft** version later, when you start to edit a format.</span></span>

    4. <span data-ttu-id="79c7c-676">No campo **Definição do modelo de dados**, selecione a definição **Raiz**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-676">In the **Data model definition** field, select the **Root** definition.</span></span>

5. <span data-ttu-id="79c7c-677">Selecione **Criar configuração** para criar a configuração.</span><span class="sxs-lookup"><span data-stu-id="79c7c-677">Select **Create configuration** to create the configuration.</span></span>

#### <a name="import-a-report-template"></a><a name="ImportReportTemplate"></a><span data-ttu-id="79c7c-678">Importar um modelo do relatório</span><span class="sxs-lookup"><span data-stu-id="79c7c-678">Import a report template</span></span>

1. <span data-ttu-id="79c7c-679">Na página **Configurações**, na árvore de configurações, selecione **Relatório de questionário**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-679">On the **Configurations** page, in the configuration tree, select **Questionnaire report**.</span></span>
2. <span data-ttu-id="79c7c-680">Selecione **Designer** para começar a configurar um formato personalizado.</span><span class="sxs-lookup"><span data-stu-id="79c7c-680">Select **Designer** to start to configure a custom format.</span></span>
3. <span data-ttu-id="79c7c-681">Na página **Designer de formato**, no Painel de Ações, selecione **Importar** \> **Importar do Excel**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-681">On the **Format designer** page, on the Action Pane, select **Import** \> **Import from Excel**.</span></span>
4. <span data-ttu-id="79c7c-682">Na caixa de diálogo, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="79c7c-682">In the dialog box, follow these steps:</span></span>

    1. <span data-ttu-id="79c7c-683">Selecione **Adicionar modelo**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-683">Select **Add template**.</span></span>
    2. <span data-ttu-id="79c7c-684">Localize e selecione arquivo **Questionnaires report template.xslx** salvo localmente e selecione **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-684">Find and select the locally saved **Questionnaires report template.xslx** file, and then select **Open**.</span></span>
    3. <span data-ttu-id="79c7c-685">Selecione **OK** para importar o modelo.</span><span class="sxs-lookup"><span data-stu-id="79c7c-685">Select **OK** to import the template.</span></span>

    ![Importar um modelo de relatório](./media/er-quick-start1-template-import.png)

<span data-ttu-id="79c7c-687">O formato **Excel\\Arquivo** é adicionado automaticamente ao formato editável como um elemento raiz.</span><span class="sxs-lookup"><span data-stu-id="79c7c-687">The **Excel\\File** format element is automatically added to the editable format as a root element.</span></span> <span data-ttu-id="79c7c-688">Além disso, o elemento de formato **Excel\\Intervalo** ou o elemento de formato **Excel\\Célula** é automaticamente adicionado a cada nome do Excel reconhecido do modelo importado.</span><span class="sxs-lookup"><span data-stu-id="79c7c-688">Additionally, either the **Excel\\Range** format element or the **Excel\\Cell** format element is automatically added for every recognized Excel name of the imported template.</span></span> <span data-ttu-id="79c7c-689">O formato **Excel\\Cabeçalho** que tem o elemento **Cadeia de caracteres** aninhado é automaticamente adicionado para refletir as configurações de cabeçalho do modelo importado.</span><span class="sxs-lookup"><span data-stu-id="79c7c-689">The **Excel\\Header** format that has the nested **String** element is automatically added to reflect the header settings of the imported template.</span></span>

![Estrutura de formato que inclui elementos adicionados automaticamente no designer de Operação do ER](./media/er-quick-start1-template-import2.png)

#### <a name="configure-a-format"></a><a name="ConfigureFormat"></a><span data-ttu-id="79c7c-691">Configurar um formato</span><span class="sxs-lookup"><span data-stu-id="79c7c-691">Configure a format</span></span>

1. <span data-ttu-id="79c7c-692">Na página **Designer de formato**, na árvore de formatos, selecione o elemento raiz do **Excel**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-692">On the **Format designer** page, in the format tree, select the **Excel** root element.</span></span>
2. <span data-ttu-id="79c7c-693">Na guia **Formatar** no lado direito da página, no campo **Nome**, insira <a name="AddFormatRootElement"></a>**Relatório**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-693">On the **Format** tab on the right side of the page, in the **Name** field, enter <a name="AddFormatRootElement"></a>**Report**.</span></span>
3. <span data-ttu-id="79c7c-694">No campo **Preferência de idioma**, selecione a **Preferência de usuário** para executar o relatório no idioma preferencial do usuário.</span><span class="sxs-lookup"><span data-stu-id="79c7c-694">In the **Language preference** field, select **User preference** to run the report in the user's preferred language.</span></span>
4. <span data-ttu-id="79c7c-695">No campo **Preferência de cultura**, selecione a **Preferência de usuário** para executar o relatório na cultura preferencial do usuário.</span><span class="sxs-lookup"><span data-stu-id="79c7c-695">In the **Culture preference** field, select **User preference** to run the report in the user's preferred culture.</span></span>

    <span data-ttu-id="79c7c-696">Para obter informações sobre como especificar o idioma e os contextos de cultura para um processo ER, consulte [Criar relatórios multilíngues](er-design-multilingual-reports.md).</span><span class="sxs-lookup"><span data-stu-id="79c7c-696">For information about how to specify the language and culture contexts for an ER process, see [Design multilingual reports](er-design-multilingual-reports.md).</span></span>

    ![Como definir configurações de idioma e cultura para o relatório criado no designer de Operações do ER](./media/er-quick-start1-template-format-structure1.png)

5. <span data-ttu-id="79c7c-698">Na árvore de formatos, expanda o nó raiz e selecione **ResultsGroup**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-698">In the format tree, expand the root node, and then select **ResultsGroup**.</span></span>
6. <span data-ttu-id="79c7c-699">Na guia **Formatar**, no campo **Direção da replicação**, selecione **Sem replicação**, porque você não espera ter vários grupos de resultados para um único questionário.</span><span class="sxs-lookup"><span data-stu-id="79c7c-699">On the **Format** tab, in the **Replication direction** field, select **No replication**, because you don't expect to have multiple result groups for a single questionnaire.</span></span>

    ![Como definir a direção de replicação para elementos de formato de intervalo no designer de Operação do ER](./media/er-quick-start1-template-format-structure2.png)

7. <span data-ttu-id="79c7c-701">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-701">Select **Save**.</span></span>

#### <a name="define-the-data-binding-for-a-report-title"></a><a name="DefineFormatBindings"></a><span data-ttu-id="79c7c-702">Definir a associação de dados para um título de relatório</span><span class="sxs-lookup"><span data-stu-id="79c7c-702">Define the data binding for a report title</span></span>

<span data-ttu-id="79c7c-703">Você deve especificar uma associação de dados para um elemento de formato que é usado para preencher o título de um relatório gerado.</span><span class="sxs-lookup"><span data-stu-id="79c7c-703">You must specify a data binding for a format element that is used to fill in the title of a generated report.</span></span>

1. <span data-ttu-id="79c7c-704">Na página **Designer de formato**, na guia **Mapeamento** à direita, selecione o elemento **Relatório\\ReportTitle**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-704">On the **Format designer** page, on the **Mapping** tab on the right, select the **Report\\ReportTitle** element.</span></span>
2. <span data-ttu-id="79c7c-705">Selecione **Editar fórmula**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-705">Select **Edit formula**.</span></span>
3. <span data-ttu-id="79c7c-706">No editor de fórmulas, selecione **Traduzir**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-706">In the formula editor, select **Translate**.</span></span>
4. <span data-ttu-id="79c7c-707">Na caixa de diálogo **Tradução de texto**, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="79c7c-707">In the **Text translation** dialog box, follow these steps:</span></span>

    1. <span data-ttu-id="79c7c-708">No campo **ID do rótulo**, insira **ReportTitle**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-708">In the **Label ID** field, enter **ReportTitle**.</span></span>
    2. <span data-ttu-id="79c7c-709">No campo **Texto no idioma padrão**, insira **Relatório Questionários**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-709">In the **Text in default language** field, enter **Questionnaires report**.</span></span>
    3. <span data-ttu-id="79c7c-710">Selecione **Traduzir** e, depois, **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-710">Select **Translate**, and then select **Save**.</span></span>
    4. <span data-ttu-id="79c7c-711">Selecione **Traduzir** para fechar a caixa de diálogo **Tradução de texto**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-711">Select **Translate** to close the **Text translation** dialog box.</span></span>

5. <span data-ttu-id="79c7c-712">Feche o editor de fórmulas.</span><span class="sxs-lookup"><span data-stu-id="79c7c-712">Close the formula editor.</span></span>

    ![Como configurar a associação para preencher o título de um relatório gerado](./media/er-quick-start1-add-report-title-label.png)

<span data-ttu-id="79c7c-714">Você pode usar essa técnica para tornar todos os outros rótulos do modelo atual dependentes de idioma.</span><span class="sxs-lookup"><span data-stu-id="79c7c-714">You can use this technique to make all other labels of the current template language-dependent.</span></span> <span data-ttu-id="79c7c-715">Para obter informações sobre como os rótulos adicionados de uma única configuração de ER podem ser traduzidos em todos os idiomas com suporte, consulte [Criar relatórios multilíngues](er-design-multilingual-reports.md).</span><span class="sxs-lookup"><span data-stu-id="79c7c-715">For information about how the added labels of a single ER configuration can be translated into all supported languages, see [Design multilingual reports](er-design-multilingual-reports.md).</span></span>

#### <a name="review-model-data-source"></a><a name="ReviewModelDataSource"></a><span data-ttu-id="79c7c-716">Analisar a fonte de dados do modelo</span><span class="sxs-lookup"><span data-stu-id="79c7c-716">Review model data source</span></span>

1. <span data-ttu-id="79c7c-717">Na página **Designer de formato**, na guia **Mapeamento**, selecione a fonte de dados <a name="ModelDSName"></a>**modelo** que representa o modelo de dados base deste formato ER.</span><span class="sxs-lookup"><span data-stu-id="79c7c-717">On the **Format designer** page, on the **Mapping** tab, select the <a name="ModelDSName"></a>**model** data source that represents the base data model of this ER format.</span></span>
2. <span data-ttu-id="79c7c-718">Selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-718">Select **Edit**.</span></span>
3. <span data-ttu-id="79c7c-719">Revise as informações na caixa de diálogo **Propriedades da fonte de dados**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-719">Review the information in the **Data source properties** dialog box.</span></span> <span data-ttu-id="79c7c-720">Essa fonte de dados representa a versão 1 do componente do modelo de dados **Questionários** que reside na configuração ER do **modelo Questionários**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-720">This data source represents version 1 of the **Questionnaires** data model component that resides in the **Questionnaires model** ER configuration.</span></span>

![Propriedades da fonte de dados do modelo no designer de Operações do ER](./media/er-quick-start1-model-data-source.png)

#### <a name="bind-format-elements-to-data-source-fields"></a><a name="BindFormatElements"></a><span data-ttu-id="79c7c-722">Associar elementos a campos da fonte de dados</span><span class="sxs-lookup"><span data-stu-id="79c7c-722">Bind format elements to data source fields</span></span>

<span data-ttu-id="79c7c-723">Para especificar como um modelo é preenchido no tempo de execução, você deve associar todos os elementos de formato associados a um nome do Excel apropriado a um único campo da fonte de dados desse formato.</span><span class="sxs-lookup"><span data-stu-id="79c7c-723">To specify how a template is filled in at runtime, you must bind every format element that is associated with an appropriate Excel name to a single field of this format's data source.</span></span>

1. <span data-ttu-id="79c7c-724">Na página **Designer de formato**, na árvore de formatos, selecione o elemento **Relatório\\CompanyName**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-724">On the **Format designer** page, in the format tree, select the **Report\\CompanyName** format element.</span></span>
2. <span data-ttu-id="79c7c-725">Na guia **Mapeamento**, selecione o campo de fonte de dados **model.CompanyName** do tipo **Cadeia de caracteres**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-725">On the **Mapping** tab, select the **model.CompanyName** data source field of the **String** type.</span></span>
3. <span data-ttu-id="79c7c-726">Selecione **Associar** para inserir um nome de empresa em um modelo.</span><span class="sxs-lookup"><span data-stu-id="79c7c-726">Select **Bind** to enter a company name in a template.</span></span>
4. <span data-ttu-id="79c7c-727">Na árvore de formatos, selecione o elemento **Relatório\\Questionário**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-727">In the format tree, select the **Report\\Questionnaire** element.</span></span>
5. <span data-ttu-id="79c7c-728">Na guia **Mapeamento**, selecione o campo de fonte de dados **model.Questionnaire** do tipo **Lista de registros**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-728">On the **Mapping** tab, select the **model.Questionnaire** data source field of the **Record list** type.</span></span>
6. <span data-ttu-id="79c7c-729">Selecione **Associar**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-729">Select **Bind**.</span></span>
7. <span data-ttu-id="79c7c-730">Selecione **Mostrar detalhes** para ver mais detalhes dos elementos de formato.</span><span class="sxs-lookup"><span data-stu-id="79c7c-730">Select **Show details** to see more details for format elements.</span></span>

    <span data-ttu-id="79c7c-731">O elemento de formato do intervalo **Questionário** é configurado como replicado verticalmente.</span><span class="sxs-lookup"><span data-stu-id="79c7c-731">The **Questionnaire** range format element is configured as vertically replicated.</span></span> <span data-ttu-id="79c7c-732">Quando ele está associado a uma fonte de dados do tipo **Lista de registros**, o intervalo de **Questionário** apropriado do modelo do Excel é repetido para cada registro da fonte de dados associada.</span><span class="sxs-lookup"><span data-stu-id="79c7c-732">When it's bound to a data source of the **Record list** type, the appropriate **Questionnaire** range of the Excel template is repeated for every record of the bound data source.</span></span>
 
    ![Associação do elemento Formato do intervalo do questionário a fontes de dados de Lista de registros apropriadas no designer de Operação do ER](./media/er-quick-start1-bindings1.png)

    <span data-ttu-id="79c7c-734">Como o intervalo **Questionário** do modelo do Excel é definido entre as linhas 5 e 14, essas linhas são repetidas para todos os questionários relatados.</span><span class="sxs-lookup"><span data-stu-id="79c7c-734">Because the **Questionnaire** range of the Excel template is defined between rows 5 through 14, these rows are repeated for every reported questionnaire.</span></span>

    ![Linhas do modelo do Excel que serão repetidas em um relatório gerado para cada registro das fontes de dados da lista de registros](./media/er-quick-start1-template-questionnaire-range.png)

8. <span data-ttu-id="79c7c-736">Configure associações semelhantes para os elementos de formato restantes, conforme descrito na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="79c7c-736">Configure similar bindings for the remaining format elements, as described in the following table.</span></span>

    > [!NOTE]
    > <span data-ttu-id="79c7c-737">Nesta tabela, as informações na coluna "Caminho da fonte de dados" supõem que o recurso do ER [caminho relativo](relative-path-data-bindings-er-models-format.md) está ativado.</span><span class="sxs-lookup"><span data-stu-id="79c7c-737">In this table, the information in the "Data source path" column assumes that the [relative path](relative-path-data-bindings-er-models-format.md) ER feature is turned on.</span></span>

    | <span data-ttu-id="79c7c-738">Caminho do elemento de formato</span><span class="sxs-lookup"><span data-stu-id="79c7c-738">Format element path</span></span>                                      | <span data-ttu-id="79c7c-739">Caminho da fonte de dados</span><span class="sxs-lookup"><span data-stu-id="79c7c-739">Data source path</span></span> |
    |----------------------------------------------------------|------------------|
    | <span data-ttu-id="79c7c-740">Excel\\ReportTitle</span><span class="sxs-lookup"><span data-stu-id="79c7c-740">Excel\\ReportTitle</span></span>                                       | <span data-ttu-id="79c7c-741">**\@"GER\_LABEL:ReportTitle"**</span><span class="sxs-lookup"><span data-stu-id="79c7c-741">**\@"GER\_LABEL:ReportTitle"**</span></span> |
    | <span data-ttu-id="79c7c-742">Excel\\CompanyName</span><span class="sxs-lookup"><span data-stu-id="79c7c-742">Excel\\CompanyName</span></span>                                       | <span data-ttu-id="79c7c-743">**model.CompanyName**</span><span class="sxs-lookup"><span data-stu-id="79c7c-743">**model.CompanyName**</span></span> |
    | <span data-ttu-id="79c7c-744">Excel\\Questionário</span><span class="sxs-lookup"><span data-stu-id="79c7c-744">Excel\\Questionnaire</span></span>                                     | <span data-ttu-id="79c7c-745">**model.Questionnaire**</span><span class="sxs-lookup"><span data-stu-id="79c7c-745">**model.Questionnaire**</span></span> |
    | <span data-ttu-id="79c7c-746">Excel\\Questionário\\Ativo</span><span class="sxs-lookup"><span data-stu-id="79c7c-746">Excel\\Questionnaire\\Active</span></span>                             | <span data-ttu-id="79c7c-747">**\@.Active**, onde **\@** é **model.Questionnaire**</span><span class="sxs-lookup"><span data-stu-id="79c7c-747">**\@.Active**, where **\@** is **model.Questionnaire**</span></span> |
    | <span data-ttu-id="79c7c-748">Excel\\Questionário\\Código</span><span class="sxs-lookup"><span data-stu-id="79c7c-748">Excel\\Questionnaire\\Code</span></span>                               | <span data-ttu-id="79c7c-749">**\@.Code**</span><span class="sxs-lookup"><span data-stu-id="79c7c-749">**\@.Code**</span></span> |
    | <span data-ttu-id="79c7c-750">Excel\\Questionário\\Descrição</span><span class="sxs-lookup"><span data-stu-id="79c7c-750">Excel\\Questionnaire\\Description</span></span>                        | <span data-ttu-id="79c7c-751">**\@.Description**</span><span class="sxs-lookup"><span data-stu-id="79c7c-751">**\@.Description**</span></span> |
    | <span data-ttu-id="79c7c-752">Excel\\Questionário\\QuestionnaireType</span><span class="sxs-lookup"><span data-stu-id="79c7c-752">Excel\\Questionnaire\\QuestionnaireType</span></span>                  | <span data-ttu-id="79c7c-753">**\@.QuestionnaireType**</span><span class="sxs-lookup"><span data-stu-id="79c7c-753">**\@.QuestionnaireType**</span></span> |
    | <span data-ttu-id="79c7c-754">Excel\\Questionário\\QuestionOrder</span><span class="sxs-lookup"><span data-stu-id="79c7c-754">Excel\\Questionnaire\\QuestionOrder</span></span>                      | <span data-ttu-id="79c7c-755">**\@.QuestionOrder**</span><span class="sxs-lookup"><span data-stu-id="79c7c-755">**\@.QuestionOrder**</span></span> |
    | <span data-ttu-id="79c7c-756">Excel\\Questionário\\ResultsGroup\\Código\_</span><span class="sxs-lookup"><span data-stu-id="79c7c-756">Excel\\Questionnaire\\ResultsGroup\\Code\_</span></span>               | <span data-ttu-id="79c7c-757">**\@.ResultsGroup.Code**</span><span class="sxs-lookup"><span data-stu-id="79c7c-757">**\@.ResultsGroup.Code**</span></span> |
    | <span data-ttu-id="79c7c-758">Excel\\Questionário\\ResultsGroup\\Descrição\_</span><span class="sxs-lookup"><span data-stu-id="79c7c-758">Excel\\Questionnaire\\ResultsGroup\\Description\_</span></span>        | <span data-ttu-id="79c7c-759">**\@.ResultsGroup.Description**</span><span class="sxs-lookup"><span data-stu-id="79c7c-759">**\@.ResultsGroup.Description**</span></span> |
    | <span data-ttu-id="79c7c-760">Excel\\Questionário\\ResultsGroup\\MaxNumberOfPoints</span><span class="sxs-lookup"><span data-stu-id="79c7c-760">Excel\\Questionnaire\\ResultsGroup\\MaxNumberOfPoints</span></span>    | <span data-ttu-id="79c7c-761">**\@.ResultsGroup.MaxNumberOfPoint**</span><span class="sxs-lookup"><span data-stu-id="79c7c-761">**\@.ResultsGroup.MaxNumberOfPoint**</span></span> |
    | <span data-ttu-id="79c7c-762">Excel\\Questionário\\Pergunta</span><span class="sxs-lookup"><span data-stu-id="79c7c-762">Excel\\Questionnaire\\Question</span></span>                           | <span data-ttu-id="79c7c-763">**\@.Question**</span><span class="sxs-lookup"><span data-stu-id="79c7c-763">**\@.Question**</span></span> |
    | <span data-ttu-id="79c7c-764">Excel\\Questionário\\Pergunta\\CollectionSequenceNumber</span><span class="sxs-lookup"><span data-stu-id="79c7c-764">Excel\\Questionnaire\\Question\\CollectionSequenceNumber</span></span> | <span data-ttu-id="79c7c-765">**\@.CollectionSequenceNumber**, onde **\@** é **model.Questionnaire.Question**</span><span class="sxs-lookup"><span data-stu-id="79c7c-765">**\@.CollectionSequenceNumber**, where **\@** is **model.Questionnaire.Question**</span></span> |
    | <span data-ttu-id="79c7c-766">Excel\\Questionário\\Pergunta\\Id</span><span class="sxs-lookup"><span data-stu-id="79c7c-766">Excel\\Questionnaire\\Question\\Id</span></span>                       | <span data-ttu-id="79c7c-767">**\@.Id**</span><span class="sxs-lookup"><span data-stu-id="79c7c-767">**\@.Id**</span></span> |
    | <span data-ttu-id="79c7c-768">Excel\\Questionário\\Pergunta\\MustBeCompleted</span><span class="sxs-lookup"><span data-stu-id="79c7c-768">Excel\\Questionnaire\\Question\\MustBeCompleted</span></span>          | <span data-ttu-id="79c7c-769">**\@.MustBeCompleted**</span><span class="sxs-lookup"><span data-stu-id="79c7c-769">**\@.MustBeCompleted**</span></span> |
    | <span data-ttu-id="79c7c-770">Excel\\Questionário\\Pergunta\\PrimaryQuestion</span><span class="sxs-lookup"><span data-stu-id="79c7c-770">Excel\\Questionnaire\\Question\\PrimaryQuestion</span></span>          | <span data-ttu-id="79c7c-771">**\@.PrimaryQuestion**</span><span class="sxs-lookup"><span data-stu-id="79c7c-771">**\@.PrimaryQuestion**</span></span> |
    | <span data-ttu-id="79c7c-772">Excel\\Questionário\\Pergunta\\SequenceNumber</span><span class="sxs-lookup"><span data-stu-id="79c7c-772">Excel\\Questionnaire\\Question\\SequenceNumber</span></span>           | <span data-ttu-id="79c7c-773">**\@.SequenceNumber**</span><span class="sxs-lookup"><span data-stu-id="79c7c-773">**\@.SequenceNumber**</span></span> |
    | <span data-ttu-id="79c7c-774">Excel\\Questionário\\Pergunta\\Texto</span><span class="sxs-lookup"><span data-stu-id="79c7c-774">Excel\\Questionnaire\\Question\\Text</span></span>                     | <span data-ttu-id="79c7c-775">**\@.Text**</span><span class="sxs-lookup"><span data-stu-id="79c7c-775">**\@.Text**</span></span> |
    | <span data-ttu-id="79c7c-776">Excel\\Questionário\\Pergunta\\Resposta</span><span class="sxs-lookup"><span data-stu-id="79c7c-776">Excel\\Questionnaire\\Question\\Answer</span></span>                   | <span data-ttu-id="79c7c-777">**\@.Answer**</span><span class="sxs-lookup"><span data-stu-id="79c7c-777">**\@.Answer**</span></span> |
    | <span data-ttu-id="79c7c-778">Excel\\Questionário\\Pergunta\\Resposta\\CorrectAnswer</span><span class="sxs-lookup"><span data-stu-id="79c7c-778">Excel\\Questionnaire\\Question\\Answer\\CorrectAnswer</span></span>    | <span data-ttu-id="79c7c-779">**\@.CorrectAnswer**, onde **\@** é **model.Questionnaire.Answer**</span><span class="sxs-lookup"><span data-stu-id="79c7c-779">**\@.CorrectAnswer**, where **\@** is **model.Questionnaire.Answer**</span></span> |
    | <span data-ttu-id="79c7c-780">Excel\\Questionário\\Pergunta\\Resposta\\Pontos</span><span class="sxs-lookup"><span data-stu-id="79c7c-780">Excel\\Questionnaire\\Question\\Answer\\Points</span></span>           | <span data-ttu-id="79c7c-781">**\@.Points**</span><span class="sxs-lookup"><span data-stu-id="79c7c-781">**\@.Points**</span></span> |
    | <span data-ttu-id="79c7c-782">Excel\\Questionário\\Pergunta\\Resposta\\Texto</span><span class="sxs-lookup"><span data-stu-id="79c7c-782">Excel\\Questionnaire\\Question\\Answer\\Text</span></span>             | <span data-ttu-id="79c7c-783">**\@.Text**</span><span class="sxs-lookup"><span data-stu-id="79c7c-783">**\@.Text**</span></span> |

9. <span data-ttu-id="79c7c-784">Quando terminar, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-784">When you've finished, select **Save**.</span></span>

<span data-ttu-id="79c7c-785">A ilustração a seguir mostra o estado final de associações de dados configuradas na página **Designer de formato**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-785">The following illustration shows the final state of the configured data bindings on the **Format designer** page.</span></span>

![Associações de dados configuradas no designer Operação do ER](./media/er-quick-start1-bindings2.png)

> [!IMPORTANT]
> <span data-ttu-id="79c7c-787">Toda a coleção de fontes de dados e associações especificadas representa um componente de mapeamento de formato do formato configurado.</span><span class="sxs-lookup"><span data-stu-id="79c7c-787">The whole collection of specified data sources and bindings represents a format mapping component of the configured format.</span></span> <span data-ttu-id="79c7c-788">Esse mapeamento de formato é chamado quando você executa o formato configurado para a geração de relatórios.</span><span class="sxs-lookup"><span data-stu-id="79c7c-788">This format mapping is called when you run the configured format for report generation.</span></span>

### <a name="run-a-designed-format-from-er"></a><a name="RunFormatFromER"></a><span data-ttu-id="79c7c-789">Executar um formato criado a partir do ER</span><span class="sxs-lookup"><span data-stu-id="79c7c-789">Run a designed format from ER</span></span>

<span data-ttu-id="79c7c-790">Agora você pode executar um formato criado para fins de teste na página **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-790">You can now run a designed format for testing purposes from the **Configurations** page.</span></span>

1. <span data-ttu-id="79c7c-791">Vá para **Administração da organização** \> **Relatório eletrônico** \> **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-791">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="79c7c-792">Na página **Configuração**, na árvore de configurações, expanda **Modelo de questionário** e selecione **Relatório de questionário**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-792">On the **Configuration** page, in the configuration tree, expand **Questionnaire model**, and then select **Questionnaire report**.</span></span>
3. <span data-ttu-id="79c7c-793">Selecione **Designer** para a versão de formato que tem um status **Rascunho**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-793">Select **Designer** for the format version that has a status of **Draft**.</span></span>
4. <span data-ttu-id="79c7c-794">Na página **Designer de formato**, selecione **Executar**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-794">On the **Format designer** page, select **Run**.</span></span>
5. <span data-ttu-id="79c7c-795">Na caixa de diálogo **Parâmetros de ER**, na FastTab **Registros a serem incluídos**, configure a opção de filtragem para que somente o questionário **SBCCrsExam** seja incluído.</span><span class="sxs-lookup"><span data-stu-id="79c7c-795">In the **ER parameters** dialog box, on the **Records to include** FastTab, configure the filtering option so that only the **SBCCrsExam** questionnaire is included.</span></span>
6. <span data-ttu-id="79c7c-796">Selecione **OK** para confirmar a opção de filtragem.</span><span class="sxs-lookup"><span data-stu-id="79c7c-796">Select **OK** to confirm the filtering option.</span></span>
7. <span data-ttu-id="79c7c-797">Selecione **OK** para executar o relatório.</span><span class="sxs-lookup"><span data-stu-id="79c7c-797">Select **OK** to run the report.</span></span>
8. <span data-ttu-id="79c7c-798">Revise o relatório gerado.</span><span class="sxs-lookup"><span data-stu-id="79c7c-798">Review the generated report.</span></span>

<span data-ttu-id="79c7c-799">Por [padrão](electronic-reporting-destinations.md#default-behavior), um relatório gerado é entregue como um arquivo do Excel que pode ser baixado.</span><span class="sxs-lookup"><span data-stu-id="79c7c-799">By [default](electronic-reporting-destinations.md#default-behavior), a generated report is delivered as an Excel file that you can download.</span></span> <span data-ttu-id="79c7c-800">As ilustrações a seguir mostram duas páginas do relatório gerado no formato Excel.</span><span class="sxs-lookup"><span data-stu-id="79c7c-800">The following illustrations show two pages of the generated report in Excel format.</span></span>

![Exemplo de um relatório gerado no formato Excel, página 1](./media/er-quick-start1-report1a.png)

![Exemplo de um relatório gerado no formato Excel, página 2](./media/er-quick-start1-report1b.png)

## <a name="tune-a-designed-format"></a><a name="TuneFormat"></a><span data-ttu-id="79c7c-803">Ajustar um formato criado</span><span class="sxs-lookup"><span data-stu-id="79c7c-803">Tune a designed format</span></span>

### <a name="modify-a-format-to-change-the-name-of-a-generated-document"></a><a name="ModifyToChangeName"></a><span data-ttu-id="79c7c-804">Modificar um formato para alterar o nome de um documento gerado</span><span class="sxs-lookup"><span data-stu-id="79c7c-804">Modify a format to change the name of a generated document</span></span>

<span data-ttu-id="79c7c-805">Por padrão, um documento gerado é nomeado usando o alias do usuário atual.</span><span class="sxs-lookup"><span data-stu-id="79c7c-805">By default, a generated document is named by using the alias of the current user.</span></span> <span data-ttu-id="79c7c-806">Ao modificar o formato, você pode alterar esse comportamento para que um documento gerado seja nomeado com base na lógica personalizada.</span><span class="sxs-lookup"><span data-stu-id="79c7c-806">By modifying the format, you can change this behavior so that a generated document is named based on your custom logic.</span></span> <span data-ttu-id="79c7c-807">Por exemplo, o nome de um documento gerado pode se basear na data e na hora da sessão atual e no título do relatório.</span><span class="sxs-lookup"><span data-stu-id="79c7c-807">For example, the name of a generated document can be based on the current session date and time, and on the report's title.</span></span>

1. <span data-ttu-id="79c7c-808">Na página **Designer de formato**, selecione o item de raiz **Relatório**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-808">On the **Format designer** page, select the **Report** root item.</span></span>
2. <span data-ttu-id="79c7c-809">Na guia **Mapeamento**, selecione **Editar nome do arquivo**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-809">On the **Mapping** tab, select **Edit file name**.</span></span>
3. <span data-ttu-id="79c7c-810">No campo **Fórmula**, insira **CONCATENATE (\@"GER\_LABEL:ReportTitle", " - ", DATETIMEFORMAT(SESSIONNOW(), "aaaa-MM-dd hh-mm-ss"))**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-810">In the **Formula** field, enter **CONCATENATE (\@"GER\_LABEL:ReportTitle", " - ", DATETIMEFORMAT(SESSIONNOW(), "yyyy-MM-dd hh-mm-ss"))**.</span></span>
4. <span data-ttu-id="79c7c-811">Selecione **Salvar** e feche o editor de fórmula.</span><span class="sxs-lookup"><span data-stu-id="79c7c-811">Select **Save**, and close the formula editor.</span></span>
5. <span data-ttu-id="79c7c-812">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-812">Select **Save**.</span></span>

### <a name="modify-a-format-to-change-the-order-of-questions"></a><a name="ModifyToOrder"></a><span data-ttu-id="79c7c-813">Modificar um formato para alterar a ordem das perguntas</span><span class="sxs-lookup"><span data-stu-id="79c7c-813">Modify a format to change the order of questions</span></span>

<span data-ttu-id="79c7c-814">As perguntas não são ordenadas corretamente em um relatório gerado.</span><span class="sxs-lookup"><span data-stu-id="79c7c-814">The questions aren't correctly ordered in a generated report.</span></span> <span data-ttu-id="79c7c-815">Você pode alterar a ordem modificando o formato.</span><span class="sxs-lookup"><span data-stu-id="79c7c-815">You can change the order by modifying the format.</span></span>

1. <span data-ttu-id="79c7c-816">Na página **Designer de formato**, selecione o item de raiz **Relatório**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-816">On the **Format designer** page, select the **Report** root item.</span></span>
2. <span data-ttu-id="79c7c-817">Na guia **Mapeamento**, na árvore de formatos, expanda **Relatório\\Questionário\\Pergunta**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-817">On the **Mapping** tab, in the format tree, expand **Report\\Questionnaire\\Question**.</span></span>

    ![Elemento de formato da pergunta do tipo de intervalo no designer de Operação do ER](./media/er-quick-start1-bindings3.png)

3. <span data-ttu-id="79c7c-819">Na guia **Mapeamento**, selecione **model.Questionnaire**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-819">On the **Mapping** tab, select **model.Questionnaire**.</span></span>
4. <span data-ttu-id="79c7c-820">Selecione **Adicionar** \> **Funções\\Campo calculado** e, em seguida, no campo **Nome**, insira **OrderedQuestions**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-820">Select **Add** \> **Functions\\Calculated field**, and then, in the **Name** field, enter **OrderedQuestions**.</span></span>
5. <span data-ttu-id="79c7c-821">Selecione **Editar fórmula**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-821">Select **Edit formula**.</span></span>
6. <span data-ttu-id="79c7c-822">No editor de fórmulas, no campo **Fórmula**, insira **ORDERBY (model.Questionnaire.Question, model.Questionnaire.Question.SequenceNumber)** para ordenar a lista de perguntas do questionário atual pelo número da ordem de sequência.</span><span class="sxs-lookup"><span data-stu-id="79c7c-822">In the formula editor, in the **Formula** field, enter **ORDERBY (model.Questionnaire.Question, model.Questionnaire.Question.SequenceNumber)** to order the list of questions of the current questionnaire by the sequence order number.</span></span>
7. <span data-ttu-id="79c7c-823">Selecione **Salvar** e feche o editor de fórmula.</span><span class="sxs-lookup"><span data-stu-id="79c7c-823">Select **Save**, and close the formula editor.</span></span>
8. <span data-ttu-id="79c7c-824">Selecione **OK** para concluir a entrada de um novo campo calculado.</span><span class="sxs-lookup"><span data-stu-id="79c7c-824">Select **OK** to complete the entry of a new calculated field.</span></span>
9. <span data-ttu-id="79c7c-825">Na guia **Mapeamento**, selecione **model.Questionnaire.OrderedQuestions**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-825">On the **Mapping** tab, select **model.Questionnaire.OrderedQuestions**.</span></span>
10. <span data-ttu-id="79c7c-826">Na árvore de formatos, selecione **Excel\\Questionário\\Pergunta**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-826">In the format tree, select **Excel\\Questionnaire\\Question**.</span></span>
11. <span data-ttu-id="79c7c-827">Selecione **Associar** e confirme se o caminho **model.Questionnaire.Questions** atual é substituído pelo novo caminho **model.Questionnaire.OrderedQuestions** em todas as associações de elementos aninhados.</span><span class="sxs-lookup"><span data-stu-id="79c7c-827">Select **Bind**, and then confirm that the current **model.Questionnaire.Questions** path is replaced by the new **model.Questionnaire.OrderedQuestions** path in all bindings of nested elements.</span></span>
12. <span data-ttu-id="79c7c-828">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-828">Select **Save**.</span></span>

![Associação do elemento de formato da pergunta à fonte de dados OrderedQuestions configurada no designer de Operação do ER](./media/er-quick-start1-bindings4.png)

### <a name="run-a-modified-format-from-er"></a><a name="RunFormatFromER2"></a><span data-ttu-id="79c7c-830">Executar um formato modificado a partir de ER</span><span class="sxs-lookup"><span data-stu-id="79c7c-830">Run a modified format from ER</span></span>

<span data-ttu-id="79c7c-831">Agora você pode executar um formato modificado para fins de teste a partir da estrutura de ER.</span><span class="sxs-lookup"><span data-stu-id="79c7c-831">You can now run a modified format for testing purposes from the ER framework.</span></span>

1. <span data-ttu-id="79c7c-832">Na página **Designer de formato**, selecione **Executar**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-832">On the **Format designer** page, select **Run**.</span></span>
2. <span data-ttu-id="79c7c-833">Na caixa de diálogo **Parâmetros de ER**, na FastTab **Registros a serem incluídos**, configure a opção de filtragem para que somente o questionário **SBCCrsExam** seja incluído.</span><span class="sxs-lookup"><span data-stu-id="79c7c-833">In the **ER parameters** dialog box, on the **Records to include** FastTab, configure the filtering option so that only the **SBCCrsExam** questionnaire is included.</span></span>
3. <span data-ttu-id="79c7c-834">Selecione **OK** para confirmar a opção de filtragem.</span><span class="sxs-lookup"><span data-stu-id="79c7c-834">Select **OK** to confirm the filtering option.</span></span>
4. <span data-ttu-id="79c7c-835">Selecione **OK** para executar o relatório.</span><span class="sxs-lookup"><span data-stu-id="79c7c-835">Select **OK** to run the report.</span></span>
5. <span data-ttu-id="79c7c-836">Revise o relatório gerado.</span><span class="sxs-lookup"><span data-stu-id="79c7c-836">Review the generated report.</span></span>

<span data-ttu-id="79c7c-837">A ilustração a seguir mostra um relatório gerado no formato Excel, no qual as perguntas estão corretamente ordenadas.</span><span class="sxs-lookup"><span data-stu-id="79c7c-837">The following illustration shows a generated report in Excel format where the questions are correctly ordered.</span></span>

![Relatório gerado no formato Excel com perguntas corretamente ordenadas](./media/er-quick-start1-report2.png)

### <a name="complete-the-format-design"></a><a name="CompleteFormat"></a><span data-ttu-id="79c7c-839">Concluir a criação do formato</span><span class="sxs-lookup"><span data-stu-id="79c7c-839">Complete the format design</span></span>

1. <span data-ttu-id="79c7c-840">Vá para **Administração da organização** \> **Relatório eletrônico** \> **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-840">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="79c7c-841">Na página **Configurações**, na árvore de configurações, expanda **Modelo de questionário** e selecione **Relatório de questionário**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-841">On the **Configurations** page, in the configuration tree, expand **Questionnaire model**, and then select **Questionnaire report**.</span></span>
3. <span data-ttu-id="79c7c-842">Na FastTab **Versões**, selecione a versão de configuração com o status **Rascunho**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-842">On the **Versions** FastTab, select the configuration version that has a status of **Draft**.</span></span>
4. <span data-ttu-id="79c7c-843">Selecione **Alterar status** \> **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-843">Select **Change status** \> **Complete**.</span></span>

<span data-ttu-id="79c7c-844">O status da versão 1.1 dessa configuração é alterado de **Rascunho** para **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-844">The status of version 1.1 of this configuration is changed from **Draft** to **Completed**.</span></span> <span data-ttu-id="79c7c-845">A versão 1.1 não pode mais ser alterada.</span><span class="sxs-lookup"><span data-stu-id="79c7c-845">Version 1.1 can no longer be changed.</span></span> <span data-ttu-id="79c7c-846">Esta versão contém o formato configurado e pode ser usada para imprimir o relatório personalizado.</span><span class="sxs-lookup"><span data-stu-id="79c7c-846">This version contains the configured format and can be used to print your custom report.</span></span> <span data-ttu-id="79c7c-847">A versão 1.2 dessa configuração é criada e tem um status **Rascunho**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-847">Version 1.2 of this configuration is created and has a status of **Draft**.</span></span> <span data-ttu-id="79c7c-848">Você pode editar esta versão para ajustar a formatar o relatório **Questionário**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-848">You can edit this version to adjust the format of your **Questionnaire** report.</span></span>

![Versões da configuração do ER editável na página Configurações](./media/er-quick-start1-format-configuration.png)

> [!NOTE]
> <span data-ttu-id="79c7c-850">O formato configurado é o design do relatório **Questionário** e não contém relações com artefatos específicos do Finance.</span><span class="sxs-lookup"><span data-stu-id="79c7c-850">The configured format is your design of the **Questionnaire** report and contains no relations to the Finance-specific artefacts.</span></span>

## <a name="develop-application-artefacts-to-call-the-designed-report"></a><a name="DevelopCustomCode"></a><span data-ttu-id="79c7c-851">Desenvolver artefatos de aplicativos para chamar o relatório criado</span><span class="sxs-lookup"><span data-stu-id="79c7c-851">Develop application artefacts to call the designed report</span></span>

<span data-ttu-id="79c7c-852">Como um usuário na função Administrador do sistema, você deve desenvolver uma nova lógica para que o formato ER configurado possa ser chamado a partir da interface do usuário do aplicativo (IU) para gerar o relatório personalizado.</span><span class="sxs-lookup"><span data-stu-id="79c7c-852">As a user in the System Administrator role, you must develop new logic so that the configured ER format can be called from the application user interface (UI) to generate your custom report.</span></span> <span data-ttu-id="79c7c-853">No momento, o ER não oferece recursos para a configuração desse tipo de lógica.</span><span class="sxs-lookup"><span data-stu-id="79c7c-853">Currently, ER doesn't offer any capability for configuring this type of logic.</span></span> <span data-ttu-id="79c7c-854">Portanto, é necessário algum trabalho de engenharia.</span><span class="sxs-lookup"><span data-stu-id="79c7c-854">Therefore, some engineering work is required.</span></span> 

<span data-ttu-id="79c7c-855">Para desenvolver a nova lógica, você deve implantar uma topologia que dê suporte à compilação contínua.</span><span class="sxs-lookup"><span data-stu-id="79c7c-855">To develop the new logic, you must deploy a topology that supports continuous build.</span></span> <span data-ttu-id="79c7c-856">Para obter mais informações, consulte [Implantar topologias que dão suporte à contínua automação de compilações e testes](../perf-test/continuous-build-test-automation.md).</span><span class="sxs-lookup"><span data-stu-id="79c7c-856">For more information, see [Deploy topologies that support continuous build and test automation](../perf-test/continuous-build-test-automation.md).</span></span> <span data-ttu-id="79c7c-857">Você também deve ter acesso ao ambiente de desenvolvimento para essa topologia.</span><span class="sxs-lookup"><span data-stu-id="79c7c-857">You must also have access to the development environment for this topology.</span></span> <span data-ttu-id="79c7c-858">Para obter mais informações sobre a API de ER disponível, consulte [API da estrutura de ER](er-apis-app73.md).</span><span class="sxs-lookup"><span data-stu-id="79c7c-858">For more information about the available ER API, see [ER framework API](er-apis-app73.md).</span></span>

### <a name="modify-source-code"></a><a name="ModifySourceCode"></a><span data-ttu-id="79c7c-859">Modificar o código-fonte</span><span class="sxs-lookup"><span data-stu-id="79c7c-859">Modify source code</span></span>

#### <a name="add-a-data-contract-class"></a><a name="DataContractClass"></a><span data-ttu-id="79c7c-860">Adicionar uma classe de contrato de dados</span><span class="sxs-lookup"><span data-stu-id="79c7c-860">Add a data contract class</span></span>

<span data-ttu-id="79c7c-861">Adicione a nova classe **QuestionnairesErReportContract** ao projeto Microsoft Visual Studio e escreva o código que especifica o contrato de dados que deve ser usado para executar o formato ER configurado.</span><span class="sxs-lookup"><span data-stu-id="79c7c-861">Add the new **QuestionnairesErReportContract** class to your Microsoft Visual Studio project, and write code that specifies the data contract that should be used to run the configured ER format.</span></span>

```xpp
/// <summary>
///     This class is the data contract class for the <c>QuestionnairesErReportDP</c> class.
/// </summary>
/// <remarks>
///    This is the data contract class for the Questionnaires ER report.
/// </remarks>
[
    DataContractAttribute,
    SysOperationContractProcessingAttribute(classStr(QuestionnairesErReportUIBuilder))
    ]
    public class QuestionnairesErReportContract extends ERFormatMappingRunBaseContract implements SysOperationValidatable
{
    ERFormatMappingId formatMapping;

    /// <summary>
    ///    Validates the report parameters.
    /// </summary>
    /// <returns>
    ///    true if no errors; otherwise, false.
    /// </returns>
    public boolean validate()
    {
        boolean ret = true;
        if (!formatMapping)
        {
            ret = checkFailed(strFmt("@SYS26332", new SysDictType(extendedTypeNum(ERFormatMappingId)).label()));
        }
        return ret;
    }
    [
        DataMemberAttribute('FormatMapping'),
        SysOperationLabelAttribute(literalstr("@ElectronicReporting:FormatMapping")),
        SysOperationHelpTextAttribute(literalstr("@ElectronicReporting:FormatMapping"))
    ]
    public ERFormatMappingId parmFormatMapping(ERFormatMappingId _formatMapping = formatMapping)
    {
        formatMapping = _formatMapping;
        return formatMapping;
    }
}
```

#### <a name="add-a-ui-builder-class"></a><a name="UIBuilderClass"></a><span data-ttu-id="79c7c-862">Adicionar uma classe do construtor de interface de usuário</span><span class="sxs-lookup"><span data-stu-id="79c7c-862">Add a UI builder class</span></span>

<span data-ttu-id="79c7c-863">Adicione a nova classe **QuestionnairesErReportUIBuilder** ao projeto do Visual Studio e escreva o código para gerar uma caixa de diálogo em tempo de execução que será usada para pesquisar a ID de mapeamento do formato do formato de ER que deve ser executado.</span><span class="sxs-lookup"><span data-stu-id="79c7c-863">Add the new **QuestionnairesErReportUIBuilder** class to your Visual Studio project, and write code to generate a runtime dialog box that will be used to look up the format mapping ID of the ER format that must be run.</span></span> <span data-ttu-id="79c7c-864">O código fornecido pesquisa somente os formatos de ER que contêm uma fonte de dados do tipo **Modelo de dados**, que se refere ao modelo de dados **[Questionários](#DataModeName)**, por meio do uso da definição **[Raiz](#RootDefinitionName)**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-864">The provided code looks up only ER formats that contain a data source of the **Data model** type that refers to the **[Questionnaires](#DataModeName)** data model by using the **[Root](#RootDefinitionName)** definition.</span></span>

> [!NOTE]
> <span data-ttu-id="79c7c-865">Como alternativa, você pode usar os pontos de integração de ER para filtrar os formatos de ER.</span><span class="sxs-lookup"><span data-stu-id="79c7c-865">Alternatively, you can use ER integration points to filter ER formats.</span></span> <span data-ttu-id="79c7c-866">Para obter mais informações, consulte [API para mostrar uma pesquisa de mapeamento de formato](er-apis-app10-0-11.md#api-to-show-a-format-mapping-lookup).</span><span class="sxs-lookup"><span data-stu-id="79c7c-866">For more information, see [API to show a format mapping lookup](er-apis-app10-0-11.md#api-to-show-a-format-mapping-lookup).</span></span>

```xpp
/// <summary>
/// The UIBuilder class for Questionnaires ER report
/// </summary>
class QuestionnairesErReportUIBuilder extends SysOperationAutomaticUIBuilder
{
    public const str ERQuestionnairesModel = 'Questionnaires';
    public const str ERQuestionnairesDataContainer = 'Root';

    /// <summary>
    /// Action after build of the dialog UI.
    /// </summary>
    public void postBuild()
    {
        DialogField formatMapping;
        super();
        formatMapping = this.bindInfo().getDialogField(this.dataContractObject(),
            methodStr(QuestionnairesErReportContract, parmFormatMapping));
        formatMapping.registerOverrideMethod(
            methodStr(FormReferenceControl, lookupReference),
            methodStr(QuestionnairesErReportUIBuilder, formatMappingLookup),
            this);
    }

    /// <summary>
    /// Performs the lookup form for format mapping.
    /// </summary>
    /// <param name="_referenceGroupControl">
    /// The control to perform lookup form.
    /// </param>
    public void formatMappingLookup(FormReferenceControl _referenceGroupControl)
    {
        ERObjectsFactory::createFormatMappingTableLookupForControlAndModel(
            _referenceGroupControl,
            ERQuestionnairesModel,
            ERQuestionnairesDataContainer).performFormLookup();
    }
}
```

#### <a name="add-a-data-provider-class"></a><a name="DataProviderClass"></a><span data-ttu-id="79c7c-867">Adicionar uma classe de provedor de dados</span><span class="sxs-lookup"><span data-stu-id="79c7c-867">Add a data provider class</span></span>

<span data-ttu-id="79c7c-868">Adicione a nova classe **QuestionnairesErReportDP** ao projeto Visual Studio e escreva o código que apresenta o provedor de dados que deve ser usado para executar o formato de ER configurado.</span><span class="sxs-lookup"><span data-stu-id="79c7c-868">Add the new **QuestionnairesErReportDP** class to your Visual Studio project, and write code that introduces the data provider that should used to run the configured ER format.</span></span> <span data-ttu-id="79c7c-869">O código fornecido inclui somente o contrato de dados deste provedor de dados.</span><span class="sxs-lookup"><span data-stu-id="79c7c-869">The provided code includes only the data contract for this data provider.</span></span>

```xpp
/// <summary>
/// Data provider class for Questionnaires ER report.
/// </summary>
public class QuestionnairesErReportDP
{
    QuestionnairesErReportContract contract;
    public static QuestionnairesErReportDP construct()
    {
        QuestionnairesErReportDP  dataProvider;
        dataProvider = new QuestionnairesErReportDP();
        return dataProvider;
    }
}
```

#### <a name="add-a-labels-file"></a><a name="LabelsFile"></a><span data-ttu-id="79c7c-870">Adicionar um arquivo de rótulos</span><span class="sxs-lookup"><span data-stu-id="79c7c-870">Add a labels file</span></span>

<span data-ttu-id="79c7c-871">Adicione o novo arquivo de rótulos **QuestionnairesErReportLabels\_en-US** ao projeto do Visual Studio e especifique os seguintes rótulos para novos recursos da interface do usuário:</span><span class="sxs-lookup"><span data-stu-id="79c7c-871">Add the new **QuestionnairesErReportLabels\_en-US** labels file to your Visual Studio project, and specify the following labels for new UI resources:</span></span>

- <span data-ttu-id="79c7c-872">O rótulo **\@QuestionnairesReport** de um novo item de menu que contém o seguinte texto em inglês dos EUA (en-US): **Relatório Questionários (alimentado pelo ER)**</span><span class="sxs-lookup"><span data-stu-id="79c7c-872">The **\@QuestionnairesReport** label for a new menu item that contains the following text in US English (en-US): **Questionnaires report (powered by ER)**</span></span>
- <span data-ttu-id="79c7c-873">O rótulo **\@QuestionnairesReportBatchJobDescription** de um cargo de lote se um formato de ER selecionado for agendado para execução como um trabalho em lotes</span><span class="sxs-lookup"><span data-stu-id="79c7c-873">The **\@QuestionnairesReportBatchJobDescription** label for a batch job title if a selected ER format is scheduled for execution as a batch job</span></span>

#### <a name="add-a-report-service-class"></a><a name="ServiceClass"></a><span data-ttu-id="79c7c-874">Adicionar uma classe de serviço de relatório</span><span class="sxs-lookup"><span data-stu-id="79c7c-874">Add a report service class</span></span>

<span data-ttu-id="79c7c-875">Adicione a nova classe **QuestionnairesErReportService** ao projeto do Visual Studio e escreva o código que chama um formato de ER, o identifica por uma ID de mapeamento de formato e fornece um contrato de dados como um parâmetro.</span><span class="sxs-lookup"><span data-stu-id="79c7c-875">Add the new **QuestionnairesErReportService** class to your Visual Studio project, and write code that calls an ER format, identifies it by a format mapping ID, and provides a data contract as a parameter.</span></span>

```xpp
using Microsoft.Dynamics365.LocalizationFramework;
/// <summary>
/// The electronic reporting service class for Questionnaires ER report
/// </summary>
class QuestionnairesErReportService extends SysOperationServiceBase
{
    public const str ERModelDataSourceName = 'model';
    public const str DefaultExportedFileName = 'Questionnaires report';
    public const str ParametersDataSourceName = 'RunTimeParameters';

    /// <summary>
    /// Generates report by using Electronic reporting framework
    /// </summary>
    /// <param name = "_contract">The Questionnaires report contract</param>
    public void generateReportByGER(QuestionnairesErReportContract _contract)
    {
        ERFormatMappingId formatMappingId;
        QuestionnairesErReportDP  dataProvider;
        dataProvider = QuestionnairesErReportDP::construct();
        formatMappingId = _contract.parmFormatMapping();
        if (formatMappingId)
        {
            try
            {
                ERIModelDefinitionParamsAction parameters = new ERModelDefinitionParamsUIActionComposite()
                    .add(new ERModelDefinitionObjectParameterAction(ERModelDataSourceName, ParametersDataSourceName, _contract, true));

                // Call ER to generate the report.
                ERIFormatMappingRun formatMappingRun = ERObjectsFactory::createFormatMappingRunByFormatMappingId(formatMappingId, DefaultExportedFileName);
                if (formatMappingRun.parmShowPromptDialog(true))
                {
                    formatMappingRun.withParameter(parameters);
                    formatMappingRun.withFileDestination(_contract.getFileDestination());
                    formatMappingRun.run();
                }
            }
            catch
            {
                // An error occurred while exporting data.
                error("@SYP4861341");
            }
        }
        else
        {
            // There is no data available.
            info("@SYS300117");
        }
    }
}
```

<span data-ttu-id="79c7c-876">Quando você precisa usar um formato de ER que executa dados de aplicativo, deve configurar uma fonte de dados do tipo **Modelo de dados** no mapeamento de formato.</span><span class="sxs-lookup"><span data-stu-id="79c7c-876">When you must use an ER format that runs application data, you must configure a data source of the **Data model** type in the format mapping.</span></span> <span data-ttu-id="79c7c-877">Essa fonte de dados se refere a uma parte específica do modelo de dados especificado usando uma única definição de raiz.</span><span class="sxs-lookup"><span data-stu-id="79c7c-877">This data source refers to a specific part of the specified data model by using a single root definition.</span></span> <span data-ttu-id="79c7c-878">Quando o formato de ER é executado, ele chama essa fonte de dados para acessar o mapeamento do modelo de ER apropriado configurado para determinada definição de modelo e raiz.</span><span class="sxs-lookup"><span data-stu-id="79c7c-878">When the ER format is run, it calls this data source to access the appropriate ER model mapping that is configured for a given model and root definition.</span></span>

<span data-ttu-id="79c7c-879">Todas as informações que você pode preparar no código-fonte e no armazenamento como parte do contrato de dados podem ser passadas para o formato de ER em execução usando um mapeamento do modelo de ER deste tipo.</span><span class="sxs-lookup"><span data-stu-id="79c7c-879">All the information that you might prepare in the source code and store as part of the data contract can be passed to the running ER format by using an ER model mapping of this type.</span></span> <span data-ttu-id="79c7c-880">No mapeamento do modelo de ER, você deve configurar uma fonte de dados do tipo **Objeto** que se refere à classe **[QuestionnairesErReportContract](#DataContractClass)**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-880">In the ER model mapping, you must configure a data source of the **Object** type that refers to the **[QuestionnairesErReportContract](#DataContractClass)** class.</span></span> <span data-ttu-id="79c7c-881">Para identificar um mapeamento de modelos, você deve especificar uma fonte de dados que chame esse mapeamento de modelo.</span><span class="sxs-lookup"><span data-stu-id="79c7c-881">To identify a model mapping, you must specify a data source that calls this model mapping.</span></span> <span data-ttu-id="79c7c-882">No código fornecido, essa fonte de dados especificada pela constante **ERModelDataSourceName** que tem o valor do **[modelo](#ModelDSName)**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-882">In the provided code, this data source specified by the **ERModelDataSourceName** constant that has the **[model](#ModelDSName)** value.</span></span> <span data-ttu-id="79c7c-883">Para identificar qual fonte de dados é usada para expor o contrato de dados no mapeamento do modelo, você deve especificar um nome de fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="79c7c-883">To identify which data source is used to expose the data contract in the model mapping, you must specify a data source name.</span></span> <span data-ttu-id="79c7c-884">No código fornecido, esse nome é especificado pela constante **ParametersDataSourceName** que tem o valor <a name="DataContractDSName"></a>**RunTimeParameters**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-884">In the provided code, this name is specified by the **ParametersDataSourceName** constant that has <a name="DataContractDSName"></a>**RunTimeParameters** value.</span></span>

> [!NOTE]
> <span data-ttu-id="79c7c-885">Em um novo ambiente, talvez seja necessário atualizar os metadados ER para que esse tipo de classe esteja disponível no designer de mapeamento do modelo ER.</span><span class="sxs-lookup"><span data-stu-id="79c7c-885">In a new environment, you might have to refresh the ER metadata so that this type of class is available in the ER model mapping designer.</span></span> <span data-ttu-id="79c7c-886">Para obter mais informações, consulte [Configurar a estrutura do ER](electronic-reporting-er-configure-parameters.md#frequently-asked-questions).</span><span class="sxs-lookup"><span data-stu-id="79c7c-886">For more information, see [Configure the ER framework](electronic-reporting-er-configure-parameters.md#frequently-asked-questions).</span></span>

#### <a name="add-a-report-controller-class"></a><a name="ControllerClass"></a><span data-ttu-id="79c7c-887">Adicionar uma classe de controlador de relatório</span><span class="sxs-lookup"><span data-stu-id="79c7c-887">Add a report controller class</span></span>

<span data-ttu-id="79c7c-888">Adicione a nova classe **QuestionnairesErReportController** ao projeto do Visual Studio e escreva o código que executa um formato de ER no modo síncrono ou no modo de lotes, como preferir, na caixa de diálogo criada com base na lógica da classe **QuestionnairesErReportUIBuilder** fornecida.</span><span class="sxs-lookup"><span data-stu-id="79c7c-888">Add the new **QuestionnairesErReportController** class to your Visual Studio project, and write code that runs an ER format in either synchronous mode or batch mode, as you prefer, in the dialog box that is built based on the logic of the provided **QuestionnairesErReportUIBuilder** class.</span></span>

```xpp
/// <summary>
/// The controller for Questionnaires ER report
/// </summary>
class QuestionnairesErReportController extends ERFormatMappingRunBaseController
{
    /// <summary>
    /// The main entrance of the controller
    /// </summary>
    /// <param name = "args">The arguments</param>
    public static void main(Args args)
    {
        QuestionnairesErReportController operation;
        operation = new QuestionnairesErReportController(
            classStr(QuestionnairesErReportService),
            methodStr(QuestionnairesErReportService, generateReportByGER),
            SysOperationExecutionMode::Synchronous);
        operation.startOperation();
    }

    /// <summary>
    /// Gets caption of the dialog.
    /// </summary>
    /// <returns>Caption of the dialog</returns>
    public ClassDescription defaultCaption()
    {
        ClassDescription batchDescription;
        batchDescription = "Questionnaires report (powered by ER)";
        return batchDescription;
    }
}
```

#### <a name="add-a-menu-item"></a><a name="MenuItem"></a><span data-ttu-id="79c7c-889">Adicionar um item de menu</span><span class="sxs-lookup"><span data-stu-id="79c7c-889">Add a menu item</span></span>

<span data-ttu-id="79c7c-890">Adicione o novo item de menu **QuestionnairesErReport** ao projeto do Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="79c7c-890">Add the new **QuestionnairesErReport** menu item to your Visual Studio project.</span></span> <span data-ttu-id="79c7c-891">Na propriedade **Objeto**, esse item de menu se refere à classe **QuestionnairesErReportController** e é usado para especificar uma permissão de usuário para selecionar e executar um formato de ER.</span><span class="sxs-lookup"><span data-stu-id="79c7c-891">In the **Object** property, this menu item refers to the **QuestionnairesErReportController** class, and it's used to specify a user permission to select and run an ER format.</span></span> <span data-ttu-id="79c7c-892">Na propriedade **Rótulo**, esse item de menu se refere ao rótulo **\@QuestionnairesReport** que você criou anteriormente, de forma que o texto correto seja apresentado na interface do usuário do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="79c7c-892">In the **Label** property, this menu item refers to the **\@QuestionnairesReport** label that you created earlier, so that correct text is presented in the application UI.</span></span>

#### <a name="add-a-menu-item-to-a-menu"></a><a name="Menu"></a><span data-ttu-id="79c7c-893">Adicionar um item de menu a um menu</span><span class="sxs-lookup"><span data-stu-id="79c7c-893">Add a menu item to a menu</span></span>

<span data-ttu-id="79c7c-894">Adicione o menu **KM** existente ao projeto do Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="79c7c-894">Add the existing **KM** menu to your Visual Studio project.</span></span> <span data-ttu-id="79c7c-895">Você deve adicionar um novo item **QuestionnairesErReport** do tipo **Saída** a este menu.</span><span class="sxs-lookup"><span data-stu-id="79c7c-895">You must add a new **QuestionnairesErReport** item of the **Output** type to this menu.</span></span> <span data-ttu-id="79c7c-896">Este item deve se referir ao item de menu **QuestionnairesErReport** descrito na seção anterior.</span><span class="sxs-lookup"><span data-stu-id="79c7c-896">This item must refer to the **QuestionnairesErReport** menu item that is described in the previous section.</span></span>

#### <a name="build-a-visual-studio-project"></a><a name="BuildVSProject"></a><span data-ttu-id="79c7c-897">Criar um projeto do Visual Studio</span><span class="sxs-lookup"><span data-stu-id="79c7c-897">Build a Visual Studio project</span></span>

<span data-ttu-id="79c7c-898">Crie seu projeto para disponibilizar um novo item de menu para os usuários.</span><span class="sxs-lookup"><span data-stu-id="79c7c-898">Build your project to make a new menu item available to users.</span></span>

### <a name="run-a-format-from-the-application"></a><a name="RunFormatFromApp"></a><span data-ttu-id="79c7c-899">Executar um formato do aplicativo</span><span class="sxs-lookup"><span data-stu-id="79c7c-899">Run a format from the application</span></span>

1. <span data-ttu-id="79c7c-900">Vá para **Questionário** \> **Design** \> **Relatório Questionários (alimentado pelo ER)**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-900">Go to **Questionnaire** \> **Design** \> **Questionnaires report (powered by ER)**.</span></span>

    ![Seleção do item de menu do relatório Questionários (alimentado pelo ER) no módulo Questionário para executar o formato de ER configurado](./media/er-quick-start1-application-menu-modified.png)

2. <span data-ttu-id="79c7c-902">Na caixa de diálogo, no campo **Mapeamento de formato**, selecione **relatório Questionários**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-902">In the dialog box, in the **Format mapping** field, select **Questionnaires report**.</span></span>
3. <span data-ttu-id="79c7c-903">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-903">Select **OK**.</span></span>
4. <span data-ttu-id="79c7c-904">Na caixa de diálogo **Parâmetros de relatório eletrônico**, na FastTab **Registros a serem incluídos**, configure a opção de filtragem para que somente o questionário **SBCCrsExam** seja incluído.</span><span class="sxs-lookup"><span data-stu-id="79c7c-904">In the **Electronic report parameters** dialog box, on the **Records to include** FastTab, configure the filtering option so that only the **SBCCrsExam** questionnaire is included.</span></span>
5. <span data-ttu-id="79c7c-905">Selecione **OK** para confirmar a opção de filtragem.</span><span class="sxs-lookup"><span data-stu-id="79c7c-905">Select **OK** to confirm the filtering option.</span></span>
6. <span data-ttu-id="79c7c-906">Selecione **OK** para executar o relatório.</span><span class="sxs-lookup"><span data-stu-id="79c7c-906">Select **OK** to run the report.</span></span>

    ![Como especificar os critérios de seleção na caixa de diálogo Relatório eletrônico](./media/er-quick-start1-report-run-dialog-page.png)

7. <span data-ttu-id="79c7c-908">Revise o relatório gerado.</span><span class="sxs-lookup"><span data-stu-id="79c7c-908">Review the generated report.</span></span>

## <a name="tune-a-designed-er-solution"></a><a name="TuneSolution"></a><span data-ttu-id="79c7c-909">Ajustar uma solução de ER criada</span><span class="sxs-lookup"><span data-stu-id="79c7c-909">Tune a designed ER solution</span></span>

<span data-ttu-id="79c7c-910">Você pode modificar a solução de ER configurada de forma que use a classe de provedor de dados que desenvolveu para acessar detalhes da execução do formato de ER e para que ela insira o nome do formato de ER em um relatório gerado.</span><span class="sxs-lookup"><span data-stu-id="79c7c-910">You can modify the configured ER solution so that it uses the data provider class that you developed to access details of the running ER format, and so that it enters the name of this ER format in a generated report.</span></span>

### <a name="modify-a-model-mapping"></a><a name="ModifyModelMapping"></a><span data-ttu-id="79c7c-911">Modificar um mapeamento de modelo</span><span class="sxs-lookup"><span data-stu-id="79c7c-911">Modify a model mapping</span></span>

#### <a name="add-data-sources-to-access-a-data-contract-object"></a><a name="AddDataSource1"></a><span data-ttu-id="79c7c-912">Adicionar fontes de dados para acessar um objeto de contrato de dados</span><span class="sxs-lookup"><span data-stu-id="79c7c-912">Add data sources to access a data contract object</span></span>

1. <span data-ttu-id="79c7c-913">Vá para **Administração da organização** \> **Relatório eletrônico** \> **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-913">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="79c7c-914">Na página **Configurações**, na árvore de configurações, expanda **Modelo de questionário** e selecione **Mapeamento de questionário**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-914">On the **Configurations** page, in the configuration tree, expand **Questionnaire model**, and then select **Questionnaire mapping**.</span></span>
3. <span data-ttu-id="79c7c-915">Selecione **Designer** para abrir a página **Modelo para mapeamento de fonte de dados**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-915">Select **Designer** to open the **Model to datasource mapping** page.</span></span>
4. <span data-ttu-id="79c7c-916">Selecione **Designer** para abrir o mapeamento selecionado no designer de mapeamento de modelo.</span><span class="sxs-lookup"><span data-stu-id="79c7c-916">Select **Designer** to open the selected mapping in the model mapping designer.</span></span>
5. <span data-ttu-id="79c7c-917">Na página **Designer de mapeamento de modelo**, no painel **Tipos de fontes de dados**, selecione **Dynamics 365 for Operations\\Objeto**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-917">On the **Model mapping designer** page, in the **Data source types** pane, select **Dynamics 365 for Operations\\Object**.</span></span>
6. <span data-ttu-id="79c7c-918">No painel **Fontes de dados**, selecione **Adicionar raiz**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-918">In the **Data sources** pane, select **Add root**.</span></span>
7. <span data-ttu-id="79c7c-919">Na caixa de diálogo, no campo **Nome**, insira **[RunTimeParameters](#DataContractDSName)**, conforme definido no código-fonte da classe **QuestionnairesErReportService**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-919">In the dialog box, in the **Name** field, enter **[RunTimeParameters](#DataContractDSName)**, as defined in the source code of the **QuestionnairesErReportService** class.</span></span>
8. <span data-ttu-id="79c7c-920">No campo **Classe**, insira **[QuestionnairesErReportContract](#DataContractClass)**, que foi codificado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="79c7c-920">In the **Class** field, enter **[QuestionnairesErReportContract](#DataContractClass)**, which was coded earlier.</span></span>
9. <span data-ttu-id="79c7c-921">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-921">Select **OK**.</span></span>
10. <span data-ttu-id="79c7c-922">Expanda **RunTimeParameters**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-922">Expand **RunTimeParameters**.</span></span>

<span data-ttu-id="79c7c-923">A fonte de dados adicionada fornece informações sobre a ID de registro do mapeamento de formato de ER em execução.</span><span class="sxs-lookup"><span data-stu-id="79c7c-923">The added data source provides information about the record ID of the running ER format mapping.</span></span>

![Fonte de dados adicionada no designer de mapeamento do modelo de ER](./media/er-quick-start1-mapping3.png)

#### <a name="add-a-data-source-to-access-er-format-mapping-records"></a><a name="AddDataSource2"></a><span data-ttu-id="79c7c-925">Adicionar uma fonte de dados para acessar registros de mapeamento de formato de ER</span><span class="sxs-lookup"><span data-stu-id="79c7c-925">Add a data source to access ER format mapping records</span></span>

<span data-ttu-id="79c7c-926">Continue para editar o mapeamento de modelos selecionado, adicionando uma fonte de dados para acessar registros de mapeamento de formato de ER.</span><span class="sxs-lookup"><span data-stu-id="79c7c-926">Continue to edit the selected model mapping by adding a data source to access ER format mapping records.</span></span>

1. <span data-ttu-id="79c7c-927">Na página **Designer de mapeamento de modelo**, no painel **Tipos de fontes de dados**, selecione **Dynamics 365 for Operations\\Registros de tabela**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-927">On the **Model mapping designer** page, in the **Data source types** pane, select **Dynamics 365 for Operations\\Table records**.</span></span>
2. <span data-ttu-id="79c7c-928">No painel **Fontes de dados**, selecione **Adicionar raiz**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-928">In the **Data sources** pane, select **Add root**.</span></span>
3. <span data-ttu-id="79c7c-929">Na caixa de diálogo, no campo **Nome** , insira **ER1**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-929">In the dialog box, in the **Name** field, enter **ER1**.</span></span>
4. <span data-ttu-id="79c7c-930">No campo **Tabela**, insira **ERFormatMappingTable**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-930">In the **Table** field, enter **ERFormatMappingTable**.</span></span>
5. <span data-ttu-id="79c7c-931">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-931">Select **OK**.</span></span>

#### <a name="add-a-data-source-to-access-a-format-mapping-record-of-a-running-er-format"></a><a name="AddDataSource3"></a><span data-ttu-id="79c7c-932">Adicionar uma fonte de dados para acessar um registro de mapeamento de formato de um formato de ER em execução</span><span class="sxs-lookup"><span data-stu-id="79c7c-932">Add a data source to access a format mapping record of a running ER format</span></span>

<span data-ttu-id="79c7c-933">Continue para editar o mapeamento de modelos selecionado, adicionando uma fonte de dados para acessar o registro de mapeamento do formato de ER em execução.</span><span class="sxs-lookup"><span data-stu-id="79c7c-933">Continue to edit the selected model mapping by adding a data source to access the format mapping record of the running ER format.</span></span>

1. <span data-ttu-id="79c7c-934">Na página **Designer de mapeamento de modelo**, no painel **Tipos de fontes de dados**, selecione **Funções\\Campo calculado**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-934">On the **Model mapping designer** page, in the **Data source types** pane, select **Functions\\Calculated field**.</span></span>
2. <span data-ttu-id="79c7c-935">No painel **Fontes de dados**, selecione **Adicionar raiz**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-935">In the **Data sources** pane, select **Add root**.</span></span>
3. <span data-ttu-id="79c7c-936">Na caixa de diálogo, no campo **Nome** , insira **ER2**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-936">In the dialog box, in the **Name** field, enter **ER2**.</span></span>
4. <span data-ttu-id="79c7c-937">Selecione **Editar fórmula**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-937">Select **Edit formula**.</span></span>
5. <span data-ttu-id="79c7c-938">No editor de fórmulas, no campo **Fórmula**, insira **FIRSTORNULL (FILTER(ER1, ER1.RecId = RunTimeParameters.parmFormatMapping))**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-938">In the formula editor, in the **Formula** field, enter **FIRSTORNULL (FILTER(ER1, ER1.RecId = RunTimeParameters.parmFormatMapping))**.</span></span>
6. <span data-ttu-id="79c7c-939">Selecione **Salvar** e feche o editor de fórmula.</span><span class="sxs-lookup"><span data-stu-id="79c7c-939">Select **Save**, and close the formula editor.</span></span>
7. <span data-ttu-id="79c7c-940">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-940">Select **OK**.</span></span>

#### <a name="enter-the-name-of-the-running-er-format-in-the-data-model"></a><a name="AddBinding"></a><span data-ttu-id="79c7c-941">Inserir o nome do formato de ER em execução no modelo de dados</span><span class="sxs-lookup"><span data-stu-id="79c7c-941">Enter the name of the running ER format in the data model</span></span>

<span data-ttu-id="79c7c-942">Continue para editar o mapeamento de modelo selecionado, de forma que o nome do formato ER em execução seja inserido no modelo de dados.</span><span class="sxs-lookup"><span data-stu-id="79c7c-942">Continue to edit the selected model mapping so that the name of the running ER format is entered in the data model.</span></span>

1. <span data-ttu-id="79c7c-943">Na página **Designer de mapeamento de modelo**, no painel **Modelo de dados**, expanda **ExecutionContext** e selecione **ExecutionContext\\FormatName**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-943">On the **Model mapping designer** page, in the **Data model** pane, expand **ExecutionContext**, and then select **ExecutionContext\\FormatName**.</span></span>
2. <span data-ttu-id="79c7c-944">No painel **Modelo de dados**, selecione **Editar** para configurar uma associação de dados para o campo do modelo de dados selecionado.</span><span class="sxs-lookup"><span data-stu-id="79c7c-944">In the **Data model** pane, select **Edit** to configure a data binding for the selected data model's field.</span></span>
3. <span data-ttu-id="79c7c-945">No editor de fórmulas, no campo **Fórmula**, insira **FIRSTORNULL (ER2.'\>Relations'.Format).Name**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-945">In the formula editor, in the **Formula** field, enter **FIRSTORNULL (ER2.'\>Relations'.Format).Name**.</span></span>
4. <span data-ttu-id="79c7c-946">Selecione **Salvar** e feche o editor de fórmula.</span><span class="sxs-lookup"><span data-stu-id="79c7c-946">Select **Save**, and close the formula editor.</span></span>

<span data-ttu-id="79c7c-947">Como você utilizou o campo **FormatName**, o mapeamento do modelo configurado agora expõe o nome de um formato de ER que chama esse mapeamento de modelo durante a execução.</span><span class="sxs-lookup"><span data-stu-id="79c7c-947">Because you used the **FormatName** field, the configured model mapping now exposes the name of an ER format that calls this model mapping during execution.</span></span>

![Associação do campo de modelo de dados ao método da fonte de dados adicionada no designer de mapeamento do modelo de ER](./media/er-quick-start1-mapping4.png)

#### <a name="complete-the-design-of-the-model-mapping"></a><a name="CompleteModelMapping2"></a><span data-ttu-id="79c7c-949">Concluir o design de mapeamento de modelo</span><span class="sxs-lookup"><span data-stu-id="79c7c-949">Complete the design of the model mapping</span></span>

1. <span data-ttu-id="79c7c-950">Na página **Designer de mapeamento de modelo**, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-950">On the **Model mapping designer** page, select **Save**.</span></span>
2. <span data-ttu-id="79c7c-951">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="79c7c-951">Close the page.</span></span>
3. <span data-ttu-id="79c7c-952">Feche a página de mapeamentos de modelo.</span><span class="sxs-lookup"><span data-stu-id="79c7c-952">Close the model mappings page.</span></span>
4. <span data-ttu-id="79c7c-953">Na página **Configurações**, na árvore de configurações, verifique se a configuração de **Mapeamento de questionário** ainda está selecionada.</span><span class="sxs-lookup"><span data-stu-id="79c7c-953">On the **Configurations** page, in the configuration tree, make sure that the **Questionnaire mapping** configuration is still selected.</span></span> <span data-ttu-id="79c7c-954">Na FastTab **Versões**, selecione a versão de configuração com o status **Rascunho**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-954">Then, on the **Versions** FastTab, select the configuration version that has a status of **Draft**.</span></span>
5. <span data-ttu-id="79c7c-955">Selecione **Alterar status** \> **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-955">Select **Change status** \> **Complete**.</span></span>

<span data-ttu-id="79c7c-956">O status da versão 1.2 dessa configuração é alterado de **Rascunho** para **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-956">The status of version 1.2 of this configuration is changed from **Draft** to **Completed**.</span></span> <span data-ttu-id="79c7c-957">A versão 1.2 não pode mais ser alterada.</span><span class="sxs-lookup"><span data-stu-id="79c7c-957">Version 1.2 can no longer be changed.</span></span> <span data-ttu-id="79c7c-958">Esta versão contém o mapeamento de modelo configurado e pode ser usada como base para outras configurações de ER.</span><span class="sxs-lookup"><span data-stu-id="79c7c-958">This version contains the configured model mapping and can be used as the basis for other ER configurations.</span></span> <span data-ttu-id="79c7c-959">A versão 1.3 dessa configuração é criada e tem um status **Rascunho**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-959">Version 1.3 of this configuration is created and has a status of **Draft**.</span></span> <span data-ttu-id="79c7c-960">Você pode editar esta versão para ajustar o mapeamento de modelo **Questionário**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-960">You can edit this version to adjust the **Questionnaire** model mapping.</span></span>

### <a name="modify-a-format"></a><a name="ModifyFormat"></a><span data-ttu-id="79c7c-961">Modificar um formato</span><span class="sxs-lookup"><span data-stu-id="79c7c-961">Modify a format</span></span>

<span data-ttu-id="79c7c-962">Você pode modificar o formato de ER configurado de forma que o nome dele apareça no rodapé de um relatório que é gerado quando o formato de ER é executado.</span><span class="sxs-lookup"><span data-stu-id="79c7c-962">You can modify the configured ER format so that its name is shown in the footer of a report that is generated when the ER format is run.</span></span>

#### <a name="add-a-new-format-element"></a><a name="AddFormatElement"></a><span data-ttu-id="79c7c-963">Adicionar um novo elemento de formato</span><span class="sxs-lookup"><span data-stu-id="79c7c-963">Add a new format element</span></span>

1. <span data-ttu-id="79c7c-964">Vá para **Administração da organização** \> **Relatório eletrônico** \> **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-964">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="79c7c-965">Na página **Configurações**, na árvore de configurações, expanda **Modelo de questionário** e selecione **Relatório de questionário**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-965">On the **Configurations** page, in the configuration tree, expand **Questionnaire model**, and then select **Questionnaire report**.</span></span>
3. <span data-ttu-id="79c7c-966">Selecione **Designer**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-966">Select **Designer**.</span></span>
4. <span data-ttu-id="79c7c-967">Na página **Designer de formato**, selecione o item de raiz **Relatório**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-967">On the **Format designer** page, select the **Report** root item.</span></span>
5. <span data-ttu-id="79c7c-968">Selecione **Adicionar** para adicionar um novo elemento de formato aninhado ao item raiz **Relatório** selecionado.</span><span class="sxs-lookup"><span data-stu-id="79c7c-968">Select **Add** to add a new nested format element for the selected **Report** root item.</span></span>
6. <span data-ttu-id="79c7c-969">Selecione **Excel\\Rodapé**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-969">Select **Excel\\Footer**.</span></span>
7. <span data-ttu-id="79c7c-970">No campo **Nome**, insira **Rodapé**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-970">In the **Name** field, enter **Footer**.</span></span>
8. <span data-ttu-id="79c7c-971">Selecione **Relatório\Rodapé** e, depois, **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-971">Select **Report\Footer**, and then select **Add**.</span></span>
9. <span data-ttu-id="79c7c-972">Selecione **Texto\\Cadeia de caracteres**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-972">Select **Text\\String**.</span></span>

#### <a name="bind-the-added-format-element"></a><a name="BindAddedFormatElement"></a><span data-ttu-id="79c7c-973">Vincular o elemento de formato adicionado</span><span class="sxs-lookup"><span data-stu-id="79c7c-973">Bind the added format element</span></span>

1. <span data-ttu-id="79c7c-974">Na página **Designer de formato**, na guia **Mapeamento**, selecione a árvore de formatos para o elemento **Rodapé\\Cadeia de caracteres** ativo e selecione **Editar fórmula**</span><span class="sxs-lookup"><span data-stu-id="79c7c-974">On the **Format designer** page, on the **Mapping** tab, in the format tree, for the active **Footer\\String** element, select **Edit formula**.</span></span>
2. <span data-ttu-id="79c7c-975">No editor de fórmulas, no campo **Fórmula**, insira **CONCATENATE ("\&C\&10", FORMAT("Generated by'\%1' ER solution", model.ExecutionContext.FormatName))**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-975">In the formula editor, in the **Formula** field, enter **CONCATENATE ("\&C\&10", FORMAT("Generated by'\%1' ER solution", model.ExecutionContext.FormatName))**.</span></span>
3. <span data-ttu-id="79c7c-976">Selecione **Salvar** e feche o editor de fórmula.</span><span class="sxs-lookup"><span data-stu-id="79c7c-976">Select **Save**, and close the formula editor.</span></span>
4. <span data-ttu-id="79c7c-977">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-977">Select **Save**.</span></span>

<span data-ttu-id="79c7c-978">O formato configurado foi modificado para que o nome dele seja inserido no rodapé de um relatório gerado usando o elemento **Rodapé\\Cadeia de caracteres**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-978">The configured format has now been modified so that its name will be entered in the footer of a generated report by using the **Footer\\String** element.</span></span>

![Adição do elemento de formato do rodapé ao formato configurado no designer de Operação do ER](./media/er-quick-start1-template-format-structure3.png)

#### <a name="complete-the-format-design"></a><a name="CompleteFormat2"></a><span data-ttu-id="79c7c-980">Concluir a criação do formato</span><span class="sxs-lookup"><span data-stu-id="79c7c-980">Complete the format design</span></span>

1. <span data-ttu-id="79c7c-981">Feche a página **Designer de formato**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-981">Close the **Format designer** page.</span></span>
2. <span data-ttu-id="79c7c-982">Na página **Configurações**, na árvore de configurações, verifique se a configuração de **Relatório de questionário** ainda está selecionada.</span><span class="sxs-lookup"><span data-stu-id="79c7c-982">On the **Configurations** page, in the configuration tree, make sure that the **Questionnaire report** configuration is still selected.</span></span> <span data-ttu-id="79c7c-983">Na FastTab **Versões**, selecione a versão de configuração com o status **Rascunho**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-983">Then, on the **Versions** FastTab, select the configuration version that has a status of **Draft**.</span></span>
3. <span data-ttu-id="79c7c-984">Selecione **Alterar status** \> **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-984">Select **Change status** \> **Complete**.</span></span>

<span data-ttu-id="79c7c-985">O status da versão 1.2 dessa configuração é alterado de **Rascunho** para **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-985">The status of version 1.2 of this configuration is changed from **Draft** to **Completed**.</span></span> <span data-ttu-id="79c7c-986">A versão 1.2 não pode mais ser alterada.</span><span class="sxs-lookup"><span data-stu-id="79c7c-986">Version 1.2 can no longer be changed.</span></span> <span data-ttu-id="79c7c-987">Esta versão contém o formato configurado e pode ser usada como base para outras configurações de ER.</span><span class="sxs-lookup"><span data-stu-id="79c7c-987">This version contains the configured format and can be used as the basis for other ER configurations.</span></span> <span data-ttu-id="79c7c-988">A versão 1.3 dessa configuração é criada e tem um status **Rascunho**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-988">Version 1.3 of this configuration is created and has a status of **Draft**.</span></span> <span data-ttu-id="79c7c-989">Você pode editar esta versão para ajustar o relatório **Questionário**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-989">You can edit this version to adjust the **Questionnaire** report.</span></span>

### <a name="run-a-format-from-the-application"></a><a name="RunFormatFromApp2"></a><span data-ttu-id="79c7c-990">Executar um formato do aplicativo</span><span class="sxs-lookup"><span data-stu-id="79c7c-990">Run a format from the application</span></span>

1. <span data-ttu-id="79c7c-991">Vá para **Questionário** \> **Design** \> **Relatório Questionários (alimentado pelo ER)**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-991">Go to **Questionnaire** \> **Design** \> **Questionnaires report (powered by ER)**.</span></span>
2. <span data-ttu-id="79c7c-992">Na caixa de diálogo, no campo **Mapeamento de formato**, selecione **relatório Questionários**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-992">In the dialog box, in the **Format mapping** field, select **Questionnaires report**.</span></span>
3. <span data-ttu-id="79c7c-993">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-993">Select **OK**.</span></span>
4. <span data-ttu-id="79c7c-994">Na caixa de diálogo **Parâmetros de ER**, na FastTab **Registros a serem incluídos**, configure a opção de filtragem para que somente o questionário **SBCCrsExam** seja incluído.</span><span class="sxs-lookup"><span data-stu-id="79c7c-994">In the **ER parameters** dialog box, on the **Records to include** FastTab, configure the filtering option so that only the **SBCCrsExam** questionnaire is included.</span></span>
5. <span data-ttu-id="79c7c-995">Selecione **OK** para confirmar a opção de filtragem.</span><span class="sxs-lookup"><span data-stu-id="79c7c-995">Select **OK** to confirm the filtering option.</span></span>
6. <span data-ttu-id="79c7c-996">Selecione **OK** para executar o relatório.</span><span class="sxs-lookup"><span data-stu-id="79c7c-996">Select **OK** to run the report.</span></span>
7. <span data-ttu-id="79c7c-997">Revise o relatório gerado no formato Excel.</span><span class="sxs-lookup"><span data-stu-id="79c7c-997">Review the generated report in Excel format.</span></span>

<span data-ttu-id="79c7c-998">Observe que o rodapé do relatório gerado contém o nome do formato de ER que foi usado para gerá-lo.</span><span class="sxs-lookup"><span data-stu-id="79c7c-998">Notice that the footer of the generated report contains the name of the ER format that was used to generate it.</span></span>

![Relatório gerado no formato Excel](./media/er-quick-start1-report4.png)

### <a name="run-a-format-from-er"></a><a name="RunFormatFromER3"></a><span data-ttu-id="79c7c-1000">Executar um formato de ER</span><span class="sxs-lookup"><span data-stu-id="79c7c-1000">Run a format from ER</span></span>

1. <span data-ttu-id="79c7c-1001">Vá para **Administração da organização** \> **Relatório eletrônico** \> **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-1001">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="79c7c-1002">Na página **Configurações**, na árvore de configurações, expanda **Modelo de questionário** e selecione **Relatório de questionário**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-1002">On the **Configurations** page, in the configuration tree, expand **Questionnaire model**, and then select **Questionnaire report**.</span></span>
3. <span data-ttu-id="79c7c-1003">No Painel de Ação, selecione **Executar**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-1003">On the Action Pane, select **Run**.</span></span>
4. <span data-ttu-id="79c7c-1004">Na caixa de diálogo **Parâmetros de relatório eletrônico**, na FastTab **Registros a serem incluídos**, configure a opção de filtragem para que somente o questionário **SBCCrsExam** seja incluído.</span><span class="sxs-lookup"><span data-stu-id="79c7c-1004">In the **Electronic report parameters** dialog box, on the **Records to include** FastTab, configure the filtering option so that only the **SBCCrsExam** questionnaire is included.</span></span>
5. <span data-ttu-id="79c7c-1005">Selecione **OK** para confirmar a opção de filtragem.</span><span class="sxs-lookup"><span data-stu-id="79c7c-1005">Select **OK** to confirm the filtering option.</span></span>
6. <span data-ttu-id="79c7c-1006">Selecione **OK** para executar o relatório.</span><span class="sxs-lookup"><span data-stu-id="79c7c-1006">Select **OK** to run the report.</span></span>
7. <span data-ttu-id="79c7c-1007">Revise o relatório gerado no formato Excel.</span><span class="sxs-lookup"><span data-stu-id="79c7c-1007">Review the generated report in Excel format.</span></span>

<span data-ttu-id="79c7c-1008">Observe que o rodapé do relatório gerado não contém o nome do formato de ER que foi usado para gerá-lo, pois o objeto de contrato de dados não foi passado para o mapeamento do modelo em execução quando ele foi chamado pelo formato de ER executado a partir de ER.</span><span class="sxs-lookup"><span data-stu-id="79c7c-1008">Notice that the footer of the generated report doesn't contain the name of ER format that was used to generate it, because the data contract object wasn't passed to the running model mapping when it was called by the ER format that was run from ER.</span></span>

### <a name="configure-a-format-destination-for-on-screen-preview"></a><a name="ConfigureDestination"></a><span data-ttu-id="79c7c-1009">Configurar um destino de formato para versão prévia na tela</span><span class="sxs-lookup"><span data-stu-id="79c7c-1009">Configure a format destination for on-screen preview</span></span>

1. <span data-ttu-id="79c7c-1010">Vá para **Administração da organização** \> **Relatório eletrônico** \> **Destino de relatório eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-1010">Go to **Organization administration** \> **Electronic reporting** \> **Electronic reporting destination**.</span></span>
2. <span data-ttu-id="79c7c-1011">Na página **Destino do relatório eletrônico**, adicione um registro de destino para o formato de ER configurado para o formato de ER **Relatório de questionário**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-1011">On the **Electronic reporting destination** page, add a destination record for the configured **Questionnaire report** ER format.</span></span>
3. <span data-ttu-id="79c7c-1012">Na FastTab **Destino do arquivo**, configure o [destino](er-destination-type-screen.md) da **Tela** para o componente de formato de **Relatório** que foi [adicionado](#AddFormatRootElement) como o elemento-raiz do formato de ER do **Relatório de questionário** configurado.</span><span class="sxs-lookup"><span data-stu-id="79c7c-1012">On the **File destination** FastTab, set up the **Screen** [destination](er-destination-type-screen.md) for the **Report** format component that has been [added](#AddFormatRootElement) as the root element of the configured **Questionnaire report** ER format.</span></span>
4. <span data-ttu-id="79c7c-1013">Na FastTab **Configurações de conversão de PDF**, configure o destino para converter um relatório em [formato PDF](electronic-reporting-destinations.md#OutputConversionToPDF) que usa a orientação de página **Paisagem**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-1013">On the **PDF conversion settings** FastTab, configure the destination to convert a report to [PDF format](electronic-reporting-destinations.md#OutputConversionToPDF) that uses the **Landscape** page orientation.</span></span>

![Configuração do destino de tela personalizado para o formato de ER na página destino Relatório eletrônico](./media/er-quick-start1-destination.png)

### <a name="run-a-format-from-the-application-to-preview-it-as-a-pdf-document"></a><a name="RunFormatFromApp3"></a><span data-ttu-id="79c7c-1015">Executar um formato do aplicativo para visualizá-lo como um documento PDF</span><span class="sxs-lookup"><span data-stu-id="79c7c-1015">Run a format from the application to preview it as a PDF document</span></span>

1. <span data-ttu-id="79c7c-1016">Vá para **Questionário** \> **Design** \> **Relatório Questionários (alimentado pelo ER)**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-1016">Go to **Questionnaire** \> **Design** \> **Questionnaires report (powered by ER)**.</span></span>
2. <span data-ttu-id="79c7c-1017">Na caixa de diálogo, no campo **Mapeamento de formato**, selecione **relatório Questionários**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-1017">In the dialog box, in the **Format mapping** field, select **Questionnaires report**.</span></span>
3. <span data-ttu-id="79c7c-1018">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-1018">Select **OK**.</span></span>
4. <span data-ttu-id="79c7c-1019">Na caixa de diálogo **Parâmetros de relatório eletrônico**, na FastTab **Registros a serem incluídos**, configure a opção de filtragem para que somente o questionário **SBCCrsExam** seja incluído.</span><span class="sxs-lookup"><span data-stu-id="79c7c-1019">In the **Electronic report parameters** dialog box, on the **Records to include** FastTab, configure the filtering option so that only the **SBCCrsExam** questionnaire is included.</span></span>
5. <span data-ttu-id="79c7c-1020">Selecione **OK** para confirmar a opção de filtragem.</span><span class="sxs-lookup"><span data-stu-id="79c7c-1020">Select **OK** to confirm the filtering option.</span></span>

    <span data-ttu-id="79c7c-1021">Na FastTab **Destinos**, observe que o campo **Saída** está definido como **Tela**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-1021">On the **Destinations** FastTab, notice that the **Output** field is set to **Screen**.</span></span> <span data-ttu-id="79c7c-1022">Se desejar alterar o destino configurado, selecione **Alterar**.</span><span class="sxs-lookup"><span data-stu-id="79c7c-1022">If you want to change the configured destination, select **Change**.</span></span>

    ![Caixa de diálogo Tempo de execução de relatório de ER, em que você pode alterar o destino configurado](./media/er-quick-start1-run-settings.png)

6. <span data-ttu-id="79c7c-1024">Selecione **OK** para executar o relatório.</span><span class="sxs-lookup"><span data-stu-id="79c7c-1024">Select **OK** to run the report.</span></span>
7. <span data-ttu-id="79c7c-1025">Revise o relatório gerado no formato PDF.</span><span class="sxs-lookup"><span data-stu-id="79c7c-1025">Review the generated report in PDF format.</span></span>

    ![Versão prévia na tela do relatório gerado no formato PDF](./media/er-quick-start1-preview-PDF.png)

## <a name="additional-resources"></a><a name="References"></a><span data-ttu-id="79c7c-1027">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="79c7c-1027">Additional resources</span></span>

- [<span data-ttu-id="79c7c-1028">Visão geral do Relatório Eletrônico</span><span class="sxs-lookup"><span data-stu-id="79c7c-1028">Electronic Reporting overview</span></span>](general-electronic-reporting.md)
- [<span data-ttu-id="79c7c-1029">Linguagem da fórmula de relatório eletrônico</span><span class="sxs-lookup"><span data-stu-id="79c7c-1029">Electronic reporting formula language</span></span>](er-formula-language.md)
- [<span data-ttu-id="79c7c-1030">Criar relatórios multilíngues</span><span class="sxs-lookup"><span data-stu-id="79c7c-1030">Design multilingual reports</span></span>](er-design-multilingual-reports.md)
- [<span data-ttu-id="79c7c-1031">API da estrutura de ER</span><span class="sxs-lookup"><span data-stu-id="79c7c-1031">ER framework API</span></span>](er-apis-app73.md)
- [<span data-ttu-id="79c7c-1032">Função CASE</span><span class="sxs-lookup"><span data-stu-id="79c7c-1032">CASE function</span></span>](er-functions-logical-case.md)
- [<span data-ttu-id="79c7c-1033">Função CONCATENATE</span><span class="sxs-lookup"><span data-stu-id="79c7c-1033">CONCATENATE function</span></span>](er-functions-text-concatenate.md)
- [<span data-ttu-id="79c7c-1034">Função DATETIMEFORMAT</span><span class="sxs-lookup"><span data-stu-id="79c7c-1034">DATETIMEFORMAT function</span></span>](er-functions-datetime-datetimeformat.md)
- [<span data-ttu-id="79c7c-1035">Função FILTER</span><span class="sxs-lookup"><span data-stu-id="79c7c-1035">FILTER function</span></span>](er-functions-list-filter.md)
- [<span data-ttu-id="79c7c-1036">Função FIRSTORNULL</span><span class="sxs-lookup"><span data-stu-id="79c7c-1036">FIRSTORNULL function</span></span>](er-functions-list-firstornull.md)
- [<span data-ttu-id="79c7c-1037">Função FORMAT</span><span class="sxs-lookup"><span data-stu-id="79c7c-1037">FORMAT function</span></span>](er-functions-text-format.md)
- [<span data-ttu-id="79c7c-1038">Função IF</span><span class="sxs-lookup"><span data-stu-id="79c7c-1038">IF function</span></span>](er-functions-logical-if.md)
- [<span data-ttu-id="79c7c-1039">Função ORDERBY</span><span class="sxs-lookup"><span data-stu-id="79c7c-1039">ORDERBY function</span></span>](er-functions-list-orderby.md)
- [<span data-ttu-id="79c7c-1040">Função SESSIONNOW</span><span class="sxs-lookup"><span data-stu-id="79c7c-1040">SESSIONNOW function</span></span>](er-functions-datetime-sessionnow.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]