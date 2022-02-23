---
title: Depurar fontes de dados de um formato de relatório eletrônico executado para analisar o fluxo de dados e a transformação
description: Este tópico explica como você pode depurar as fontes de dados de um formato de relatório executado para compreender melhor o fluxo de dados configurado e a transformação.
author: NickSelin
manager: AnnBe
ms.date: 04/22/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
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
ms.openlocfilehash: 3a486800f37dda7829aeeaa56a30285a92a61b9d
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4680773"
---
# <a name="debug-data-sources-of-an-executed-er-format-to-analyze-data-flow-and-transformation"></a>Depurar fontes de dados de um formato de relatório eletrônico executado para analisar o fluxo de dados e a transformação

[!include[banner](../includes/banner.md)]

[!include[banner](../includes/preview-banner.md)]

Ao [configurar](tasks/er-format-configuration-2016-11.md) uma solução do relatório eletrônico (ER) para gerar documentos de saída, você define os métodos usados para obter os dados do aplicativo e inseri-los na saída gerada. Para tornar o suporte ao ciclo de vida da solução de ER mais eficiente, a sua solução deve consistir em um [modelo de dados](general-electronic-reporting.md#DataModelComponent) de ER e seus componentes de [mapeamento](general-electronic-reporting.md#ModelMappingComponent), além de um [formato](general-electronic-reporting.md#FormatComponentOutbound) de ER e seus componentes de mapeamento, para que o mapeamento do modelo seja específico para o aplicativo, enquanto outros componentes permanecem independentes do aplicativo. Portanto, vários componentes do ER podem [afetar](general-electronic-reporting.md#FormatComponentOutbound) o processo de inserir dados na saída gerada.

Às vezes, os dados da saída gerada parecem diferentes dos mesmos dados no banco de dados do aplicativo. Nesses casos, será necessário determinar qual componente do ER é responsável pela transformação dos dados. O recurso do depurador da fonte de dados do ER reduz significativamente o tempo e o custo envolvidos nesta investigação. Você pode interromper a execução de um formato de ER e abrir a interface do depurador da fonte de dados. Nela, é possível procurar as fontes de dados disponíveis e selecionar uma fonte de dados individual para execução. Esta execução manual simula a execução da fonte de dados durante a execução real de um formato de ER. O resultado é apresentado em uma página na qual você pode analisar os dados recebidos.

Para ativar o recurso de depuração da fonte de dados, defina a opção **Habilitar depuração de dados na execução do formato** como **Sim** nos parâmetros de usuário do ER. Em seguida, você pode iniciar a depuração da fonte de dados enquanto executa o formato de ER para gerar documentos de saída. Você também pode usar a opção **Iniciar depuração** para iniciar a depuração da fonte de dados para um formato de ER configurado no [Designer da operação do ER](./tasks/er-format-configuration-2016-11.md#design-the-format-of-an-electronic-document).

Este tópico fornece diretrizes para iniciar a depuração da fonte de dados para formatos de ER executados. Ele explica como as informações podem ajudar você a entender o fluxo e as transformações de dados. Os exemplos neste tópico usam o processo de negócios para o processamento de pagamentos de fornecedores.

## <a name="limitations"></a>Limitações

O depurador da fonte de dados pode ser usado para acessar os dados de fontes de dados usadas em formatos de ER executados para gerar documentos de saída. Ele não pode ser usado para depurar fontes de dados de formatos de ER criadas para analisar documentos de entrada.

As seguintes configurações de formatos de ER não estão acessíveis no momento para a depuração da fonte de dados:

- Transformações de formatos
- Regras de validação de mapeamento e formato
- Habilitar expressões
- Detalhes da coleta de dados na memória

## <a name="prerequisites"></a>Pré-requisitos

- Para concluir os exemplos deste tópico, você deve ter acesso a uma das seguintes [funções](../sysadmin/tasks/assign-users-security-roles.md):

    - Desenvolvedor de relatório eletrônico
    - Consultor funcional de relatório eletrônico
    - Administrador do sistema

- A empresa deve ser definida como **DEMF**.

- Siga as etapas no [Apêndice 1](#appendix1) deste tópico para baixar os componentes da solução do Microsoft ER necessários para processar os pagamentos de fornecedores.
- Siga as etapas no [Apêndice 2](#appendix2) deste tópico para preparar o recurso Contas a pagar para o processamento de pagamentos de fornecedores usando a solução de ER que você obterá por download.

## <a name="process-a-vendor-payment-to-get-a-payment-file"></a>Processar um pagamento do fornecedor para obter um arquivo de pagamento

1. Siga as etapas no [Apêndice 3](#appendix3) deste tópico para processar os pagamentos de fornecedores.

    ![Processamento de pagamento do fornecedor em andamento](./media/er-data-debugger-process-payment.png)

2. Baixe e salve o arquivo zip no computador local.
3. Extraia o arquivo de pagamento **ISO20022 Credit transfer.xml** do arquivo zip.
4. Abra o arquivo de pagamento extraído usando o visualizador de arquivos XML.

    No arquivo de pagamento, o código do número da conta bancária internacional (IBAN) da conta bancária do fornecedor não contém espaços. Portanto, difere do valor [inserido](#enteredIBANcode) na página **Contas bancárias**.

    ![Código IBAN sem espaços](./media/er-data-debugger-payment-file.png)

    Você pode usar o depurador da fonte de dados do ER para saber qual componente da solução de ER é usado para truncar espaços no código IBAN.

## <a name="turn-on-data-source-debugging"></a>Ativar depuração da fonte de dados

1. Vá para **Administração da organização** \> **Relatório eletrônico** \> **Configurações**.
2. Na página **Configurações**, no Painel Ação, na guia **Configurações**, no grupo **Configurações avançadas**, selecione **Parâmetros de usuário**.
3. Defina a opção **Habilitar depuração de dados na execução do formato** como **Sim**.

    > [!NOTE]
    > Esse parâmetro é específico do usuário e da empresa.

    ![Caixa de diálogo de parâmetros do usuário](./media/er-data-debugger-user-parameters.png)

## <a name="process-a-vendor-payment-for-debugging"></a>Processar um pagamento de fornecedor para depuração

1. Siga as etapas no [Apêndice 3](#appendix3) deste tópico para processar os pagamentos de fornecedores.
2. Na caixa de mensagem, selecione **Sim** para confirmar que deseja interromper o processamento de pagamentos de fornecedores e iniciar a depuração da fonte de dados na página **Depurar fontes de dados**.

    ![Caixa de mensagem de confirmação](./media/er-data-debugger-start-debugging.png)

## <a name="debug-data-sources-that-are-used-in-payment-processing"></a>Depurar fontes de dados usadas no processamento de pagamentos

### <a name="debug-the-model-mapping"></a>Depurar o mapeamento de modelos

1. Na página **Depurar fontes de dados**, no Painel de Ações, selecione **Mapeamento de modelo** para iniciar a depuração deste componente de ER.
2. No painel da fonte de dados à esquerda, selecione a fonte de dados **\$notSentTransactions** e selecione **Ler todos os registros**.

    Você pode selecionar **Ler 1 registro**, **Ler 10 registros**, **Ler 100 registros** ou **Ler todos os registros** para forçar o número apropriado de registros a serem lidos na fonte de dados selecionada. Dessa forma, você pode simular o acesso à fonte de dados do formato de ER em execução.

3. No painel de dados à direita, selecione **Expandir tudo**.

    Você pode ver que a fonte de dados selecionada do tipo **Lista de registros** contém um único registro.

4. Expanda a fonte de dados **\$notSentTransactions** e selecione o método **vendBankAccountInTransactionCompany()** aninhado.
5. Expanda o método **vendBankAccountInTransactionCompany()** e selecione o campo **IBAN** aninhado.
6. Selecione **Obter valor**.

    Você pode selecionar **Obter valor** para forçar a leitura do valor de um campo selecionado da fonte de dados selecionada. Dessa forma, você pode simular o acesso a esse campo do formato de ER em execução.

7. Selecione **Expandir tudo**.

    ![Valor do campo IBAN no mapeamento de modelos](./media/er-data-debugger-debugging-model-mapping.png)

    Como pode ver, o mapeamento de modelos não é responsável pelos espaços truncados, pois o código IBAN retornado para a conta bancária do fornecedor inclui espaços. Portanto, é necessário continuar a depuração da fonte de dados.

### <a name="debug-the-format-mapping"></a>Depurar o mapeamento de formato

1. Na página **Depurar fontes de dados**, no Painel de Ações, selecione **Mapeamento de formato** para continuar a depuração deste componente de ER.
2. Selecione a fonte de dados **\$PaymentByDebtor** e selecione **Ler todos os registros**.
3. Expanda **\$PaymentByDebtor**.
4. Expanda **\$PaymentByDebtor.Lines** e selecione **Ler todos os registros**.
5. Expanda **\$PaymentByDebtor.Lines.CreditorAccount**.
6. Expanda **\$PaymentByDebtor.Lines.CreditorAccount.Identification** e selecione **\$PaymentByDebtor.Lines.CreditorAccount.Identification.IBAN**.
7. Selecione **Obter valor**.
8. Selecione **Expandir tudo**.

    ![Valor do campo IBAN no mapeamento de formato](./media/er-data-debugger-debugging-format-mapping.png)

    Como pode ver, as fontes de dados do mapeamento de formato não são responsáveis pelos espaços truncados, pois o código IBAN retornado para a conta bancária do fornecedor inclui espaços. Portanto, é necessário continuar a depuração da fonte de dados.

### <a name="debug-the-format"></a>Depurar o formato

1. Na página **Depurar fontes de dados**, no Painel de Ações, selecione **Formato** para continuar a depuração deste componente de ER.
2. Expanda os elementos de formato para selecionar **ISO20022CTReports** \> **XMLHeader** \> **Documento** \> **CstmrCdtTrfInitn** \> **PmtInf** e, em seguida, selecionar **Ler todos os registros**.
3. Expanda os elementos de formato para selecionar **ISO20022CTReports** \> **XMLHeader** \> **Documento** \> **CstmrCdtTrfInitn** \> **PmtInf** \> **CdtTrfTxInf** e, em seguida, selecionar **Ler todos os registros**.
4. Expanda os elementos de formato para selecionar **ISO20022CTReports** \> **XMLHeader** \> **Documento** \> **CstmrCdtTrfInitn** \> **PmtInf** \> **CdtTrfTxInf** \> **CdtrAcct** \> **Id** \> **IBAN** \> **BankIBAN** e, em seguida, selecionar **Obter valor**.
5. Selecione **Expandir tudo**.

    ![Valor do campo IBAN no formato](./media/er-data-debugger-debugging-format.png)

   Como pode ver, a associação de formato não é responsável pelos espaços truncados, pois o código IBAN retornado para a conta bancária do fornecedor inclui espaços. Portanto, o elemento **BankIBAN** está configurado para usar uma transformação de formato que trunca os espaços.

6. Feche o depurador da fonte de dados.

### <a name="review-the-format-transformations"></a>Revise as transformações de formato

1. Vá para **Administração da organização** \> **Relatório eletrônico** \> **Configurações**.
2. Na página **Configurações**, selecione **Modelo de pagamento** \> **Transferência de crédito ISO20022**.
3. Selecione **Designer** e expanda os elementos para selecionar **Documento** \> **CstmrCdtTrfInitn** \> **PmtInf** \> **CdtTrfTxInf** \> **CdtrAcct** \> **Id** \> **IBAN** \> **BankIBAN**.

    ![Elemento BankIBAN na página Designer de formato](./media/er-data-debugger-referred-transformation.png)

    Como pode ver, o elemento **BankIBAN** está configurado para usar a transformação **remover não alfanuméricos**.

4. Selecione a guia **Transformações**.

    ![Guia Transformações para o elemento BankIBAN](./media/er-data-debugger-transformation.png)

    Como pode ver, a transformação **remover não alfanumérico** está configurada para usar uma expressão que trunca os espaços da cadeia de texto fornecida.

## <a name="start-to-debug-in-the-operation-designer"></a>Iniciar depuração no Designer da operação

Ao configurar uma versão de rascunho do formato de ER que pode ser executado diretamente do Designer da operação, você pode acessar o depurador da fonte de dados selecionando **Iniciar Depuração** no Painel de Ações.

![Botão Iniciar Depuração na página do Designer de formato](./media/er-data-debugger-run-from-designer.png)

Os componentes do mapeamento de formato e do formato de ER que estão sendo editados estão disponíveis para depuração.

## <a name="start-to-debug-in-the-model-mapping-designer"></a>Iniciar depuração no Designer do mapeamento de modelos

Ao configurar um mapeamento de modelos de ER que pode ser executado diretamente da página **Mapeamento de modelos**, você pode acessar o depurador da fonte de dados selecionando **Iniciar Depuração** no Painel de Ações.

![Botão Iniciar Depuração na página do Designer do mapeamento de modelos](./media/er-data-debugger-run-from-designer-mapping.png)

O componente de mapeamento de modelos do mapeamento de ER que está sendo editado está disponível para depuração.

## <a name="appendix-1-get-an-er-solution"></a><a name="appendix1"></a>Apêndice 1: Obter uma solução de ER

### <a name="download-an-er-solution"></a>Baixar uma solução de ER

Se deseja usar uma solução de ER para gerar um arquivo de pagamento eletrônico para um pagamento de fornecedor que já foi processado, você pode [baixar](download-electronic-reporting-configuration-lcs.md) o formato de pagamento de ER **Transferência de crédito ISO20022** disponível na biblioteca de Ativos compartilhados no Microsoft Dynamics Lifecycle Services (LCS) ou no repositório Global.

![Importar o formato de pagamento de ER na página do Repositório de configuração](./media/er-data-debugger-import-from-repo.png)

Além do formato de ER selecionado, as [configurações](general-electronic-reporting.md#Configuration) a seguir devem ser importadas automaticamente para a instância do Microsoft Dynamics 365 Finance como parte da solução de ER **Transferência de crédito ISO20022**:

- [Configuração do modelo de dados de ER](general-electronic-reporting.md#DataModelComponent) do **Modelo de pagamento**
- [Configuração do formato de ER](general-electronic-reporting.md#FormatComponentOutbound) **Transferência de crédito ISO20022**
- [Configuração do mapeamento de modelos de ER](general-electronic-reporting.md#ModelMappingComponent) **Mapeamento de modelos de pagamento 1611**
- Configuração do mapeamento de modelos de ER **Mapeamento de modelos de pagamento para o destino ISO20022**

Você pode encontrar essas configurações na página **Configurações** da estrutura do ER (**Administração da organização** \> **Relatório eletrônico** \> **Configurações**).

![Configurações importadas na página Configurações](./media/er-data-debugger-configurations.png)

Se qualquer uma das configurações listadas estiver ausente na árvore de configuração, será necessário baixá-la manualmente da biblioteca de Ativos compartilhados do LCS, da mesma forma como baixou o formato de pagamento de ER **Transferência de crédito ISO20022**.

### <a name="analyze-the-downloaded-er-solution"></a>Analisar a solução de ER baixada

#### <a name="review-the-model-mapping"></a>Revisar o mapeamento de modelos

1. Vá para **Administração da organização** \> **Relatório eletrônico** \> **Configurações**.
2. Selecione **Modelo de pagamento** \> **Mapeamento de modelos de pagamento 1611**.
3. Selecione **Designer**.
4. Selecione o registro de mapeamento **Mapeamento de modelos de pagamento ISO20022 CT**.
5. Selecione **Designer** e revise o mapeamento de modelos aberto.

    Observe que o campo **Pagamentos** do modelo de dados está vinculado à fonte de dados **\$notSentTransactions** que retorna a lista de linhas de pagamento de fornecedores que estão sendo processadas.

    ![Campo Pagamentos na página do designer de mapeamento de modelos](./media/er-data-debugger-model-mapping.png)

#### <a name="review-the-format-mapping"></a>Revisar o mapeamento de formato

1. Vá para **Administração da organização** \> **Relatório eletrônico** \> **Configurações**.
2. Selecione **Modelo de pagamento** \> **Transferência de crédito ISO20022**.
3. Selecione **Designer**.
4. Na guia **Mapeamento**, revise o mapeamento de formato exibido.

    Observe que o elemento **Documento** \> **CstmrCdtTrfInitn** \> **PmtInf** do arquivo **ISO20022CTReports** \> **XMLHeader** está associado à fonte de dados **\$PaymentByDebtor** configurada para agrupar registros do campo **Pagamentos** do modelo de dados.

    ![Elemento PmtInf na página Designer de formato](./media/er-data-debugger-format-mapping.png)

#### <a name="review-the-format"></a>Revisar o formato

1. Vá para **Administração da organização** \> **Relatório eletrônico** \> **Configurações**.
2. Selecione **Modelo de pagamento** \> **Transferência de crédito ISO20022**.
3. Selecione **Designer** e revise o formato de modelos aberto.

    Observe que o elemento do formato em **Documento** \> **CstmrCdtTrfInitn** \> **PmtInf** \> **CdtTrfTxInf** \> **CdtrAcct** \> **Id** \> **IBAN** \> **BankIBAN** está configurado para inserir o código IBAN da conta do fornecedor no arquivo de pagamento.

    ![Elemento BankIBAN na página Designer de formato](./media/er-data-debugger-format.png)

## <a name="appendix-2-configure-accounts-payable"></a><a name="appendix2"></a>Apêndice 2: Configurar Contas a pagar

### <a name="modify-a-vendor-property"></a>Modificar uma propriedade do fornecedor

1. Acesse **Contas a pagar** \> **Fornecedores** \> **Todos os fornecedores**.
2. Selecione um fornecedor **DE-01002** e, no Painel de Ações, na guia **Fornecedor**, no grupo **Configurar**, selecione **Contas bancárias**.
3. Na FastTab **Identificação**, no campo **IBAN**, <a name="enteredIBANcode"></a>insira **GB33 BUKB 2020 1555 5555 55**.
4. Selecione **Salvar**.

![Campo IBAN definido na página de Contas bancárias do fornecedor](./media/er-data-debugger-iban.png)

### <a name="set-up-a-method-of-payment"></a>Configurar um meio de pagamento

1. Vá para **Contas a pagar** \> **Configuração de pagamento** \> **Métodos de pagamento**.
2. Selecione o método de pagamento **SEPA CT**.
3. Na FastTab **Formatos de arquivo**, na seção **Formatos de arquivo**, defina a opção **Formato de exportação eletrônico genérico** como **Sim**.
4. No campo **Exportar configuração de formato**, selecione o formato de ER **Transferência de crédito ISO20022**.
5. Selecione **Salvar**.

![Configurações de formato de arquivo na página Métodos de pagamento](./media/er-data-debugger-payment-method.png)

### <a name="add-a-vendor-payment"></a>Adicionar um pagamento de fornecedor

1. Vá para **Contas a pagar** \> **Pagamentos** \> **Diário de pagamentos do fornecedor**.
2. Adicione um novo diário de pagamento.
3. Selecione **Linhas** e adicione uma nova linha de pagamento.
4. No campo **Conta**, selecione o fornecedor **DE-01002**.
5. No campo **Débito**, insira um valor.
6. No campo **Método de pagamento**, selecione **SEPA CT**.
7. Selecione **Salvar**.

![Pagamento do fornecedor adicionado à página Pagamentos do fornecedor](./media/er-data-debugger-payment-journal.png)

## <a name="appendix-3-process-a-vendor-payment"></a><a name="appendix3"></a>Apêndice 3: Processar pagamento do fornecedor

1. Vá para **Contas a pagar** \> **Pagamentos** \> **Diário de pagamentos do fornecedor**.
2. Na página **Diário de pagamentos do fornecedor**, selecione o diário de pagamento criado anteriormente e, em seguida, selecione **Linhas**.
3. Selecione a linha de pagamento e, depois, **Status do pagamento** \> **Não**.
4. Selecione **Gerar pagamentos**.
5. No campo **Método de pagamento**, selecione **SEPA CT**.
6. No campo **Conta bancária**, selecione **DEMF OPER**.
7. Na caixa de diálogo **Gerar pagamentos**, selecione **OK**.
8. Na caixa de diálogo **Parâmetros de relatório eletrônico**, selecione **OK**.
