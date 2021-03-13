---
title: Verificar configuração de gravação dupla nos aplicativos Finance and Operations e Dataverse
description: Este tópico explica como você pode determinar se a gravação dupla está configurada em aplicativos Finance and Operations e em Dataverse.
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
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: 361d6555b60e02832c337b6f416b2b3627b6d365
ms.sourcegitcommit: f8bac7ca2803913fd236adbc3806259a17a110f4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2021
ms.locfileid: "5129298"
---
# <a name="verify-dual-write-configuration-in-finance-and-operations-apps-and-dataverse"></a>Verificar configuração de gravação dupla nos aplicativos Finance and Operations e Dataverse

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]



Este tópico fornece informações de solução de problemas para integração de gravação dupla entre aplicativos do Finance and Operations e o Dataverse. Especificamente, ele explica como você pode determinar se a gravação dupla está configurada em aplicativos Finance and Operations e em Dataverse.

## <a name="verify-that-dual-write-is-configured-in-a-finance-and-operations-app"></a>Verifique se a gravação dupla está configurada em um aplicativo Finance and Operations

Para determinar se os erros que você vê ao tentar salvar linhas para atualização são provenientes de duas gravações, verifique primeiro se a gravação dupla está configurada.

+ Se você tiver privilégios de administrador no aplicativo Finance and Operations, vá para **Espaços de trabalho \> Gerenciamento de dados** e selecione o bloco **Gravação dupla**. Se os detalhes dos ambientes vinculados e a lista de mapas de tabela que estão sendo executados são exibidos, a gravação dupla é configurada.

    ![Verificando a conexão do aplicativo Finance and Operations quando você tem privilégios administrativos](media/verify_fin_ops_1.png)

+ Se você não tiver privilégios de administrador, receberá uma mensagem de erro *Não é possível gravar dados na entidade \<entity name\>*. No exemplo da ilustração a seguir, não é possível criar uma linha de cliente no aplicativo Finance and Operations, porque a gravação dupla está configurada, mas o grupo de clientes e os dados de referência das condições de pagamento não existem no Dataverse.

    ![Verificando a conexão do aplicativo Finance and Operations quando você não tem privilégios administrativos](media/verify_fin_ops_2.png)

Para obter informações sobre como corrigir problemas ao criar dados em aplicativos Finance and Operations, consulte [Solucionar problemas de sincronização ao vivo](dual-write-troubleshooting-live-sync.md).

## <a name="verify-that-dual-write-is-configured-in-dataverse"></a>Verifique se a gravação dupla está configurada em Dataverse

Ao criar dados, se você vir a coluna **Empresa** em páginas no Dataverse, a gravação dupla está configurada.

![Verificando a conexão Dataverse](media/verify_cds.png)

Para obter informações sobre como corrigir problemas ao criar dados em Dataverse, consulte [Solucionar problemas de sincronização ao vivo](dual-write-troubleshooting-live-sync.md).

Para obter informações sobre como exibir detalhes de erro se você encontrar algum erro ao criar dados no Dataverse, consulte [Habilitar e exibir o log de rastreamento de plug-in no Dataverse para exibir os detalhes de erro ](dual-write-troubleshooting.md#enable-view-trace).
