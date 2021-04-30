---
title: Tutorial sobre a Regression Suite Automation Tool
description: Esse tópico mostra como usar a Regression Suite Automation Tool (RSAT). Descreve diversos recursos e oferece exemplos que usam o script avançado.
author: robinarh
ms.date: 01/15/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: rhaertle
ms.custom: 21761
ms.search.region: Global
ms.author: rhaertle
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: AX 7.0.0, Operations
ms.openlocfilehash: a194e14c76827650e6752f331081ebe0c2130a13
ms.sourcegitcommit: e4992c57eea4c15ac052e9d65dddae625e3528f9
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/07/2021
ms.locfileid: "5866147"
---
# <a name="regression-suite-automation-tool-tutorial"></a><span data-ttu-id="09a6e-104">Tutorial sobre a Regression Suite Automation Tool</span><span class="sxs-lookup"><span data-stu-id="09a6e-104">Regression suite automation tool tutorial</span></span>

[!include [banner](../../includes/banner.md)]

> [!NOTE]
> <span data-ttu-id="09a6e-105">Usa as ferramentas do navegador da internet para fazer download e salvar esta página no formato pdf.</span><span class="sxs-lookup"><span data-stu-id="09a6e-105">Use your internet browser tools to download and save this page in pdf format.</span></span>

<span data-ttu-id="09a6e-106">Este tutorial aborda alguns dos recursos avançados da Regression Suite Automation Tool (RSAT), inclui uma atribuição de demonstração e descreve a estratégia e os principais pontos de aprendizagem.</span><span class="sxs-lookup"><span data-stu-id="09a6e-106">This tutorial walks through some of the advanced features of the Regression suite automation tool (RSAT), includes a demo assignment, and describes strategy and key learning points.</span></span>

## <a name="notable-features-of-rsat-and-task-recorder"></a><span data-ttu-id="09a6e-107">Recursos notáveis do RSAT e Gravador de tarefas</span><span class="sxs-lookup"><span data-stu-id="09a6e-107">Notable Features of RSAT and Task recorder</span></span>

### <a name="validate-a-field-value"></a><span data-ttu-id="09a6e-108">Validar um valor do campo</span><span class="sxs-lookup"><span data-stu-id="09a6e-108">Validate a field value</span></span>

<span data-ttu-id="09a6e-109">O RSAT permite incluir etapas de validação no caso de teste para validar os valores esperados.</span><span class="sxs-lookup"><span data-stu-id="09a6e-109">RSAT allows you to include validation steps within your test case to validate expected values.</span></span> <span data-ttu-id="09a6e-110">Para obter informações sobre esse recurso, consulte o artigo [Validar valores esperados](rsat-validate-expected.md).</span><span class="sxs-lookup"><span data-stu-id="09a6e-110">For information about this feature, see the article [Validate expected values](rsat-validate-expected.md).</span></span>

<span data-ttu-id="09a6e-111">O exemplo a seguir mostra como é possível usar este recurso para validar se o estoque disponível é maior que 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="09a6e-111">The following example shows how you can use this feature to validate whether the on-hand inventory is more than 0 (zero).</span></span>

1. <span data-ttu-id="09a6e-112">Nos dados de demonstração da empresa **USMF**, crie uma gravação de tarefas que tenha as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="09a6e-112">In the demo data in the **USMF** company, create a task recording that has the following steps:</span></span>

    1. <span data-ttu-id="09a6e-113">Vá para **Gerenciamento de informações do produto \> Produtos \> Produtos liberados**.</span><span class="sxs-lookup"><span data-stu-id="09a6e-113">Go to **Product information management \> Products \> Released products**.</span></span>
    2. <span data-ttu-id="09a6e-114">Use o Filtro Rápido para localizar registros.</span><span class="sxs-lookup"><span data-stu-id="09a6e-114">Use the Quick Filter to find records.</span></span> <span data-ttu-id="09a6e-115">Por exemplo, filtre um valor de **1000** para o campo **Número do item**.</span><span class="sxs-lookup"><span data-stu-id="09a6e-115">For example, filter on a value of **1000** for the **Item number** field.</span></span>
    3. <span data-ttu-id="09a6e-116">Selecione **Estoque disponível**.</span><span class="sxs-lookup"><span data-stu-id="09a6e-116">Select **On-hand inventory**.</span></span>
    4. <span data-ttu-id="09a6e-117">Use o Filtro Rápido para localizar registros.</span><span class="sxs-lookup"><span data-stu-id="09a6e-117">Use the Quick Filter to find records.</span></span> <span data-ttu-id="09a6e-118">Por exemplo, filtro em um valor **1** para o campo **Local**.</span><span class="sxs-lookup"><span data-stu-id="09a6e-118">For example, filter on a value of **1** for the **Site** field.</span></span>
    5. <span data-ttu-id="09a6e-119">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="09a6e-119">In the list, mark the selected row.</span></span>
    6. <span data-ttu-id="09a6e-120">Valide se o valor do campo **Total disponível** é **411.0000000000000000**.</span><span class="sxs-lookup"><span data-stu-id="09a6e-120">Validate that the value of the **Total available** field is **411.0000000000000000**.</span></span>

2. <span data-ttu-id="09a6e-121">Salve a gravação de tarefas como uma **gravação do desenvolvedor** e anexe-a ao caso de teste no Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="09a6e-121">Save the task recording as a **developer recording** and attach it to your test case in Azure Devops.</span></span>
3. <span data-ttu-id="09a6e-122">Adicione o caso de teste ao plano de teste e carregue o caso de teste no RSAT.</span><span class="sxs-lookup"><span data-stu-id="09a6e-122">Add the test case to the test plan, and load the test case into RSAT.</span></span>
4. <span data-ttu-id="09a6e-123">Abra o arquivo de parâmetros do Excel e vá para a guia **TestCaseSteps**.</span><span class="sxs-lookup"><span data-stu-id="09a6e-123">Open the Excel parameter file and go to the **TestCaseSteps** tab.</span></span>
5. <span data-ttu-id="09a6e-124">Para validar se o estoque disponível sempre será maior do que **0**, vá para a etapa **Validar total disponível** e altere seu valor de **411** para **0**.</span><span class="sxs-lookup"><span data-stu-id="09a6e-124">To validate whether the inventory on-hand will always be more than **0**, go to the **Validate Total Available** step and change its value from **411** to **0**.</span></span> <span data-ttu-id="09a6e-125">Altere o valor do campo **Operador** de um sinal de igualdade (**=**) para um sinal de maior que (**\>**).</span><span class="sxs-lookup"><span data-stu-id="09a6e-125">Change the value of the **Operator** field from an equal sign (**=**) to a greater than sign (**\>**).</span></span>
6. <span data-ttu-id="09a6e-126">Salve e feche o arquivo de parâmetro do Excel.</span><span class="sxs-lookup"><span data-stu-id="09a6e-126">Save and close the Excel parameter file.</span></span>
7. <span data-ttu-id="09a6e-127">Selecione **Carregar** para salvar as alterações feitas no arquivo de parâmetros do Excel para o Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="09a6e-127">Select **Upload** to save the changes that you made to the Excel parameter file to Azure DevOps.</span></span>

<span data-ttu-id="09a6e-128">Agora, se o valor do campo **Total Disponível** para o item especificado no estoque for maior que 0 (zero), os testes serão aprovados, independentemente do valor do estoque disponível real.</span><span class="sxs-lookup"><span data-stu-id="09a6e-128">Now, if the value of the **Total Available** field for the specified item in inventory is more than 0 (zero), tests will pass, regardless of the actual on-hand inventory value.</span></span>

### <a name="saved-variables-and-chaining-of-test-cases"></a><span data-ttu-id="09a6e-129">Variáveis salvas e encadeamento de casos de teste</span><span class="sxs-lookup"><span data-stu-id="09a6e-129">Saved variables and chaining of test cases</span></span>

<span data-ttu-id="09a6e-130">Um dos principais recursos de RSAT é o encadeamento dos casos de teste, ou seja, a possibilidade de um teste passar variáveis para outros testes.</span><span class="sxs-lookup"><span data-stu-id="09a6e-130">One of the key features of RSAT is the chaining of test cases, that is, the ability of a test to pass variables to other tests.</span></span> <span data-ttu-id="09a6e-131">Para obter mais informações, consulte o artigo [Copiar variáveis para casos de teste de encadeamento](rsat-chain-test-cases.md).</span><span class="sxs-lookup"><span data-stu-id="09a6e-131">For more information, see the article [Copy variables to chain test cases](rsat-chain-test-cases.md).</span></span>

### <a name="derived-test-case"></a><span data-ttu-id="09a6e-132">Caso de teste derivado</span><span class="sxs-lookup"><span data-stu-id="09a6e-132">Derived test case</span></span>

<span data-ttu-id="09a6e-133">O RSAT permite usar a mesma gravação de tarefas com vários casos de teste, permitindo que uma tarefa seja executada com configurações de dados diferentes.</span><span class="sxs-lookup"><span data-stu-id="09a6e-133">RSAT lets you use the same task recording with multiple test cases, enabling a task to run with different data configurations.</span></span> <span data-ttu-id="09a6e-134">Consulte o artigo [Casos de teste derivados](rsat-derived-test-cases.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="09a6e-134">See the article [Derived test cases](rsat-derived-test-cases.md) for more information.</span></span>

### <a name="validate-notifications-and-messages"></a><span data-ttu-id="09a6e-135">Validar notificações e mensagens</span><span class="sxs-lookup"><span data-stu-id="09a6e-135">Validate notifications and messages</span></span>

<span data-ttu-id="09a6e-136">Esse recurso pode ser usado para validar se uma ação ocorreu.</span><span class="sxs-lookup"><span data-stu-id="09a6e-136">This feature can be used to validate whether an action occurred.</span></span> <span data-ttu-id="09a6e-137">Por exemplo, quando uma ordem de produção é criada, prevista e iniciada, o aplicativo mostra a mensagem "Produção - Início" para notificar que a ordem de produção foi iniciada.</span><span class="sxs-lookup"><span data-stu-id="09a6e-137">For example, when a production order is created, estimated, and then started, the app shows a "Production – Start" message to notify you that the production order has been started.</span></span>

![Produção - Iniciar notificação](./media/use_rsa_tool_05.png)

<span data-ttu-id="09a6e-139">Você pode validar essa mensagem através do RSAT inserindo o texto da mensagem na guia **MessageValidation** do arquivo de parâmetro do Excel para o registro apropriado.</span><span class="sxs-lookup"><span data-stu-id="09a6e-139">You can validate this message through RSAT by entering the message text on the **MessageValidation** tab of the Excel parameter file for the appropriate recording.</span></span>

![Guia Validação da Mensagem](./media/use_rsa_tool_06.png)

<span data-ttu-id="09a6e-141">Depois que o caso de teste for executado, a mensagem no arquivo de parâmetros do Excel será comparada à mensagem mostrada.</span><span class="sxs-lookup"><span data-stu-id="09a6e-141">After the test case is run, the message in the Excel parameter file is compared to the message that is shown.</span></span> <span data-ttu-id="09a6e-142">Se as mensagens não forem correspondentes, o caso de teste falhará.</span><span class="sxs-lookup"><span data-stu-id="09a6e-142">If the messages don't match, the test case will fail.</span></span>

> [!NOTE]
> <span data-ttu-id="09a6e-143">Você pode inserir mais de uma mensagem na guia **MessageValidation** do arquivo de parâmetro do Excel.</span><span class="sxs-lookup"><span data-stu-id="09a6e-143">You can enter more than one message on the **MessageValidation** tab in the Excel parameter file.</span></span> <span data-ttu-id="09a6e-144">As mensagens também podem ser de erro ou de advertência, em vez de mensagens informativas.</span><span class="sxs-lookup"><span data-stu-id="09a6e-144">The messages also can be error or warning messages instead of informational messages.</span></span>

### <a name="snapshot"></a><span data-ttu-id="09a6e-145">Instantâneo</span><span class="sxs-lookup"><span data-stu-id="09a6e-145">Snapshot</span></span>

<span data-ttu-id="09a6e-146">Esse recurso faz capturas de tela das etapas executadas durante a gravação de tarefas.</span><span class="sxs-lookup"><span data-stu-id="09a6e-146">This feature takes screenshots of the steps that were performed during task recording.</span></span> <span data-ttu-id="09a6e-147">É útil para fins de auditoria ou depuração.</span><span class="sxs-lookup"><span data-stu-id="09a6e-147">It is useful for auditing or debugging purposes.</span></span>

- <span data-ttu-id="09a6e-148">Para usar este recurso, abra o arquivo **Microsoft.Dynamics.RegressionSuite.WindowsApp.exe.config** na pasta de instalação do RSAT (por exemplo, **C:\\Arquivos de Programas (x86)\\Regression Suite Automation Tool**) e altere o valor do seguinte elemento de **falso** para **verdadeiro**.</span><span class="sxs-lookup"><span data-stu-id="09a6e-148">To use this feature, open the **Microsoft.Dynamics.RegressionSuite.WindowsApp.exe.config** file under the RSAT installation folder (for example, **C:\\Program Files (x86)\\Regression Suite Automation Tool**), and change the value of the following element from **false** to **true**.</span></span>

    ```xml
    <add key="VerboseSnapshotsEnabled" value="false" />
    ```

<span data-ttu-id="09a6e-149">Quando o caso de teste for executado, o RSAT gerará instantâneos (imagens) das etapas na pasta de reprodução dos casos de teste no diretório de trabalho.</span><span class="sxs-lookup"><span data-stu-id="09a6e-149">When your run the test case, RSAT will generate snapshots (images) of the steps in the playback folder of the test cases in the working diretory.</span></span> <span data-ttu-id="09a6e-150">Se você estiver usando uma versão mais antiga do RSAT, as imagens serão salvas em **C:\\Users\\\<Username\>\\AppData\\Roaming\\regressionTool\\playback** e uma pasta separada é criada para cada caso de teste executado.</span><span class="sxs-lookup"><span data-stu-id="09a6e-150">If you are using an older version of RSAT, the images are saved to **C:\\Users\\\<Username\>\\AppData\\Roaming\\regressionTool\\playback**, a separate folder is created for each test case that is run.</span></span>

## <a name="assignment"></a><span data-ttu-id="09a6e-151">Atribuição</span><span class="sxs-lookup"><span data-stu-id="09a6e-151">Assignment</span></span>

### <a name="scenario"></a><span data-ttu-id="09a6e-152">Cenário</span><span class="sxs-lookup"><span data-stu-id="09a6e-152">Scenario</span></span>

1. <span data-ttu-id="09a6e-153">O designer de produtos cria um novo produto liberado.</span><span class="sxs-lookup"><span data-stu-id="09a6e-153">The product designer creates a new released product.</span></span>
2. <span data-ttu-id="09a6e-154">O gerente de produção inicia uma ordem de produção para deixar o nível de estoque com duas peças.</span><span class="sxs-lookup"><span data-stu-id="09a6e-154">The production manager initiates a production order to bring the stock level to two pieces.</span></span>
3. <span data-ttu-id="09a6e-155">A fabricação inicia e termina a ordem de produção e verifica se a quantidade disponível está com duas peças.</span><span class="sxs-lookup"><span data-stu-id="09a6e-155">Manufacturing starts and ends the production order, and verifies that the on-hand quantity is two pieces.</span></span>
4. <span data-ttu-id="09a6e-156">A equipe de venda recebe um pedido de quatro peças do novo produto.</span><span class="sxs-lookup"><span data-stu-id="09a6e-156">The sales team receives an order for four pieces of the new product.</span></span> <span data-ttu-id="09a6e-157">Portanto, a equipe de vendas atualiza os requisitos líquidos através do plano dinâmico.</span><span class="sxs-lookup"><span data-stu-id="09a6e-157">Therefore, the sales team updates the net requirements via the dynamic plan.</span></span> <span data-ttu-id="09a6e-158">Como nenhuma capacidade adicional está disponível, a política de ordem padrão é definida como "comprar em vez de fazer".</span><span class="sxs-lookup"><span data-stu-id="09a6e-158">Because no additional capacity is available, the default order policy is set to "buy instead of make."</span></span> <span data-ttu-id="09a6e-159">Portanto, uma ordem de compra planejada é criada.</span><span class="sxs-lookup"><span data-stu-id="09a6e-159">Therefore, a planned purchase order is created.</span></span>
5. <span data-ttu-id="09a6e-160">O comprador adiciona um fornecedor, firma a ordem de compra planejada e confirma a ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="09a6e-160">The buyer adds a vendor, firms the planned purchase order, and then confirms the purchase order.</span></span>
6. <span data-ttu-id="09a6e-161">Quando as mercadorias que foram compradas chegam na loja, o operador da loja pesquisa a ordem de compra relacionada e recebe as mercadorias.</span><span class="sxs-lookup"><span data-stu-id="09a6e-161">When the goods that were purchased arrive at the store, the store operator searches the related purchase order and receives the goods.</span></span> <span data-ttu-id="09a6e-162">Como a ordem agora está concluída, as mercadorias podem ser separadas e embaladas conforme a ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="09a6e-162">Because the order is now completed, goods can be picked and packed against the sales order.</span></span>
7. <span data-ttu-id="09a6e-163">O financeiro lança a fatura de compras e a fatura de vendas.</span><span class="sxs-lookup"><span data-stu-id="09a6e-163">Finance posts the purchase invoice and sales invoice.</span></span>

<span data-ttu-id="09a6e-164">A ilustração a seguir mostra o fluxo para esse cenário.</span><span class="sxs-lookup"><span data-stu-id="09a6e-164">The following illustration shows the flow for this scenario.</span></span>

![Fluxo do cenário de demonstração](./media/use_rsa_tool_14.png)

<span data-ttu-id="09a6e-166">A ilustração a seguir mostra a hierarquia de processos comerciais para esse cenário no LCS Business Process Modeler.</span><span class="sxs-lookup"><span data-stu-id="09a6e-166">The following illustration shows the business processes hierarchy for this scenario in the LCS Business Process Modeler.</span></span>

![Processos empresariais do cenário de demonstração](./media/use_rsa_tool_15.png)

## <a name="strategy--key-learning"></a><span data-ttu-id="09a6e-168">Estratégia – Aprendizagem principal</span><span class="sxs-lookup"><span data-stu-id="09a6e-168">Strategy – Key learning</span></span>

### <a name="data"></a><span data-ttu-id="09a6e-169">Dados</span><span class="sxs-lookup"><span data-stu-id="09a6e-169">Data</span></span>

- <span data-ttu-id="09a6e-170">Verifique se você tem volumes de dados representativos (uma cópia da produção/dados de configuração dourada mais dados migrados).</span><span class="sxs-lookup"><span data-stu-id="09a6e-170">Make sure that you have representative data volumes (a copy of production/golden configuration data plus migrated data).</span></span>
- <span data-ttu-id="09a6e-171">Ao gerar novos dados por meio do gravador de tarefas, cria nomes de teste que não irão entrar em conflito com os nomes existentes (por exemplo, usar um prefixo como **RSATxxx**).</span><span class="sxs-lookup"><span data-stu-id="09a6e-171">When you generate new data via Task recorder, create test names that won't conflict with existing names (for example, use a prefix such as **RSATxxx**).</span></span>
- <span data-ttu-id="09a6e-172">Use a restauração pontual do Azure para reexecutar testes nos ambientes que não estão na Camada 1.</span><span class="sxs-lookup"><span data-stu-id="09a6e-172">Use Azure Point-In-Time restore to rerun tests in non-Tier 1 environments.</span></span>
- <span data-ttu-id="09a6e-173">Embora você possa usar as funções **RANDOM** e **NOW** do Excel para gerar uma combinação exclusiva, o esforço é consideravelmente alto.</span><span class="sxs-lookup"><span data-stu-id="09a6e-173">Although you can use the **RANDOM** and **NOW** Excel functions to generate a unique combination, the effort is considerably high.</span></span> <span data-ttu-id="09a6e-174">Veja aqui um exemplo.</span><span class="sxs-lookup"><span data-stu-id="09a6e-174">Here is an example.</span></span>

    ```Excel
    product = "AT" &TEXT(NOW(),"yyymmddhhmm")
    ```

### <a name="task-recorder"></a><span data-ttu-id="09a6e-175">Gravador de Tarefas</span><span class="sxs-lookup"><span data-stu-id="09a6e-175">Task recorder</span></span>

- <span data-ttu-id="09a6e-176">Definir cenários antes de iniciar a gravação.</span><span class="sxs-lookup"><span data-stu-id="09a6e-176">Define scenarios before you start recording.</span></span> <span data-ttu-id="09a6e-177">Um projeto bem gerenciado tem cenários de teste predefinidos.</span><span class="sxs-lookup"><span data-stu-id="09a6e-177">A well-managed project has predefined test scenarios.</span></span> <span data-ttu-id="09a6e-178">Para criar um caso de teste, considere como é previsível o resultado desses cenários de teste.</span><span class="sxs-lookup"><span data-stu-id="09a6e-178">To build a test case, consider how predictable the outcome of those test scenarios is.</span></span>
- <span data-ttu-id="09a6e-179">Divida as gravações, se forem executadas por diferentes funções, ou se houver tempo de espera ou um evento externo antes da próxima etapa.</span><span class="sxs-lookup"><span data-stu-id="09a6e-179">Split recordings if they are performed by different roles, or if there is waiting time or an external event before the next step.</span></span>
- <span data-ttu-id="09a6e-180">Evite selecionar valores nas listas.</span><span class="sxs-lookup"><span data-stu-id="09a6e-180">Avoid selecting values in lists.</span></span> <span data-ttu-id="09a6e-181">Em vez disso, use formatos de texto, como **PEPS**, **AudioRM** e **SiteWH**.</span><span class="sxs-lookup"><span data-stu-id="09a6e-181">Instead, use text formats, such as **FIFO**, **AudioRM**, and **SiteWH**.</span></span> <span data-ttu-id="09a6e-182">Quando você seleciona em uma lista, a posição do valor na lista é registrada, não o valor em si.</span><span class="sxs-lookup"><span data-stu-id="09a6e-182">When you select in a list, the position of the value in the list is recorded, not the value itself.</span></span> <span data-ttu-id="09a6e-183">Se itens forem adicionados a essa lista, a posição do valor pode mudar.</span><span class="sxs-lookup"><span data-stu-id="09a6e-183">If items are added to that list, the position of the value can change.</span></span> <span data-ttu-id="09a6e-184">Portanto, sua gravação usará um parâmetro diferente e o restante de cenário poderá ser afetado.</span><span class="sxs-lookup"><span data-stu-id="09a6e-184">Therefore, your recording will use a different parameter, and the rest of the scenario might be affected.</span></span>
- <span data-ttu-id="09a6e-185">Pense sobre o comportamento de vários usuários.</span><span class="sxs-lookup"><span data-stu-id="09a6e-185">Think about multi-user behavior.</span></span> <span data-ttu-id="09a6e-186">Por exemplo, não presuma que sua ordem de venda recém-criada será sempre selecionada automaticamente.</span><span class="sxs-lookup"><span data-stu-id="09a6e-186">For example, don't assume that your newly created sales order will always be automatically selected.</span></span> <span data-ttu-id="09a6e-187">Em vez disso, sempre use o filtro para localizar a ordem correta.</span><span class="sxs-lookup"><span data-stu-id="09a6e-187">Instead, always use the filter to find the correct order.</span></span>
- <span data-ttu-id="09a6e-188">Use a função Copiar no gravador de tarefas para salvar o nome de um produto recém-criado, de forma que ele possa ser usado em casos de teste encadeados.</span><span class="sxs-lookup"><span data-stu-id="09a6e-188">Use the Copy function in Task recorder to save the name of a newly created product so it can be used in chained test cases.</span></span>
- <span data-ttu-id="09a6e-189">Use a função Validar no gravador de tarefas para definir pontos de verificação que detectam se as etapas foram executadas corretamente.</span><span class="sxs-lookup"><span data-stu-id="09a6e-189">Use the Validate function in Task recorder to set checkpoints that verify that steps have been run correctly.</span></span>

### <a name="rsat"></a><span data-ttu-id="09a6e-190">RSAT</span><span class="sxs-lookup"><span data-stu-id="09a6e-190">RSAT</span></span>

- <span data-ttu-id="09a6e-191">Para executar o teste em outra empresa, você pode alterar a empresa na guia **Geral** do arquivo de parâmetro do Excel.</span><span class="sxs-lookup"><span data-stu-id="09a6e-191">To run the test in another company, you can change the company on the **General** tab of the Excel parameter file.</span></span> <span data-ttu-id="09a6e-192">Verifique se as configurações e os dados estão disponíveis na empresa selecionada recentemente.</span><span class="sxs-lookup"><span data-stu-id="09a6e-192">Make sure that settings and data are available in the newly selected company.</span></span>
- <span data-ttu-id="09a6e-193">Você pode alterar o usuário do teste na guia **Geral** do arquivo de parâmetros do Excel.</span><span class="sxs-lookup"><span data-stu-id="09a6e-193">You can change the test user on the **General** tab of the Excel parameter file.</span></span> <span data-ttu-id="09a6e-194">Especifique a ID de email do usuário que executará o caso de teste.</span><span class="sxs-lookup"><span data-stu-id="09a6e-194">Specify the email ID of the user who will run the test case.</span></span> <span data-ttu-id="09a6e-195">Dessa forma, o caso de teste pode ser executado usando as permissões de segurança do usuário especificado.</span><span class="sxs-lookup"><span data-stu-id="09a6e-195">In this way, the test case can be run by using the security permissions of the specified user.</span></span>
- <span data-ttu-id="09a6e-196">Para aguardar antes de iniciar o teste, você pode definir uma pausa na guia **Geral** do arquivo de parâmetros do Excel.</span><span class="sxs-lookup"><span data-stu-id="09a6e-196">To wait before the test is started, you can define a pause on the **General** tab of the Excel parameter file.</span></span> <span data-ttu-id="09a6e-197">Esta pausa pode ser usada em um trabalho em lotes (por exemplo, se um fluxo de trabalho tiver que ser executado antes da próxima etapa ser executada).</span><span class="sxs-lookup"><span data-stu-id="09a6e-197">This pause can be used in a batch job (for example, if a workflow must be run before the next step can be performed.)</span></span>

## <a name="advanced-scripting"></a><span data-ttu-id="09a6e-198">Script avançado</span><span class="sxs-lookup"><span data-stu-id="09a6e-198">Advanced scripting</span></span>

### <a name="cli"></a><span data-ttu-id="09a6e-199">CLI</span><span class="sxs-lookup"><span data-stu-id="09a6e-199">CLI</span></span>

<span data-ttu-id="09a6e-200">O RSAT pode ser chamado de uma janela do **Prompt de Comando** ou **PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="09a6e-200">RSAT can be called from a **Command Prompt** or **PowerShell** window.</span></span>

> [!NOTE]
> <span data-ttu-id="09a6e-201">Verifique se a variável de ambiente **TestRoot** está definida para o caminho de instalação de RSAT.</span><span class="sxs-lookup"><span data-stu-id="09a6e-201">Verify that the **TestRoot** environment variable is set to the RSAT installation path.</span></span> <span data-ttu-id="09a6e-202">(No Microsoft Windows, abra **Painel de Controle**, selecione **Sistema e segurança \> Sistema \> Configurações avançadas do sistema**, e **Variáveis de Ambiente**).</span><span class="sxs-lookup"><span data-stu-id="09a6e-202">(In Microsoft Windows, open **Control Panel**, select **System and Security \> System \> Advanced system settings**, and then select **Environment Variables**.)</span></span>

1. <span data-ttu-id="09a6e-203">Abra uma janela do **Prompt de Comando** ou **PowerShell** como um administrador.</span><span class="sxs-lookup"><span data-stu-id="09a6e-203">Open a **Command Prompt** or **PowerShell** window as an admin.</span></span>
2. <span data-ttu-id="09a6e-204">Navegue até o diretório de instalação do RSAT.</span><span class="sxs-lookup"><span data-stu-id="09a6e-204">Navigate to the RSAT installation directory.</span></span>

    ```Console
    cd "c:\Program Files (x86)\Regression Suite Automation Tool\"
    ```

3. <span data-ttu-id="09a6e-205">Liste todos os comandos.</span><span class="sxs-lookup"><span data-stu-id="09a6e-205">List all commands.</span></span>

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

#### <a name=""></a><span data-ttu-id="09a6e-206">?</span><span class="sxs-lookup"><span data-stu-id="09a6e-206">?</span></span>

<span data-ttu-id="09a6e-207">Mostra a ajuda sobre todos os comandos disponíveis e seus parâmetros.</span><span class="sxs-lookup"><span data-stu-id="09a6e-207">Shows help about all available commands and their parameters.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``?``**``[command]``

##### <a name="-optional-parameters"></a><span data-ttu-id="09a6e-208">?: parâmetros opcionais</span><span class="sxs-lookup"><span data-stu-id="09a6e-208">?: Optional parameters</span></span>

<span data-ttu-id="09a6e-209">`command`: em que ``[command]`` é um dos comandos especificados abaixo.</span><span class="sxs-lookup"><span data-stu-id="09a6e-209">`command`: Where ``[command]`` is one of the commands specified below.</span></span>

#### <a name="about"></a><span data-ttu-id="09a6e-210">sobre</span><span class="sxs-lookup"><span data-stu-id="09a6e-210">about</span></span>

<span data-ttu-id="09a6e-211">Exibe a versão atual.</span><span class="sxs-lookup"><span data-stu-id="09a6e-211">Displays the current version.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``about``**

#### <a name="cls"></a><span data-ttu-id="09a6e-212">cls</span><span class="sxs-lookup"><span data-stu-id="09a6e-212">cls</span></span>

<span data-ttu-id="09a6e-213">Limpa a tela.</span><span class="sxs-lookup"><span data-stu-id="09a6e-213">Clears the screen.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``cls``**

#### <a name="download"></a><span data-ttu-id="09a6e-214">fazer download</span><span class="sxs-lookup"><span data-stu-id="09a6e-214">download</span></span>

<span data-ttu-id="09a6e-215">Baixa anexos para o caso de teste especificado no diretório de saída.</span><span class="sxs-lookup"><span data-stu-id="09a6e-215">Downloads attachments for the specified test case to the output directory.</span></span>
<span data-ttu-id="09a6e-216">Você pode usar o comando ``list`` para obter todos os casos de teste disponíveis.</span><span class="sxs-lookup"><span data-stu-id="09a6e-216">You can use the ``list`` command to get all available test cases.</span></span> <span data-ttu-id="09a6e-217">Use qualquer valor da primeira coluna como um parâmetro **test_case_id**.</span><span class="sxs-lookup"><span data-stu-id="09a6e-217">Use any value from the first column as a **test_case_id** parameter.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``download``**``[test_case_id] [output_dir]``

##### <a name="download-required-parameters"></a><span data-ttu-id="09a6e-218">baixar: parâmetros obrigatórios</span><span class="sxs-lookup"><span data-stu-id="09a6e-218">download: required parameters</span></span>

+ <span data-ttu-id="09a6e-219">`test_case_id`: representa a ID do caso de teste.</span><span class="sxs-lookup"><span data-stu-id="09a6e-219">`test_case_id`: Represents the test case ID.</span></span>
+ <span data-ttu-id="09a6e-220">`output_dir`: representa o diretório de saída.</span><span class="sxs-lookup"><span data-stu-id="09a6e-220">`output_dir`: Represents the output directory.</span></span> <span data-ttu-id="09a6e-221">O diretório deve existir.</span><span class="sxs-lookup"><span data-stu-id="09a6e-221">The directory must exist.</span></span>

##### <a name="download-examples"></a><span data-ttu-id="09a6e-222">baixar: exemplos</span><span class="sxs-lookup"><span data-stu-id="09a6e-222">download: examples</span></span>

`download 123 c:\temp\rsat`

`download 765 c:\rsat\last`

#### <a name="edit"></a><span data-ttu-id="09a6e-223">editar</span><span class="sxs-lookup"><span data-stu-id="09a6e-223">edit</span></span>

<span data-ttu-id="09a6e-224">Permite abrir o arquivo de parâmetros no programa Excel e editá-lo.</span><span class="sxs-lookup"><span data-stu-id="09a6e-224">Allows you to open parameters file in Excel program and edit it.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``edit``**``[excel_file]``

##### <a name="edit-required-parameters"></a><span data-ttu-id="09a6e-225">editar: parâmetros obrigatórios</span><span class="sxs-lookup"><span data-stu-id="09a6e-225">edit: required parameters</span></span>

+ <span data-ttu-id="09a6e-226">`excel_file`: deve conter um caminho completo para um arquivo existente do Excel.</span><span class="sxs-lookup"><span data-stu-id="09a6e-226">`excel_file`: Must contain a full path to an existing Excel file.</span></span>

##### <a name="edit-examples"></a><span data-ttu-id="09a6e-227">editar: exemplos</span><span class="sxs-lookup"><span data-stu-id="09a6e-227">edit: examples</span></span>

`edit c:\RSAT\TestCase_123_Base.xlsx`

`edit e:\temp\TestCase_456_Base.xlsx`

#### <a name="generate"></a><span data-ttu-id="09a6e-228">gerar</span><span class="sxs-lookup"><span data-stu-id="09a6e-228">generate</span></span>

<span data-ttu-id="09a6e-229">Gera arquivos de execução e parâmetro de teste para o caso de teste especificado no diretório de saída.</span><span class="sxs-lookup"><span data-stu-id="09a6e-229">Generates test execution and parameter files for the specified test case in the output directory.</span></span> <span data-ttu-id="09a6e-230">Você pode usar o comando ``list`` para obter todos os casos de teste disponíveis.</span><span class="sxs-lookup"><span data-stu-id="09a6e-230">You can use the ``list`` command to get all available test cases.</span></span> <span data-ttu-id="09a6e-231">Use qualquer valor da primeira coluna como um parâmetro **test_case_id**.</span><span class="sxs-lookup"><span data-stu-id="09a6e-231">Use any value from the first column as a **test_case_id** parameter.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``generate``**``[test_case_id] [output_dir]``

##### <a name="generate-required-parameters"></a><span data-ttu-id="09a6e-232">gerar: parâmetros obrigatórios</span><span class="sxs-lookup"><span data-stu-id="09a6e-232">generate: required parameters</span></span>

+ <span data-ttu-id="09a6e-233">`test_case_id`: representa a ID do caso de teste.</span><span class="sxs-lookup"><span data-stu-id="09a6e-233">`test_case_id`: Represents the test case ID.</span></span>
+ <span data-ttu-id="09a6e-234">`output_dir`: representa o diretório de saída.</span><span class="sxs-lookup"><span data-stu-id="09a6e-234">`output_dir`: Represents the output directory.</span></span> <span data-ttu-id="09a6e-235">O diretório deve existir.</span><span class="sxs-lookup"><span data-stu-id="09a6e-235">The directory must exist.</span></span>

##### <a name="generate-examples"></a><span data-ttu-id="09a6e-236">gerar: exemplos</span><span class="sxs-lookup"><span data-stu-id="09a6e-236">generate: examples</span></span>

`generate 123 c:\temp\rsat`

`generate 765 c:\rsat\last`

#### <a name="generatederived"></a><span data-ttu-id="09a6e-237">generatederived</span><span class="sxs-lookup"><span data-stu-id="09a6e-237">generatederived</span></span>

<span data-ttu-id="09a6e-238">Gera um novo caso de teste, derivado do caso de teste fornecido.</span><span class="sxs-lookup"><span data-stu-id="09a6e-238">Generates a new test case, derived from the provided test case.</span></span> <span data-ttu-id="09a6e-239">Você pode usar o comando ``list`` para obter todos os casos de teste disponíveis.</span><span class="sxs-lookup"><span data-stu-id="09a6e-239">You can use the ``list`` command to get all available test cases.</span></span> <span data-ttu-id="09a6e-240">Use qualquer valor da primeira coluna como um parâmetro **test_case_id**.</span><span class="sxs-lookup"><span data-stu-id="09a6e-240">Use any value from the first column as a **test_case_id** parameter.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``generatederived``**``[parent_test_case_id] [test_plan_id] [test_suite_id]``

##### <a name="generatederived-required-parameters"></a><span data-ttu-id="09a6e-241">generatederived: parâmetros obrigatórios</span><span class="sxs-lookup"><span data-stu-id="09a6e-241">generatederived: required parameters</span></span>

+ <span data-ttu-id="09a6e-242">`parent_test_case_id`: representa a ID do caso de teste pai.</span><span class="sxs-lookup"><span data-stu-id="09a6e-242">`parent_test_case_id`: Represents the parent test case ID.</span></span>
+ <span data-ttu-id="09a6e-243">`test_plan_id`: representa a ID do plano de teste.</span><span class="sxs-lookup"><span data-stu-id="09a6e-243">`test_plan_id`: Represents the test plan ID.</span></span>
+ <span data-ttu-id="09a6e-244">`test_suite_id`: representa a ID do pacote de teste.</span><span class="sxs-lookup"><span data-stu-id="09a6e-244">`test_suite_id`: Represents the test suite ID.</span></span>

##### <a name="generatederived-examples"></a><span data-ttu-id="09a6e-245">generatederived: exemplos</span><span class="sxs-lookup"><span data-stu-id="09a6e-245">generatederived: examples</span></span>

`generatederived 123 8901 678`

#### <a name="generatetestonly"></a><span data-ttu-id="09a6e-246">generatetestonly</span><span class="sxs-lookup"><span data-stu-id="09a6e-246">generatetestonly</span></span>

<span data-ttu-id="09a6e-247">Gera somente o arquivo de execução de teste para o caso de teste especificado no diretório de saída.</span><span class="sxs-lookup"><span data-stu-id="09a6e-247">Generates only test execution file for the specified test case in the output directory.</span></span> <span data-ttu-id="09a6e-248">Você pode usar o comando ``list`` para obter todos os casos de teste disponíveis.</span><span class="sxs-lookup"><span data-stu-id="09a6e-248">You can use the ``list`` command to get all available test cases.</span></span> <span data-ttu-id="09a6e-249">Use qualquer valor da primeira coluna como um parâmetro **test_case_id**.</span><span class="sxs-lookup"><span data-stu-id="09a6e-249">Use any value from the first column as a **test_case_id** parameter.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``generatetestonly``**``[test_case_id] [output_dir]``

##### <a name="generatetestonly-required-parameters"></a><span data-ttu-id="09a6e-250">generatetestonly: parâmetros obrigatórios</span><span class="sxs-lookup"><span data-stu-id="09a6e-250">generatetestonly: required parameters</span></span>

+ <span data-ttu-id="09a6e-251">`test_case_id`: representa a ID do caso de teste.</span><span class="sxs-lookup"><span data-stu-id="09a6e-251">`test_case_id`: Represents the test case ID.</span></span>
+ <span data-ttu-id="09a6e-252">`output_dir`: representa o diretório de saída.</span><span class="sxs-lookup"><span data-stu-id="09a6e-252">`output_dir`: Represents the output directory.</span></span> <span data-ttu-id="09a6e-253">O diretório deve existir.</span><span class="sxs-lookup"><span data-stu-id="09a6e-253">The directory must exist.</span></span>

##### <a name="generatetestonly-examples"></a><span data-ttu-id="09a6e-254">generatetestonly: exemplos</span><span class="sxs-lookup"><span data-stu-id="09a6e-254">generatetestonly: examples</span></span>

`generatetestonly 123 c:\temp\rsat`

`generatetestonly 765 c:\rsat\last`

#### <a name="generatetestsuite"></a><span data-ttu-id="09a6e-255">generatetestsuite</span><span class="sxs-lookup"><span data-stu-id="09a6e-255">generatetestsuite</span></span>

<span data-ttu-id="09a6e-256">Gera todos os casos de teste para o conjunto especificado no diretório de saída.</span><span class="sxs-lookup"><span data-stu-id="09a6e-256">Generates all test cases for the specified suite in the output directory.</span></span> <span data-ttu-id="09a6e-257">Você pode usar o comando ``listtestsuitenames`` para obter todos os pacotes de teste disponíveis.</span><span class="sxs-lookup"><span data-stu-id="09a6e-257">You can use ``listtestsuitenames`` command to get all available test suits.</span></span> <span data-ttu-id="09a6e-258">Use qualquer valor da coluna como um parâmetro **test_suite_name**.</span><span class="sxs-lookup"><span data-stu-id="09a6e-258">Use any value from the column as a **test_suite_name** parameter.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``generatetestsuite``**``[test_suite_name] [output_dir]``

##### <a name="generatetestsuite-required-parameters"></a><span data-ttu-id="09a6e-259">generatetestsuite: parâmetros obrigatórios</span><span class="sxs-lookup"><span data-stu-id="09a6e-259">generatetestsuite: required parameters</span></span>

+ <span data-ttu-id="09a6e-260">`test_suite_name`: representa o nome do pacote de teste.</span><span class="sxs-lookup"><span data-stu-id="09a6e-260">`test_suite_name`: Represents the test suite name.</span></span>
+ <span data-ttu-id="09a6e-261">`output_dir`: representa o diretório de saída.</span><span class="sxs-lookup"><span data-stu-id="09a6e-261">`output_dir`: Represents the output directory.</span></span> <span data-ttu-id="09a6e-262">O diretório deve existir.</span><span class="sxs-lookup"><span data-stu-id="09a6e-262">The directory must exist.</span></span>

##### <a name="generatetestsuite-examples"></a><span data-ttu-id="09a6e-263">generatetestsuite: exemplos</span><span class="sxs-lookup"><span data-stu-id="09a6e-263">generatetestsuite: examples</span></span>

`generatetestsuite Tests c:\temp\rsat`

`generatetestsuite Purchase c:\rsat\last`

#### <a name="help"></a><span data-ttu-id="09a6e-264">ajuda</span><span class="sxs-lookup"><span data-stu-id="09a6e-264">help</span></span>

<span data-ttu-id="09a6e-265">Idêntico ao comando [?](#section)</span><span class="sxs-lookup"><span data-stu-id="09a6e-265">Identical to the [?](#section)</span></span> <span data-ttu-id="09a6e-266">.</span><span class="sxs-lookup"><span data-stu-id="09a6e-266">command.</span></span>

#### <a name="list"></a><span data-ttu-id="09a6e-267">lista</span><span class="sxs-lookup"><span data-stu-id="09a6e-267">list</span></span>

<span data-ttu-id="09a6e-268">Lista todos os casos de teste disponíveis.</span><span class="sxs-lookup"><span data-stu-id="09a6e-268">Lists all available test cases.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``list``**

#### <a name="listtestplans"></a><span data-ttu-id="09a6e-269">listtestplans</span><span class="sxs-lookup"><span data-stu-id="09a6e-269">listtestplans</span></span>

<span data-ttu-id="09a6e-270">Lista todos os planos de teste disponíveis.</span><span class="sxs-lookup"><span data-stu-id="09a6e-270">Lists all available test plans.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``listtestplans``**

#### <a name="listtestsuite"></a><span data-ttu-id="09a6e-271">listtestsuite</span><span class="sxs-lookup"><span data-stu-id="09a6e-271">listtestsuite</span></span>

<span data-ttu-id="09a6e-272">Lista casos de teste para o pacote de teste especificado.</span><span class="sxs-lookup"><span data-stu-id="09a6e-272">Lists test cases for the specified test suite.</span></span> <span data-ttu-id="09a6e-273">Você pode usar o comando ``listtestsuitenames`` para obter todos os pacotes de teste disponíveis.</span><span class="sxs-lookup"><span data-stu-id="09a6e-273">You can use ``listtestsuitenames`` command to get all available test suites.</span></span> <span data-ttu-id="09a6e-274">Use qualquer valor da primeira coluna como parâmetro **suite_name**.</span><span class="sxs-lookup"><span data-stu-id="09a6e-274">Use any value from first column as **suite_name** parameter.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``listtestsuite``**``[suite_name]``

##### <a name="listtestsuite-required-parameters"></a><span data-ttu-id="09a6e-275">listtestsuite: parâmetros obrigatórios</span><span class="sxs-lookup"><span data-stu-id="09a6e-275">listtestsuite: required parameters</span></span>

+ <span data-ttu-id="09a6e-276">`suite_name`: nome do pacote desejado.</span><span class="sxs-lookup"><span data-stu-id="09a6e-276">`suite_name`: Name of the desired suite.</span></span>

##### <a name="listtestsuite-examples"></a><span data-ttu-id="09a6e-277">listtestsuite: exemplos</span><span class="sxs-lookup"><span data-stu-id="09a6e-277">listtestsuite: examples</span></span>

`listtestsuite "sample suite name"`

`listtestsuite NameOfTheSuite`

#### <a name="listtestsuitenames"></a><span data-ttu-id="09a6e-278">listtestsuitenames</span><span class="sxs-lookup"><span data-stu-id="09a6e-278">listtestsuitenames</span></span>

<span data-ttu-id="09a6e-279">Lista todos os pacotes de teste disponíveis.</span><span class="sxs-lookup"><span data-stu-id="09a6e-279">Lists all available test suites.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``listtestsuitenames``**

#### <a name="playback"></a><span data-ttu-id="09a6e-280">reprodução</span><span class="sxs-lookup"><span data-stu-id="09a6e-280">playback</span></span>

<span data-ttu-id="09a6e-281">Reproduz um caso de teste usando um arquivo do Excel.</span><span class="sxs-lookup"><span data-stu-id="09a6e-281">Plays back a test case using an Excel file.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``playback``**``[excel_file]``

##### <a name="playback-required-parameters"></a><span data-ttu-id="09a6e-282">reprodução: parâmetros obrigatórios</span><span class="sxs-lookup"><span data-stu-id="09a6e-282">playback: required parameters</span></span>

+ <span data-ttu-id="09a6e-283">`excel_file`: um caminho completo para o arquivo do Excel.</span><span class="sxs-lookup"><span data-stu-id="09a6e-283">`excel_file`: A full path to the Excel file.</span></span> <span data-ttu-id="09a6e-284">O arquivo deve existir.</span><span class="sxs-lookup"><span data-stu-id="09a6e-284">File must exist.</span></span>

##### <a name="playback-examples"></a><span data-ttu-id="09a6e-285">reprodução: exemplos</span><span class="sxs-lookup"><span data-stu-id="09a6e-285">playback: examples</span></span>

`playback c:\RSAT\TestCaseParameters\sample1.xlsx`

`playback e:\temp\test.xlsx`

#### <a name="playbackbyid"></a><span data-ttu-id="09a6e-286">playbackbyid</span><span class="sxs-lookup"><span data-stu-id="09a6e-286">playbackbyid</span></span>

<span data-ttu-id="09a6e-287">Reproduz vários casos de teste de uma só vez.</span><span class="sxs-lookup"><span data-stu-id="09a6e-287">Plays back multiple test cases at once.</span></span> <span data-ttu-id="09a6e-288">Você pode usar o comando ``list`` para obter todos os casos de teste disponíveis.</span><span class="sxs-lookup"><span data-stu-id="09a6e-288">You can use the ``list`` command to get all available test cases.</span></span> <span data-ttu-id="09a6e-289">Use qualquer valor da primeira coluna como um parâmetro **test_case_id**.</span><span class="sxs-lookup"><span data-stu-id="09a6e-289">Use any value from the first column as a **test_case_id** parameter.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``playbackbyid``**``[test_case_id1] [test_case_id2] ... [test_case_idN]``

##### <a name="playbackbyid-required-parameters"></a><span data-ttu-id="09a6e-290">playbackbyid: parâmetros obrigatórios</span><span class="sxs-lookup"><span data-stu-id="09a6e-290">playbackbyid: required parameters</span></span>

+ <span data-ttu-id="09a6e-291">`test_case_id1`: ID do caso de teste existente.</span><span class="sxs-lookup"><span data-stu-id="09a6e-291">`test_case_id1`: ID of exisiting test case.</span></span>
+ <span data-ttu-id="09a6e-292">`test_case_id2`: ID do caso de teste existente.</span><span class="sxs-lookup"><span data-stu-id="09a6e-292">`test_case_id2`: ID of exisiting test case.</span></span>
+ <span data-ttu-id="09a6e-293">`test_case_idN`: ID do caso de teste existente.</span><span class="sxs-lookup"><span data-stu-id="09a6e-293">`test_case_idN`: ID of exisiting test case.</span></span>

##### <a name="playbackbyid-examples"></a><span data-ttu-id="09a6e-294">playbackbyid: exemplos</span><span class="sxs-lookup"><span data-stu-id="09a6e-294">playbackbyid: examples</span></span>

`playbackbyid 878`

`playbackbyid 2345 667 135`

#### <a name="playbackmany"></a><span data-ttu-id="09a6e-295">playbackmany</span><span class="sxs-lookup"><span data-stu-id="09a6e-295">playbackmany</span></span>

<span data-ttu-id="09a6e-296">Reproduz muitos casos de teste de uma só vez, usando arquivos do Excel.</span><span class="sxs-lookup"><span data-stu-id="09a6e-296">Plays back many test cases at once, using Excel files.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``playbackmany``**``[excel_file1] [excel_file2] ... [excel_fileN]``

##### <a name="playbackmany-required-parameters"></a><span data-ttu-id="09a6e-297">playbackmany: parâmetros obrigatórios</span><span class="sxs-lookup"><span data-stu-id="09a6e-297">playbackmany: required parameters</span></span>

+ <span data-ttu-id="09a6e-298">`excel_file1`: caminho completo para o arquivo do Excel.</span><span class="sxs-lookup"><span data-stu-id="09a6e-298">`excel_file1`: Full path to the Excel file.</span></span> <span data-ttu-id="09a6e-299">O arquivo deve existir.</span><span class="sxs-lookup"><span data-stu-id="09a6e-299">File must exist.</span></span>
+ <span data-ttu-id="09a6e-300">`excel_file2`: caminho completo para o arquivo do Excel.</span><span class="sxs-lookup"><span data-stu-id="09a6e-300">`excel_file2`: Full path to the Excel file.</span></span> <span data-ttu-id="09a6e-301">O arquivo deve existir.</span><span class="sxs-lookup"><span data-stu-id="09a6e-301">File must exist.</span></span>
+ <span data-ttu-id="09a6e-302">`excel_fileN`: caminho completo para o arquivo do Excel.</span><span class="sxs-lookup"><span data-stu-id="09a6e-302">`excel_fileN`: Full path to the Excel file.</span></span> <span data-ttu-id="09a6e-303">O arquivo deve existir.</span><span class="sxs-lookup"><span data-stu-id="09a6e-303">File must exist.</span></span>

##### <a name="playbackmany-examples"></a><span data-ttu-id="09a6e-304">playbackmany: exemplos</span><span class="sxs-lookup"><span data-stu-id="09a6e-304">playbackmany: examples</span></span>

`playbackmany c:\RSAT\TestCaseParameters\param1.xlsx`

`playbackmany e:\temp\test.xlsx f:\rsat\sample1.xlsx c:\RSAT\sample2.xlsx`

#### <a name="playbacksuite"></a><span data-ttu-id="09a6e-305">playbacksuite</span><span class="sxs-lookup"><span data-stu-id="09a6e-305">playbacksuite</span></span>

<span data-ttu-id="09a6e-306">Reproduz todos os casos de teste do pacote de teste especificado.</span><span class="sxs-lookup"><span data-stu-id="09a6e-306">Plays back all test cases from the specified test suite.</span></span>
<span data-ttu-id="09a6e-307">Você pode usar o comando ``listtestsuitenames`` para obter todos os pacotes de teste disponíveis.</span><span class="sxs-lookup"><span data-stu-id="09a6e-307">You can use ``listtestsuitenames`` command to get all available test suites.</span></span> <span data-ttu-id="09a6e-308">Use qualquer valor da primeira coluna como parâmetro **suite_name**.</span><span class="sxs-lookup"><span data-stu-id="09a6e-308">Use any value from first column as **suite_name** parameter.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``playbacksuite``**``[suite_name]``

##### <a name="playbacksuite-required-parameters"></a><span data-ttu-id="09a6e-309">playbacksuite: parâmetros obrigatórios</span><span class="sxs-lookup"><span data-stu-id="09a6e-309">playbacksuite: required parameters</span></span>

+ <span data-ttu-id="09a6e-310">`suite_name`: nome do pacote desejado.</span><span class="sxs-lookup"><span data-stu-id="09a6e-310">`suite_name`: Name of the desired suite.</span></span>

##### <a name="playbacksuite-examples"></a><span data-ttu-id="09a6e-311">playbacksuite: exemplos</span><span class="sxs-lookup"><span data-stu-id="09a6e-311">playbacksuite: examples</span></span>

`playbacksuite suiteName`

`playbacksuite sample_suite`

#### <a name="quit"></a><span data-ttu-id="09a6e-312">encerrar</span><span class="sxs-lookup"><span data-stu-id="09a6e-312">quit</span></span>

<span data-ttu-id="09a6e-313">Fecha o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="09a6e-313">Closes the  application.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``quit``**

#### <a name="upload"></a><span data-ttu-id="09a6e-314">carregar</span><span class="sxs-lookup"><span data-stu-id="09a6e-314">upload</span></span>

<span data-ttu-id="09a6e-315">Carrega todos os arquivos pertencentes ao pacote de teste ou casos de teste especificados.</span><span class="sxs-lookup"><span data-stu-id="09a6e-315">Uploads all files belonging to the specified test suite or test cases.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``upload``**``[suite_name] [testcase_id]``

#### <a name="upload-required-parameters"></a><span data-ttu-id="09a6e-316">carregar: parâmetros obrigatórios</span><span class="sxs-lookup"><span data-stu-id="09a6e-316">upload: required parameters</span></span>

+ <span data-ttu-id="09a6e-317">`suite_name`: todos os arquivos pertencentes ao pacote de teste especificado serão carregados.</span><span class="sxs-lookup"><span data-stu-id="09a6e-317">`suite_name`: All files belonging to the specified test suite will be uploaded.</span></span>
+ <span data-ttu-id="09a6e-318">`testcase_id`: todos os arquivos pertencentes aos casos de teste especificados serão carregados.</span><span class="sxs-lookup"><span data-stu-id="09a6e-318">`testcase_id`: All files beloning to the specified test case(s) will be uploaded.</span></span>

##### <a name="upload-examples"></a><span data-ttu-id="09a6e-319">carregar: exemplos</span><span class="sxs-lookup"><span data-stu-id="09a6e-319">upload: examples</span></span>

`upload sample_suite`

`upload 123`

`upload 123 456`

#### <a name="uploadrecording"></a><span data-ttu-id="09a6e-320">uploadrecording</span><span class="sxs-lookup"><span data-stu-id="09a6e-320">uploadrecording</span></span>

<span data-ttu-id="09a6e-321">Carrega apenas o arquivo de gravação pertencente aos casos de teste especificados.</span><span class="sxs-lookup"><span data-stu-id="09a6e-321">Uploads only recording file belonging to the specified test cases.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``uploadrecording``**``[testcase_id]``

##### <a name="uploadrecording-required-parameters"></a><span data-ttu-id="09a6e-322">uploadrecording: parâmetros obrigatórios</span><span class="sxs-lookup"><span data-stu-id="09a6e-322">uploadrecording: required parameters</span></span>

+ <span data-ttu-id="09a6e-323">`testcase_id`: o arquivo de gravação pertencente aos casos de teste especificados será carregado.</span><span class="sxs-lookup"><span data-stu-id="09a6e-323">`testcase_id`: Recording file belonging to the specified test cases will be uploaded.</span></span>

##### <a name="uploadrecording-examples"></a><span data-ttu-id="09a6e-324">uploadrecording: exemplos</span><span class="sxs-lookup"><span data-stu-id="09a6e-324">uploadrecording: examples</span></span>

`uploadrecording 123`

`uploadrecording 123 456`

#### <a name="usage"></a><span data-ttu-id="09a6e-325">uso</span><span class="sxs-lookup"><span data-stu-id="09a6e-325">usage</span></span>

<span data-ttu-id="09a6e-326">Mostra duas maneiras de chamar esse aplicativo: uma usando um arquivo de configuração padrão, outra fornecendo um arquivo de configuração.</span><span class="sxs-lookup"><span data-stu-id="09a6e-326">Shows two ways to invoke this application: one using a default setting file, another one providing a setting file.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``usage``**

### <a name="windows-powershell-examples"></a><span data-ttu-id="09a6e-327">Exemplos de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="09a6e-327">Windows PowerShell examples</span></span>

#### <a name="run-a-test-case-in-a-loop"></a><span data-ttu-id="09a6e-328">Executar um caso de teste em um loop</span><span class="sxs-lookup"><span data-stu-id="09a6e-328">Run a test case in a loop</span></span>

<span data-ttu-id="09a6e-329">Você tem um script de teste que cria um novo cliente.</span><span class="sxs-lookup"><span data-stu-id="09a6e-329">You have a test script that creates a new customer.</span></span> <span data-ttu-id="09a6e-330">Através do script, este caso de teste pode ser executado em um loop, randomizando os seguintes dados antes de cada iteração ser executada:</span><span class="sxs-lookup"><span data-stu-id="09a6e-330">Via scripting, this test case can be run in a loop by randomizing the following data before each iteration is run:</span></span>

- <span data-ttu-id="09a6e-331">ID do cliente</span><span class="sxs-lookup"><span data-stu-id="09a6e-331">Customer ID</span></span>
- <span data-ttu-id="09a6e-332">Nome do Cliente</span><span class="sxs-lookup"><span data-stu-id="09a6e-332">Customer name</span></span>
- <span data-ttu-id="09a6e-333">Endereço do cliente</span><span class="sxs-lookup"><span data-stu-id="09a6e-333">Customer address</span></span>

<span data-ttu-id="09a6e-334">O ID do cliente estará no formato *ATCUS\<number\>*, onde \<number\> é um valor entre **000000001** e **999999999**.</span><span class="sxs-lookup"><span data-stu-id="09a6e-334">The customer ID will be in the format *ATCUS\<number\>*, where \<number\> is a value between **000000001** and **999999999**.</span></span>

<span data-ttu-id="09a6e-335">O seguinte exemplo usa um parâmetro, **iniciar**, para definir o primeiro número usado.</span><span class="sxs-lookup"><span data-stu-id="09a6e-335">The following example uses one parameter, **start**, to define the first number that is used.</span></span> <span data-ttu-id="09a6e-336">Usa um segundo parâmetro, **nr**, para definir o número de clientes que deve ser criado.</span><span class="sxs-lookup"><span data-stu-id="09a6e-336">Is uses a second parameter, **nr**, to define the number of customers that must be created.</span></span> <span data-ttu-id="09a6e-337">Para cada iteração, os parâmetros no arquivo de parâmetros do Excel são alterados usando uma função UpdateCustomer.</span><span class="sxs-lookup"><span data-stu-id="09a6e-337">For each iteration, the parameters in the Excel parameter file are changed by using an UpdateCustomer function.</span></span> <span data-ttu-id="09a6e-338">Em seguida, a linha de comandos de RSAT é chamada em uma função de RunTestCase.</span><span class="sxs-lookup"><span data-stu-id="09a6e-338">Then the RSAT command line is called in a RunTestCase function.</span></span>

<span data-ttu-id="09a6e-339">Abra o Ambiente de Script Integrado (ISE) do Microsoft Windows PowerShell no modo de administração e cole o seguinte código na janela que é nomeada **Untitled1.ps1**.</span><span class="sxs-lookup"><span data-stu-id="09a6e-339">Open Microsoft Windows PowerShell Integrated Scripting Environment (ISE) in admin mode, and paste the following code into the window that is named **Untitled1.ps1**.</span></span>

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
$excelFilename = "full path to Excel parameter file"
l$sheetName = "DirPartyQuickCreateForm"
for ($i = $start; $i -lt $start + $nr; $i++ )
{
    $CustomerId = $i.ToString("000000000")
    Write-Host "customer : " $CustomerId
    UpdateCustomer $excelFilename $sheetName $CustomerId
    RunTestCase $excelFilename
```

#### <a name="run-a-script-that-depends-on-data-in-microsoft-dynamics-365"></a><span data-ttu-id="09a6e-340">Execute um script que dependa de dados no Microsoft Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="09a6e-340">Run a script that depends on data in Microsoft Dynamics 365</span></span>

<span data-ttu-id="09a6e-341">O exemplo a seguir usa uma chamada do Protocolo Open Data (OData) para localizar o status da ordem de uma ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="09a6e-341">The following example uses an Open Data Protocol (OData) call to find the order status of a purchase order.</span></span> <span data-ttu-id="09a6e-342">Se o status não for **faturado**, você pode, por exemplo, chamar um caso de teste RSAT que lança a fatura.</span><span class="sxs-lookup"><span data-stu-id="09a6e-342">If the status isn't **invoiced**, you can, for example, call an RSAT test case that posts the invoice.</span></span>

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


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]