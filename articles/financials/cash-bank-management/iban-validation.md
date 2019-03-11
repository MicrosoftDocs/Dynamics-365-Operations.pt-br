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
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mikefalkner
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: 19e0528b95952de8e5503c361efcfeca4c529caf
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "359994"
---
# <a name="manage-international-bank-account-number-iban-validation"></a>Gerenciar a validação do IBAN (número de conta bancária internacional)

[!include [banner](../includes/banner.md)]

A validação do IBAN aumenta o valor de validação realizada quando você adiciona um IBAN a uma conta bancária.

As informações sobre a estrutura do IBAN são armazenadas no Microsoft Dynamics 365 for Finance and Operations. Essas informações são carregadas automaticamente quando você usa o IBAN pela primeira vez em contas bancárias. Elas contêm o tamanho do IBAN, as posições iniciais do número de conta bancária e o número de roteamento, além do tamanho do número de conta bancária e do número de roteamento.

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
