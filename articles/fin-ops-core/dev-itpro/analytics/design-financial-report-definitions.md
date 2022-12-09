---
title: Definições de relatório no designer de relatório financeiro
description: Este artigo fornece informações sobre definições de relatório.
author: aprilolson
ms.date: 11/22/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.custom: 59131
ms.assetid: 966a3f1d-c59c-4a84-acd4-5bb7e65144c8
ms.search.form: FinancialReports
ms.openlocfilehash: 2ffef335c694af56486ccd7738818c4edda49b9e
ms.sourcegitcommit: d27fef61593c6d1e9e26d5c9fad21411bc52fabc
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/23/2022
ms.locfileid: "9802523"
---
# <a name="report-definitions-in-financial-report-designer"></a>Definições de relatório no designer de relatório financeiro

[!include [banner](../includes/banner.md)]

Este artigo fornece informações sobre definições de relatório. Uma definição de relatórios é um componente de relatório (ou bloco de construção) que usa uma definição de linha, uma definição de coluna e uma definição de árvore de relatórios opcional para criar um relatório. Uma definição de relatório também fornece opções e configurações para personalizar um relatório. 

Uma definição de relatórios é um componente de relatório (ou bloco de construção) que usa uma definição de linha, uma definição de coluna e uma definição de árvore de relatórios opcional para criar um relatório. Uma definição de relatório também fornece opções e configurações que você pode usar para personalizar um relatório. Depois de estabelecer as definições de linha e de coluna, você deverá combiná-las em uma definição de relatório. Nesse ponto, você também pode especificar outros aspectos das definições, como o nível de detalhe e a data do relatório. Você pode salvar e gerar um relatório. O relatório financeiro fornece os seguintes níveis de detalhe:

- Financeiro
- Financeiro e Contas
- Financeiro, Contas e Transações

Entretanto, dependendo de como os dados são armazenados no sistema de ERP do Microsoft Dynamics, os detalhes da transação podem não estar disponíveis nos relatórios.

## <a name="create-a-report-definition"></a>Criar uma definição de relatório
1. No Report Designer, no menu **Arquivo**, clique em **Novo** e selecione **Definição de relatório**.
2. Especifique as informações apropriadas nas guias **Relatório**, **Saída e distribuição**, **Cabeçalhos e rodapés** e **Configurações**.

## <a name="contents-of-a-report-definition"></a>Conteúdos para uma definição de relatório
A tabela a seguir descreve as guias em uma definição de relatório e como as informações são usadas.

<table>
<thead>
<tr>
<th>Guia</th>
<th>Descrição</th>
</tr>
</thead>
<tbody>
<tr>
<td>Relatório</td>
<td>Criar, configurar ou alterar um relatório existente.</td>
</tr>
<tr>
<td>Saída e distribuição</td>
<td>Alterar o tipo de saída e o destino do relatório.</td>
</tr>
<tr>
<td>Cabeçalhos e rodapés</td>
<td>Definir e formatar os cabeçalhos e rodapés do relatório. Por exemplo, você pode adicionar texto ou imagens ao cabeçalho ou ao rodapé. O relatório financeiro dá suporte a arquivos .bmp, .jpg e .png para imagens. Você também pode adicionar códigos de autotexto para inserir outras informações, como o nome da empresa, o nome do relatório ou o número de página.</td>
</tr>
<tr>
<td>Configurações</td>
<td>Especificar configurações da definição de relatório, como as seguintes configurações:
<ul>
<li>Formatação e valores de arredondamento</li>
<li>Relatórios de detalhe do formato</li>
<li>Formatar hierarquias organizacionais</li>
<li>Gerar um relatório de exceção</li>
<li>Especificar conversão de moeda</li>
<li>Gerar um subtotal e filtrar detalhes da conta</li>
</ul>
</td>
</tr>
</tbody>
</table>

## <a name="additional-resources"></a>Recursos adicionais

[Relatórios financeiros](financial-reporting-intro.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
