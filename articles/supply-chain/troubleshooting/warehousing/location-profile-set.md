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
ms.openlocfilehash: 2a7345281301ee70a512dfadcd553cb4eb33003904d0dddf6967659b693f60d7
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6742599"
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
