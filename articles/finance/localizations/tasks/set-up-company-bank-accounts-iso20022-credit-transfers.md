---
title: Configurar contas bancárias de empresa para transferências de crédito de ISO20022
description: Este procedimento mostra como configurar as informações da conta bancária específica da empresa que são necessárias para a geração do arquivo de pagamento.
author: mrolecki
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankAccountTable, OMLegalEntity, BankAccountTableLookUp
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2bbbf55ed28ad2131d7e1253dd44842d85d39315
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2174760"
---
# <a name="set-up-company-bank-accounts-for-iso20022-credit-transfers"></a>Configurar contas bancárias de empresa para transferências de crédito de ISO20022

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este procedimento mostra como configurar as informações da conta bancária específica da empresa que são necessárias para a geração do arquivo de pagamento. Você configura as informações necessárias para gerar o formato de transferência de crédito ISO 20022 mas, dependendo do formato, outras informações podem ser necessárias, como a ID da empresa ou o código de classificação. 

A empresa de dados demonstrativos utilizada para criar esse procedimento é a DEMF.

Este é o segundo dos cinco procedimentos que ilustram o processo de pagamento de fornecedores usando as configurações de relatório eletrônico. Este procedimento é para um recurso que foi adicionado na versão 1611 do Dynamics 365 for Operations.


## <a name="set-up-iban-and-swift-code"></a>Configurar IBAN e código SWIFT
1. Vá para Gerenciamento de caixa e bancos > Contas bancárias.
2. Use o Filtro Rápido para filtrar o campo Conta bancária com o valor 'DEMF OPER'.
3. Clique em DEMF OPER para abrir os detalhes da conta bancária.
4. Clique em Editar.
5. Expanda a seção Identificação adicional.
6. No campo IBAN, digite ''DE89370400440532013000'.
7. No campo Código SWIFT, digite 'DEUTDEFF'.
    * Observe que o SWIFT\BIC não é necessário para vários formatos de pagamento, no entanto, é recomendável registrá-lo em uma conta bancária.  
8. Clique em Salvar.

## <a name="set-up-bank-account-for-the-legal-entity"></a>Configurar conta bancária da entidade legal
1. Vá para Administração da organização > Organizações > Entidades legais.
2. Clique em Editar.
3. Expanda a seção Informações de conta bancária.
4. No campo Conta bancária, insira ou selecione um valor.
5. Clique em Salvar.

