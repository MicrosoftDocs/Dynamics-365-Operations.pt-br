---
title: Solução de problemas de importação do arquivo de extrato bancário
description: Este artigo explica como corrigir problemas causados por pequenas diferenças no arquivo de extrato bancário.
author: angelad116
ms.date: 03/29/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BankStatementFormat
audience: Application User
ms.reviewer: kfend
ms.custom: 141273
ms.assetid: 3ee2f32b-02aa-420b-8990-e6aa5fc6bda3
ms.search.region: global
ms.author: angelading
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 44658ea48b9f7dae76c34c5f3d8828c9e8c4ac32
ms.sourcegitcommit: 0b7a034e644f4d93fe55c7baca5a3f89dbe56898
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/14/2022
ms.locfileid: "9151750"
---
# <a name="bank-statement-file-import-troubleshooting"></a>Solução de problemas de importação do arquivo de extrato bancário

[!include [banner](../includes/banner.md)]

>[!NOTE]
>Essa funcionalidade será preterida em 2022 de setembro, os novos usuários devem usar a emissão de relatórios eletrônicos.

É importante que o arquivo de extrato bancário do banco corresponda ao layout ao qual o Microsoft Dynamics 365 Finance oferece suporte. Devido a padrões restritos de extratos bancários, a maioria das integrações funcionarão corretamente. No entanto, algumas vezes, o arquivo de extrato bancário não é importado ou apresenta resultados incorretos. Normalmente, esses problemas são causados por pequenas diferenças no arquivo de extrato bancário. Este artigo explica como corrigir essas diferenças e resolver os problemas.

## <a name="what-is-the-error"></a>Qual é o erro?

Após tentar importar um arquivo de extrato bancário, acesse o histórico de trabalho de gerenciamento de dados e os detalhes da execução para localizar o erro. O erro pode ajudar indicando o extrato, o saldo ou a linha do extrato. Entretanto, é improvável que você receba informações suficientes para identificar o campo ou o elemento que está causando o problema.

> [!NOTE]
> Os extratos bancários importados só podem se sobrepor por momento específico.  Por exemplo, se uma instrução termina à meia-noite de 1º de janeiro de 2021, a data de início da próxima instrução poderá ser à meia-noite de 1º de janeiro de 2021, meia-noite.

## <a name="what-are-the-differences"></a>Quais são as diferenças?
Compare a definição de layout do arquivo bancário com a definição de importação do Finance e observe todas as diferenças nos campos e nos elementos. Compare o arquivo de extrato bancário com o arquivo de exemplo relacionado do Finance. Nos arquivos ISO20022, todas as diferenças devem ser fáceis de ver.

## <a name="time-zone-differences-on-imported-bank-statements"></a>Diferenças de fuso horário em extratos bancários importados
Os valores de data/hora no arquivo de importação podem diferir dos valores de data/hora exibidos no aplicativo de finanças e operações. Para evitar essa discrepância, insira uma preferência de fuso horário na página **Configurar fontes de dados**. Para obter mais informações sobre como inserir uma preferência de fuso horário, consulte [Configurar o processo de importação de reconciliação bancária avançada](set-up-advanced-bank-reconciliation-import-process.md).

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

    ```xml
    <Batch><![CDATA[PASTESTATEMENTFILEHERE
        ]]></Batch>
    ```
    
2.  Copie o conteúdo do arquivo de extrato bancário e cole-o no arquivo XML para que ele substitua **PASTESTATEMENTFILEHERE**.

### <a name="debug-the-xslt"></a>Depurar a XSLT

Para obter mais informações, consulte <https://msdn.microsoft.com/library/ms255605.aspx>.

1.  Iniciar o Microsoft Visual Studio.
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

Ajuste a transformação para obter o campo ou elemento apropriado no arquivo de extrato bancário. Em seguida, mapeie esse campo ou elemento para o elemento apropriado do Finance.

### <a name="debitcredit-indicator"></a>Indicador de débito/crédito

Às vezes, os débitos são importados como créditos, e os créditos são importados como débitos. Para resolver esse problema, você deve alterar a XSLT apropriada. Se os extratos bancários forem provenientes de vários bancos, verifique se todos usam a mesma abordagem de débito/crédito, ou crie transformações separadas.

-   Modelo BAI2XML-to-Reconciliation.xlst GetAmountCreditDebitIndicator
-   Modelo ISO20022XML-to-Reconcilation.xslt GetCreditDebit
-   Modelo MT940XML-to-Reconcilation.xslt GetCreditDebitIndicator

## <a name="examples-of-bank-statement-formats-and-technical-layouts"></a>Exemplos de formatos de extrato bancário e layouts técnicos
A tabela a seguir lista exemplos das definições de layout técnico de arquivos de importação avançada de reconciliação bancária e de três arquivos de exemplo de extrato bancário relacionados. Você pode baixar arquivos de exemplo e layouts técnicos aqui: [Importar exemplos de arquivos](//download.microsoft.com/download/8/e/c/8ec8d2d0-eb8c-41fb-ad8c-f01a4d670a44/Dynamics365FinanceAdvancedBankStatementLayouts.xlsx)  

| Definição do layout técnico                             | Arquivo de exemplo de extrato bancário          |
|---------------------------------------------------------|--------------------------------------|
| DynamicsAXMT940Layout                                   | [MT940StatementExample](//download.microsoft.com/download/2/d/c/2dcc4e55-ddc8-4a74-b79c-250fae201c3c/mt940StatementExample.txt)                |
| DynamicsAXISO20022Layout                                | [ISO20022StatementExample](https://nam06.safelinks.protection.outlook.com/?url=https%3A%2F%2Fdownload.microsoft.com%2Fdownload%2F1%2F5%2F5%2F155d84ed-c250-48f3-b0b1-c5a431e7855b%2FISO20022-MultipleStatements.xml&data=04%7C01%7CRobert.Schlomann%40microsoft.com%7C30d0c233cb6546547d0a08d8f4965edc%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637528273956712775%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C1000&sdata=3VzvLZK%2BO8PjuI7XVdC6rD2j3nUJfteo7zFp%2B1s9BwM%3D&reserved=0)             |
| DynamicsAXBAI2Layout                                    | [BAI2StatementExample](//download.microsoft.com/download/1/1/6/11693f57-bfc1-4993-a274-5fb978be70fa/BAI2StatementExample.txt)                 |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]

