---
title: Distribuições contábeis e entradas de diário para faturas de texto livre
description: As distribuições contábeis são usadas para definir como um valor será contabilizado, assim como a receita, os impostos ou os encargos serão contabilizados em uma fatura de texto livre. Cada valor que deve ser contabilizado terá uma ou mais distribuições contábeis quando a fatura de texto livre for lançada no diário.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustFreeInvoice
audience: Application User
ms.reviewer: roschlom
ms.custom: 3141
ms.assetid: fecd17a2-d7b4-4a20-ac81-eb71abbfa9d1
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f3ee26825ec48a8e8e32401ceaa8c80ecd679d2e
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4993180"
---
# <a name="accounting-distributions-and-subledger-entries-for-free-text-invoices"></a>Distribuições contábeis e entradas no razão auxiliar para faturas de texto livre

[!include [banner](../includes/banner.md)]

As distribuições contábeis são usadas para definir como um valor será contabilizado, assim como a receita, os impostos ou os encargos serão contabilizados em uma fatura de texto livre. Cada valor que deve ser contabilizado terá uma ou mais distribuições contábeis quando a fatura de texto livre for lançada no diário.

<a name="accounting-distributions"></a>Distribuições contábeis
------------------------

Você pode usar os botões a seguir na página Fatura de texto livre para exibir e, possivelmente, alterar as distribuições contábeis de cada valor da fatura de texto livre.

-   **Distribuir valores**—Exibir e modificar as distribuições contábeis para uma linha individual e todas as linhas filho, como impostos ou encargos. Também é possível exibir e modificar as distribuições contábeis para a linha filho diretamente da página Transações de imposto ou Transações de encargos.
    -   Modifique os valores do cabeçalho da fatura de texto livre, como encargos ou valores de arredondamento de moeda.
    -   Modifique os valores da linha da fatura de texto livre.
-   **Exibir distribuições** - Exibir as distribuições contábeis para todas as linhas do documento. Você não pode alterar as distribuições contábeis nesse modo de exibição.
    -   Exibir valores de cabeçalho e de linha.

## <a name="distributing-amounts"></a>Valores de distribuição
Quando você insere uma fatura de texto livre, cada valor será distribuído como a seguir.

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Digite o valor monetário</th>
<th>Da onde a conta principal é exibida</th>
<th>Ordem de prioridade que determina qual dimensão financeira padrão será exibida</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Linha da fatura de texto livre</td>
<td>A conta contábil na linha da fatura de texto livre.</td>
<td><ol>
<li>Se a conta principal é uma conta de alocação, use o valor padrão de definição da conta de alocação.</li>
<li>Se a conta principal não é uma conta de alocação, use o modelo padrão de dimensão financeira na linha da fatura de texto livre.</li>
<li>Use os valores de dimensão financeira padrão na linha da fatura de texto livre.</li>
<li>Use os valores de dimensão financeira padrão da conta contábil na página Plano de contas.</li>
</ol></td>
</tr>
<tr class="even">
<td>Linha da fatura de texto livre de uma combinação do número ativo fixo e o método de depreciação
<div class="alert">
<table>
<thead>
<tr class="header">
<th><strong>Nota </strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>A conta principal na linha da fatura de texto livre será uma conta de alienação de ativo fixo.</td>
</tr>
</tbody>
</table>
</div></td>
<td>A conta contábil na linha da fatura de texto livre.</td>
<td><ol>
<li>Use os valores de dimensão financeira padrão na linha da fatura de texto livre.</li>
<li>Use os valores de dimensão financeira padrão da conta contábil na página Plano de contas.</li>
</ol></td>
</tr>
<tr class="odd">
<td>Valor do desconto da fatura de texto livre</td>
<td>A conta principal para descontos do cliente na página Descontos à vista.</td>
<td><ol>
<li>Se a conta principal é uma conta de alocação, use o valor padrão de definição da conta de alocação.</li>
<li>Se a conta principal não é uma conta de alocação, use o modelo padrão de dimensão financeira na linha da fatura de texto livre.</li>
<li>Use os valores de dimensão financeira padrão na linha da fatura de texto livre.</li>
<li>Use os valores de dimensão financeira padrão da conta contábil na página Plano de contas.</li>
</ol></td>
</tr>
<tr class="even">
<td>Valor do imposto da fatura de texto livre</td>
<td>O campo Imposto a pagar na página Grupos de lançamento contábil.</td>
<td><ol>
<li>Use as dimensões financeiras definidas no valor da linha da fatura de texto livre ou em distribuições do valor da linha do encargo.</li>
<li>Use os valores de dimensão financeira padrão na linha da fatura de texto livre.</li>
<li>Use os valores de dimensão financeira padrão da conta contábil na página Plano de contas.</li>
</ol></td>
</tr>
<tr class="odd">
<td>Valor da linha de encargos da fatura de texto livre</td>
<td>O campo Conta de crédito na página Código de encargos.</td>
<td><ol>
<li>Se a conta principal é uma conta de alocação, use o valor padrão de definição da conta de alocação.</li>
<li>Se a conta principal não é uma conta de alocação, use o modelo padrão de dimensão financeira na linha da fatura de texto livre.</li>
<li>Use os valores de dimensão financeira padrão na linha da fatura de texto livre.</li>
<li>Use os valores de dimensão financeira padrão da conta contábil na página Plano de contas.</li>
</ol></td>
</tr>
</tbody>
</table>

## <a name="distributing-taxes"></a>Impostos de distribuição
As distribuições contábeis de impostos não podem ser criadas até que os impostos sejam calculados. Para calcular impostos, você deve concluir uma das seguintes tarefas no formulário Fatura de texto livre:
-   Exibir imposto.
-   Exibir total da fatura.
-   Exibir caixa registradora.
-   Exibir distribuições contábeis de toda a fatura de texto livre.
-   Exibir o diário-razão auxiliar

## <a name="subledger-journals-for-free-text-invoices"></a>Diário-razão auxiliar de faturas de texto livre
Você pode exibir a entrada contábil total da fatura antes de lançar uma fatura de texto livre, incluindo débitos e créditos, para verificar se a fatura está sendo lançada nas contas corretas. Esta exibição de entrada contábil total é chamada de diário-razão auxiliar. Se a entrada no diário-razão auxiliar estiver incorreta quando você exibi-la antes de lançar em diário a fatura de texto livre, não será possível alterar a entrada no diário-razão auxiliar. Em vez de isso, você deve alterar as distribuições contábeis ou o perfil de lançamento. As distribuições contábeis são usadas para definir um lado de entrada contábil, de débito ou de crédito. A entrada de conta no diário-razão auxiliar de compensação é criada a partir dos perfis de lançamento, como a conta de cliente ou imposto.



