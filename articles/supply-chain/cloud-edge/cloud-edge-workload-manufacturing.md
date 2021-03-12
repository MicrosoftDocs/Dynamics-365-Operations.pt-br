---
title: Cargas de trabalho de execução de fabricação para unidades de escala de nuvem e de borda
description: Este tópico descreve como cargas de trabalho de execução de fabricação funcionam com unidades de escala de nuvem e de borda.
author: cabeln
manager: ''
ms.date: 10/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: SCM
ms.author: cabeln
ms.search.validFrom: 2020-10-06
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 08c46655d3966ad1433935318c5e60667dd10bb6
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4967750"
---
# <a name="manufacturing-execution-workloads-for-cloud-and-edge-scale-units"></a>Cargas de trabalho de execução de fabricação para unidades de escala de nuvem e de borda

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

> [!WARNING]
> Algumas funcionalidades comerciais não têm suporte total na versão preliminar pública quando unidades de escala de carga de trabalho são usadas.

Na execução de fabricação, as unidades de escala de nuvem e de borda fornecem os seguintes recursos, mesmo quando as unidades de borda não estão conectadas ao hub:

- Os operadores de máquina e os supervisores de chão de fábrica podem acessar o plano de produção operacional.
- Os operadores de máquina podem manter o plano atualizado ao executar trabalhos de fabricação discretos e de processo.
- O supervisor de chão de fábrica pode ajustar o plano operacional.
- Os trabalhadores podem acessar o tempo e a presença de entrada e de saída na borda para garantir o cálculo correto do pagamento do trabalhador.

Este tópico descreve como cargas de trabalho de execução de fabricação funcionam com unidades de escala de nuvem e de borda.

## <a name="the-manufacturing-lifecycle"></a>O ciclo de vida de fabricação

A ilustração a seguir mostra que o ciclo de vida da fabricação é dividido em três fases: *Planejar*, *Executar* e *Finalizar*.

[![Fases de execução de fabricação quando um único ambiente é usado](media/mes-phases.png "Fases de execução de fabricação quando um único ambiente é usado")](media/mes-phases-large.png)

A fase _Planejar_ inclui definição de produtos, planejamento, criação e agendamento de ordens e liberação. A etapa de liberação indica a transição da fase _Planejar_ para a fase _Executar_. Quando uma ordem de produção é liberada, os trabalhos de ordem de produção ficam visíveis no piso de produção e prontos para execução.

Quando um trabalho de produção é marcado como concluído, ele passa da fase _Executar_ para a fase _Finalizar_. Na fase _Finalizar_, os registros da fase *Executar* passam por um fluxo de trabalho de aprovação, em que são calculados, aprovados e transferidos. Nesse ponto, a ordem de produção é concluída. Portanto, é gerada a base do pagamento dos trabalhadores.

## <a name="splitting-the-execute-phase-into-a-separate-workload"></a>Dividir a fase Executar em uma carga de trabalho separada

Conforme ilustrado a seguir, quando as unidades de escala são usadas, a fase _Executar_ é dividida como uma carga de trabalho separada.

[![Fases de execução de fabricação quando unidades de escala são usadas](media/mes-phases-workloads.png "Fases de execução de fabricação quando unidades de escala são usadas")](media/mes-phases-workloads-large.png)

O modelo passa de uma instalação de única instância para um modelo baseado no hub e em unidades de escala. As fases _Planejar_ e _Finalizar_ são executadas como operações back office no hub; a carga de trabalho de execução de fabricação é executada nas unidades de escala. Os dados são transferidos de forma assíncrona entre o hub e as unidades de escala.

Quando uma ordem de produção é liberada no hub, todos os dados necessários para processar os trabalhos de produção são transferidos para a unidade de escala. Esses dados incluem ordens de produção, roteiros de produção, listas de materiais e produtos. Os dados que não estão relacionados a uma ordem de produção (como atividades indiretas, códigos de ausência e parâmetros de produção) também são transferidos do hub para a unidade de escala. Como regra, os dados obtidos no hub e que são transferidos para a unidade de escala só podem ser criados ou atualizados no hub. Por exemplo, não é possível criar um novo código de ausência ou uma atividade indireta na unidade de escala &mdash; eles só podem ser usados para registro. Os registros feitos na unidade de escala durante a execução são transferidos para o hub, no qual a aprovação de tempo e presença, o estoque e as atualizações financeiras são processados.

## <a name="manufacturing-execution-tasks-that-can-be-run-on-workloads"></a>Tarefas de execução de fabricação que podem ser executadas em cargas de trabalho

As seguintes tarefas de execução de fabricação podem ser executadas no momento em cargas de trabalho quando as unidades de escala são usadas:

- Registro de entrada, login, registro de saída e ausência
- Iniciar trabalho
- Agrupar trabalhos
- Progresso do relatório
- Relatório de sucata
- Atividade indireta
- Interrupção

## <a name="working-with-manufacturing-execution-workloads-on-the-hub"></a>Trabalhar com cargas de trabalho de execução de fabricação no hub

Normalmente, os processos necessários para executar cargas de trabalho de execução de fabricação são executados automaticamente para manter o hub e todas as unidades de escala em sincronia, conforme necessário. No entanto, se tiver problemas, você poderá disparar manualmente o processamento de registros brutos que são recebidos de cargas de trabalho e/ou verificar o log de processamento de registros.

### <a name="manually-process-raw-registrations"></a>Processar manualmente registros brutos

Um trabalho em lotes no Supply Chain Management é executado automaticamente para processar todos os registros que foram recebidos das cargas de trabalho. Esse trabalho cria os diários de produção e as entradas do livro de registro necessários quando um registro é processado para um trabalho concluído na carga de trabalho.

Embora o trabalho em geral seja executado automaticamente, você pode executá-lo manualmente a qualquer momento, entrando no hub e acessando **Controle de produção \> Tarefas periódicas \> Gerenciamento de carga de trabalho back office \> Processar registros brutos**.

### <a name="check-the-raw-registration-processing-log"></a>Verificar o log de processamento do registro bruto

Para revisar o log de processamento do registro, entre no hub e acesse **Controle de produção \> Tarefas periódicas \> Gerenciamento de carga de trabalho back office \> Log de processamento de registro bruto**. A página **Log de processamento de registro bruto** mostra uma lista de registros brutos processados e o status de cada registro.

![Página Log de processamento de registro bruto](media/mes-processing-log.png "Página Log de processamento de registro bruto")

Você pode trabalhar em qualquer registro na lista selecionando ele e um dos seguintes botões no Painel de Ações:

- **Processar** – processe manualmente o registro selecionado. Essa ação poderá ser útil se o trabalho _Processar registros brutos_ não for executado ou se ele falhar.
- **Cancelar** – cancele o registro selecionado.

## <a name="working-with-manufacturing-execution-workloads-on-a-scale-unit"></a>Trabalhar com cargas de trabalho de execução de fabricação em uma unidade de escala

Normalmente, os processos necessários para executar cargas de trabalho de execução de fabricação são executados automaticamente para manter o hub e todas as unidades de escala em sincronia, conforme necessário. No entanto, se tiver problemas, você poderá verificar o histórico de ordens que foram processadas em uma unidade de escala ou executar manualmente o trabalho _Hub de fabricação para processador de mensagens da unidade de escala_.

### <a name="view-the-history-of-manufacturing-jobs-that-have-been-processed-on-a-scale-unit"></a>Exibir o histórico de trabalhos de fabricação que foram processados em uma unidade de escala

Para revisar o histórico de trabalhos de fabricação que foram processados em uma unidade de escala, entre na máquina da unidade de escala e acesse **Controle de produção \> Tarefas periódicas \> Gerenciamento de carga de trabalho back office \> Histórico de processamento de trabalhos de fabricação**. A página **Histórico de processamento de trabalhos de fabricação** mostra o histórico de processamento das ordens de produção na unidade de escala. Você pode trabalhar em qualquer ordem de produção selecionando ela e um dos seguintes botões no Painel de Ações:

- **Processar** – processe manualmente a ordem de produção selecionada.
- **Cancelar** – cancele a ordem de produção selecionada.

### <a name="manufacturing-hub-to-scale-unit-message-processor-job"></a>Trabalho Hub de fabricação para processador de mensagens da unidade de escala

O trabalho _Hub de fabricação para processador de mensagens da unidade de escala_ processa dados do hub para a unidade de escala. Esse trabalho é iniciado automaticamente quando a carga de trabalho de execução de fabricação é implantada. No entanto, você pode executá-lo manualmente a qualquer momento, acessando **Controle de produção \> Tarefas periódicas \> Gerenciamento de carga de trabalho back office \> Hub de fabricação para processador de mensagens da unidade de escala**.
