---
title: "Solução de problemas de importação do arquivo de extrato bancário"
description: "É importante que o arquivo de extrato bancário do banco corresponda ao layout ao qual o Microsoft Dynamics 365 for Operations oferece suporte. Devido a padrões restritos de extratos bancários, a maioria das integrações funcionarão corretamente. No entanto, algumas vezes, o arquivo de extrato bancário não é importado ou apresenta resultados incorretos. Normalmente, esses problemas são causados por pequenas diferenças no arquivo de extrato bancário. Este artigo explica como corrigir essas diferenças e resolver os problemas."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 141273
ms.assetid: 3ee2f32b-02aa-420b-8990-e6aa5fc6bda3
ms.search.region: global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: e2029a03cf6b46ee206417076c64a269080119ed
ms.contentlocale: pt-br
ms.lasthandoff: 05/25/2017


---

# <a name="bank-statement-file-import-troubleshooting"></a>Solução de problemas de importação do arquivo de extrato bancário

[!include[banner](../includes/banner.md)]


É importante que o arquivo de extrato bancário do banco corresponda ao layout ao qual o Microsoft Dynamics 365 for Operations oferece suporte. Devido a padrões restritos de extratos bancários, a maioria das integrações funcionarão corretamente. No entanto, algumas vezes, o arquivo de extrato bancário não é importado ou apresenta resultados incorretos. Normalmente, esses problemas são causados por pequenas diferenças no arquivo de extrato bancário. Este artigo explica como corrigir essas diferenças e resolver os problemas.

<a name="what-is-the-error"></a>Qual é o erro?
------------------

Após tentar importar um arquivo de extrato bancário, acesse o histórico de trabalho de gerenciamento de dados e os detalhes da execução para localizar o erro. O erro pode ajudar indicando o extrato, o saldo ou a linha do extrato. Entretanto, é improvável que você receba informações suficientes para identificar o campo ou o elemento que está causando o problema.

## <a name="what-are-the-differences"></a>Quais são as diferenças?
Compare a definição de layout do arquivo bancário com a definição de importação do Microsoft Dynamics 365 for Operations e observe todas as diferenças nos campos e nos elementos. Compare o arquivo de extrato bancário ao arquivo de amostra relacionado do Dynamics 365 for Operations. Nos arquivos ISO20022, todas as diferenças devem ser fáceis de ver.

## <a name="transformations"></a>Transformações
Normalmente, a alteração deve ser feita em uma das três transformações. Cada transformação é gravada em um padrão específico.

| Nome do recurso                                         | Nome do arquivo                          |
|-------------------------------------------------------|------------------------------------|
| BankStmtImport\_BAI2CSV\_to\_BAI2XML\_xslt            | BAI2CSV-to-BAI2XML.xslt            |
| BankStmtImport\_ISO20022XML\_to\_Reconciliation\_xslt | ISO20022XML-to-Reconciliation.xslt |
| BankStmtImport\_MT940TXT\_to\_MT940XML\_xslt          | MT940TXT-to-MT940XML.xslt          |

## <a name="debugging-transformations"></a>Depurando transformações
### <a name="adjust-the-bai2-and-mt940-files"></a>Ajustar os arquivos BAI2 e MT940

Os arquivos BAI2 e MT940 são baseados em texto e requerem um ajuste para habilitar a depuração das transformações XSLT. O programa faz esse ajuste quando um arquivo é importado.

1.  Crie um arquivo XML e copie o texto a seguir nele.

        <Batch><![CDATA[PASTESTATEMENTFILEHERE
        ]]></Batch>

2.  Copie o conteúdo do arquivo de extrato bancário e cole-o no arquivo XML para que ele substitua **PASTESTATEMENTFILEHERE**.

### <a name="debug-the-xslt"></a>Depurar a XSLT

Para obter mais informações, consulte <https://msdn.microsoft.com/en-us/library/ms255605.aspx>.

1.  Inicie o Microsoft Visual Studio.
2.  Crie um aplicativo de console.
3.  Abra a XSLT apropriada.
4.  Clique na XLST e na respectiva página de propriedades.
5.  Defina a entrada para o local do arquivo de extrato bancário.
6.  Defina um local e um nome de arquivo como saída.
7.  Definia os pontos de quebra necessários.
8.  No menu, clique em **XML** &gt; **Iniciar Depuração XSLT**.

### <a name="format-the-xslt-output"></a>Formatar a saída XSLT

Quando a transformação é executada, ela cria um arquivo de saída que você pode exibir no Visual Studio. Use Ctrl+A, Ctrl+K e Ctrl+D para formatar rapidamente o arquivo de saída.

### <a name="adjust-the-transformation"></a>Ajustar a transformação

Ajuste a transformação para obter o campo ou elemento apropriado no arquivo de extrato bancário. Em seguida, mapeie esse campo ou elemento ao elemento apropriado do Dynamics 365 for Operations.

### <a name="debitcredit-indicator"></a>Indicador de débito/crédito

Às vezes, os débitos são importados como créditos, e os créditos são importados como débitos. Para resolver esse problema, você deve alterar a XSLT apropriada. Se os extratos bancários forem provenientes de vários bancos, verifique se todos usam a mesma abordagem de débito/crédito, ou crie transformações separadas.

-   Modelo BAI2XML-to-Reconciliation.xlst GetAmountCreditDebitIndicator
-   Modelo ISO20022XML-to-Reconcilation.xslt GetCreditDebit
-   Modelo MT940XML-to-Reconcilation.xslt GetCreditDebitIndicator

## <a name="examples-of-bank-statement-formats-and-technical-layouts"></a>Exemplos de formatos de extrato bancário e layouts técnicos
A tabela a seguir lista exemplos das definições de layout técnico de arquivos de importação avançada de reconciliação bancária e de três arquivos de exemplo de extrato bancário relacionados. Você pode baixar arquivos de exemplo e layouts técnicos aqui: https://mbs.microsoft.com/customersource/northamerica/AX/learning/documentation/how-to-articles/exofbankstfotechlayouts  


| Definição do layout técnico                             | Arquivo de exemplo de extrato bancário          |
|---------------------------------------------------------|--------------------------------------|
| DynamicsAXMT940Layout                                   | MT940StatementExample                |
| DynamicsAXISO20022Layout                                | ISO20022StatementExample             |
| DynamicsAXBAI2Layout                                    | BAI2StatementExample                 |






