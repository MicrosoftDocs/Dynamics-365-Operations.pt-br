---
title: Solução de problemas de importação do arquivo de extrato bancário
description: É importante que o arquivo de extrato bancário do banco corresponda ao layout ao qual o Microsoft Dynamics 365 Finance oferece suporte. Devido a padrões restritos de extratos bancários, a maioria das integrações funcionarão corretamente. No entanto, algumas vezes, o arquivo de extrato bancário não é importado ou apresenta resultados incorretos. Normalmente, esses problemas são causados por pequenas diferenças no arquivo de extrato bancário. Este artigo explica como corrigir essas diferenças e resolver os problemas.
author: panolte
ms.date: 03/29/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BankStatementFormat
audience: Application User
ms.reviewer: roschlom
ms.custom: 141273
ms.assetid: 3ee2f32b-02aa-420b-8990-e6aa5fc6bda3
ms.search.region: global
ms.author: panolte
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 14f0e480b93e663f81db5a1edb2ae71b559bb05e
ms.sourcegitcommit: ff09736563d3cd2bc74c7664edd1767b218401cb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2021
ms.locfileid: "6188550"
---
# <a name="bank-statement-file-import-troubleshooting"></a><span data-ttu-id="a042b-107">Solução de problemas de importação do arquivo de extrato bancário</span><span class="sxs-lookup"><span data-stu-id="a042b-107">Bank statement file import troubleshooting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a042b-108">É importante que o arquivo de extrato bancário do banco corresponda ao layout ao qual o Microsoft Dynamics 365 Finance oferece suporte.</span><span class="sxs-lookup"><span data-stu-id="a042b-108">It's important that the bank statement file from the bank matches the layout that Microsoft Dynamics 365 Finance supports.</span></span> <span data-ttu-id="a042b-109">Devido a padrões restritos de extratos bancários, a maioria das integrações funcionarão corretamente.</span><span class="sxs-lookup"><span data-stu-id="a042b-109">Because of strict standards for bank statements, most integrations will work correctly.</span></span> <span data-ttu-id="a042b-110">No entanto, algumas vezes, o arquivo de extrato bancário não é importado ou apresenta resultados incorretos.</span><span class="sxs-lookup"><span data-stu-id="a042b-110">However, sometimes the statement file can't be imported or has incorrect results.</span></span> <span data-ttu-id="a042b-111">Normalmente, esses problemas são causados por pequenas diferenças no arquivo de extrato bancário.</span><span class="sxs-lookup"><span data-stu-id="a042b-111">Typically, these issues are caused by small differences in the bank statement file.</span></span> <span data-ttu-id="a042b-112">Este artigo explica como corrigir essas diferenças e resolver os problemas.</span><span class="sxs-lookup"><span data-stu-id="a042b-112">This article explains how to fix these differences and resolve the issues.</span></span>

## <a name="what-is-the-error"></a><span data-ttu-id="a042b-113">Qual é o erro?</span><span class="sxs-lookup"><span data-stu-id="a042b-113">What is the error?</span></span>

<span data-ttu-id="a042b-114">Após tentar importar um arquivo de extrato bancário, acesse o histórico de trabalho de gerenciamento de dados e os detalhes da execução para localizar o erro.</span><span class="sxs-lookup"><span data-stu-id="a042b-114">After you try to import a bank statement file, go to the Data management job history and its execution details to find the error.</span></span> <span data-ttu-id="a042b-115">O erro pode ajudar indicando o extrato, o saldo ou a linha do extrato.</span><span class="sxs-lookup"><span data-stu-id="a042b-115">The error can help by pointing to the statement, balance, or statement line.</span></span> <span data-ttu-id="a042b-116">Entretanto, é improvável que você receba informações suficientes para identificar o campo ou o elemento que está causando o problema.</span><span class="sxs-lookup"><span data-stu-id="a042b-116">However, it's unlikely to provide enough information to help you identify the field or element that is causing the issue.</span></span>

> [!NOTE]
> <span data-ttu-id="a042b-117">Os extratos bancários importados só podem se sobrepor por momento específico.</span><span class="sxs-lookup"><span data-stu-id="a042b-117">Imported bank statements can overlap only for single a point in time.</span></span>  <span data-ttu-id="a042b-118">Por exemplo, se uma instrução termina à meia-noite de 1º de janeiro de 2021, a data de início da próxima instrução poderá ser à meia-noite de 1º de janeiro de 2021, meia-noite.</span><span class="sxs-lookup"><span data-stu-id="a042b-118">For example, if a statement ends at 12:00 AM on January 1, 2021, then beginning date for the next statement can be 12:00 AM on Jarnuary 1, 2021 12:00:00 AM.</span></span>

## <a name="what-are-the-differences"></a><span data-ttu-id="a042b-119">Quais são as diferenças?</span><span class="sxs-lookup"><span data-stu-id="a042b-119">What are the differences?</span></span>
<span data-ttu-id="a042b-120">Compare a definição de layout do arquivo bancário com a definição de importação do Finance e observe todas as diferenças nos campos e nos elementos.</span><span class="sxs-lookup"><span data-stu-id="a042b-120">Compare the bank file layout definition to the Finance import definition, and note any differences in the fields and elements.</span></span> <span data-ttu-id="a042b-121">Compare o arquivo de extrato bancário com o arquivo de exemplo relacionado do Finance.</span><span class="sxs-lookup"><span data-stu-id="a042b-121">Compare the bank statement file to the related sample Finance file.</span></span> <span data-ttu-id="a042b-122">Nos arquivos ISO20022, todas as diferenças devem ser fáceis de ver.</span><span class="sxs-lookup"><span data-stu-id="a042b-122">In the ISO20022 files, any differences should be easy to see.</span></span>

## <a name="time-zone-differences-on-imported-bank-statements"></a><span data-ttu-id="a042b-123">Diferenças de fuso horário em extratos bancários importados</span><span class="sxs-lookup"><span data-stu-id="a042b-123">Time zone differences on imported bank statements</span></span>
<span data-ttu-id="a042b-124">Os valores de data/hora no arquivo de importação podem diferir dos valores de data/hora exibidos no Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="a042b-124">The date-time values in the import file can differ from the date-time values that are shown in Finance and Operations.</span></span> <span data-ttu-id="a042b-125">Para evitar essa discrepância, insira uma preferência de fuso horário na página **Configurar fontes de dados**.</span><span class="sxs-lookup"><span data-stu-id="a042b-125">To prevent this discrepancy, enter a time zone preference on the **Configure data sources** page.</span></span> <span data-ttu-id="a042b-126">Para obter mais informações sobre como inserir uma preferência de fuso horário, consulte [Configurar o processo de importação de reconciliação bancária avançada](set-up-advanced-bank-reconciliation-import-process.md).</span><span class="sxs-lookup"><span data-stu-id="a042b-126">For more information about entering a time zone preference, see [Set up the advanced bank reconciliation import process](set-up-advanced-bank-reconciliation-import-process.md).</span></span>

## <a name="transformations"></a><span data-ttu-id="a042b-127">Transformações</span><span class="sxs-lookup"><span data-stu-id="a042b-127">Transformations</span></span>
<span data-ttu-id="a042b-128">Normalmente, a alteração deve ser feita em uma das três transformações.</span><span class="sxs-lookup"><span data-stu-id="a042b-128">Typically, the change must be made in one of three transformations.</span></span> <span data-ttu-id="a042b-129">Cada transformação é gravada em um padrão específico.</span><span class="sxs-lookup"><span data-stu-id="a042b-129">Each transformation is written for a specific standard.</span></span>

| <span data-ttu-id="a042b-130">Nome do recurso</span><span class="sxs-lookup"><span data-stu-id="a042b-130">Resource name</span></span>                                         | <span data-ttu-id="a042b-131">Nome do arquivo</span><span class="sxs-lookup"><span data-stu-id="a042b-131">File name</span></span>                          |
|-------------------------------------------------------|------------------------------------|
| <span data-ttu-id="a042b-132">BankStmtImport\_BAI2CSV\_to\_BAI2XML\_xslt</span><span class="sxs-lookup"><span data-stu-id="a042b-132">BankStmtImport\_BAI2CSV\_to\_BAI2XML\_xslt</span></span>            | <span data-ttu-id="a042b-133">BAI2CSV-to-BAI2XML.xslt</span><span class="sxs-lookup"><span data-stu-id="a042b-133">BAI2CSV-to-BAI2XML.xslt</span></span>            |
| <span data-ttu-id="a042b-134">BankStmtImport\_ISO20022XML\_to\_Reconciliation\_xslt</span><span class="sxs-lookup"><span data-stu-id="a042b-134">BankStmtImport\_ISO20022XML\_to\_Reconciliation\_xslt</span></span> | <span data-ttu-id="a042b-135">ISO20022XML-to-Reconciliation.xslt</span><span class="sxs-lookup"><span data-stu-id="a042b-135">ISO20022XML-to-Reconciliation.xslt</span></span> |
| <span data-ttu-id="a042b-136">BankStmtImport\_MT940TXT\_to\_MT940XML\_xslt</span><span class="sxs-lookup"><span data-stu-id="a042b-136">BankStmtImport\_MT940TXT\_to\_MT940XML\_xslt</span></span>          | <span data-ttu-id="a042b-137">MT940TXT-to-MT940XML.xslt</span><span class="sxs-lookup"><span data-stu-id="a042b-137">MT940TXT-to-MT940XML.xslt</span></span>          |

## <a name="debugging-transformations"></a><span data-ttu-id="a042b-138">Depurando transformações</span><span class="sxs-lookup"><span data-stu-id="a042b-138">Debugging transformations</span></span>
### <a name="adjust-the-bai2-and-mt940-files"></a><span data-ttu-id="a042b-139">Ajustar os arquivos BAI2 e MT940</span><span class="sxs-lookup"><span data-stu-id="a042b-139">Adjust the BAI2 and MT940 files</span></span>

<span data-ttu-id="a042b-140">Os arquivos BAI2 e MT940 são baseados em texto e requerem um ajuste para habilitar a depuração das transformações XSLT.</span><span class="sxs-lookup"><span data-stu-id="a042b-140">The BAI2 and MT940 files are text-based files and require an adjustment to enable Extensible Stylesheet Language Transformations (XSLT) debugging.</span></span> <span data-ttu-id="a042b-141">O programa faz esse ajuste quando um arquivo é importado.</span><span class="sxs-lookup"><span data-stu-id="a042b-141">The program makes this adjustment when a file is imported.</span></span>

1.  <span data-ttu-id="a042b-142">Crie um arquivo XML e copie o texto a seguir nele.</span><span class="sxs-lookup"><span data-stu-id="a042b-142">Create an XML file, and copy the following text into it.</span></span>

    ```xml
    <Batch><![CDATA[PASTESTATEMENTFILEHERE
        ]]></Batch>
    ```
    
2.  <span data-ttu-id="a042b-143">Copie o conteúdo do arquivo de extrato bancário e cole-o no arquivo XML para que ele substitua **PASTESTATEMENTFILEHERE**.</span><span class="sxs-lookup"><span data-stu-id="a042b-143">Copy the contents of the bank statement file, and paste them into the XML file so that they replace **PASTESTATEMENTFILEHERE**.</span></span>

### <a name="debug-the-xslt"></a><span data-ttu-id="a042b-144">Depurar a XSLT</span><span class="sxs-lookup"><span data-stu-id="a042b-144">Debug the XSLT</span></span>

<span data-ttu-id="a042b-145">Para obter mais informações, consulte <https://msdn.microsoft.com/library/ms255605.aspx>.</span><span class="sxs-lookup"><span data-stu-id="a042b-145">For more information, see <https://msdn.microsoft.com/library/ms255605.aspx>.</span></span>

1.  <span data-ttu-id="a042b-146">Iniciar o Microsoft Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="a042b-146">Start Microsoft Visual Studio.</span></span>
2.  <span data-ttu-id="a042b-147">Crie um aplicativo de console.</span><span class="sxs-lookup"><span data-stu-id="a042b-147">Create a console application.</span></span>
3.  <span data-ttu-id="a042b-148">Abra a XSLT apropriada.</span><span class="sxs-lookup"><span data-stu-id="a042b-148">Open the appropriate XSLT.</span></span>
4.  <span data-ttu-id="a042b-149">Clique na XLST e na respectiva página de propriedades.</span><span class="sxs-lookup"><span data-stu-id="a042b-149">Click the XLST and its properties page.</span></span>
5.  <span data-ttu-id="a042b-150">Defina a entrada para o local do arquivo de extrato bancário.</span><span class="sxs-lookup"><span data-stu-id="a042b-150">Set the input to the location of the bank statement file.</span></span>
6.  <span data-ttu-id="a042b-151">Defina um local e um nome de arquivo como saída.</span><span class="sxs-lookup"><span data-stu-id="a042b-151">Define a location and file name for the output.</span></span>
7.  <span data-ttu-id="a042b-152">Definia os pontos de quebra necessários.</span><span class="sxs-lookup"><span data-stu-id="a042b-152">Set the required break points.</span></span>
8.  <span data-ttu-id="a042b-153">No menu, clique em **XML** &gt; **Iniciar Depuração XSLT**.</span><span class="sxs-lookup"><span data-stu-id="a042b-153">On the menu, click **XML** &gt; **Start XSLT Debugging**.</span></span>

### <a name="format-the-xslt-output"></a><span data-ttu-id="a042b-154">Formatar a saída XSLT</span><span class="sxs-lookup"><span data-stu-id="a042b-154">Format the XSLT output</span></span>

<span data-ttu-id="a042b-155">Quando a transformação é executada, ela cria um arquivo de saída que você pode exibir no Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="a042b-155">When the transformation runs, it creates an output file that you can view in Visual Studio.</span></span> <span data-ttu-id="a042b-156">Use Ctrl+A, Ctrl+K e Ctrl+D para formatar rapidamente o arquivo de saída.</span><span class="sxs-lookup"><span data-stu-id="a042b-156">Use Ctrl+A, Ctrl+K, and Ctrl+D to quickly format the output file.</span></span>

### <a name="adjust-the-transformation"></a><span data-ttu-id="a042b-157">Ajustar a transformação</span><span class="sxs-lookup"><span data-stu-id="a042b-157">Adjust the transformation</span></span>

<span data-ttu-id="a042b-158">Ajuste a transformação para obter o campo ou elemento apropriado no arquivo de extrato bancário.</span><span class="sxs-lookup"><span data-stu-id="a042b-158">Adjust the transformation to get the appropriate field or element in the bank statement file.</span></span> <span data-ttu-id="a042b-159">Em seguida, mapeie esse campo ou elemento para o elemento apropriado do Finance.</span><span class="sxs-lookup"><span data-stu-id="a042b-159">Then map that field or element to the appropriate Finance element.</span></span>

### <a name="debitcredit-indicator"></a><span data-ttu-id="a042b-160">Indicador de débito/crédito</span><span class="sxs-lookup"><span data-stu-id="a042b-160">Debit/credit indicator</span></span>

<span data-ttu-id="a042b-161">Às vezes, os débitos são importados como créditos, e os créditos são importados como débitos.</span><span class="sxs-lookup"><span data-stu-id="a042b-161">Sometimes, debits might be imported as credits, and credits might be imported as debits.</span></span> <span data-ttu-id="a042b-162">Para resolver esse problema, você deve alterar a XSLT apropriada.</span><span class="sxs-lookup"><span data-stu-id="a042b-162">To resolve this issue, you must change the appropriate XSLT.</span></span> <span data-ttu-id="a042b-163">Se os extratos bancários forem provenientes de vários bancos, verifique se todos usam a mesma abordagem de débito/crédito, ou crie transformações separadas.</span><span class="sxs-lookup"><span data-stu-id="a042b-163">If bank statements come from multiple banks, make sure that they all use the same debit/credit approach, or create separate transformations.</span></span>

-   <span data-ttu-id="a042b-164">Modelo BAI2XML-to-Reconciliation.xlst GetAmountCreditDebitIndicator</span><span class="sxs-lookup"><span data-stu-id="a042b-164">BAI2XML-to-Reconciliation.xlst GetAmountCreditDebitIndicator template</span></span>
-   <span data-ttu-id="a042b-165">Modelo ISO20022XML-to-Reconcilation.xslt GetCreditDebit</span><span class="sxs-lookup"><span data-stu-id="a042b-165">ISO20022XML-to-Reconcilation.xslt GetCreditDebit template</span></span>
-   <span data-ttu-id="a042b-166">Modelo MT940XML-to-Reconcilation.xslt GetCreditDebitIndicator</span><span class="sxs-lookup"><span data-stu-id="a042b-166">MT940XML-to-Reconcilation.xslt GetCreditDebitIndicator template</span></span>

## <a name="examples-of-bank-statement-formats-and-technical-layouts"></a><span data-ttu-id="a042b-167">Exemplos de formatos de extrato bancário e layouts técnicos</span><span class="sxs-lookup"><span data-stu-id="a042b-167">Examples of bank statement formats and technical layouts</span></span>
<span data-ttu-id="a042b-168">A tabela a seguir lista exemplos das definições de layout técnico de arquivos de importação avançada de reconciliação bancária e de três arquivos de exemplo de extrato bancário relacionados.</span><span class="sxs-lookup"><span data-stu-id="a042b-168">The following table lists examples of the technical layout definitions for advanced bank reconciliation import files and three related bank statement example files.</span></span> <span data-ttu-id="a042b-169">Você pode baixar arquivos de exemplo e layouts técnicos aqui: [Importar exemplos de arquivos](//download.microsoft.com/download/8/e/c/8ec8d2d0-eb8c-41fb-ad8c-f01a4d670a44/Dynamics365FinanceAdvancedBankStatementLayouts.xlsx)</span><span class="sxs-lookup"><span data-stu-id="a042b-169">You can download the example files and technical layouts here: [Import file examples](//download.microsoft.com/download/8/e/c/8ec8d2d0-eb8c-41fb-ad8c-f01a4d670a44/Dynamics365FinanceAdvancedBankStatementLayouts.xlsx)</span></span>  

| <span data-ttu-id="a042b-170">Definição do layout técnico</span><span class="sxs-lookup"><span data-stu-id="a042b-170">Technical layout definition</span></span>                             | <span data-ttu-id="a042b-171">Arquivo de exemplo de extrato bancário</span><span class="sxs-lookup"><span data-stu-id="a042b-171">Bank statement example file</span></span>          |
|---------------------------------------------------------|--------------------------------------|
| <span data-ttu-id="a042b-172">DynamicsAXMT940Layout</span><span class="sxs-lookup"><span data-stu-id="a042b-172">DynamicsAXMT940Layout</span></span>                                   | [<span data-ttu-id="a042b-173">MT940StatementExample</span><span class="sxs-lookup"><span data-stu-id="a042b-173">MT940StatementExample</span></span>](//download.microsoft.com/download/2/d/c/2dcc4e55-ddc8-4a74-b79c-250fae201c3c/mt940StatementExample.txt)                |
| <span data-ttu-id="a042b-174">DynamicsAXISO20022Layout</span><span class="sxs-lookup"><span data-stu-id="a042b-174">DynamicsAXISO20022Layout</span></span>                                | [<span data-ttu-id="a042b-175">ISO20022StatementExample</span><span class="sxs-lookup"><span data-stu-id="a042b-175">ISO20022StatementExample</span></span>](https://nam06.safelinks.protection.outlook.com/?url=https%3A%2F%2Fdownload.microsoft.com%2Fdownload%2F1%2F5%2F5%2F155d84ed-c250-48f3-b0b1-c5a431e7855b%2FISO20022-MultipleStatements.xml&data=04%7C01%7CRobert.Schlomann%40microsoft.com%7C30d0c233cb6546547d0a08d8f4965edc%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637528273956712775%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C1000&sdata=3VzvLZK%2BO8PjuI7XVdC6rD2j3nUJfteo7zFp%2B1s9BwM%3D&reserved=0)             |
| <span data-ttu-id="a042b-176">DynamicsAXBAI2Layout</span><span class="sxs-lookup"><span data-stu-id="a042b-176">DynamicsAXBAI2Layout</span></span>                                    | [<span data-ttu-id="a042b-177">BAI2StatementExample</span><span class="sxs-lookup"><span data-stu-id="a042b-177">BAI2StatementExample</span></span>](//download.microsoft.com/download/1/1/6/11693f57-bfc1-4993-a274-5fb978be70fa/BAI2StatementExample.txt)                 |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
