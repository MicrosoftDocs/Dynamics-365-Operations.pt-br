---
title: Usar as fontes de dados JOIN nos mapeamentos do modelo de ER para obter dados de várias tabelas de aplicativos
description: Este tópico explica como você pode usar fontes de dados do tipo JOIN no relatório eletrônico (ER).
author: NickSelin
manager: AnnBe
ms.date: 05/04/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERModelMappingDesigner, EROperationDesigner
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-03-01
ms.dyn365.ops.version: Release 10.0.1
ms.openlocfilehash: 0d7df12026d6d668b1f48a48cd12bf4b12e0f94e
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4686407"
---
# <a name="use-join-data-sources-to-get-data-from-multiple-application-tables-in-electronic-reporting-er-model-mappings"></a>Usar as fontes de dados JOIN para obter dados de várias tabelas de aplicativos nos mapeamentos do modelo de relatório eletrônico (ER)

[!include[banner](../includes/banner.md)]

Ao configurar mapeamentos ou formatos de modelo de relatório eletrônico (ER), é possível [adicionar](#review) fontes de dados exigidas do tipo **Join**. No momento da criação, uma fonte de dados **Join** é configurada como um conjunto de várias fontes de dados, com cada uma retornando uma lista de registros. Em todas as fontes de dados, com exceção da primeira, é necessário definir as condições necessárias para inclusão dos registros das fontes de dados atuais e anteriores. Durante a execução, uma fonte de dados configurada do tipo **Join** [retornará](#executeERformat) uma única lista incluída de registros contendo campos dos registros de fontes de dados aninhadas.

Atualmente, há suporte para os seguintes tipos de junções:

- Junção externa (esquerda):
    - Inclua todos os registros da primeira fonte de dados (mais à esquerda) e, em seguida, qualquer correspondência de acordo com os registros de condições configurados da segunda fonte de dados (mais à direita).
- Junção externa (direita):
    - Inclua apenas registros da primeira fonte de dados (mais à esquerda) e apenas registros da segunda fonte de dados (mais à direita) que correspondam entre si de acordo com as condições configuradas.

Na fonte de dados **Join** configurada, quando todas as fontes de dados são do tipo **Registros de tabela**, a execução da fonte de dados Join pode ser [realizada no nível do banco de dados](#analyze) usando uma única instrução SQL. Essa instrução reduz o número de chamadas de banco de dados, o que melhora o desempenho do mapeamento do modelo. Caso contrário, a execução da fonte de dados **Join** é executada na memória.

> [!NOTE]
> Ainda não há suporte para o uso da função **VALUEIN** em expressões de ER que especificam condições para inclusão de registros em fontes de dados do tipo Join. Visite a página [Designer de fórmulas em relatórios eletrônicos](general-electronic-reporting-formula-designer.md) para obter mais detalhes sobre essa função.

Para saber mais sobre este recurso, conclua o exemplo neste tópico.

## <a name="example-use-join-data-sources-in-er-model-mappings"></a>Exemplo: use fontes de dados JOIN em mapeamentos do modelo de ER

As etapas a seguir explicam como o administrador do sistema ou o desenvolvedor de relatórios eletrônicos pode configurar um mapeamento de modelo de relatórios eletrônicos (ER) para obter dados de várias tabelas de aplicativos de uma só vez usando fontes de dados do tipo **Join** para melhorar o desempenho do acesso a dados. Essas etapas podem ser executadas em qualquer empresa do Dynamics 365 Finance ou Regulatory Configuration Services (RCS).

### <a name="prerequisites"></a>Pré-requisitos

Para concluir os exemplos neste tópico, você deve ter acesso a um dos itens a seguir, dependendo de qual serviço é usado para concluir estas etapas:

**Acesso ao Finance para uma das seguintes funções:**

- Desenvolvedor de relatório eletrônico
- Consultor funcional de relatório eletrônico
- Administrador do sistema

**Acesso ao RCS para uma das seguintes funções:**

- Desenvolvedor de relatório eletrônico
- Consultor funcional de relatório eletrônico
- Administrador do sistema

Primeiro você também deve concluir as etapas no procedimento [Criar um provedor de configuração e marcá-lo como ativo](tasks/er-configuration-provider-mark-it-active-2016-11.md).

Com antecedência, também é preciso fazer download no [Microsoft Download Center](https://go.microsoft.com/fwlink/?linkid=000000) e salvar localmente os seguintes arquivos de configuração de ER de amostra:

| **Descrição do conteúdo**  | **Nome do arquivo**   |
|--------------------------|-----------------|
| Amostra do arquivo de configuração **Modelo de dados de ER**, usado como fonte de dados para os exemplos.| [Modelo para conhecer fontes de dados JOIN.versão.1.1.xml](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg) |
| Amostra do arquivo de configuração **Mapeamento do modelo de ER**, que implementa o modelo de dados de ER para os exemplos. | [Mapeamento para conhecer fontes de dados JOIN.versão.1.1.xml](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg) |
| Amostra do arquivo de configuração **Formato de ER**. Este arquivo descreve os dados para preencher o componente de formato de ER para os exemplos. | [Formato para conhecer fontes de dados JOIN.versão.1.1.xml](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg) |

### <a name="activate-a-configurations-provider"></a>Ativar um provedor de configurações

1. Acesse o Finance ou o RCS na primeira sessão do seu navegador da Web.
2. Ir para **Administração da organização \> Espaços de trabalho \> Relatório eletrônico**.
3. Na página **Configurações de localização**, na seção **Provedores de configuração**, verifique se o provedor de configuração para a empresa de exemplo [Litware, Inc.](http://www.litware.com) está listado e marcado como **Ativo**. Caso não veja este provedor de configuração, siga as etapas do procedimento [Criar um provedor de configuração e marcá-lo como ativo](tasks/er-configuration-provider-mark-it-active-2016-11.md).

    ![Espaço de trabalho de relatório eletrônico](./media/GER-JoinDS-ActiveProvider.PNG)

### <a name="import-sample-er-configuration-files"></a>Importar amostra de arquivos de configuração de ER

1. Selecione **Configurações de relatórios**.
2. Importe o arquivo de configuração Modelo de dados de ER.
    1. Selecione **Taxa de câmbio**.
    2. Selecione **Carregar do arquivo XML**.
    3. Selecione **Procurar** para encontrar o arquivo **Modelo para conhecer fontes de dados JOIN.versão.1.1.xml**.
    4. Selecione **OK**.
3. Importe o arquivo de configuração Mapeamento de modelo de ER.
    1. Selecione **Taxa de câmbio**.
    2. Selecione **Carregar do arquivo XML**.
    3. Selecione **Procurar** para encontrar o arquivo **Mapeamento para conhecer fontes de dados JOIN.versão.1.1.xml**.
    4. Selecione **OK**.
4. Importe o arquivo de configuração do formato de ER.
    1. Selecione **Taxa de câmbio**.
    2. Selecione **Carregar do arquivo XML**.
    3. Selecione **Procurar** para encontrar o arquivo **Formato para conhecer fontes de dados JOIN.versão.1.1.xml**.
    4. Selecione **OK**.
5. Na árvore de configurações, expanda o item **Modelo para conhecer fontes de dados JOIN**, bem como outros itens de modelo (quando disponíveis).
6. Observe a lista de configurações de ER na árvore e os detalhes da versão na guia rápida **Versões**. Tais informações serão usadas como fonte de dados no seu relatório de exemplo.

    ![Página de configurações de relatórios eletrônicos](./media/GER-JoinDS-ConfigurationsTree.PNG)

### <a name="turn-on-execution-trace-options"></a>Ativar opções de rastreamento de execução

1. Selecione **CONFIGURAÇÕES**.
2. Selecione **Parâmetros de usuário**.
3. Defina os parâmetros de rastreamento de execução, conforme mostrado na captura de tela abaixo.

    ![Página de parâmetros do usuário de relatórios eletrônicos](./media/GER-JoinDS-Parameters.PNG)

    Com esses parâmetros ativados, para cada execução do arquivo de formato de ER importado, o rastreamento de execução será gerado. Usando detalhes do rastreamento de execução gerado, é possível analisar a execução do formato de ER e dos componentes de mapeamento do modelo de ER. Visite a página [Rastrear a execução do formato de ER para solucionar problemas de desempenho](trace-execution-er-troubleshoot-perf.md) para obter mais detalhes sobre o recurso de rastreamento de execução do ER.

### <a name="review-er-model-mapping-part-1"></a>Revisar o mapeamento do modelo de ER (parte 1)

Revise as configurações do componente de mapeamento do modelo de ER. O componente está configurado para acessar informações sobre versões de configurações de ER, detalhes de configurações e provedores de configuração sem usar fontes de dados do tipo **Join**.

1. Selecione a configuração **Mapeamento para conhecer fontes de dados JOIN**.
2. Selecione **Designer** para abrir a lista de mapeamentos.
3. Selecione **Designer** para revisar os detalhes do mapeamento.
4. Selecione **Mostrar detalhes**.
5. Na árvore de configurações, expanda os itens do modelo de dados **Set1** e **Set1.Details**:

    1. A associação de **Details: Record list = Versions** indica que o item **Set1.Details** está vinculado à fonte de dados **Versões** retornando registros da tabela **ERSolutionVersionTable**. Cada registro desta tabela representa uma única versão de uma configuração de ER. O conteúdo desta tabela é apresentado na guia rápida **Versões** da página **Configurações**.
    2. A associação de **ConfigurationVersion: String = @.PublicVersionNumber** significa que o valor da versão pública da versão de cada configuração de ER é retirado do campo **PublicVersionNumber** da tabela **ERSolutionVersionTable** e colocado no item **ConfigurationVersion**.
    3. A associação de **ConfigurationTitle: String = @.'>Relations'.Solution.Name** indica que o nome de uma configuração de ER é obtido do campo **Nome** da tabela **ERSolutionTable** com avaliação por meio da relação várias para um (**'>Relations'**) entre as tabelas **ERSolutionVersionTable** e **ERSolutionTable**. Os nomes das configurações de ER da instância atual do aplicativo são apresentados na árvore de configurações na página **Configurações**.
    4. A associação de **@.'>Relations'.Solution.'>Relations'.SolutionVendor.Name** significa que o nome do provedor de configuração que possui a configuração atual é obtido do campo **Nome** da tabela **ERVendorTable** com avaliação por meio da relação várias para um entre as tabelas **ERSolutionTable** e **ERVendorTable**. Os nomes dos provedores de configuração de ER são apresentados na árvore de configurações na página **Configurações** no cabeçalho da página de cada configuração. A lista inteira de provedores de configuração de ER pode ser encontrada na página da tabela **Administração da organização \> Relatório eletrônico \> Provedor de configuração**.

    ![Página de designer de mapeamento de modelo de ER](./media/GER-JoinDS-Set1Review.PNG)

6. Na árvore de configurações, expanda o item do modelo de dados **Set1.Summary**:

    1. A associação de **VersionsNumber: Integer = VersionsSummary.aggregated.VersionsNumber** indica que o item **Set1.Summary.VersionsNumber** está vinculado ao campo de agregação **VersionsNumber** da fonte de dados **VersionsSummary** do tipo **GroupBy** que foi configurado para retornar o número de registros da tabela **ERSolutionVersionTable** por meio da fonte de dados **Versões**.

    ![Página de parâmetros da fonte de dados GROUPBY](./media/GER-JoinDS-Set1GroupByReview.PNG)

7. Feche a página.

### <a name="review-er-model-mapping-part-2"></a><a name="review"></a> Revisar o mapeamento do modelo de ER (parte 2)

Revise as configurações do componente de mapeamento do modelo de ER. O componente está configurado para acessar informações sobre versões de configurações de ER, detalhes de configurações e provedores de configuração com o uso de fonte de dados do tipo **Join**.

1. Na árvore de configurações, expanda os itens do modelo de dados **Set2** e **Set2.Details**. A associação de **Details: Record list = Details** indica que o item **Set2.Details** está vinculado à fonte de dados **Detalhes** configurada como a fonte de dados do tipo **Join**.

    ![Página de designer de mapeamento de modelo de ER](./media/GER-JoinDS-Set2Review.PNG)

    A fonte de dados **Join** pode ser adicionada selecionando a fonte de dados **Funções\Join**:

    ![Página de designer de mapeamento de modelo de ER](./media/GER-JoinDS-AddJoinDS.PNG)

2. Selecione a fonte de dados **Detalhes**.
3. Selecione **Editar** no painel **Fontes de dados**.
4. Selecione **Editar junção**.
5. Selecione **Mostrar detalhes**.

    ![Página de parâmetros da fonte de dados JOIN](./media/GER-JoinDS-JoinDSEditor.PNG)

    Esta página é usada para criar a fonte de dados necessária do **tipo Join**. No tempo de execução, essa fonte de dados criará uma única lista incluída de registros das fontes de dados na grade **Lista incluída**. A junção de registros começará na fonte de dados **ConfigurationProviders** que está na grade como a primeira (para ela, a coluna **Tipo** está em branco). Os registros de todas as outras fontes de dados serão incluídos, consequentemente, nos registros da fonte de dados original, com base em sua ordem nessa grade. Toda fonte de dados de junção deve ser configurada como uma fonte de dados aninhada em uma fonte de dados de destino (a fonte de dados `1Versions` está aninhada em um; a fonte de dados `1Configurations` está aninhada em **ConfigurationProviders** um). Cada fonte de dados configurada deve conter as condições para a junção. Na fonte de dados do **Join** específico, as seguintes junções são definidas:

    - Cada registro da fonte de dados **ConfigurationProviders** (referido na tabela **ERVendorTable**) é associado apenas a registros de **1Configurations** (referidos na tabela **ERSolutionTable**) com o mesmo valor nos campos **SolutionVendor** e **RecId**. O tipo **Junção interna** é usado para essa associação, bem como as condições a seguir para registros correspondentes:

    FILTER (Configurations, Configurations.SolutionVendor = ConfigurationProviders.RecId)

    - Cada registro da fonte de dados **1Configurations** (referida na tabela **ERSolutionTable**) é associado apenas a registros de **1Versions** (referidos na tabela **ERSolutionVersionTable**) com o mesmo valor nos campos **Solution** e **RecId**. O tipo **Junção interna** é usado para essa associação, bem como as condições a seguir para registros correspondentes:

    FILTER (ConfigurationVersions, ConfigurationVersions.Solution = ConfigurationProviders.'1Configurations'.RecId)

    - A opção **Executar** está configurada como **Consulta**, ou seja, essa fonte de dados de junção será executada em tempo de execução no nível do banco de dados como uma chamada SQL direta.

    Para incluir registros de fontes de dados que representam tabelas de aplicativos, é possível especificar condições de junção usando pares de campos diferentes daqueles que descrevem as relações existentes na AOT entre essas tabelas. Esse tipo de junção também pode ser configurado para ser executado no nível do banco de dados.

6. Feche a página.
7. Selecione **Cancelar**.
8. Na árvore de configurações, expanda o item do modelo de dados **Set2.Summary**:

    - A associação de **VersionsNumber: Integer = DetailsSummary.aggregated.VersionsNumber** indica que o item **Set2.Summary.VersionsNumber** está vinculado ao campo de agregação **VersionsNumber** da fonte de dados **DetailsSummary** do tipo **GroupBy** que foi configurado para retornar o número de registros incluídos da fonte de dados **Detalhes** do tipo **Join**.
    - A opção de local **Execução** está configurada como **Consulta**, ou seja, essa fonte de dados **GroupBy** será executada em tempo de execução como uma chamada SQL direta no nível do banco de dados. Esse comportamento é possível porque a fonte de dados base **Detalhes** do tipo **Join** está configurada como executada no nível do banco de dados.

    ![Página de parâmetros da fonte de dados GROUPBY](./media/GER-JoinDS-Set2GroupByReview.PNG)

9. Feche a página.
10. Selecione **Cancelar**.

### <a name="execute-er-format"></a><a name="executeERformat"></a> Executar formato de ER

1. Acesse o Finance ou o RCS na segunda sessão do seu navegador da Web, usando as mesmas credenciais e empresa da primeira sessão.
2. Vá para **Administração da organização \> Relatório eletrônico \> Configurações**.
3. Expanda a configuração **Modelo para conhecer fontes de dados JOIN**.
4. Selecione a configuração **Formato para conhecer fontes de dados JOIN**.
5. Selecione **Designer**.
6. Selecione **Mostrar detalhes**.
7. Selecione **Mapeamento**.
8. Selecione **Expandir/Recolher**.

    Esse formato foi criado para preencher um arquivo de texto gerado com uma nova linha para todas as versões de uma configuração de ER (sequência **Versão**). Cada linha gerada conterá o nome de um provedor de configuração que possui a configuração atual, o nome da configuração e a versão da configuração separados por ponto e vírgula. A linha final do arquivo gerado conterá o número de versões descobertas das configurações de ER (sequência **Resumo**).

    ![Página de designer de formato de ER](./media/GER-JoinDS-FormatReview.PNG)

    As fontes de dados **Dados** e **Resumo** são usadas para preencher os detalhes da versão de configuração no arquivo gerado:

    - As informações do modelo de dados **Set1** são usadas quando você escolhe **Não** para a fonte de dados **Seletor** em tempo de execução na página de diálogo do usuário ao executar o formato de ER.
    - As informações do modelo de dados **Set2** são usadas quando você escolhe **Sim** para a fonte de dados **Seletor** em tempo de execução na página de diálogo do usuário.

    ![Página de designer de formato de ER](./media/GER-JoinDS-FormatMappingReview.PNG)

9. Selecione **Executar**.
10. Na página de diálogo, selecione **Não** no campo **Usar fontes de dados JOIN**.
11. Selecione **OK**.
12. Revise o arquivo gerado.

    ![Página de diálogo do usuário de ER](./media/GER-JoinDS-Set1Run.PNG)

#### <a name="analyze-er-format-execution-trace"></a>Analisar rastreio de execução do formato de ER

1. Na primeira sessão do Finance ou RCS, selecione **Designer**.
2. Selecione **Rastreamento de desempenho**.
3. Na grade **Rastreamento de desempenho**, selecione o registro mais superior do rastreamento de execução mais recente de um formato de ER em que foi usado o componente de mapeamento do modelo atual.
4. Selecione **OK**.

    As estatísticas de execução informam sobre chamadas duplicadas para tabelas de aplicativos:

    - **ERSolutionTable** foi chamado na mesma proporção de vezes em que houve registros de versão de configuração na tabela **ERSolutionVersionTable**, enquanto o número dessas chamadas pode ser reduzido em vários momentos para melhorar o desempenho.
    - **ERVendorTable** foi chamado duas vezes para cada registro de versão de configuração que foi descoberto na tabela **ERSolutionVersionTable**, enquanto o número dessas chamadas também pôde ser reduzido.

    ![Página de designer de mapeamento de modelo de ER](./media/GER-JoinDS-Set1Run2.PNG)

5. Feche a página.

### <a name="execute-er-format"></a>Executar formato de ER

1. Alterne para a guia do navegador da Web com a segunda sessão do Finance ou RCS.
2. Selecione **Executar**.
3. Na página de diálogo, selecione **Sim** no campo **Usar fontes de dados JOIN**.
4. Selecione **OK**.
5. Revise o arquivo gerado.

    ![Página de diálogo do usuário de ER](./media/GER-JoinDS-Set2Run.PNG)

#### <a name="analyze-er-format-execution-trace"></a><a name="analyze"></a> Analisar rastreio de execução do formato de ER

1. Na primeira sessão do Finance ou RCS, selecione **Designer**.
2. Selecione **Rastreamento de desempenho**.
3. Na grade **Rastreamento de desempenho**, selecione o registro mais superior representando o rastreamento de execução mais recente de um formato de ER em que foi usado o componente de mapeamento do modelo atual.
4. Selecione **OK**.

    As estatísticas o informam sobre o seguinte:

    - O banco de dados do aplicativo foi chamado uma vez para obter registros das tabelas **ERVendorTable**, **ERSolutionTable** e **ERSolutionVersionTable** para acessar os campos obrigatórios.

    ![Página de designer de mapeamento de modelo de ER](./media/GER-JoinDS-Set2Run2.PNG)

    - O banco de dados do aplicativo foi chamado uma vez para calcular o número de versões de configuração usando junções configuradas na fonte de dados **Detalhes**.

    ![Página de designer de mapeamento de modelo de ER](./media/GER-JoinDS-Set2Run3.PNG)

## <a name="limitations"></a>Limitações

Como você pode ver no exemplo deste tópico, a fonte de dados **JOIN** pode ser criada a partir de várias fontes de dados que descrevem os conjuntos individuais dos registros que devem ser incluídos eventualmente. Você pode configurar essas fontes de dados usando a função de ER [FILTER](er-functions-list-filter.md) integrada. Ao configurar a fonte de dados de forma que ela seja chamada além da fonte de dados **JOIN**, você pode usar intervalos da empresa como parte da condição para a seleção de dados. A implementação inicial da fonte de dados **JOIN** não oferece suporte a fontes de dados deste tipo. Por exemplo, ao chamar uma fonte de dados baseada em [FILTER](er-functions-list-filter.md) no escopo de execução de uma fonte de dados **JOIN**, se a fonte de dados chamada contiver intervalos da empresa como parte da condição para a seleção de dados, ocorrerá uma exceção.

Na versão 10.0.12 do Microsoft Dynamics 365 Finance (agosto de 2020), você pode usar intervalos da empresa como parte da condição para a seleção de dados em fontes de dados baseadas em [FILTER](er-functions-list-filter.md) que são chamados dentro do escopo de execução de uma fonte de dados **JOIN**. Devido às limitações do construtor de [consulta](../dev-ref/xpp-library-objects.md#query-object-model) de aplicativos, os intervalos da empresa têm suporte apenas para a primeira fonte de dados de uma fonte de dados **JOIN**.

### <a name="example"></a>Exemplo

Por exemplo, você deve fazer uma única chamada para o banco de dados do aplicativo para obter a lista de transações de comércio exterior de várias empresas e os detalhes do item de estoque referido nessas transações.

Nesse caso, configure os seguintes artefatos no mapeamento do modelo de ER:

- Fonte de dados raiz **Intrastat** que representa a tabela **Intrastat**.
- Fonte de dados raiz de **Itens** que representa a tabela **InventTable**.
- Fonte de dados raiz de **Empresas** que retorna a lista de empresas (**DEMF** e **GBSI** neste exemplo) onde as transações devem ser acessadas. O código da empresa está disponível no campo **Companies.Code**.
- Fonte de dados raiz **X1** que tem a expressão `FILTER (Intrastat, VALUEIN(Intrastat.dataAreaId, Companies, Companies.Code))`. Como parte da condição para a seleção de dados, essa expressão contém a definição de intervalos da empresa `VALUEIN(Intrastat.dataAreaId, Companies, Companies.Code)`.
- Fonte de dados **X2** como um item aninhado da fonte de dados **X1**. Ela inclui a expressão `FILTER (Items, Items.ItemId = X1.ItemId)`.

Finalmente, você pode configurar uma fonte de dados **JOIN** na qual **X1** é a primeira fonte de dados e **X2** é a segunda fonte de dados. Você pode especificar a **Consulta** como a opção **Executar** para forçar o ER a executar essa fonte de dados no nível do banco como uma chamada SQL direta.

Quando a fonte de dados configurada é executada enquanto a execução de ER é [rastreada](trace-execution-er-troubleshoot-perf.md), a instrução a seguir é mostrada no designer de mapeamento do modelo er como parte do rastreamento de desempenho ER.

`SELECT ... FROM INTRASTAT T1 CROSS JOIN INVENTTABLE T2 WHERE ((T1.PARTITION=?) AND (T1.DATAAREAID IN (N'DEMF',N'GBSI') )) AND ((T2.PARTITION=?) AND (T2.ITEMID=T1.ITEMID AND (T2.DATAAREAID = T1.DATAAREAID) AND (T2.PARTITION = T1.PARTITION))) ORDER BY T1.DISPATCHID,T1.SEQNUM`

> [!NOTE]
> Ocorrerá um erro se você executar uma fonte de dados **JOIN** que foi configurada de forma a conter condições de seleção de dados que têm intervalos da empresa para fontes de dados adicionais da fonte de dados **JOIN** executada.

## <a name="additional-resources"></a>Recursos adicionais

[Designer de fórmulas no Relatório eletrônico](general-electronic-reporting-formula-designer.md)

[Rastrear a execução do formato ER para solucionar problemas de desempenho](trace-execution-er-troubleshoot-perf.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]