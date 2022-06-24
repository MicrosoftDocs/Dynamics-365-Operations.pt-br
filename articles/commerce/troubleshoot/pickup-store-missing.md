---
title: A loja de varejo não aparece na lista de lojas para retirada
description: Este artigo fornece orientação de solução de problemas que pode ajudar quando uma loja de varejo não aparece na lista de lojas de onde os itens podem ser retirados.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 936b3df3194fbdacf8e853ed60431b077f4015cd
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8905247"
---
# <a name="retail-store-doesnt-appear-in-the-list-of-stores-to-pick-up-from"></a>A loja de varejo não aparece na lista de lojas para retirada

[!include [banner](../../includes/banner.md)]

Este artigo fornece orientação de solução de problemas que pode ajudar quando uma loja de varejo não aparece na lista de lojas de onde os itens podem ser retirados.

## <a name="description"></a>descrição

Uma loja de varejo não aparece na lista de lojas onde os itens podem ser retirados.

## <a name="resolution"></a>Resolução

### <a name="configure-the-longitude-and-latitude-for-the-store-address-in-commerce-headquarters"></a>Configurar longitude e latitude do endereço da loja no Commerce headquarters

Para configurar longitude e latitude do endereço da loja no Commerce headquarters, siga estas etapas.

1. Acesse **Varejo e Comércio \> Canais \> Lojas \> Todas as lojas**.
1. Localize a loja que você deseja que apareça entre as opções de retirada no site de comércio eletrônico. Anote o valor de seu **Número da unidade operacional**.
1. Acesse **Administração da organização \> Organizações \> Unidades operacionais**.
1. Procure o número da unidade operacional que você anotou anteriormente e selecione a unidade operacional nos resultados da pesquisa.
1. Na guia rápida **Endereços**, selecione **Mais opções** e, em seguida, **Avançado**.
1. Na guia rápida **Geral**, verifique se os campos **Longitude** e **Latitude** estão definidos corretamente. Como parte dessa etapa, certifique-se de que os valores estão corretamente especificados como números positivos ou negativos.

### <a name="configure-fulfillment-groups-in-commerce-headquarters"></a>Configurar grupos de atendimento no Commerce headquarters

Para configurar grupos de atendimento no Commerce headquarters, siga estas etapas:

1. Acesse **Varejo e Comércio \> Canais \> Lojas online**.
1. Selecione a loja online a ser configurada.
1. No Painel de Ação, selecione **Configurar** e, depois, **Atribuição do grupo de atendimento**.
1. Na página **Atribuição do grupo de atendimento**, selecione o grupo de atendimento da loja online.
1. Em **Configuração**, verifique se a loja de varejo está configurada corretamente para o grupo de atendimento.

## <a name="additional-resources"></a>Recursos adicionais 

[Criar uma unidade operacional](../../fin-ops-core/fin-ops/organization-administration/tasks/create-operating-unit.md)

[Configurar um canal online](../channel-setup-online.md)