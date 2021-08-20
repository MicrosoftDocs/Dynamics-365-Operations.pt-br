---
title: Solução de problemas de desempenho nas configurações ER
description: Este tópico explica como encontrar e corrigir problemas de desempenho nas configurações de Relatórios Eletrônicos (ER).
author: NickSelin
ms.date: 06/08/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERModelMappingDesigner, EROperationDesigner, ERFormatMappingRunJobTable, ERParameters, ERSolutionTable
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: ''
ms.search.region: Global
ms.author: maximbel
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: b5f5308f171b6cd4224debec897dbde133e6d8424673aabfab51e6b83b9014e2
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6744377"
---
# <a name="troubleshooting-performance-issues-in-er-configurations"></a>Solução de problemas de desempenho nas configurações ER

Este tópico explica como encontrar e solucionar problemas de desempenho nas [configurações](general-electronic-reporting.md#Configuration) de [Relatórios Eletrônicos](general-electronic-reporting.md) (ER).

Normalmente, a investigação de desempenho consiste em várias etapas.

1. [Coletar](#collecting-data) dados.
2. Analise os dados coletados.
3. Com base nos resultados da análise, use as configurações ER para [fazer alterações](#making-changes) ou decida coletar mais dados.

## <a name="troubleshooting"></a>Solução de problemas

### <a name="analyze-execution-time"></a>Analisar o tempo de execução

O tempo de execução pode depender de fatores imprevisíveis, como outras tarefas que estão em execução no mesmo ambiente e armazenamento em cache que usa dados quando chamado pela primeira vez. Portanto, você deve repetir a execução e a medição várias vezes.

Às vezes, os problemas de desempenho não são causados por uma configuração do formato de ER que é usado para os relatórios. Em vez disso, eles são causados pelo código X++ que é usado para abrir essa configuração de formato de ER.

1. Na [Central de ações](#infolog-time) ou no [log de registros](#event-log-time), veja o tempo de execução do relatório.
2. Compare o tempo de execução do relatório com o tempo total de execução no cenário.
3. Se o tempo de execução do relatório for muito menor do que o tempo total de execução, considere a quantidade de dados que o relatório processa:

    - Se o relatório processar uma pequena quantidade de dados, o problema pode envolver o tempo de carregamento da configuração.
    - Se o relatório processar uma grande quantidade de dados, o problema pode envolver o pré-processamento de X++. Use o [Analisador de Rastreamento](#analyze-trace-parser-trace) para analisar este caso.

    Para outros casos, consulte as próximas seções.

4. Execute vários testes que envolvem diferentes quantidades de dados para determinar como o tempo de execução depende da quantidade de dados.

### <a name="analyze-trace-parser-traces"></a><a name="analyze-trace-parser-trace"></a>Analisar rastreamentos do Analisador de Rastreamento

Prepare um pequeno exemplo ou colete vários rastreamentos durante partes aleatórias da geração de relatórios.

Em seguida, no [Analisador de Rastreamento](#trace-parser), faça uma análise padrão de baixo para cima e responda às seguintes perguntas:

- Quais são os principais métodos em termos de consumo de tempo?
- Que parte do tempo global esses métodos usam?

Responda às mesmas perguntas para consultas.

Se você vir que os métodos estão prefixados com "ER", passe para a próxima seção.

Se você vir que os métodos ou consultas se originaram no pacote de aplicativos, considere otimizações genéricas (por exemplo, criar índices).

Analise o número de chamadas. Se o número for significativamente maior do que o esperado, considere armazenar em cache os nódulos correspondentes da configuração.

### <a name="analyze-database-calls"></a><a name="analyze-database-calls"></a>Analisar chamadas de banco de dados

Prepare um exemplo que tenha uma pequena quantidade de dados, para que você possa coletar um [rastreamento de ER](#electronic-reporting-traces).

Em seguida, abra o rastreamento no designer de mapeamento de modelo de ER, e veja a parte inferior da página. Responda às seguintes perguntas:

- Há alguma duplicação de consulta? Se houver, considere uma das seguintes correções:

    - [Use o armazenamento em cache](#use-caching) se você achar que há várias chamadas dentro de um registro pai.
    - [Use um campo calculado, parametrizado e armazenado em cache](#cached-parameterized) se você achar que há chamadas para o mesmo registro dentro de diferentes registros.
    - [Use uma fonte de dados **JOIN**](#use-join-datasource) se você tiver que ler para um número significativo de registros diferentes de um banco de dados.

- O número de consultas e registros obtidos corresponde à quantidade total de dados? Por exemplo, se um documento tem 10 linhas, as estatísticas mostram que o relatório extrai 10 linhas ou 1.000 linhas? Se você tiver um número significativo de registros obtidos, considere uma das seguintes correções:

    - [Use a função **FILTER** em vez da função **WHERE**](#filter) para processar dados no lado do SQL Server.
    - Use o armazenamento em cache para evitar obter os mesmos dados.
    - [Use funções dos dados coletados](#collected-data) para evitar obter os mesmos dados para resumo.

### <a name="analyze-perfview-traces"></a>Analisar rastreamentos do PerfView

[PerfView](#perfview) é uma ferramenta para desenvolvedores experientes. Para obter informações mais detalhadas sobre as etapas seguintes, consulte [Noções básicas sobre a investigação do tempo do relógio de parede](https://channel9.msdn.com/Series/PerfView-Tutorial/Tutorial-12-Wall-Clock-Time-Investigation-Basics).

1. Colete um rastreamento usando o tempo do thread.
2. Inclua apenas pilhas que usam **runUnattended** para filtrar somente o thread que tenha a execução da configuração. (Adicione **runUnattended** à caixa de entrada **IncPats**.)
3. Dobre toda a CPU, rede e o tempo bloqueado.
4. Carregue as [predefinições do ER para o PerfView](https://download.microsoft.com/download/2/d/0/2d037b0f-ffd1-4d65-b64f-fcdf51f2c81f/ER_PerfViewPresets.xml).
5. Selecione **ER** \> **Outra predefinição**.
6. Veja os nomes:

    - Você provavelmente verá o código da plataforma que consome mais tempo.
    - Você pode tocar duas vezes (ou clicar duas vezes) e subir até **receptores de chamada**.

        Se você encontrar classes que tenham o prefixo "ERExpression" e se forem funções relacionadas às fórmulas, você poderá presumir o nome da função com base no nome da classe, e você poderá examinar o repositório ER para visualizar os atributos.

### <a name="fixes"></a>Correções

- Se você vir que a maior parte do tempo da CPU é consumido por consultas, tente reduzir o número de consultas:

    - [Analise o rastreamento de ER](#analyze-database-calls) para ver se não há consultas duplicadas.
    - Veja quantos registros são obtidos e avalie quantos dados devem teoricamente ser obtidos.

- Se você vir que a maior parte do tempo da CPU é consumido pelas funções que são usadas, tente encontrar o lugar na configuração que consome mais recursos.
- Se você vir que a maior parte do tempo da CPU é consumido por funções de coleta de dados, considere substituí-los por *Agrupar por SQL* ao lado do mapeamento do modelo.

### <a name="collecting-data"></a><a name="collecting-data"></a>Coletando dados

Dependendo do seu ambiente, existem várias maneiras disponíveis para coletar dados:

- Obtenha o tempo total de execução:

    - A partir da Central de ações
    - A partir do log de eventos

- Perfil da execução:

    - Usando ferramentas de ER
    - Usando o Analisador de Rastreamento
    - Usando o PerfView

#### <a name="collecting-data-in-a-production-environment"></a>Coletando dados em um ambiente de produção

Às vezes, os problemas só podem ser reproduzidos em um ambiente de produção. Os dados podem ser coletados da seguintes maneiras:

- Usando rastreamentos do [Analisador de Rastreamento](../perf-test/trace-trace-tutorial.md)
- Usando rastreamentos da [execução de ER](trace-execution-er-troubleshoot-perf.md)
- Usando o tempo total de execução

#### <a name="collecting-data-in-a-development-environment"></a>Coletando dados em um ambiente de desenvolvimento

Além das ferramentas que podem ser usadas em um ambiente de produção, existem várias ferramentas que você pode usar em um ambiente de desenvolvimento:

- Log de eventos (Microsoft-Dynamics-ElectronicReporting). Esse log pode fornecer a você o tempo total de execução.
- Ferramentas .NET comuns, como o PerfView.

Além disso, um ambiente de desenvolvimento fornece a você mais flexibilidade para experimentar. Por exemplo, você pode desativar partes de relatórios para ver como o tempo de execução é afetado.

### <a name="tools"></a><a name="tools"></a>Ferramentas

#### <a name="execution-time-in-the-action-center"></a><a name="infolog-time"></a>Tempo de execução na Central de ações

O ER pode mostrar o tempo de execução da configuração na Central de ações. Essa opção funciona somente para um usuário específico e uma empresa específica, e somente para sessões interativas. Para disponibilizar esse recurso, siga estas etapas:

1. Acesse **Administração da organização** \> **Relatório eletrônico** \> **Configurações**.
2. Na página **Configurações**, no Painel Ação, na guia **Configurações**, no grupo **Configurações avançadas**, selecione **Parâmetros de usuário**.
3. Na caixa de diálogo **Parâmetros do usuário**, defina a opção **Mostrar tempo de geração do arquivo** como **Sim**.

#### <a name="execution-time-in-the-event-log"></a><a name="event-log-time"></a>Tempo de execução no log de eventos

1. Abra o Visualizador de Eventos do Windows.
2. Em **Logs de Aplicativos e Serviços**, abra **Microsoft-Dynamics-ElectronicReporting/Operational**.
3. Procure eventos **FormatMapingRun**, em que **EventID=2**, porque esses eventos contêm as informações sobre o tempo decorrido.

#### <a name="trace-parser-traces"></a><a name="trace-parser"></a>Rastreamentos do Analisador de Rastreamento 

Como o ER é implementado em X++, você pode usar ferramentas X++ comuns para analisar o desempenho. Para obter mais informações, consulte [Obter rastreamentos usando o Analisador de Rastreamento](../perf-test/trace-trace-tutorial.md).

Há algumas limitações para essa abordagem. Como parte do ER é implementado em C#, nem todos os detalhes estarão disponíveis. No entanto, você poderá exibir os detalhes do uso de dados. Além disso, longas execuções de relatórios podem exceder as limitações de armazenamento de rastreamentos.

#### <a name="er-traces"></a><a name="electronic-reporting-traces"></a>Rastreamentos de ER

O ER pode coletar seus próprios rastreamentos, e tem ferramentas de visualização e análise para esses rastreamentos. Para obter mais informações, consulte [Rastrear a execução de formatos de ER para solucionar problemas de desempenho](trace-execution-er-troubleshoot-perf.md).

#### <a name="perfview"></a><a name="perfview"></a>PerfView

Como X++ e o ER são implementados na plataforma .NET, você pode usar ferramentas comuns .NET. Por exemplo, você pode usar a ferramenta gratuita [PerfView](https://github.com/Microsoft/perfview).

Você também pode coletar dados a partir da linha de comando. Por exemplo, o script a seguir do Windows PowerShell coleta o tempo de execução até que qualquer execução de formato seja interrompido na máquina.

```powershell
c:\programs\PerfView collect "e:\traces\$(date -format "ddMMyyyy_hhmm").etl" `
    -CircularMB:20000 -ThreadTime `
    -NoNGenRundown `
    -StopOnEtwEvent:Microsoft-Dynamics-ElectronicReporting/FormatMappingRun/Stop
```

Há algumas limitações para essa abordagem. Você deve ter acesso administrativo ao computador. Além disso, você deve ser um desenvolvedor experiente, porque há uma curva de aprendizado acentuada.

### <a name="making-changes"></a><a name="making-changes"></a>Fazendo alterações

#### <a name="use-caching"></a><a name="use-caching"></a>Usar armazenamento em cache

Embora o armazenamento em cache reduza a quantidade de tempo necessário para obter dados novamente, isso tem um custo de memória. Use o armazenamento em cache nos casos em que a quantidade de dados obtidos não seja muito grande. Para obter mais informações e um exemplo que mostre como usar o armazenamento em cache, consulte [Melhorar o mapeamento do modelo com base em informações do rastreamento de execução](trace-execution-er-troubleshoot-perf.md#improve-the-model-mapping-based-on-information-from-the-execution-trace).

#### <a name="use-a-cached-parameterized-calculated-field"></a><a name="cached-parameterized"></a>Usar um campo calculado armazenamento em cache e parametrizado

Às vezes, os valores devem ser pesquisados repetidamente. Exemplos incluem nomes de contas e números de contas. Para ajudar a economizar tempo, você pode criar um campo calculado que tenha parâmetros no nível superior e, em seguida, adicionar o campo ao armazenamento em cache.

Recomendamos que você use essa abordagem somente quando o tamanho dos dados armazenados em cache for pequeno. Para obter mais informações, consulte [Melhorar o desempenho de soluções ER adicionando fontes de dados de CAMPOS CALCULADOS parametrizados](er-calculated-field-ds-performance.md).

#### <a name="use-a-join-data-source"></a><a name="use-join-datasource"></a>Usar uma fonte de dados JOIN

Uma fonte de dados **JOIN** permite a obtenção de vários registros conectados por uma consulta. Não é necessário usar uma consulta separada para obter cada registro conectado. Por exemplo, se você tiver 1.000 linhas e obter dados de itens para cada linha por relação, você terá 1.001 consultas (= 1.000 + 1). Se usar uma fonte de dados **JOIN** você usará apenas uma consulta para obter os mesmos dados. Para obter mais informações, consulte [Usar as fontes de dados JOIN em mapeamentos do modelo de ER para obter dados de várias tabelas de aplicativos](er-join-data-sources.md).

#### <a name="use-the-filter-function-instead-of-the-where-function"></a><a name="filter"></a>Usar a função FILTER em vez da função WHERE

A função **[FILTER](er-functions-list-filter.md)** executa as condições no SQL Server, enquanto a função **WHERE** obtém todos os dados da lista, um registro por vez , e aplica a condição para cada registro. Por exemplo, você deseja selecionar um registro de 1.000 registros. Se você usar **WHERE**, todos os 1.000 registros serão obtidos. No entanto, se você usar **FILTER**, exatamente um registro será obtido. **FILTER** também pode usar índices no lado do banco de dados.

#### <a name="using-collected-data-functions-or-an-accumulated-data-data-source"></a><a name="collected-data"></a>Usando funções de dados coletados ou uma fonte de dados acumulados

Se a sua configuração tiver um componente *agrupar por* que resume dados obtidos anteriormente por relatório, o componente obterá todos os dados novamente. Ao usar as funções de dados coletados, você permite que o ER acumule dados durante a primeira obtenção. Para obter mais informações, consulte [ER Configurar o formato para contagem e soma](tasks/er-format-counting-summing-2.md).

#### <a name="rewrite-parts-of-the-configuration-in-x"></a>Reescrever partes da configuração em X++

O ER oferece suporte a métodos de chamada de tabelas e classes, incluindo extensões. Considere reescrever partes do mapeamento do modelo em X++ para ajudar a melhorar o desempenho.

O ER pode consumir dados das seguintes fontes:

- Classes (fontes de dados de **objetos** e **classes**)
- Tabelas (fontes de dados de **tabelas** e **registros de tabela**)

A [API de ER](er-apis-app73.md#how-to-access-internal-x-objects-by-using-erobjectsfactory) também fornece uma maneira de enviar dados pré-calculados a partir do código de chamada. O pacote de aplicativos contém vários exemplos dessa abordagem.
