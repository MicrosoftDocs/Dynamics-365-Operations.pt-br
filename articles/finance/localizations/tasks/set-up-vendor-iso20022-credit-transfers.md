---
title: Configurar fornecedores e contas bancárias de fornecedor para transferências de crédito de ISO20022
description: Este procedimento demonstra como configurar o fornecedor e as informações da conta bancária específica do fornecedor necessárias para a Transferência de Crédito ISO20022 ou para a geração do arquivo de pagamento de qualquer fornecedor.
author: mrolecki
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: VendTable, VendBankAccounts
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f7a901591f9f3d1a892c29f92e59dc96c1f172143cae6bec571da33b4a50d274
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6723710"
---
# <a name="set-up-vendors-and-vendor-bank-accounts-for-iso20022-credit-transfers"></a>Configurar fornecedores e contas bancárias de fornecedor para transferências de crédito de ISO20022

[!include [banner](../../includes/banner.md)]

Este procedimento demonstra como configurar o fornecedor e as informações da conta bancária específica do fornecedor necessárias para a Transferência de Crédito ISO20022 ou para a geração do arquivo de pagamento de qualquer fornecedor. 

A empresa de dados demonstrativos utilizada para criar esse procedimento é a DEMF.
Este é o quarto dos cinco procedimentos que ilustram o processo de pagamento de fornecedores usando as configurações de relatório eletrônico. Este procedimento é para um recurso que foi adicionado na versão 1611 do Dynamics 365 for Operations.


## <a name="set-up-bank-details"></a>Configurar detalhes do banco
1. Acesse Contas a pagar > Fornecedores > Todos os fornecedores.
2. Use o Filtro Rápido para localizar registros. Por exemplo, no campo Conta de fornecedor, filtre com um valor de 'DE-001'.
3. Clique em DE-001 para abrir detalhes de fornecedor.
4. No Painel de Ação, clique em Fornecedor.
5. Clique em Contas bancárias.
6. Clique em Editar.
    * Se não houver nenhuma conta bancária disponível, você precisa criar uma nova.  
7. No campo Código SWIFT, digite 'COBADEFFXXX'.
8. No campo IBAN, digite ''DE36200400000628808808'.
9. Feche a página.

## <a name="set-up-a-method-of-payment-for-the-vendor"></a>Configurar um método de pagamento para o fornecedor
1. Clique em Editar.
2. Expandir ou recolher a seção Pagamento.
3. No campo Método de pagamento, clique no botão suspenso para abrir a pesquisa.
4. Na lista, clique no link na linha SEPA CT.
5. Clique em Salvar.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]