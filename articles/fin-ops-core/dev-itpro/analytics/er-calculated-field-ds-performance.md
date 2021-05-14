---
title: Melhorar o desempenho de soluções ER adicionando fontes de dados de CAMPOS CALCULADOS parametrizados
description: Este tópico explica como você pode melhorar o desempenho das soluções de relatório eletrônico (ER) adicionando fontes de dados de CAMPO CALCULADO parametrizado.
author: NickSelin
ms.date: 04/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 4ee5a074c5c6d2e2144181e39917b1cc42dfc015
ms.sourcegitcommit: ab3f5d0da6eb0177bbad720e73c58926d686f168
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/26/2021
ms.locfileid: "5944819"
---
# <a name="improve-the-performance-of-er-solutions-by-adding-parameterized-calculated-field-data-sources"></a><span data-ttu-id="13e09-103">Melhorar o desempenho de soluções ER adicionando fontes de dados de CAMPOS CALCULADOS parametrizados</span><span class="sxs-lookup"><span data-stu-id="13e09-103">Improve the performance of ER solutions by adding parameterized CALCULATED FIELD data sources</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="13e09-104">Este tópico explica como você pode usar [rastreamentos de desempenho](trace-execution-er-troubleshoot-perf.md) de formatos de [relatório eletrônico (ER)](general-electronic-reporting.md) que são executados e, em seguida, usar as informações desses rastreamentos para ajudar a melhorar o desempenho, configurando uma fonte de dados de **Campo calculado** parametrizado.</span><span class="sxs-lookup"><span data-stu-id="13e09-104">This topic explains how you can take [performance traces](trace-execution-er-troubleshoot-perf.md) of [Electronic reporting (ER)](general-electronic-reporting.md) formats that are run, and then use the information from those traces to help improve performance by configuring a parameterized **Calculated field** data source.</span></span>

<span data-ttu-id="13e09-105">Como parte do processo de designar configurações ER para gerar documentos comerciais, você define o método usado para recuperar dados do aplicativo e inseri-los na saída gerada.</span><span class="sxs-lookup"><span data-stu-id="13e09-105">As part of the process of designing ER configurations to generate business documents, you define the method that is used to retrieve data from the application and enter it in the generated output.</span></span> <span data-ttu-id="13e09-106">Ao criar uma fonte de dados ER do tipo **Campo calculado** parametrizado, você pode reduzir o número de chamadas de banco do dados e reduzir bastante o tempo e o custo envolvidos na coleta dos detalhes da execução de formato ER.</span><span class="sxs-lookup"><span data-stu-id="13e09-106">By designing a parametrized ER data source of the **Calculated field** type, you can reduce the number of database calls, and significantly reduce the time and cost that are involved in collecting the details of ER format execution.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="13e09-107">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="13e09-107">Prerequisites</span></span>

- <span data-ttu-id="13e09-108">Para concluir os exemplos deste tópico, você deve ter acesso a uma das seguintes [funções](../sysadmin/tasks/assign-users-security-roles.md):</span><span class="sxs-lookup"><span data-stu-id="13e09-108">To complete the examples in this topic, you must have the access to one of the following [roles](../sysadmin/tasks/assign-users-security-roles.md):</span></span>

    - <span data-ttu-id="13e09-109">Desenvolvedor de relatório eletrônico</span><span class="sxs-lookup"><span data-stu-id="13e09-109">Electronic reporting developer</span></span>
    - <span data-ttu-id="13e09-110">Consultor funcional de relatório eletrônico</span><span class="sxs-lookup"><span data-stu-id="13e09-110">Electronic reporting functional consultant</span></span>
    - <span data-ttu-id="13e09-111">Administrador do sistema</span><span class="sxs-lookup"><span data-stu-id="13e09-111">System administrator</span></span>

- <span data-ttu-id="13e09-112">A empresa deve ser definida como **DEMF**.</span><span class="sxs-lookup"><span data-stu-id="13e09-112">The company must be set to **DEMF**.</span></span>
- <span data-ttu-id="13e09-113">Siga as etapas no [Apêndice 1](#appendix1) deste tópico para baixar os componentes da solução de exemplo do Microsoft ER necessários para concluir os exemplos deste tópico.</span><span class="sxs-lookup"><span data-stu-id="13e09-113">Follow the steps in [Appendix 1](#appendix1) of this topic to download the components of the sample Microsoft ER solution that is required to complete the examples in this topic.</span></span>
- <span data-ttu-id="13e09-114">Siga as etapas no [Apêndice 2](#appendix2) deste tópico para configurar o conjunto mínimo de parâmetros ER necessários para usar a estrutura ER para ajudar a melhorar o desempenho da solução ER de exemplo da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="13e09-114">Follow the steps in [Appendix 2](#appendix2) of this topic to configure the minimal set of ER parameters that is required to use the ER framework to help improve the performance of the sample Microsoft ER solution.</span></span>

## <a name="import-the-sample-er-solution"></a><span data-ttu-id="13e09-115">Importar a solução ER de exemplo</span><span class="sxs-lookup"><span data-stu-id="13e09-115">Import the sample ER solution</span></span>

<span data-ttu-id="13e09-116">Imagine que você precise criar uma solução ER para gerar um novo relatório que mostre transações de fornecedor.</span><span class="sxs-lookup"><span data-stu-id="13e09-116">Imagine that you must design an ER solution to generate a new report that shows vendor transactions.</span></span> <span data-ttu-id="13e09-117">Atualmente, você pode encontrar as transações de um fornecedor selecionado na página **Transações do fornecedor** (acesse **Conta a pagar** \> **Fornecedores** \> **Todos os fornecedores**, selecione um fornecedor e, no Painel de Ações, na guia **Fornecedor**, no grupo **Transações**, selecione **Transações**).</span><span class="sxs-lookup"><span data-stu-id="13e09-117">Currently, you can find the transactions for a selected vendor on the **Vendor transactions** page (go to **Account payable** \> **Vendors** \> **All vendors**, select a vendor, and then, on the Action Pane, on the **Vendor** tab, in the **Transactions** group, select **Transactions**).</span></span> <span data-ttu-id="13e09-118">Contudo, você deseja ter todas as transações do fornecedor juntas em um documento eletrônico no formato XML.</span><span class="sxs-lookup"><span data-stu-id="13e09-118">However, you want to have all vendor transactions together in one electronic document in XML format.</span></span> <span data-ttu-id="13e09-119">Essa solução consistirá em várias configurações de ER que contêm os modelos de dados, mapeamento de modelo e componentes de formato necessários.</span><span class="sxs-lookup"><span data-stu-id="13e09-119">This solution will consist of several ER configurations that contain the required data model, model mapping, and format components.</span></span>

<span data-ttu-id="13e09-120">A primeira etapa é importar a solução ER de exemplo para gerar um relatório de transações de fornecedor.</span><span class="sxs-lookup"><span data-stu-id="13e09-120">The first step is to import the sample ER solution to generate a vendor transactions report.</span></span>

1. <span data-ttu-id="13e09-121">Entre na instância do Microsoft Dynamics 365 Finance que foi provisionada para sua empresa.</span><span class="sxs-lookup"><span data-stu-id="13e09-121">Sign in to the instance of Microsoft Dynamics 365 Finance that is provisioned for your company.</span></span>
2. <span data-ttu-id="13e09-122">Neste tópico, você criará e modificará configurações para a empresa de exemplo **Litware, Inc.**.</span><span class="sxs-lookup"><span data-stu-id="13e09-122">In this topic, you will create and modify configurations for the **Litware, Inc.** sample company.</span></span> <span data-ttu-id="13e09-123">Verifique se esse provedor de configuração foi adicionado à instância do Finance e marcado como ativo.</span><span class="sxs-lookup"><span data-stu-id="13e09-123">Make sure that this configuration provider has been added to your Finance instance and is marked as active.</span></span> <span data-ttu-id="13e09-124">Para obter mais informações, consulte [Criar provedores de configuração e marcá-los como ativos](tasks/er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="13e09-124">For more information, see [Create configuration providers and mark them as active](tasks/er-configuration-provider-mark-it-active-2016-11.md).</span></span>
3. <span data-ttu-id="13e09-125">No espaço de trabalho **Relatório eletrônico**, selecione o bloco **Configurações de relatórios**.</span><span class="sxs-lookup"><span data-stu-id="13e09-125">In the **Electronic reporting** workspace, select the **Reporting configurations** tile.</span></span>
4. <span data-ttu-id="13e09-126">Na página **Configurações**, importe as configurações ER que você baixou como um pré-requisito para o Finance, na seguinte ordem: modelo de dados, mapeamento de modelo, formato.</span><span class="sxs-lookup"><span data-stu-id="13e09-126">On the **Configurations** page, import the ER configurations that you downloaded as a prerequisite into Finance, in the following order: data model, model mapping, format.</span></span> <span data-ttu-id="13e09-127">Para cada configuração, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="13e09-127">For each configuration, follow these steps:</span></span>

    1. <span data-ttu-id="13e09-128">No Painel de Ação, selecione **Câmbio** \> **Carregar de arquivo XML**.</span><span class="sxs-lookup"><span data-stu-id="13e09-128">On the Action Pane, select **Exchange** \> **Load from XML file**.</span></span>
    2. <span data-ttu-id="13e09-129">Selecione **Procurar** e o arquivo apropriado para a configuração ER no formato XML.</span><span class="sxs-lookup"><span data-stu-id="13e09-129">Select **Browse**, and select the appropriate file for the ER configuration in XML format.</span></span>
    3. <span data-ttu-id="13e09-130">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="13e09-130">Select **OK**.</span></span>

![Configurações importadas na página Configurações](./media/er-calculated-field-ds-performance-imported-configurations.png)

## <a name="review-the-sample-er-solution"></a><span data-ttu-id="13e09-132">Revisar a solução ER de exemplo</span><span class="sxs-lookup"><span data-stu-id="13e09-132">Review the sample ER solution</span></span>

### <a name="review-the-model-mapping"></a><span data-ttu-id="13e09-133">Revisar o mapeamento de modelos</span><span class="sxs-lookup"><span data-stu-id="13e09-133">Review the model mapping</span></span>

1. <span data-ttu-id="13e09-134">Na página **Configurações**, na árvore de configurações, expanda **Modelo de aperfeiçoamento de desempenho** e selecione **Mapeamento de aperfeiçoamento de desempenho**.</span><span class="sxs-lookup"><span data-stu-id="13e09-134">On the **Configurations** page, in the configuration tree, expand **Performance improvement model**, and select **Performance improvement mapping**.</span></span>
2. <span data-ttu-id="13e09-135">No Painel de Ação, selecione **Designer**.</span><span class="sxs-lookup"><span data-stu-id="13e09-135">On the Action Pane, select **Designer**.</span></span>
3. <span data-ttu-id="13e09-136">Na página **Modelo para mapeamento de fonte de dados**, no Painel de Ações, selecione **Designer**.</span><span class="sxs-lookup"><span data-stu-id="13e09-136">On the **Model to datasource mapping** page, on the Action Pane, select **Designer**.</span></span>

    <span data-ttu-id="13e09-137">Esse mapeamento de modelo de ER foi criado para executar as seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="13e09-137">This ER model mapping is designed to perform the following actions:</span></span>

    - <span data-ttu-id="13e09-138">Obtenha a lista de transações de fornecedor armazenadas na tabela VendTrans (fonte de dados **Trans**).</span><span class="sxs-lookup"><span data-stu-id="13e09-138">Fetch the list of vendor transactions that are stored in the VendTrans table (**Trans** data source).</span></span>
    - <span data-ttu-id="13e09-139">Para cada transação, na tabela Vendtable, obtenha o registro de um fornecedor para o qual a transação foi lançada para (fonte de dados **\#Vend**).</span><span class="sxs-lookup"><span data-stu-id="13e09-139">For every transaction, fetch, from the VendTable table, the record of a vendor that the transaction has been posted for (**\#Vend** data source).</span></span>

    > [!NOTE]
    > <span data-ttu-id="13e09-140">A fonte de dados **\#Vend** é configurada para obter o registro de fornecedor correspondente usando a relação de vários para um existente **\@.'\>Relations'.VendTable\_AccountNum**.</span><span class="sxs-lookup"><span data-stu-id="13e09-140">The **\#Vend** data source is configured to fetch the corresponding vendor record by using the existing many-to-one relation **\@.'\>Relations'.VendTable\_AccountNum**.</span></span>

    <span data-ttu-id="13e09-141">O mapeamento do modelo nesta configuração implementa o modelo de dados de base para qualquer formato de ER criado para esse modelo e executado no Finance.</span><span class="sxs-lookup"><span data-stu-id="13e09-141">The model mapping in this configuration implements the base data model for any ER formats that are created for this model and run in Finance.</span></span> <span data-ttu-id="13e09-142">Portanto, o conteúdo da fonte de dados **Trans** é exposto para formatos de ER, como fontes de dados **modelo**.</span><span class="sxs-lookup"><span data-stu-id="13e09-142">Therefore, the content of the **Trans** data source is exposed for ER formats such as abstract **model** data sources.</span></span>

    ![Fonte de dados Trans na página Designer de mapeamento do modelo](media/er-calculated-field-ds-performance-mapping-1.png)

4. <span data-ttu-id="13e09-144">Feche a página **Designer de mapeamento de modelo**.</span><span class="sxs-lookup"><span data-stu-id="13e09-144">Close the **Model mapping designer** page.</span></span>
5. <span data-ttu-id="13e09-145">Feche a página **Modelo para mapeamento de fonte de dados**.</span><span class="sxs-lookup"><span data-stu-id="13e09-145">Close the **Model to datasource mapping** page.</span></span>

### <a name="review-format"></a><span data-ttu-id="13e09-146">Revisar o formato</span><span class="sxs-lookup"><span data-stu-id="13e09-146">Review format</span></span>

1. <span data-ttu-id="13e09-147">Na página **Configurações**, na árvore de configurações, expanda **Modelo de aperfeiçoamento de desempenho** e selecione **Formato de aperfeiçoamento de desempenho**.</span><span class="sxs-lookup"><span data-stu-id="13e09-147">On the **Configurations** page, in the configuration tree, expand **Performance improvement model**, and select **Performance improvement format**.</span></span>
2. <span data-ttu-id="13e09-148">No Painel de Ação, selecione **Designer**.</span><span class="sxs-lookup"><span data-stu-id="13e09-148">On the Action Pane, select **Designer**.</span></span>
3. <span data-ttu-id="13e09-149">Na página **Designer de formato**, na a guia **Mapeamento**, selecione **Expandir/Recolher**.</span><span class="sxs-lookup"><span data-stu-id="13e09-149">On the **Format designer** page, on the **Mapping** tab, select **Expand/Collapse**.</span></span>
4. <span data-ttu-id="13e09-150">Expanda os itens **Modelo**, **Dados** e **Transação**.</span><span class="sxs-lookup"><span data-stu-id="13e09-150">Expand the **Model**, **Data,** and **Transaction** items.</span></span>

    <span data-ttu-id="13e09-151">Este formato ER foi projetado para gerar um relatório de transações de fornecedor no formato XML.</span><span class="sxs-lookup"><span data-stu-id="13e09-151">This ER format is designed to generate a vendor transactions report in XML format.</span></span>

    ![Formatar fontes de dados e associações configuradas de elementos de formato na página Designer de formato](media/er-calculated-field-ds-performance-format.png)

5. <span data-ttu-id="13e09-153">Feche a página **Designer de formato**.</span><span class="sxs-lookup"><span data-stu-id="13e09-153">Close the **Format designer** page.</span></span>

## <a name="run-the-sample-er-solution-to-trace-execution"></a><span data-ttu-id="13e09-154">Executar a solução de ER de exemplo para rastrear a execução</span><span class="sxs-lookup"><span data-stu-id="13e09-154">Run the sample ER solution to trace execution</span></span>

<span data-ttu-id="13e09-155">Imagine que você tenha terminado de criar a primeira versão da solução de ER.</span><span class="sxs-lookup"><span data-stu-id="13e09-155">Imagine that you've finished designing the first version of the ER solution.</span></span> <span data-ttu-id="13e09-156">Agora você deseja testar a solução em sua instância do Finance e analisar o desempenho da execução.</span><span class="sxs-lookup"><span data-stu-id="13e09-156">You now want to test the solution in your Finance instance and analyze the execution performance.</span></span>

### <a name="turn-on-the-er-performance-trace"></a><span data-ttu-id="13e09-157">Ativar o rastreamento de desempenho de ER</span><span class="sxs-lookup"><span data-stu-id="13e09-157">Turn on the ER performance trace</span></span>

1. <span data-ttu-id="13e09-158">Selecione a empresa **DEMF**.</span><span class="sxs-lookup"><span data-stu-id="13e09-158">Select the **DEMF** company.</span></span>
2. <span data-ttu-id="13e09-159">Siga as etapas em [Ativar o rastreamento de desempenho ER](trace-execution-er-troubleshoot-perf.md#turn-on-the-er-performance-trace) para gerar um rastreamento de desempenho enquanto um formato ER é executado.</span><span class="sxs-lookup"><span data-stu-id="13e09-159">Follow the steps in [Turn on the ER performance trace](trace-execution-er-troubleshoot-perf.md#turn-on-the-er-performance-trace) to generate a performance trace while an ER format is run.</span></span>

    ![Caixa de diálogo de parâmetros do usuário](media/er-calculated-field-ds-performance-format-user-parameters.png)

### <a name="run-the-er-format"></a><a id="run-format"></a><span data-ttu-id="13e09-161">Executar o formato de ER</span><span class="sxs-lookup"><span data-stu-id="13e09-161">Run the ER format</span></span>

1. <span data-ttu-id="13e09-162">Vá para **Administração da organização** \> **Relatório eletrônico** \> **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="13e09-162">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="13e09-163">Na página **Configurações**, na árvore de configuração, selecione **Formato de aperfeiçoamento de desempenho**.</span><span class="sxs-lookup"><span data-stu-id="13e09-163">On the **Configurations** page, in the configuration tree, select **Performance improvement format**.</span></span>
3. <span data-ttu-id="13e09-164">No Painel de Ação, selecione **Executar**.</span><span class="sxs-lookup"><span data-stu-id="13e09-164">On the Action Pane, select **Run**.</span></span>

## <a name="use-the-performance-trace-to-analyze-model-mapping-performance"></a><span data-ttu-id="13e09-165">Use o rastreamento de desempenho para analisar o desempenho do mapeamento do modelo</span><span class="sxs-lookup"><span data-stu-id="13e09-165">Use the performance trace to analyze model mapping performance</span></span>

1. <span data-ttu-id="13e09-166">Na página **Configurações**, na árvore de configuração, selecione **Mapeamento de aperfeiçoamento de desempenho**.</span><span class="sxs-lookup"><span data-stu-id="13e09-166">On the **Configurations** page, in the configuration tree, select **Performance improvement mapping**.</span></span>
2. <span data-ttu-id="13e09-167">No Painel de Ação, selecione **Designer**.</span><span class="sxs-lookup"><span data-stu-id="13e09-167">On the Action Pane, select **Designer**.</span></span>
3. <span data-ttu-id="13e09-168">Na página **Mapeamentos de modelo**, no Painel de Ações, selecione **Designer**.</span><span class="sxs-lookup"><span data-stu-id="13e09-168">On the **Model mappings** page, on the Action Pane, select **Designer**.</span></span>
4. <span data-ttu-id="13e09-169">Na página **Designer de mapeamento de modelo**, no Painel de Ação, selecione **Rastreamento de desempenho**.</span><span class="sxs-lookup"><span data-stu-id="13e09-169">On the **Model mapping designer** page, on the Action Pane, select **Performance trace**.</span></span>
5. <span data-ttu-id="13e09-170">Selecione o rastreamento mais recente que foi gerado e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="13e09-170">Select the most recent trace that was generated, and then select **OK**.</span></span>

<span data-ttu-id="13e09-171">Novas informações estão disponíveis para alguns itens da fonte de dados do mapeamento do modelo atual:</span><span class="sxs-lookup"><span data-stu-id="13e09-171">New information is now available for some data source items of the current model mapping:</span></span>

- <span data-ttu-id="13e09-172">O tempo real gasto ao obter dados usando a fonte de dados</span><span class="sxs-lookup"><span data-stu-id="13e09-172">The actual time that was spent getting data by using the data source</span></span>
- <span data-ttu-id="13e09-173">O mesmo tempo expresso como uma porcentagem do tempo total gasto na execução do mapeamento do modelo inteiro</span><span class="sxs-lookup"><span data-stu-id="13e09-173">The same time expressed as a percentage of the total time that was spent running the whole model mapping</span></span>

![Detalhes do tempo de execução na página Designer de mapeamento de modelo](./media/er-calculated-field-ds-performance-mapping-2.png)

<span data-ttu-id="13e09-175">A grade **Estatísticas de desempenho** mostra que a fonte de dados **Trans** chama a tabela VendTrans uma vez.</span><span class="sxs-lookup"><span data-stu-id="13e09-175">The **Performance statistics** grid shows that the **Trans** data source calls the VendTrans table one time.</span></span> <span data-ttu-id="13e09-176">O valor **\[265\]\[Q:265\]** da fonte de dados **Trans** indica que 265 transações do fornecedor foram obtidas na tabela do aplicativo e devolvidas ao modelo de dados.</span><span class="sxs-lookup"><span data-stu-id="13e09-176">The value **\[265\]\[Q:265\]** of the **Trans** data source indicates that 265 vendor transactions have been fetched from the application table and returned to the data model.</span></span>

<span data-ttu-id="13e09-177">A grade **Estatísticas de desempenho** também mostra que o mapeamento do modelo atual duplica as solicitações de banco de dados enquanto a fonte de dados **\#Vend** é executada.</span><span class="sxs-lookup"><span data-stu-id="13e09-177">The **Performance statistics** grid also shows that the current model mapping duplicates database requests while the **\#Vend** data source is run.</span></span> <span data-ttu-id="13e09-178">Essa duplicação ocorre pelos seguintes motivos:</span><span class="sxs-lookup"><span data-stu-id="13e09-178">This duplication occurs for the following reasons:</span></span>

- <span data-ttu-id="13e09-179">A tabela de fornecedores é chamada duas vezes para cada uma das 265 transações do fornecedor iterado, para um total de 530 chamadas:</span><span class="sxs-lookup"><span data-stu-id="13e09-179">The vendor table is called two times for each of the 265 iterated vendor transactions, for a total of 530 calls:</span></span>

    - <span data-ttu-id="13e09-180">Uma chamada é feita para inserir o número da conta do fornecedor.</span><span class="sxs-lookup"><span data-stu-id="13e09-180">One call is made to enter the vendor account number.</span></span>
    - <span data-ttu-id="13e09-181">Uma chamada é feita para inserir o nome do fornecedor.</span><span class="sxs-lookup"><span data-stu-id="13e09-181">One call is made to enter the vendor name.</span></span>

- <span data-ttu-id="13e09-182">A tabela de fornecedores é chamada para cada transação de fornecedor iterada, mesmo que as transações obtidas tenham sido lançadas somente para cinco fornecedores.</span><span class="sxs-lookup"><span data-stu-id="13e09-182">The vendor table is called for each iterated vendor transaction, even though the fetched transactions have been posted for only five vendors.</span></span> <span data-ttu-id="13e09-183">Das 530 chamadas, 525 são duplicatas.</span><span class="sxs-lookup"><span data-stu-id="13e09-183">Of the 530 calls, 525 are duplicates.</span></span> <span data-ttu-id="13e09-184">A ilustração a seguir mostra a mensagem recebida sobre chamadas duplicadas (solicitações de banco de dados).</span><span class="sxs-lookup"><span data-stu-id="13e09-184">The following illustration shows the message that you receive about duplicate calls (database requests).</span></span>

![Mensagem sobre solicitações de banco de dados duplicadas na página Designer de mapeamento de modelo](./media/er-calculated-field-ds-performance-mapping-2a.png)

<span data-ttu-id="13e09-186">Do tempo de execução do mapeamento total do modelo (cerca de oito segundos), observe que mais de 80% (cerca de seis segundos) foi gasto na recuperação de valores da tabela do aplicativo VendTable.</span><span class="sxs-lookup"><span data-stu-id="13e09-186">Of the total model mapping execution time (approximately eight seconds), notice that more than 80 percent (approximately six seconds) has been spent retrieving values from the VendTable application table.</span></span> <span data-ttu-id="13e09-187">Essa porcentagem é muito grande para dois atributos de cinco fornecedores, em comparação com o volume de informações da tabela do aplicativo VendTrans.</span><span class="sxs-lookup"><span data-stu-id="13e09-187">That percentage is too large for two attributes of five vendors, compared with the volume of information from the VendTrans application table.</span></span>

<span data-ttu-id="13e09-188">Para reduzir o número de chamadas feitas para obter os detalhes do fornecedor para cada transação e melhorar o desempenho do mapeamento do modelo, você pode usar o armazenamento em cache para a fonte de dados **\#Vend**.</span><span class="sxs-lookup"><span data-stu-id="13e09-188">To reduce the number of calls that are made to get the vendor details for every transaction, and to improve the performance of the model mapping, you can use caching for the **\#Vend** data source.</span></span>

> [!NOTE]
> <span data-ttu-id="13e09-189">A fonte de dados **Trans\\\#Vend** será armazenada em cache no escopo da transação atual da fonte de dados da Trans **Trans** no tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="13e09-189">The **Trans\\\#Vend** data source will be cached in the scope of the current transaction of the **Trans** data source at runtime.</span></span>

<span data-ttu-id="13e09-190">Ao armazenar em cache a fonte de dados **\#Vend**, você reduz o número de chamadas duplicadas de 525 para 260, mas não elimina totalmente a duplicação.</span><span class="sxs-lookup"><span data-stu-id="13e09-190">By caching the **\#Vend** data source, you reduce the number of duplicated calls from 525 to 260, but you don't completely eliminate the duplication.</span></span> <span data-ttu-id="13e09-191">Para eliminar totalmente a duplicação, você pode configurar uma nova fonte de dados parametrizada do tipo **Campo calculado**.</span><span class="sxs-lookup"><span data-stu-id="13e09-191">To completely eliminate duplication, you can configure a new parameterized data source of the **Calculated field** type.</span></span>

## <a name="improve-the-model-mapping-based-on-information-from-the-execution-trace"></a><span data-ttu-id="13e09-192">Melhorar o mapeamento do modelo com base nas informações do rastreamento de execução</span><span class="sxs-lookup"><span data-stu-id="13e09-192">Improve the model mapping based on information from the execution trace</span></span>

### <a name="change-the-logic-of-the-model-mapping"></a><span data-ttu-id="13e09-193">Alterar a lógica do mapeamento do modelo</span><span class="sxs-lookup"><span data-stu-id="13e09-193">Change the logic of the model mapping</span></span>

<span data-ttu-id="13e09-194">Siga estas etapas para usar o cache e uma fonte de dados do tipo **Campo calculado** para ajudar a evitar chamadas duplicadas para o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="13e09-194">Follow these steps to use caching and a data source of the **Calculated field** type, to help prevent duplicate calls to the database.</span></span>

1. <span data-ttu-id="13e09-195">Na página **Configurações**, na árvore de configuração, selecione **Mapeamento de aperfeiçoamento de desempenho**.</span><span class="sxs-lookup"><span data-stu-id="13e09-195">On the **Configurations** page, in the configuration tree, select **Performance improvement mapping**.</span></span>
2. <span data-ttu-id="13e09-196">No Painel de Ação, selecione **Designer**.</span><span class="sxs-lookup"><span data-stu-id="13e09-196">On the Action Pane, select **Designer**.</span></span>
3. <span data-ttu-id="13e09-197">Na página **Mapeamentos de modelo**, no Painel de Ações, selecione **Designer**.</span><span class="sxs-lookup"><span data-stu-id="13e09-197">On the **Model mappings** page, on the Action Pane, select **Designer**.</span></span>
4. <span data-ttu-id="13e09-198">Na página **Designer de mapeamento de modelo**, siga estas etapas para adicionar uma fonte de dados do tipo **Registros de tabela** para acessar registros na tabela do aplicativo VendTable:</span><span class="sxs-lookup"><span data-stu-id="13e09-198">On the **Model mapping designer** page, follow these steps to add a data source of the **Table records** type to access records in the VendTable application table:</span></span>

    1. <span data-ttu-id="13e09-199">No painel **Tipos de fonte de dados**, expanda **Dynamics 365 for Operations** e selecione **Registros de tabela**.</span><span class="sxs-lookup"><span data-stu-id="13e09-199">In the **Data source types** pane, expand **Dynamics 365 for Operations**, and select **Table records**.</span></span>
    2. <span data-ttu-id="13e09-200">Selecione **Adicionar raiz**.</span><span class="sxs-lookup"><span data-stu-id="13e09-200">Select **Add root**.</span></span>
    3. <span data-ttu-id="13e09-201">Na caixa de diálogo, no campo **Nome** , digite **Vend**.</span><span class="sxs-lookup"><span data-stu-id="13e09-201">In the dialog box, in the **Name** field, enter **Vend**.</span></span>
    4. <span data-ttu-id="13e09-202">No campo **Tabela**, insira **VendTable**.</span><span class="sxs-lookup"><span data-stu-id="13e09-202">In the **Table** field, enter **VendTable**.</span></span>
    5. <span data-ttu-id="13e09-203">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="13e09-203">Select **OK**.</span></span>

5. <span data-ttu-id="13e09-204">Você só poderá parametrizar chamadas para as fontes de dados do tipo **Campo calculado** se essas fontes de dados residirem em um contêiner.</span><span class="sxs-lookup"><span data-stu-id="13e09-204">You can parameterize calls to data sources of the **Calculated field** type only if those data sources reside in a container.</span></span> <span data-ttu-id="13e09-205">Portanto, siga estas etapas para adicionar uma fonte de dados do tipo **Contêiner vazio** para conter uma nova fonte de dados parametrizada do tipo **Campo calculado**:</span><span class="sxs-lookup"><span data-stu-id="13e09-205">Therefore, follow these steps to add a data source of the **Empty container** type to hold a new parameterized data source of the **Calculated field** type:</span></span>

    1. <span data-ttu-id="13e09-206">No painel **Tipos de fonte de dados**, expanda **Geral** e selecione **Contêiner vazio**.</span><span class="sxs-lookup"><span data-stu-id="13e09-206">In the **Data source types** pane, expand **General**, and select **Empty container**.</span></span>
    2. <span data-ttu-id="13e09-207">Selecione **Adicionar raiz**.</span><span class="sxs-lookup"><span data-stu-id="13e09-207">Select **Add root**.</span></span>
    3. <span data-ttu-id="13e09-208">Na caixa de diálogo, no campo **Nome** , digite **Box**.</span><span class="sxs-lookup"><span data-stu-id="13e09-208">In the dialog box, in the **Name** field, enter **Box**.</span></span>
    3. <span data-ttu-id="13e09-209">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="13e09-209">Select **OK**.</span></span>

    ![Fonte de dados Box na página Designer de mapeamento do modelo](./media/er-calculated-field-ds-performance-mapping-3.png)

6. <span data-ttu-id="13e09-211">Siga estas etapas para adicionar uma fonte de dados parametrizada do tipo **Campo calculado**:</span><span class="sxs-lookup"><span data-stu-id="13e09-211">Follow these steps to add a parameterized data source of the **Calculated field** type:</span></span>

    1. <span data-ttu-id="13e09-212">No painel **Fontes de dados**, selecione **Box**.</span><span class="sxs-lookup"><span data-stu-id="13e09-212">In the **Data sources** pane, select **Box**.</span></span>
    2. <span data-ttu-id="13e09-213">No painel **Tipos de fontes de dados**, expanda **Funções** e selecione **Campo calculado**.</span><span class="sxs-lookup"><span data-stu-id="13e09-213">In the **Data source types** pane, expand **Functions**, and select **Calculated field**.</span></span>
    3. <span data-ttu-id="13e09-214">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="13e09-214">Select **Add**.</span></span>
    4. <span data-ttu-id="13e09-215">Na caixa de diálogo, no campo **Nome** , digite **Vend**.</span><span class="sxs-lookup"><span data-stu-id="13e09-215">In the dialog box, in the **Name** field, enter **Vend**.</span></span>
    5. <span data-ttu-id="13e09-216">Selecione **Editar fórmula**.</span><span class="sxs-lookup"><span data-stu-id="13e09-216">Select **Edit formula**.</span></span>
    6. <span data-ttu-id="13e09-217">Na página **Designer de fórmulas**, selecione **Parâmetros** para especificar os parâmetros que devem ser fornecidos quando essa fonte de dados é chamada.</span><span class="sxs-lookup"><span data-stu-id="13e09-217">On the **Formula designer** page, select **Parameters** to specify the parameters that must be provided when this data source is called.</span></span>
    7. <span data-ttu-id="13e09-218">Na caixa de diálogo **Parâmetros**, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="13e09-218">In the **Parameters** dialog box, select **New**.</span></span>
    8. <span data-ttu-id="13e09-219">No campo **Nome**, insira **parmVendAccNumber**.</span><span class="sxs-lookup"><span data-stu-id="13e09-219">In the **Name** field, enter **parmVendAccNumber**.</span></span>
    9. <span data-ttu-id="13e09-220">No campo **Tipo**, selecione **Cadeia de caracteres**.</span><span class="sxs-lookup"><span data-stu-id="13e09-220">In the **Type** field, select **String**.</span></span>
    10. <span data-ttu-id="13e09-221">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="13e09-221">Select **OK**.</span></span>
    11. <span data-ttu-id="13e09-222">No campo **Fórmula**, insira **FIRSTORNULL(FILTER(Vend, Vend.AccountNum=parmVendAccNumber))**.</span><span class="sxs-lookup"><span data-stu-id="13e09-222">In the **Formula** field, enter **FIRSTORNULL(FILTER(Vend, Vend.AccountNum=parmVendAccNumber))**.</span></span>
    12. <span data-ttu-id="13e09-223">Selecione **Salvar** e feche a página **Designer de fórmulas**.</span><span class="sxs-lookup"><span data-stu-id="13e09-223">Select **Save**, and close the **Formula designer** page.</span></span>
    13. <span data-ttu-id="13e09-224">Selecione **OK** para adicionar a nova fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="13e09-224">Select **OK** to add the new data source.</span></span>

7. <span data-ttu-id="13e09-225">Siga estas etapas para marcar a fonte de dados adicionada como armazenada em cache durante a execução:</span><span class="sxs-lookup"><span data-stu-id="13e09-225">Follow these steps to mark the added data source as cached during the execution:</span></span>

    1. <span data-ttu-id="13e09-226">No painel **Fontes de dados**, selecione **Box\\Vend**.</span><span class="sxs-lookup"><span data-stu-id="13e09-226">In the **Data sources** pane, select **Box\\Vend**.</span></span>
    2. <span data-ttu-id="13e09-227">Selecione **Cache**.</span><span class="sxs-lookup"><span data-stu-id="13e09-227">Select **Cache**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="13e09-228">A fonte de dados **Box\\Vend** será armazenada em cache no escopo de todas as transações de fornecedor da fonte de dados **Trans** no tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="13e09-228">The **Box\\Vend** data source will be cached in the scope of all vendor transactions of the **Trans** data source at runtime.</span></span>

8. <span data-ttu-id="13e09-229">Siga estas etapas para atualizar a fonte de dados da **Trans\\\#Vend** aninhada de forma que ela use a fonte de dados **Box\\Vend**:</span><span class="sxs-lookup"><span data-stu-id="13e09-229">Follow these steps to update the nested **Trans\\\#Vend** data source so that it uses the **Box\\Vend** data source:</span></span>

    1. <span data-ttu-id="13e09-230">No painel **Fontes de dados**, expanda **Trans**.</span><span class="sxs-lookup"><span data-stu-id="13e09-230">In the **Data sources** pane, expand **Trans**.</span></span>
    2. <span data-ttu-id="13e09-231">Selecione a fonte de dados **Trans\\\#Vend** e, depois, **Editar** \> **Editar fórmula**.</span><span class="sxs-lookup"><span data-stu-id="13e09-231">Select the **Trans\\\#Vend** data source, and then select **Edit** \> **Edit formula**.</span></span>
    3. <span data-ttu-id="13e09-232">Na página **Designer de fórmulas**, no campo **Fórmula**, insira **Box.Vend(\@.AccountNum)**.</span><span class="sxs-lookup"><span data-stu-id="13e09-232">On the **Formula designer** page, in the **Formula** field, enter **Box.Vend(\@.AccountNum)**.</span></span>
    4. <span data-ttu-id="13e09-233">Selecione **Salvar** e feche a página **Designer de fórmulas**.</span><span class="sxs-lookup"><span data-stu-id="13e09-233">Select **Save**, and then close the **Formula designer** page.</span></span>
    5. <span data-ttu-id="13e09-234">Selecione **OK** para concluir as alterações na fonte de dados selecionada.</span><span class="sxs-lookup"><span data-stu-id="13e09-234">Select **OK** to complete your changes to the selected data source.</span></span>

9. <span data-ttu-id="13e09-235">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="13e09-235">Select **Save**.</span></span>

    ![Fonte de dados Vend na página Designer de mapeamento do modelo](./media/er-calculated-field-ds-performance-mapping-4.png)

10. <span data-ttu-id="13e09-237">Feche a página **Designer de mapeamento de modelo**.</span><span class="sxs-lookup"><span data-stu-id="13e09-237">Close the **Model mapping designer** page.</span></span>
11. <span data-ttu-id="13e09-238">Feche a página **Mapeamentos de modelo**.</span><span class="sxs-lookup"><span data-stu-id="13e09-238">Close the **Model mappings** page.</span></span>

### <a name="complete-the-modified-version-of-the-er-model-mapping"></a><span data-ttu-id="13e09-239">Concluir a versão modificada do mapeamento do modelo de ER</span><span class="sxs-lookup"><span data-stu-id="13e09-239">Complete the modified version of the ER model mapping</span></span>

1. <span data-ttu-id="13e09-240">Na página **Configurações**, na FastTab **Versões**, selecione a versão **1.2** da configuração **Mapeamento de aperfeiçoamento de desempenho**.</span><span class="sxs-lookup"><span data-stu-id="13e09-240">On the **Configurations** page, on the **Versions** FastTab, select version **1.2** of the **Performance improvement mapping** configuration.</span></span>
2. <span data-ttu-id="13e09-241">Selecione **Alterar status** \> **Concluir** e, depois, **OK**.</span><span class="sxs-lookup"><span data-stu-id="13e09-241">Select **Change status** \> **Complete**, and then select **OK**.</span></span>

## <a name="run-the-modified-er-solution-to-trace-execution"></a><span data-ttu-id="13e09-242">Executar a solução de ER modificada para rastrear a execução</span><span class="sxs-lookup"><span data-stu-id="13e09-242">Run the modified ER solution to trace execution</span></span>

<span data-ttu-id="13e09-243">Repita as etapas na seção [Executar o formato de ER](#run-format) anterior neste tópico para gerar um novo rastreio de desempenho.</span><span class="sxs-lookup"><span data-stu-id="13e09-243">Repeat the steps in the [Run the ER format](#run-format) section earlier in this topic to generate a new performance trace.</span></span>

## <a name="use-the-performance-trace-to-analyze-adjustments-to-the-model-mapping"></a><span data-ttu-id="13e09-244">Use o rastreamento de desempenho para analisar ajustes do mapeamento de modelo</span><span class="sxs-lookup"><span data-stu-id="13e09-244">Use the performance trace to analyze adjustments to the model mapping</span></span> 

1. <span data-ttu-id="13e09-245">Na página **Configurações**, na árvore de configuração, selecione **Mapeamento de aperfeiçoamento de desempenho**.</span><span class="sxs-lookup"><span data-stu-id="13e09-245">On the **Configurations** page, in the configuration tree, select **Performance improvement mapping**.</span></span>
2. <span data-ttu-id="13e09-246">No Painel de Ação, selecione **Designer**.</span><span class="sxs-lookup"><span data-stu-id="13e09-246">On the Action Pane, select **Designer**.</span></span>
3. <span data-ttu-id="13e09-247">Na página **Mapeamentos de modelo**, no Painel de Ações, selecione **Designer**.</span><span class="sxs-lookup"><span data-stu-id="13e09-247">On the **Model mappings** page, on the Action Pane, select **Designer**.</span></span>
4. <span data-ttu-id="13e09-248">Na página **Designer de mapeamento de modelo**, no Painel de Ação, selecione **Rastreamento de desempenho**.</span><span class="sxs-lookup"><span data-stu-id="13e09-248">On the **Model mapping designer** page, on the Action Pane, select **Performance trace**.</span></span>
5. <span data-ttu-id="13e09-249">Selecione o rastreamento mais recente que foi gerado e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="13e09-249">Select the most recent trace that was generated, and then select **OK**.</span></span>

<span data-ttu-id="13e09-250">Observe que os ajustes feitos no mapeamento do modelo eliminaram consultas duplicadas no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="13e09-250">Notice that the adjustments that you made to the model mapping have eliminated duplicate queries to database.</span></span> <span data-ttu-id="13e09-251">O número de chamadas para tabelas de banco de dados e fontes de dados para esse mapeamento do modelo também foi reduzido.</span><span class="sxs-lookup"><span data-stu-id="13e09-251">The number of calls to database tables and data sources for this model mapping has also been reduced.</span></span>

![Informações de rastreamento na página Designer de mapeamento do modelo 1](./media/er-calculated-field-ds-performance-mapping-5.png)

<span data-ttu-id="13e09-253">O tempo de execução total foi reduzido em torno de 20 vezes (de 8 segundos para 400 milissegundos).</span><span class="sxs-lookup"><span data-stu-id="13e09-253">The total execution time has been reduced about 20 times (from about 8 seconds to about 400 milliseconds).</span></span> <span data-ttu-id="13e09-254">Portanto, o desempenho de toda a solução ER melhorou.</span><span class="sxs-lookup"><span data-stu-id="13e09-254">Therefore, the performance of the whole ER solution has been improved.</span></span>

![Informações de rastreamento na página Designer de mapeamento do modelo 2](./media/er-calculated-field-ds-performance-mapping-5a.png)

## <a name="appendix-1-download-the-components-of-the-sample-microsoft-er-solution"></a><a name="appendix1"></a><span data-ttu-id="13e09-256">Apêndice 1: baixar os componentes da solução ER de exemplo da Microsoft</span><span class="sxs-lookup"><span data-stu-id="13e09-256">Appendix 1: Download the components of the sample Microsoft ER solution</span></span>

<span data-ttu-id="13e09-257">Você deve baixar os arquivos a seguir e armazená-los localmente.</span><span class="sxs-lookup"><span data-stu-id="13e09-257">You must download the following files and store them locally.</span></span>

| <span data-ttu-id="13e09-258">Arquivo</span><span class="sxs-lookup"><span data-stu-id="13e09-258">File</span></span>                                        | <span data-ttu-id="13e09-259">Conteúdo</span><span class="sxs-lookup"><span data-stu-id="13e09-259">Content</span></span> |
|---------------------------------------------|---------|
| <span data-ttu-id="13e09-260">Aperfeiçoamento de desempenho model.version.1</span><span class="sxs-lookup"><span data-stu-id="13e09-260">Performance improvement model.version.1</span></span>     | [<span data-ttu-id="13e09-261">Configuração do modelo de dados de ER de exemplo</span><span class="sxs-lookup"><span data-stu-id="13e09-261">Sample ER data model configuration</span></span>](https://download.microsoft.com/download/4/6/f/46f0f3fa-782b-414a-8f7b-b6c64a388661/Performance_improvement_model.version.1.xml) |
| <span data-ttu-id="13e09-262">Aperfeiçoamento de desempenho mapping.version.1.1</span><span class="sxs-lookup"><span data-stu-id="13e09-262">Performance improvement mapping.version.1.1</span></span> | [<span data-ttu-id="13e09-263">Configuração do mapeamento do modelo de ER de exemplo</span><span class="sxs-lookup"><span data-stu-id="13e09-263">Sample ER model mapping configuration</span></span>](https://download.microsoft.com/download/8/9/1/8913a763-afb8-4bf4-aaf1-95ad793ffc5a/Performance_improvement_mapping.version.1.1.xml) |
| <span data-ttu-id="13e09-264">Aperfeiçoamento de desempenho format.version.1.1</span><span class="sxs-lookup"><span data-stu-id="13e09-264">Performance improvement format.version.1.1</span></span>  | [<span data-ttu-id="13e09-265">Configuração de formato de ER de exemplo</span><span class="sxs-lookup"><span data-stu-id="13e09-265">Sample ER format configuration</span></span>](https://download.microsoft.com/download/9/0/c/90c75963-bc78-4edc-9096-556bbe281f10/Performance_improvement_format.version.1.1.xml) |

## <a name="appendix-2-configure-the-er-framework"></a><a name="appendix2"></a><span data-ttu-id="13e09-266">Apêndice 2: configurar a estrutura de ER</span><span class="sxs-lookup"><span data-stu-id="13e09-266">Appendix 2: Configure the ER framework</span></span>

<span data-ttu-id="13e09-267">Antes de começar a usar a estrutura de ER para melhorar o desempenho da solução ER de exemplo da Microsoft, você deve configurar o conjunto mínimo de parâmetros ER.</span><span class="sxs-lookup"><span data-stu-id="13e09-267">Before you can start to use the ER framework to improve the performance of the sample Microsoft ER solution, you must configure the minimal set of ER parameters.</span></span>

### <a name="configure-er-parameters"></a><a id="ConfigureParameters"></a><span data-ttu-id="13e09-268">Configurar parâmetros de ER</span><span class="sxs-lookup"><span data-stu-id="13e09-268">Configure ER parameters</span></span>

1. <span data-ttu-id="13e09-269">Vá para **Administração da organização** \> **Espaços de trabalho** \> **Relatório eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="13e09-269">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="13e09-270">Na página **Configurações de localização**, na seção **Links relacionados**, selecione **Parâmetros de relatório eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="13e09-270">On the **Localization configurations** page, in the **Related links** section, select **Electronic reporting parameters**.</span></span>
3. <span data-ttu-id="13e09-271">Na página **Parâmetros de relatório eletrônico**, na guia **Geral**, defina a opção **Habilitar modo de design** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="13e09-271">On the **Electronic reporting parameters** page, on the **General** tab, set the **Enable design mode** option to **Yes**.</span></span>
4. <span data-ttu-id="13e09-272">Na guia **Anexos**, defina os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="13e09-272">On the **Attachments** tab, set the following parameters:</span></span>

    - <span data-ttu-id="13e09-273">No campo **Configurações**, selecione o tipo **Arquivo** para a empresa **DEMF**.</span><span class="sxs-lookup"><span data-stu-id="13e09-273">In the **Configurations** field, select the **File** type for the **DEMF** company.</span></span>
    - <span data-ttu-id="13e09-274">Nos campos **Arquivo de trabalho**, **Temporário**, **Linha de base** e **Outros**, selecione o tipo **Arquivo**.</span><span class="sxs-lookup"><span data-stu-id="13e09-274">In the **Job archive**, **Temporary**, **Baseline**, and **Others** fields, select the **File** type.</span></span>

<span data-ttu-id="13e09-275">Para obter mais informações sobre parâmetros de ER, consulte [Configurar a estrutura de ER](electronic-reporting-er-configure-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="13e09-275">For more information about ER parameters, see [Configure the ER framework](electronic-reporting-er-configure-parameters.md).</span></span>

### <a name="activate-an-er-configuration-provider"></a><a id="ActivateProvider"></a><span data-ttu-id="13e09-276">Ativar um provedor de configuração de ER</span><span class="sxs-lookup"><span data-stu-id="13e09-276">Activate an ER configuration provider</span></span>

<span data-ttu-id="13e09-277">Toda configuração de ER adicionada é marcada como pertencente a um provedor de configuração de ER.</span><span class="sxs-lookup"><span data-stu-id="13e09-277">Every ER configuration that is added is marked as owned by an ER configuration provider.</span></span> <span data-ttu-id="13e09-278">O provedor de configuração de ER ativado no espaço de trabalho **Relatório eletrônico** é usado para essa finalidade.</span><span class="sxs-lookup"><span data-stu-id="13e09-278">The ER configuration provider that is activated in the **Electronic reporting** workspace is used for this purpose.</span></span> <span data-ttu-id="13e09-279">Por isso você deve ativar um provedor de configuração de ER no espaço de trabalho **Relatório eletrônico** antes de começar a adicionar ou editar configurações de ER.</span><span class="sxs-lookup"><span data-stu-id="13e09-279">Therefore, you must activate an ER configuration provider in the **Electronic reporting** workspace before you start to add or edit ER configurations.</span></span>

> [!NOTE]
> <span data-ttu-id="13e09-280">Somente o proprietário de uma configuração ER pode editá-la.</span><span class="sxs-lookup"><span data-stu-id="13e09-280">Only the owner of an ER configuration can edit the configuration.</span></span> <span data-ttu-id="13e09-281">Assim, para que uma configuração de ER possa ser editada, o provedor de configuração de ER apropriado deve estar ativado no espaço de trabalho **Relatório eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="13e09-281">Therefore, before an ER configuration can be edited, the appropriate ER configuration provider must be activated in the **Electronic reporting** workspace.</span></span>

#### <a name="review-the-list-of-er-configuration-providers"></a><a id="ReviewProvidersList"></a><span data-ttu-id="13e09-282">Examinar a lista de provedores de configuração de ER</span><span class="sxs-lookup"><span data-stu-id="13e09-282">Review the list of ER configuration providers</span></span>

1. <span data-ttu-id="13e09-283">Vá para **Administração da organização** \> **Espaços de trabalho** \> **Relatório eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="13e09-283">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="13e09-284">Na página **Configurações de localização**, na seção **Links relacionados**, selecione **Provedores de configuração**.</span><span class="sxs-lookup"><span data-stu-id="13e09-284">On the **Localization configurations** page, in the **Related links** section, select **Configuration providers**.</span></span>
3. <span data-ttu-id="13e09-285">Na página **Tabela de provedores de configuração**, cada registro de provedor tem um nome e uma URL exclusivos.</span><span class="sxs-lookup"><span data-stu-id="13e09-285">On the **Configuration provider table** page, each provider record has a unique name and URL.</span></span> <span data-ttu-id="13e09-286">Examine o conteúdo dessa página.</span><span class="sxs-lookup"><span data-stu-id="13e09-286">Review the contents of this page.</span></span> <span data-ttu-id="13e09-287">Se já existir um registro para **Litware, Inc.**, ignore o próximo procedimento, [Adicionar um novo provedor de configuração ER](#ActivateProvider).</span><span class="sxs-lookup"><span data-stu-id="13e09-287">If a record for **Litware, Inc.** already exists, skip the next procedure, [Add a new ER configuration provider](#ActivateProvider).</span></span>

#### <a name="add-a-new-er-configuration-provider"></a><a id="ActivateProvider"></a><span data-ttu-id="13e09-288">Adicionar um novo provedor de configuração de ER</span><span class="sxs-lookup"><span data-stu-id="13e09-288">Add a new ER configuration provider</span></span>

1. <span data-ttu-id="13e09-289">Vá para **Administração da organização** \> **Espaços de trabalho** \> **Relatório eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="13e09-289">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="13e09-290">Na página **Configurações de localização**, na seção **Links relacionados**, selecione **Provedores de configuração**.</span><span class="sxs-lookup"><span data-stu-id="13e09-290">On the **Localization configurations** page, in the **Related links** section, select **Configuration providers**.</span></span>
3. <span data-ttu-id="13e09-291">Na página **Provedores de configuração**, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="13e09-291">On the **Configuration providers** page, select **New**.</span></span>
4. <span data-ttu-id="13e09-292">No campo **Nome**, insira **Litware, Ltda.**</span><span class="sxs-lookup"><span data-stu-id="13e09-292">In the **Name** field, enter **Litware, Inc.**</span></span>
5. <span data-ttu-id="13e09-293">No campo **Endereço na Internet**, insira `https://www.litware.com`.</span><span class="sxs-lookup"><span data-stu-id="13e09-293">In the **Internet address** field, enter `https://www.litware.com`.</span></span>
6. <span data-ttu-id="13e09-294">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="13e09-294">Select **Save**.</span></span>

#### <a name="activate-an-er-configuration-provider"></a><a id="ActivateAddedProvider"></a><span data-ttu-id="13e09-295">Ativar um provedor de configuração de ER</span><span class="sxs-lookup"><span data-stu-id="13e09-295">Activate an ER configuration provider</span></span>

1. <span data-ttu-id="13e09-296">Vá para **Administração da organização** \> **Espaços de trabalho** \> **Relatório eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="13e09-296">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="13e09-297">Na página **Configurações de localização**, na seção **Provedores de configuração**, selecione o bloco **Litware, Ltda.** e, depois, **Definir como ativo**.</span><span class="sxs-lookup"><span data-stu-id="13e09-297">On the **Localization configurations** page, in the **Configuration providers** section, select the **Litware, Inc.** tile, and then select **Set active**.</span></span>

<span data-ttu-id="13e09-298">Para obter mais informações sobre provedores de configuração de ER, consulte [Criar provedores de configuração e marcá-los como ativos](tasks/er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="13e09-298">For more information about ER configuration providers, see [Create configuration providers and mark them as active](tasks/er-configuration-provider-mark-it-active-2016-11.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="13e09-299">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="13e09-299">Additional resources</span></span>

- [<span data-ttu-id="13e09-300">Visão geral do Relatório Eletrônico</span><span class="sxs-lookup"><span data-stu-id="13e09-300">Electronic Reporting overview</span></span>](general-electronic-reporting.md)
- [<span data-ttu-id="13e09-301">Rastrear a execução de formatos de ER para solucionar problemas de desempenho</span><span class="sxs-lookup"><span data-stu-id="13e09-301">Trace the execution of ER formats to troubleshoot performance issues</span></span>](trace-execution-er-troubleshoot-perf.md)
- [<span data-ttu-id="13e09-302">Suporte a chamadas parametrizadas de fontes de dados de ER do tipo Campo calculado</span><span class="sxs-lookup"><span data-stu-id="13e09-302">Support parameterized calls of ER data sources of the Calculated field type</span></span>](er-calculated-field-type.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
