---
title: Processamento em lotes de alertas
description: Este artigo fornece informações sobre o processamento em lotes de alertas.
author: RichdiMSFT
ms.date: 08/24/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: sericks
ms.search.region: Global
ms.author: richdi
ms.search.validFrom: 2018-3-30
ms.dyn365.ops.version: Platform update 15
ms.openlocfilehash: ba17ebe1bdd95b8780b99b8f82b566bf527aca89
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8860058"
---
# <a name="batch-processing-of-alerts"></a>Processamento em lotes de alertas

[!include [banner](../includes/banner.md)]

Os alertas são processados pela funcionalidade de processamento em lotes. É necessário configurar o processamento em lotes para que o processo emita os alertas.

A funcionalidade de processamento em lotes oferece suporte a dois tipos de eventos:

- Eventos acionados por eventos baseados em alterações. Esses eventos também são conhecidos como criar/excluir e atualizar eventos.
- Eventos acionados por datas de vencimento.

Você pode configurar processos em lotes para cada tipo de evento.

## <a name="batch-processing-for-change-based-events"></a>Processamento em lotes para eventos baseados em alterações

O sistema lê todos os eventos baseados em alterações que ocorreram desde a última execução do processamento em lotes. Os eventos baseados em alteração incluem as atualizações nos campos, a exclusão de registros e a criação de registros. Esses eventos são comparados com as condições que você configura em regras de alerta. Quando um evento corresponde às condições de uma regra, o processo em lote gera um alerta.

### <a name="frequency-for-change-based-events"></a>Frequência para eventos baseados em alterações

Para eventos baseados em alteração, você pode configurar um trabalho de lote que dispare o processamento de um evento assim que o sistema registrar o evento. Se você configurar o trabalho em lotes para uma repetição mais frequente, os usuários receberão os alertas mais rapidamente após a ocorrência de alterações. Entretanto, uma alta frequência de processamento em lotes pode ter um impacto negativo no desempenho do sistema.

Por outro lado, um trabalho em lotes que ocorra com menos frequência e que você tenha agendado para horários em que a carga do sistema estiver baixa pode ajudar a melhorar o desempenho do sistema. Entretanto, uma frequência baixa de processamento em lotes pode não atender as demandas de usuários de alertas oportunos.

Portanto, quando você configura a frequência do processamento em lotes para eventos baseados em alteração, considere o equilíbrio entre o tempo dos alertas e a performance de todo o sistema. Essas considerações se tornam mais relevantes de acordo com o aumento do número de usuários que criam regras de alerta. A frequência não afeta o número de eventos que o sistema processa. No entanto, se mais usuários criarem regras, o processo executa mais verificações. Esse tipo de troca de dados pode afetar o desempenho do sistema.

#### <a name="the-risks-of-low-batch-frequency"></a>Os riscos de frequência de lote baixa

Se você definir uma frequência baixa para o processamento em lotes para eventos baseados em alterações, os dados que são relevantes para as condições nas regras de alerta podem mudar antes do processamento. Portanto, você pode perder alertas.

Por exemplo, você cria um alerta para ser acionado quando o evento for **alterações de contato do cliente** e a condição for **cliente = BB**. Em outras palavras, quando o contato do cliente para cliente BB for alterado, o processo registrará o evento. No entanto, o sistema de processamento em lote é configurado de forma que ele seja menos frequente do que a entrada de dados. Se o nome do cliente for alterado de **BB** para **AA** antes do evento ser processado, os dados no banco de dados não corresponderão à condição na regra: **cliente = BB**. Portanto, quando o evento for finalmente processado, nenhum alerta será gerado.

### <a name="set-up-processing-for-change-based-alerts"></a>Configurar o processamento para alertas com base em alteração

1. Acesse **Administração do sistema** &gt; **Tarefas periódicas** &gt; **Alertas** &gt; **Alertas com base nas alterações**.
2. Na caixa de diálogo **Alertas com base nas alterações** , insira as informações apropriadas.

## <a name="batch-processing-for-due-date-events"></a>Processamento de lotes de eventos com data de vencimento

O sistema detecta todos os eventos causados por datas de vencimento e compara esses eventos com as condições definidas nas regras de alerta. O processo em lote gera um alerta quando um evento corresponde à condição de uma regra.

### <a name="frequency-for-due-date-events"></a>Frequência de eventos com data de vencimento

Para eventos com data de vencimento, você pode configurar trabalhos em lotes que está sendo executados durante a noite ou em horários específicos do dia para equilibrar a carga do sistema. É recomendável configurar o trabalho em lotes para ser executado pelo menos uma vez por dia. Se os alertas tiverem que ser enviados o mais rápido possível, configure o processamento em lotes para ocorrer imediatamente após a alteração da data do sistema. Se quiser gerar alertas para eventos com data de vencimento que ocorram depois que o trabalho em lotes tiver processado os alertas, execute o trabalho em lotes novamente no mesmo dia.

Por exemplo, um trabalho em lote foi executado em um dia específico. Em seguida você cria uma ordem de compra com uma data de vencimento que deve disparar um alerta no mesmo dia. Para receber o alerta nesse dia, você precisa executar o trabalho em lote novamente, depois que a ordem de compra for criada. Entretanto, se você não executar o trabalho em lotes novamente nesse dia, o trabalho em lotes do dia seguinte detectará todos os eventos com data de vencimento não processados nos dias anteriores.

> [!NOTE]
> Mesmo quando o processamento em lotes for executado mais de uma vez ao dia, os alertas não serão duplicados para as mesmas condições e eventos com data de vencimento. Os alertas só serão gerados para as datas que vencerem devido a alterações do sistema que tiverem ocorrido após a execução do último trabalho em lotes.

### <a name="batch-processing-window"></a>Janela de processamento em lote

O processamento de regras de alerta em uma empresa pode ser interrompido por vários motivos. Esses motivos incluem férias, erros do sistema ou outros problemas que impedem a execução de trabalhos em lotes durante um período.

Para evitar que os alertas com data de vencimento se tornem obsoletos porque o trabalho em lotes não foi executado por vários dias, você pode configurar uma janela de processamento em lotes. Uma janela de processamento em lotes pode ser usada para impedir a execução de um trabalho em lotes durante um número especificado de dias.

Se você configurar uma janela de processamento em lotes, um alerta será enviado quando a regra de alerta for processada, mesmo se o alerta ultrapassar o limite de tempo definido nos critérios de data de vencimento. Um alerta continuará a ser enviado desde que o período definido por esse limite de tempo, mais a janela de processamento em lotes não sejam excedidos. No entanto, quando o período excede o valor definido pelo limite de tempo e a janela de processamento em lotes, um alerta não será mais enviado.

### <a name="set-up-processing-for-due-date-alerts"></a>Configurar o processamento para alertas de data de vencimento

1. Acesse **Administração do sistema** &gt; **Tarefas periódicas** &gt; **Alertas** &gt; **Alertas de data de vencimento**.
2. Na caixa de diálogo **Alertas de data de vencimento** , insira as informações apropriadas.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
