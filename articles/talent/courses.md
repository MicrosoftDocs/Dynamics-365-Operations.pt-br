---
title: Configurar cursos de treinamento
description: Os administradores e gerentes de recursos humanos podem usar os recursos dos cursos para manter informações sobre o treinamento que é oferecido aos funcionários.
author: andreabichsel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: HcmCourseType, HcmCourseTypeGroup, HRMCourseTable
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Talent
ms.custom: 7532
ms.assetid: a6950c29-8b3e-45b2-9084-ddfb1317ffaa
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Talent July 2017 update
ms.openlocfilehash: 83f88d17c744bb53dad975b77d169a09375d20d1
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2019
ms.locfileid: "1517291"
---
# <a name="set-up-training-courses"></a>Configurar cursos de treinamento

[!include [banner](includes/banner.md)]

Os administradores e gerentes de recursos humanos podem usar os recursos dos cursos para manter informações sobre o treinamento que é oferecido aos funcionários.

 <a name="set-up-prerequisites"></a>Pré-requisitos de configuração
---------------------

As informações a seguir são necessárias e devem ser configuradas antes de criar cursos.
-   **Tipos de cursos**

As informações a seguir são informações opcionais que você poderá especificar para cursos. Se você sabe que essas informações serão inseridas para cursos, deve configurá-las antes de criar registros do curso.
-   **Grupos de salas de aula**
-   **Grupos de cursos**
-   **Locais do curso**
-   **Salas de aula**
-   **Instrutores**

## <a name="course-types"></a>Tipos de cursos
Você pode usar tipos de curso para categorizar os cursos de acordo com a estrutura ou o conteúdo do curso. Você pode criar tipos de curso na página **Tipos de curso**. Você deverá selecionar um tipo de curso ao criar um registro do curso.

## <a name="course-setup-type"></a>Tipo de configuração de curso
A tabela a seguir lista os três tipos de configuração para cursos. Os tipos de configuração determinam a estrutura do curso.

<table>
<thead>
<tr class="header">
<th>Tipo de configuração</th>
<th>Descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>Padrão</strong></td>
<td>Selecione esse tipo para os cursos que não terão uma agenda diária. Esse será o tipo padrão de configuração quando você criar um novo curso.</td>
</tr>
<tr class="even">
<td><strong>Agenda</strong></td>
<td>Selecione esse tipo para planejar os detalhes de cada dia de um curso que dura vários dias.</td>
</tr>
<tr class="odd">
<td><strong>Agenda + sessão</strong></td>
<td>Selecione esse tipo para os cursos mais complexos. Por exemplo, você pode dividir a agenda do curso em controles e sessões.
<ul>
<li><strong>Controle</strong> – Os controles são áreas de assunto específicas de um curso.</li>
<li><strong>Sessões</strong> – As sessões são divididas em controles e ajudam a identificar processos ou técnicas específicas relevantes ao controle.</li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="course-tasks"></a>Tarefas do curso
Para cada curso, você pode concluir as tarefas a seguir.
- Registrar participantes
- Especificar um prazo final para registro
- Definir os números máximo e mínimo de participantes
- Atribuir um local do curso e uma sala de aula
- Recomendar hotéis aos participantes do curso
- Criar uma descrição do curso, que pode ser anunciada no Autoatendimento para funcionários

  >**Observação:** você pode excluir um curso somente se ninguém estiver registrado nele. 

## <a name="course-statuses"></a>Status do curso
A tabela a seguir lista os possíveis status do curso e as ações que poderão ser concluídas quando o curso tiver um status específico.

<table>
<thead>
<tr class="header">
<th>Status</th>
<th>Ações</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>Criado</strong></td>
<td><ul>
<li>Inserir e modificar informações do curso.</li>
<li>Alterar o status do curso para <strong>Aberto</strong> de modo que os trabalhadores possam se registrar no curso.</li>
</ul></td>
</tr>
<tr class="even">
<td><strong>Abrir</strong></td>
<td><ul>
<li>Registrar participantes no curso.</li>
<li>Remover participantes do curso.</li>
<li>Confirmar participantes no curso.</li>
<li>Alterar o status do curso para <strong>Fechado</strong> ou <strong>Cancelado</strong>.</li>
<li>Planejar questionários para participantes cujo status é <strong>Confirmado</strong>.</li>
</ul></td>
</tr>
<tr class="odd">
<td><strong>Fechado</strong></td>
<td>Você pode reabrir o curso.</td>
</tr>
<tr class="even">
<td><strong>Cancelado</strong></td>
<td>Você pode reabrir o curso.</td>
</tr>
</tbody>
</table>

## <a name="course-participants"></a>Participantes do curso
Os participantes de curso são funcionários, candidatos ou pessoas de contato que estão participando de um curso de treinamento ou de um evento. Você só pode registrar participantes em cursos em aberto. Os números máximo e mínimo de participantes que você pode registrar para um curso é definido na Guia Rápida **Geral**, na página **Cursos**.

<a name="workflow"></a>Fluxo de trabalho
--------

Os funcionários que se registrarem em um curso na página **Autoatendimento para funcionários** podem ter seu registro roteado com o fluxo de trabalho para aprovação.  Um fluxo de trabalho pode ser atribuído a um curso na Guia Rápida **Geral** na página **Cursos**.





