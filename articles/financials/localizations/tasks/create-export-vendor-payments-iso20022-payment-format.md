--- 
title: Criar e exportar pagamentos de fornecedores usando o formato de pagamento ISO20022
description: "Este procedimento mostra como criar linhas de pagamento no diário de pagamentos do fornecedor e gerar um arquivo de pagamento de fornecedor usando o exemplo de Transferência de Crédito ISO2022."
author: mrolecki
manager: AnnBe
ms.date: 10/24/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 16c2af862a73047a2e6ebdc056275392fa8a0d93
ms.contentlocale: pt-br
ms.lasthandoff: 07/27/2017

---
# <a name="create-and-export-vendor-payments-using-iso20022-payment-format"></a>Criar e exportar pagamentos de fornecedores usando o formato de pagamento ISO20022

[!include[task guide banner](../../includes/task-guide-banner.md)]

Este procedimento mostra como criar linhas de pagamento no diário de pagamentos do fornecedor e gerar um arquivo de pagamento de fornecedor usando o exemplo de Transferência de Crédito ISO2022. 

A empresa de dados demonstrativos utilizada para criar esse procedimento é a DEMF.

Este é o quinto dos cinco procedimentos que ilustram o processo de pagamento de fornecedores usando as configurações de relatório eletrônico. Este procedimento é para um recurso que foi adicionado à versão 1611 do Dynamics 365 for Operations.


## <a name="create-payment-lines"></a>Criar linhas de pagamento
1. Vá para Contas a pagar > Pagamentos > Diário de pagamentos.
2. Clique em Novo.
3. Na lista, marque a linha selecionada.
4. No campo Nome, insira ou selecione um valor.
5. Clique em Linhas.
6. Clique em Proposta de pagamento.
7. Clique em Criar proposta de pagamento.
8. Expanda os Registros para incluir a seção.
9. Clique em Filtro.
10. Na lista, selecione a linha para Tabela de fornecedores e o campo Conta de fornecedor.
11. No campo Critérios, insira ou selecione um valor.
    * Você pode aplicar quaisquer critérios para selecionar transações de fornecedor para pagamento. Para este exemplo, use DE-001 como uma conta de fornecedor.  
12. Clique em OK.
13. Clique em OK.
14. Clique em Criar pagamentos.

## <a name="generate-an-iso20022-payment-file"></a>Gerar um arquivo de pagamento ISO20022

