---
title: Perfis de lançamentos de fornecedores
description: Os perfis de lançamentos que controlam o lançamento de transações de fornecedor na contabilidade.
author: abruer
ms.date: 11/21/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.custom: 24691
ms.assetid: 18def866-7655-4f0b-b299-eec83098d23a
ms.search.form: VendPosting
ms.openlocfilehash: 09f27ef510f38c10fc265b682a492ba5872b6d3e
ms.sourcegitcommit: fb9b6969218f2b82f0a4c72bfad75387fe00395c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/22/2022
ms.locfileid: "9799590"
---
# <a name="vendor-posting-profiles"></a>Perfis de lançamentos de fornecedores

[!include [banner](../includes/banner.md)]

Os perfis de lançamentos que controlam o lançamento de transações de fornecedor na contabilidade.

## <a name="vendor-posting-profiles"></a>Perfis de lançamentos de fornecedores

Os perfis de lançamento de fornecedor permitem que você atribua configurações de documento e de contas de contabilidade a todos os fornecedores, a um grupo de fornecedores ou a um único fornecedor. Essas configurações serão usadas quando você criar ordens de compra, faturas de fornecedor e pagamentos à vista. Para algumas transações, você pode selecionar um perfil de lançamento diferente e anterior aos perfis de lançamento configurados para as transações desta página. O perfil de lançamento padrão é definido na Guia Rápida **Razão e Imposto** na página **Parâmetros de contas a pagar**. O perfil de lançamento padrão é incluído automaticamente no cabeçalho dos novos documentos em que você pode alterá-lo para um perfil de lançamento diferente, se necessário.

Você também pode associar definições de lançamento com os tipos de lançamento de transação na página **Definições de lançamento da transação**. As definições de lançamento controlam o lançamento de transações de fornecedor na contabilidade em vez de perfis de lançamento.

## <a name="creating-a-posting-profile"></a>Criando um perfil de lançamento
### <a name="setup"></a>**Configuração**

Especifique as contas contábeis que são usadas no lançamento de transações que usam o perfil de lançamento selecionado. Selecione um código de conta e, sempre que possível, uma conta ou número de grupo para o perfil de lançamento selecionado. No processo de lançamento, o perfil de lançamento mais apropriado para cada transação é localizado por meio da busca da combinação de código de conta, número de conta ou grupo e número mais específica na prioridade a seguir.

| Valor do campo **Código de conta** | Valor do campo **Conta/número de grupo**        | Prioridade de pesquisa |
|------------------------------|---------------------------------------------|-----------------|
| **Tabela**                    | Conta de fornecedor específica                     | 1               |
| **Agrupar**                    | Grupo de fornecedores que é atribuído ao fornecedor | 2               |
| **Todas**                      | Em Branco                                       | 3               |

Se desejar que todas as transações de fornecedores tenham o mesmo perfil de lançamento, configure somente um perfil de lançamento com **Tudo** no campo **Código de conta**. Especifique os valores a seguir para configurar o perfil de lançamento.

<table>
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
<li><strong>Tabela</strong> – O perfil de lançamento se aplica a um único fornecedor. Selecione a conta de fornecedor no campo <strong>Número de conta/grupo</strong>.</li>
<li><strong>Grupo</strong> – O perfil de lançamento se aplica a um grupo de fornecedor. Selecione o grupo de fornecedores no campo <strong>Número de conta/grupo</strong>.</li>
<li><strong>Todos</strong> – O perfil de lançamento se aplica a todos os fornecedores. Deixe o campo <strong>Número de conta/grupo</strong> em branco.</li>
</ul></td>
</tr>
<tr class="even">
<td><strong>Número de conta/grupo</strong></td>
<td>Se <strong>Tabela</strong> estiver selecionado no campo <strong>Código de conta</strong>, selecione o número de conta do fornecedor que está associado ao perfil de lançamento. Se <strong>Grupo</strong> estiver selecionado, selecione um grupo de fornecedores. Se <strong>Todos</strong> estiver selecionado, deixe este campo em branco.</td>
</tr>
<tr class="odd">
<td><strong>Conta resumo</strong></td>
<td>Selecione a conta contábil a ser usada como conta resumo para os fornecedores cobertos pelo perfil de lançamento. O parâmetro <strong>Não permitir entrada manual</strong> para esta conta principal será marcado. Se você remover subsequentemente esta conta do perfil de lançamento, valide a configuração <strong>Não permitir entrada manual</strong> na página <strong>Contas principais</strong>. 
<p><strong>Nota:</strong> Se a opção <strong>Usar definições de lançamento</strong> estiver marcada na página <strong>Parâmetros da contabilidade</strong>, a definição de lançamento de transação para faturas de fornecedor será usada em vez da conta de resumo.</p>
</td>
</tr>
<tr class="even">
<td><strong>Liquidar conta</strong></td>
<td>Selecione a conta contábil de liquidez usada para previsões de fluxo de caixa. Este campo está disponível apenas quando a previsão de fluxo de caixa está habilitada.</td>
</tr>
<tr class="odd">
<td><strong>Pagamentos antecipados de imposto</strong></td>
<td>Selecione a conta para os pagamentos de imposto sobre vendas recebidos antecipadamente.
<p><strong>Nota:</strong> O perfil de lançamento usado quando o pagamento é marcado como um pagamento antecipado é selecionado no perfil <strong>Lançamento</strong> com o campo <strong>Comprovante do diário de pagamentos antecipados</strong> na área <strong>Razão e imposto</strong> na página <strong>Parâmetros de contas a pagar</strong>.</p>
</td>
</tr>
<tr class="even">
<td><strong>Entrada</strong></td>
<td>Selecione a conta contábil na qual as informações sobre as faturas de fornecedor não aprovadas são lançadas. As informações são inseridas no <strong>Diário de registro de fatura</strong>. Por exemplo, um usuário insere informações muito básicas sobre as faturas do fornecedor quando são recebidas no registro de faturas. Quando o registro de faturas é lançado, as transações são lançadas na conta que é inserida aqui e no campo <strong>Contrapartida</strong>. Quando as faturas são aprovadas, o débito é transferido da conta de entrada para a conta de resumo do fornecedor.</td>
</tr>
<tr class="odd">
<td><strong>Contrapartida</strong></td>
<td>Selecione a conta contábil usada para a compensação das faturas de fornecedor não aprovadas que são atualizadas por meio do registro de faturas. A contrapartida atua como contrapartida para as transações que são lançadas nas contas de entrada. Sendo assim, a conta contém as compras de fornecedor que ainda não foram aprovadas.</td>
</tr>
</tbody>
</table>


### <a name="table-restrictions"></a>**Restrições da tabela**

Para as transações com o perfil de lançamento selecionado, especifique se as transações serão automaticamente liquidadas, os juros calculados, e as cartas de cobrança emitidas. Também é possível selecionar a conta usada quando transações com o perfil de lançamento selecionado forem fechadas.

Especifique os valores a seguir para configurar o perfil de lançamento

| Campo          | Descrição             |
|----------------|--------------------------------------------------------------------------|
| **Liquidação** | Selecione esta opção para habilitar a liquidação automática de transações que possuem este perfil de lançamento. Se esta opção for desmarcada, você deverá liquidar manualmente as transações usando a página **Liquidar transações em aberto**. |
| **Cancelamento**     | Selecione esta opção se você deseja ser capaz de cancelar as transações que possuem este perfil de lançamento.                              |
| **Fechar**      | Selecione um perfil de lançamento para o qual alternar quando as transações que tiverem este perfil de lançamento forem fechadas. Uma transação é considerada fechada quando tiver sido integralmente liquidada.                                       |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
