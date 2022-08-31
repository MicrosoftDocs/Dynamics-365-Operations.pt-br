---
title: Zonas de localização adicionais
description: Este artigo mostra uma visão geral das novas zonas de localização que foram adicionadas ao Microsoft Dynamics 365 Supply Chain Management.
author: Mirzaab
ms.date: 08/09/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSLocationBuild, WHSZone
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: 819330e0f6e6cd419da441f919d68ff996b6475c
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/23/2022
ms.locfileid: "9336475"
---
# <a name="additional-location-zones"></a>Zonas de localização adicionais

[!include [banner](../includes/banner.md)]

Três novos campos de zona estão disponíveis no Microsoft Dynamics 365 Supply Chain Management. Os gerentes de depósito podem usá-los para definir organizações ou layouts de depósito adicionais. Os novos campos de zona podem ser definidos manualmente ou usando o assistente **Configuração de localização**. Eles podem ser usados em qualquer consulta ou filtragem que utiliza a tabela Localizações.

Nenhuma configuração adicional é necessária para usar os campos de zona.

## <a name="turn-the-additional-location-zone-feature-on-or-off"></a>Ativar ou desativar o recurso Zona de localização adicional

Para usar esse recurso, você deve habilitá-lo no seu sistema. A partir do Supply Chain Management versão 10.0.25, o recurso está ativado por padrão. A partir do Supply Chain Management versão 10.0.29, o recurso é obrigatório e não pode ser desativado. Se você estiver executando uma versão anterior à 10.0.29, os administradores poderão ativar ou desativar essa funcionalidade procurando o recurso *Zona de localização adicional* no espaço de trabalho [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="use-location-zones"></a>Usar zonas de localização

1. Acesse **Gerenciamento de depósito \> Configuração \> Depósito \> Assistente de configuração de localização**.
2. Defina os seguintes valores:

    - No campo **Depósito**, selecione _62_.
    - No campo **ID da zona**, selecione _CHÃO_.
    - No campo **Zona Adicional 1**, selecione _PICKZONE1_.
    - No campo **Zona Adicional 2**, selecione _WEBSHOP1_.
    - No campo **ID do perfil de localização**, selecione _FLOOR_.

3. Selecione a linha **Chão**.
4. No campo **Número inicial**, insira _1_. No campo **Número final**, insira _3_.
5. Selecione a linha **Corredor**.
6. No campo **Número inicial**, insira _1_. No campo **Número final**, insira _5_.
7. Selecione **Criar**.
8. Você recebe mensagens indicando que novas localizações foram adicionadas. Selecione o botão **Mostrar mensagens** para exibir as mensagens.
9. Acesse **Gerenciamento de depósito \> Configuração \> Depósito \> Localizações**. As novas localizações serão exibidas na lista, e todos os campos de zona estarão disponíveis (ou seja, o campo de zona existente e os novos campos de zona adicionais).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]