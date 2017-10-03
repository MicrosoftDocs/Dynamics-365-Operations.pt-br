---
title: "Perfis de lançamentos de cliente"
description: "Perfis de postagem de cliente controlam o lançamento de transações de cliente na contabilidade."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustPosting
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 24651
ms.assetid: cb82245e-8c02-429c-b36e-8db0e3e6f7e5
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 45d28110ca93875eb534c69886ac2074ea4fe737
ms.openlocfilehash: b36e75a5f527b41d50cc73e28a0b4e7e5df67e5c
ms.contentlocale: pt-br
ms.lasthandoff: 08/09/2017

---

# <a name="customer-posting-profiles"></a>Perfis de lançamentos de cliente

[!include[banner](../includes/banner.md)]


Perfis de postagem de cliente controlam o lançamento de transações de cliente na contabilidade.

<a name="customer-posting-profiles"></a>Perfis de lançamentos de cliente
-------------------------

Os perfis de lançamento de cliente permitem que você atribua configurações de documento e de contas de contabilidade a todos os clientes, um grupo de clientes ou um único cliente. Essas configurações serão usadas ao criar ordens de venda, faturas de texto livre, pagamentos em dinheiro, cartas de cobrança e notas de juros. Para algumas transações, você pode selecionar um perfil de lançamento diferente dos perfis de lançamento configurados para as transações nesta página e que seja prioritário. 

O perfil de lançamento padrão é definido na Guia Rápida Razão e Imposto na página Parâmetros de contas a receber. O perfil de lançamento padrão é incluído automaticamente no cabeçalho dos novos documentos onde você pode alterá-lo para um perfil de lançamento diferente, se necessário.

Você também pode associar definições de lançamento com os tipos de lançamento de transação na página Definições de lançamento da transação. As definições de lançamento controlam o lançamento de transações de cliente na contabilidade em vez de perfis de lançamento.

## <a name="creating-a-posting-profile"></a>Criando um perfil de lançamento
Especifique as contas contábeis que são usadas no lançamento de transações que usam o perfil de lançamento selecionado. Selecione um código de conta e, sempre que possível, uma conta ou número de grupo para o perfil de lançamento selecionado. No processo de lançamento, o perfil de lançamento mais apropriado para cada transação é localizado procurando a combinação de código de conta, número de conta, grupo e número mais específica segundo esta prioridade:

| Valor do campo **Código de conta** | Valor do campo **Conta/número de grupo**            | Prioridade de pesquisa |
|------------------------------|-------------------------------------------------|-----------------|
| **Tabela**                    | Conta de cliente específico                       | 1               |
| **Grupo**                    | Grupo de clientes atribuído ao cliente | 2               |
| **Todos**                      | Em Branco                                           | 3               |

Se desejar que todas as transações de clientes tenham o mesmo perfil de lançamento, configure somente um perfil de lançamento com a opção Todos no campo Código de conta. Especifique os seguintes valores para configurar o perfil de lançamento:

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Campo</th>
<th>Descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>Perfil de lançamentos</strong></td>
<td>Insira um código para o perfil de lançamento. Por exemplo, você pode criar dois perfis de lançamento para obter uma conta para os saldos de cliente na moeda nacional e outra para os saldos de cliente em uma moeda estrangeira. Você poderia chamar uma conta de Nacional e a outra de Estrangeira.</td>
</tr>
<tr class="even">
<td><strong>Descrição</strong></td>
<td>Insira uma descrição do perfil de lançamento. É usado apenas para melhor identificar o perfil de lançamento quando você o exibe nessa página.</td>
</tr>
<tr class="odd">
<td><strong>Código da conta</strong></td>
<td>Especifique se o perfil de lançamento se aplica a um único cliente, um grupo de clientes ou todos os clientes:
<ul>
<li><strong>Tabela</strong> – O perfil de lançamento se aplica a um único cliente. Selecione a conta de cliente no campo Conta/número de grupo.</li>
<li><strong>Grupo</strong> – O perfil de lançamento se aplica a um grupo de cliente. Selecione o grupo de cliente no campo Conta/número de grupo.</li>
<li><strong>Todos</strong> – O perfil de lançamento se aplica a todos os clientes. Deixe o campo Conta/número de grupo em branco.</li>
</ul></td>
</tr>
<tr class="even">
<td><strong>Número de conta/grupo</strong></td>
<td>Se Tabela for selecionado no campo Código de conta, selecione o número de conta do cliente que está associado ao perfil de lançamento. Se Grupo for selecionado, selecione o grupo de clientes. Se Todos for selecionado, deixe este campo em branco.</td>
</tr>
<tr class="odd">
<td><strong>Conta resumo</strong></td>
<td>Selecione a conta contábil que será usada com conta resumo para os clientes associados ao perfil de lançamento.</td>
</tr>
<tr class="even">
<td><strong>Liquidar conta</strong></td>
<td>Selecione a conta contábil de liquidez usada para previsões de fluxo de caixa. Este campo só aparecerá se as previsões de fluxo de caixa estiverem habilitadas.</td>
</tr>
<tr class="odd">
<td><strong>Pagamentos antecipados de imposto</strong></td>
<td>Selecione a conta para imposto sobre vendas para os pagamentos recebidos antecipadamente.
<div class="alert">
<table>
<thead>
<tr class="header">
<th><img src="https://i-technet.sec.s-msft.com/areas/global/content/clear.gif" title="Observação" alt="Note" id="alert_note" class="cl_IC101471" /><strong>Observação</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Use a página Parâmetros de contas a receber para especificar o perfil de lançamento a ser usado quando um pagamento for marcado como pagamento antecipado.</td>
</tr>
</tbody>
</table>
</div></td>
</tr>
<tr class="even">
<td><strong>Passivos para conta de desconto</strong></td>
<td>Selecione a conta contábil para passivos de desconto.</td>
</tr>
<tr class="odd">
<td><strong>Sequência de cartas de cobrança</strong></td>
<td>Selecione o identificador da sequência de cartas de cobrança a ser usado para clientes aos quais o perfil de lançamento é atribuído.</td>
</tr>
<tr class="even">
<td><strong>Código de juros</strong></td>
<td>Selecione o código de juros a ser usado para o cálculo de juros para clientes aos quais o perfil de lançamento é atribuído.</td>
</tr>
</tbody>
</table>

### 

### <a name="table-restrictions"></a>**Restrições da tabela**

Para as transações com o perfil de lançamento selecionado, especifique se as transações serão automaticamente liquidadas, os juros calculados, e as cartas de cobrança emitidas. Também é possível selecionar a conta usada quando transações com o perfil de lançamento selecionado forem fechadas.

Especifique os seguintes valores para configurar o perfil de lançamento:

| Campo                 | Descrição                                                                                                                                                                                                                                        |
|-----------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Liquidação**        | Selecione esta alternância para habilitar a liquidação automática de transações que possuem este perfil de lançamento. Se esta alternância for desmarcada, você deverá liquidar manualmente as transações usando a página Liquidar transações em aberto ou a página Inserir pagamentos de cliente. |
| **Interesse**          | Selecione esta alternância se os juros precisarem ser calculados sobre saldos em aberto para contas de cliente que usam este perfil. Se esta alternância for desmarcada, os juros não serão calculados para esses clientes.                                           |
| **Carta de cobrança** | Selecione esta alternância se as cartas de cobrança precisarem ser geradas para contas de cliente que usam este perfil. Se esta alternância for desmarcada, as cartas de cobrança não serão geradas para esses clientes.                                                 |
| **Fechar**             | Selecione um perfil de lançamento para o qual alternar quando as transações que tiverem este perfil de lançamento forem fechadas. Uma transação é considerada fechada quando tiver sido integralmente liquidada.                                                                           |



Para obter mais informações, consulte [Visão geral de pagamentos do cliente](../cash-bank-management/tasks/customer-payment-overview.md).


