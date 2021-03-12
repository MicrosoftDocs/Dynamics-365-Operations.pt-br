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
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b677056f11a8733bf90f18110b8ee47f6447503b
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4976276"
---
# <a name="set-up-postdated-checks"></a>Configurar cheques pré-datados

[!include [banner](../../includes/banner.md)]

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
18. Clique em Salvar.
19. Feche a página.

