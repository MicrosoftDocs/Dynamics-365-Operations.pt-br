---
title: Gerenciar a validação da conta do IBAN (número de conta bancária internacional)
description: Este tópico explica como gerenciar a validação da conta do IBAN (número de conta bancária internacional).
author: mikefalkner
manager: aolson
ms.date: 08/24/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: 28abef376e8462c9a69dbd8e5033ea799b6a4b3a
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4440367"
---
# <a name="manage-international-bank-account-number-iban-account-validation"></a>Gerenciar a validação da conta do IBAN (número de conta bancária internacional)

[!include [banner](../includes/banner.md)]

A validação do IBAN aumenta o valor de validação realizada quando você adiciona um IBAN a uma conta bancária.

As informações sobre a estrutura do IBAN são armazenadas no Microsoft Dynamics 365 Finance. Essas informações são carregadas automaticamente quando você usa o IBAN pela primeira vez em contas bancárias. Elas contêm o tamanho do IBAN, as posições iniciais do número de conta bancária e o número de roteamento, além do tamanho do número de conta bancária e do número de roteamento.

## <a name="set-up-iban-structures"></a>Configurar estruturas IBAN

1. Vá para **Gerenciamento de dinheiro e banco \> Configuração \> Estruturas IBAN**.
2. Observe que as estruturas IBAN de cada país ou região foram configuradas automaticamente.
3. Se desejar personalizar as estruturas de um país ou região específica, você poderá editá-las.
4. As definições das estruturas farão parte de cada lançamento. Você pode usar o menu **Redefinir estruturas** para carregar as definições mais recentes após cada atualização.

## <a name="validate-the-iban-structure-in-a-bank-account"></a>Validar a estrutura IBAN em uma conta bancária

1. Vá para **Gerenciamento de caixa e bancos \> Contas bancárias \> Contas bancárias**.
2. Crie uma conta bancária.
3. Na Guia Rápida **Informações adicionais**, insira um IBAN.

    Se o tamanho do IBAN não corresponder ao tamanho definido para cada país ou região, você receberá uma mensagem de aviso. Você não poderá continuar se o tamanho do IBAN não corresponder ao tamanho especificado na estrutura do IBAN.

    A validação também verifica se o número da conta bancária corresponde à parte do IBAN que representa o número da conta bancária. Se o número da conta bancária não coincidir, você receberá uma mensagem de aviso. Essa mensagem é apenas um aviso. Você poderá continuar mesmo se o número da conta bancária não corresponder.

    A validação também verifica se o número de roteamento do banco corresponde à parte do IBAN que representa o número de roteamento do banco. O número de roteamento inclui um número de banco e, em geral, uma agência bancária adicional. Se o número de roteamento do banco não coincidir, você receberá uma mensagem de aviso. Essa mensagem é apenas um aviso. Você poderá continuar mesmo se o número da roteamento do banco não coincidir.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]