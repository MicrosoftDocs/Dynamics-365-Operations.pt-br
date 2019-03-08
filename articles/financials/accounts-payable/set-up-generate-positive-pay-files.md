---
title: Configurar e gerar arquivos de pagamento positivo
description: Este artigo explica como configurar o pagamento positivo e gerar arquivos de pagamento positivo.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankPositivePayFormat
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 88433
ms.assetid: 73f3dcf6-040a-44ad-9512-7b3e0d17a571
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 0a15669c477223b922d8892d675eaa1df2563714
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "346079"
---
# <a name="set-up-and-generate-positive-pay-files"></a><span data-ttu-id="4e049-103">Configurar e gerar arquivos de pagamento positivo</span><span class="sxs-lookup"><span data-stu-id="4e049-103">Set up and generate positive pay files</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4e049-104">Este artigo explica como configurar o pagamento positivo e gerar arquivos de pagamento positivo.</span><span class="sxs-lookup"><span data-stu-id="4e049-104">This article explains how to set up positive pay and generate positive pay files.</span></span> 

<span data-ttu-id="4e049-105">Configure o pagamento positivo para gerar uma lista eletrônica de cheques que é fornecida ao banco.</span><span class="sxs-lookup"><span data-stu-id="4e049-105">Set up positive pay to generate an electronic list of checks that is provided to the bank.</span></span> <span data-ttu-id="4e049-106">Então, quando o cheque é apresentado ao banco, o banco o compara à lista de cheques.</span><span class="sxs-lookup"><span data-stu-id="4e049-106">Then, when a check is presented to the bank, the bank compares it with the list of checks.</span></span> <span data-ttu-id="4e049-107">Se o cheque corresponder a um cheque na lista, o banco o liberará.</span><span class="sxs-lookup"><span data-stu-id="4e049-107">If the check matches a check in the list, the bank clears it.</span></span> <span data-ttu-id="4e049-108">Se o cheque não corresponder a um cheque na lista, o banco o reterá para revisão.</span><span class="sxs-lookup"><span data-stu-id="4e049-108">If the check doesn't match a check in the list, the bank holds it for review.</span></span>

## <a name="security-for-positive-pay-files"></a><span data-ttu-id="4e049-109">Segurança para arquivos de pagamento positivo</span><span class="sxs-lookup"><span data-stu-id="4e049-109">Security for positive pay files</span></span>
<span data-ttu-id="4e049-110">Os arquivos de pagamento positivo podem conter dados sigilosos sobre o credor e valores de cheque.</span><span class="sxs-lookup"><span data-stu-id="4e049-110">Positive pay files can contain sensitive information about payees and check amounts.</span></span> <span data-ttu-id="4e049-111">Portanto, certifique-se de usar medidas de segurança apropriadas a partir do momento em que os arquivos são geradas até o momento em que são recebidos pelo banco.</span><span class="sxs-lookup"><span data-stu-id="4e049-111">Therefore, make sure that you use appropriate security measures from the time that the files are generated until they are received by the bank.</span></span> <span data-ttu-id="4e049-112">Os arquivos de pagamento positivo são baixados para o local especificado pelo navegador.</span><span class="sxs-lookup"><span data-stu-id="4e049-112">Positive pay files are downloaded to the location that is specified by your web browser.</span></span> <span data-ttu-id="4e049-113">Como os arquivos de pagamento positivo podem conter dados sigilosos, é importante que somente os usuários autorizados tenham acesso para gerar e exibir as informações no Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="4e049-113">Because positive pay files can contain sensitive information, it's important that only authorized users have access to generate and view this information in Microsoft Dynamics 365 for Finance and Operations.</span></span> <span data-ttu-id="4e049-114">Use a tabela a seguir para ajudar a determinar os privilégios necessários.</span><span class="sxs-lookup"><span data-stu-id="4e049-114">Use the following table to help you determine the privileges that are required.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4e049-115">Tarefa</span><span class="sxs-lookup"><span data-stu-id="4e049-115">Task</span></span></th>
<th><span data-ttu-id="4e049-116">Privilégio</span><span class="sxs-lookup"><span data-stu-id="4e049-116">Privilege</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="4e049-117">Gere arquivos de pagamento positivo na página de listagem <strong>Contas bancárias</strong> ou na página <strong>Contas bancárias</strong>.</span><span class="sxs-lookup"><span data-stu-id="4e049-117">Generate positive pay files from the <strong>Bank accounts</strong> list page or the <strong>Bank accounts</strong> page.</span></span></td>
<td><ul>
<li><span data-ttu-id="4e049-118"><strong>Manter informações de pagamento positivo do banco</strong> (BankPositivePayProcess)</span><span class="sxs-lookup"><span data-stu-id="4e049-118"><strong>Maintain bank positive pay information</strong> (BankPositivePayProcess)</span></span></li>
<li><span data-ttu-id="4e049-119"><strong>BankPositivePayExportEntityView</strong> (BankPositivePayExportEntityView)</span><span class="sxs-lookup"><span data-stu-id="4e049-119"><strong>BankPositivePayExportEntityView</strong> (BankPositivePayExportEntityView)</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="4e049-120">Gere arquivos de pagamento positivo para várias entidades legais e contas bancárias na página <strong>Gerar um arquivo de pagamento positivo</strong>.</span><span class="sxs-lookup"><span data-stu-id="4e049-120">Generate positive pay files for multiple legal entities and bank accounts from the <strong>Generate a positive pay file</strong> page.</span></span></td>
<td><ul>
<li><span data-ttu-id="4e049-121"><strong>Manter informações de pagamento positivo do banco</strong> (BankPositivePayProcess)</span><span class="sxs-lookup"><span data-stu-id="4e049-121"><strong>Maintain bank positive pay information</strong> (BankPositivePayProcess)</span></span></li>
<li><span data-ttu-id="4e049-122"><strong>BankPositivePayExportEntityView</strong> (BankPositivePayExportEntityView)</span><span class="sxs-lookup"><span data-stu-id="4e049-122"><strong>BankPositivePayExportEntityView</strong> (BankPositivePayExportEntityView)</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="4e049-123">Exiba os arquivos de pagamento positivo na página <strong>Resumo do arquivo de pagamento positivo</strong>.</span><span class="sxs-lookup"><span data-stu-id="4e049-123">View positive pay files on the <strong>Positive pay file summary</strong> page.</span></span></td>
<td><span data-ttu-id="4e049-124"><strong>Exibir informações de pagamento positivo bancário para várias entidades legais</strong> (BankPositivePayView)</span><span class="sxs-lookup"><span data-stu-id="4e049-124"><strong>View bank positive pay information for multiple legal entities</strong> (BankPositivePayView)</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="4e049-125">Confirme um arquivo de pagamento positivo na página <strong>Resumo do arquivo de pagamento positivo</strong>.</span><span class="sxs-lookup"><span data-stu-id="4e049-125">Confirm a bank positive pay file on the <strong>Positive pay file summary</strong> page.</span></span></td>
<td><span data-ttu-id="4e049-126"><strong>Confirmar arquivo de pagamento positivo</strong> (BankPositivePayConfirm)</span><span class="sxs-lookup"><span data-stu-id="4e049-126"><strong>Confirm positive payment file</strong> (BankPositivePayConfirm)</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="4e049-127">Cancele um arquivo de pagamento positivo na página <strong>Resumo do arquivo de pagamento positivo</strong>.</span><span class="sxs-lookup"><span data-stu-id="4e049-127">Recall a bank positive pay file on the <strong>Positive pay file summary</strong> page.</span></span></td>
<td><span data-ttu-id="4e049-128"><strong>Cancelar arquivo de pagamento positivo</strong> (BankPositivePayRecall)</span><span class="sxs-lookup"><span data-stu-id="4e049-128"><strong>Recall positive pay file</strong> (BankPositivePayRecall)</span></span></td>
</tr>
</tbody>
</table>

## <a name="set-up-a-positive-pay-format"></a><span data-ttu-id="4e049-129">Configurar um formato de pagamento positivo</span><span class="sxs-lookup"><span data-stu-id="4e049-129">Set up a positive pay format</span></span>
<span data-ttu-id="4e049-130">Os arquivos de pagamento positivo são criados usando entidades de dados.</span><span class="sxs-lookup"><span data-stu-id="4e049-130">Positive pay files are created by using data entities.</span></span> <span data-ttu-id="4e049-131">Antes de gerar um arquivo de pagamento positivo, você deve configurar um formato da entrada de transformação usado para traduzir as informações de verificação em um formato que possa se comunicar com o banco.</span><span class="sxs-lookup"><span data-stu-id="4e049-131">Before you can generate a positive pay file, you must set up a transformation input format that will be used to translate the check information into a format that can communicate with the bank.</span></span> <span data-ttu-id="4e049-132">Na página **Formato de pagamento positivo**, você pode criar um identificador e uma descrição do formato de arquivo.</span><span class="sxs-lookup"><span data-stu-id="4e049-132">On the **Positive pay format** page, you can create a file format identifier and a description.</span></span> <span data-ttu-id="4e049-133">O formato de entrada de transformação deve ser do tipo XML.</span><span class="sxs-lookup"><span data-stu-id="4e049-133">The transformation input format must be of the XML type.</span></span> <span data-ttu-id="4e049-134">O formato específico depende do arquivo de transformação que você está usando.</span><span class="sxs-lookup"><span data-stu-id="4e049-134">The specific format depends on the transformation file that you're using.</span></span> <span data-ttu-id="4e049-135">Por exemplo, o arquivo XSLT (Extensible Stylesheet Language Transformations) de exemplo fornecido usa o formato **XML-Element**.</span><span class="sxs-lookup"><span data-stu-id="4e049-135">For example, the sample Extensible Stylesheet Language Transformations (XSLT) file that is provided uses the **XML-Element** format.</span></span> <span data-ttu-id="4e049-136">Use a ação **Arquivo de upload usado para a transformação** para especificar o local do arquivo de transformação para o formato exigido pelo banco.</span><span class="sxs-lookup"><span data-stu-id="4e049-136">Use the **Upload file used for transformation** action to specify the location of the transform file for the format that your bank requires.</span></span>

## <a name="example-xslt-file-for-positive-pay-file"></a><span data-ttu-id="4e049-137">Exemplo: arquivo XSLT para arquivo de pagamento positivo</span><span class="sxs-lookup"><span data-stu-id="4e049-137">Example: XSLT file for positive pay file</span></span>
    <xsl:stylesheet version="1.0" xmlns:xsl="http://www.w3.org/1999/XSL/Transform" xmlns:msxsl="urn:schemas-microsoft-com:xslt" exclude-result-prefixes="msxsl xslthelper" xmlns="urn:iso:std:iso:20022:tech:xsd:pain.001.001.02" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xslthelper="http://schemas.microsoft.com/BizTalk/2003/xslthelper">
      <xsl:output method="xml" omit-xml-declaration="no" version="1.0" encoding="utf-8"/>
      <xsl:template match="/">
        <xsl:value-of select="'
    '" />
        <Document>
          <xsl:value-of select="'
    '" />
          <!--Header Begin-->
          <xsl:value-of select='string("Vendor ID,Vendor Name,Voided,Document Type,Check Date,Check Number,Check Amount,Checkbook ID,Vendor Class ID,Posted Date")'/>
          <xsl:value-of select="'
    '" />
          <!--Header End-->
          <xsl:for-each select="Document/BankPositivePayExportEntity">
            <!--Cheque Detail begin-->
            <xsl:value-of select='RECIPIENTACCOUNTNUM/text()'/>
            <xsl:value-of select="','" />
            <xsl:value-of select='BANKNEGINSTRECIPIENTNAME/text()'/>
            <xsl:value-of select="','" />
            <xsl:choose>
              <xsl:when test='CHEQUESTATUS/text()=normalize-space("Void") or CHEQUESTATUS/text()=normalize-space("Rejected") or CHEQUESTATUS/text()=normalize-space("Cancelled")'>
                <xsl:value-of select='string("Yes")'/>
              </xsl:when>
              <xsl:when test='CHEQUESTATUS/text()=normalize-space("Payment")'>
                <xsl:value-of select='string("No")'/>
              </xsl:when>
              <xsl:otherwise>
                <xsl:value-of select='string(" ")'/>
              </xsl:otherwise>
            </xsl:choose>
            <xsl:value-of select="','" />
            <xsl:value-of select='string("Payment")'/>
            <xsl:value-of select="','" />
            <xsl:value-of select='TRANSDATE/text()'/>
            <xsl:value-of select="','" />
            <xsl:value-of select='CHEQUENUM/text()'/>
            <xsl:value-of select="','" />
            <xsl:value-of select='AMOUNTCUR/text()'/>
            <xsl:value-of select="','" />
            <xsl:value-of select='string("BOA-#1812")'/>
            <xsl:value-of select="','" />
            <xsl:choose>
              <xsl:when test='RECIPIENTTYPE/text()=normalize-space("Vend")'>
                <xsl:value-of select='VENDGROUP/text()'/>
              </xsl:when>
              <xsl:otherwise>
                <xsl:value-of select='CUSTGROUP/text()'/>
              </xsl:otherwise>
            </xsl:choose>
            <xsl:value-of select="','" />
            <xsl:value-of select='TRANSDATE/text()'/>
            <xsl:value-of select="'
    '" />
          </xsl:for-each>
        </Document>
      </xsl:template>
    </xsl:stylesheet>

## <a name="assign-the-positive-pay-format-to-a-bank-account"></a><span data-ttu-id="4e049-138">Atribuir o formato de pagamento positivo a uma conta bancária</span><span class="sxs-lookup"><span data-stu-id="4e049-138">Assign the positive pay format to a bank account</span></span>
<span data-ttu-id="4e049-139">Para cada conta bancária que você deseja gerar as informações de pagamento positivo, é necessário atribuir o formato de pagamento positivo que foi especificado na seção anterior.</span><span class="sxs-lookup"><span data-stu-id="4e049-139">For each bank account that you want to generate positive pay information for, you must assign the positive pay format that you specified in the previous section.</span></span> <span data-ttu-id="4e049-140">Na página **Contas bancárias**, selecione o formato de pagamento positivo que corresponda à conta bancária.</span><span class="sxs-lookup"><span data-stu-id="4e049-140">On the **Bank accounts** page, select the positive pay format that corresponds to the bank account.</span></span> <span data-ttu-id="4e049-141">No campo **Data inicial do pagamento positivo**, insira a primeira data para gerar os arquivos de pagamento positivo.</span><span class="sxs-lookup"><span data-stu-id="4e049-141">In the **Positive pay start date** field, enter the first date to generate positive pay files.</span></span> <span data-ttu-id="4e049-142">É importante que você insira uma data nesse campo.</span><span class="sxs-lookup"><span data-stu-id="4e049-142">It's important that you enter a date in this field.</span></span> <span data-ttu-id="4e049-143">Caso contrário, o primeiro arquivo de pagamento positivo gerado incluirá todos os cheques já criados para essa conta bancária.</span><span class="sxs-lookup"><span data-stu-id="4e049-143">Otherwise, the first positive pay file that you generate will include all checks that have ever been created for this bank account.</span></span>

## <a name="assign-a-number-sequence-for-positive-pay-files"></a><span data-ttu-id="4e049-144">Atribuir uma sequência numérica para arquivos de pagamento positivo</span><span class="sxs-lookup"><span data-stu-id="4e049-144">Assign a number sequence for positive pay files</span></span>
<span data-ttu-id="4e049-145">Cada arquivo de pagamento positivo deve ter um número exclusivo.</span><span class="sxs-lookup"><span data-stu-id="4e049-145">Each positive pay file must have a unique number.</span></span> <span data-ttu-id="4e049-146">Use a guia **Sequências numéricas** na página **Parâmetros de de gerenciamento de caixa e bancário** para criar uma sequência numérica para arquivos de pagamento positivo.</span><span class="sxs-lookup"><span data-stu-id="4e049-146">Use the **Number sequences** tab on the **Cash and bank management parameters** page to create a number sequence for positive pay files.</span></span>

## <a name="generate-a-positive-pay-file-for-a-single-bank-account"></a><span data-ttu-id="4e049-147">Gerar um arquivo de pagamento positivo para uma única conta bancária</span><span class="sxs-lookup"><span data-stu-id="4e049-147">Generate a positive pay file for a single bank account</span></span>
<span data-ttu-id="4e049-148">Você pode gerar um arquivo de pagamento positivo para uma única entidade legal e uma única conta bancária.</span><span class="sxs-lookup"><span data-stu-id="4e049-148">You can generate a positive pay file for a single legal entity and a single bank account.</span></span> <span data-ttu-id="4e049-149">Para obter informações sobre como gerar arquivos de pagamento positivo para várias entidades legais e contas bancárias ao mesmo tempo, consulte a próxima seção.</span><span class="sxs-lookup"><span data-stu-id="4e049-149">For information about how to generate positive pay files for multiple legal entities and bank accounts at the same time, see the next section.</span></span> <span data-ttu-id="4e049-150">Para gerar um arquivo de pagamento positivo para uma única entidade legal e uma única conta bancária, abra a caixa de diálogo **Gerar um arquivo de pagamento positivo** na página **Contas bancárias**.</span><span class="sxs-lookup"><span data-stu-id="4e049-150">To generate a positive pay file for a single legal entity and a single bank account, open the **Generate a positive pay file** dialog box from the **Bank accounts** page.</span></span> <span data-ttu-id="4e049-151">No campo **Data de fechamento**, insira a data do último cheque a ser incluído no arquivo de pagamento positivo.</span><span class="sxs-lookup"><span data-stu-id="4e049-151">In the **Cut-off date** field, enter the last check date to include in the positive pay file.</span></span> <span data-ttu-id="4e049-152">Todos os cheques que não tiverem sido incluídos em um arquivo de pagamento positivo até o final dessa data de verificação serão incluídos no arquivo.</span><span class="sxs-lookup"><span data-stu-id="4e049-152">All checks that haven’t been included in a positive pay file by the end of this check date are included in the file.</span></span>

## <a name="generate-a-positive-pay-file-for-multiple-bank-accounts"></a><span data-ttu-id="4e049-153">Gerar um arquivo de pagamento positivo para várias contas bancárias</span><span class="sxs-lookup"><span data-stu-id="4e049-153">Generate a positive pay file for multiple bank accounts</span></span>
<span data-ttu-id="4e049-154">Para gerar um arquivo de pagamento positivo para várias contas bancárias, use a tarefa periódica **Gerar um arquivo de pagamento positivo**.</span><span class="sxs-lookup"><span data-stu-id="4e049-154">To generate a positive pay file for multiple bank accounts, use the **Generate a positive pay file** periodic task.</span></span> <span data-ttu-id="4e049-155">Selecione o formato de pagamento positivo para o arquivo e especifique se deseja gerar o arquivo de pagamento positivo para todas as entidades legais ou para uma entidade legal selecionada.</span><span class="sxs-lookup"><span data-stu-id="4e049-155">Select the positive pay format for the file, and specify whether to generate the file for all legal entities or for a selected legal entity.</span></span> <span data-ttu-id="4e049-156">Você também pode gerar o arquivo de pagamento positivo para todas as contas bancárias que usam o formato de pagamento positivo para uma conta bancária selecionada.</span><span class="sxs-lookup"><span data-stu-id="4e049-156">You can also generate the positive pay file for all bank accounts that use the specified positive pay format or for a selected bank account.</span></span> <span data-ttu-id="4e049-157">No campo **Data de fechamento**, insira a data do último cheque a ser incluído no arquivo de pagamento positivo.</span><span class="sxs-lookup"><span data-stu-id="4e049-157">In the **Cut-off date** field, enter the last check date to include in the positive pay file.</span></span> <span data-ttu-id="4e049-158">Todos os cheques que não tiverem sido incluídos em um arquivo de pagamento positivo até o final dessa data de verificação serão incluídos no arquivo.</span><span class="sxs-lookup"><span data-stu-id="4e049-158">All checks that haven’t been included in a positive pay file by the end of this check date are included in the file.</span></span>

## <a name="view-the-results-of-positive-pay-file-generation"></a><span data-ttu-id="4e049-159">Exibir os resultados de geração de um arquivo de pagamento positivo</span><span class="sxs-lookup"><span data-stu-id="4e049-159">View the results of positive pay file generation</span></span>
<span data-ttu-id="4e049-160">Depois que o arquivo positivo de pagamento for gerado, você poderá exibir os resultados na página **Resumo do arquivo de pagamento positivo**.</span><span class="sxs-lookup"><span data-stu-id="4e049-160">After the positive pay file is generated, you can view the results on the **Positive pay file summary** page.</span></span> <span data-ttu-id="4e049-161">Para exibir os detalhes das verificações individuais, use a página de detalhes **Arquivo de pagamento positivo**.</span><span class="sxs-lookup"><span data-stu-id="4e049-161">To view the details of the individual checks, use the **Positive pay file** details page.</span></span>

## <a name="confirm-a-positive-pay-file"></a><span data-ttu-id="4e049-162">Confirmar um arquivo de pagamento positivo</span><span class="sxs-lookup"><span data-stu-id="4e049-162">Confirm a positive pay file</span></span>
<span data-ttu-id="4e049-163">Depois que os cheques listados em um arquivo de pagamento positivo forem pagos, você receberá um número de confirmação do banco.</span><span class="sxs-lookup"><span data-stu-id="4e049-163">After the checks that are listed in a positive pay file have been paid, you receive a confirmation number from your bank.</span></span> <span data-ttu-id="4e049-164">Em seguida, será possível confirmar o arquivo de pagamento positivo..</span><span class="sxs-lookup"><span data-stu-id="4e049-164">You can then confirm the positive pay file.</span></span> <span data-ttu-id="4e049-165">Na página **Resumo do arquivo de pagamento positivo**, selecione um arquivo de pagamento positivo com o status **Criado** e selecione a ação **Inserir confirmação**.</span><span class="sxs-lookup"><span data-stu-id="4e049-165">On the **Positive pay file summary** page, select a positive pay file that has a status of **Created**, and then select the **Enter confirmation** action.</span></span> <span data-ttu-id="4e049-166">Quando você confirma um arquivo de pagamento positivo, o número de confirmação recebido do banco é registrado.</span><span class="sxs-lookup"><span data-stu-id="4e049-166">When you confirm a positive pay file, the confirmation number that you received from the bank is recorded.</span></span>

## <a name="recall-a-positive-pay-file"></a><span data-ttu-id="4e049-167">Cancelar um arquivo de pagamento positivo</span><span class="sxs-lookup"><span data-stu-id="4e049-167">Recall a positive pay file</span></span>
<span data-ttu-id="4e049-168">Se você tiver de alterar um arquivo de pagamento positivo, poderá cancelá-lo.</span><span class="sxs-lookup"><span data-stu-id="4e049-168">If you must change a positive pay file, you can recall it.</span></span> <span data-ttu-id="4e049-169">Na página **Resumo do arquivo de pagamento positivo**, selecione um arquivo de pagamento positivo com o status **Criado** e selecione a ação **Cancelar**.</span><span class="sxs-lookup"><span data-stu-id="4e049-169">On the **Positive pay file summary** page, select a positive pay file that has a status of **Created**, and then select the **Recall** action.</span></span> <span data-ttu-id="4e049-170">Para cada cheque no arquivo de pagamento positivo, o campo que indica se esse cheque foi incluído em um arquivo de pagamento positivo será redefinido.</span><span class="sxs-lookup"><span data-stu-id="4e049-170">For each check in the positive pay file, the field that indicates whether that check has been included in a positive pay file is reset.</span></span> <span data-ttu-id="4e049-171">Em seguida, você poderá criar um novo arquivo de pagamento positivo que inclua o cheque cancelado.</span><span class="sxs-lookup"><span data-stu-id="4e049-171">You can then create a new positive pay file that includes the check that was recalled.</span></span>



