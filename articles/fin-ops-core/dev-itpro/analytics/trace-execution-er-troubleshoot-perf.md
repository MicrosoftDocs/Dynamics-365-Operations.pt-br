---
title: Rastrear a execução de formatos de ER para solucionar problemas de desempenho
description: Este tópico fornece informações sobre como usar o recurso de rastreamento de desempenho no relatório eletrônico (ER) para solucionar problemas de desempenho.
author: NickSelin
ms.date: 06/22/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: 10eddf2f60db914e6451840d4d7aedb9dce7108874ea3ff45f375b85a55a694f
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6724384"
---
# <a name="trace-the-execution-of-er-formats-to-troubleshoot-performance-issues"></a>Rastrear a execução dos formatos ER para solucionar problemas de desempenho

[!include[banner](../includes/banner.md)]

Como parte do processo de designar configurações de relatórios eletrônicos (ER) para gerar documentos eletrônicos, você define o método usado para obter dados do aplicativo e inseri-los na saída gerada. O recurso de rastreamento de desempenho de ER ajuda a reduzir significativamente o tempo e o custo envolvidos na coleta dos detalhes da execução do formato ER e o uso deles para solucionar problemas de desempenho. Este tutorial fornece diretrizes sobre como obter rastreamentos de desempenho para formatos ER executados e como usar as informações desses rastreamentos para ajudar a melhorar o desempenho.

## <a name="prerequisites"></a>Pré-requisitos

Para concluir os exemplos neste tutorial, você deve ter o seguinte acesso:

- Acesso a uma das seguintes funções:

    - Desenvolvedor de relatório eletrônico
    - Consultor funcional de relatório eletrônico
    - Administrador do sistema

- Acesso à instância de Regulatory Configuration Services (RCS) que foi provisionado para o mesmo locatário como o aplicativo, para uma das seguintes funções:

    - Desenvolvedor de relatório eletrônico
    - Consultor funcional de relatório eletrônico
    - Administrador do sistema

Você também deve baixar e armazenar localmente os arquivos a seguir.

| Arquivo                                  | Conteúdo                               |
|---------------------------------------|---------------------------------------|
| Rastreamento de desempenho model.version.1     | [Configuração do modelo de dados de ER de exemplo](https://download.microsoft.com/download/0/a/a/0aa84e48-8040-4c46-b542-e3bf15c9b2ad/Performancetracemodelversion.1.xml)    |
| Rastreamento de desempenho metadata.version.1  | [Configuração de metadados de ER de exemplo](https://download.microsoft.com/download/a/9/3/a937e8c4-1f8a-43e4-83ee-7d599cf7d983/Performancetracemetadataversion.1.xml)      |
| Rastreamento de desempenho mapping.version.1.1 | [Configuração do mapeamento do modelo de ER de exemplo](https://download.microsoft.com/download/7/7/3/77379bdc-7b22-4cfc-9b64-a9147599f931/Performancetracemappingversion1.1.xml) |
| Rastreamento de desempenho format.version.1.1  | [Configuração de formato de ER de exemplo](https://download.microsoft.com/download/8/6/8/868ba581-5a06-459e-b173-fb00f038b37f/Performancetraceformatversion1.1.xml)       |

### <a name="configure-er-parameters"></a>Configurar parâmetros de ER

Cada rastreamento de desempenho de ER gerado no aplicativo é armazenado como um anexo do registro do log de execução. A estrutura de gerenciamento de documentos (DM) é usada para gerenciar esses anexos. Você deve configurar os parâmetros do ER antecipadamente para especificar o tipo de documento DM que deve ser usado para anexar rastreamentos de desempenho. No espaço de trabalho **Relatório eletrônico**, selecione **Parâmetros de relatório eletrônico**. Depois, na página **Parâmetros de relatório eletrônico**, na guia **Anexos**, no campo **Outros**, selecione o tipo de documento DM a ser usado para rastreamentos de desempenho.

![Página de parâmetros de relatórios eletrônicos.](./media/GER-PerfTrace-GER-Parameters-DocumentType.png)

Para estar disponível no campo de pesquisa **Outros**, um tipo de documento DM deve ser configurado da seguinte maneira na página **Tipos de documento** (**Administração da organização \> Gerenciamento de documentos \> Tipos de documento**):

- **Classe:** anexar arquivo
- **Grupo:** arquivo

![Página Tipos de documento.](./media/GER-PerfTrace-DM-DocumentType.png)

> [!NOTE]
> O tipo de documento selecionado deve estar disponível em todas as empresas da instância atual, porque os anexos do DM são específicos da empresa.

### <a name="configure-rcs-parameters"></a>Configurar parâmetros do RCS

Os rastreamentos de desempenho do ER gerados serão importados para o RCS para análise usando o designer de formato do ER e o designer de mapeamento do ER. Como os rastreamentos de desempenho do ER são armazenados como anexos do registro de log de execução relacionado ao formato ER, você deve configurar os parâmetros do RCS antecipadamente, para especificar o tipo de documento DM que deve ser usado para anexar rastreamentos de desempenho. Na instância do RCS que foi provisionada para sua empresa, no espaço de trabalho **Relatório eletrônico**, selecione **Parâmetros de relatório eletrônico**. Depois, na página **Parâmetros de relatório eletrônico**, na guia **Anexos**, no campo **Outros**, selecione o tipo de documento DM a ser usado para rastreamentos de desempenho.

![Página Parâmetros de relatório eletrônico no RCS.](./media/GER-PerfTrace-RCS-Parameters-DocumentType.png)

Para estar disponível no campo de pesquisa **Outros**, um tipo de documento DM deve ser configurado da seguinte maneira na página **Tipos de documento** (**Administração da organização \> Gerenciamento de documentos \> Tipos de documento**):

- **Classe:** anexar arquivo
- **Grupo:** arquivo

## <a name="design-an-er-solution"></a>Criar uma solução de ER

Suponha que você tenha começado a criar uma solução de ER para gerar um novo relatório que apresente transações de fornecedor. Atualmente, você pode encontrar as transações de um fornecedor selecionado na página **Transações do fornecedor** (Acesse **Conta a pagar \> Fornecedores \> Todos os fornecedores**, selecione um fornecedor e, no Painel de Ação, na guia **Fornecedor**, no grupo **Transações**, selecione **Transações**). Contudo, você deseja ter todas as transações do fornecedor ao mesmo tempo em um documento eletrônico no formato XML. Essa solução consistirá em várias configurações de ER que contêm os modelos de dados, metadados, mapeamento de modelo e componentes de formato necessários.

1. Entre na instância do RCS que foi provisionada para sua empresa.
2. Neste tutorial, você criará e modificará configurações para a empresa exemplo **Litware, Inc.**. Portanto, verifique se esse provedor de configuração foi adicionado ao RCS e selecionado como ativo. Para obter instruções, consulte o procedimento [Criar provedores de configuração e marcá-los como ativos](tasks/er-configuration-provider-mark-it-active-2016-11.md).
3. No espaço de trabalho **Relatório eletrônico**, selecione o bloco **Configurações de relatórios**.
4. Na página **Configurações**, importe as configurações de ER que você baixou como um pré-requisito para o RCS, na seguinte ordem: modelo de dados, metadados, mapeamento de modelo, formato. Para cada configuração, siga estas etapas:

    1. No Painel de Ação, selecione **Troca \> Carregar de um arquivo XML**.
    2. Selecione **Procurar** para selecionar o arquivo apropriado para a configuração de ER necessária no formato XML.
    3. Selecione **OK**.

    ![Página Configurações no RCS.](./media/GER-PerfTrace-RCS-ImportedConfigurations.png)

## <a name="run-the-er-solution-to-trace-execution"></a>Executar a solução de ER para rastrear a execução

Suponha que você tenha terminado de criar a primeira versão da solução de ER. Agora você deseja testá-la em sua instância e analisar o desempenho da execução.

### <a name="import-an-er-configuration-from-rcs-into-finance-and-operations"></a><a id='import-configuration'></a>Importar uma configuração ER do RCS para o Finance and Operations

1. Entre na sua instância do aplicativo.
2. Para este tutorial, você importará configurações de sua instância do RCS (onde você projeta seus componentes de ER) em sua instância (onde você testa e finalmente as utiliza). Portanto, você deve se certificar de que todos os artefatos necessários foram preparados. Para obter instruções, consulte o procedimento [Importar configurações do ER (Relatório eletrônico) dos RCS (Serviços de configuração regulatória)](rcs-download-configurations.md).
3. Siga estas etapas para importar as configurações do RCS para o aplicativo:

    1. No espaço de trabalho **Relatório eletrônico**, no bloco do provedor de configuração **Litware, Inc.**, selecione **Repositórios**.
    2. Na página **Repositório de configuração**, selecione o repositório do tipo **RCS** e depois selecione **Abrir**.
    3. Na Guia Rápida **Configurações**, selecione a configuração **Formato de rastreamento de desempenho**.
    4. Na Guia Rápida **Versões**, selecione a versão **1.1** da configuração selecionada e depois selecione **Importar**.

    ![Página do repositório de configuração.](./media/GER-PerfTrace-GER-ImportedConfigurations.png)

As versões correspondentes do modelo de dados e as configurações de mapeamento de modelo são importadas automaticamente como pré-requisitos para a configuração importada do formato ER.

### <a name="turn-on-the-er-performance-trace"></a>Ativar o rastreamento de desempenho de ER

1. Acesse **Administração da organização \> Relatório eletrônico \> Configurações**.
2. Na página **Configurações**, no Painel Ação, na guia **Configurações**, no grupo **Configurações avançadas**, selecione **Parâmetros de usuário**.
3. Na caixa de diálogo **Parâmetros de usuário**, na seção **Rastreamento de execução**, siga estas etapas:

    1. No campo **Formato de rastreamento de execução**, especifique o formato do rastreamento de desempenho gerado em que os detalhes de execução devem ser armazenados em formato ER e elementos de mapeamento:

        - **Formato de rastreamento de depuração** – Selecione este valor se você planeja executar interativamente um formato de ER que tenha um curto tempo de execução. A coleção de detalhes sobre a execução do formato de ER é então iniciada. Quando esse valor é selecionado, o rastreamento de desempenho coleta informações sobre o tempo gasto nas seguintes ações:

            - Execução de cada fonte de dados no mapeamento de modelo que é chamado para obter dados
            - Processamento de cada item de formato para inserir dados na saída gerada

            Se selecionar o valor de **Formato de rastreamento de depuração**, você pode analisar o conteúdo do rastreamento no designer da Operação de ER. Lá, você pode visualizar o formato de ER ou mapear elementos que são mencionados no rastreamento.

        - **Formato de rastreamento agregado** – Selecione este valor se você planeja executar um formato de ER que tenha um longo tempo de execução. A coleção de detalhes agregados sobre a execução do formato de ER é então iniciada. Quando esse valor é selecionado, o rastreamento de desempenho coleta informações sobre o tempo gasto nas seguintes ações:

            - Execução de cada fonte de dados no mapeamento de modelo que é chamado para obter dados
            - Execução de cada fonte de dados no mapeamento de formato que é chamado para obter dados
            - Processamento de cada item de formato para inserir dados na saída gerada

            O valor **Formato de rastreamento agregado** está disponível na versão 10.0.20 e posterior do Microsoft Dynamics 365 Finance.

            No designer de formato de ER e no designer de mapeamento de modelos de ER, você pode visualizar o tempo total de execução de um único componente. Além disso, o rastreamento contém detalhes sobre a execução, como o número de execuções e o tempo mínimo e máximo de uma única execução.

            > [!NOTE]
            > Este rastreamento é coletado com base no caminho dos componentes rastreados. Portanto, as estatísticas podem estar incorretas quando um componente pai solteiro contém vários componentes filhos não nomeados, ou quando vários componentes filhos têm o mesmo nome.

    2. Defina as seguintes opções como **Sim** para coletar detalhes específicos da execução dos componentes de mapeamento do modelo de ER e formato ER:

        - **Coletar estatísticas da consulta** – Quando esta opção está ativada, o rastreamento de desempenho coletará as seguintes informações:

            - O número de chamadas de banco de dados feitas por fontes de dados
            - O número de chamadas duplicadas para o banco de dados
            - Detalhes das instruções SQL que foram usadas para fazer chamadas de banco de dados

        - **Acesso de rastreamento de cache** – Quando esta opção está ativada, o rastreamento de desempenho coletará informações sobre o uso de cache do mapeamento do modelo de ER.
        - **Acesso de dados de rastreamento** – Quando esta opção está ativada, o rastreamento de desempenho coletará informações sobre o número de chamadas para o banco de dados para origens de dados executadas do tipo de lista de registros.
        - **Enumeração da lista de rastreamento** – Quando esta opção está ativada, o rastreamento de desempenho coletará informações sobre o número de registros que são solicitados de fontes de dados do tipo de lista de registros.

    > [!NOTE]
    > Os parâmetros na caixa de diálogo **Parâmetros de usuário** são específicos do usuário e da empresa atual.

    ![Caixa de diálogo de parâmetros do usuário.](./media/GER-PerfTrace-GER-UserParameters.png)

### <a name="run-the-er-format"></a><a id='run-format'></a>Executar o formato de ER

1. Selecione a empresa **DEMF**.
2. Acesse **Administração da organização \> Relatório eletrônico \> Configurações**.
3. Na página **Configurações**, na árvore de configuração, selecione o item **Formato de rastreamento de desempenho**.
4. No Painel de Ação, selecione **Executar**.

Observe que o arquivo gerado apresenta informações sobre 265 transações de seis fornecedores.

## <a name="review-the-execution-trace"></a>Revisar o rastreamento de execução

### <a name="export-the-generated-trace-from-the-application"></a><a id='export-trace'></a>Exporte o rastreamento gerado do aplicativo

Os rastreamentos de desempenho são desacoplados do formato ER de origem e podem ser serializados em um arquivo zip externo.

1. Acesse **Administração da organização \> Relatório eletrônico \> Logs de depuração de configuração**.
2. Na página **Logs de execução de relatórios eletrônicos**, no painel esquerdo, no campo **Nome da configuração**, selecione **Formato de rastreamento de desempenho** para encontrar os registros de log que foram gerados pela execução da configuração **Formato de rastreamento de desempenho**.
3. Selecione o botão **Anexos** (o símbolo de clipe de papel) no canto superior direito da página ou pressione **Ctrl+Shift+A**.

    ![Botão Anexos na página Logs de execução de relatórios eletrônicos.](./media/GER-PerfTrace-GER-DebugLog.png)

4. Na página **Anexos para Logs de execução de relatórios eletrônicos**, no Painel de Ação, selecione **Abrir** para obter o rastreamento de desempenho como um arquivo zip e armazená-lo localmente.

    ![Anexos para Logs de execução de relatórios eletrônicos.](./media/GER-PerfTrace-GER-DebugLog-AttachedTrace.png)

> [!NOTE]
> O rastreamento gerado tem uma referência ao relatório ER de origem por meio de um identificador de relatório exclusivo no formato **GUID** apenas. A numeração de versão do formato não é considerada.

Observe que a associação entre o rastreamento de desempenho que foi gerado para o formato ER executado e o mapeamento do modelo de ER é baseada no descritor raiz que foi usado e no modelo de dados comum. A numeração da versão do formato e do mapeamento do modelo não é considerada. A configuração do sinalizador **Padrão do mapeamento de modelo** para o mapeamento do modelo também não é considerada.

### <a name="import-the-generated-trace-into-rcs"></a><a id='import-trace'></a>Importar o rastreamento gerado para o RCS

1. No RCS, no espaço de trabalho **Relatório eletrônico**, selecione o bloco **Configurações de relatórios**.
2. Na página **Configurações**, na árvore de configuração, expanda o item **Modelo de rastreamento de desempenho** e selecione o item **Formato de rastreamento de desempenho**.
3. No Painel de Ação, selecione **Designer**.
4. Na página **Designer de formato**, no Painel de Ação, selecione **Rastreamento de desempenho**.
5. Na caixa de diálogo **Configurações de resultado de rastreamento de desempenho**, selecione **Importar rastreamento de desempenho**.
6. Selecione **Procurar** para selecionar o arquivo zip que você exportou anteriormente.
7. Selecione **OK**.

    ![Caixa de diálogo Configurações de resultado de rastreamento de desempenho no RCS.](./media/GER-PerfTrace-RCS-ImportedPerfTrace.png)

### <a name="use-the-performance-trace-for-analysis-in-rcs--format-execution"></a>Use o rastreamento de desempenho para análise no RCS - Execução de formato

1. No RCS, na página **Designer de formato**, selecione **Expandir/recolher** para expandir o conteúdo de todos os itens de formato.

    Observe que informações adicionais são mostradas para alguns itens do formato atual:

    - O tempo real gasto ao inserir dados na saída gerada usando o item de formato
    - O mesmo tempo expresso como uma porcentagem do tempo total gasto gerando toda a saída

    ![Página Designer de formatos no RCS.](./media/GER-PerfTrace-RCS-TraceInfoInFormat.png)

2. Feche a página **Designer de formato**.

### <a name="use-the-performance-trace-for-analysis-in-rcs--model-mapping"></a><a id='use-trace'></a>Use o rastreamento de desempenho para análise no RCS – Mapeamento de modelos

1. No RCS, na página **Configurações**, na árvore de configuração, selecione o item **Mapeamento de rastreamento de desempenho**.
2. No Painel de Ação, selecione **Designer**.
3. Selecione **Designer**.
4. Na página **Designer de mapeamento de modelo**, no Painel de Ação, selecione **Rastreamento de desempenho**.
5. Selecione o rastreamento que você importou anteriormente.
6. Selecione **OK**.

Observe que novas informações ficam disponíveis para alguns itens da fonte de dados do mapeamento atual do modelo:

- O tempo real gasto ao obter dados usando a fonte de dados
- O mesmo tempo expresso como uma porcentagem do tempo total gasto na execução do mapeamento do modelo inteiro

Observe que o ER informa que o mapeamento do modelo atual duplica as solicitações do banco de dados enquanto a fonte de dados VendTable/\<Relations/VendTrans.VendTable\_AccountNum é executada. Essa duplicação ocorre porque a lista de transações do fornecedor é chamada duas vezes para cada registro de fornecedor repetido:

- Uma chamada é feita para inserir detalhes de cada transação no modelo de dados, com base nas ligações configuradas.
- Uma chamada é feita para inserir o número calculado de transações por fornecedor no modelo de dados.

![Mensagem sobre solicitações de banco de dados duplicadas na página Designer de mapeamento de modelo no RCS.](./media/GER-PerfTrace-RCS-TraceInfoInMapping1.png)

O valor **\[Q:530\]** indica que a tabela VendTrans foi chamada 530 vezes para retornar um registro dessa tabela para a fonte de dados VendTable/\<Relations/VendTrans.VendTable\_AccountNum. O valor **\[530\]** indica que a fonte de dados VendTable/\<Relations/VendTrans.VendTable\_AccountNum foi chamada 530 vezes para retornar um registro dessa fonte de dados e inserir os detalhes dela no modelo de dados.

Recomendamos que você use o armazenamento em cache para a fonte de dados VendTable/\<Relations/VendTrans.VendTable\_AccountNum, para reduzir o número de chamadas feitas para obter os detalhes de 265 transações e ajudar a melhorar o desempenho do mapeamento do modelo.

Também pode ser útil reduzir o número de chamadas feitas à fonte de dados LedgerTransTypeList. Essa fonte de dados é usada para associar cada valor da enumeração **LedgerTransType** a seu rótulo. Usando essa fonte de dados, você pode encontrar um rótulo apropriado e inseri-lo no modelo de dados para cada transação do fornecedor. O número atual de chamadas para essa fonte de dados (9.027) é bastante alto para 265 transações.

![Página Designer de mapeamento de modelo no RCS, mostrando 9.027 chamadas para a fonte de dados.](./media/GER-PerfTrace-RCS-TraceInfoInMapping1a.png)

## <a name="improve-the-model-mapping-based-on-information-from-the-execution-trace"></a>Melhorar o mapeamento do modelo com base nas informações do rastreamento de execução

### <a name="modify-the-logic-of-the-model-mapping"></a>Modificar a lógica do mapeamento do modelo

1. Siga estas etapas para usar o armazenamento em cache, para ajudar a evitar chamadas duplicadas para o banco de dados:

    1. No RCS, na página **Designer de mapeamento de modelo**, no painel **Fontes de dados**, selecione o item **VendTable**.
    2. Selecione **Cache**.
    3. Expanda o item **VendTable**, expanda a lista de relações um para muitos para a fonte de dados VendTable (o item **\<Relações**) e selecione o item **VendTrans.VendTable\_AccountNum**.
    4. Selecione **Cache**.

    ![Configuração de cache para ajudar a impedir chamadas duplicadas.](./media/GER-PerfTrace-RCS-ChangeMapping-Cache.png)

2. Siga estas etapas para trazer a fonte de dados LedgerTransTypeList para o escopo da fonte de dados VendTable:

    1. No painel **Tipos de fontes de dados**, expanda o item **Funções** e selecione o item **Campo calculado**.
    2. No painel **Fontes de dados**, selecione o item **VendTable**.
    3. Selecione **Adicionar**.
    4. No campo **Nome**, insira **\$TransType**.
    5. Selecione **Editar fórmula**.
    6. No campo **Fórmula**, insira **LedgerTransTypeList**.
    7. Selecione **Salvar**.
    8. Feche a página **Editor de fórmulas**.
    9. Clique em **OK**.

3. Siga estas etapas para fazer o armazenamento em cache do campo **\$TransType**:

    1. Selecione o item **LedgerTransTypeList**.
    2. Selecione **Cache**.
    3. Selecione o item **VendTable.\$TransType**.
    4. Selecione **Cache**.

    ![Configuração de cache para o campo $TransType.](./media/GER-PerfTrace-RCS-ChangeMapping-Cache2.png)

4. Siga estas etapas para alterar o campo **\$TransTypeRecord** para que ele comece a usar o campo **\$TransType** em cache:

    1. No painel **Fontes de dados**, expanda o item **VendTable**, expanda o item **\<Relations**, expanda o item **VendTrans.VendTable\_AccountNum** e selecione o item **VendTable. VendTrans.VendTable\_AccountNum.\$TransTypeRecord**.
    2. Selecione **Editar**.
    3. Selecione **Editar fórmula**.
    4. No campo **Fórmula**, encontre a seguinte expressão:

        FIRSTORNULL (WHERE (LedgerTransTypeList, LedgerTransTypeList.Enum = \@.TransType))

    5. No campo **Fórmula**, insira a seguinte expressão:

        FIRSTORNULL (WHERE (VendTable.'\$TransType', VendTable.'\$TransType'.Enum = \@.TransType)).

    6. Selecione **Salvar**.
    7. Feche a página **Editor de fórmulas**.
    8. Selecione **OK**.

5. Selecione **Salvar**.
6. Feche a página **Designer de mapeamento de modelo**.
7. Feche a página **Mapeamentos de modelo**.

### <a name="complete-the-modified-version-of-the-er-model-mapping"></a>Concluir a versão modificada do mapeamento do modelo de ER

1. No RCS, na página **Configurações**, na Guia Rápida **Versões**, selecione a versão **1.2** da configuração **Mapeamento de rastreamento de desempenho**.
2. Selecione **Alterar status**.
3. Selecione **Concluir**.

### <a name="import-the-modified-er-model-mapping-configuration-from-rcs-into-the-application"></a>Importar a configuração de mapeamento do modelo de ER modificado do RCS para o aplicativo

Repita as etapas na seção [Importar uma configuração de ER do RCS para Finance and Operations](#import-configuration) anteriormente neste tópico para importar a versão 1.2 da configuração **Mapeamento de rastreamento de desempenho**.

## <a name="run-the-modified-er-solution-to-trace-execution"></a>Executar a solução de ER modificada para rastrear a execução

### <a name="run-the-er-format"></a>Executar o formato de ER

Repita as etapas na seção [Executar o formato de ER](#run-format) anterior neste tópico para gerar um novo rastreio de desempenho.

## <a name="work-with-the-execution-trace"></a>Trabalhar com o rastreamento de execução

### <a name="export-the-generated-trace-from-the-application"></a>Exportar o rastreamento gerado do aplicativo

Repita as etapas na seção [Exportar o rastreamento gerado no aplicativo](#export-trace) anteriormente neste tópico para salvar um novo rastreamento de desempenho localmente.

### <a name="import-the-generated-trace-into-rcs"></a>Importar o rastreamento gerado para o RCS

Repita as etapas na seção [Importar o rastreamento gerado para o RCS](#import-trace) anterior neste tópico para importar o novo rastreamento de desempenho para o RCS.

### <a name="use-the-performance-trace-for-analysis-in-rcs--model-mapping"></a>Use o rastreamento de desempenho para análise no RCS – Mapeamento de modelos

Repita as etapas na seção [Use o rastreamento de desempenho para análise no RCS – Mapeamento de modelos](#use-trace) anterior deste tópico para analisar o último rastreio de desempenho.

Observe que os ajustes feitos no mapeamento do modelo eliminaram consultas duplicadas no banco de dados. O número de chamadas para tabelas de banco de dados e fontes de dados para esse mapeamento de modelo também foi reduzido. Portanto, o desempenho de toda a solução de ER melhorou.

![Informações de rastreamento da fonte de dados VendTable na página Designer de mapeamento de modelo no RCS.](./media/GER-PerfTrace-RCS-TraceInfoInMapping2.png)

Nas informações de rastreamento, o valor **\[12\]** da fonte de dados VendTable indica que essa fonte de dados foi chamada 12 vezes. O valor **\[Q:6\]** indica que seis chamadas foram convertidas em chamadas de banco de dados para a tabela VendTable. O valor **\[C:6\]** indica que os registros que foram obtidos do banco de dados foram armazenados em cache e seis outras chamadas foram processadas usando o cache.

Observe que o número de chamadas para a fonte de dados LedgerTransTypeList foi reduzido de 9.027 para 240.

![Informações de rastreamento da fonte de dados LedgerTransTypeList na página Designer de mapeamento de modelo no RCS.](./media/GER-PerfTrace-RCS-TraceInfoInMapping2a.png)

## <a name="review-the-execution-trace-in-the-application"></a>Revisar o rastreamento de execução do aplicativo

Além do RCS, algumas versões podem oferecer recursos para uma experiência de designer de estrutura de ER. Essas versões têm uma opção **Habilitar o modo de design** que pode ser ativada. Você pode encontrar essa opção na guia **General** da página **Parâmetros de relatório eletrônico**, que pode ser aberta no espaço de trabalho **Relatório eletrônico**.

![Habilitar a opção do modo de design da página de parâmetros de relatórios eletrônicos.](./media/GER-PerfTrace-GER-Parameters-DesignMode.png)

Se usar uma dessas versões, você poderá analisar os detalhes dos rastreamentos de desempenho gerados diretamente no aplicativo. Você não precisa exportá-los do aplicativo e importá-los para o RCS.

## <a name="review-the-execution-trace-by-using-external-tools"></a>Revisar o rastreamento de execução usando ferramentas externas

### <a name="configure-user-parameters"></a>Configurar parâmetros de usuário

1. Acesse **Administração da organização \> Relatório eletrônico \> Configurações**.
2. Na página **Configurações**, no Painel Ação, na guia **Configurações**, no grupo **Configurações avançadas**, selecione **Parâmetros de usuário**.
3. Na caixa de diálogo **Parâmetros de usuário**, na seção **Rastreamento de execução**, no campo **Formato de rastreamento de execução**, selecione **PerfView XML**.

### <a name="run-the-er-format"></a>Executar o formato de ER

Repita as etapas na seção [Executar o formato de ER](#run-format) anterior neste tópico para gerar um novo rastreio de desempenho.

Observe que o navegador da Web oferece um arquivo zip para download. Este arquivo contém o rastreamento de desempenho no formato PerfView. Você pode então usar a ferramenta de análise de desempenho do PerfView para analisar os detalhes da execução do formato ER.

![informações de rastreamento de desempenho no formato PerfView.](./media/GER-PerfTrace2-PerfViewTrace1.PNG)

## <a name="use-external-tools-to-review-an-execution-trace-that-includes-database-queries"></a>Use ferramentas externas para revisar um rastreamento de execução que inclua consultas a bancos de dados

Devido as melhorias feitas na estrutura de ER, o rastreamento de desempenho que é gerado no formato PerfView agora oferece mais detalhes sobre a execução do formato ER. No Microsoft Dynamics 365 for Finance and Operations versão 10.0.4 (julho de 2019), este rastreamento também pode incluir detalhes de consultas SQL executadas para o banco de dados do aplicativo.

### <a name="configure-user-parameters"></a>Configurar parâmetros de usuário

1. Acesse **Administração da organização** \> **Relatório eletrônico** \> **Configurações**.
2. Na página **Configurações**, no Painel Ação, na guia **Configurações**, no grupo **Configurações avançadas**, selecione **Parâmetros de usuário**.
3. Na caixa de diálogo **Parâmetros de usuário**, na seção **Rastreamento de execução**, defina os seguintes parâmetros:

    - No campo **Formato de rastreamento de execução** , selecione **PerfView XML**.
    - Defina a opção **Coletar estatísticas da consulta** como **Sim**.
    - Defina a opção **Rastrear consulta** como **Sim**.

    ![Seção de rastreamento de execução, caixa de diálogo Parâmetros do usuário.](./media/GER-PerfTrace2-GER-UserParameters.PNG)

### <a name="run-the-er-format"></a>Executar o formato de ER

Repita as etapas na seção [Executar o formato de ER](#run-format) anterior neste tópico para gerar um novo rastreio de desempenho.

Observe que o navegador da Web oferece um arquivo zip para download. Este arquivo contém o rastreamento de desempenho no formato PerfView. Você pode então usar a ferramenta de análise de desempenho do PerfView para analisar os detalhes da execução do formato ER. Este rastreamento agora inclui os detalhes de acesso do banco de dados SQL durante a execução do formato ER.

![Informações de rastreamento para o formato ER executado em PerfView.](./media/GER-PerfTrace2-PerfViewTrace2.PNG)

## <a name="additional-resources"></a>Recursos adicionais

- [Visão geral do Relatório Eletrônico](general-electronic-reporting.md)
- [Melhorar o desempenho das soluções ER adicionando fontes de dados de CAMPOS CALCULADOS parametrizados](er-calculated-field-ds-performance.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
