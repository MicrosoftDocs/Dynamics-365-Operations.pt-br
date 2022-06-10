---
title: Converter clientes assíncronos em clientes síncronos
description: Este tópico explica como converter clientes assíncronos em clientes síncronos no Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 12/10/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgri
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-12-17
ms.openlocfilehash: fc1690ff6068317c748bda0d767a10f306f3debe
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/04/2022
ms.locfileid: "8691435"
---
# <a name="convert-asynchronous-customers-to-synchronous-customers"></a>Converter clientes assíncronos em clientes síncronos

[!include [banner](includes/banner.md)]

Este tópico explica como converter clientes assíncronos em clientes síncronos no Microsoft Dynamics 365 Commerce.

Para converter clientes assíncronos em clientes síncronos, siga estas etapas.

1. Na matriz do Commerce, execute o **trabalho P** para enviar os clientes assíncronos para a matriz do Commerce.
1. Execute o trabalho **Sincronizar clientes e parceiros comerciais do modo assíncrono** para criar IDs da conta de cliente. (Anteriormente denominado trabalho **Sincronizar clientes e parceiros comerciais do modo assíncrono**.)
1. Execute o trabalho **1010** para sincronizar as novas IDs da conta de cliente para os canais.

Se uma ordem fizer referência a um cliente ou endereço assíncrono que ainda não foi sincronizado com a matriz do Commerce, o cliente ou o endereço será sincronizado como parte do trabalho em lotes **Sincronizar ordens**. Se uma transação cash-and-carry fizer referência a um cliente ou endereço assíncrono, o cliente ou o endereço será sincronizado antes do lançamento do EOD (final do dia).

## <a name="additional-resources"></a>Recursos adicionais

[Gerenciamento de clientes em lojas](customer-mgmt-stores.md)

[Modo de criação de cliente assíncrono](async-customer-mode.md)

[Atributos de clientes](dev-itpro/customer-attributes.md)

[Exclusão de dados offline](dev-itpro/implementation-considerations-cdx.md#offline-data-exclusion)