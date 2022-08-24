---
title: Definir direitos de administrador para eventos da vida
description: Este artigo explica como configurar direitos de administrador para eventos da vida no Microsoft Dynamics 365 Human Resources.
author: twheeloc
ms.date: 08/01/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 9deed240977394667cee8b107397267b182d960b
ms.sourcegitcommit: e0905a3af85d8cdc24a22e0c041cb3a391c036cb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/06/2022
ms.locfileid: "9229885"
---
# <a name="set-administrator-rights-for-life-events"></a>Definir direitos de administrador para eventos da vida

[!include [banner](../includes/preview-banner.md)]

Os administradores podem atualizar as opções de eventos da vida, dependendo das definições de configuração. Na página **Parâmetros de recursos humanos**, você pode configurar parâmetros que permitem aos administradores fazer alterações em seleções de plano. Você também pode restringir totalmente os administradores a fazerem alterações.

Na página **Parâmetros de recursos humanos**, você pode configurar restrições de alteração de plano para planos confirmados e opções de evento de vida.

Se a opção **Planos confirmados** estiver selecionada, as alterações só poderão ser feitas se um período de inscrição estiver ativo. (Exemplos de períodos de inscrição incluem períodos de inscrição abertos, novos períodos de inscrição de contratação e períodos de inscrição de eventos da vida.) Se essa opção não estiver selecionada, as alterações poderão ser feitas a qualquer momento.

Se a opção **Opções de evento da vida** estiver selecionada, as alterações de plano durante um evento da vida serão restritas pelas opções de evento da vida definidas no tipo de plano. Se essa opção não estiver selecionada, será possível alterar as seleções de plano durante um evento da vida.

## <a name="set-plan-change-restrictions"></a>Definir restrições de alteração do plano

Na página **Parâmetros de recursos humanos**, na guia **Gerenciamento de benefícios**, os campos a seguir estão disponíveis.

| Campo | Descrição |
|-------|-------------|
| Planos confirmados | Selecione esta opção se forem permitidas alterações em um plano somente se um período de inscrição estiver ativo. Se essa opção não estiver selecionada, as alterações poderão ser feitas a qualquer momento. |
| Opções de evento de vida | Selecione esta opção se as alterações de plano durante um evento da vida forem restritas pelas opções de evento da vida definidas no tipo de plano. Se essa opção não estiver selecionada, será possível alterar as seleções de plano durante um evento da vida. |
