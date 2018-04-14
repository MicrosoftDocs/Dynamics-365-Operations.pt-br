--- 
title: Configurar um formato da guia de pagamento para faturas de projeto
description: "Geralmente, as empresas anexam guias de pagamento impressas a faturas para ajudar os clientes e fornecer uma referência de pagamento para lançamento e liquidação."
author: EvgenyPopovMBS
manager: AnnBe
ms.date: 02/16/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: epopov
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 9700571110a1b488e250dd8ee7b8c5c8f15cbc01
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---
# <a name="set-up-payment-slip-format-for-project-invoices"></a>Configurar um formato da guia de pagamento para faturas de projeto

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

Geralmente, as empresas anexam guias de pagamento impressas a faturas para ajudar os clientes e fornecer uma referência de pagamento para lançamento e liquidação. A guia de pagamento pode ser usada para faturas de projeto ou serviço, cartas de cobrança, notas de juros e demonstrativos de conta, além das faturas de venda e faturas de texto livre. Para processar guias de pagamento, primeiro configure os formatos de número de identificação do credor e de anexo de guia de pagamento.

Este procedimento usa a empresa de dados de demonstração DEMF. 

Esta funcionalidade está disponível para entidades legais cujo endereço principal seja na Dinamarca.


## <a name="set-up-a-creditor-id-number"></a>Configurar um número de identificação do credor
1. Vá para Administração da organização > Organizações > Entidades legais.
2. Expandir ou recolher a seção Informações de conta bancária.
3. Clique em Editar.
4. No campo ID do FI-Credor, digite um valor.
5. Clique em Salvar.
6. Feche a página.

## <a name="set-up-a-payment-slip-format-for-invoices-notes-letters-and-statements"></a>Configurar um formato da guia de pagamento para faturas, notas, letras e demonstrativos
1. Vá para Contas a receber > Configuração > Formulários > Configuração de formulário.
2. Clique na guia Fatura.
3. No campo Anexo do pagamento associado na fatura de cliente, selecione uma opção.
    * Nenhum – Não imprime uma guia de pagamento. Escolha esta opção se o valor do pagamento estiver em uma moeda diferente da coroa dinamarquesa (DKK).   FIK 751 – Imprima uma guia de pagamento FIK 751, se você pretende gravar manualmente o valor de pagamento e a data de vencimento na guia de pagamento.   FIK 752 – imprime uma guia de pagamento FIK 752, se você pretende usar uma guia de pagamento gerada pelo computador com um valor de pagamento e uma data de vencimento pré-impressos.  
4. Clique em Salvar.
5. Clique na guia Fatura de texto livre.
6. No campo Anexo de pagamento associado na fatura de texto livre, selecione uma opção.
    * Nenhum – Não imprime uma guia de pagamento. Escolha esta opção se o valor do pagamento estiver em uma moeda diferente da coroa dinamarquesa (DKK).   FIK 751 – Imprime uma guia de pagamento FIK 751, se você pretende gravar o valor de pagamento e a data de vencimento na guia de pagamento manualmente.   FIK 752 – imprime uma guia de pagamento FIK 752, se você pretende usar uma guia de pagamento gerada pelo computador com um valor de pagamento e uma data de vencimento pré-impressos.  
7. Clique em Salvar.
8. Clique na guia Nota de juros.
9. No campo Anexo do pagamento associado na nota de juros, selecione uma opção.
    * Nenhum – Não imprime uma guia de pagamento. Escolha esta opção se o valor do pagamento estiver em uma moeda diferente da coroa dinamarquesa (DKK).   FIK 751 – Imprime uma guia de pagamento FIK 751, se você pretende gravar o valor de pagamento e a data de vencimento na guia de pagamento manualmente.   FIK 752 – imprime uma guia de pagamento FIK 752, se você pretende usar uma guia de pagamento gerada pelo computador com um valor de pagamento e uma data de vencimento pré-impressos.  
10. Clique em Salvar.
11. Clique na guia Carta de cobrança.
12. No campo Anexo de pagamento associado na carta de cobrança, selecione uma opção.
    * Nenhum – Não imprime uma guia de pagamento. Escolha esta opção se o valor do pagamento estiver em uma moeda diferente da coroa dinamarquesa (DKK).   FIK 751 – Imprime uma guia de pagamento FIK 751, se você pretende gravar o valor de pagamento e a data de vencimento na guia de pagamento manualmente.   FIK 752 – imprime uma guia de pagamento FIK 752, se você pretende usar uma guia de pagamento gerada pelo computador com um valor de pagamento e uma data de vencimento pré-impressos.  
13. Clique em Salvar.
14. Clique na guia Demonstrativo da conta.
15. No campo Anexo de pagamento associado no demonstrativo da conta, selecione uma opção.
    * Nenhum – Não imprime uma guia de pagamento. Escolha esta opção se o valor do pagamento estiver em uma moeda diferente da coroa dinamarquesa (DKK).   FIK 751 – Imprime uma guia de pagamento FIK 751, se você pretende gravar o valor de pagamento e a data de vencimento na guia de pagamento manualmente.   FIK 752 – imprime uma guia de pagamento FIK 752, se você pretende usar uma guia de pagamento gerada pelo computador com um valor de pagamento e uma data de vencimento pré-impressos.  
16. Clique em Salvar.
17. Feche a página.


