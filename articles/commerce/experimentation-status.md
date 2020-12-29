---
title: Revisar o status de um experimento
description: Este tópico explica o status de um experimento no ciclo de vida da experimentação no Dynamics 365 Commerce.
author: sushma-rao
manager: AnnBe
ms.date: 10/21/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: sushmar
ms.search.validFrom: 2020-09-30
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: eea67ddc1718902198b74614ee1a910fc6e29c1d
ms.sourcegitcommit: cd83f2bc0e52e13071ad306e07e4c255fc65cb03
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/22/2020
ms.locfileid: "4410330"
---
# <a name="review-the-status-of-an-experiment"></a>Revisar o status de um experimento
Há várias etapas envolvidas na configuração e na execução de um experimento no Dynamics 365 Commerce. Para obter informações sobre o ciclo de vida de experimentação, consulte [Experimentação no Dynamics 365 Commerce](experimentation-overview.md).

Para saber onde um experimento está no ciclo de vida, no construtor de sites do Commerce, selecione **Experimentos** no painel de navegação esquerdo. Uma lista de experimentos é exibida com o status de cada experimento no Commerce e no serviço de terceiros que está sendo usado para habilitar a criação de experimentos, atribuir variações e analisar dados.

Na coluna **Status do Commerce**, os valores a seguir podem ser exibidos. 
- **Rascunho** - o experimento está conectado a uma página ou fragmento no Commerce e está sendo editado.
- **Publicado** - as variações do experimento estão prontas para serem exibidas no seu site. Se o experimento estiver sendo executado no serviço de terceiros, os usuários do site verão uma variação da página ou do fragmento, conforme selecionado pelo serviço de terceiros.
- **Não publicado** - o experimento não está mais disponível no seu site. Os usuários do site verão apenas a versão padrão da página ou fragmento, mesmo se o experimento estiver sendo executado no serviço de terceiros.
- **Concluído** - o experimento foi executado e uma variação foi promovida a ativa para todos os usuários do site.

Da mesma forma, na coluna **status de terceiros**, os valores a seguir podem ser exibidos para indicar que status são os experimentos no serviço de terceiros.
- **Rascunho** - o experimento é configurado no serviço de terceiros, mas ainda não foi iniciado.
- **Em execução** - o experimento foi iniciado no serviço de terceiros e está retirando dados.
- **Em pausa** - o experimento está pausado e não está retirando dados. Você deve continuar o experimento para retirar dados novamente.
- **Arquivado** - o experimento foi executado no curso e foi catalogado no serviço de terceiros para referência futura.

O diagrama a seguir mostra os dois conjuntos de status e como eles se relacionam entre si.

[ ![Status da experimentação](./media/experimentation_statuses.svg) ](./media/experimentation_statuses.svg#lightbox)
