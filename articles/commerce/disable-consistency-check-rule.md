---
title: Desabilitar regras no verificador de consistência das transações de varejo
description: Este tópico descreve a funcionalidade para desabilitar as regras do verificador de consistência das transações de varejo no Microsoft Dynamics 365 Commerce.
author: josaw1
manager: AnnBe
ms.date: 10/15/2019
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: ''
ms.openlocfilehash: b11b901fafc3907e9d3cae5cd554cc9a868a414c
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/01/2020
ms.locfileid: "3004334"
---
# <a name="disable-rules-in-the-retail-transaction-consistency-checker"></a>Desabilitar regras no verificador de consistência das transações de varejo 

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

Os varejistas podem ter os cenários comerciais e processos que são exclusivos deles. Portanto, nem todas as regras incluídas por padrão no verificador de consistência das transações de comércio são aplicáveis a todos os varejistas. Para acomodar diferenças, o Microsoft Dynamics 365 Commerce fornece uma funcionalidade que pode ser usada para desabilitar as regras que não são aplicáveis.

Para exibir a lista de regras que estão disponíveis no verificador de consistência das transações de varejo em seu ambiente e para consultar e o status de cada regra, acesse **Varejo e Comércio \> Configuração da sede \> Parâmetros \> Parâmetros de comércio** e selecione a guia **Validação da transação**.

Por padrão, o status de cada regra é definido como **Habilitado**. Portanto, todas as regras são usadas para validar transações de varejo antes que elas sejam incluídas nos demonstrativos de comércio. Para desabilitar uma regra, altere seu status para **Desabilitado**. As regras desabilitadas não serão consideradas quando as transações forem validadas durante o processo de cálculo do demonstrativo.

Para ignorar o processo de validação inteiro, independentemente das regras que estão habilitadas, acesse **Varejo e Comércio \> Configuração da sede \> Parâmetros \> Parâmetros de comércio** e, na guia **Validação da transação**, defina a opção **Desativar verificador de consistência das transações de comércio** como **Sim**. Depois que essa opção for definida como **Não**, ela não poderá ser redefinida como **Sim** na interface do usuário (IU).
