---
title: Perfis de lançamentos de cliente
description: Este artigo descreve perfis de lançamento o cliente, que controla o lançamento de transações do cliente para a contabilidade.
author: JodiChristiansen
ms.date: 12/22/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustPosting, CustVendExternalItem
audience: Application User
ms.reviewer: twheeloc
ms.custom: 24651
ms.assetid: cb82245e-8c02-429c-b36e-8db0e3e6f7e5
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d0563040590eefab57706b183281c47a82e46076
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8891685"
---
# <a name="customer-posting-profiles"></a>Perfis de lançamentos de cliente

[!include [banner](../includes/banner.md)]

Este artigo descreve perfis de lançamento o cliente, que controla o lançamento de transações do cliente para a contabilidade.

## <a name="customer-posting-profiles"></a>Perfis de lançamentos de cliente

Os perfis de lançamento de cliente permitem que você atribua configurações de documento e de contas de contabilidade a todos os clientes, um grupo de clientes ou um único cliente. Essas configurações serão usadas ao criar faturas de ordens de venda, faturas de texto livre, faturas do projeto, diários de pagamento, cartas de cobranças e notas de juros. 

O perfil de lançamento padrão é definido na guia **Razão e Imposto** da página **Parâmetros de contas a receber**. Em seguida, ele é automaticamente incluído no cabeçalho de novos documentos. Você pode alterá-lo se for necessário um perfil de lançamento diferente. 

As organizações que aceitam pagamentos antecipados de clientes geralmente configuram um segundo perfil de lançamentos para pagamentos antecipados e o vinculam nos parâmetros como o perfil de lançamento padrão para pagamentos antecipados. Para obter mais informações, consulte [Pagamentos antecipados do cliente](customer-prepayments.md).

Você também pode associar definições de lançamento com os tipos de lançamento de transação na página **Definições de lançamento da transação**. As definições de lançamento são usados, em vez de perfis de lançamento para controlar o lançamento de transações do cliente para a contabilidade. Para obter mais informações, consulte [Definições de lançamento](../general-ledger/posting-definitions.md).

## <a name="creating-a-posting-profile"></a>Criando um perfil de lançamento
Especifique as contas contábeis que são usadas no lançamento de transações que usam o perfil de lançamento selecionado. Selecione um código de conta e, sempre que possível, uma conta ou número de grupo para o perfil de lançamento selecionado. No processo de lançamento, o perfil de lançamento mais apropriado para cada transação é localizado procurando a combinação de código de conta, número de conta, grupo e número mais específica segundo esta prioridade:

| Valor do campo Código de conta | Valor do campo Conta/número de grupo                | Prioridade de pesquisa |
|--------------------------|-------------------------------------------------|-----------------|
| Tabela                    | Conta de cliente específico                       | 1               |
| Agrupar                    | Grupo de clientes atribuído ao cliente | 2               |
| Tudo                      | Em Branco                                           | 3               |

Se quiser que todas as transações de fornecedores tenham o mesmo perfil de lançamento, configure somente um perfil de lançamento com **Tudo** no campo **Código de conta**. Especifique os valores a seguir para configurar o perfil de lançamento.

<table>
<thead>
<tr>
<th>Campo</th>
<th>Descrição</th>
</tr>
</thead>
<tbody>
<tr>
<td>Perfil de lançamento</td>
<td>Insira um código para o perfil de lançamento. Por exemplo, você pode criar dois perfis de lançamento para obter uma conta para os saldos de cliente na moeda nacional e outra para os saldos de cliente em uma moeda estrangeira. Você poderia chamar uma conta de Nacional e a outra de Estrangeira.</td>
</tr>
<tr>
<td>Descrição</td>
<td>Insira uma descrição do perfil de lançamento. É usado apenas para melhor identificar o perfil de lançamento quando você o exibe nessa página.</td>
</tr>
<tr>
<td>Código da conta</td>
<td>Especifique se o perfil de lançamento se aplica a um único cliente, um grupo de clientes ou todos os clientes:
<ul>
<li><b>Tabela</b> – O perfil de lançamento se aplica a um único cliente. Selecione a conta de cliente no campo <b>Conta/Número de grupo</b>.</li>
<li><b>Grupo</b> – O perfil de lançamento se aplica a um grupo de cliente. Selecione o grupo de clientes no campo <b>Conta/Número de grupo</b>.</li>
<li><b>Todos</b> – O perfil de lançamento se aplica a todos os clientes. Deixe o campo <b>Número de conta/grupo</b> em branco.</li>
</ul>
</td>
</tr>
<tr>
<td>Número de conta/grupo</td>
<td>Se <b>Tabela</b> for selecionada no campo <b>Código da conta</b>, selecione o número de conta do cliente que está associado ao perfil de lançamento. Se <b>Grupo</b> for selecionado, selecione o grupo de clientes. Se <b>Todos</b> estiver selecionado, deixe este campo em branco.</td>
</tr>
<tr>
<td>Conta resumo</td>
<td>Selecione a principal conta que será usada com conta comercial de Contas a receber para os clientes associados ao perfil de lançamento. Esta conta é a conta do tipo de lançamento de <b>Saldo do cliente</b>.</td>
</tr>
<tr>
<td>Conta de liquidez para pagamentos</td>
<td>Selecione a conta contábil de liquidez usada para previsões de fluxo de caixa. Este campo só aparecerá se as previsões de fluxo de caixa estiverem habilitadas.</td>
</tr>
<tr>
<td>Pagamentos antecipados de imposto</td>
<td><p>Selecione a conta para imposto sobre vendas para os pagamentos recebidos antecipadamente.</p>
<p><strong>Observação:</strong> Use a página <b>Parâmetros de contas a receber</b> para especificar o perfil de lançamento a ser usado quando um pagamento for marcado como pagamento antecipado.</p>
</td>
</tr>
<tr>
<td>Passivos para conta de desconto</td>
<td>Selecione a conta contábil para passivos de desconto.</td>
</tr>
<tr>
<td>Sequência de cartas de cobrança</td>
<td>Selecione o identificador da sequência de cartas de cobrança a ser usado para clientes aos quais o perfil de lançamento é atribuído.</td>
</tr>
<tr>
<td>Código de juros</td>
<td>Selecione o código de juros a ser usado para o cálculo de juros para clientes aos quais o perfil de lançamento é atribuído.</td>
</tr>
</tbody>
</table>

## <a name="posting-examples"></a>​Exemplos de lançamento​

A tabela a seguir mostra exemplos dos tipos de lançamento padrão com as principais contas e descrições da amostra. A coluna **Débito/crédito** indica se a transação normalmente Debita ou Credita ou em alguns casos, pode lançar. A coluna **Conta de compensação** indica que o tipo de lançamento é uma conta de compensação. Isso significa que o valor lançado nessa conta é revertido automaticamente quando uma transação posterior é lançada. 

| Tipo de lançamento | Exemplo de conta principal | Exemplo de nome de conta principal | Tipo de conta | Débito/Crédito | Conta de compensação | Descrição |
|--------------|----------------------|---------------------------|--------------|--------------|------------------|-------------|
| Saldo do cliente | 130100 | Comércio de contas a receber | Ativo | Ambos | Não | Especifique a conta no campo **Conta resumo**.|
| Nenhum | 110110 | Conta Bancária | Ativo | Ambos | Não | Especifique a conta principal no campo **Conta de liquidez para pagamentos**. Essa conta não é usada para lançamentos. Ela é usada apenas para a previsão de fluxo de caixa. |
| Pagamentos antecipados de imposto | 202900 | Compensação de imposto | Passivo | Ambos | Sim | Selecione a conta para imposto sobre vendas para os pagamentos recebidos antecipadamente. |
| Passivos para conta de desconto | 250600 | Receita e Descontos Diferidos | Passivo | Ambos | Sim | Selecione a conta contábil para passivos de descontos.|     

### <a name="table-restrictions"></a>Restrições da tabela

Para as transações com o perfil de lançamento selecionado, especifique se as transações serão automaticamente liquidadas, os juros calculados, e as cartas de cobrança emitidas. Também é possível selecionar a conta usada quando transações com o perfil de lançamento selecionado forem fechadas.

Especifique os seguintes valores para configurar o perfil de lançamento:

| Campo                 | Descrição                                           |
|-----------------------|-------------------------------------------------------|
| Liquidação        | Selecione esta alternância para habilitar a liquidação automática de transações que possuem este perfil de lançamento. Se esta alternância for desmarcada, você deverá liquidar manualmente as transações usando a página **Liquidar transações abertas** ou a página **Inserir pagamentos de cliente**. |
| Interesse          | Selecione esta alternância se os juros precisarem ser calculados sobre saldos em aberto para contas de cliente que usam este perfil. Se esta alternância for desmarcada, os juros não serão calculados para esses clientes.                                           |
| Carta de cobrança | Selecione esta alternância se as cartas de cobrança precisarem ser geradas para contas de cliente que usam este perfil. Se esta alternância for desmarcada, as cartas de cobrança não serão geradas para esses clientes.                                                 |
| Fechar             | Selecione um perfil de lançamento para o qual alternar quando as transações que tiverem este perfil de lançamento forem fechadas. Uma transação é considerada fechada quando tiver sido integralmente liquidada.             |



Para obter mais informações, consulte [Visão geral de pagamentos do cliente](../cash-bank-management/tasks/customer-payment-overview.md).



[!INCLUDE[footer-include](../../includes/footer-banner.md)]
