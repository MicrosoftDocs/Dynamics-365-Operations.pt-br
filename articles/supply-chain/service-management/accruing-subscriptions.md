---
title: Acúmulo de subscrições
description: Com as subscrições de serviço, você acumula a receita manualmente nos períodos após a data em que faturou uma transação de taxa.
author: sorenva
ms.date: 04/30/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMASubscriptionGroup
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9ff184b24a264e37613b2302a3d92b74e870c5ac
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2022
ms.locfileid: "8677328"
---
# <a name="accruing-subscriptions"></a>Acúmulo de subscrições 

[!include [banner](../includes/banner.md)]


Com as subscrições de serviço, você acumula a receita manualmente nos períodos após a data em que faturou uma transação de taxa.

Os períodos de acumulação são criados para o período da nota fiscal configurado para a taxa de subscrição e se baseiam no código de período da subscrição.

Você pode acumular e reverter a receita acumulada.

## <a name="reverse-accruals-of-credit-amounts"></a>Reverter acúmulos dos valores de crédito

Se você creditar valores de subscrição faturados, poderá usar dois métodos para reverter os valores acumulados:

  - Você pode reverter cada transação de receita acumulada individualmente antes de criar a proposta de nota de crédito para a transação. Esse é o método manual. (manual)

  - Você pode ter os valores acumulados revertidos na data em que a nota de crédito é lançada ou na data de lançamento original da competência.

Para obter mais informações, consulte [Parâmetros de subscrição (formulário)](/dynamicsax-2012//subscription-parameters-form).

## <a name="setup-requirements"></a>Requisitos de instalação

Para acumular receitas, verifique se os seguintes requisitos de dados são atendidos:

## <a name="account-setup"></a>Configuração da conta

As contas **WIP - subscrição** e **Receita acumulada - subscrição** devem ser configuradas no módulo **Projeto**.

Quando você lança a receita acumulada, o valor da acumulação é debitado da conta **WIP - subscrição** e creditado na conta **Receita acumulada - Subscrição**.

## <a name="set-up-accounts-for-accrual-of-subscription-revenue"></a>Configurar contas para acumulação de receitas de subscrição

1.  Clique em **Gerenciamento e contabilidade de projeto** \> **Configuração** \> **Lançamento** \> **Configuração de lançamento contábil**.

2.  Clique na guia **Contas de receita**, selecione **WIP - subscrição** ou **Receita acumulada - subscrição** para configurar as contas.

## <a name="subscription-group-setup"></a>Configuração do grupo de subscrições

Para acumular receita de subscrições, a caixa de seleção **Acumular receita** deve ser marcada. Isso é encontrado no formulário **Grupos de subscrições** do grupo que está anexado à subscrição. Clique em **Gerenciamento de serviço** \> **Configuração** \> **Subscrições de serviço** \> **Grupos de subscrições**.

## <a name="enable-revenue-accrual-on-a-subscription-group"></a>Habilitar acumulação de receita em um grupo de subscrições

Clique em **Gerenciamento de serviço** \> **Configuração** \> **Subscrições de serviço** \> **Grupos de subscrições**.

## <a name="periods"></a>Períodos

É necessário configurar um código de período de faturamento. A menos que você deseje acumular receitas nos mesmos intervalos de tempo usados no faturamento, também é necessário configurar um período de acúmulo.

A seguinte tabela fornece uma visão geral dos períodos de acumulo que podem ser configurados para cada período de faturamento:

<table>
<colgroup>
<col />
<col />
</colgroup>
<thead>
<tr class="header">
<th><p>Período de faturamento</p></th>
<th><p>Período de acumulação</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Anos</strong></p></td>
<td><ul>
<li><p><strong>Anos</strong></p></li>
<li><p><strong>Trimestre</strong></p></li>
<li><p><strong>Mês</strong></p></li>
<li><p><strong>Dia</strong></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Trimestre</strong></p></td>
<td><ul>
<li><p><strong>Trimestre</strong></p></li>
<li><p><strong>Mês</strong></p></li>
<li><p><strong>Dia</strong></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>Mês</strong></p></td>
<td><ul>
<li><p><strong>Mês</strong></p></li>
<li><p><strong>Dia</strong></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Semana</strong></p></td>
<td><ul>
<li><p><strong>Dia</strong></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>Dia</strong></p></td>
<td><ul>
<li><p><strong>Dia</strong></p></li>
</ul></td>
</tr>
</tbody>
</table>

Configurar o período de faturamento é uma parte obrigatória da configuração geral do grupo de subscrições. Você também pode optar por configurar um período de acúmulo para o grupo de subscrições. Se você configurar um período de acúmulo para o grupo de subscrições, esse período será sugerido no campo **Código de período**. Esse campo é encontrado no formulário **Acumular receita de subscrição**, quando você acumula receita de subscrição. Entretanto, o período de acumulação é uma informação opcional sobre o grupo de subscrições.


> [!NOTE]
> <P>Use o seguinte caminho para abrir o formulário <STRONG>Acumular receita de subscrição</STRONG>. Clique em <STRONG>Gerenciamento de serviço</STRONG> &gt; <STRONG>Periódico</STRONG> &gt; <STRONG>Subscrições de serviço</STRONG> &gt; <STRONG>Acumular receita de subscrição</STRONG>.</P>


## <a name="transactions"></a>Transações

Você pode controlar o número de transações do razão que são criadas quando você lança a receita acumulada. Em subscrições, defina se as transações do razão devem ser criadas como um total ou por linha.

## <a name="specify-the-level-of-posting-details-to-display-for-accrued-transactions"></a>Especificar o nível de detalhes de lançamento a serem exibidos para transações acumuladas

1.  Clique em **Gerenciamento e contabilidade de projetos** \> **Configurar** \> **Parâmetros de gerenciamento e contabilidade de projetos**.

2.  Na guia **Financeiro**, no campo **Fatura**, selecione **Total** ou **Linha**.


## <a name="see-also"></a>Consulte também

[Acumular receita de subscrição](accrue-subscription-revenue.md)

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]