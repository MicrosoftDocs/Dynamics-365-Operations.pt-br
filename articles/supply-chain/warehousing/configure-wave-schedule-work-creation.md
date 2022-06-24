---
title: Agendar a criação de trabalho durante o ciclo
description: Este artigo descreve como configurar e usar o método de processamento Agendar ciclo de criação de trabalho.
author: Mirzaab
ms.date: 01/14/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSPostMethod, WHSWavePostMethodTaskConfig, WHSWaveTemplateTable, WHSParameters, WHSWaveTableListPage, WHSWorkTableListPage, WHSWorkTable, BatchJobEnhanced, WHSPlannedWorkOrder
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-01-14
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 8b4505d66c37134bc8f672b38d195f4f677df9bc
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8852060"
---
# <a name="schedule-work-creation-during-wave"></a>Agendar a criação de trabalho durante o ciclo

[!include [banner](../../includes/banner.md)]

Use o recurso *Agendar criação de trabalho* como parte do seu processo cíclico para ajudar a aumentar o resultado do processamento em ciclos, fazendo com que o sistema crie o trabalho usando o processamento paralelo.

Quando a funcionalidade estiver habilitada, o trabalho planejado será criado automaticamente, e o sistema eventualmente irá processá-lo para criar o trabalho real. Se o número de linhas de carga de ciclos atingir um limite predeterminado, o sistema criará o trabalho real mais rapidamente, aplicando o processamento paralelo assíncrono.

## <a name="turn-on-the-scheduled-work-creation-features-in-feature-management"></a>Ativar os recursos de criação de trabalho agendado no gerenciamento de recursos

Para usar os recursos descritos neste artigo, eles devem ser ativados para o seu sistema. Use o espaço de trabalho [Gerenciamento de recurso](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para ativar os seguintes recursos na seguinte ordem:

1. **Bloqueio de trabalho em toda a organização** - necessário para a configuração manual e automática da criação de trabalho agendado. (Desde a versão 10.0.21 do Supply Chain Management, este recurso é obrigatório, portanto, é ativado por padrão e não pode ser desativado novamente.)
1. **Agendar criação de trabalho** - necessário para a configuração manual e automática da criação de trabalho agendado.
1. **Método do ciclo "Agendar criação de trabalho" em toda a organização** - necessário para a configuração automática da criação de trabalho agendado. Esse recurso não será necessário se você só usar a configuração manual.

<a name="Auto-enable-schedule-work-creation"></a>

## <a name="automatically-configure-scheduled-work-creation"></a>Configurar automaticamente a criação do trabalho agendado

Se você habilitar o recurso *método do ciclo "Agendar criação de trabalho" em toda a organização* ocorrerá o seguinte automaticamente em seu sistema:

- O método do ciclo *Agendar criação de trabalho* (`WHSScheduleWorkCreationWaveStepMethod`) foi adicionado e configurado para ser executado em paralelo em todas as entidades legais.
- Os modelos de ciclo de todas as entidades legais têm **Tipo de modelo de ciclo** definido como *Remessa* e o **Status do modelo** definido como *Válido* terá o método *Criar trabalho* substituído pelo método *Agendar criação de trabalho*. No entanto, os modelos do ciclo das entidades legais em que o método *Criar trabalho* tem permissão para serem repetidos não serão modificados.
- As configurações de tarefas para o método *Agendar criação de trabalho* serão criadas para todos os depósitos de todas as entidades legais que têm **Usar processos de gerenciamento de depósito** habilitados. Isso significa que o método *Agendar criação de trabalho* agora será executado em paralelo, por padrão. Os depósitos existentes para os quais você altera **Usar processos de gerenciamento de depósito** de *Não* para *Sim* também executarão esse método em paralelo por padrão.
- Todas as entidades legais processarão ciclos em lotes e a opção **Esperar por bloqueio (ms)** será definida como um valor padrão *60.000* ms, se tiver sido definida anteriormente como *0* ms.
- Todos os novos modelos de ciclo que você criar terão o método de ciclo *Agendar criação de trabalho*, em vez do método *Criar Trabalho*.

As configurações de processamento de tarefas e de ciclo existentes também serão mantidas para todas as entidades legais que já foram configuradas para processar ciclos em lotes e para todos os depósitos que já tenham sido configurados para usar o método *Agendar criação de trabalho* em paralelo.

Se necessário, você pode reverter manualmente qualquer uma ou todas as configurações feitas automaticamente ao habilitar o recurso *Método do ciclo de Agendar criação de trabalho de toda a organização*, fazendo o seguinte:

- Para modelos de ciclo, Acesse **Gerenciamento de depósito \> Configuração \> Ciclos \> Modelos do ciclo**. Substitua o método *Agendar criação de trabalho* por *Criar trabalho*.
- Para parâmetros de depósito, acesse **Gerenciamento de depósito \> Configuração \> Parâmetros de gerenciamento de depósito**. Na guia **Processamento do ciclo**, aplique os valores preferidos para **Processar ciclos em lotes** e **Aguardar bloqueio (ms)**.
- Para métodos de ciclo, Acesse **Gerenciamento de depósito \> Configuração \> Ciclos \> Métodos de processo do ciclo**. Selecione `WHSScheduleWorkCreationWaveStepMethod` e no Painel de Ação, selecione **Configuração da tarefa**. Modifique ou exclua o número de tarefas em lotes e o grupo de ciclos atribuído a cada depósito listado, conforme necessário.

## <a name="manually-configure-scheduled-work-creation"></a>Configurar manualmente a criação do trabalho agendado

Se você não tiver habilitado o [*recurso de método do ciclo "Agendar criação de trabalho" em toda a organização*](#Auto-enable-schedule-work-creation), poderá usar os procedimentos fornecidos nesta seção para configurar manualmente a criação de trabalho agendado, conforme necessário.

### <a name="manually-enable-batch-processing-of-waves"></a>Habilitar o processamento manualmente em lotes de ciclos

Para aproveitar um método assíncrono paralelo para criar trabalho de depósito, o processo de ciclos deve estar sendo executado em lotes. Para fazer essa configuração:

1. Acesse **Gerenciamento de depósito \> Configuração \> Parâmetros de gerenciamento de depósito**.
1. Na guia **Geral**, defina a opção **Processar ciclos em lote** como *Sim*. Se preferir, você também pode selecionar um **Grupo de lotes de processamento em ciclos** dedicado para impedir que o processamento de fila em lotes seja executado ao mesmo tempo que outros processos.
1. Defina o **Tempo de espera para o bloqueio (ms)**, que se aplica quando o sistema está processando vários ciclos ao mesmo tempo. Para a maioria dos processos em ciclos maiores, recomendamos um valor de *60.000*.

### <a name="manually-enable-the-new-wave-step-method-for-existing-wave-templates"></a>Habilitar manualmente o novo método de etapa de ciclo para modelos de ciclo existentes

Comece criando o novo método de etapa de ciclo e habilite-o para o processamento de tarefas assíncronas paralelas.

1. Acesse **Gerenciamento de depósito \> Configuração \> Ondas \> Métodos de processo de onda**.
1. Selecione **Gerar método novamente** e observe que *WHSScheduleWorkCreationWaveStepMethod* foi adicionado à lista de métodos de processo de ciclo que podem ser usados nos modelos de ciclo de remessa.
1. Selecione o registro com o **Nome do método** *WHSScheduleWorkCreationWaveStepMethod* e selecione **Configuração de tarefas**.
1. Para adicionar uma nova linha à grade, selecione **Novo** no Painel de Ações e use as seguintes configurações:

    - **Depósito** - Selecione o depósito que será usado para agendar o processamento de criação de trabalho.
    - **Número máximo de tarefas em lotes** - Especifique um número máximo de tarefas em lotes. Na maioria dos casos, esse valor deve estar no intervalo de 8-16, mas recomendamos que você experimente a configuração ideal com base nos seus cenários.
    - **Grupo de lotes de processamento em ciclos** - Selecione um grupo de lotes de processamento em ciclos dedicados para otimizar o processamento da fila de lotes.

Agora, você está pronto para atualizar um modelo de ciclo existente (ou criar um novo) para usar o método de processamento em ciclos *Agendar criação de trabalho*.

1. Acesse **Gerenciamento de depósito \> Configuração \> Ondas \> Modelos de onda**.
1. Selecione **Editar** no Painel de Ações.
1. No painel de lista, selecione o modelo de ciclo que deseja atualizar (se você estiver testando com dados de demonstração, poderá usar *24 Padrão de remessa*).
1. Expanda a guia rápida **Métodos** e selecione a linha com o **Nome** *Agendar criação de trabalho* na grade **Métodos restantes**.
1. Selecione a seta apontando para a coluna **Métodos selecionados** para mover a linha selecionada para essa coluna. (Você só pode ter um método selecionado de cada vez que use o `WHSScheduleWorkCreationWaveStepMethod` ou `createWork`, de forma que a linha existente com o **Nome do método** `createWork` seja movida automaticamente para a grade **Métodos restantes**.)

## <a name="set-wave-task-processing-threshold-data"></a>Definir dados do limite de processamento de tarefa de ciclo

O sistema criará dados padrão de limite de processamento de tarefa de ciclo na primeira vez que um processo de ciclo for executado usando qualquer processamento baseado em tarefa. Os dados são usados para controlar quando o processamento de ciclo será executado assincronamente e será baseado em tarefas, o que permite processar e criar trabalhos em paralelo.

Os dados padrão usarão inicialmente um valor limite de 15 para o número mínimo de linhas de carregamento (`MINIMUMWAVELOADLINES`). Isso significa que, quando o sistema processa um ciclo com mais de 15 linhas de cargas , ele usará o processamento de tarefa assíncrona. Você pode inserir/atualizar manualmente esses dados na tabela `WHSWaveTaskProcessingThresholdParameters` em seus ambientes de teste. Se você precisar alterar esta configuração em um ambiente de produção, deverá contatar o Suporte da Microsoft para solicitar a atualização.

## <a name="work-with-the-scheduled-work-creation"></a>Trabalhar com a criação de trabalho agendado

Para obter detalhes sobre como trabalhar com a criação de trabalho agendado, consulte [Criação e processamento de ciclo](wave-processing.md). 


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
