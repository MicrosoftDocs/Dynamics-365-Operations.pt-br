---
title: Desabilitar regras usadas no processo de validação de transação
description: Este artigo descreve a funcionalidade para desabilitar as regras de validação de transação no Microsoft Dynamics 365 Commerce.
author: analpert
ms.date: 12/11/2021
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
ms.openlocfilehash: 7d566aa3b829dad281528925a341382f9637fdba
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8884866"
---
# <a name="disable-rules-used-in-the-transaction-validation-process"></a>Desabilitar regras usadas no processo de validação de transação

[!include [banner](../includes/banner.md)]

Os varejistas podem ter os cenários comerciais e processos que são exclusivos deles. Portanto, nem todas as regras incluídas no processo de validação de transação comercial são aplicáveis a todos os varejistas. Para acomodar diferenças, o Microsoft Dynamics 365 Commerce fornece uma funcionalidade que pode ser usada para desabilitar as regras que não são aplicáveis.

Para exibir a lista de regras que estão disponíveis no processo de validação de transação no seu ambiente e para ver o status de cada regra, vá para **Retail e Commerce** \> Configuração da sede \> Parâmetros \> Parâmetros do Commerce e selecione a guia **Validação da transação**. Todas as regras habilitadas são usadas para validar transações durante o processo **Validar transações de loja** e devem ser aprovadas para que as transações sejam coletadas e lançadas em um demonstrativo transacional.

Por padrão, o status de cada regra é definido como **Habilitado**. Portanto, todas as regras são usadas para validar transações para que elas possam ser incluídas nos demonstrativos transacionais comerciais. Para desabilitar uma regra, altere seu status para **Desabilitado**. As regras desabilitadas não serão consideradas quando as transações forem validadas durante o processo **Validar transações de loja**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
