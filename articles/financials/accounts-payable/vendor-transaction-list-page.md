---
title: "Página da lista de transações de fornecedor"
description: "Este tópico fornece informações sobre a página de listagem Transações de fornecedor para o Microsoft Dynamics 365 for Finance and Operations."
author: mikefalkner
manager: aolson
ms.date: 08/24/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: VendTrans
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mikefalkner
ms.search.validFrom: 2018-10-31
ms.dyn365.ops.version: 8.1
ms.translationtype: HT
ms.sourcegitcommit: c5d4fb53939d88fcb1bd83d70bc361ed9879f298
ms.openlocfilehash: 53740f6ed0d463de5ba962f1ba15b208634a0739
ms.contentlocale: pt-br
ms.lasthandoff: 10/01/2018

---

# <a name="vendor-transactions-list-page"></a>Página da lista de transações de fornecedor

[!include [banner](../includes/banner.md)]

## <a name="view-settlements"></a>Exibir liquidações

O botão **Exibir liquidações** no Painel de Ação fornece acesso rápido ao histórico de liquidações e mais informações sobre toda a transação de liquidação. Também é possível exibir transações adicionais relacionadas à transação selecionada, porque elas faziam parte da mesma liquidação ou porque são pagamentos criados no mesmo diário de pagamento.

1. Selecione **Contas a pagar \> Todos os fornecedores**.
2. Selecione um fornecedor com transações e, em seguida, no Painel de Ações, na guia **Fornecedor** , selecione **Transações**.
3. Selecione uma transação para pesquisar, em seguida, no Painel da Ação, selecione **Exibir liquidações**.

    A caixa de diálogo **Exibir liquidações** é exibida e mostra a transação selecionada e todos os documentos que foram liquidados em relação a ela. Essa caixa de diálogo é semelhante à exibição do histórico de liquidações, mas inclui todos os documentos relacionados.

4. Na caixa de diálogo, você pode executar várias tarefas. Selecione um ou mais comprovantes e, em seguida, selecione um dos seguintes botões:

    - **Exibir relacionado** – Mostra todas as transações do diário de pagamento criadas no diário de pagamento relacionado ao documento selecionado. Além disso, todas as liquidações relacionadas a esses pagamentos são exibidas. Quando você exibe os pagamentos relacionados, o rótulo desse botão é alterado para **Exibir liquidações**. Selecione **Exibir liquidações** para mostrar apenas as transações que foram exibidas quando você abriu a caixa de diálogo **Exibir liquidações**.
    - **Exibir histórico** – Exibe o histórico de liquidação dos comprovantes. Selecione **Fechar** para fechar a caixa de diálogo.
    - **Exibir contabilidade** – Mostra todos os comprovantes relacionados aos documentos selecionados. Selecione **Fechar** para fechar a caixa de diálogo.
    - **Exportar** – Exportar os comprovantes selecionados para o Microsoft Excel.
    - **Liquidar transações** – Este botão aparece somente se o documento original que foi selecionado não foi totalmente liquidado. Ao selecioná-lo, é exibida a caixa de diálogo **Liquidar transações**, na qual você pode selecionar transações para liquidação.
    - **Desfazer liquidações** – Este botão aparece somente se o documento original selecionado foi totalmente liquidado. Ao selecioná-lo, é exibida a caixa de diálogo **Desfazer liquidações**, na qual você pode desfazer as liquidações que foram feitas para esse documento.

## <a name="global-transactions"></a>Transações globais

O botão **Transações globais** foi adicionado ao fornecedor. Este botão permite exibir todas as transações de um fornecedor em todas as entidades legais. A página de listagem **Transações de fornecedor** mostra apenas transações para entidades legais às quais o usuário tem acesso, com base nas configurações de segurança.

A página de listagem mostrará todas as transações de fornecedores que têm o mesmo ID de participante do fornecedor com o qual você começou. Por exemplo, se o fornecedor US-001 em uma entidade legal tem o mesmo ID de participante do fornecedor DE-001 em outra entidade legal, todas as transações para os dois IDs do fornecedor são exibidas.

Os menus na página **Transações de fornecedor** podem variar, de acordo com a entidade legal da transação. Por exemplo, se um recurso estiver disponível apenas para entidades legais suíças, as opções do menu para o recurso serão exibidas somente quando uma transação da Suíça for selecionada.

Para acessar o recurso, siga essas etapas.

1. Selecione **Contas a pagar** \> **Todos os fornecedores**.
2. Selecione um fornecedor e, no Painel de Ações, na guia **Fornecedor**, no grupo **Transações**, selecione **Transações globais**.

## <a name="more-transaction-filters"></a>Mais filtros de transação

O filtro para mostrar transações abertas foi substituído por um novo filtro que permite exibir mais combinações de transações. As seguintes opções estão disponíveis no campo **Mostrar**:

- **Todos** – Visualize todas as transações dos fornecedores selecionados (abertas e fechadas).
- **Fechada** – Mostra somente as transações que foram completamente liquidadas e fechadas.
- **Aberta** – Mostra somente as transações que não foram completamente liquidadas.
- **Abrir a partir da data** – Mostra somente as transações que não foram totalmente liquidadas a partir da data especificada. Quando você selecionar esta opção, poderá alterar a data que é exibida ao lado do filtro. As transações que possuem um valor **Última data de liquidação** após a data especificada serão mostradas na lista, mesmo se essas transações forem totalmente liquidadas a partir da data atual. Porém, o saldo representa os saldos a partir da data atual, não a partir da data selecionada.

Um filtro também foi adicionado que permite ocultar transações de conversão de moeda. Basta marcar a a caixa de seleção **Ocultar reavaliações de moeda** .

## <a name="more-easily-modify-due-dates-and-discount-dates"></a>Modificar as datas de vencimento e as datas de desconto mais facilmente

Você pode atualizar datas de vencimento e datas de descontos para transações de cliente abertas. Na versão 8.1, a experiência foi melhorada. Agora você pode adicionar datas de vencimento à pagina de listagem **Transações de fornecedor** . Ao clicar na data de vencimento da página de listagem **Transações de fornecedor** , você também pode modificar as datas de vencimento, datas de desconto, condições de pagamento e condições de desconto à vista na caixa de diálogo **Atualizar a data de vencimento e as datas de desconto à vista**.

### <a name="activate-the-feature"></a>Ativar o recurso

Para adicionar datas de vencimento à pagina de listagem **Transações de fornecedor** e alterar as configurações de pagamento para uma transação por meio da caixa de diálogo **Atualizar a data de vencimento e as datas de desconto à vista** , siga estas etapas.

1. Selecione **Contas a pagar \> Configuração \> Parâmetros de contas a pagar**.
2. Na guia **Liquidações** , defina a opção **Mostrar a data de vencimento e permitir edição** como **Sim**.
3. Para habilitar esse recurso, novos campos foram adicionados a transações de fornecedor. Esses campos serão preenchidos quando uma nova transação for concluída. Serão preenchidos também quando você abrir a caixa de diálogo **Atualizar a data de vencimento e as datas de desconto à vista** . Quando você definir a opção **Mostrar a data de vencimento e permitir edição** como **Sim**, você verá a caixa de diálogo **Atualizar informações de pagamento** .  Para atualizar imediatamente transações existentes, selecione **Atualizar todas as transações existentes**. Alternativamente, preencha os campos somente para novas transações, selecione **Continuar sem atualização**.

A data de vencimento foi adicionada à página de listagem **Transações de fornecedor**, e você pode alterar as datas de vencimento e a data de desconto à vista para transações com mais facilidade.

### <a name="modify-the-payment-settings"></a>Alterar configurações de pagamento

A página de listagem **Transações de fornecedor** mostra todas as transações de um fornecedor. Quando você seleciona a data de vencimento para uma transação, uma caixa de diálogo é exibida. Esta caixa de diálogo mostra a data base para cálculos de data de vencimento e descontos, a data de vencimento, condições de pagamento, condições de desconto à vista e as datas de desconto à vista.

Cada campo tem um efeito diferente na transação ao editá-lo:

- **Editar a data base:** As datas de vencimento e de desconto são alteradas como se a data base fosse a data do documento.
- **Editar a data de vencimento:** somente a data de vencimento é alterada
- **Edite as datas de desconto:** Somente as datas de desconto são alteradas.
- **Edite as condições de pagamento:** A data de vencimento é alterada, com base na data base e nas condições de pagamento.
- **Edite as condições de desconto à vista:** Os descontos à vista são alterados, com base na data base e nas condições de desconto à vista.

Quando você terminar de editar as configurações de pagamento, selecione **Fechar** para salvar as alterações.

