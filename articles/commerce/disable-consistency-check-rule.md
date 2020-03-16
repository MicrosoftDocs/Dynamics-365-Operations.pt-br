---
title: Desabilitar regras no verificador de consistência das transações de varejo
description: Este tópico descreve a funcionalidade para desabilitar as regras do verificador de consistência das transações no Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: 51a02d6f305cbad9784cf1b811188d0e06b6f15b
ms.sourcegitcommit: 12b9d6f2dd24e52e46487748c848864909af6967
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2020
ms.locfileid: "3057628"
---
# <a name="disable-rules-in-the-retail-transaction-consistency-checker"></a>Desabilitar regras no verificador de consistência das transações de varejo 

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

Os varejistas podem ter os cenários comerciais e processos que são exclusivos deles. Portanto, nem todas as regras incluídas por padrão no verificador de consistência das transações comerciais são aplicáveis a todos os varejistas. Para acomodar diferenças, o Microsoft Dynamics 365 Commerce fornece uma funcionalidade que pode ser usada para desabilitar as regras que não são aplicáveis.

Para exibir a lista de regras que estão disponíveis no verificador de consistência das transações de varejo em seu ambiente e para consultar e o status de cada regra, acesse **Retail e Commerce \> Configuração da sede \> Parâmetros \> Parâmetros do Commerce** e selecione a guia **Validação da transação**.

Por padrão, o status de cada regra é definido como **Habilitado**. Portanto, todas as regras são usadas para validar transações de varejo antes que elas sejam incluídas nos demonstrativos comerciais. Para desabilitar uma regra, altere seu status para **Desabilitado**. As regras desabilitadas não serão consideradas quando as transações forem validadas durante o processo de cálculo do demonstrativo.

Para ignorar o processo de validação inteiro, independentemente das regras que estão habilitadas, acesse **Retail e Commerce \> Configuração da sede \> Parâmetros \> Parâmetros do Commerce** e, na guia **Validação da transação**, defina a opção **Desativar verificador de consistência das transações do Commerce** como **Sim**. Depois que essa opção for definida como **Não**, ela não poderá ser redefinida como **Sim** na interface do usuário (IU).
