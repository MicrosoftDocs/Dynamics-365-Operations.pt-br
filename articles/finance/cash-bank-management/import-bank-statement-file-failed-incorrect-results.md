---
title: Solução de problemas de importação do arquivo de extrato bancário
description: É importante que o arquivo de extrato bancário do banco corresponda ao layout ao qual o Microsoft Dynamics 365 Finance oferece suporte. Devido a padrões restritos de extratos bancários, a maioria das integrações funcionarão corretamente. No entanto, algumas vezes, o arquivo de extrato bancário não é importado ou apresenta resultados incorretos. Normalmente, esses problemas são causados por pequenas diferenças no arquivo de extrato bancário. Este artigo explica como corrigir essas diferenças e resolver os problemas.
author: ShylaThompson
manager: AnnBe
ms.date: 01/11/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankStatementFormat
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 141273
ms.assetid: 3ee2f32b-02aa-420b-8990-e6aa5fc6bda3
ms.search.region: global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a5e7e6897f19dc0303ffbd3111f93669a91daa1b
ms.sourcegitcommit: 4f668b23f5bfc6d6502858850d2ed59d7a79cfbb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2020
ms.locfileid: "3059367"
---
# <a name="bank-statement-file-import-troubleshooting"></a><span data-ttu-id="a4443-107">Solução de problemas de importação do arquivo de extrato bancário</span><span class="sxs-lookup"><span data-stu-id="a4443-107">Bank statement file import troubleshooting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a4443-108">É importante que o arquivo de extrato bancário do banco corresponda ao layout ao qual o Microsoft Dynamics 365 Finance oferece suporte.</span><span class="sxs-lookup"><span data-stu-id="a4443-108">It's important that the bank statement file from the bank match the layout that Microsoft Dynamics 365 Finance supports.</span></span> <span data-ttu-id="a4443-109">Devido a padrões restritos de extratos bancários, a maioria das integrações funcionarão corretamente.</span><span class="sxs-lookup"><span data-stu-id="a4443-109">Because of strict standards for bank statements, most integrations will work correctly.</span></span> <span data-ttu-id="a4443-110">No entanto, algumas vezes, o arquivo de extrato bancário não é importado ou apresenta resultados incorretos.</span><span class="sxs-lookup"><span data-stu-id="a4443-110">However, sometimes the statement file can't be imported or has incorrect results.</span></span> <span data-ttu-id="a4443-111">Normalmente, esses problemas são causados por pequenas diferenças no arquivo de extrato bancário.</span><span class="sxs-lookup"><span data-stu-id="a4443-111">Typically, these issues are caused by small differences in the bank statement file.</span></span> <span data-ttu-id="a4443-112">Este artigo explica como corrigir essas diferenças e resolver os problemas.</span><span class="sxs-lookup"><span data-stu-id="a4443-112">This article explains how to fix these differences and resolve the issues.</span></span>

<a name="what-is-the-error"></a><span data-ttu-id="a4443-113">Qual é o erro?</span><span class="sxs-lookup"><span data-stu-id="a4443-113">What is the error?</span></span>
------------------

<span data-ttu-id="a4443-114">Após tentar importar um arquivo de extrato bancário, acesse o histórico de trabalho de gerenciamento de dados e os detalhes da execução para localizar o erro.</span><span class="sxs-lookup"><span data-stu-id="a4443-114">After you try to import a bank statement file, go to the Data management job history and its execution details to find the error.</span></span> <span data-ttu-id="a4443-115">O erro pode ajudar indicando o extrato, o saldo ou a linha do extrato.</span><span class="sxs-lookup"><span data-stu-id="a4443-115">The error can help by pointing to the statement, balance, or statement line.</span></span> <span data-ttu-id="a4443-116">Entretanto, é improvável que você receba informações suficientes para identificar o campo ou o elemento que está causando o problema.</span><span class="sxs-lookup"><span data-stu-id="a4443-116">However, it's unlikely to provide enough information to help you identify the field or element that is causing the issue.</span></span>

## <a name="what-are-the-differences"></a><span data-ttu-id="a4443-117">Quais são as diferenças?</span><span class="sxs-lookup"><span data-stu-id="a4443-117">What are the differences?</span></span>
<span data-ttu-id="a4443-118">Compare a definição de layout do arquivo bancário com a definição de importação do Finance e observe todas as diferenças nos campos e nos elementos.</span><span class="sxs-lookup"><span data-stu-id="a4443-118">Compare the bank file layout definition to the Finance import definition, and note any differences in the fields and elements.</span></span> <span data-ttu-id="a4443-119">Compare o arquivo de extrato bancário com o arquivo de exemplo relacionado do Finance.</span><span class="sxs-lookup"><span data-stu-id="a4443-119">Compare the bank statement file to the related sample Finance file.</span></span> <span data-ttu-id="a4443-120">Nos arquivos ISO20022, todas as diferenças devem ser fáceis de ver.</span><span class="sxs-lookup"><span data-stu-id="a4443-120">In the ISO20022 files, any differences should be easy to see.</span></span>

## <a name="time-zone-differences-on-imported-bank-statements"></a><span data-ttu-id="a4443-121">Diferenças de fuso horário em extratos bancários importados</span><span class="sxs-lookup"><span data-stu-id="a4443-121">Time zone differences on imported bank statements</span></span>
<span data-ttu-id="a4443-122">Os valores de data/hora no arquivo de importação podem diferir dos valores de data/hora exibidos no Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="a4443-122">The date-time values in the import file can differ from the date-time values that are shown in Finance and Operations.</span></span> <span data-ttu-id="a4443-123">Para evitar essa discrepância, insira uma preferência de fuso horário na página **Configurar fontes de dados**.</span><span class="sxs-lookup"><span data-stu-id="a4443-123">To prevent this discrepancy, enter a time zone preference on the **Configure data sources** page.</span></span> <span data-ttu-id="a4443-124">Consulte [Configurar o processo de importação de reconciliação bancária avançada​](set-up-advanced-bank-reconciliation-import-process.md) para obter mais informações sobre como inserir uma preferência de fuso horário.</span><span class="sxs-lookup"><span data-stu-id="a4443-124">See [Set up the advanced bank reconciliation import process](set-up-advanced-bank-reconciliation-import-process.md) for more information about entering a time zone preference.</span></span>

## <a name="transformations"></a><span data-ttu-id="a4443-125">Transformações</span><span class="sxs-lookup"><span data-stu-id="a4443-125">Transformations</span></span>
<span data-ttu-id="a4443-126">Normalmente, a alteração deve ser feita em uma das três transformações.</span><span class="sxs-lookup"><span data-stu-id="a4443-126">Typically, the change must be made in one of three transformations.</span></span> <span data-ttu-id="a4443-127">Cada transformação é gravada em um padrão específico.</span><span class="sxs-lookup"><span data-stu-id="a4443-127">Each transformation is written for a specific standard.</span></span>

| <span data-ttu-id="a4443-128">Nome do recurso</span><span class="sxs-lookup"><span data-stu-id="a4443-128">Resource name</span></span>                                         | <span data-ttu-id="a4443-129">Nome do arquivo</span><span class="sxs-lookup"><span data-stu-id="a4443-129">File name</span></span>                          |
|-------------------------------------------------------|------------------------------------|
| <span data-ttu-id="a4443-130">BankStmtImport\_BAI2CSV\_to\_BAI2XML\_xslt</span><span class="sxs-lookup"><span data-stu-id="a4443-130">BankStmtImport\_BAI2CSV\_to\_BAI2XML\_xslt</span></span>            | <span data-ttu-id="a4443-131">BAI2CSV-to-BAI2XML.xslt</span><span class="sxs-lookup"><span data-stu-id="a4443-131">BAI2CSV-to-BAI2XML.xslt</span></span>            |
| <span data-ttu-id="a4443-132">BankStmtImport\_ISO20022XML\_to\_Reconciliation\_xslt</span><span class="sxs-lookup"><span data-stu-id="a4443-132">BankStmtImport\_ISO20022XML\_to\_Reconciliation\_xslt</span></span> | <span data-ttu-id="a4443-133">ISO20022XML-to-Reconciliation.xslt</span><span class="sxs-lookup"><span data-stu-id="a4443-133">ISO20022XML-to-Reconciliation.xslt</span></span> |
| <span data-ttu-id="a4443-134">BankStmtImport\_MT940TXT\_to\_MT940XML\_xslt</span><span class="sxs-lookup"><span data-stu-id="a4443-134">BankStmtImport\_MT940TXT\_to\_MT940XML\_xslt</span></span>          | <span data-ttu-id="a4443-135">MT940TXT-to-MT940XML.xslt</span><span class="sxs-lookup"><span data-stu-id="a4443-135">MT940TXT-to-MT940XML.xslt</span></span>          |

## <a name="debugging-transformations"></a><span data-ttu-id="a4443-136">Depurando transformações</span><span class="sxs-lookup"><span data-stu-id="a4443-136">Debugging transformations</span></span>
### <a name="adjust-the-bai2-and-mt940-files"></a><span data-ttu-id="a4443-137">Ajustar os arquivos BAI2 e MT940</span><span class="sxs-lookup"><span data-stu-id="a4443-137">Adjust the BAI2 and MT940 files</span></span>

<span data-ttu-id="a4443-138">Os arquivos BAI2 e MT940 são baseados em texto e requerem um ajuste para habilitar a depuração das transformações XSLT.</span><span class="sxs-lookup"><span data-stu-id="a4443-138">The BAI2 and MT940 files are text-based files and require an adjustment to enable Extensible Stylesheet Language Transformations (XSLT) debugging.</span></span> <span data-ttu-id="a4443-139">O programa faz esse ajuste quando um arquivo é importado.</span><span class="sxs-lookup"><span data-stu-id="a4443-139">The program makes this adjustment when a file is imported.</span></span>

1.  <span data-ttu-id="a4443-140">Crie um arquivo XML e copie o texto a seguir nele.</span><span class="sxs-lookup"><span data-stu-id="a4443-140">Create an XML file, and copy the following text into it.</span></span>

    ```xml
    <Batch><![CDATA[PASTESTATEMENTFILEHERE
        ]]></Batch>
    ```
    
2.  <span data-ttu-id="a4443-141">Copie o conteúdo do arquivo de extrato bancário e cole-o no arquivo XML para que ele substitua **PASTESTATEMENTFILEHERE**.</span><span class="sxs-lookup"><span data-stu-id="a4443-141">Copy the contents of the bank statement file, and paste them into the XML file so that they replace **PASTESTATEMENTFILEHERE**.</span></span>

### <a name="debug-the-xslt"></a><span data-ttu-id="a4443-142">Depurar a XSLT</span><span class="sxs-lookup"><span data-stu-id="a4443-142">Debug the XSLT</span></span>

<span data-ttu-id="a4443-143">Para obter mais informações, consulte <https://msdn.microsoft.com/library/ms255605.aspx>.</span><span class="sxs-lookup"><span data-stu-id="a4443-143">For more information, see <https://msdn.microsoft.com/library/ms255605.aspx>.</span></span>

1.  <span data-ttu-id="a4443-144">Iniciar o Microsoft Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="a4443-144">Start Microsoft Visual Studio.</span></span>
2.  <span data-ttu-id="a4443-145">Crie um aplicativo de console.</span><span class="sxs-lookup"><span data-stu-id="a4443-145">Create a console application.</span></span>
3.  <span data-ttu-id="a4443-146">Abra a XSLT apropriada.</span><span class="sxs-lookup"><span data-stu-id="a4443-146">Open the appropriate XSLT.</span></span>
4.  <span data-ttu-id="a4443-147">Clique na XLST e na respectiva página de propriedades.</span><span class="sxs-lookup"><span data-stu-id="a4443-147">Click the XLST and its properties page.</span></span>
5.  <span data-ttu-id="a4443-148">Defina a entrada para o local do arquivo de extrato bancário.</span><span class="sxs-lookup"><span data-stu-id="a4443-148">Set the input to the location of the bank statement file.</span></span>
6.  <span data-ttu-id="a4443-149">Defina um local e um nome de arquivo como saída.</span><span class="sxs-lookup"><span data-stu-id="a4443-149">Define a location and file name for the output.</span></span>
7.  <span data-ttu-id="a4443-150">Definia os pontos de quebra necessários.</span><span class="sxs-lookup"><span data-stu-id="a4443-150">Set the required break points.</span></span>
8.  <span data-ttu-id="a4443-151">No menu, clique em **XML** &gt; **Iniciar Depuração XSLT**.</span><span class="sxs-lookup"><span data-stu-id="a4443-151">On the menu, click **XML** &gt; **Start XSLT Debugging**.</span></span>

### <a name="format-the-xslt-output"></a><span data-ttu-id="a4443-152">Formatar a saída XSLT</span><span class="sxs-lookup"><span data-stu-id="a4443-152">Format the XSLT output</span></span>

<span data-ttu-id="a4443-153">Quando a transformação é executada, ela cria um arquivo de saída que você pode exibir no Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="a4443-153">When the transformation runs, it creates an output file that you can view in Visual Studio.</span></span> <span data-ttu-id="a4443-154">Use Ctrl+A, Ctrl+K e Ctrl+D para formatar rapidamente o arquivo de saída.</span><span class="sxs-lookup"><span data-stu-id="a4443-154">Use Ctrl+A, Ctrl+K, and Ctrl+D to quickly format the output file.</span></span>

### <a name="adjust-the-transformation"></a><span data-ttu-id="a4443-155">Ajustar a transformação</span><span class="sxs-lookup"><span data-stu-id="a4443-155">Adjust the transformation</span></span>

<span data-ttu-id="a4443-156">Ajuste a transformação para obter o campo ou elemento apropriado no arquivo de extrato bancário.</span><span class="sxs-lookup"><span data-stu-id="a4443-156">Adjust the transformation to get the appropriate field or element in the bank statement file.</span></span> <span data-ttu-id="a4443-157">Em seguida, mapeie esse campo ou elemento para o elemento apropriado do Finance.</span><span class="sxs-lookup"><span data-stu-id="a4443-157">Then map that field or element to the appropriate Finance element.</span></span>

### <a name="debitcredit-indicator"></a><span data-ttu-id="a4443-158">Indicador de débito/crédito</span><span class="sxs-lookup"><span data-stu-id="a4443-158">Debit/credit indicator</span></span>

<span data-ttu-id="a4443-159">Às vezes, os débitos são importados como créditos, e os créditos são importados como débitos.</span><span class="sxs-lookup"><span data-stu-id="a4443-159">Sometimes, debits might be imported as credits, and credits might be imported as debits.</span></span> <span data-ttu-id="a4443-160">Para resolver esse problema, você deve alterar a XSLT apropriada.</span><span class="sxs-lookup"><span data-stu-id="a4443-160">To resolve this issue, you must change the appropriate XSLT.</span></span> <span data-ttu-id="a4443-161">Se os extratos bancários forem provenientes de vários bancos, verifique se todos usam a mesma abordagem de débito/crédito, ou crie transformações separadas.</span><span class="sxs-lookup"><span data-stu-id="a4443-161">If bank statements come from multiple banks, make sure that they all use the same debit/credit approach, or create separate transformations.</span></span>

-   <span data-ttu-id="a4443-162">Modelo BAI2XML-to-Reconciliation.xlst GetAmountCreditDebitIndicator</span><span class="sxs-lookup"><span data-stu-id="a4443-162">BAI2XML-to-Reconciliation.xlst GetAmountCreditDebitIndicator template</span></span>
-   <span data-ttu-id="a4443-163">Modelo ISO20022XML-to-Reconcilation.xslt GetCreditDebit</span><span class="sxs-lookup"><span data-stu-id="a4443-163">ISO20022XML-to-Reconcilation.xslt GetCreditDebit template</span></span>
-   <span data-ttu-id="a4443-164">Modelo MT940XML-to-Reconcilation.xslt GetCreditDebitIndicator</span><span class="sxs-lookup"><span data-stu-id="a4443-164">MT940XML-to-Reconcilation.xslt GetCreditDebitIndicator template</span></span>

## <a name="examples-of-bank-statement-formats-and-technical-layouts"></a><span data-ttu-id="a4443-165">Exemplos de formatos de extrato bancário e layouts técnicos</span><span class="sxs-lookup"><span data-stu-id="a4443-165">Examples of bank statement formats and technical layouts</span></span>
<span data-ttu-id="a4443-166">A tabela a seguir lista exemplos das definições de layout técnico de arquivos de importação avançada de reconciliação bancária e de três arquivos de exemplo de extrato bancário relacionados.</span><span class="sxs-lookup"><span data-stu-id="a4443-166">The following table lists examples of the technical layout definitions for advanced bank reconciliation import files and three related bank statement example files.</span></span> <span data-ttu-id="a4443-167">Você pode baixar arquivos de exemplo e layouts técnicos aqui: https://mbs.microsoft.com/customersource/northamerica/AX/learning/documentation/how-to-articles/exofbankstfotechlayouts</span><span class="sxs-lookup"><span data-stu-id="a4443-167">You can download the example files and technical layouts here: https://mbs.microsoft.com/customersource/northamerica/AX/learning/documentation/how-to-articles/exofbankstfotechlayouts</span></span>  


| <span data-ttu-id="a4443-168">Definição do layout técnico</span><span class="sxs-lookup"><span data-stu-id="a4443-168">Technical layout definition</span></span>                             | <span data-ttu-id="a4443-169">Arquivo de exemplo de extrato bancário</span><span class="sxs-lookup"><span data-stu-id="a4443-169">Bank statement example file</span></span>          |
|---------------------------------------------------------|--------------------------------------|
| <span data-ttu-id="a4443-170">DynamicsAXMT940Layout</span><span class="sxs-lookup"><span data-stu-id="a4443-170">DynamicsAXMT940Layout</span></span>                                   | <span data-ttu-id="a4443-171">MT940StatementExample</span><span class="sxs-lookup"><span data-stu-id="a4443-171">MT940StatementExample</span></span>                |
| <span data-ttu-id="a4443-172">DynamicsAXISO20022Layout</span><span class="sxs-lookup"><span data-stu-id="a4443-172">DynamicsAXISO20022Layout</span></span>                                | <span data-ttu-id="a4443-173">ISO20022StatementExample</span><span class="sxs-lookup"><span data-stu-id="a4443-173">ISO20022StatementExample</span></span>             |
| <span data-ttu-id="a4443-174">DynamicsAXBAI2Layout</span><span class="sxs-lookup"><span data-stu-id="a4443-174">DynamicsAXBAI2Layout</span></span>                                    | <span data-ttu-id="a4443-175">BAI2StatementExample</span><span class="sxs-lookup"><span data-stu-id="a4443-175">BAI2StatementExample</span></span>                 |





