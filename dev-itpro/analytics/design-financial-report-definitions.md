---
title: "Definições de relatório no designer de relatório financeiro"
description: "Este artigo fornece informações sobre definições de relatório. Uma definição de relatórios é um componente de relatório (ou bloco de construção) que usa uma definição de linha, uma definição de coluna e uma definição de árvore de relatórios opcional para criar um relatório. Uma definição de relatório também fornece opções e configurações para personalizar um relatório."
author: RobinARH
manager: AnnBe
ms.date: 2016-03-07 18 - 58 - 18
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: RobinARH
ms.search.scope: Management Reporter, Core
ms.custom: 59131
ms.assetid: 966a3f1d-c59c-4a84-acd4-5bb7e65144c8
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 
ms.dyn365.ops.version: 
translationtype: Human Translation
ms.sourcegitcommit: 4d6cf88788dcc5e982e509137aa444a020137a5e
ms.openlocfilehash: 81ac503410e51672c2f97a76d37d4c567832912f
ms.lasthandoff: 03/29/2017


---

# <a name="report-definitions-in-financial-report-designer"></a>Definições de relatório no designer de relatório financeiro

Este artigo fornece informações sobre definições de relatório. Uma definição de relatórios é um componente de relatório (ou bloco de construção) que usa uma definição de linha, uma definição de coluna e uma definição de árvore de relatórios opcional para criar um relatório. Uma definição de relatório também fornece opções e configurações para personalizar um relatório. 

Uma definição de relatórios é um componente de relatório (ou bloco de construção) que usa uma definição de linha, uma definição de coluna e uma definição de árvore de relatórios opcional para criar um relatório. Uma definição de relatório também fornece opções e configurações que você pode usar para personalizar um relatório. Após especificar definições de linha e de coluna, você deve combiná-las em uma definição de relatório. Nesse ponto, você também pode especificar outros aspectos das definições, como o nível de detalhe e a data do relatório. Você pode salvar e gerar um relatório. O relatório financeiro fornece os seguintes níveis de detalhe:

-   Financeiro
-   Financeiro e Contas
-   Financeiro, Contas e Transações

Entretanto, dependendo de como os dados são armazenados no sistema ERP do Microsoft Dynamics, os detalhes da transação podem não estar disponíveis nos relatórios.

## <a name="create-a-report-definition"></a>Criar uma definição de relatório
1.  No Designer de Relatórios, no menu **Arquivo**, clique em **Novo** e selecione **Definição de Relatório**.
2.  Especifique as informações apropriadas nas guias **Relatório**, **Saída e Distribuição**, **Cabeçalhos e Rodapés** e **Configurações**.

## <a name="contents-of-a-report-definition"></a>Conteúdo de uma definição de relatório
A tabela a seguir descreve as guias em uma definição de relatório e como as informações são usadas.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Guia</th>
<th>Descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Relatório</td>
<td>Criar um relatório, configurar um relatório ou modificar um relatório existente.</td>
</tr>
<tr class="even">
<td>Saída e Distribuição</td>
<td>Alterar o tipo de saída e o destino do relatório.</td>
</tr>
<tr class="odd">
<td>Cabeçalhos e Rodapés</td>
<td>Definir e formatar os cabeçalhos e os rodapés do relatório. Por exemplo, você pode adicionar texto ou imagens ao cabeçalho ou ao rodapé. O relatório financeiro dá suporte a arquivos .bmp, .jpg e .png para imagens. Você também pode adicionar códigos de autotexto para inserir outras informações, como o nome da empresa, o nome do relatório ou o número de página.</td>
</tr>
<tr class="even">
<td>Configurações</td>
<td>Especifique configurações da definição de relatório, como estas:
<ul>
<li>Formatação e valores de arredondamento</li>
<li>Formatar relatórios de detalhes</li>
<li>Formatar árvores de relatórios</li>
<li>Gerar um relatório de exceção</li>
<li>Especificar a conversão de moeda</li>
<li>Detalhes de subtotal e conta de filtro</li>
</ul></td>
</tr>
</tbody>
</table>



<a name="see-also"></a>Consulte também
--------

[Relatórios financeiros para o Microsoft Dynamics 365 para operações (financial-reporting-intro.md])


