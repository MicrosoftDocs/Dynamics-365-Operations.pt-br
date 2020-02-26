---
title: Funcionalidade de vendas do call center
description: Este tópico mostra uma visão geral da funcionalidade de vendas do call center no Dynamics 365 Commerce.
author: josaw1
manager: AnnBe
ms.date: 04/03/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailMCRChannelDetailPage, MCROrderParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 16361
ms.assetid: c8ed2ba4-8d06-4d99-9728-2a83e6d95ca9
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 816bfc8b93f52fe91192874bcc1c8e605e41b582
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/01/2020
ms.locfileid: "3021577"
---
# <a name="call-center-sales-functionality"></a>Funcionalidade de vendas do call center

[!include [banner](includes/banner.md)]


No Dynamics 365 Commerce, call center é um tipo de canal que pode ser definido no aplicativo. Definir um canal específico das entidades de call center permite que o sistema una padrões de dados específicos e padrões de processamento de ordem para ordens de vendas criadas por um usuário do canal do call center.

Os recursos de call center incluem preço avançado e promoções, catálogos, cartões-presente, programas de fidelidade e cupons. Ordens de call center são aproveitadas também por uma aplicação de ponto de venda (PDV) para oferecer suporte a cenários de preenchimento de ordem entre canal.

É importante observar que, quando o módulo de call center pode ser utilizado por outros setores fora do comércio, a versão atual do aplicativo de call center não foi otimizada para uso em cenários de processamento de ordens B2B (entre empresas) ou em cenários onde as ordens têm muitas linhas de venda. Recomenda-se que os usuários que desejam utilizar os recursos do call center para processamento de ordem fora de um processamento de transação direto ao consumidor típico, levem o tempo adequado para testar e validar essa funcionalidade de call center para estar compatível com as necessidades funcional e de desempenho.

Além da criação da ordem de atendimento, o módulo de call center também fornece um aplicativo de serviço ao cliente amigável que facilita para que os usuários encontrem contas de cliente e examina todos os dados relacionados e atributos da ordem de cliente. A tela de serviço do cliente é projetada para habilitar um usuário a acessar rapidamente os dados da ordem relacionada que permitirão que eles respondam às questões relacionadas a ordem mais comuns recebidas dos clientes.

Esta página fornece links para documentação relevante relacionada à instalação, à configuração e ao uso funcional dos recursos de call center.


## <a name="configure-the-call-center"></a>Configurar o call center

[Configurar canais de call center](set-up-order-processing-options.md)

## <a name="configure-order-processing"></a>Configurar processamento de ordem

[Configurar e trabalhar com alertas de fraude de call center](set-up-fraud-alerts.md)

[Configurar e trabalhar com bloqueios de ordem do call center](work-with-order-holds.md)

## <a name="configure-payment-processing"></a>Configurar processamento de pagamento

[Meios de pagamento nos call centers](work-with-payments.md)

## <a name="configure-delivery-modes"></a>Configurar modos de entrega

[Configurar modos de entrega e encargos do call center](configure-call-center-delivery.md)

## <a name="configure-direct-marketing"></a>Configurar marketing direto

[Catálogos do call center](call-center-catalogs.md)

[Configurar análise de Recency, frequência e valor monetário (RFM)](set-up-rfm-analysis.md)

## <a name="configure-continuity-programs"></a>Configurar programas de continuidade

[Configurar programas de continuidade para call centers](set-up-continuity-program.md)
