---
title: Criar e exportar pagamentos de fornecedores usando o formato de pagamento ISO20022
description: Este procedimento mostra como criar linhas de pagamento no diário de pagamentos do fornecedor e gerar um arquivo de pagamento de fornecedor usando o exemplo de Transferência de Crédito ISO2022.
author: mrolecki
manager: AnnBe
ms.date: 01/17/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransVendPaym, SysQueryForm, VendPaymProposalEdit, BankAccountTableLookUp
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1df738e3925dc23e7723d93f33acf6a9d811b113
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4964532"
---
# <a name="create-and-export-vendor-payments-using-iso20022-payment-format"></a>Criar e exportar pagamentos de fornecedores usando o formato de pagamento ISO20022

[!include [banner](../../includes/banner.md)]

Este tópico explica como criar linhas de pagamento no diário de pagamentos do fornecedor e gerar um arquivo de pagamentos do fornecedor usando o exemplo de transferência de crédito ISO2022.

Este é o quinto dos cinco procedimentos que ilustram o processo de pagamento de fornecedores usando as configurações de relatório eletrônico. Use os dados de demonstração DEMF para completar este exemplo.

## <a name="example"></a>Exemplo

1.    Vá para **Contas a pagar > Pagamentos > Diário de pagamentos**.
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