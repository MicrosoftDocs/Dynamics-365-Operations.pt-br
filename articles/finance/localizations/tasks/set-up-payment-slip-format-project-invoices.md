---
title: Configurar um formato da guia de pagamento para faturas de projeto
description: Geralmente, as empresas anexam guias de pagamento impressas a faturas para ajudar os clientes e fornecer uma referência de pagamento para lançamento e liquidação.
author: EvgenyPopovMBS
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: OMLegalEntity, CustFormletterParameters
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: epopov
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: cb0d1d95013b3eac3131064992920da5fa9bea5a1f6d554e6be1d5006a9b21fb
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6732891"
---
# <a name="set-up-payment-slip-format-for-project-invoices"></a>Configurar um formato da guia de pagamento para faturas de projeto

[!include [banner](../../includes/banner.md)]

Geralmente, as empresas anexam guias de pagamento impressas a faturas para ajudar os clientes e fornecer uma referência de pagamento para lançamento e liquidação. A guia de pagamento pode ser usada para faturas de projeto ou serviço, cartas de cobrança, notas de juros e demonstrativos de conta, além das faturas de venda e faturas de texto livre. Para processar guias de pagamento, primeiro configure os formatos de número de identificação do credor e de anexo de guia de pagamento.

Este procedimento usa a empresa de dados de demonstração DEMF. 

Esta funcionalidade está disponível para entidades legais cujo endereço principal seja na Dinamarca.


## <a name="set-up-a-creditor-id-number"></a>Configurar um número de identificação do credor
1. Acesse Administração da organização > Organizações > Entidades legais.
2. Expandir ou recolher a seção Informações de conta bancária.
3. Clique em Editar.
4. No campo ID do FI-Credor, digite um valor.
5. Clique em Salvar.
6. Feche a página.

## <a name="set-up-a-payment-slip-format-for-invoices-notes-letters-and-statements"></a>Configurar um formato da guia de pagamento para faturas, notas, letras e demonstrativos
1. Acesse Contas a receber > Configuração > Formulários > Configuração de formulário.
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



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]