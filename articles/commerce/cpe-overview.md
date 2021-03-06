---
title: Visão geral do ambiente de avaliação do Dynamics 365 Commerce
description: Este tópico fornece uma visão geral do ambiente de avaliação do Microsoft Dynamics 365 Commerce.
author: v-chgri
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2019-12-10
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: c890d7c49b6607ab0cbad536bbf8a3649465a7c1
ms.sourcegitcommit: 74e47075eab2b0b28f82b0d57f439719847ecb01
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/07/2021
ms.locfileid: "6193483"
---
# <a name="dynamics-365-commerce-evaluation-environment-overview"></a>Visão geral do ambiente de avaliação do Dynamics 365 Commerce

[!include [banner](includes/banner.md)]

Este tópico fornece uma visão geral do ambiente de avaliação do Microsoft Dynamics 365 Commerce.

> [!NOTE]
> Os ambientes de avaliação do Commerce não estão disponíveis para o público geral e são concedidos a parceiros e clientes por solicitação. Para obter mais informações, fale com o contato do seu parceiro Microsoft.

O ambiente de avaliação do Commerce é um ambiente opcional de ponta a ponta do Dynamics 365 Commerce, que permite aos parceiros e clientes potenciais experimentar o produto do Commerce.

Os ambientes de avaliação são parcialmente pré-configurados para reduzir as etapas necessárias de pós-provisionamento.

Com exceção de algumas limitações mínimas que não afetam os recursos ou a funcionalidade, o ambiente de avaliação do Commerce oferece a experiência completa do Commerce e pode ser usado por clientes e parceiros de implementação para avaliar o produto, fornecer comentários e realizar análise de lacuna/ajuste.

## <a name="limitations-of-the-commerce-evaluation-environment"></a>Limitações do ambiente de avaliação do Commerce

Embora o ambiente de avaliação do Commerce forneça o conjunto completo de recursos e funcionalidades do Commerce, há algumas limitações mínimas:

- Embora o ambiente de avaliação do Commerce não tenha limitações geográficas, os componentes do ambiente, como os aplicativos Retail Cloud Scale Unit (RCSU) e e-Commerce, devem ser provisionados somente nos Estados Unidos.
- O uso do ambiente de avaliação do Commerce é limitado a 30 dias a partir da data em que o e-Commerce foi provisionado.
- O ambiente de avaliação do Commerce pode ser implantado e inicializado com êxito somente em um ambiente que use a topologia de demonstração, na qual todos os componentes de um ambiente são implantados em uma única máquina virtual (VM) hospedada na nuvem. A principal limitação dessa topologia é o número de usuários simultâneos aos quais o ambiente pode oferecer suporte.

## <a name="get-started"></a>Iniciado

Para provisionar o ambiente de avaliação do Commerce, consulte [Provisionar um ambiente de avaliação do Commerce](provisioning-guide.md).

## <a name="additional-resources"></a>Recursos adicionais

[Provisionar um ambiente de avaliação do Dynamics 365 Commerce](provisioning-guide.md)

[Configurar um ambiente de avaliação do Dynamics 365 Commerce](cpe-post-provisioning.md)

[Configurar BOPIS em um ambiente de avaliação do Dynamics 365 Commerce](cpe-bopis.md)

[Configurar recursos opcionais para um ambiente de avaliação do Dynamics 365 Commerce](cpe-optional-features.md)

[Perguntas frequentes sobre o ambiente de avaliação do Dynamics 365 Commerce](cpe-faq.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
