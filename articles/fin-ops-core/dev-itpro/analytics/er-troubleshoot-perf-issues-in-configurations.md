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
ms.openlocfilehash: d77c2aad904ba911ac19009d6a981ea4153aaa48
ms.sourcegitcommit: 60afcd85b3b5b9e5e8981ebbb57c0161cf05e54b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/09/2021
ms.locfileid: "6216856"
---
# <a name="troubleshooting-performance-issues-in-er-configurations"></a><span data-ttu-id="24cf1-103">Solução de problemas de desempenho nas configurações ER</span><span class="sxs-lookup"><span data-stu-id="24cf1-103">Troubleshooting performance issues in ER configurations</span></span>

<span data-ttu-id="24cf1-104">Este tópico explica como encontrar e solucionar problemas de desempenho nas [configurações](general-electronic-reporting.md#Configuration) de [Relatórios Eletrônicos](general-electronic-reporting.md) (ER).</span><span class="sxs-lookup"><span data-stu-id="24cf1-104">This topic explains how to find and solve performance issues in [Electronic reporting](general-electronic-reporting.md) (ER) [configurations](general-electronic-reporting.md#Configuration).</span></span>

<span data-ttu-id="24cf1-105">Normalmente, a investigação de desempenho consiste em várias etapas.</span><span class="sxs-lookup"><span data-stu-id="24cf1-105">Typically, performance investigation consists of several steps.</span></span>

1. <span data-ttu-id="24cf1-106">[Coletar](#collecting-data) dados.</span><span class="sxs-lookup"><span data-stu-id="24cf1-106">[Collect](#collecting-data) data.</span></span>
2. <span data-ttu-id="24cf1-107">Analise os dados coletados.</span><span class="sxs-lookup"><span data-stu-id="24cf1-107">Analyze the collected data.</span></span>
3. <span data-ttu-id="24cf1-108">Com base nos resultados da análise, use as configurações ER para [fazer alterações](#making-changes) ou decida coletar mais dados.</span><span class="sxs-lookup"><span data-stu-id="24cf1-108">Based on the results of the analysis, use ER configurations to [make changes](#making-changes), or decide to collect more data.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="24cf1-109">Solução de problemas</span><span class="sxs-lookup"><span data-stu-id="24cf1-109">Troubleshooting</span></span>

### <a name="analyze-execution-time"></a><span data-ttu-id="24cf1-110">Analisar o tempo de execução</span><span class="sxs-lookup"><span data-stu-id="24cf1-110">Analyze execution time</span></span>

<span data-ttu-id="24cf1-111">O tempo de execução pode depender de fatores imprevisíveis, como outras tarefas que estão em execução no mesmo ambiente e armazenamento em cache que usa dados quando chamado pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="24cf1-111">Execution time can depend on unpredictable factors, such as other tasks that are running in the same environment and caching that uses data when it's called for the first time.</span></span> <span data-ttu-id="24cf1-112">Portanto, você deve repetir a execução e a medição várias vezes.</span><span class="sxs-lookup"><span data-stu-id="24cf1-112">Therefore, you should repeat the execution and measurement several times.</span></span>

<span data-ttu-id="24cf1-113">Às vezes, os problemas de desempenho não são causados por uma configuração do formato de ER que é usado para os relatórios.</span><span class="sxs-lookup"><span data-stu-id="24cf1-113">Sometimes, performance issues aren't caused by an ER format configuration that is used for reporting.</span></span> <span data-ttu-id="24cf1-114">Em vez disso, eles são causados pelo código X++ que é usado para abrir essa configuração de formato de ER.</span><span class="sxs-lookup"><span data-stu-id="24cf1-114">Instead, they are caused by the X++ code that is used to open that ER format configuration.</span></span>

1. <span data-ttu-id="24cf1-115">Na [Central de ações](#infolog-time) ou no [log de registros](#event-log-time), veja o tempo de execução do relatório.</span><span class="sxs-lookup"><span data-stu-id="24cf1-115">In either the [Action center](#infolog-time) or the [event log](#event-log-time), look at the execution time of the report.</span></span>
2. <span data-ttu-id="24cf1-116">Compare o tempo de execução do relatório com o tempo total de execução no cenário.</span><span class="sxs-lookup"><span data-stu-id="24cf1-116">Compare the execution time of the report with the total execution time in the scenario.</span></span>
3. <span data-ttu-id="24cf1-117">Se o tempo de execução do relatório for muito menor do que o tempo total de execução, considere a quantidade de dados que o relatório processa:</span><span class="sxs-lookup"><span data-stu-id="24cf1-117">If the execution time of the report is much less than the total execution time, consider the amount of data that the report processes:</span></span>

    - <span data-ttu-id="24cf1-118">Se o relatório processar uma pequena quantidade de dados, o problema pode envolver o tempo de carregamento da configuração.</span><span class="sxs-lookup"><span data-stu-id="24cf1-118">If the report processes a small amount of data, the issue might involve the loading time of the configuration.</span></span>
    - <span data-ttu-id="24cf1-119">Se o relatório processar uma grande quantidade de dados, o problema pode envolver o pré-processamento de X++.</span><span class="sxs-lookup"><span data-stu-id="24cf1-119">If the report processes a large amount of data, the issue might involve preprocessing X++.</span></span> <span data-ttu-id="24cf1-120">Use o [Analisador de Rastreamento](#analyze-trace-parser-trace) para analisar este caso.</span><span class="sxs-lookup"><span data-stu-id="24cf1-120">Use [Trace parser](#analyze-trace-parser-trace) to analyze this case.</span></span>

    <span data-ttu-id="24cf1-121">Para outros casos, consulte as próximas seções.</span><span class="sxs-lookup"><span data-stu-id="24cf1-121">For other cases, see the next sections.</span></span>

4. <span data-ttu-id="24cf1-122">Execute vários testes que envolvem diferentes quantidades de dados para determinar como o tempo de execução depende da quantidade de dados.</span><span class="sxs-lookup"><span data-stu-id="24cf1-122">Run multiple tests that involve different amounts of data to determine how the execution time depends on the amount of data.</span></span>

### <a name="analyze-trace-parser-traces"></a><a name="analyze-trace-parser-trace"></a><span data-ttu-id="24cf1-123">Analisar rastreamentos do Analisador de Rastreamento</span><span class="sxs-lookup"><span data-stu-id="24cf1-123">Analyze Trace parser traces</span></span>

<span data-ttu-id="24cf1-124">Prepare um pequeno exemplo ou colete vários rastreamentos durante partes aleatórias da geração de relatórios.</span><span class="sxs-lookup"><span data-stu-id="24cf1-124">Prepare a small example, or collect several traces during random parts of the report generation.</span></span>

<span data-ttu-id="24cf1-125">Em seguida, no [Analisador de Rastreamento](#trace-parser), faça uma análise padrão de baixo para cima e responda às seguintes perguntas:</span><span class="sxs-lookup"><span data-stu-id="24cf1-125">Then, in [Trace parser](#trace-parser), do a standard bottom-to-up analysis, and answer the following questions:</span></span>

- <span data-ttu-id="24cf1-126">Quais são os principais métodos em termos de consumo de tempo?</span><span class="sxs-lookup"><span data-stu-id="24cf1-126">What are the top methods in terms of time consumption?</span></span>
- <span data-ttu-id="24cf1-127">Que parte do tempo global esses métodos usam?</span><span class="sxs-lookup"><span data-stu-id="24cf1-127">What part of the overall time do those methods use?</span></span>

<span data-ttu-id="24cf1-128">Responda às mesmas perguntas para consultas.</span><span class="sxs-lookup"><span data-stu-id="24cf1-128">Answer the same questions for queries.</span></span>

<span data-ttu-id="24cf1-129">Se você vir que os métodos estão prefixados com "ER", passe para a próxima seção.</span><span class="sxs-lookup"><span data-stu-id="24cf1-129">If you see that methods are prefixed with "ER," move on to the next section.</span></span>

<span data-ttu-id="24cf1-130">Se você vir que os métodos ou consultas se originaram no pacote de aplicativos, considere otimizações genéricas (por exemplo, criar índices).</span><span class="sxs-lookup"><span data-stu-id="24cf1-130">If you see that methods or queries originated in the application suite, consider generic optimizations (for example, create indexes).</span></span>

<span data-ttu-id="24cf1-131">Analise o número de chamadas.</span><span class="sxs-lookup"><span data-stu-id="24cf1-131">Analyze the number of calls.</span></span> <span data-ttu-id="24cf1-132">Se o número for significativamente maior do que o esperado, considere armazenar em cache os nódulos correspondentes da configuração.</span><span class="sxs-lookup"><span data-stu-id="24cf1-132">If the number is significantly higher than expected, consider caching the corresponding nodes of the configuration.</span></span>

### <a name="analyze-database-calls"></a><a name="analyze-database-calls"></a><span data-ttu-id="24cf1-133">Analisar chamadas de banco de dados</span><span class="sxs-lookup"><span data-stu-id="24cf1-133">Analyze database calls</span></span>

<span data-ttu-id="24cf1-134">Prepare um exemplo que tenha uma pequena quantidade de dados, para que você possa coletar um [rastreamento de ER](#electronic-reporting-traces).</span><span class="sxs-lookup"><span data-stu-id="24cf1-134">Prepare an example that has a small amount of data, so that you can collect an [ER trace](#electronic-reporting-traces).</span></span>

<span data-ttu-id="24cf1-135">Em seguida, abra o rastreamento no designer de mapeamento de modelo de ER, e veja a parte inferior da página.</span><span class="sxs-lookup"><span data-stu-id="24cf1-135">Then open the trace in the ER model mapping designer, and look at the bottom of the page.</span></span> <span data-ttu-id="24cf1-136">Responda às seguintes perguntas:</span><span class="sxs-lookup"><span data-stu-id="24cf1-136">Answer the following questions:</span></span>

- <span data-ttu-id="24cf1-137">Há alguma duplicação de consulta?</span><span class="sxs-lookup"><span data-stu-id="24cf1-137">Is there any query duplication?</span></span> <span data-ttu-id="24cf1-138">Se houver, considere uma das seguintes correções:</span><span class="sxs-lookup"><span data-stu-id="24cf1-138">If there is, consider one of the following fixes:</span></span>

    - <span data-ttu-id="24cf1-139">[Use o armazenamento em cache](#use-caching) se você achar que há várias chamadas dentro de um registro pai.</span><span class="sxs-lookup"><span data-stu-id="24cf1-139">[Use caching](#use-caching) if you think that there are several calls inside one parent record.</span></span>
    - <span data-ttu-id="24cf1-140">[Use um campo calculado, parametrizado e armazenado em cache](#cached-parameterized) se você achar que há chamadas para o mesmo registro dentro de diferentes registros.</span><span class="sxs-lookup"><span data-stu-id="24cf1-140">[Use a cached, parameterized calculated field](#cached-parameterized) if you think that there are calls to the same record inside different records.</span></span>
    - <span data-ttu-id="24cf1-141">[Use uma fonte de dados **JOIN**](#use-join-datasource) se você tiver que ler para um número significativo de registros diferentes de um banco de dados.</span><span class="sxs-lookup"><span data-stu-id="24cf1-141">[Use a **JOIN** data source](#use-join-datasource) if you have to read to a substantial number of different records from a database.</span></span>

- <span data-ttu-id="24cf1-142">O número de consultas e registros obtidos corresponde à quantidade total de dados?</span><span class="sxs-lookup"><span data-stu-id="24cf1-142">Does the number of queries and fetched records correspond to the overall amount of data?</span></span> <span data-ttu-id="24cf1-143">Por exemplo, se um documento tem 10 linhas, as estatísticas mostram que o relatório extrai 10 linhas ou 1.000 linhas?</span><span class="sxs-lookup"><span data-stu-id="24cf1-143">For example, if a document has 10 lines, do the statistics show that the report extracts 10 lines or 1,000 lines?</span></span> <span data-ttu-id="24cf1-144">Se você tiver um número significativo de registros obtidos, considere uma das seguintes correções:</span><span class="sxs-lookup"><span data-stu-id="24cf1-144">If you have a substantial number of fetched records, consider one of the following fixes:</span></span>

    - <span data-ttu-id="24cf1-145">[Use a função **FILTER** em vez da função **WHERE**](#filter) para processar dados no lado do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="24cf1-145">[Use the **FILTER** function instead of the **WHERE** function](#filter) to process data on the SQL Server side.</span></span>
    - <span data-ttu-id="24cf1-146">Use o armazenamento em cache para evitar obter os mesmos dados.</span><span class="sxs-lookup"><span data-stu-id="24cf1-146">Use caching to avoid fetching the same data.</span></span>
    - <span data-ttu-id="24cf1-147">[Use funções dos dados coletados](#collected-data) para evitar obter os mesmos dados para resumo.</span><span class="sxs-lookup"><span data-stu-id="24cf1-147">[Use collected data functions](#collected-data) to avoid fetching the same data for summarization.</span></span>

### <a name="analyze-perfview-traces"></a><span data-ttu-id="24cf1-148">Analisar rastreamentos do PerfView</span><span class="sxs-lookup"><span data-stu-id="24cf1-148">Analyze PerfView traces</span></span>

<span data-ttu-id="24cf1-149">[PerfView](#perfview) é uma ferramenta para desenvolvedores experientes.</span><span class="sxs-lookup"><span data-stu-id="24cf1-149">[PerfView](#perfview) is a tool for experienced developers.</span></span> <span data-ttu-id="24cf1-150">Para obter informações mais detalhadas sobre as etapas seguintes, consulte [Noções básicas sobre a investigação do tempo do relógio de parede](https://channel9.msdn.com/Series/PerfView-Tutorial/Tutorial-12-Wall-Clock-Time-Investigation-Basics).</span><span class="sxs-lookup"><span data-stu-id="24cf1-150">For more detailed information about the following steps, see [Wall Clock Time Investigation Basics](https://channel9.msdn.com/Series/PerfView-Tutorial/Tutorial-12-Wall-Clock-Time-Investigation-Basics).</span></span>

1. <span data-ttu-id="24cf1-151">Colete um rastreamento usando o tempo do thread.</span><span class="sxs-lookup"><span data-stu-id="24cf1-151">Collect a trace by using thread time.</span></span>
2. <span data-ttu-id="24cf1-152">Inclua apenas pilhas que usam **runUnattended** para filtrar somente o thread que tenha a execução da configuração.</span><span class="sxs-lookup"><span data-stu-id="24cf1-152">Include only stacks that use **runUnattended**, to filter only the thread that has configuration execution.</span></span> <span data-ttu-id="24cf1-153">(Adicione **runUnattended** à caixa de entrada **IncPats**.)</span><span class="sxs-lookup"><span data-stu-id="24cf1-153">(Add **runUnattended** to the **IncPats** input box.)</span></span>
3. <span data-ttu-id="24cf1-154">Dobre toda a CPU, rede e o tempo bloqueado.</span><span class="sxs-lookup"><span data-stu-id="24cf1-154">Fold all CPU, network, and blocked time.</span></span>
4. <span data-ttu-id="24cf1-155">Carregue as [predefinições do ER para o PerfView](https://download.microsoft.com/download/2/d/0/2d037b0f-ffd1-4d65-b64f-fcdf51f2c81f/ER_PerfViewPresets.xml).</span><span class="sxs-lookup"><span data-stu-id="24cf1-155">Load [ER presets for PerfView](https://download.microsoft.com/download/2/d/0/2d037b0f-ffd1-4d65-b64f-fcdf51f2c81f/ER_PerfViewPresets.xml).</span></span>
5. <span data-ttu-id="24cf1-156">Selecione **ER** \> **Outra predefinição**.</span><span class="sxs-lookup"><span data-stu-id="24cf1-156">Select **ER** \> **Other preset**.</span></span>
6. <span data-ttu-id="24cf1-157">Veja os nomes:</span><span class="sxs-lookup"><span data-stu-id="24cf1-157">Look at the names:</span></span>

    - <span data-ttu-id="24cf1-158">Você provavelmente verá o código da plataforma que consome mais tempo.</span><span class="sxs-lookup"><span data-stu-id="24cf1-158">You will probably see the platform code that consumes the most time.</span></span>
    - <span data-ttu-id="24cf1-159">Você pode tocar duas vezes (ou clicar duas vezes) e subir até **receptores de chamada**.</span><span class="sxs-lookup"><span data-stu-id="24cf1-159">You can double-tap (or double-click) and go up through **callees**.</span></span>

        <span data-ttu-id="24cf1-160">Se você encontrar classes que tenham o prefixo "ERExpression" e se forem funções relacionadas às fórmulas, você poderá presumir o nome da função com base no nome da classe, e você poderá examinar o repositório ER para visualizar os atributos.</span><span class="sxs-lookup"><span data-stu-id="24cf1-160">If you find classes that have the prefix "ERExpression," and if they are functions that are related to formulas, you can guess the function name based on the class name, and you can look at the ER repo to view the attributes.</span></span>

### <a name="fixes"></a><span data-ttu-id="24cf1-161">Correções</span><span class="sxs-lookup"><span data-stu-id="24cf1-161">Fixes</span></span>

- <span data-ttu-id="24cf1-162">Se você vir que a maior parte do tempo da CPU é consumido por consultas, tente reduzir o número de consultas:</span><span class="sxs-lookup"><span data-stu-id="24cf1-162">If you see that most of the CPU time is consumed by queries, try to reduce the number of queries:</span></span>

    - <span data-ttu-id="24cf1-163">[Analise o rastreamento de ER](#analyze-database-calls) para ver se não há consultas duplicadas.</span><span class="sxs-lookup"><span data-stu-id="24cf1-163">[Review the ER trace](#analyze-database-calls) for duplicated queries.</span></span>
    - <span data-ttu-id="24cf1-164">Veja quantos registros são obtidos e avalie quantos dados devem teoricamente ser obtidos.</span><span class="sxs-lookup"><span data-stu-id="24cf1-164">See how many records are fetched, and evaluate how much data should theoretically be fetched.</span></span>

- <span data-ttu-id="24cf1-165">Se você vir que a maior parte do tempo da CPU é consumido pelas funções que são usadas, tente encontrar o lugar na configuração que consome mais recursos.</span><span class="sxs-lookup"><span data-stu-id="24cf1-165">If you see that most of the CPU time is consumed by the functions that are used, try to find the place in the configuration that consumes the most resources.</span></span>
- <span data-ttu-id="24cf1-166">Se você vir que a maior parte do tempo da CPU é consumido por funções de coleta de dados, considere substituí-los por *Agrupar por SQL* ao lado do mapeamento do modelo.</span><span class="sxs-lookup"><span data-stu-id="24cf1-166">If you see that most of the CPU time is consumed by data collection functions, consider replacing them with *SQL group by* on the model mapping side.</span></span>

### <a name="collecting-data"></a><a name="collecting-data"></a><span data-ttu-id="24cf1-167">Coletando dados</span><span class="sxs-lookup"><span data-stu-id="24cf1-167">Collecting data</span></span>

<span data-ttu-id="24cf1-168">Dependendo do seu ambiente, existem várias maneiras disponíveis para coletar dados:</span><span class="sxs-lookup"><span data-stu-id="24cf1-168">Depending on your environment, there are several ways to collect available data:</span></span>

- <span data-ttu-id="24cf1-169">Obtenha o tempo total de execução:</span><span class="sxs-lookup"><span data-stu-id="24cf1-169">Get the total running time:</span></span>

    - <span data-ttu-id="24cf1-170">A partir da Central de ações</span><span class="sxs-lookup"><span data-stu-id="24cf1-170">From the Action center</span></span>
    - <span data-ttu-id="24cf1-171">A partir do log de eventos</span><span class="sxs-lookup"><span data-stu-id="24cf1-171">From the event log</span></span>

- <span data-ttu-id="24cf1-172">Perfil da execução:</span><span class="sxs-lookup"><span data-stu-id="24cf1-172">Profile the execution:</span></span>

    - <span data-ttu-id="24cf1-173">Usando ferramentas de ER</span><span class="sxs-lookup"><span data-stu-id="24cf1-173">By using ER tools</span></span>
    - <span data-ttu-id="24cf1-174">Usando o Analisador de Rastreamento</span><span class="sxs-lookup"><span data-stu-id="24cf1-174">By using Trace parser</span></span>
    - <span data-ttu-id="24cf1-175">Usando o PerfView</span><span class="sxs-lookup"><span data-stu-id="24cf1-175">By using PerfView</span></span>

#### <a name="collecting-data-in-a-production-environment"></a><span data-ttu-id="24cf1-176">Coletando dados em um ambiente de produção</span><span class="sxs-lookup"><span data-stu-id="24cf1-176">Collecting data in a production environment</span></span>

<span data-ttu-id="24cf1-177">Às vezes, os problemas só podem ser reproduzidos em um ambiente de produção.</span><span class="sxs-lookup"><span data-stu-id="24cf1-177">Sometimes, issues can be reproduced only in a production environment.</span></span> <span data-ttu-id="24cf1-178">Os dados podem ser coletados da seguintes maneiras:</span><span class="sxs-lookup"><span data-stu-id="24cf1-178">Data can be collected in the following ways:</span></span>

- <span data-ttu-id="24cf1-179">Usando rastreamentos do [Analisador de Rastreamento](../perf-test/trace-trace-tutorial.md)</span><span class="sxs-lookup"><span data-stu-id="24cf1-179">By using [Trace parser](../perf-test/trace-trace-tutorial.md) traces</span></span>
- <span data-ttu-id="24cf1-180">Usando rastreamentos da [execução de ER](trace-execution-er-troubleshoot-perf.md)</span><span class="sxs-lookup"><span data-stu-id="24cf1-180">By using [ER execution](trace-execution-er-troubleshoot-perf.md) traces</span></span>
- <span data-ttu-id="24cf1-181">Usando o tempo total de execução</span><span class="sxs-lookup"><span data-stu-id="24cf1-181">By using the total execution time</span></span>

#### <a name="collecting-data-in-a-development-environment"></a><span data-ttu-id="24cf1-182">Coletando dados em um ambiente de desenvolvimento</span><span class="sxs-lookup"><span data-stu-id="24cf1-182">Collecting data in a development environment</span></span>

<span data-ttu-id="24cf1-183">Além das ferramentas que podem ser usadas em um ambiente de produção, existem várias ferramentas que você pode usar em um ambiente de desenvolvimento:</span><span class="sxs-lookup"><span data-stu-id="24cf1-183">In addition to the tools that can be used in a production environment, there are several tools that you can use in a development environment:</span></span>

- <span data-ttu-id="24cf1-184">Log de eventos (Microsoft-Dynamics-ElectronicReporting).</span><span class="sxs-lookup"><span data-stu-id="24cf1-184">Event log (Microsoft-Dynamics-ElectronicReporting).</span></span> <span data-ttu-id="24cf1-185">Esse log pode fornecer a você o tempo total de execução.</span><span class="sxs-lookup"><span data-stu-id="24cf1-185">This log can give you the total execution time.</span></span>
- <span data-ttu-id="24cf1-186">Ferramentas .NET comuns, como o PerfView.</span><span class="sxs-lookup"><span data-stu-id="24cf1-186">Common .NET tools, such as PerfView.</span></span>

<span data-ttu-id="24cf1-187">Além disso, um ambiente de desenvolvimento fornece a você mais flexibilidade para experimentar.</span><span class="sxs-lookup"><span data-stu-id="24cf1-187">Additionally, a development environment gives you more flexibility to experiment.</span></span> <span data-ttu-id="24cf1-188">Por exemplo, você pode desativar partes de relatórios para ver como o tempo de execução é afetado.</span><span class="sxs-lookup"><span data-stu-id="24cf1-188">For example, you can turn off parts of reports to see how the execution time is affected.</span></span>

### <a name="tools"></a><a name="tools"></a><span data-ttu-id="24cf1-189">Ferramentas</span><span class="sxs-lookup"><span data-stu-id="24cf1-189">Tools</span></span>

#### <a name="execution-time-in-the-action-center"></a><a name="infolog-time"></a><span data-ttu-id="24cf1-190">Tempo de execução na Central de ações</span><span class="sxs-lookup"><span data-stu-id="24cf1-190">Execution time in the Action center</span></span>

<span data-ttu-id="24cf1-191">O ER pode mostrar o tempo de execução da configuração na Central de ações.</span><span class="sxs-lookup"><span data-stu-id="24cf1-191">ER can show the execution time of the configuration in the Action center.</span></span> <span data-ttu-id="24cf1-192">Essa opção funciona somente para um usuário específico e uma empresa específica, e somente para sessões interativas.</span><span class="sxs-lookup"><span data-stu-id="24cf1-192">This option works only for a specific user and a specific company, and only for interactive sessions.</span></span> <span data-ttu-id="24cf1-193">Para disponibilizar esse recurso, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="24cf1-193">To make this feature available, follow these steps.</span></span>

1. <span data-ttu-id="24cf1-194">Vá para **Administração da organização** \> **Relatório eletrônico** \> **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="24cf1-194">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="24cf1-195">Na página **Configurações**, no Painel Ação, na guia **Configurações**, no grupo **Configurações avançadas**, selecione **Parâmetros de usuário**.</span><span class="sxs-lookup"><span data-stu-id="24cf1-195">On the **Configurations** page, on the Action Pane, on the **Configurations** tab, in the **Advanced settings** group, select **User parameters**.</span></span>
3. <span data-ttu-id="24cf1-196">Na caixa de diálogo **Parâmetros do usuário**, defina a opção **Mostrar tempo de geração do arquivo** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="24cf1-196">In the **User parameters** dialog box, set the **Show file generation time** option to **Yes**.</span></span>

#### <a name="execution-time-in-the-event-log"></a><a name="event-log-time"></a><span data-ttu-id="24cf1-197">Tempo de execução no log de eventos</span><span class="sxs-lookup"><span data-stu-id="24cf1-197">Execution time in the event log</span></span>

1. <span data-ttu-id="24cf1-198">Abra o Visualizador de Eventos do Windows.</span><span class="sxs-lookup"><span data-stu-id="24cf1-198">Open Windows Event Viewer.</span></span>
2. <span data-ttu-id="24cf1-199">Em **Logs de Aplicativos e Serviços**, abra **Microsoft-Dynamics-ElectronicReporting/Operational**.</span><span class="sxs-lookup"><span data-stu-id="24cf1-199">Under **Applications and Services logs**, open **Microsoft-Dynamics-ElectronicReporting/Operational**.</span></span>
3. <span data-ttu-id="24cf1-200">Procure eventos **FormatMapingRun**, em que **EventID=2**, porque esses eventos contêm as informações sobre o tempo decorrido.</span><span class="sxs-lookup"><span data-stu-id="24cf1-200">Look for **FormatMapingRun** events where **EventID=2**, because these events contain the information about elapsed time.</span></span>

#### <a name="trace-parser-traces"></a><a name="trace-parser"></a><span data-ttu-id="24cf1-201">Rastreamentos do Analisador de Rastreamento</span><span class="sxs-lookup"><span data-stu-id="24cf1-201">Trace parser traces</span></span> 

<span data-ttu-id="24cf1-202">Como o ER é implementado em X++, você pode usar ferramentas X++ comuns para analisar o desempenho.</span><span class="sxs-lookup"><span data-stu-id="24cf1-202">Because ER is implemented in X++, you can use common X++ tools to analyze performance.</span></span> <span data-ttu-id="24cf1-203">Para obter mais informações, consulte [Obter rastreamentos usando o Analisador de Rastreamento](../perf-test/trace-trace-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="24cf1-203">For more information, see [Take traces by using Trace parser](../perf-test/trace-trace-tutorial.md).</span></span>

<span data-ttu-id="24cf1-204">Há algumas limitações para essa abordagem.</span><span class="sxs-lookup"><span data-stu-id="24cf1-204">There are a few limitations to this approach.</span></span> <span data-ttu-id="24cf1-205">Como parte do ER é implementado em C#, nem todos os detalhes estarão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="24cf1-205">Because part of ER is implemented in C#, not all the details will be available.</span></span> <span data-ttu-id="24cf1-206">No entanto, você poderá exibir os detalhes do uso de dados.</span><span class="sxs-lookup"><span data-stu-id="24cf1-206">However, you can view the data usage details.</span></span> <span data-ttu-id="24cf1-207">Além disso, longas execuções de relatórios podem exceder as limitações de armazenamento de rastreamentos.</span><span class="sxs-lookup"><span data-stu-id="24cf1-207">Additionally, long report runs can exceed trace storage limitations.</span></span>

#### <a name="er-traces"></a><a name="electronic-reporting-traces"></a><span data-ttu-id="24cf1-208">Rastreamentos de ER</span><span class="sxs-lookup"><span data-stu-id="24cf1-208">ER traces</span></span>

<span data-ttu-id="24cf1-209">O ER pode coletar seus próprios rastreamentos, e tem ferramentas de visualização e análise para esses rastreamentos.</span><span class="sxs-lookup"><span data-stu-id="24cf1-209">ER can collect its own traces, and it has visualization and analysis tools for those traces.</span></span> <span data-ttu-id="24cf1-210">Para obter mais informações, consulte [Rastrear a execução de formatos de ER para solucionar problemas de desempenho](trace-execution-er-troubleshoot-perf.md).</span><span class="sxs-lookup"><span data-stu-id="24cf1-210">For more information, see [Trace the execution of ER formats to troubleshoot performance issues](trace-execution-er-troubleshoot-perf.md).</span></span>

#### <a name="perfview"></a><a name="perfview"></a><span data-ttu-id="24cf1-211">PerfView</span><span class="sxs-lookup"><span data-stu-id="24cf1-211">PerfView</span></span>

<span data-ttu-id="24cf1-212">Como X++ e o ER são implementados na plataforma .NET, você pode usar ferramentas comuns .NET.</span><span class="sxs-lookup"><span data-stu-id="24cf1-212">Because both X++ and ER are implemented on top of the .NET platform, you can use common .NET tools.</span></span> <span data-ttu-id="24cf1-213">Por exemplo, você pode usar a ferramenta gratuita [PerfView](https://github.com/Microsoft/perfview).</span><span class="sxs-lookup"><span data-stu-id="24cf1-213">For example, you can use the free [PerfView](https://github.com/Microsoft/perfview) tool.</span></span>

<span data-ttu-id="24cf1-214">Você também pode coletar dados a partir da linha de comando.</span><span class="sxs-lookup"><span data-stu-id="24cf1-214">You can also collect data from the command line.</span></span> <span data-ttu-id="24cf1-215">Por exemplo, o script a seguir do Windows PowerShell coleta o tempo de execução até que qualquer execução de formato seja interrompido na máquina.</span><span class="sxs-lookup"><span data-stu-id="24cf1-215">For example, the following Windows PowerShell script collects the execution time until any format execution is stopped on the machine.</span></span>

```powershell
c:\programs\PerfView collect "e:\traces\$(date -format "ddMMyyyy_hhmm").etl" `
    -CircularMB:20000 -ThreadTime `
    -NoNGenRundown `
    -StopOnEtwEvent:Microsoft-Dynamics-ElectronicReporting/FormatMappingRun/Stop
```

<span data-ttu-id="24cf1-216">Há algumas limitações para essa abordagem.</span><span class="sxs-lookup"><span data-stu-id="24cf1-216">There are a few limitations to this approach.</span></span> <span data-ttu-id="24cf1-217">Você deve ter acesso administrativo ao computador.</span><span class="sxs-lookup"><span data-stu-id="24cf1-217">You must have administrative access to the machine.</span></span> <span data-ttu-id="24cf1-218">Além disso, você deve ser um desenvolvedor experiente, porque há uma curva de aprendizado acentuada.</span><span class="sxs-lookup"><span data-stu-id="24cf1-218">Additionally, you must be an experienced developer, because there is a steep learning curve.</span></span>

### <a name="making-changes"></a><a name="making-changes"></a><span data-ttu-id="24cf1-219">Fazendo alterações</span><span class="sxs-lookup"><span data-stu-id="24cf1-219">Making changes</span></span>

#### <a name="use-caching"></a><a name="use-caching"></a><span data-ttu-id="24cf1-220">Usar armazenamento em cache</span><span class="sxs-lookup"><span data-stu-id="24cf1-220">Use caching</span></span>

<span data-ttu-id="24cf1-221">Embora o armazenamento em cache reduza a quantidade de tempo necessário para obter dados novamente, isso tem um custo de memória.</span><span class="sxs-lookup"><span data-stu-id="24cf1-221">Although caching reduces the amount of time that is required to fetch data again, it costs memory.</span></span> <span data-ttu-id="24cf1-222">Use o armazenamento em cache nos casos em que a quantidade de dados obtidos não seja muito grande.</span><span class="sxs-lookup"><span data-stu-id="24cf1-222">Use caching in cases where the amount of fetched data isn't very large.</span></span> <span data-ttu-id="24cf1-223">Para obter mais informações e um exemplo que mostre como usar o armazenamento em cache, consulte [Melhorar o mapeamento do modelo com base em informações do rastreamento de execução](trace-execution-er-troubleshoot-perf.md#improve-the-model-mapping-based-on-information-from-the-execution-trace).</span><span class="sxs-lookup"><span data-stu-id="24cf1-223">For more information and an example that shows how to use caching, see [Improve the model mapping based on information from the execution trace](trace-execution-er-troubleshoot-perf.md#improve-the-model-mapping-based-on-information-from-the-execution-trace).</span></span>

#### <a name="use-a-cached-parameterized-calculated-field"></a><a name="cached-parameterized"></a><span data-ttu-id="24cf1-224">Usar um campo calculado armazenamento em cache e parametrizado</span><span class="sxs-lookup"><span data-stu-id="24cf1-224">Use a cached, parameterized calculated field</span></span>

<span data-ttu-id="24cf1-225">Às vezes, os valores devem ser pesquisados repetidamente.</span><span class="sxs-lookup"><span data-stu-id="24cf1-225">Sometimes, values must be looked up repeatedly.</span></span> <span data-ttu-id="24cf1-226">Exemplos incluem nomes de contas e números de contas.</span><span class="sxs-lookup"><span data-stu-id="24cf1-226">Examples include account names and account numbers.</span></span> <span data-ttu-id="24cf1-227">Para ajudar a economizar tempo, você pode criar um campo calculado que tenha parâmetros no nível superior e, em seguida, adicionar o campo ao armazenamento em cache.</span><span class="sxs-lookup"><span data-stu-id="24cf1-227">To help save time, you can create a calculated field that has parameters on the top level, and then add the field to the cache.</span></span>

<span data-ttu-id="24cf1-228">Recomendamos que você use essa abordagem somente quando o tamanho dos dados armazenados em cache for pequeno.</span><span class="sxs-lookup"><span data-stu-id="24cf1-228">We recommend that you use this approach only when the size of the cached data is small.</span></span> <span data-ttu-id="24cf1-229">Para obter mais informações, consulte [Melhorar o desempenho de soluções ER adicionando fontes de dados de CAMPOS CALCULADOS parametrizados](er-calculated-field-ds-performance.md).</span><span class="sxs-lookup"><span data-stu-id="24cf1-229">For more information, see [Improve the performance of ER solutions by adding parameterized CALCULATED FIELD data sources](er-calculated-field-ds-performance.md).</span></span>

#### <a name="use-a-join-data-source"></a><a name="use-join-datasource"></a><span data-ttu-id="24cf1-230">Usar uma fonte de dados JOIN</span><span class="sxs-lookup"><span data-stu-id="24cf1-230">Use a JOIN data source</span></span>

<span data-ttu-id="24cf1-231">Uma fonte de dados **JOIN** permite a obtenção de vários registros conectados por uma consulta.</span><span class="sxs-lookup"><span data-stu-id="24cf1-231">A **JOIN** data source enables several connected records to be fetched by one query.</span></span> <span data-ttu-id="24cf1-232">Não é necessário usar uma consulta separada para obter cada registro conectado.</span><span class="sxs-lookup"><span data-stu-id="24cf1-232">A separate query doesn't have to be used to fetch each connected record.</span></span> <span data-ttu-id="24cf1-233">Por exemplo, se você tiver 1.000 linhas e obter dados de itens para cada linha por relação, você terá 1.001 consultas (= 1.000 + 1).</span><span class="sxs-lookup"><span data-stu-id="24cf1-233">For example, if you have 1,000 lines, and you fetch item data for each line by relation, you will have 1,001 queries (= 1,000 + 1).</span></span> <span data-ttu-id="24cf1-234">Se usar uma fonte de dados **JOIN** você usará apenas uma consulta para obter os mesmos dados.</span><span class="sxs-lookup"><span data-stu-id="24cf1-234">If you use a **JOIN** data source, you will use only one query to fetch the same data.</span></span> <span data-ttu-id="24cf1-235">Para obter mais informações, consulte [Usar as fontes de dados JOIN em mapeamentos do modelo de ER para obter dados de várias tabelas de aplicativos](er-join-data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="24cf1-235">For more information, see [Use JOIN data sources in ER model mappings to get data from multiple application tables](er-join-data-sources.md).</span></span>

#### <a name="use-the-filter-function-instead-of-the-where-function"></a><a name="filter"></a><span data-ttu-id="24cf1-236">Usar a função FILTER em vez da função WHERE</span><span class="sxs-lookup"><span data-stu-id="24cf1-236">Use the FILTER function instead of the WHERE function</span></span>

<span data-ttu-id="24cf1-237">A função **[FILTER](er-functions-list-filter.md)** executa as condições no SQL Server, enquanto a função **WHERE** obtém todos os dados da lista, um registro por vez , e aplica a condição para cada registro.</span><span class="sxs-lookup"><span data-stu-id="24cf1-237">The **[FILTER](er-functions-list-filter.md)** function runs conditions on SQL Server, whereas the **WHERE** function fetches all data from the list, one record at a time, and applies the condition for each record.</span></span> <span data-ttu-id="24cf1-238">Por exemplo, você deseja selecionar um registro de 1.000 registros.</span><span class="sxs-lookup"><span data-stu-id="24cf1-238">For example, you want to select one record out of 1,000 records.</span></span> <span data-ttu-id="24cf1-239">Se você usar **WHERE**, todos os 1.000 registros serão obtidos.</span><span class="sxs-lookup"><span data-stu-id="24cf1-239">If you use **WHERE**, all 1,000 records will be fetched.</span></span> <span data-ttu-id="24cf1-240">No entanto, se você usar **FILTER**, exatamente um registro será obtido.</span><span class="sxs-lookup"><span data-stu-id="24cf1-240">However, if you use **FILTER**, exactly one record will be fetched.</span></span> <span data-ttu-id="24cf1-241">**FILTER** também pode usar índices no lado do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="24cf1-241">**FILTER** can also use indexes on the database side.</span></span>

#### <a name="using-collected-data-functions-or-an-accumulated-data-data-source"></a><a name="collected-data"></a><span data-ttu-id="24cf1-242">Usando funções de dados coletados ou uma fonte de dados acumulados</span><span class="sxs-lookup"><span data-stu-id="24cf1-242">Using collected data functions or an accumulated data data source</span></span>

<span data-ttu-id="24cf1-243">Se a sua configuração tiver um componente *agrupar por* que resume dados obtidos anteriormente por relatório, o componente obterá todos os dados novamente.</span><span class="sxs-lookup"><span data-stu-id="24cf1-243">If your configuration has a *group by* component that summarizes previously fetched data by report, the component will fetch all the data again.</span></span> <span data-ttu-id="24cf1-244">Ao usar as funções de dados coletados, você permite que o ER acumule dados durante a primeira obtenção.</span><span class="sxs-lookup"><span data-stu-id="24cf1-244">By using collected data functions, you enable ER to accumulate data during the first fetch.</span></span> <span data-ttu-id="24cf1-245">Para obter mais informações, consulte [ER Configurar o formato para contagem e soma](tasks/er-format-counting-summing-2.md).</span><span class="sxs-lookup"><span data-stu-id="24cf1-245">For more information, see [ER Configure format to do counting and summing](tasks/er-format-counting-summing-2.md).</span></span>

#### <a name="rewrite-parts-of-the-configuration-in-x"></a><span data-ttu-id="24cf1-246">Reescrever partes da configuração em X++</span><span class="sxs-lookup"><span data-stu-id="24cf1-246">Rewrite parts of the configuration in X++</span></span>

<span data-ttu-id="24cf1-247">O ER oferece suporte a métodos de chamada de tabelas e classes, incluindo extensões.</span><span class="sxs-lookup"><span data-stu-id="24cf1-247">ER supports calling methods of tables and classes, including extensions.</span></span> <span data-ttu-id="24cf1-248">Considere reescrever partes do mapeamento do modelo em X++ para ajudar a melhorar o desempenho.</span><span class="sxs-lookup"><span data-stu-id="24cf1-248">Consider rewriting parts of the model mapping in X++ to help improve performance.</span></span>

<span data-ttu-id="24cf1-249">O ER pode consumir dados das seguintes fontes:</span><span class="sxs-lookup"><span data-stu-id="24cf1-249">ER can consume data from the following sources:</span></span>

- <span data-ttu-id="24cf1-250">Classes (fontes de dados de **objetos** e **classes**)</span><span class="sxs-lookup"><span data-stu-id="24cf1-250">Classes (**object** and **class** data sources)</span></span>
- <span data-ttu-id="24cf1-251">Tabelas (fontes de dados de **tabelas** e **registros de tabela**)</span><span class="sxs-lookup"><span data-stu-id="24cf1-251">Tables (**table** and **table records** data sources)</span></span>

<span data-ttu-id="24cf1-252">A [API de ER](er-apis-app73.md#how-to-access-internal-x-objects-by-using-erobjectsfactory) também fornece uma maneira de enviar dados pré-calculados a partir do código de chamada.</span><span class="sxs-lookup"><span data-stu-id="24cf1-252">The [ER API](er-apis-app73.md#how-to-access-internal-x-objects-by-using-erobjectsfactory) also provides a way to send precalculated data from the calling code.</span></span> <span data-ttu-id="24cf1-253">O pacote de aplicativos contém vários exemplos dessa abordagem.</span><span class="sxs-lookup"><span data-stu-id="24cf1-253">The application suite contains numerous examples of this approach.</span></span>
