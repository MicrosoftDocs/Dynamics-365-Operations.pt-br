---
title: Agendar a criação de trabalho durante o ciclo
description: Este tópico descreve como configurar e usar o método de processamento Agendar ciclo de criação de trabalho.
author: perlynne
manager: mirzaab
ms.date: 01/14/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSPostMethod, WHSWavePostMethodTaskConfig, WHSWaveTemplateTable, WHSParameters, WHSWaveTableListPage, WHSWorkTableListPage, WHSWorkTable, BatchJobEnhanced, WHSPlannedWorkOrder
audience: Application User
ms.reviewer: ''
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2021-01-14
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 36a450f78695f617056875f8d236fe46bc66aaaf
ms.sourcegitcommit: 2b4809e60974e72df9476ffd62706b1bfc8da4a7
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/04/2021
ms.locfileid: "5501213"
---
# <a name="schedule-work-creation-during-wave"></a>Agendar a criação de trabalho durante o ciclo

[!include [banner](../../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Use o recurso *Agendar criação de trabalho* como parte do seu processo cíclico para ajudar a aumentar o resultado do processamento em ciclos, fazendo com que o sistema crie o trabalho usando o processamento paralelo.

Quando a funcionalidade estiver habilitada, o trabalho planejado será criado automaticamente, e o sistema eventualmente irá processá-lo para criar o trabalho real. Se o número de linhas de carga de ciclos atingir um limite predeterminado, o sistema criará o trabalho real mais rapidamente, aplicando o processamento paralelo assíncrono.

## <a name="enable-the-schedule-work-creation-feature"></a>Habilitar o recurso Agendar criação de trabalho

### <a name="enable-the-feature-in-feature-management"></a>Habilitar o recurso no gerenciamento de recursos

Para que você possa usar o recurso *Agendar criação de trabalho*, ele deve estar ativado no sistema. Os administradores podem usar o espaço de trabalho [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar o status do recurso e ativá-lo, se necessário. Nesse caso, o recurso é listado da seguinte maneira:

- **Módulo:** *Gerenciamento de Depósito*
- **Nome do recurso:** *Agendar criação de trabalho*

> [!NOTE]
> O recurso *Bloquear trabalho em toda a organização* deve estar habilitado para que você possa habilitar o recurso *Agendar criação de trabalho*.

### <a name="manually-enable-batch-processing-of-waves"></a>Habilitar o processamento manualmente em lotes de ciclos

Para aproveitar um método assíncrono paralelo para criar trabalho de depósito, o processo de ciclos deve estar sendo executado em lotes. Para fazer essa configuração:

1. Vá para **Gerenciamento de depósito \> Configuração \> Parâmetros de gerenciamento de depósito**.

1. Na guia **Geral**, defina a opção **Processar ciclos em lote** como *Sim*. Se preferir, você também pode selecionar um **Grupo de lotes de processamento em ciclos** dedicado para impedir que o processamento de fila em lotes seja executado ao mesmo tempo que outros processos.

1. Defina o **Tempo de espera para o bloqueio (ms)**, que se aplica quando o sistema está processando vários ciclos ao mesmo tempo. Para a maioria dos processos em ciclos maiores, recomendamos um valor de *60.000*.

### <a name="manually-enable-the-new-wave-step-method-for-existing-wave-templates"></a>Habilitar manualmente o novo método de etapa de ciclo para modelos de ciclo existentes

Comece criando o novo método de etapa de ciclo e habilite-o para o processamento de tarefas assíncronas paralelas.

1. Vá para **Gerenciamento de depósito \> Configuração \> Ondas \> Métodos de processo de onda**.

1. Selecione  **Gerar método novamente** e observe que *WHSScheduleWorkCreationWaveStepMethod* foi adicionado à lista de métodos de processo de ciclo que podem ser usados nos modelos de ciclo de remessa.

1. Selecione o registro com o **Nome do método** *WHSScheduleWorkCreationWaveStepMethod* e selecione **Configuração de tarefas**.

1. Para adicionar uma nova linha à grade, selecione **Novo** no Painel de Ações e use as seguintes configurações:

    - **Depósito** - Selecione o depósito que será usado para agendar o processamento de criação de trabalho.

    - **Número máximo de tarefas em lotes** - Especifique um número máximo de tarefas em lotes. Na maioria dos casos, esse valor deve estar no intervalo de 8-16, mas recomendamos que você experimente a configuração ideal com base nos seus cenários.

    - **Grupo de lotes de processamento em ciclos** - Selecione um grupo de lotes de processamento em ciclos dedicados para otimizar o processamento da fila de lotes.

Agora, você está pronto para atualizar um modelo de ciclo existente (ou criar um novo) para usar o método de processamento em ciclos *Agendar criação de trabalho*.

1. Vá para **Gerenciamento de depósito \> Configuração \> Ciclos \> Modelos de ciclo**.

1. Selecione **Editar** no Painel de Ações.

1. No painel de lista, selecione o modelo de ciclo que deseja atualizar (se você estiver testando com dados de demonstração, poderá usar *24 Padrão de remessa*).

1. Expanda a guia rápida **Métodos** e selecione a linha com o **Nome** *Agendar criação de trabalho* na grade **Métodos restantes**.

1. Selecione a seta apontando para a coluna **Métodos selecionados** para mover a linha selecionada para essa coluna. (Você só pode ter um método selecionado de cada vez que use o *WHSScheduleWorkCreationWaveStepMethod* ou *createWork*, portanto, a linha existente com o **Nome do método** *createWork* será automaticamente movida para a grade **Métodos restantes**.)

## <a name="set-wave-task-processing-threshold-data"></a>Definir dados do limite de processamento de tarefa de ciclo

O sistema criará dados padrão de limite de processamento de tarefa de ciclo na primeira vez que um processo de ciclo for executado usando qualquer processamento baseado em tarefa. Os dados são usados para controlar quando o processamento de ciclo será executado assincronamente e será baseado em tarefas, o que permite processar e criar trabalhos em paralelo.

Os dados padrão usarão inicialmente um valor limite de 15 para o número mínimo de linhas de carregamento (MINIMUMWAVELOADLINES). Isso significa que, quando o sistema processa um ciclo com mais de 15 linhas de cargas , ele usará o processamento de tarefa assíncrona. Você pode inserir ou atualizar manualmente esses dados na tabela **WHSWaveTaskProcessingThresholdParameters** em seus ambientes de teste, mas se precisar alterar essa configuração em um ambiente de produção, precisará contatar o Suporte da Microsoft para solicitar a atualização.

## <a name="work-with-the-feature"></a>Trabalhar com o recurso

Quando a funcionalidade *Agendar criação de trabalho* for habilitada, o processamento em ciclos criará um trabalho planejado, que acabará sendo usado pelo novo processo de criação de trabalho. Durante a criação do trabalho, o trabalho será bloqueado usando o recurso *Bloquear trabalho em toda a organização*.

O fluxograma a seguir mostra como o trabalho planejado é criado durante o processamento em ciclos.

![Agendar criação de trabalho](media/schedule-work-creation-process.png)

### <a name="planned-work"></a>Trabalho planejado

A página **Detalhes do trabalho planejado** (**Gerenciamento de depósito \> Trabalho \> Detalhes do trabalho planejado**) mostra informações sobre o trabalho planejado, que é inicialmente criado durante o processamento em ciclos. Estes são os **Status de progresso** disponíveis:

- **Em fila** - O trabalho planejado está aguardando para ser usado para criar trabalho.
- **Concluído** - O trabalho planejado foi usado para criar trabalho.
- **Falha** - O processamento em ciclos falhou. Observe que o trabalho planejado pode estar em um estado de **Falha** com ou sem trabalho real relacionado. Quando o processo de criação do trabalho real falha, o trabalho real permanece no status *Cancelado*.

### <a name="batch-job-for-the-work-creation-process"></a>Trabalho em lotes para o processo de criação de trabalho

Para exibir os trabalhos em lotes para o processamento em ciclos, selecione **Trabalhos em lotes** no painel de ações na página **Todas as ondas**.

Aqui, você pode exibir todos os detalhes da tarefa em lotes para cada um dos IDs do trabalho em lotes.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]