---
title: "Configurar nomes de campo de aplicativo no aplicativo de depósito"
description: "Este tópico descreve como definir e configurar os nomes e prioridades de campo do aplicativo de depósito no Dynamics 365 for Operations."
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
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: 73fcc19b9ee17a691206019efbff29c4967f4e2f
ms.contentlocale: pt-br
ms.lasthandoff: 04/25/2017


---

# <a name="configure-app-field-names-in-warehousing-app"></a>Configurar nomes de campo de aplicativo no aplicativo de depósito

[!include[banner](../includes/banner.md)]


Este tópico descreve como definir e configurar os nomes e prioridades de campo do aplicativo de depósito no Dynamics 365 for Operations. 

**Observação:** este tópico se aplica aos recursos do Gerenciamento de depósito. Ele não se aplica aos recursos do Gerenciamento de estoque. Dynamics 365 for Operations - O Depósito é um aplicativo que você pode usar para realizar tarefas de depósito. Você pode definir e configurar os nomes de campo usados no aplicativo, bem como configurar a prioridade à qual os nomes de campo devem ser atribuídos. Este tópico explica como definir e configurar esses nomes e prioridades de campo do aplicativo de depósito e como eles são usados no Dynamics 365 for Operations - Depósito. Para obter informações detalhadas sobre como configurar a conexão com o Dynamics 365 for Operations - Depósito, consulte o tutorial [Instale e configure o Dynamics 365 for Operations - Depósito](install-configure-warehousing-app.md).

<a name="configure-warehouse-app-field-names"></a>Configurar nomes de campo do aplicativo de depósito
===================================

Ao usar o Dynamics 365 for Operations - Depósito no seu dispositivo, você pode configurar como os metadados devem ser exibidos no seu dispositivo na página **Nomes de campo de aplicativo de depósito**. Em uma nova companhia no Dynamics 365 for Operations, selecione **Criar configuração padrão** para gerar todos os nomes de campo que serão usados nos fluxos de trabalho do dispositivo móvel de depósito e depois atribuir um modo e tipo de saída preferenciais para eles. Após a criação de todos os nomes de campo, você pode selecionar as seguintes opções de saída.

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
<td>Essa opção define se um campo de digitalização ou um campo de saída de entrada manual deve ser mostrado para o nome de campo selecionado. Isso é útil para diferenciar campos, o que dependerá da utilidade dos códigos de barras para o campo. <strong>Observação:</strong> para nomes de campo com modo de saída preferencial definido como <strong>Digitalizando</strong>, você pode inserir informações manualmente se o código de barras for ilegível ou estiver danificado.</td>
</tr>
<tr class="even">
<td>Tipo de Entrada</td>
<td>Essa opção define qual tipo de saída deve ser usado para o nome do campo selecionado. Quatro opções estão disponíveis:
<ul>
<li><strong>Seleção</strong> - Contém uma lista de opções para escolha. Nomes de campo com essa opção não são editáveis.</li>
<li><strong>Data</strong> - Nomes de campo especificados como data mostrarão um formato de data com o rótulo. Com isso, os trabalhadores de depósito podem ver em qual formato inserir a data. Nomes de campo com essa opção não são editáveis.</li>
<li><strong>Alfa</strong> - Se selecionado, o teclado do dispositivo será usado na inserção manual de informações no aplicativo. A experiência de teclado pode ser alterada dependendo de qual dispositivo é usado.</li>
<li><strong>Numérico</strong> - Para nomes de campo que usam apenas saída numérica, você pode selecionar essa opção para exibir um teclado numérico personalizado com o campo de saída em vez do teclado do dispositivo.</li>
</ul></td>
</tr>
</tbody>
</table>

<a name="configure-warehouse-app-field-priority"></a>Configurar a prioridade de campo do aplicativo de depósito
======================================

Na página **Prioridade de campo de aplicativo de depósito**, você pode colocar nomes de campo em grupos de prioridade diferentes. Com isso, é possível decidir quais informações devem ser exibidas na página de tarefa principal quando os trabalhadores de depósito realizam tarefas usando o aplicativo. Se clicar em **Criar configuração padrão**, um conjunto padrão de grupos de prioridades será gerado. É possível criar tantos grupos de prioridade quantos forem necessários, mas apenas três grupos de prioridades serão mostrados na página de tarefas. Ao enviar os metadados ao aplicativo, o Dynamics 365 for Operations atribuirá a cada campo uma prioridade relativa de acordo com seu grupo de prioridades, e o aplicativo exibirá os primeiros três grupos de prioridades contidos nos metadados na página de tarefas. O resto dos metadados transbordantes serão exibidos em uma página de detalhes secundária. A tabela a seguir mostra um exemplo de cinco grupos de prioridades.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Grupo de prioridades</th>
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

Por exemplo, quando um trabalhador de depósito está realizando uma tarefa em um dispositivo móvel, se os metadados que serão exibidos no aplicativo consistirem nos seguintes campos:

-   Item
-   Quantidade
-   Unidade de medida
-   Descrição do item
-   Tamanho e local

Com base na prioridade de campo do aplicativo de depósito configurada na tabela acima, as 3 linhas de informação a seguir serão exibidas na página de tarefas:

-   Linha 1: Item, quantidade, unidade de medida
-   Linha 2: descrição do item
-   Linha 3: tamanho

Os metadados restantes, como Local, não serão exibidos na página de tarefas, mas o serão em uma página de detalhes. Para saber mais e ver exemplos da interface do usuário, consulte a postagem do blog [Anúncio do Dynamics 365 for Operations - Depósito](https://blogs.msdn.microsoft.com/dynamicsaxscm/2017/01/20/announcing-dynamics-365-for-operations-warehousing/).

<a name="see-also"></a>Consulte também
--------

[Instale e configure o Microsoft Dynamics 365 for Operations – Depósito](install-configure-warehousing-app.md)




