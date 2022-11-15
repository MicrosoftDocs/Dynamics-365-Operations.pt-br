---
title: Exibir logs de histórico de plano e de planejamento
description: Este artigo explica como exibir o histórico de trabalhos de planejamento.
author: t-benebo
ms.date: 06/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: MPSPlanRegenerationJobList, MPSPlanRegenerationJobLogs
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: ab469686a009364bf53cb963506fd2107075a283
ms.sourcegitcommit: 491ab9ae2b6ed991b4eb0317e396fef542d3a21b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2022
ms.locfileid: "9740922"
---
# <a name="view-plan-history-and-planning-logs"></a>Exibir logs de histórico de plano e de planejamento

[!include [banner](../../includes/banner.md)]

Este artigo explica como exibir o histórico de trabalhos de planejamento no Microsoft Dynamics 365 Supply Chain Management.

Para exibir o histórico de um plano, abra o plano em **Planejamento mestre** \> **Configuração** \> **Planos** \> **Planos mestres** e selecione **Histórico**. O histórico lista todos os trabalhos do plano selecionado. A lista inclui os trabalhos concluídos e ativos.

O sistema mantém no máximo 60 registros de histórico por plano mestre e exclui registros com mais de 30 dias. Toda vez que você executa um novo cálculo de planejamento mestre, o sistema adiciona um novo registro de histórico e depois limpa os registros mais antigos conforme necessário.

Além de verificar a hora inicial e o status de trabalhos, você pode exibir o log para um determinado trabalho. O log inclui informações e avisos adicionais. Nem todos os trabalhos têm um log. Para exibir o log para um trabalho, selecione **Log**. As entradas de registro só são armazenadas por 30 dias após a data de término do trabalho, depois disso, são automaticamente excluídas.

Se a opção **Processamento em lotes** na Guia Rápida **Executar em segundo plano** foi habilitada durante a configuração do processamento do planejamento, o log do trabalho em lotes mostrará mais informações sobre quaisquer avisos e erros que foram gerados durante a execução do planejamento mestre. Por exemplo, os erros de confirmação automática são capturados somente no log do trabalho em lotes. Elas não são mostradas nos logs da página **Histórico**.

Para exibir erros de confirmação automática e outros avisos ou erros ocorridos durante a execução de um planejamento mestre, siga estas etapas:

1. Acesse **Administração do sistema \> Consultas \> Trabalhos em lotes**.
1. Encontre e selecione o registro que representa o planejamento mestre executado no qual você está interessado. (Por exemplo, o valor do campo **Descrição do trabalho** pode começar com *Planejamento mestre*.)
1. Siga uma destas etapas, dependendo se você estiver usando o *formulário avançado* ou o *formulário herdado (não avançado)* para a página **Trabalhos em lotes**:

    - Se estiver usando o formulário avançado: no Painel de Ações, selecione **Histórico de trabalho em lotes**. Em seguida, na página **Histórico de trabalho em lotes**, no Painel de Ações, selecione **Log**.
    - Se estiver usando o formulário herdado: no Painel de Ações, na guia **Trabalho em lotes**, selecione **Log**.

1. Selecione **Detalhes da mensagem** para abrir o painel **Detalhes da mensagem**, no qual você poderá exibir todos os avisos e erros capturados durante o processamento.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
