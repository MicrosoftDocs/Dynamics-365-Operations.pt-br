---
title: Reconciliar uma conta bancária
description: Este artigo descreve como reconciliar uma conta bancária.
author: angelad116
ms.date: 11/16/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: angelading
ms.search.validFrom:
- month/year of release that feature was introduced in
- in format yyyy-mm-dd
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 576dcd320600f4741a43bfeee53198637bffce15
ms.sourcegitcommit: cf6b764824bd1cf2c0dde6d37ddd0a7abab87ff0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/16/2022
ms.locfileid: "9779518"
---
# <a name="reconcile-a-bank-account"></a>Reconciliar uma conta bancária

[!include[banner](../includes/banner.md)]

Quando receber um extrato bancário, você deve periodicamente reconciliar as transações bancárias de entidade legal com as transações no extrato bancário.

Não é possível reconciliar um extrato bancário com uma conta bancária se algum pagamento de cheque ou guia de depósito listado no extrato tiver, no momento, o status **Cancelamento pendente**. Depois que um revisor lançar ou rejeitar uma reversão de cheque ou um cancelamento de pagamento de guia de depósito, o status não é mais **Cancelamento pendente** e você pode reconciliar a conta.

1. Acesse **Gerenciamento de caixa e bancos** \> **Contas bancárias** \> **Contas bancárias**. Selecione a conta bancária para reconciliar com o extrato bancário e selecione **Reconciliar** > **Reconciliação de conta**.

2. Insira informações nos campos **Data do extrato bancário** e **Extrato bancário**. No campo **Saldo final**, você pode inserir o saldo da conta bancária como ele aparece no extrato.

3. Selecione **Transações** para abrir a página **Reconciliação de conta**.

4. Para cada transação incluída no extrato bancário, marque a caixa de seleção **Compensado** se o valor no Dynamics 365 Finance corresponder ao valor no extrato bancário. Você também pode inserir ou modificar o valor no campo **Tipo de transação bancária**. Esse valor do campo é importante para as estatísticas de transações bancárias e para alguns relatórios.
    

>[!NOTE]
>Não marque a caixa de seleção **Compensado** para transações que não estejam no extrato bancário. Essas transações continuarão sendo exibidas nesta página até que sejam reconciliadas com o extrato bancário futuro.
>A caixa de seleção **Compensado** não estará disponível se o status da transação for **Cancelamento pendente**. As transações podem ter esse status se o Finance estiver configurado para exigir que estornos ou cancelamentos sejam enviados para revisão antes de serem lançados. Depois que um revisor lançar ou rejeitar a reversão ou o cancelamento, o status deixa de ser **Cancelamento pendente** e você pode reconciliar a conta bancária com o extrato bancário.


Para marcar a caixa de seleção **Compensado** para um intervalo de cheques que também são exibidos no extrato bancário, selecione **Marcar intervalo de cheques** e indique o intervalo.

5.  Se o valor de uma transação de conta bancária não corresponder ao valor da transação no extrato bancário, insira o valor da correção no campo **Valor da correção**.
    

> [!NOTE]
> Se o período fiscal da transação a ser corrigida estiver fechado, o campo **Valor da correção** não poderá ser usado. Em vez de isso, crie uma linha com uma data de transação que está em um período fiscal em aberto para a correção. Nesse caso, você deve adicionar as dimensões financeiras que foram usadas na transação original, além da conta principal de contrapartida.



6.  Crie transações para entradas, como taxas e juros que estão no extrato bancário, mas não estão registradas no Finance. Insira o **Tipo de transação bancária** e as dimensões financeiras apropriadas.

7.  À medida que as transações no extrato bancário são marcadas como **Compensado**, o valor no campo **Não reconciliado**, que é recalculado continuamente conforme você faz alterações, se aproxima de zero. Quando ele atingir zero, selecione **Reconciliar conta** para lançar a reconciliação, e as transações e as correções criadas.
    
    Depois de lançada a reconciliação, as transações incluídas não poderão mais ser alteradas ou corrigidas, e não são exibidas para reconciliação de conta no futuro.

8.  Para exibir as transações bancárias que ainda não foram reconciliadas, use o relatório **Transações bancárias não reconciliadas**. Para exibir o extrato bancário de uma conta, use o relatório **Extrato bancário**.

## <a name="cancel-bank-statement-reconciliation"></a>Cancelar reconciliação de extrato bancário 

A funcionalidade Cancelar reconciliação de extrato bancário permite cancelar a reconciliação de extrato bancário. Para usar esse recurso, habilite **Cancelar reconciliação de extrato bancário** no espaço de trabalho **Gerenciamento de recursos**. Também será necessário habilitar o parâmetro **Permitir edição de extrato bancário**. Para fazer isso, Acesse **Gerenciamento de dinheiro e banco > Configuração > Parâmetros do gerenciamento de dinheiro e banco**.
 
As reconciliações de extrato bancário só podem ser canceladas na ordem cronológica em que foram inseridas. Quando a reconciliação de extrato bancário for cancelada, as novas transações e correções serão revertidas e todas as outras transações serão marcadas como não reconciliadas.
 
Para cancelar a reconciliação de extrato bancário, selecione o extrato bancário e selecione **Extrato bancário > Cancelar reconciliação bancária**. Na página **Cancelar reconciliação bancária**, forneça **Código de motivo**, **Comentário do motivo** e **Data de cancelamento**. Selecione **OK** para iniciar o cancelamento. Observe, a data de cancelamento do extrato bancário deve ser na data do extrato bancário ou posterior a ela. Após o cancelamento da reconciliação de extrato bancário, o campo **Data de cancelamento** para o extrato bancário será atualizado com a **Data de cancelamento** fornecida. Selecione o botão **Transações** para exibir as transações para as quais a reconciliação foi cancelada.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
