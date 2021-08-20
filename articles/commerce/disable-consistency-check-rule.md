---
title: Desabilitar regras no verificador de consistência das transações de varejo
description: Este tópico descreve a funcionalidade para desabilitar as regras do verificador de consistência das transações no Microsoft Dynamics 365 Commerce.
author: josaw1
ms.date: 10/15/2019
ms.topic: index-page
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: ''
ms.openlocfilehash: 381bc8534d4b0a06a50c8c18b3f78aba9d43a1f497bfd271361216ed1dee9197
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6746652"
---
# <a name="disable-rules-in-the-retail-transaction-consistency-checker"></a>Desabilitar regras no verificador de consistência das transações de varejo 

[!include [banner](../includes/banner.md)]

Os varejistas podem ter os cenários comerciais e processos que são exclusivos deles. Portanto, nem todas as regras incluídas por padrão no verificador de consistência das transações comerciais são aplicáveis a todos os varejistas. Para acomodar diferenças, o Microsoft Dynamics 365 Commerce fornece uma funcionalidade que pode ser usada para desabilitar as regras que não são aplicáveis.

Para exibir a lista de regras que estão disponíveis no verificador de consistência das transações de varejo em seu ambiente e para consultar e o status de cada regra, acesse **Retail e Commerce \> Configuração da sede \> Parâmetros \> Parâmetros do Commerce** e selecione a guia **Validação da transação**.

Por padrão, o status de cada regra é definido como **Habilitado**. Portanto, todas as regras são usadas para validar transações de varejo antes que elas sejam incluídas nos demonstrativos comerciais. Para desabilitar uma regra, altere seu status para **Desabilitado**. As regras desabilitadas não serão consideradas quando as transações forem validadas durante o processo de cálculo do demonstrativo.

Para ignorar o processo de validação inteiro, independentemente das regras que estão habilitadas, acesse **Retail e Commerce \> Configuração da sede \> Parâmetros \> Parâmetros do Commerce** e, na guia **Validação da transação**, defina a opção **Desativar verificador de consistência das transações do Commerce** como **Sim**. Depois que essa opção for definida como **Não**, ela não poderá ser redefinida como **Sim** na interface do usuário (IU).


[!INCLUDE[footer-include](../includes/footer-banner.md)]