---
title: Liberar para o depósito
description: Este artigo fornece detalhes sobre o processo de liberação para o depósito. Descreve entidades criadas quando você libera uma ordem para o depósito e as opções que podem ser usadas para iniciar o processo.
author: Mirzaab
ms.date: 8/13/2021
ms.topic: article
ms.search.form: WHSReleaseToWarehouse, WHSReleaseToWarehouseSalesOrder, WHSReleaseToWarehouseTransferOrder, WHSLoadPlanningWorkbench, WHSWaveTemplateTable, WHSWorkTemplateTable, WHSLocDirTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-08-13
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: caa38c4ed1c7fb8cf1ead3ba6534f8405a5ff57f
ms.sourcegitcommit: 3d7ae22401b376d2899840b561575e8d5c55658c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/08/2022
ms.locfileid: "9428027"
---
# <a name="release-to-warehouse"></a>Liberar para o depósito

[!include [banner](../../includes/banner.md)]

Este artigo fornece detalhes sobre o processo de liberação para o depósito. Descreve entidades criadas quando você libera uma ordem para o depósito e as opções que podem ser usadas para iniciar o processo.

## <a name="release-to-warehouse-overview"></a>Visão geral da liberação para o depósito

A liberação para o depósito é o processo de preparar o estoque para o processamento de expedição. Quando você libera uma ordem para o depósito, o sistema cria linhas de carregamento e remessas. Se o processamento automático de ciclo for configurado, as cargas e os trabalhos necessários também serão criados. A configuração das entidades envolvidas depende das configurações do sistema. Esta seção do artigo revisa as entidades criadas durante o processo de liberação para o depósito e as configurações do sistema que as definem.

Uma *remessa* é um grupo de ordens de venda ou linhas de ordem de transferência para o mesmo cliente ou o mesmo endereço de entrega.

Uma *carga* é um grupo de ordens de venda ou linhas de ordem de transferência que são agrupadas em um único caminhão, vagão ou outro modo de transporte. Uma carga pode ter uma ou várias remessas. Você pode criar manualmente uma carga adicionando linhas de ordem a uma nova carga. Nesse caso, as linhas de ordem são atribuídas à carga antes que o processo de liberação para o depósito seja iniciado e só podem ser liberadas na página **Bancada de planejamento de carga**.

Um *trabalho* de depósito é qualquer operação de depósito executada por um trabalhador de depósito. Normalmente, as operações de trabalho de depósito consistem em pelo menos duas ações consecutivas: um trabalhador do depósito coleta o estoque disponível em um local e o descarrega em outro local.

Quando ordens são liberadas para o depósito, o sistema cria *linhas de carregamento* e as agrupa em remessas. O processo de consolidação de remessa permite a consolidação automatizada de remessa durante o processo de liberação para o depósito. Para obter mais informações, consulte [Visão geral das políticas de consolidação de remessa](about-shipment-consolidation-policies.md).

O sistema usa *ciclos* para criar um trabalho de separação e cargas para remessa. Um *modelo do ciclo* deve estar disponível para o tipo de ciclo que você deseja criar e para o depósito da linha de ordem. Modelos do ciclo do tipo *Remessa* são usados para enviar itens para ordens de venda e ordens de transferência.

Cada modelo do ciclo contém *métodos de ciclo*. Os métodos de ciclo executam ações como criar um trabalho para o ciclo ou criar cargas. Por exemplo, um modelo do ciclo para o envio de ciclos pode conter os métodos de criação de cargas, alocação de linhas aos ciclos, reabastecimento e criação de trabalhos de separação para o ciclo. O modelo do ciclo estabelece configurações que definem como o ciclo será gerado e processado, quais etapas deverão ser concluídas de forma manual e quais etapas serão concluídas automaticamente. Para obter mais informações, consulte [Modelos de ciclo](wave-templates.md). Portanto, dependendo da configuração do modelo do ciclo, um ciclo é criado, processado e liberado automaticamente quando você libera uma ordem para o depósito, ou algumas ou todas as ações são executadas manualmente após a conclusão da liberação para o depósito.

Quando um ciclo é processado, o sistema cria um trabalho de separação, com base em uma *diretiva de localização* e um *modelo de trabalho*, e disponibiliza esse trabalho em dispositivos móveis. O modelo de trabalho determina como o trabalho é executado para cada processo de depósito, e a diretiva de localização especifica os locais de separação e armazenamento para o movimento do estoque. Para obter mais informações, consulte [Controlar o trabalho do depósito por meio de modelos de trabalho e diretivas de localização](control-warehouse-location-directives.md).

> [!NOTE]
> Por padrão, os ciclos são processados no modo de lote.

Durante o processamento de ondas, o sistema normalmente cria uma nova carga para cada remessa para a qual não há uma carga atribuída. Se desejar que o sistema atribua remessas não atribuídas a cargas existentes, você poderá usar a funcionalidade avançada de criação de carga de ciclo. Para obter mais informações, consulte [Criação de carga avançada durante um ciclo](advanced-load-building-during-wave.md).

Nas páginas **Ordens de venda** e **Ordens de transferência**, você pode revisar as entidades criadas para linhas de ordem durante o processo de liberação para o depósito.

- Página **Ordens de venda**:

    - Na Guia Rápida **Linhas de ordem de venda**, selecione **Depósito** e, no menu, selecione **Detalhes de remessa** para abrir remessas relacionadas, **Detalhes da carga** para abrir cargas relacionadas ou **Detalhes do trabalho** para abrir detalhes relacionados ao trabalho.
    - Na Guia Rápida **Detalhes da linha**, selecione a guia **Carga** para revisar as cargas relacionadas.

- Página **Ordens de transferência**:

    - No Painel de Ações, na guia **Remessa**, selecione **Detalhes da remessa** para abrir remessas relacionadas ou **Detalhes da carga** para abrir cargas relacionadas.
    - Na Guia Rápida **Linhas de ordem de transferência**, selecione **Detalhes do trabalho** para abrir detalhes do trabalho relacionado.

Concluindo, quando uma ordem é liberada para o depósito, o fluxo mais automatizado funciona da seguinte maneira:

1. O sistema cria uma remessa para a ordem e um ciclo.
1. O ciclo é processado.
1. O sistema cria uma ID de trabalho e carga.

Dependendo das configurações de modelos de ciclo, modelos de trabalho e diretivas de locais, algumas etapas desse fluxo podem se tornar manuais. No entanto, o fluxo geral permanece o mesmo.

Há várias opções de como você libera uma ordem para o depósito. Você pode executar a operação manualmente ou configurar um trabalho em lotes. As seções restantes deste artigo revisam detalhadamente as várias maneiras de executar uma operação de liberação para o depósito.

## <a name="manual-release-to-the-warehouse-from-the-sales-orders-and-transfer-orders-pages"></a>Liberação manual para o depósito nas páginas Ordens de venda e Ordens de transferência

Você pode liberar uma ordem para o depósito diretamente na página **Ordens de venda** ou **Ordens de transferência**, selecionando **Liberar para o depósito**.

- Na página **Ordens de venda**, o botão está na guia **Depósito** do Painel de Ações.
- Na página **Ordens de transferência**, o botão está na guia **Remessa** do Painel de Ações.

Na página **Ordens de venda**, você pode liberar várias ordens de venda simultaneamente.

## <a name="manual-release-to-the-warehouse-from-the-release-to-warehouse-pages"></a>Liberação manual para o depósito nas páginas Liberar para o depósito

No momento, o sistema fornece três páginas nas quais é possível revisar linhas de várias ordens e liberá-las para o depósito:

- **Liberar para o depósito** (**Gerenciamento de depósito \> Liberação para o depósito \> Liberar para o depósito**) – esta página permite trabalhar com ordens de venda e ordens de transferência. No entanto, ela oferece um desempenho mais lento do que as outras duas páginas. Essa página será preterida em breve.
- **Liberar ordens de venda para o depósito** (**Gerenciamento de depósito \> Liberação para o depósito \> Liberar ordens de venda para o depósito**) – Esta página permite trabalhar somente com ordens de venda. No entanto, ela oferece melhor desempenho do que a página **Liberar para o depósito**.
- **Liberar ordens de transferência para o depósito** (**Gerenciamento de depósito \> Liberação para o depósito \> Liberar ordens de transferência para o depósito**) – Esta página permite trabalhar somente com ordens de transferência. No entanto, ela oferece melhor desempenho do que a página **Liberar para o depósito**.

Todas as três páginas fornecem uma funcionalidade semelhante, conforme descrito no restante desta seção. Todas elas permitem selecionar linhas de ordem ou ordens inteiras e, em seguida, liberá-las para o depósito.

Cada uma das páginas consiste em uma seção superior, na qual você pode selecionar linhas de ordem, e uma seção inferior, na qual é possível iniciar o processo de liberação para o depósito. Você pode usar filtros na seção superior para pesquisar as linhas de ordem de venda que deseja liberar. A página **Liberar para o depósito** fornece uma guia separada para ordens de venda e ordens de transferência na seção superior, enquanto cada uma das outras duas páginas exibe apenas um tipo de ordem.

A barra de ferramentas na seção superior inclui os botões a seguir, que você pode usar para selecionar linhas da ordem a serem liberadas para o depósito:

- **Adicionar** – Selecione uma ou mais linhas da ordem na seção superior e selecione este botão para as linhas na seção inferior.
- **Adicionar tudo** – Adiciona todas as linhas da seção superior à seção inferior.
- **Adicionar ordem** – Selecione uma ordem e este botão para adicionar todas as linhas da ordem à seção inferior.

Depois de concluir a adição de linhas à seção inferior, marque cada linha que deseja liberar. Depois disso, selecione **Liberar para o depósito** na barra de ferramentas para liberar essas linhas para o depósito.

## <a name="manual-release-to-the-warehouse-from-the-load-planning-workbench-page"></a>Liberação manual para o depósito na página Bancada do planejamento de carga

Você também pode liberar manualmente as ordens para o depósito usando a página **Bancada de planejamento de carga**. Essa página permite organizar as linhas da ordem em cargas e liberar essas cargas para o depósito.

Para abrir a página **Bancada de planejamento de carga**, acesse **Gerenciamento de depósito \> Cargas**. Você também pode abri-la nas páginas **Ordens de venda** e **Ordens de transferência**. Na seção superior da página, você pode selecionar as linhas de ordem de venda na guia **Linhas de venda** e as linhas de ordem de transferência na guia **Linhas de transferência** e adicionar essas linhas a uma carga nova ou existente.

A guia **Oferta e demanda** no Painel de Ações inclui os botões a seguir que podem ser usados para adicionar linhas de ordem na seção superior a uma carga:

- **Para nova carga** – Selecione uma ou mais linhas da ordem na seção superior e selecione este botão para criar uma nova carga e adicionar essas linhas a ela.
- **Para carga existente** – Selecione uma ou mais linhas da ordem na seção superior e selecione este botão para criar uma nova carga e adicionar essas linhas a uma carga existente.
- **Ordem inteira para nova carga** – Selecione ordens e este botão para criar uma nova carga e adicionar todas as linhas dessas ordens a ela.
- **Ordem inteira para carga existente** – Selecione uma ordem e este botão para adicionar todas as linhas dessa ordem a uma carga existente.

Na seção inferior, você pode revisar as cargas criadas. Para liberar cargas para o depósito, selecione-as e selecione **Liberar \> Liberação para o depósito** na barra de ferramentas. Se você estiver usando o processamento automático de ciclo, porque as cargas já estão atribuídas a linhas de ordem, o sistema criará remessas e IDs de trabalho quando a operação de liberação para o depósito for executada.

## <a name="automatic-release-to-the-warehouse"></a>Liberação automática para o depósito

Para liberar automaticamente as ordens para o depósito, use os trabalhos **Liberação automática de ordens de venda** e **Liberação automática de ordens de transferência**.

Para configurar o trabalho em lotes que libera ordens de venda, siga estas etapas.

1. Acesse **Gerenciamento de depósito \> Liberar para depósito \> Liberação automática de ordens de venda**.
1. Na caixa de diálogo **Liberação automática de ordens de venda**, na Guia Rápida **Parâmetros**, defina os campos a seguir:

    - **Quantidade a ser liberada** – Selecione se toda a quantidade ou somente a quantidade fisicamente reservada deve ser liberada para o depósito.
    - **Permitir a liberação de ordens parcialmente liberadas** – Especifique se as quantidades restantes para ordens parcialmente liberadas devem ser liberadas para o depósito.
    - **Manter reservas em caso de falha na liberação** – Especifique se as quantidades reservadas automaticamente para uma ordem de venda devem permanecer reservadas se o processo de liberação para o depósito falhar.
    - **Liberações de grupo por cliente** – especifique se o sistema deve processar operações de liberação para o depósito separadamente para cada cliente ou liberar todas as ordens de venda ao mesmo tempo. Quando esta opção estiver definida como *Sim*, o sistema coletará todas as linhas da ordem de venda para um cliente selecionado, liberará essas ordens para o depósito e processará o próximo cliente. Quando esta opção estiver definida como *Não*, o sistema liberará todas as linhas da ordem de venda disponíveis em uma única liberação para a operação de depósito. Ao habilitar esta opção, você pode ajudar a aprimorar o desempenho e a resiliência do processo de liberação para o depósito. No entanto, você deve ter cuidado ao usar essa opção junto com os modelos de ciclo que estão configurados como processar ciclo na liberação para o depósito porque essa combinação deve gerar muitos ciclos de único cliente, cada um com trabalho gerado somente para esse cliente. Se você deseja gerar um trabalho que combine remessas para vários clientes, desative a opção *Liberações de grupo por cliente* ou configure os modelos de ciclo para usar o processamento adiado.
    - **Tratamento de ordens bloqueadas** – Selecione como o sistema deve tratar ordens de venda que estão bloqueadas no momento porque estão sendo editadas por outros usuários ou processos:

        - *Aguardar o desbloqueio de ordens* – O sistema deve esperar que as ordens sejam desbloqueadas antes de serem liberadas para o depósito. Nesse caso, o processo de liberação para o depósito pode demorar mais tempo.
        - *Ignorar ordens bloqueadas* – O sistema deve ignorar ordens bloqueadas.

    - **Tipos de ordem válidos** – Selecione os tipos de ordens de venda a serem incluídos no lote.
    - **Tipo de limite de crédito** – Selecione se as verificações de limites de crédito devem ser feitas durante o processo de liberação para o depósito e, se os cheques devem ser concluídos, as informações da transação a serem incluídas neles.

1. Para controlar quais ordens devem ser processadas, na Guia Rápida **Registros a serem incluídos**, selecione **Filtro**. Uma caixa de diálogo de consulta padrão é exibida, na qual você pode definir critérios de seleção, critérios de classificação e junções. Os campos funcionam da mesma forma que em outros tipos de consultas no Microsoft Dynamics 365 Supply Chain Management.
1. Na Guia Rápida **Executar em segundo plano**, escolha se o trabalho deve ser executado no modo de lote e/ou configure uma agenda recorrente. Os campos funcionam da mesma forma que em outros tipos de [trabalhos em segundo plano](../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md) no Supply Chain Management.
1. Selecione **OK** para aplicar suas configurações e iniciar o processo de liberação para o depósito.

Para configurar o trabalho em lotes que libera ordens de transferência, siga as etapas.

1. Acesse **Gerenciamento de depósito \> Liberar para depósito \> Liberação automática de ordens de transferência**.
1. Na caixa de diálogo **Liberação automática de ordens de transferência**, na Guia Rápida **Parâmetros**, defina os campos a seguir:

    - **Quantidade a ser liberada** – Selecione se toda a quantidade ou somente a quantidade fisicamente reservada deve ser liberada para o depósito.
    - **Permitir a liberação de ordens parcialmente liberadas** – Especifique se as quantidades restantes para ordens parcialmente liberadas devem ser liberadas para o depósito.
    - **Liberações de grupo por depósito de destino** – Especifica se o sistema deve liberar todas as ordens de transferência ao mesmo tempo ou se deve agrupar linhas de ordem de transferência por depósito de destino e liberar cada grupo para o depósito separadamente.

1. Para controlar quais ordens devem ser processadas, na Guia Rápida **Registros a serem incluídos**, selecione **Filtro**. Uma caixa de diálogo de consulta padrão é exibida, na qual você pode definir critérios de seleção, critérios de classificação e junções. Os campos funcionam da mesma forma que em outros tipos de consultas no Supply Chain Management.
1. Na Guia Rápida **Executar em segundo plano**, escolha se o trabalho deve ser executado no modo de lote e/ou configure uma agenda para recorrência. Os campos funcionam da mesma forma que em outros tipos de [trabalhos em segundo plano](../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md) no Supply Chain Management.
1. Selecione **OK** para aplicar suas configurações e iniciar o processo de liberação para o depósito.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
