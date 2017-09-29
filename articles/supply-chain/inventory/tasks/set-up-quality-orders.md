---
title: Configurar ordens de qualidade
description: "Este procedimento mostra como habilitar um processo de gerenciamento de qualidade no estoque de entrada que será inspecionado imediatamente após o registro de entrada."
author: perlynne
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0e7f66cccd76e5326fce75d1a13aff294c16fb9b
ms.openlocfilehash: 73981313fc662094ee4f8bb15a88271e16d41193
ms.contentlocale: pt-br
ms.lasthandoff: 09/12/2017

---
# <a name="set-up-quality-orders"></a><span data-ttu-id="16ef6-103">Configurar ordens de qualidade</span><span class="sxs-lookup"><span data-stu-id="16ef6-103">Set up quality orders</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="16ef6-104">Este procedimento mostra como habilitar um processo de gerenciamento de qualidade no estoque de entrada que será inspecionado imediatamente após o registro de entrada.</span><span class="sxs-lookup"><span data-stu-id="16ef6-104">This procedure shows you how to enable a quality management process where incoming inventory must be inspected immediately after arrival registration.</span></span> <span data-ttu-id="16ef6-105">O procedimento será executado tipicamente por um gerente de qualidade.</span><span class="sxs-lookup"><span data-stu-id="16ef6-105">The procedure will typically be carried out by a quality manager.</span></span> <span data-ttu-id="16ef6-106">O processo inclui a criação de um grupo de qualidade, para definir os itens que estejam prestes a ser provados, e um grupo de teste para agrupar os testes que devem ser executados em itens no grupo de qualidade.</span><span class="sxs-lookup"><span data-stu-id="16ef6-106">The process includes the creation of a quality group, to define the items that are going to be sampled, and a test group to group the tests that are to be performed on items in the quality group.</span></span> <span data-ttu-id="16ef6-107">Você pode executar este guia na empresa de dados de demonstração da USMF.</span><span class="sxs-lookup"><span data-stu-id="16ef6-107">You can run this guide in the USMF demo data company.</span></span>


## <a name="enable-quality-management"></a><span data-ttu-id="16ef6-108">Habilitar gerenciamento de qualidade</span><span class="sxs-lookup"><span data-stu-id="16ef6-108">Enable quality management</span></span>
1. <span data-ttu-id="16ef6-109">Vá para Gerenciamento de estoque > Configuração > Parâmetros de gerenciamento de depósito e estoque.</span><span class="sxs-lookup"><span data-stu-id="16ef6-109">Go to Inventory management > Setup > Inventory and warehouse management parameters.</span></span>
2. <span data-ttu-id="16ef6-110">Clique na guia gerenciamento de qualidade.</span><span class="sxs-lookup"><span data-stu-id="16ef6-110">Click the Quality management tab.</span></span>
3. <span data-ttu-id="16ef6-111">Defina a opção Usar gerenciamento de qualidade como Sim.</span><span class="sxs-lookup"><span data-stu-id="16ef6-111">Set the Use quality management option to Yes.</span></span>
4. <span data-ttu-id="16ef6-112">Clique em Configuração de relatório.</span><span class="sxs-lookup"><span data-stu-id="16ef6-112">Click Report setup.</span></span>
    * <span data-ttu-id="16ef6-113">Em USMF, a configuração do relatório para a gestão de qualidade já está definida.</span><span class="sxs-lookup"><span data-stu-id="16ef6-113">In USMF, the report setup for quality management is already defined.</span></span> <span data-ttu-id="16ef6-114">Se isso não tivesse sido feito, você adicionaria novas linhas aqui para os diferentes tipos de relatório, e selecionaria o tipo de documento a ser usado para cada relatório.</span><span class="sxs-lookup"><span data-stu-id="16ef6-114">If this wasn’t done, you’d add new lines here for the different report types, and select the type of document to be used for each report.</span></span>  
5. <span data-ttu-id="16ef6-115">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="16ef6-115">Close the page.</span></span>
6. <span data-ttu-id="16ef6-116">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="16ef6-116">Close the page.</span></span>

## <a name="create-a-test"></a><span data-ttu-id="16ef6-117">Criar um teste</span><span class="sxs-lookup"><span data-stu-id="16ef6-117">Create a test</span></span>
1. <span data-ttu-id="16ef6-118">Vá para Gerenciamento de estoque > Configuração > Controle de qualidade > Testes.</span><span class="sxs-lookup"><span data-stu-id="16ef6-118">Go to Inventory management > Setup > Quality control > Tests.</span></span>
2. <span data-ttu-id="16ef6-119">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="16ef6-119">Click New.</span></span>
3. <span data-ttu-id="16ef6-120">No campo Teste, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="16ef6-120">In the Test field, type a value.</span></span>
4. <span data-ttu-id="16ef6-121">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="16ef6-121">In the Description field, type a value.</span></span>
5. <span data-ttu-id="16ef6-122">No campo Tipo, selecione 'Opção'.</span><span class="sxs-lookup"><span data-stu-id="16ef6-122">In the Type field, select 'Option'.</span></span>
    * <span data-ttu-id="16ef6-123">Neste exemplo, selecionaremos a "opção" que tornará possível atribuir os resultados do teste com base nos valores predefinidos.</span><span class="sxs-lookup"><span data-stu-id="16ef6-123">In this example, we'll select "Option" which will make it possible to assign the test results based on pre-defined values.</span></span>  
6. <span data-ttu-id="16ef6-124">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="16ef6-124">Click Save.</span></span>
7. <span data-ttu-id="16ef6-125">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="16ef6-125">Close the page.</span></span>

## <a name="create-test-variables-to-define-the-way-test-results-are-recorded"></a><span data-ttu-id="16ef6-126">Crie variáveis de teste para definir a forma como os resultados do teste são registrados</span><span class="sxs-lookup"><span data-stu-id="16ef6-126">Create Test variables to define the way test results are recorded</span></span>
1. <span data-ttu-id="16ef6-127">Vá para Gerenciamento de estoque > Configuração > Controle de qualidade > Variáveis de testes.</span><span class="sxs-lookup"><span data-stu-id="16ef6-127">Go to Inventory management > Setup > Quality control > Test variables.</span></span>
2. <span data-ttu-id="16ef6-128">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="16ef6-128">Click New.</span></span>
3. <span data-ttu-id="16ef6-129">No campo Variável, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="16ef6-129">In the Variable field, type a value.</span></span>
4. <span data-ttu-id="16ef6-130">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="16ef6-130">In the Description field, type a value.</span></span>
5. <span data-ttu-id="16ef6-131">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="16ef6-131">Click Save.</span></span>
6. <span data-ttu-id="16ef6-132">Clique em Resultados.</span><span class="sxs-lookup"><span data-stu-id="16ef6-132">Click Outcomes.</span></span>
7. <span data-ttu-id="16ef6-133">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="16ef6-133">Click New.</span></span>
8. <span data-ttu-id="16ef6-134">No campo Resultado, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="16ef6-134">In the Outcome field, type a value.</span></span>
9. <span data-ttu-id="16ef6-135">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="16ef6-135">In the Description field, type a value.</span></span>
10. <span data-ttu-id="16ef6-136">No campo Status de resultado, selecione 'Passar'.</span><span class="sxs-lookup"><span data-stu-id="16ef6-136">In the Outcome status field, select 'Pass'.</span></span>
11. <span data-ttu-id="16ef6-137">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="16ef6-137">Click Save.</span></span>
12. <span data-ttu-id="16ef6-138">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="16ef6-138">Click New.</span></span>
13. <span data-ttu-id="16ef6-139">No campo Resultado, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="16ef6-139">In the Outcome field, type a value.</span></span>
14. <span data-ttu-id="16ef6-140">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="16ef6-140">In the Description field, type a value.</span></span>
15. <span data-ttu-id="16ef6-141">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="16ef6-141">Click Save.</span></span>
16. <span data-ttu-id="16ef6-142">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="16ef6-142">Close the page.</span></span>
17. <span data-ttu-id="16ef6-143">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="16ef6-143">Close the page.</span></span>

## <a name="set-up-item-sampling"></a><span data-ttu-id="16ef6-144">Configurar amostragem de item</span><span class="sxs-lookup"><span data-stu-id="16ef6-144">Set up item sampling</span></span>
1. <span data-ttu-id="16ef6-145">Vá para Gerenciamento de estoque > Configuração > Controle de qualidade > Amostragem de item.</span><span class="sxs-lookup"><span data-stu-id="16ef6-145">Go to Inventory management > Setup > Quality control > Item sampling.</span></span>
2. <span data-ttu-id="16ef6-146">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="16ef6-146">Click New.</span></span>
3. <span data-ttu-id="16ef6-147">No campo Amostragem de item, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="16ef6-147">In the Item sampling field, type a value.</span></span>
4. <span data-ttu-id="16ef6-148">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="16ef6-148">In the Description field, type a value.</span></span>
5. <span data-ttu-id="16ef6-149">No campo Valor, insira um número.</span><span class="sxs-lookup"><span data-stu-id="16ef6-149">In the Value field, enter a number.</span></span>
    * <span data-ttu-id="16ef6-150">Esse valor é relacionado à especificação da quantidade selecionada no campo adjacente.</span><span class="sxs-lookup"><span data-stu-id="16ef6-150">This value relates to the Quantity specification that’s selected in the adjacent field.</span></span>  
6. <span data-ttu-id="16ef6-151">Expandir ou recolher a seção Processo.</span><span class="sxs-lookup"><span data-stu-id="16ef6-151">Expand or collapse the Process section.</span></span>
7. <span data-ttu-id="16ef6-152">Selecionar ou desmarcar a caixa de seleção Bloqueio completo.</span><span class="sxs-lookup"><span data-stu-id="16ef6-152">Select or clear the Full blocking check box.</span></span>
    * <span data-ttu-id="16ef6-153">Se você selecionar esta opção, a quantidade de muitos ou da linha da ordem estará bloqueada se um teste falhar.</span><span class="sxs-lookup"><span data-stu-id="16ef6-153">If you select this option, the whole lot or order line quantity is blocked if a test is failed.</span></span> <span data-ttu-id="16ef6-154">Se você não selecionar, somente os itens na ordem de qualidade estarão bloqueados.</span><span class="sxs-lookup"><span data-stu-id="16ef6-154">If you don't select it, only the items in the quality order are blocked.</span></span>  
8. <span data-ttu-id="16ef6-155">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="16ef6-155">Click Save.</span></span>
9. <span data-ttu-id="16ef6-156">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="16ef6-156">Close the page.</span></span>

## <a name="create-a-quality-group"></a><span data-ttu-id="16ef6-157">Criar um grupo de qualidade</span><span class="sxs-lookup"><span data-stu-id="16ef6-157">Create a quality group</span></span>
1. <span data-ttu-id="16ef6-158">Vá para Gerenciamento de estoque > Configuração > Controle de qualidade > Grupos de qualidade.</span><span class="sxs-lookup"><span data-stu-id="16ef6-158">Go to Inventory management > Setup > Quality control > Quality groups.</span></span>
2. <span data-ttu-id="16ef6-159">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="16ef6-159">Click New.</span></span>
3. <span data-ttu-id="16ef6-160">No campo Grupo de qualidade, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="16ef6-160">In the Quality group field, type a value.</span></span>
    * <span data-ttu-id="16ef6-161">Use um nome descritivo para ajudar a identificar quais o tipo de itens o grupo conterá (seus critérios de amostragem).</span><span class="sxs-lookup"><span data-stu-id="16ef6-161">Use a descriptive name to help you identify which kind of items the group will contain (your sampling criteria).</span></span>  
4. <span data-ttu-id="16ef6-162">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="16ef6-162">In the Description field, type a value.</span></span>
5. <span data-ttu-id="16ef6-163">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="16ef6-163">Click Save.</span></span>
6. <span data-ttu-id="16ef6-164">Clique em Adicionar itens.</span><span class="sxs-lookup"><span data-stu-id="16ef6-164">Click Add items.</span></span>
7. <span data-ttu-id="16ef6-165">Selecione a linha do número do item</span><span class="sxs-lookup"><span data-stu-id="16ef6-165">Select the Item number row</span></span>
    * <span data-ttu-id="16ef6-166">Neste exemplo a filtragem será executada com base no número do item.</span><span class="sxs-lookup"><span data-stu-id="16ef6-166">In this example the filtering will be run based on  the item number.</span></span>  
8. <span data-ttu-id="16ef6-167">No campo Critérios, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="16ef6-167">In the Criteria field, type a value.</span></span>
    * <span data-ttu-id="16ef6-168">Por exemplo, digite T* para filtrar os números de item que começam com T.</span><span class="sxs-lookup"><span data-stu-id="16ef6-168">For example, type T* to filter on the item numbers that start with T.</span></span>  
9. <span data-ttu-id="16ef6-169">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="16ef6-169">Click OK.</span></span>
10. <span data-ttu-id="16ef6-170">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="16ef6-170">Click OK.</span></span>
11. <span data-ttu-id="16ef6-171">Clique em Grupos de qualidade de item.</span><span class="sxs-lookup"><span data-stu-id="16ef6-171">Click Item quality groups.</span></span>
12. <span data-ttu-id="16ef6-172">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="16ef6-172">Close the page.</span></span>
13. <span data-ttu-id="16ef6-173">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="16ef6-173">Close the page.</span></span>

## <a name="create-a-test-group"></a><span data-ttu-id="16ef6-174">Criar um grupo de teste</span><span class="sxs-lookup"><span data-stu-id="16ef6-174">Create a test group</span></span>
1. <span data-ttu-id="16ef6-175">Vá para Gerenciamento de estoque > Configuração > Controle de qualidade > Grupos de teste.</span><span class="sxs-lookup"><span data-stu-id="16ef6-175">Go to Inventory management > Setup > Quality control > Test groups.</span></span>
2. <span data-ttu-id="16ef6-176">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="16ef6-176">Click New.</span></span>
3. <span data-ttu-id="16ef6-177">No campo Grupo de teste, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="16ef6-177">In the Test group field, type a value.</span></span>
    * <span data-ttu-id="16ef6-178">Insira ao grupo de testes um nome que ajude a lembrar que tipo de teste está sendo executado, e com qual grupo de qualidade ele deve ser associado.</span><span class="sxs-lookup"><span data-stu-id="16ef6-178">Give the Test group a name that will help you remember what kind of tests are being run, and which quality group it should be associated with.</span></span> <span data-ttu-id="16ef6-179">Por exemplo, deve ser usado com um grupo de qualidade que selecione os itens que começam com “O”, você pode chamá-lo de “Testes de item T“.</span><span class="sxs-lookup"><span data-stu-id="16ef6-179">For example, it it’s to be used with a quality group that selects items starting with “T”, you could call it “T-item tests”.</span></span>  
4. <span data-ttu-id="16ef6-180">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="16ef6-180">In the Description field, type a value.</span></span>
5. <span data-ttu-id="16ef6-181">No campo de amostragem do item, selecione a linha de amostragem do item que você criou anteriormente.</span><span class="sxs-lookup"><span data-stu-id="16ef6-181">In the Item sampling field, select the item sampling line that you created before.</span></span>
6. <span data-ttu-id="16ef6-182">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="16ef6-182">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="16ef6-183">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="16ef6-183">Click Add.</span></span>
8. <span data-ttu-id="16ef6-184">No campo de número de sequência, insira um número.</span><span class="sxs-lookup"><span data-stu-id="16ef6-184">In the Sequence number field, enter a number.</span></span>
9. <span data-ttu-id="16ef6-185">No campo Teste, selecione o teste criado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="16ef6-185">In the Test field, select the test that you created earlier.</span></span>
10. <span data-ttu-id="16ef6-186">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="16ef6-186">In the list, find and select the desired record.</span></span>
11. <span data-ttu-id="16ef6-187">Clique na guia Teste.</span><span class="sxs-lookup"><span data-stu-id="16ef6-187">Click the Test tab.</span></span>
12. <span data-ttu-id="16ef6-188">No campo Variável, selecione o teste variável criado anteriormente</span><span class="sxs-lookup"><span data-stu-id="16ef6-188">In the Variable field, select the test variable that you created before</span></span>
13. <span data-ttu-id="16ef6-189">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="16ef6-189">In the list, find and select the desired record.</span></span>
14. <span data-ttu-id="16ef6-190">No campo Resultado padrão, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="16ef6-190">In the Default outcome field, click the drop-down button to open the lookup.</span></span>
15. <span data-ttu-id="16ef6-191">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="16ef6-191">In the list, click the link in the selected row.</span></span>
16. <span data-ttu-id="16ef6-192">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="16ef6-192">Click Save.</span></span>
17. <span data-ttu-id="16ef6-193">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="16ef6-193">Close the page.</span></span>

## <a name="define-when-quality-orders-will-be-created"></a><span data-ttu-id="16ef6-194">Define quando as ordens de qualidade serão criadas</span><span class="sxs-lookup"><span data-stu-id="16ef6-194">Define when quality orders will be created</span></span>
1. <span data-ttu-id="16ef6-195">Vá para Gerenciamento de estoque > Configuração > Controle de qualidade > Associações de qualidade.</span><span class="sxs-lookup"><span data-stu-id="16ef6-195">Go to Inventory management > Setup > Quality control > Quality associations.</span></span>
2. <span data-ttu-id="16ef6-196">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="16ef6-196">Click New.</span></span>
3. <span data-ttu-id="16ef6-197">No campo Tipo de referência, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="16ef6-197">In the Reference type field, select an option.</span></span>
4. <span data-ttu-id="16ef6-198">No campo Código de item, selecione 'Grupo'.</span><span class="sxs-lookup"><span data-stu-id="16ef6-198">In the Item code field, select 'Group'.</span></span>
    * <span data-ttu-id="16ef6-199">Neste exemplo, selecionaremos o "Grupo" e usaremos o grupo de qualidade que criamos antes.</span><span class="sxs-lookup"><span data-stu-id="16ef6-199">In this example, we’ll select "Group" and use the quality group we created before.</span></span> <span data-ttu-id="16ef6-200">Você também pode definir para "Tabela" para especificar manualmente os itens, ou selecionar "Tudo" para adicionar todos os itens na ordem de qualidade.</span><span class="sxs-lookup"><span data-stu-id="16ef6-200">You could also set this to "Table" to specify the items manually, or select "All" to add all items to the quality order.</span></span>  
5. <span data-ttu-id="16ef6-201">No campo Item, selecione o grupo de qualidade criado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="16ef6-201">In the Item field, select the quality group that you created before.</span></span>
    * <span data-ttu-id="16ef6-202">As opções disponíveis no campo item dependem do que você definiu no campo Código do item.</span><span class="sxs-lookup"><span data-stu-id="16ef6-202">The options available in the Item field depend on what you set in the Item code field.</span></span>  
6. <span data-ttu-id="16ef6-203">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="16ef6-203">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="16ef6-204">Expandir ou recolher a seção Processo.</span><span class="sxs-lookup"><span data-stu-id="16ef6-204">Expand or collapse the Process section.</span></span>
8. <span data-ttu-id="16ef6-205">No campo Tipo de evento, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="16ef6-205">In the Event type field, select an option.</span></span>
    * <span data-ttu-id="16ef6-206">Este é o evento que dispara o teste.</span><span class="sxs-lookup"><span data-stu-id="16ef6-206">This is the event that triggers the test.</span></span> <span data-ttu-id="16ef6-207">As opções disponíveis dependem de qual processo você selecionou no campo Tipo de referência.</span><span class="sxs-lookup"><span data-stu-id="16ef6-207">The options available here depend on which process you selected in the Reference type field.</span></span>  
9. <span data-ttu-id="16ef6-208">No campo Execução, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="16ef6-208">In the Execution field, select an option.</span></span>
10. <span data-ttu-id="16ef6-209">Expandir ou recolher a seção Processo de ordem de qualidade.</span><span class="sxs-lookup"><span data-stu-id="16ef6-209">Expand or collapse the Quality order process section.</span></span>
11. <span data-ttu-id="16ef6-210">No campo Bloqueio de evento, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="16ef6-210">In the Event blocking field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="16ef6-211">Este campo mostra a lista de processos que é possível bloquear se a ordem de qualidade ainda estiver aberta.</span><span class="sxs-lookup"><span data-stu-id="16ef6-211">This field shows the list of processes that it’s possible to block if the quality order is still open.</span></span> <span data-ttu-id="16ef6-212">As opções dependem de qual opção selecionada no campo Tipo de evento.</span><span class="sxs-lookup"><span data-stu-id="16ef6-212">The options depend on what you selected in the Event type field.</span></span>  
12. <span data-ttu-id="16ef6-213">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="16ef6-213">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="16ef6-214">Isso dependerá dos valores selecionados anteriormente.</span><span class="sxs-lookup"><span data-stu-id="16ef6-214">This will be depending on the previous selected values.</span></span> <span data-ttu-id="16ef6-215">Selecione se os processos a seguir devem ser bloqueados durante as ordens de qualidade abertas vinculados a um documento de linha de origem.</span><span class="sxs-lookup"><span data-stu-id="16ef6-215">Select if the following processes must be blocked while having open quality orders linked to a source document line.</span></span>  
13. <span data-ttu-id="16ef6-216">Expandir ou recolher a seção Especificações.</span><span class="sxs-lookup"><span data-stu-id="16ef6-216">Expand or collapse the Specifications section.</span></span>
14. <span data-ttu-id="16ef6-217">No campo Grupo de teste, selecione o grupo de teste criado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="16ef6-217">In the Test group field, select the test group that you created before.</span></span>
15. <span data-ttu-id="16ef6-218">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="16ef6-218">In the list, find and select the desired record.</span></span>
16. <span data-ttu-id="16ef6-219">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="16ef6-219">Click Save.</span></span>
17. <span data-ttu-id="16ef6-220">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="16ef6-220">Close the page.</span></span>

