---
title: "Gerenciar a validação da conta do IBAN (número de conta bancária internacional)"
description: "Este tópico explica como gerenciar a validação da conta do IBAN (número de conta bancária internacional)."
author: mikefalkner
manager: aolson
ms.date: 08/24/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mikefalkner
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.translationtype: HT
ms.sourcegitcommit: 98ed3378ab05c0c69c9e5b2a82310113a81c2264
ms.openlocfilehash: e091aab70a98e0f4b96c41c1ee48926947539105
ms.contentlocale: pt-br
ms.lasthandoff: 08/31/2018

---

# <a name="manage-international-bank-account-number-iban-account-validation"></a>Gerenciar a validação da conta do IBAN (número de conta bancária internacional)

[!include [banner](../includes/banner.md)]

A validação da conta do IBAN aumenta a quantidade de validação realizada quando você adiciona um IBAN a uma conta bancária.

A estrutura do IBAN é armazenada no Microsoft Dynamics 365 for Finance and Operation e é automaticamente carregada quando você usa o IBAN pela primeira vez em contas bancárias. O número de conta bancária faz parte da estrutura definida para um IBAN. Com base nessa estrutura, se a posição e o comprimento do número da conta no IBAN não corresponderem à posição definida na estrutura para cada país ou região, você receberá mensagens de aviso.

## <a name="set-up-iban-structures"></a>Configurar estruturas IBAN

1. Vá para **Gerenciamento de dinheiro e banco \> Configuração \> Estruturas IBAN**.
2. Observe que as estruturas IBAN de cada país ou região foram configuradas automaticamente.
3. Se você precisar personalizar as estruturas de um país ou região específico, poderá editá-las.
4. As definições das estruturas farão parte de cada lançamento. Você pode usar o menu **Redefinir estruturas** para carregar as definições mais recentes após cada atualização.

## <a name="validate-the-iban-structure-in-a-bank-account"></a>Validar a estrutura IBAN em uma conta bancária

1. Vá para **Gerenciamento de caixa e bancos \> Contas bancárias \> Contas bancárias**.
2. Crie uma conta bancária.
3. Na Guia Rápida **Informações adicionais**, insira um IBAN.

    Se a posição e o comprimento do número da conta no IBAN não corresponderem à posição definida na estrutura para cada país ou região, você receberá uma mensagem. Você não poderá continuar se o comprimento do IBAN não corresponder ao comprimento na estrutura IBAN.

    A validação também verifica se o número da conta bancária corresponde à parte do IBAN que representa o número da conta bancária. Se o número da conta bancária não corresponder, você receberá uma mensagem de aviso. Essa mensagem é apenas um aviso. Você poderá continuar mesmo se o número da conta bancária não corresponder.

