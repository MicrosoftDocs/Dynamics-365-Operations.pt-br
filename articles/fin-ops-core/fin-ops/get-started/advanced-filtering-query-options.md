---
title: Sintaxe avançada de filtragem e consulta
description: Este tópico descreve as opções de filtragem e consulta para a caixa de diálogo Filtro/Classificação Avançada e o operador correspondências no Painel de filtragem ou nos filtros de cabeçalho de coluna de grade.
author: jasongre
ms.date: 03/09/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SysQueryForm
audience: Application User
ms.reviewer: sericks
ms.custom: 3811
ms.assetid: b4969b30-2fe1-4a3c-bbea-725dc37c8b60
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c0fefac5a7a2b299ba606a854824ee456c572487
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8070000"
---
# <a name="advanced-filtering-and-query-syntax"></a>Sintaxe avançada de filtragem e consulta

[!include [banner](../includes/banner.md)]


[!INCLUDE [PEAP](../../../includes/peap-1.md)]

Este tópico descreve as opções de filtragem e consulta disponíveis quando você usa a caixa de diálogo Filtro/Classificação Avançada ou o operador **correspondências** no Painel de filtragem ou nos filtros de cabeçalho de coluna de grade.

## <a name="advanced-query-syntax"></a>Sintaxe de consulta avançada

<table>
<thead>
<tr>
<th>Sintaxe</th>
<th>Descrição de caractere</th>
<th>Descrição</th>
<th>Exemplo</th>
</tr>
</thead>
<tbody>
<tr>
<td><em>valor</em></td>
<td>Igual ao valor inserido que é inserido</td>
<td>Digite o valor para encontrar.</td>
<td><strong>Smith</strong> localiza &quot;Smith&quot;.</td>
</tr>
<tr>
<td>!<em>valor</em> (ponto de exclamação)</td>
<td>Diferente do valor que é inserido</td>
<td>Digite um ponto de exclamação e o valor a ser excluído.</td>
<td><strong>!Smith</strong> localiza todos os valores, exceto &quot;Smith&quot;.</td>
</tr>
<tr>
<td><em>-valor de</em>.<em>valor até</em> (dois pontos finais)</td>
<td>Entre os dois valores que são separados por dois pontos finais</td>
<td>Digite o Valor - de, os dois pontos finais e o Valor - até.</td>
<td><strong>1..10</strong> localiza todos os valores de 1 a 10. No entanto, em um campo de string, <strong>A..C</strong> localiza todos os valores que começam com &quot;A&quot; e &quot;B&quot; e os valores exatamente iguais a &quot;C&quot;. Por exemplo, esta consulta não encontrará &quot;Ca&quot;. Para localizar todos os valores de &quot;A<em>&quot; a &quot;C</em>&quot;, digite <strong>A..D</strong>.</td>
</tr>
<tr>
<td>..<em>valor</em> (dois pontos finais)</td>
<td>Menor ou igual ao valor inserido.</td>
<td>Digite os dois pontos finais e, em seguida, o valor.</td>
<td><strong>..1000</strong> localiza todos os números menores ou iguais a 1000, como &quot;100&quot;, &quot;999,95&quot; e &quot;1.000&quot;.</td>
</tr>
<tr>
<td><em>valor</em>.. (dois pontos finais)</td>
<td>Maior ou igual ao valor inserido.</td>
<td>Digite o valor e, em seguida, dois pontos.</td>
<td><strong>1000..</strong> localiza todos os números maiores ou iguais a 1000, como &quot;1.000&quot;, &quot;1.000,01&quot; e &quot;1.000.000&quot;.</td>
</tr>
<tr>
<td>&gt;<em>valor</em> (sinal maior que)</td>
<td>Maior que o valor inserido</td>
<td>Digite um sinal maior que (<strong>&gt;</strong>) e o valor.</td>
<td><strong>&gt;1000</strong> localiza todos os números maiores ou iguais a 1000, como &quot;1000,01&quot;, &quot;20.000&quot; e &quot;1.000.000&quot;.</td>
</tr>
<tr>
<td>&lt;<em>valor</em> (sinal menor que)</td>
<td>Menor que o valor inserido</td>
<td>Digite um sinal de menor que (<strong>&lt;</strong>) e o valor.</td>
<td><strong>&lt;1000</strong> localiza todo número menor que 1000, como &quot;999,99&quot;, &quot;1&quot; e &quot;-200&quot;.</td>
</tr>
<tr>
<td><em>valor</em>* (asterisco)</td>
<td>Iniciando a partir do valor que é inserido</td>
<td>Digite o valor inicial e, em seguida, um asterisco (<strong>*</strong>).</td>
<td><strong>S*</strong> localiza todas as sequências de caracteres que começam com &quot;S&quot;, como &quot;Stockholm&quot;, &quot;Sydney&quot; e &quot;San Francisco&quot;.</td>
</tr>
<tr>
<td>*<em>valor</em> (asterisco)</td>
<td>Terminando com o valor inserido.</td>
<td>Digite um asterisco e, em seguida, o valor final.</td>
<td><strong>*east</strong> localiza todas as cadeias de caracteres que terminam com &quot;east&quot; como &quot;Northeast&quot; e &quot;Southeast&quot;.</td>
</tr>
<tr>
<td>*<em>valor</em>* (asterisco)</td>
<td>Contendo o valor inserido</td>
<td>Digite um asterisco, um valor e outro asterisco.</td>
<td><strong>*th*</strong> localiza todas as cadeias que contenham &quot;th&quot;, como &quot;Northeast&quot; e &quot;Southeast&quot;.</td>
</tr>
<tr>
<td>? (ponto de interrogação)</td>
<td>Tendo um ou mais caracteres desconhecidos</td>
<td>Digite um ponto de interrogação na posição de caracteres desconhecidos do valor.</td>
<td><strong>Sm?th</strong> localiza &quot;Smith&quot; e &quot;Smyth&quot;.</td>
</tr>
<tr>
<td><em>valor</em>,<em>valor</em> (vírgula)</td>
<td>Correspondendo aos valores separados por vírgulas</td>
<td>Digite todos os critérios, e separe-os usando vírgulas.</td>
<td><strong>A, D, F, G</strong> localiza exatamente &quot;A&quot;, &quot;D&quot;, &quot;F&quot; e &quot;G&quot;. <strong>10, 20, 30, 100</strong> localiza exatamente &quot;10, 20, 30, 100&quot;.</td>
</tr>
<tr>
<td>"" (duas aspas duplas)</td>
<td>Coincidir um valor em branco</td>
<td>Digite duas aspas duplas consecutivas para filtrar valores em branco nesse campo.</td>
<td>Duas aspas duplas consecutivas (<strong>""</strong>) localiza linhas sem nenhum valor para a coluna atual.</td>
</tr>
<tr>
<td>(<span class="code">Consulta do Finance and Operations</span>) (consulta do Finance and Operations entre parênteses)</td>
<td>Corresponder a uma consulta definida</td>
<td>Digite uma consulta como uma instrução SQL entre parênteses usando a linguagem de consulta do Finance and Operations.</td>
  <td><strong><span class="code">((AccountNum LIKE "US *") && (DirPartyTable.Name LIKE "Cont*"))</span></strong><br><br> 
       como um exemplo de sintaxe de uma condição de filtro em um campo da fonte de dados raiz, bem como um campo de uma fonte de dados diferente (para a página Todos os clientes)</td>
</tr>
<tr>
<td>F</td>
<td>Data atual</td>
<td>Digite <strong>T</strong>.</td>
<td><strong>T</strong> corresponde à data de hoje.</td>
</tr>
<tr>
<td>(methodName (parâmetros)) (<strong>SysQueryRangeUtil</strong> método entre parênteses)</td>
<td>Correspondendo o valor ou o intervalo de valores especificados pelos parâmetros do método <strong>SysQueryRangeUtil</strong></td>
<td>Digite um método <strong>SysQueryRangeUtil</strong> com parâmetros que especificam o valor ou o intervalo de valores.</td>
<td>
<ol>
<li>Clique em <strong>Contas a receber</strong> &gt; <strong>Faturas</strong> &gt; <strong>Abrir faturas de cliente</strong>.</li>
<li>Pressione Ctrl+Shift+F3 para abrir a página <strong>Consulta</strong>.</li>
<li>Na guia <strong>Intervalo</strong>, clique em <strong>Adicionar</strong>.</li>
<li>No campo <strong>Tabela</strong>, selecione <strong>Transações de cliente abertas</strong>.</li>
<li>No campo <strong>Campo</strong>, selecione <strong>Data de conclusão</strong>.</li>
<li>No campo <strong>Critérios</strong>, digite <strong>(yearRange(-2,0))</strong>.</li>
<li>Clique em <strong>OK</strong>. A página de listagem é atualizada e lista as faturas que correspondem aos critérios inseridos. Para este exemplo, as faturas que venceram nos dois anos anteriores serão listadas.</li>
</ol>
Consulte a tabela na seção a seguir para obter detalhes adicionais sobre os métodos de data de <strong>SysQueryRangeUtil</strong> e vários exemplos.</td>
</tr>
</tbody>
</table>

## <a name="advanced-date-queries-that-use-sysqueryrangeutil-methods"></a>As consultas avançadas de datas que usam os métodos SysQueryRangeUtil

<table>
<thead>
<tr>
<th>Método</th>
<th>Descrição</th>
<th>Exemplo</th>
</tr>
</thead>
<tbody>
<tr>
<td>Dia (_relativeDays=0)</td>
<td>Localiza uma data em relação à data da sessão. Os valores positivos indicam as datas futuras, e os valores negativos indicam datas passadas.</td>
<td>
<ul>
<li><strong>Amanhã</strong> – Digite <strong>(Dia(1))</strong>.</li>
<li><strong>Hoje</strong> – Digite <strong>(Dia(0))</strong>.</li>
<li><strong>Ontem</strong> – Digite <strong>(Dia(-1))</strong>.</li>
</ul>
</td>
</tr>
<tr>
<td>DayRange (_relativeDaysFrom=0, _relativeDaysTo=0)</td>
<td>Localiza um intervalo de datas em relação à data da sessão. Os valores positivos indicam as datas futuras, e os valores negativos indicam datas passadas.</td>
<td>
<ul>
<li><strong>Últimos 30 dias</strong> – Insira <strong>(DayRange(-30,0))</strong>.</li>
<li><strong>30 dias anteriores e próximos 30 dias</strong> – Insira <strong>(DayRange(-30,30))</strong>.</li>
</ul>
</td>
</tr>
<tr>
<td>GreaterThanDate (_relativeDays=0) GreaterThanUtcDate (_relativeDays=0)</td>
<td>Localiza todas as datas após a data em relação à data especificada.</td>
<td>
<ul>
<li><strong>Mais do que em 30 dias a partir de agora</strong> – Digite <strong>(GreaterThanDate (30))</strong>.</li>
</ul>
</td>
</tr>
<tr>
<td>GreaterThanUtcNow ()</td>
<td>Localiza todas as entradas de data/hora após a hora atual.</td>
<td>
<ul>
<li><strong>Todas as data/hora futuras</strong> – Digite <strong>(GreaterThanUtcNow ())</strong>.</li>
</ul>
</td>
</tr>
<tr>
<td>LessThanDate (_relativeDays=0) LessThanUtcDate (_relativeDays=0)</td>
<td>Localiza todas as datas antes da data em relação à data especificada.</td>
<td>
<ul>
<li><strong>Menor do que sete dias a partir de agora</strong> – Digite <strong>(LessThanDate (7))</strong>.</li>
</ul>
</td>
</tr>
<tr>
<td>LessThanUtcNow ()</td>
<td>Localiza todas as entradas de data/hora antes da hora atual.</td>
<td>
<ul>
<li><strong>Todas as datas/horas anteriores</strong> – Digite <strong>(LessThanUtcNow())</strong>.</li>
</ul>
</td>
</tr>
<tr>
<td>MonthRange (_relativeFrom=0, _relativeTo=0)</td>
<td>Localiza um intervalo de datas, com base em meses em relação ao mês atual.</td>
<td>
<ul>
<li><strong>Dois meses anteriores</strong> – Digite <strong>(MonthRange (- 2,0))</strong>.</li>
<li><strong>Próximos três meses</strong> – Digite <strong>(MonthRange (0,3))</strong>.</li>
</ul>
</td>
</tr>
<tr>
<td>YearRange (_relativeFrom=0, _relativeTo=0)</td>
<td>Localiza um intervalo de datas, com base em anos em relação ao ano atual.</td>
<td>
<ul>
<li><strong>Próximo ano</strong> – Digite <strong>(YearRange (0, 1))</strong>.</li>
<li><strong>Ano anterior</strong> – Digite <strong>(YearRange(-1,0))</strong>.</li>
</ul>
</td>
</tr>
</tbody>
</table>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]