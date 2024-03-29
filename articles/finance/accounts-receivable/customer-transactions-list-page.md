---
title: Página da lista de transações de cliente
description: Este artigo fornece informações sobre a Página da lista de transações de cliente do Microsoft Dynamics 365 Finance.
author: abruer
ms.date: 08/28/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustTrans
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: 2ca7aaa0ccea8f4936ae4a177ef9b9eba2282ae6
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8864444"
---
# <a name="customer-transactions-list-page"></a>Página da lista de transações de cliente

[!include [banner](../includes/banner.md)]

## <a name="view-settlements"></a>Exibir liquidações

O botão **Exibir liquidações** no Painel de Ação fornece acesso rápido ao histórico de liquidações e informações detalhadas sobre a transação de liquidação. Também é possível exibir transações adicionais relacionadas à transação selecionada, porque elas faziam parte da mesma liquidação ou porque são pagamentos criados no mesmo diário de pagamento.

1. Selecione **Contas a receber \> Todos os clientes**.
2. Selecione um cliente que tem transações e, em seguida, no Painel da Ação, na guia **Cliente** , selecione **Transações**.
3. Selecione uma transação para pesquisar, em seguida, no Painel da Ação, selecione **Exibir liquidações**.

    A caixa de diálogo **Exibir liquidações** é exibida e mostra a transação selecionada e todos os documentos que foram liquidados em relação a ela. Essa caixa de diálogo é semelhante à exibição do histórico de liquidações, mas inclui todos os documentos relacionados.

4. Na caixa de diálogo, você pode executar várias tarefas. Selecione um ou mais comprovantes e, em seguida, selecione um dos seguintes botões:

    - **Ver relacionados** – Mostra todas as transações de diário de pagamento e transações de diário geral do cliente que foram criadas nos diários em que foram criados os documentos exibidos na lista. Por exemplo, se um pagamento for mostrado, serão mostrados todos os pagamentos no diário de pagamento no qual ele foi criado. Se uma nota fiscal ou um pagamento forem mostrados e se eles foram criados em um diário geral, serão mostrados todos os documentos no diário geral em que eles foram criados. Todas as liquidações relacionadas à lista de documentos também são exibidas. Quando você exibe os pagamentos relacionados, o rótulo desse botão é alterado para **Exibir liquidações**. Selecione **Exibir liquidações** para mostrar apenas as transações que foram exibidas quando você abriu a caixa de diálogo **Exibir liquidações**.
    - **Exibir histórico** – Exibe o histórico de liquidação dos comprovantes. Selecione **Fechar** para fechar a caixa de diálogo.
    - **Exibir contabilidade** – Mostra todos os comprovantes relacionados aos documentos selecionados. Selecione **Fechar** para fechar a caixa de diálogo.
    - **Exportar** – exporte os comprovantes selecionados para o Microsoft Excel.
    - **Liquidar transações** – Este botão aparece somente se o documento original que foi selecionado não foi totalmente liquidado. Ao selecioná-lo, é exibida a caixa de diálogo **Liquidar transações**, na qual você pode selecionar transações para liquidação.
    - **Desfazer liquidações** – Este botão aparece somente se o documento original selecionado foi totalmente liquidado. Ao selecioná-lo, é exibida a caixa de diálogo **Desfazer liquidações**, na qual você pode desfazer as liquidações que foram feitas para esse documento.

## <a name="global-transactions"></a>Transações globais

O botão **Transações globais** também é exibido na página de listagem **Transações de cliente**. Este botão permite exibir todas as transações de um cliente em todas as entidades legais. A página de listagem **Transações de cliente** mostra apenas transações para entidades legais às quais o usuário tem acesso, com base nas configurações de segurança.

A página de listagem mostra todas as transações de clientes que têm o mesmo ID de participante do cliente com o qual você começou. Por exemplo, se o cliente US-001 em uma entidade legal tiver o mesmo ID de participante do cliente DE-001 em outra entidade legal, todas as transações para os dois IDs do cliente serão exibidas.

Os menus na página **Transações de cliente** podem variar, dependendo da entidade legal da transação. Por exemplo, se um recurso estiver disponível apenas para entidades legais suíças, as opções do menu para o recurso serão exibidas somente quando uma transação da Suíça for selecionada.

Para acessar o recurso, siga essas etapas.

1. Selecione **Contas a receber \> Todos os clientes**.
2. Selecione um cliente e, em seguida, no Painel da Ação, na guia **Cliente**, no grupo **Transações**, selecione **Transações globais**.

## <a name="more-transaction-filters"></a>Mais filtros de transação 

O filtro para mostrar transações abertas foi substituído por um novo filtro que permite exibir mais combinações de transações. As seguintes opções estão disponíveis no campo **Mostrar**:

- **Todos** – Mostra todas as transações dos clientes selecionados (abertas e fechadas).
- **Fechada** – Mostra somente as transações que foram completamente liquidadas e fechadas.
- **Aberta** – Mostra somente as transações que não foram completamente liquidadas.
- **Abrir incluindo a data de fechamento ou a data posterior** – mostra somente as transações que não foram totalmente liquidadas na data especificada ou depois dela. Quando você selecionar esta opção, poderá alterar a data que é exibida ao lado do filtro. As transações com um valor **Última data de liquidação** na data especificada ou depois dela serão mostradas na lista, mesmo se essas transações forem totalmente liquidadas a partir da data atual. Porém, o saldo representa os saldos a partir da data atual, não a partir da data selecionada.

Marque a caixa de seleção **Ocultar reavaliações de moeda** para ocultar transações de conversão de moeda.

## <a name="modify-due-dates-and-discount-dates"></a>Modificar as datas de vencimento e as datas de desconto

Você pode atualizar datas de vencimento e datas de descontos para transações de cliente abertas. Na versão 8.1, você pode adicionar datas de vencimento à pagina de listagem **Transações de cliente**. Ao clicar na data de vencimento da página de listagem **Transações de cliente** , você também pode modificar as datas de vencimento, datas de desconto, condições de pagamento e condições de desconto à vista na caixa de diálogo **Atualizar a data de vencimento e as datas de desconto à vista**.

### <a name="activate-the-feature"></a>Ativar o recurso

Para adicionar datas de vencimento à pagina de listagem **Transações de cliente** e alterar as configurações de pagamento para uma transação usando a caixa de diálogo **Atualizar a data de vencimento e as datas de desconto à vista** , siga estas etapas.

1. Selecione **Contas a receber \> Configuração \> Parâmetros de contas a receber**.
2. Na guia **Liquidações** , defina a opção **Mostrar a data de vencimento e permitir edição** como **Sim**.
3. Para habilitar esse recurso, novos campos foram adicionados a transações de cliente. Esses campos serão preenchidos quando uma nova transação for concluída. Serão preenchidos também quando você abrir a caixa de diálogo **Atualizar a data de vencimento e as datas de desconto à vista** . Quando você definir a opção **Mostrar a data de vencimento e permitir edição** como **Sim**, você verá a caixa de diálogo **Atualizar informações de pagamento** .  Para atualizar imediatamente transações existentes, selecione **Atualizar todas as transações existentes**. Alternativamente, preencha os campos somente para novas transações, selecione **Continuar sem atualização**.

A data de vencimento foi adicionada à página de listagem **Transações de cliente**, para que você possa alterar com facilidade as datas de vencimento e a data de desconto à vista para transações.

### <a name="modify-the-payment-settings"></a>Alterar configurações de pagamento

A página de listagem **Transações de cliente** mostra todas as transações de um cliente. Quando você seleciona a data de vencimento de uma transação, a caixa de diálogo **Atualizar a data de vencimento e as datas de desconto à vista** será exibida. Esta caixa de diálogo mostra a data base para cálculos de data de vencimento e descontos, a data de vencimento, as condições de pagamento, as condições de desconto à vista e as datas de desconto à vista.

Cada campo tem um efeito diferente na transação ao editá-lo:

- **Editar a data base** - as datas de vencimento e de desconto são alteradas como se a data base fosse a data do documento.
- **Editar a data de vencimento** - somente a data de vencimento é alterada.
- **Editar as datas de desconto** - somente as datas de desconto são alteradas.
- **Editar as condições de pagamento** - a data de vencimento é alterada, com base na data base e nas condições de pagamento.
- **Editar as condições de desconto à vista** - os descontos à vista são alterados, com base na data base e nas condições de desconto à vista.

Quando você terminar de editar as configurações de pagamento, selecione **Fechar** para salvar as alterações.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
