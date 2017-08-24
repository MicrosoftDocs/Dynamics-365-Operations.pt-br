---
title: Reembolsar clientes
description: "Este artigo explica como criar transações de reembolso para um grupo de clientes. Se um cliente tiver um saldo de crédito, é possível reembolsar o cliente para o valor do saldo."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerJournalTransCustPaym, LedgerJournalTransVendPaym
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 14191
ms.assetid: 53533ee3-470e-458a-ac8b-3815aa4cb502
ms.search.region: Global
ms.author: Shiva.Pandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: c3201166eb7054205647a54ed80f98968fcfda6e
ms.contentlocale: pt-br
ms.lasthandoff: 05/25/2017

---

# <a name="reimburse-customers"></a>Reembolsar clientes

[!include[banner](../includes/banner.md)]


Este artigo explica como criar transações de reembolso para um grupo de clientes. Se um cliente tiver um saldo de crédito, é possível reembolsar o cliente para o valor do saldo. 

A tabela a seguir mostra os pré-requisitos que devem estar funcionando antes de começar.

| Pré-requisito                                                            | Descrição                                                                                                                                                                                 |
|-------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Especificar o valor mínimo de reembolso para a entidade legal.          | Na página **Parâmetros de contas a receber**, na área **Geral** no campo **Reembolso mínimo**, insira o valor mínimo que pode ser reembolsado para pagamentos do cliente. |
| Opcional: Adicionar uma conta de fornecedor para cada cliente que pode ser reembolsado. | Na página **Clientes**, na Guia Rápida **Detalhes diversos**, no campo **Conta do fornecedor**, selecione a conta do fornecedor para o cliente.                                           |

Ao criar transações de reembolso, uma fatura de fornecedor é criada para o valor do saldo de crédito. O processo de reembolso remove o saldo de crédito para a conta de cliente e cria um saldo devedor para a conta do fornecedor que corresponde ao cliente.

1.  Em Contas a receber, execute o processo **Reembolso**.
2.  Siga uma destas etapas:
    -   Para reembolsar contas específicas de clientes, clique em **Selecionar** e especifique as contas do cliente na consulta.
    -   Para reembolsar todas as contas de clientes, clique em **OK**.

    Os valores de crédito são transferidos para as contas de fornecedor dos clientes e processados como pagamentos normais. Se um cliente não tiver uma conta de fornecedor, uma conta de fornecedor ocasional será criada automaticamente para o cliente.
3.  Para visualizar as transações do reembolso que foram criados, use a página **Reembolso**.
4.  Em Contas a pagar, crie um pagamento para as faturas de fornecedor que foram criadas pelo processo de reembolso.





