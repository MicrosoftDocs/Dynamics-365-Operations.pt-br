---
title: Configurar cheques pré-datados
description: Este tópico explica como especificar se deseja lançar entradas de diário para cheques pré-datados e quais diários de lançamento a serem usados para limpar as entradas e os pagamentos de fornecedores.
author: kweekley
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankParameters, VendPaymMode, CustPaymMode
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e4b18ebe1388998b45e5ef38318b0ade9153f7c8
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1565940"
---
# <a name="set-up-postdated-checks"></a>Configurar cheques pré-datados

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este tópico explica como especificar se deseja lançar entradas de diário para cheques pré-datados e quais diários de lançamento a serem usados para limpar as entradas e os pagamentos de fornecedores. Também é possível especificar as contas de compensação para cheques emitidos, cheques recebidos, e a retenção de imposto. Cheques pré-datados que são emitidos com a finalidade de realizar e receber pagamentos em uma data futura. É possível especificar se o cheque deve ser refletido nos registros de contabilidade antes da data de vencimento.



A função deste procedimento é Tesoureiro. Este procedimento usa a empresa de dados de demonstração USMF.


## <a name="set-up-postdated-checks"></a>Configurar cheques pré-datados
1. Vá para Gerenciamento de dinheiro e banco > Configuração > Parâmetros do gerenciamento de dinheiro e banco.
2. Clique na aba Cheques pré-datados.
3. Marque ou desmarque a caixa de seleção Habilitar cheques pré-datados.
4. Marque ou desmarque a caixa de seleção Lançar entradas de diário para cheques pré-datados.
5. No campo Conta de compensação para cheques emitidos, especifique os valores desejados.
6. No campo Conta de compensação para cheques recebidos, especifique os valores desejados.
7. No campo Diário geral para entradas de compensação, digite um valor.
8. No campo Transferir cheques pré-datados para este diário de pagamento de fornecedor, digite um valor.
9. No campo Conta de compensação de imposto retido na fonte, especifique os valores desejados.
10. Clique em Salvar.
11. Feche a página.
12. Vá para Contas a pagar > Configurar pagamento > Métodos de pagamento.
13. Clique em Novo.
14. No campo Método de pagamento, digite um valor.
15. Selecione a opção de lançamento Compensação de cheque pré-datado para indicar que o valor do cheque está lançado em uma conta de compensação.
16. No campo Tipo de conta, selecione 'Banco'.
    * A conta de contrapartida do método de pagamento será um banco.  
17. No campo Conta de pagamento, especifique os valores desejados.
    * Selecione a conta bancária utilizada para deduzir o valor da fatura.  
18. Feche a página.
19. Vá para Contas a receber > Configurar pagamentos > Métodos de pagamento
20. Clique em Novo.
21. No campo Método de pagamento, digite um valor.
22. Selecione a opção de lançamento Compensação de cheque pré-datado para indicar que o valor do cheque está lançado em uma conta de compensação.
23. No campo Tipo de conta, selecione 'Banco'.
    * A conta de contrapartida do método de pagamento será um banco.  
24. No campo Conta de pagamento, especifique os valores desejados.
    * Selecione a conta bancária utilizada para deduzir o valor da fatura.  
25. Feche a página.

