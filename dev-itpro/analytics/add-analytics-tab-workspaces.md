---
title: "Adicionar análise a espaços de trabalho usando o Power BI Embedded"
description: "Este tópico mostra como incorporar um relatório do Power BI na guia Análise de um espaço de trabalho."
author: tjvass
manager: AnnBe
ms.date: 06/21/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application user, IT Pro
ms.reviewer: robinr
ms.search.scope: Operations, Platform, UnifiedOperations
ms.search.region: Global
ms.author: tjvass
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.intro: Platform update 8
ms.dyn365.ops.version: July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 20d28e22e4e89d0d864a0cbeaadeb568e73e223e
ms.openlocfilehash: e819aafbdf55fbc2a6dc996d275244de1e11d89b
ms.contentlocale: pt-br
ms.lasthandoff: 07/27/2017

---

# <a name="add-analytics-to-workspaces-by-using-power-bi-embedded"></a><span data-ttu-id="376d3-103">Adicionar análise a espaços de trabalho usando o Power BI Embedded</span><span class="sxs-lookup"><span data-stu-id="376d3-103">Add analytics to workspaces by using Power BI Embedded</span></span>

[!include[banner](../includes/banner.md)]

> [!NOTE]
> <span data-ttu-id="376d3-104">Esse recurso é compatível com o Dynamics 365 for Finance and Operations (versão 7.2 e posterior).</span><span class="sxs-lookup"><span data-stu-id="376d3-104">This feature is supported in Dynamics 365 for Finance and Operations (version 7.2 and later).</span></span>

# <a name="introduction"></a><span data-ttu-id="376d3-105">Introdução</span><span class="sxs-lookup"><span data-stu-id="376d3-105">Introduction</span></span>
<span data-ttu-id="376d3-106">Este tópico mostra como incorporar um relatório do Microsoft Power BI na guia **Análise** de um espaço de trabalho.</span><span class="sxs-lookup"><span data-stu-id="376d3-106">This topic shows how to embed a Microsoft Power BI report on the **Analytics** tab of a workspace.</span></span> <span data-ttu-id="376d3-107">No exemplo dado aqui, estenderemos o espaço de trabalho **Gerenciamento de reservas** no aplicativo de Gerenciamento de Frota para incorporar um espaço de trabalho analítico em uma guia **Análise**.</span><span class="sxs-lookup"><span data-stu-id="376d3-107">For the example that is given here, we will extend the **Reservation management** workspace in the Fleet Management application to embed an analytical workspace on an **Analytics** tab.</span></span>

# <a name="prerequisites"></a><span data-ttu-id="376d3-108">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="376d3-108">Prerequisites</span></span>
+ <span data-ttu-id="376d3-109">Acesso a um ambiente de desenvolvedor que executa a atualização 8 da plataforma ou posterior.</span><span class="sxs-lookup"><span data-stu-id="376d3-109">Access to a developer environment that runs Platform update 8 or later.</span></span>
+ <span data-ttu-id="376d3-110">Um relatório analítico (.pbix file) que foi criado por meio da área de trabalho do Microsoft Power BI e que apresenta um modelo de dados com origem no banco de dados de loja Entidade.</span><span class="sxs-lookup"><span data-stu-id="376d3-110">An analytical report (.pbix file) that was created by using Microsoft Power BI Desktop, and that has a data model that is sourced from the Entity store database.</span></span>

# <a name="overview"></a><span data-ttu-id="376d3-111">Visão Geral</span><span class="sxs-lookup"><span data-stu-id="376d3-111">Overview</span></span>
<span data-ttu-id="376d3-112">Se você estender um espaço de trabalho de aplicativo existente ou introduzir seu próprio espaço de trabalho, é possível usar exibições analíticas incorporadas para fornecer exibições intuitivas e interativas de seus dados comerciais.</span><span class="sxs-lookup"><span data-stu-id="376d3-112">Whether you extend an existing application workspace or introduce a new workspace of your own, you can use embedded analytical views to deliver insightful and interactive views of your business data.</span></span> <span data-ttu-id="376d3-113">O processo para adicionar uma guia de espaço de trabalho analítico apresenta quatro etapas.</span><span class="sxs-lookup"><span data-stu-id="376d3-113">The process for adding an analytical workspace tab has four steps.</span></span>

1. <span data-ttu-id="376d3-114">Adicione um arquivo .pbix como um recurso do Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="376d3-114">Add a .pbix file as a Dynamics 365 resource.</span></span>
2. <span data-ttu-id="376d3-115">Define uma guia de espaço de trabalho analítico.</span><span class="sxs-lookup"><span data-stu-id="376d3-115">Define an analytical workspace tab.</span></span>
3. <span data-ttu-id="376d3-116">Incorpore o recurso .pbix na guia do espaço de trabalho.</span><span class="sxs-lookup"><span data-stu-id="376d3-116">Embed the .pbix resource on the workspace tab.</span></span>
4. <span data-ttu-id="376d3-117">Opcional: adicione extensões para personalizar a exibição.</span><span class="sxs-lookup"><span data-stu-id="376d3-117">Optional: Add extensions to customize the view.</span></span>

> [!NOTE]
> <span data-ttu-id="376d3-118">Para obter informações sobre como criar relatórios analíticos, consulte [Introdução à área de trabalho do Power BI](https://powerbi.microsoft.com/documentation/powerbi-desktop-getting-started/).</span><span class="sxs-lookup"><span data-stu-id="376d3-118">For more information about how to create analytical reports, see [Getting started with Power BI Desktop](https://powerbi.microsoft.com/documentation/powerbi-desktop-getting-started/).</span></span> <span data-ttu-id="376d3-119">Esta página é um grande recurso para informações que podem ajudar a criar soluções de relatório analítico atrativas.</span><span class="sxs-lookup"><span data-stu-id="376d3-119">This page is a great source for insights that can help you create compelling analytical reporting solutions.</span></span>

# <a name="add-a-pbix-file-as-a-resource"></a><span data-ttu-id="376d3-120">Adicionar um arquivo .pbix como um recurso</span><span class="sxs-lookup"><span data-stu-id="376d3-120">Add a .pbix file as a resource</span></span>
<span data-ttu-id="376d3-121">Antes de começar, é preciso criar ou obter o relatório do Power BI que será incorporado no espaço de trabalho.</span><span class="sxs-lookup"><span data-stu-id="376d3-121">Before you begin, you must create or obtain the Power BI report that you will embed in the workspace.</span></span> <span data-ttu-id="376d3-122">Para obter informações sobre como criar relatórios analíticos, consulte [Introdução à área de trabalho do Power BI](https://powerbi.microsoft.com/documentation/powerbi-desktop-getting-started/).</span><span class="sxs-lookup"><span data-stu-id="376d3-122">For more information about how to create analytical reports, see [Getting started with Power BI Desktop](https://powerbi.microsoft.com/documentation/powerbi-desktop-getting-started/).</span></span>
 
<span data-ttu-id="376d3-123">Siga essas etapas para adicionar um arquivo .pbix como um artefato de projetos do Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="376d3-123">Follow these steps to add a .pbix file as a Visual Studio project artifact.</span></span>

1. <span data-ttu-id="376d3-124">Crie um projeto no modelo apropriado.</span><span class="sxs-lookup"><span data-stu-id="376d3-124">Create a new project in the appropriate model.</span></span>
2. <span data-ttu-id="376d3-125">No Gerenciador de Soluções, selecione o projeto, clique com o botão direito do mouse e depois selecione **Adicionar** > **Novo item**.</span><span class="sxs-lookup"><span data-stu-id="376d3-125">In Solution Explorer, select the project, right-click, and then select **Add** > **New Item**.</span></span>
3. <span data-ttu-id="376d3-126">Na caixa de diálogo **Adicionar novo item**, em **Artefatos do Operations**, selecione o modelo **Recurso**.</span><span class="sxs-lookup"><span data-stu-id="376d3-126">In the **Add New Item** dialog box, under **Operations Artifacts**, select the **Resource** template.</span></span>
4. <span data-ttu-id="376d3-127">Insira um nome que será usado para referenciar o relatório em metadados X++ e depois clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="376d3-127">Enter a name that will be used to reference the report in X++ metadata, and then click **Add**.</span></span>

    ![Adicionar a caixa de diálogo Novo item](media/analytical-workspace-add.png)

5. <span data-ttu-id="376d3-129">Localize o arquivo .pbix que contém a definição do relatório analítico e depois clique em **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="376d3-129">Find the .pbix file that contains the definition of the analytical report, and then click **Open**.</span></span>

    ![Selecionar uma caixa de diálogo Arquivo de recurso](media/analytical-workspace-select-resource.png)
  
<span data-ttu-id="376d3-131">Agora que você já adicionou o arquivo .pbix como um recurso do Dynamics 365, é possível incorporar os relatórios nos espaços de trabalho e adicionar links diretos usando itens de menu.</span><span class="sxs-lookup"><span data-stu-id="376d3-131">Now that you've added the .pbix file as a Dynamics 365 resource, you can embed the reports in workspaces and add direct links by using menu items.</span></span>

# <a name="add-a-tab-control-to-an-application-workspace"></a><span data-ttu-id="376d3-132">Adicionar um controle de guias a um espaço de trabalho de aplicativo</span><span class="sxs-lookup"><span data-stu-id="376d3-132">Add a tab control to an application workspace</span></span>
<span data-ttu-id="376d3-133">Neste exemplo, estenderemos o espaço de trabalho **Gerenciamento de reservas** no modelo de Gerenciamento de Frota adicionando a guia **Análise** à definição do formulário **FMClerkWorkspace**.</span><span class="sxs-lookup"><span data-stu-id="376d3-133">In this example, we will extend the **Reservation management** workspace in the Fleet Management model by adding the **Analytics** tab to the definition of the **FMClerkWorkspace** form.</span></span>
 
<span data-ttu-id="376d3-134">A ilustração a seguir mostra a aparência do formulário **FMClerkWorkspace** no designer do Microsoft Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="376d3-134">The following illustration shows what the **FMClerkWorkspace** form looks like in the designer in Microsoft Visual Studio.</span></span>

![Formulário FMClerkWorkspace antes de alterações](media/analytical-workspace-definition-before.png)

<span data-ttu-id="376d3-136">Siga essas etapas para estender a definição de formulário para o espaço de trabalho **Gerenciamento de reservas**.</span><span class="sxs-lookup"><span data-stu-id="376d3-136">Follow these steps to extend the form definition for the **Reservation management** workspace.</span></span>

1. <span data-ttu-id="376d3-137">Abra o designer de formulário para estender a definição de design.</span><span class="sxs-lookup"><span data-stu-id="376d3-137">Open the form designer to extend the design definition.</span></span>
2. <span data-ttu-id="376d3-138">Na definição de design, selecione o elemento superior que é rotulado **Design | Pattern: Workspace Operational**.</span><span class="sxs-lookup"><span data-stu-id="376d3-138">In the design definition, select the top element that is labeled **Design | Pattern: Workspace Operational**.</span></span>
3. <span data-ttu-id="376d3-139">Clique com o botão direito do mouse e depois selecione **Novo** > **Guia** para adicionar um novo controle que é nomeado **FormTabControl1**.</span><span class="sxs-lookup"><span data-stu-id="376d3-139">Right-click, and then select **New** > **Tab** to add a new control that is named **FormTabControl1**.</span></span>
4. <span data-ttu-id="376d3-140">No designer de formulário, selecione **FormTabControl1**.</span><span class="sxs-lookup"><span data-stu-id="376d3-140">In the form designer, select **FormTabControl1**.</span></span>
5. <span data-ttu-id="376d3-141">Clique com o botão direito do mouse e depois selecione **Nova página de guia** para adicionar uma nova página de guia.</span><span class="sxs-lookup"><span data-stu-id="376d3-141">Right-click, and then select **New Tab Page** to add a new tab page.</span></span>
6. <span data-ttu-id="376d3-142">Renomeie a página de guia para algo significativo, como **Espaço de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="376d3-142">Rename the tab page to something meaningful, such as **Workspace**.</span></span>
7. <span data-ttu-id="376d3-143">No designer de formulário, selecione **FormTabControl1**.</span><span class="sxs-lookup"><span data-stu-id="376d3-143">In the form designer, select **FormTabControl1**.</span></span>
8. <span data-ttu-id="376d3-144">Clique com o botão direito do mouse e depois selecione **Nova página de guia**.</span><span class="sxs-lookup"><span data-stu-id="376d3-144">Right-click, and then select **New Tab Page**.</span></span>
9. <span data-ttu-id="376d3-145">Renomeie a página de guia para algo significativo, como **Análise**.</span><span class="sxs-lookup"><span data-stu-id="376d3-145">Rename the tab page to something meaningful, such as **Analytics**.</span></span>
10. <span data-ttu-id="376d3-146">No designer de formulário, selecione **Análise (Página da Guia)**.</span><span class="sxs-lookup"><span data-stu-id="376d3-146">In the form designer, select **Analytics (Tab Page)**.</span></span>
11. <span data-ttu-id="376d3-147">Defina a propriedade **Legenda** como **Análise**.</span><span class="sxs-lookup"><span data-stu-id="376d3-147">Set the **Caption** property to **Analytics**.</span></span>
12. <span data-ttu-id="376d3-148">Clique com o botão direito do mouse e depois selecione **Novo** > **Grupo** para adicionar um novo controle de grupo de formulários.</span><span class="sxs-lookup"><span data-stu-id="376d3-148">Right-click the control, and then select **New** > **Group** to add a new form group control.</span></span>
13. <span data-ttu-id="376d3-149">Renomeie o grupo do formulários para algo significativo, como **powerBIReportGroup**.</span><span class="sxs-lookup"><span data-stu-id="376d3-149">Rename the form group to something meaningful, such as **powerBIReportGroup**.</span></span>
14. <span data-ttu-id="376d3-150">No designer de formulário, selecione **PanoramaBody (Guia)** e depois arraste o controle até a guia **Espaço de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="376d3-150">In the form designer, select **PanoramaBody (Tab)**, and then drag the control onto the **Workspace** tab.</span></span>
15. <span data-ttu-id="376d3-151">Na definição de design, selecione o elemento superior que é rotulado **Design | Pattern: Workspace Operational**.</span><span class="sxs-lookup"><span data-stu-id="376d3-151">In the design definition, select the top element that is labeled **Design | Pattern: Workspace Operational**.</span></span>
16. <span data-ttu-id="376d3-152">Clique com o botão direito do mouse e depois selecione **Remover padrão**.</span><span class="sxs-lookup"><span data-stu-id="376d3-152">Right-click, and then select **Remove pattern**.</span></span>
17. <span data-ttu-id="376d3-153">Clique com o botão direito do mouse e depois selecione **Adicionar padrão** > **Espaço de trabalho com guias**.</span><span class="sxs-lookup"><span data-stu-id="376d3-153">Right-click again, and then select **Add pattern** > **Workspace Tabbed**.</span></span>
18. <span data-ttu-id="376d3-154">Execute uma compilação para verificar suas alterações.</span><span class="sxs-lookup"><span data-stu-id="376d3-154">Perform a build to verify your changes.</span></span>
 
<span data-ttu-id="376d3-155">A ilustração a seguir mostra a aparência do design após a aplicação dessas alterações.</span><span class="sxs-lookup"><span data-stu-id="376d3-155">The following illustration shows what the design looks like after these changes are applied.</span></span>

![FMClerkWorkspace após as alterações](media/analytical-workspace-definition-after.png)

<span data-ttu-id="376d3-157">Agora que você já adicionou os controles de formulário que serão usados para incorporar o relatório de espaço de trabalho, é preciso definir o tamanho do controle pai para que ele acomode o layout.</span><span class="sxs-lookup"><span data-stu-id="376d3-157">Now that you've added the form controls that will be used to embed the workspace report, you must define the size of the parent control so that it accommodates the layout.</span></span> <span data-ttu-id="376d3-158">Por padrão, as páginas **Painel de filtros** e **Guia** estarão visíveis no relatório.</span><span class="sxs-lookup"><span data-stu-id="376d3-158">By default, both the **Filters Pane** page and the **Tab** page will be visible on the report.</span></span> <span data-ttu-id="376d3-159">No entanto, você pode alterar a visibilidade desses controles conforme apropriado para o consumidor alvo do relatório.</span><span class="sxs-lookup"><span data-stu-id="376d3-159">However, you can change the visibility of these controls as appropriate for the target consumer of the report.</span></span>
 
> [!NOTE]
> <span data-ttu-id="376d3-160">Para espaços de trabalho incorporados, recomendamos o uso de extensões para ocultar as páginas **Painel de filtros** e **Guia** para que haja consistência.</span><span class="sxs-lookup"><span data-stu-id="376d3-160">For embedded workspaces, we recommend that you use extensions to hide both the **Filters Pane** and **Tab** pages, for consistency.</span></span>
 
<span data-ttu-id="376d3-161">Agora você já concluiu a tarefa de estender a definição de formulário de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="376d3-161">You've now completed the task of extending the application form definition.</span></span> <span data-ttu-id="376d3-162">Para obter mais informações sobre como usar extensões para realizar personalizações, consulte [Personalização: sobreposições e extensões](../extensibility/customization-overlayering-extensions.md).</span><span class="sxs-lookup"><span data-stu-id="376d3-162">For more information about how to use extensions to do customizations, see  [Customization: Overlayering and extensions](../extensibility/customization-overlayering-extensions.md).</span></span>

# <a name="add-x-business-logic-to-embed-a-viewer-control"></a><span data-ttu-id="376d3-163">Adicionar a lógica comercial X++ para incorporar um controle mais amplo</span><span class="sxs-lookup"><span data-stu-id="376d3-163">Add X++ business logic to embed a viewer control</span></span>
<span data-ttu-id="376d3-164">Siga essas etapas para adicionar a lógica comercial que inicializa o controle de relatório mais amplo incorporado no espaço de trabalho **Gerenciamento de reservas**.</span><span class="sxs-lookup"><span data-stu-id="376d3-164">Follow these steps to add business logic that initializes the report viewer control that is embedded in the **Reservation management** workspace.</span></span>

1. <span data-ttu-id="376d3-165">Abra o designer de formulário **FMClerkWorkspace** para estender a definição de design.</span><span class="sxs-lookup"><span data-stu-id="376d3-165">Open the **FMClerkWorkspace** form designer to extend the design definition.</span></span>
2. <span data-ttu-id="376d3-166">Pressione F7 para acessar o código por trás da definição de código.</span><span class="sxs-lookup"><span data-stu-id="376d3-166">Press F7 to access the code behind the code definition.</span></span>
3. <span data-ttu-id="376d3-167">Adicione o código X++ a seguir.</span><span class="sxs-lookup"><span data-stu-id="376d3-167">Add the following X++ code.</span></span>

    ```
    [Form] 
    public class FMClerkWorkspace extends FormRun
    {
        private boolean initReportControl = true;     
        protected void initAnalyticalReport()
        {
            if (!initReportControl)
            {
                return;
            }
            // Note: secure entry point into the Workspace's Analytics report
            if (Global::hasMenuItemAccess(menuItemDisplayStr(FMClerkWorkspace), MenuItemType::Display))
            {
                FMPBIWorkspaceController controller = new FMPBIWorkspaceController();
                PBIReportHelper::initializeReportControl('FMPBIWorkspaces', powerBIReportGroup);
            }
            initReportControl = false;
    }
        /// <summary>
        /// Initializes the form.
        /// </summary>
        public void init()
        {
            super();
            this.initAnalyticalReport();
        }
    }
    ```

4. <span data-ttu-id="376d3-168">Execute uma compilação para verificar suas alterações.</span><span class="sxs-lookup"><span data-stu-id="376d3-168">Perform a build to verify your changes.</span></span>

<span data-ttu-id="376d3-169">Agora você já concluiu a tarefa de adicionar a lógica comercial para inicializar o controle de relatório incorporado mais amplo.</span><span class="sxs-lookup"><span data-stu-id="376d3-169">You've now completed the task of adding business logic to initialize the embedded report viewer control.</span></span> <span data-ttu-id="376d3-170">A ilustração a seguir mostra a aparência do espaço de trabalho após a aplicação dessas alterações.</span><span class="sxs-lookup"><span data-stu-id="376d3-170">The following illustration shows what the workspace looks like after these changes are applied.</span></span>

![Relatório incorporado no espaço de trabalho](media/analytical-workspace-final.png)

> [!NOTE]
> <span data-ttu-id="376d3-172">É possível acessar a exibição operacional existente usando as guias de espaço de trabalho abaixo do título da página.</span><span class="sxs-lookup"><span data-stu-id="376d3-172">You can access the existing operational view by using the workspace tabs below the page title.</span></span>

# <a name="reference"></a><span data-ttu-id="376d3-173">Demonstrativo</span><span class="sxs-lookup"><span data-stu-id="376d3-173">Reference</span></span>

## <a name="pbireporthelperinitializereportcontrol-method"></a><span data-ttu-id="376d3-174">Método PBIReportHelper.initializeReportControl</span><span class="sxs-lookup"><span data-stu-id="376d3-174">PBIReportHelper.initializeReportControl method</span></span>
<span data-ttu-id="376d3-175">Esta seção fornece informações sobre a classe auxiliar usada para incorporar um relatório do Power BI (recurso .pbix) em um controle de grupo de formulário.</span><span class="sxs-lookup"><span data-stu-id="376d3-175">This section provides information about the helper class that is used to embed a Power BI report (.pbix resource) in a form group control.</span></span>

### <a name="syntax"></a><span data-ttu-id="376d3-176">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="376d3-176">Syntax</span></span>
```
public static void initializeReportControl(
     str                 _resourceName,
     FormGroupControl    _formGroupControl,
     str                 _defaultPageName = '',
     boolean             _showFilterPane = false,
     boolean             _showNavPane = false,
     List                _defaultFilters = new List(Types::Class))
```

### <a name="parameters"></a><span data-ttu-id="376d3-177">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="376d3-177">Parameters</span></span>

| <span data-ttu-id="376d3-178">Nome</span><span class="sxs-lookup"><span data-stu-id="376d3-178">Name</span></span> | <span data-ttu-id="376d3-179">descrição</span><span class="sxs-lookup"><span data-stu-id="376d3-179">Description</span></span> |
|---|---|
| <span data-ttu-id="376d3-180">resourceName</span><span class="sxs-lookup"><span data-stu-id="376d3-180">resourceName</span></span> | <span data-ttu-id="376d3-181">O nome do recurso .pbix.</span><span class="sxs-lookup"><span data-stu-id="376d3-181">The name of the .pbix resource.</span></span> |
| <span data-ttu-id="376d3-182">formGroupControl</span><span class="sxs-lookup"><span data-stu-id="376d3-182">formGroupControl</span></span> | <span data-ttu-id="376d3-183">O controle de grupo de formulário ao qual aplicar o controle de relatório do Power BI.</span><span class="sxs-lookup"><span data-stu-id="376d3-183">The form group control to apply the Power BI report control to.</span></span> |
| <span data-ttu-id="376d3-184">defaultPageName</span><span class="sxs-lookup"><span data-stu-id="376d3-184">defaultPageName</span></span> | <span data-ttu-id="376d3-185">O nome de página padrão.</span><span class="sxs-lookup"><span data-stu-id="376d3-185">The default page name.</span></span> |
| <span data-ttu-id="376d3-186">showFilterPane</span><span class="sxs-lookup"><span data-stu-id="376d3-186">showFilterPane</span></span> | <span data-ttu-id="376d3-187">Um valor booliano que indica se o painel de filtros deve ser mostrado (**true**) ou ocultado (**false**).</span><span class="sxs-lookup"><span data-stu-id="376d3-187">A Boolean value that indicates whether the filter pane should be shown (**true**) or hidden (**false**).</span></span> |
| <span data-ttu-id="376d3-188">showNavPane</span><span class="sxs-lookup"><span data-stu-id="376d3-188">showNavPane</span></span> | <span data-ttu-id="376d3-189">Um valor booliano que indica se o painel de navegação deve ser mostrado (**true**) ou ocultado (**false**).</span><span class="sxs-lookup"><span data-stu-id="376d3-189">A Boolean value that indicates whether the navigation pane should be shown (**true**) or hidden (**false**).</span></span> |
| <span data-ttu-id="376d3-190">defaultFilters</span><span class="sxs-lookup"><span data-stu-id="376d3-190">defaultFilters</span></span> | <span data-ttu-id="376d3-191">Os filtros padrão para o relatório do Power BI.</span><span class="sxs-lookup"><span data-stu-id="376d3-191">The default filters for the Power BI report.</span></span> |

