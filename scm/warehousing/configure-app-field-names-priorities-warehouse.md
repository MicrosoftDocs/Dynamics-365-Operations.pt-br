---
title: Configurar nomes de campo descritivo de armazenar descritivo no
description: "Este tópico descreve como configurar e definir nomes e prioridades descritivo do campo de depósito em dynamics 365 para as operações."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: WHSMobileAppField, WHSMobileAppFieldPriority
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 269434
ms.assetid: 6cf3d7da-29bb-4d3d-aaf5-544ca9cc2980
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: mafoge
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: f77012e7b64b7f153103e9bbe91e8ded202b509a
ms.openlocfilehash: ce8f6d6f7090995bc44db1ba0103a7d6c0416620
ms.lasthandoff: 03/31/2017


---

# <a name="configure-app-field-names-in-warehousing-app"></a>Configurar nomes de campo descritivo de armazenar descritivo no

Este tópico descreve como configurar e definir nomes e prioridades descritivo do campo de depósito em dynamics 365 para as operações. 

** Observação: ** Este tópico se aplica aos recursos de gerenciamento de depósito. Não se aplica a recursos em gerenciamento de estoque. Dynamics 365 para operações - id é um aplicativo de usar para executar tarefas de depósito. Você pode configurar e definir nomes de campo usado em descritivo, bem como definir a prioridade em que nomes de campo devem ser atribuídos. Este tópico explica como configurar e definir esses nomes e prioridades descritivo de campo do depósito, e como são usadas em dynamics 365 para operações do armazenamento. Para informações sobre como configurar a conexão ao dynamics 365 para as operações do armazenamento, consulte o tutorial [a instalação e a configuração dinâmica 365 para operações - para armazenar] install-configure-warehousing-app.md ().

<a name="configure-warehouse-app-field-names"></a>Configurar nomes de campo de descritivo de depósito
===================================

Quando você usa o dynamics 365 para operações - para armazenar no dispositivo móvel, você pode configurar como os metadados serão exibidos no dispositivo em ** nomes de campo de depósito ** descritivo de página. Uma nova empresa em dynamics 365 para operações, selecione ** criar de instalação ** padrão para gerar os nomes de campos que serão usados os fluxos de trabalho do dispositivo móvel depósito, e atribuir um modo de entrada preferenciais e um tipo de entrada. Após você gerou todos os nomes de campo, pode selecionar as seguintes opções de entrada.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Opção</th>
<th>descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Modo de entrada preferencial</td>
<td>Essa opção define se um campo de exploração ou um campo de entrada manual de entrada devem ser mostrados para o nome do campo selecionado. Isso é útil distinguir campos caso os códigos de barras são usados para o campo. <strong>Observação:</strong> Para nomes de campo ao modo de entrada preferido definido como <strong>Digitalizando</strong>, insira as informações manualmente se o código de barras for danificado ou ilegível.</td>
</tr>
<tr class="even">
<td>Tipo de Entrada</td>
<td>Essa opção define o tipo de entrada deve ser usado para o nome do campo selecionado. Quatro opções estão disponíveis:
<ul>
<li><strong>Seleção</strong> - contém uma lista de opções de. Nomes de campo para essa opção não é editável.</li>
<li><strong>Data</strong>nomes de campo do - como data especificados mostrarão um formato de data rótulo com o. Isso ajuda trabalhadores de depósito para ver em que linha para inserir a data. Nomes de campo para essa opção não é editável.</li>
<li><strong>Alpha</strong> - se selecionado, o teclado de dispositivo será usado ao inserir as informações manualmente em descritivo. A experiência do teclado pode ser alterada conforme o dispositivo for usado.</li>
<li><strong>Numérico</strong> - para nomes de campo que usam apenas a entrada numérica, selecione esta opção exibe um teclado numérico numérico personalizado com campo de entrada do teclado em vez do dispositivo.</li>
</ul></td>
</tr>
</tbody>
</table>

<a name="configure-warehouse-app-field-priority"></a>Configurar a prioridade do descritivo de depósito
======================================

** O a prioridade do descritivo ** na página, é possível inserir nomes de campos de prioridade em grupos diferentes. Isso possibilita decidir quais informações devem ser exibidas no task page principal quando os funcionários do depósito realizam tarefas usando o descritivo. Se clicar ** criar de instalação padrão **, um conjunto padrão de grupos de prioridade será gerado. É possível criar tantos necessário como grupos de prioridade, mas apenas três grupos de prioridade serão mostrados no task page. Quando o dynamics 365 para operações envia metadados para descritivo, atribuídos a cada campo prioridade relativo dependendo do grupo de prioridade, o descritivo exibirá os primeiros três grupos de prioridade contidos nos metadados no task page. O resto de metadados estourando será exibido em páginas secundário detalhes. A tabela mostra um exemplo de cinco grupos de prioridade.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Grupo de prioridade</th>
<th>Campos atribuídos</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td> Prioridade 10</td>
<td><ul>
<li>Item</li>
<li>Quantidade</li>
<li>Unidade de medida</li>
</ul></td>
</tr>
<tr class="even">
<td> Prioridade 20</td>
<td><ul>
<li>Posição de cluster</li>
<li>Cluster</li>
</ul></td>
</tr>
<tr class="odd">
<td> Prioridade 30</td>
<td><ul>
<li>Descrição do item</li>
</ul></td>
</tr>
<tr class="even">
<td> Prioridade 40</td>
<td><ul>
<li>Configuração</li>
<li>Cor</li>
<li>Tamanho</li>
<li>Estilo</li>
</ul></td>
</tr>
<tr class="odd">
<td> Prioridade 50</td>
<td><ul>
<li>Local</li>
<li>Placa de licença</li>
</ul></td>
</tr>
</tbody>
</table>

Por exemplo, quando um trabalhador depósito executar uma tarefa em um dispositivo móvel, se os metadados que serão exibidos em descritivo consistem nestes campos:

-   Item
-   Quantidade
-   Unidade de medida
-   Descrição do item
-   Tamanho e o local

Com base na configuração de prioridade do descritivo de depósito na tabela anterior, as seguintes linhas 3 de informações serão exibidas no task page:

-   Linha 1: Item, quantidade, unidade de medida
-   Linha 2: Descrição do item
-   Linha 3: Tamanho

Os metadados restantes, por exemplo, local, não serão exibidos no task page, mas serão exibidos em páginas detalhes. Para saber mais e veja exemplos de interface de usuário, consulte a postagem de blog [que anuncia o dynamics 365 para operações - para armazenar] (https://blogs.msdn.microsoft.com/dynamicsaxscm/2017/01/20/announcing-dynamics-365-for-operations-warehousing/).

<a name="see-also"></a>Consulte também
--------

[Instalar e configurar o Microsoft Dynamics 365 para operações – para armazenar] (install-configure-warehousing-app.md)


