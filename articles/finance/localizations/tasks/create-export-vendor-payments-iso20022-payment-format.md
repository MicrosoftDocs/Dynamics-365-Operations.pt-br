---
title: Criar e exportar pagamentos de fornecedores usando o formato de pagamento ISO20022
description: Este procedimento mostra como criar linhas de pagamento no diário de pagamentos do fornecedor e gerar um arquivo de pagamento de fornecedor usando o exemplo de Transferência de Crédito ISO2022.
author: mrolecki
ms.date: 01/17/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransVendPaym, SysQueryForm, VendPaymProposalEdit, BankAccountTableLookUp
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ac84055586eff678ea489b35198b1c2dfab13658
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8856457"
---
# <a name="create-and-export-vendor-payments-using-iso20022-payment-format"></a>Criar e exportar pagamentos de fornecedores usando o formato de pagamento ISO20022

[!include [banner](../../includes/banner.md)]

Este artigo explica como criar linhas de pagamento no diário de pagamentos do fornecedor e gerar um arquivo de pagamentos do fornecedor usando o exemplo de transferência de crédito ISO2022.

Este é o quinto dos cinco procedimentos que ilustram o processo de pagamento de fornecedores usando as configurações de relatório eletrônico. Use os dados de demonstração DEMF para completar este exemplo.

## <a name="example"></a>Exemplo

1.    Acesse **Contas a pagar > Pagamentos > Diário de pagamentos**.
2.    Clique em **Novo**.
3.    No campo **Nome**, insira ou selecione um valor.
4.    Clique em **Linhas > Proposta de pagamento > Criar proposta de pagamento**.
5.    Expanda a seção **Registros a serem incluídos**.
6.    Clique em **Filtrar**.
7.    Na lista, selecione a linha para a **tabela Fornecedores** e o **campo Conta de fornecedor**.
8.    No campo **Critérios**, insira ou selecione um valor. Você pode aplicar quaisquer critérios para selecionar transações de fornecedor para pagamento. Neste exemplo, use DE-001 como conta de fornecedor.
12.    Clique em **OK**.
13.    Clique em **OK**.
14.    Clique em **Criar pagamentos**.
15. Gere um arquivo de pagamento ISO20022.
    1.    Clique em **Gerar pagamentos**.
    2.    No campo **Método de pagamento**, insira ou selecione um valor.
    3.    No campo **Nome do arquivo**, digite um valor. Por exemplo, devido a um pagamento em euros, o arquivo gerado será compatível com SEPA. A transferência de crédito ISO20022 e outros formatos de pagamento de fornecedor também podem ser usados para gerar pagamentos em outras moedas.
    4.    No campo **Conta bancária**, insira ou selecione um valor.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]