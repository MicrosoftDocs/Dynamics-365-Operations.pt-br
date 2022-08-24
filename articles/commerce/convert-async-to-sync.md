---
title: Converter clientes assíncronos em clientes síncronos
description: Este artigo explica como converter clientes assíncronos em clientes síncronos no Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 12/10/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-12-17
ms.openlocfilehash: b442bfc0685706359771e4d9e2729565d3652a60
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9278183"
---
# <a name="convert-asynchronous-customers-to-synchronous-customers"></a>Converter clientes assíncronos em clientes síncronos

[!include [banner](includes/banner.md)]

Este artigo explica como converter clientes assíncronos em clientes síncronos no Microsoft Dynamics 365 Commerce.

Para converter clientes assíncronos em clientes síncronos, siga estas etapas.

1. No Commerce headquarters, execute o **trabalho P** para enviar os clientes assíncronos para o Commerce headquarters.
1. Execute o trabalho **Sincronizar clientes e parceiros comerciais do modo assíncrono** para criar IDs da conta de cliente. (Anteriormente denominado trabalho **Sincronizar clientes e parceiros comerciais do modo assíncrono**.)
1. Execute o trabalho **1010** para sincronizar as novas IDs da conta de cliente para os canais.

Se uma ordem fizer referência a um cliente ou endereço assíncrono que ainda não foi sincronizado com o Commerce headquarters, o cliente ou o endereço será sincronizado como parte do trabalho em lotes **Sincronizar ordens**. Se uma transação cash-and-carry fizer referência a um cliente ou endereço assíncrono, o cliente ou o endereço será sincronizado antes do lançamento do EOD (final do dia).

## <a name="additional-resources"></a>Recursos adicionais

[Gerenciamento de clientes em lojas](customer-mgmt-stores.md)

[Modo de criação de cliente assíncrono](async-customer-mode.md)

[Atributos de clientes](dev-itpro/customer-attributes.md)

[Exclusão de dados offline](dev-itpro/implementation-considerations-cdx.md#offline-data-exclusion)
