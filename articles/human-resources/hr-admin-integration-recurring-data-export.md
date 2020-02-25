---
title: Criar um aplicativo de exportação de dados recorrente
description: Este artigo mostra como criar um aplicativo lógico de Microsoft Azure que exporta dados da Microsoft Dynamics 365 Human Resources em um plano recorrente.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: edd4b999624a845fc145ed9ff348ae9cba782719
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "3008048"
---
# <a name="create-a-recurring-data-export-app"></a><span data-ttu-id="cb77b-103">Criar um aplicativo de exportação de dados recorrente</span><span class="sxs-lookup"><span data-stu-id="cb77b-103">Create a recurring data export app</span></span>

<span data-ttu-id="cb77b-104">Este artigo mostra como criar um aplicativo lógico de Microsoft Azure que exporta dados da Microsoft Dynamics 365 Human Resources em um plano recorrente.</span><span class="sxs-lookup"><span data-stu-id="cb77b-104">This article shows how to create a Microsoft Azure logic app that exports data from Microsoft Dynamics 365 Human Resources on a recurring schedule.</span></span> <span data-ttu-id="cb77b-105">O tutorial tira proveito da interface de programação de aplicativo (API) REST de recursos humanos para exportar os dados.</span><span class="sxs-lookup"><span data-stu-id="cb77b-105">The tutorial takes advantage of Human Resources' DMF package REST application programming interface (API) to export the data.</span></span> <span data-ttu-id="cb77b-106">Depois que os dados tiverem sido exportados, o aplicativo lógico salva o pacote de dados exportados em uma pasta Microsoft OneDrive for Business.</span><span class="sxs-lookup"><span data-stu-id="cb77b-106">After the data has been exported, the logic app saves the exported data package to a Microsoft OneDrive for Business folder.</span></span>

## <a name="business-scenario"></a><span data-ttu-id="cb77b-107">Cenário de negócios</span><span class="sxs-lookup"><span data-stu-id="cb77b-107">Business scenario</span></span>

<span data-ttu-id="cb77b-108">Em um cenário comercial típico para integrações do Microsoft Dynamics 365, os dados devem ser exportados para um sistema downstream em um plano recorrente.</span><span class="sxs-lookup"><span data-stu-id="cb77b-108">In one typical business scenario for Microsoft Dynamics 365 integrations, data must be exported to a downstream system on a recurring schedule.</span></span> <span data-ttu-id="cb77b-109">Este tutorial mostra como exportar todos os registros de trabalhador da Microsoft Dynamics 365 Human Resources e salvar a lista de trabalhadores em uma pasta OneDrive for Business.</span><span class="sxs-lookup"><span data-stu-id="cb77b-109">This tutorial shows how to export all worker records from Microsoft Dynamics 365 Human Resources and save the list of workers in a OneDrive for Business folder.</span></span>

> [!TIP]
> <span data-ttu-id="cb77b-110">Os dados específicos que são exportados neste tutorial e o destino dos dados exportados são apenas exemplos.</span><span class="sxs-lookup"><span data-stu-id="cb77b-110">The specific data that is exported in this tutorial and the destination of the exported data are only examples.</span></span> <span data-ttu-id="cb77b-111">Você pode alterá-las facilmente para atender às suas necessidades comerciais.</span><span class="sxs-lookup"><span data-stu-id="cb77b-111">You can easily change them to meet your business needs.</span></span>

## <a name="technologies-used"></a><span data-ttu-id="cb77b-112">Tecnologias usadas</span><span class="sxs-lookup"><span data-stu-id="cb77b-112">Technologies used</span></span>

<span data-ttu-id="cb77b-113">Este tutorial usa as seguintes tecnologias:</span><span class="sxs-lookup"><span data-stu-id="cb77b-113">This tutorial uses the following technologies:</span></span>

- <span data-ttu-id="cb77b-114">**[Dynamics 365 Human Resources](https://dynamics.microsoft.com/talent/overview/)**– A fonte de dados mestre dos trabalhadores que serão exportados.</span><span class="sxs-lookup"><span data-stu-id="cb77b-114">**[Dynamics 365 Human Resources](https://dynamics.microsoft.com/talent/overview/)** – The master data source for workers that will be exported.</span></span>
- <span data-ttu-id="cb77b-115">**[Aplicativos lógicos do Azure](https://azure.microsoft.com/services/logic-apps/)** – A tecnologia que fornece orquestração e programação da exportação recorrente.</span><span class="sxs-lookup"><span data-stu-id="cb77b-115">**[Azure Logic Apps](https://azure.microsoft.com/services/logic-apps/)** – The technology that provides orchestration and scheduling of the recurring export.</span></span>

    - <span data-ttu-id="cb77b-116">**[Conectores](https://docs.microsoft.com/azure/connectors/apis-list)** – A tecnologia usada para conectar o aplicativo lógico às empresas requeridas.</span><span class="sxs-lookup"><span data-stu-id="cb77b-116">**[Connectors](https://docs.microsoft.com/azure/connectors/apis-list)** – The technology that is used to connect the logic app to the required endpoints.</span></span>

        - <span data-ttu-id="cb77b-117">[HTTP com conector Azure AD](https://docs.microsoft.com/connectors/webcontents/)</span><span class="sxs-lookup"><span data-stu-id="cb77b-117">[HTTP with Azure AD](https://docs.microsoft.com/connectors/webcontents/) connector</span></span>
        - <span data-ttu-id="cb77b-118">Conector [OneDrive for Business](https://docs.microsoft.com/azure/connectors/connectors-create-api-onedriveforbusiness)</span><span class="sxs-lookup"><span data-stu-id="cb77b-118">[OneDrive for Business](https://docs.microsoft.com/azure/connectors/connectors-create-api-onedriveforbusiness) connector</span></span>

- <span data-ttu-id="cb77b-119">**[API REST do pacote DMF](../dev-itpro/data-entities/data-management-api.md)** – A tecnologia usada para disparar a exportação e monitorar seu progresso.</span><span class="sxs-lookup"><span data-stu-id="cb77b-119">**[DMF package REST API](../dev-itpro/data-entities/data-management-api.md)** – The technology that is used to trigger the export and monitor its progress.</span></span>
- <span data-ttu-id="cb77b-120">**[OneDrive for Business](https://onedrive.live.com/about/business/)** – O destino dos trabalhadores exportados.</span><span class="sxs-lookup"><span data-stu-id="cb77b-120">**[OneDrive for Business](https://onedrive.live.com/about/business/)** – The destination for the exported workers.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="cb77b-121">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="cb77b-121">Prerequisites</span></span>

<span data-ttu-id="cb77b-122">Antes de iniciar o exercício neste tutorial, você deve ter os seguintes itens:</span><span class="sxs-lookup"><span data-stu-id="cb77b-122">Before you begin the exercise in this tutorial, you must have the following items:</span></span>

- <span data-ttu-id="cb77b-123">Um ambiente de Human Resources que tem permissões de nível de administrador no ambiente</span><span class="sxs-lookup"><span data-stu-id="cb77b-123">A Human Resources environment that has admin-level permissions in the environment</span></span>
- <span data-ttu-id="cb77b-124">Uma [Assinatura do Azure](https://azure.microsoft.com/free/) para hospedar o aplicativo lógico</span><span class="sxs-lookup"><span data-stu-id="cb77b-124">An [Azure subscription](https://azure.microsoft.com/free/) to host the logic app</span></span>

## <a name="the-exercise"></a><span data-ttu-id="cb77b-125">O exercício</span><span class="sxs-lookup"><span data-stu-id="cb77b-125">The exercise</span></span>

<span data-ttu-id="cb77b-126">Depois de concluir este exercício, você terá um aplicativo lógico conectado ao seu ambiente de Human Resources e à sua conta do OneDrive for Business.</span><span class="sxs-lookup"><span data-stu-id="cb77b-126">At the end of this exercise, you will have a logic app that is connected to your Human Resources environment and your OneDrive for Business account.</span></span> <span data-ttu-id="cb77b-127">O aplicativo lógico exporta um pacote de dados de recursos humanos, aguarda a conclusão da exportação, faz o download do pacote de dados exportados e salva o pacote de dados na pasta OneDrive for Business que você especificou.</span><span class="sxs-lookup"><span data-stu-id="cb77b-127">The logic app will export a data package from Human Resources, wait for the export to be completed, download the exported data package, and save the data package in the OneDrive for Business folder that you specified.</span></span>

<span data-ttu-id="cb77b-128">O aplicativo lógico concluído será semelhante à ilustração a seguir.</span><span class="sxs-lookup"><span data-stu-id="cb77b-128">The completed logic app will resemble the following illustration.</span></span>

![Visão geral do aplicativo lógico](media/integration-logic-app-overview.png)

### <a name="step-1-create-a-data-export-project-in-human-resources"></a><span data-ttu-id="cb77b-130">Etapa 1: Criar um projeto de exportação de dados em recursos humanos</span><span class="sxs-lookup"><span data-stu-id="cb77b-130">Step 1: Create a data export project in Human Resources</span></span>

<span data-ttu-id="cb77b-131">Em Human Resources, crie um projeto de exportação de dados que exporta trabalhadores.</span><span class="sxs-lookup"><span data-stu-id="cb77b-131">In Human Resources, create a data export project that exports workers.</span></span> <span data-ttu-id="cb77b-132">Nomeie o projeto **Exportar trabalhadores**, e certifique-se de que a opção **Gerar pacote de dados** está definida como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="cb77b-132">Name the project **Export Workers**, and make sure that the **Generate data package** option is set to **Yes**.</span></span> <span data-ttu-id="cb77b-133">Adicione uma única entidade (**Trabalhador**) ao projeto e selecione o formato a ser exportado.</span><span class="sxs-lookup"><span data-stu-id="cb77b-133">Add a single entity (**Worker**) to the project, and select the format to export in.</span></span> <span data-ttu-id="cb77b-134">(O formato Microsoft Excel é usado neste tutorial.)</span><span class="sxs-lookup"><span data-stu-id="cb77b-134">(Microsoft Excel format is used in this tutorial.)</span></span>

![Projeto de dados de exportação de trabalhadores](media/integration-logic-app-export-workers-project.png)

> [!IMPORTANT]
> <span data-ttu-id="cb77b-136">Lembre o nome do projeto de exportação de dados.</span><span class="sxs-lookup"><span data-stu-id="cb77b-136">Remember the name of the data export project.</span></span> <span data-ttu-id="cb77b-137">Você precisará delas quando criar o aplicativo lógico na próxima etapa.</span><span class="sxs-lookup"><span data-stu-id="cb77b-137">You will need it when you create the logic app in the next step.</span></span>

### <a name="step-2-create-the-logic-app"></a><span data-ttu-id="cb77b-138">Etapa 2: Criar o aplicativo lógico</span><span class="sxs-lookup"><span data-stu-id="cb77b-138">Step 2: Create the logic app</span></span>

<span data-ttu-id="cb77b-139">A maior parte do exercício envolve a criação do aplicativo lógico.</span><span class="sxs-lookup"><span data-stu-id="cb77b-139">The bulk of the exercise involves creating the logic app.</span></span>

1. <span data-ttu-id="cb77b-140">No portal do Azure, crie um aplicativo lógico.</span><span class="sxs-lookup"><span data-stu-id="cb77b-140">In the Azure portal, create a logic app.</span></span>

    ![Página de criação lógica de aplicativo](media/integration-logic-app-creation-1.png)

2. <span data-ttu-id="cb77b-142">No designer de aplicativos lógicos, comece com um aplicativo lógico em branco.</span><span class="sxs-lookup"><span data-stu-id="cb77b-142">In the Logic Apps Designer, start with a blank logic app.</span></span>
3. <span data-ttu-id="cb77b-143">Adicione um [Disparador de agenda recorrência](https://docs.microsoft.com/azure/connectors/connectors-native-recurrence) para executar o aplicativo lógica a cada 24 horas (ou de acordo com um plano de sua escolha).</span><span class="sxs-lookup"><span data-stu-id="cb77b-143">Add a [Recurrence Schedule trigger](https://docs.microsoft.com/azure/connectors/connectors-native-recurrence) to run the logic app every 24 hours (or according to a schedule of your choice).</span></span>

    ![Caixa de diálogo de recorrência](media/integration-logic-app-recurrence-step.png)

4. <span data-ttu-id="cb77b-145">Chame a API REST de DMF [ExportToPackage](../dev-itpro/data-entities/data-management-api.md#exporttopackage) para programar a exportação de seu pacote de dados.</span><span class="sxs-lookup"><span data-stu-id="cb77b-145">Call the [ExportToPackage](../dev-itpro/data-entities/data-management-api.md#exporttopackage) DMF REST API to schedule the export of your data package.</span></span>

    1. <span data-ttu-id="cb77b-146">Use a ação **Invocar uma solicitação HTTP** do HTTP com conector Azure AD.</span><span class="sxs-lookup"><span data-stu-id="cb77b-146">Use the **Invoke an HTTP request** action from the HTTP with Azure AD connector.</span></span>

        - <span data-ttu-id="cb77b-147">**URL do recurso básico:** A URL do seu ambiente de Human Resources (não inclui informações de caminho/namespace).</span><span class="sxs-lookup"><span data-stu-id="cb77b-147">**Base Resource URL:** The URL of your Human Resources environment (Don't include path/namespace information.)</span></span>
        - <span data-ttu-id="cb77b-148">**Azure AD URI do Recurso:** `http://hr.talent.dynamics.com`</span><span class="sxs-lookup"><span data-stu-id="cb77b-148">**Azure AD Resource URI:** `http://hr.talent.dynamics.com`</span></span>

        > [!NOTE]
        > <span data-ttu-id="cb77b-149">O serviço de Human Resources ainda não fornece um conector que expõe todas as APIs que compõem a API REST do pacote DMF, como **ExportToPackage**.</span><span class="sxs-lookup"><span data-stu-id="cb77b-149">The Human Resources service doesn't yet provide a connector that exposes all the APIs that make up the DMF package REST API, such as **ExportToPackage**.</span></span> <span data-ttu-id="cb77b-150">Em vez disso, você deve chamar as APIs usando solicitações HTTPS brutas por meio do HTTP com o conector Azure AD.</span><span class="sxs-lookup"><span data-stu-id="cb77b-150">Instead, you must call the APIs by using raw HTTPS requests through the HTTP with Azure AD connector.</span></span> <span data-ttu-id="cb77b-151">Esse conector usa Azure Active Directory (Azure AD) para autenticação e autorização para Human Resources.</span><span class="sxs-lookup"><span data-stu-id="cb77b-151">This connector uses Azure Active Directory (Azure AD) for authentication and authorization to Human Resources.</span></span>

        ![HTTP com conector Azure AD](media/integration-logic-app-http-aad-connector-step.png)

    2. <span data-ttu-id="cb77b-153">Faça login no seu ambiente de Human Resources por meio do HTTP com o conector Azure AD.</span><span class="sxs-lookup"><span data-stu-id="cb77b-153">Sign in to your Human Resources environment through the HTTP with Azure AD connector.</span></span>
    3. <span data-ttu-id="cb77b-154">Configure uma solicitação HTTP **LANÇAR** para chamar a API REST de DMF **ExportToPackage**.</span><span class="sxs-lookup"><span data-stu-id="cb77b-154">Set up an HTTP **POST** request to call the **ExportToPackage** DMF REST API.</span></span>

        - <span data-ttu-id="cb77b-155">**Método:** LANÇAR</span><span class="sxs-lookup"><span data-stu-id="cb77b-155">**Method:** POST</span></span>
        - <span data-ttu-id="cb77b-156">**URL da solicitação:** https://\<hostname\>/namespaces/\<namespace\_guid\>/data/DataManagementDefinitionGroups/Microsoft.Dynamics.DataEntities.ExportToPackage</span><span class="sxs-lookup"><span data-stu-id="cb77b-156">**Url of the request:** https://\<hostname\>/namespaces/\<namespace\_guid\>/data/DataManagementDefinitionGroups/Microsoft.Dynamics.DataEntities.ExportToPackage</span></span>
        - <span data-ttu-id="cb77b-157">**Corpo da solicitação:**</span><span class="sxs-lookup"><span data-stu-id="cb77b-157">**Body of the request:**</span></span>

            ```JSON
            {
                "definitionGroupId":"Export Workers",
                "packageName":"talent_package.zip",
                "executionId":"",
                "reExecute":false,
                "legalEntityId":"USMF"
            }
            ```

        ![Invocar uma ação de solicitação HTTP](media/integration-logic-app-export-to-package-step.png)

    > [!TIP]
    > <span data-ttu-id="cb77b-159">Você pode desejar renomear cada etapa para que seja mais significativo do que o nome padrão, **Invocar uma solicitação HTTP**.</span><span class="sxs-lookup"><span data-stu-id="cb77b-159">You might want to rename each step so that it's more meaningful than the default name, **Invoke an HTTP request**.</span></span> <span data-ttu-id="cb77b-160">Por exemplo, você pode renomear essa etapa **ExportToPackage**.</span><span class="sxs-lookup"><span data-stu-id="cb77b-160">For example, you can rename this step **ExportToPackage**.</span></span>

5. <span data-ttu-id="cb77b-161">[Inicialize uma variável](https://docs.microsoft.com/azure/logic-apps/logic-apps-create-variables-store-values#initialize-variable) para armazenar o status de execução da solicitação **ExportToPackage**.</span><span class="sxs-lookup"><span data-stu-id="cb77b-161">[Initialize a variable](https://docs.microsoft.com/azure/logic-apps/logic-apps-create-variables-store-values#initialize-variable) to store the execution status of the **ExportToPackage** request.</span></span>

    ![Inicializar ação variável](media/integration-logic-app-initialize-variable-step.png)

6. <span data-ttu-id="cb77b-163">Aguarde até que o status da execução da exportação de dados seja **Bem-sucedido**.</span><span class="sxs-lookup"><span data-stu-id="cb77b-163">Wait until the execution status of the data export is **Succeeded**.</span></span>

    1. <span data-ttu-id="cb77b-164">Adicione um [Até loop](https://docs.microsoft.com/azure/logic-apps/logic-apps-control-flow-loops#until-loop) que se repita até que o valor da variável **ExecutionStatus** seja **Bem-sucedido**.</span><span class="sxs-lookup"><span data-stu-id="cb77b-164">Add an [Until loop](https://docs.microsoft.com/azure/logic-apps/logic-apps-control-flow-loops#until-loop) that repeats until the value of the **ExecutionStatus** variable is **Succeeded**.</span></span>
    2. <span data-ttu-id="cb77b-165">Adicionar uma ação de **Atraso** que aguarda cinco segundos antes de sondar o status de execução atual da exportação.</span><span class="sxs-lookup"><span data-stu-id="cb77b-165">Add a **Delay** action that waits five seconds before it polls for the current execution status of the export.</span></span>

        ![Até contêiner de loop](media/integration-logic-app-until-loop-step.png)

        > [!NOTE]
        > <span data-ttu-id="cb77b-167">Defina a contagem de limite como **15** para aguardar um máximo de 75 segundos (15 iterações × 5 segundos) para a exportação ser concluída.</span><span class="sxs-lookup"><span data-stu-id="cb77b-167">Set the limit count to **15** to wait a maximum of 75 seconds (15 iterations × 5 seconds) for the export to be completed.</span></span> <span data-ttu-id="cb77b-168">Se a exportação levar mais tempo, ajuste a contagem de limites conforme apropriado.</span><span class="sxs-lookup"><span data-stu-id="cb77b-168">If your export takes more time, adjust the limit count as appropriate.</span></span>        

    3. <span data-ttu-id="cb77b-169">Adicione uma ação **Invocar solicitação HTTP** para chamar a API REST de DMF [GetExecutionSummaryStatus](../dev-itpro/data-entities/data-management-api.md#getexecutionsummarystatus), e definir a variável **ExecutionStatus** ao resultado da resposta **GetExecutionSummaryStatus**.</span><span class="sxs-lookup"><span data-stu-id="cb77b-169">Add an **Invoke HTTP request** action to call the [GetExecutionSummaryStatus](../dev-itpro/data-entities/data-management-api.md#getexecutionsummarystatus) DMF REST API, and set the **ExecutionStatus** variable to the result of the **GetExecutionSummaryStatus** response.</span></span>

        > <span data-ttu-id="cb77b-170">Este exemplo não faz a verificação de erros.</span><span class="sxs-lookup"><span data-stu-id="cb77b-170">This sample doesn't do error checking.</span></span> <span data-ttu-id="cb77b-171">A API **GetExecutionSummaryStatus** pode retornar estados de terminal sem êxito (ou seja, estados diferentes de **Bem-sucedido**).</span><span class="sxs-lookup"><span data-stu-id="cb77b-171">The **GetExecutionSummaryStatus** API can return non-successful terminal states (that is, states other than **Succeeded**).</span></span> <span data-ttu-id="cb77b-172">Para obter mais informações, consulte a [documentação do API](../dev-itpro/data-entities/data-management-api.md#getexecutionsummarystatus).</span><span class="sxs-lookup"><span data-stu-id="cb77b-172">For more information, see the [API documentation](../dev-itpro/data-entities/data-management-api.md#getexecutionsummarystatus).</span></span>

        - <span data-ttu-id="cb77b-173">**Método:** LANÇAR</span><span class="sxs-lookup"><span data-stu-id="cb77b-173">**Method:** POST</span></span>
        - <span data-ttu-id="cb77b-174">**URL da solicitação:** https://\<hostname\>/namespaces/\<namespace\_guid\>/data/DataManagementDefinitionGroups/Microsoft.Dynamics.DataEntities.GetExecutionSummaryStatus</span><span class="sxs-lookup"><span data-stu-id="cb77b-174">**Url of the request:** https://\<hostname\>/namespaces/\<namespace\_guid\>/data/DataManagementDefinitionGroups/Microsoft.Dynamics.DataEntities.GetExecutionSummaryStatus</span></span>
        - <span data-ttu-id="cb77b-175">**Corpo da solicitação:** body('Invoke\_an\_HTTP\_request')?['value']</span><span class="sxs-lookup"><span data-stu-id="cb77b-175">**Body of the request:** body('Invoke\_an\_HTTP\_request')?['value']</span></span>

            > [!NOTE]
            > <span data-ttu-id="cb77b-176">Talvez seja necessário inserir o **Corpo da solicitação** no modo de exibição de código ou no editor de funções no designer.</span><span class="sxs-lookup"><span data-stu-id="cb77b-176">You might have to enter the **Body of the request** value either in code view or in the function editor in the designer.</span></span>

        ![Invocar uma ação de solicitação 2 HTTP](media/integration-logic-app-get-execution-status-step.png)

        ![Definir ação variável](media/integration-logic-app-set-variable-step.png)

        > [!IMPORTANT]
        > <span data-ttu-id="cb77b-179">O valor da ação **Definir variável** (**body('Invoke\_an\_HTTP\_request\_2')?['value']**) será diferente do valor para o valor de corpo **Invocar uma solicitação HTTP 2**, embora o designer mostre os valores da mesma forma.</span><span class="sxs-lookup"><span data-stu-id="cb77b-179">The value for the **Set variable** action (**body('Invoke\_an\_HTTP\_request\_2')?['value']**) will differ from the value for the **Invoke an HTTP request 2** body value, even though the designer will show the values in the same way.</span></span>

7. <span data-ttu-id="cb77b-180">Obter a URL de download do pacote exportado.</span><span class="sxs-lookup"><span data-stu-id="cb77b-180">Get the download URL of the exported package.</span></span>

    - <span data-ttu-id="cb77b-181">Adicione uma ação **Invocar solicitação HTTP** para chamar a API REST do DMF [GetExportedPackageUrl](../dev-itpro/data-entities/data-management-api.md#getexportedpackageurl).</span><span class="sxs-lookup"><span data-stu-id="cb77b-181">Add an **Invoke HTTP request** action to call the [GetExportedPackageUrl](../dev-itpro/data-entities/data-management-api.md#getexportedpackageurl) DMF REST API.</span></span>

        - <span data-ttu-id="cb77b-182">**Método:** LANÇAR</span><span class="sxs-lookup"><span data-stu-id="cb77b-182">**Method:** POST</span></span>
        - <span data-ttu-id="cb77b-183">**URL da solicitação:** https://\<hostname\>/namespaces/\<namespace\_guid\>/data/DataManagementDefinitionGroups/Microsoft.Dynamics.DataEntities.GetExportedPackageUrl</span><span class="sxs-lookup"><span data-stu-id="cb77b-183">**Url of the request:** https://\<hostname\>/namespaces/\<namespace\_guid\>/data/DataManagementDefinitionGroups/Microsoft.Dynamics.DataEntities.GetExportedPackageUrl</span></span>
        - <span data-ttu-id="cb77b-184">**Corpo da solicitação:** {"executionId": body('GetExportedPackageURL')?['value']}</span><span class="sxs-lookup"><span data-stu-id="cb77b-184">**Body of the request:** {"executionId": body('GetExportedPackageURL')?['value']}</span></span>

        ![Ação GetExportedPackageURL](media/integration-logic-app-get-exported-package-step.png)

8. <span data-ttu-id="cb77b-186">Baixe o pacote exportado.</span><span class="sxs-lookup"><span data-stu-id="cb77b-186">Download the exported package.</span></span>

    - <span data-ttu-id="cb77b-187">Adicione uma solicitação HTTP **OBTER** (uma ação de conector [HTTP integrada](https://docs.microsoft.com/azure/connectors/connectors-native-http)) para baixar o pacote da URL que foi retornada na etapa anterior.</span><span class="sxs-lookup"><span data-stu-id="cb77b-187">Add an HTTP **GET** request (a built-in [HTTP connector action](https://docs.microsoft.com/azure/connectors/connectors-native-http)) to download the package from the URL that was returned in the previous step.</span></span>

        - <span data-ttu-id="cb77b-188">**Método:** OBTER</span><span class="sxs-lookup"><span data-stu-id="cb77b-188">**Method:** GET</span></span>
        - <span data-ttu-id="cb77b-189">**URI:** body('Invoke\_an\_HTTP\_request\_3').value</span><span class="sxs-lookup"><span data-stu-id="cb77b-189">**URI:** body('Invoke\_an\_HTTP\_request\_3').value</span></span>

            > [!NOTE]
            > <span data-ttu-id="cb77b-190">Talvez seja necessário inserir o **URI** no modo de exibição de código ou no editor de funções no designer.</span><span class="sxs-lookup"><span data-stu-id="cb77b-190">You might have to enter the **URI** value either in code view or in the function editor in the designer.</span></span>

        ![Ação OBTER HTTP](media/integration-logic-app-download-file-step.png)

        > [!NOTE]
        > <span data-ttu-id="cb77b-192">Essa solicitação não exige nenhuma autenticação adicional, porque a URL que a **GetExportedPackageUrl** retorna inclui um token de assinaturas de acesso compartilhado que concede acesso ao download do arquivo.</span><span class="sxs-lookup"><span data-stu-id="cb77b-192">This request doesn't require any additional authentication, because the URL that the **GetExportedPackageUrl** API returns includes a shared access signatures token that grants access to download the file.</span></span>

9. <span data-ttu-id="cb77b-193">Salve o pacote baixado usando o conector do [OneDrive for Business](https://docs.microsoft.com/azure/connectors/connectors-create-api-onedriveforbusiness).</span><span class="sxs-lookup"><span data-stu-id="cb77b-193">Save the downloaded package by using the [OneDrive for Business](https://docs.microsoft.com/azure/connectors/connectors-create-api-onedriveforbusiness) connector.</span></span>

    - <span data-ttu-id="cb77b-194">Adicione uma ação [Criar arquivo](https://docs.microsoft.com/connectors/onedriveforbusinessconnector/#create-file) do OneDrive for Business.</span><span class="sxs-lookup"><span data-stu-id="cb77b-194">Add a OneDrive for Business [Create File](https://docs.microsoft.com/connectors/onedriveforbusinessconnector/#create-file) action.</span></span>
    - <span data-ttu-id="cb77b-195">Conecte sua conta do OneDrive for Business, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="cb77b-195">Connect to your OneDrive for Business account, as required.</span></span>

        - <span data-ttu-id="cb77b-196">**Caminho da pasta:** Uma pasta escolhida</span><span class="sxs-lookup"><span data-stu-id="cb77b-196">**Folder Path:** A folder of your choice</span></span>
        - <span data-ttu-id="cb77b-197">**Nome do arquivo:** worker\_package.zip</span><span class="sxs-lookup"><span data-stu-id="cb77b-197">**File Name:** worker\_package.zip</span></span>
        - <span data-ttu-id="cb77b-198">**Conteúdo do arquivo:** O corpo da etapa anterior (conteúdo dinâmico)</span><span class="sxs-lookup"><span data-stu-id="cb77b-198">**File Content:** The body from the previous step (dynamic content)</span></span>

        ![Criar ação de arquivo](media/integration-logic-app-create-file-step.png)

### <a name="step-3-test-the-logic-app"></a><span data-ttu-id="cb77b-200">Etapa 3: Testar o aplicativo lógico</span><span class="sxs-lookup"><span data-stu-id="cb77b-200">Step 3: Test the logic app</span></span>

<span data-ttu-id="cb77b-201">Para testar seu aplicativo lógico, selecione o botão **Executar** no designer.</span><span class="sxs-lookup"><span data-stu-id="cb77b-201">To test your logic app, select the **Run** button in the designer.</span></span> <span data-ttu-id="cb77b-202">Você verá que as etapas do aplicativo lógico começam a ser executadas.</span><span class="sxs-lookup"><span data-stu-id="cb77b-202">You will see that the steps of the logic app start to run.</span></span> <span data-ttu-id="cb77b-203">Após 30 a 40 segundos, o aplicativo lógico deve concluir a execução, e sua pasta OneDrive for Business deve incluir um novo arquivo de pacote que contém os trabalhadores exportados.</span><span class="sxs-lookup"><span data-stu-id="cb77b-203">After 30 to 40 seconds, the logic app should finish running, and your OneDrive for Business folder should include a new package file that contains the exported workers.</span></span>

<span data-ttu-id="cb77b-204">Se uma falha for relatada em qualquer etapa, selecione a etapa com falha no designer e examine os campos de **Entradas** e **Saídas** da falha.</span><span class="sxs-lookup"><span data-stu-id="cb77b-204">If a failure is reported for any step, select the failed step in the designer, and examine the **Inputs** and **Outputs** fields for it.</span></span> <span data-ttu-id="cb77b-205">Depure e ajuste a etapa conforme necessário para corrigir os erros.</span><span class="sxs-lookup"><span data-stu-id="cb77b-205">Debug and adjust the step as required to correct the errors.</span></span>

<span data-ttu-id="cb77b-206">A ilustração a seguir mostra como o designer de aplicativos lógico é parecido quando todas as etapas do aplicativo lógico são executadas com êxito.</span><span class="sxs-lookup"><span data-stu-id="cb77b-206">The following illustration shows what the Logic Apps Designer looks like when all the steps of the logic app run successfully.</span></span>

![Execução bem-sucedida de aplicativo lógico](media/integration-logic-app-successful-run.png)

## <a name="summary"></a><span data-ttu-id="cb77b-208">Resumo</span><span class="sxs-lookup"><span data-stu-id="cb77b-208">Summary</span></span>

<span data-ttu-id="cb77b-209">Neste tutorial, você aprendeu a usar um aplicativo lógico para exportar dados de recursos humanos e salvar os dados exportados em uma pasta OneDrive for Business.</span><span class="sxs-lookup"><span data-stu-id="cb77b-209">In this tutorial, you learned how to use a logic app to export data from Human Resources and save the exported data to a OneDrive for Business folder.</span></span> <span data-ttu-id="cb77b-210">Você pode modificar as etapas deste tutorial conforme necessário para atender às suas necessidades comerciais.</span><span class="sxs-lookup"><span data-stu-id="cb77b-210">You can modify the steps of this tutorial as required to suit your business needs.</span></span>


