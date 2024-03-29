---
title: Configurar contas bancárias de empresa para débitos diretos de ISO20022
description: Esta tarefa orienta como configurar com as informações de conta bancária específicas da empresa que são necessárias para gerar arquivos de pagamento de cliente.
author: mrolecki
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: BankAccountTable, OMLegalEntity, BankAccountTableLookUp
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a0f8ac369bb6b9a7a0f21c23aaddab2601ae3f8f37e2427cbb10b5509a7a2f23
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6768708"
---
# <a name="set-up-company-bank-accounts-for-iso20022-direct-debits"></a>Configurar contas bancárias de empresa para débitos diretos de ISO20022

[!include [banner](../../includes/banner.md)]

Esta tarefa orienta como configurar com as informações de conta bancária específicas da empresa que são necessárias para gerar arquivos de pagamento de cliente. Este procedimento usa o formato de débito direto ISO 20022 como exemplo. Outros formatos podem exigir informações de configuração adicionais, como a ID da empresa ou o código de classificação.



Essa tarefa foi criada usando a empresa de dados demonstrativos DEMF.



Este é o segundo dos cinco procedimentos que demonstram o processo de pagamento de clientes usando as configurações de relatório eletrônico.


## <a name="set-up-the-iban-and-swift-codes"></a>Configurar códigos IBAN e SWIFT
1. Acesse Gerenciamento de caixa e bancos > Contas bancárias.
2. Use o Filtro Rápido para filtrar o campo Conta bancária com o valor 'DEMF OPER'.
3. Na lista, clique no link na linha selecionada.
    * Por exemplo, clique em 'DEMF OPER' para abrir os detalhes da conta bancária.  
4. Clique em Editar.
5. Expanda ou recolha a seção Identificação adicional.
6. No campo IBAN, digite um valor.
    * Por exemplo, insira "DE89370400440532013000".  
7. No campo Código SWIFT, digite um valor.
    * Por exemplo, insira "DEUTDEFF".    Observe que o SWIFT\BIC não é obrigatório para vários formatos de pagamento, no entanto, é recomendável registrá-lo em uma conta bancária.  
8. Clique em Salvar.

## <a name="set-up-a-bank-account-for-the-legal-entity"></a>Configurar conta bancária da entidade legal
1. Acesse Administração da organização > Organizações > Entidades legais.
2. Clique em Editar.
3. Expandir ou recolher a seção Informações de conta bancária.
4. No campo Conta bancária, clique no botão suspenso para abrir a pesquisa.
5. Na lista, clique no link na linha selecionada.
    * Por exemplo, selecione a conta bancária "DEMF OPER".  
6. Clique em Salvar.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]