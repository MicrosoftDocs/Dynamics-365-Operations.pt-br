---
title: "Solução de problemas de importação do arquivo de extrato bancário"
description: "É importante que o arquivo de extrato bancário do banco corresponda ao layout ao qual o Microsoft Dynamics 365 for Finance and Operations, Enterprise edition oferece suporte. Devido a padrões restritos de extratos bancários, a maioria das integrações funcionarão corretamente. No entanto, algumas vezes, o arquivo de extrato bancário não é importado ou apresenta resultados incorretos. Normalmente, esses problemas são causados por pequenas diferenças no arquivo de extrato bancário. Este artigo explica como corrigir essas diferenças e resolver os problemas."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 141273
ms.assetid: 3ee2f32b-02aa-420b-8990-e6aa5fc6bda3
ms.search.region: global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: 51cd32217b2f753f606e3060b4872a8274f16549
ms.contentlocale: pt-br
ms.lasthandoff: 07/18/2017

---

# <a name="bank-statement-file-import-troubleshooting"></a><span data-ttu-id="f196f-107">Solução de problemas de importação do arquivo de extrato bancário</span><span class="sxs-lookup"><span data-stu-id="f196f-107">Bank statement file import troubleshooting</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="f196f-108">É importante que o arquivo de extrato bancário do banco corresponda ao layout ao qual o Microsoft Dynamics 365 for Finance and Operations, Enterprise edition oferece suporte.</span><span class="sxs-lookup"><span data-stu-id="f196f-108">It's important that the bank statement file from the bank match the layout that Microsoft Dynamics 365 for Finance and Operations, Enterprise edition supports.</span></span> <span data-ttu-id="f196f-109">Devido a padrões restritos de extratos bancários, a maioria das integrações funcionarão corretamente.</span><span class="sxs-lookup"><span data-stu-id="f196f-109">Because of strict standards for bank statements, most integrations will work correctly.</span></span> <span data-ttu-id="f196f-110">No entanto, algumas vezes, o arquivo de extrato bancário não é importado ou apresenta resultados incorretos.</span><span class="sxs-lookup"><span data-stu-id="f196f-110">However, sometimes the statement file can't be imported or has incorrect results.</span></span> <span data-ttu-id="f196f-111">Normalmente, esses problemas são causados por pequenas diferenças no arquivo de extrato bancário.</span><span class="sxs-lookup"><span data-stu-id="f196f-111">Typically, these issues are caused by small differences in the bank statement file.</span></span> <span data-ttu-id="f196f-112">Este artigo explica como corrigir essas diferenças e resolver os problemas.</span><span class="sxs-lookup"><span data-stu-id="f196f-112">This article explains how to fix these differences and resolve the issues.</span></span>

<a name="what-is-the-error"></a><span data-ttu-id="f196f-113">Qual é o erro?</span><span class="sxs-lookup"><span data-stu-id="f196f-113">What is the error?</span></span>
------------------

<span data-ttu-id="f196f-114">Após tentar importar um arquivo de extrato bancário, acesse o histórico de trabalho de gerenciamento de dados e os detalhes da execução para localizar o erro.</span><span class="sxs-lookup"><span data-stu-id="f196f-114">After you try to import a bank statement file, go to the Data management job history and its execution details to find the error.</span></span> <span data-ttu-id="f196f-115">O erro pode ajudar indicando o extrato, o saldo ou a linha do extrato.</span><span class="sxs-lookup"><span data-stu-id="f196f-115">The error can help by pointing to the statement, balance, or statement line.</span></span> <span data-ttu-id="f196f-116">Entretanto, é improvável que você receba informações suficientes para identificar o campo ou o elemento que está causando o problema.</span><span class="sxs-lookup"><span data-stu-id="f196f-116">However, it's unlikely to provide enough information to help you identify the field or element that is causing the issue.</span></span>

## <a name="what-are-the-differences"></a><span data-ttu-id="f196f-117">Quais são as diferenças?</span><span class="sxs-lookup"><span data-stu-id="f196f-117">What are the differences?</span></span>
<span data-ttu-id="f196f-118">Compare a definição de layout do arquivo bancário com a definição de importação do Finance and Operations, e observe todas as diferenças nos campos e nos elementos.</span><span class="sxs-lookup"><span data-stu-id="f196f-118">Compare the bank file layout definition to the Finance and Operations import definition, and note any differences in the fields and elements.</span></span> <span data-ttu-id="f196f-119">Compare o arquivo de extrato bancário ao arquivo de amostra relacionado do Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="f196f-119">Compare the bank statement file to the related sample Finance and Operations file.</span></span> <span data-ttu-id="f196f-120">Nos arquivos ISO20022, todas as diferenças devem ser fáceis de ver.</span><span class="sxs-lookup"><span data-stu-id="f196f-120">In the ISO20022 files, any differences should be easy to see.</span></span>

## <a name="transformations"></a><span data-ttu-id="f196f-121">Transformações</span><span class="sxs-lookup"><span data-stu-id="f196f-121">Transformations</span></span>
<span data-ttu-id="f196f-122">Normalmente, a alteração deve ser feita em uma das três transformações.</span><span class="sxs-lookup"><span data-stu-id="f196f-122">Typically, the change must be made in one of three transformations.</span></span> <span data-ttu-id="f196f-123">Cada transformação é gravada em um padrão específico.</span><span class="sxs-lookup"><span data-stu-id="f196f-123">Each transformation is written for a specific standard.</span></span>

| <span data-ttu-id="f196f-124">Nome do recurso</span><span class="sxs-lookup"><span data-stu-id="f196f-124">Resource name</span></span>                                         | <span data-ttu-id="f196f-125">Nome do arquivo</span><span class="sxs-lookup"><span data-stu-id="f196f-125">File name</span></span>                          |
|-------------------------------------------------------|------------------------------------|
| <span data-ttu-id="f196f-126">BankStmtImport\_BAI2CSV\_to\_BAI2XML\_xslt</span><span class="sxs-lookup"><span data-stu-id="f196f-126">BankStmtImport\_BAI2CSV\_to\_BAI2XML\_xslt</span></span>            | <span data-ttu-id="f196f-127">BAI2CSV-to-BAI2XML.xslt</span><span class="sxs-lookup"><span data-stu-id="f196f-127">BAI2CSV-to-BAI2XML.xslt</span></span>            |
| <span data-ttu-id="f196f-128">BankStmtImport\_ISO20022XML\_to\_Reconciliation\_xslt</span><span class="sxs-lookup"><span data-stu-id="f196f-128">BankStmtImport\_ISO20022XML\_to\_Reconciliation\_xslt</span></span> | <span data-ttu-id="f196f-129">ISO20022XML-to-Reconciliation.xslt</span><span class="sxs-lookup"><span data-stu-id="f196f-129">ISO20022XML-to-Reconciliation.xslt</span></span> |
| <span data-ttu-id="f196f-130">BankStmtImport\_MT940TXT\_to\_MT940XML\_xslt</span><span class="sxs-lookup"><span data-stu-id="f196f-130">BankStmtImport\_MT940TXT\_to\_MT940XML\_xslt</span></span>          | <span data-ttu-id="f196f-131">MT940TXT-to-MT940XML.xslt</span><span class="sxs-lookup"><span data-stu-id="f196f-131">MT940TXT-to-MT940XML.xslt</span></span>          |

## <a name="debugging-transformations"></a><span data-ttu-id="f196f-132">Depurando transformações</span><span class="sxs-lookup"><span data-stu-id="f196f-132">Debugging transformations</span></span>
### <a name="adjust-the-bai2-and-mt940-files"></a><span data-ttu-id="f196f-133">Ajustar os arquivos BAI2 e MT940</span><span class="sxs-lookup"><span data-stu-id="f196f-133">Adjust the BAI2 and MT940 files</span></span>

<span data-ttu-id="f196f-134">Os arquivos BAI2 e MT940 são baseados em texto e requerem um ajuste para habilitar a depuração das transformações XSLT.</span><span class="sxs-lookup"><span data-stu-id="f196f-134">The BAI2 and MT940 files are text-based files and require an adjustment to enable Extensible Stylesheet Language Transformations (XSLT) debugging.</span></span> <span data-ttu-id="f196f-135">O programa faz esse ajuste quando um arquivo é importado.</span><span class="sxs-lookup"><span data-stu-id="f196f-135">The program makes this adjustment when a file is imported.</span></span>

1.  <span data-ttu-id="f196f-136">Crie um arquivo XML e copie o texto a seguir nele.</span><span class="sxs-lookup"><span data-stu-id="f196f-136">Create an XML file, and copy the following text into it.</span></span>

        <Batch><![CDATA[PASTESTATEMENTFILEHERE
        ]]></Batch>

2.  <span data-ttu-id="f196f-137">Copie o conteúdo do arquivo de extrato bancário e cole-o no arquivo XML para que ele substitua **PASTESTATEMENTFILEHERE**.</span><span class="sxs-lookup"><span data-stu-id="f196f-137">Copy the contents of the bank statement file, and paste them into the XML file so that they replace **PASTESTATEMENTFILEHERE**.</span></span>

### <a name="debug-the-xslt"></a><span data-ttu-id="f196f-138">Depurar a XSLT</span><span class="sxs-lookup"><span data-stu-id="f196f-138">Debug the XSLT</span></span>

<span data-ttu-id="f196f-139">Para obter mais informações, consulte <https://msdn.microsoft.com/en-us/library/ms255605.aspx>.</span><span class="sxs-lookup"><span data-stu-id="f196f-139">For more information, see <https://msdn.microsoft.com/en-us/library/ms255605.aspx>.</span></span>

1.  <span data-ttu-id="f196f-140">Inicie o Microsoft Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="f196f-140">Start Microsoft Visual Studio.</span></span>
2.  <span data-ttu-id="f196f-141">Crie um aplicativo de console.</span><span class="sxs-lookup"><span data-stu-id="f196f-141">Create a console application.</span></span>
3.  <span data-ttu-id="f196f-142">Abra a XSLT apropriada.</span><span class="sxs-lookup"><span data-stu-id="f196f-142">Open the appropriate XSLT.</span></span>
4.  <span data-ttu-id="f196f-143">Clique na XLST e na respectiva página de propriedades.</span><span class="sxs-lookup"><span data-stu-id="f196f-143">Click the XLST and its properties page.</span></span>
5.  <span data-ttu-id="f196f-144">Defina a entrada para o local do arquivo de extrato bancário.</span><span class="sxs-lookup"><span data-stu-id="f196f-144">Set the input to the location of the bank statement file.</span></span>
6.  <span data-ttu-id="f196f-145">Defina um local e um nome de arquivo como saída.</span><span class="sxs-lookup"><span data-stu-id="f196f-145">Define a location and file name for the output.</span></span>
7.  <span data-ttu-id="f196f-146">Definia os pontos de quebra necessários.</span><span class="sxs-lookup"><span data-stu-id="f196f-146">Set the required break points.</span></span>
8.  <span data-ttu-id="f196f-147">No menu, clique em **XML** &gt; **Iniciar Depuração XSLT**.</span><span class="sxs-lookup"><span data-stu-id="f196f-147">On the menu, click **XML** &gt; **Start XSLT Debugging**.</span></span>

### <a name="format-the-xslt-output"></a><span data-ttu-id="f196f-148">Formatar a saída XSLT</span><span class="sxs-lookup"><span data-stu-id="f196f-148">Format the XSLT output</span></span>

<span data-ttu-id="f196f-149">Quando a transformação é executada, ela cria um arquivo de saída que você pode exibir no Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="f196f-149">When the transformation runs, it creates an output file that you can view in Visual Studio.</span></span> <span data-ttu-id="f196f-150">Use Ctrl+A, Ctrl+K e Ctrl+D para formatar rapidamente o arquivo de saída.</span><span class="sxs-lookup"><span data-stu-id="f196f-150">Use Ctrl+A, Ctrl+K, and Ctrl+D to quickly format the output file.</span></span>

### <a name="adjust-the-transformation"></a><span data-ttu-id="f196f-151">Ajustar a transformação</span><span class="sxs-lookup"><span data-stu-id="f196f-151">Adjust the transformation</span></span>

<span data-ttu-id="f196f-152">Ajuste a transformação para obter o campo ou elemento apropriado no arquivo de extrato bancário.</span><span class="sxs-lookup"><span data-stu-id="f196f-152">Adjust the transformation to get the appropriate field or element in the bank statement file.</span></span> <span data-ttu-id="f196f-153">Em seguida, mapeie esse campo ou elemento ao elemento apropriado do Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="f196f-153">Then map that field or element to the appropriate Finance and Operations element.</span></span>

### <a name="debitcredit-indicator"></a><span data-ttu-id="f196f-154">Indicador de débito/crédito</span><span class="sxs-lookup"><span data-stu-id="f196f-154">Debit/credit indicator</span></span>

<span data-ttu-id="f196f-155">Às vezes, os débitos são importados como créditos, e os créditos são importados como débitos.</span><span class="sxs-lookup"><span data-stu-id="f196f-155">Sometimes, debits might be imported as credits, and credits might be imported as debits.</span></span> <span data-ttu-id="f196f-156">Para resolver esse problema, você deve alterar a XSLT apropriada.</span><span class="sxs-lookup"><span data-stu-id="f196f-156">To resolve this issue, you must change the appropriate XSLT.</span></span> <span data-ttu-id="f196f-157">Se os extratos bancários forem provenientes de vários bancos, verifique se todos usam a mesma abordagem de débito/crédito, ou crie transformações separadas.</span><span class="sxs-lookup"><span data-stu-id="f196f-157">If bank statements come from multiple banks, make sure that they all use the same debit/credit approach, or create separate transformations.</span></span>

-   <span data-ttu-id="f196f-158">Modelo BAI2XML-to-Reconciliation.xlst GetAmountCreditDebitIndicator</span><span class="sxs-lookup"><span data-stu-id="f196f-158">BAI2XML-to-Reconciliation.xlst GetAmountCreditDebitIndicator template</span></span>
-   <span data-ttu-id="f196f-159">Modelo ISO20022XML-to-Reconcilation.xslt GetCreditDebit</span><span class="sxs-lookup"><span data-stu-id="f196f-159">ISO20022XML-to-Reconcilation.xslt GetCreditDebit template</span></span>
-   <span data-ttu-id="f196f-160">Modelo MT940XML-to-Reconcilation.xslt GetCreditDebitIndicator</span><span class="sxs-lookup"><span data-stu-id="f196f-160">MT940XML-to-Reconcilation.xslt GetCreditDebitIndicator template</span></span>

## <a name="examples-of-bank-statement-formats-and-technical-layouts"></a><span data-ttu-id="f196f-161">Exemplos de formatos de extrato bancário e layouts técnicos</span><span class="sxs-lookup"><span data-stu-id="f196f-161">Examples of bank statement formats and technical layouts</span></span>
<span data-ttu-id="f196f-162">A tabela a seguir lista exemplos das definições de layout técnico de arquivos de importação avançada de reconciliação bancária e de três arquivos de exemplo de extrato bancário relacionados.</span><span class="sxs-lookup"><span data-stu-id="f196f-162">The following table lists examples of the technical layout definitions for advanced bank reconciliation import files and three related bank statement example files.</span></span> <span data-ttu-id="f196f-163">Você pode baixar arquivos de exemplo e layouts técnicos aqui: https://mbs.microsoft.com/customersource/northamerica/AX/learning/documentation/how-to-articles/exofbankstfotechlayouts</span><span class="sxs-lookup"><span data-stu-id="f196f-163">You can download the example files and technical layouts here: https://mbs.microsoft.com/customersource/northamerica/AX/learning/documentation/how-to-articles/exofbankstfotechlayouts</span></span>  


| <span data-ttu-id="f196f-164">Definição do layout técnico</span><span class="sxs-lookup"><span data-stu-id="f196f-164">Technical layout definition</span></span>                             | <span data-ttu-id="f196f-165">Arquivo de exemplo de extrato bancário</span><span class="sxs-lookup"><span data-stu-id="f196f-165">Bank statement example file</span></span>          |
|---------------------------------------------------------|--------------------------------------|
| <span data-ttu-id="f196f-166">DynamicsAXMT940Layout</span><span class="sxs-lookup"><span data-stu-id="f196f-166">DynamicsAXMT940Layout</span></span>                                   | <span data-ttu-id="f196f-167">MT940StatementExample</span><span class="sxs-lookup"><span data-stu-id="f196f-167">MT940StatementExample</span></span>                |
| <span data-ttu-id="f196f-168">DynamicsAXISO20022Layout</span><span class="sxs-lookup"><span data-stu-id="f196f-168">DynamicsAXISO20022Layout</span></span>                                | <span data-ttu-id="f196f-169">ISO20022StatementExample</span><span class="sxs-lookup"><span data-stu-id="f196f-169">ISO20022StatementExample</span></span>             |
| <span data-ttu-id="f196f-170">DynamicsAXBAI2Layout</span><span class="sxs-lookup"><span data-stu-id="f196f-170">DynamicsAXBAI2Layout</span></span>                                    | <span data-ttu-id="f196f-171">BAI2StatementExample</span><span class="sxs-lookup"><span data-stu-id="f196f-171">BAI2StatementExample</span></span>                 |






