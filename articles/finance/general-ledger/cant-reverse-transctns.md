---
title: Por que não é possível reverter esta transação?
description: Este artigo descreve os diferentes motivos pelos quais as transações não podem ser revertidas. Ele também lista soluções para esse problema.
author: kweekley
ms.date: 07/21/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2021-07-21
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 9a8b26584b1a9b82440583db693cd14daa580e22
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8876172"
---
# <a name="why-cant-i-reverse-this-transaction"></a>Por que não é possível reverter esta transação?

[!include [banner](../includes/banner.md)]

Este artigo descreve os diferentes motivos pelos quais as transações não podem ser revertidas. Ele também lista soluções para esse problema.

## <a name="symptom"></a>Sintoma

As organizações podem encontrar situações em que devem reverter uma transação lançada. Ocasionalmente, o sistema impedirá que elas revertam essas transações. Esse comportamento pode gerar duas perguntas:

- Por que não é possível reverter a transação?
- Como o recurso de reversão em massa afeta esse comportamento?

## <a name="resolution"></a>Resolução

As transações precisam atender a critérios específicos para que possam ser revertidas. As seções restantes deste artigo fornecem a validação para cada módulo. Embora este artigo se concentre em transações no Microsoft Dynamics 365 Finance, alguns dos conceitos e validação podem ser aplicados a outros aplicativos, como o Dynamics 365 Supply Chain Management.

Além disso, o local em que uma transação é revertida pode afetar a capacidade de reversão dela. Por exemplo, um pagamento de fornecedor que é lançado como um cheque pode ser revertido somente na seção **Cheques** na página de transação das contas bancárias. Não é possível revertê-lo na página **Transações de comprovante** na Contabilidade.

Se o recurso **Reversão em massa para vários documentos** (também conhecido como recurso Reversão em massa) estiver ativado na área de trabalho **Gerenciamento de recursos**, ele afetará a quantidade de transações que podem ser revertidas e onde elas podem ser revertidas. Este recurso oferece dois benefícios quando está ativado:

- Para alguns tipos de transação, mais de uma transação por vez pode ser selecionada e revertida no diário em que foi lançada ou na página **Transações de comprovante**. No entanto, as transações individuais tinham que ser reversíveis antes da ativação do recurso. Antes da introdução desse recurso, as transações precisavam ser revertidas uma por vez.
- *Algumas* transações do diário-razão auxiliar podem ser revertidas do diário (diário geral) ou da página **Transações de comprovante**. Elas não precisam ser revertidas da página do diário-razão auxiliar. Por exemplo, um diário de fatura de fornecedor anteriormente podia ser revertido somente na página **Transações do fornecedor**. No entanto, agora ele pode ser revertido também na Contabilidade, no diário ou na página **Transações de comprovante**. Cada seção deste artigo explica os tipos de transações aos quais esse benefício não se aplica.

O recurso Reversão em massa **não** habilita mais tipos de transação para reversão. Se um tipo de transação não podia ser revertido anteriormente, ele ainda não poderá ser revertido após a ativação do recurso. Por exemplo, não é possível reverter as faturas de fornecedor da ordem de compra, mesmo que o recurso Reversão em massa esteja ativado.

Para obter mais informações sobre o recurso Reversão em massa, consulte [Reverter lançamento do diário](reverse-journal-posting.md).

## <a name="general-ledger"></a>Contabilidade

Os ajustes da Contabilidade são inseridos somente usando contas contábeis. Portanto, eles atualizam somente a Contabilidade.

Se o recurso Reversão em massa estiver desativado, será possível reverter individualmente a maioria dos ajustes da contabilidade na página **Transações para \<main account\>** do razão (**LedgerTransAccount**). (O título exato da página varia, dependendo da conta principal selecionada). A página mostra cada transação que foi lançada na conta principal. Normalmente, ela é aberta na página **Lista de balancetes** ou selecionando **Transações** na página **Transações de comprovante**.

Se o recurso Reversão em massa estiver ativado, um ou mais comprovantes da contabilidade agora podem ser revertidos na página **Transações de comprovante** e no diário no qual a transação foi lançada. As exceções são: reavaliação de moeda estrangeira da Contabilidade, consolidação e transações de fechamento do exercício. Essas transações são revertidas nas páginas nas quais o fechamento do exercício foi executado.

### <a name="reasons-why-transactions-cant-be-reversed"></a>Motivos pelos quais não é possível reverter transações

Não é possível reverter transações pelos seguintes motivos:

- Diário geral:

    - O período fiscal está em espera ou fechado permanentemente:

        - Se a data de reversão for em um período fiscal que não está aberto, não será possível reverter a transação.
        - Se a transação oferecer suporte à entrada de uma data de reversão, ainda será possível reverter a transação alterando a data de reversão para um período aberto.

    - O processo de fechamento do exercício foi executado:

        - A data contábil da transação é em um ano fiscal que já passou pelo fechamento do exercício. Embora um período no ano fiscal ainda possa estar aberto, não será possível reverter a transação se o processo de fechamento do exercício tiver sido executado para o ano fiscal. O ano fiscal tem um status diferente dos períodos nele.
        - O fechamento do exercício pode ser revertido e, então, a transação pode ser revertida. Talvez essa abordagem não seja uma opção. Pode ser mais fácil inserir manualmente uma transação de reversão em um período aberto do ano fiscal fechado ou do próximo ano fiscal, dependendo do status do processo de fechamento fiscal. Se uma nova transação for lançada em um período aberto do ano fiscal que passou pelo processo de fechamento do exercício, o fechamento do exercício deverá ser executado novamente.

    - A reversão da transação já está em processo:

        - Se a transação estiver em processo de reversão, o processo deverá ser concluído. Não é possível realizar um processo separado de reversão. 
        - Depois da conclusão da reversão, uma transação revertida poderá ser revertida novamente (isto é, a reversão poderá ser revertida).

    - Liquidação do razão:

        - Se uma ou mais linhas da transação tiverem sido liquidadas pelo razão usando a tarefa periódica **Liquidações do razão** (**Contabilidade \> Tarefas periódicas \> Liquidações do razão**), de modo que o registro exista na tabela LedgerTransSettlement, não será possível reverter a transação.
        - A liquidação do razão pode ser revertida e, então, o comprovante pode ser revertido.

    - Intercompanhia:

        - Se a transação for intercompanhia, não será possível revertê-la.
        - A transação **não** é uma transação intercompanhia, mas é lançada em uma conta principal "devido a" ou "devido de" definida na página **Configuração intercompanhia**.

    - Provisões:

        - Se o comprovante de provisão da contabilidade for revertido, a entrada provisionada e todas as subtransações de provisão correspondentes serão revertidas.
        - Não é possível reverter as subtransações individuais da provisão.

- Diário de reconhecimento de receita:

    - Não é possível reverter transações de reconhecimento de receita.
    - Quando a receita é reconhecida por meio do diário de reconhecimento de receita, o comprovante é lançado somente em contas contábeis. Portanto, em páginas como **Transações de comprovante**, as transações aparecem como se fossem somente entradas da contabilidade.

- Reavaliação de moeda estrangeira:

    - As transações de reavaliação de moeda estrangeira podem ser revertidas, mas somente na página **Reavaliação de moeda estrangeira** da Contabilidade na qual a reavaliação foi executada.
    - A reversão só poderá ser concluída se for lançada em um período fiscal aberto.

- Consolidação:

    - As transações de consolidação podem ser revertidas, mas somente da página **Transações de consolidação**.
    - A reversão só poderá ser concluída se for lançada em um período fiscal aberto.

- Fechamento do exercício:

    - As transações de fechamento do exercício (transações de fechamento e de abertura) podem ser revertidas das seguintes maneiras:

        - Se o recurso de aprimoramentos de fechamento do exercício da Contabilidade estiver desativado, selecione a opção **Desfazer fechamento anterior** na caixa de diálogo **Fechamento do exercício**.
        - Se o recurso de aprimoramentos do exercício da Contabilidade estiver ativado, selecione os registros da empresa e do ano fiscal que foram criados para o fechamento do exercício na página **Fechamento do exercício** e selecione **Reverter fechamento do exercício**.

    - Observe que a reversão do fechamento do exercício na verdade exclui as transações de fechamento e de abertura. Um comprovante de reversão nunca é lançado.

## <a name="accounts-payable"></a>Contas a Pagar

Vários tipos de transação atualizam o diário-razão auxiliar de contas a pagar. Os exemplos incluem faturas de fornecedor, diários de faturas de fornecedor e relatórios de despesas.

Se o recurso Reversão em massa estiver desativado, as transações poderão ser revertidas individualmente na página **Transações do fornecedor** para faturas ou na página **Conta bancária** para pagamentos em cheque.

Se o recurso Reversão em massa estiver ativado, uma ou mais transações de contas a pagar também poderão ser revertidas na página **Transações de comprovante** e no diário no qual as transações foram lançadas. No entanto, os pagamentos do fornecedor ainda podem ser revertidos somente da conta bancária. Além disso, as transações de fornecedor não podem ser revertidas na página **Transações para \<main account\>** do razão. Elas só podem ser revertidas na página **Transações de comprovante**.

Observe que algumas transações nunca podem ser revertidas. Os exemplos incluem faturas de fornecedor da ordem de compra e pagamentos eletrônicos de fornecedor.

### <a name="reasons-why-vouchers-cant-be-reversed"></a>Motivos pelos quais não é possível reverter comprovantes

Não é possível reverter comprovantes pelos seguintes motivos:

- O período fiscal está em espera ou fechado:

    - Se a data de reversão for em um período fiscal que não está aberto, não será possível reverter a transação.
    - Se a transação oferecer suporte à entrada de uma data de reversão, ainda será possível reverter a transação alterando a data de reversão para um período aberto.

- O processo de fechamento do exercício da Contabilidade foi executado:

    - A data contábil da transação é em um ano fiscal que já foi encerrado na Contabilidade. Embora um período no ano fiscal ainda possa estar aberto, não será possível reverter a transação se o processo de fechamento do exercício tiver sido executado para o ano fiscal. O ano fiscal tem um status diferente dos períodos nele.
    - O fechamento do exercício pode ser revertido e, então, a transação pode ser revertida. Talvez essa abordagem não seja uma opção. Pode ser mais fácil inserir manualmente uma transação de reversão em um período aberto do ano fiscal fechado ou do próximo ano fiscal, dependendo do status do processo de fechamento fiscal. Se uma nova transação for lançada em um período aberto do ano fiscal que passou pelo processo de fechamento do exercício, o fechamento do exercício deverá ser executado novamente.

- A entrada no diário-razão auxiliar não foi transferida para a Contabilidade:

    - Esse motivo se aplica apenas a faturas de fornecedor com ordens que não são de compra.
    - Use a página **Entradas do diário-razão auxiliar ainda não transferidas** para transferir a entrada para a Contabilidade. A fatura do fornecedor da ordem que não é compra poderá então ser revertida na página **Transações do fornecedor**.

- Liquidação:

    - A transação (como uma fatura ou um pagamento) é liquidada ou marcada para liquidação.

        - Você pode verificar se uma transação está liquidada ou marcada para liquidação ao selecionar **Exibir liquidações** ou **Liquidação \> Histórico de liquidação** na página **Transações do fornecedor**.
        - Você também pode reverter uma liquidação na página **Transações do fornecedor** (**Liquidação \> Desfazer liquidação**) se uma das transações precisar ser revertida.

- O comprovante contém mais de uma transação do diário-razão auxiliar que foi inserida usando o mesmo número de comprovante (problema de um comprovante).
- A fatura não foi aprovada:

    - Se a caixa de seleção **Aprovação** não estiver selecionada na fatura, a fatura não poderá ser revertida.

        - Nesse caso, a aprovação não se refere a aprovações no processo de fluxo de trabalho, mas à opção **Aprovação** na fatura. Essa opção é usada para impedir que uma fatura seja paga. Normalmente, é usada para faturas de registro de fatura de fornecedor.

- A transação está no pool de transações:

    - Não é possível reverter uma fatura no pool diretamente da página **Transações do fornecedor**. Em vez disso, ela precisará ser revertida através do processo de cancelamento na página **Diário de aprovação de fatura**.

- A transação tem uma fatura pai que foi corrigida (localização para a Índia).
- A transação tem um status promissório de **Fatura remetida**.
- A transação é usada para uma liquidação de imposto parcial.
- A transação contém uma conta de fornecedor, mas está sendo revertida em uma página incorreta, como a página **Transações para \<main account\>**:

    - Como este motivo sugere, mesmo quando o recurso Reversão em massa está ativado, algumas transações do diário-razão auxiliar podem ser revertidas somente de páginas específicas.

### <a name="types-of-transactions-that-cant-be-reversed"></a>Tipos de transação que não podem ser revertidas

Não é possível reverter estes tipos de transação:

- Reavaliação de moeda estrangeira:

    - Diferentemente da reavaliação de moeda estrangeira da Contabilidade, não é possível reverter a reavaliação de moeda estrangeira de contas a pagar e contas a receber. Em vez disso, a reavaliação precisa ser executada novamente usando a data da nota fiscal. Nesse caso, a reavaliação usará a taxa de câmbio da data da fatura e, essencialmente, apresentará a perda ou o ganho não realizado como 0 (zero). Portanto, o resultado lembra o resultado da reversão da reavaliação anterior. No entanto, observe que o mesmo valor não será revertido se a taxa de câmbio padrão tiver sido alterada na fatura.

- Fatura de fornecedor de ordem de compra:

    - Uma nota de crédito precisa ser criada para reverter a fatura de fornecedor. Para obter mais informações sobre como criar uma transação de reversão, consulte [Criar uma ordem de devolução de compra](../../supply-chain/procurement/tasks/create-purchase-return-order.md).

- Nota Promissória
- Remessa de exportação de carta de crédito do banco

## <a name="accounts-receivable"></a>Contas a Receber

Vários tipos de transação atualizam os diários-razão auxiliares de contas a receber. Os exemplos incluem faturas de clientes de ordens de venda, faturas de clientes que são inseridas através do diário geral, faturas de texto livre, pagamentos de clientes e baixas.

Se o recurso Reversão em massa estiver desativado, as transações poderão ser revertidas individualmente na página **Transações do cliente** para faturas, ou na página **Contas bancárias** para depósitos em cheque. Para obter informações sobre como reverter um pagamento, consulte a seção [Gerenciamento de caixa e de bancos](cant-reverse-transctns.md#cash-and-bank-management) posteriormente neste artigo.

Se o recurso Reversão em massa estiver ativado, uma ou mais transações de contas a receber também poderão ser revertidas na página **Transações de comprovante** e no diário em que elas foram lançadas. No entanto, os depósitos ainda podem ser revertidos somente na conta bancária, e as faturas de texto livre podem ser revertidas somente na página de origem (se o recurso que permite correções estiver ativado). Além disso, as transações de cliente ainda não podem ser revertidas na página **Transações para \<main account\>** do razão. No entanto, elas podem ser revertidas na página **Transações de comprovante**.

Observe que algumas transações não podem ser revertidas. Os exemplos incluem as faturas de ordem de venda e as baixas.

### <a name="reasons-why-transactions-cant-be-reversed"></a>Motivos pelos quais não é possível reverter transações

Não é possível reverter transações pelos seguintes motivos:

- O período fiscal está em espera ou fechado permanentemente:

    - Se a data de reversão for em um período fiscal que não está aberto, não será possível reverter a transação.
    - Se a transação oferecer suporte à entrada de uma data de reversão, ainda será possível reverter a transação alterando a data de reversão para um período aberto.

- O processo de fechamento do exercício da Contabilidade foi executado:

    - A data contábil da transação é em um ano fiscal que já passou pelo fechamento do exercício da Contabilidade. Embora um período no ano fiscal ainda possa estar aberto, não será possível reverter a transação se o processo de fechamento do exercício tiver sido executado para o ano fiscal. O ano fiscal tem um status diferente dos períodos nele.
    - O fechamento do exercício pode ser revertido e, então, a transação pode ser revertida. Talvez essa abordagem não seja uma opção. Pode ser mais fácil inserir manualmente uma transação de reversão em um período aberto do ano fiscal fechado ou do próximo ano fiscal, dependendo do status do processo de fechamento fiscal. Se uma nova transação for lançada em um período aberto do ano fiscal que passou pelo processo de fechamento do exercício, o fechamento do exercício deverá ser executado novamente.

- A entrada no diário-razão auxiliar não foi transferida para a Contabilidade:

    - Esse motivo se aplica somente a faturas de texto livre.
    - Use a página **Entradas do diário-razão auxiliar ainda não transferidas** para transferir a entrada para a Contabilidade. A fatura de texto livre poderá então ser revertida ou corrigida se a funcionalidade de correções estiver habilitada.

- Liquidação:

    - A transação (como uma fatura ou um pagamento) é liquidada ou marcada para liquidação.

        - Você pode verificar se uma transação está liquidada ou marcada para liquidação ao selecionar **Exibir liquidações** ou **Liquidação \> Histórico de liquidação** na página **Transações do cliente**.
        - Você também pode reverter uma liquidação na página **Transações do cliente** (**Liquidação \> Desfazer liquidação**) se uma das transações precisar ser revertida.

- A transação contém mais de uma transação do diário-razão auxiliar que foi inserida usando o mesmo número de comprovante (problema de um comprovante).
- A fatura não foi aprovada:

    - Se a caixa de seleção **Aprovação** não estiver selecionada na fatura, a fatura não poderá ser revertida.

        - Nesse caso, a aprovação não se refere a aprovações no processo de fluxo de trabalho, mas à opção **Aprovação** nas linhas do comprovante. Essa opção é usada para impedir que uma fatura seja paga. Embora essa opção seja normalmente usada em contas a pagar, ela também está disponível para faturas de contas a receber inseridas por meio de diários.

- A transação tem uma fatura pai que foi corrigida (localização para a Índia).
- A transação contém uma conta de cliente, mas está sendo revertida em uma página incorreta, como a página **Transações para \<main account\>**:

    - Como este motivo sugere, mesmo quando o recurso Reversão em massa está ativado, algumas transações do diário-razão auxiliar podem ser revertidas somente de páginas específicas.

### <a name="types-of-transactions-that-cant-be-reversed"></a>Tipos de transação que não podem ser revertidas

Não é possível reverter estes tipos de transação:

- Reavaliação de moeda estrangeira:

    - Diferentemente da reavaliação de moeda estrangeira da Contabilidade, não é possível reverter a reavaliação de moeda estrangeira de contas a pagar e contas a receber. Em vez disso, a reavaliação precisa ser executada novamente usando a data da nota fiscal. Nesse caso, a reavaliação usará a taxa de câmbio da data da fatura e, essencialmente, apresentará a perda ou o ganho não realizado como 0 (zero). Portanto, o resultado lembra o resultado da reversão da reavaliação anterior. No entanto, observe que o mesmo valor não será revertido se a taxa de câmbio padrão tiver sido alterada na fatura.

- Uma transação que tenha ajustado a retenção de imposto
- Fatura de cliente de ordem de venda:

    - Uma nota de crédito ou uma devolução precisa ser criada para reverter a transação. Para obter informações sobre como criar a transação de reversão, consulte [Devoluções de vendas](../../supply-chain/warehousing/sales-returns.md).

- Letra de Câmbio
- Transação de caixa registradora
- Ajuste avançado
- Nota de juros
- Carta de cobrança
- Carta de crédito do banco
- Remessa de exportação
- Diário de reconhecimento de receita:

    - Quando você reconhece receita por meio do diário de reconhecimento de receita, os comprovantes são lançados em contas contábeis. Portanto, eles aparecem como se fossem apenas entradas da contabilidade. Não é possível reverter essas entradas porque a agenda de receita não será reaberta para reconhecer a receita novamente.

## <a name="cash-and-bank-management"></a>Gerenciamento de caixa e bancos

Vários tipos de transação atualizam o Diário-auxiliar do banco usando o diário geral. Os exemplos incluem pagamentos de fornecedor, pagamentos de cliente e transferências bancárias.

Se o recurso Reversão em massa estiver desativado, as transações poderão ser revertidas individualmente na página **Contas bancárias** para cheques e depósitos, ou na página **Transações de cliente** para pagamentos do cliente.

Se o recurso Reversão em massa estiver ativado, uma ou mais transações de pagamento também poderão ser revertidas na página **Transações de comprovante** e no diário no qual as transações foram lançadas. No entanto, os depósitos ainda podem ser revertidos somente da conta bancária. Além disso, as transações bancárias ainda não podem ser revertidas na página **Transações para \<main account\>** do razão. No entanto, elas podem ser revertidas na página **Transações de comprovante**.

Observe que algumas transações não podem ser revertidas. Os exemplos incluem pagamentos eletrônicos de fornecedor.

### <a name="reasons-why-transactions-cant-be-reversed"></a>Motivos pelos quais não é possível reverter transações

Não é possível reverter transações pelos seguintes motivos:

- O período fiscal está em espera ou fechado permanentemente:

    - Se a data de reversão for em um período fiscal que não está aberto, não será possível reverter a transação.
    - Se a transação oferecer suporte à entrada de uma data de reversão, ainda será possível reverter a transação alterando a data de reversão para um período aberto.

- O processo de fechamento do exercício da Contabilidade foi executado:

    - A data contábil da transação é em um ano fiscal que já passou pelo fechamento do exercício da Contabilidade. Embora um período no ano fiscal ainda possa estar aberto, não será possível reverter a transação se o processo de fechamento do exercício tiver sido executado para o ano fiscal. O ano fiscal tem um status diferente dos períodos nele.
    - O fechamento do exercício pode ser revertido e, então, a transação pode ser revertida. Talvez essa abordagem não seja uma opção. Pode ser mais fácil inserir manualmente uma transação de reversão em um período aberto do ano fiscal fechado ou do próximo ano fiscal, dependendo do status do processo de fechamento fiscal. Se uma nova transação for lançada em um período aberto do ano fiscal que passou pelo processo de fechamento do exercício, o fechamento do exercício deverá ser executado novamente.

- Liquidação:

    - A transação (pagamento) é liquidada ou marcada para liquidação.

        - Você pode verificar se uma transação está liquidada ou marcada para liquidação ao selecionar **Exibir liquidações** ou **Liquidação \> Histórico de liquidação** na página **Transações do fornecedor** ou **Transações do cliente**.
        - Você também pode reverter uma liquidação na página **Transações do fornecedor** ou **Transações do cliente** (**Liquidação \> Desfazer liquidação**) se uma das transações precisar ser revertida.

- A transação contém mais de uma transação do diário-razão auxiliar que foi inserida usando o mesmo número de comprovante (problema de um comprovante).
- Transações de transição:

    - Se a transação estiver relacionada a um pagamento de transição, ela não poderá ser revertida.
    - Se o pagamento de transição precisar ser revertido, ele primeiro deverá ser removido da conta de transição para o banco. O pagamento poderá então ser revertido, desde que atenda aos outros critérios de validação.

- A transação contém uma conta bancária, mas está sendo revertida da página **Transações para \<main account\>** ou de um diário-razão auxiliar incorreto, como Contas a receber ou Contas a pagar:

    - Como este motivo sugere, mesmo quando o recurso Reversão em massa está ativado, algumas transações do diário-razão auxiliar podem ser revertidas somente de páginas específicas.

- Reavaliação de moeda estrangeira do banco:

    - A reavaliação de moeda estrangeira do banco pode ser revertida. No entanto, a reversão poderá ser evitada se você concluir as etapas de reversão fora da ordem cronológica. Por exemplo, se você executou a reavaliação em março e abril, a reavaliação de março não poderá ser revertida até que a reavaliação de abril seja revertida.

### <a name="types-of-transactions-that-cant-be-reversed"></a>Tipos de transação que não podem ser revertidas

Não é possível reverter estes tipos de transação:

- Pagamentos do fornecedor que foram feitos como transferências eletrônicas de fundos (EFTs)
- Notas Promissórias
- Letras de câmbio

## <a name="fixed-assets"></a>Ativos Fixos

Vários tipos de transação atualizam o diário-razão auxiliar de Ativos fixos. Os exemplos incluem aquisições e depreciação.

Se o recurso Reversão em massa estiver desativado, as transações poderão ser revertidas individualmente na página **Transações do fornecedor**, na página **Transações de ativo fixo**, ou no Arrendamento de ativos, dependendo do tipo de transação.

Se o recurso Reversão em massa estiver ativado, uma ou mais transações de Ativo fixo também poderão ser revertidas na página **Transações de comprovante** no diário no qual as transações foram lançadas.

### <a name="reasons-why-transactions-cant-be-reversed"></a>Motivos pelos quais não é possível reverter transações

Não é possível reverter transações pelos seguintes motivos:

- O período fiscal está em espera ou fechado permanentemente:

    - Se a data de reversão for em um período fiscal que não está aberto, não será possível reverter a transação.
    - Se a transação oferecer suporte à entrada de uma data de reversão, ainda será possível reverter a transação alterando a data de reversão para um período aberto.

- O processo de fechamento do exercício da Contabilidade foi executado:

    - A data contábil da transação é em um ano fiscal que já foi encerrado na Contabilidade. Embora um período no ano fiscal ainda possa estar aberto, não será possível reverter a transação se o processo de fechamento do exercício tiver sido executado para o ano fiscal. O ano fiscal tem um status diferente dos períodos nele.
    - O fechamento do exercício pode ser revertido e, então, a transação pode ser revertida. Talvez essa abordagem não seja uma opção. Pode ser mais fácil inserir manualmente uma transação de reversão em um período aberto do ano fiscal fechado ou do próximo ano fiscal, dependendo do status do processo de fechamento fiscal. Se uma nova transação for lançada em um período aberto do ano fiscal que passou pelo processo de fechamento do exercício, o fechamento do exercício deverá ser executado novamente.

- Aquisições:

    - Se a aquisição ocorreu em uma fatura de fornecedor da ordem de compra, a reversão precisa ser realizada inserindo uma nota de crédito do fornecedor. Para obter mais informações sobre como inserir a transação de reversão, consulte [Criar uma ordem de devolução de compra](../../supply-chain/procurement/tasks/create-purchase-return-order.md).
    - A aquisição ocorreu em uma transação de projeto.
    - Não é possível reverter a aquisição após a depreciação ser lançada para o ativo. A depreciação precisa ser revertida para que a aquisição possa ser revertida.
    - Se o status do modelo de valor ou do registro de depreciações de um ativo fixo não estiver aberto, a transação não poderá ser revertida.

- Alienações:

    - A alienação é feita por meio de uma fatura de texto livre:

        - A correção de uma fatura de texto livre será bloqueada se contiver um ativo fixo. No entanto, se o ativo for alienado por meio de um diário, a fatura de texto livre poderá ser revertida do registro de ativo fixo.

    - Se o status do modelo de valor ou do registro de depreciações de um ativo fixo não estiver aberto, a transação não poderá ser revertida.

- Depreciação:

    - A depreciação **poderá** ser revertida se a depreciação subsequente também for lançada. No entanto, você receberá um aviso, pois essa abordagem não é uma prática recomendada.
    - Se o status do modelo de valor ou do registro de depreciações de um ativo fixo não estiver aberto, a transação não poderá ser revertida.

- As transações (ou transações revertidas) de um ativo e um registro de ativos específicos existem para a data da transação do comprovante ou posterior.
- A transação contém uma conta de ativo, mas está sendo revertida da página **Transações para \<main account\>** ou de um diário-razão auxiliar incorreto, como Contas a receber ou Contas a pagar:

    - Como este motivo sugere, mesmo quando o recurso Reversão em massa está ativado, algumas transações do diário-razão auxiliar podem ser revertidas somente de páginas específicas.
    - Se ocorrer uma aquisição em uma fatura de fornecedor de ordem que não seja de compra ou em um diário de fatura de fornecedor, ela poderá ser revertida somente na página **Transações do fornecedor** no Contas a pagar.
    - Se um ativo for adquirido de Arrendamento de ativos, ele poderá ser revertido na página **Transações de passivo** em Arrendamento de ativos.
