---
title: Zonas de localização adicionais
description: Este artigo mostra uma visão geral das novas zonas de localização que foram adicionadas ao Microsoft Dynamics 365 Supply Chain Management.
author: Mirzaab
ms.date: 07/01/2020
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
ms.openlocfilehash: c20225cfb3c44fff955d0ad4e96c7fecf0ddf715
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8900641"
---
# <a name="additional-location-zones"></a>Zonas de localização adicionais

[!include [banner](../includes/banner.md)]

Três novos campos de zona estão disponíveis no Microsoft Dynamics 365 Supply Chain Management. Os gerentes de depósito podem usá-los para definir organizações ou layouts de depósito adicionais. Os novos campos de zona podem ser definidos manualmente ou usando o assistente **Configuração de localização**. Eles podem ser usados em qualquer consulta ou filtragem que utiliza a tabela Localizações.

Nenhuma configuração adicional é necessária para usar os campos de zona.

## <a name="turn-the-additional-location-zone-feature-on-or-off"></a>Ativar ou desativar o recurso Zona de localização adicional

A partir da versão 10.0.25 do Supply Chain Management, este recurso está ativado por padrão. Os administradores podem ativar ou desativar essa funcionalidade procurando o recurso *Zona de localização adicional* no espaço de trabalho [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

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