---
title: "Perfis de lançamentos de fornecedores"
description: "Os perfis de lançamentos que controlam o lançamento de transações de fornecedor na contabilidade."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: VendPosting
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 24691
ms.assetid: 18def866-7655-4f0b-b299-eec83098d23a
ms.search.region: Global
ms.author: mfalkner
ms.search.validFrom: 2016-02-28T00:00:00.000Z
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 20d28e22e4e89d0d864a0cbeaadeb568e73e223e
ms.openlocfilehash: c0eb19f128288e97ec21b15e2aaacf44101db282
ms.contentlocale: pt-br
ms.lasthandoff: 07/27/2017

---

# <a name="vendor-posting-profiles"></a>Perfis de lançamentos de fornecedores

[!include[banner](../includes/banner.md)]


Os perfis de lançamentos que controlam o lançamento de transações de fornecedor na contabilidade.

<a name="vendor-posting-profiles"></a>Perfis de lançamentos de fornecedores
-----------------------

Os perfis de lançamento de fornecedor permitem que você atribua configurações de documento e de contas de contabilidade a todos os fornecedores, um grupo de fornecedores ou um único fornecedor. Essas configurações serão usadas quando você criar ordens de compra, faturas de fornecedor e pagamentos em dinheiro. Para algumas transações, você pode selecionar um perfil de lançamento diferente dos perfis de lançamento configurados para as transações nesta página e que seja prioritário. O perfil de lançamento padrão é definido na Guia Rápida Razão e Imposto na página Parâmetros de contas a pagar. O perfil de lançamento padrão é incluído automaticamente no cabeçalho dos novos documentos onde você pode alterá-lo para um perfil de lançamento diferente, se necessário.

Você também pode associar definições de lançamento com os tipos de lançamento de transação na página Definições de lançamento da transação. As definições de lançamento controlam o lançamento de transações de fornecedor na contabilidade em vez de perfis de lançamento.

## <a name="creating-a-posting-profile"></a>Criando um perfil de lançamento
### <a name="setup"></a>**Configuração**

Especifique as contas contábeis que são usadas no lançamento de transações que usam o perfil de lançamento selecionado. Selecione um código de conta e, sempre que possível, uma conta ou número de grupo para o perfil de lançamento selecionado. No processo de lançamento, o perfil de lançamento mais apropriado para cada transação é localizado procurando a combinação de código de conta, número de conta, grupo e número mais específica segundo esta prioridade:

| Valor do campo **Código de conta** | Valor do campo **Conta/número de grupo**        | Prioridade de pesquisa |
|------------------------------|---------------------------------------------|-----------------|
| **Tabela**                    | Conta de fornecedor específica                     | 1               |
| **Grupo**                    | grupo de fornecedores atribuído ao fornecedor | 2               |
| **Todos**                      | Em Branco                                       | 3               |

Se desejar que todas as transações de fornecedores tenham o mesmo perfil de lançamento, configure somente um perfil de lançamento com a opção Todos no campo Código de conta. Especifique os seguintes valores para configurar o perfil de lançamento:

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
<td>Insira um código para o perfil de lançamento. Por exemplo, você pode criar dois perfis de lançamento para obter uma conta para os saldos do fornecedor na moeda nacional e outra para os saldos do fornecedor em moeda estrangeira. Você poderia chamar uma conta de Nacional e a outra de Estrangeira.</td>
</tr>
<tr class="even">
<td><strong>Descrição</strong></td>
<td>Insira uma descrição do perfil de lançamento.</td>
</tr>
<tr class="odd">
<td><strong>Código da conta</strong></td>
<td>Especifique se o perfil de lançamento se aplica a um fornecedor específico, a um grupo de fornecedores ou a todos os fornecedores:
<ul>
<li><strong>Tabela</strong> – O perfil de lançamento se aplica a um único fornecedor. Selecione a conta de fornecedor no campo Conta/número de grupo.</li>
<li><strong>Grupo</strong> – O perfil de lançamento se aplica a um grupo de fornecedor. Selecione o grupo de fornecedor no campo Conta/número de grupo.</li>
<li><strong>Todos</strong> – O perfil de lançamento se aplica a todos os fornecedores. Deixe o campo Conta/número de grupo em branco.</li>
</ul></td>
</tr>
<tr class="even">
<td><strong>Número de conta/grupo</strong></td>
<td>Se Tabela for selecionado no campo Código de conta, selecione o número de conta do fornecedor que está associado ao perfil de lançamento. Se Grupo for selecionado, selecione um grupo de fornecedores. Se Todos for selecionado, deixe este campo em branco.</td>
</tr>
<tr class="odd">
<td><strong>Conta resumo</strong></td>
<td>Selecione a conta contábil a ser usada como conta resumo para os fornecedores cobertos pelo perfil de lançamento.
<div class="alert">
<table>
<thead>
<tr class="header">
<th><img src="https://i-technet.sec.s-msft.com/areas/global/content/clear.gif" title="Observação" alt="Note" id="alert_note" class="cl_IC101471" /><strong>Observação</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Se a opção Alternância de definições de lançamento de uso estiver marcada na página Parâmetros da contabilidade, a definição de lançamento de transação para faturas de fornecedor será usada no lugar da conta resumo.</td>
</tr>
</tbody>
</table>
</div></td>
</tr>
<tr class="even">
<td><strong>Liquidar conta</strong></td>
<td>Selecione a conta contábil de liquidez usada para previsões de fluxo de caixa. Este campo está disponível apenas quando a previsão de fluxo de caixa está habilitada.</td>
</tr>
<tr class="odd">
<td><strong>Pagamentos antecipados de imposto</strong></td>
<td>Selecione a conta para os pagamentos de imposto sobre vendas recebidos antecipadamente.
<div class="alert">
<table>
<thead>
<tr class="header">
<th><img src="https://i-technet.sec.s-msft.com/areas/global/content/clear.gif" title="Observação" alt="Note" id="alert_note" class="cl_IC101471" /><strong>Observação</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>O perfil de lançamento usado quando o pagamento é marcado como um pagamento antecipado é selecionado no perfil de lançamento com o campo do comprovante do diário de pagamentos antecipados na área do razão e do imposto sobre vendas da página Parâmetros de contas a pagar.</td>
</tr>
</tbody>
</table>
</div></td>
</tr>
<tr class="even">
<td><strong>Entrada</strong></td>
<td>Selecione a conta contábil na qual as informações sobre as faturas de fornecedor não aprovadas são lançadas. As informações são inseridas no diário de registro de fatura. Por exemplo, um usuário insere informações muito básicas sobre as faturas do fornecedor quando são recebidas no registro de faturas. Quando o registro de faturas é lançado, as transações são lançadas na conta que é inserida aqui e no campo Contrapartida. Quando as faturas são aprovadas, o débito é transferido da conta de entrada para a conta resumo do fornecedor.</td>
</tr>
<tr class="odd">
<td><strong>Contrapartida</strong></td>
<td>Selecione a conta contábil usada para a compensação das faturas de fornecedor não aprovadas que são atualizadas por meio do registro de faturas. A contrapartida atua como contrapartida para as transações que são lançadas nas contas de entrada. Sendo assim, a conta contém as compras de fornecedor que ainda não foram aprovadas.</td>
</tr>
</tbody>
</table>
 

### <a name="table-restrictions"></a>**Restrições da tabela**

Para as transações com o perfil de lançamento selecionado, especifique se as transações serão automaticamente liquidadas, os juros calculados, e as cartas de cobrança emitidas. Também é possível selecionar a conta usada quando transações com o perfil de lançamento selecionado forem fechadas.

Especifique os seguintes valores para configurar o perfil de lançamento:

| Campo          | Descrição                                                                                                                                                                                                    |
|----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Liquidação** | Selecione esta opção para habilitar a liquidação automática de transações que possuem este perfil de lançamento. Se esta opção for desmarcada, você deverá liquidar manualmente as transações usando a página Liquidar transações em aberto. |
| **Cancelamento**     | Selecione esta opção se você deseja ser capaz de cancelar as transações que possuem este perfil de lançamento.                                                                                                               |
| **Fechar**      | Selecione um perfil de lançamento para o qual alternar quando as transações que tiverem este perfil de lançamento forem fechadas. Uma transação é considerada fechada quando tiver sido integralmente liquidada.                                       |






