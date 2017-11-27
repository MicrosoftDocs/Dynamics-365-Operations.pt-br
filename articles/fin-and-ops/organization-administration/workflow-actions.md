---
title: "Ações de fluxo de trabalho"
description: "Este artigo explica as ações que cada participante em um processo de aprovação de fluxo de trabalho pode executar."
author: sericks007
manager: AnnBe
ms.date: 08/23/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 56411
ms.assetid: 65fb711c-6474-42d1-81ed-ca657c29bf1f
ms.search.region: Global
ms.author: tjvass
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 2a4717accfa7e5879ee757820c39f000fa7d3e95
ms.contentlocale: pt-br
ms.lasthandoff: 11/03/2017

---

# <a name="workflow-actions"></a>Ações de fluxo de trabalho

[!include[banner](../includes/banner.md)]


Este artigo explica as ações que cada participante em um processo de aprovação de fluxo de trabalho pode executar.

Um fluxo de trabalho pode envolver vários grupos de pessoas: o originador, os destinatários de tarefa, os tomadores de decisão, e os aprovadores. Por exemplo, no fluxo de trabalho de relatório de despesas a seguir, Samuel é o originador; os membros da fila são os destinatários de tarefa; Mateus é um tomador de decisão e Fábio, Manuela e Ana são os aprovadores.   

[![Workflow\_WithManualDecision](./media/workflow_withmanualdecision.gif)](./media/workflow_withmanualdecision.gif) 

As seções a seguir explicam as ações de fluxo de trabalho que cada grupo pode executar.

## <a name="actions-that-an-originator-can-perform"></a>Ações que um originador pode executar
O originador inicia uma instância de fluxo de trabalho enviando um documento para processamento. Por exemplo, para que Samuel possa enviar o relatório de despesas, ele deverá clicar no botão **Enviar** na página**Relatório de despesas** para enviar o relatório de despesas.

## <a name="actions-that-a-task-assignee-can-perform"></a>Ações que um destinatário de tarefa pode executar
Uma tarefa pode ser atribuída a várias pessoas ou a uma fila de itens de trabalho que é monitorada por várias pessoas. Entretanto, somente uma pessoa pode concluí-la. Por exemplo, suponha que Samuel tenha enviado um relatório de despesas e encaminhado seus recibos ao departamento de relatórios de despesas da organização para revisão. 

Os membros do departamento de relatórios de despesas da Adventure Works monitoram a fila. Suponha que Julieta, membro desse departamento, tenha aceitado a tarefa de revisar o relatório de despesas e os recibos de Samuel. Agora, ela pode executar uma das seguintes ações: concluir, rejeitar, delegar, solicitar alteração, reatribuir ou liberar. 

**Observação:**as ações disponíveis irão variar dependendo de como o desenvolvedor do software tiver criado a tarefa.

### <a name="complete"></a>Concluir

Quando um usuário conclui uma tarefa, o documento que foi enviado para processamento é atribuído ao usuário seguinte no fluxo de trabalho, se houver um usuário seguinte. Se não for necessário nenhum processamento adicional, o processo do fluxo de trabalho termina. 

Por exemplo, Julieta, membro do departamento de relatórios de despesas da Adventure Works, aceitou a tarefa de revisar o relatório de despesas e os recibos de Samuel. Depois que Julieta concluir sua revisão, o documento será atribuído a Mateus.

### <a name="reject"></a>Rejeitar

Quando um usuário rejeita um documento, o processo de fluxo de trabalho é encerrado. 

Por exemplo, Julieta, membro do departamento de relatórios de despesas da Adventure Works, aceitou a tarefa de revisar o relatório de despesas e os recibos de Samuel. Se Julieta rejeitar o relatório de despesas, o processo de fluxo de trabalho será encerrado. 

Samuel poderá reenviar o relatório de despesas. Ele pode fazer alterações primeiro ou pode reenviar a versão original. Se Samuel reenviar o relatório de despesas, o processo de fluxo de trabalho começará na tarefa de revisão manual.

### <a name="delegate"></a>Delegar

Quando um usuário delega uma tarefa, ela é atribuída a outro usuário. 

Por exemplo, Julieta, membro do departamento de relatórios de despesas da Adventure Works, aceitou a tarefa de revisar o relatório de despesas e os recibos de Samuel. Julieta delega essa tarefa a Valério, seu assistente. 

Tim executa uma ação em nome de Julie. Isso significa que quando Valério concluir a revisão, o relatório de despesas será atribuído a Mateus, como se Julieta tivesse concluído a tarefa.

### <a name="request-change"></a>Solicitar alteração

Quando um usuário solicita uma alteração em um documento que foi enviado, ele é enviado de volta ao originador. 

Por exemplo, Julieta, membro do departamento de relatórios de despesas da Adventure Works, aceitou a tarefa de revisar o relatório de despesas e os recibos de Samuel. Julieta observa alguns erros no relatório de despesas e solicita alterações. O relatório é enviado de volta para Samuel. 

Samuel poderá reenviar o relatório de despesas. Ele pode fazer as alterações solicitadas primeiro ou pode reenviar a versão original. Se ele reenviar o relatório de despesas, um membro da fila de itens de trabalho deverá revisar o relatório de despesas e os recibos novamente.

### <a name="reassign"></a>Reatribuir

Os membros da uma fila de itens de trabalho podem reatribuir os documentos que estão na fila para outra fila. 

Por exemplo, Julieta, membro do departamento de relatórios de despesas da Adventure Works, está monitorando a fila. Para ajudar a equilibrar a carga de trabalho, ela pode reatribuir o relatório de despesas e os recibos incluídos nele, a outra fila.

### <a name="release"></a>Liberar

Ocasionalmente, um membro de uma fila de itens de trabalho pode aceitar uma tarefa, mas depois decidir que não pode concluir a tarefa. Nesse caso, a pessoa que aceitou a tarefa pode liberar o documento de volta à lista de itens de trabalho. 

Por exemplo, Julieta, membro do departamento de relatórios de despesas da Adventure Works, aceitou a tarefa de revisar o relatório de despesas e os recibos de Samuel. Se Julieta decidir que não pode concluir a tarefa, ela poderá liberar o documento. O relatório de despesas é devolvido à fila de modo que outros membros do departamento de relatórios de despesas da Adventure Works possam concluir a tarefa.

## <a name="actions-that-a-decision-maker-can-perform"></a>Ações que um tomador de decisões pode executar
Geralmente, um documento é atribuído a um tomador de decisões porque há uma pergunta deve ser respondida pelo tomador de decisões. A resposta para a pergunta normalmente é **Sim** ou **Não**, ou **Verdadeiro** ou **Falso**. Se o tomador de decisões não selecionar uma dessas opções, ele poderá delegar a decisão.

### <a name="choice-1-or-choice-2"></a>\[Escolha 1\] ou \[Escolha 2\]

Um tomador de decisões deve responder a uma pergunta que esteja relacionada ao documento. A resposta para a pergunta normalmente é **Sim** ou **Não**, ou **Verdadeiro** ou **Falso**. A resposta que o tomador de decisões seleciona determina a ramificação do fluxo de trabalho usada para processar o documento. 

Por exemplo, suponha que o relatório de despesas de Samuel seja atribuído a Mateus. Mateus deve decidir se as informações no documento precisam de uma ligação ao gerente de Samuel. Se Mateus decidir que uma ligação é necessária, o relatório de despesas será atribuído a Yara, que deve ligar para o gerente do Samuel. Se Mateus decidir que uma ligação não é necessária, o relatório de despesas será atribuído a Fábio para aprovação.

### <a name="delegate"></a>Delegar

Quando um tomador de decisões delega uma decisão, o documento é atribuído a outro usuário que deve fazer a decisão. 

Por exemplo, suponha que o relatório de despesas de Samuel seja atribuído a Mateus. Mateus delega a decisão a Marina, sua assistente. 

Em seguida, Maria age em nome de João. Se Marina decidir que uma ligação ao gerente de Samuel é necessária, o relatório de despesas será atribuído a Yara, que deve ligar para o gerente do Samuel. Se Marina decidir que uma chamada não é necessária, o relatório de despesas é atribuído a Fábio para aprovação.

## <a name="actions-that-an-approver-can-perform"></a>Ações que um aprovador pode executar
Quando um documento é atribuído a um aprovador, ele pode executar uma das seguintes ações: aprovar, rejeitar, delegar ou solicitar alteração.

### <a name="approve"></a>Aprovar

Quando um aprovador aprova um documento, o documento é atribuído ao usuário seguinte no fluxo de trabalho, se houver um usuário seguinte. Se não for necessário nenhum processamento adicional, o processo do fluxo de trabalho termina. 

Por exemplo, suponha que Samuel tenha enviado um relatório de despesas de R$ 6.000,00, que é atribuído a Fábio. Quando Fábio aprova o documento, ele é atribuído a Manuela para aprovação. Depois que Manuela aprovar o relatório de despesas, o processo de fluxo de trabalho será encerrado.

### <a name="reject"></a>Rejeitar

Quando um aprovador rejeita um documento, o processo de fluxo de trabalho termina. 

Por exemplo, suponha que Samuel tenha enviado um relatório de despesas de R$ 12,000, que é atribuído a Manuela. Se Suzana rejeitar o relatório, o processo de fluxo de trabalho é encerrado. 

Samuel poderá reenviar o relatório de despesas. Ele pode fazer as alterações primeiro ou pode reenviar a versão original do relatório de despesas. Se Samuel reenviar o relatório de despesas, o processo de fluxo de trabalho começa no processo de aprovação.

### <a name="delegate"></a>Delegar

Quando um aprovador delega um documento, o documento é atribuído a outro usuário para aprovação. 

Por exemplo, suponha que Samuel tenha enviado um relatório de despesas de R$ 12,000, que é atribuído a Fábio. Francisco delega o relatório a Ana. 

Em seguida, Ana age em nome de Francisco. Portanto, quando Ana aprovar o documento, ele será atribuído a Manuela para aprovação, como se Fábio o tivesse aprovado. Depois que Manuela aprovar o documento, ele será enviado a Ana para aprovação.

### <a name="request-change"></a>Solicitar Alteração

Quando um aprovador solicita uma alteração em um documento, o documento é enviado de volta para o originador. 

Por exemplo, suponha que Samuel tenha enviado um relatório de despesas de R$ 12,000, que é atribuído a Manuela. Se Suzana solicitar uma alteração, o relatório de despesas é enviado de volta para Samuel. 

Samuel poderá reenviar o relatório de despesas. Ele pode fazer as alterações solicitadas primeiro ou pode reenviar a versão original do relatório de despesas. Se Samuel reenviar o relatório de despesas, ele será enviado a Fábio para aprovação, pois Fábio é o primeiro aprovador do processo de aprovação.




