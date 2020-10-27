---
title: Relatório de classificação por vencimento de clientes
description: O relatório Classificação por vencimento do cliente exibe os saldos devidos de clientes, classificados por intervalo de datas ou por período de classificação por vencimento.
author: JodiChristiansen
manager: AnnBe
ms.date: 10/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 062e8972c879d770cc4106c2811cd4c16fff0446
ms.sourcegitcommit: 25909c6ad3616e4f75a2fe006057dda18d7cc856
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/09/2020
ms.locfileid: "3974852"
---
# <a name="customer-aging-report"></a>Relatório de classificação por vencimento de clientes 

O relatório **Classificação por vencimento do cliente** exibe os saldos devidos de clientes, classificados por intervalo de datas ou por período de classificação por vencimento.

Quando você gera o relatório, os seguintes parâmetros padrão serão exibidos. Você pode usar esses parâmetros para filtrar os dados que são exibidos no relatório. Para saber mais, consulte [Configurar coleções](set-up-collections.md).

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Campo</p></th>
<th><p>descrição</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Classificação de cobrança</strong></p></td>
<td><p>Selecione uma ou mais classificações de cobrança para incluir no relatório.</p>
<div class="alert">

**Observação:** esse controle só estará disponível se a chave de configuração <STRONG>Setor Público</STRONG> estiver selecionada.</P>


</div></td>
</tr>
<tr class="even">
<td><p><strong>Incluir transações sem uma classificação de cobrança</strong></p></td>
<td><p>Se essa caixa de seleção for marcada, todas as transações que não têm uma classificação de cobrança atribuída serão exibidas no relatório.</p>
<div class="alert">

**Observação:** esse controle só estará disponível se a chave de configuração <STRONG>Setor Público</STRONG> estiver selecionada.</P>

</div></td>
</tr>
<tr class="odd">
<td><p><strong>Classificação por vencimento a partir de</strong></p></td>
<td><p>Insira a data usada no bucket de classificação por vencimento atual.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Saldo a partir de</strong></p></td>
<td><p>Insira a data para a qual deseja exibir os saldos do cliente. Isso também é conhecido como data de fechamento para transações.</p></td>
</tr>
<tr class="even">
<td><p><strong>Data inicial:</strong></p></td>
<td><p>Insira uma data que esteja no primeiro intervalo do período ou no período de classificação por vencimento para incluir no relatório.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Critérios</strong></p></td>
<td><p>Selecione o tipo de data no qual basear o relatório.</p>
<ul>
<li><p><strong>Data da transação</strong> – a data de lançamento das transações. Por exemplo, pode ser uma data da fatura que é a base para o cálculo da data de vencimento.</p></li>
<li><p><strong>Data de vencimento</strong> – a data de vencimento das transações, com base nas condições de pagamento.</p></li>
<li><p><strong>Data do documento</strong> – uma data do documento definida pelo usuário que é a base para o cálculo da data de vencimento.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Definição do período de classificação por vencimento</strong></p></td>
<td><p>Selecione uma definição de período de classificação por vencimento. O campo <strong>Intervalo</strong> não será usado se você selecionar uma definição de período de classificação por vencimento.</p>
<p>As definições do período de classificação por vencimento com mais de seis períodos de classificação por vencimento não podem ser usadas no relatório impresso.</p>
<div class="alert">

**Observação:** você pode configurar períodos de classificação por vencimento na página <STRONG>Definições de período de classificação por vencimento</STRONG>.</P>


</div></td>
</tr>
<tr class="odd">
<td><p><strong>Imprimir a descrição do período de classificação por vencimento</strong></p></td>
<td><p>Selecione <strong>Sim</strong> para incluir descrições na parte superior de cada coluna de período de classificação por vencimento do relatório. Selecione <strong>Não</strong> para imprimir o relatório sem cabeçalhos de coluna.</p></td>
</tr>
<tr class="even">
<td><p><strong>Intervalo</strong></p></td>
<td><p>Defina o período a ser usado digitando o número de unidades de dias ou meses em cada período. Por exemplo, para ver as informações de classificação por vencimento por semana, digite 7 nesse campo e selecione <strong>Dia</strong> no campo <strong>Dia/Mês</strong>.</p>
<div class="alert">

**Observação:** as informações que você digitar no campo serão usadas somente se você não tiver selecionado uma definição de período de classificação por vencimento. Caso contrário, a direção de impressão será definida na definição do período de classificação por vencimento.</P>


</div></td>
</tr>
<tr class="odd">
<td><p><strong>Dia/mês</strong></p></td>
<td><p>Selecione a unidade, <strong>Dia</strong> ou <strong>Mês</strong>, usada para definir o campo <strong>Intervalo</strong>.</p></td>
</tr>
<tr class="even">
<td><p><strong>Direção de impressão</strong></p></td>
<td><p>Selecione se deseja calcular saldos e imprimir o relatório de classificação por vencimento para períodos passados ou futuros. As datas são avaliadas em relação à data selecionada no campo <strong>Saldo como em</strong>. Selecione <strong>Recuar</strong> para mostrar informações sobre períodos passados. Selecione <strong>Avançar</strong> para mostrar informações para períodos futuros.</p>

**Observação:** as informações que você digitar no campo serão usadas somente se você não tiver selecionado uma definição de período de classificação por vencimento.</P>


</div></td>
</tr>
<tr class="odd">
<td><p><strong>Detalhes</strong></p></td>
<td><p>Selecione para listar incluir as transações incluídas nos saldos mostrados no relatório.</p></td>
</tr>
<tr class="even">
<td><p><strong>Incluir valores na moeda de transação</strong></p></td>
<td><p>Selecione para incluir valores na moeda da transação além dos valores na moeda contábil. Se essa caixa de seleção não estiver marcada, os valores no relatório só serão exibidos na moeda contábil.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Saldo negativo</strong></p></td>
<td><p>Selecione para incluir contas de cliente que têm saldos negativos.</p></td>
</tr>
<tr class="even">
<td><p><strong>Excluir as contas de saldo zero</strong></p></td>
<td><p>Selecione para excluir contas de cliente com saldo zerado.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Posição de pagamento</strong></p></td>
<td><p>Selecione para exibir os pagamentos que não foram liquidados. Eles são exibidos na primeira coluna do relatório.</p></td>
</tr>
</tbody>
</table>

