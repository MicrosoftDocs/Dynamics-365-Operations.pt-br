---
title: Configurar e gerar arquivos de pagamento positivo
description: Este tópico explica como configurar o pagamento positivo e gerar arquivos de pagamento positivo.
author: abruer
manager: AnnBe
ms.date: 03/06/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankPositivePayFormat
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 88433
ms.assetid: 73f3dcf6-040a-44ad-9512-7b3e0d17a571
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 00ab2b28813dce4f5317fc93c13c89d0753d4033
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1837171"
---
# <a name="set-up-and-generate-positive-pay-files"></a>Configurar e gerar arquivos de pagamento positivo

[!include [banner](../includes/banner.md)]

Este tópico explica como configurar o pagamento positivo e gerar arquivos de pagamento positivo. 

Configure o pagamento positivo para gerar uma lista eletrônica de cheques que é fornecida ao banco. Então, quando o cheque é apresentado ao banco, o banco o compara à lista de cheques. Se o cheque corresponder a um cheque na lista, o banco o liberará. Se o cheque não corresponder a um cheque na lista, o banco o reterá para revisão.

## <a name="security-for-positive-pay-files"></a>Segurança para arquivos de pagamento positivo
Os arquivos de pagamento positivo podem conter dados sigilosos sobre o credor e valores de cheque. Portanto, certifique-se de usar medidas de segurança apropriadas a partir do momento em que os arquivos são geradas até o momento em que são recebidos pelo banco. Os arquivos de pagamento positivo são baixados para o local especificado pelo navegador. Como os arquivos de pagamento positivo podem conter dados sigilosos, é importante que somente os usuários autorizados tenham acesso para gerar e exibir as informações no Microsoft Dynamics 365 for Finance and Operations. Use a tabela a seguir para ajudar a determinar os privilégios necessários.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Tarefa</th>
<th>Privilégio</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Gere arquivos de pagamento positivo na página de listagem <strong>Contas bancárias</strong> ou na página <strong>Contas bancárias</strong>.</td>
<td><ul>
<li><strong>Manter informações de pagamento positivo do banco</strong> (BankPositivePayProcess)</li>
<li><strong>BankPositivePayExportEntityView</strong> (BankPositivePayExportEntityView)</li>
</ul></td>
</tr>
<tr class="even">
<td>Gere arquivos de pagamento positivo para várias entidades legais e contas bancárias na página <strong>Gerar um arquivo de pagamento positivo</strong>.</td>
<td><ul>
<li><strong>Manter informações de pagamento positivo do banco</strong> (BankPositivePayProcess)</li>
<li><strong>BankPositivePayExportEntityView</strong> (BankPositivePayExportEntityView)</li>
</ul></td>
</tr>
<tr class="odd">
<td>Exiba os arquivos de pagamento positivo na página <strong>Resumo do arquivo de pagamento positivo</strong>.</td>
<td><strong>Exibir informações de pagamento positivo bancário para várias entidades legais</strong> (BankPositivePayView)</td>
</tr>
<tr class="even">
<td>Confirme um arquivo de pagamento positivo na página <strong>Resumo do arquivo de pagamento positivo</strong>.</td>
<td><strong>Confirmar arquivo de pagamento positivo</strong> (BankPositivePayConfirm)</td>
</tr>
<tr class="odd">
<td>Cancele um arquivo de pagamento positivo na página <strong>Resumo do arquivo de pagamento positivo</strong>.</td>
<td><strong>Cancelar arquivo de pagamento positivo</strong> (BankPositivePayRecall)</td>
</tr>
</tbody>
</table>

## <a name="set-up-a-positive-pay-format"></a>Configurar um formato de pagamento positivo
Os arquivos de pagamento positivo são criados usando entidades de dados. Antes de gerar um arquivo de pagamento positivo, você deve configurar um formato da entrada de transformação usado para traduzir as informações de verificação em um formato que possa se comunicar com o banco. Na página **Formato de pagamento positivo**, você pode criar um identificador e uma descrição do formato de arquivo. O formato de entrada de transformação deve ser do tipo XML. O formato específico depende do arquivo de transformação que você está usando. Por exemplo, o arquivo XSLT (Extensible Stylesheet Language Transformations) de exemplo fornecido usa o formato **XML-Element**. Use a ação **Arquivo de upload usado para a transformação** para especificar o local do arquivo de transformação para o formato exigido pelo banco.

## <a name="example-xslt-file-for-positive-pay-file"></a>Exemplo: arquivo XSLT para arquivo de pagamento positivo
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
          <xsl:for-each select="Document/BANKPOSITIVEPAYEXPORTENTITY">
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

## <a name="assign-the-positive-pay-format-to-a-bank-account"></a>Atribuir o formato de pagamento positivo a uma conta bancária
Para cada conta bancária que você deseja gerar as informações de pagamento positivo, é necessário atribuir o formato de pagamento positivo que foi especificado na seção anterior. Na página **Contas bancárias**, selecione o formato de pagamento positivo que corresponda à conta bancária. No campo **Data inicial do pagamento positivo**, insira a primeira data para gerar os arquivos de pagamento positivo. É importante que você insira uma data nesse campo. Caso contrário, o primeiro arquivo de pagamento positivo gerado incluirá todos os cheques já criados para essa conta bancária.

## <a name="assign-a-number-sequence-for-positive-pay-files"></a>Atribuir uma sequência numérica para arquivos de pagamento positivo
Cada arquivo de pagamento positivo deve ter um número exclusivo. Use a guia **Sequências numéricas** na página **Parâmetros de de gerenciamento de caixa e bancário** para criar uma sequência numérica para arquivos de pagamento positivo.

## <a name="generate-a-positive-pay-file-for-a-single-bank-account"></a>Gerar um arquivo de pagamento positivo para uma única conta bancária
Você pode gerar um arquivo de pagamento positivo para uma única entidade legal e uma única conta bancária. Para obter informações sobre como gerar arquivos de pagamento positivo para várias entidades legais e contas bancárias ao mesmo tempo, consulte a próxima seção. Para gerar um arquivo de pagamento positivo para uma única entidade legal e uma única conta bancária, abra a caixa de diálogo **Gerar um arquivo de pagamento positivo** na página **Contas bancárias**. No campo **Data de fechamento**, insira a data do último cheque a ser incluído no arquivo de pagamento positivo. Todos os cheques que não tiverem sido incluídos em um arquivo de pagamento positivo até o final dessa data de verificação serão incluídos no arquivo.

## <a name="generate-a-positive-pay-file-for-multiple-bank-accounts"></a>Gerar um arquivo de pagamento positivo para várias contas bancárias
Para gerar um arquivo de pagamento positivo para várias contas bancárias, use a tarefa periódica **Gerar um arquivo de pagamento positivo**. Selecione o formato de pagamento positivo para o arquivo e especifique se deseja gerar o arquivo de pagamento positivo para todas as entidades legais ou para uma entidade legal selecionada. Você também pode gerar o arquivo de pagamento positivo para todas as contas bancárias que usam o formato de pagamento positivo para uma conta bancária selecionada. No campo **Data de fechamento**, insira a data do último cheque a ser incluído no arquivo de pagamento positivo. Todos os cheques que não tiverem sido incluídos em um arquivo de pagamento positivo até o final dessa data de verificação serão incluídos no arquivo.

## <a name="view-the-results-of-positive-pay-file-generation"></a>Exibir os resultados de geração de um arquivo de pagamento positivo
Depois que o arquivo positivo de pagamento for gerado, você poderá exibir os resultados na página **Resumo do arquivo de pagamento positivo**. Para exibir os detalhes das verificações individuais, use a página de detalhes **Arquivo de pagamento positivo**.

## <a name="confirm-a-positive-pay-file"></a>Confirmar um arquivo de pagamento positivo
Depois que os cheques listados em um arquivo de pagamento positivo forem pagos, você receberá um número de confirmação do banco. Em seguida, será possível confirmar o arquivo de pagamento positivo.. Na página **Resumo do arquivo de pagamento positivo**, selecione um arquivo de pagamento positivo com o status **Criado** e selecione a ação **Inserir confirmação**. Quando você confirma um arquivo de pagamento positivo, o número de confirmação recebido do banco é registrado.

## <a name="recall-a-positive-pay-file"></a>Cancelar um arquivo de pagamento positivo
Se você tiver de alterar um arquivo de pagamento positivo, poderá cancelá-lo. Na página **Resumo do arquivo de pagamento positivo**, selecione um arquivo de pagamento positivo com o status **Criado** e selecione a ação **Cancelar**. Para cada cheque no arquivo de pagamento positivo, o campo que indica se esse cheque foi incluído em um arquivo de pagamento positivo será redefinido. Em seguida, você poderá criar um novo arquivo de pagamento positivo que inclua o cheque cancelado.



