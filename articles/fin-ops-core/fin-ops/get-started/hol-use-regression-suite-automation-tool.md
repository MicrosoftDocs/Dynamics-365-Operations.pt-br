---
title: Usar o tutorial sobre a Regression Suite Automation Tool
description: Esse tópico mostra como usar a Regression Suite Automation Tool (RSAT). Descreve diversos recursos e oferece exemplos que usam o script avançado.
author: kfend
manager: AnnBe
ms.date: 06/09/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 21761
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: AX 7.0.0, Operations
ms.openlocfilehash: 6cdaa89fb6d50ebaaaefe7f92d7224a1567d17d1
ms.sourcegitcommit: 3dede95a3b17de920bb0adcb33029f990682752b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/18/2020
ms.locfileid: "3070811"
---
# <a name="use-the-regression-suite-automation-tool-tutorial"></a><span data-ttu-id="d358c-104">Usa o tutorial da Regression Suite Automation Tool</span><span class="sxs-lookup"><span data-stu-id="d358c-104">Use the Regression suite automation tool tutorial</span></span>

[!include [banner](../includes/banner.md)]

> [!NOTE]
> <span data-ttu-id="d358c-105">Usa as ferramentas do navegador da internet para fazer download e salvar esta página no formato pdf.</span><span class="sxs-lookup"><span data-stu-id="d358c-105">Use your internet browser tools to download and save this page in pdf format.</span></span> 

<span data-ttu-id="d358c-106">Este tutorial aborda alguns dos recursos avançados da Regression Suite Automation Tool (RSAT), inclui uma atribuição de demonstração e descreve a estratégia e os principais pontos de aprendizagem.</span><span class="sxs-lookup"><span data-stu-id="d358c-106">This tutorial walks through some of the advanced features of the Regression suite automation tool (RSAT), includes a demo assignment, and describes strategy and key learning points.</span></span>

## <a name="features-of-rsattask-recorder"></a><span data-ttu-id="d358c-107">Recursos do RSAT/Gravador de tarefas</span><span class="sxs-lookup"><span data-stu-id="d358c-107">Features of RSAT/Task recorder</span></span>

### <a name="validate-a-field-value"></a><span data-ttu-id="d358c-108">Validar um valor do campo</span><span class="sxs-lookup"><span data-stu-id="d358c-108">Validate a field value</span></span>

<span data-ttu-id="d358c-109">Para obter informações sobre este recurso, consulte [Criar uma nova gravação de tarefas que tem uma função de Validação](./hol-set-up-regression-suite-automation-tool.md#create-a-new-task-recording-that-has-a-validate-function).</span><span class="sxs-lookup"><span data-stu-id="d358c-109">For information about this feature, see the [Create a new task recording that has a Validate function](./hol-set-up-regression-suite-automation-tool.md#create-a-new-task-recording-that-has-a-validate-function).</span></span>

### <a name="saved-variable"></a><span data-ttu-id="d358c-110">Variável salva</span><span class="sxs-lookup"><span data-stu-id="d358c-110">Saved variable</span></span>

<span data-ttu-id="d358c-111">Para obter informações sobre este recurso, consulte [Modificar uma gravação de tarefas existente para criar uma variável salva](./hol-set-up-regression-suite-automation-tool.md#modify-an-existing-task-recording-to-create-a-saved-variable).</span><span class="sxs-lookup"><span data-stu-id="d358c-111">For information about this feature, see the [Modify an existing task recording to create a saved variable](./hol-set-up-regression-suite-automation-tool.md#modify-an-existing-task-recording-to-create-a-saved-variable).</span></span>

### <a name="derived-test-case"></a><span data-ttu-id="d358c-112">Caso de teste derivado</span><span class="sxs-lookup"><span data-stu-id="d358c-112">Derived test case</span></span>

1. <span data-ttu-id="d358c-113">Abra a Regression Suite Automation Tool (RSAT) e selecione os casos de teste que você criou no [tutorial Configurar e instalar a Regression Suite Automation Tool](./hol-set-up-regression-suite-automation-tool.md).</span><span class="sxs-lookup"><span data-stu-id="d358c-113">Open Regression suite automation tool (RSAT), and select both the test cases that you created in [Set up and install Regression suite automation tool tutorial](./hol-set-up-regression-suite-automation-tool.md).</span></span>
2. <span data-ttu-id="d358c-114">Selecione **Novo \> Criar caso de teste derivado**.</span><span class="sxs-lookup"><span data-stu-id="d358c-114">Select **New \> Create derived test case**.</span></span>

    ![Comando Criar caso de teste derivado no menu Novo](./media/use_rsa_tool_01.png)

3. <span data-ttu-id="d358c-116">Você receberá uma mensagem que determina que um caso de teste derivado será criado, para cada caso de teste selecionado no conjunto de testes atual, e que cada caso de teste derivado terá sua própria cópia do arquivo de parâmetro do Excel.</span><span class="sxs-lookup"><span data-stu-id="d358c-116">You receive a message that states that a derived test case will be created for each selected test case in the current test suite, and that each derived test case will have its own copy of the Excel parameter file.</span></span> <span data-ttu-id="d358c-117">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="d358c-117">Select **OK**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d358c-118">Ao executar um caso de teste derivado, ele usa a gravação de tarefas de seu caso de teste pai e sua própria cópia do arquivo de parâmetros do Excel.</span><span class="sxs-lookup"><span data-stu-id="d358c-118">When you run a derived test case, it uses the task recording of its parent test case and its own copy of the Excel parameter file.</span></span> <span data-ttu-id="d358c-119">Dessa forma, você pode executar o mesmo teste com diferentes parâmetros, sem ter que manter mais de uma gravação de tarefas.</span><span class="sxs-lookup"><span data-stu-id="d358c-119">In this way, you can run the same test with different parameters, without having to maintain more than one task recording.</span></span> <span data-ttu-id="d358c-120">Um caso de teste derivado não deve fazer parte do mesmo conjunto de testes do caso de teste pai.</span><span class="sxs-lookup"><span data-stu-id="d358c-120">A derived test case doesn't have to be part of the same test suite as its parent test case.</span></span>

    ![Caixa de mensagem](./media/use_rsa_tool_02.png)

    <span data-ttu-id="d358c-122">Dois casos de teste derivados adicionais são criados e a caixa de seleção **Derivado?** é marcada para eles.</span><span class="sxs-lookup"><span data-stu-id="d358c-122">Two additional derived test cases are created, and the **Derived?** check box is selected for them.</span></span>

    ![Casos de teste derivados criados](./media/use_rsa_tool_03.png)

    <span data-ttu-id="d358c-124">Um caso de teste derivado é criado automaticamente no Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="d358c-124">A derived test case is automatically created in Azure DevOps.</span></span> <span data-ttu-id="d358c-125">É um item filho do caso de teste **Criar um novo produto** e é marcado com uma palavra-chave especial: **RSAT:DerivedTestSteps**.</span><span class="sxs-lookup"><span data-stu-id="d358c-125">It's a child item of the **Create a new product** test case and is tagged with a special keyword: **RSAT:DerivedTestSteps**.</span></span> <span data-ttu-id="d358c-126">Esses casos de teste são adicionados automaticamente ao plano de teste no Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="d358c-126">These test cases are also automatically added to the test plan in Azure DevOps.</span></span>

    ![Palavra-chave RSAT:DerivedTestSteps](./media/use_rsa_tool_04.png)

    > [!NOTE]
    > <span data-ttu-id="d358c-128">Se, por algum motivo, os casos de teste derivados que forem criados não estiverem na ordem correta, vá para Azure DevOps e reorganize-os no conjunto de testes, de forma que o RSAT possa executá-los na ordem correta.</span><span class="sxs-lookup"><span data-stu-id="d358c-128">If, for any reason, the derived test cases that are created aren't in the correct order, go to Azure DevOps, and reorder the test cases in the test suite, so that RSAT can run them in the correct order.</span></span>

4. <span data-ttu-id="d358c-129">Selecione os casos de teste derivados e, em seguida, selecione **Editar** para abrir os arquivos de parâmetro do Excel correspondentes.</span><span class="sxs-lookup"><span data-stu-id="d358c-129">Select the derived test cases, and then select **Edit** to open the corresponding Excel parameter files.</span></span>
5. <span data-ttu-id="d358c-130">Edite esses arquivos de parâmetro do Excel da mesma forma que editou os arquivos pai.</span><span class="sxs-lookup"><span data-stu-id="d358c-130">Edit these Excel parameter files in the same way that you edited the parent files.</span></span> <span data-ttu-id="d358c-131">Em outras palavras, certifique-se de que o ID do produto está definido, de forma que seja gerado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="d358c-131">In other words, make sure that the product ID is set so that it's automatically generated.</span></span> <span data-ttu-id="d358c-132">Além disso, certifique-se de que a variável salva é copiada para os campos relevantes.</span><span class="sxs-lookup"><span data-stu-id="d358c-132">Also make sure that the saved variable is copied to the relevant fields.</span></span>
6. <span data-ttu-id="d358c-133">Na guia **Geral** dos arquivos de parâmetro do Excel, atualize o valor do campo **Empresa** para **USSI**, dessa forma, os casos de teste derivados serão gerados com uma entidade legal diferente daquela do caso de teste pai.</span><span class="sxs-lookup"><span data-stu-id="d358c-133">On the **General** tab of both Excel parameter files, update the value of the **Company** field to **USSI**, so that the derived test cases will be run against a different legal entity than the parent test case.</span></span> <span data-ttu-id="d358c-134">Para executar os casos de teste para um usuário específico (ou a função que está associada a um usuário específico), você pode atualizar o valor do campo **Testar Usuário**.</span><span class="sxs-lookup"><span data-stu-id="d358c-134">To run the test cases against a specific user (or the role that is associated with a specific user), you can update the value of the **Test User** field.</span></span>
7. <span data-ttu-id="d358c-135">Selecione **Executar** e valide se o produto é criado na entidade legal do USMF e do USSI.</span><span class="sxs-lookup"><span data-stu-id="d358c-135">Select **Run**, and validate that the product is created in both the USMF legal entity and the USSI legal entity.</span></span>

### <a name="validate-notifications"></a><span data-ttu-id="d358c-136">Validar notificações</span><span class="sxs-lookup"><span data-stu-id="d358c-136">Validate notifications</span></span>

<span data-ttu-id="d358c-137">Esse recurso pode ser usado para validar se uma ação ocorreu.</span><span class="sxs-lookup"><span data-stu-id="d358c-137">This feature can be used to validate whether an action occurred.</span></span> <span data-ttu-id="d358c-138">Por exemplo, quando uma ordem de produção é criada, prevista e iniciada, o aplicativo mostra a mensagem "Produção - Início" para notificar que a ordem de produção foi iniciada.</span><span class="sxs-lookup"><span data-stu-id="d358c-138">For example, when a production order is created, estimated, and then started, the app shows a "Production – Start" message to notify you that the production order has been started.</span></span>

![Produção - Iniciar notificação](./media/use_rsa_tool_05.png)

<span data-ttu-id="d358c-140">Você pode validar essa mensagem através do RSAT inserindo o texto da mensagem na guia **MessageValidation** do arquivo de parâmetro do Excel para o registro apropriado.</span><span class="sxs-lookup"><span data-stu-id="d358c-140">You can validate this message through RSAT by entering the message text on the **MessageValidation** tab of the Excel parameter file for the appropriate recording.</span></span>

![Guia Validação da Mensagem](./media/use_rsa_tool_06.png)

<span data-ttu-id="d358c-142">Depois que o caso de teste for executado, a mensagem no arquivo de parâmetros do Excel será comparada à mensagem mostrada.</span><span class="sxs-lookup"><span data-stu-id="d358c-142">After the test case is run, the message in the Excel parameter file is compared to the message that is shown.</span></span> <span data-ttu-id="d358c-143">Se as mensagens não forem correspondentes, o caso de teste falhará.</span><span class="sxs-lookup"><span data-stu-id="d358c-143">If the messages don't match, the test case will fail.</span></span>

> [!NOTE]
> <span data-ttu-id="d358c-144">Você pode inserir mais de uma mensagem na guia **MessageValidation** do arquivo de parâmetro do Excel.</span><span class="sxs-lookup"><span data-stu-id="d358c-144">You can enter more than one message on the **MessageValidation** tab in the Excel parameter file.</span></span> <span data-ttu-id="d358c-145">As mensagens também podem ser de erro ou de advertência, em vez de mensagens informativas.</span><span class="sxs-lookup"><span data-stu-id="d358c-145">The messages also can be error or warning messages instead of informational messages.</span></span>

### <a name="validate-values-by-using-operators"></a><span data-ttu-id="d358c-146">Validar valores usando operadores</span><span class="sxs-lookup"><span data-stu-id="d358c-146">Validate values by using operators</span></span>

<span data-ttu-id="d358c-147">Nas versões anteriores do RSAT, você pode validar valores somente se um valor de controle for igual a um valor esperado.</span><span class="sxs-lookup"><span data-stu-id="d358c-147">In previous versions of RSAT, you could validate values only if a control value equaled an expected value.</span></span> <span data-ttu-id="d358c-148">O novo recurso permite validar que uma variável não é igual a, é menor que ou é maior que um valor especificado.</span><span class="sxs-lookup"><span data-stu-id="d358c-148">The new feature lets you validate that a variable isn't equal to, is less than, or is more than a specified value.</span></span>

- <span data-ttu-id="d358c-149">Para usar este recurso, abra o arquivo **Microsoft.Dynamics.RegressionSuite.WindowsApp.exe.config** na pasta de instalação do RSAT (por exemplo, **C:\\Arquivos de Programas (x86)\\Regression Suite Automation Tool**) e altere o valor no seguinte elemento de **falso** para **verdadeiro**.</span><span class="sxs-lookup"><span data-stu-id="d358c-149">To use this feature, open the **Microsoft.Dynamics.RegressionSuite.WindowsApp.exe.config** file under the RSAT installation folder (for example, **C:\\Program Files (x86)\\Regression Suite Automation Tool**), and change the value in the following element from **false** to **true**.</span></span>

    ```xml
    <add key="AddOperatorFieldsToExcelValidation" value="false" />
    ```

    <span data-ttu-id="d358c-150">No arquivo de parâmetro do Excel, é exibido um novo campo **Operador**.</span><span class="sxs-lookup"><span data-stu-id="d358c-150">In the Excel parameter file, a new **Operator** field appears.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d358c-151">Se estiver usando uma versão mais antiga do RSAT, você deverá gerar novos arquivos de parâmetro do Excel.</span><span class="sxs-lookup"><span data-stu-id="d358c-151">If you've been using an older version of RSAT, you must generate new Excel parameter files.</span></span>

    ![Campo Operador](./media/use_rsa_tool_07.png)

<span data-ttu-id="d358c-153">O exemplo a seguir mostra como é possível usar este recurso para validar se o estoque disponível é maior que 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="d358c-153">The following example shows how you can use this feature to validate whether the on-hand inventory is more than 0 (zero).</span></span>

1. <span data-ttu-id="d358c-154">Nos dados de demonstração da empresa **USMF**, crie uma gravação de tarefas que tenha as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="d358c-154">In the demo data in the **USMF** company, create a task recording that has the following steps:</span></span>

    1. <span data-ttu-id="d358c-155">Vá para **Gerenciamento de informações do produto \> Produtos \> Produtos liberados**.</span><span class="sxs-lookup"><span data-stu-id="d358c-155">Go to **Product information management \> Products \> Released products**.</span></span>
    2. <span data-ttu-id="d358c-156">Use o Filtro Rápido para localizar registros.</span><span class="sxs-lookup"><span data-stu-id="d358c-156">Use the Quick Filter to find records.</span></span> <span data-ttu-id="d358c-157">Por exemplo, filtre um valor de **1000** para o campo **Número do item**.</span><span class="sxs-lookup"><span data-stu-id="d358c-157">For example, filter on a value of **1000** for the **Item number** field.</span></span>
    3. <span data-ttu-id="d358c-158">Selecione **Estoque disponível**.</span><span class="sxs-lookup"><span data-stu-id="d358c-158">Select **On-hand inventory**.</span></span>
    4. <span data-ttu-id="d358c-159">Use o Filtro Rápido para localizar registros.</span><span class="sxs-lookup"><span data-stu-id="d358c-159">Use the Quick Filter to find records.</span></span> <span data-ttu-id="d358c-160">Por exemplo, filtro em um valor **1** para o campo **Local**.</span><span class="sxs-lookup"><span data-stu-id="d358c-160">For example, filter on a value of **1** for the **Site** field.</span></span>
    5. <span data-ttu-id="d358c-161">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="d358c-161">In the list, mark the selected row.</span></span>
    6. <span data-ttu-id="d358c-162">Valide se o valor do campo **Total disponível** é **411.0000000000000000**.</span><span class="sxs-lookup"><span data-stu-id="d358c-162">Validate that the value of the **Total available** field is **411.0000000000000000**.</span></span>

2. <span data-ttu-id="d358c-163">Salve a gravação de tarefas para a biblioteca BPM no LCS e sincronize-o para Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="d358c-163">Save the task recording to the BPM library in LCS, and sync it to Azure DevOps.</span></span>
3. <span data-ttu-id="d358c-164">Adicione o caso de teste ao plano de teste e carregue o caso de teste no RSAT.</span><span class="sxs-lookup"><span data-stu-id="d358c-164">Add the test case to the test plan, and load the test case into RSAT.</span></span>
4. <span data-ttu-id="d358c-165">Abra o arquivo de parâmetro do Excel.</span><span class="sxs-lookup"><span data-stu-id="d358c-165">Open the Excel parameter file.</span></span> <span data-ttu-id="d358c-166">Na guia **InventOnhandItem** , você verá uma seção **Validar InventOnhandItem** que contenha um campo **Operador** .</span><span class="sxs-lookup"><span data-stu-id="d358c-166">On the **InventOnhandItem** tab, you will see a **Validate InventOnhandItem** section that includes an **Operator** field.</span></span>

    ![Campo Operador](./media/use_rsa_tool_08.png)

5. <span data-ttu-id="d358c-168">Para validar se o estoque disponível sempre será maior que 0, altere o valor do campo **Valor** de **411** para **0** e o valor do campo **Operador** de um sinal de igual (**=**) para um sinal maior que (**\>**).</span><span class="sxs-lookup"><span data-stu-id="d358c-168">To validate whether the inventory on-hand will always be more than 0, change the value of the **Value** field from **411** to **0** and the value of the **Operator** field from an equal sign (**=**) to a greater than sign (**\>**).</span></span>

    ![Valores dos campos Valor e Operador alterados](./media/use_rsa_tool_09.png)

6. <span data-ttu-id="d358c-170">Salve e feche o arquivo de parâmetro do Excel.</span><span class="sxs-lookup"><span data-stu-id="d358c-170">Save and close the Excel parameter file.</span></span>
7. <span data-ttu-id="d358c-171">Selecione **Carregar** para salvar as alterações feitas no arquivo de parâmetros do Excel para o Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="d358c-171">Select **Upload** to save the changes that you made to the Excel parameter file to Azure DevOps.</span></span>

<span data-ttu-id="d358c-172">Agora, se o valor do campo **Total Disponível** para o item especificado no estoque for maior que 0 (zero), os testes serão aprovados, independentemente do valor do estoque disponível real.</span><span class="sxs-lookup"><span data-stu-id="d358c-172">Now, if the value of the **Total Available** field for the specified item in inventory is more than 0 (zero), tests will pass, regardless of the actual on-hand inventory value.</span></span>

### <a name="generator-logs"></a><span data-ttu-id="d358c-173">Logs do gerador</span><span class="sxs-lookup"><span data-stu-id="d358c-173">Generator logs</span></span>

<span data-ttu-id="d358c-174">Este recurso cria uma pasta que contém os logs dos casos de teste que foram executados.</span><span class="sxs-lookup"><span data-stu-id="d358c-174">This feature creates a folder that contains the logs of the test cases that have been run.</span></span>

- <span data-ttu-id="d358c-175">Para usar este recurso, abra o arquivo **Microsoft.Dynamics.RegressionSuite.WindowsApp.exe.config** na pasta de instalação do RSAT (por exemplo, **C:\\Arquivos de Programas (x86)\\Regression Suite Automation Tool**) e altere o valor no seguinte elemento de **falso** para **verdadeiro**.</span><span class="sxs-lookup"><span data-stu-id="d358c-175">To use this feature, open the **Microsoft.Dynamics.RegressionSuite.WindowsApp.exe.config** file under the RSAT installation folder (for example, **C:\\Program Files (x86)\\Regression Suite Automation Tool**), and change the value in the following element from **false** to **true**.</span></span>

    ```xml
    <add key="LogGeneration" value="false" />
    ```

<span data-ttu-id="d358c-176">Depois que os casos de teste são executados, é possível localizar os arquivos de log em **C:\\Users\\\<Username\>\\AppData\\Roaming\\regressionTool\\generatorLogs**.</span><span class="sxs-lookup"><span data-stu-id="d358c-176">After the test cases are run, you can find the log files under **C:\\Users\\\<Username\>\\AppData\\Roaming\\regressionTool\\generatorLogs**.</span></span>

![Pasta GeneratorLogs](./media/use_rsa_tool_10.png)

> [!NOTE]
> <span data-ttu-id="d358c-178">Se houver casos de teste existentes antes de você alterar o valor no arquivo .config, os logs não serão gerados para esses casos de teste até que você gere novos arquivos de execução de teste.</span><span class="sxs-lookup"><span data-stu-id="d358c-178">If there were existing test cases before you changed the value in the .config file, logs won't be generated for those test cases until you generate new test execution files.</span></span>
> 
> ![Comando Gerar Somente Arquivos de Execução de texto no menu Novo](./media/use_rsa_tool_11.png)

### <a name="snapshot"></a><span data-ttu-id="d358c-180">Instantâneo</span><span class="sxs-lookup"><span data-stu-id="d358c-180">Snapshot</span></span>

<span data-ttu-id="d358c-181">Esse recurso faz capturas de tela das etapas executadas durante a gravação de tarefas.</span><span class="sxs-lookup"><span data-stu-id="d358c-181">This feature takes screenshots of the steps that were performed during task recording.</span></span>

- <span data-ttu-id="d358c-182">Para usar este recurso, abra o arquivo **Microsoft.Dynamics.RegressionSuite.WindowsApp.exe.config** na pasta de instalação do RSAT (por exemplo, **C:\\Arquivos de Programas (x86)\\Regression Suite Automation Tool**) e altere o valor do seguinte elemento de **falso** para **verdadeiro**.</span><span class="sxs-lookup"><span data-stu-id="d358c-182">To use this feature, open the **Microsoft.Dynamics.RegressionSuite.WindowsApp.exe.config** file under the RSAT installation folder (for example, **C:\\Program Files (x86)\\Regression Suite Automation Tool**), and change the value of the following element from **false** to **true**.</span></span>

    ```xml
    <add key="VerboseSnapshotsEnabled" value="false" />
    ```

<span data-ttu-id="d358c-183">Em **C:\\Usuários\\\<Nome de usuário\>\\AppData\\Roaming\\regressionTool\\playback**, uma pasta separada será criada para cada caso de teste que for executado.</span><span class="sxs-lookup"><span data-stu-id="d358c-183">Under **C:\\Users\\\<Username\>\\AppData\\Roaming\\regressionTool\\playback**, a separate folder is created for each test case that is run.</span></span>

![Pasta de instantâneo para um caso de teste](./media/use_rsa_tool_12.png)

<span data-ttu-id="d358c-185">Em cada uma dessas pastas, você pode localizar instantâneos das etapas executadas quando os casos de teste foram executados.</span><span class="sxs-lookup"><span data-stu-id="d358c-185">In each of these folders, you can find snapshots of the steps that were performed while the test cases were run.</span></span>

![Arquivos de instantâneo](./media/use_rsa_tool_13.png)

## <a name="assignment"></a><span data-ttu-id="d358c-187">Atribuição</span><span class="sxs-lookup"><span data-stu-id="d358c-187">Assignment</span></span>

### <a name="scenario"></a><span data-ttu-id="d358c-188">Cenário</span><span class="sxs-lookup"><span data-stu-id="d358c-188">Scenario</span></span>

1. <span data-ttu-id="d358c-189">O designer de produtos cria um novo produto liberado.</span><span class="sxs-lookup"><span data-stu-id="d358c-189">The product designer creates a new released product.</span></span>
2. <span data-ttu-id="d358c-190">O gerente de produção inicia uma ordem de produção para deixar o nível de estoque com duas peças.</span><span class="sxs-lookup"><span data-stu-id="d358c-190">The production manager initiates a production order to bring the stock level to two pieces.</span></span>
3. <span data-ttu-id="d358c-191">A fabricação inicia e termina a ordem de produção e verifica se a quantidade disponível está com duas peças.</span><span class="sxs-lookup"><span data-stu-id="d358c-191">Manufacturing starts and ends the production order, and verifies that the on-hand quantity is two pieces.</span></span>
4. <span data-ttu-id="d358c-192">A equipe de venda recebe um pedido de quatro peças do novo produto.</span><span class="sxs-lookup"><span data-stu-id="d358c-192">The sales team receives an order for four pieces of the new product.</span></span> <span data-ttu-id="d358c-193">Portanto, a equipe de vendas atualiza os requisitos líquidos através do plano dinâmico.</span><span class="sxs-lookup"><span data-stu-id="d358c-193">Therefore, the sales team updates the net requirements via the dynamic plan.</span></span> <span data-ttu-id="d358c-194">Como nenhuma capacidade adicional está disponível, a política de ordem padrão é definida como "comprar em vez de fazer".</span><span class="sxs-lookup"><span data-stu-id="d358c-194">Because no additional capacity is available, the default order policy is set to "buy instead of make."</span></span> <span data-ttu-id="d358c-195">Portanto, uma ordem de compra planejada é criada.</span><span class="sxs-lookup"><span data-stu-id="d358c-195">Therefore, a planned purchase order is created.</span></span>
5. <span data-ttu-id="d358c-196">O comprador adiciona um fornecedor, firma a ordem de compra planejada e confirma a ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="d358c-196">The buyer adds a vendor, firms the planned purchase order, and then confirms the purchase order.</span></span>
6. <span data-ttu-id="d358c-197">Quando as mercadorias que foram compradas chegam na loja, o operador da loja pesquisa a ordem de compra relacionada e recebe as mercadorias.</span><span class="sxs-lookup"><span data-stu-id="d358c-197">When the goods that were purchased arrive at the store, the store operator searches the related purchase order and receives the goods.</span></span> <span data-ttu-id="d358c-198">Como a ordem agora está concluída, as mercadorias podem ser separadas e embaladas conforme a ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="d358c-198">Because the order is now completed, goods can be picked and packed against the sales order.</span></span>
7. <span data-ttu-id="d358c-199">O financeiro lança a fatura de compras e a fatura de vendas.</span><span class="sxs-lookup"><span data-stu-id="d358c-199">Finance posts the purchase invoice and sales invoice.</span></span>

<span data-ttu-id="d358c-200">A ilustração a seguir mostra o fluxo para esse cenário.</span><span class="sxs-lookup"><span data-stu-id="d358c-200">The following illustration shows the flow for this scenario.</span></span>

![Fluxo do cenário de demonstração](./media/use_rsa_tool_14.png)

<span data-ttu-id="d358c-202">A ilustração a seguir mostra os processos empresariais para esse cenário no RSAT.</span><span class="sxs-lookup"><span data-stu-id="d358c-202">The following illustration shows the business processes for this scenario in RSAT.</span></span>

![Processos empresariais do cenário de demonstração](./media/use_rsa_tool_15.png)

## <a name="strategy--key-learning"></a><span data-ttu-id="d358c-204">Estratégia – Aprendizagem principal</span><span class="sxs-lookup"><span data-stu-id="d358c-204">Strategy – Key learning</span></span>

### <a name="data"></a><span data-ttu-id="d358c-205">Dados</span><span class="sxs-lookup"><span data-stu-id="d358c-205">Data</span></span>

- <span data-ttu-id="d358c-206">Verifique se você tem volumes de dados representativos (uma cópia da produção/dados de configuração dourada mais dados migrados).</span><span class="sxs-lookup"><span data-stu-id="d358c-206">Make sure that you have representative data volumes (a copy of production/golden configuration data plus migrated data).</span></span>
- <span data-ttu-id="d358c-207">Ao gerar novos dados por meio do gravador de tarefas, cria nomes de teste que não irão entrar em conflito com os nomes existentes (por exemplo, usar um prefixo como **RSATxxx**).</span><span class="sxs-lookup"><span data-stu-id="d358c-207">When you generate new data via Task recorder, create test names that won't conflict with existing names (for example, use a prefix such as **RSATxxx**).</span></span>
- <span data-ttu-id="d358c-208">Use a restauração pontual do Azure para reexecutar testes nos ambientes que não estão na Camada 1.</span><span class="sxs-lookup"><span data-stu-id="d358c-208">Use Azure Point-In-Time restore to rerun tests in non-Tier 1 environments.</span></span>
- <span data-ttu-id="d358c-209">Embora você possa usar as funções **RANDOM** e **NOW** do Excel para gerar uma combinação exclusiva, o esforço é consideravelmente alto.</span><span class="sxs-lookup"><span data-stu-id="d358c-209">Although you can use the **RANDOM** and **NOW** Excel functions to generate a unique combination, the effort is considerably high.</span></span> <span data-ttu-id="d358c-210">Veja aqui um exemplo.</span><span class="sxs-lookup"><span data-stu-id="d358c-210">Here is an example.</span></span>

    ```Excel
    product = "AT" &TEXT(NOW(),"yyymmddhhmm")
    ```

### <a name="task-recorder"></a><span data-ttu-id="d358c-211">Gravador de Tarefas</span><span class="sxs-lookup"><span data-stu-id="d358c-211">Task recorder</span></span>

- <span data-ttu-id="d358c-212">Definir cenários antes de iniciar a gravação.</span><span class="sxs-lookup"><span data-stu-id="d358c-212">Define scenarios before you start recording.</span></span> <span data-ttu-id="d358c-213">Um projeto bem gerenciado tem cenários de teste predefinidos.</span><span class="sxs-lookup"><span data-stu-id="d358c-213">A well-managed project has predefined test scenarios.</span></span> <span data-ttu-id="d358c-214">Para criar um caso de teste, considere como é previsível o resultado desses cenários de teste.</span><span class="sxs-lookup"><span data-stu-id="d358c-214">To build a test case, consider how predictable the outcome of those test scenarios is.</span></span>
- <span data-ttu-id="d358c-215">Divida as gravações, se forem executadas por diferentes funções, ou se houver tempo de espera ou um evento externo antes da próxima etapa.</span><span class="sxs-lookup"><span data-stu-id="d358c-215">Split recordings if they are performed by different roles, or if there is waiting time or an external event before the next step.</span></span>
- <span data-ttu-id="d358c-216">Evite selecionar valores nas listas.</span><span class="sxs-lookup"><span data-stu-id="d358c-216">Avoid selecting values in lists.</span></span> <span data-ttu-id="d358c-217">Em vez disso, use formatos de texto, como **PEPS**, **AudioRM** e **SiteWH**.</span><span class="sxs-lookup"><span data-stu-id="d358c-217">Instead, use text formats, such as **FIFO**, **AudioRM**, and **SiteWH**.</span></span> <span data-ttu-id="d358c-218">Quando você seleciona em uma lista, a posição do valor na lista é registrada, não o valor em si.</span><span class="sxs-lookup"><span data-stu-id="d358c-218">When you select in a list, the position of the value in the list is recorded, not the value itself.</span></span> <span data-ttu-id="d358c-219">Se itens forem adicionados a essa lista, a posição do valor pode mudar.</span><span class="sxs-lookup"><span data-stu-id="d358c-219">If items are added to that list, the position of the value can change.</span></span> <span data-ttu-id="d358c-220">Portanto, sua gravação usará um parâmetro diferente e o restante de cenário poderá ser afetado.</span><span class="sxs-lookup"><span data-stu-id="d358c-220">Therefore, your recording will use a different parameter, and the rest of the scenario might be affected.</span></span>
- <span data-ttu-id="d358c-221">Pense sobre o comportamento de vários usuários.</span><span class="sxs-lookup"><span data-stu-id="d358c-221">Think about multi-user behavior.</span></span> <span data-ttu-id="d358c-222">Por exemplo, não presuma que sua ordem de venda recém-criada será sempre selecionada automaticamente.</span><span class="sxs-lookup"><span data-stu-id="d358c-222">For example, don't assume that your newly created sales order will always be automatically selected.</span></span> <span data-ttu-id="d358c-223">Em vez disso, sempre use o filtro para localizar a ordem correta.</span><span class="sxs-lookup"><span data-stu-id="d358c-223">Instead, always use the filter to find the correct order.</span></span>
- <span data-ttu-id="d358c-224">Use a função Copiar no gravador de tarefas para salvar o nome de um produto recém-criado, de forma que ele possa ser usado em casos de teste encadeados.</span><span class="sxs-lookup"><span data-stu-id="d358c-224">Use the Copy function in Task recorder to save the name of a newly created product so it can be used in chained test cases.</span></span>
- <span data-ttu-id="d358c-225">Use a função Validar no gravador de tarefas para definir pontos de verificação que detectam se as etapas foram executadas corretamente.</span><span class="sxs-lookup"><span data-stu-id="d358c-225">Use the Validate function in Task recorder to set checkpoints that verify that steps have been run correctly.</span></span>

### <a name="rsat"></a><span data-ttu-id="d358c-226">RSAT</span><span class="sxs-lookup"><span data-stu-id="d358c-226">RSAT</span></span>

- <span data-ttu-id="d358c-227">Para executar o teste em outra empresa, você pode alterar a empresa na guia **Geral** do arquivo de parâmetro do Excel.</span><span class="sxs-lookup"><span data-stu-id="d358c-227">To run the test in another company, you can change the company on the **General** tab of the Excel parameter file.</span></span> <span data-ttu-id="d358c-228">Verifique se as configurações e os dados estão disponíveis na empresa selecionada recentemente.</span><span class="sxs-lookup"><span data-stu-id="d358c-228">Make sure that settings and data are available in the newly selected company.</span></span>
- <span data-ttu-id="d358c-229">Você pode alterar o usuário do teste na guia **Geral** do arquivo de parâmetros do Excel.</span><span class="sxs-lookup"><span data-stu-id="d358c-229">You can change the test user on the **General** tab of the Excel parameter file.</span></span> <span data-ttu-id="d358c-230">Especifique a ID de email do usuário que executará o caso de teste.</span><span class="sxs-lookup"><span data-stu-id="d358c-230">Specify the email ID of the user who will run the test case.</span></span> <span data-ttu-id="d358c-231">Dessa forma, o caso de teste pode ser executado usando as permissões de segurança do usuário especificado.</span><span class="sxs-lookup"><span data-stu-id="d358c-231">In this way, the test case can be run by using the security permissions of the specified user.</span></span>
- <span data-ttu-id="d358c-232">Para aguardar antes de iniciar o teste, você pode definir uma pausa na guia **Geral** do arquivo de parâmetros do Excel.</span><span class="sxs-lookup"><span data-stu-id="d358c-232">To wait before the test is started, you can define a pause on the **General** tab of the Excel parameter file.</span></span> <span data-ttu-id="d358c-233">Esta pausa pode ser usada em um trabalho em lotes (por exemplo, se um fluxo de trabalho tiver que ser executado antes da próxima etapa ser executada).</span><span class="sxs-lookup"><span data-stu-id="d358c-233">This pause can be used in a batch job (for example, if a workflow must be run before the next step can be performed.)</span></span>

## <a name="advanced-scripting"></a><span data-ttu-id="d358c-234">Script avançado</span><span class="sxs-lookup"><span data-stu-id="d358c-234">Advanced scripting</span></span>

### <a name="cli"></a><span data-ttu-id="d358c-235">CLI</span><span class="sxs-lookup"><span data-stu-id="d358c-235">CLI</span></span>

<span data-ttu-id="d358c-236">O RSAT pode ser chamado de uma janela do **Prompt de Comando** ou **PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="d358c-236">RSAT can be called from a **Command Prompt** or **PowerShell** window.</span></span>

> [!NOTE]
> <span data-ttu-id="d358c-237">Verifique se a variável de ambiente **TestRoot** está definida para o caminho de instalação de RSAT.</span><span class="sxs-lookup"><span data-stu-id="d358c-237">Verify that the **TestRoot** environment variable is set to the RSAT installation path.</span></span> <span data-ttu-id="d358c-238">(No Microsoft Windows, abra **Painel de Controle**, selecione **Sistema e segurança \> Sistema \> Configurações avançadas do sistema**, e **Variáveis de Ambiente**).</span><span class="sxs-lookup"><span data-stu-id="d358c-238">(In Microsoft Windows, open **Control Panel**, select **System and Security \> System \> Advanced system settings**, and then select **Environment Variables**.)</span></span>

1. <span data-ttu-id="d358c-239">Abra uma janela do **Prompt de Comando** ou **PowerShell** como um administrador.</span><span class="sxs-lookup"><span data-stu-id="d358c-239">Open a **Command Prompt** or **PowerShell** window as an admin.</span></span>
2. <span data-ttu-id="d358c-240">Navegue até o diretório de instalação do RSAT.</span><span class="sxs-lookup"><span data-stu-id="d358c-240">Navigate to the RSAT installation directory.</span></span>

    ```Console
    cd "c:\Program Files (x86)\Regression Suite Automation Tool\"
    ```

3. <span data-ttu-id="d358c-241">Liste todos os comandos.</span><span class="sxs-lookup"><span data-stu-id="d358c-241">List all commands.</span></span>

    ```Console
    C:\Program Files (x86)\Regression Suite Automation Tool>Microsoft.Dynamics.RegressionSuite.ConsoleApp.exe help

    Usage:
        Microsoft.Dynamics.RegressionSuite.ConsoleApp.exe command
        or
        Microsoft.Dynamics.RegressionSuite.ConsoleApp.exe /settings "C:\Path to\file.settings" command

    Available commands:
        ?
        about
        cls
        download
        edit
        generate
        generatederived
        generatetestonly
        generatetestsuite
        help
        list
        listtestplans
        listtestsuite
        listtestsuitenames
        playback
        playbackbyid
        playbackmany
        playbacksuite
        quit
        upload
        uploadrecording
        usage
    ```

#### <a name=""></a><span data-ttu-id="d358c-242">?</span><span class="sxs-lookup"><span data-stu-id="d358c-242">?</span></span> 
<span data-ttu-id="d358c-243">Mostra a ajuda sobre todos os comandos disponíveis e seus parâmetros.</span><span class="sxs-lookup"><span data-stu-id="d358c-243">Shows help about all available commands and their parameters.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``?``**``[command]``

##### <a name="optional-parameters"></a><span data-ttu-id="d358c-244">Parâmetros opcionais</span><span class="sxs-lookup"><span data-stu-id="d358c-244">Optional parameters</span></span>

**``command``**


<span data-ttu-id="d358c-245">Onde ``[command]`` é um dos comandos especificados abaixo.</span><span class="sxs-lookup"><span data-stu-id="d358c-245">Where ``[command]`` is one of the commands specified below.</span></span>


#### <a name="about"></a><span data-ttu-id="d358c-246">sobre</span><span class="sxs-lookup"><span data-stu-id="d358c-246">about</span></span>
<span data-ttu-id="d358c-247">Exibe a versão atual.</span><span class="sxs-lookup"><span data-stu-id="d358c-247">Displays the current version.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``about``**

#### <a name="cls"></a><span data-ttu-id="d358c-248">cls</span><span class="sxs-lookup"><span data-stu-id="d358c-248">cls</span></span>
<span data-ttu-id="d358c-249">Limpa a tela.</span><span class="sxs-lookup"><span data-stu-id="d358c-249">Clears the screen.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``cls``**


#### <a name="download"></a><span data-ttu-id="d358c-250">fazer download</span><span class="sxs-lookup"><span data-stu-id="d358c-250">download</span></span>
<span data-ttu-id="d358c-251">Baixa anexos para o caso de teste especificado no diretório de saída.</span><span class="sxs-lookup"><span data-stu-id="d358c-251">Downloads attachments for the specified test case to the output directory.</span></span> <span data-ttu-id="d358c-252">Você pode usar o comando ``list`` para obter todos os casos de teste disponíveis.</span><span class="sxs-lookup"><span data-stu-id="d358c-252">You can use the ``list`` command to get all available test cases.</span></span> <span data-ttu-id="d358c-253">Use qualquer valor da primeira coluna como um parâmetro **test_case_id**.</span><span class="sxs-lookup"><span data-stu-id="d358c-253">Use any value from the first column as a **test_case_id** parameter.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``download``**``[test_case_id] [output_dir]``

##### <a name="required-parameters"></a><span data-ttu-id="d358c-254">Parâmetros obrigatórios</span><span class="sxs-lookup"><span data-stu-id="d358c-254">Required parameters</span></span>
<span data-ttu-id="d358c-255">**``test_case_id``** Representa a ID do caso de teste.</span><span class="sxs-lookup"><span data-stu-id="d358c-255">**``test_case_id``** Represents the test case ID.</span></span>  
<span data-ttu-id="d358c-256">**``output_dir``** Representa o diretório de saída.</span><span class="sxs-lookup"><span data-stu-id="d358c-256">**``output_dir``** Represents the output directory.</span></span> <span data-ttu-id="d358c-257">O diretório deve existir.</span><span class="sxs-lookup"><span data-stu-id="d358c-257">The directory must exist.</span></span>

##### <a name="examples"></a><span data-ttu-id="d358c-258">Exemplos</span><span class="sxs-lookup"><span data-stu-id="d358c-258">Examples</span></span>

``download 123 c:\temp\rsat``   
``download 765 c:\rsat\last``


#### <a name="edit"></a><span data-ttu-id="d358c-259">editar</span><span class="sxs-lookup"><span data-stu-id="d358c-259">edit</span></span>
<span data-ttu-id="d358c-260">Permite abrir o arquivo de parâmetros no programa Excel e editá-lo.</span><span class="sxs-lookup"><span data-stu-id="d358c-260">Allows you to open parameters file in Excel program and edit it.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``edit``**``[excel_file]``

##### <a name="required-parameters"></a><span data-ttu-id="d358c-261">Parâmetros obrigatórios</span><span class="sxs-lookup"><span data-stu-id="d358c-261">Required parameters</span></span>
<span data-ttu-id="d358c-262">**``excel_file``** Deve conter um caminho completo para um arquivo existente do Excel.</span><span class="sxs-lookup"><span data-stu-id="d358c-262">**``excel_file``** Must contain a full path to an existing Excel file.</span></span>

##### <a name="examples"></a><span data-ttu-id="d358c-263">Exemplos</span><span class="sxs-lookup"><span data-stu-id="d358c-263">Examples</span></span>
``edit c:\RSAT\TestCase_123_Base.xlsx``  
``edit e:\temp\TestCase_456_Base.xlsx``


#### <a name="generate"></a><span data-ttu-id="d358c-264">gerar</span><span class="sxs-lookup"><span data-stu-id="d358c-264">generate</span></span>
<span data-ttu-id="d358c-265">Gera arquivos de execução e parâmetro de teste para o caso de teste especificado no diretório de saída.</span><span class="sxs-lookup"><span data-stu-id="d358c-265">Generates test execution and parameter files for the specified test case in the output directory.</span></span>
<span data-ttu-id="d358c-266">Você pode usar o comando ``list`` para obter todos os casos de teste disponíveis.</span><span class="sxs-lookup"><span data-stu-id="d358c-266">You can use the ``list`` command to get all available test cases.</span></span> <span data-ttu-id="d358c-267">Use qualquer valor da primeira coluna como um parâmetro **test_case_id**.</span><span class="sxs-lookup"><span data-stu-id="d358c-267">Use any value from the first column as a **test_case_id** parameter.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``generate``**``[test_case_id] [output_dir]``

##### <a name="required-parameters"></a><span data-ttu-id="d358c-268">Parâmetros obrigatórios</span><span class="sxs-lookup"><span data-stu-id="d358c-268">Required parameters</span></span>
<span data-ttu-id="d358c-269">**``test_case_id``** Representa a ID do caso de teste.</span><span class="sxs-lookup"><span data-stu-id="d358c-269">**``test_case_id``** Represents the test case ID.</span></span>  
<span data-ttu-id="d358c-270">**``output_dir``** Representa o diretório de saída.</span><span class="sxs-lookup"><span data-stu-id="d358c-270">**``output_dir``** Represents the output directory.</span></span> <span data-ttu-id="d358c-271">O diretório deve existir.</span><span class="sxs-lookup"><span data-stu-id="d358c-271">The directory must exist.</span></span>

##### <a name="examples"></a><span data-ttu-id="d358c-272">Exemplos</span><span class="sxs-lookup"><span data-stu-id="d358c-272">Examples</span></span>
``generate 123 c:\temp\rsat``  
``generate 765 c:\rsat\last``


#### <a name="generatederived"></a><span data-ttu-id="d358c-273">generatederived</span><span class="sxs-lookup"><span data-stu-id="d358c-273">generatederived</span></span>
<span data-ttu-id="d358c-274">Gera um novo caso de teste, derivado do caso de teste fornecido.</span><span class="sxs-lookup"><span data-stu-id="d358c-274">Generates a new test case, derived from the provided test case.</span></span> <span data-ttu-id="d358c-275">Você pode usar o comando ``list`` para obter todos os casos de teste disponíveis.</span><span class="sxs-lookup"><span data-stu-id="d358c-275">You can use the ``list`` command to get all available test cases.</span></span> <span data-ttu-id="d358c-276">Use qualquer valor da primeira coluna como um parâmetro **test_case_id**.</span><span class="sxs-lookup"><span data-stu-id="d358c-276">Use any value from the first column as a **test_case_id** parameter.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``generatederived``**``[parent_test_case_id] [test_plan_id] [test_suite_id]``

##### <a name="required-parameters"></a><span data-ttu-id="d358c-277">Parâmetros obrigatórios</span><span class="sxs-lookup"><span data-stu-id="d358c-277">Required parameters</span></span>
<span data-ttu-id="d358c-278">**``parent_test_case_id``** Representa a ID do caso de teste pai.</span><span class="sxs-lookup"><span data-stu-id="d358c-278">**``parent_test_case_id``** Represents the parent test case ID.</span></span>  
<span data-ttu-id="d358c-279">**``test_plan_id``** Representa a ID do plano de teste.</span><span class="sxs-lookup"><span data-stu-id="d358c-279">**``test_plan_id``** Represents the test plan ID.</span></span>  
<span data-ttu-id="d358c-280">**``test_suite_id``** Representa a ID do pacote de teste.</span><span class="sxs-lookup"><span data-stu-id="d358c-280">**``test_suite_id``** Represents the test suite ID.</span></span>

##### <a name="examples"></a><span data-ttu-id="d358c-281">Exemplos</span><span class="sxs-lookup"><span data-stu-id="d358c-281">Examples</span></span>
``generatederived 123 8901 678``


#### <a name="generatetestonly"></a><span data-ttu-id="d358c-282">generatetestonly</span><span class="sxs-lookup"><span data-stu-id="d358c-282">generatetestonly</span></span>
<span data-ttu-id="d358c-283">Gera somente o arquivo de execução de teste para o caso de teste especificado no diretório de saída.</span><span class="sxs-lookup"><span data-stu-id="d358c-283">Generates only test execution file for the specified test case in the output directory.</span></span> <span data-ttu-id="d358c-284">Você pode usar o comando ``list`` para obter todos os casos de teste disponíveis.</span><span class="sxs-lookup"><span data-stu-id="d358c-284">You can use the ``list`` command to get all available test cases.</span></span> <span data-ttu-id="d358c-285">Use qualquer valor da primeira coluna como um parâmetro **test_case_id**.</span><span class="sxs-lookup"><span data-stu-id="d358c-285">Use any value from the first column as a **test_case_id** parameter.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``generatetestonly``**``[test_case_id] [output_dir]``

##### <a name="required-parameters"></a><span data-ttu-id="d358c-286">Parâmetros obrigatórios</span><span class="sxs-lookup"><span data-stu-id="d358c-286">Required parameters</span></span>
<span data-ttu-id="d358c-287">**``test_case_id``** Representa a ID do caso de teste.</span><span class="sxs-lookup"><span data-stu-id="d358c-287">**``test_case_id``** Represents the test case ID.</span></span>  
<span data-ttu-id="d358c-288">**``output_dir``** Representa o diretório de saída.</span><span class="sxs-lookup"><span data-stu-id="d358c-288">**``output_dir``** Represents the output directory.</span></span> <span data-ttu-id="d358c-289">O diretório deve existir.</span><span class="sxs-lookup"><span data-stu-id="d358c-289">The directory must exist.</span></span>

##### <a name="examples"></a><span data-ttu-id="d358c-290">Exemplos</span><span class="sxs-lookup"><span data-stu-id="d358c-290">Examples</span></span>
``generatetestonly 123 c:\temp\rsat``  
``generatetestonly 765 c:\rsat\last``


#### <a name="generatetestsuite"></a><span data-ttu-id="d358c-291">generatetestsuite</span><span class="sxs-lookup"><span data-stu-id="d358c-291">generatetestsuite</span></span>
<span data-ttu-id="d358c-292">Gera todos os casos de teste para o conjunto especificado no diretório de saída.</span><span class="sxs-lookup"><span data-stu-id="d358c-292">Generates all test cases for the specified suite in the output directory.</span></span>
<span data-ttu-id="d358c-293">Você pode usar o comando ``listtestsuitenames`` para obter todos os pacotes de teste disponíveis.</span><span class="sxs-lookup"><span data-stu-id="d358c-293">You can use ``listtestsuitenames`` command to get all available test suits.</span></span> <span data-ttu-id="d358c-294">Use qualquer valor da coluna como um parâmetro **test_suite_name**.</span><span class="sxs-lookup"><span data-stu-id="d358c-294">Use any value from the column as a **test_suite_name** parameter.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``generatetestsuite``**``[test_suite_name] [output_dir]``

##### <a name="required-parameters"></a><span data-ttu-id="d358c-295">Parâmetros obrigatórios</span><span class="sxs-lookup"><span data-stu-id="d358c-295">Required parameters</span></span>
<span data-ttu-id="d358c-296">**``test_suite_name``** Representa o nome do pacote de teste.</span><span class="sxs-lookup"><span data-stu-id="d358c-296">**``test_suite_name``** Represents the test suite name.</span></span>  
<span data-ttu-id="d358c-297">**``output_dir``** Representa o diretório de saída.</span><span class="sxs-lookup"><span data-stu-id="d358c-297">**``output_dir``** Represents the output directory.</span></span> <span data-ttu-id="d358c-298">O diretório deve existir.</span><span class="sxs-lookup"><span data-stu-id="d358c-298">The directory must exist.</span></span>

##### <a name="examples"></a><span data-ttu-id="d358c-299">Exemplos</span><span class="sxs-lookup"><span data-stu-id="d358c-299">Examples</span></span>
``generatetestsuite Tests c:\temp\rsat``   
``generatetestsuite Purchase c:\rsat\last``


#### <a name="help"></a><span data-ttu-id="d358c-300">ajuda</span><span class="sxs-lookup"><span data-stu-id="d358c-300">help</span></span>
<span data-ttu-id="d358c-301">Idêntico ao [?](####?)</span><span class="sxs-lookup"><span data-stu-id="d358c-301">Identical to the [?](####?)</span></span> <span data-ttu-id="d358c-302">comando</span><span class="sxs-lookup"><span data-stu-id="d358c-302">command</span></span>


#### <a name="list"></a><span data-ttu-id="d358c-303">lista</span><span class="sxs-lookup"><span data-stu-id="d358c-303">list</span></span>
<span data-ttu-id="d358c-304">Lista todos os casos de teste disponíveis.</span><span class="sxs-lookup"><span data-stu-id="d358c-304">Lists all available test cases.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``list``**


#### <a name="listtestplans"></a><span data-ttu-id="d358c-305">listtestplans</span><span class="sxs-lookup"><span data-stu-id="d358c-305">listtestplans</span></span>
<span data-ttu-id="d358c-306">Lista todos os planos de teste disponíveis.</span><span class="sxs-lookup"><span data-stu-id="d358c-306">Lists all available test plans.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``listtestplans``**


#### <a name="listtestsuite"></a><span data-ttu-id="d358c-307">listtestsuite</span><span class="sxs-lookup"><span data-stu-id="d358c-307">listtestsuite</span></span>
<span data-ttu-id="d358c-308">Lista casos de teste para o pacote de teste especificado.</span><span class="sxs-lookup"><span data-stu-id="d358c-308">Lists test cases for the specified test suite.</span></span> <span data-ttu-id="d358c-309">Você pode usar o comando ``listtestsuitenames`` para obter todos os pacotes de teste disponíveis.</span><span class="sxs-lookup"><span data-stu-id="d358c-309">You can use ``listtestsuitenames`` command to get all available test suites.</span></span> <span data-ttu-id="d358c-310">Use qualquer valor da primeira coluna como parâmetro **suite_name**.</span><span class="sxs-lookup"><span data-stu-id="d358c-310">Use any value from first column as **suite_name** parameter.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``listtestsuite``**``[suite_name]``

##### <a name="required-parameters"></a><span data-ttu-id="d358c-311">Parâmetros obrigatórios</span><span class="sxs-lookup"><span data-stu-id="d358c-311">Required parameters</span></span>
<span data-ttu-id="d358c-312">**``suite_name``** Nome do pacote desejado.</span><span class="sxs-lookup"><span data-stu-id="d358c-312">**``suite_name``** Name of the desired suite.</span></span>

##### <a name="examples"></a><span data-ttu-id="d358c-313">Exemplos</span><span class="sxs-lookup"><span data-stu-id="d358c-313">Examples</span></span>
``listtestsuite "sample suite name"``  
``listtestsuite NameOfTheSuite``


#### <a name="listtestsuitenames"></a><span data-ttu-id="d358c-314">listtestsuitenames</span><span class="sxs-lookup"><span data-stu-id="d358c-314">listtestsuitenames</span></span>
<span data-ttu-id="d358c-315">Lista todos os pacotes de teste disponíveis.</span><span class="sxs-lookup"><span data-stu-id="d358c-315">Lists all available test suites.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``listtestsuitenames``**


#### <a name="playback"></a><span data-ttu-id="d358c-316">reprodução</span><span class="sxs-lookup"><span data-stu-id="d358c-316">playback</span></span>
<span data-ttu-id="d358c-317">Reproduz um caso de teste usando um arquivo do Excel.</span><span class="sxs-lookup"><span data-stu-id="d358c-317">Plays back a test case using an Excel file.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``playback``**``[excel_file]``

##### <a name="required-parameters"></a><span data-ttu-id="d358c-318">Parâmetros obrigatórios</span><span class="sxs-lookup"><span data-stu-id="d358c-318">Required parameters</span></span>
<span data-ttu-id="d358c-319">**``excel_file``** Um caminho completo para o arquivo do Excel.</span><span class="sxs-lookup"><span data-stu-id="d358c-319">**``excel_file``** A full path to the Excel file.</span></span> <span data-ttu-id="d358c-320">O arquivo deve existir.</span><span class="sxs-lookup"><span data-stu-id="d358c-320">File must exist.</span></span> 

##### <a name="examples"></a><span data-ttu-id="d358c-321">Exemplos</span><span class="sxs-lookup"><span data-stu-id="d358c-321">Examples</span></span>
``
playback c:\RSAT\TestCaseParameters\sample1.xlsx
playback e:\temp\test.xlsx
``


#### <a name="playbackbyid"></a><span data-ttu-id="d358c-322">playbackbyid</span><span class="sxs-lookup"><span data-stu-id="d358c-322">playbackbyid</span></span>
<span data-ttu-id="d358c-323">Reproduz vários casos de teste de uma só vez.</span><span class="sxs-lookup"><span data-stu-id="d358c-323">Plays back multiple test cases at once.</span></span>
<span data-ttu-id="d358c-324">Você pode usar o comando ``list`` para obter todos os casos de teste disponíveis.</span><span class="sxs-lookup"><span data-stu-id="d358c-324">You can use the ``list`` command to get all available test cases.</span></span> <span data-ttu-id="d358c-325">Use qualquer valor da primeira coluna como um parâmetro **test_case_id**.</span><span class="sxs-lookup"><span data-stu-id="d358c-325">Use any value from the first column as a **test_case_id** parameter.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``playbackbyid``**``[test_case_id1] [test_case_id2] ... [test_case_idN]``

##### <a name="required-parameters"></a><span data-ttu-id="d358c-326">Parâmetros obrigatórios</span><span class="sxs-lookup"><span data-stu-id="d358c-326">Required parameters</span></span>
<span data-ttu-id="d358c-327">**``test_case_id1``** ID do caso de teste existente.</span><span class="sxs-lookup"><span data-stu-id="d358c-327">**``test_case_id1``** ID of exisiting test case.</span></span>  
<span data-ttu-id="d358c-328">**``test_case_id2``** ID do caso de teste existente.</span><span class="sxs-lookup"><span data-stu-id="d358c-328">**``test_case_id2``** ID of exisiting test case.</span></span>  
<span data-ttu-id="d358c-329">**``test_case_idN``** ID do caso de teste existente.</span><span class="sxs-lookup"><span data-stu-id="d358c-329">**``test_case_idN``** ID of exisiting test case.</span></span>  

##### <a name="examples"></a><span data-ttu-id="d358c-330">Exemplos</span><span class="sxs-lookup"><span data-stu-id="d358c-330">Examples</span></span>
``playbackbyid 878``  
``playbackbyid 2345 667 135``


#### <a name="playbackmany"></a><span data-ttu-id="d358c-331">playbackmany</span><span class="sxs-lookup"><span data-stu-id="d358c-331">playbackmany</span></span>
<span data-ttu-id="d358c-332">Reproduz muitos casos de teste de uma só vez, usando arquivos do Excel.</span><span class="sxs-lookup"><span data-stu-id="d358c-332">Plays back many test cases at once, using Excel files.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``playbackmany``**``[excel_file1] [excel_file2] ... [excel_fileN]``

##### <a name="required-parameters"></a><span data-ttu-id="d358c-333">Parâmetros obrigatórios</span><span class="sxs-lookup"><span data-stu-id="d358c-333">Required parameters</span></span>
<span data-ttu-id="d358c-334">**``excel_file1``** Caminho completo para o arquivo do Excel.</span><span class="sxs-lookup"><span data-stu-id="d358c-334">**``excel_file1``** Full path to the Excel file.</span></span> <span data-ttu-id="d358c-335">O arquivo deve existir.</span><span class="sxs-lookup"><span data-stu-id="d358c-335">File must exist.</span></span>  
<span data-ttu-id="d358c-336">**``excel_file2``** Caminho completo para o arquivo do Excel.</span><span class="sxs-lookup"><span data-stu-id="d358c-336">**``excel_file2``** Full path to the Excel file.</span></span> <span data-ttu-id="d358c-337">O arquivo deve existir.</span><span class="sxs-lookup"><span data-stu-id="d358c-337">File must exist.</span></span>  
<span data-ttu-id="d358c-338">**``excel_fileN``** Caminho completo para o arquivo do Excel.</span><span class="sxs-lookup"><span data-stu-id="d358c-338">**``excel_fileN``** Full path to the Excel file.</span></span> <span data-ttu-id="d358c-339">O arquivo deve existir.</span><span class="sxs-lookup"><span data-stu-id="d358c-339">File must exist.</span></span>  

##### <a name="examples"></a><span data-ttu-id="d358c-340">Exemplos</span><span class="sxs-lookup"><span data-stu-id="d358c-340">Examples</span></span>
``playbackmany c:\RSAT\TestCaseParameters\param1.xlsx``  
``playbackmany e:\temp\test.xlsx f:\rsat\sample1.xlsx c:\RSAT\sample2.xlsx``


#### <a name="playbacksuite"></a><span data-ttu-id="d358c-341">playbacksuite</span><span class="sxs-lookup"><span data-stu-id="d358c-341">playbacksuite</span></span>
<span data-ttu-id="d358c-342">Reproduz todos os casos de teste do pacote de teste especificado.</span><span class="sxs-lookup"><span data-stu-id="d358c-342">Plays back all test cases from the specified test suite.</span></span> <span data-ttu-id="d358c-343">Você pode usar o comando ``listtestsuitenames`` para obter todos os pacotes de teste disponíveis.</span><span class="sxs-lookup"><span data-stu-id="d358c-343">You can use ``listtestsuitenames`` command to get all available test suites.</span></span> <span data-ttu-id="d358c-344">Use qualquer valor da primeira coluna como parâmetro **suite_name**.</span><span class="sxs-lookup"><span data-stu-id="d358c-344">Use any value from first column as **suite_name** parameter.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``playbacksuite``**``[suite_name]``

##### <a name="required-parameters"></a><span data-ttu-id="d358c-345">Parâmetros obrigatórios</span><span class="sxs-lookup"><span data-stu-id="d358c-345">Required parameters</span></span>
<span data-ttu-id="d358c-346">**``suite_name``** Nome do pacote desejado.</span><span class="sxs-lookup"><span data-stu-id="d358c-346">**``suite_name``** Name of the desired suite.</span></span>

##### <a name="examples"></a><span data-ttu-id="d358c-347">Exemplos</span><span class="sxs-lookup"><span data-stu-id="d358c-347">Examples</span></span>
``playbacksuite suiteName``  
``playbacksuite sample_suite``


#### <a name="quit"></a><span data-ttu-id="d358c-348">encerrar</span><span class="sxs-lookup"><span data-stu-id="d358c-348">quit</span></span>
<span data-ttu-id="d358c-349">Fecha o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="d358c-349">Closes the  application.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``quit``**


#### <a name="upload"></a><span data-ttu-id="d358c-350">carregar</span><span class="sxs-lookup"><span data-stu-id="d358c-350">upload</span></span>
<span data-ttu-id="d358c-351">Carrega todos os arquivos pertencentes ao pacote de teste ou casos de teste especificados.</span><span class="sxs-lookup"><span data-stu-id="d358c-351">Uploads all files belonging to the specified test suite or test cases.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``upload``**``[suite_name] [testcase_id]``

#### <a name="required-parameters"></a><span data-ttu-id="d358c-352">Parâmetros obrigatórios</span><span class="sxs-lookup"><span data-stu-id="d358c-352">Required parameters</span></span>
<span data-ttu-id="d358c-353">**``suite_name``** Todos os arquivos pertencentes ao pacote de teste especificado serão carregados.</span><span class="sxs-lookup"><span data-stu-id="d358c-353">**``suite_name``** All files belonging to the specified test suite will be uploaded.</span></span>
<span data-ttu-id="d358c-354">**``testcase_id``** Todos os arquivos pertencentes aos casos de teste especificados serão carregados.</span><span class="sxs-lookup"><span data-stu-id="d358c-354">**``testcase_id``** All files beloning to the specified test case(s) will be uploaded.</span></span>

##### <a name="examples"></a><span data-ttu-id="d358c-355">Exemplos</span><span class="sxs-lookup"><span data-stu-id="d358c-355">Examples</span></span>
``upload sample_suite``  
``upload 123``  
``upload 123 456``


#### <a name="uploadrecording"></a><span data-ttu-id="d358c-356">uploadrecording</span><span class="sxs-lookup"><span data-stu-id="d358c-356">uploadrecording</span></span>
<span data-ttu-id="d358c-357">Carrega apenas o arquivo de gravação pertencente aos casos de teste especificados.</span><span class="sxs-lookup"><span data-stu-id="d358c-357">Uploads only recording file belonging to the specified test cases.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``uploadrecording``**``[testcase_id]``

##### <a name="required-parameters"></a><span data-ttu-id="d358c-358">Parâmetros obrigatórios</span><span class="sxs-lookup"><span data-stu-id="d358c-358">Required parameters</span></span>
<span data-ttu-id="d358c-359">**``testcase_id``** O arquivo de gravação pertencente aos casos de teste especificados será carregado.</span><span class="sxs-lookup"><span data-stu-id="d358c-359">**``testcase_id``** Recording file belonging to the specified test cases will be uploaded.</span></span>

##### <a name="examples"></a><span data-ttu-id="d358c-360">Exemplos</span><span class="sxs-lookup"><span data-stu-id="d358c-360">Examples</span></span>
``uploadrecording 123``  
``uploadrecording 123 456``


#### <a name="usage"></a><span data-ttu-id="d358c-361">uso</span><span class="sxs-lookup"><span data-stu-id="d358c-361">usage</span></span>
<span data-ttu-id="d358c-362">Mostra duas maneiras de chamar esse aplicativo: uma usando um arquivo de configuração padrão, outra fornecendo um arquivo de configuração.</span><span class="sxs-lookup"><span data-stu-id="d358c-362">Shows two ways to invoke this application: one using a default setting file, another one providing a setting file.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``usage``**


### <a name="windows-powershell-examples"></a><span data-ttu-id="d358c-363">Exemplos de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d358c-363">Windows PowerShell examples</span></span>

#### <a name="run-a-test-case-in-a-loop"></a><span data-ttu-id="d358c-364">Executar um caso de teste em um loop</span><span class="sxs-lookup"><span data-stu-id="d358c-364">Run a test case in a loop</span></span>

<span data-ttu-id="d358c-365">Você tem um script de teste que cria um novo cliente.</span><span class="sxs-lookup"><span data-stu-id="d358c-365">You have a test script that creates a new customer.</span></span> <span data-ttu-id="d358c-366">Através do script, este caso de teste pode ser executado em um loop, randomizando os seguintes dados antes de cada iteração ser executada:</span><span class="sxs-lookup"><span data-stu-id="d358c-366">Via scripting, this test case can be run in a loop by randomizing the following data before each iteration is run:</span></span>

- <span data-ttu-id="d358c-367">ID do cliente</span><span class="sxs-lookup"><span data-stu-id="d358c-367">Customer ID</span></span>
- <span data-ttu-id="d358c-368">Nome do Cliente</span><span class="sxs-lookup"><span data-stu-id="d358c-368">Customer name</span></span>
- <span data-ttu-id="d358c-369">Endereço do cliente</span><span class="sxs-lookup"><span data-stu-id="d358c-369">Customer address</span></span>

<span data-ttu-id="d358c-370">O ID do cliente ficará no formato *ATCUS\<number\>*, onde \<number\> é um valor entre **000000001** e **999999999**.</span><span class="sxs-lookup"><span data-stu-id="d358c-370">The customer ID will be in the format *ATCUS\<number\>*, where \<number\> is a value between **000000001** and **999999999**.</span></span>

<span data-ttu-id="d358c-371">O seguinte exemplo usa um parâmetro, **iniciar**, para definir o primeiro número usado.</span><span class="sxs-lookup"><span data-stu-id="d358c-371">The following example uses one parameter, **start**, to define the first number that is used.</span></span> <span data-ttu-id="d358c-372">Usa um segundo parâmetro, **nr**, para definir o número de clientes que deve ser criado.</span><span class="sxs-lookup"><span data-stu-id="d358c-372">Is uses a second parameter, **nr**, to define the number of customers that must be created.</span></span> <span data-ttu-id="d358c-373">Para cada iteração, os parâmetros no arquivo de parâmetros do Excel são alterados usando uma função UpdateCustomer.</span><span class="sxs-lookup"><span data-stu-id="d358c-373">For each iteration, the parameters in the Excel parameter file are changed by using an UpdateCustomer function.</span></span> <span data-ttu-id="d358c-374">Em seguida, a linha de comandos de RSAT é chamada em uma função de RunTestCase.</span><span class="sxs-lookup"><span data-stu-id="d358c-374">Then the RSAT command line is called in a RunTestCase function.</span></span>

<span data-ttu-id="d358c-375">Abra o Ambiente de Script Integrado (ISE) do Microsoft Windows PowerShell no modo de administração e cole o seguinte código na janela que é nomeada **Untitled1.ps1**.</span><span class="sxs-lookup"><span data-stu-id="d358c-375">Open Microsoft Windows PowerShell Integrated Scripting Environment (ISE) in admin mode, and paste the following code into the window that is named **Untitled1.ps1**.</span></span>

```powershell
param ( [int]$start = 1, [int]$nr = 1 )
function UpdateCustomer
{
    param ([string]$paramFilename, [string]$sheetName, [string]$CustId)
    $xl = New-Object -COM "Excel.Application"
    $xl.Visible = $false
    $wb = $xl.Workbooks.Open($paramFilename)
    $ws = $wb.Sheets.Item($sheetName)
    $ws.Cells.Item(3, 2).Value = "ATCUS" + $CustId
    $ws.Cells.Item(4, 2).Value = "Automated Test Customer " + $CustId
    $ws.Cells.Item(8, 2).Value = "Automated Test Street " + $CustId
    $wb.Save()
    $wb.Close()
    $xl.Quit()
    [System.Runtime.Interopservices.Marshal]::ReleaseComObject($xl)
}
function RunTestCase
{
    param ( [string]$filename )
    $cmd = "cd c:\Program Files (x86)\Regression Suite Automation Tool\ &&  "
    $cmd = $cmd + "Microsoft.Dynamics.RegressionSuite.ConsoleApp.exe playback "
    $cmd = $cmd + $filename
    cmd /c $cmd
}
$excelFilename = "full path to excel file parameter file"
l$sheetName = "DirPartyQuickCreateForm"
for ($i = $start; $i -lt $start + $nr; $i++ )
{
    $CustomerId = $i.ToString("000000000")
    Write-Host "customer : " $CustomerId
    UpdateCustomer $excelFilename $sheetName $CustomerId
    RunTestCase $excelFilename
```

#### <a name="run-a-script-that-depends-on-data-in-microsoft-dynamics-365"></a><span data-ttu-id="d358c-376">Execute um script que dependa de dados no Microsoft Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="d358c-376">Run a script that depends on data in Microsoft Dynamics 365</span></span>

<span data-ttu-id="d358c-377">O exemplo a seguir usa uma chamada do Protocolo Open Data (OData) para localizar o status da ordem de uma ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="d358c-377">The following example uses an Open Data Protocol (OData) call to find the order status of a purchase order.</span></span> <span data-ttu-id="d358c-378">Se o status não for **faturado**, você pode, por exemplo, chamar um caso de teste RSAT que lança a fatura.</span><span class="sxs-lookup"><span data-stu-id="d358c-378">If the status isn't **invoiced**, you can, for example, call an RSAT test case that posts the invoice.</span></span>

```xpp
function Odata_Get
{
    Param ( [string] $environment, [string] $cmd )
    [Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12
    $tenant = "your tenant"
    $creds = @{
        grant_type = "client_credentials"
        client_id = "your client application Id"
        client_secret = "your client secret"
        resource = $environment
    }
    $headers = $null
    $bearer = Invoke-RestMethod https://login.microsoftonline.com/$tenant/oauth2/token -Method Post -Body $creds -Headers $headers;
    $headers = @{
        Authorization = "Bearer " + $bearer.access_token
    }
    $Odata_cmd = $environment + '/data/' + $cmd
    return (Invoke-RestMethod -Uri $Odata_cmd -Method Get -Headers $headers -ContentType application/json )
}
function PurchaseOrderStatus
{
    Param ( [string] $environment, [string] $purchaseOrderNumber )
    $cmd = 'PurchaseOrderHeaders?$filter=PurchaseOrderNumber eq '
    $cmd = $cmd + "'" + $purchaseOrderNumber + "'"
    $response = Odata_Get -environment $environment -cmd $cmd
    return $response.value.PurchaseOrderStatus
}
$environment = "https://your environment"
$orderStatus = PurchaseOrderStatus -environment $environment -purchaseOrderNumber '000003'
if ($orderStatus -eq $null) {   write-host 'doesn''t exist'}
elseif ($orderStatus -ne 'invoiced') { RunTestCase "PostInvoice" }
```
