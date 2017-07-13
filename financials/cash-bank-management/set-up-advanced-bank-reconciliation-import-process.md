---
title: "Configurar o processo de importação de reconciliação bancária avançada"
description: "O recurso Reconciliação bancária avançada permite que você importe extratos bancários eletrônicos e os reconcilie automaticamente com as transações bancárias do Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition. Este artigo explica como configurar a funcionalidade de importação para seus extratos bancários."
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
ms.custom: 106853
ms.assetid: 45dae275-ea45-4c7e-b38f-89297c7b5352
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: a4d1c81386c0ef03391f3127fa51a6b09a5142b3
ms.contentlocale: pt-br
ms.lasthandoff: 06/13/2017


---

# <a name="set-up-the-advanced-bank-reconciliation-import-process"></a>Configurar o processo de importação de reconciliação bancária avançada

[!include[banner](../includes/banner.md)]


O recurso Reconciliação bancária avançada permite que você importe extratos bancários eletrônicos e os reconcilie automaticamente com as transações bancárias do Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition. Este artigo explica como configurar a funcionalidade de importação para seus extratos bancários. 

A configuração de importação de extrato bancário varia de acordo com o formato do seu extrato bancário eletrônico. O Finanças e Operações oferece suporte para três formatos prontos de extratos bancários: ISO20022, MT940 e BAI2.

## <a name="sample-files"></a>Arquivos de exemplo
Para todos os três formatos, você deve ter os arquivos que convertem o extrato bancário eletrônico do formato original para um formato que o Finanças e Operações pode usar. Você pode encontrar os arquivos de recurso necessários no nó **Recursos** no Application Explores dentro do Microsoft Visual Studio. Após localizar os arquivos, copie-os para um local único conhecido, para que você possa carregá-los mais facilmente durante o processo de configuração.

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
Abaixo estão exemplos das definições avançadas de layout técnico de arquivo de importação de reconciliação bancária e três arquivos de exemplo de extrato bancário relacionados: https://mbs.microsoft.com/customersource/northamerica/AX/learning/documentation/how-to-articles/exofbankstfotechlayouts  

| Definição do layout técnico                             | Arquivo de exemplo de extrato bancário          |
|---------------------------------------------------------|--------------------------------------|
| DynamicsAXMT940Layout                                   | MT940StatementExample                |
| DynamicsAXISO20022Layout                                | ISO20022StatementExample             |
| DynamicsAXBAI2Layout                                    | BAI2StatementExample                 |

 

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
10. Para a sequência número 1, clique em **Carregar arquivo** e, em seguida, selecione o arquivo **ISO20022XML-to-Reconciliation.xslt** salvo anteriormente. **Observação:** Os arquivos de transformação do Finanças e Operações são criados para o formato padrão. Devido aos bancos geralmente divergirem desse formato, será necessário atualizar o arquivo de transformação para mapeá-lo ao seu formato de extrato bancário. <!-- For details about the expected format for ISO20022, see [Dynamics AX ISO20022 Layout](./media/dynamicsaxiso20022layout1.xlsx).-->
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
12. Para a sequência número 2, clique em **Carregar arquivo** e, em seguida, selecione o arquivo **MT940XML-to-Reconciliation.xslt** salvo anteriormente. **Observação:** Os arquivos de transformação do Finanças e Operações são criados para o formato padrão. Devido aos bancos geralmente divergirem desse formato, será necessário atualizar o arquivo de transformação para mapeá-lo ao seu formato de extrato bancário. <!--- For details about the expected format for MT940, see [Dynamics AX MT940 Layout](./media/dynamicsaxmt940layout1.xlsx)-->
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
12. Para a sequência número 2, clique em **Carregar arquivo** e, em seguida, selecione o arquivo **BAI2XML-to-Reconciliation.xslt** salvo anteriormente. **Observação:** Os arquivos de transformação do Finanças e Operações são criados para o formato padrão. Devido aos bancos geralmente divergirem desse formato, será necessário atualizar o arquivo de transformação para mapeá-lo ao seu formato de extrato bancário. <!--- For details about the expected format for BAI2, see [Dynamics AX BAI2 Layout](./media/dynamicsaxbai2layout1.xlsx).-->
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




