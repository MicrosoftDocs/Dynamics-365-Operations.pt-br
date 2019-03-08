---
title: Opções avançadas de filtragem e sintaxe de consulta
description: Este artigo descreve as opções de filtragem e consulta disponíveis quando você usa a caixa de diálogo Filtro/Classificação Avançada ou o operador correspondências no Painel de filtragem ou nos filtros de cabeçalho de coluna de grade.
author: jasongre
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysQueryForm
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 3811
ms.assetid: b4969b30-2fe1-4a3c-bbea-725dc37c8b60
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 01a508e97721099f92b9167dfdfa1b9669b9341c
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "355946"
---
# <a name="advanced-filtering-and-query-syntax"></a><span data-ttu-id="962fa-103">Sintaxe avançada de filtragem e consulta</span><span class="sxs-lookup"><span data-stu-id="962fa-103">Advanced filtering and query syntax</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="962fa-104">Este artigo descreve as opções de filtragem e consulta disponíveis quando você usa a caixa de diálogo Filtro/Classificação Avançada ou o operador **correspondências** no Painel de filtragem ou nos filtros de cabeçalho de coluna de grade.</span><span class="sxs-lookup"><span data-stu-id="962fa-104">This article describes the filtering and query options that are available when you use the Advanced filter/sort dialog or the **matches** operator in the Filter pane or grid column header filters.</span></span>

## <a name="advanced-query-syntax"></a><span data-ttu-id="962fa-105">Sintaxe de consulta avançada</span><span class="sxs-lookup"><span data-stu-id="962fa-105">Advanced query syntax</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="962fa-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="962fa-106">Syntax</span></span></th>
<th><span data-ttu-id="962fa-107">Descrição de caractere</span><span class="sxs-lookup"><span data-stu-id="962fa-107">Character description</span></span></th>
<th><span data-ttu-id="962fa-108">descrição</span><span class="sxs-lookup"><span data-stu-id="962fa-108">Description</span></span></th>
<th><span data-ttu-id="962fa-109">Exemplo</span><span class="sxs-lookup"><span data-stu-id="962fa-109">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="962fa-110"><em>valor</em></span><span class="sxs-lookup"><span data-stu-id="962fa-110"><em>value</em></span></span></td>
<td><span data-ttu-id="962fa-111">Igual ao valor inserido que é inserido</span><span class="sxs-lookup"><span data-stu-id="962fa-111">Equal to the value that is entered</span></span></td>
<td><span data-ttu-id="962fa-112">Digite o valor para encontrar.</span><span class="sxs-lookup"><span data-stu-id="962fa-112">Type the value to find.</span></span></td>
<td><span data-ttu-id="962fa-113"><strong>Smith</strong> localiza &quot;Smith&quot;.</span><span class="sxs-lookup"><span data-stu-id="962fa-113"><strong>Smith</strong> finds &quot;Smith&quot;.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="962fa-114">!<em>valor</em> (ponto de exclamação)</span><span class="sxs-lookup"><span data-stu-id="962fa-114">!<em>value</em> (exclamation point)</span></span></td>
<td><span data-ttu-id="962fa-115">Diferente do valor que é inserido</span><span class="sxs-lookup"><span data-stu-id="962fa-115">Not equal to the value that is entered</span></span></td>
<td><span data-ttu-id="962fa-116">Digite um ponto de exclamação e o valor a ser excluído.</span><span class="sxs-lookup"><span data-stu-id="962fa-116">Type an exclamation point and then the value to exclude.</span></span></td>
<td><span data-ttu-id="962fa-117"><strong>!Smith</strong> localiza todos os valores, exceto &quot;Smith&quot;.</span><span class="sxs-lookup"><span data-stu-id="962fa-117"><strong>!Smith</strong> finds all values except &quot;Smith&quot;.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="962fa-118"><em>-valor de</em>.<em>valor até</em> (dois pontos finais)</span><span class="sxs-lookup"><span data-stu-id="962fa-118"><em>from-value</em>..<em>to-value</em> (double period)</span></span></td>
<td><span data-ttu-id="962fa-119">Entre os dois valores que são separados por dois pontos finais</span><span class="sxs-lookup"><span data-stu-id="962fa-119">Between the two values that are separated by double periods</span></span></td>
<td><span data-ttu-id="962fa-120">Digite o Valor - de, os dois pontos finais e o Valor - até.</span><span class="sxs-lookup"><span data-stu-id="962fa-120">Type the from-value, then two periods, and then the to-value.</span></span></td>
<td><span data-ttu-id="962fa-121"><strong>1..10</strong> localiza todos os valores de 1 a 10.</span><span class="sxs-lookup"><span data-stu-id="962fa-121"><strong>1..10</strong> finds all values from 1 through 10.</span></span> <span data-ttu-id="962fa-122">No entanto, em um campo de string, <strong>A..C</strong> localiza todos os valores que começam com &quot;A&quot; e &quot;B&quot; e os valores exatamente iguais a &quot;C&quot;.</span><span class="sxs-lookup"><span data-stu-id="962fa-122">However, in a string field, <strong>A..C</strong> finds all values that start with &quot;A&quot; and &quot;B&quot;, and values that are exactly equal to &quot;C&quot;.</span></span> <span data-ttu-id="962fa-123">Por exemplo, esta consulta não encontrará &quot;Ca&quot;.</span><span class="sxs-lookup"><span data-stu-id="962fa-123">For example, this query won't find &quot;Ca&quot;.</span></span> <span data-ttu-id="962fa-124">Para localizar todos os valores de &quot;A<em>&quot; a &quot;C</em>&quot;, digite <strong>A..D</strong>.</span><span class="sxs-lookup"><span data-stu-id="962fa-124">To find all values from &quot;A<em>&quot; through &quot;C</em>&quot;, type <strong>A..D</strong>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="962fa-125">..<em>valor</em> (dois pontos finais)</span><span class="sxs-lookup"><span data-stu-id="962fa-125">..<em>value</em> (double period)</span></span></td>
<td><span data-ttu-id="962fa-126">Menor ou igual ao valor inserido.</span><span class="sxs-lookup"><span data-stu-id="962fa-126">Less than or equal to the value that is entered</span></span></td>
<td><span data-ttu-id="962fa-127">Digite os dois pontos finais e, em seguida, o valor.</span><span class="sxs-lookup"><span data-stu-id="962fa-127">Type two periods and then the value.</span></span></td>
<td><span data-ttu-id="962fa-128"><strong>..1000</strong> localiza todos os números menores ou iguais a 1000, como &quot;100&quot;, &quot;999,95&quot; e &quot;1.000&quot;.</span><span class="sxs-lookup"><span data-stu-id="962fa-128"><strong>..1000</strong> finds any number that is less than or equal to 1000, such as &quot;100&quot;, &quot;999.95&quot;, and &quot;1,000&quot;.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="962fa-129"><em>valor</em>..</span><span class="sxs-lookup"><span data-stu-id="962fa-129"><em>value</em>..</span></span> <span data-ttu-id="962fa-130">(dois pontos finais)</span><span class="sxs-lookup"><span data-stu-id="962fa-130">(double period)</span></span></td>
<td><span data-ttu-id="962fa-131">Maior ou igual ao valor inserido.</span><span class="sxs-lookup"><span data-stu-id="962fa-131">Greater than or equal to the value that is entered</span></span></td>
<td><span data-ttu-id="962fa-132">Digite o valor e, em seguida, dois pontos.</span><span class="sxs-lookup"><span data-stu-id="962fa-132">Type the value and then two periods.</span></span></td>
<td><span data-ttu-id="962fa-133"><strong>1000..</strong></span><span class="sxs-lookup"><span data-stu-id="962fa-133"><strong>1000..</strong></span></span> <span data-ttu-id="962fa-134">localiza todos os números maiores ou iguais a 1000, como &quot;1.000&quot;, &quot;1.000,01&quot; e &quot;1.000.000&quot;.</span><span class="sxs-lookup"><span data-stu-id="962fa-134">finds any number that is greater than or equal to 1000, such as &quot;1,000&quot;, &quot;1,000.01&quot;, and &quot;1,000,000&quot;.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="962fa-135">&gt;<em>valor</em> (sinal maior que)</span><span class="sxs-lookup"><span data-stu-id="962fa-135">&gt;<em>value</em> (greater than sign)</span></span></td>
<td><span data-ttu-id="962fa-136">Maior que o valor inserido</span><span class="sxs-lookup"><span data-stu-id="962fa-136">Greater than the value that is entered</span></span></td>
<td><span data-ttu-id="962fa-137">Digite um sinal maior que (<strong>&gt;</strong>) e o valor.</span><span class="sxs-lookup"><span data-stu-id="962fa-137">Type a greater than sign (<strong>&gt;</strong>) and then the value.</span></span></td>
<td><span data-ttu-id="962fa-138"><strong>&gt;1000</strong> localiza todos os números maiores ou iguais a 1000, como &quot;1000,01&quot;, &quot;20.000&quot; e &quot;1.000.000&quot;.</span><span class="sxs-lookup"><span data-stu-id="962fa-138"><strong>&gt;1000</strong> finds any number that is greater than 1000, such as &quot;1000.01&quot;, &quot;20,000&quot;, and &quot;1,000,000&quot;.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="962fa-139">&lt;<em>valor</em> (sinal menor que)</span><span class="sxs-lookup"><span data-stu-id="962fa-139">&lt;<em>value</em> (less than sign)</span></span></td>
<td><span data-ttu-id="962fa-140">Menor que o valor inserido</span><span class="sxs-lookup"><span data-stu-id="962fa-140">Less than the value that is entered</span></span></td>
<td><span data-ttu-id="962fa-141">Digite um sinal de menor que (<strong>&lt;</strong>) e o valor.</span><span class="sxs-lookup"><span data-stu-id="962fa-141">Type a less than sign (<strong>&lt;</strong>) and then the value.</span></span></td>
<td><span data-ttu-id="962fa-142"><strong>&lt;1000</strong> localiza todo número menor que 1000, como &quot;999,99&quot;, &quot;1&quot; e &quot;-200&quot;.</span><span class="sxs-lookup"><span data-stu-id="962fa-142"><strong>&lt;1000</strong> finds any number that is less than 1000, such as &quot;999.99&quot;, &quot;1&quot;, and &quot;-200&quot;.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="962fa-143"><em>valor</em>\* (asterisco)</span><span class="sxs-lookup"><span data-stu-id="962fa-143"><em>value</em>\* (asterisk)</span></span></td>
<td><span data-ttu-id="962fa-144">Iniciando a partir do valor que é inserido</span><span class="sxs-lookup"><span data-stu-id="962fa-144">Starting from the value that is entered</span></span></td>
<td><span data-ttu-id="962fa-145">Digite o valor inicial e, em seguida, um asterisco (<strong>\*</strong>).</span><span class="sxs-lookup"><span data-stu-id="962fa-145">Type the starting value and then an asterisk (<strong>\*</strong>).</span></span></td>
<td><span data-ttu-id="962fa-146"><strong>S\*</strong> localiza todas as sequências de caracteres que começam com &quot;S&quot;, como &quot;Stockholm&quot;, &quot;Sydney&quot; e &quot;San Francisco&quot;.</span><span class="sxs-lookup"><span data-stu-id="962fa-146"><strong>S\*</strong> finds any string that starts with &quot;S&quot;, such as &quot;Stockholm&quot;, &quot;Sydney&quot;, and &quot;San Francisco&quot;.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="962fa-147">\*<em>valor</em> (asterisco)</span><span class="sxs-lookup"><span data-stu-id="962fa-147">\*<em>value</em> (asterisk)</span></span></td>
<td><span data-ttu-id="962fa-148">Terminando com o valor inserido.</span><span class="sxs-lookup"><span data-stu-id="962fa-148">Ending with the value that is entered</span></span></td>
<td><span data-ttu-id="962fa-149">Digite um asterisco e, em seguida, o valor final.</span><span class="sxs-lookup"><span data-stu-id="962fa-149">Type an asterisk and then the ending value.</span></span></td>
<td><span data-ttu-id="962fa-150"><strong>\*east</strong> localiza todas as cadeias de caracteres que terminam com &quot;east&quot; como &quot;Northeast&quot; e &quot;Southeast&quot;.</span><span class="sxs-lookup"><span data-stu-id="962fa-150"><strong>\*east</strong> finds any string that ends with &quot;east&quot;, such as &quot;Northeast&quot; and &quot;Southeast&quot;.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="962fa-151">*<em>valor</em>* (asterisco)</span><span class="sxs-lookup"><span data-stu-id="962fa-151">*<em>value</em>* (asterisk)</span></span></td>
<td><span data-ttu-id="962fa-152">Contendo o valor inserido</span><span class="sxs-lookup"><span data-stu-id="962fa-152">Containing the value that is entered</span></span></td>
<td><span data-ttu-id="962fa-153">Digite um asterisco, um valor e outro asterisco.</span><span class="sxs-lookup"><span data-stu-id="962fa-153">Type an asterisk, then a value, and then another asterisk.</span></span></td>
<td><span data-ttu-id="962fa-154"><strong>*th*</strong> localiza todas as cadeias que contenham &quot;th&quot;, como &quot;Northeast&quot; e &quot;Southeast&quot;.</span><span class="sxs-lookup"><span data-stu-id="962fa-154"><strong>*th*</strong> finds any string that contains &quot;th&quot;, such as &quot;Northeast&quot; and &quot;Southeast&quot;.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="962fa-155">?</span><span class="sxs-lookup"><span data-stu-id="962fa-155">?</span></span> <span data-ttu-id="962fa-156">(ponto de interrogação)</span><span class="sxs-lookup"><span data-stu-id="962fa-156">(question mark)</span></span></td>
<td><span data-ttu-id="962fa-157">Tendo um ou mais caracteres desconhecidos</span><span class="sxs-lookup"><span data-stu-id="962fa-157">Having one or more unknown characters</span></span></td>
<td><span data-ttu-id="962fa-158">Digite um ponto de interrogação na posição de caracteres desconhecidos do valor.</span><span class="sxs-lookup"><span data-stu-id="962fa-158">Type a question mark at the position of the unknown character in the value.</span></span></td>
<td><span data-ttu-id="962fa-159"><strong>Sm?th</strong> localiza &quot;Smith&quot; e &quot;Smyth&quot;.</span><span class="sxs-lookup"><span data-stu-id="962fa-159"><strong>Sm?th</strong> finds &quot;Smith&quot; and &quot;Smyth&quot;.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="962fa-160"><em>valor</em>,<em>valor</em> (vírgula)</span><span class="sxs-lookup"><span data-stu-id="962fa-160"><em>value</em>,<em>value</em> (comma)</span></span></td>
<td><span data-ttu-id="962fa-161">Correspondendo aos valores separados por vírgulas</span><span class="sxs-lookup"><span data-stu-id="962fa-161">Matching the values that are separated by commas</span></span></td>
<td><span data-ttu-id="962fa-162">Digite todos os critérios, e separe-os usando vírgulas.</span><span class="sxs-lookup"><span data-stu-id="962fa-162">Type all your criteria, and separate them by using commas.</span></span></td>
<td><span data-ttu-id="962fa-163"><strong>A, D, F, G</strong> localiza exatamente &quot;A&quot;, &quot;D&quot;, &quot;F&quot; e &quot;G&quot;.</span><span class="sxs-lookup"><span data-stu-id="962fa-163"><strong>A, D, F, G</strong> finds exactly &quot;A&quot;, &quot;D&quot;, &quot;F&quot;, and &quot;G&quot;.</span></span> <span data-ttu-id="962fa-164"><strong>10, 20, 30, 100</strong> localiza exatamente &quot;10, 20, 30, 100&quot;.</span><span class="sxs-lookup"><span data-stu-id="962fa-164"><strong>10, 20, 30, 100</strong> finds exactly &quot;10, 20, 30, 100&quot;.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="962fa-165">(<span class="code">Instrução SQL</span>) (instrução SQL entre parênteses)</span><span class="sxs-lookup"><span data-stu-id="962fa-165">(<span class="code">SQL statement</span>) (SQL statement between parentheses)</span></span></td>
<td><span data-ttu-id="962fa-166">Correspondendo a uma consulta definida</span><span class="sxs-lookup"><span data-stu-id="962fa-166">Matching a defined query</span></span></td>
<td><span data-ttu-id="962fa-167">Digite uma consulta como instrução SQL entre parênteses.</span><span class="sxs-lookup"><span data-stu-id="962fa-167">Type a query as an SQL statement between parentheses.</span></span></td>
<td><span data-ttu-id="962fa-168"><strong><span class="code">(data source.Fieldname != &quot;A&quot;)</span></strong></span><span class="sxs-lookup"><span data-stu-id="962fa-168"><strong><span class="code">(data source.Fieldname != &quot;A&quot;)</span></strong></span></span></td>
</tr>
<tr>
<td><span data-ttu-id="962fa-169">Q</span><span class="sxs-lookup"><span data-stu-id="962fa-169">T</span></span></td>
<td><span data-ttu-id="962fa-170">Data atual</span><span class="sxs-lookup"><span data-stu-id="962fa-170">Today's date</span></span></td>
<td><span data-ttu-id="962fa-171">Digite <strong>T</strong>.</span><span class="sxs-lookup"><span data-stu-id="962fa-171">Type <strong>T</strong>.</span></span></td>
<td><span data-ttu-id="962fa-172"><strong>T</strong> corresponde à data de hoje.</span><span class="sxs-lookup"><span data-stu-id="962fa-172"><strong>T</strong> matches today's date.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="962fa-173">(methodName parâmetros)) (<strong>SysQueryRangeUtil</strong> método entre parênteses)</span><span class="sxs-lookup"><span data-stu-id="962fa-173">(methodName(parameters)) (<strong>SysQueryRangeUtil</strong> method between parentheses)</span></span></td>
<td><span data-ttu-id="962fa-174">Correspondendo o valor ou o intervalo de valores especificados pelos parâmetros do método <strong>SysQueryRangeUtil</strong></span><span class="sxs-lookup"><span data-stu-id="962fa-174">Matching the value or range of values that are specified by the parameters of the <strong>SysQueryRangeUtil</strong> method</span></span></td>
<td><span data-ttu-id="962fa-175">Digite um método <strong>SysQueryRangeUtil</strong> com parâmetros que especificam o valor ou o intervalo de valores.</span><span class="sxs-lookup"><span data-stu-id="962fa-175">Type a <strong>SysQueryRangeUtil</strong> method that has parameters that specify the value or range of values.</span></span></td>
<td>
<ol>
<li><span data-ttu-id="962fa-176">Clique em <strong>Contas a receber</strong> &gt; <strong>Faturas</strong> &gt; <strong>Abrir faturas de cliente</strong>.</span><span class="sxs-lookup"><span data-stu-id="962fa-176">Click <strong>Accounts receivable</strong> &gt; <strong>Invoices</strong> &gt; <strong>Open customer invoices</strong>.</span></span></li>
<li><span data-ttu-id="962fa-177">Pressione Ctrl+Shift+F3 para abrir a página <strong>Consulta</strong>.</span><span class="sxs-lookup"><span data-stu-id="962fa-177">Press Ctrl+Shift+F3 to open the <strong>Inquiry</strong> page.</span></span></li>
<li><span data-ttu-id="962fa-178">Na guia <strong>Intervalo</strong>, clique em <strong>Adicionar</strong>.</span><span class="sxs-lookup"><span data-stu-id="962fa-178">On the <strong>Range</strong> tab, click <strong>Add</strong>.</span></span></li>
<li><span data-ttu-id="962fa-179">No campo <strong>Tabela</strong>, selecione <strong>Transações de cliente abertas</strong>.</span><span class="sxs-lookup"><span data-stu-id="962fa-179">In the <strong>Table</strong> field, select <strong>Open customer transactions</strong>.</span></span></li>
<li><span data-ttu-id="962fa-180">No campo <strong>Campo</strong>, selecione <strong>Data de conclusão</strong>.</span><span class="sxs-lookup"><span data-stu-id="962fa-180">In the <strong>Field</strong> field, select <strong>Due date</strong>.</span></span></li>
<li><span data-ttu-id="962fa-181">No campo <strong>Critérios</strong>, digite <strong>(yearRange(-2,0))</strong>.</span><span class="sxs-lookup"><span data-stu-id="962fa-181">In the <strong>Criteria</strong> field, enter <strong>(yearRange(-2,0))</strong>.</span></span></li>
<li><span data-ttu-id="962fa-182">Clique em <strong>OK</strong>.</span><span class="sxs-lookup"><span data-stu-id="962fa-182">Click <strong>OK</strong>.</span></span> <span data-ttu-id="962fa-183">A página de listagem é atualizada e lista as faturas que correspondem aos critérios inseridos.</span><span class="sxs-lookup"><span data-stu-id="962fa-183">The list page is updated and lists the invoices that match the criterion that you entered.</span></span> <span data-ttu-id="962fa-184">Para este exemplo, as faturas que venceram nos dois anos anteriores serão listadas.</span><span class="sxs-lookup"><span data-stu-id="962fa-184">For this example, invoices that were due in the previous two years are listed.</span></span></li>
</ol>
<span data-ttu-id="962fa-185">Consulte a tabela na seção a seguir para obter detalhes adicionais sobre os métodos de data de <strong>SysQueryRangeUtil</strong> e vários exemplos.</span><span class="sxs-lookup"><span data-stu-id="962fa-185">See the table in the next section for additional details about <strong>SysQueryRangeUtil</strong> date methods, and several examples.</span></span></td>
</tr>
</tbody>
</table>

## <a name="advanced-date-queries-that-use-sysqueryrangeutil-methods"></a><span data-ttu-id="962fa-186">As consultas avançadas de datas que usam os métodos SysQueryRangeUtil</span><span class="sxs-lookup"><span data-stu-id="962fa-186">Advanced date queries that use SysQueryRangeUtil methods</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="962fa-187">Método</span><span class="sxs-lookup"><span data-stu-id="962fa-187">Method</span></span></th>
<th><span data-ttu-id="962fa-188">Descrição</span><span class="sxs-lookup"><span data-stu-id="962fa-188">Description</span></span></th>
<th><span data-ttu-id="962fa-189">Exemplo</span><span class="sxs-lookup"><span data-stu-id="962fa-189">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="962fa-190">Dia (_relativeDays=0)</span><span class="sxs-lookup"><span data-stu-id="962fa-190">Day (_relativeDays=0)</span></span></td>
<td><span data-ttu-id="962fa-191">Localiza uma data em relação à data da sessão.</span><span class="sxs-lookup"><span data-stu-id="962fa-191">Find a date relative to the session date.</span></span> <span data-ttu-id="962fa-192">Os valores positivos indicam as datas futuras, e os valores negativos indicam datas passadas.</span><span class="sxs-lookup"><span data-stu-id="962fa-192">Positive values indicate future dates, and negative values indicate past dates.</span></span></td>
<td>
<ul>
<li><span data-ttu-id="962fa-193"><strong>Amanhã</strong> – Digite <strong>(Dia(1))</strong>.</span><span class="sxs-lookup"><span data-stu-id="962fa-193"><strong>Tomorrow</strong> – Enter <strong>(Day(1))</strong>.</span></span></li>
<li><span data-ttu-id="962fa-194"><strong>Hoje</strong> – Digite <strong>(Dia(0))</strong>.</span><span class="sxs-lookup"><span data-stu-id="962fa-194"><strong>Today</strong> – Enter <strong>(Day(0))</strong>.</span></span></li>
<li><span data-ttu-id="962fa-195"><strong>Ontem</strong> – Digite <strong>(Dia(-1))</strong>.</span><span class="sxs-lookup"><span data-stu-id="962fa-195"><strong>Yesterday</strong> – Enter <strong>(Day(-1))</strong>.</span></span></li>
</ul>
</td>
</tr>
<tr>
<td><span data-ttu-id="962fa-196">DayRange (_relativeDaysFrom=0, _relativeDaysTo=0)</span><span class="sxs-lookup"><span data-stu-id="962fa-196">DayRange (_relativeDaysFrom=0, _relativeDaysTo=0)</span></span></td>
<td><span data-ttu-id="962fa-197">Localiza um intervalo de datas em relação à data da sessão.</span><span class="sxs-lookup"><span data-stu-id="962fa-197">Find a range of dates relative to the session date.</span></span> <span data-ttu-id="962fa-198">Os valores positivos indicam as datas futuras, e os valores negativos indicam datas passadas.</span><span class="sxs-lookup"><span data-stu-id="962fa-198">Positive values indicate future dates, and negative values indicate past dates.</span></span></td>
<td>
<ul>
<li><span data-ttu-id="962fa-199"><strong>Últimos 30 dias</strong> – Insira <strong>(DayRange(-30,0))</strong>.</span><span class="sxs-lookup"><span data-stu-id="962fa-199"><strong>Last 30 days</strong> – Enter <strong>(DayRange(-30,0))</strong>.</span></span></li>
<li><span data-ttu-id="962fa-200"><strong>30 dias anteriores e próximos 30 dias</strong> – Insira <strong>(DayRange(-30,30))</strong>.</span><span class="sxs-lookup"><span data-stu-id="962fa-200"><strong>Previous 30 days and next 30 days</strong> – Enter <strong>(DayRange(-30,30))</strong>.</span></span></li>
</ul>
</td>
</tr>
<tr>
<td><span data-ttu-id="962fa-201">GreaterThanDate (_relativeDays=0) GreaterThanUtcDate (_relativeDays=0)</span><span class="sxs-lookup"><span data-stu-id="962fa-201">GreaterThanDate (_relativeDays=0) GreaterThanUtcDate (_relativeDays=0)</span></span></td>
<td><span data-ttu-id="962fa-202">Localiza todas as datas após a data em relação à data especificada.</span><span class="sxs-lookup"><span data-stu-id="962fa-202">Find all dates after the specified relative date.</span></span></td>
<td>
<ul>
<li><span data-ttu-id="962fa-203"><strong>Mais do que em 30 dias a partir de agora</strong> – Digite <strong>(GreaterThanDate (30))</strong>.</span><span class="sxs-lookup"><span data-stu-id="962fa-203"><strong>More than 30 days from now</strong> – Enter <strong>(GreaterThanDate(30))</strong>.</span></span></li>
</ul>
</td>
</tr>
<tr>
<td><span data-ttu-id="962fa-204">GreaterThanUtcNow ()</span><span class="sxs-lookup"><span data-stu-id="962fa-204">GreaterThanUtcNow ()</span></span></td>
<td><span data-ttu-id="962fa-205">Localiza todas as entradas de data/hora após a hora atual.</span><span class="sxs-lookup"><span data-stu-id="962fa-205">Find all date/time entries after the current time.</span></span></td>
<td>
<ul>
<li><span data-ttu-id="962fa-206"><strong>Todas as data/hora futuras</strong> – Digite <strong>(GreaterThanUtcNow ())</strong>.</span><span class="sxs-lookup"><span data-stu-id="962fa-206"><strong>All future date/times</strong> – Enter <strong>(GreaterThanUtcNow())</strong>.</span></span></li>
</ul>
</td>
</tr>
<tr>
<td><span data-ttu-id="962fa-207">LessThanDate (_relativeDays=0) LessThanUtcDate (_relativeDays=0)</span><span class="sxs-lookup"><span data-stu-id="962fa-207">LessThanDate (_relativeDays=0) LessThanUtcDate (_relativeDays=0)</span></span></td>
<td><span data-ttu-id="962fa-208">Localiza todas as datas antes da data em relação à data especificada.</span><span class="sxs-lookup"><span data-stu-id="962fa-208">Find all dates before the specified relative date.</span></span></td>
<td>
<ul>
<li><span data-ttu-id="962fa-209"><strong>Menor do que sete dias a partir de agora</strong> – Digite <strong>(LessThanDate (7))</strong>.</span><span class="sxs-lookup"><span data-stu-id="962fa-209"><strong>Less than seven days from now</strong> – Enter <strong>(LessThanDate(7))</strong>.</span></span></li>
</ul>
</td>
</tr>
<tr>
<td><span data-ttu-id="962fa-210">LessThanUtcNow ()</span><span class="sxs-lookup"><span data-stu-id="962fa-210">LessThanUtcNow ()</span></span></td>
<td><span data-ttu-id="962fa-211">Localiza todas as entradas de data/hora antes da hora atual.</span><span class="sxs-lookup"><span data-stu-id="962fa-211">Find all date/time entries before the current time.</span></span></td>
<td>
<ul>
<li><span data-ttu-id="962fa-212"><strong>Todas as datas/horas anteriores</strong> – Digite <strong>(LessThanUtcNow())</strong>.</span><span class="sxs-lookup"><span data-stu-id="962fa-212"><strong>All past date/times</strong> – Enter <strong>(LessThanUtcNow())</strong>.</span></span></li>
</ul>
</td>
</tr>
<tr>
<td><span data-ttu-id="962fa-213">MonthRange (_relativeFrom=0, _relativeTo=0)</span><span class="sxs-lookup"><span data-stu-id="962fa-213">MonthRange (_relativeFrom=0, _relativeTo=0)</span></span></td>
<td><span data-ttu-id="962fa-214">Localiza um intervalo de datas, com base em meses em relação ao mês atual.</span><span class="sxs-lookup"><span data-stu-id="962fa-214">Find a range of dates, based on months relative to the current month.</span></span></td>
<td>
<ul>
<li><span data-ttu-id="962fa-215"><strong>Dois meses anteriores</strong> – Digite <strong>(MonthRange (- 2,0))</strong>.</span><span class="sxs-lookup"><span data-stu-id="962fa-215"><strong>Previous two months</strong> – Enter <strong>(MonthRange(-2,0))</strong>.</span></span></li>
<li><span data-ttu-id="962fa-216"><strong>Próximos três meses</strong> – Digite <strong>(MonthRange (0,3))</strong>.</span><span class="sxs-lookup"><span data-stu-id="962fa-216"><strong>Next three months</strong> – Enter <strong>(MonthRange(0,3))</strong>.</span></span></li>
</ul>
</td>
</tr>
<tr>
<td><span data-ttu-id="962fa-217">YearRange (_relativeFrom=0, _relativeTo=0)</span><span class="sxs-lookup"><span data-stu-id="962fa-217">YearRange (_relativeFrom=0, _relativeTo=0)</span></span></td>
<td><span data-ttu-id="962fa-218">Localiza um intervalo de datas, com base em anos em relação ao ano atual.</span><span class="sxs-lookup"><span data-stu-id="962fa-218">Find a range of dates, based on years relative to the current year.</span></span></td>
<td>
<ul>
<li><span data-ttu-id="962fa-219"><strong>Próximo ano</strong> – Digite <strong>(YearRange (0, 1))</strong>.</span><span class="sxs-lookup"><span data-stu-id="962fa-219"><strong>Next year</strong> – Enter <strong>(YearRange(0, 1))</strong>.</span></span></li>
<li><span data-ttu-id="962fa-220"><strong>Ano anterior</strong> – Digite <strong>(YearRange(-1,0))</strong>.</span><span class="sxs-lookup"><span data-stu-id="962fa-220"><strong>Previous year</strong> – Enter <strong>(YearRange(-1,0))</strong>.</span></span></li>
</ul>
</td>
</tr>
</tbody>
</table>
