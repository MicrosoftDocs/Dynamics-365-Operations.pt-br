---
title: Processamento de lotes de alertas
description: Este tópico fornece informações sobre o processamento em lotes de alertas.
author: tjvass
manager: AnnBe
ms.date: 09/10/2010
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application user
ms.reviewer: sericks
ms.search.region: Global
ms.author: tjvass
ms.search.validFrom: 2018-3-30
ms.dyn365.ops.version: Platform update 15
ms.openlocfilehash: 4e34685731a09131d2ab49a0e04479c9c20f4da8
ms.sourcegitcommit: f5e31c34640add6d40308ac1365cc0ee60e60e24
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/08/2020
ms.locfileid: "4693789"
---
# <a name="batch-processing-of-alerts"></a>Processamento em lotes de alertas

[!include [banner](../includes/banner.md)]

Os alertas são processados pela funcionalidade de processamento em lotes. É necessário configurar o processamento em lotes antes dos alertas serem emitidos.

Há suporte para dois tipos de eventos:

- Eventos que são disparados por eventos baseados em alterações. Esses eventos também são conhecidos como criar/excluir e atualizar eventos.
- Eventos que são disparados pela data de vencimento.

Você pode configurar processos em lotes para cada tipo de evento.
        
## <a name="batch-processing-for-change-based-events"></a>Processamento em lotes para eventos baseados em alterações

O sistema lê todos os eventos baseados em alterações que ocorreram desde a última execução do processamento em lotes. Os eventos baseados em alteração incluem as atualizações nos campos, a exclusão de registros e a criação de registros. Esses eventos são comparados com as condições configuradas em regras de alerta. Quando um evento corresponde às condições de uma regra, o processo em lote gera um alerta.

### <a name="frequency-for-change-based-events"></a>Frequência para eventos baseados em alterações

Para eventos baseados em alteração, você pode configurar um trabalho de lote que dispare o processamento de um evento assim que o evento for registrado pelo sistema. Se você configurar o trabalho em lotes para uma repetição mais frequente, os usuários receberão os alertas mais rapidamente após a ocorrência de alterações. Entretanto, uma alta frequência de processamento em lotes pode ter um impacto negativo no desempenho do sistema.

Por outro lado, um trabalho em lotes que ocorra com menos frequência ou que esteja programado para horários em que a carga do sistema estiver baixa pode ajudar a melhorar o desempenho do sistema. Entretanto, uma frequência baixa de processamento em lotes pode não atender as demandas de usuários de alertas oportunos.

Portanto, quando você configura a frequência do processamento em lotes para eventos baseados em alteração, considere o equilíbrio entre o tempo dos alertas e a performance de todo o sistema. Essas considerações se tornam mais relevantes de acordo com o aumento do número de usuários que criam regras de alerta. A frequência não afeta o número de eventos que devem ser processados. No entanto, se mais usuários criarem regras, mais verificações deverão ser feitas. Esse tipo de troca de dados pode afetar o desempenho do sistema.

#### <a name="the-risks-of-low-batch-frequency"></a>Os riscos de frequência de lote baixa

Se você definir uma frequência baixa para o processamento em lotes para eventos baseados em alterações, os dados que são relevantes para as condições nas regras de alerta podem ser alterados antes do processamento do lote. Portanto, você pode perder alertas.

Por exemplo, uma regra de alerta é configurada para disparar um alerta quando o evento for **alterações de contato do cliente** e a condição for **cliente = BB**. Em outras palavras, quando o contato do cliente para cliente BB for alterado, o evento será registrado. No entanto, o sistema de processamento em lote é configurado de forma que ele seja menos frequente do que a entrada de dados. Se o nome do cliente for alterado de **BB** para **AA** antes de o evento ser processado, os dados no banco de dados não corresponderão mais à condição na regra, **cliente = BB**. Portanto, quando o evento for finalmente processado, nenhum alerta será gerado.

### <a name="set-up-processing-for-change-based-alerts"></a>Configurar o processamento para alertas com base em alteração

1. Vá para **Administração do sistema** &gt; **Tarefas periódicas** &gt; **Alertas** &gt; **Alertas com base nas alterações**.
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

Se você configurar uma janela de processamento em lotes, um alerta será enviado quando a regra de alerta for processada, mesmo se o alerta ultrapassar o limite de tempo definido nos critérios de data de vencimento. Um alerta continuará a ser enviado desde que o período definido por esse limite de tempo, mais a janela de processamento em lotes não sejam excedidos. No entanto, quando o período definido pelo limite de tempo e a janela de processamento em lotes se excederem, um alerta não será mais enviado.

### <a name="set-up-processing-for-due-date-alerts"></a>Configurar o processamento para alertas de data de vencimento

1. Vá para **Administração do sistema** &gt; **Tarefas periódicas** &gt; **Alertas** &gt; **Alertas de data de vencimento**.
2. Na caixa de diálogo **Alertas de data de vencimento** , insira as informações apropriadas.
