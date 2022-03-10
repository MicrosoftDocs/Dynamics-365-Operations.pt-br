---
title: Verificar a configuração de gravação dupla em aplicativos do Finance and Operations e no Dataverse
description: Este tópico explica como você pode determinar se a gravação dupla está configurada em aplicativos de Finanças e Operações e no Dataverse.
author: RamaKrishnamoorthy
ms.date: 03/16/2020
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 3fa16a450032464e445ae166f0699fe0dc388071
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8062791"
---
# <a name="verify-dual-write-configuration-in-finance-and-operations-apps-and-dataverse"></a>Verificar a configuração de gravação dupla em aplicativos do Finance and Operations e no Dataverse

[!include [banner](../../includes/banner.md)]





Este tópico fornece informações de solução de problemas para a integração de gravação dupla entre aplicativos de Finanças e Operações e o Dataverse. Especificamente, ele explica como você pode determinar se a gravação dupla está configurada em aplicativos de Finanças e Operações e no Dataverse.

## <a name="verify-that-dual-write-is-configured-in-a-finance-and-operations-app"></a>Verificar se a gravação dupla está configurada em um aplicativo de Finanças e Operações

Para determinar se os erros que você vê ao tentar salvar linhas para atualização são provenientes de duas gravações, verifique primeiro se a gravação dupla está configurada.

+ Se você tiver privilégios de administrador no aplicativo de Finanças e Operações, acesse **Espaços de trabalho \> Gerenciamento de dados** e selecione o bloco **Gravação dupla**. Se os detalhes dos ambientes vinculados e a lista de mapas de tabela que estão sendo executados são exibidos, a gravação dupla é configurada.

    ![Verificar a conexão do aplicativo de Finanças e Operações quando você não tem privilégios administrativos.](media/verify_fin_ops_1.png)

+ Se você não tiver privilégios de administrador, receberá uma mensagem de erro *Não é possível gravar dados na entidade \<entity name\>*. No exemplo da ilustração a seguir, não é possível criar uma linha de cliente no aplicativo de Finanças e Operações, porque a gravação dupla está configurada, mas o grupo de clientes e os dados de referência das condições de pagamento não existem no Dataverse.

    ![Verificar a conexão do aplicativo de Finanças e Operações quando você não tem privilégios administrativos.](media/verify_fin_ops_2.png)

Para obter informações sobre como corrigir problemas ao criar dados em aplicativos de Finanças e Operações, consulte [Solucionar problemas de sincronização ao vivo](dual-write-troubleshooting-live-sync.md).

## <a name="verify-that-dual-write-is-configured-in-dataverse"></a>Verifique se a gravação dupla está configurada em Dataverse

Ao criar dados, se você vir a coluna **Empresa** em páginas no Dataverse, a gravação dupla está configurada.

![Verificando a conexão Dataverse.](media/verify_cds.png)

Para obter informações sobre como corrigir problemas ao criar dados em Dataverse, consulte [Solucionar problemas de sincronização ao vivo](dual-write-troubleshooting-live-sync.md).

Para obter informações sobre como exibir detalhes de erro se você encontrar algum erro ao criar dados no Dataverse, consulte [Habilitar e exibir o log de rastreamento de plug-in no Dataverse para exibir os detalhes de erro ](dual-write-troubleshooting.md#enable-view-trace).


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]