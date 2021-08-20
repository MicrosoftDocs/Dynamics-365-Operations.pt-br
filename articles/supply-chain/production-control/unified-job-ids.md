---
title: Sequência numérica unificada para IDs de trabalho
description: Esse recurso fornece uma sequência numérica única e unificada que gera IDs de trabalho para os módulos Controle de produção, Execução de fabricação e Tempo e presença.
author: johanhoffmann
ms.date: 03/25/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2021-03-05
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: 8ff8fae0bb20b11b15c7520fbb14727ff0372ca0255adc82599c6680a64671af
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6748706"
---
# <a name="unified-number-sequence-for-job-ids"></a>Sequência numérica unificada para IDs de trabalho

[!include [banner](../includes/banner.md)]

Esse recurso fornece uma sequência numérica única e unificada que gera IDs de trabalho para os módulos Controle de produção, Execução de fabricação e Tempo e presença. Anteriormente, você conseguia escolher uma sequência numérica diferente para cada um desses módulos, o que podia resultar em uma identificação de trabalho conflitante se duas ou mais dessas sequências usassem um formato idêntico. Esse conflito pode causar a corrupção de dados.

## <a name="turn-on-this-feature-for-your-system"></a>Ative este recurso para o seu sistema

Se o sistema ainda não incluir o recurso descrito neste tópico, acesse [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) e ative o recurso *Sequência numérica unificada para IDs de trabalho*.

## <a name="set-up-the-unified-number-sequence-for-job-ids"></a>Configurar a sequência numérica unificada para identificações de trabalho

Depois de habilitar esse recurso, as configurações existentes da sequência numérica **Identificação do trabalho** localizadas nas páginas de parâmetros para os módulos Controle de produção, Execução de fabricação e Tempo e presença serão preteridas e um novo campo **ID do trabalho unificada** será adicionado. O valor da **ID do trabalho unificado** é compartilhado por todos os três módulos, garantindo, dessa forma, que todos os módulos façam referência à mesma sequência numérica. Portanto, as IDs do trabalho serão exclusivas entre os três módulos e um conflito nunca ocorrerá.

Para configurar a sequência numérica unificada para IDs do trabalho:

1. Ative o recurso conforme descrito na seção anterior.
1. Identifique a sequência numérica que você deseja usar para as IDs do trabalho unificadas ou crie uma nova. Para obter mais informações, consulte [Visão geral de sequências numéricas](../../fin-ops-core/fin-ops/organization-administration/number-sequence-overview.md).
1. Acesse a página **Parâmetros de controle de produção**, **Parâmetros de execução de fabricação** ou **Parâmetros de tempo e presença**. Não importa qual seja a escolha, já que quando você faz essa configuração em qualquer uma dessas páginas, todas as outras páginas são atualizadas automaticamente.
1. Abra a guia **Sequências numéricas** na página de parâmetros selecionada.
1. Atribua o **Código de sequência numérica** identificado anteriormente à linha **IDs do trabalho unificadas** da grade.
