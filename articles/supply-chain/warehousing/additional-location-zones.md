---
title: Zonas de localização adicionais
description: Este tópico mostra uma visão geral das novas zonas de localização que foram adicionadas ao Microsoft Dynamics 365 Supply Chain Management.
author: Mirzaab
manager: tfehr
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
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
ms.openlocfilehash: 4e8d8ddb65ea49f3d5278db0cac6ae891ab40ecf
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5233214"
---
# <a name="additional-location-zones"></a>Zonas de localização adicionais

[!include [banner](../includes/banner.md)]

Três novos campos de zona estão disponíveis no Microsoft Dynamics 365 Supply Chain Management. Os gerentes de depósito podem usá-los para definir organizações ou layouts de depósito adicionais. Os novos campos de zona podem ser definidos manualmente ou usando o assistente **Configuração de localização**. Eles podem ser usados em qualquer consulta ou filtragem que utiliza a tabela Localizações.

Nenhuma configuração adicional é necessária para usar os campos de zona.

## <a name="turn-on-the-additional-location-zone-feature"></a>Ativar o recurso Zona de localização adicional

Para que você possa usar o recurso *Zona de localização adicional*, ele deve estar ativado no sistema. Os administradores podem usar as configurações de [gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar o status do recurso e ativá-lo se necessário. No espaço de trabalho **Gerenciamento de recursos**, o recurso está listado da seguinte forma:

- **Módulo:** *Gerenciamento de Depósito*
- **Nome do recurso:** *Zona de localização adicional*

## <a name="use-location-zones"></a>Usar zonas de localização

1. Vá para **Gerenciamento de depósito \> Configuração \> Depósito \> Assistente de configuração de localização**.
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
9. Vá para **Gerenciamento de depósito \> Configuração \> Depósito \> Localizações**. As novas localizações serão exibidas na lista, e todos os campos de zona estarão disponíveis (ou seja, o campo de zona existente e os novos campos de zona adicionais).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]