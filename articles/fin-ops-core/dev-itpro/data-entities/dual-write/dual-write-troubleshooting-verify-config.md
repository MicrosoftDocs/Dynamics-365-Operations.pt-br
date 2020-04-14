---
title: Verifique se a gravação dupla está configurada nos aplicativos Finance and Operations e Common Data Service
description: Este tópico explica como você pode determinar se a gravação dupla está configurada em aplicativos Finance and Operations e em Common Data Service.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 03/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: 2f2ba2564ad3e8e444e27fcc0c586ddf252afabd
ms.sourcegitcommit: 68f1485de7d64a6c9eba1088af63bd07992d972d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2020
ms.locfileid: "3172636"
---
# <a name="verify-that-dual-write-is-configured-in-finance-and-operations-apps-and-common-data-service"></a>Verifique se a gravação dupla está configurada nos aplicativos Finance and Operations e Common Data Service

[!include [banner](../../includes/banner.md)]



Este tópico fornece informações de solução de problemas para integração de gravação dupla entre aplicativos do Finance and Operations e o Common Data Service. Especificamente, ele explica como você pode determinar se a gravação dupla está configurada em aplicativos Finance and Operations e em Common Data Service.

## <a name="verify-that-dual-write-is-configured-in-a-finance-and-operations-app"></a>Verifique se a gravação dupla está configurada em um aplicativo Finance and Operations

Para determinar se os erros que você vê ao tentar salvar registros para atualização são provenientes de duas gravações, verifique primeiro se a gravação dupla está configurada.

+ Se você tiver privilégios de administrador no aplicativo Finance and Operations, vá para **Espaços de trabalho \> Gerenciamento de dados** e selecione o bloco **Gravação dupla**. Se os detalhes dos ambientes vinculados e a lista de mapas de entidade que estão sendo executados são exibidos, a gravação dupla é configurada.

    ![Verificando a conexão do aplicativo Finance and Operations quando você tem privilégios administrativos](media/verify_fin_ops_1.png)

+ Se você não tiver privilégios de administrador, receberá uma mensagem de erro *Não será possível gravar dados no nome da entidade \< da entidade \>*. No exemplo da ilustração a seguir, não é possível criar um registro de cliente no aplicativo Finance and Operations, porque a gravação dupla está configurada, mas o grupo de clientes e os dados de referência das condições de pagamento não existem no Common Data Service.

    ![Verificando a conexão do aplicativo Finance and Operations quando você não tem privilégios administrativos](media/verify_fin_ops_2.png)

Para obter informações sobre como corrigir problemas ao criar dados em aplicativos Finance and Operations, consulte [Solucionar problemas de sincronização ao vivo](dual-write-troubleshooting-live-sync.md).

## <a name="verify-that-dual-write-is-configured-in-common-data-service"></a>Verifique se a gravação dupla está configurada em Common Data Service

Ao criar dados, se você vir o campo **Empresa** em páginas no Common Data Service, a gravação dupla é configurada.

![Verificando a conexão Common Data Service](media/verify_cds.png)

Para obter informações sobre como corrigir problemas ao criar dados em Common Data Service, consulte [Solucionar problemas de sincronização ao vivo](dual-write-troubleshooting-live-sync.md).

Para obter informações sobre como exibir detalhes de erro se você encontrar algum erro ao criar dados no Common Data Service, consulte [Habilitar e exibir o log de rastreamento de plug-in no Common Data Service para exibir os detalhes de erro ](dual-write-troubleshooting.md#enable-and-view-the-plug-in-trace-log-in-common-data-service-to-view-error-details).
