---
title: Suporte do quadro de transferência kanban para os scanners de código de barras
description: O Quadro de transferência do kanban oferece suporte à entrada de scanner de um scanner de código de barras de widget para Selecionar, Iniciar, Concluir e Esvaziar um trabalho kanban.
author: ChristianRytt
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanBoardTransferJob
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 19391
ms.assetid: a426f645-d59b-4c98-8d78-eba8d64a562e
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1bd6f1bdd847f74cee7d3594d19b72454063c0cb
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3207177"
---
# <a name="kanban-transfer-board-support-for-barcode-scanners"></a>Suporte do quadro de transferência kanban para os scanners de código de barras

[!include [banner](../includes/banner.md)]

O Quadro de transferência do kanban oferece suporte à entrada de scanner de um scanner de código de barras de widget para Selecionar, Iniciar, Concluir e Esvaziar um trabalho kanban.

<a name="registration-modes"></a>Modos de registro
------------------

Na Guia Rápida **Registro do scanner** você pode selecionar o modo do registro, que controla a ação quando você pesquisa um número de cartão kanban ou digita manualmente o número no campo Número do cartão kanban.

| Definir o modo de registro | Descrição                                                                                     |
|-----------------------|-------------------------------------------------------------------------------------------------|
| Inicial                 | Registra um trabalho de transferência kanban como em andamento.                                                 |
| Concluída              | Registra um trabalho de transferência kanban como concluído.                                                   |
| Vazio                 | Registra a unidade de manuseio de material referenciada por um cartão kanban como vazia.              |
| Selecionar                | Registra um número de cartão kanban e seleciona automaticamente o trabalho referenciado na lista Kanban. |

 
Seleção do Modo de registro
------------------------

Quando você usa um leitor de código de barras para selecionar um trabalho, o modo de exibição do quadro kanban é alterado.Desse modo, as seguintes condições se aplicam:

-   Somente o trabalho kanban verificado é exibido.
-   Os detalhes do trabalho selecionado são exibidos na Guia Rápida **Detalhes**.
-   A Guia Rápida **Mensagens** exibe mensagens somente do trabalho selecionado.
-   Você pode alterar o status do trabalho usando as funções disponíveis no Painel de Ações. O quadro de transferência kanban continuará a exibir somente um único trabalho durante esse tempo.
-   Você pode atualizar as informações da lista de trabalhos manualmente, clicando em **Atualizar** (Shift+F5) no Painel de Ação. Depois de atualizar as informações, os resultados completos sobre o filtro de trabalho serão exibidos mais uma vez.

## <a name="job-status-and-possible-actions"></a>Status do trabalho e ações possíveis
O status do trabalho selecionado e o status de todos os trabalhos vinculados para kanbans de eventos, determinam se você pode processar o trabalho ainda mais. A tabela a seguir exibe informações sobre esses status e tarefas:
-   Os status disponíveis para trabalhos, ou para as unidades de manuseio de material referenciadas pelos trabalhos.
-   Cada tarefa que você pode executar para o trabalho.

<table>
<colgroup>
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipo de trabalho</th>
<th>Status do trabalho ou status da unidade de manuseio de material</th>
<th>Atualizar lista de separação</th>
<th>Inicial</th>
<th>Atualizar registro</th>
<th>Concluída</th>
<th>Vazio</th>
<th>Criar kanbans de evento</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Transferência</td>
<td><ul>
<li>Não planejados</li>
<li>Nenhum trabalho vinculado ou os trabalhos vinculados estão Concluídos</li>
</ul></td>
<td>Sim</td>
<td>Sim</td>
<td>Sim</td>
<td>Sim</td>
<td>Não</td>
<td>Sim</td>
</tr>
<tr class="even">
<td>Transferência</td>
<td><ul>
<li>Não planejados</li>
<li>O trabalho vinculado não está Concluído</li>
</ul></td>
<td>Sim</td>
<td>Não</td>
<td>Sim</td>
<td>Não</td>
<td>Não</td>
<td>Não</td>
</tr>
<tr class="odd">
<td>Transferência</td>
<td>Em andamento</td>
<td>Sim</td>
<td>Não</td>
<td>Sim</td>
<td>Sim</td>
<td>Não</td>
<td>Não</td>
</tr>
<tr class="even">
<td>Transferência</td>
<td>Concluídas</td>
<td>Não</td>
<td>Não</td>
<td>Não</td>
<td>Não</td>
<td>Sim</td>
<td>Não</td>
</tr>
<tr class="odd">
<td>Transferência ou processo</td>
<td>Vazio</td>
<td>Não</td>
<td>Não</td>
<td>Não</td>
<td>Não</td>
<td>Não</td>
<td>Não</td>
</tr>
<tr class="even">
<td>Transferência ou processo</td>
<td>Um cartão kanban não foi encontrado</td>
<td>Não</td>
<td>Não</td>
<td>Não</td>
<td>Não</td>
<td>Não</td>
<td>Não</td>
</tr>
<tr class="odd">
<td>Transferência ou processo</td>
<td>Um cartão kanban foi encontrado, mas não foi atribuído a um kanban</td>
<td>Não</td>
<td>Não</td>
<td>Não</td>
<td>Não</td>
<td>Não</td>
<td>Não</td>
</tr>
<tr class="even">
<td>Processo</td>
<td><ul>
<li>Não planejados</li>
<li>Preparados</li>
<li>Em andamento</li>
</ul></td>
<td>Não</td>
<td>Não</td>
<td>Não</td>
<td>Não</td>
<td>Não</td>
<td>Não</td>
</tr>
<tr class="odd">
<td>Processo</td>
<td>Concluídas</td>
<td>Não</td>
<td>Não</td>
<td>Não</td>
<td>Não</td>
<td>Não</td>
<td>Não</td>
</tr>
</tbody>
</table>





