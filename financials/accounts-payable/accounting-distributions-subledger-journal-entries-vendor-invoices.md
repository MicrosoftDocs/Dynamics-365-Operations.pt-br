---
title: "Distribuições contábeis e entradas no diário-razão auxiliar para faturas de fornecedor"
description: "As distribuições contábeis são usadas para definir como um valor será contabilizado, por exemplo, como a receita, os impostos ou os encargos serão contabilizados em uma fatura de fornecedor. Cada valor a ser contabilizado quando a fatura de fornecedor é lançada no diário terá uma ou várias distribuições contábeis."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: VendEditInvoice
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 26891
ms.assetid: 93dc608a-b5b4-4ec3-83c2-618e3d80a583
ms.search.region: Global
ms.author: mfalkner
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 35133c305457b53abdf761f7fd557bf81bc28cde
ms.contentlocale: pt-br
ms.lasthandoff: 05/25/2017


---

# <a name="accounting-distributions-and-subledger-journal-entries-for-vendor-invoices"></a>Distribuições contábeis e entradas no diário-razão auxiliar para faturas de fornecedor

[!include[banner](../includes/banner.md)]


As distribuições contábeis são usadas para definir como um valor será contabilizado, por exemplo, como a receita, os impostos ou os encargos serão contabilizados em uma fatura de fornecedor. Cada valor a ser contabilizado quando a fatura de fornecedor é lançada no diário terá uma ou várias distribuições contábeis. 

<a name="accounting-distributions"></a>Distribuições contábeis 
-------------------------

Você pode usar os botões a seguir na página Fatura de fornecedor para exibir e, possivelmente, modificar as distribuições contábeis para cada valor da fatura de fornecedor.
-   **Distribuir valores** – Exibir e modificar as distribuições contábeis para uma linha individual e todas as linhas filho, como impostos ou encargos. Também é possível exibir e modificar as distribuições contábeis para a linha filho diretamente da página Transações de imposto ou Transações de encargos.
    -   Modifique valores do cabeçalho da fatura de fornecedor, como encargos ou valores de arredondamento de moeda.
    -   Modifique valores da linha da fatura de fornecedor.
-   **Exibir distribuições** – Exibir as distribuições contábeis para todas as linhas do documento. Você não pode alterar as distribuições contábeis nesse modo de exibição.
    -   Exibir valores de cabeçalho e de linha.

Se a fatura de fornecedor fizer referência a uma ordem de compra, você poderá dividir e alterar as distribuições contábeis para as linhas que contenham um item que não esteja em estoque. Se a linha da fatura de fornecedor não fizer referência a uma linha da ordem de compra, também será possível excluir uma distribuição contábil. Não é possível dividir nem excluir linhas de encargos, impostos e descontos de linha. Você pode alterar a conta contábil, mas não pode alterar os valores nem as porcentagens.
> [!NOTE]                                                                                                                                 
> Se a linha pai contém um item que não está em estoque e as distribuições contábeis são divididas, a linha filho será dividida automaticamente para corresponder às dimensões financeiras da linha pai. As distribuições contábeis para a linha filho não podem ser divididas ou excluídas, mas dependendo da configuração da linha filho, é possível modificar a conta contábil das distribuições contábeis da linha filho.

## <a name="distributing-amounts"></a>Valores de distribuição
Quando você insere uma fatura de fornecedor, cada valor é distribuído da forma a seguir.

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipo da linha da fatura de fornecedor</th>
<th>Ordem de prioridade que determina de onde a conta principal é exibida</th>
<th>Ordem de prioridade que determina qual dimensão financeira padrão será exibida</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Produto em estoque.</td>
<td><ol>
<li>A distribuição contábil para a linha da ordem de compra.</li>
<li>O campo Conta principal quando Despesa de compra para produto for selecionada na página Lançamento.</li>
</ol></td>
<td><ol>
<li>Se a linha da fatura fizer referência a uma linha da ordem de compra, use a distribuição da conta para a linha da ordem de compra.</li>
<li>Use os valores de dimensão financeira padrão na fatura de fornecedor.</li>
</ol></td>
</tr>
<tr class="even">
<td>Uma categoria de compras ou um produto que não está em estoque</td>
<td><ol>
<li>A distribuição contábil da linha da ordem de compra, se a linha da fatura de fornecedor fizer referência a uma linha da ordem de compra.</li>
<li>O campo Conta principal quando Despesas de compra para despesa for selecionada na página Lançamento.</li>
</ol></td>
<td><ol>
<li>Se a linha da fatura fizer referência a uma linha da ordem de compra, use a distribuição da conta para a linha da ordem de compra.</li>
<li>Se a conta principal é uma conta de alocação, use o valor padrão de definição da conta de alocação.</li>
<li>Use os valores de dimensão financeira padrão na fatura de fornecedor.</li>
<li>Use os valores de dimensões financeiras da linha da fatura de fornecedor.</li>
<li>Use os valores de dimensão financeira padrão da conta principal na página Plano de contas.</li>
</ol></td>
</tr>
<tr class="odd">
<td>Ativo fixo</td>
<td><ol>
<li>A distribuição contábil da linha da ordem de compra, se a linha da fatura de fornecedor fizer referência a uma linha da ordem de compra.</li>
<li>Se Aquisição for selecionada no campo Tipo de transação no formulário Fatura de fornecedor, no campo Conta principal, quando Aquisição for selecionada na página Perfis de lançamentos de ativo fixo.</li>
<li>Se Ajuste de aquisição for selecionado no campo Tipo de transação, no campo Conta principal, quando ajuste de Aquisição for selecionado na página Perfis de lançamentos de ativo fixo.</li>
</ol></td>
<td><ol>
<li>Use a distribuição contábil para a linha da ordem de compra, se a linha da fatura fizer referência a uma linha da ordem de compra.</li>
<li>Use os valores de dimensões financeiras da linha da fatura de fornecedor.</li>
<li>Use os valores de dimensão financeira padrão da conta principal na página Plano de contas.</li>
</ol></td>
</tr>
<tr class="even">
<td>Projeto definido na linha da fatura de fornecedor</td>
<td><ol>
<li>A distribuição contábil para a linha da ordem de compra, se a linha da fatura fizer referência a uma linha da ordem de compra.</li>
<li>Se o Saldo for selecionado no campo Lançar custos - Item na página Grupos de projeto, no campo Conta principal, quando Custo for selecionado na página Configuração de lançamento contábil.</li>
<li>Se Lucros e perdas for selecionado no campo Lançar custos - Item na página Grupos de projeto, no campo Conta principal quando Custo - item for selecionado na página Configuração de lançamento contábil.</li>
</ol></td>
<td><ol>
<li>Se a linha da fatura fizer referência a uma linha da ordem de compra, use a distribuição da conta para a linha da ordem de compra.</li>
</ol></td>
</tr>
<tr class="odd">
<td>Desconto de linha</td>
<td><ol>
<li>A distribuição contábil para a linha da ordem de compra, se a linha da fatura fizer referência a uma linha da ordem de compra.</li>
<li>O campo Conta principal quando Desconto for selecionado na página Lançamento.</li>
<li>Se uma conta principal para um desconto não for definida no perfil de lançamentos, a distribuição contábil do preço bruto da linha da ordem de compra.</li>
</ol></td>
<td><ol>
<li>Se a linha da fatura fizer referência a uma linha da ordem de compra, use a distribuição contábil para a linha da ordem de compra.</li>
<li>Use as dimensões financeiras das distribuições contábeis para o preço bruto da linha da fatura de fornecedor.</li>
<li>Use os valores de dimensões financeiras para a linha da fatura de fornecedor.</li>
<li>Use os valores de dimensão financeira padrão da conta principal na página Plano de contas.</li>
</ol></td>
</tr>
<tr class="even">
<td>Encargo de compra, que é inserido na guia Preço e desconto da linha da ordem de compra</td>
<td><ol>
<li>A distribuição contábil para a linha da ordem de compra, se a linha da fatura fizer referência a uma linha da ordem de compra.</li>
<li>A distribuição contábil de preço bruto da linha da ordem de compra.</li>
</ol></td>
<td><ol>
<li>Se a linha da fatura fizer referência a uma linha da ordem de compra, use a distribuição da conta para a linha da ordem de compra.</li>
<li>Use as dimensões financeiras das distribuições contábeis para o preço bruto da linha da fatura de fornecedor.</li>
</ol></td>
</tr>
<tr class="odd">
<td>Encargo da linha</td>
<td><ol>
<li>A distribuição contábil para a linha da ordem de compra, se a linha da fatura fizer referência a uma linha da ordem de compra.</li>
<li>Se a conta contábil for selecionada no campo Tipo de débito no formulário Código de encargos, no campo da Conta de débito na página Código de encargos.</li>
<li>Se Item estiver selecionado no campo Tipo de débito no formulário Código de encargos, a distribuição contábil para o preço bruto na linha da ordem de compra.</li>
<li>Se Cliente/Fornecedor for selecionado no campo Tipo de débito no formulário Código de encargos, no campo da Conta de crédito na página Código de encargos.</li>
</ol></td>
<td><ol>
<li>Se a linha da fatura fizer referência a uma linha da ordem de compra, use a distribuição da conta para a linha da ordem de compra.</li>
<li>Use as dimensões financeiras das distribuições contábeis para o preço bruto da linha da fatura de fornecedor.</li>
<li>Use os valores de dimensões financeiras da linha da fatura de fornecedor.</li>
<li>Use os valores de dimensão financeira padrão da conta principal na página Plano de contas.</li>
</ol></td>
</tr>
<tr class="even">
<td>Impostos, com a seguinte condição:
<ul>
<li>A opção de regras de tributação dos EUA é selecionada na página Parâmetros da contabilidade.</li>
</ul></td>
<td><ol>
<li>A distribuição contábil para a linha da ordem de compra, se a linha da fatura fizer referência a uma linha da ordem de compra.</li>
<li>A distribuição contábil do preço bruto ou encargo.</li>
</ol></td>
<td><ol>
<li>Se a linha da fatura fizer referência a uma linha da ordem de compra, use a distribuição da conta para a linha da ordem de compra.</li>
<li>Use as dimensões financeiras das distribuições contábeis para o preço bruto da linha da fatura de fornecedor.</li>
<li>Use os valores de dimensões financeiras da linha da fatura de fornecedor.</li>
</ol></td>
</tr>
<tr class="odd">
<td>Impostos, com as seguintes condições:
<ul>
<li>A opção de regras de tributação dos EUA é desmarcada na página Parâmetros da contabilidade.</li>
<li>O campo Imposto sobre o uso para o grupo de impostos está desmarcado na página dos Grupos de impostos.</li>
</ul></td>
<td><ol>
<li>Se o valor do imposto é recuperável, o campo Imposto a receber na página Grupos de lançamento contábil.</li>
<li>Se o valor do imposto não for recuperável, o preço bruto ou a distribuição contábil do encargo.</li>
</ol></td>
<td><ol>
<li>Se a linha da fatura fizer referência a uma linha da ordem de compra, use a distribuição da conta para a linha da ordem de compra.</li>
<li>Use as dimensões financeiras do preço bruto ou as distribuições contábeis para o encargo na linha da fatura de fornecedor.</li>
<li>Use os valores de dimensões financeiras da linha da fatura de fornecedor.</li>
<li>Use os valores de dimensão financeira padrão da conta principal na página Plano de contas.</li>
</ol></td>
</tr>
<tr class="even">
<td>Impostos, com as seguintes condições:
<ul>
<li>A opção de regras de tributação dos EUA é desmarcada na página Parâmetros da contabilidade.</li>
<li>O campo Imposto sobre o uso para o grupo de impostos é selecionado na página Grupos de impostos.</li>
</ul></td>
<td><ol>
<li>Se o valor do imposto é recuperável, o campo Imposto a receber na página Grupos de lançamento contábil.</li>
<li>Se o valor do imposto não for recuperável, o campo Despesas de imposto sobre o uso na página Grupos de lançamento contábil.</li>
</ol></td>
<td><ol>
<li>Se a linha da fatura fizer referência a uma linha da ordem de compra, use a distribuição da conta para a linha da ordem de compra.</li>
<li>Use as dimensões financeiras do preço bruto ou as distribuições contábeis para o encargo na linha da fatura de fornecedor.</li>
<li>Use os valores de dimensões financeiras da linha da fatura de fornecedor.</li>
<li>Use os valores de dimensão financeira padrão da conta principal na página Plano de contas.</li>
</ol></td>
</tr>
<tr class="odd">
<td>Encargo de cabeçalho</td>
<td><ol>
<li>Se a conta contábil for selecionada no campo Tipo de débito no formulário Código de encargos, no campo da Conta de débito na página Código de encargos.</li>
<li>Se Cliente/Fornecedor for selecionado no campo Tipo de débito no formulário Código de encargos, no campo da Conta de crédito na página Código de encargos.</li>
</ol></td>
<td><ol>
<li>Se a linha da fatura fizer referência a uma linha da ordem de compra, use a distribuição da conta para a linha da ordem de compra.</li>
<li>Se a conta principal é uma conta de alocação, use o valor padrão de definição da conta de alocação.</li>
<li>Use os valores do modelo padrão de dimensão financeira do cabeçalho da fatura de fornecedor.</li>
<li>Use os valores de dimensões financeiras da linha da fatura de fornecedor.</li>
<li>Use os valores de dimensão financeira padrão da conta principal na página Plano de contas.</li>
</ol></td>
</tr>
<tr class="even">
<td>Desconto do cabeçalho</td>
<td><ol>
<li>O campo Conta principal para o Tipo de lançamento do desconto da fatura de fornecedor na página Contas para transações automáticas.</li>
</ol></td>
<td><ol>
<li>Se a linha da fatura fizer referência a uma linha da ordem de compra, use a distribuição da conta para a linha da ordem de compra.</li>
<li>Use as dimensões financeiras das distribuições contábeis para o preço bruto da linha da fatura de fornecedor.</li>
<li>Use os valores de dimensões financeiras da linha da fatura de fornecedor.</li>
<li>Use os valores de dimensão financeira padrão da conta principal na página Plano de contas.</li>
</ol></td>
</tr>
</tbody>
</table>

 
<a name="distributing-taxes"></a>Impostos de distribuição
------------------

As distribuições contábeis de impostos não podem ser criadas até que os impostos sejam calculados. Para calcular impostos, você deve concluir uma das seguintes tarefas na página Fatura de fornecedor:
-   Exibir total da fatura.
-   Exibir imposto.
-   Exibir o diário-razão auxiliar
-   Exiba as distribuições contábeis para a fatura de fornecedor completa.
-   Coloque a fatura de fornecedor em espera.
-   Lance a fatura de fornecedor.

## <a name="subledger-journals-for-vendor-invoices"></a>Diários-razão auxiliares para faturas de fornecedor
Antes de lançar uma fatura de fornecedor, você pode exibir a entrada contábil total da fatura, incluindo débitos e créditos, para verificar se a fatura está sendo lançada nas contas corretas. Esta exibição de entrada contábil total é chamada de diário-razão auxiliar. 

Se a entrada no diário-razão auxiliar estiver incorreta quando você a visualizar antes de lançar a fatura de fornecedor no diário, não será possível alterá-la. Em vez de isso, você deve alterar as distribuições contábeis ou o perfil de lançamento. As distribuições contábeis são usadas para definir um lado de entrada contábil, de débito ou de crédito. A entrada de conta no diário-razão auxiliar de compensação é criada por perfis de lançamento, como a conta de fornecedor ou imposto.






