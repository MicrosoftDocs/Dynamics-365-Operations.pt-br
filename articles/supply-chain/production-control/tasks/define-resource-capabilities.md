--- 
title: Definir capacidades do recurso
description: "As funcionalidade do recurso descrevem qual recursos de operações podem ser feitos."
author: sorenva
manager: AnnBe
ms.date: 10/27/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: sorenand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 99c230c0e6a580f77d863b6f0be298615966c479
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---
# <a name="define-resource-capabilities"></a>Definir capacidades do recurso

[!include [task guide banner](../../includes/task-guide-banner.md)]

As funcionalidade do recurso descrevem qual recursos de operações podem ser feitos. Durante a programação, os requisitos de cada trabalho e a operação são correspondentes em relação às funcionalidades de recursos disponíveis. Essa guia da tarefa irá ajudá-lo a criar uma funcionalidade de recursos e a atribui a um recurso. A empresa de dados demo usada para criar esta tarefa é USMF.


## <a name="create-a-resource-capability"></a>Criar uma nova capacidade de recurso
1. Ir para Capacidades do recurso.
2. Clique em Novo.
3. No campo Capacidade, digite a ID de capacidade do recurso.
    * Para uma operação específica, use a ID do recurso para especificar quais recursos devem ter esse recurso para executar a operação.  
4. No campo Descrição, insira uma descrição da capacidade.

## <a name="assign-capability-to-a-resource"></a>Atribuir a capacidade a um recurso
1. Clique em Adicionar.
2. No campo Recurso, digite a ID do recurso.
    * Uma funcionalidade do recurso pode ser atribuída a um ou vários recursos.  
3. No campo Vencimento, insira uma data.
    * É possível usar este campo para especificar uma funcionalidade do recurso somente por um tempo limitado.  
4. No campo Prioridade, insira um número.
    * Quando você planejar o trabalho e operações, você pode especificar se deseja selecionar recursos prioridade. Se você optar por fazer isso, é possível definir mais de um recurso para executar o trabalho ou a operação na data de solicitação, o recurso com a menor prioridade em relação ao recurso necessário está selecionado.  
5. No campo Nível, insira um número.
    * Quando você especifica que um trabalho ou uma operação requer um recurso específico, você também pode especificar o nível mínimo necessário. Use o recurso em nível para diferenciar os recursos que podem realizar o mesmo trabalho, velocidades diferentes, pontos fortes, tamanho, e assim por diante.  


