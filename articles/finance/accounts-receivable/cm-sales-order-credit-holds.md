---
title: Retenções de crédito de ordens de venda
description: Este tópico descreve a configuração das regras usadas para colocar uma ordem de venda em bloqueio de crédito.
author: mikefalkner
manager: AnnBe
ms.date: 01/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschloma
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 102ea4285407a4f4985cc8dd46ebc1ad21fc6f67
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4440223"
---
# <a name="credit-holds-for-sales-orders"></a>Retenções de crédito de ordens de venda
[!include [banner](../includes/banner.md)]

Este tópico descreve a configuração das regras usadas para colocar uma ordem de venda em bloqueio de crédito. As regras de bloqueio de gerenciamento de crédito podem ser aplicadas a um cliente individual ou a um grupo de clientes. As regras de bloqueio definem respostas para as seguintes circunstâncias:

1. Número de dias de atraso
2. Status da conta
3. Condições de pagamento
4. Limite de crédito expirado
5. Valor vencido
6. Valor da ordem de venda
7. Parte do crédito disponível usada

Além disso, há dois parâmetros que controlam outros cenários que bloquearão uma ordem de venda

1. Alteração nas condições de pagamento
2. Alteração nos descontos de liquidação

## <a name="set-up-blocking-rules-and-exclusion-rules"></a>Configurar regras de bloqueio e de exclusão

Quando um cliente inicia uma transação de venda, as informações na ordem de venda são revisadas em relação a um conjunto de regras de bloqueio que orientam a decisão de estender ou não o crédito ao cliente e permitir que a venda avance. Você também pode definir exclusões que substituirão as regras de bloqueio e permitirão que uma ordem de venda seja processada. Você pode configurar regras de bloqueio e de exclusão na página **Gerenciamento de crédito > Configuração > Configuração de gerenciamento de crédito > Regras de bloqueio**.

### <a name="days-overdue"></a>Dias vencidos

Abra a guia **Dias vencidos** se a regra de bloqueio se aplicar ao cliente com uma ou mais faturas vencidas há um determinado número de dias.
1. Selecione o intervalo de clientes para o qual esta regra é válida (**Válida para**).
   - Selecione **Tabela** se a regra se aplica a um cliente específico.
   - Selecione **Grupo** se a regra é aplicada no nível de grupo de clientes. 
   - Selecione **Todos** se a regra se aplica a todos os clientes.
2. Depois de especificar o intervalo, você deve especificar a **Conta/grupo** para uso no intervalo.
   - Para o intervalo **Tabela**, a pesquisa fornecerá uma lista de clientes a serem selecionados. 
   - Selecione um **Grupo** se a regra se aplica a um grupo de crédito de cliente.
   - Selecione **Todos** se a regra se aplica a todos os clientes. 
3. Selecione **Grupo de risco** para usar critérios para aplicar um bloqueio de gerenciamento de crédito aos clientes agrupados por um conjunto de fatores em comum, como a classificação Dun e Bradstreet, o número de anos em que eles estão na empresa, há quanto tempo eles são seus clientes e assim por diante.  
4. Selecione o tipo de regra que você está configurando. A opção **Bloqueio** criará uma regra que bloqueia uma ordem. A opção **Exclusão** criará uma regra que impedirá que outra regra bloqueie uma ordem. 
5. Selecione um **Tipo de valor**. A entrada padrão é um número fixo de dias. Se você estiver criando uma exclusão, poderá especificar um número fixo de dias ou um valor em vez disso. 
6. Digite o número de dias de **Atraso** que será permitido para a regra de bloqueio selecionada antes que uma ordem seja colocada em bloqueio de gerenciamento de crédito para revisão. O número de dias vencidos representa um número de dias de carência a mais que são adicionados ao número de dias além da data de vencimento do pagamento que a fatura pode ter antes de ser considerada vencida. Se você especificou o **Tipo de valor** como um valor para uma exclusão, insira um valor e uma moeda para esse valor.

### <a name="accounts-status"></a>Status da conta

Abra a guia **Status da conta** se a regra de bloqueio se aplica a um cliente com o status de conta selecionado.
1. Selecione o tipo de regra que você está configurando.  **Bloqueio** criará uma regra que bloqueia uma ordem. **Exclusão** cria uma regra que impedirá que uma regra bloqueie uma ordem. 
2. Selecione o **Status da conta** que fará com que a regra coloque uma ordem de venda em espera ou a exclua.

### <a name="terms-of-payment"></a>Condições de pagamento

Selecione **Condições de pagamento** se a regra de bloqueio se aplica à condição de pagamento selecionada.
1. Selecione o tipo de regra que você está configurando.  **Bloqueio** criará uma regra que bloqueia uma ordem. **Exclusão** cria uma regra que impedirá que uma regra bloqueie uma ordem. 
2. Selecione as **Condições de pagamento** que farão com que a regra coloque uma ordem de venda em espera ou a exclua.

### <a name="credit-limit-expired"></a>Limite de crédito expirado

Abra a guia **Limite de crédito expirado** se a regra de bloqueio se aplica a clientes com limites de crédito que venceram.
1. Selecione o intervalo de clientes para o qual esta regra é válida (**Válida para**).
   - Selecione **Tabela** se a regra se aplica a um cliente específico.
   - Selecione **Grupo** se a regra é aplicada no nível de grupo de Clientes. 
   - Selecione **Todos** se a regra se aplica a todos os clientes.
2. Uma vez especificado o intervalo, você deve especificar a **Conta/grupo** para uso no intervalo.
   - Para o intervalo **Tabela**, a pesquisa fornecerá uma lista de clientes para seleção. 
   - Selecione um **Grupo** se a regra se aplica a um grupo de gerenciamento de crédito de cliente.
   - Selecione **Todos** se a regra se aplica a todos os clientes. 
3. Selecione um **Grupo de risco** para limitar ainda mais a lista de clientes que serão colocados em bloqueio de gerenciamento de crédito. 
4. Selecione o tipo de regra que você está configurando. 
   - Selecione **Bloqueio** para criar uma regra que bloqueie uma ordem. 
   - Selecione **Exclusão** para criar uma regra que impedirá que outra regra bloqueie uma ordem. 
5. Insira o **Limite de crédito diário expirado** para a regra de bloqueio selecionada antes que uma ordem seja colocada em bloqueio de gerenciamento de crédito. O número de dias vencidos representa os dias de carência a mais que são adicionados ao número de dias que o limite de crédito expirou.

### <a name="overdue-amount"></a>Valor vencido

Abra a guia **Valor vencido** se a regra de bloqueio se aplica a clientes com valores vencidos.
1. Selecione o intervalo de clientes para o qual esta regra é válida (**Válida para**).
   - Selecione **Tabela** se a regra se aplica a um cliente específico.
   - Selecione **Grupo** se a regra é aplicada no nível de grupo de Clientes. 
   - Selecione **Todos** se a regra se aplica a todos os clientes.
2. Uma vez especificado o intervalo, você deve especificar a **Conta/grupo** para uso no intervalo.
   - Para o intervalo **Tabela**, a pesquisa fornecerá uma pesquisa de clientes. 
   - Selecione um **Grupo** se a regra se aplica a um grupo de gerenciamento de crédito de cliente.
   - Selecione **Todos** se a regra se aplica a todos os clientes. 
3. Selecione um **Grupo de risco** se quiser limitar ainda mais a lista de clientes a serem colocados em bloqueio de gerenciamento de crédito. 
4. Selecione o tipo de regra que você está configurando. 
   - Selecione **Bloqueio** para criar uma regra que bloqueie uma ordem. 
   - Selecione **Exclusão** para criar uma regra que impedirá que outra regra bloqueie uma ordem. 
5. Insira o **Valor vencido** para a regra de bloqueio selecionada antes que uma ordem seja colocada em bloqueio de gerenciamento de crédito para revisão. 
6. Selecione o **Tipo de valor** que define o tipo de valor a ser usado para também testar quanto do limite de crédito foi usado. As regras de bloqueio exigem uma porcentagem, mas uma exclusão pode ter um valor fixo ou uma porcentagem. O limite está relacionado ao limite de crédito.
7. Insira o valor de **Limite de limite de crédito** para a regra selecionada antes que um cliente seja colocado em bloqueio de gerenciamento de crédito. Pode ser um valor ou uma porcentagem com base no tipo de valor selecionado.
8. A regra verifica se o **Valor vencido** foi excedido e se o **Limite de limite de crédito** foi excedido. 

### <a name="sales-order"></a>Ordem de venda 

Selecione **Ordem de venda** se a regra de bloqueio se aplica ao valor da ordem de venda.
1. Selecione o intervalo de clientes para o qual esta regra é válida (**Válida para**).
   - Selecione **Tabela** se a regra se aplica a um cliente específico.
   - Selecione **Grupo** se a regra é aplicada no nível de grupo de Clientes. 
   - Selecione **Todos** se a regra se aplica a todos os clientes.
2. Uma vez especificado o intervalo, você deve especificar a **Conta/grupo** para uso no intervalo.
   - Para o intervalo **Tabela**, a pesquisa fornecerá uma pesquisa de clientes. 
   - Selecione um **Grupo** se a regra se aplica a um grupo de gerenciamento de crédito de cliente.
   - Selecione **Todos** se a regra se aplica a todos os clientes. 
3. Selecione um **Grupo de risco** se quiser limitar ainda mais a lista de clientes a serem colocados em bloqueio de gerenciamento de crédito. 
4. Selecione o tipo de regra que você está configurando.  
   - Selecione **Bloqueio** para criar uma regra que bloqueie uma ordem. 
   - Selecione **Exclusão** para criar uma regra que impedirá que outra regra bloqueie uma ordem. 
5. Insira o **Valor da ordem de venda** para a regra de bloqueio selecionada antes que uma ordem seja colocada em bloqueio de gerenciamento de crédito. 

A regra de ordem de venda inclui uma configuração adicional que substitui todas as outras regras. Para criar uma exclusão que liberará a ordem de venda sem aplicar nenhuma outra regra, marque a caixa de seleção **Liberar ordem de venda** na linha de exclusão.

### <a name="credit-limit-used"></a>Limite de crédito usado

Selecione **Limite de crédito usado** se a regra de bloqueio se aplica ao valor de limite de crédito do cliente que foi utilizado.
1. Selecione o intervalo de clientes para o qual esta regra é válida (**Válida para**).
   - Selecione **Tabela** se a regra se aplica a um cliente específico.
   - Selecione **Grupo** se a regra é aplicada no nível de grupo de Clientes. 
   - Selecione **Todos** se a regra se aplica a todos os clientes.
2. Uma vez especificado o intervalo, você deve especificar a **Conta/grupo** para uso no intervalo.
   - Para o intervalo **Tabela**, a pesquisa fornecerá uma pesquisa de clientes. 
   - Selecione um **Grupo** se a regra se aplica a um grupo de gerenciamento de crédito de cliente.
   - Selecione **Todos** se a regra se aplica a todos os clientes. 
3. Selecione um **Grupo de risco** se quiser limitar ainda mais a lista de clientes a serem colocados em bloqueio de gerenciamento de crédito. 
4. Selecione o tipo de regra que você está configurando.
   - Selecione **Bloqueio** para criar uma regra que bloqueie uma ordem. 
   - Selecione **Exclusão** para criar uma regra que impedirá que outra regra bloqueie uma ordem. 
5. Selecione o **Limite restante** que define a porcentagem do limite de crédito que bloqueará a ordem de venda. Se o valor de uma ordem aumentar o valor do limite de crédito usado acima da porcentagem, a ordem será colocada em espera. 

## <a name="put-a-sales-order-on-hold-based-on-other-criteria"></a>Colocar uma ordem de venda em espera com base em outros critérios
  
### <a name="rank-payment-terms"></a>Classificar condições de pagamento  

Você pode forçar a execução das regras de controle de crédito quando as condições de pagamento são alteradas. Você deve classificar as condições de pagamento e atribuir um valor de classificação a elas. Se você alterar as condições de pagamento na ordem para as condições de pagamento com classificação mais elevada do que as antigas, a ordem será enviada ao gerenciamento de crédito e terá de ser aprovada.

Você pode configurar as classificações de condições de pagamento na página **Gerenciamento de crédito > Configuração > Configuração de gerenciamento de crédito > Classificar condições de pagamento**.

1. Selecione as condições de pagamento no campo **Condições de pagamento** para classificação; quando você selecionar uma condição, a descrição será exibida no campo **Descrição**.
2. Selecione a classificação da condição no campo **Classificação**. Os valores são todos relativos entre si, por isso você pode usar 1, 2, 3 ou 10, 20, 30. Você também pode usar o mesmo valor para a maioria das condições de pagamento de modo que somente uma ou duas condições de pagamento disparem a verificação de crédito.

### <a name="rank-settlement-discounts"></a>Classificar descontos de liquidação   

Você pode forçar a execução das regras de controle de crédito quando os descontos de liquidação são alteradas. Você deve classificar os descontos de liquidação e atribuir um valor de classificação a eles. Se você alterar os descontos de liquidação na ordem para os descontos de liquidação com classificação mais elevada do que os antigos, a ordem será enviada ao gerenciamento de crédito e terá de ser aprovada.

É possível configurar as classificações de condições de pagamento na página **Gerenciamento de crédito > Configuração > Configuração de gerenciamento de crédito > Classificar descontos de liquidação**.

1. Selecione o **Desconto à vista** que você deseja classificar. A **Descrição** do desconto de liquidação será exibida.
2. Selecione o valor de **Classificação**. Os valores são todos relativos entre si, por isso você pode usar 1, 2, 3 ou 10, 20, 30. Você também pode usar o mesmo valor para a maioria dos descontos de liquidação de modo que somente um ou dois descontos de liquidação disparem a verificação de crédito.

## <a name="sequence-the-application-of-rules"></a>Sequenciar a aplicação de regras

As regras são executadas em uma ordem específica, que você altera de acordo com as necessidades da organização. 

- Uma instância das regras de exclusão de ordem de venda permite substituir todas as regras que possam bloquear uma ordem de venda. Crie uma regra de exclusão de ordem de venda e selecione a opção **Liberar Ordem de venda**. A ordem não será colocada em espera se a regra de exclusão for verdadeira e se nenhuma outra regra for verificada.
- As regras de bloqueio podem colocar a ordem em espera.
- As regras de exclusão são executadas depois das regras de bloqueio. As regras de exclusão afetarão somente a regra na qual elas estão definidas. 
- As regras de bloqueio e de exclusão são executadas na ordem de Tabela, Grupo e Todos. Devido a essa ordem de processamento, é possível ter uma regra de bloqueio no nível Todos, que não será executada porque uma regra de exclusão no nível Tabela ou Grupo é executada.
- As exclusões não substituem a regra de bloqueio se elas estiverem no mesmo nível. Por exemplo, uma regra de exclusão no nível de grupo não substituirá a regra de bloqueio no nível de grupo. Você não precisará configurar exclusões no nível Todos, exceto como indicado acima com a instância única da regra de exclusão de ordem de venda. 

O comportamento da regra **Limite de crédito usado** será alterado com base nas configurações do parâmetro **Verificar o limite de crédito da ordem de venda** encontrado no formulário de parâmetros Crédito e Cobranças.
- Se o parâmetro for definido como Não, a regra Limite de crédito usado não será executada.
- Se o parâmetro for definido como Sim e a **Mensagem ao ser excedido o limite de crédito** for definida como Aviso, você receberá um aviso quando o limite de crédito for excedido. As regras **Limite de crédito usado** serão executadas para verificar se há regras que você deseja executar. No entanto, para este cenário, normalmente você não adicionaria regras.
- Se o parâmetro for definido como Sim e a **Mensagem ao ser excedido o limite de crédito** for definida como Erro, o limite de crédito será verificado e a ordem será colocada em espera se o limite for excedido. Além disso, as regras **Limite de crédito usado** serão executadas para verificar se existem outras regras que devem ser executadas. Uma mensagem de erro não será exibida, mas será mostrado o motivo de bloqueio **Limite de crédito excedido**. 

## <a name="settings-that-will-change-the-way-an-order-is-placed-on-hold"></a>Configurações que mudarão a forma como uma ordem é colocada em espera

É possível excluir ordens do gerenciamento de crédito mesmo se há regras em vigor. 

- Se você alterar as configurações **Excluir cliente do gerenciamento de crédito** na FastTab **Todos os clientes > Selecionar um cliente > Crédito e cobranças** como **Sim**, nenhuma ordem desse cliente será processada
- Se você alterar o valor **Excluir do gerenciamento de crédito** no **cabeçalho de ordens de venda** na **FastTab Gerenciamento de crédito** como **Sim**, as regras de gerenciamento de crédito não serão processadas. Essa configuração só pode ser feita pelo auxiliar de gerenciamento de crédito ou pelo gerente de crédito.

## <a name="processing-orders-on-hold-using-the-credit-management-hold-list"></a>Processando ordens em espera usando a lista de bloqueio de gerenciamento de crédito

A lista de bloqueio de Gerenciamento de crédito permite que os gerentes de crédito vejam todas as ordens de venda colocadas em espera e removam os bloqueios quando os problemas de crédito forem resolvidos. A página **Lista de bloqueio de gerenciamento de crédito** mostra todas as ordens de venda que foram colocadas em espera. Você pode ver a lista de bloqueio na página **Todos os bloqueios de crédito** (**Gerenciamento de crédito > Lista de bloqueio de gerenciamento de crédito > Todos os bloqueios de crédito**).
As ordens de venda de todas as entidades legais são enviadas para a mesma lista de bloqueio de gerenciamento de crédito, oferecendo uma exibição centralizada de todas as transações que exigem atenção. Os usuários verão somente as informações das entidades legais que eles têm permissão para acessar.

Uma ordem de venda pode ser colocada na lista de bloqueio pelos seguintes motivos:
1. O cliente tem uma fatura que está vencida há um determinado número de dias. 
2. A ordem tem um status de conta específico.
3. A ordem tem condições de pagamento específicas.
4. O cliente tem um limite de crédito expirado.
5. O cliente tem um valor vencido e usou uma porcentagem especificada do limite de crédito
6. A ordem de venda excede um determinado valor.
7. O cliente excedeu uma determinada porcentagem do limite de crédito.
8. As condições de pagamento diferem das condições de pagamento padrão do cliente.
9. Os descontos de liquidação diferem do desconto de liquidação padrão do cliente.

O motivo do bloqueio de cada ordem de venda na lista de bloqueios é exibido. Se houver mais de um motivo para o bloqueio, ele será mostrado como **Múltiplo**. Você pode usar o menu **Motivos do bloqueio** do Painel de Ação para ver todos os motivos pelos quais a ordem de venda foi colocada em espera. Você também pode ver os **Motivos do bloqueio** em um Quadro de Fatos.

### <a name="releasing-orders-from-the-hold-list-for-processing"></a>Liberando ordens da lista de bloqueio para processamento

Depois que você pesquisar e mitigar os motivos do bloqueio, poderá liberar as ordens de venda para continuar o processamento.

1) Selecione uma linha na lista de bloqueio. É possível liberar várias ordens selecionando mais de uma linha.
2) Selecione um **Motivo da liberação** para a ordem selecionada para liberação.  
3) Insira a **Data de revisão** de cada ordem selecionada para liberação.  
4) Selecione o menu **Liberar** no painel de ação para liberar uma ordem. Este menu só ficará disponível depois que as transações forem selecionadas. Duas opções são apresentadas ao usuário:
   - Selecione **Com lançamento** para remover o bloqueio e lançar o documento usando o mesmo processo de lançamento que foi utilizado quando ele foi colocado em espera. Por exemplo, se a confirmação da ordem de venda foi colocada em espera, a confirmação será concluída após a liberação. O formulário lançamento da ordem de venda será exibido, permitindo que o usuário lance a confirmação.
   - Selecione **Sem lançamento** para remover o bloqueio sem processamento adicional. A ordem de venda pode ser lançada manualmente.

### <a name="rejecting-orders-in-the-hold-list"></a>Rejeitando ordens na lista de bloqueio
Você pode usar o menu **Rejeitar** do painel de ação para rejeitar uma ordem de venda
1. Selecione uma linha na lista de bloqueio. É possível liberar várias ordens selecionando mais de uma linha.
2. A ordem será removida da lista de bloqueio, e o cabeçalho da ordem de venda será atualizado para mostrar que a ordem foi rejeitada.

### <a name="automatically-releasing-credit-management-holds"></a>Liberando bloqueios de gerenciamento de crédito automaticamente
As ordens de venda são colocadas na lista de bloqueio com base nas regras de bloqueio. No entanto, alguns motivos para os bloqueios podem mudar com o tempo se a ordem de venda permanecer na lista de bloqueio por um determinado período. Por exemplo, um cliente pode pagar sua conta, liberando o limite de crédito. 

Você pode usar o menu **Avaliar para liberação** para revisar as ordens de venda na lista de bloqueio e liberá-las automaticamente se o motivo do bloqueio foi atenuado.
1.  Selecione o menu **Avaliar para liberação**
2.  Selecione **Processar regras de bloqueio** para revisar todas as ordens de venda. Selecione **Processar regras de bloqueio para linhas selecionadas** para revisar somente as linhas selecionadas.
3. Será exibido um controle deslizante para que você possa selecionar um único cliente. Deixe a lista suspensa de clientes em branco para todos os clientes. 
4. Quando você clica em OK, o processo é executado em segundo plano e você pode continuar trabalhando em outras tarefas. Se você selecionar o processamento em lotes antes de clicar em OK, o processo será executado em lote quando você clicar em OK. Pode levar algum tempo para processar as ordens em espera na lista, por isso use Atualizar para atualizar o status das ordens. 
5.  Se um motivo de bloqueio não for mais aplicável a uma ordem, será considerado inválido e você não verá mais uma marca de seleção ao lado dele quando exibir os motivos de bloqueio.
6.  Se todos os motivos de bloqueio forem desmarcados, um novo motivo, **Pronta para liberação**, será adicionado à lista de motivos de bloqueio. A ordem de venda pode ser liberada automaticamente.
7.  Se o parâmetro **Liberado automaticamente** na guia **Crédito e cobranças > Configuração > Parâmetros de crédito e cobranças > Crédito > Liberação automática** for definido como **Com lançamento**, você será solicitado a lançar usando o formulário de lançamento do documento bloqueado.
8.  Se o parâmetro **Liberado automaticamente** na guia **Crédito e cobranças > Configuração > Parâmetros de crédito e cobranças > Crédito > Liberação automática** for definido como **Sem lançamento**, você deverá lançar a ordem manualmente.

### <a name="credit-management-approval-workflow"></a>Fluxo de trabalho de aprovação de gerenciamento de crédito

Você também pode criar **Fluxos de trabalho de gerenciamento de crédito** para controlar a liberação de bloqueios de crédito. Depois que você configurar o fluxo de trabalho usando a página **Gerenciamento de crédito > Configuração > Fluxos de trabalho de gerenciamento de crédito**, as ordens marcadas para liberação ou rejeição serão enviadas para o fluxo de trabalho, onde deverão ser aprovadas primeiro antes de serem liberadas ou rejeitadas. 

Se você incluir as tarefas para liberação com lançamento ou liberação sem lançamento no fluxo de trabalho, a aprovação do fluxo de trabalho também liberará a ordem de venda. No entanto, se houver uma falha no processo de liberação devido a informações de configuração ausentes ou outras causas, será necessário cancelar a ordem de venda do fluxo de trabalho, corrigir o problema que causou a falha e enviar a ordem para o fluxo de trabalho novamente.

Se você não incluir as tarefas para liberação com lançamento ou liberação sem lançamento no fluxo de trabalho, o processo de aprovação do fluxo de trabalho simplesmente permitirá que você libere a ordem de venda manualmente quando a aprovação for concluída.

### <a name="forced-credit-hold"></a>Bloqueio de crédito forçado  
  
Às vezes, pode ser necessário bloquear ordens de venda mesmo que elas não atendam aos critérios das regras de bloqueio. Por exemplo, um gerente de crédito pode ser notificado sobre um problema com o cliente não relacionado a crédito e decidir colocar as ordens em espera manualmente de imediato até que o problema seja resolvido. Você pode forçar manualmente uma ordem de venda para ser colocada em espera se essa situação ocorrer.

1. Abra a ordem de venda que deseja colocar em espera.  
2. Selecione **Forçar bloqueio de crédito** na guia **Gerenciamento de crédito** do painel de ação **Gerenciamento de crédito**.
3. Selecione um **Motivo do Bloqueio Forçado**.
4. Clique em **OK**. A ordem de venda voltará para a lista de bloqueio de gerenciamento de crédito.

Também é possível forçar várias ordens a serem colocadas em espera usando a página **Gerenciamento de crédito > Tarefas periódicas > Forçar Bloqueio de Crédito**. Por exemplo, você pode colocar em espera todas as ordens de venda de um cliente específico.
1. Selecione o **Motivo do bloqueio forçado**. 
2. Clique em **Registros a serem incluídos** para selecionar as ordens de venda a serem colocadas em espera. 
3. Clique em **OK** para processar as ordens de venda selecionadas.

As ordens de venda que foram colocadas em espera forçada não podem ser processadas com o fluxo de trabalho.

#### <a name="releasing-orders-that-were-added-to-the-credit-management-hold-list-with-a-forced-credit-hold"></a>Liberando ordens adicionadas à lista de bloqueio de gerenciamento de crédito com um bloqueio de crédito forçado
As ordens de venda que têm um motivo de bloqueio forçado não podem ser liberadas automaticamente. Se a ordem de venda foi colocada em espera forçada e você usou um processo que libera as ordens de venda automaticamente, ela será mostrada como **Pronta para liberação** e permanecerá na lista de bloqueio. Você deve usar o menu **Liberar** para liberar a ordem.
 
## <a name="free-text-invoices-orders-and-project-invoice-support-in-credit-management"></a>Suporte para faturas de texto livre, ordens e fatura de projeto no Gerenciamento de crédito 
No momento, o gerenciamento de crédito só pode ser usado para ordens de venda. As faturas de texto livre, as ordens do ponto de venda e as ordens de call center usarão os limites de crédito temporários e os seguros/garantias que você adicionar para ajustar o limite de crédito. Elas não usarão as regras de bloqueio e não serão colocadas na lista de bloqueio se houver um problema de limite de crédito.

Não há suporte para faturas de projeto no gerenciamento de crédito.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]