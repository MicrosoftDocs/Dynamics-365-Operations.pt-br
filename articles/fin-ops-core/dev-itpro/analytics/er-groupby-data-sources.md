---
title: Agrupar registros e cálculos agregados usando fontes de dados GROUPBY
description: Este tópico explica como você pode usar fontes de dados do tipo GROUPBY no relatório eletrônico (ER).
author: NickSelin
ms.date: 01/31/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERModelMappingDesigner, EROperationDesigner
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5a6cdc486c5f799bdedafa38e90be989fd328c96
ms.sourcegitcommit: 89655f832e722cefbf796a95db10c25784cc2e8e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8075598"
---
# <a name="group-records-and-aggregate-calculations-by-using-groupby-data-sources"></a>Agrupar registros e cálculos agregados usando fontes de dados GROUPBY

[!include[banner](../includes/banner.md)]

[!include[banner](../includes/preview-banner.md)]

Ao configurar mapeamentos ou formatos de modelo de [Relatório eletrônico (ER)](general-electronic-reporting.md), é possível [adicionar](#AddMmDataSource2) fontes de dados exigidas do tipo **GroupBy**.

Na etapa de design, uma fonte de dados **GroupBy** é configurada para identificar os seguintes elementos:

- Uma [fonte de dados de base](#BaseDataSource) que contém registros que serão agrupados no runtime
- [Agrupamento de campos](#GroupingFields) da fonte de dados de base, que será usado para agrupamento de registros no runtime
- [Agregar funções](#AggregateFunctions) que especificam os cálculos agregados que serão efetuados para cada grupo descoberto no runtime

No runtime, uma fonte de dados configurada **GroupBy** agrupa os registros que têm os mesmos valores nos campos de agrupamento e, em seguida, retorna uma lista de registros. Cada registro representa um único grupo. Para cada grupo, a fonte de dados expõe os valores de campo que os registros iniciais foram agrupados, os valores das funções agregadas calculadas e a lista de registros da fonte de dados de base que pertence ao grupo.

## <a name="aggregate-functions"></a><a name="AggregateFunctions"></a>Funções para agregação

No runtime, todo cálculo agregado é feito para cada grupo de registros. Esse cálculo é feito usando o valor de um único campo ou uma expressão nos registros de uma fonte de dados selecionada para agrupamento na fonte de dados editável do tipo **GroupBy**. Atualmente, há suporte para as funções agregada:

- **MÉDIA** – Esta função retorna a média dos valores em um grupo. Ele pode ser usado somente com campos numéricos.
- **CONTAGEM** – Esta função retorna o número de itens que foram encontrados em um grupo.
- **Mín.** -Esta função retorna o valor mínimo entre os valores de um grupo.
- **Máx.** -Esta função retorna o valor máximo entre os valores de um grupo.
- **TOTAL** – Esta função retorna o total dos valores em um grupo. Ele pode ser usado somente com campos numéricos.

## <a name="execution-location"></a><a name="ExecutionLocation"></a>Local de execução

Quando você edita uma fonte de dados **GroupBy** e especifica a fonte de dados base que contém os registros que devem ser agrupados, o sistema detecta automaticamente o [local](#ExecutionLocation) mais eficiente para a execução dessa fonte de dados **GroupBy**. Se a fonte de dados base for [consultável](er-functions-list-filter.md#usage-notes) (ou seja, se puder ser executada no nível do banco de dados), o banco de dados do aplicativo também será especificado como a localização da execução da fonte de dados **GroupBy** editável. Caso contrário, a memória do servidor de aplicativos será especificada como o local de execução.

Você pode alterar manualmente o local de execução detectado automaticamente selecionando o local aplicável à fonte de dados configurada. Se o local de execução selecionado não for aplicável, um [erro de validação](er-components-inspections.md#i5) será lançado na etapa de design.

> [!TIP]
> Recomendamos que você use a localização do banco de dados para agrupar fontes que expõem um grande número de registros.

## <a name="memory-consumption"></a><a name="MemoryConsumption"></a>Consumo de memória

Por padrão, se uma fonte de dados **GroupBy** for executada na memória, a memória do servidor de aplicativos será usada para armazenar registros da fonte de dados de base que pertença a cada grupo descoberto como registros de um único grupo. Para ajudar a reduzir o consumo de memória, você pode suprimir o armazenamento de registros para fontes de dados **GroupBy** se elas foram configuradas para computar somente funções agregadas e os registros de seu grupo não são usados no runtime. Para reduzir o consumo de memória dessa forma, habilite a opção **Redução do uso de memória no ER quando o agrupamento de registros só é usado para computar o recurso de agregações** no espaço de trabalho **Gerenciamento de recursos**.

## <a name="alternatives"></a><a name="Alternatives"></a>Alternativas

Agregações semelhantes podem ser calculadas usando [diferentes](er-data-collection-data-sources.md#if-i-have-to-calculate-running-totals-and-collect-data-what-is-the-difference-between-using-a-data-collection-data-source-and-using-the-built-in-data-collection-functions) tipos de fontes de dados ou funções incluídas no ER.

Para saber mais sobre este recurso, conclua o exemplo que segue.

## <a name="example-use-a-groupby-data-source-for-aggregate-calculations-and-record-grouping"></a><a name="Example"></a>Exemplo: Utilize uma fonte de dados "GROUPBY" para agregar cálculos e registrar agrupamentos

Este exemplo mostra como um usuário na função de Administrador do sistema ou de Consultor funcional do relatório eletrônico pode configurar um mapeamento de modelo de ER que tem uma fonte de dados **GROUPBY** que é usada para calcular funções de agregação e registros de grupos. Esse mapeamento de modelo é usado para imprimir o relatório de controle quando a declaração Intrastat é gerada. Este relatório permite revisar transações Intrastat relatadas.

Os procedimentos neste exemplo podem ser concluídos na empresa **DEMF** no Microsoft Dynamics 365 Finance. 

### <a name="prepare-sample-data"></a>Preparar dados de amostra

Verificar se você tem transações do Intrastat para relatar na página **Intrastat**. Você deve ter transações para códigos de transporte diferentes, pois as transações serão agrupadas pelo campo **Transporte** neste exemplo.

![Preparação de transações intrastat na página Intrastat.](./media/er-groupby-data-sources-prepare-transactions.png)

### <a name="configure-the-er-framework"></a>Configurar a estrutura de ER

Siga as etapas em [Configurar a estrutura de ER](er-quick-start2-customize-report.md#ConfigureFramework) para configurar o conjunto mínimo de parâmetros de ER. Você deve concluir essa configuração antes de começar a usar a estrutura de ER para criar um mapeamento do modelo de ER.

### <a name="import-the-standard-er-format-configuration"></a>Importar a configuração do formato de ER padrão

Siga as etapas em [Importar a configuração do formato de ER padrão](er-quick-start2-customize-report.md#ImportERSolution1) para adicionar as configurações de ER padrão à sua instância atual do Dynamics 365 Finance. Importar a versão 1 da configuração do modelo **Intrastat** do repositório.

### <a name="create-a-custom-data-model-configuration"></a>Criar uma configuração de modelo de dados personalizada

Seguir as etapas em [Adicionar uma configuração de modelo de dados](er-quick-start3-customize-report.md#add-a-custom-data-model-configuration) para adicionar manualmente uma nova configuração do modelo de dados do ER **para o modelo Intrastat (Litware)** que você derivou da configuração do modelo **Intrastat** importado.

### <a name="configure-a-custom-data-model-component"></a>Configurar um componente de modelo de dados personalizada

Seguir estas etapas para fazer as alterações necessárias no modelo de dados do **modelo Intrastat (Litware)** derivado, de forma que possa ser usado para expor códigos de transporte com os detalhes necessários.

1. Acesse **Administração da organização** \> **Relatório eletrônico** \> **Configurações**.
2. Na página **Configurações**, na árvore de configurações, selecione o modelo **Intrastat (Litware)**.
3. Selecione **Designer**.
4. Na página **Designer de mapeamento de modelo**, na árvore de modelo, selecione **Intrastat**.
5. Selecionar **Novo** para adicionar um novo nó aninhado ao nó **Intrastat** selecionado. Na caixa de diálogo suspensa para adicionar um nó de modelo de dados, siga estas etapas:

    1. No campo **Nome**, inserir **Transporte**.
    2. No campo **Tipo de item**, selecione **Lista de registros**.
    3. Selecione **Adicionar** para adicionar o novo nó.

6. Selecionar **Novo** para adicionar um novo nó aninhado ao nó de **Transporte** recém-adicionado. Na caixa de diálogo suspensa para adicionar um nó de modelo de dados, siga estas etapas:

    1. No campo **Nome**, inserir **Código**.
    2. No campo **Tipo de item**, selecione **String**.
    3. Selecione **Adicionar** para adicionar o novo nó.

7. Selecionar **Novo** para adicionar um novo nó aninhado ao nó de **Transporte** recém-adicionado. Na caixa de diálogo suspensa para adicionar um nó de modelo de dados, siga estas etapas:

    1. No campo **Nome**, inserir **TotalInvoicedAmount**.
    2. No campo **Tipo de item**, selecione **Real**.
    3. Selecione **Adicionar** para adicionar o novo nó.

8. Selecionar **Novo** para adicionar um novo nó aninhado ao nó de **Transporte** recém-adicionado. Na caixa de diálogo suspensa para adicionar um nó de modelo de dados, siga estas etapas:

    1. No campo **Nome**, inserir **NumberOfTransactions**.
    2. No campo **Tipo de item**, selecione **Inteiro**.
    3. Selecione **Adicionar** para adicionar o novo nó.

9. Selecionar **Novo** para adicionar um novo nó aninhado ao nó de **Transporte** recém-adicionado. Na caixa de diálogo suspensa para adicionar um nó de modelo de dados, siga estas etapas:

    1. No campo **Nome**, inserir **Transação**.
    2. No campo **Tipo de item**, selecione **Lista de registros**.
    3. Selecione **Adicionar** para adicionar o novo nó.

10. Para o nó da **Transação** que você acabou de adicionar, na guia rápida **Nó**, selecionar **Alternar referência do item**.
11. Na caixa de diálogo **Alternar referência de itens**, na árvore modelo de dados, selecionar **CommodityRecord**. Em seguida, selecione **OK**.

![Modelo de dados configurado no designer de modelos de dados de ER.](./media/er-groupby-data-sources-configure-data-model.png)

### <a name="complete-the-design-of-a-custom-data-model"></a>Concluir o design do modelo de dados personalizado

Seguir as etapas em [Concluir o design do modelo de dados](er-quick-start3-customize-report.md#add-a-custom-data-model-configuration) para concluir o design do modelo de dados **do modelo Intrastat (Litware)** derivado.

### <a name="create-a-new-model-mapping-configuration"></a>Criar uma nova configuração de mapeamento de modelo

Seguir as etapas em [Criar uma nova configuração de modelo de mapeamento](er-quick-start1-new-solution.md#CreateModelMapping) para adicionar manualmente uma nova configuração do modelo de mapeamento do ER **para o mapeamento de amostra Intrastat** para a configuração do **modelo Intrastat** derivada.

### <a name="add-a-new-model-mapping-component"></a>Adicionar um novo componente de mapeamento de modelo

1. Acesse **Administração da organização** \> **Relatório eletrônico** \> **Configurações**.
2. Na página **Configurações**, na árvore de configuração, expandir a configuração **Modelo intrastat**.
3. Selecionar a configuração **Mapeamento de amostra de intrastat**.
4. Selecione **Designer** para abrir a lista de mapeamentos.
5. Selecionar **Excluir** para remover o componente de mapeamento existente.
6. Selecionar **Novo** para adicionar um novo componente de mapeamento.
7. No campo **Definição**, selecionar **Intrastat**.
8. No campo **Nome**, inserir **Mapeamento intrastat**.
9. Selecionar **Designer** para configurar o novo mapeamento.

### <a name="design-the-added-model-mapping-component"></a>Criar o componente de mapeamento de modelo adicionado

#### <a name="add-a-data-source-to-access-an-application-table"></a><a name="AddMmDataSource1"></a>Adicionar uma fonte de dados para acessar uma tabela de aplicativo

Configurar uma fonte de dados para acessar as tabelas do aplicativo que contêm detalhes das transações intrastat.

1. Na página **Designer de mapeamento de modelo**, no painel **Tipos de fontes de dados**, selecione **Dynamics 365 for Operations\\Registros de tabela**.
2. No painel **Fontes de dados**, selecionar **Adicionar raiz** para adicionar uma nova fonte de dados que será usada para acessar a tabela **Intrastat**. Cada registro na tabela **Intrastat** representa uma única transação Intrastat.
3. Na caixa de diálogo **Propriedades da fonte de dados**, no campo **Nome**, inserir **Transação**.
4. No campo **Tabela**, inserir **Intrastat**.
5. Selecione **OK** para adicionar a nova fonte de dados.

#### <a name="add-a-data-source-to-group-intrastat-transactions"></a><a name="AddMmDataSource2"></a>Adicionar uma fonte de dados ao grupo transações intrastat

Configurar uma fonte de dados **GroupBy** para agrupar transações intrastat e computar funções agregadas.

1. Na página **Designer de mapeamento de modelo**, no painel **Tipos de fontes de dados**, selecionar **Funções\\Agrupar por**.
2. No painel **Fontes de dados**, selecionar **Adicionar raiz** para adicionar uma nova fonte de dados que será usada para agrupar transações intrastat e computar funções agregadas.
3. Na caixa de diálogo **Propriedades da fonte de dados**, no campo **Nome**, inserir **TransportRecord**.
4. Selecionar **Editar agrupar por** para configurar condições de agrupamento.
5. Na página **Editar parâmetros de Agrupar por** na lista de fontes de dados do painel à direita, selecionar a fonte de dados **Transação** e expandir a opção.
6. Selecionar **"Adicionar campo à opção" \> "Qual agrupar"** para indicar que a fonte de dados **"Transação"** está selecionada como a fonte de dados base <a name="BaseDataSource">para a fonte de dados</a> configurada **GroupBy**. Os registros da fonte de dados de **Transação** serão agrupados, e os valores de campo dessa fonte de dados serão usados para cálculos em funções agregadas.
7. Selecionar o campo **"Transação\Transporte"** e selecionar **"Adicionar campo ao \> campo "Agrupado"** para indicar que o campo **"Transporte"** da fonte de dados base é selecionado como o critério de agrupamento <a name="GroupingFields">para</a> a fonte de dados **"GroupBy"** configurada. Em outras palavras, os registros da fonte de dados da **Transação** serão agrupados com base no valor do campo **Transporte**. Cada registro da fonte de dados **GroupBy** configurada representará um único código de transporte que foi encontrado nos registros da fonte de dados base.
8. Selecionar o campo **Transaction\AmountMST** e seguir estas etapas:

    1. Selecionar **Adicionar campo para \> Agregar campos** para indicar que uma <a name="AggregateFunctions">função agregada</a> será calculada para este campo.
    2. No painel **Agregações**, no registro que foi adicionado para o campo selecionado **Transaction\AmountMST**, no campo **Método**, selecionar a função **Soma**.
    3. No campo opcional **Nome**, inserir **TotalInvoicedAmount**.

    Essas configurações especificam que, para cada grupo de transporte, o valor total do campo **Transaction\AmountMST** será calculado.

9. Selecionar o campo **Transação\Recld** e seguir estas etapas:

    1. Selecionar **Adicionar campo para \> agregar campos** para indicar que uma função agregada será calculada para este campo.
    2. No painel **Agregações**, no registro que foi adicionado para o campo selecionado **Transação\Recld**, no campo **Método**, selecionar a função **Computar**.
    3. No campo opcional **Nome**, inserir **NumberOfTransactions**.

    Essas configurações especificam que, para cada grupo de transporte, o número de transações no grupo será calculado.

10. Selecione **Salvar**.
11. Revisar os parâmetros de execução <a name="ExecutionLocation">da</a> fonte de dados editável. Observe que a **Detecção automática** foi selecionada automaticamente no campo **Local de execução** e o campo **Execução em** contém o valor **SQL**. Essas configurações especificam que a fonte de dados base de **Transação** selecionada é consultável no momento e você pode executar a fonte de dados **GroupBy** editável no nível do banco de dados.
12. Abrir a opção de pesquisa para o campo **Local de execução** para revisar a lista de valores disponíveis. Observar que você pode selecionar **Consulta** ou **Na memória** para forçar que essa fonte de dados **GroupBy** seja executada no nível do banco do dados ou na memória do servidor de aplicativos.
13. Selecionar **Salvar** e fechar a página **Editar grupos por parâmetros**.
14. Selecionar **OK** para concluir as configurações da fonte de dados **GroupBy**.

#### <a name="bind-the-groupby-data-source-to-data-model-fields"></a><a name="AddMmBindings"></a>Vincular fontes de dados "GroupBy" a campos do modelo de dados

Vincular fontes de dados configuradas aos campos do modelo de dados para especificar como o modelo de dados será preenchido com os dados do aplicativo em runtime.

1. Na página **Designer de mapeamento de modelo**, no painel **Modelo de dados**, expandir o nó **Transportar**.
2. No painel **Fontes de dados**, expandir a fonte de dados **TransportRecord**.
3. Adicionar uma associação para expor a lista de grupos de transporte detectados:

    1. No painel **Modelo de dados**, selecionar o item **Transporte**.
    2. No painel **Fontes de dados**, selecionar a fonte de dados **TransportRecord**.
    3. Selecione **Associar**.

4. Adicionar uma associação para expor o código de transporte para cada grupo de transporte detectado:

    1. Selecionar o item de modelo de dados **Transport.Code**.
    2. Selecionar o campo agrupado **TransportRecord.grouped.TransportMode**.
    3. Selecione **Associar**.

5. Adicionar uma associação para expor os valores das funções agregadas calculadas para cada grupo de transporte descoberto:

    1. Selecionar o item de modelo de dados **Transport.NumberOfTransactions**.
    2. Selecionar o campo agregado **TransportRecord.aggregated.NumberOfTransactions**.
    3. Selecione **Associar**.
    4. Selecionar o item de modelo de dados **Transport.TotalInvoicedAmount**.
    5. Selecionar o campo agregado **TransportRecord.aggregated.TotalInvoicedAmount**.
    6. Selecione **Associar**.

6. Adicionar uma associação para expor registros de transação que pertencem a cada grupo de transporte descoberto:

    1. Selecionar o item de modelo de dados **Transport.Transaction**.
    2. Selecionar o campo **TransportRecord.lines**.
    3. Selecione **Associar**.

    Você pode continuar a configurar associações para os itens aninhados do modelo de dados **Transport.Transaction** e o campo de fonte de dados **TransportRecord.lines** para expor, no runtime, detalhes das transações intrastat que pertencem a cada grupo de transporte descoberto.

![Mapeamento de modelo configurado no designer de mapeamento de modelos de ER.](./media/er-groupby-data-sources-configure-model-mapping.png)

### <a name="debug-the-added-model-mapping-component"></a>Depurar o componente de mapeamento de modelo adicionado

Uso do [depurador de fonte de dados de ER](er-debug-data-sources.md) para testar o mapeamento do modelo configurado.

1. Na página **Designer de mapeamento do modelo** selecionar **Iniciar depuração**.
2. Na página **Depurar fontes de dados** no painel à esquerda, selecionar a fonte de dados **TransportRecord** e selecionar **Ler todos os registros**.
3. Expandir a fonte de dados **TransportRecord** e seguir estas etapas:

    1. Selecionar a fonte de dados **TransportRecord.grouped.TransportMode**.
    2. Selecione **Obter valor**.
    3. Selecionar a fonte de dados **TransportRecord.grouped.NumberOfTransactions**.
    4. Selecione **Obter valor**.
    5. Selecionar a fonte de dados **TransportRecord.grouped.TotalInvoicedAmount**.
    6. Selecione **Obter valor**.

4. No painel à direita, selecionar **Expandir tudo**.

A fonte de dados **TransportRecord** expõe dois registros e apresenta dois códigos de transporte. Para cada código de transporte, o número de transações e o valor total faturado são calculados.

> [!NOTE]
> A abordagem de "leitura lenta" é usada quando uma fonte de dados **"GroupBy"** é chamada para otimizar chamadas de banco de dados. Portanto, alguns dos valores de campo em uma fonte de dados **GroupBy** são calculados no depurador da fonte de dados ER somente quando são limitados a campos de modelo de dados.

![Resultados da depuração da fonte de dados na página Depurar fontes de dados.](./media/er-groupby-data-sources-debug-datasource.png)

## <a name="frequently-asked-questions"></a>Perguntas frequentes

### <a name="is-there-any-way-to-calculate-grand-totals-when-the-group-totals-are-calculated"></a>Existe alguma forma de calcular totais gerais quando os totais de grupo são calculados?

Sim. Para calcular totais gerais, configurar outra fonte de dados **GroupBy** na qual a fonte de dados **GroupBy** configurada anteriormente seja usada como a fonte de dados base. A ilustração a seguir mostra a fonte de dados **Totais** do tipo **GroupBy** que é usada para calcular a função **SOMA** agregada, com base na agregação **SOMA** da fonte de dados **TransportRecord** do tipo **GroupBy**.

![Fonte de dados totais no designer de mapeamento do modelo de ER.](./media/er-groupby-data-sources-configure-model-mapping2.png)

A ilustração a seguir mostra os resultados da depuração da fonte de dados **Totais**.

![Resultados da depuração da fonte de dados Totais na página Depurar fontes de dados.](./media/er-groupby-data-sources-debug-datasource2.png)

## <a name="additional-resources"></a>Recursos adicionais

- [Visão geral do Relatório Eletrônico](general-electronic-reporting.md)
- [Depurar fontes de dados de um formato de relatório eletrônico executado para analisar o fluxo de dados e a transformação](er-debug-data-sources.md)
- [Usar fontes de dados de COLETA DE DADOS em formatos de relatório eletrônico](er-data-collection-data-sources.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
