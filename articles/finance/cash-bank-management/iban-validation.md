---
title: Gerenciar a validação da conta do IBAN (número de conta bancária internacional)
description: Este tópico explica como gerenciar a validação da conta do IBAN (número de conta bancária internacional).
author: mikefalkner
ms.date: 08/24/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: f7f6bcb9085630966310efb5af2e7def23d919d6653376b8f6637a6da915a8d5
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6757136"
---
# <a name="manage-international-bank-account-number-iban-account-validation"></a>Gerenciar a validação da conta do IBAN (número de conta bancária internacional)

[!include [banner](../includes/banner.md)]

A validação do IBAN aumenta o valor de validação realizada quando você adiciona um IBAN a uma conta bancária.

As informações sobre a estrutura do IBAN são armazenadas no Microsoft Dynamics 365 Finance. Essas informações são carregadas automaticamente quando você usa o IBAN pela primeira vez em contas bancárias. Elas contêm o tamanho do IBAN, as posições iniciais do número de conta bancária e o número de roteamento, além do tamanho do número de conta bancária e do número de roteamento.

## <a name="set-up-iban-structures"></a>Configurar estruturas IBAN

1. Acesse **Gerenciamento de dinheiro e banco \> Configuração \> Estruturas IBAN**.
2. Observe que as estruturas IBAN de cada país ou região foram configuradas automaticamente.
3. Se desejar personalizar as estruturas de um país ou região específica, você poderá editá-las.
4. As definições das estruturas farão parte de cada lançamento. Você pode usar o menu **Redefinir estruturas** para carregar as definições mais recentes após cada atualização.

## <a name="validate-the-iban-structure-in-a-bank-account"></a>Validar a estrutura IBAN em uma conta bancária

1. Acesse **Gerenciamento de caixa e bancos \> Contas bancárias \> Contas bancárias**.
2. Crie uma conta bancária.
3. Na Guia Rápida **Informações adicionais**, insira um IBAN.

    Se o tamanho do IBAN não corresponder ao tamanho definido para cada país ou região, você receberá uma mensagem de aviso. Você não poderá continuar se o tamanho do IBAN não corresponder ao tamanho especificado na estrutura do IBAN.

    A validação também verifica se o número da conta bancária corresponde à parte do IBAN que representa o número da conta bancária. Se o número da conta bancária não coincidir, você receberá uma mensagem de aviso. Essa mensagem é apenas um aviso. Você poderá continuar mesmo se o número da conta bancária não corresponder.

    A validação também verifica se o número de roteamento do banco corresponde à parte do IBAN que representa o número de roteamento do banco. O número de roteamento inclui um número de banco e, em geral, uma agência bancária adicional. Se o número de roteamento do banco não coincidir, você receberá uma mensagem de aviso. Essa mensagem é apenas um aviso. Você poderá continuar mesmo se o número da roteamento do banco não coincidir.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]