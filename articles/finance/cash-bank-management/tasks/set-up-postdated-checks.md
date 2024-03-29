---
title: Configurar cheques pré-datados
description: Este artigo explica como especificar se deseja lançar entradas de diário para cheques pré-datados e quais diários de lançamento a serem usados para limpar as entradas e os pagamentos de fornecedores.
author: kweekley
ms.date: 11/15/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: BankParameters, VendPaymMode, CustPaymMode
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a5ef9aa6b67eb630713dd1f15b2ae49c358edae9
ms.sourcegitcommit: 81bb8e51951395be3f18f45212e47e6c41656f6a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/23/2022
ms.locfileid: "9804173"
---
# <a name="set-up-postdated-checks"></a>Configurar cheques pré-datados

[!include [banner](../../includes/banner.md)]

Este artigo explica como especificar se deseja lançar entradas de diário para cheques pré-datados e quais diários de lançamento a serem usados para limpar as entradas e os pagamentos de fornecedores. Também é possível especificar as contas de compensação para cheques emitidos, cheques recebidos, e a retenção de imposto. Cheques pré-datados que são emitidos com a finalidade de realizar e receber pagamentos em uma data futura. É possível especificar se o cheque deve ser refletido nos registros de contabilidade antes da data de vencimento.



A função deste procedimento é Tesoureiro. Este procedimento usa a empresa de dados de demonstração USMF.


## <a name="set-up-postdated-checks"></a>Configurar cheques pré-datados
1. Vá para **Gerenciamento de caixa e bancos > Configuração > Parâmetros de gerenciamento de caixa e bancos**.
2. Clique na guia **Cheques pré-datados**.
3. Marque ou desmarque a caixa de seleção **Habilitar cheques pré-datados**.
4. Marque ou desmarque a caixa de seleção **Lançar entradas de diário para cheques pré-datados**.
5. No campo **Conta de compensação para cheques emitidos**, especifique os valores desejados.
6. No campo **Conta de compensação para cheques recebidos**, especifique os valores desejados.
7. No campo **Diário geral para entradas de compensação**, digite um valor.
8. No campo **Transferir cheques pré-datados para este diário de pagamento de fornecedor**, digite um valor.
9. No campo **Conta de compensação de imposto retido na fonte**, especifique os valores desejados.
10. Clique em **Salvar**.
11. Feche a página.
12. Vá para **Contas a pagar > Configuração de pagamento > Formas de pagamento**.
13. Clique em **Novo**.
14. No campo **Método de pagamento**, digite um valor.
15. Selecione a opção de lançamento **Compensação de cheque pré-datado** para indicar que o valor do cheque está lançado em uma conta de compensação.
16. No campo **Tipo de conta**, selecione **Banco**.
    * A conta de contrapartida do método de pagamento será um banco.  
17. No campo **Conta de pagamento**, especifique os valores desejados.
    * Selecione a conta bancária utilizada para deduzir o valor da fatura.  
18. Clique em **Salvar**.
19. Feche a página.
> [!NOTE]
> Para conseguir postar um cheque prédatado para uma conta bancária quando a data da sessão for superior ou igual à data de vencimento, você deve habilitar o recurso **Validação de data de validade do diário de pagamento de postagem com cheques prédatados para a conta bancária**. Este recurso permite que você poste diários de pagamento para fornecedores ou clientes com cheques prédatados, quando a data da sessão for superior ou igual à data de vencimento.
> 
> Ao configurar o **Método de pagamento** (**Contas a pagar > Configuração de pagamento > Métodos de pagamento**), não preencha **Conta de ponte**. Nesse caso, a conta de compensação é preenchida com a conta bancária, que é configurada no **Método de pagamento**.
>  
> Quando o recurso é habilitado e a data da sessão é inferior à data de vencimento, a seguinte mensagem de erro é exibida ao postar um diário de pagamento, **A data de vencimento deve ser inferior ou igual à data da sessão se o tipo de conta de compensação for Banco**. Se o recurso não estiver habilitado, você pode postar um diário de pagamento com um cheque prédatado quando a data da sessão for inferior à data de vencimento.
> Este recurso está disponível na versão 10.0.21 e posterior.    

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
