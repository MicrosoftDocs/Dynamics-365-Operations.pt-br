---
title: Habilitar o processamento do modo de entrega consistente em canais de comércio eletrônico
description: Este artigo descreve como habilitar o processamento do modo de entrega consistente para corrigir possíveis problemas relacionados a fluxos de encargos em canais de comércio eletrônico do Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 02/24/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgri
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2022-02-10
ms.openlocfilehash: f32f1915f8f7de1d5536b69b05bc74c6149dfda6
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8885576"
---
# <a name="enable-consistent-delivery-mode-handling-in-e-commerce-channels"></a>Habilitar o processamento do modo de entrega consistente em canais de comércio eletrônico 

[!include [banner](includes/banner.md)]

Este artigo descreve como habilitar o processamento do modo de entrega consistente para corrigir possíveis problemas relacionados a fluxos de encargos em canais de comércio eletrônico do Microsoft Dynamics 365 Commerce.

No Dynamics 365 Commerce, os encargos no nível de cabeçalho não rateados não são aplicados por padrão em canais de comércio eletrônico. Esse comportamento pode causar um ou mais dos seguintes problemas nos canais de comércio eletrônico:

- Os encargos no nível de cabeçalho não rateados não são exibidos.
- Os encargos para modos de entrega não são consistentes entre a seleção do modo de entrega e o resumo da ordem de finalização da compra.

Para corrigir esses problemas, é necessário ativar o recurso **Habilitar o processamento do modo de entrega consistente no canal**. Esse recurso garante que os encargos no nível de cabeçalho não rateados apareçam em canais de comércio eletrônico e que as informações de entrega da ordem de venda sejam processadas consistentemente pelo mesmo fluxo de trabalho da solicitação.

## <a name="turn-on-the-enable-consistent-delivery-mode-handling-in-channel-feature"></a>Ative o recurso Habilitar o processamento do modo de entrega consistente no canal

Para habilitar o recurso **Habilitar o processamento do modo de entrega consistente no canal** no Commerce headquarters, siga estas etapas.

1. Abra o espaço de trabalho **Gerenciamento de recursos** (**Administração do sistema \> Espaços de trabalho \> Gerenciamento de recursos**).
1. Na lista de recursos disponíveis, pesquise e selecione **Habilitar o processamento do modo de entrega consistente no canal**.
1. No painel à direita, selecione **Habilitar agora**.
