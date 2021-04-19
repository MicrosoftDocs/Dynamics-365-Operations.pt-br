---
title: Melhorar o desempenho de soluções ER adicionando fontes de dados de CAMPOS CALCULADOS parametrizados
description: Este tópico explica como você pode melhorar o desempenho das soluções de relatório eletrônico (ER) adicionando fontes de dados de CAMPO CALCULADO parametrizado.
author: NickSelin
ms.date: 09/02/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 299570d6a94b0f9e7ee7cf490d4c1aeeb86d5716
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5749504"
---
# <a name="improve-the-performance-of-er-solutions-by-adding-parameterized-calculated-field-data-sources"></a>Melhorar o desempenho de soluções ER adicionando fontes de dados de CAMPOS CALCULADOS parametrizados

[!include [banner](../includes/banner.md)]

Este tópico explica como você pode usar [rastreamentos de desempenho](trace-execution-er-troubleshoot-perf.md) de formatos de [relatório eletrônico (ER)](general-electronic-reporting.md) que são executados e, em seguida, usar as informações desses rastreamentos para ajudar a melhorar o desempenho, configurando uma fonte de dados de **Campo calculado** parametrizado.

Como parte do processo de designar configurações ER para gerar documentos comerciais, você define o método usado para recuperar dados do aplicativo e inseri-los na saída gerada. Ao criar uma fonte de dados ER do tipo **Campo calculado** parametrizado, você pode reduzir o número de chamadas de banco do dados e reduzir bastante o tempo e o custo envolvidos na coleta dos detalhes da execução de formato ER.

## <a name="prerequisites"></a>Pré-requisitos

- Para concluir os exemplos deste tópico, você deve ter acesso a uma das seguintes [funções](../sysadmin/tasks/assign-users-security-roles.md):

    - Desenvolvedor de relatório eletrônico
    - Consultor funcional de relatório eletrônico
    - Administrador do sistema

- A empresa deve ser definida como **DEMF**.
- Siga as etapas no [Apêndice 1](#appendix1) deste tópico para baixar os componentes da solução de exemplo do Microsoft ER necessários para concluir os exemplos deste tópico.
- Siga as etapas no [Apêndice 2](#appendix2) deste tópico para configurar o conjunto mínimo de parâmetros ER necessários para usar a estrutura ER para ajudar a melhorar o desempenho da solução ER de exemplo da Microsoft.

## <a name="import-the-sample-er-solution"></a>Importar a solução ER de exemplo

Imagine que você precise criar uma solução ER para gerar um novo relatório que mostre transações de fornecedor. Atualmente, você pode encontrar as transações de um fornecedor selecionado na página **Transações do fornecedor** (acesse **Conta a pagar** \> **Fornecedores** \> **Todos os fornecedores**, selecione um fornecedor e, no Painel de Ações, na guia **Fornecedor**, no grupo **Transações**, selecione **Transações**). Contudo, você deseja ter todas as transações do fornecedor juntas em um documento eletrônico no formato XML. Essa solução consistirá em várias configurações de ER que contêm os modelos de dados, mapeamento de modelo e componentes de formato necessários.

A primeira etapa é importar a solução ER de exemplo para gerar um relatório de transações de fornecedor.

1. Entre na instância do Microsoft Dynamics 365 Finance que foi provisionada para sua empresa.
2. Neste tópico, você criará e modificará configurações para a empresa de exemplo **Litware, Inc.**. Verifique se esse provedor de configuração foi adicionado à instância do Finance e marcado como ativo. Para obter mais informações, consulte [Criar provedores de configuração e marcá-los como ativos](tasks/er-configuration-provider-mark-it-active-2016-11.md).
3. No espaço de trabalho **Relatório eletrônico**, selecione o bloco **Configurações de relatórios**.
4. Na página **Configurações**, importe as configurações ER que você baixou como um pré-requisito para o Finance, na seguinte ordem: modelo de dados, mapeamento de modelo, formato. Para cada configuração, siga estas etapas:

    1. No Painel de Ação, selecione **Câmbio** \> **Carregar de arquivo XML**.
    2. Selecione **Procurar** e o arquivo apropriado para a configuração ER no formato XML.
    3. Selecione **OK**.

![Configurações importadas na página Configurações](./media/er-calculated-field-ds-performance-imported-configurations.png)

## <a name="review-the-sample-er-solution"></a>Revisar a solução ER de exemplo

### <a name="review-the-model-mapping"></a>Revisar o mapeamento de modelos

1. Na página **Configurações**, na árvore de configurações, expanda **Modelo de aperfeiçoamento de desempenho** e selecione **Mapeamento de aperfeiçoamento de desempenho**.
2. No Painel de Ação, selecione **Designer**.
3. Na página **Modelo para mapeamento de fonte de dados**, no Painel de Ações, selecione **Designer**.

    Esse mapeamento de modelo de ER foi criado para executar as seguintes ações:

    - Obtenha a lista de transações de fornecedor armazenadas na tabela VendTrans (fonte de dados **Trans**).
    - Para cada transação, na tabela Vendtable, obtenha o registro de um fornecedor para o qual a transação foi lançada para (fonte de dados **\#Vend**).

    > [!NOTE]
    > A fonte de dados **\#Vend** é configurada para obter o registro de fornecedor correspondente usando a relação de vários para um existente **\@.'\>Relations'.VendTable\_AccountNum**.

    O mapeamento do modelo nesta configuração implementa o modelo de dados de base para qualquer formato de ER criado para esse modelo e executado no Finance. Portanto, o conteúdo da fonte de dados **Trans** é exposto para formatos de ER, como fontes de dados **modelo**.

    ![Fonte de dados Trans na página Designer de mapeamento do modelo](media/er-calculated-field-ds-performance-mapping-1.png)

4. Feche a página **Designer de mapeamento de modelo**.
5. Feche a página **Modelo para mapeamento de fonte de dados**.

### <a name="review-format"></a>Revisar o formato

1. Na página **Configurações**, na árvore de configurações, expanda **Modelo de aperfeiçoamento de desempenho** e selecione **Formato de aperfeiçoamento de desempenho**.
2. No Painel de Ação, selecione **Designer**.
3. Na página **Designer de formato**, na a guia **Mapeamento**, selecione **Expandir/Recolher**.
4. Expanda os itens **Modelo**, **Dados** e **Transação**.

    Este formato ER foi projetado para gerar um relatório de transações de fornecedor no formato XML.

    ![Formatar fontes de dados e associações configuradas de elementos de formato na página Designer de formato](media/er-calculated-field-ds-performance-format.png)

5. Feche a página **Designer de formato**.

## <a name="run-the-sample-er-solution-to-trace-execution"></a>Executar a solução de ER de exemplo para rastrear a execução

Imagine que você tenha terminado de criar a primeira versão da solução de ER. Agora você deseja testar a solução em sua instância do Finance e analisar o desempenho da execução.

### <a name="turn-on-the-er-performance-trace"></a>Ativar o rastreamento de desempenho de ER

1. Selecione a empresa **DEMF**.
2. Siga as etapas em [Ativar o rastreamento de desempenho ER](trace-execution-er-troubleshoot-perf.md#turn-on-the-er-performance-trace) para gerar um rastreamento de desempenho enquanto um formato ER é executado.

    ![Caixa de diálogo de parâmetros do usuário](media/er-calculated-field-ds-performance-format-user-parameters.png)

### <a name="run-the-er-format"></a><a id="run-format"></a>Executar o formato de ER

1. Vá para **Administração da organização** \> **Relatório eletrônico** \> **Configurações**.
2. Na página **Configurações**, na árvore de configuração, selecione **Formato de aperfeiçoamento de desempenho**.
3. No Painel de Ação, selecione **Executar**.

## <a name="use-the-performance-trace-to-analyze-model-mapping-performance"></a>Use o rastreamento de desempenho para analisar o desempenho do mapeamento do modelo

1. Na página **Configurações**, na árvore de configuração, selecione **Mapeamento de aperfeiçoamento de desempenho**.
2. No Painel de Ação, selecione **Designer**.
3. Na página **Mapeamentos de modelo**, no Painel de Ações, selecione **Designer**.
4. Na página **Designer de mapeamento de modelo**, no Painel de Ação, selecione **Rastreamento de desempenho**.
5. Selecione o rastreamento mais recente que foi gerado e selecione **OK**.

Novas informações estão disponíveis para alguns itens da fonte de dados do mapeamento do modelo atual:

- O tempo real gasto ao obter dados usando a fonte de dados
- O mesmo tempo expresso como uma porcentagem do tempo total gasto na execução do mapeamento do modelo inteiro

![Detalhes do tempo de execução na página Designer de mapeamento de modelo](./media/er-calculated-field-ds-performance-mapping-2.png)

A grade **Estatísticas de desempenho** mostra que a fonte de dados **Trans** chama a tabela VendTrans uma vez. O valor **\[265\]\[Q:265\]** da fonte de dados **Trans** indica que 265 transações do fornecedor foram obtidas na tabela do aplicativo e devolvidas ao modelo de dados.

A grade **Estatísticas de desempenho** também mostra que o mapeamento do modelo atual duplica as solicitações de banco de dados enquanto a fonte de dados **\#Vend** é executada. Essa duplicação ocorre pelos seguintes motivos:

- A tabela de fornecedores é chamada duas vezes para cada uma das 265 transações do fornecedor iterado, para um total de 530 chamadas:

    - Uma chamada é feita para inserir o número da conta do fornecedor.
    - Uma chamada é feita para inserir o nome do fornecedor.

- A tabela de fornecedores é chamada para cada transação de fornecedor iterada, mesmo que as transações obtidas tenham sido lançadas somente para cinco fornecedores. Das 530 chamadas, 525 são duplicatas. A ilustração a seguir mostra a mensagem recebida sobre chamadas duplicadas (solicitações de banco de dados).

![Mensagem sobre solicitações de banco de dados duplicadas na página Designer de mapeamento de modelo](./media/er-calculated-field-ds-performance-mapping-2a.png)

Do tempo de execução do mapeamento total do modelo (cerca de oito segundos), observe que mais de 80% (cerca de seis segundos) foi gasto na recuperação de valores da tabela do aplicativo VendTable. Essa porcentagem é muito grande para dois atributos de cinco fornecedores, em comparação com o volume de informações da tabela do aplicativo VendTrans.

Para reduzir o número de chamadas feitas para obter os detalhes do fornecedor para cada transação e melhorar o desempenho do mapeamento do modelo, você pode usar o armazenamento em cache para a fonte de dados **\#Vend**.

> [!NOTE]
> A fonte de dados **Trans\\\#Vend** será armazenada em cache no escopo da transação atual da fonte de dados da Trans **Trans** no tempo de execução.

Ao armazenar em cache a fonte de dados **\#Vend**, você reduz o número de chamadas duplicadas de 525 para 260, mas não elimina totalmente a duplicação. Para eliminar totalmente a duplicação, você pode configurar uma nova fonte de dados parametrizada do tipo **Campo calculado**.

## <a name="improve-the-model-mapping-based-on-information-from-the-execution-trace"></a>Melhorar o mapeamento do modelo com base nas informações do rastreamento de execução

### <a name="change-the-logic-of-the-model-mapping"></a>Alterar a lógica do mapeamento do modelo

Siga estas etapas para usar o cache e uma fonte de dados do tipo **Campo calculado** para ajudar a evitar chamadas duplicadas para o banco de dados.

1. Na página **Configurações**, na árvore de configuração, selecione **Mapeamento de aperfeiçoamento de desempenho**.
2. No Painel de Ação, selecione **Designer**.
3. Na página **Mapeamentos de modelo**, no Painel de Ações, selecione **Designer**.
4. Na página **Designer de mapeamento de modelo**, siga estas etapas para adicionar uma fonte de dados do tipo **Registros de tabela** para acessar registros na tabela do aplicativo VendTable:

    1. No painel **Tipos de fonte de dados**, expanda **Dynamics 365 for Operations** e selecione **Registros de tabela**.
    2. Selecione **Adicionar raiz**.
    3. Na caixa de diálogo, no campo **Nome** , digite **Vend**.
    4. No campo **Tabela**, insira **VendTable**.
    5. Selecione **OK**.

5. Você só poderá parametrizar chamadas para as fontes de dados do tipo **Campo calculado** se essas fontes de dados residirem em um contêiner. Portanto, siga estas etapas para adicionar uma fonte de dados do tipo **Contêiner vazio** para conter uma nova fonte de dados parametrizada do tipo **Campo calculado**:

    1. No painel **Tipos de fonte de dados**, expanda **Geral** e selecione **Contêiner vazio**.
    2. Selecione **Adicionar raiz**.
    3. Na caixa de diálogo, no campo **Nome** , digite **Box**.
    3. Selecione **OK**.

    ![Fonte de dados Box na página Designer de mapeamento do modelo](./media/er-calculated-field-ds-performance-mapping-3.png)

6. Siga estas etapas para adicionar uma fonte de dados parametrizada do tipo **Campo calculado**:

    1. No painel **Fontes de dados**, selecione **Box**.
    2. No painel **Tipos de fontes de dados**, expanda **Funções** e selecione **Campo calculado**.
    3. Selecione **Adicionar**.
    4. Na caixa de diálogo, no campo **Nome** , digite **Vend**.
    5. Selecione **Editar fórmula**.
    6. Na página **Designer de fórmulas**, selecione **Parâmetros** para especificar os parâmetros que devem ser fornecidos quando essa fonte de dados é chamada.
    7. Na caixa de diálogo **Parâmetros**, selecione **Novo**.
    8. No campo **Nome**, insira **parmVendAccNumber**.
    9. No campo **Tipo**, selecione **Cadeia de caracteres**.
    10. Selecione **OK**.
    11. No campo **Fórmula**, insira **FIRSTORNULL(FILTER(Vend, Vend.AccountNum=parmVendAccNumber))**.
    12. Selecione **Salvar** e feche a página **Designer de fórmulas**.
    13. Selecione **OK** para adicionar a nova fonte de dados.

7. Siga estas etapas para marcar a fonte de dados adicionada como armazenada em cache durante a execução:

    1. No painel **Fontes de dados**, selecione **Box\\Vend**.
    2. Selecione **Cache**.

    > [!NOTE]
    > A fonte de dados **Box\\Vend** será armazenada em cache no escopo de todas as transações de fornecedor da fonte de dados **Trans** no tempo de execução.

8. Siga estas etapas para atualizar a fonte de dados da **Trans\\\#Vend** aninhada de forma que ela use a fonte de dados **Box\\Vend**:

    1. No painel **Fontes de dados**, expanda **Trans**.
    2. Selecione a fonte de dados **Trans\\\#Vend** e, depois, **Editar** \> **Editar fórmula**.
    3. Na página **Designer de fórmulas**, no campo **Fórmula**, insira **Box.Vend(\@.AccountNum)**.
    4. Selecione **Salvar** e feche a página **Designer de fórmulas**.
    5. Selecione **OK** para concluir as alterações na fonte de dados selecionada.

9. Selecione **Salvar**.

    ![Fonte de dados Vend na página Designer de mapeamento do modelo](./media/er-calculated-field-ds-performance-mapping-4.png)

10. Feche a página **Designer de mapeamento de modelo**.
11. Feche a página **Mapeamentos de modelo**.

### <a name="complete-the-modified-version-of-the-er-model-mapping"></a>Concluir a versão modificada do mapeamento do modelo de ER

1. Na página **Configurações**, na FastTab **Versões**, selecione a versão **1.2** da configuração **Mapeamento de aperfeiçoamento de desempenho**.
2. Selecione **Alterar status** \> **Concluir** e, depois, **OK**.

## <a name="run-the-modified-er-solution-to-trace-execution"></a>Executar a solução de ER modificada para rastrear a execução

Repita as etapas na seção [Executar o formato de ER](#run-format) anterior neste tópico para gerar um novo rastreio de desempenho.

## <a name="use-the-performance-trace-to-analyze-adjustments-to-the-model-mapping"></a>Use o rastreamento de desempenho para analisar ajustes do mapeamento de modelo 

1. Na página **Configurações**, na árvore de configuração, selecione **Mapeamento de aperfeiçoamento de desempenho**.
2. No Painel de Ação, selecione **Designer**.
3. Na página **Mapeamentos de modelo**, no Painel de Ações, selecione **Designer**.
4. Na página **Designer de mapeamento de modelo**, no Painel de Ação, selecione **Rastreamento de desempenho**.
5. Selecione o rastreamento mais recente que foi gerado e selecione **OK**.

Observe que os ajustes feitos no mapeamento do modelo eliminaram consultas duplicadas no banco de dados. O número de chamadas para tabelas de banco de dados e fontes de dados para esse mapeamento do modelo também foi reduzido.

![Informações de rastreamento na página Designer de mapeamento do modelo 1](./media/er-calculated-field-ds-performance-mapping-5.png)

O tempo de execução total foi reduzido em torno de 20 vezes (de 8 segundos para 400 milissegundos). Portanto, o desempenho de toda a solução ER melhorou.

![Informações de rastreamento na página Designer de mapeamento do modelo 2](./media/er-calculated-field-ds-performance-mapping-5a.png)

## <a name="appendix-1-download-the-components-of-the-sample-microsoft-er-solution"></a><a name="appendix1"></a>Apêndice 1: baixar os componentes da solução ER de exemplo da Microsoft

Você deve baixar os arquivos a seguir e armazená-los localmente.

| Arquivo                                        | Conteúdo |
|---------------------------------------------|---------|
| Aperfeiçoamento de desempenho model.version.1     | [Configuração do modelo de dados de ER de exemplo](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg) |
| Aperfeiçoamento de desempenho mapping.version.1.1 | [Configuração do mapeamento do modelo de ER de exemplo](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg) |
| Aperfeiçoamento de desempenho format.version.1.1  | [Configuração de formato de ER de exemplo](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg) |

## <a name="appendix-2-configure-the-er-framework"></a><a name="appendix2"></a>Apêndice 2: configurar a estrutura de ER

Antes de começar a usar a estrutura de ER para melhorar o desempenho da solução ER de exemplo da Microsoft, você deve configurar o conjunto mínimo de parâmetros ER.

### <a name="configure-er-parameters"></a><a id="ConfigureParameters"></a>Configurar parâmetros de ER

1. Vá para **Administração da organização** \> **Espaços de trabalho** \> **Relatório eletrônico**.
2. Na página **Configurações de localização**, na seção **Links relacionados**, selecione **Parâmetros de relatório eletrônico**.
3. Na página **Parâmetros de relatório eletrônico**, na guia **Geral**, defina a opção **Habilitar modo de design** como **Sim**.
4. Na guia **Anexos**, defina os seguintes parâmetros:

    - No campo **Configurações**, selecione o tipo **Arquivo** para a empresa **DEMF**.
    - Nos campos **Arquivo de trabalho**, **Temporário**, **Linha de base** e **Outros**, selecione o tipo **Arquivo**.

Para obter mais informações sobre parâmetros de ER, consulte [Configurar a estrutura de ER](electronic-reporting-er-configure-parameters.md).

### <a name="activate-an-er-configuration-provider"></a><a id="ActivateProvider"></a>Ativar um provedor de configuração de ER

Toda configuração de ER adicionada é marcada como pertencente a um provedor de configuração de ER. O provedor de configuração de ER ativado no espaço de trabalho **Relatório eletrônico** é usado para essa finalidade. Por isso você deve ativar um provedor de configuração de ER no espaço de trabalho **Relatório eletrônico** antes de começar a adicionar ou editar configurações de ER.

> [!NOTE]
> Somente o proprietário de uma configuração ER pode editá-la. Assim, para que uma configuração de ER possa ser editada, o provedor de configuração de ER apropriado deve estar ativado no espaço de trabalho **Relatório eletrônico**.

#### <a name="review-the-list-of-er-configuration-providers"></a><a id="ReviewProvidersList"></a>Examinar a lista de provedores de configuração de ER

1. Vá para **Administração da organização** \> **Espaços de trabalho** \> **Relatório eletrônico**.
2. Na página **Configurações de localização**, na seção **Links relacionados**, selecione **Provedores de configuração**.
3. Na página **Tabela de provedores de configuração**, cada registro de provedor tem um nome e uma URL exclusivos. Examine o conteúdo dessa página. Se já existir um registro para **Litware, Inc.**, ignore o próximo procedimento, [Adicionar um novo provedor de configuração ER](#ActivateProvider).

#### <a name="add-a-new-er-configuration-provider"></a><a id="ActivateProvider"></a>Adicionar um novo provedor de configuração de ER

1. Vá para **Administração da organização** \> **Espaços de trabalho** \> **Relatório eletrônico**.
2. Na página **Configurações de localização**, na seção **Links relacionados**, selecione **Provedores de configuração**.
3. Na página **Provedores de configuração**, selecione **Novo**.
4. No campo **Nome**, insira **Litware, Ltda.**
5. No campo **Endereço na Internet**, insira `https://www.litware.com`.
6. Selecione **Salvar**.

#### <a name="activate-an-er-configuration-provider"></a><a id="ActivateAddedProvider"></a>Ativar um provedor de configuração de ER

1. Vá para **Administração da organização** \> **Espaços de trabalho** \> **Relatório eletrônico**.
2. Na página **Configurações de localização**, na seção **Provedores de configuração**, selecione o bloco **Litware, Ltda.** e, depois, **Definir como ativo**.

Para obter mais informações sobre provedores de configuração de ER, consulte [Criar provedores de configuração e marcá-los como ativos](tasks/er-configuration-provider-mark-it-active-2016-11.md).

## <a name="additional-resources"></a>Recursos adicionais

- [Visão geral do Relatório Eletrônico](general-electronic-reporting.md)
- [Rastrear a execução de formatos de ER para solucionar problemas de desempenho](trace-execution-er-troubleshoot-perf.md)
- [Suporte a chamadas parametrizadas de fontes de dados de ER do tipo Campo calculado](er-calculated-field-type.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]