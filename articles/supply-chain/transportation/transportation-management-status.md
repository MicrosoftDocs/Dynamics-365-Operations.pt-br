---
title: Status de gerenciamento de transporte
description: Este artigo explica como criar um status de transporte e mapear esse status para um status de transportadora.
author: Weijiesa
ms.date: 10/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: weijiesa
ms.search.validFrom: 2020-09-08
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 9b20570a87a9f8969ca6dcf898176fd40f88eeca
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8897361"
---
# <a name="transportation-management-statuses"></a>Status de gerenciamento de transporte

[!include [banner](../includes/banner.md)]

Configure códigos mestre para status de transporte para interpretar códigos fornecidos por suas transportadoras. Isso permite a integração com transportadoras para fornecer um status. O status de transporte que você fornece para um código de status mestre de transporte pode ajudar você a rastrear o status de uma carga, remessa ou contêiner. O status de transporte específico para uma carga, remessa ou contêiner só pode ser atualizado por meio da integração de dados e não manualmente por meio da interface do usuário.

## <a name="create-a-transportation-status"></a>Criar o status do transporte

Para criar um status de transporte, siga estas etapas:

1. Acesse **Gerenciamento de transporte \> Configurar \> Mestres do status do transporte**.
1. Selecione **Novo** para criar um mestre de status do transporte.
1. No campo **Mestre do status do transporte**, insira um código exclusivo para o status de transporte.
1. No campo **Tipo de transporte**, selecione *Transportadora* ou *Hub* como o tipo de transporte.
1. Insira um nome e status de transporte.
1. Feche a página.

## <a name="map-a-transportation-status-to-a-carrier-status"></a>Mapear um status de transporte para um status de transportadora

Para mapear um status de transporte para um status de transportadora, siga estas etapas:

1. Acesse **Gerenciamento de transporte \> Configurar \> Transportadoras \> Status do transporte da transportadora**.
1. Selecione **Novo** para mapear um código de uma transportadora para um código mestre de status da transportadora.
1. Selecione a ID exclusiva da transportadora e o serviço da transportadora.
1. Selecione o código de status do transporte a ser mapeado para o código da transportadora selecionada.
1. Insira o código externo que é usado pela transportadora.
1. Feche a página.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]