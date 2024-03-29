---
title: Eventos do aplicativo de depósito
description: Este artigo descreve o processamento de eventos de aplicativos de depósito usado para processar mensagens de eventos do aplicativo de depósito como parte de um trabalho em lotes.
author: perlynne
ms.date: 09/02/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSMobileDeviceQueueEvent
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-09
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 2dc24fed1ec71432d9e2a3e1cb5b366267c2938b
ms.sourcegitcommit: c98d55a4a6e27239ae6b317872332f01cbe8b875
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/02/2022
ms.locfileid: "9218732"
---
# <a name="warehouse-app-event-processing"></a>Processamento de eventos do aplicativo de depósito

[!include [banner](../includes/banner.md)]

Os trabalhos em lotes executados no Supply Chain Management podem usar dados de uma fila para processar eventos emitidos pelo aplicativo móvel Gerenciamento de Depósito para reagir conforme a necessidade dos eventos sinalizados. Esse recurso adiciona eventos relevantes à fila em resposta a certos tipos de ações executadas por trabalhadores usando o aplicativo. Um exemplo é ao usar o recurso *Criar e processar ordens de transferência do aplicativo de depósito*, as linhas e o cabeçalho da ordem de transferência serão criados e atualizados no back-end quando o sistema estiver executando o trabalho em lotes **Processar eventos do aplicativo de depósito**.

## <a name="turn-the-process-warehouse-app-events-feature-on-or-off"></a>Ativar ou desativar o recurso Processar eventos de aplicativo de depósito

A partir da versão 10.0.25 do Supply Chain Management, este recurso está ativado por padrão. A partir do Supply Chain Management versão 10.0.29, este recurso é obrigatório. Portanto, ele é ativado por padrão e não pode ser desativado novamente. Se você estiver executando uma versão anterior à 10.0.29, os administradores poderão habilitar ou desabilitar essa funcionalidade pesquisando o recurso *Processar eventos do aplicativo de depósito* no espaço de trabalho [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="set-up-a-batch-job-to-process-warehouse-app-events"></a>Configurar um trabalho em lotes para processar eventos de aplicativo de depósito

### <a name="process-warehouse-app-events"></a>Processar eventos do aplicativo de depósito

Configure um trabalho em lotes agendado para processar os eventos do aplicativo de depósito para a criação da ordem de transferência e as atualizações de linha.

1. Acesse **Gerenciamento de depósito \> Tarefas periódicas \> Processar remessas de saída**.
1. A caixa de diálogo Processar eventos do aplicativo de depósito será aberta. Expanda a guia rápida **Executar em segundo plano** e defina **Processamento em lotes** como **Sim**.
1. Na guia rápida **Executar em segundo plano**, selecione **Recorrência**.
1. A caixa de diálogo **Definir recorrência** será aberta. Defina o plano de execução, conforme necessário para a sua empresa.
1. Selecione **OK** para retornar à caixa de diálogo **Processar eventos de aplicativo de depósito**.
1. Selecione **OK** na caixa de diálogo **Processar eventos de aplicativo de depósito** para adicionar o trabalho em lotes à fila de lotes.

## <a name="query-warehouse-app-events"></a>Consultar eventos do aplicativo de depósito

Você pode exibir a fila de eventos e as mensagens de eventos geradas pelo aplicativo móvel Gerenciamento de Depósito indo para **Gerenciamento de depósito \> Consultas e relatórios \> Logs do dispositivo móvel \> Eventos do aplicativo de depósito**.

## <a name="the-standard-event-queue-process"></a>O processo da fila de eventos padrão

A fila de eventos de aplicativo de depósito normalmente será usada com o seguinte fluxo descrito:

1. Um evento é adicionado à fila com uma mensagem de evento. A nova mensagem inicialmente tem um estado de evento de **Espera**, o que significa que o trabalho em lotes **Processar eventos do aplicativo de depósito** não será coletado e processará essa mensagem.
1. Assim que o estado da mensagem é atualizado para **Enfileirado**, o trabalho em lotes **Processar aplicativo de depósito** irá coletar e processar o evento.
1. O trabalho em lotes atualiza os estados de evento para **Concluído** ou **Com falha**, dependendo do processo solicitado ser possível.
1. Quando todas as mensagens de evento relacionadas forem **Concluídas**, o evento será excluído da fila.

 Para obter um exemplo detalhado, consulte [Criar ordem de transferência do processo de aplicativo de depósito](create-transfer-order-from-warehouse-app.md).

## <a name="handle-event-errors"></a>Tratar erros de eventos

Como parte do processamento de eventos de depósito, a atividade de mensagem solicitada pode não receber processos do trabalho em lotes. Nesse caso, a mensagem do evento será alterada para **Com falha**. Você pode usar as informações do **Log do lote** para saber o motivo e tomar as medidas necessárias para corrigir qualquer problema.

Para obter um exemplo detalhado, consulte [Criar ordem de transferência do aplicativo de depósito](create-transfer-order-from-warehouse-app.md).

Para redefinir uma mensagem do evento de aplicativo de depósito com falha:

1. Acesse **Gerenciamento de depósito \> Consultas e relatórios \> Logs do dispositivo móvel \> Eventos do aplicativo de depósito**.
1. Na Guia Rápida **Mensagens de eventos do aplicativo de depósito**, localize e selecione um evento relevante que está mostrando **Com Falha** na coluna **Estado do evento**.
1. Selecione **Redefinir** na barra de ferramentas **Mensagens de eventos do aplicativo de depósito**.
1. Continue trabalhando até que todas as mensagens relevantes sejam redefinidas.

Você também pode remover uma mensagem de evento **Com falha** usando a opção **Excluir** na barra de ferramentas **Mensagens de eventos do aplicativo de depósito**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
