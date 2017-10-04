---
title: "Cheques pós-datados"
description: "Este artigo fornece informações sobre o suporte para cheques pós-datados no Microsoft Dynamics 365 for Finance and Operations, edição Enterprise. Cheques pós-datados são cheques emitidos com a finalidade de fazer e receber pagamentos em uma data futura. Consequentemente, a verificação não pode ser descontada até a data especificada."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 21741
ms.assetid: 4eb7c7da-1e6b-4d35-9f41-373b66103229
ms.search.region: Global
ms.author: leguo
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 45d28110ca93875eb534c69886ac2074ea4fe737
ms.openlocfilehash: 6a535b5f1192b7c27383cb8ece53f76a9c76f047
ms.contentlocale: pt-br
ms.lasthandoff: 08/09/2017

---

# <a name="postdated-checks"></a>Cheques pós-datados

[!include[banner](../includes/banner.md)]


Este artigo fornece informações sobre o suporte para cheques pós-datados no Microsoft Dynamics 365 for Finance and Operations, edição Enterprise. Cheques pós-datados são cheques emitidos com a finalidade de fazer e receber pagamentos em uma data futura. Consequentemente, a verificação não pode ser descontada até a data especificada.

O Microsoft Dynamics 365 for Finance and Operations oferece suporte ao ciclo completo de gerenciamento de cheques pós-datados em contas a receber e em contas a pagar, como mostra a tabela a seguir.
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
- Um pagamento à vista é feito no cheque.
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



