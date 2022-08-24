---
title: Verificar a configuração de gravação dupla em aplicativos de finanças e operações e no Dataverse
description: Este artigo explica como você pode determinar se a gravação dupla está configurada em aplicativos de finanças e operações e no Dataverse.
author: RamaKrishnamoorthy
ms.date: 03/16/2020
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 4ff7821fce661f174f57fb45667d4ceb3cfcede9
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9289380"
---
# <a name="verify-dual-write-configuration-in-finance-and-operations-apps-and-dataverse"></a>Verificar a configuração de gravação dupla em aplicativos de finanças e operações e no Dataverse

[!include [banner](../../includes/banner.md)]





Este artigo fornece informações de solução de problemas para a integração de gravação dupla entre aplicativos de finanças e operações e o Dataverse. Especificamente, ele explica como você pode determinar se a gravação dupla está configurada em aplicativos de finanças e operações e no Dataverse.

## <a name="verify-that-dual-write-is-configured-in-a-finance-and-operations-app"></a>Verificar se a gravação dupla está configurada em um aplicativo de finanças e operações

Para determinar se os erros que você vê ao tentar salvar linhas para atualização são provenientes de duas gravações, verifique primeiro se a gravação dupla está configurada.

+ Se você tiver privilégios de administrador no aplicativo de finanças e operações, acesse **Espaços de trabalho \> Gerenciamento de dados** e selecione o bloco **Gravação dupla**. Se os detalhes dos ambientes vinculados e a lista de mapas de tabela que estão sendo executados são exibidos, a gravação dupla é configurada.

    ![Verificando a conexão do aplicativo de finanças e operações quando você tem privilégios administrativos.](media/verify_fin_ops_1.png)

+ Se você não tiver privilégios de administrador, receberá uma mensagem de erro *Não é possível gravar dados na entidade \<entity name\>*. No exemplo da ilustração a seguir, não é possível criar uma linha de cliente no aplicativo de finanças e operações porque a gravação dupla está configurada, mas o grupo de clientes e os dados de referência das condições de pagamento não existem no Dataverse.

    ![Verificando a conexão do aplicativo de finanças e operações quando você não tem privilégios administrativos.](media/verify_fin_ops_2.png)

Para obter informações sobre como corrigir problemas ao criar dados em aplicativos de finanças e operações, consulte [Solucionar problemas de sincronização ao vivo](dual-write-troubleshooting-live-sync.md).

## <a name="verify-that-dual-write-is-configured-in-dataverse"></a>Verifique se a gravação dupla está configurada em Dataverse

Ao criar dados, se você vir a coluna **Empresa** em páginas no Dataverse, a gravação dupla está configurada.

![Verificando a conexão Dataverse.](media/verify_cds.png)

Para obter informações sobre como corrigir problemas ao criar dados em Dataverse, consulte [Solucionar problemas de sincronização ao vivo](dual-write-troubleshooting-live-sync.md).

Para obter informações sobre como exibir detalhes de erro se você encontrar algum erro ao criar dados no Dataverse, consulte [Habilitar e exibir o log de rastreamento de plug-in no Dataverse para exibir os detalhes de erro ](dual-write-troubleshooting.md#enable-view-trace).


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
