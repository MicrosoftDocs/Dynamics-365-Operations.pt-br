---
title: Arquivo-morto de transações de estoque
description: Este tópico descreve como arquivar dados de transações de estoque para ajudar a melhorar o desempenho do sistema.
author: sherry-zheng
ms.date: 03/01/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventTransArchiveProcessForm
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-03-01
ms.dyn365.ops.version: Release 10.0.18
ms.openlocfilehash: b740da1a8a349f4a1a80b41bf717c388fd3db0c0
ms.sourcegitcommit: d18d9cdb175c9d42eafbed66352c24b2aa94258b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/13/2021
ms.locfileid: "5881823"
---
# <a name="archive-inventory-transactions"></a>Arquivo-morto de transações de estoque

[!include [banner](../../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Com o tempo, a tabela de transações de estoque (`InventTrans`) continuará a crescer e consumir mais espaço no banco de dados. Portanto, as consultas feitas na tabela ficarão mais lentas gradualmente. Este tópico descreve como você pode usar o recurso *Arquivo-morto de transações de estoque* para arquivar dados sobre transações de estoque para ajudar a melhorar o desempenho do sistema.

> [!NOTE]
> Somente as transações de estoque atualizadas financeiramente podem ser arquivadas em um período contábil fechado selecionado. Para serem arquivados, as transações de estoque de saída atualizadas financeiramente devem ter um status de saída de *Vendido*, e as transações de estoque de entrada devem ter um status de recebimento de *Comprado*.

Ao arquivar transações de estoque, todas as transações relacionadas são movidas para a tabela `InventTransArchive`. As transações de saída de estoque e as transações de recebimento de estoque são arquivadas separadamente, com base na combinação da ID do item (`itemId`) e da ID da dimensão de estoque (`inventDimId`), e são colocadas na saída resumida e nas transações de recebimento resumidas.

Se uma combinação de `itemId` e `inventDimId` contiver somente uma transação de recebimento ou de saída, a transação não será arquivada.

## <a name="turn-on-the-feature-in-your-system"></a>Ative o recurso no seu sistema

Se o sistema ainda não incluir os recursos descritos neste tópico, acesse [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) e ative o recurso *Arquivo-morto de transações de estoque*. Observe que esse recurso não pode ser desabilitado após ter sido habilitado.

## <a name="things-to-consider-before-you-archive-inventory-transactions"></a>Itens a serem considerados antes de arquivar transações de estoque

Antes de arquivar transações de estoque, considere os cenários comerciais a seguir, porque eles serão afetados pela operação:

- Quando você auditar transações de estoque de documentos relacionados, como linhas de ordem de compra, elas serão mostradas como arquivadas. Para revisar as transações arquivadas, você deve acessar **Gerenciamento de estoque \> Tarefas periódicas \> Limpar \> Arquivo-morto de transações de estoque**.
- Não é possível cancelar o fechamento de estoque para períodos arquivados. Antes que possa cancelar um fechamento de estoque, você deve reverter o arquivamento da transação de estoque para o período relevante.
- Não é possível fazer a conversão de custo padrão para períodos arquivados. Antes que possa fazer a conversão de custo padrão, você deve reverter o arquivamento da transação de estoque para o período relevante.
- Os relatórios de estoque que são originados das transações de estoque serão afetados quando você arquivar as transações de estoque. Esses relatórios incluem o relatório de classificação por vencimento do estoque e os relatórios de valor de estoque.
- As previsões de estoque podem ser afetadas se forem executadas durante o horizonte de tempo dos períodos arquivados.

## <a name="prerequisites"></a>Pré-requisitos

As transações de estoque poderão ser arquivadas somente durante os períodos em que as seguintes condições forem atendidas:

- O período contábil deve estar fechado.
- O fechamento de estoque deve ser executado na data final do período do arquivamento ou em data posterior.
- O período deve ser pelo menos um ano antes da data inicial do período do arquivamento.
- Não deve haver nenhum recálculos de estoque existente.

## <a name="archive-inventory-transactions"></a>Arquivo-morto de transações de estoque

Para arquivar as transações de estoque, siga estas etapas:

1. Acesse **Gerenciamento de estoque** \> **Tarefas periódicas** \> **Limpar** \> **Arquivo-morto de transação de estoque**.

    A página **Arquivo-morto de transações de estoque** será exibida e exibirá uma lista de registros de processos arquivados.

    ![Página Arquivo-morto de transações de estoque](media/archive-inventory-empty.png "Página Arquivo-morto de transações de estoque")

1. No Painel de Ações, selecione **Arquivo-morto de transações de estoque** para criar um arquivo de transação de estoque.
1. Na caixa de diálogo **Arquivo-morto de transações de estoque**, na FastTab **Parâmetros**, defina os seguintes campos:

    - **Data inicial do período contábil fechado** — selecione a data da transação mais antiga a ser incluída no arquivo morto.
    - **Data final do período contábil fechado** — selecione a data da transação mais recente a ser incluída no arquivo morto.

    ![Caixa de diálogo Arquivo-morto de transações de estoque](media/archive-inventory-dates.png "Caixa de diálogo Arquivo-morto de transações de estoque")

    > [!NOTE]
    > Somente os períodos que atendem aos [pré-requisitos](#prerequisites) estarão disponíveis para seleção.

1. Na FastTab **Executar em segundo plano**, configure os detalhes do processamento em lotes conforme necessário. Siga as etapas usuais para trabalhos em lotes no Microsoft Dynamics 365 Supply Chain Management.
1. Selecione **OK**.
1. Você receberá uma mensagem solicitando que você confirme se deseja continuar. Leia a mensagem com atenção e selecione **Sim** se quiser continuar.

    Você receberá uma mensagem indicando que o trabalho de arquivamento de transações de estoque foi adicionado à fila de lotes. Agora, o trabalho começará a arquivar as transações de estoque do período selecionado.

## <a name="view-archived-inventory-transactions"></a>Exibir transações de estoque arquivadas

A página **Arquivo-morto de transações de estoque** exibe o histórico completo do arquivamento. Cada linha na grade mostra informações como a data em que o arquivo foi criado, o usuário que o criou e seu status.

![Histórico do arquivamento na página Arquivo-morto de transações de estoque](media/archive-inventory-full.png "Histórico do arquivamento na página Arquivo-morto de transações de estoque")

Na lista suspensa na parte superior da página, selecione um dos seguintes valores para filtrar os arquivos exibidos na grade:

- **Ativo** — mostra somente os arquivos ativos, não os arquivos revertidos.
- **Todos** — mostra todos os arquivos, ativos e revertidos.

Para cada arquivo na grade, são fornecidas as seguintes informações:

- **Ativo** — uma marca de seleção indica se o arquivo-morto está ativo.
- **Data inicial** — a data da transação mais antiga que pode ser incluída no arquivo-morto.
- **Data final** — a data da transação mais recente que pode ser incluída no arquivo-morto.
- **Agendado por** — a conta de usuário que criou o arquivo.
- **Executado** — a data de criação do arquivo-morto.
- **Revertido** — uma marca de seleção indica que o arquivo foi revertido.
- **Parar atualização presente** — uma marca de seleção indica que o arquivamento está em andamento, mas que foi pausado.
- **Estado** — o status de processamento do arquivo-morto. Os valores possíveis são *Aguardando*, *Em andamento* e *Concluído*.

A barra de ferramentas acima da grade fornece os seguintes botões que podem ser usados para trabalhar com um arquivo-morto selecionado:

- **Transações arquivadas** — exibe os detalhes completos do arquivo-morto selecionado. A página **Transações arquivadas** exibida mostra todas as transações no arquivo-morto.

    ![Página Transações arquivadas](media/archive-inventory-transactions.png "Página Transações arquivadas")

    Para exibir mais informações sobre uma transação específica na página **Transações arquivadas**, selecione-a na grade e, no Painel de Ações, selecione **Detalhes da transação arquivada**. A página **Detalhes da transação arquivada** exibida mostra informações como o lançamento contábil, as referências do auxiliar relacionado e as dimensões financeiras.

- **Pausar arquivamento** — pausa um arquivo-morto selecionado que está sendo processado no momento. A pausa entrará em vigor somente após a geração da tarefa de arquivamento. Portanto, pode haver um breve atraso antes que a pausa entre em vigor. Se um arquivo-morto for pausado, aparecerá uma marca de seleção no campo **Parar atualização presente**.
- **Continuar arquivamento** — retoma o processamento de um arquivo-morto selecionado que está pausado no momento.
- **Reverter** — reverte o arquivo-morto selecionado. Só é possível reverter um arquivo-morto se o campo **Estado** estiver definido como *Concluído*. Se um arquivo-morto for revertido, aparecerá uma marca de seleção no campo **Revertido**.
