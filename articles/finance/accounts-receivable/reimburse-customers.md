---
title: Reembolsar clientes
description: Este artigo explica como criar transações de reembolso para um grupo de clientes.
author: JodiChristiansen
ms.date: 09/09/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTransCustPaym, LedgerJournalTransVendPaym
audience: Application User
ms.reviewer: twheeloc
ms.custom: 14191
ms.assetid: 53533ee3-470e-458a-ac8b-3815aa4cb502
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 892b089edb16ba560f588c086d37faafdf16958d
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8891772"
---
# <a name="reimburse-customers"></a>Reembolsar clientes

[!include [banner](../includes/banner.md)]

Este artigo explica como criar transações de reembolso para um grupo de clientes. Se um cliente tiver um saldo de crédito, é possível reembolsar o cliente para o valor do saldo. 

A tabela a seguir mostra os pré-requisitos que devem estar funcionando antes de começar.

| Pré-requisito                                                            | Descrição |
|-------------------------------------------------------------------------|-------------|
| Especificar o valor mínimo de reembolso para a entidade legal.          | Na página **Parâmetros de contas a receber**, na área **Geral** no campo **Reembolso mínimo**, insira o valor mínimo que pode ser reembolsado para pagamentos do cliente. |
| Opcional: Adicionar uma conta de fornecedor para cada cliente que pode ser reembolsado. | Na página **Clientes**, na Guia Rápida **Detalhes diversos**, no campo **Conta do fornecedor**, selecione a conta do fornecedor para o cliente. |

Ao criar transações de reembolso, uma fatura de fornecedor é criada para o valor do saldo de crédito. O processo de reembolso remove o saldo de crédito para a conta de cliente e cria um saldo devedor para a conta do fornecedor que corresponde ao cliente.

1. Em Contas a receber, execute o processo de **Reembolso** (**Contas a receber \> Tarefas periódicas \> Reembolso**).
2. Para agrupar todas as transações, independentemente das dimensões do razão, defina a opção **Resumir cliente** como **Sim**. Para agrupar somente transações que tenham dimensões contábeis semelhantes, defina a opção como **Não**.
3. Selecione **Incluir clientes com transações de débito pendentes** para selecionar clientes que tenham valores de débito não liquidados.
4. Para reembolsar contas de cliente específicas, na Guia Rápida **Registros a incluir**, selecione **Filtrar** e especifique as contas de cliente na consulta.

    Os valores de crédito são transferidos para as contas de fornecedor dos clientes e processados como pagamentos normais. Se um cliente não tiver uma conta de fornecedor, uma conta de fornecedor ocasional será criada automaticamente para o cliente.

5. Para exibir as transações de reembolso criadas, use o relatório **Reembolso** (**Contas a Receber \> Consultas e relatórios \> relatório Reembolso**).
6. Em Contas a pagar, crie um pagamento para as faturas de fornecedor que foram criadas pelo processo de reembolso. Para obter informações sobre como pagar fornecedores, consulte [Visão geral de pagamentos do fornecedor](../accounts-payable/Vendor-payments-workspace.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
