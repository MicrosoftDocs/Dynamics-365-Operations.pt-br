---
title: Processar, revisar e lançar reembolsos
description: Este artigo descreve como processar suas negociações de gerenciamento de Reembolso, calcular descontos, revisar as transações geradas, lançar transações e revisar os lançamentos.
author: sherry-zheng
ms.date: 02/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TAMRebateDeal
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-02-19
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: e63f02e5e93ec2ce8c321a20c2a0c5886edcbe42
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8901927"
---
# <a name="process-review-and-post-rebates"></a>Processar, revisar e lançar reembolsos

[!include [banner](../includes/banner.md)]

Este artigo descreve como processar suas negociações de gerenciamento de Reembolso, calcular descontos, revisar as transações geradas, lançar transações e revisar os lançamentos.

## <a name="change-the-status-of-a-deal"></a>Alterar o status de uma negociação

Você pode atribuir um status a cada negociação para ajudar a rastreá-lo. O status é apenas para fins informativos.

1. Selecione uma negociação (por exemplo, na página [**Todas as negociações de reembolso**](rebate-management-deals.md)).
1. No Painel de Ações, na guia **Negociações de gerenciamento de reembolsos**, no grupo **Manter**, selecione **Alterar status**.
1. Na caixa de diálogo **Alterar status**, defina o campo **Status do reembolso** como um novo status.
1. Selecione **OK**.

## <a name="calculate-fifo-purchase-prices"></a>Calcular preços de compra de FIFO

A tarefa periódica **Calcular preço de compra FIFO** deve ser executada para calcular os reembolsos para [negociações](rebate-management-deals.md) em que o campo **Preço base** é definido como *PEPS*. O sistema usará uma regra PEPS (primeiro a entrar, primeiro a sair) para calcular o valor do estoque vendido. Esse valor será usado para calcular os reembolsos do fornecedor.

Acesse **Gerenciamento de reembolso \> Tarefas periódicas \> Calcule o preço de compra PEPS**. Na caixa de diálogo exibida, selecione **OK** para executar o cálculo.

## <a name="create-source-transactions"></a>Criar transações de origem

Você pode criar as ordens de venda ou de compra que têm transações de origem antes ou depois de criar uma oportunidade de gerenciamento de reembolso aplicável.

Você pode configurar cada linha de oportunidade para que ela crie automaticamente uma provisão de reembolso lançando a entrega ou a fatura de uma ordem de venda ou ordem de compra. Defina o campo **Tipo de transação** para a linha de oportunidade como *Entrega* ou *Fatura* e defina a opção **Processar no lançamento** como *Sim*. Se o campo **Tipo de transação** estiver definido como *Ordem*, o processamento no lançamento será desabilitado. Para transações de origem criadas após a ativação de uma oportunidade, você ainda poderá processar a provisão, conforme descrito na seção [Processar oportunidades de gerenciamento de reembolso](#process-deals), posteriormente neste artigo.

### <a name="enable-price-details"></a>Ativar detalhes de preço

Antes de criar transações de origem, você deve habilitar a opção **Habilitar detalhes de preço** para contas a receber.

1. Acesse **Contas a receber \> Configuração \> Parâmetros de contas a receber**.
1. Na guia **Preços**, na Guia Rápida **Detalhes de preço** , defina a opção **Habilitar detalhes de preço** como *Sim*.

### <a name="create-a-source-transaction"></a>Criar uma transação de origem

Para criar uma transação de origem, siga estas etapas.

1. Acesse **Vendas e marketing \> Ordens de venda \> Todas as ordens de venda**.
1. Selecione **Novo**.

    Para imitar a forma como as reivindicações de reembolso são geradas, agora você deve criar uma ordem de venda, na qual o produto e a quantidade irão qualificar o cliente para um reembolso.

1. No campo **conta de cliente**, insira ou selecione um cliente que será qualificado para um acordo de descontos.
1. Selecione **OK** para criar a ordem de venda.
1. Na guia rápida **Linhas da ordem de venda**, adicione uma linha e defina os seguintes campos para ela:

    - **Número do item** – Especifique um item que se qualifica para um reembolso.
    - **Quantidade** – Especifique uma quantidade qualificada para um acordo de reembolsos que inclui uma linha na qual o campo **Com base** esteja definido como *Quantidade*.
    - **Preço unitário** – Especifique um preço qualificado para um acordo de reembolsos que inclui uma linha na qual o campo **Com base** esteja definido como *Valor*.
    - **Site** – Selecione um site onde o produto está disponível e que seja qualificado para uma oportunidade de reembolso.
    - **Armazém** – Selecione um armazém onde o produto está disponível e que seja qualificado para uma oportunidade de reembolso.

1. Na Guia Rápida **Linhas da ordem de venda**, na barra de ferramentas, selecione **Linha da ordem de venda \> Detalhes de preço**. Este comando só ficará disponível se você tiver habilitado os detalhes de preço conforme descrito na seção anterior.
1. Na página **Detalhes de preço**, selecione a Guia Rápida **Gerenciamento de reembolso**. A guia rápida lista todas as oportunidades de gerenciamento que são aplicáveis à linha de ordem atual e mostra o valor estimado do reembolso. Lembre-se de que os valores são apenas estimativas das futuras declarações de reembolso. Os valores de reembolso reais podem ser diferentes. Estes são alguns dos fatores que podem afetar os valores reais:

    - O volume de vendas total que o cliente obteve sob um contrato de reembolso periódico.
    - Se o cliente retornou todas as quantidades ou quantidades parciais.
    - Se a ordem de venda aplicável tiver obtido o tipo de transação (*Ordem, Entrega* ou *Fatura*) definido para o acordo de Gerenciamento de reembolso.
    - O valor de **Saída** da oportunidade. Um valor de reembolso em branco será mostrado para as oportunidades nas quais o campo **Saída** está definido como *Item*.

1. Na Guia Rápida **Detalhes**, observe que a seção **Estimativa de margem** inclui os campos a seguir. Esses campos são adicionados pelo Gerenciamento de reembolso. Todas elas mostram valores por unidade (enquanto os campos na Guia Rápida **Gerenciamento de reembolso** mostram os valores totais da linha).

    - **Valor de reembolso do Gerenciamento de reembolso** (somente ordens de venda)
    - **Valor de royalty do Gerenciamento de reembolso** (somente ordens de venda)
    - **Valor de reembolso do fornecedor do Gerenciamento de reembolso** (ordens de venda e ordens de compra)

1. Feche a página **Detalhes de preço**.
1. Se a ordem de venda não deve ser qualificada para os reembolsos que você acabou de visualizar, siga estas etapas para excluir reembolsos. (No entanto, geralmente não é possível excluir reembolsos).

    1. Na Guia Rápida **Linhas de ordem de venda**, selecione a linha relevante.
    1. Na Guia Rápida **Detalhes da linha**, na guia **Preço e desconto**, defina a opção **Excluir do gerenciamento de reembolso** como *Sim*. Esta opção não se aplica a ordens de compra. Além disso, somente os reembolsos do cliente são excluídos quando essa opção é definida como *Sim*. Os reembolsos de royalty do cliente e reembolsos de fornecedor ainda se aplicam.

1. No painel de ações, na guia **Separar e embalar**, no grupo **Gerar**, selecione **Lançar guia de remessa**.
1. Na Guia Rápida **Parâmetros**, no campo **Quantidade**, selecione *Tudo*.
1. Selecione **OK**.
1. Se você for solicitado a confirmar a operação, selecione **OK**.
1. No Painel de Ação, na guia **Fatura**, no grupo **Gerar**, selecione **Fatura**.
1. Na Guia Rápida **Parâmetros**, no campo **Quantidade**, selecione *Tudo* ou *Guia de remessa*.
1. Selecione **OK**.
1. Se você for solicitado a confirmar a operação, selecione **OK**.

## <a name="process-rebate-management-deals"></a><a name="process-deals"></a>Processar Negociações de gerenciamento de reembolsos

Quando você processa uma negociação, o sistema calcula todos os reembolsos e royalties relevantes configurados. Somente as negociações selecionadas com períodos de cálculo que estão prontos para serem calculadas e que têm o status *Ativo* serão processadas. Depois de concluído o processamento, o sistema gera um conjunto de transações que podem ser revisadas e lançadas.

> [!NOTE]
> Em todos os casos, os reembolsos são processados no nível especificado por cada definição **Reconciliar por** (*Negociação* ou *Linha*). Só é possível fazer cálculos de linha única para negociações nas quais o campo **Reconciliar por** está definido como *Linha*.

### <a name="process-all-lines-for-one-or-more-deals"></a>Processar todas as linhas para uma ou mais negociações

1. Abra a [página da lista de negociações de reembolso](rebate-management-deals.md) para o tipo de negociação com o qual você deseja trabalhar.
1. Selecione a linha para cada negociação que deseja processar (ou abra a negociação que deseja processar).
1. No Painel de Ações, na guia **Negociações de gerenciamento de reembolsos**, no grupo **Gerar**, selecione um dos seguintes comandos:

    - **Processar \> Provisão** – provisione um conjunto de competências para cada acordo de reembolso relevante, mas não os lance. Este item do menu não está disponível para ofertas nas quais o campo **Saída de reembolso** é definido como *Item*.
    - **Processar \> gerenciamento de reembolso** – processa uma série de transações que fornecem o valor do reembolso para cada negociação.
    - **Processo \> Dar baixa** – Para cada transação de origem para o contrato de reembolso e período especificado, processe a variação entre os valores que foram postados para um provisionamento e para o gerenciamento de reembolso. Este item do menu não está disponível para ofertas nas quais o campo **Saída de reembolso** é definido como *Item*.

1. Na caixa de diálogo exibida, defina os campos **Data de** e **Data até** para definir o intervalo de datas para o cálculo.
1. Selecione **OK** para executar o cálculo.

### <a name="process-one-or-more-specific-deal-lines-for-a-selected-deal"></a>Processar uma ou mais linhas de negociação específicas para uma negociação selecionada

1. Abra a [página da lista de negociações de reembolso](rebate-management-deals.md) para o tipo de negociação com o qual você deseja trabalhar.
1. Abra a negociação da qual você deseja processar uma linha.
1. Selecione a guia **Linhas** no canto superior direito.
1. Na guia rápida **Gerenciamento de reembolso**, selecione a linha para cada linha de negociação que você deseja processar.
1. Na barra de ferramentas da guia rápida **Gerenciamento de reembolso**, selecione um dos seguintes comandos. (Esses comandos estão disponíveis apenas para as negociações nas quais o campo **Reconciliar por** está definido como *Linha*.)

    - **Processar \> Provisão** – provisione um conjunto de competências para cada linha de negociação relevante, mas não o lance. Este item do menu não está disponível para ofertas nas quais o campo **Saída de reembolso** é definido como *Item*.
    - **Processar \> gerenciamento de reembolso** – processa uma série de transações que fornecem o valor do reembolso para cada linha da negociação.
    - **Processo \> Dar baixa** – Para cada transação de origem para o contrato de reembolso e período especificado, processe a variação entre os valores que foram postados para um provisionamento e para o gerenciamento de reembolso. Este item do menu não está disponível para ofertas nas quais o campo **Saída de reembolso** é definido como *Item*. 

1. Na caixa de diálogo exibida, defina os campos **Data de** e **Data até** para definir o intervalo de datas para o cálculo.
1. Selecione **OK** para executar o cálculo.

### <a name="process-deals-using-a-batch-job"></a>Processar negociações usando um trabalho em lotes

Em vez de processar negociações ou linhas de negociações específicas, você pode executar um trabalho em lotes para processar várias negociações ao mesmo tempo. Opcionalmente, você pode aplicar filtros de registro e/ou configurar um agendamento recorrente. Para processar as negociações usando um trabalho em lotes, siga estas etapas.

1. Siga uma destas etapas:

    - Acesse **Gerenciamento de reembolso \> Tarefas periódicas \> Processar \> Provisionar** para provisionar um conjunto de competências para cada negócio relevante, mas sem lançá-las.
    - Acesse **Gerenciamento de reembolso \> Tarefas periódicas \> Processar \> Gerenciamento de reembolso** para processar uma série de transações que fornecem o valor do reembolso para cada linha da negociação.
    - Acesse **Gerenciamento de reembolso \> Tarefas periódicas \> Processar \> Baixa** para reverter as transações lançadas anteriormente para baixá-las para que novas transações de negociação de reembolso possam ser calculadas.

1. Na caixa de diálogo exibida, na guia rápida **Parâmetros**, na seção **Período**, defina os campos **Data de** e **Data até** para definir o intervalo de datas para as transações do cálculo.
1. Na seção **Período de Garantia**, defina os campos **Data - de** e **Data - até** para definir o intervalo de datas para garantias para o cálculo.
1. Na guia rápida **Registros a serem incluídos**, você pode configurar filtros para limitar o conjunto de negociações que o trabalho em lotes processará. Essas configurações funcionam da mesma forma que funcionam para outros tipos de trabalhos em lotes.
1. Na guia rápida **Executar em segundo plano**, você pode configurar as opções de processamento e programação de lote, conforme necessário. Essas configurações funcionam da mesma forma que funcionam para outros tipos de trabalhos em lotes.
1. Selecione **OK** para executar e/ou programar o cálculo.

### <a name="process-deals-by-using-the-rebate-workbench"></a>Processar oportunidades usando a bancada de reembolso

Em vez de processar negociações ou linhas de negociações específicas, você pode usar a *bancada de reembolso* para processar várias negociações ao mesmo tempo. Opcionalmente, você pode aplicar filtros de registro e/ou configurar um agendamento recorrente. Não é necessário selecionar linhas. O sistema processará todas as linhas que atenderem aos requisitos de data e de filtro configurados.

Para processar as negociações usando a bancada de reembolso, siga estas etapas.

1. Acesse **Gerenciamento de reembolso \> Acordos de gerenciamento de reembolso \> Bancada de reembolso**.
1. No Painel de Ações, na guia **Bancada de reembolso**, no grupo **Processamento**, selecione um dos seguintes comandos:

    - **Processar \> Provisão** – Provisione um conjunto de competências para cada linha de negociação relevante, mas não lance os acúmulos.
    - **Processar \> gerenciamento de reembolso** – processa uma série de transações que fornecem o valor do reembolso para cada linha da negociação.
    - **Processo \> Dar baixa** – Para cada transação de origem para o contrato de reembolso e período especificado, processe a variação entre os valores que foram postados para um provisionamento e para o gerenciamento de reembolso.

1. Na caixa de diálogo **Gerenciamento de reembolso**, na seção **Período**, defina os campos **Data de** e **Data até** para definir o intervalo de datas para o cálculo.
1. Na seção **Período de Garantia**, defina os campos **Data de** e **Data até** para definir o intervalo de datas para garantias para o cálculo.
1. Na guia rápida **Registros a serem incluídos**, você pode configurar filtros para limitar o conjunto de negociações que o trabalho em lotes processará. Essas configurações funcionam da mesma forma que funcionam para outros tipos de trabalhos em lotes.
1. Na guia rápida **Executar em segundo plano**, você pode configurar as opções de processamento e programação de lote, conforme necessário. Essas configurações funcionam da mesma forma que funcionam para outros tipos de trabalhos em lotes.
1. Selecione **OK** para executar e/ou programar o cálculo.

## <a name="view-and-edit-rebate-management-transactions"></a>Exibir e editar transações de gerenciamento de reembolso

Ao processar uma ou mais negociações, o sistema cria transações que você pode exibir e, talvez, editar antes de lançá-las.

### <a name="view-and-edit-rebate-management-transactions-by-using-the-rebate-deals-list-page"></a>Exibir e editar transações de gerenciamento de reembolsos usando a página lista de oportunidades de reembolsos

Para exibir e editar transações de gerenciamento de reembolsos usando a página lista de oportunidades de reembolsos, siga estas etapas.

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

    - Selecione **Lançar** no Painel de Ações para lançar a solicitação de todas as linhas relevantes. Se você estiver usando um processo de declaração (quando a opção **Usar processo de declaração** estiver ativada na página **Parâmetros de gerenciamento de reembolso**), apenas as linhas marcadas como **Declarado** são lançadas. Caso contrário, todas as transações de origem para a transação de reembolso selecionada são lançadas. O botão **Lançar** está disponível apenas para transações de reembolso. Ele não está disponível para provisionamento e transações de baixa. Na caixa de diálogo **Lançar**, os campos **Data de** e **Data para** são definidos automaticamente. Defina o campo **Data do lançamento** e selecione **OK**.
    - Para ajustar o valor mostrado para qualquer transação aberta ou não lançada, selecione a transação e siga uma destas etapas:

        - Edite o valor no campo **Valor corrigido**.
        - No painel de ação, selecione **Definir correção**. Em seguida, na caixa de diálogo suspensa que aparece, no campo **Valor corrigido**, insira um valor.

> [!NOTE]
> Se você estiver usando um processo de declarações, quando processar o próximo período, a lista de transações incluirá todas as transações não reivindicadas do lançamento anterior, além de todas as novas transações do período selecionado.

### <a name="view-and-edit-rebate-management-transactions-by-using-the-rebate-workbench"></a>Exibir e editar transações de gerenciamento de reembolsos usando a bancada de reembolsos

Para exibir e editar transações de gerenciamento de reembolsos usando a bancada de reembolsos, siga estas etapas.

1. Acesse **Gerenciamento de reembolso \> Acordos de gerenciamento de reembolso \> Bancada de reembolso**.
1. Defina o campo **Mostrar** como *Não lançado*.
1. A página **Bancada de reembolsos** exibe uma lista das transações. Cada transação fornece detalhes relevantes. Esses detalhes variam, dependendo do tipo de transação. Nessa página, você pode executar as seguintes ações:

    - Para exibir mais informações sobre qualquer transação, selecione-a e depois a guia **Geral**, **Dimensão financeira** ou **Dimensão**.
    - Se você estiver usando um processo de declarações, poderá marcar transações como declaradas ou não declaradas. Selecione as linhas relevantes e, no Painel de Ações, na guia **Bancada de reembolso**, selecione um dos seguintes comandos. (Você habilita os processos de declarações na página [**Parâmetros de gerenciamento de reembolso**](rebate-management-parameters.md).)

        - **Definir declaradas** – Marque as transações selecionadas como declaradas.
        - **Definir não declaradas** – Marque as transações selecionadas como não declaradas.

    - Para lançar a declaração para uma ou mais linhas, selecione as linhas relevantes. Em seguida, no Painel de Ações, na guia **Bancada de reembolso**, selecione **Lançar**. O botão **Lançar** está disponível para transações de provisionamento, reembolso e baixa. Na caixa de diálogo **Lançar**, os campos **Data de** e **Data para** são definidos automaticamente. Defina o campo **Data do lançamento** e selecione **OK**.
    - Para ajustar o valor mostrado para qualquer transação aberta ou não lançada, selecione a transação e siga uma destas etapas:

        - Edite o valor no campo **Valor corrigido**.
        - No Painel de Ações, na guia **Bancada de reembolso**, selecione **Definir correção**. Em seguida, na caixa de diálogo suspensa que aparece, no campo **Valor corrigido**, insira um valor.

> [!NOTE]
> Se você estiver usando um processo de declarações, quando processar o próximo período, a lista de transações incluirá todas as transações não reivindicadas do lançamento anterior, além de todas as novas transações do período selecionado.

## <a name="post-rebates-transactions"></a>Lançar transações de reembolso

Para lançar o valor de um provisionamento processado, valor de gerenciamento de reembolso e baixa, é necessário executar o processo de lançamento. O processo de lançamento marca as transações de provisionamento, gerenciamento de reembolso, ou transações de baixa como lançadas, e cria a transação de destino. Se você não tiver que revisar a transação de destino, essas transações podem ser configuradas para que sejam lançadas automaticamente.

### <a name="set-up-the-system-to-post-all-target-transactions-automatically"></a>Configurar o sistema para lançar todas as transações de destino automaticamente

Para configurar o sistema para lançar todas as transações de destino assim que forem geradas por um provisionamento de lançamento, valor de gerenciamento de reembolso e baixa, ative a opção **Lançar diários automaticamente** e/ou **Lançar automaticamente faturas de texto livre** na página **Parâmetros de gerenciamento de reembolso**. Para obter mais informações, consulte [Parâmetros de gerenciamento de reembolsos](rebate-management-parameters.md).

### <a name="post-transactions-for-all-lines-for-one-or-more-deals"></a>Lançar transações para todas as linhas para uma ou mais negociações

Depois de ter processado as negociações relevantes, siga estas etapas para revisar e lançar as transações geradas para todas as linhas de uma ou mais negociações.

1. Abra a [página da lista de negociações de reembolso](rebate-management-deals.md) para o tipo de negociação com o qual você deseja trabalhar.
1. Selecione a linha para cada negociação que deseja lançar (ou abra a negociação que deseja lançar).
1. No Painel de Ações, na guia **Negociações de gerenciamento de reembolsos**, no grupo **Gerar**, selecione um dos seguintes comandos:

    - **Lançar \> Provisão** – lançar transações de competências disponíveis criadas por você.
    - **Lançar \> Gerenciamento de reembolso** – lançar transações de reembolso disponíveis criadas por você.
    - **Lançar \> Baixa** – lançar transações de baixa disponíveis criadas por você.

1. Na caixa de diálogo que aparece, defina o campo **Data do lançamento**. Em seguida, defina os campos **Data de** e **Data até** para definir o intervalo de dados para as transações que devem ser lançadas.
1. Selecione **OK** para lançar as transações.

### <a name="post-transactions-for-one-or-more-specific-deal-lines-for-a-selected-deal"></a>Lançar transações para uma ou mais linhas de negociação específicas para uma negociação selecionada

Depois de ter processado as negociações relevantes, siga estas etapas para revisar e lançar as transações geradas para uma ou mais linhas de negociação específica para uma negociação selecionada. Este procedimento é aplicável somente para as negociações nas quais o campo **Reconciliar por** está definido como *Linha*.

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

    - Acesse **Gerenciamento de reembolsos \> Tarefas periódicas \> Lançar \> Provisão** para lançar transações de competência disponíveis criadas por você.
    - Acesse **Gerenciamento de reembolsos \> Tarefas periódicas \> Lançar \> Gerenciamento de reembolso** para lançar transações de competência disponíveis criadas por você.
    - Acesse **Gerenciamento de reembolso \> Tarefas periódicas \> Lançar \> Baixa** para lançar transações de baixa disponíveis criadas por você.

1. Na caixa de diálogo exibida, na guia rápida **Parâmetros**, na seção **Período**, defina o campo **Data de lançamento**. Em seguida, defina os campos **Data de** e **Data até** para definir o intervalo de dados para as transações que devem ser lançadas.
1. Na seção **Período de Garantia**, defina os campos **Data - de** e **Data - até** para definir o intervalo de datas para garantias que devem ser lançadas.
1. Na guia rápida **Registros a serem incluídos**, você pode configurar filtros para limitar o conjunto de negociações que o trabalho em lotes processará. Essas configurações funcionam da mesma forma que funcionam para outros tipos de trabalhos em lotes.
1. Na guia rápida **Executar em segundo plano**, você pode configurar as opções de processamento e programação de lote, conforme necessário. Essas configurações funcionam da mesma forma que funcionam para outros tipos de trabalhos em lotes.
1. Selecione **OK** para executar e/ou programar o cálculo.

### <a name="post-transactions-by-using-the-rebate-workbench"></a>Lançar transações usando a bancada de reembolso

Depois de processar as transações de provisão, reembolso ou baixa, siga estas etapas para usar a bancada de reembolso para revisar e lançar as transações geradas para uma ou mais linhas de transação específicas para todas as negociações.

1. Acesse **Gerenciamento de reembolso \> Acordos de gerenciamento de reembolso \> Bancada de reembolso**.
1. Na grade, marque a linha para cada linha de transação que você deseja lançar. Você pode selecionar transações de provisão, reembolso e/ou baixa. As seguintes regras são aplicadas:

    - O sistema também lançará todas as linhas que têm o mesmo valor **Número de transação de reembolso** que as linhas selecionadas.
    - O sistema não lançará linhas de transação de *Reembolso* que não estejam marcados como declaradas.
    - Se você selecionar linhas que já foram lançadas, o sistema ignorará as linhas lançadas.
    - O botão **Lançar** só estará disponível se você selecionar pelo menos uma linha não lançada.

1. No Painel de Ação, na guia **Bancada de reembolso**, no grupo **Processamento**, selecione **Lançar**.
1. Na caixa de diálogo **Lançar**, defina o campo **Data do lançamento**. Os campos **Data de** e **Data até** são definidos automaticamente, com base no valor **Data de** mais antigo e no valor **Data até** mais recente para as linhas selecionadas.
1. Selecione **OK** para lançar as transações.

## <a name="review-rebate-management-journals"></a><a name="review-journals"></a>Revisar diários de gerenciamento de reembolso

Depois que as transações forem lançadas, você poderá revisar os diários, documentos ou itens resultantes. As transações de destino para reembolsos e royalties se baseiam no tipo de pagamento definido no perfil de lançamentos e no tipo de saída do reembolso. Por exemplo, se a saída de reembolso for definida como *Item*, uma ordem de venda será criada para um reembolso do cliente, e uma ordem de compra será criada para um reembolso de fornecedor. Essas ordens podem ser visualizadas através das transações de destino. Como alternativa, se o pagamento for configurado para usar Contas a pagar, uma fatura de fornecedor para o fornecedor configurado no cliente será criada para reembolsos do cliente.

### <a name="review-journals-by-using-the-rebate-deals-list-page"></a>Revisar diários usando a página lista de oportunidades de reembolso

Para revisar as entradas de diário associadas a um acordo de gerenciamento de reembolso, siga estas etapas.

1. Abra a [página da lista de negociações de reembolso](rebate-management-deals.md) para o tipo de negociação com o qual você deseja trabalhar.
1. Selecione a negociação para o qual inspecionar entradas de diário.
1. No Painel de Ações, na guia **Negociações de gerenciamento de reembolso**, no grupo **Transações**, selecione **Transações** ou **Garantir transações**, dependendo do tipo de transação que você deseja exibir.
1. Defina o campo **Mostrar** como *Tudo* ou *Lançado*.
1. Localize e selecione a coleção de transações que deseja inspecionar e, no Painel de Ação, selecione um dos botões a seguir. (Esses botões estão disponíveis somente quando há lançamentos relevantes para a coleção de transações selecionada.)

    - **Transações de destino** – revise os diários relevantes e outros tipos de documentos que foram gerados pela negociação selecionada.
    - **Itens** – Revise as ordens de venda ou ordens de compra relevantes que foram gerados pela negociação selecionada.

1. Uma lista de diários, documentos ou itens relevantes é exibida. Para exibir mais informações sobre qualquer diário, documento ou item, selecione sua linha e, no Painel de Ação, selecione **Exibir detalhes**.

### <a name="review-journals-by-using-the-rebate-workbench"></a>Revisar diários usando a bancada de reembolso

Para revisar diários usando a bancada de reembolso, siga estas etapas.

1. Acesse **Gerenciamento de reembolso \> Acordos de gerenciamento de reembolso \> Bancada de reembolso**.
1. Defina o campo **Mostrar** como _Tudo_ ou _Lançado_.
1. Encontre e selecione a linha que você deseja inspecionar. Em seguida, no Painel de Ação, na guia **Bancada de reembolso**, no grupo **Visualizar**, selecione **Transações alvo**. Este botão só ficará disponível se houver lançamentos relevantes para a linha selecionada.
1. Uma lista de diários, documentos ou itens relevantes é exibida. Para exibir mais informações sobre qualquer diário, documento ou item, selecione sua linha e, no Painel de Ação, selecione **Exibir detalhes**.

## <a name="rebate-management-transactions-on-the-deduction-workbench"></a>Transações de gerenciamento de reembolsos na bancada de dedução

Quando você lança uma transação de gerenciamento de reembolso que tem um dos seguintes valores **Tipo de pagamento**, o sistema cria um diário de dedução de cliente ou uma fatura de texto livre para a conta de cliente relevante:

- Deduções do cliente
- Deduções de cliente da fatura de imposto
- Gasto comercial
- Relatório

Depois que uma transação de destino é criada e lançada, ela estará disponível como uma transação aberta na página **Bancada de dedução** (**Vendas e marketing \> Bonificações comerciais \> Deduções \> de Bancada de dedução**). As transações abertas têm um valor **Tipo de declaração** de *Gerenciamento de reembolso* e um valor **Número de transação de reembolsos** está disponível para habilitar o rastreamento. A data é definida como a data de lançamento da transação de destino de gerenciamento de reembolsos. Para usar a bancada de dedução para liquidar transações abertas em deduções existentes para a mesma conta de cliente, selecione **Manter \> Corresponder** no painel de ações.

Para obter mais informações, consulte [Gerenciar deduções usando a bancada de dedução](deduction-workbench.md).

## <a name="purge-unposted-transactions"></a>Excluir transações não lançadas

Depois de processar as transações de provisão, reembolso ou baixa, siga estas etapas para limpar as transações não lançadas selecionadas.

1. Acesse **Gerenciamento de reembolso \> Acordos de gerenciamento de reembolso \> Bancada de reembolso**.
2. Defina o campo **Mostrar** como *Não lançado*.
3. Localize e selecione as transações a serem excluídas. Depois, no Painel de Ação, na guia **Bancada de reembolso**, no grupo **Processamento**, selecione **Limpar**.
4. Selecione **OK** para excluir as transações não lançadas.

## <a name="cancel-a-posted-provision"></a>Cancelar uma provisão lançada

Depois de ter processado e lançado uma provisão, siga estas etapas para cancelar as transações de provisão lançadas.

1. Acesse **Gerenciamento de reembolso \> Acordos de gerenciamento de reembolso \> Bancada de reembolso**.
2. Defina o campo **Mostrar** como *Lançado*.
3. Localize e selecione as transações de provisão a serem canceladas. Depois, no Painel de Ação, na guia **Bancada de reembolso**, no grupo **Processamento**, selecione **Cancelar provisão**.
4. Selecione **OK** para reverter as transações.

Esses reversões de provisão também ficarão visíveis nos [Diários de gerenciamento de reembolsos](#review-journals) relevantes.
