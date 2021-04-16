---
title: Depurar fontes de dados de um formato de relatório eletrônico executado para analisar o fluxo de dados e a transformação
description: Este tópico explica como você pode depurar as fontes de dados de um formato de relatório executado para compreender melhor o fluxo de dados configurado e a transformação.
author: NickSelin
ms.date: 04/22/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, EROperationDesigner
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-04-01
ms.dyn365.ops.version: Release 10.0.11
ms.openlocfilehash: fe3e6a4223fc8b26e523a982a2e1752a34b370de
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5753663"
---
# <a name="debug-data-sources-of-an-executed-er-format-to-analyze-data-flow-and-transformation"></a><span data-ttu-id="94d02-103">Depurar fontes de dados de um formato de relatório eletrônico executado para analisar o fluxo de dados e a transformação</span><span class="sxs-lookup"><span data-stu-id="94d02-103">Debug data sources of an executed ER format to analyze data flow and transformation</span></span>

[!include[banner](../includes/banner.md)]

[!include[banner](../includes/preview-banner.md)]

<span data-ttu-id="94d02-104">Ao [configurar](tasks/er-format-configuration-2016-11.md) uma solução do relatório eletrônico (ER) para gerar documentos de saída, você define os métodos usados para obter os dados do aplicativo e inseri-los na saída gerada.</span><span class="sxs-lookup"><span data-stu-id="94d02-104">When you [configure](tasks/er-format-configuration-2016-11.md) an Electronic reporting (ER) solution to generate outbound documents, you define the methods that are used to get data out of the application and enter it in the output that is generated.</span></span> <span data-ttu-id="94d02-105">Para tornar o suporte ao ciclo de vida da solução de ER mais eficiente, a sua solução deve consistir em um [modelo de dados](general-electronic-reporting.md#DataModelComponent) de ER e seus componentes de [mapeamento](general-electronic-reporting.md#ModelMappingComponent), além de um [formato](general-electronic-reporting.md#FormatComponentOutbound) de ER e seus componentes de mapeamento, para que o mapeamento do modelo seja específico para o aplicativo, enquanto outros componentes permanecem independentes do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="94d02-105">To make the life cycle support of the ER solution more efficient, your solution should consist of an ER [data model](general-electronic-reporting.md#DataModelComponent) and its [mapping](general-electronic-reporting.md#ModelMappingComponent) components, and also an ER [format](general-electronic-reporting.md#FormatComponentOutbound) and its mapping components, so that the model mapping is application-specific, whereas other components remain application-agnostic.</span></span> <span data-ttu-id="94d02-106">Portanto, vários componentes do ER podem [afetar](general-electronic-reporting.md#FormatComponentOutbound) o processo de inserir dados na saída gerada.</span><span class="sxs-lookup"><span data-stu-id="94d02-106">Therefore, several ER components might [affect](general-electronic-reporting.md#FormatComponentOutbound) the process of entering data in the generated output.</span></span>

<span data-ttu-id="94d02-107">Às vezes, os dados da saída gerada parecem diferentes dos mesmos dados no banco de dados do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="94d02-107">Sometimes, the data of the generated output looks different than the same data in the application database.</span></span> <span data-ttu-id="94d02-108">Nesses casos, será necessário determinar qual componente do ER é responsável pela transformação dos dados.</span><span class="sxs-lookup"><span data-stu-id="94d02-108">In these cases, you will want to determine which ER component is responsible for the data transformation.</span></span> <span data-ttu-id="94d02-109">O recurso do depurador da fonte de dados do ER reduz significativamente o tempo e o custo envolvidos nesta investigação.</span><span class="sxs-lookup"><span data-stu-id="94d02-109">The ER data source debugger feature significantly reduces the time and cost that are involved in this investigation.</span></span> <span data-ttu-id="94d02-110">Você pode interromper a execução de um formato de ER e abrir a interface do depurador da fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="94d02-110">You can interrupt the execution of an ER format and open the data source debugger interface.</span></span> <span data-ttu-id="94d02-111">Nela, é possível procurar as fontes de dados disponíveis e selecionar uma fonte de dados individual para execução.</span><span class="sxs-lookup"><span data-stu-id="94d02-111">There, you can browse the available data sources and select an individual data source for execution.</span></span> <span data-ttu-id="94d02-112">Esta execução manual simula a execução da fonte de dados durante a execução real de um formato de ER.</span><span class="sxs-lookup"><span data-stu-id="94d02-112">This manual execution simulates the execution of the data source during the real run of an ER format.</span></span> <span data-ttu-id="94d02-113">O resultado é apresentado em uma página na qual você pode analisar os dados recebidos.</span><span class="sxs-lookup"><span data-stu-id="94d02-113">The result is presented on a page where you can analyze the data that is received.</span></span>

<span data-ttu-id="94d02-114">Para ativar o recurso de depuração da fonte de dados, defina a opção **Habilitar depuração de dados na execução do formato** como **Sim** nos parâmetros de usuário do ER.</span><span class="sxs-lookup"><span data-stu-id="94d02-114">To turn on the data source debugging feature, set the **Enable data debugging at format run** option to **Yes** in the ER user parameters.</span></span> <span data-ttu-id="94d02-115">Em seguida, você pode iniciar a depuração da fonte de dados enquanto executa o formato de ER para gerar documentos de saída.</span><span class="sxs-lookup"><span data-stu-id="94d02-115">You can then start data source debugging while you run an ER format to generate outbound documents.</span></span> <span data-ttu-id="94d02-116">Você também pode usar a opção **Iniciar depuração** para iniciar a depuração da fonte de dados para um formato de ER configurado no [Designer da operação do ER](./tasks/er-format-configuration-2016-11.md#design-the-format-of-an-electronic-document).</span><span class="sxs-lookup"><span data-stu-id="94d02-116">You can also use the **Start debugging** option to initiate data source debugging for an ER format that is configured in the [ER Operation designer](./tasks/er-format-configuration-2016-11.md#design-the-format-of-an-electronic-document).</span></span>

<span data-ttu-id="94d02-117">Este tópico fornece diretrizes para iniciar a depuração da fonte de dados para formatos de ER executados.</span><span class="sxs-lookup"><span data-stu-id="94d02-117">This topic provides guidelines for initiating data source debugging for executed ER formats.</span></span> <span data-ttu-id="94d02-118">Ele explica como as informações podem ajudar você a entender o fluxo e as transformações de dados.</span><span class="sxs-lookup"><span data-stu-id="94d02-118">It explains how the information can help you understand the data flow and data transformations.</span></span> <span data-ttu-id="94d02-119">Os exemplos neste tópico usam o processo de negócios para o processamento de pagamentos de fornecedores.</span><span class="sxs-lookup"><span data-stu-id="94d02-119">The examples in this topic use the business process for vendor payments processing.</span></span>

## <a name="limitations"></a><span data-ttu-id="94d02-120">Limitações</span><span class="sxs-lookup"><span data-stu-id="94d02-120">Limitations</span></span>

<span data-ttu-id="94d02-121">O depurador da fonte de dados pode ser usado para acessar os dados de fontes de dados usadas em formatos de ER executados para gerar documentos de saída.</span><span class="sxs-lookup"><span data-stu-id="94d02-121">The data source debugger can be used to access the data of data sources that are used in ER formats that are run to generate outbound documents.</span></span> <span data-ttu-id="94d02-122">Ele não pode ser usado para depurar fontes de dados de formatos de ER criadas para analisar documentos de entrada.</span><span class="sxs-lookup"><span data-stu-id="94d02-122">It can't be used to debug data sources of ER formats that are designed to parse inbound documents.</span></span>

<span data-ttu-id="94d02-123">As seguintes configurações de formatos de ER não estão acessíveis no momento para a depuração da fonte de dados:</span><span class="sxs-lookup"><span data-stu-id="94d02-123">The following settings of ER formats aren't currently accessible for data source debugging:</span></span>

- <span data-ttu-id="94d02-124">Transformações de formatos</span><span class="sxs-lookup"><span data-stu-id="94d02-124">Format transformations</span></span>
- <span data-ttu-id="94d02-125">Regras de validação de mapeamento e formato</span><span class="sxs-lookup"><span data-stu-id="94d02-125">Format and mapping validation rules</span></span>
- <span data-ttu-id="94d02-126">Habilitar expressões</span><span class="sxs-lookup"><span data-stu-id="94d02-126">Enabling expressions</span></span>
- <span data-ttu-id="94d02-127">Detalhes da coleta de dados na memória</span><span class="sxs-lookup"><span data-stu-id="94d02-127">Details of in-memory data collection</span></span>

## <a name="prerequisites"></a><span data-ttu-id="94d02-128">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="94d02-128">Prerequisites</span></span>

- <span data-ttu-id="94d02-129">Para concluir os exemplos deste tópico, você deve ter acesso a uma das seguintes [funções](../sysadmin/tasks/assign-users-security-roles.md):</span><span class="sxs-lookup"><span data-stu-id="94d02-129">To complete the examples in this topic, you must have the access to one of the following [roles](../sysadmin/tasks/assign-users-security-roles.md):</span></span>

    - <span data-ttu-id="94d02-130">Desenvolvedor de relatório eletrônico</span><span class="sxs-lookup"><span data-stu-id="94d02-130">Electronic reporting developer</span></span>
    - <span data-ttu-id="94d02-131">Consultor funcional de relatório eletrônico</span><span class="sxs-lookup"><span data-stu-id="94d02-131">Electronic reporting functional consultant</span></span>
    - <span data-ttu-id="94d02-132">Administrador do sistema</span><span class="sxs-lookup"><span data-stu-id="94d02-132">System administrator</span></span>

- <span data-ttu-id="94d02-133">A empresa deve ser definida como **DEMF**.</span><span class="sxs-lookup"><span data-stu-id="94d02-133">The company must be set to **DEMF**.</span></span>

- <span data-ttu-id="94d02-134">Siga as etapas no [Apêndice 1](#appendix1) deste tópico para baixar os componentes da solução do Microsoft ER necessários para processar os pagamentos de fornecedores.</span><span class="sxs-lookup"><span data-stu-id="94d02-134">Follow the steps in [Appendix 1](#appendix1) of this topic to download the components of the Microsoft ER solution that are required to process vendor payments.</span></span>
- <span data-ttu-id="94d02-135">Siga as etapas no [Apêndice 2](#appendix2) deste tópico para preparar o recurso Contas a pagar para o processamento de pagamentos de fornecedores usando a solução de ER que você obterá por download.</span><span class="sxs-lookup"><span data-stu-id="94d02-135">Follow the steps in [Appendix 2](#appendix2) of this topic to prepare Accounts payable for vendor payment processing by using the ER solution that you will download.</span></span>

## <a name="process-a-vendor-payment-to-get-a-payment-file"></a><span data-ttu-id="94d02-136">Processar um pagamento do fornecedor para obter um arquivo de pagamento</span><span class="sxs-lookup"><span data-stu-id="94d02-136">Process a vendor payment to get a payment file</span></span>

1. <span data-ttu-id="94d02-137">Siga as etapas no [Apêndice 3](#appendix3) deste tópico para processar os pagamentos de fornecedores.</span><span class="sxs-lookup"><span data-stu-id="94d02-137">Follow the steps in [Appendix 3](#appendix3) of this topic to process vendor payments.</span></span>

    ![Processamento de pagamento do fornecedor em andamento](./media/er-data-debugger-process-payment.png)

2. <span data-ttu-id="94d02-139">Baixe e salve o arquivo zip no computador local.</span><span class="sxs-lookup"><span data-stu-id="94d02-139">Download and save the zip file to your local computer.</span></span>
3. <span data-ttu-id="94d02-140">Extraia o arquivo de pagamento **ISO20022 Credit transfer.xml** do arquivo zip.</span><span class="sxs-lookup"><span data-stu-id="94d02-140">Extract the **ISO20022 Credit transfer.xml** payment file from the zip file.</span></span>
4. <span data-ttu-id="94d02-141">Abra o arquivo de pagamento extraído usando o visualizador de arquivos XML.</span><span class="sxs-lookup"><span data-stu-id="94d02-141">Open the extracted payment file by using the XML file viewer.</span></span>

    <span data-ttu-id="94d02-142">No arquivo de pagamento, o código do número da conta bancária internacional (IBAN) da conta bancária do fornecedor não contém espaços.</span><span class="sxs-lookup"><span data-stu-id="94d02-142">In the payment file, the International Bank Account Number (IBAN) code of the vendor bank account contains no spaces.</span></span> <span data-ttu-id="94d02-143">Portanto, difere do valor [inserido](#enteredIBANcode) na página **Contas bancárias**.</span><span class="sxs-lookup"><span data-stu-id="94d02-143">Therefore, it differs from the value that was [entered](#enteredIBANcode) on the **Bank accounts** page.</span></span>

    ![Código IBAN sem espaços](./media/er-data-debugger-payment-file.png)

    <span data-ttu-id="94d02-145">Você pode usar o depurador da fonte de dados do ER para saber qual componente da solução de ER é usado para truncar espaços no código IBAN.</span><span class="sxs-lookup"><span data-stu-id="94d02-145">You can use the ER data source debugger to learn which component of the ER solution is used to truncate spaces in the IBAN code.</span></span>

## <a name="turn-on-data-source-debugging"></a><span data-ttu-id="94d02-146">Ativar depuração da fonte de dados</span><span class="sxs-lookup"><span data-stu-id="94d02-146">Turn on data source debugging</span></span>

1. <span data-ttu-id="94d02-147">Vá para **Administração da organização** \> **Relatório eletrônico** \> **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="94d02-147">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="94d02-148">Na página **Configurações**, no Painel Ação, na guia **Configurações**, no grupo **Configurações avançadas**, selecione **Parâmetros de usuário**.</span><span class="sxs-lookup"><span data-stu-id="94d02-148">On the **Configurations** page, on the Action Pane, on the **Configurations** tab, in the **Advanced settings** group, select **User parameters**.</span></span>
3. <span data-ttu-id="94d02-149">Defina a opção **Habilitar depuração de dados na execução do formato** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="94d02-149">Set the **Enable data debugging at format run** option to **Yes**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="94d02-150">Esse parâmetro é específico do usuário e da empresa.</span><span class="sxs-lookup"><span data-stu-id="94d02-150">This parameter is user-specific and company-specific.</span></span>

    ![Caixa de diálogo de parâmetros do usuário](./media/er-data-debugger-user-parameters.png)

## <a name="process-a-vendor-payment-for-debugging"></a><span data-ttu-id="94d02-152">Processar um pagamento de fornecedor para depuração</span><span class="sxs-lookup"><span data-stu-id="94d02-152">Process a vendor payment for debugging</span></span>

1. <span data-ttu-id="94d02-153">Siga as etapas no [Apêndice 3](#appendix3) deste tópico para processar os pagamentos de fornecedores.</span><span class="sxs-lookup"><span data-stu-id="94d02-153">Follow the steps in [Appendix 3](#appendix3) of this topic to process vendor payments.</span></span>
2. <span data-ttu-id="94d02-154">Na caixa de mensagem, selecione **Sim** para confirmar que deseja interromper o processamento de pagamentos de fornecedores e iniciar a depuração da fonte de dados na página **Depurar fontes de dados**.</span><span class="sxs-lookup"><span data-stu-id="94d02-154">In the message box, select **Yes** to confirm that you want to interrupt vendor payment processing and instead start data source debugging on the **Debug Datasources** page.</span></span>

    ![Caixa de mensagem de confirmação](./media/er-data-debugger-start-debugging.png)

## <a name="debug-data-sources-that-are-used-in-payment-processing"></a><span data-ttu-id="94d02-156">Depurar fontes de dados usadas no processamento de pagamentos</span><span class="sxs-lookup"><span data-stu-id="94d02-156">Debug data sources that are used in payment processing</span></span>

### <a name="debug-the-model-mapping"></a><span data-ttu-id="94d02-157">Depurar o mapeamento de modelos</span><span class="sxs-lookup"><span data-stu-id="94d02-157">Debug the model mapping</span></span>

1. <span data-ttu-id="94d02-158">Na página **Depurar fontes de dados**, no Painel de Ações, selecione **Mapeamento de modelo** para iniciar a depuração deste componente de ER.</span><span class="sxs-lookup"><span data-stu-id="94d02-158">On the **Debug Datasources** page, on the Action Pane, select **Model mapping** to start to debug from this ER component.</span></span>
2. <span data-ttu-id="94d02-159">No painel da fonte de dados à esquerda, selecione a fonte de dados **\$notSentTransactions** e selecione **Ler todos os registros**.</span><span class="sxs-lookup"><span data-stu-id="94d02-159">In the data source pane on the left, select the **\$notSentTransactions** data source, and then select **Read all records**.</span></span>

    <span data-ttu-id="94d02-160">Você pode selecionar **Ler 1 registro**, **Ler 10 registros**, **Ler 100 registros** ou **Ler todos os registros** para forçar o número apropriado de registros a serem lidos na fonte de dados selecionada.</span><span class="sxs-lookup"><span data-stu-id="94d02-160">You can select **Read 1 record**, **Read 10 records**, **Read 100 records**, or **Read all records** to force the appropriate number of records to be read from the selected data source.</span></span> <span data-ttu-id="94d02-161">Dessa forma, você pode simular o acesso à fonte de dados do formato de ER em execução.</span><span class="sxs-lookup"><span data-stu-id="94d02-161">In this way, you can simulate access to the data source from the running ER format.</span></span>

3. <span data-ttu-id="94d02-162">No painel de dados à direita, selecione **Expandir tudo**.</span><span class="sxs-lookup"><span data-stu-id="94d02-162">In the data pane on the right, select **Expand all**.</span></span>

    <span data-ttu-id="94d02-163">Você pode ver que a fonte de dados selecionada do tipo **Lista de registros** contém um único registro.</span><span class="sxs-lookup"><span data-stu-id="94d02-163">You can see that the selected data source of the **Record list** type contains a single record.</span></span>

4. <span data-ttu-id="94d02-164">Expanda a fonte de dados **\$notSentTransactions** e selecione o método **vendBankAccountInTransactionCompany()** aninhado.</span><span class="sxs-lookup"><span data-stu-id="94d02-164">Expand the **\$notSentTransactions** data source, and select the nested **vendBankAccountInTransactionCompany()** method.</span></span>
5. <span data-ttu-id="94d02-165">Expanda o método **vendBankAccountInTransactionCompany()** e selecione o campo **IBAN** aninhado.</span><span class="sxs-lookup"><span data-stu-id="94d02-165">Expand the **vendBankAccountInTransactionCompany()** method, and select the nested **IBAN** field.</span></span>
6. <span data-ttu-id="94d02-166">Selecione **Obter valor**.</span><span class="sxs-lookup"><span data-stu-id="94d02-166">Select **Get value**.</span></span>

    <span data-ttu-id="94d02-167">Você pode selecionar **Obter valor** para forçar a leitura do valor de um campo selecionado da fonte de dados selecionada.</span><span class="sxs-lookup"><span data-stu-id="94d02-167">You can select **Get value** to force the value of a selected field of the selected data source to be read.</span></span> <span data-ttu-id="94d02-168">Dessa forma, você pode simular o acesso a esse campo do formato de ER em execução.</span><span class="sxs-lookup"><span data-stu-id="94d02-168">In this way, you can simulate access to this field from the running ER format.</span></span>

7. <span data-ttu-id="94d02-169">Selecione **Expandir tudo**.</span><span class="sxs-lookup"><span data-stu-id="94d02-169">Select **Expand all**.</span></span>

    ![Valor do campo IBAN no mapeamento de modelos](./media/er-data-debugger-debugging-model-mapping.png)

    <span data-ttu-id="94d02-171">Como pode ver, o mapeamento de modelos não é responsável pelos espaços truncados, pois o código IBAN retornado para a conta bancária do fornecedor inclui espaços.</span><span class="sxs-lookup"><span data-stu-id="94d02-171">As you can see, the model mapping isn't responsible for the truncated spaces, because the IBAN code that it returns for the vendor bank account includes spaces.</span></span> <span data-ttu-id="94d02-172">Portanto, é necessário continuar a depuração da fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="94d02-172">Therefore, you must continue data source debugging.</span></span>

### <a name="debug-the-format-mapping"></a><span data-ttu-id="94d02-173">Depurar o mapeamento de formato</span><span class="sxs-lookup"><span data-stu-id="94d02-173">Debug the format mapping</span></span>

1. <span data-ttu-id="94d02-174">Na página **Depurar fontes de dados**, no Painel de Ações, selecione **Mapeamento de formato** para continuar a depuração deste componente de ER.</span><span class="sxs-lookup"><span data-stu-id="94d02-174">On the **Debug Datasources** page, on the Action Pane, select **Format mapping** to continue to debug from this ER component.</span></span>
2. <span data-ttu-id="94d02-175">Selecione a fonte de dados **\$PaymentByDebtor** e selecione **Ler todos os registros**.</span><span class="sxs-lookup"><span data-stu-id="94d02-175">Select the **\$PaymentByDebtor** data source, and then select **Read all records**.</span></span>
3. <span data-ttu-id="94d02-176">Expanda **\$PaymentByDebtor**.</span><span class="sxs-lookup"><span data-stu-id="94d02-176">Expand **\$PaymentByDebtor**.</span></span>
4. <span data-ttu-id="94d02-177">Expanda **\$PaymentByDebtor.Lines** e selecione **Ler todos os registros**.</span><span class="sxs-lookup"><span data-stu-id="94d02-177">Expand **\$PaymentByDebtor.Lines**, and then select **Read all records**.</span></span>
5. <span data-ttu-id="94d02-178">Expanda **\$PaymentByDebtor.Lines.CreditorAccount**.</span><span class="sxs-lookup"><span data-stu-id="94d02-178">Expand **\$PaymentByDebtor.Lines.CreditorAccount**.</span></span>
6. <span data-ttu-id="94d02-179">Expanda **\$PaymentByDebtor.Lines.CreditorAccount.Identification** e selecione **\$PaymentByDebtor.Lines.CreditorAccount.Identification.IBAN**.</span><span class="sxs-lookup"><span data-stu-id="94d02-179">Expand **\$PaymentByDebtor.Lines.CreditorAccount.Identification**, and then select **\$PaymentByDebtor.Lines.CreditorAccount.Identification.IBAN**.</span></span>
7. <span data-ttu-id="94d02-180">Selecione **Obter valor**.</span><span class="sxs-lookup"><span data-stu-id="94d02-180">Select **Get value**.</span></span>
8. <span data-ttu-id="94d02-181">Selecione **Expandir tudo**.</span><span class="sxs-lookup"><span data-stu-id="94d02-181">Select **Expand all**.</span></span>

    ![Valor do campo IBAN no mapeamento de formato](./media/er-data-debugger-debugging-format-mapping.png)

    <span data-ttu-id="94d02-183">Como pode ver, as fontes de dados do mapeamento de formato não são responsáveis pelos espaços truncados, pois o código IBAN retornado para a conta bancária do fornecedor inclui espaços.</span><span class="sxs-lookup"><span data-stu-id="94d02-183">As you can see, the data sources of the format mapping aren't responsible for the truncated spaces, because the IBAN code that they return for the vendor bank account includes spaces.</span></span> <span data-ttu-id="94d02-184">Portanto, é necessário continuar a depuração da fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="94d02-184">Therefore, you must continue data source debugging.</span></span>

### <a name="debug-the-format"></a><span data-ttu-id="94d02-185">Depurar o formato</span><span class="sxs-lookup"><span data-stu-id="94d02-185">Debug the format</span></span>

1. <span data-ttu-id="94d02-186">Na página **Depurar fontes de dados**, no Painel de Ações, selecione **Formato** para continuar a depuração deste componente de ER.</span><span class="sxs-lookup"><span data-stu-id="94d02-186">On the **Debug Datasources** page, on the Action Pane, select **Format** to continue to debug from this ER component.</span></span>
2. <span data-ttu-id="94d02-187">Expanda os elementos de formato para selecionar **ISO20022CTReports** \> **XMLHeader** \> **Documento** \> **CstmrCdtTrfInitn** \> **PmtInf** e, em seguida, selecionar **Ler todos os registros**.</span><span class="sxs-lookup"><span data-stu-id="94d02-187">Expand the format elements to select **ISO20022CTReports** \> **XMLHeader** \> **Document** \> **CstmrCdtTrfInitn** \> **PmtInf**, and then select **Read all records**.</span></span>
3. <span data-ttu-id="94d02-188">Expanda os elementos de formato para selecionar **ISO20022CTReports** \> **XMLHeader** \> **Documento** \> **CstmrCdtTrfInitn** \> **PmtInf** \> **CdtTrfTxInf** e, em seguida, selecionar **Ler todos os registros**.</span><span class="sxs-lookup"><span data-stu-id="94d02-188">Expand the format elements to select **ISO20022CTReports** \> **XMLHeader** \> **Document** \> **CstmrCdtTrfInitn** \> **PmtInf** \> **CdtTrfTxInf**, and then select **Read all records**.</span></span>
4. <span data-ttu-id="94d02-189">Expanda os elementos de formato para selecionar **ISO20022CTReports** \> **XMLHeader** \> **Documento** \> **CstmrCdtTrfInitn** \> **PmtInf** \> **CdtTrfTxInf** \> **CdtrAcct** \> **Id** \> **IBAN** \> **BankIBAN** e, em seguida, selecionar **Obter valor**.</span><span class="sxs-lookup"><span data-stu-id="94d02-189">Expand the format elements to select **ISO20022CTReports** \> **XMLHeader** \> **Document** \> **CstmrCdtTrfInitn** \> **PmtInf** \> **CdtTrfTxInf** \> **CdtrAcct** \> **Id** \> **IBAN** \> **BankIBAN**, and then select **Get value**.</span></span>
5. <span data-ttu-id="94d02-190">Selecione **Expandir tudo**.</span><span class="sxs-lookup"><span data-stu-id="94d02-190">Select **Expand all**.</span></span>

    ![Valor do campo IBAN no formato](./media/er-data-debugger-debugging-format.png)

   <span data-ttu-id="94d02-192">Como pode ver, a associação de formato não é responsável pelos espaços truncados, pois o código IBAN retornado para a conta bancária do fornecedor inclui espaços.</span><span class="sxs-lookup"><span data-stu-id="94d02-192">As you can see, the format binding isn't responsible for the truncated spaces because the IBAN code that it returns for the vendor bank account includes spaces.</span></span> <span data-ttu-id="94d02-193">Portanto, o elemento **BankIBAN** está configurado para usar uma transformação de formato que trunca os espaços.</span><span class="sxs-lookup"><span data-stu-id="94d02-193">Therefore, the **BankIBAN** element is configured to use a format transformation that truncates spaces.</span></span>

6. <span data-ttu-id="94d02-194">Feche o depurador da fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="94d02-194">Close the data source debugger.</span></span>

### <a name="review-the-format-transformations"></a><span data-ttu-id="94d02-195">Revise as transformações de formato</span><span class="sxs-lookup"><span data-stu-id="94d02-195">Review the format transformations</span></span>

1. <span data-ttu-id="94d02-196">Vá para **Administração da organização** \> **Relatório eletrônico** \> **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="94d02-196">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="94d02-197">Na página **Configurações**, selecione **Modelo de pagamento** \> **Transferência de crédito ISO20022**.</span><span class="sxs-lookup"><span data-stu-id="94d02-197">On the **Configurations** page, select **Payment model** \> **ISO20022 Credit transfer**.</span></span>
3. <span data-ttu-id="94d02-198">Selecione **Designer** e expanda os elementos para selecionar **Documento** \> **CstmrCdtTrfInitn** \> **PmtInf** \> **CdtTrfTxInf** \> **CdtrAcct** \> **Id** \> **IBAN** \> **BankIBAN**.</span><span class="sxs-lookup"><span data-stu-id="94d02-198">Select **Designer**, and then expand the elements to select **Document** \> **CstmrCdtTrfInitn** \> **PmtInf** \> **CdtTrfTxInf** \> **CdtrAcct** \> **Id** \> **IBAN** \> **BankIBAN**.</span></span>

    ![Elemento BankIBAN na página Designer de formato](./media/er-data-debugger-referred-transformation.png)

    <span data-ttu-id="94d02-200">Como pode ver, o elemento **BankIBAN** está configurado para usar a transformação **remover não alfanuméricos**.</span><span class="sxs-lookup"><span data-stu-id="94d02-200">As you can see, the **BankIBAN** element is configured to use the **remove not alphanumeric** transformation.</span></span>

4. <span data-ttu-id="94d02-201">Selecione a guia **Transformações**.</span><span class="sxs-lookup"><span data-stu-id="94d02-201">Select the **Transformations** tab.</span></span>

    ![Guia Transformações para o elemento BankIBAN](./media/er-data-debugger-transformation.png)

    <span data-ttu-id="94d02-203">Como pode ver, a transformação **remover não alfanumérico** está configurada para usar uma expressão que trunca os espaços da cadeia de texto fornecida.</span><span class="sxs-lookup"><span data-stu-id="94d02-203">As you can see, the **remove not alphanumeric** transformation is configured to use an expression that truncates spaces from the text string that is provided.</span></span>

## <a name="start-to-debug-in-the-operation-designer"></a><span data-ttu-id="94d02-204">Iniciar depuração no Designer da operação</span><span class="sxs-lookup"><span data-stu-id="94d02-204">Start to debug in the Operation designer</span></span>

<span data-ttu-id="94d02-205">Ao configurar uma versão de rascunho do formato de ER que pode ser executado diretamente do Designer da operação, você pode acessar o depurador da fonte de dados selecionando **Iniciar Depuração** no Painel de Ações.</span><span class="sxs-lookup"><span data-stu-id="94d02-205">When you configure a draft version of the ER format that can be run directly from the Operation designer, you can access the data source debugger by selecting **Start Debugging** on the Action Pane.</span></span>

![Botão Iniciar Depuração na página do Designer de formato](./media/er-data-debugger-run-from-designer.png)

<span data-ttu-id="94d02-207">Os componentes do mapeamento de formato e do formato de ER que estão sendo editados estão disponíveis para depuração.</span><span class="sxs-lookup"><span data-stu-id="94d02-207">The format mapping and format components of the ER format that is being edited are available for debugging.</span></span>

## <a name="start-to-debug-in-the-model-mapping-designer"></a><span data-ttu-id="94d02-208">Iniciar depuração no Designer do mapeamento de modelos</span><span class="sxs-lookup"><span data-stu-id="94d02-208">Start to debug in the Model mapping designer</span></span>

<span data-ttu-id="94d02-209">Ao configurar um mapeamento de modelos de ER que pode ser executado diretamente da página **Mapeamento de modelos**, você pode acessar o depurador da fonte de dados selecionando **Iniciar Depuração** no Painel de Ações.</span><span class="sxs-lookup"><span data-stu-id="94d02-209">When you configure an ER model mapping that can be run from the **Model mapping** page, you can access the data source debugger by selecting **Start Debugging** on the Action Pane.</span></span>

![Botão Iniciar Depuração na página do Designer do mapeamento de modelos](./media/er-data-debugger-run-from-designer-mapping.png)

<span data-ttu-id="94d02-211">O componente de mapeamento de modelos do mapeamento de ER que está sendo editado está disponível para depuração.</span><span class="sxs-lookup"><span data-stu-id="94d02-211">The model mapping component of the ER mapping that is being edited is available for debugging.</span></span>

## <a name="appendix-1-get-an-er-solution"></a><a name="appendix1"></a><span data-ttu-id="94d02-212">Apêndice 1: Obter uma solução de ER</span><span class="sxs-lookup"><span data-stu-id="94d02-212">Appendix 1: Get an ER solution</span></span>

### <a name="download-an-er-solution"></a><span data-ttu-id="94d02-213">Baixar uma solução de ER</span><span class="sxs-lookup"><span data-stu-id="94d02-213">Download an ER solution</span></span>

<span data-ttu-id="94d02-214">Se deseja usar uma solução de ER para gerar um arquivo de pagamento eletrônico para um pagamento de fornecedor que já foi processado, você pode [baixar](download-electronic-reporting-configuration-lcs.md) o formato de pagamento de ER **Transferência de crédito ISO20022** disponível na biblioteca de Ativos compartilhados no Microsoft Dynamics Lifecycle Services (LCS) ou no repositório Global.</span><span class="sxs-lookup"><span data-stu-id="94d02-214">If you want to use an ER solution to generate an electronic payment file for a vendor payment that is processed, you can [download](download-electronic-reporting-configuration-lcs.md) the **ISO20022 Credit transfer** ER payment format that is available from the Shared asset library in Microsoft Dynamics Lifecycle Services (LCS) or from the Global repository.</span></span>

![Importar o formato de pagamento de ER na página do Repositório de configuração](./media/er-data-debugger-import-from-repo.png)

<span data-ttu-id="94d02-216">Além do formato de ER selecionado, as [configurações](general-electronic-reporting.md#Configuration) a seguir devem ser importadas automaticamente para a instância do Microsoft Dynamics 365 Finance como parte da solução de ER **Transferência de crédito ISO20022**:</span><span class="sxs-lookup"><span data-stu-id="94d02-216">In addition to the selected ER format, the following [configurations](general-electronic-reporting.md#Configuration) must be automatically imported into your Microsoft Dynamics 365 Finance instance as part of the **ISO20022 Credit transfer** ER solution:</span></span>

- <span data-ttu-id="94d02-217">[Configuração do modelo de dados de ER](general-electronic-reporting.md#DataModelComponent) do **Modelo de pagamento**</span><span class="sxs-lookup"><span data-stu-id="94d02-217">**Payment model** [ER data model configuration](general-electronic-reporting.md#DataModelComponent)</span></span>
- <span data-ttu-id="94d02-218">[Configuração do formato de ER](general-electronic-reporting.md#FormatComponentOutbound) **Transferência de crédito ISO20022**</span><span class="sxs-lookup"><span data-stu-id="94d02-218">**ISO20022 Credit transfer** [ER format configuration](general-electronic-reporting.md#FormatComponentOutbound)</span></span>
- <span data-ttu-id="94d02-219">[Configuração do mapeamento de modelos de ER](general-electronic-reporting.md#ModelMappingComponent) **Mapeamento de modelos de pagamento 1611**</span><span class="sxs-lookup"><span data-stu-id="94d02-219">**Payment model mapping 1611** [ER model mapping configuration](general-electronic-reporting.md#ModelMappingComponent)</span></span>
- <span data-ttu-id="94d02-220">Configuração do mapeamento de modelos de ER **Mapeamento de modelos de pagamento para o destino ISO20022**</span><span class="sxs-lookup"><span data-stu-id="94d02-220">**Payment model mapping to destination ISO20022** ER model mapping configuration</span></span>

<span data-ttu-id="94d02-221">Você pode encontrar essas configurações na página **Configurações** da estrutura do ER (**Administração da organização** \> **Relatório eletrônico** \> **Configurações**).</span><span class="sxs-lookup"><span data-stu-id="94d02-221">You can find these configurations on the **Configurations** page of the ER framework (**Organization administration** \> **Electronic reporting** \> **Configurations**).</span></span>

![Configurações importadas na página Configurações](./media/er-data-debugger-configurations.png)

<span data-ttu-id="94d02-223">Se qualquer uma das configurações listadas estiver ausente na árvore de configuração, será necessário baixá-la manualmente da biblioteca de Ativos compartilhados do LCS, da mesma forma como baixou o formato de pagamento de ER **Transferência de crédito ISO20022**.</span><span class="sxs-lookup"><span data-stu-id="94d02-223">If any of the previously listed configurations are missing in the configuration tree, you must manually download them from the LCS Shared asset library in the same way that you downloaded the **ISO20022 Credit transfer** ER payment format.</span></span>

### <a name="analyze-the-downloaded-er-solution"></a><span data-ttu-id="94d02-224">Analisar a solução de ER baixada</span><span class="sxs-lookup"><span data-stu-id="94d02-224">Analyze the downloaded ER solution</span></span>

#### <a name="review-the-model-mapping"></a><span data-ttu-id="94d02-225">Revisar o mapeamento de modelos</span><span class="sxs-lookup"><span data-stu-id="94d02-225">Review the model mapping</span></span>

1. <span data-ttu-id="94d02-226">Vá para **Administração da organização** \> **Relatório eletrônico** \> **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="94d02-226">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="94d02-227">Selecione **Modelo de pagamento** \> **Mapeamento de modelos de pagamento 1611**.</span><span class="sxs-lookup"><span data-stu-id="94d02-227">Select **Payment model** \> **Payment model mapping 1611**.</span></span>
3. <span data-ttu-id="94d02-228">Selecione **Designer**.</span><span class="sxs-lookup"><span data-stu-id="94d02-228">Select **Designer**.</span></span>
4. <span data-ttu-id="94d02-229">Selecione o registro de mapeamento **Mapeamento de modelos de pagamento ISO20022 CT**.</span><span class="sxs-lookup"><span data-stu-id="94d02-229">Select the **Payment model mapping ISO20022 CT** mapping record.</span></span>
5. <span data-ttu-id="94d02-230">Selecione **Designer** e revise o mapeamento de modelos aberto.</span><span class="sxs-lookup"><span data-stu-id="94d02-230">Select **Designer**, and then review the model mapping that is opened.</span></span>

    <span data-ttu-id="94d02-231">Observe que o campo **Pagamentos** do modelo de dados está vinculado à fonte de dados **\$notSentTransactions** que retorna a lista de linhas de pagamento de fornecedores que estão sendo processadas.</span><span class="sxs-lookup"><span data-stu-id="94d02-231">Notice that the **Payments** field of the data model is bound to the **\$notSentTransactions** data source that returns the list of vendor payment lines that are being processed.</span></span>

    ![Campo Pagamentos na página do designer de mapeamento de modelos](./media/er-data-debugger-model-mapping.png)

#### <a name="review-the-format-mapping"></a><span data-ttu-id="94d02-233">Revisar o mapeamento de formato</span><span class="sxs-lookup"><span data-stu-id="94d02-233">Review the format mapping</span></span>

1. <span data-ttu-id="94d02-234">Vá para **Administração da organização** \> **Relatório eletrônico** \> **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="94d02-234">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="94d02-235">Selecione **Modelo de pagamento** \> **Transferência de crédito ISO20022**.</span><span class="sxs-lookup"><span data-stu-id="94d02-235">Select **Payment model** \> **ISO20022 Credit transfer**.</span></span>
3. <span data-ttu-id="94d02-236">Selecione **Designer**.</span><span class="sxs-lookup"><span data-stu-id="94d02-236">Select **Designer**.</span></span>
4. <span data-ttu-id="94d02-237">Na guia **Mapeamento**, revise o mapeamento de formato exibido.</span><span class="sxs-lookup"><span data-stu-id="94d02-237">On the **Mapping** tab, review the format mapping that is opened.</span></span>

    <span data-ttu-id="94d02-238">Observe que o elemento **Documento** \> **CstmrCdtTrfInitn** \> **PmtInf** do arquivo **ISO20022CTReports** \> **XMLHeader** está associado à fonte de dados **\$PaymentByDebtor** configurada para agrupar registros do campo **Pagamentos** do modelo de dados.</span><span class="sxs-lookup"><span data-stu-id="94d02-238">Notice that the **Document** \> **CstmrCdtTrfInitn** \> **PmtInf** element of the **ISO20022CTReports** \> **XMLHeader** file is bound to the **\$PaymentByDebtor** data source that is configured to group records of the data model's **Payments** field.</span></span>

    ![Elemento PmtInf na página Designer de formato](./media/er-data-debugger-format-mapping.png)

#### <a name="review-the-format"></a><span data-ttu-id="94d02-240">Revisar o formato</span><span class="sxs-lookup"><span data-stu-id="94d02-240">Review the format</span></span>

1. <span data-ttu-id="94d02-241">Vá para **Administração da organização** \> **Relatório eletrônico** \> **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="94d02-241">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="94d02-242">Selecione **Modelo de pagamento** \> **Transferência de crédito ISO20022**.</span><span class="sxs-lookup"><span data-stu-id="94d02-242">Select **Payment model** \> **ISO20022 Credit transfer**.</span></span>
3. <span data-ttu-id="94d02-243">Selecione **Designer** e revise o formato de modelos aberto.</span><span class="sxs-lookup"><span data-stu-id="94d02-243">Select **Designer**, and then review the format that is opened.</span></span>

    <span data-ttu-id="94d02-244">Observe que o elemento do formato em **Documento** \> **CstmrCdtTrfInitn** \> **PmtInf** \> **CdtTrfTxInf** \> **CdtrAcct** \> **Id** \> **IBAN** \> **BankIBAN** está configurado para inserir o código IBAN da conta do fornecedor no arquivo de pagamento.</span><span class="sxs-lookup"><span data-stu-id="94d02-244">Notice that the format element under **Document** \> **CstmrCdtTrfInitn** \> **PmtInf** \> **CdtTrfTxInf** \> **CdtrAcct** \> **Id** \> **IBAN** \> **BankIBAN** is configured to enter the IBAN code of the vendor account in the payment file.</span></span>

    ![Elemento BankIBAN na página Designer de formato](./media/er-data-debugger-format.png)

## <a name="appendix-2-configure-accounts-payable"></a><a name="appendix2"></a><span data-ttu-id="94d02-246">Apêndice 2: Configurar Contas a pagar</span><span class="sxs-lookup"><span data-stu-id="94d02-246">Appendix 2: Configure Accounts payable</span></span>

### <a name="modify-a-vendor-property"></a><span data-ttu-id="94d02-247">Modificar uma propriedade do fornecedor</span><span class="sxs-lookup"><span data-stu-id="94d02-247">Modify a vendor property</span></span>

1. <span data-ttu-id="94d02-248">Acesse **Contas a pagar** \> **Fornecedores** \> **Todos os fornecedores**.</span><span class="sxs-lookup"><span data-stu-id="94d02-248">Go to **Accounts payable** \> **Vendors** \> **All vendors**.</span></span>
2. <span data-ttu-id="94d02-249">Selecione um fornecedor **DE-01002** e, no Painel de Ações, na guia **Fornecedor**, no grupo **Configurar**, selecione **Contas bancárias**.</span><span class="sxs-lookup"><span data-stu-id="94d02-249">Select vendor **DE-01002**, and then, on the Action Pane, on the **Vendor** tab, in the **Set up** group, select **Bank accounts**.</span></span>
3. <span data-ttu-id="94d02-250">Na FastTab **Identificação**, no campo **IBAN**, <a name="enteredIBANcode"></a>insira **GB33 BUKB 2020 1555 5555 55**.</span><span class="sxs-lookup"><span data-stu-id="94d02-250">On the **Identification** FastTab, in the **IBAN** field, <a name="enteredIBANcode"></a>enter **GB33 BUKB 2020 1555 5555 55**.</span></span>
4. <span data-ttu-id="94d02-251">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="94d02-251">Select **Save**.</span></span>

![Campo IBAN definido na página de Contas bancárias do fornecedor](./media/er-data-debugger-iban.png)

### <a name="set-up-a-method-of-payment"></a><span data-ttu-id="94d02-253">Configurar um meio de pagamento</span><span class="sxs-lookup"><span data-stu-id="94d02-253">Set up a method of payment</span></span>

1. <span data-ttu-id="94d02-254">Vá para **Contas a pagar** \> **Configuração de pagamento** \> **Métodos de pagamento**.</span><span class="sxs-lookup"><span data-stu-id="94d02-254">Go to **Accounts payable** \> **Payment setup** \> **Methods of payment**.</span></span>
2. <span data-ttu-id="94d02-255">Selecione o método de pagamento **SEPA CT**.</span><span class="sxs-lookup"><span data-stu-id="94d02-255">Select the **SEPA CT** payment method.</span></span>
3. <span data-ttu-id="94d02-256">Na FastTab **Formatos de arquivo**, na seção **Formatos de arquivo**, defina a opção **Formato de exportação eletrônico genérico** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="94d02-256">On the **File formats** FastTab, in the **File formats** section, set the **Generic electronic Export format** option to **Yes**.</span></span>
4. <span data-ttu-id="94d02-257">No campo **Exportar configuração de formato**, selecione o formato de ER **Transferência de crédito ISO20022**.</span><span class="sxs-lookup"><span data-stu-id="94d02-257">In the **Export format configuration** field, select the **ISO20022 Credit transfer** ER format.</span></span>
5. <span data-ttu-id="94d02-258">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="94d02-258">Select **Save**.</span></span>

![Configurações de formato de arquivo na página Métodos de pagamento](./media/er-data-debugger-payment-method.png)

### <a name="add-a-vendor-payment"></a><span data-ttu-id="94d02-260">Adicionar um pagamento de fornecedor</span><span class="sxs-lookup"><span data-stu-id="94d02-260">Add a vendor payment</span></span>

1. <span data-ttu-id="94d02-261">Vá para **Contas a pagar** \> **Pagamentos** \> **Diário de pagamentos do fornecedor**.</span><span class="sxs-lookup"><span data-stu-id="94d02-261">Go to **Accounts payable** \> **Payments** \> **Vendor payment journal**.</span></span>
2. <span data-ttu-id="94d02-262">Adicione um novo diário de pagamento.</span><span class="sxs-lookup"><span data-stu-id="94d02-262">Add a new payment journal.</span></span>
3. <span data-ttu-id="94d02-263">Selecione **Linhas** e adicione uma nova linha de pagamento.</span><span class="sxs-lookup"><span data-stu-id="94d02-263">Select **Lines**, and add a new payment line.</span></span>
4. <span data-ttu-id="94d02-264">No campo **Conta**, selecione o fornecedor **DE-01002**.</span><span class="sxs-lookup"><span data-stu-id="94d02-264">In the **Account** field, select vendor **DE-01002**.</span></span>
5. <span data-ttu-id="94d02-265">No campo **Débito**, insira um valor.</span><span class="sxs-lookup"><span data-stu-id="94d02-265">In the **Debit** field, enter a value.</span></span>
6. <span data-ttu-id="94d02-266">No campo **Método de pagamento**, selecione **SEPA CT**.</span><span class="sxs-lookup"><span data-stu-id="94d02-266">In the **Method of payment** field, select **SEPA CT**.</span></span>
7. <span data-ttu-id="94d02-267">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="94d02-267">Select **Save**.</span></span>

![Pagamento do fornecedor adicionado à página Pagamentos do fornecedor](./media/er-data-debugger-payment-journal.png)

## <a name="appendix-3-process-a-vendor-payment"></a><a name="appendix3"></a><span data-ttu-id="94d02-269">Apêndice 3: Processar pagamento do fornecedor</span><span class="sxs-lookup"><span data-stu-id="94d02-269">Appendix 3: Process a vendor payment</span></span>

1. <span data-ttu-id="94d02-270">Vá para **Contas a pagar** \> **Pagamentos** \> **Diário de pagamentos do fornecedor**.</span><span class="sxs-lookup"><span data-stu-id="94d02-270">Go to **Accounts payable** \> **Payments** \> **Vendor payment journal**.</span></span>
2. <span data-ttu-id="94d02-271">Na página **Diário de pagamentos do fornecedor**, selecione o diário de pagamento criado anteriormente e, em seguida, selecione **Linhas**.</span><span class="sxs-lookup"><span data-stu-id="94d02-271">On the **Vendor payment journal** page, select the payment journal that you previously created, and then select **Lines**.</span></span>
3. <span data-ttu-id="94d02-272">Selecione a linha de pagamento e, depois, **Status do pagamento** \> **Não**.</span><span class="sxs-lookup"><span data-stu-id="94d02-272">Select the payment line, and then select **Payment status** \> **None**.</span></span>
4. <span data-ttu-id="94d02-273">Selecione **Gerar pagamentos**.</span><span class="sxs-lookup"><span data-stu-id="94d02-273">Select **Generate payments**.</span></span>
5. <span data-ttu-id="94d02-274">No campo **Método de pagamento**, selecione **SEPA CT**.</span><span class="sxs-lookup"><span data-stu-id="94d02-274">In the **Method of payment** field, select **SEPA CT**.</span></span>
6. <span data-ttu-id="94d02-275">No campo **Conta bancária**, selecione **DEMF OPER**.</span><span class="sxs-lookup"><span data-stu-id="94d02-275">In the **Bank account** field, select **DEMF OPER**.</span></span>
7. <span data-ttu-id="94d02-276">Na caixa de diálogo **Gerar pagamentos**, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="94d02-276">In the **Generate payments** dialog box, select **OK**.</span></span>
8. <span data-ttu-id="94d02-277">Na caixa de diálogo **Parâmetros de relatório eletrônico**, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="94d02-277">In the **Electronic report parameters** dialog box, select **OK**.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]