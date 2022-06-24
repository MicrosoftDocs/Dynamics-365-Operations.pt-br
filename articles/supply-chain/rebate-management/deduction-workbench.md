---
title: Gerenciar deduções usando a bancada de dedução
description: Este artigo descreve como usar o workbench de dedução de forma que seja possível processar pagamentos de clientes que incluem deduções.
author: sherry-zheng
ms.date: 08/02/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 607ad528b56d1f0c9a78e113f67c920cdae6e620
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8873598"
---
# <a name="manage-deductions-using-the-deduction-workbench"></a>Gerenciar deduções usando a bancada de dedução

[!include [banner](../includes/banner.md)]

Este artigo descreve como usar o workbench de dedução de forma que seja possível processar pagamentos de clientes que incluem deduções.

Um cliente que tem direito a um reembolso pode decidir não aguardar o pagamento do reembolso. Em vez disso, o cliente pode enviar um pagamento que inclui a dedução do valor do reembolso. Para lidar com esse tipo de transação, é possível usar a bancada de dedução para corresponder as deduções e abrir as transações de crédito, dividir deduções, negar deduções e dar baixa em deduções.

> [!NOTE]
> A bancada de dedução faz parte da funcionalidade de vendas e marketing do Microsoft Dynamics 365 Supply Chain Management há muito tempo. No entanto, agora ele foi aprimorado para que também funcione com o módulo **Gerenciamento de reembolsos** mais recente. Este artigo descreve como usar recursos antigos e recursos de gerenciamento de reembolsos do workbench de dedução. No entanto, se você não [tiver ativado o módulo **Gerenciamento de reembolsos** para seu sistema](rebate-management-enable.md), algumas das funcionalidades descritas aqui não estarão disponíveis para você.

## <a name="prerequisites"></a>Pré-requisitos

### <a name="set-up-the-old-deduction-management-system"></a>Configurar o sistema antigo de gerenciamento de reembolsos

Você pode usar a bancada de dedução com os recursos de gerenciamento de dedução antigos do Supply Chain Management, mesmo que não esteja usando o módulo **Gerenciamento de reembolsos**. No entanto, você deve primeiro preparar o sistema conforme descrito nesta seção.

Para poder usar a bancada de dedução, você deve concluir as tarefas de configuração descritas em [Configurar o gerenciamento de deduções](/dynamicsax-2012/appuser-itpro/set-up-deduction-management). Você também deve ter um determinado tipo de contrato de reembolso configurado para o cliente: seja um desconto do cliente, conforme descrito em [Configurar e manter reembolsos de clientes](/dynamicsax-2012/appuser-itpro/setting-up-and-maintaining-customer-rebates), ou um reembolso comercial.

Se estiver aplicando uma dedução a um reembolso de cliente, você deverá executar estas tarefas:

- [Configure os reembolsos do cliente](/dynamicsax-2012/appuser-itpro/setting-up-and-maintaining-customer-rebates).
- Aprove e processe o reembolso, de forma que você possa usar a bancada de dedução.

Se estiver aplicando uma dedução a um reembolso comercial, você deverá executar estas tarefas:

- Configure os reembolsos de despesas.
- Aplique reembolsos de despesas.

### <a name="configure-accounts-receivable-and-deductions"></a><a name="accounts-receivable-deductions"></a>Configurar contas a receber e deduções

O sistema registra todos os eventos de dedução em um diário de declarações. Portanto, o sistema deve incluir um diário que possa ser usado para essa finalidade. Se você ainda não tiver um diário de declarações, configure-o agora. Esse diário é necessário para criar deduções diretamente na bancada de dedução, na liquidação do cliente ou na página do cliente.

Para configurar um novo diário de declarações para deduções, siga estas etapas.

1. Acesse **Contabilidade \> Configuração do diário \> Nomes de diário**.
1. Selecione **Novo** e defina os campos a seguir para o nome do novo diário:

    - **Nome** - Digite um nome exclusivo para o diário de declarações.
    - **Descrição** – insira uma descrição do novo diário.
    - **Tipo de diário** - Selecione *Diário*.
    - **Série de comprovante** – Atribua uma sequência numérica existente. Outra opção é criar uma nova sequência numérica que tenha o escopo da empresa e atribuí-la ao nome do novo diário.

1. Acesse **Contas a receber \> Configuração \> Parâmetros de contas a receber**.
1. Na guia **Deduções**, na Guia Rápida **Geral**, defina o campo **Nome do diário de declarações** como o nome do diário que você acabou de criar.
1. Na Guia Rápida **Ordem de devolução**, defina os seguintes campos:

    - **Criar ordem de devolução** – Defina esta opção para especificar o que o sistema deve fazer quando uma declaração baseada em quantidade for aprovada:

        - *Sim* - Criar uma ordem de devolução.
        - *Não* – Criar uma ordem de venda negativa.

    - **Criação sem fatura anexada** – Selecione um valor para especificar o que o sistema deve fazer quando uma declaração baseada em quantidade for aprovada, mas nenhuma fatura estiver associada:

        - *Aceitar* - Criar uma ordem de devolução.
        - *Aviso* – Crie uma ordem de devolução, mas mostre a seguinte mensagem de aviso: "a declaração não está anexada a uma fatura".
        - *Erro* – Não criar uma ordem de devolução e exibir a seguinte mensagem de erro: "A declaração não está anexada a uma fatura". A atualização foi cancelada."

    - **Criar ordem de devolução antes da aprovação da dedução** – Defina esta opção como *Sim* se as ordens de devolução puderem ser criadas antes de a solicitação ser aprovada. Essa configuração aplica-se somente a declarações baseadas em quantidade nas quais a opção **Criar ordem de devolução** esteja definida como *Sim*.

### <a name="configure-general-ledger-parameters"></a>Configurar parâmetros de contabilidade

Quando o sistema cria um diário de declarações para uma nova dedução, ele também cria duas novas transações de cliente: uma para compensar o valor da declaração na fatura original e outra para registrar a dívida de um cliente no valor da declaração (porque a declaração ainda não foi aprovada). Portanto, você deve configurar o sistema para que um único comprovante possa ter várias linhas de cliente.

Para permitir que um único comprovante tenha várias linhas de cliente, siga estas etapas.

1. Acesse **Contabilidade \> Configuração do razão \> Parâmetros da contabilidade**.
1. Na guia **Razão**, na Guia Rápida **Geral**, defina a opção **Permitir várias transações em um único comprovante** como *Sim*.
1. Se você receber uma mensagem de aviso, selecione **Fechar** para aceitar a alteração.

### <a name="create-deduction-reasons"></a><a name="deduction-reasons"></a>Criar motivos de dedução

O sistema requer que os usuários especifiquem um motivo para cada dedução que eles inserem diretamente na bancada de dedução, liquidação de cliente ou página de cliente. O motivo determina como a dedução é tratada quando é aprovada.

1. Acesse **Vendas e marketing \> Bonificações comerciais \> Deduções \> Motivos de dedução**.
1. Selecione **Novo** para adicionar uma linha à grade e defina os seguintes campos para ela:

    - **Motivo da declaração** - Digite um nome exclusivo para o motivo.
    - **Descrição** – Insira uma descrição do motivo para fornecer mais informações sobre como ela deve ser usada.
    - **Base de declaração** – Selecione uma base de declaração para o motivo da declaração:

        - *Com base no preço* – Crie um crédito de texto livre após a aprovação.
        - *Com base na quantidade* – Crie uma ordem de venda negativa ou uma ordem de devolução após a aprovação.

    - **Código do motivo de devolução** – Selecione um código de motivo de devolução que será aplicado como o valor de **Código de motivo de devolução** da ordem de devolução.
    - **Tipo** – Selecione um tipo de dedução. O valor de **Compensação de dedução** para o tipo selecionado será usado para definir o campo **Compensação de dedução** quando uma dedução ou uma declaração for criada. Os tipos de dedução são definidos na página **Tipos de dedução** (**Vendas e marketing \> Bonificações comerciais \> Deduções \> Tipos de dedução**).
    - **Conta de lançamento da declaração** – Este campo só está disponível quando o campo **Base da declaração** é definido como *Com base no preço*. Quando uma declaração baseada em preço é aprovada, o sistema atribui a conta contábil que você seleciona aqui como o valor da **Conta principal** para a nota de crédito de texto livre de rascunho.

### <a name="set-up-the-settle-approved-deductions-periodic-task"></a>Configurar a tarefa periódica de liquidação de deduções aprovadas

Para deduções que são criadas com o uso do comando **Nova dedução** na bancada de dedução, liquidação de cliente ou página de cliente, você pode configurar a tarefa periódica *Liquidar deduções aprovadas* para corresponder automaticamente deduções e créditos que têm valores de e valores correspondentes de **ID de dedução**.

Para programar essa tarefa, Acesse as tarefas **Marketing de vendas \> Tarefas periódicas \> Liquidar deduções aprovadas** e configure opções, filtros e uma agenda, da mesma forma que outros tipos de tarefas periódicas.

> [!NOTE]
> Se a opção **Liquidação automática** estiver definida como *Sim* na guia **Liquidação** da página **Parâmetros de contas a receber** (**Contas a receber \> Configuração \> Parâmetros de contas a receber**), a tarefa periódica *Liquidação de deduções aprovadas*, pois o crédito será liquidado automaticamente.

## <a name="create-a-deduction"></a>Criar uma dedução

### <a name="create-a-deduction-journal-entry-by-using-the-customer-payment-journal"></a>Criar uma entrada de diário de deduções usando o diário de pagamentos do cliente

Para criar uma entrada de diário de dedução, siga estas etapas.

1. Acesse **Contas a receber \> Pagamentos \> Diário de pagamento do cliente**.
1. Selecione **Novo** para adicionar uma linha à grade.
1. No campo **Nome** da nova linha, selecione o nome do diário.
1. No Painel de Ações, selecione **Linhas**.
1. Insira a data, a conta da empresa e o número da conta do cliente.
1. No campo **Fatura**, selecione a fatura à qual a dedução está associada.
1. No campo **Crédito**, insira o valor pago pelo cliente.
1. Selecione **OK** para confirmar que o valor é menor do que o total da transação marcada.
1. Selecione um tipo de contrapartida e a contrapartida.
1. Na barra de ferramentas acima da grade, selecione **Deduções**.
1. Na página **Dedução**, no Painel de Ações, selecione **Novo** para adicionar uma linha à grade. O campo **ID da dedução** para a nova linha é automaticamente definido.
1. No campo **Tipo**, selecione o tipo de dedução.
1. No campo **Valor**, insira o valor que é exibido no campo **Saldo** abaixo da lista de dedução. Esse valor representa o valor deduzido pelo cliente do pagamento.
1. Feche a página **Dedução**. Você retorna à página **Pagamentos do cliente**, que agora mostra uma nova linha para a dedução.
1. No Painel de Ações, selecione **Validar \> Validar**. Você deve receber a seguinte mensagem: "O diário está OK".
1. No Painel de Ação, selecione **Lançar**.

### <a name="create-a-deduction-by-using-the-deduction-workbench"></a>Criar uma dedução usando a bancada de dedução

Para criar uma nova dedução na bancada de dedução, siga estas etapas.

1. Acesse **Vendas e marketing \> Bonificações comerciais \> Deduções \> Bancada de dedução**.
1. No Painel de Ações, selecione **Manter \> Nova dedução**.

    Na caixa de diálogo **Nova dedução**, o campo **ID de dedução** é definido com base na sequência numérica da **ID de dedução** definida na página **Parâmetros de gerenciamento da bonificação comercial** (**Vendas e marketing \> Configuração \> Bonificações comerciais \> Parâmetros de gerenciamento de bonificação comercial**).

1. Defina os seguintes campos:

    - **Conta de cliente** – Selecione a conta de cliente à qual a dedução se aplica.
    - **Número da declaração externa** – Insira a referência da declaração do cliente.
    - **Valor da declaração** – Insira o valor da declaração de imposto inclusivo. O valor deve ser positivo.
    - **Moeda** – Selecione a moeda para a dedução. O valor padrão é a moeda definida para a conta de cliente selecionada.
    - **Base da declaração** – Selecione a base da declaração. A base da declaração determina o tipo de transação de crédito que é criado após a dedução ou a declaração ser aprovada.

        - *Com base no preço* – Uma fatura de texto livre de rascunho será criada.
        - *Com base na quantidade* – Uma ordem de venda negativa ou uma ordem de devolução será criada.

    - **Data da declaração** – Selecione a data da declaração. O valor padrão é a data atual.
    - **Motivo da declaração** – Selecione o código de motivo que se aplica à dedução atual. A base da declaração selecionada afeta as opções que se apliquem. Para obter mais informações sobre como criar e configurar os motivos da declaração que estão disponíveis para seleção aqui, consulte a seção [Criar motivos da dedução](#deduction-reasons) anteriormente neste artigo.
    - **Notas** – Adicione notas que se apliquem. Quando a declaração for aprovada, o aprovador poderá editar ou adicionar as notas da declaração.
    - **Criar diário de declarações** – Defina esta opção para especificar se o diário de declarações deve ser criado quando a declaração ou dedução é criada:

        - *Sim* – O sistema criará e lançará um diário geral usando o diário de declaração configurado na página **Parâmetros de contas a receber**. (Para obter mais informações, consulte a seção [Configurar contas a receber e deduções](#accounts-receivable-deductions), abordada anteriormente neste artigo.) Quando uma fatura é anexada à declaração, o diário de declarações é usado para reduzir o saldo da fatura aplicável. Se a declaração for rejeitada posteriormente, o diário de declarações e as liquidações (se uma fatura anexada) serão revertidos.
        - *Não* – Nenhum diário de declarações é criado neste momento. Ele será criado quando a solicitação for aprovada. Uma fatura ainda pode ser anexada à nova declaração, mesmo que um diário de declaração não seja criado. No entanto, a liquidação não poderá ser feita sem o diário de declarações.

1. Selecione **OK**.

    Uma nova dedução é criada. Se você definir a opção **Criar diário de declarações** como *Sim*, as transações a seguir serão lançadas:

    - **Duas novas transações de cliente** – Uma transação compensa o valor da declaração em relação à fatura original. A outra transação registra a dívida de um cliente para o valor da declaração, pois a declaração ainda não foi aprovada. A transação de fatura original e a transação de declaração de compensação serão marcadas automaticamente para liquidação quando você anexar a fatura selecionando **Manter \> Anexar fatura** no painel de ações.
    - **Duas transações de compensação** – Essas transações são lançadas na conta contábil de **Compensação por dedução**.
    - **Diário de declarações** – Para exibir o diário de declarações para cada dedução que é mostrada na bancada de dedução, selecione a guia **Referências**. O diário de declarações é mostrado no campo **Número de lote do diário**. Você também pode exibir o diário de declarações na guia **Eventos de dedução**. Lá, ele terá um valor **Tipo de atualização** de *Corresponder*.

### <a name="create-a-deduction-from-a-customer-settlement"></a>Criar uma dedução em uma liquidação de cliente

O processo de criação de uma dedução a partir de uma liquidação de cliente é semelhante ao processo de criar uma dedução via bancada de dedução. No entanto, o cliente e a moeda da fatura são definidos automaticamente e a fatura é anexada. Não é necessário selecionar **Manter \> Anexar fatura** no painel de ações ao criar uma declaração ou dedução por meio da página de liquidação de cliente.

1. Ir para **Contas recebíveis \> Clientes \> Todos os clientes**.
1. Selecione o cliente para o qual será criada uma dedução.
1. No painel de ação, na guia **Coletar** , no grupo **Liquidar** , selecione **Liquidar transações**.
1. Na caixa de diálogo **Liquidar transações**, na guia **Visão geral**, selecione a fatura para criar a dedução associada.
1. Na barra de ferramentas, selecione **Deduções \> Nova dedução**.

    Na caixa de diálogo **Nova dedução**, o campo **ID de dedução** é definido com base na sequência numérica da **ID de dedução** definida na página **Parâmetros de gerenciamento da bonificação comercial** (**Vendas e marketing \> Configuração \> Bonificações comerciais \> Parâmetros de gerenciamento de bonificação comercial**). O campo **Conta de cliente** é definido como a conta de cliente à qual a dedução se aplica.

1. Defina os seguintes campos:

    - **Número da declaração externa** – Insira a referência da declaração do cliente.
    - **Valor da declaração** – Insira o valor da declaração de imposto inclusivo. O valor deve ser positivo.
    - **Moeda** – Selecione a moeda para a dedução. O valor padrão é a moeda definida para a conta de cliente selecionada.
    - **Base da declaração** – Selecione a base da declaração. A base da declaração determina o tipo de transação de crédito que é criado após a dedução ou a declaração ser aprovada.

        - *Com base no preço* – Uma fatura de texto livre de rascunho será criada.
        - *Com base na quantidade* – Uma ordem de venda negativa ou uma ordem de devolução será criada.

    - **Data da declaração** – Selecione a data da declaração. O valor padrão é a data atual.
    - **Motivo da declaração** – Selecione o código de motivo que se aplica à dedução atual. A base da declaração selecionada afeta as opções que se apliquem. Para obter mais informações sobre como criar e configurar os motivos da declaração que estão disponíveis para seleção aqui, consulte a seção [Criar motivos da dedução](#deduction-reasons) anteriormente neste artigo.
    - **Notas** – Adicione notas que se apliquem. Quando a declaração for aprovada, o aprovador poderá editar ou adicionar as notas da declaração.
    - **Criar diário de declarações** – Defina esta opção para especificar se o diário de declarações deve ser criado quando a declaração ou dedução é criada:

        - *Sim* – O sistema criará e lançará um diário geral usando o diário de declaração configurado na página **Parâmetros de contas a receber**. (Para obter mais informações, consulte a seção [Configurar contas a receber e deduções](#accounts-receivable-deductions), abordada anteriormente neste artigo.) Quando uma fatura é anexada à declaração, o diário de declarações é usado para reduzir o saldo da fatura aplicável. Se a declaração for rejeitada posteriormente, o diário de declarações e as liquidações (se uma fatura anexada) serão revertidos.
        - *Não* – Nenhum diário de declarações é criado neste momento. Ele será criado quando a solicitação for aprovada. Uma fatura ainda pode ser anexada à nova declaração, mesmo que um diário de declaração não seja criado. No entanto, a liquidação não poderá ser feita sem o diário de declarações.

1. Selecione **OK**.

    Uma nova dedução é criada. Se você definir a opção **Criar diário de declarações** como *Sim*, as transações a seguir serão lançadas:

    - **Duas novas transações de cliente** – Uma transação compensa o valor da declaração em relação à fatura original. A outra transação registra a dívida de um cliente para o valor da declaração, pois a declaração ainda não foi aprovada. A transação de fatura original e a transação de declaração de compensação serão marcadas automaticamente para liquidação quando você anexar a fatura selecionando **Manter \> Anexar fatura** no painel de ações.
    - **Duas transações de compensação** – Essas transações são lançadas na conta contábil de **Compensação por dedução**.
    - **Diário de declarações** – Para exibir o diário de declarações para cada dedução que é mostrada na bancada de dedução, selecione a guia **Referências**. O diário de declarações é mostrado no campo **Número de lote do diário**. Você também pode exibir o diário de declarações na guia **Eventos de dedução**. Lá, ele terá um valor **Tipo de atualização** de *Corresponder*.

    Você voltará à página **Liquidar transações**, que agora mostra a fatura selecionada como marcada. O botão **Lançar** só estará disponível se você definir a opção **Criar diário de declarações** como *Sim*. Se estiver disponível, selecione **Lançar** para reduzir o saldo na fatura pelo **Valor da declaração**.

### <a name="create-a-deduction-from-a-customer-page"></a>Criar uma dedução em uma página de cliente

O processo de criação de uma dedução a partir de uma página de cliente é semelhante ao processo de criar uma dedução via bancada de dedução. No entanto, o cliente é definido automaticamente.

1. Ir para **Contas recebíveis \> Clientes \> Todos os clientes**.
1. Selecione o cliente para o qual será criada uma dedução.
1. No Painel de Ação, na guia **Coletar**, no grupo **Deduções**, selecione **Criar deduções**.

    Na caixa de diálogo **Nova dedução**, o campo **ID de dedução** é definido com base na sequência numérica da **ID de dedução** definida na página **Parâmetros de gerenciamento da bonificação comercial** (**Vendas e marketing \> Configuração \> Bonificações comerciais \> Parâmetros de gerenciamento de bonificação comercial**). O campo **Conta de cliente** é definido como a conta de cliente à qual a dedução se aplica.

1. Defina os seguintes campos:

    - **Número da declaração externa** – Insira a referência da declaração do cliente.
    - **Valor da declaração** – Insira o valor da declaração de imposto inclusivo. O valor deve ser positivo.
    - **Moeda** – Selecione a moeda para a dedução. O valor padrão é a moeda definida para a conta de cliente selecionada.
    - **Base da declaração** – Selecione a base da declaração. A base da declaração determina o tipo de transação de crédito que é criado após a dedução ou a declaração ser aprovada.

        - *Com base no preço* – Uma fatura de texto livre de rascunho será criada.
        - *Com base na quantidade* – Uma ordem de venda negativa ou uma ordem de devolução será criada.

    - **Data da declaração** – Selecione a data da declaração. O valor padrão é a data atual.
    - **Motivo da declaração** – Selecione o código de motivo que se aplica à dedução atual. A base da declaração selecionada afeta as opções que se apliquem. Para obter mais informações sobre como criar e configurar os motivos da declaração que estão disponíveis para seleção aqui, consulte a seção [Criar motivos da dedução](#deduction-reasons) anteriormente neste artigo.
    - **Notas** – Adicione notas que se apliquem. Quando a declaração for aprovada, o aprovador poderá editar ou adicionar as notas da declaração.
    - **Criar diário de declarações** – Defina esta opção para especificar se o diário de declarações deve ser criado quando a declaração ou dedução é criada:

        - *Sim* – O sistema criará e lançará um diário geral usando o diário de declaração configurado na página **Parâmetros de contas a receber**. (Para obter mais informações, consulte a seção [Configurar contas a receber e deduções](#accounts-receivable-deductions), abordada anteriormente neste artigo.) Quando uma fatura é anexada à declaração, o diário de declarações é usado para reduzir o saldo da fatura aplicável. Se a declaração for rejeitada posteriormente, o diário de declarações e as liquidações (se uma fatura anexada) serão revertidos.
        - *Não* – Nenhum diário de declarações é criado neste momento. Ele será criado quando a solicitação for aprovada. Uma fatura ainda pode ser anexada à nova declaração, mesmo que um diário de declaração não seja criado. No entanto, a liquidação não poderá ser feita sem o diário de declarações.

1. Selecione **OK**.

    Uma nova dedução é criada. Se você definir a opção **Criar diário de declarações** como *Sim*, as transações a seguir serão lançadas:

    - **Duas novas transações de cliente** – Uma transação compensa o valor da declaração em relação à fatura original. A outra transação registra a dívida de um cliente para o valor da declaração, pois a declaração ainda não foi aprovada. A transação de fatura original e a transação de declaração de compensação serão marcadas automaticamente para liquidação quando você anexar a fatura selecionando **Manter \> Anexar fatura** no painel de ações.
    - **Duas transações de compensação** – Essas transações são lançadas na conta contábil de **Compensação por dedução**.
    - **Diário de declarações** – Para exibir o diário de declarações para cada dedução que é mostrada na bancada de dedução, selecione a guia **Referências**. O diário de declarações é mostrado no campo **Número de lote do diário**. Você também pode exibir o diário de declarações na guia **Eventos de dedução**. Lá, ele terá um valor **Tipo de atualização** de *Corresponder*.

## <a name="create-a-credit-note-for-a-customer"></a>Criar uma nota de crédito para um cliente

Se existir um reembolso aprovado para o cliente, você pode criar uma nota de crédito na conta do cliente para representar o reembolso, conforme necessário. O crédito aparece na bancada de dedução, onde pode ser correspondido a uma dedução.

Para criar uma nota de crédito, siga estas etapas.

1. Acesse **Vendas e marketing \> Clientes \> Todos os clientes**.
1. Selecione o cliente.
1. No painel de ação, na guia **Coletar** , no grupo **Liquidar** , selecione **Liquidar transações**.
1. Na caixa de diálogo **Liquidar transações**, selecione a transação à qual o desconto foi aplicado.
1. Na barra de ferramentas, no menu **Funções**, selecione o tipo de programa de descontos que se aplica.
1. Na página **Reembolso**, na guia **Visão geral**, marque a caixa de seleção **Marcar** ao lado da ID de reembolso relevante.
1. No painel de ações, selecione **Funções \> Criar nota de crédito**.

## <a name="process-a-deduction-on-the-deduction-workbench"></a>Processar uma dedução na bancada de dedução

Na bancada de dedução, é possível corresponder deduções para abrir as transações de crédito, dividir deduções, negar deduções e dar baixa em deduções.

Dependendo de como você deseja processar a dedução, execute um ou mais dos seguintes procedimentos nestas subseções: Você pode combinar os procedimentos conforme necessário. Por exemplo, você pode dividir a dedução em duas partes e depois corresponder uma parte a um crédito, mas deixar a parte pendente na bancada a ser correspondida a outro crédito posteriormente. Você também pode corresponder uma dedução a um crédito que seja menor que o valor de dedução, e então negar ou dar baixa do saldo restante da dedução.

### <a name="match-a-deduction-to-a-credit"></a>Corresponder uma dedução a um crédito

Para corresponder a dedução a um crédito, siga estas etapas.

1. Acesse **Vendas e marketing \> Bonificações comerciais \> Deduções \> Bancada de dedução**.
1. Selecione a caixa de seleção **Marcar** ao lado da dedução a ser processada.
1. Na seção **Transações abertas**, marque a caixa de seleção **Marcar** para o crédito de acordo com a dedução. Se vários créditos estiverem listados, é possível selecionar mais de um crédito para corresponder à dedução. Se quiser que o sistema selecione automaticamente os créditos que correspondam ao valor da dedução, na barra de ferramentas, selecione uma opção apropriada no menu **Selecionar valor de dedução**.
1. No Painel de Ação, selecione **Manter \> Corresponder**. O sistema corresponde a dedução ao crédito. Se um saldo permanecer na dedução, ele será mostrado no campo **Valor restante** na guia **Deduções**.

    > [!NOTE]
    > Para deduções que foram criadas usando o comando **Nova dedução** na bancada de dedução, liquidação de cliente ou página de cliente, o comando **Manter \> Corresponder** só estará disponível se o campo **Status da declaração** estiver definido como *Aceito*. Este comando pode ser usado para fazer a correspondência manual entre a transação baseada em preço ou em quantidade ao crédito associado na seção **Transações abertas**. Esse crédito é criado quando a dedução é aprovada (usando o comando **Manter \> Aprovar dedução**) ou quando está anexada a um crédito existente, conforme descrito na seção [Créditos criados fora do processo de aprovação de dedução](#credits-outside-approval) posteriormente neste artigo. As tarefas periódicas *Liquidar deduções aprovadas* (**Venda de marketing \> Tarefas periódicas \> Liquidar deduções aprovadas**) também podem ser usadas para corresponder automaticamente deduções e créditos que têm valores correspondentes de **ID de dedução**.

### <a name="split-a-deduction"></a>Dividir uma dedução

Para dividir uma dedução, siga estas etapas.

1. Acesse **Vendas e marketing \> Bonificações comerciais \> Deduções \> Bancada de dedução**.
1. Selecione a caixa de seleção **Marcar** ao lado da dedução a ser processada.
1. No Painel de Ação, selecione **Manter \> Dividir**.
1. Na caixa de diálogo **Dividir**, no campo **Dividir valor**, insira o valor a ser dividido a partir da dedução principal. Em seguida, selecione **OK**.
1. Na guia **Deduções**, observe que um novo registro é exibido para o valor dividido. O registro original da dedução contém o restante do saldo da dedução. Agora você pode gerenciar as duas partes do reembolso original separadamente.
1. Selecione o registro de dedução original e selecione a guia **Referências**. O campo **Valor dividido** mostra o valor que foi dividido do valor original.

### <a name="attach-an-invoice-to-a-deduction"></a>Anexar uma fatura a uma dedução

Você pode anexar uma fatura a uma dedução se a dedução tiver sido criada usando o comando **Nova dedução** na bancada de dedução, liquidação de cliente ou página de cliente, e também se nenhuma fatura estiver anexada a ela (ou seja, a coluna **Fatura** ficará em branco).

Para anexar uma fatura a uma dedução, siga estas etapas.

1. Acesse **Vendas e marketing \> Bonificações comerciais \> Deduções \> Bancada de dedução**.
1. Selecione a caixa de seleção **Marcar** ao lado da dedução a ser processada.
1. No Painel de Ações, selecione **Manter \> Anexar fatura**.
1. Na caixa de diálogo **Anexar fatura**, selecione uma fatura e selecione **OK**.
1. Na caixa de diálogo **Liquidar transações**, siga uma destas etapas, dependendo se um diário de declarações foi lançado quando a dedução foi criada:

    - Se um diário de declarações tiver sido lançado, a fatura selecionada e a transação de crédito do diário de declaração exibem uma marca de seleção na coluna **Marca**. Selecione **Lançar**. O saldo restante na fatura associada é reduzido pelo valor da declaração.
    - Se um diário de declarações não tiver sido lançado, nenhuma transação mostrará uma marca de seleção na coluna **Marca**. Como não é possível compensar com um diário de declarações até a dedução ser aprovada, selecione **Cancelar**.

### <a name="detach-an-invoice-from-a-deduction"></a>Desanexar uma fatura de uma dedução

Você pode desanexar uma faturada de uma dedução se a dedução tiver sido criada usando o comando **Nova dedução** na bancada de dedução, liquidação de cliente ou página de cliente, e também se uma fatura estiver anexada a ela (ou seja, a coluna **Fatura** mostrará um número de fatura) e se o campo **Status da declaração** estiver definido como *Aberto*. Você pode concluir esta tarefa caso uma fatura incorreta tenha sido anexada. A fatura será removida da dedução e o saldo restante será atualizado se tiver sido reduzido quando a fatura foi associada.

Para desafixar uma fatura, siga estas etapas.

1. Acesse **Vendas e marketing \> Bonificações comerciais \> Deduções \> Bancada de dedução**.
1. Selecione a caixa de seleção **Marcar** ao lado da dedução a ser processada.
1. No Painel de Ações, selecione **Manter \> Desanexar fatura**.

### <a name="approve-a-deduction"></a>Aprovar uma dedução

Você pode aprovar deduções criadas com o uso do comando **Nova dedução** na bancada de dedução, liquidação de cliente ou página de cliente. No entanto, você só pode aprovar deduções nas quais o campo **Status da declaração** está definido como *Aberto*.

Para aprovar uma dedução, siga estas etapas.

1. Acesse **Vendas e marketing \> Bonificações comerciais \> Deduções \> Bancada de dedução**.
1. Selecione a caixa de seleção **Marcar** ao lado da dedução a ser processada.
1. No Painel de Ações, selecione **Manter \> Aprovar dedução**.
1. Na caixa de diálogo **Aprovar dedução**, edite ou adicione informações ao valor **Nota**, conforme necessário.
1. Se a dedução for baseada em preço e uma fatura não tiver sido anexada a ela, selecione um grupo de impostos sobre vendas do item. Normalmente, o grupo de itens de imposto é definido na fatura. Portanto, o código de item do imposto deve ser especificado quando não está associado a uma fatura.
1. Selecione **OK**.

    Neste ponto, não será possível fazer alterações adicionais na dedução. Se a opção **Criar diário de declarações** tiver sido definida como *Não* quando a dedução foi criada, o diário de declarações será criado e lançado quando a dedução for aprovada. Depois que a dedução for aprovada, o crédito será automaticamente criado e aberto. O tipo depende do valor **Base da declaração** da dedução:

    - *Com base no preço* – Se a dedução for baseada em preço, uma fatura de texto livre é criada para a conta do cliente. Você pode adicionar uma descrição e lançar o crédito. Os campos a seguir são preenchidos pela dedução quando o rascunho é criado:

        - **ID de dedução** – Este campo é adicionado ao cabeçalho para permitir que a rastreabilidade volte à dedução.
        - **Conta principal** – O valor é determinado pelo valor **Conta de lançamento da declaração** definido para o motivo da dedução atribuído à dedução.
        - **Grupo de impostos sobre vendas do item** – O valor é determinado pela fatura anexada ou pelo valor que você selecionou quando aprovou a dedução.
        - **Preço unitário** – O valor é o crédito do valor da declaração da dedução.
        - **Texto da fatura** – Por padrão, este campo é definido como o valor das **Notas**.

    - *Quantidade com base* – Se a dedução for baseada em quantidade, uma ordem de venda aberta ou uma ordem de devolução será criada. A configuração **Criar ordem de devolução** na página **[Parâmetros de contas a receber](#accounts-receivable-deductions)** determina se uma ordem de venda ou uma ordem de devolução é criada quando a dedução é aprovada. A página **Copiar ordens** exibida e filtrada para mostrar as linhas nas quais o campo **Conta da fatura** está definido como a conta de cliente da dedução. Execute estas etapas:

        1. Na Guia Rápida **Faturas**, a seção **Cabeçalhos** mostra as faturas de venda nas quais o valor **Conta da fatura** corresponde à conta de cliente da dedução. Selecione uma fatura de venda aplicável.
        1. A seção **Linhas** mostra as linhas da fatura de venda selecionada. Marque a caixa de seleção **Selecionar** para cada linha que você deseja copiar. Como alternativa, na seção **Cabeçalhos**, marque a caixa de seleção **Selecionar tudo** para a ordem de venda para selecionar todas as linhas.
        1. Ajuste o valor **Quantidade** para uma ou mais linhas, conforme necessário.

            Todas as linhas que você selecionou até agora são listadas na Guia Rápida **Linhas selecionadas ou cabeçalho a serem copiados**.

        1. Repita as duas etapas anteriores, conforme necessário, até que todas as linhas obrigatórias sejam listadas na Guia Rápida **Linhas selecionadas ou cabeçalho a serem copiados**.
        1. Selecione **OK**.

            A nova ordem de devolução é aberta e os seguintes campos são definidos automaticamente:

            - **ID de dedução** – Este campo é adicionado ao cabeçalho para permitir que a rastreabilidade volte à dedução.
            - **Código do motivo de devolução** – Por padrão, este campo é definido como o valor **Código do motivo de devolução** definido para o motivo de dedução atribuído à dedução.

Depois que o crédito for faturado, ele aparecerá na seção **Transações abertas** da bancada de dedução com o valor **ID de dedução** aplicável, e seu campo **Tipo de declaração** será definido como *Outros créditos*. O crédito ficará disponível até ser liquidado com a dedução de uma das seguintes maneiras:

- Você pode liquidá-lo manualmente selecionando **Manter \> Corresponder** no painel de ações.
- Ele é liquidado automaticamente pelo trabalho periódico *Liquidar declarações aprovadas* (**Vendas e marketing \> Tarefas periódicas \> Liquidar declarações aprovadas**).
- Ele é liquidado automaticamente porque a opção **Liquidação automática** na guia **Liquidação** da página **Parâmetros de contas a receber** está definida como *Sim*.

Para exibir o crédito que é criado quando a dedução é aprovada, você também pode usar o botão **Crédito aberto** na seção **Transações abertas** da bancada de dedução.

### <a name="create-a-return-order"></a>Criar uma ordem de devolução

Você pode criar uma ordem de devolução para deduções criadas com o uso do comando **Nova dedução** na bancada de dedução, liquidação de cliente ou página de cliente. No entanto, todas as condições a seguir devem ser atendidas:

- O campo **Base da declaração** é definido como *Com base na quantidade*.
- O campo **Status da declaração** é definido como *Aberto*.
- A opção **Criar ordem de devolução** na guia **Deduções** da página **[Parâmetros de contas a receber](#accounts-receivable-deductions)** é definida como *Sim*.
- A opção **Criar ordem de devolução antes da aprovação da dedução** na guia **Deduções** da página **[Parâmetros de contas a receber](#accounts-receivable-deductions)** é definida como *Sim*.

Siga estas etapas para criar uma ordem de devolução.

1. Acesse **Vendas e marketing \> Bonificações comerciais \> Deduções \> Bancada de dedução**.
1. Selecione a caixa de seleção **Marcar** ao lado da dedução a ser processada.
1. No Painel de Ações, selecione **Manter \> Criar ordem de devolução**.
1. Na caixa de diálogo **Aprovar dedução**, edite ou adicione informações ao valor **Notas** existente conforme necessário, e depois selecione **OK**.
1. Na caixa de diálogo **Copiar ordens**, na Guia Rápida **Faturas**, a seção **Cabeçalhos** mostra as faturas de venda nas quais o valor **Conta da fatura** corresponde à conta de cliente da dedução. Selecione uma fatura de venda aplicável.
1. A seção **Linhas** mostra as linhas da fatura de venda selecionada. Marque a caixa de seleção **Selecionar** para cada linha que você deseja copiar. Como alternativa, na seção **Cabeçalhos**, marque a caixa de seleção **Selecionar tudo** para a ordem de venda para selecionar todas as linhas.
1. Ajuste o valor **Quantidade** para uma ou mais linhas, conforme necessário.

    Todas as linhas que você selecionou até agora são listadas na Guia Rápida **Linhas selecionadas ou cabeçalho a serem copiados**.

1. Repita as duas etapas anteriores, conforme necessário, até que todas as linhas obrigatórias sejam listadas na Guia Rápida **Linhas selecionadas ou cabeçalho a serem copiados**.
1. Selecione **OK**.

    A nova ordem de devolução é aberta e os seguintes campos são definidos automaticamente:

    - **ID de dedução** – Este campo é adicionado ao cabeçalho para permitir que a rastreabilidade volte à dedução.
    - **Código do motivo de devolução** – Por padrão, este campo é definido como o valor **Código do motivo de devolução** definido para o motivo de dedução atribuído à dedução.

### <a name="deny-a-deduction"></a>Negar uma dedução

Para negar uma dedução, siga estas etapas.

1. Acesse **Vendas e marketing \> Bonificações comerciais \> Deduções \> Bancada de dedução**.
1. Selecione a caixa de seleção **Marcar** ao lado da dedução a ser processada.
1. No Painel de Ação, selecione **Manter \> Negar**.
1. Na caixa de diálogo **Negar**, selecione o código de motivo para a negação e selecione **OK**.
1. No campo **Mostrar** embaixo do Painel de Ação, selecione *Fechado*.

    A guia **Deduções** mostra a dedução negada, e o campo **Valor restante** da dedução é definido como *0,00*.

    Para deduções criadas com o uso do comando **Nova dedução** na bancada de dedução, liquidação de cliente ou página de cliente, os seguintes eventos ocorrerão:

    - Na guia **Referências**, os campos na seção **Negação** são atualizados.
    - Se você selecionou para criar o diário de declarações quando a dedução foi criada, e se uma fatura tiver sido anexada à dedução que reduziu o saldo da fatura, a fatura será desanexada e o saldo restante da fatura previamente anexada será aumentado pelo valor da declaração rejeitada.
    - O campo **Status** da dedução é definido como *Fechado*.
    - O campo **Status da declaração** é definido como *Rejeitado*.

Para reverter uma rejeição, siga estas etapas.

1. Na guia **Deduções**, selecione uma dedução negada.
1. No Painel de Ação, selecione **Reverter negação**.

    Para deduções criadas com o uso do comando **Nova dedução** na bancada de dedução, liquidação de cliente ou página de cliente, os seguintes eventos ocorrerão:

    - Na guia **Referências**, os campos na seção **Negação** são atualizados.
    - O campo **Status** da dedução é definido como *Aberto*.
    - O campo **Status da declaração** é definido como *Aberto*.

### <a name="write-off-a-deduction"></a>Dar baixa em uma dedução

Para dar baixa em uma dedução, siga estas etapas.

1. Acesse **Vendas e marketing \> Bonificações comerciais \> Deduções \> Bancada de dedução**.
1. Selecione a caixa de seleção **Marcar** ao lado da dedução a ser processada.
1. No Painel de Ação, selecione **Manter \> Dar baixa**.
1. Na caixa de diálogo **Dar baixa**, selecione o código de motivo para a baixa e selecione **OK**.
1. No campo **Mostrar**, selecione *Fechado*.

    A guia **Deduções** mostra a dedução com baixa, e o campo **Valor restante** da dedução é definido como *0,00*.

    Para deduções criadas com o uso do comando **Nova dedução** na bancada de dedução, liquidação de cliente ou página de cliente, os seguintes eventos ocorrerão:

    - Na guia **Referências**, os campos na seção **Dar baixa** são atualizados.
    - Se você tiver criado o diário de declarações quando a dedução foi criada, um diário de solicitação é lançado no código de motivo de baixa da dedução. Você pode exibir essa entrada na guia **Eventos de dedução**, em que ela tem um valor **Tipo de atualização** de *Dar baixa*.
    - O campo **Status** da dedução é definido como *Fechado*
    - O campo **Status da declaração** é definido como *Dar baixa*.

Para reverter uma baixa, siga estas etapas.

1. Na guia **Deduções**, selecione uma dedução negada.
1. No Painel de Ação, selecione **Reverter baixa**.

    Para deduções criadas com o uso do comando **Nova dedução** na bancada de dedução, liquidação de cliente ou página de cliente, os seguintes eventos ocorrerão:

    - Na guia **Referências**, os campos na seção **Dar baixa** são atualizados.
    - Se você tiver criado o diário de declarações quando a dedução foi criada, um diário de solicitação é lançado no código de motivo de baixa da dedução. Você pode exibir essa entrada na guia **Eventos de dedução**, em que ela tem um valor **Tipo de atualização** de *Reverter baixa*.
    - O campo **Status** da dedução é definido como *Aberto*.
    - O campo **Status da declaração** é definido como *Aberto*.

## <a name="credits-created-outside-the-approve-deduction-process"></a><a name="credits-outside-approval"></a>Créditos criados fora do processo Aprovar dedução

Esta seção aplica-se apenas a deduções criadas com o uso do comando **Nova dedução** na bancada de dedução, liquidação de cliente ou página de cliente.

Diferentes usuários podem já ter criado uma fatura de texto livre, uma ordem de devolução ou uma ordem de venda negativa para a declaração de um cliente fora do processo **Aprovação de dedução**. Quando a dedução existente é aprovada na bancada de dedução, o sistema cria automaticamente outra fatura de texto livre, ordem de devolução ou ordem de venda negativa. Esta seção descreve como anexar os créditos existentes a uma dedução antes de a dedução ser aprovada, para ajudar a evitar créditos duplicados.

### <a name="attach-a-credit-to-deduction"></a>Anexar um crédito à dedução

Esta seção descreve como você pode associar um crédito a uma dedução do crédito.

Após o crédito ser anexado à dedução, você pode visualizá-lo usando o botão **Crédito aberto** na barra de ferramentas na seção **Transações abertas** da bancada de dedução.

Depois que o crédito for faturado e a dedução for aprovada, o crédito aparecerá na seção **Transações abertas** da bancada de dedução com o valor **ID de dedução** aplicável, e seu campo **Tipo de declaração** será definido como *Outros créditos*.

#### <a name="attach-a-free-text-invoice-to-a-deduction"></a>Anexar uma fatura de texto livre a uma dedução

Para anexar uma fatura de texto livre a uma dedução, siga estas etapas.

1. Acesse **Contas recebíveis \> Faturas \> Todas faturas de texto livre**.
1. Selecione a fatura aplicável.
1. No Painel de ações, na guia **Fatura**, selecione **Anexar crédito à dedução**. Este botão estará disponível somente se o campo **ID da dedução** da fatura de texto livre estiver em branco. Um campo em branco indica que a fatura de texto livre ainda não está anexada a uma dedução.
1. Na página **Anexar crédito à dedução**, você pode selecionar *uma* dedução. Somente as deduções *Com base no preço* abertas estão disponíveis para seleção.
1. Selecione **OK**. O campo **ID de dedução** é definido no cabeçalho da fatura de texto livre.

#### <a name="attach-a-return-order-to-a-deduction"></a>Anexar uma ordem de devolução a uma dedução

Para anexar uma ordem de devolução a uma dedução, siga estas etapas.

1. Acesse **Contas a receber \> Ordens \> Todas as ordens de devolução**.
1. Selecione o número de autorização de devolução (RMA) aplicável recebido ou aberto.
1. No Painel de ações, na guia **Ordem de devolução**, selecione **Anexar crédito à dedução**. Este botão estará disponível somente se o campo **ID da dedução** da ordem de devolução estiver em branco. Um campo em branco indica que a ordem de devolução ainda não está anexada a uma dedução.
1. Na página **Anexar crédito à dedução**, você pode selecionar *uma* dedução. Somente as deduções *Com base na quantidade* abertas estão disponíveis para seleção.
1. Selecione **OK**. O campo **ID de dedução** é definido no cabeçalho da ordem de devolução.

#### <a name="attach-a-sales-order-to-a-deduction"></a>Anexar uma ordem de venda a uma dedução

Para anexar uma ordem de venda a uma dedução, siga estas etapas.

1. Acesse **Contas a receber \> Ordens \> Todas as ordens de venda**.
1. Selecione a ordem de venda aberta, entregue ou faturada aplicável.
1. No Painel de ações, na guia **Fatura**, selecione **Anexar crédito à dedução**. Este botão estará disponível somente se o campo **ID da dedução** da ordem de venda estiver em branco. Um campo em branco indica que a ordem de venda ainda não está anexada a uma dedução.
1. Na página **Anexar dedução**, você pode selecionar *uma* dedução. Somente as deduções *Com base na quantidade* abertas estão disponíveis para seleção.
1. Selecione **OK**. O campo **ID de dedução** é definido no cabeçalho da ordem de venda.

#### <a name="detach-a-deduction-from-a-credit"></a>Separar uma dedução de um crédito

Se a dedução incorreta tiver sido anexada, você poderá desanexá-la do crédito. No entanto, todas as condições a seguir devem ser atendidas:

- Um crédito está associado à dedução.
- O campo **Status da declaração** é definido como *Aberto*.

Para desanexar uma dedução de um crédito, siga uma destas etapas, dependendo do tipo de crédito:

- **Faturas de texto livre:** na página **Todas as faturas de texto livre**, selecione uma fatura. Em seguida, no Painel de ações, na guia **Fatura**, selecione **Desanexar crédito da dedução**.
- **Ordens de devolução:** na página **Todas as ordens de devolução**, selecione uma ordem. Em seguida, no Painel de ações, na guia **Ordem de devolução**, selecione **Desanexar crédito da dedução**.
- **Ordens de venda:** na página **Todas as ordens de venda**, selecione uma ordem. Em seguida, no Painel de ações, na guia **Fatura**, selecione **Desanexar crédito da dedução**.

### <a name="attach-a-deduction-to-a-credit"></a>Anexar uma dedução a um crédito

Esta seção descreve como você pode associar uma dedução a um crédito da dedução.

#### <a name="attach-a-deduction-to-a-free-text-return-order-or-sales-order-credit"></a>Associar uma dedução a um texto livre, uma ordem de devolução ou um crédito de ordem de venda

Para associar uma dedução a um texto livre, uma ordem de devolução ou um crédito de ordem de venda, siga estas etapas.

1. Acesse **Vendas e marketing \> Bonificações comerciais \> Deduções \> Bancada de dedução**.
1. Selecione a dedução aberta aplicável.
1. No Painel de Ações, selecione **Manter \> Anexar dedução ao crédito**. Este botão só estará disponível se o campo **Status da declaração** estiver definido como *Aberto*.
1. Na página **Anexar crédito**, você pode selecionar *um* crédito. O tipo de crédito mostrado depende do valor de **Base da declaração** da dedução:

    - *Com base no preço* – A página mostra faturas de texto livre para a conta do cliente na qual o campo **ID de dedução** está em branco. As requisições de clientes também são mostradas porque a fatura de texto livre pode ser não lançada. Portanto, talvez não haja um número que possa ser referenciado.
    - *Com base na quantidade* – O tipo de crédito mostrado depende da configuração da opção **Criar ordem de devolução** na página **[Parâmetros de contas a receber](#accounts-receivable-deductions)**:

        - *Sim* – A página mostra ordens de devolução para a conta do cliente na qual o campo **ID de dedução** está em branco.
        - *Não* – A página mostra ordens de venda para a conta do cliente na qual o campo **ID de dedução** está em branco.

1. Selecione **OK**. O campo **ID de dedução** é definido no cabeçalho do crédito.

Após o crédito ser anexado à dedução, você pode visualizá-lo usando o botão **Crédito aberto** na barra de ferramentas na seção **Transações abertas** da bancada de dedução.

Depois que o crédito for faturado e a dedução for aprovada, o crédito aparecerá na seção **Transações abertas** da bancada de dedução com o valor **ID de dedução** aplicável, e seu campo **Tipo de declaração** será definido como *Outros créditos*.

#### <a name="detach-a-credit-from-the-deduction"></a>Desanexar um crédito de uma dedução

Se o crédito incorreto tiver sido anexado, você poderá desanexá-la da dedução. No Painel de ações, no grupo **Manter**, selecione **Desanexar dedução do crédito**. O valor **ID da dedução** é removido do crédito.

O botão **Desanexar dedução do crédito** só estará disponível se as seguintes condições forem atendidas:

- Um crédito está associado à dedução.
- O campo **Status da declaração** é definido como *Aberto*.

## <a name="create-a-one-time-promotion"></a>Criar uma promoção única

Às vezes, você pode não ter um reembolso aprovado que possa corresponder a uma dedução. Nesse caso, você poderá usar o recurso *promoção única* para corresponder a dedução a uma bonificação comercial associada ao cliente. O recurso *promoção única* cria um novo contrato da bonificação de comércio e um evento de venda do valor total. O recurso corresponde o valor total à dedução e faz lançamentos que são necessários para fechar a dedução.

Este recurso é útil se você usar as bonificações comerciais. Para obter mais informações sobre as bonificações comerciais, consulte [Gerenciamento de bonificação comercial](../sales-marketing/trade-allowance.md).

Primeiro, você deve configurar um modelo que pode ser usado para criar o novo contrato da bonificação de comércio. Para configurar um modelo, siga estas etapas.

1. Acesse **Vendas e marketing \> Bonificações comerciais \> Modelos**.
1. No Painel de Ações, selecione **Novo**.
1. Nos campos, insira as informações que devem aparecer nos contratos criados a partir do modelo.
1. Na Guia Rápida **Clientes**, no campo **Hierarquia**, selecione um nível de hierarquia.
1. Na lista de hierarquia, selecione o cliente que tem uma dedução incomparável e selecione o botão de seta para a direita (**\>**). O cliente é adicionado à lista **Clientes do contrato de bonificação comercial**.
1. Defina os campos restantes conforme necessário e, em seguida, feche a página.
1. Acesse **Vendas e marketing \> Configuração \> Bonificação comercial \> Parâmetros de gerenciamento da bonificação comercial**.
1. Na guia **Visão geral**, no campo **Modelo de promoção única**, selecione o nome do modelo a ser usado para criar promoções únicas.

Em seguida, você pode criar uma promoção única na bancada de dedução. Para criar uma promoção única, siga estas etapas.

1. Acesse **Vendas e marketing \> Bonificações comerciais \> Deduções \> Bancada de dedução**.
1. Selecione a caixa de seleção **Marcar** ao lado da dedução que será processada.
1. No painel de ações, selecione **Manter \> Liquidar dedução como promoção única**.
1. Na caixa de diálogo **Promoção única**, siga estas etapas para associar a dedução a um ou mais fundos:

    1. Clique em **Novo**, e então, no campo **ID do fundo**, selecione um ID de fundos. Repita essa etapa para adicionar quantos fundos forem necessários.
    1. No campo **Porcentagem** ao lado de cada ID de fundo, insira a porcentagem da dedução para alocar ao fundo. Os valores inseridos nos campos **Porcentagem** devem totalizar 100%.

1. Selecione **OK**. O sistema cria um novo contrato da bonificação comercial com um evento de venda do valor total e corresponde o valor total à dedução.

## <a name="do-a-mass-update-of-deductions"></a>Realizar uma atualização em massa de deduções

Se você precisar fazer a mesma alteração para várias deduções, é possível selecionar as deduções e realizar uma atualização em massa dos campos.

Para realizar uma atualização em massa, siga estas etapas.

1. Acesse **Vendas e marketing \> Bonificações comerciais \> Deduções \> Bancada de dedução**.
1. No campo **Mostrar** abaixo do Painel de Ação, selecione o tipo de deduções para visualizar.
1. Marque a caixa de seleção ao lado de cada dedução que você deseja atualizar. Em seguida, no Painel de Ações, selecione **Manter \> Atualização em massa**.
1. A caixa de diálogo **Atualização em massa** mostra as deduções selecionadas. Atualize os campos conforme necessário e então selecione **OK** para aceitar as alterações.
