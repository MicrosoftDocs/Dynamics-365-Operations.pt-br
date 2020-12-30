---
title: Usar o tutorial sobre a Regression Suite Automation Tool
description: Esse tópico mostra como usar a Regression Suite Automation Tool (RSAT). Descreve diversos recursos e oferece exemplos que usam o script avançado.
author: robinarh
manager: AnnBe
ms.date: 06/09/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: rhaertle
ms.custom: 21761
ms.search.region: Global
ms.author: rhaertle
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: AX 7.0.0, Operations
ms.openlocfilehash: 798717b276e68949a9425350720bf683a37d6fb5
ms.sourcegitcommit: f5e31c34640add6d40308ac1365cc0ee60e60e24
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/08/2020
ms.locfileid: "4692981"
---
# <a name="regression-suite-automation-tool-tutorial"></a><span data-ttu-id="604f3-104">Tutorial sobre a Regression Suite Automation Tool</span><span class="sxs-lookup"><span data-stu-id="604f3-104">Regression suite automation tool tutorial</span></span>

[!include [banner](../includes/banner.md)]

> [!NOTE]
> <span data-ttu-id="604f3-105">Usa as ferramentas do navegador da internet para fazer download e salvar esta página no formato pdf.</span><span class="sxs-lookup"><span data-stu-id="604f3-105">Use your internet browser tools to download and save this page in pdf format.</span></span> 

<span data-ttu-id="604f3-106">Este tutorial aborda alguns dos recursos avançados da Regression Suite Automation Tool (RSAT), inclui uma atribuição de demonstração e descreve a estratégia e os principais pontos de aprendizagem.</span><span class="sxs-lookup"><span data-stu-id="604f3-106">This tutorial walks through some of the advanced features of the Regression suite automation tool (RSAT), includes a demo assignment, and describes strategy and key learning points.</span></span> 

## <a name="notable-features-of-rsat-and-task-recorder"></a><span data-ttu-id="604f3-107">Recursos notáveis do RSAT e Gravador de tarefas</span><span class="sxs-lookup"><span data-stu-id="604f3-107">Notable Features of RSAT and Task recorder</span></span>

### <a name="validate-a-field-value"></a><span data-ttu-id="604f3-108">Validar um valor do campo</span><span class="sxs-lookup"><span data-stu-id="604f3-108">Validate a field value</span></span>

<span data-ttu-id="604f3-109">O RSAT permite incluir etapas de validação no caso de teste para validar os valores esperados.</span><span class="sxs-lookup"><span data-stu-id="604f3-109">RSAT allows you to include validation steps within your test case to validate expected values.</span></span> <span data-ttu-id="604f3-110">Para obter informações sobre esse recurso, consulte o artigo [Validar valores esperados](../../dev-itpro/perf-test/rsat/rsat-validate-expected.md).</span><span class="sxs-lookup"><span data-stu-id="604f3-110">For information about this feature, see the article [Validate expected values](../../dev-itpro/perf-test/rsat/rsat-validate-expected.md).</span></span>

<span data-ttu-id="604f3-111">O exemplo a seguir mostra como é possível usar este recurso para validar se o estoque disponível é maior que 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="604f3-111">The following example shows how you can use this feature to validate whether the on-hand inventory is more than 0 (zero).</span></span>

1. <span data-ttu-id="604f3-112">Nos dados de demonstração da empresa **USMF**, crie uma gravação de tarefas que tenha as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="604f3-112">In the demo data in the **USMF** company, create a task recording that has the following steps:</span></span>

    1. <span data-ttu-id="604f3-113">Vá para **Gerenciamento de informações do produto \> Produtos \> Produtos liberados**.</span><span class="sxs-lookup"><span data-stu-id="604f3-113">Go to **Product information management \> Products \> Released products**.</span></span>
    2. <span data-ttu-id="604f3-114">Use o Filtro Rápido para localizar registros.</span><span class="sxs-lookup"><span data-stu-id="604f3-114">Use the Quick Filter to find records.</span></span> <span data-ttu-id="604f3-115">Por exemplo, filtre um valor de **1000** para o campo **Número do item**.</span><span class="sxs-lookup"><span data-stu-id="604f3-115">For example, filter on a value of **1000** for the **Item number** field.</span></span>
    3. <span data-ttu-id="604f3-116">Selecione **Estoque disponível**.</span><span class="sxs-lookup"><span data-stu-id="604f3-116">Select **On-hand inventory**.</span></span>
    4. <span data-ttu-id="604f3-117">Use o Filtro Rápido para localizar registros.</span><span class="sxs-lookup"><span data-stu-id="604f3-117">Use the Quick Filter to find records.</span></span> <span data-ttu-id="604f3-118">Por exemplo, filtro em um valor **1** para o campo **Local**.</span><span class="sxs-lookup"><span data-stu-id="604f3-118">For example, filter on a value of **1** for the **Site** field.</span></span>
    5. <span data-ttu-id="604f3-119">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="604f3-119">In the list, mark the selected row.</span></span>
    6. <span data-ttu-id="604f3-120">Valide se o valor do campo **Total disponível** é **411.0000000000000000**.</span><span class="sxs-lookup"><span data-stu-id="604f3-120">Validate that the value of the **Total available** field is **411.0000000000000000**.</span></span>

2. <span data-ttu-id="604f3-121">Salve a gravação da tarefas e anexe-a ao caso de teste no Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="604f3-121">Save the task recording and attach it to your test case in Azure Devops.</span></span>
3. <span data-ttu-id="604f3-122">Adicione o caso de teste ao plano de teste e carregue o caso de teste no RSAT.</span><span class="sxs-lookup"><span data-stu-id="604f3-122">Add the test case to the test plan, and load the test case into RSAT.</span></span>
4. <span data-ttu-id="604f3-123">Abra o arquivo de parâmetro do Excel.</span><span class="sxs-lookup"><span data-stu-id="604f3-123">Open the Excel parameter file.</span></span> <span data-ttu-id="604f3-124">Na guia **InventOnhandItem** , você verá uma seção **Validar InventOnhandItem** que contenha um campo **Operador** .</span><span class="sxs-lookup"><span data-stu-id="604f3-124">On the **InventOnhandItem** tab, you will see a **Validate InventOnhandItem** section that includes an **Operator** field.</span></span>

    ![Campo Operador](./media/use_rsa_tool_08.png)

5. <span data-ttu-id="604f3-126">Para validar se o estoque disponível sempre será maior que 0, altere o valor do campo **Valor** de **411** para **0** e o valor do campo **Operador** de um sinal de igual (**=**) para um sinal maior que (**\>**).</span><span class="sxs-lookup"><span data-stu-id="604f3-126">To validate whether the inventory on-hand will always be more than 0, change the value of the **Value** field from **411** to **0** and the value of the **Operator** field from an equal sign (**=**) to a greater than sign (**\>**).</span></span>

    ![Valores dos campos Valor e Operador alterados](./media/use_rsa_tool_09.png)

6. <span data-ttu-id="604f3-128">Salve e feche o arquivo de parâmetro do Excel.</span><span class="sxs-lookup"><span data-stu-id="604f3-128">Save and close the Excel parameter file.</span></span>
7. <span data-ttu-id="604f3-129">Selecione **Carregar** para salvar as alterações feitas no arquivo de parâmetros do Excel para o Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="604f3-129">Select **Upload** to save the changes that you made to the Excel parameter file to Azure DevOps.</span></span>

<span data-ttu-id="604f3-130">Agora, se o valor do campo **Total Disponível** para o item especificado no estoque for maior que 0 (zero), os testes serão aprovados, independentemente do valor do estoque disponível real.</span><span class="sxs-lookup"><span data-stu-id="604f3-130">Now, if the value of the **Total Available** field for the specified item in inventory is more than 0 (zero), tests will pass, regardless of the actual on-hand inventory value.</span></span>

### <a name="saved-variables-and-chaining-of-test-cases"></a><span data-ttu-id="604f3-131">Variáveis salvas e encadeamento de casos de teste</span><span class="sxs-lookup"><span data-stu-id="604f3-131">Saved variables and chaining of test cases</span></span>

<span data-ttu-id="604f3-132">Um dos principais recursos de RSAT é o encadeamento dos casos de teste, ou seja, a possibilidade de um teste passar variáveis para outros testes.</span><span class="sxs-lookup"><span data-stu-id="604f3-132">One of the key features of RSAT is the chaining of test cases, that is, the ability of a test to pass variables to other tests.</span></span> <span data-ttu-id="604f3-133">Para obter mais informações, consulte o artigo [Copiar variáveis para casos de teste de encadeamento](../../dev-itpro/perf-test/rsat/rsat-chain-test-cases.md).</span><span class="sxs-lookup"><span data-stu-id="604f3-133">For more information, see the article [Copy variables to chain test cases](../../dev-itpro/perf-test/rsat/rsat-chain-test-cases.md).</span></span>

### <a name="derived-test-case"></a><span data-ttu-id="604f3-134">Caso de teste derivado</span><span class="sxs-lookup"><span data-stu-id="604f3-134">Derived test case</span></span>

<span data-ttu-id="604f3-135">O RSAT permite usar a mesma gravação de tarefas com vários casos de teste, permitindo que uma tarefa seja executada com configurações de dados diferentes.</span><span class="sxs-lookup"><span data-stu-id="604f3-135">RSAT lets you use the same task recording with multiple test cases, enabling a task to run with different data configurations.</span></span> <span data-ttu-id="604f3-136">Consulte o artigo [Casos de teste derivados](../../dev-itpro/perf-test/rsat/rsat-derived-test-cases.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="604f3-136">See the article [Derived test cases](../../dev-itpro/perf-test/rsat/rsat-derived-test-cases.md) for more information.</span></span>

### <a name="validate-notifications-and-messages"></a><span data-ttu-id="604f3-137">Validar notificações e mensagens</span><span class="sxs-lookup"><span data-stu-id="604f3-137">Validate notifications and messages</span></span>

<span data-ttu-id="604f3-138">Esse recurso pode ser usado para validar se uma ação ocorreu.</span><span class="sxs-lookup"><span data-stu-id="604f3-138">This feature can be used to validate whether an action occurred.</span></span> <span data-ttu-id="604f3-139">Por exemplo, quando uma ordem de produção é criada, prevista e iniciada, o aplicativo mostra a mensagem "Produção - Início" para notificar que a ordem de produção foi iniciada.</span><span class="sxs-lookup"><span data-stu-id="604f3-139">For example, when a production order is created, estimated, and then started, the app shows a "Production – Start" message to notify you that the production order has been started.</span></span>

![Produção - Iniciar notificação](./media/use_rsa_tool_05.png)

<span data-ttu-id="604f3-141">Você pode validar essa mensagem através do RSAT inserindo o texto da mensagem na guia **MessageValidation** do arquivo de parâmetro do Excel para o registro apropriado.</span><span class="sxs-lookup"><span data-stu-id="604f3-141">You can validate this message through RSAT by entering the message text on the **MessageValidation** tab of the Excel parameter file for the appropriate recording.</span></span>

![Guia Validação da Mensagem](./media/use_rsa_tool_06.png)

<span data-ttu-id="604f3-143">Depois que o caso de teste for executado, a mensagem no arquivo de parâmetros do Excel será comparada à mensagem mostrada.</span><span class="sxs-lookup"><span data-stu-id="604f3-143">After the test case is run, the message in the Excel parameter file is compared to the message that is shown.</span></span> <span data-ttu-id="604f3-144">Se as mensagens não forem correspondentes, o caso de teste falhará.</span><span class="sxs-lookup"><span data-stu-id="604f3-144">If the messages don't match, the test case will fail.</span></span>

> [!NOTE]
> <span data-ttu-id="604f3-145">Você pode inserir mais de uma mensagem na guia **MessageValidation** do arquivo de parâmetro do Excel.</span><span class="sxs-lookup"><span data-stu-id="604f3-145">You can enter more than one message on the **MessageValidation** tab in the Excel parameter file.</span></span> <span data-ttu-id="604f3-146">As mensagens também podem ser de erro ou de advertência, em vez de mensagens informativas.</span><span class="sxs-lookup"><span data-stu-id="604f3-146">The messages also can be error or warning messages instead of informational messages.</span></span>

### <a name="snapshot"></a><span data-ttu-id="604f3-147">Instantâneo</span><span class="sxs-lookup"><span data-stu-id="604f3-147">Snapshot</span></span>

<span data-ttu-id="604f3-148">Esse recurso faz capturas de tela das etapas executadas durante a gravação de tarefas.</span><span class="sxs-lookup"><span data-stu-id="604f3-148">This feature takes screenshots of the steps that were performed during task recording.</span></span> <span data-ttu-id="604f3-149">É útil para fins de auditoria ou depuração.</span><span class="sxs-lookup"><span data-stu-id="604f3-149">It is useful for auditing or debugging purposes.</span></span>

- <span data-ttu-id="604f3-150">Para usar este recurso, abra o arquivo **Microsoft.Dynamics.RegressionSuite.WindowsApp.exe.config** na pasta de instalação do RSAT (por exemplo, **C:\\Arquivos de Programas (x86)\\Regression Suite Automation Tool**) e altere o valor do seguinte elemento de **falso** para **verdadeiro**.</span><span class="sxs-lookup"><span data-stu-id="604f3-150">To use this feature, open the **Microsoft.Dynamics.RegressionSuite.WindowsApp.exe.config** file under the RSAT installation folder (for example, **C:\\Program Files (x86)\\Regression Suite Automation Tool**), and change the value of the following element from **false** to **true**.</span></span>

    ```xml
    <add key="VerboseSnapshotsEnabled" value="false" />
    ```

<span data-ttu-id="604f3-151">Quando o caso de teste for executado, o RSAT gerará instantâneos (imagens) das etapas na pasta de reprodução dos casos de teste no diretório de trabalho.</span><span class="sxs-lookup"><span data-stu-id="604f3-151">When your run the test case, RSAT will generate snapshots (images) of the steps in the playback folder of the test cases in the working diretory.</span></span> <span data-ttu-id="604f3-152">Se você estiver usando uma versão mais antiga do RSAT, as imagens serão salvas em **C:\\Users\\\<Username\>\\AppData\\Roaming\\regressionTool\\playback** e uma pasta separada é criada para cada caso de teste executado.</span><span class="sxs-lookup"><span data-stu-id="604f3-152">If you are using an older version of RSAT, the images are saved to **C:\\Users\\\<Username\>\\AppData\\Roaming\\regressionTool\\playback**, a separate folder is created for each test case that is run.</span></span>

## <a name="assignment"></a><span data-ttu-id="604f3-153">Atribuição</span><span class="sxs-lookup"><span data-stu-id="604f3-153">Assignment</span></span>

### <a name="scenario"></a><span data-ttu-id="604f3-154">Cenário</span><span class="sxs-lookup"><span data-stu-id="604f3-154">Scenario</span></span>

1. <span data-ttu-id="604f3-155">O designer de produtos cria um novo produto liberado.</span><span class="sxs-lookup"><span data-stu-id="604f3-155">The product designer creates a new released product.</span></span>
2. <span data-ttu-id="604f3-156">O gerente de produção inicia uma ordem de produção para deixar o nível de estoque com duas peças.</span><span class="sxs-lookup"><span data-stu-id="604f3-156">The production manager initiates a production order to bring the stock level to two pieces.</span></span>
3. <span data-ttu-id="604f3-157">A fabricação inicia e termina a ordem de produção e verifica se a quantidade disponível está com duas peças.</span><span class="sxs-lookup"><span data-stu-id="604f3-157">Manufacturing starts and ends the production order, and verifies that the on-hand quantity is two pieces.</span></span>
4. <span data-ttu-id="604f3-158">A equipe de venda recebe um pedido de quatro peças do novo produto.</span><span class="sxs-lookup"><span data-stu-id="604f3-158">The sales team receives an order for four pieces of the new product.</span></span> <span data-ttu-id="604f3-159">Portanto, a equipe de vendas atualiza os requisitos líquidos através do plano dinâmico.</span><span class="sxs-lookup"><span data-stu-id="604f3-159">Therefore, the sales team updates the net requirements via the dynamic plan.</span></span> <span data-ttu-id="604f3-160">Como nenhuma capacidade adicional está disponível, a política de ordem padrão é definida como "comprar em vez de fazer".</span><span class="sxs-lookup"><span data-stu-id="604f3-160">Because no additional capacity is available, the default order policy is set to "buy instead of make."</span></span> <span data-ttu-id="604f3-161">Portanto, uma ordem de compra planejada é criada.</span><span class="sxs-lookup"><span data-stu-id="604f3-161">Therefore, a planned purchase order is created.</span></span>
5. <span data-ttu-id="604f3-162">O comprador adiciona um fornecedor, firma a ordem de compra planejada e confirma a ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="604f3-162">The buyer adds a vendor, firms the planned purchase order, and then confirms the purchase order.</span></span>
6. <span data-ttu-id="604f3-163">Quando as mercadorias que foram compradas chegam na loja, o operador da loja pesquisa a ordem de compra relacionada e recebe as mercadorias.</span><span class="sxs-lookup"><span data-stu-id="604f3-163">When the goods that were purchased arrive at the store, the store operator searches the related purchase order and receives the goods.</span></span> <span data-ttu-id="604f3-164">Como a ordem agora está concluída, as mercadorias podem ser separadas e embaladas conforme a ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="604f3-164">Because the order is now completed, goods can be picked and packed against the sales order.</span></span>
7. <span data-ttu-id="604f3-165">O financeiro lança a fatura de compras e a fatura de vendas.</span><span class="sxs-lookup"><span data-stu-id="604f3-165">Finance posts the purchase invoice and sales invoice.</span></span>

<span data-ttu-id="604f3-166">A ilustração a seguir mostra o fluxo para esse cenário.</span><span class="sxs-lookup"><span data-stu-id="604f3-166">The following illustration shows the flow for this scenario.</span></span>

![Fluxo do cenário de demonstração](./media/use_rsa_tool_14.png)

<span data-ttu-id="604f3-168">A ilustração a seguir mostra a hierarquia de processos comerciais para esse cenário no LCS Business Process Modeler.</span><span class="sxs-lookup"><span data-stu-id="604f3-168">The following illustration shows the business processes hierarchy for this scenario in the LCS Business Process Modeler.</span></span>

![Processos empresariais do cenário de demonstração](./media/use_rsa_tool_15.png)

## <a name="strategy--key-learning"></a><span data-ttu-id="604f3-170">Estratégia – Aprendizagem principal</span><span class="sxs-lookup"><span data-stu-id="604f3-170">Strategy – Key learning</span></span>

### <a name="data"></a><span data-ttu-id="604f3-171">Dados</span><span class="sxs-lookup"><span data-stu-id="604f3-171">Data</span></span>

- <span data-ttu-id="604f3-172">Verifique se você tem volumes de dados representativos (uma cópia da produção/dados de configuração dourada mais dados migrados).</span><span class="sxs-lookup"><span data-stu-id="604f3-172">Make sure that you have representative data volumes (a copy of production/golden configuration data plus migrated data).</span></span>
- <span data-ttu-id="604f3-173">Ao gerar novos dados por meio do gravador de tarefas, cria nomes de teste que não irão entrar em conflito com os nomes existentes (por exemplo, usar um prefixo como **RSATxxx**).</span><span class="sxs-lookup"><span data-stu-id="604f3-173">When you generate new data via Task recorder, create test names that won't conflict with existing names (for example, use a prefix such as **RSATxxx**).</span></span>
- <span data-ttu-id="604f3-174">Use a restauração pontual do Azure para reexecutar testes nos ambientes que não estão na Camada 1.</span><span class="sxs-lookup"><span data-stu-id="604f3-174">Use Azure Point-In-Time restore to rerun tests in non-Tier 1 environments.</span></span>
- <span data-ttu-id="604f3-175">Embora você possa usar as funções **RANDOM** e **NOW** do Excel para gerar uma combinação exclusiva, o esforço é consideravelmente alto.</span><span class="sxs-lookup"><span data-stu-id="604f3-175">Although you can use the **RANDOM** and **NOW** Excel functions to generate a unique combination, the effort is considerably high.</span></span> <span data-ttu-id="604f3-176">Veja aqui um exemplo.</span><span class="sxs-lookup"><span data-stu-id="604f3-176">Here is an example.</span></span>

    ```Excel
    product = "AT" &TEXT(NOW(),"yyymmddhhmm")
    ```

### <a name="task-recorder"></a><span data-ttu-id="604f3-177">Gravador de Tarefas</span><span class="sxs-lookup"><span data-stu-id="604f3-177">Task recorder</span></span>

- <span data-ttu-id="604f3-178">Definir cenários antes de iniciar a gravação.</span><span class="sxs-lookup"><span data-stu-id="604f3-178">Define scenarios before you start recording.</span></span> <span data-ttu-id="604f3-179">Um projeto bem gerenciado tem cenários de teste predefinidos.</span><span class="sxs-lookup"><span data-stu-id="604f3-179">A well-managed project has predefined test scenarios.</span></span> <span data-ttu-id="604f3-180">Para criar um caso de teste, considere como é previsível o resultado desses cenários de teste.</span><span class="sxs-lookup"><span data-stu-id="604f3-180">To build a test case, consider how predictable the outcome of those test scenarios is.</span></span>
- <span data-ttu-id="604f3-181">Divida as gravações, se forem executadas por diferentes funções, ou se houver tempo de espera ou um evento externo antes da próxima etapa.</span><span class="sxs-lookup"><span data-stu-id="604f3-181">Split recordings if they are performed by different roles, or if there is waiting time or an external event before the next step.</span></span>
- <span data-ttu-id="604f3-182">Evite selecionar valores nas listas.</span><span class="sxs-lookup"><span data-stu-id="604f3-182">Avoid selecting values in lists.</span></span> <span data-ttu-id="604f3-183">Em vez disso, use formatos de texto, como **PEPS**, **AudioRM** e **SiteWH**.</span><span class="sxs-lookup"><span data-stu-id="604f3-183">Instead, use text formats, such as **FIFO**, **AudioRM**, and **SiteWH**.</span></span> <span data-ttu-id="604f3-184">Quando você seleciona em uma lista, a posição do valor na lista é registrada, não o valor em si.</span><span class="sxs-lookup"><span data-stu-id="604f3-184">When you select in a list, the position of the value in the list is recorded, not the value itself.</span></span> <span data-ttu-id="604f3-185">Se itens forem adicionados a essa lista, a posição do valor pode mudar.</span><span class="sxs-lookup"><span data-stu-id="604f3-185">If items are added to that list, the position of the value can change.</span></span> <span data-ttu-id="604f3-186">Portanto, sua gravação usará um parâmetro diferente e o restante de cenário poderá ser afetado.</span><span class="sxs-lookup"><span data-stu-id="604f3-186">Therefore, your recording will use a different parameter, and the rest of the scenario might be affected.</span></span>
- <span data-ttu-id="604f3-187">Pense sobre o comportamento de vários usuários.</span><span class="sxs-lookup"><span data-stu-id="604f3-187">Think about multi-user behavior.</span></span> <span data-ttu-id="604f3-188">Por exemplo, não presuma que sua ordem de venda recém-criada será sempre selecionada automaticamente.</span><span class="sxs-lookup"><span data-stu-id="604f3-188">For example, don't assume that your newly created sales order will always be automatically selected.</span></span> <span data-ttu-id="604f3-189">Em vez disso, sempre use o filtro para localizar a ordem correta.</span><span class="sxs-lookup"><span data-stu-id="604f3-189">Instead, always use the filter to find the correct order.</span></span>
- <span data-ttu-id="604f3-190">Use a função Copiar no gravador de tarefas para salvar o nome de um produto recém-criado, de forma que ele possa ser usado em casos de teste encadeados.</span><span class="sxs-lookup"><span data-stu-id="604f3-190">Use the Copy function in Task recorder to save the name of a newly created product so it can be used in chained test cases.</span></span>
- <span data-ttu-id="604f3-191">Use a função Validar no gravador de tarefas para definir pontos de verificação que detectam se as etapas foram executadas corretamente.</span><span class="sxs-lookup"><span data-stu-id="604f3-191">Use the Validate function in Task recorder to set checkpoints that verify that steps have been run correctly.</span></span>

### <a name="rsat"></a><span data-ttu-id="604f3-192">RSAT</span><span class="sxs-lookup"><span data-stu-id="604f3-192">RSAT</span></span>

- <span data-ttu-id="604f3-193">Para executar o teste em outra empresa, você pode alterar a empresa na guia **Geral** do arquivo de parâmetro do Excel.</span><span class="sxs-lookup"><span data-stu-id="604f3-193">To run the test in another company, you can change the company on the **General** tab of the Excel parameter file.</span></span> <span data-ttu-id="604f3-194">Verifique se as configurações e os dados estão disponíveis na empresa selecionada recentemente.</span><span class="sxs-lookup"><span data-stu-id="604f3-194">Make sure that settings and data are available in the newly selected company.</span></span>
- <span data-ttu-id="604f3-195">Você pode alterar o usuário do teste na guia **Geral** do arquivo de parâmetros do Excel.</span><span class="sxs-lookup"><span data-stu-id="604f3-195">You can change the test user on the **General** tab of the Excel parameter file.</span></span> <span data-ttu-id="604f3-196">Especifique a ID de email do usuário que executará o caso de teste.</span><span class="sxs-lookup"><span data-stu-id="604f3-196">Specify the email ID of the user who will run the test case.</span></span> <span data-ttu-id="604f3-197">Dessa forma, o caso de teste pode ser executado usando as permissões de segurança do usuário especificado.</span><span class="sxs-lookup"><span data-stu-id="604f3-197">In this way, the test case can be run by using the security permissions of the specified user.</span></span>
- <span data-ttu-id="604f3-198">Para aguardar antes de iniciar o teste, você pode definir uma pausa na guia **Geral** do arquivo de parâmetros do Excel.</span><span class="sxs-lookup"><span data-stu-id="604f3-198">To wait before the test is started, you can define a pause on the **General** tab of the Excel parameter file.</span></span> <span data-ttu-id="604f3-199">Esta pausa pode ser usada em um trabalho em lotes (por exemplo, se um fluxo de trabalho tiver que ser executado antes da próxima etapa ser executada).</span><span class="sxs-lookup"><span data-stu-id="604f3-199">This pause can be used in a batch job (for example, if a workflow must be run before the next step can be performed.)</span></span>

## <a name="advanced-scripting"></a><span data-ttu-id="604f3-200">Script avançado</span><span class="sxs-lookup"><span data-stu-id="604f3-200">Advanced scripting</span></span>

### <a name="cli"></a><span data-ttu-id="604f3-201">CLI</span><span class="sxs-lookup"><span data-stu-id="604f3-201">CLI</span></span>

<span data-ttu-id="604f3-202">O RSAT pode ser chamado de uma janela do **Prompt de Comando** ou **PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="604f3-202">RSAT can be called from a **Command Prompt** or **PowerShell** window.</span></span>

> [!NOTE]
> <span data-ttu-id="604f3-203">Verifique se a variável de ambiente **TestRoot** está definida para o caminho de instalação de RSAT.</span><span class="sxs-lookup"><span data-stu-id="604f3-203">Verify that the **TestRoot** environment variable is set to the RSAT installation path.</span></span> <span data-ttu-id="604f3-204">(No Microsoft Windows, abra **Painel de Controle**, selecione **Sistema e segurança \> Sistema \> Configurações avançadas do sistema**, e **Variáveis de Ambiente**).</span><span class="sxs-lookup"><span data-stu-id="604f3-204">(In Microsoft Windows, open **Control Panel**, select **System and Security \> System \> Advanced system settings**, and then select **Environment Variables**.)</span></span>

1. <span data-ttu-id="604f3-205">Abra uma janela do **Prompt de Comando** ou **PowerShell** como um administrador.</span><span class="sxs-lookup"><span data-stu-id="604f3-205">Open a **Command Prompt** or **PowerShell** window as an admin.</span></span>
2. <span data-ttu-id="604f3-206">Navegue até o diretório de instalação do RSAT.</span><span class="sxs-lookup"><span data-stu-id="604f3-206">Navigate to the RSAT installation directory.</span></span>

    ```Console
    cd "c:\Program Files (x86)\Regression Suite Automation Tool\"
    ```

3. <span data-ttu-id="604f3-207">Liste todos os comandos.</span><span class="sxs-lookup"><span data-stu-id="604f3-207">List all commands.</span></span>

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

#### <a name=""></a><span data-ttu-id="604f3-208">?</span><span class="sxs-lookup"><span data-stu-id="604f3-208">?</span></span> 
<span data-ttu-id="604f3-209">Mostra a ajuda sobre todos os comandos disponíveis e seus parâmetros.</span><span class="sxs-lookup"><span data-stu-id="604f3-209">Shows help about all available commands and their parameters.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``?``**``[command]``

##### <a name="optional-parameters"></a><span data-ttu-id="604f3-210">Parâmetros opcionais</span><span class="sxs-lookup"><span data-stu-id="604f3-210">Optional parameters</span></span>

**``command``**


<span data-ttu-id="604f3-211">Onde ``[command]`` é um dos comandos especificados abaixo.</span><span class="sxs-lookup"><span data-stu-id="604f3-211">Where ``[command]`` is one of the commands specified below.</span></span>


#### <a name="about"></a><span data-ttu-id="604f3-212">sobre</span><span class="sxs-lookup"><span data-stu-id="604f3-212">about</span></span>
<span data-ttu-id="604f3-213">Exibe a versão atual.</span><span class="sxs-lookup"><span data-stu-id="604f3-213">Displays the current version.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``about``**

#### <a name="cls"></a><span data-ttu-id="604f3-214">cls</span><span class="sxs-lookup"><span data-stu-id="604f3-214">cls</span></span>
<span data-ttu-id="604f3-215">Limpa a tela.</span><span class="sxs-lookup"><span data-stu-id="604f3-215">Clears the screen.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``cls``**


#### <a name="download"></a><span data-ttu-id="604f3-216">fazer download</span><span class="sxs-lookup"><span data-stu-id="604f3-216">download</span></span>
<span data-ttu-id="604f3-217">Baixa anexos para o caso de teste especificado no diretório de saída.</span><span class="sxs-lookup"><span data-stu-id="604f3-217">Downloads attachments for the specified test case to the output directory.</span></span> <span data-ttu-id="604f3-218">Você pode usar o comando ``list`` para obter todos os casos de teste disponíveis.</span><span class="sxs-lookup"><span data-stu-id="604f3-218">You can use the ``list`` command to get all available test cases.</span></span> <span data-ttu-id="604f3-219">Use qualquer valor da primeira coluna como um parâmetro **test_case_id**.</span><span class="sxs-lookup"><span data-stu-id="604f3-219">Use any value from the first column as a **test_case_id** parameter.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``download``**``[test_case_id] [output_dir]``

##### <a name="required-parameters"></a><span data-ttu-id="604f3-220">Parâmetros obrigatórios</span><span class="sxs-lookup"><span data-stu-id="604f3-220">Required parameters</span></span>
<span data-ttu-id="604f3-221">**``test_case_id``** Representa a ID do caso de teste.</span><span class="sxs-lookup"><span data-stu-id="604f3-221">**``test_case_id``** Represents the test case ID.</span></span>  
<span data-ttu-id="604f3-222">**``output_dir``** Representa o diretório de saída.</span><span class="sxs-lookup"><span data-stu-id="604f3-222">**``output_dir``** Represents the output directory.</span></span> <span data-ttu-id="604f3-223">O diretório deve existir.</span><span class="sxs-lookup"><span data-stu-id="604f3-223">The directory must exist.</span></span>

##### <a name="examples"></a><span data-ttu-id="604f3-224">Exemplos</span><span class="sxs-lookup"><span data-stu-id="604f3-224">Examples</span></span>

``download 123 c:\temp\rsat``   
``download 765 c:\rsat\last``


#### <a name="edit"></a><span data-ttu-id="604f3-225">editar</span><span class="sxs-lookup"><span data-stu-id="604f3-225">edit</span></span>
<span data-ttu-id="604f3-226">Permite abrir o arquivo de parâmetros no programa Excel e editá-lo.</span><span class="sxs-lookup"><span data-stu-id="604f3-226">Allows you to open parameters file in Excel program and edit it.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``edit``**``[excel_file]``

##### <a name="required-parameters"></a><span data-ttu-id="604f3-227">Parâmetros obrigatórios</span><span class="sxs-lookup"><span data-stu-id="604f3-227">Required parameters</span></span>
<span data-ttu-id="604f3-228">**``excel_file``** Deve conter um caminho completo para um arquivo existente do Excel.</span><span class="sxs-lookup"><span data-stu-id="604f3-228">**``excel_file``** Must contain a full path to an existing Excel file.</span></span>

##### <a name="examples"></a><span data-ttu-id="604f3-229">Exemplos</span><span class="sxs-lookup"><span data-stu-id="604f3-229">Examples</span></span>
``edit c:\RSAT\TestCase_123_Base.xlsx``  
``edit e:\temp\TestCase_456_Base.xlsx``


#### <a name="generate"></a><span data-ttu-id="604f3-230">gerar</span><span class="sxs-lookup"><span data-stu-id="604f3-230">generate</span></span>
<span data-ttu-id="604f3-231">Gera arquivos de execução e parâmetro de teste para o caso de teste especificado no diretório de saída.</span><span class="sxs-lookup"><span data-stu-id="604f3-231">Generates test execution and parameter files for the specified test case in the output directory.</span></span>
<span data-ttu-id="604f3-232">Você pode usar o comando ``list`` para obter todos os casos de teste disponíveis.</span><span class="sxs-lookup"><span data-stu-id="604f3-232">You can use the ``list`` command to get all available test cases.</span></span> <span data-ttu-id="604f3-233">Use qualquer valor da primeira coluna como um parâmetro **test_case_id**.</span><span class="sxs-lookup"><span data-stu-id="604f3-233">Use any value from the first column as a **test_case_id** parameter.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``generate``**``[test_case_id] [output_dir]``

##### <a name="required-parameters"></a><span data-ttu-id="604f3-234">Parâmetros obrigatórios</span><span class="sxs-lookup"><span data-stu-id="604f3-234">Required parameters</span></span>
<span data-ttu-id="604f3-235">**``test_case_id``** Representa a ID do caso de teste.</span><span class="sxs-lookup"><span data-stu-id="604f3-235">**``test_case_id``** Represents the test case ID.</span></span>  
<span data-ttu-id="604f3-236">**``output_dir``** Representa o diretório de saída.</span><span class="sxs-lookup"><span data-stu-id="604f3-236">**``output_dir``** Represents the output directory.</span></span> <span data-ttu-id="604f3-237">O diretório deve existir.</span><span class="sxs-lookup"><span data-stu-id="604f3-237">The directory must exist.</span></span>

##### <a name="examples"></a><span data-ttu-id="604f3-238">Exemplos</span><span class="sxs-lookup"><span data-stu-id="604f3-238">Examples</span></span>
``generate 123 c:\temp\rsat``  
``generate 765 c:\rsat\last``


#### <a name="generatederived"></a><span data-ttu-id="604f3-239">generatederived</span><span class="sxs-lookup"><span data-stu-id="604f3-239">generatederived</span></span>
<span data-ttu-id="604f3-240">Gera um novo caso de teste, derivado do caso de teste fornecido.</span><span class="sxs-lookup"><span data-stu-id="604f3-240">Generates a new test case, derived from the provided test case.</span></span> <span data-ttu-id="604f3-241">Você pode usar o comando ``list`` para obter todos os casos de teste disponíveis.</span><span class="sxs-lookup"><span data-stu-id="604f3-241">You can use the ``list`` command to get all available test cases.</span></span> <span data-ttu-id="604f3-242">Use qualquer valor da primeira coluna como um parâmetro **test_case_id**.</span><span class="sxs-lookup"><span data-stu-id="604f3-242">Use any value from the first column as a **test_case_id** parameter.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``generatederived``**``[parent_test_case_id] [test_plan_id] [test_suite_id]``

##### <a name="required-parameters"></a><span data-ttu-id="604f3-243">Parâmetros obrigatórios</span><span class="sxs-lookup"><span data-stu-id="604f3-243">Required parameters</span></span>
<span data-ttu-id="604f3-244">**``parent_test_case_id``** Representa a ID do caso de teste pai.</span><span class="sxs-lookup"><span data-stu-id="604f3-244">**``parent_test_case_id``** Represents the parent test case ID.</span></span>  
<span data-ttu-id="604f3-245">**``test_plan_id``** Representa a ID do plano de teste.</span><span class="sxs-lookup"><span data-stu-id="604f3-245">**``test_plan_id``** Represents the test plan ID.</span></span>  
<span data-ttu-id="604f3-246">**``test_suite_id``** Representa a ID do pacote de teste.</span><span class="sxs-lookup"><span data-stu-id="604f3-246">**``test_suite_id``** Represents the test suite ID.</span></span>

##### <a name="examples"></a><span data-ttu-id="604f3-247">Exemplos</span><span class="sxs-lookup"><span data-stu-id="604f3-247">Examples</span></span>
``generatederived 123 8901 678``


#### <a name="generatetestonly"></a><span data-ttu-id="604f3-248">generatetestonly</span><span class="sxs-lookup"><span data-stu-id="604f3-248">generatetestonly</span></span>
<span data-ttu-id="604f3-249">Gera somente o arquivo de execução de teste para o caso de teste especificado no diretório de saída.</span><span class="sxs-lookup"><span data-stu-id="604f3-249">Generates only test execution file for the specified test case in the output directory.</span></span> <span data-ttu-id="604f3-250">Você pode usar o comando ``list`` para obter todos os casos de teste disponíveis.</span><span class="sxs-lookup"><span data-stu-id="604f3-250">You can use the ``list`` command to get all available test cases.</span></span> <span data-ttu-id="604f3-251">Use qualquer valor da primeira coluna como um parâmetro **test_case_id**.</span><span class="sxs-lookup"><span data-stu-id="604f3-251">Use any value from the first column as a **test_case_id** parameter.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``generatetestonly``**``[test_case_id] [output_dir]``

##### <a name="required-parameters"></a><span data-ttu-id="604f3-252">Parâmetros obrigatórios</span><span class="sxs-lookup"><span data-stu-id="604f3-252">Required parameters</span></span>
<span data-ttu-id="604f3-253">**``test_case_id``** Representa a ID do caso de teste.</span><span class="sxs-lookup"><span data-stu-id="604f3-253">**``test_case_id``** Represents the test case ID.</span></span>  
<span data-ttu-id="604f3-254">**``output_dir``** Representa o diretório de saída.</span><span class="sxs-lookup"><span data-stu-id="604f3-254">**``output_dir``** Represents the output directory.</span></span> <span data-ttu-id="604f3-255">O diretório deve existir.</span><span class="sxs-lookup"><span data-stu-id="604f3-255">The directory must exist.</span></span>

##### <a name="examples"></a><span data-ttu-id="604f3-256">Exemplos</span><span class="sxs-lookup"><span data-stu-id="604f3-256">Examples</span></span>
``generatetestonly 123 c:\temp\rsat``  
``generatetestonly 765 c:\rsat\last``


#### <a name="generatetestsuite"></a><span data-ttu-id="604f3-257">generatetestsuite</span><span class="sxs-lookup"><span data-stu-id="604f3-257">generatetestsuite</span></span>
<span data-ttu-id="604f3-258">Gera todos os casos de teste para o conjunto especificado no diretório de saída.</span><span class="sxs-lookup"><span data-stu-id="604f3-258">Generates all test cases for the specified suite in the output directory.</span></span>
<span data-ttu-id="604f3-259">Você pode usar o comando ``listtestsuitenames`` para obter todos os pacotes de teste disponíveis.</span><span class="sxs-lookup"><span data-stu-id="604f3-259">You can use ``listtestsuitenames`` command to get all available test suits.</span></span> <span data-ttu-id="604f3-260">Use qualquer valor da coluna como um parâmetro **test_suite_name**.</span><span class="sxs-lookup"><span data-stu-id="604f3-260">Use any value from the column as a **test_suite_name** parameter.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``generatetestsuite``**``[test_suite_name] [output_dir]``

##### <a name="required-parameters"></a><span data-ttu-id="604f3-261">Parâmetros obrigatórios</span><span class="sxs-lookup"><span data-stu-id="604f3-261">Required parameters</span></span>
<span data-ttu-id="604f3-262">**``test_suite_name``** Representa o nome do pacote de teste.</span><span class="sxs-lookup"><span data-stu-id="604f3-262">**``test_suite_name``** Represents the test suite name.</span></span>  
<span data-ttu-id="604f3-263">**``output_dir``** Representa o diretório de saída.</span><span class="sxs-lookup"><span data-stu-id="604f3-263">**``output_dir``** Represents the output directory.</span></span> <span data-ttu-id="604f3-264">O diretório deve existir.</span><span class="sxs-lookup"><span data-stu-id="604f3-264">The directory must exist.</span></span>

##### <a name="examples"></a><span data-ttu-id="604f3-265">Exemplos</span><span class="sxs-lookup"><span data-stu-id="604f3-265">Examples</span></span>
``generatetestsuite Tests c:\temp\rsat``   
``generatetestsuite Purchase c:\rsat\last``


#### <a name="help"></a><span data-ttu-id="604f3-266">ajuda</span><span class="sxs-lookup"><span data-stu-id="604f3-266">help</span></span>
<span data-ttu-id="604f3-267">Idêntico ao [?](#section)</span><span class="sxs-lookup"><span data-stu-id="604f3-267">Identical to the [?](#section)</span></span> <span data-ttu-id="604f3-268">comando</span><span class="sxs-lookup"><span data-stu-id="604f3-268">command</span></span>


#### <a name="list"></a><span data-ttu-id="604f3-269">lista</span><span class="sxs-lookup"><span data-stu-id="604f3-269">list</span></span>
<span data-ttu-id="604f3-270">Lista todos os casos de teste disponíveis.</span><span class="sxs-lookup"><span data-stu-id="604f3-270">Lists all available test cases.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``list``**


#### <a name="listtestplans"></a><span data-ttu-id="604f3-271">listtestplans</span><span class="sxs-lookup"><span data-stu-id="604f3-271">listtestplans</span></span>
<span data-ttu-id="604f3-272">Lista todos os planos de teste disponíveis.</span><span class="sxs-lookup"><span data-stu-id="604f3-272">Lists all available test plans.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``listtestplans``**


#### <a name="listtestsuite"></a><span data-ttu-id="604f3-273">listtestsuite</span><span class="sxs-lookup"><span data-stu-id="604f3-273">listtestsuite</span></span>
<span data-ttu-id="604f3-274">Lista casos de teste para o pacote de teste especificado.</span><span class="sxs-lookup"><span data-stu-id="604f3-274">Lists test cases for the specified test suite.</span></span> <span data-ttu-id="604f3-275">Você pode usar o comando ``listtestsuitenames`` para obter todos os pacotes de teste disponíveis.</span><span class="sxs-lookup"><span data-stu-id="604f3-275">You can use ``listtestsuitenames`` command to get all available test suites.</span></span> <span data-ttu-id="604f3-276">Use qualquer valor da primeira coluna como parâmetro **suite_name**.</span><span class="sxs-lookup"><span data-stu-id="604f3-276">Use any value from first column as **suite_name** parameter.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``listtestsuite``**``[suite_name]``

##### <a name="required-parameters"></a><span data-ttu-id="604f3-277">Parâmetros obrigatórios</span><span class="sxs-lookup"><span data-stu-id="604f3-277">Required parameters</span></span>
<span data-ttu-id="604f3-278">**``suite_name``** Nome do pacote desejado.</span><span class="sxs-lookup"><span data-stu-id="604f3-278">**``suite_name``** Name of the desired suite.</span></span>

##### <a name="examples"></a><span data-ttu-id="604f3-279">Exemplos</span><span class="sxs-lookup"><span data-stu-id="604f3-279">Examples</span></span>
``listtestsuite "sample suite name"``  
``listtestsuite NameOfTheSuite``


#### <a name="listtestsuitenames"></a><span data-ttu-id="604f3-280">listtestsuitenames</span><span class="sxs-lookup"><span data-stu-id="604f3-280">listtestsuitenames</span></span>
<span data-ttu-id="604f3-281">Lista todos os pacotes de teste disponíveis.</span><span class="sxs-lookup"><span data-stu-id="604f3-281">Lists all available test suites.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``listtestsuitenames``**


#### <a name="playback"></a><span data-ttu-id="604f3-282">reprodução</span><span class="sxs-lookup"><span data-stu-id="604f3-282">playback</span></span>
<span data-ttu-id="604f3-283">Reproduz um caso de teste usando um arquivo do Excel.</span><span class="sxs-lookup"><span data-stu-id="604f3-283">Plays back a test case using an Excel file.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``playback``**``[excel_file]``

##### <a name="required-parameters"></a><span data-ttu-id="604f3-284">Parâmetros obrigatórios</span><span class="sxs-lookup"><span data-stu-id="604f3-284">Required parameters</span></span>
<span data-ttu-id="604f3-285">**``excel_file``** Um caminho completo para o arquivo do Excel.</span><span class="sxs-lookup"><span data-stu-id="604f3-285">**``excel_file``** A full path to the Excel file.</span></span> <span data-ttu-id="604f3-286">O arquivo deve existir.</span><span class="sxs-lookup"><span data-stu-id="604f3-286">File must exist.</span></span> 

##### <a name="examples"></a><span data-ttu-id="604f3-287">Exemplos</span><span class="sxs-lookup"><span data-stu-id="604f3-287">Examples</span></span>
``
playback c:\RSAT\TestCaseParameters\sample1.xlsx
playback e:\temp\test.xlsx
``


#### <a name="playbackbyid"></a><span data-ttu-id="604f3-288">playbackbyid</span><span class="sxs-lookup"><span data-stu-id="604f3-288">playbackbyid</span></span>
<span data-ttu-id="604f3-289">Reproduz vários casos de teste de uma só vez.</span><span class="sxs-lookup"><span data-stu-id="604f3-289">Plays back multiple test cases at once.</span></span>
<span data-ttu-id="604f3-290">Você pode usar o comando ``list`` para obter todos os casos de teste disponíveis.</span><span class="sxs-lookup"><span data-stu-id="604f3-290">You can use the ``list`` command to get all available test cases.</span></span> <span data-ttu-id="604f3-291">Use qualquer valor da primeira coluna como um parâmetro **test_case_id**.</span><span class="sxs-lookup"><span data-stu-id="604f3-291">Use any value from the first column as a **test_case_id** parameter.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``playbackbyid``**``[test_case_id1] [test_case_id2] ... [test_case_idN]``

##### <a name="required-parameters"></a><span data-ttu-id="604f3-292">Parâmetros obrigatórios</span><span class="sxs-lookup"><span data-stu-id="604f3-292">Required parameters</span></span>
<span data-ttu-id="604f3-293">**``test_case_id1``** ID do caso de teste existente.</span><span class="sxs-lookup"><span data-stu-id="604f3-293">**``test_case_id1``** ID of exisiting test case.</span></span>  
<span data-ttu-id="604f3-294">**``test_case_id2``** ID do caso de teste existente.</span><span class="sxs-lookup"><span data-stu-id="604f3-294">**``test_case_id2``** ID of exisiting test case.</span></span>  
<span data-ttu-id="604f3-295">**``test_case_idN``** ID do caso de teste existente.</span><span class="sxs-lookup"><span data-stu-id="604f3-295">**``test_case_idN``** ID of exisiting test case.</span></span>  

##### <a name="examples"></a><span data-ttu-id="604f3-296">Exemplos</span><span class="sxs-lookup"><span data-stu-id="604f3-296">Examples</span></span>
``playbackbyid 878``  
``playbackbyid 2345 667 135``


#### <a name="playbackmany"></a><span data-ttu-id="604f3-297">playbackmany</span><span class="sxs-lookup"><span data-stu-id="604f3-297">playbackmany</span></span>
<span data-ttu-id="604f3-298">Reproduz muitos casos de teste de uma só vez, usando arquivos do Excel.</span><span class="sxs-lookup"><span data-stu-id="604f3-298">Plays back many test cases at once, using Excel files.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``playbackmany``**``[excel_file1] [excel_file2] ... [excel_fileN]``

##### <a name="required-parameters"></a><span data-ttu-id="604f3-299">Parâmetros obrigatórios</span><span class="sxs-lookup"><span data-stu-id="604f3-299">Required parameters</span></span>
<span data-ttu-id="604f3-300">**``excel_file1``** Caminho completo para o arquivo do Excel.</span><span class="sxs-lookup"><span data-stu-id="604f3-300">**``excel_file1``** Full path to the Excel file.</span></span> <span data-ttu-id="604f3-301">O arquivo deve existir.</span><span class="sxs-lookup"><span data-stu-id="604f3-301">File must exist.</span></span>  
<span data-ttu-id="604f3-302">**``excel_file2``** Caminho completo para o arquivo do Excel.</span><span class="sxs-lookup"><span data-stu-id="604f3-302">**``excel_file2``** Full path to the Excel file.</span></span> <span data-ttu-id="604f3-303">O arquivo deve existir.</span><span class="sxs-lookup"><span data-stu-id="604f3-303">File must exist.</span></span>  
<span data-ttu-id="604f3-304">**``excel_fileN``** Caminho completo para o arquivo do Excel.</span><span class="sxs-lookup"><span data-stu-id="604f3-304">**``excel_fileN``** Full path to the Excel file.</span></span> <span data-ttu-id="604f3-305">O arquivo deve existir.</span><span class="sxs-lookup"><span data-stu-id="604f3-305">File must exist.</span></span>  

##### <a name="examples"></a><span data-ttu-id="604f3-306">Exemplos</span><span class="sxs-lookup"><span data-stu-id="604f3-306">Examples</span></span>
``playbackmany c:\RSAT\TestCaseParameters\param1.xlsx``  
``playbackmany e:\temp\test.xlsx f:\rsat\sample1.xlsx c:\RSAT\sample2.xlsx``


#### <a name="playbacksuite"></a><span data-ttu-id="604f3-307">playbacksuite</span><span class="sxs-lookup"><span data-stu-id="604f3-307">playbacksuite</span></span>
<span data-ttu-id="604f3-308">Reproduz todos os casos de teste do pacote de teste especificado.</span><span class="sxs-lookup"><span data-stu-id="604f3-308">Plays back all test cases from the specified test suite.</span></span> <span data-ttu-id="604f3-309">Você pode usar o comando ``listtestsuitenames`` para obter todos os pacotes de teste disponíveis.</span><span class="sxs-lookup"><span data-stu-id="604f3-309">You can use ``listtestsuitenames`` command to get all available test suites.</span></span> <span data-ttu-id="604f3-310">Use qualquer valor da primeira coluna como parâmetro **suite_name**.</span><span class="sxs-lookup"><span data-stu-id="604f3-310">Use any value from first column as **suite_name** parameter.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``playbacksuite``**``[suite_name]``

##### <a name="required-parameters"></a><span data-ttu-id="604f3-311">Parâmetros obrigatórios</span><span class="sxs-lookup"><span data-stu-id="604f3-311">Required parameters</span></span>
<span data-ttu-id="604f3-312">**``suite_name``** Nome do pacote desejado.</span><span class="sxs-lookup"><span data-stu-id="604f3-312">**``suite_name``** Name of the desired suite.</span></span>

##### <a name="examples"></a><span data-ttu-id="604f3-313">Exemplos</span><span class="sxs-lookup"><span data-stu-id="604f3-313">Examples</span></span>
``playbacksuite suiteName``  
``playbacksuite sample_suite``


#### <a name="quit"></a><span data-ttu-id="604f3-314">encerrar</span><span class="sxs-lookup"><span data-stu-id="604f3-314">quit</span></span>
<span data-ttu-id="604f3-315">Fecha o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="604f3-315">Closes the  application.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``quit``**


#### <a name="upload"></a><span data-ttu-id="604f3-316">carregar</span><span class="sxs-lookup"><span data-stu-id="604f3-316">upload</span></span>
<span data-ttu-id="604f3-317">Carrega todos os arquivos pertencentes ao pacote de teste ou casos de teste especificados.</span><span class="sxs-lookup"><span data-stu-id="604f3-317">Uploads all files belonging to the specified test suite or test cases.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``upload``**``[suite_name] [testcase_id]``

#### <a name="required-parameters"></a><span data-ttu-id="604f3-318">Parâmetros obrigatórios</span><span class="sxs-lookup"><span data-stu-id="604f3-318">Required parameters</span></span>
<span data-ttu-id="604f3-319">**``suite_name``** Todos os arquivos pertencentes ao pacote de teste especificado serão carregados.</span><span class="sxs-lookup"><span data-stu-id="604f3-319">**``suite_name``** All files belonging to the specified test suite will be uploaded.</span></span>
<span data-ttu-id="604f3-320">**``testcase_id``** Todos os arquivos pertencentes aos casos de teste especificados serão carregados.</span><span class="sxs-lookup"><span data-stu-id="604f3-320">**``testcase_id``** All files beloning to the specified test case(s) will be uploaded.</span></span>

##### <a name="examples"></a><span data-ttu-id="604f3-321">Exemplos</span><span class="sxs-lookup"><span data-stu-id="604f3-321">Examples</span></span>
``upload sample_suite``  
``upload 123``  
``upload 123 456``


#### <a name="uploadrecording"></a><span data-ttu-id="604f3-322">uploadrecording</span><span class="sxs-lookup"><span data-stu-id="604f3-322">uploadrecording</span></span>
<span data-ttu-id="604f3-323">Carrega apenas o arquivo de gravação pertencente aos casos de teste especificados.</span><span class="sxs-lookup"><span data-stu-id="604f3-323">Uploads only recording file belonging to the specified test cases.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``uploadrecording``**``[testcase_id]``

##### <a name="required-parameters"></a><span data-ttu-id="604f3-324">Parâmetros obrigatórios</span><span class="sxs-lookup"><span data-stu-id="604f3-324">Required parameters</span></span>
<span data-ttu-id="604f3-325">**``testcase_id``** O arquivo de gravação pertencente aos casos de teste especificados será carregado.</span><span class="sxs-lookup"><span data-stu-id="604f3-325">**``testcase_id``** Recording file belonging to the specified test cases will be uploaded.</span></span>

##### <a name="examples"></a><span data-ttu-id="604f3-326">Exemplos</span><span class="sxs-lookup"><span data-stu-id="604f3-326">Examples</span></span>
``uploadrecording 123``  
``uploadrecording 123 456``


#### <a name="usage"></a><span data-ttu-id="604f3-327">uso</span><span class="sxs-lookup"><span data-stu-id="604f3-327">usage</span></span>
<span data-ttu-id="604f3-328">Mostra duas maneiras de chamar esse aplicativo: uma usando um arquivo de configuração padrão, outra fornecendo um arquivo de configuração.</span><span class="sxs-lookup"><span data-stu-id="604f3-328">Shows two ways to invoke this application: one using a default setting file, another one providing a setting file.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``usage``**


### <a name="windows-powershell-examples"></a><span data-ttu-id="604f3-329">Exemplos de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="604f3-329">Windows PowerShell examples</span></span>

[!IMPORTANT] <span data-ttu-id="604f3-330">Os scripts de exemplo a seguir são fornecidos como são para fins ilustrados e não têm suporte da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="604f3-330">The example scripts below are provided AS IS for illustration purposes and are not supported by Microsoft.</span></span>

#### <a name="run-a-test-case-in-a-loop"></a><span data-ttu-id="604f3-331">Executar um caso de teste em um loop</span><span class="sxs-lookup"><span data-stu-id="604f3-331">Run a test case in a loop</span></span>

<span data-ttu-id="604f3-332">Você tem um script de teste que cria um novo cliente.</span><span class="sxs-lookup"><span data-stu-id="604f3-332">You have a test script that creates a new customer.</span></span> <span data-ttu-id="604f3-333">Através do script, este caso de teste pode ser executado em um loop, randomizando os seguintes dados antes de cada iteração ser executada:</span><span class="sxs-lookup"><span data-stu-id="604f3-333">Via scripting, this test case can be run in a loop by randomizing the following data before each iteration is run:</span></span>

- <span data-ttu-id="604f3-334">ID do cliente</span><span class="sxs-lookup"><span data-stu-id="604f3-334">Customer ID</span></span>
- <span data-ttu-id="604f3-335">Nome do Cliente</span><span class="sxs-lookup"><span data-stu-id="604f3-335">Customer name</span></span>
- <span data-ttu-id="604f3-336">Endereço do cliente</span><span class="sxs-lookup"><span data-stu-id="604f3-336">Customer address</span></span>

<span data-ttu-id="604f3-337">O ID do cliente estará no formato *ATCUS\<number\>*, onde \<number\> é um valor entre **000000001** e **999999999**.</span><span class="sxs-lookup"><span data-stu-id="604f3-337">The customer ID will be in the format *ATCUS\<number\>*, where \<number\> is a value between **000000001** and **999999999**.</span></span>

<span data-ttu-id="604f3-338">O seguinte exemplo usa um parâmetro, **iniciar**, para definir o primeiro número usado.</span><span class="sxs-lookup"><span data-stu-id="604f3-338">The following example uses one parameter, **start**, to define the first number that is used.</span></span> <span data-ttu-id="604f3-339">Usa um segundo parâmetro, **nr**, para definir o número de clientes que deve ser criado.</span><span class="sxs-lookup"><span data-stu-id="604f3-339">Is uses a second parameter, **nr**, to define the number of customers that must be created.</span></span> <span data-ttu-id="604f3-340">Para cada iteração, os parâmetros no arquivo de parâmetros do Excel são alterados usando uma função UpdateCustomer.</span><span class="sxs-lookup"><span data-stu-id="604f3-340">For each iteration, the parameters in the Excel parameter file are changed by using an UpdateCustomer function.</span></span> <span data-ttu-id="604f3-341">Em seguida, a linha de comandos de RSAT é chamada em uma função de RunTestCase.</span><span class="sxs-lookup"><span data-stu-id="604f3-341">Then the RSAT command line is called in a RunTestCase function.</span></span>

<span data-ttu-id="604f3-342">Abra o Ambiente de Script Integrado (ISE) do Microsoft Windows PowerShell no modo de administração e cole o seguinte código na janela que é nomeada **Untitled1.ps1**.</span><span class="sxs-lookup"><span data-stu-id="604f3-342">Open Microsoft Windows PowerShell Integrated Scripting Environment (ISE) in admin mode, and paste the following code into the window that is named **Untitled1.ps1**.</span></span>

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

#### <a name="run-a-script-that-depends-on-data-in-microsoft-dynamics-365"></a><span data-ttu-id="604f3-343">Execute um script que dependa de dados no Microsoft Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="604f3-343">Run a script that depends on data in Microsoft Dynamics 365</span></span>

<span data-ttu-id="604f3-344">O exemplo a seguir usa uma chamada do Protocolo Open Data (OData) para localizar o status da ordem de uma ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="604f3-344">The following example uses an Open Data Protocol (OData) call to find the order status of a purchase order.</span></span> <span data-ttu-id="604f3-345">Se o status não for **faturado**, você pode, por exemplo, chamar um caso de teste RSAT que lança a fatura.</span><span class="sxs-lookup"><span data-stu-id="604f3-345">If the status isn't **invoiced**, you can, for example, call an RSAT test case that posts the invoice.</span></span>

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
