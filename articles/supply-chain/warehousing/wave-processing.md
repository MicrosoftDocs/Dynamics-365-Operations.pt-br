---
title: Criação e processamento de ciclo
description: Este tópico descreve como criar, processar, e liberar manualmente um ciclo para criar o trabalho de separação para uma carga, remessa, ordem de produção ou ordem kanban.
author: Mirzaab
ms.date: 03/08/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSWaveTemplateTable, WHSParameters, whswavetablecreatenew, WHSWaveTable, WHSWaveAttributes, WHSKanbanWaveTable, WHSWaveTableListPage, WHSKanbanWaveTableListPage, WHSProdWaveTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-03-08
ms.dyn365.ops.version: Release 10.0.18
ms.openlocfilehash: 76b11eaec0f22393e877c2837e2533a176018f2b
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/06/2021
ms.locfileid: "6355473"
---
# <a name="wave-creation-and-processing"></a>Criação e processamento de ciclo

[!include [banner](../includes/banner.md)]

Este tópico descreve como criar, processar, e liberar manualmente um ciclo para criar o trabalho de separação para uma carga, remessa, ordem de produção ou ordem kanban. É possível criar ciclos para os seguintes tipos de ordens:

- **Ordens de venda** – use ciclos de remessa para incluir as linhas das ordens de venda. Quando uma ordem de venda é liberada para o depósito, as linhas da ordem de venda podem ser incluídas no ciclo.
- **Ordens de produção** – use ondas de produção para incluir as linhas da BOM (lista de materiais) do produto.
- **Ordens kanban** – Aos ciclos kanban incluem as linhas da lista de separação das ordens kanban.

Para ordens de venda e ordens de kanban, o estoque será reservado antes de a ordem ser liberada para o depósito. Caso contrário, os itens ou as linhas de alocação não poderão ser processadas em um ciclo. Entretanto, as ordens de produção são ligeiramente mais flexíveis. Para ordens de produção, você pode escolher uma das seguintes opções:

- Exija que todo o material seja reservado antes que uma ordem possa ser liberada para o depósito.
- Permita que ordens de produção sejam liberadas para o depósito mesmo que nem todo o material possa ser reservado. Se você selecionar esta opção, repita manualmente a liberação para o processo de armazém quando o material adicional for disponibilizado. Por exemplo, isso será útil se você tiver o material necessário para iniciar uma produção, e puder aguardar até que o material adicional seja disponibilizado.

Você pode especificar quais dessas opções de ordem de produção devem ser usadas por padrão usando o campo **Necessidade de reserva de material** na página **Parâmetros do controle de produção**. No entanto, você poderá alterar a configuração de cada ordem de produção específica conforme o necessário. Para obter mais informações, consulte [Parâmetros de depósito para processamento do ciclo](wave-warehouse-parameters.md).

## <a name="create-and-process-a-wave"></a>Criar e processar um ciclo

O diagrama a seguir mostra o fluxo de como os ciclos de remessa são criados, processados e liberados. Os números correspondem às seções posteriormente nesta seção.

![Processo para a criação de um ciclo.](media/wave-processing-diagram.png "Processo para a criação de um ciclo")

### <a name="prerequisites"></a>Pré-requisitos

Antes de começar, um modelo de ciclo deverá estar disponível para o tipo de ciclo que você deseja criar (remessa, produção ou kanban). O modelo de ciclo estabelece várias configurações de como o ciclo será gerado e processado, incluindo quais etapas devem ser concluídas de forma manual e quais são concluídas automaticamente. Para obter mais informações, consulte [Modelos de ciclo](wave-templates.md).

### <a name="create-a-wave"></a>Criar uma onda

#### <a name="automatically-create-waves-based-on-warehouse-and-order-type"></a>Criar ciclos automaticamente com base no depósito e no tipo de ordem

Para criar ciclos automaticamente, configure os [Modelos de ciclo](wave-templates.md) que se aplicam a cada tipo de ordem e depósito relevantes. Certifique-se de que cada modelo tenha a opção **Automatizar criação de ciclo** definida como *Sim*.

#### <a name="manually-create-waves"></a>Criar ciclos manualmente

Para criar manualmente um ciclo, siga estas etapas:

1. Verifique se os [Modelos de ciclo](wave-templates.md) relevantes não foram definidos para criar automaticamente um ciclo para os tipos de depósito e ordem em que você deseja fazer isso manualmente.
1. Dependendo do tipo de ciclo a ser criado, siga um destes procedimentos:

    - Vá para **Gerenciamento de depósito** \> **Comum** \> **Ciclos** \> **Ciclos de remessa** \> **Todos os ciclos**. No Painel de Ações, selecione **Ciclo**.
    - Vá para **Gerenciamento de depósito** \> **Comum** \> **Ciclos** \> **Ciclos de produção** \> **Todos os ciclos de produção**. No Painel de Ações, selecione **Ciclo de produção**.
    - Vá para **Gerenciamento de depósito** \> **Comum** \> **Ciclos** \> **Ciclos de kanban** \> **Todos os ciclos de kanban**. No Painel de Ações, selecione **Criar ciclo**.

1. No campo **Descrição**, insira uma curta descrição do ciclo. Isso deve indicar o que você está processando no ciclo.

1. No campo **Nome do modelo de ciclo**, selecione o modelo de ciclo para o tipo de ciclo a ser criado. O modelo de ciclo contém os métodos de ciclo que executarão ações, como a criação de um trabalho para o ciclo. Por exemplo, o modelo de ciclo para o envio de ciclos pode conter os métodos para a criação de cargas, alocação de linhas aos ciclos, reabastecimento e a criação de trabalho de separação para o ciclo.

1. Se você desejar usar os atributos do ciclo como critérios adicionais de consulta para o ciclo, selecione os atributos nos campos **Atributos do ciclo**.

### <a name="specify-what-to-include-in-a-wave"></a>Especificar o que incluir em um ciclo

Depois que um ciclo tiver sido criado, você estará pronto para começar a adicionar conteúdo a ele.

> [!NOTE]
> Se necessário, você poderá adicionar linhas a um ciclo mesmo depois que ele tiver sido processado, desde que não tenha sido liberado.

#### <a name="automatically-specify-what-to-include-in-a-wave"></a>Especificar automaticamente o que incluir em um ciclo

Para criar ciclos automaticamente, configure os [Modelos de ciclo](wave-templates.md) que se aplicam a cada tipo de ordem e depósito relevantes. Certifique-se de que cada modelo tenha a opção **Automatizar criação de ciclo** definida como *Sim*. Como alternativa, o modelo pode atribuir linhas automaticamente a qualquer ciclo aberto qualificado se a opção **Atribuir a ciclos abertos** estiver definida como *Sim*.

#### <a name="manually-specify-what-to-include-in-a-wave"></a>Especificar manualmente o que incluir em um ciclo

Quando um ciclo for criado , mas ainda não liberado, você poderá especificar manualmente o que incluir nele. Para adicionar linhas a um ciclo manualmente:

1. Dependendo do tipo de ciclo ao qual adicionar linhas, siga um destes procedimentos:

    - Vá para **Gerenciamento de depósito** \> **Comum** \> **Ciclos** \> **Ciclos de remessa** \> **Todos os ciclos**. No Painel de Ações, selecione **Ciclo**.
    - Vá para **Gerenciamento de depósito** \> **Comum** \> **Ciclos** \> **Ciclos de produção** \> **Todos os ciclos de produção**. No Painel de Ações, selecione **Ciclo de produção**.
    - Vá para **Gerenciamento de depósito** \> **Comum** \> **Ciclos** \> **Ciclos de kanban** \> **Todos os ciclos de kanban**. No Painel de Ações, selecione **Criar ciclo**.

1. Selecione o ciclo. No Painel de Ações, selecione uma destas opções:

      - **Manter remessas**
      - **Manter produções**
      - **Manter listas de separação de trabalhos kanban**

1. Na parte superior da janela, selecione a linha para adicionar ao ciclo e, em seguida, selecione **Adicionar ao ciclo**. A linha é movida para a Guia Rápida **Linhas do ciclo**.

    Repita esta etapa para cada linha a ser adicionada. Para adicionar todas as linhas, selecione **Adicionar tudo**.

    > [!TIP]
    > Para os ciclos de remessa, você pode encontrar rapidamente uma ordem específica selecionando um filtro personalizado no campo **Código de filtro de ciclo**. Os códigos de filtro de ciclo contêm os critérios de consulta para as remessas que são criadas no formulário **Filtros de ciclo**. Este campo não está disponível para ondas de produção ou ondas de kanban.
    > Uma marca de verificação verde na coluna **No ciclo** indica que a remessa foi adicionada ao ciclo.

### <a name="process-the-wave-to-create-the-picking-work"></a>Processar o ciclo para criar o trabalho de separação

Depois que um ciclo tiver sido criado e contiver todas as linhas necessárias, você estará pronto para processá-lo para criar o trabalho de separação correspondente.

#### <a name="automatically-process-a-wave"></a>Processar automaticamente um ciclo

Para processar automaticamente um ciclo, configure os [Modelos de ciclo](wave-templates.md) relevantes com as opções de processamento automático necessárias.

#### <a name="manually-process-a-wave"></a>Processar manualmente um ciclo

Você só poderá processar um ciclo quando o **Status do ciclo** for *Criado*. Depois que você processar um ciclo, o **Status do ciclo** será alterado para *Retido*.

Para processar manualmente um ciclo com todo o conteúdo necessário, siga estas etapas:

1. Dependendo do tipo de ciclo a ser processado, siga um destes procedimentos:

    - Selecione **Gerenciamento de depósito** \> **Comum** \> **Ciclos** \> **Ciclos de remessa** \> **Todos os ciclos**. No Painel de Ações, selecione **Ciclo**.
    - Selecione **Gerenciamento de depósito** \> **Comum** \> **Ciclos** \> **Ciclos de produção** \> **Todos os ciclos de produção**. No Painel de Ações, selecione **Ciclo de produção**.
    - Selecione **Gerenciamento de depósito** \> **Comum** \> **Ciclos** \> **Ciclos de kanban** \> **Todos os ciclos de kanban**. No Painel de Ações, selecione **Criar ciclo**.

1. Selecione o ciclo a ser processado. No Painel de Ação, selecione **Processo**.

### <a name="release-the-wave-to-the-warehouse-to-start-picking-and-packing"></a>Liberar o ciclo para o depósito para iniciar a separação e a embalagem

Você deve processar um ciclo antes de poder liberá-lo. Ao liberar o ciclo, o trabalho de separação estará disponível no depósito. Você pode cancelar um ciclo depois de liberado e adicionar mais linhas, mas não poderá alterar as linhas.

#### <a name="automatically-release-a-wave"></a>Liberar automaticamente um ciclo

Para processar automaticamente um ciclo, configure os [Modelos de ciclo](wave-templates.md) relevantes com as opções de processamento automático necessárias.

#### <a name="manually-release-a-wave"></a>Liberar manualmente um ciclo

Para liberar um ciclo manualmente, siga estas etapas:

1. Dependendo do tipo de ciclo a ser liberado, siga um destes procedimentos:

      - Selecione **Gerenciamento de depósito** \> **Comum** \> **Ciclos** \> **Ciclos de remessa** \> **Todos os ciclos**. No Painel de Ações, selecione **Ciclo**.
      - Selecione **Gerenciamento de depósito** \> **Comum** \> **Ciclos** \> **Ciclos de produção** \> **Todos os ciclos de produção**. No Painel de Ações, selecione **Ciclo de produção**.
      - Selecione **Gerenciamento de depósito** \> **Comum** \> **Ciclos** \> **Ciclos de kanban** \> **Todos os ciclos de kanban**. No Painel de Ações, selecione **Criar ciclo**.

1. Selecione o ciclo a ser liberado. No Painel de Ações, selecione **Liberar ciclo**.

## <a name="containerize-a-wave"></a>Transportar em contêineres um ciclo

O transporte em contêineres automatizado cria contêineres e o trabalho de separação para remessas quando um ciclo é processado. Para obter detalhes sobre como configurá-lo, consulte [Transporte em contêineres](wave-containerization.md).

## <a name="work-with-the-scheduled-work-creation"></a>Trabalhar com a criação de trabalho agendado

Quando a funcionalidade *Agendar criação de trabalho* for habilitada, o processamento em ciclos criará um trabalho planejado, que acabará sendo usado pelo novo processo de criação de trabalho. Durante a criação do trabalho, o trabalho será bloqueado usando o recurso *Bloquear trabalho em toda a organização*. Para obter mais informações, consulte [Agendar a criação de trabalhos durante o ciclo](configure-wave-schedule-work-creation.md).

O fluxograma a seguir mostra como o trabalho planejado é criado durante o processamento em ciclos.

![Agendar criação de trabalho.](media/schedule-work-creation-process.png)

### <a name="planned-work"></a>Trabalho planejado

A página **Detalhes do trabalho planejado** (**Gerenciamento de depósito \> Trabalho \> Detalhes do trabalho planejado**) mostra informações sobre o trabalho planejado, que é inicialmente criado durante o processamento em ciclos. Estes são os **Status de progresso** disponíveis:

- **Em fila** - O trabalho planejado está aguardando para ser usado para criar trabalho.
- **Concluído** - O trabalho planejado foi usado para criar trabalho.
- **Falha** - O processamento em ciclos falhou. Observe que o trabalho planejado pode estar em um estado de **Falha** com ou sem trabalho real relacionado. Quando o processo de criação do trabalho real falha, o trabalho real permanece no status *Cancelado*.

### <a name="batch-job-for-the-work-creation-process"></a>Trabalho em lotes para o processo de criação de trabalho

Para exibir os trabalhos em lotes para o processamento em ciclos, selecione **Trabalhos em lotes** no painel de ações na página **Todas as ondas**.

Aqui, você pode exibir todos os detalhes da tarefa em lotes para cada um dos IDs do trabalho em lotes.

## <a name="cancel-a-wave"></a>Cancelar um ciclo

Se necessário, você pode cancelar um ciclo que foi processado. Para cancelar um ciclo e o trabalho de separação que foi criado, siga estas etapas:

1. Dependendo do tipo de ciclo a ser cancelado, siga um destes procedimentos:

      - Vá para **Gerenciamento de depósito** \> **Comum** \> **Ciclos** \> **Ciclos de remessa** \> **Todos os ciclos**.
      - Vá para **Gerenciamento de depósito** \> **Comum** \> **Ciclos** \> **Ciclos de produção** \> **Todos os ciclos de produção**.
      - Vá para **Gerenciamento de depósito** \> **Comum** \> **Ciclos** \> **Ciclos de kanban** \> **Todos os ciclos de kanban**.

1. Selecione o ciclo a ser cancelado. No Painel de Ações, na guia **Trabalho**, selecione **Cancelar**.

## <a name="review-wave-batch-job-details"></a>Revisar detalhes do trabalho em lotes do ciclo

Use a página **Detalhes do trabalho em lotes do ciclo** para inspecionar os trabalhos em lotes e as tarefas relacionadas a qualquer ciclo. Isso é especialmente útil para solucionar problemas de um ciclo que falhou. Sem esse recurso, somente administradores normalmente terão acesso aos detalhes do trabalho em lotes. A página **Detalhes do trabalho em lotes do ciclo** pode ser disponibilizada para usuários não administradores e fornece uma exibição somente leitura de trabalhos em lotes e tarefas relacionadas.

### <a name="enable-the-wave-batch-job-details-page"></a>Habilitar a página Detalhes do trabalho em lotes do ciclo

Se o sistema ainda não incluir a página **Detalhes do trabalho em lotes do ciclo**, vá para [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) e ative o recurso *Detalhes do trabalho em lotes do ciclo*.

### <a name="use-the-wave-batch-job-details-page"></a>Usar a página Detalhes do trabalho em lotes do ciclo

A página **Detalhes do trabalho em lotes do ciclo** combina trabalhos em lotes e tarefas de trabalho em lotes, o que permite investigar todas as etapas do ciclo sem a necessidade de navegar para frente e para trás entre um único trabalho em lotes e a lista de tarefas em lotes. A página também fornece acesso ao log de lotes e, se você tiver as permissões necessárias, fornece um link para a página **Trabalhos em lotes**.

Para abrir esta página, selecione um ciclo em qualquer uma das várias páginas de ciclo diferentes e selecione **Detalhes do trabalho em lotes do ciclo** no Painel de Ações.

## <a name="review-load-validation-and-error-messages"></a>Revisar a validação de carga e as mensagens de erro

Durante o processamento do ciclo, o sistema valida e exibe o status de cada linha de carga no ciclo. Se nenhum aviso ocorrer, ele prosseguirá para a próxima etapa do ciclo. Se os avisos ocorrerem, em vez disso, ele mostrará o seguinte erro após a conclusão da validação de todo o ciclo:

> Encontradas linhas de carga inválidas no ciclo. Remova as linhas de carga inválidas.

Em seguida, você poderá revisar o status final de cada linha de carga no ciclo e corrija todos os avisos antes de tentar novamente. Isso permite que você trate de todos os avisos de uma só vez antes de reprocessar o ciclo. (Nas versões anteriores, o sistema parece de processar o ciclo após o primeiro aviso e, portanto, você só podia corrigir avisos um de cada vez).

A maneira como o sistema exibe as mensagens de status do processamento do ciclo depende de como você definiu a opção **Criar log de histórico de processamento do ciclo** na página **Parâmetros de gerenciamento de depósito**.

- Quando **Criar log de histórico de processamento do ciclo** estiver definido como *Não*, as mensagens de status de linha de carga serão mostradas no **Log de Informações**.
- Quando **Criar log de histórico de processamento do ciclo** estiver definido como *Sim*, as mensagens de status de linha de carga serão mostradas na página **Log de histórico de procedimento do ciclo**. Para exibir o log, vá para **Gerenciamento de depósito \> Ciclos de saída \> Log de histórico de processamento do ciclo**.

## <a name="additional-resources"></a>Recursos adicionais

- [Exemplo de Configuração de processamento de ciclo](tasks/configure-wave-processing.md)
- [Modelos de onda](wave-templates.md)
- [Transporte em contêineres](wave-containerization.md)