---
title: Auditar regras da política
description: Você pode usar as políticas para avaliar relatórios de despesas, faturas de fornecedor e ordens de compra para garantir que eles estejam em conformidade com as regras de política criadas. Todas as regras associadas a uma política de auditoria são executadas em modo de lotes de acordo com uma agenda especificada.  Cada regra de política é uma instância de um tipo de regra de política. Para cada tipo de regra de política, somente uma regra de política pode ficar ativa de cada vez.
author: ryansandness
manager: AnnBe
ms.date: 08/01/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AuditPolicyAdditionalOption, AuditPolicyRule
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 12991
ms.assetid: 8d787017-71dc-418f-b8c2-4ea9763d9978
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: de6406029aa88424863dd9a47505f5b3ad27f237
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4440310"
---
# <a name="audit-policy-rules"></a>Auditar regras da política

[!include [banner](../includes/banner.md)]

Você pode usar as políticas para avaliar relatórios de despesas, faturas de fornecedor e ordens de compra para garantir que eles estejam em conformidade com as regras de política criadas. Todas as regras associadas a uma política de auditoria são executadas em modo de lotes de acordo com uma agenda especificada.  Cada regra de política é uma instância de um tipo de regra de política. Para cada tipo de regra de política, somente uma regra de política pode ficar ativa de cada vez. 

<a name="queries-and-query-types"></a>Consultas e tipos de consulta
-----------------------

Quando você cria uma regra de política de auditoria, seleciona primeiro um tipo de regra de política. O tipo de regra de política especifica o aplicativo AOT (Árvore de objetos de aplicativo) para usar como ponto de partida para criar a regra de política. Também especifica o tipo de consulta a ser usado para a regra de política. A consulta determina o documento de origem que a regra de política avalia. Também especifica os campos no documento de origem que identificam a entidade legal e data a ser usada quando os documentos forem selecionados para auditoria. O tipo de consulta controla os campos padrão na página de consulta e na página Auditar regra de política. A tabela a seguir mostra os tipos de consulta disponíveis para as regras de política de auditoria.

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipo de consulta</th>
<th>Finalidade</th>
<th>Mais informações</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Condicional</td>
<td>Avaliar atributos do documento de origem com valores especificados.</td>
<td></td>
</tr>
<tr class="even">
<td>Agregado</td>
<td>Avaliar vários documentos de origem ou linhas do documento de origem para uma regra de política agregando valores numéricos.</td>
<td></td>
</tr>
<tr class="odd">
<td>Amostragem</td>
<td>Selecionar aleatoriamente uma porcentagem específica de documentos de origem para avaliar as violações de política.</td>
<td>Quando você selecionar essa opção, use a página Auditar regra de política para especificar a porcentagem de documentos a serem aleatoriamente selecionados para auditoria.</td>
</tr>
<tr class="even">
<td>Duplicata</td>
<td>Avaliar documentos de origem para determinar se eles contêm entradas duplicadas nos campos especificados.</td>
<td>Quando você selecionar essa opção, use o a página Auditar regra da política para especificar o número de dias a serem adicionados ao início do intervalo de datas da seleção de documento quando os documentos são avaliados para entradas duplicadas.</td>
</tr>
<tr class="odd">
<td>Pesquisa de lista</td>
<td>Avaliar documentos de origem para entidades específicas.</td>
<td>O documento raiz de consulta define o documento que está sendo auditado. A consulta deve ser uma consulta na lista que contenha uma referência à tabela dirpartytable. Esta opção só pode ser usada com as seguintes consultas da AOT:
<ul>
<li><span class="ui">AuditPolicyExpenseList</span> (Funcionários monitorados por relatório de despesas)</li>
<li><span class="ui">AuditPolicyPurchList</span> (Fornecedores monitorados por ordem de compra)</li>
<li><span class="ui">AuditPolicyVendInvoiceList</span> (Fornecedores monitorados por fatura de fornecedor)</li>
</ul>
Quando você selecionar essa opção, especifique as entidades monitoradas na página Auditar regra de política.</td>
</tr>
<tr class="even">
<td>Pesquisa por palavra-chave</td>
<td>Avaliar documentos de origem para determinar se eles contêm determinadas palavras.</td>
<td>Quando você selecionar essa opção, insira as palavras para procurar na página Auditar regra de política. A página Auditar regra de política também inclui opções que permitem a especificação de tabelas e campos para avaliar as palavras inseridas.</td>
</tr>
</tbody>
</table>

## <a name="common-parameters"></a>Parâmetros comuns
Todas as regras de política para uma política de auditoria específica compartilham os mesmos parâmetros de lote e o mesmo intervalo de datas da seleção de documento. Esses parâmetros são especificados para a política na página Opções adicionais.



<a name="additional-resources"></a>Recursos adicionais
--------

[Auditar violações de política e casos](audit-policy-violations-cases.md)
[Definir políticas de auditoria para documentos de origem](tasks/define-audit-policies-source-documents.md)


