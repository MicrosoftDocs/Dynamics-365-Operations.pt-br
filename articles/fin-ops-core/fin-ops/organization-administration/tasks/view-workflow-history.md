---
title: Exibir histórico do fluxo de trabalho
description: Este tópico descreve as etapas para exibir o status de um documento que foi enviado ao sistema de fluxo de trabalho para processamento e aprovação.
author: jasongre
ms.date: 07/09/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: WorkflowStatus
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0ca9a8bff246cc878a0703947a7f8c1c4fc01963
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8069950"
---
# <a name="view-workflow-history"></a>Exibir histórico do fluxo de trabalho

[!include [banner](../../includes/banner.md)]


[!INCLUDE [PEAP](../../../../includes/peap-1.md)]

Este tópico descreve as etapas para exibir o status de um documento que foi enviado ao sistema de fluxo de trabalho para processamento e aprovação. A empresa de dados demo usada para criar este procedimento é USMF.

1. Acesse **Painel de navegação > Módulos > Comum > Consultas > Fluxo de trabalho > Histórico de fluxo de trabalho**.
    - Use este formulário para exibir o status de um documento que foi enviado ao sistema de fluxo de trabalho para processamento e aprovação.  
    - A **ID da instância** é o código de identificação da instância do fluxo de trabalho que está processando ou que processou o documento.  
    - O **Status** é o status do fluxo de trabalho do documento.  
    - A **ID do fluxo de trabalho** é o código de identificação do fluxo de trabalho que está processando ou que processou o documento.  
    - O **Documento** é o código de identificação do documento.  
    - O **Tipo de documento** é o tipo de documento que foi enviado para processamento.  
    - O **Fluxo de trabalho** é o nome do fluxo de trabalho que está processando ou que processou o documento.  
    - A **Versão** é o número da versão do fluxo de trabalho que está processando ou que processou o documento.  
    - A **Data e hora de criação** é a data e a hora em que o documento foi enviado.  
    - O **Tempo decorrido** é o tempo passado desde que o documento foi enviado.  
    - O botão **Continuar** permite que você continue o processo de fluxo de trabalho para o documento selecionado.  
    - O botão **Recuperar** permite recuperar o documento selecionado de forma que não seja processado.   
2. Na lista, selecione o link na linha desejada.
    - Certifique-se de que a seção **Itens de trabalho** está expandida. Nesta seção você pode exibir os itens de trabalho associados ao documento selecionado. Por exemplo, uma tarefa pode precisar ser concluída ou o documento pode precisar de aprovação.  
    - O botão **Reatribuir** abre uma caixa de diálogo na qual é possível reatribuir um item de trabalho a outro usuário.  
    - Certifique-se de que a seção **Detalhes do rastreamento** está expandida. Nesta seção você pode exibir o histórico de fluxo de trabalho do documento selecionado.  



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]