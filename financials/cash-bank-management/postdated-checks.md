---
title: "Cheques pós-datados"
description: "Este artigo fornece informações sobre o suporte para cheques pré-datados no Microsoft Dynamics 365 for Operations. Cheques pré-datados são cheques emitidos com a finalidade de fazer e receber pagamentos em uma data futura. Consequentemente, a verificação não pode ser descontada até a data especificada."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 21741
ms.assetid: 4eb7c7da-1e6b-4d35-9f41-373b66103229
ms.search.region: Global
ms.author: leguo
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 4bb647cfd3f012efbffa93a81462c538a24ac850
ms.openlocfilehash: 7349771b7f9a1ad4cd5b239f1d10bd3229d2d0df
ms.lasthandoff: 03/31/2017


---

# <a name="postdated-checks"></a>Cheques pós-datados

[!include[banner](../includes/banner.md)]


Este artigo fornece informações sobre o suporte para cheques pré-datados no Microsoft Dynamics 365 for Operations. Cheques pré-datados são cheques emitidos com a finalidade de fazer e receber pagamentos em uma data futura. Consequentemente, a verificação não pode ser descontada até a data especificada.

O Microsoft Dynamics 365 for Operations oferece suporte ao ciclo completo de gerenciamento de cheques pré-datados em contas a receber e em contas a pagar, como mostra a tabela a seguir.
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
<td>Registrar os detalhes de um cheque pós-datado da saída para um fornecedor. Quando o pagamento é lançado, a responsabilidade do fornecedor é reconhecida, mas a conta bancária ainda não é crédito. Em vez disso, uma conta de compensação é usada com essa finalidade.</td>
</tr>
<tr class="odd">
<td>Registrar e lançar um cheque pré-datado para um cliente</td>
<td>Registre os detalhes de um cheque pré-datado recebido de um cliente. Quando o pagamento é lançado, o recebível do cliente é crédito, mas a conta bancária ainda não é débito. Em vez disso, uma conta de compensação é usada com essa finalidade.</td>
</tr>
<tr class="even">
<td>Registrar e lançar um cheque pós-datado de substituição de um cliente ou um fornecedor</td>
<td>
Se o cheque original para um fornecedor ou um cliente for perdido ou danificado, você poderá emitir um cheque pré-datado de substituição. Quando você registra os detalhes do cheque, fornece uma referência ao cheque original e indica se o novo cheque é uma substituição do original. Também é possível lançar o cheque de substituição.</td>
</tr>
<tr class="odd">
<td>Transferir um cheque pós-datado de um cliente a um fornecedor</td>
<td>Ao receber um cheque pré-datado de um cliente, você pode transferir esse cheque para um fornecedor como um pagamento.</td>
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






