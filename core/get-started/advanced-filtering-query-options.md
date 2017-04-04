---
title: "Sintaxe avançado de filtragem e consulta"
description: "Este artigo descreve a filtragem e as opções de consulta disponíveis quando você usa o operador &quot;correspondências&quot; na caixa de diálogo Filtro/Classificação Avançado."
author: jasongre
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: SysQueryForm
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 3811
ms.assetid: b4969b30-2fe1-4a3c-bbea-725dc37c8b60
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 5ee7a04572e350a7c08d0418bade6d332aa920c6
ms.lasthandoff: 03/31/2017


---

# <a name="advanced-filtering-and-query-syntax"></a>Sintaxe avançado de filtragem e consulta

Este artigo descreve a filtragem e as opções de consulta disponíveis quando você usa o operador "correspondências" na caixa de diálogo Filtro/Classificação Avançado.

<a name="advanced-query-syntax"></a>Sintaxe de consulta Avançado
---------------------

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th>Sintaxe</th>
<th>Descrição de caractere</th>
<th>descrição</th>
<th>Exemplo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><em>valor</em></td>
<td>Igual ao valor inserido que é inserido</td>
<td>Digite o valor para encontrar.</td>
<td><strong>Smith</strong> Smith&quot;localiza &quot;.</td>
</tr>
<tr class="even">
<td>!<em>valor</em> (ponto de exclamação)</td>
<td>Diferente do valor que é inserido</td>
<td>Digite um ponto de exclamação e o valor a ser excluído.</td>
<td><strong>! Smith</strong> localiza todos os valores exceto &quot;Smith&quot;.</td>
</tr>
<tr class="odd">
<td><em>-valor de</em>.<em>valor até</em> (dois pontos finais)</td>
<td>Entre os dois valores que são separados por dois pontos finais</td>
<td>Digite o Valor - de, os dois pontos finais e o Valor - até.</td>
<td><strong>1..10</strong> localiza todos os valores de 1 a 10. Entretanto, em um campo de string, <strong>A.C</strong> localiza todos os valores que começam com &quot;A&quot; e &quot;B&quot;, e os valores exatamente iguais &quot;que estão à C&quot;. por exemplo, essa consulta o não &quot;localizarão CA.&quot; Para localizar todos os valores &quot;com &quot;da* C*&quot;, digite.</td>
</tr>
<tr class="even">
<td>..<em>valor</em> (dois pontos finais)</td>
<td>Menor ou igual ao valor inserido.</td>
<td>Digite os dois pontos finais e, em seguida, o valor.</td>
<td><strong>. .1000</strong> localiza todos os números que seja menor ou igual a 1000, como &quot;100&quot;, &quot;999.95&quot;, e &quot;1,000&quot;.</td>
</tr>
<tr class="odd">
<td><em>valor</em>.. (dois pontos finais)</td>
<td>Maior ou igual ao valor inserido.</td>
<td>Digite o valor e, em seguida, dois pontos.</td>
<td><strong>1000..</strong> localiza todos os números que for maior ou igual a 1000, como &quot;1,000&quot;, &quot;1,000.01&quot;, e &quot;1,000,000&quot;.</td>
</tr>
<tr class="even">
<td>&gt;<em>valor</em> (maior que o sinal)</td>
<td>Maior que o valor inserido</td>
<td>Digite uma maior que assinam (<strong>&gt;</strong>) e o valor.</td>
<td><strong>&gt;1000</strong> localiza todos os números que for maior que 1000, como &quot;1000.01&quot;, &quot;20,000&quot;, e &quot;1,000,000&quot;.</td>
</tr>
<tr class="odd">
<td>&lt;<em>valor</em> (menor que o sinal)</td>
<td>Menor que o valor inserido</td>
<td>Digite menor que assinam (<strong>&lt;</strong>) e o valor.</td>
<td><strong>&lt;1000</strong> localiza todos os números que seja menor de 1000, como &quot;999.99&quot;, &quot;1&quot;, e &quot;-200&quot;.</td>
</tr>
<tr class="even">
<td><em>valor</em>* (asterisco)</td>
<td>Iniciando a partir do valor que é inserido</td>
<td>Digite o valor inicial e um asterisco (<strong>*</strong>).</td>
<td><strong>S*</strong> localiza todas as strings que inicie com &quot;p&quot;, como &quot;, &quot;Stockholm&quot;Sydney&quot;San&quot;Francisco, e &quot;.</td>
</tr>
<tr class="odd">
<td>*<em>value</em> (asterisk)</td>
<td>Terminando com o valor inserido.</td>
<td>Digite um asterisco e, em seguida, o valor final.</td>
<td><strong>*east</strong> localiza todas as strings que terminar com &quot;leste&quot;, como &quot;o nordeste&quot; e &quot;o sudeste&quot;.</td>
</tr>
<tr class="even">
<td>*<em>valor</em>* (asterisco)</td>
<td>Contendo o valor inserido</td>
<td>Digite um asterisco, um valor e outro asterisco.</td>
<td><strong>*th*</strong> localiza todas as strings que contenha th&quot;, como &quot;o nordeste&quot; e &quot;o sudeste&quot;.</td>
</tr>
<tr class="odd">
<td>? (ponto de interrogação)</td>
<td>Tendo um ou mais caracteres desconhecidos</td>
<td>Digite um ponto de interrogação na posição de caracteres desconhecidos do valor.</td>
<td><strong>Sm? th</strong> Smith&quot; localiza &quot;Smyth&quot;e &quot;.</td>
</tr>
<tr class="even">
<td><em>valor</em>,<em>valor</em> (vírgula)</td>
<td>Correspondendo aos valores separados por vírgulas</td>
<td>Digite todos os critérios, e separe-os usando vírgulas.</td>
<td><strong>A, D, F, G</strong> localiza exatamente &quot;10&quot;localiza&quot;exatamente &quot;da,&quot;D, &quot;F&quot;<strong>10, 20, 30, 100</strong> de, e &quot;. G, 20, 30, 100&quot;.</td>
</tr>
<tr class="odd">
<td>(<span class="code">Instrução SQL</span>) (instrução SQL entre parênteses)</td>
<td>Correspondendo a uma consulta definida</td>
<td>Digite uma consulta como instrução SQL entre parênteses.</td>
<td><strong><span class="code">(fonte de dados. Fieldname! = &quot;A&quot;)</span></strong></td>
</tr>
<tr class="even">
<td>Q</td>
<td>Data atual</td>
<td>Digite <strong>T</strong>.</td>
<td><strong>T</strong> corresponde à data de hoje.</td>
</tr>
<tr class="odd">
<td>(methodName parâmetros)) (<strong>SysQueryRangeUtil</strong> método entre parênteses)</td>
<td>Correspondendo o valor ou o intervalo de valores especificados pelos parâmetros do método <strong>SysQueryRangeUtil</strong></td>
<td>Digite um método <strong>SysQueryRangeUtil</strong> com parâmetros que especificam o valor ou o intervalo de valores.</td>
<td><ol>
<li>Clique <strong>Contas a receber</strong> &gt; <strong>Notas fiscais</strong> &gt; <strong>Notas fiscais de cliente em aberto</strong>.</li>
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
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Método</th>
<th>Descrição</th>
<th>Exemplo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Dia (_relativeDays=0)</td>
<td>Localiza uma data em relação à data da sessão. Os valores positivos indicam as datas futuras, e os valores negativos indicam datas passadas.</td>
<td><ul>
<li><strong>Amanhã</strong> – Digite <strong>(Dia(1))</strong>.</li>
<li><strong>Hoje</strong> – Digite <strong>(Dia(0))</strong>.</li>
<li><strong>Ontem</strong> – Digite <strong>(Dia(-1))</strong>.</li>
</ul></td>
</tr>
<tr class="even">
<td>DayRange (_relativeDaysFrom=0, _relativeDaysTo=0)</td>
<td>Localiza um intervalo de datas em relação à data da sessão. Os valores positivos indicam as datas futuras, e os valores negativos indicam datas passadas.</td>
<td><ul>
<li><strong>Últimos 30 dias</strong> – Insira <strong>(DayRange(-30,0))</strong>.</li>
<li><strong>30 dias anteriores e próximos 30 dias</strong> – Insira <strong>(DayRange(-30,30))</strong>.</li>
</ul></td>
</tr>
<tr class="odd">
<td>GreaterThanDate (_relativeDays=0) GreaterThanUtcDate (_relativeDays=0)</td>
<td>Localiza todas as datas após a data em relação à data especificada.</td>
<td><ul>
<li><strong>Mais do que em 30 dias a partir de agora</strong> – Digite <strong>(GreaterThanDate (30))</strong>.</li>
</ul></td>
</tr>
<tr class="even">
<td>GreaterThanUtcNow ()</td>
<td>Localiza todas as entradas de data/hora após a hora atual.</td>
<td><ul>
<li><strong>Todas as data/hora futuras</strong> – Digite <strong>(GreaterThanUtcNow ())</strong>.</li>
</ul></td>
</tr>
<tr class="odd">
<td>LessThanDate (_relativeDays=0) LessThanUtcDate (_relativeDays=0)</td>
<td>Localiza todas as datas antes da data em relação à data especificada.</td>
<td><ul>
<li><strong>Menor do que sete dias a partir de agora</strong> – Digite <strong>(LessThanDate (7))</strong>.</li>
</ul></td>
</tr>
<tr class="even">
<td>LessThanUtcNow ()</td>
<td>Localiza todas as entradas de data/hora antes da hora atual.</td>
<td><ul>
<li><strong>Todas as datas/horas anteriores</strong> – Digite <strong>(LessThanUtcNow())</strong>.</li>
</ul></td>
</tr>
<tr class="odd">
<td>MonthRange (_relativeFrom=0, _relativeTo=0)</td>
<td>Localiza um intervalo de datas, com base em meses em relação ao mês atual.</td>
<td><ul>
<li><strong>Dois meses anteriores</strong> – Digite <strong>(MonthRange (- 2,0))</strong>.</li>
<li><strong>Próximos três meses</strong> – Digite <strong>(MonthRange (0,3))</strong>.</li>
</ul></td>
</tr>
<tr class="even">
<td>YearRange (_relativeFrom=0, _relativeTo=0)</td>
<td>Localiza um intervalo de datas, com base em anos em relação ao ano atual.</td>
<td><ul>
<li><strong>Próximo ano</strong> – Digite <strong>(YearRange (0, 1))</strong>.</li>
<li><strong>Ano anterior</strong> – Digite <strong>(YearRange(-1,0))</strong>.</li>
</ul></td>
</tr>
</tbody>
</table>




