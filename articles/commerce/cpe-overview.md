---
title: Visão geral do ambiente de visualização do Commerce
description: Este tópico fornece uma visão geral do ambiente de visualização do Microsoft Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 12/10/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: v-chgri
ms.search.validFrom: 2019-12-10
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 901583afde4739be5313fa129ff0e52f11326881
ms.sourcegitcommit: 610d5c3efadbaf11752b46f24680af619bcd70a6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2019
ms.locfileid: "2906061"
---
# <a name="commerce-preview-environment-overview"></a>Visão geral do ambiente de visualização do Commerce

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Este tópico fornece uma visão geral do ambiente de visualização do Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visão geral

O ambiente de visualização do Commerce é um ambiente opcional de visualização do Dynamics 365 Commerce de ponta a ponta, que permite que os clientes potenciais experimentem o produto do Commerce antes do lançamento geral ao público.

Além de algumas limitações mínimas que não afetam os recursos ou a funcionalidade, o ambiente de visualização comercial oferece a experiência comercial completa e pode ser usado por clientes e parceiros de implementação para avaliar o produto, fornecer comentários e analisar as necessidades e a análise de lacunas.

## <a name="limitations-of-the-commerce-preview-environment"></a>Limitações do ambiente de visualização do Commerce

Embora o ambiente de visualização do Commerce forneça o conjunto completo de recursos e funcionalidades do Commerce, há algumas limitações mínimas:

- Embora o ambiente de visualização do Commerce não tenha limitações geográficas, os componentes do ambiente, como os aplicativos Retail Cloud Scale Unit (RCSU) e comércio eletrônico, podem ser provisionados somente nos Estados Unidos.
- Uso do ambiente de visualização do Commerce é limitado a 30 dias a partir da data quando o comércio eletrônico foi provisionado.
- O ambiente de visualização do Commerce pode ser implantado com êxito e inicializado somente em um ambiente que usa a topologia de demonstração, na qual todos os componentes de um ambiente são implantados em uma única máquina virtual (VM). A principal limitação dessa topologia de VM de OneBox é o número de usuários simultâneos que o ambiente de visualização pode suportar.
- O ambiente de visualização do Commerce pode ser avaliado somente até a disponibilidade geral (GA) do produto do Commerce. Novos ambientes de demonstração estarão disponíveis após GA.

## <a name="get-started"></a>Comece a usar

Para configurar o ambiente de visualização do Commerce, consulte [Provisionar um ambiente de visualização do Commerce](provisioning-guide.md).

## <a name="additional-resources"></a>Recursos adicionais

[Provisionar um ambiente de visualização do Commerce](provisioning-guide.md)

[Configurar um ambiente de visualização do Commerce](cpe-post-provisioning.md)

[Configurar recursos opcionais para um ambiente de visualização do Commerce](cpe-optional-features.md)

[Perguntas frequentes do ambiente de visualização do Commerce](cpe-faq.md)
