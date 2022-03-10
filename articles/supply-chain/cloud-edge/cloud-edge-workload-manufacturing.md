---
title: Cargas de trabalho de execução de fabricação para unidades de escala de nuvem e de borda
description: Este tópico descreve como cargas de trabalho de execução de fabricação funcionam com unidades de escala de nuvem e de borda.
author: cabeln
ms.date: 10/06/2020
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 633740ee1e26d2e4ed2ea7031ef298fb11c2ab58
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8068835"
---
# <a name="manufacturing-execution-workloads-for-cloud-and-edge-scale-units"></a>Cargas de trabalho de execução de fabricação para unidades de escala de nuvem e borda

[!include [banner](../includes/banner.md)]

> [!IMPORTANT]
> A carga de trabalho de execução de fabricação está disponível no momento apenas na versão preliminar.
>
> Algumas funcionalidades comerciais não têm suporte total na versão preliminar pública quando unidades de escala de carga de trabalho são usadas.
>
> Não é possível executar a carga de trabalho de execução de fabricação de versão preliminar em uma unidade de escala em que a carga de trabalho de execução do depósito também é instalada.

Na execução de fabricação, as unidades de escala fornecem os seguintes recursos:

- Os operadores de máquina e os supervisores de chão de fábrica podem acessar o plano de produção operacional.
- Os operadores de máquina podem manter o plano atualizado ao executar trabalhos de fabricação discretos e de processo.
- O supervisor de chão de fábrica pode ajustar o plano operacional.
- Os trabalhadores podem acessar o tempo e a presença de entrada e de saída na borda para garantir o cálculo correto do pagamento do trabalhador.

Este tópico descreve como cargas de trabalho de execução de fabricação funcionam com unidades de escala de nuvem e de borda.

## <a name="the-manufacturing-lifecycle"></a>O ciclo de vida de fabricação

A ilustração a seguir mostra que o ciclo de vida da fabricação é dividido em três fases: *Planejar*, *Executar* e *Finalizar*.

[![Fases de execução de fabricação quando um único ambiente é usado](media/mes-phases.png "Fases de execução de fabricação quando um único ambiente é usado.")](media/mes-phases-large.png)

A fase _Planejar_ inclui definição de produtos, planejamento, criação e agendamento de ordens e liberação. A etapa de liberação indica a transição da fase _Planejar_ para a fase _Executar_. Quando uma ordem de produção é liberada, os trabalhos de ordem de produção ficam visíveis no piso de produção e prontos para execução.

Quando um trabalho de produção é marcado como concluído, ele passa da fase _Executar_ para a fase _Finalizar_. Na fase _Finalizar_, os registros da fase *Executar* passam por um fluxo de trabalho de aprovação, em que são calculados, aprovados e transferidos. Nesse ponto, a ordem de produção é concluída. Portanto, é gerada a base do pagamento dos trabalhadores.

## <a name="splitting-the-execute-phase-into-a-separate-workload"></a>Dividir a fase Executar em uma carga de trabalho separada

Conforme ilustrado a seguir, quando as unidades de escala são usadas, a fase _Executar_ é dividida como uma carga de trabalho separada.

[![Fases de execução de fabricação quando unidades de escala são usadas](media/mes-phases-workloads.png "Fases de execução de fabricação quando unidades de escala são usadas.")](media/mes-phases-workloads-large.png)

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
- Relatar como finalizado e guardar (exige que você também execute a carga de trabalho de execução do armazém na sua unidade de escala, consulte também [Relatar como finalizado e guardar em uma unidade de escala](#RAF))

## <a name="working-with-manufacturing-execution-workloads-on-the-hub"></a>Trabalhar com cargas de trabalho de execução de fabricação no hub

Normalmente, os processos necessários para executar cargas de trabalho de execução de fabricação são executados automaticamente para manter o hub e todas as unidades de escala em sincronia, conforme necessário. No entanto, se tiver problemas, você poderá disparar manualmente o processamento de registros brutos que são recebidos de cargas de trabalho e/ou verificar o log de processamento de registros.

### <a name="manually-process-raw-registrations"></a>Processar manualmente registros brutos

Um trabalho em lotes no Supply Chain Management é executado automaticamente para processar todos os registros que foram recebidos das cargas de trabalho. Esse trabalho cria os diários de produção e as entradas do livro de registro necessários quando um registro é processado para um trabalho concluído na carga de trabalho.

Embora o trabalho em geral seja executado automaticamente, você pode executá-lo manualmente a qualquer momento, entrando no hub e acessando **Controle de produção \> Tarefas periódicas \> Gerenciamento de carga de trabalho back office \> Processar registros brutos**.

### <a name="check-the-raw-registration-processing-log"></a>Verificar o log de processamento do registro bruto

Para revisar o log de processamento do registro, entre no hub e acesse **Controle de produção \> Tarefas periódicas \> Gerenciamento de carga de trabalho back office \> Log de processamento de registro bruto**. A página **Log de processamento de registro bruto** mostra uma lista de registros brutos processados e o status de cada registro.

![Página Log de processamento de registro bruto.](media/mes-processing-log.png "Página Log de processamento de registro bruto")

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

<a name="RAF"></a>

## <a name="report-as-finished-and-putaway-on-a-scale-unit"></a>Relatar como finalizado e guardar em uma unidade de escala

<!-- KFM: 
This section describes how to enable the abilities to report as finished and then putaway finished items when you are using to a scale unit.

### Enable and use report as finished and putaway on a scale unit -->

Na versão atual, as operações de relatar como finalizado e guardar (para produtos acabados, coprodutos e subprodutos) são compatíveis pela [carga de trabalho de execução do armazém](cloud-edge-workload-warehousing.md) (e não a carga de trabalho de execução de fabricação). Portanto, para usar esta funcionalidade quando conectado a uma unidade de escala, você deve fazer o seguinte:

- Instale a carga de trabalho de execução do armazém e a carga de trabalho de execução de fabricação na sua unidade de escala.
- Use o aplicativo móvel Warehouse Management para relatar como finalizado e processar o trabalho de guardar. No momento, a interface de execução do chão de fábrica não dão suporte a esses processos.

<!-- KFM: API details needed

### Customize report as finished and putaway functionality

 -->

## <a name="enable-and-use-the-start-operation-on-a-scale-unit"></a>Habilitar e usar a operação de início em uma unidade de escala

Na versão atual, a operação de início para ordens de produção e lote é compatível pela [carga de trabalho de execução do depósito](cloud-edge-workload-warehousing.md) (não a carga de trabalho de execução de fabricação). Portanto, para usar esta funcionalidade em que você está conectado a uma unidade de escala, você deve concluir estas tarefas:

- Instale a carga de trabalho de execução do armazém e a carga de trabalho de execução de fabricação na sua unidade de escala.
- Habilite o recurso *Iniciar a ordem de produção na carga de trabalho de gerenciamento de depósito para unidades de escala de nuvem e de borda* em [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).
- Use o Warehouse Management Mobile app para iniciar a ordem de produção ou de lote.

## <a name="enable-and-use-material-consumption-on-a-scale-unit"></a>Habilitar e usar consumo de material em uma unidade de escala

Na versão atual, o fluxo no Warehouse Management Mobile app para registrar o consumo de material tem suporte da [carga de trabalho de execução de depósito](cloud-edge-workload-warehousing.md) (não a carga de trabalho de execução de fabricação). Portanto, para usar esta funcionalidade em que você está conectado a uma unidade de escala, você deve concluir estas tarefas:

- Instale a carga de trabalho de execução do armazém e a carga de trabalho de execução de fabricação na sua unidade de escala.
- Habilite o recurso *Registrar consumo de materiais no aplicativo móvel em uma unidade de escala* em [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).
- Use o Warehouse Management Mobile app para registrar o consumo de material.

[!INCLUDE [cloud-edge-privacy-notice](../../includes/cloud-edge-privacy-notice.md)]

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
