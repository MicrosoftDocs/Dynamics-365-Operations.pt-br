---
title: "Contrapartidas padrão para diários de fatura de fornecedor e diários de aprovação de fatura"
description: 
author: ShivamPandey-msft
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 62093
ms.assetid: 553933ca-928d-4031-bb8c-f9cff458320b
ms.search.region: global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: c2b62eafc71b5d1ad4eaaf252efd1dcbb97b86f3
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---

# <a name="default-offset-accounts-for-vendor-invoice-journals-and-invoice-approval-journals"></a>Contrapartidas padrão para diários de fatura de fornecedor e diários de aprovação de fatura

[!include[banner](../includes/banner.md)]




As contrapartidas padrão são usadas nas seguintes páginas de diário de fatura de fornecedor:

-   Diário de faturas
-   Diário de aprovações de fatura

Use a tabela a seguir para ajudar a decidir onde você deve atribuir contas padrão para diários de fatura.

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th>Configure contas padrão aqui</th>
<th>Onde as contas padrão são fornecidas</th>
<th>Como esta opção afeta o processamento</th>
<th>Quando você deve usar esta opção</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>Grupo de fornecedores</strong> – configure contrapartidas padrão para grupos de fornecedores na página <strong>Configuração de conta padrão</strong>, que você pode abrir da página <strong>Grupos de fornecedores</strong>.</td>
<td><ul>
<li>Conta de fornecedor</li>
<li>Entradas de diário para contas de fornecedor no grupo de fornecedores, caso as contas padrão não sejam especificadas para contas de fornecedor</li>
</ul></td>
<td>As contrapartidas padrão para grupos de fornecedores são mostradas como contrapartidas padrão para fornecedores na página <strong>Configuração de conta padrão</strong>. Você pode abrir essa página na página de listagem <strong>Todos os fornecedores</strong>.</td>
<td>Use esta opção se você normalmente pagar pelos mesmos tipos de itens dos mesmos grupos de fornecedores ao longo do tempo.</td>
</tr>
<tr class="even">
<td><strong>Conta de fornecedor</strong> – configure contas padrão para contas de fornecedor na página <strong>Configuração de conta padrão</strong>, que você pode abrir da página <strong>Fornecedores</strong>.</td>
<td>Entradas de diário para a conta de fornecedor</td>
<td>As contrapartidas padrão para contas de fornecedor são mostradas como contrapartidas padrão para entradas de diário para a conta do fornecedor.</td>
<td>Use esta opção se você normalmente pagar pelos mesmos tipos de itens dos mesmos fornecedores ao longo do tempo.</td>
</tr>
<tr class="odd">
<td><strong>Nomes de diário</strong> – configure as contrapartidas padrão para diários na página <strong>Nomes de diário</strong>. Selecione a opção <strong>Contrapartida fixa</strong>. Observe que não será possível especificar contrapartidas padrão em nomes de diário se o tipo de diário dos nomes de diário for <strong>Registro de fatura</strong> ou <strong>Aprovação</strong>.</td>
<td><ul>
<li>Cabeçalho de diário que usa o nome do diário</li>
<li>Entradas de diário em diários que usam o nome do diário</li>
</ul></td>
<td>Se a opção <strong>Contrapartida fixa</strong> na página <strong>Nomes de diário</strong> estiver selecionada, a contrapartida para o nome do diário substituirá a contrapartida padrão para o fornecedor ou para o grupo de fornecedores.</td>
<td>Use essa opção para configurar diários para os custos e despesas específicos cobrados de contas específicas, independentemente do fornecedor ou do grupo de fornecedores do qual o fornecedor faz parte.</td>
</tr>
<tr class="even">
<td><strong>Nomes de diário</strong> – configure as contrapartidas padrão para diários na página <strong>Nomes de diário</strong>. Desmarque a opção <strong>Contrapartida fixa</strong>. Observe que não será possível especificar contrapartidas padrão em nomes de diário se o tipo de diário dos nomes de diário for <strong>Registro de fatura</strong> ou <strong>Aprovação</strong>.</td>
<td><ul>
<li>Cabeçalho do diário</li>
<li>Entradas de diário em diários que usam o nome do diário</li>
</ul></td>
<td>Essas entradas padrão são usadas em páginas de cabeçalho de diário, e a contrapartida na página de cabeçalho de diário é usada como uma entrada padrão nas páginas de comprovante de diário. As contas padrão da página <strong>Nomes de diário </strong>só serão usadas se as contas padrão não tiverem sido configuradas para a conta de fornecedor.</td>
<td>Use esta opção para configurar contas padrão usadas quando uma contrapartida de fornecedor padrão não tiver sido atribuída.</td>
</tr>
<tr class="odd">
<td><strong>Cabeçalho do diário</strong> – configure uma contrapartida padrão para um diário como uma entrada padrão nas páginas de comprovante de diário. Observe que não será possível especificar contrapartidas padrão no cabeçalho do diário se o tipo de diário dos nomes de diário for <strong>Registro de fatura</strong> ou <strong>Aprovação</strong>.</td>
<td>Entradas de diário no diário</td>
<td>A contrapartida padrão para um diário é usada como a entrada padrão nas páginas de comprovante de diário.</td>
<td>Use esta opção para ajudar a acelerar a entrada de dados caso a maioria das entradas de um diário tenha a mesma contrapartida.</td>
</tr>
</tbody>
</table>






