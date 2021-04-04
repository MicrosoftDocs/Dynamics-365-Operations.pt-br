---
title: Configurar o processo de importação de reconciliação bancária avançada
description: O recurso Reconciliação bancária avançada permite que você importe extratos bancários eletrônicos e os reconcilie automaticamente com as transações bancárias do Microsoft Dynamics 365 Finance. Este artigo explica como configurar a funcionalidade de importação para seus extratos bancários.
author: panolte
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankStatementFormat
audience: Application User
ms.reviewer: roschlom
ms.custom: 106853
ms.assetid: 45dae275-ea45-4c7e-b38f-89297c7b5352
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2ca0001adfb73ab178a50e4346922273f0812c92
ms.sourcegitcommit: 4835acc3edacf8277937723d3f85a7875bd8de83
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/11/2021
ms.locfileid: "5580932"
---
# <a name="set-up-the-advanced-bank-reconciliation-import-process"></a>Configurar o processo de importação de reconciliação bancária avançada

[!include [banner](../includes/banner.md)]

O recurso Reconciliação bancária avançada permite que você importe extratos bancários eletrônicos e os reconcilie automaticamente com as transações bancárias do Dynamics 365 Finance. Este artigo explica como configurar a funcionalidade de importação para seus extratos bancários. 

A configuração de importação de extrato bancário varia de acordo com o formato do seu extrato bancário eletrônico. O Finanças oferece suporte para três formatos prontos de extrato bancário: ISO20022, MT940 e BAI2.

## <a name="set-time-zone-preference"></a>Definir preferência de fuso horário
Quando você configura as definições de importação do extrato bancário, pode ser importante considerar o fuso horário dos dados de data/hora nos arquivos de extrato bancário que serão importados. O padrão é supor que qualquer valor de data e hora já esteja em UTC (Tempo Universal Coordenado) e, portanto, nenhuma conversão de fuso horário será aplicada na importação dos dados. 

Há uma opção disponível para especificar um fuso horário a ser usado para importação de dados. Essa opção está disponível no campo **Preferência de fuso horário** em cada página **Detalhes do formato de dados de origem** (Guia Rápida **Espaço de trabalho de gerenciamento de dados > Configurar fontes de dados > Selecionar um formato de dados > Configurações regionais**). Essa preferência de fuso horário que você informa será aplicada a todas as importações que usam esse formato de dados de origem. Você pode criar quantos formatos de fonte de dados forem necessários para importação de dados de vários fusos horários.  

Esse fuso horário pode não ser o mesmo que o do usuário ou da empresa. Portanto, certifique-se de esclarecer qual fuso horário os dados de data e hora estão usado. É recomendável considerar os pontos a seguir ao configurar uma preferência de fuso horário. 

 - A preferência de fuso horário será aplicada a todas as importações usando esse formato de dados de origem. Você pode criar quantos formatos de fonte de dados forem necessários para tratar da importação de dados de vários fusos horários. 
 
 - A preferência de fuso horário deve ser o fuso horário local dos dados de data e hora no arquivo de importação. 
 
 - O fuso horário dos dados de data e hora pode não ser o mesmo que o do usuário ou da empresa.
 
 - Os usuários podem ajustar seu próprio fuso horário usando as **Opções do usuário**.

Observe que as ações a seguir podem ajudar a minimizar os possíveis conflitos de data e hora na importação de extratos bancários. 

 - Evite alterar as preferência de fuso horário para qualquer conta bancária que já teve extratos importados. Alterar as preferências de fuso horário pode afetar a ordenação de novos extratos relativos a extratos existentes devido ao ajuste do fuso horário. 
 
 - Revise todas as importações que usam o formato de fonte de dados selecionado. A preferência de fuso horário especificada para o formato será aplicada a todos os projetos de importação que usam esse formato. Verifique se a preferência de fuso horário é adequada para todos os projetos de importação que usam esse formato.

## <a name="sample-files"></a>Arquivos de exemplo
Para os três formatos, você deve ter os arquivos que convertem o extrato bancário eletrônico do formato original em um formato que possa ser usado pelo Finance. Você pode encontrar os arquivos de recurso necessários no nó **Recursos** no Application Explores dentro do Microsoft Visual Studio. Após localizar os arquivos, copie-os para um local único conhecido, para que você possa carregá-los mais facilmente durante o processo de configuração.

| Nome do recurso                                           | Nome do arquivo                            |
|---------------------------------------------------------|--------------------------------------|
| BankStmtImport\_BAI2CSV\_to\_BAI2XML\_xslt              | BAI2CSV-to-BAI2XML.xslt              |
| BankStmtImport\_BAI2XML\_to\_Reconciliation\_xslt       | BAI2XML-to-Reconciliation.xslt       |
| BankStmtImport\_BankReconciliation\_to\_Composite\_xslt | BankReconciliation-to-Composite.xslt |
| BankStmtImport\_ISO20022XML\_to\_Reconciliation\_xslt   | ISO20022XML-to-Reconciliation.xslt   |
| BankStmtImport\_MT940TXT\_to\_MT940XML\_xslt            | MT940TXT-to-MT940XML.xslt            |
| BankStmtImport\_MT940XML\_to\_Reconciliation\_xslt      | MT940XML-to-Reconciliation.xslt      |
| BankStmtImport\_SampleBankCompositeEntity\_xml          | SampleBankCompositeEntity.xml        |

## <a name="examples-of-bank-statement-formats-and-technical-layouts"></a>Exemplos de formatos de extrato bancário e layouts técnicos
Estes são exemplos das definições avançadas de layout técnico do arquivo de importação de reconciliação bancária e três arquivos de exemplo de extrato bancário relacionados: [Exemplos de arquivo de importação](//download.microsoft.com/download/8/e/c/8ec8d2d0-eb8c-41fb-ad8c-f01a4d670a44/Dynamics365FinanceAdvancedBankStatementLayouts.xlsx)  

| Definição do layout técnico                             | Arquivo de exemplo de extrato bancário          |
|---------------------------------------------------------|--------------------------------------|
| DynamicsAXMT940Layout                                   | [MT940StatementExample](//download.microsoft.com/download/2/d/c/2dcc4e55-ddc8-4a74-b79c-250fae201c3c/mt940StatementExample.txt)                |
| DynamicsAXISO20022Layout                                | [ISO20022StatementExample](https://dmsstager3tx7y9x22.blob.core.windows.net/155d84ed-c250-48f3-b0b1-c5a431e7855b/iso20022-multiplestatements.xml?sv=2019-02-02&sr=b&sig=1bDx0f9SONFouCcwLNPhmFHNdxDOkaibNf5%2Btoj0f0A%3D&se=2021-03-11T01%3A05%3A41Z&sp=r)             |
| DynamicsAXBAI2Layout                                    | [BAI2StatementExample](//download.microsoft.com/download/1/1/6/11693f57-bfc1-4993-a274-5fb978be70fa/BAI2StatementExample.txt)                 |



## <a name="set-up-the-import-of-iso20022-bank-statements"></a>Configurar a importação de extratos bancários ISO20022
Primeiro, você deve definir o grupo de processamento de formato do extrato bancário para extratos bancários ISO20022 utilizando a estrutura de entidade de dados.

1.  Vá para **Espaços de trabalho** &gt; **Gerenciamento de dados**.
2.  Clique em **Importar**.
3.  Insira um nome para o formato, como **ISO20022**.
4.  Defina o campo **Formato do dado fonte** para **XML-Element**.
5.  Defina o campo **Nome da entidade** para **Extratos bancários**.
6.  Para carregar os arquivos de importação, clique em **Carregar** e, em seguida, navegue para selecionar o arquivo **SampleBankCompositeEntity.xml** salvo anteriormente.
7.  Assim que a entidade Extratos bancários for carregada e o mapeamento finalizado, clique na ação **Exibir mapa** para a entidade.
8.  A entidade Extratos bancários é uma entidade composta formada por quatro entidades separadas. Na lista, selecione **BankStatementDocumentEntity** e, em seguida, clique na ação **Exibir mapa**.
9.  Na guia **Transformações**, clique em **Novo**.
10. Para a sequência número 1, clique em **Carregar arquivo** e, em seguida, selecione o arquivo **ISO20022XML-to-Reconciliation.xslt** salvo anteriormente. **Observação:** Os arquivos de transformação são criados para o formato padrão. Devido aos bancos geralmente divergirem desse formato, será necessário atualizar o arquivo de transformação para mapeá-lo ao seu formato de extrato bancário. <!-- For details about the expected format for ISO20022, see [Dynamics AX ISO20022 Layout](./media/dynamicsaxiso20022layout1.xlsx).-->
11. Clique em **Novo**.
12. Para a sequência número 2, clique em **Carregar arquivo** e, em seguida, selecione o arquivo **BankReconciliation-to-Composite.xslt** salvo anteriormente.
13. Clique em **Aplicar transformações**.

Assim que o grupo de processamento do formato for configurado, a próxima etapa é definir as regras de formato do extrato bancário para extratos bancários ISO20022.

1.  Vá para **Gerenciamento de banco e caixa** &gt; **Configuração** &gt; **Configuração avançada de reconciliação bancária** &gt; **Formato do extrato bancário**.
2.  Clique em **Novo**.
3.  Especifique um formato de extrato, tal como **ISO20022**.
4.  Digite um nome para o formato.
5.  Defina o campo **Grupo de processamento** como o grupo definido anteriormente, tal como **ISO20022**.
6.  Marque a caixa de seleção **Arquivo XML**.

A última etapa é habilitar a Reconciliação bancária avançada e definir o formato do extrato na conta bancária.

1.  Vá para **Gerenciamento de caixa e bancos** &gt; **Contas bancárias**.
2.  Selecione a conta bancária, e abra-a para exibir os detalhes.
3.  Na guia **Reconciliação**, defina a opção **Reconciliação bancária avançada** para **Sim**.
4.  Defina o campo **Formato do extrato** como o formato criado anteriormente, tal como **ISO20022**.

## <a name="set-up-the-import-of-mt940-bank-statements"></a>Configurar a importação de extratos bancários MT940
Primeiro, você deve definir o grupo de processamento de formato do extrato bancário para extratos bancários MT940 utilizando a estrutura de entidade de dados.

1.  Vá para **Espaços de trabalho** &gt; **Gerenciamento de dados**.
2.  Clique em **Importar**.
3.  Insira um nome para o formato, como **MT940**.
4.  Defina o campo **Formato do dado fonte** para **XML-Element**.
5.  Defina o campo **Nome da entidade** para **Extratos bancários**.
6.  Para carregar os arquivos de importação, clique em **Carregar** e, em seguida, navegue para selecionar o arquivo **SampleBankCompositeEntity.xml** salvo anteriormente.
7.  Assim que a entidade Extratos bancários for carregada e o mapeamento finalizado, clique na ação **Exibir mapa** para a entidade.
8.  A entidade Extratos bancários é uma entidade composta formada por quatro entidades separadas. Na lista, selecione **BankStatementDocumentEntity** e, em seguida, clique na ação **Exibir mapa**.
9.  Na guia **Transformações**, clique em **Novo**.
10. Para a sequência número 1, clique em **Carregar arquivo** e, em seguida, selecione o arquivo **MT940TXT-to-MT940XML.xslt** salvo anteriormente.
11. Clique em **Novo**.
12. Para a sequência número 2, clique em **Carregar arquivo** e, em seguida, selecione o arquivo **MT940XML-to-Reconciliation.xslt** salvo anteriormente. **Observação:** Os arquivos de transformação são criados para o formato padrão. Devido aos bancos geralmente divergirem desse formato, será necessário atualizar o arquivo de transformação para mapeá-lo ao seu formato de extrato bancário. <!--- For details about the expected format for MT940, see [Dynamics AX MT940 Layout](./media/dynamicsaxmt940layout1.xlsx)-->
13. Clique em **Novo**.
14. Para a sequência número 3, clique em **Carregar arquivo** e, em seguida, selecione o arquivo **BankReconciliation-to-Composite.xslt** salvo anteriormente.
15. Clique em **Aplicar transformações**.

Assim que o grupo de processamento do formato for configurado, a próxima etapa é definir as regras de formato do extrato bancário para extratos bancários MT940.

1.  Vá para **Gerenciamento de banco e caixa** &gt; **Configuração** &gt; **Configuração avançada de reconciliação bancária** &gt; **Formato do extrato bancário**.
2.  Clique em **Novo**.
3.  Especifique um formato de extrato, tal como **MT940**.
4.  Digite um nome para o formato.
5.  Defina o campo **Grupo de processamento** como o grupo definido anteriormente, tal como **MT940**.
6.  Defina o campo **Tipo de arquivo** como **txt**.

A última etapa é habilitar a Reconciliação bancária avançada e definir o formato do extrato na conta bancária.

1.  Vá para **Gerenciamento de caixa e bancos** &gt; **Contas bancárias**.
2.  Selecione a conta bancária, e abra-a para exibir os detalhes.
3.  Na guia **Reconciliação**, defina a opção **Reconciliação bancária avançada** para **Sim**.
4.  Quando for solicitada a confirmação e permissão para habilitar a Reconciliação bancária avançada, clique em **OK**.
5.  Defina o campo **Formato do extrato** como o formato criado anteriormente, tal como **MT940**.

## <a name="set-up-the-import-of-bai2-bank-statements"></a>Configurar a importação de extratos bancários BAI2
Primeiro, você deve definir o grupo de processamento de formato do extrato bancário para extratos bancários BAI2 utilizando a estrutura de entidade de dados.

1.  Vá para **Espaços de trabalho** &gt; **Gerenciamento de dados**.
2.  Clique **Importar**.
3.  Insira um nome para o formato, como **BAI2**.
4.  Defina o campo **Formato do dado fonte** para **XML-Element**.
5.  Defina o campo **Nome da entidade** para **Extratos bancários**.
6.  Para carregar os arquivos de importação, clique em **Carregar** e, em seguida, navegue para selecionar o arquivo **SampleBankCompositeEntity.xml** salvo anteriormente.
7.  Assim que a entidade Extratos bancários for carregada e o mapeamento finalizado, clique na ação **Exibir mapa** para a entidade.
8.  A entidade Extratos bancários é uma entidade composta formada por quatro entidades separadas. Na lista, selecione **BankStatementDocumentEntity** e, em seguida, clique na ação **Exibir mapa**.
9.  Na guia **Transformações**, clique em **Novo**.
10. Para a sequência número 1, clique em **Carregar arquivo** e, em seguida, selecione o arquivo **BAI2CSV-to-BAI2XML.xslt** salvo anteriormente.
11. Clique em **Novo**.
12. Para a sequência número 2, clique em **Carregar arquivo** e, em seguida, selecione o arquivo **BAI2XML-to-Reconciliation.xslt** salvo anteriormente. **Observação:** Os arquivos de transformação são criados para o formato padrão. Devido aos bancos geralmente divergirem desse formato, será necessário atualizar o arquivo de transformação para mapeá-lo ao seu formato de extrato bancário. <!--- For details about the expected format for BAI2, see [Dynamics AX BAI2 Layout](./media/dynamicsaxbai2layout1.xlsx).-->
13. Clique em **Novo**.
14. Para a sequência número 3, clique em **Carregar arquivo** e, em seguida, selecione o arquivo **BankReconciliation-to-Composite.xslt** salvo anteriormente.
15. Clique em **Aplicar transformações**.

Assim que o grupo de processamento do formato for configurado, a próxima etapa é definir as regras de formato do extrato bancário para extratos bancários BAI2.

1.  Vá para **Gerenciamento de banco e caixa** &gt; **Configuração** &gt; **Configuração avançada de reconciliação bancária** &gt; **Formato do extrato bancário**.
2.  Clique em **Novo**.
3.  Especifique um formato de extrato, tal como **BAI2**.
4.  Digite um nome para o formato.
5.  Defina o campo **Grupo de processamento** como o grupo definido anteriormente, tal como **BAI2**.
6.  Defina o campo **Tipo de arquivo** como **txt**.

A última etapa é habilitar a Reconciliação bancária avançada e definir o formato do extrato na conta bancária.

1.  Vá para **Gerenciamento de caixa e bancos** &gt; **Contas bancárias**.
2.  Selecione a conta bancária, e abra-a para exibir os detalhes.
3.  Na guia **Reconciliação**, defina a opção **Reconciliação bancária avançada** para **Sim**.
4.  Quando for solicitada a confirmação e permissão para habilitar a Reconciliação bancária avançada, clique em **OK**.
5.  Defina o campo **Formato do extrato** como o formato criado anteriormente, tal como **BAI2**.

## <a name="test-the-bank-statement-import"></a>Testar o arquivo de importação de extrato bancário
A etapa final é testar se é possível importar seu extrato bancário.

1.  Vá para **Gerenciamento de caixa e bancos** &gt; **Contas bancárias**.
2.  Selecione a conta bancária para a qual a funcionalidade Reconciliação bancária avançada está ativada.
3.  Na guia **Reconciliar**, clique em **Extratos bancários**.
4.  Na página **Extrato bancário**, clique em **Importar extrato**.
5.  Defina o campo **Conta bancária** para a conta bancária selecionada. O campo **Formato do extrato** será definido automaticamente, com base na configuração da conta bancária.
6.  Clique em **Procurar**, e selecione o arquivo de extrato bancário eletrônico.
7.  Clique em **Carregar**.
8.  Clique em **OK**.

Se a importação for bem-sucedida, você receberá uma mensagem informando que seu extrato foi importado. Se a importação não foi bem-sucedida, no espaço de trabalho **Gerenciamento de dados**, na seção **Histórico de trabalho**, localize o trabalho. Clique em **Detalhes de execução** para que o trabalho abra a página **Resumo de execução** e, em seguida, clique em **Exibir histórico de execução** para exibir os erros de importação.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
