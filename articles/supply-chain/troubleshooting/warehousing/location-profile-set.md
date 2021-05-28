---
title: O perfil de local desabilita inventário negativo, mas o inventário em mãos negativo é permitido
description: A opção Permitir inventário negativo para o perfil de local é definida como Não, mas o sistema ainda permite inventário em mãos negativo.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: WHSLocationProfile
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: shawan
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 356d2dd7853bf93250e14eb9bd28a8a145794584
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026267"
---
# <a name="location-profile-disallows-negative-inventory-but-negative-on-hand-inventory-is-permitted"></a>O perfil de local desabilita inventário negativo, mas o inventário em mãos negativo é permitido

Número da base de dados de conhecimento: 4613622

## <a name="symptoms"></a>Sintomas

A opção **Permitir inventário negativo** para o perfil de local é definida como *Não*, mas o sistema ainda permite inventário em mãos negativo.

## <a name="example-scenario"></a>Cenário de exemplo

Para transações regulamentadas pelo governo, o sistema deve ser capaz de registrar inventário negativo para registrar perdas. Você quer que um item seja capaz de mostrar inventário negativo, mas somente em locais designados, como tanques. No entanto, se o grupo de modelo do item permitir inventário negativo, você verá que não importa se o local está definido para permitir inventário negativo. Se o item estiver configurado para não permitir inventário negativo, não importa como o perfil de local está configurado.

## <a name="resolution"></a>Resolução

A configuração **Permitir inventário negativo** no perfil de local aplica-se somente a processos de armazém, como retirada. No entanto, os grupos de modelo de item que são definidos para permitir inventário negativo afetam todos os processos dos módulos Gerenciamento de inventário e Gerenciamento de armazém, e o perfil de local não substituirá essa configuração.

Você pode controlar se um armazém tem permissão para realizar inventário negativo. Defina seus grupos de modelo de item para não permitir inventário físico negativo e defina somente o armazém relevante para permitir inventário negativo.
