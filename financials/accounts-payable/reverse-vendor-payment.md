---
title: Estornar um pagamento do fornecedor
description: "Este artigo descreve as diferenças entre estornar, excluir, anular e rejeitar um pagamento. Além disso, explica os dois métodos para estornar um cheque de fornecedor."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: BankChequeTable, LedgerJournalTransBankChequeReversal, LedgerJournalTransVendPaym
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 14361
ms.assetid: 9f0a1883-cbe0-4cc7-b9f3-dd12fb85ebe8
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 2cb439e871d57f74c296697cfc42705fb0121bb7
ms.openlocfilehash: 716134b2230683050b234297e475d9331fbc7dab
ms.lasthandoff: 03/31/2017


---

# <a name="reverse-a-vendor-payment"></a>Estornar um pagamento do fornecedor

[!include[banner](../includes/banner.md)]


Este artigo descreve as diferenças entre estornar, excluir, anular e rejeitar um pagamento. Além disso, explica os dois métodos para estornar um cheque de fornecedor. 

Ocasionalmente, depois que um pagamento de fornecedor foi lançado, o pagamento deve ser estornado. O estorno é diferente da exclusão, da anulação, ou da rejeição de um pagamento. Você pode excluir um pagamento somente se o status for **Criado**. Esse status indica que o pagamento foi criado, mas ainda não foi gerado. Esta limitação sempre se aplica, independentemente do método de pagamento. Você pode cancelar cheques não postados depois de terem sido gerados, mas antes de serem postados. Se o pagamento gerado for feito como uma transferência eletrônica de fundos (EFT), você pode rejeitar o pagamento antes de ser lançado. Para rejeitar um pagamento, altere p valor **Status do pagamento**. Um pagamento que tenha sido anulado ou rejeitado pode ser regenerado após o valor **Status de pagamento** ser alterado para **Nenhum**. 

Depois que um pagamento é lançado, as reversões são usadas. Pagamentos que são feitos eletronicamente não podem ser revertidos depois que eles foram postados. Em vez disso, uma nova transação deverá ser criada para o valor do pagamento para obter o passivo de volta na conta do fornecedor. Há dois métodos para estornar cheques lançados. Em um método, os estornos são lançados imediatamente quando você clica em **Estorno de pagamento** na página **Cheque**. No outro método, quando você clicar em **Estorno de pagamento** na página **Cheque**, o estorno é enviado ao diário de estorno de cheque no Gerenciamento de caixa e bancos, onde um revisor poderá lançar ou rejeitar o estorno. 

Para saber qual método sua organização usa, exiba a página **Parâmetros de gerenciamento de caixa e bancos**. Se a opção **Usar processo de revisão para estornos de pagamento** for definida como **Sim**, os estornos são enviados para o diário de estornos de cheques para revisão. A tabela a seguir descreve como os métodos de estornos de cheque são diferentes.

| Se sua organização não examinar estornos de cheque antes do lançamento                                                                                                                                  | Se sua organização examina estornos de cheque antes do lançamento                                                                                                                                                                                                                                                                                                                                                                     |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| O cheque é estornado imediatamente quando você clica em **OK** na página **Cheque**.                                                                                                                      | O cheque não é estornado imediatamente. Um diário de estornos de cheque é criado para revisão. Se o diário de estornos de cheque for excluído, a verificação pode ser revertida novamente.                                                                                                                                                                                                                                                                |
| As entradas da contabilidade para o cheque original são revertidas.                                                                                                                                         | A conta contábil da entrada contábil do cheque original não pode ser lançada. As dimensões financeiras do diário do cheque original são usadas como as dimensões financeiras padrão no diário de estornos de cheque. Você pode alterar esses valores padrão. Quando o diário de estornos de cheque for lançado, as contas principais do Contas a pagar serão inseridas automaticamente a partir dos perfis de lançamento, que podem ser alterados. |
| As estruturas de contabilidade que foram usadas quando o cheque original foi lançado são usadas para reverter o cheque, mesmo se a estrutura da conta tiver sido alterada. A combinação de conta não é validada. | Se uma estrutura de conta foi alterada depois que o cheque original foi lançado, uma nova dimensão financeira pode ser necessária para o estorno do cheque. Essa dimensão financeira não pode ser inserida automaticamente no diário de pagamento original. A combinação de conta é validada quando o estorno do cheque é lançado.                                                                                                        |
| As dimensões fixas não são aplicadas ao estorno, para ajudar a garantir que as mesmas contas contábeis são estornadas.                                                                                      | As dimensões fixas são aplicadas ao diário de estornos de cheque durante o lançamento. O valor de dimensão financeira pode não existir na entrada contábil do cheque original, dependendo de quando a dimensão fixa foi definida.                                                                                                                                                                                                     |

## <a name="reverse-posted-checks-without-reviewing-them"></a>Estornos de cheques lançados sem serem examinados
Se sua organização quiser lançar de imediato estornos de cheque ao clicar no formulário **Estorno de pagamento** na página **Cheques**. Na página **Parâmetros de gerenciamento de caixa e bancos**, defina a opção **Usar processo de revisão para estornos de pagamento** como **Não**. Na página **Cheques**, você pode selecionar o cheque para estorno e selecionar **Estorno de pagamento**. É possível digitar a data e selecionar o motivo do estorno.

## <a name="reverse-posted-checks-after-they-are-reviewed-in-the-check-reversal-journal"></a>Estornar cheques lançados eles serem revisados no diário de estornos de cheque
Se sua organização quiser revisar estornos de cheques antes de eles serem lançados, crie um diário de estornos de cheque para revisão na página **Parâmetros de gerenciamento de caixa e bancos**, defina a opção **Usar processo de revisão para estornos de pagamento** como **Sim**. Na página **Cheques** você pode selecionar o cheque para estorno, selecionar **Estorno de pagamento**. É possível digitar a data e selecionar o motivo do estorno. Você também deverá selecionar um nome de diário para criar um diário de estorno de cheque.

### <a name="review-a-reversal"></a>Revisar um estorno

Se você for um usuário que precisa revisar estornos, você pode aprovar e lançar o diário, ou rejeitar o estorno, excluindo o diário. Na página **diário de estornos de cheque**, você pode selecionar o diário de estorno para revisar e clicar em **Linhas**. Você pode revisar o cheque estornado e selecionar uma das seguintes opções de aprovação:

-   Para aprovar e lançar o diário de estorno, clique em **Lançar** ou em **Lançar e transferir**.
-   Para rejeitar o estorno, exclua o diário de estornos de cheques.

> [!NOTE]
> Se você excluir o diário, o estorno será removido do sistema, mas o cheque original permanecerá na página **Cheque**. O status do cheque não é mais **Cancelamento pendente**.

## <a name="results-of-posting-a-reversal"></a>Resultados do lançamento de um estorno
Veja o que acontece quando você lança um estorno de cheque:

-   O status do cheque é atualizado para **Cancelamento**.
-   Se a opção **Reconciliar** foi selecionada na página de estorno durante o estorno, o cheque é reconciliado (a opção **Reconciliado** é selecionada) e não aparece na página **Reconciliação da conta**.
-   O comprovante do estorno é lançado na conta bancária da qual o cheque foi emitido, para aumentar o saldo da conta.
-   O comprovante é lançado na Contabilidade.
-   Os detalhes de modificação são atualizados no grupo de campos **Histórico** na página **Cheque**.

> [!NOTE] 
> Quando você estorna um cheque emitido para uma transação de comércio intercompanhia, as entradas de compensação vêm da configuração de contabilidade para comércio intercompanhia, e não da transação original. Se o cheque estornado foi emitido para um pagamento de fornecedor, o seguinte também ocorre:

-   O pagamento original da fatura contra a qual o pagamento foi liquidado não é aplicado (a liquidação é estornada).
-   Uma transação é lançada contra o fornecedor da conta para o estorno do pagamento e o pagamento estornado é liquidado contra o pagamento original. O campo **Último comprovante de liquidação** na página **Transações do fornecedor** para o pagamento original ao fornecedor é atualizado para refletir o número do comprovante da transação estornada.

Se o cheque estornado foi emitido para um reembolso de cliente, o seguinte também ocorre:

-   Uma transação é lançada contra a conta do cliente para o estorno do pagamento e a liquidação entre o pagamento original e o documento contra o qual o pagamento foi liquidado originalmente é estornado (cria-se um pagamento negativo).
-   Um estorno de pagamento é aplicado ao pagamento original. O campo **Último comprovante de liquidação** na página **Transações do cliente** para o pagamento original ao cliente é atualizado para refletir o número do comprovante da transação estornada.





