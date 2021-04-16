---
title: Processar, revisar e lançar reembolsos
description: Este tópico descreve como processar suas negociações de gerenciamento de Reembolso, calcular descontos, revisar as transações geradas, lançar transações e revisar os lançamentos.
author: sherry-zheng
ms.date: 02/19/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TAMRebateDeal
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-02-19
ms.dyn365.ops.version: Release 10.0.18
ms.openlocfilehash: 53a24866786f209a1d0f6932bb4f782bf936bd21
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5819247"
---
# <a name="process-review-and-post-rebates"></a>Processar, revisar e lançar reembolsos

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Este tópico descreve como processar suas negociações de gerenciamento de Reembolso, calcular descontos, revisar as transações geradas, lançar transações e revisar os lançamentos.

## <a name="change-the-status-of-a-deal"></a>Alterar o status de uma negociação

Você pode atribuir um status a cada negociação para ajudar a rastreá-lo. O status é apenas para fins informativos.

1. Selecione uma negociação (por exemplo, na página [**Todas as negociações de reembolso**](rebate-management-deals.md)).
1. No Painel de Ações, na guia **Negociações de gerenciamento de reembolsos**, no grupo **Manter**, selecione **Alterar status**.
1. Na caixa de diálogo **Alterar status**, defina o campo **Status do reembolso** como um novo status.
1. Selecione **OK**.

## <a name="calculate-fifo-purchase-prices"></a>Calcular preços de compra de FIFO

A tarefa periódica **Calcular preço de compra FIFO** deve ser executada para calcular os reembolsos para [negociações](rebate-management-deals.md) em que o campo **Preço base** é definido como *PEPS*. O sistema usará uma regra PEPS (primeiro a entrar, primeiro a sair) para calcular o valor do estoque vendido. Esse valor será usado para calcular os reembolsos do fornecedor.

Vá para **Gerenciamento de reembolso \> Tarefas periódicas \> Calcule o preço de compra PEPS**. Na caixa de diálogo exibida, selecione **OK** para executar o cálculo.

## <a name="process-rebate-management-deals"></a>Processar Negociações de gerenciamento de reembolsos

Quando você processa uma negociação, o sistema calcula todos os reembolsos e royalties relevantes configurados. Somente as negociações selecionadas com períodos de cálculo que estão prontos para serem calculadas e que têm o status *Ativo* serão processadas. Depois de concluído o processamento, o sistema gera um conjunto de transações que podem ser revisadas e lançadas.

> [!NOTE]
> Em todos os casos, os reembolsos são processados no nível especificado por cada definição **Reconciliar por** (*Negociação* ou *Linha*). Só é possível fazer cálculos de linha única para negociações nas quais o campo **Reconciliar por** está definido como *Linha*.

### <a name="process-all-lines-for-one-or-more-deals"></a>Processar todas as linhas para uma ou mais negociações

1. Abra a [página da lista de negociações de reembolso](rebate-management-deals.md) para o tipo de negociação com o qual você deseja trabalhar.
1. Selecione a linha para cada negociação que deseja processar (ou abra a negociação que deseja processar).
1. No Painel de Ações, na guia **Negociações de gerenciamento de reembolsos**, no grupo **Gerar**, selecione um dos seguintes comandos:

    - **Processar \> Provisão** – provisione um conjunto de competências para cada acordo de reembolso relevante, mas não os lance.
    - **Processar \> gerenciamento de reembolso** – processa uma série de transações que fornecem o valor do reembolso para cada negociação.
    - **Processar \> Baixa** – reverta as transações lançadas anteriormente para baixá-las para que novas transações de negociação de reembolso possam ser calculadas.

1. Na caixa de diálogo exibida, defina os campos **Data de** e **Data até** para definir o intervalo de datas para o cálculo.
1. Selecione **OK** para executar o cálculo.

### <a name="process-one-or-more-specific-deal-lines-for-a-selected-deal"></a>Processar uma ou mais linhas de negociação específicas para uma negociação selecionada

1. Abra a [página da lista de negociações de reembolso](rebate-management-deals.md) para o tipo de negociação com o qual você deseja trabalhar.
1. Abra a negociação da qual você deseja processar uma linha.
1. Selecione a guia **Linhas** no canto superior direito.
1. Na guia rápida **Gerenciamento de reembolso**, selecione a linha para cada linha de negociação que você deseja processar.
1. Na barra de ferramentas da guia rápida **Gerenciamento de reembolso**, selecione um dos seguintes comandos. (Esses comandos estão disponíveis apenas para as negociações nas quais o campo **Reconciliar por** está definido como *Linha*.)

    - **Processar \> Provisão** – provisione um conjunto de competências para cada linha de negociação relevante, mas não o lance.
    - **Processar \> gerenciamento de reembolso** – processa uma série de transações que fornecem o valor do reembolso para cada linha da negociação.
    - **Processar \> Baixa** – reverta as transações lançadas anteriormente para baixá-las para que novas transações de negociação de reembolso possam ser calculadas.

1. Na caixa de diálogo exibida, defina os campos **Data de** e **Data até** para definir o intervalo de datas para o cálculo.
1. Selecione **OK** para executar o cálculo.

### <a name="process-deals-using-a-batch-job"></a>Processar negociações usando um trabalho em lotes

Em vez de processar negociações ou linhas de negociações específicas, você pode executar um trabalho em lotes para processar várias negociações ao mesmo tempo. Opcionalmente, você pode aplicar filtros de registro e/ou configurar um agendamento recorrente. Para processar as negociações usando um trabalho em lotes, siga estas etapas.

1. Siga uma destas etapas:

    - Vá para **Gerenciamento de reembolso \> Tarefas periódicas \> Processar \> Provisionar** para provisionar um conjunto de competências para cada negócio relevante, mas sem lançá-las.
    - Vá para **Gerenciamento de reembolso \> Tarefas periódicas \> Processar \> Gerenciamento de reembolso** para processar uma série de transações que fornecem o valor do reembolso para cada linha da negociação.
    - Vá para **Gerenciamento de reembolso \> Tarefas periódicas \> Processar \> Baixa** para reverter as transações lançadas anteriormente para baixá-las para que novas transações de negociação de reembolso possam ser calculadas.

1. Na caixa de diálogo exibida, na guia rápida **Parâmetros**, na seção **Período**, defina os campos **Data de** e **Data até** para definir o intervalo de datas para as transações do cálculo.
1. Na seção **Período de Garantia**, defina os campos **Data - de** e **Data - até** para definir o intervalo de datas para garantias para o cálculo.
1. Na guia rápida **Registros a serem incluídos**, você pode configurar filtros para limitar o conjunto de negociações que o trabalho em lotes processará. Essas configurações funcionam da mesma forma que funcionam para outros tipos de trabalhos em lotes.
1. Na guia rápida **Executar em segundo plano**, você pode configurar as opções de processamento e programação de lote, conforme necessário. Essas configurações funcionam da mesma forma que funcionam para outros tipos de trabalhos em lotes.
1. Selecione **OK** para executar e/ou programar o cálculo.

## <a name="view-and-edit-rebate-management-transactions"></a>Exibir e editar transações de gerenciamento de reembolso

Ao processar uma ou mais negociações, o sistema cria transações que você pode exibir e, talvez, editar antes de lançá-las.

1. Siga uma destas etapas:

    - Selecione a negociação para exibir as transações (por exemplo, na [**Todas as negociações de gerenciamento de reembolso**](rebate-management-deals.md)). No painel de ações, na guia **Negociações de gerenciamento de reembolso**, no grupo **Transações**, selecione **Transações** ou **Garantir transações**, dependendo do tipo de transação que você deseja exibir.
    - Abra uma negociação (por exemplo, na página [**Todas as negociações de gerenciamento de reembolso**](rebate-management-deals.md)) para exibir seus detalhes. Na guia rápida **Gerenciamento de reembolso**, selecione a linha de negociação para exibir das transações. Em seguida, na barra de ferramentas, selecione **Transações** ou **Garantir transações**, dependendo do tipo de transação que você deseja exibir. (Esses botões estão disponíveis apenas para as negociações nas quais o campo **Reconciliar por** está definido como *Linha*.)

1. É exibida a página **Transações da data de gerenciamento de reembolso** ou **Transações de garantia de gerenciamento de reembolso**. Ela contém uma grade, em que cada linha representa um conjunto de transações de um único reembolso ou período de garantia. Selecione uma linha na grade e, no painel de ação, selecione **Transações de origem** para exibir as transações que pertencem a essa linha.
1. A página exibida mostra uma lista das transações do tipo selecionado que pertencem à linha selecionada. Cada transação fornece detalhes relevantes, dependendo do tipo de transação. Para transações de garantia, você só pode exibir a lista. Para outros tipos de transações, você pode executar as seguintes ações na página:

    - Para verificar o valor total de todas as transações reivindicadas na página, exiba o campo **Valor reivindicado**.
    - Para exibir mais informações sobre qualquer transação, selecione-a e depois a guia **Geral**, **Dimensão financeira** ou **Dimensão**.
    - Para exibir as reduções aplicáveis, selecione **Transações de redução** no Painel de Ações. Para obter mais informações, consulte [Princípios de redução de reembolso](rebate-reduction-principle.md).
    - Para marcar transações como reivindicadas ou não reivindicadas, se você estiver usando um processo de reivindicações, selecione as linhas relevantes e, no Painel de Ação, selecione um dos comandos a seguir. (Você habilita os processo de reivindicação na página [**Parâmetros de gerenciamento de reembolso**](rebate-management-parameters.md) .)

        - **Definir reivindicadas \> Todas** – marque todas as transações como reivindicadas.
        - **Definir reivindicadas \> Selecionadas** – marque as transações selecionadas como reivindicadas.
        - **Definir não reivindicadas \> Todas** – marque todas as transações como não reivindicadas.
        - **Definir não reivindicadas \> Selecionadas** – marque as transações selecionadas como não reivindicadas.

    - Para lançar a reivindicação para uma ou mais linhas, selecione as linhas relevantes e, em seguida, no painel de ação, selecione **Lançar**. (O botão **Lançar** está disponível apenas para transações de reembolso. Ele não está disponível para transações de provisão e baixa.) Na caixa de diálogo **Lançar**, os campos **Data de** e **Data até** são definidos automaticamente. Defina o campo **Data do lançamento** e selecione **OK**.
    - Para ajustar o valor mostrado para qualquer transação aberta ou não lançada, selecione a transação e siga uma destas etapas:

        - Edite o valor no campo **Valor corrigido**.
        - No painel de ação, selecione **Definir correção**. Em seguida, na caixa de diálogo suspensa que aparece, no campo **Valor corrigido**, insira um valor.

> [!NOTE]
> Quando você processar o próximo período, a lista de transações incluirá todas as transações não reivindicadas do lançamento anterior, além de todas as novas transações do período selecionado.

## <a name="post-rebates-transactions"></a>Lançar transações de reembolso

Para lançar o valor dos reembolsos e deduções, você deve executar o processo de lançamento, a menos que tenha configurado seu sistema para lançá-los automaticamente.

### <a name="set-up-the-system-to-post-all-transactions-automatically"></a>Configurar o sistema para lançar todas as transações automaticamente

Para configurar o sistema para lançar todas as transações tão logo sejam geradas, ative a opção **Lançar diários automaticamente** e/ou **Lançar automaticamente faturas de texto livre** na página **Parâmetros de gerenciamento de reembolso**. Para obter mais informações, consulte [Parâmetros de gerenciamento de reembolsos](rebate-management-parameters.md).

### <a name="post-transactions-for-all-lines-for-one-or-more-deals"></a>Lançar transações para todas as linhas para uma ou mais negociações

Se você não estiver usando o lançamento automático, depois de ter processado as negociações relevantes, siga estas etapas para revisar e lançar as transações geradas para todas as linhas de uma ou mais negociações.

1. Abra a [página da lista de negociações de reembolso](rebate-management-deals.md) para o tipo de negociação com o qual você deseja trabalhar.
1. Selecione a linha para cada negociação que deseja lançar (ou abra a negociação que deseja lançar).
1. No Painel de Ações, na guia **Negociações de gerenciamento de reembolsos**, no grupo **Gerar**, selecione um dos seguintes comandos:

    - **Lançar \> Provisão** – lançar transações de competências disponíveis criadas por você.
    - **Lançar \> Gerenciamento de reembolso** – lançar transações de reembolso disponíveis criadas por você.
    - **Lançar \> Baixa** – lançar transações de baixa disponíveis criadas por você.

1. Na caixa de diálogo que aparece, defina o campo **Data do lançamento**. Em seguida, defina os campos **Data de** e **Data até** para definir o intervalo de dados para as transações que devem ser lançadas.
1. Selecione **OK** para lançar as transações.

### <a name="post-transactions-for-one-or-more-specific-deal-lines-for-a-selected-deal"></a>Lançar transações para uma ou mais linhas de negociação específicas para uma negociação selecionada

Se você não estiver usando o lançamento automático, depois de ter processado as negociações relevantes, siga estas etapas para revisar e lançar as transações geradas para uma ou mais linhas de negociação específicas para uma negociação selecionada.

1. Abra a [página da lista de negociações de reembolso](rebate-management-deals.md) para o tipo de negociação com o qual você deseja trabalhar.
1. Abra a negociação que tem uma linha para a qual você deseja lançar transações.
1. Selecione a guia **Linhas** no canto superior direito.
1. Na guia rápida **Gerenciamento de reembolso**, selecione a linha para cada linha de negociação que você deseja lançar.
1. Na barra de ferramentas da guia rápida **Gerenciamento de reembolso**, selecione um dos seguintes comandos. (Esses comandos estão disponíveis apenas para as negociações nas quais **Reconciliar por** está definido como *Linha*).

    - **Lançar \> Provisão** – lançar transações de competências disponíveis criadas por você.
    - **Lançar \> Gerenciamento de reembolso** – lançar transações de reembolso disponíveis criadas por você.
    - **Lançar \> Baixa** – lançar transações de baixa disponíveis criadas por você.

1. Na caixa de diálogo que aparece, defina o campo **Data do lançamento**. Em seguida, defina os campos **Data de** e **Data até** para definir o intervalo de dados para as transações que devem ser lançadas.
1. Selecione **OK** para lançar as transações.

### <a name="post-transactions-using-a-batch-job"></a>Lançar transações usando um trabalho em lotes

Em vez de lançar transações para negociações específicas ou linhas da negociação, você pode executar um trabalho em lotes para lançar transações para várias negociações ao mesmo tempo. Opcionalmente, você pode aplicar filtros de registro e/ou configurar um agendamento recorrente. Para lançar transações usando um trabalho em lotes, siga estas etapas.

1. Siga uma destas etapas:

    - Vá para **Gerenciamento de reembolsos \> Tarefas periódicas \> Lançar \> Provisão** para lançar transações de competência disponíveis criadas por você.
    - Vá para **Gerenciamento de reembolsos \> Tarefas periódicas \> Lançar \> Gerenciamento de reembolso** para lançar transações de competência disponíveis criadas por você.
    - Vá para **Gerenciamento de reembolso \> Tarefas periódicas \> Lançar \> Baixa** para lançar transações de baixa disponíveis criadas por você.

1. Na caixa de diálogo exibida, na guia rápida **Parâmetros**, na seção **Período**, defina o campo **Data de lançamento**. Em seguida, defina os campos **Data de** e **Data até** para definir o intervalo de dados para as transações que devem ser lançadas. 
1. Na seção **Período de Garantia**, defina os campos **Data - de** e **Data - até** para definir o intervalo de datas para garantias que devem ser lançadas.
1. Na guia rápida **Registros a serem incluídos**, você pode configurar filtros para limitar o conjunto de negociações que o trabalho em lotes processará. Essas configurações funcionam da mesma forma que funcionam para outros tipos de trabalhos em lotes.
1. Na guia rápida **Executar em segundo plano**, você pode configurar as opções de processamento e programação de lote, conforme necessário. Essas configurações funcionam da mesma forma que funcionam para outros tipos de trabalhos em lotes.
1. Selecione **OK** para executar e/ou programar o cálculo.

## <a name="review-rebate-management-journals"></a>Revisar diários de gerenciamento de reembolso

Depois que as transações forem lançadas, você poderá revisar os diários, documentos ou itens resultantes. As transações de destino para reembolsos e royalties se baseiam no tipo de pagamento definido no perfil de lançamentos e no tipo de saída do reembolso. Por exemplo, se a saída do reembolso for definida como *Item*, uma ordem de venda será criada e poderá ser exibida por meio das transações de destino. Como alternativa, se o pagamento for configurado para usar Contas a pagar, uma fatura de fornecedor para o fornecedor configurado no cliente será criada para reembolsos do cliente.

Para revisar as entradas de diário associadas a um acordo de gerenciamento de reembolso, siga estas etapas.

1. Abra a [página da lista de negociações de reembolso](rebate-management-deals.md) para o tipo de negociação com o qual você deseja trabalhar.
1. Selecione a negociação para o qual inspecionar entradas de diário.
1. No Painel de Ações, na guia **Negociações de gerenciamento de reembolso**, no grupo **Transações**, selecione **Transações** ou **Garantir transações**, dependendo do tipo de transação que você deseja exibir.
1. Verifique se o campo **Mostrar** está definido como *Todos* ou *Lançado*.
1. Localize e selecione a coleção de transações que deseja inspecionar e, no Painel de Ação, selecione um dos botões a seguir. (Esses botões estão disponíveis somente quando há lançamentos relevantes para a coleção de transações selecionada.)

    - **Transações de destino** – revise os diários relevantes e outros tipos de documentos que foram gerados pela negociação selecionada.
    - **Itens** – revise os itens relevantes que foram gerados pela negociação selecionada.

1. Uma lista de diários, documentos ou itens relevantes é exibida. Para exibir mais informações sobre qualquer diário, documento ou item, selecione sua linha e, no Painel de Ação, selecione **Exibir detalhes**.
