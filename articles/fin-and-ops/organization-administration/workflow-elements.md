---
title: Elementos do fluxo de trabalho
description: "Este tópico descreve os diversos elementos que compõem um fluxo de trabalho."
author: sericks007
manager: AnnBe
ms.date: 11/03/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 56441
ms.assetid: de740262-6ffd-42b9-a325-540eae5cec94
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 8bbdbf882f6f73d03be0a036cb975109396e4a0d
ms.openlocfilehash: 15cac09a97305c1b467cbb97da2d4b8a864ccbc7
ms.contentlocale: pt-br
ms.lasthandoff: 11/14/2017

---

# <a name="workflow-elements"></a>Elementos do fluxo de trabalho

[!include [banner](../includes/banner.md)]

Este tópico descreve os diversos elementos que compõem um fluxo de trabalho.

Um fluxo de trabalho consiste em elementos. As seções a seguir descrevem cada tipo de elemento.

## <a name="tasks"></a>Tarefas

Uma *tarefa* é uma unidade de trabalho que deve ser executada. Dois tipos de tarefas podem ser adicionados a um fluxo de trabalho: tarefas manuais e tarefas automatizadas.

### <a name="manual-task"></a>Tarefa manual

Uma *tarefa manual* é uma unidade de trabalho que deve ser executada por um usuário. Por exemplo, um fluxo de trabalho de relatório de despesas pode ter tarefas manuais que exijam que os usuários atribuídos concluam as seguintes ações:

- Revisem os recibos que são enviados junto com um relatório de despesas.
- Liguem para o gerente de um funcionário.

### <a name="automated-task"></a>Tarefa automatizada

Uma *tarefa automatizada* é uma unidade de trabalho que deve ser executada pelo sistema. Não exige interação humana. Por exemplo, um fluxo de trabalho da ordem de venda pode ter tarefas automatizadas que exijam que o sistema conclua as seguintes ações:

- Execute uma verificação de crédito.
- Crie um registro para o cliente, caso não exista um ainda.

## <a name="approval-processes"></a>Processos de aprovação

Um *processo de aprovação* consiste em etapas isoladas. Em cada etapa de aprovação, o usuário pode executar as seguintes ações:

- Aprovar o documento.
- Rejeitar o documento.
- Solicitar uma alteração no documento.
- Atribuir o documento a outro usuário para aprovação.

## <a name="line-item-workflow-elements"></a>Elementos de fluxo de trabalho de item de linha

Um fluxo de trabalho pode ser criado para processar documentos ou os itens de linha em um documento. Por exemplo, você criou um fluxo de trabalho de aprovação para folhas de ponto. (Faremos referência a esse fluxo de trabalho como *fluxo de trabalho de documento*.) Você pode adicionar um elemento de *fluxo de trabalho de item de linha* a esse fluxo de trabalho de documento. Quando o elemento de item de linha é executado, cada item de linha do documento é enviado para processamento. Talvez seja conveniente que todos os itens de linha sejam processados pelo mesmo fluxo de trabalho de item de linha ou que cada item de linha seja processado por um fluxo de trabalho de item de linha diferente. Suponha que um funcionário tenha enviado uma folha de ponto que se assemelhe à figura a seguir.

![Fluxo de trabalho com itens de linha](./media/workflow_lineitemworkflow.gif)

Nesse cenário, talvez seja conveniente criar os seguintes fluxos de trabalho de item de linha:

- **Fluxo de trabalho de item de linha 1** – Esse fluxo de trabalho é usado para processar itens de linha onde a ID de projeto é 1111.
- **Fluxo de trabalho de item de linha 2** – Esse fluxo de trabalho é usado para processar itens de linha onde a ID de projeto é 2222.
- **Fluxo de trabalho de item de linha 3** – esse fluxo de trabalho é usado para processar itens de linha onde a ID de projeto é 3333.

## <a name="flow-control-elements"></a>Elementos de controle de fluxo

Os elementos a seguir permitem projetar os fluxos de trabalho com ramificações alternativas ou ramificações executadas ao mesmo tempo.

### <a name="manual-decision"></a>Decisão manual

Uma *decisão manual* é um ponto em que um fluxo de trabalho se divide em duas ramificações. Um usuário deve tomar uma decisão, e essa decisão determina qual ramificação é usada para processar o documento que foi enviado.

### <a name="conditional-decision"></a>Decisão condicional

Uma *decisão condicional* também é um ponto em que um fluxo de trabalho se divide em duas ramificações. No entanto, o sistema decide qual ramificação é usada para processar o documento que foi enviado. Para tomar esta decisão, o sistema avaliará o documento para determinar se ele atende às condições especificadas.

### <a name="parallel-activity"></a>Atividade paralela

Uma *atividade paralela* é um elemento de fluxo de trabalho que inclui duas ou mais ramificações de fluxo de trabalho executadas ao mesmo tempo.

### <a name="subworkflow"></a>Subfluxo de trabalho

Um *subfluxo de trabalho* é um fluxo de trabalho executado no contexto de outro fluxo de trabalho.

