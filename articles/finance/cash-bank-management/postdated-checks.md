---
title: Cheques pós-datados
description: Este artigo fornece informações sobre o suporte para cheques pré-datados no Microsoft Dynamics 365 Finance. Cheques pós-datados são cheques emitidos com a finalidade de fazer e receber pagamentos em uma data futura. Consequentemente, a verificação não pode ser descontada até a data especificada.
author: panolte
ms.date: 01/12/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: VendPostDatedChecks, CustPostDatedChecks
audience: Application User
ms.reviewer: roschlom
ms.custom: 21741
ms.assetid: 4eb7c7da-1e6b-4d35-9f41-373b66103229
ms.search.region: Global
ms.author: leguo
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3f5c4d641a3d3ccc326ee56ce7bd05c891b3fa8a
ms.sourcegitcommit: e40a9fac5bac9f57a6dcfe73a1f21856eab9b6a9
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/02/2021
ms.locfileid: "7595453"
---
# <a name="postdated-checks"></a>Cheques pós-datados

[!include [banner](../includes/banner.md)]

Este artigo fornece informações sobre o suporte para cheques pré-datados. Cheques pós-datados são cheques emitidos com a finalidade de fazer e receber pagamentos em uma data futura. Consequentemente, a verificação não pode ser descontada até a data especificada.

O Dynamics 365 Finance oferece suporte ao ciclo completo de gerenciamento de cheques pré-datados em Contas a Receber e em Contas a Pagar, como mostra a tabela a seguir.
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Cenário</th>
<th>Detalhes</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Configurar cheques pós-datados</td>
<td>Você deve configurar um novo método de pagamento, e especificar a rotina de pagamento para limpar contas de cheques emitidos, cheques recebidos e o imposto retido na fonte.</td>
</tr>
<tr class="even">
<td>Registrar e lançar um cheque pós-datado de um fornecedor</td>
<td>Registrar os detalhes de um cheque pós-datado da saída para um fornecedor. Quando o pagamento é lançado, a responsabilidade do fornecedor é reconhecida, mas a conta bancária ainda não é crédito. Em vez disso, uma conta de compensação é usada com essa finalidade. </td>
</tr>
<tr class="odd">
<td>Registrar e lançar um cheque pós-datado para um cliente</td>
<td>Registre os detalhes de um cheque pós-datado recebido de um cliente. Quando o pagamento é lançado, o recebível do cliente é crédito, mas a conta bancária ainda não é débito. Em vez disso, uma conta de compensação é usada com essa finalidade.</td>
</tr>
<tr class="even">
<td>Registrar e lançar um cheque pós-datado de substituição de um cliente ou um fornecedor</td>
<td>
Se o cheque original para um fornecedor ou um cliente for perdido ou danificado, você poderá emitir um cheque pós-datado de substituição. Quando você registra os detalhes do cheque, fornece uma referência ao cheque original e indica se o novo cheque é uma substituição do original. Também é possível lançar o cheque de substituição.</td>
</tr>
<tr class="odd">
<td>Transferir um cheque pós-datado de um cliente a um fornecedor</td>
<td>Ao receber um cheque pós-datado de um cliente, você pode transferir esse cheque para um fornecedor como um pagamento.</td>
</tr>
<tr class="even">
<td>Liquidar um cheque pós-datado de um cliente ou fornecedor</td>
<td>Defina um cheque pós-datado lançado em uma conta de transição para um cliente ou fornecedor quando o cheque finalmente cair. Quando o cheque é liquidado, o banco será finalmente débito ou crédito na conta de compensação anteriormente usada</td>
</tr>
<tr class="odd">
<td>Cancelar um cheque pós-datado de um fornecedor</td>
<td>Você pode cancelar um cheque pós-datado lançado nestas situações: - O cheque é devolvido pelo banco.
- O cheque é aplicado a uma fatura incorreta.
- Um pagamento à vista é feito em vez do cheque.
  </td>
  </tr>
  <tr class="even">
  <td>Parar pagamento de um cheque pós-datado</td>
  <td>Você pode suspender o pagamento de um cheque pós-datado emitido para um fornecedor, por razões como fundos insuficientes, alterações nas condições do contrato com o fornecedor, fornecimento de mercadorias defeituosos pelo fornecedor ou devolução de mercadorias ao fornecedor. Você pode suspender o pagamento somente de cheques não desmarcados.</td>
  </tr>
  </tbody>
  </table>



Para obter mais informações, consulte os seguintes tópicos:

[Configurar cheques pré-datados](tasks/set-up-postdated-checks.md)

[Registrar e lançar um cheque pré-datado para um cliente](tasks/register-post-postdated-check-customer.md)

[Liquidar um cheque pré-datado de um cliente](tasks/settle-postdated-check-customer.md)

[Registrar e lançar um cheque pré-datado para um fornecedor](tasks/register-post-postdated-check-vendor.md) 

[Liquidar um cheque pré-datado de um fornecedor](tasks/settle-postdated-check-vendor.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
