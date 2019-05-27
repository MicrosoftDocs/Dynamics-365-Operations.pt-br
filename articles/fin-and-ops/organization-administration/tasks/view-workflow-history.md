---
title: Exibir histórico do fluxo de trabalho
description: Use estas etapas para exibir o status de um documento que foi enviado ao sistema de fluxo de trabalho para processamento e aprovação.
author: jasongre
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WorkflowStatus
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a40fe377322e2d64b751f6cace3eda20736cd321
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1560443"
---
# <a name="view-workflow-history"></a>Exibir histórico do fluxo de trabalho

[!include [task guide banner](../../includes/task-guide-banner.md)]

Use estas etapas para exibir o status de um documento que foi enviado ao sistema de fluxo de trabalho para processamento e aprovação. A empresa de dados demo usada para criar este procedimento é USMF.

1. Vá para Comum > Consultas > Fluxo de Trabalho > Histórico do fluxo de trabalho.
    * Use este formulário para exibir o status de um documento que foi enviado ao sistema de fluxo de trabalho para processamento e aprovação.  
    * A ID da instância é o código de identificação da instância do fluxo de trabalho que está processando ou que processou o documento.  
    * O Status é o status do fluxo de trabalho do documento selecionado.  
    * O ID do Fluxo de trabalho é o código de identificação do fluxo de trabalho que está processando ou que processou o documento.  
    * O Documento é o código de identificação do documento.  
    * O tipo de Documento é o tipo de documento que foi enviado para processamento.  
    * O Fluxo de trabalho é o nome do fluxo de trabalho que está processando ou que processou o documento.  
    * A Versão é o número da versão do fluxo de trabalho que está processando ou que processou o documento.  
    * A Data e hora de criação é a data e a hora em que o documento foi enviado.  
    * O Tempo decorrido é o tempo passado desde que o documento foi enviado.  
    * O botão Continuar permite que você continue o processo de fluxo de trabalho para o documento selecionado.  
    * O botão Recuperar permite recuperar o documento selecionado de forma que não seja processado.   
2. Na lista, clique no link na linha selecionada.
    * Certifique-se de que a seção Itens de trabalho está expandida.    Nesta seção você pode exibir os itens de trabalho associados ao documento selecionado. Por exemplo, uma tarefa pode precisar ser concluída ou o documento pode precisar de aprovação.  
    * O botão Reatribuir abre uma caixa de diálogo na qual é possível reatribuir um item de trabalho a outro usuário.  
    * Certifique-se de que a seção Detalhes do rastreamento está expandida.    Nesta seção você pode exibir o histórico de fluxo de trabalho do documento selecionado.  

