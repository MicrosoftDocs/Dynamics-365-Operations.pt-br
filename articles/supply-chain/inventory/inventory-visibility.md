---
title: Visão geral do Suplemento Visibilidade de Estoque
description: Este tópico explica o que é Visibilidade de Estoque e descreve seus recursos.
author: sherry-zheng
ms.date: 10/26/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-10-26
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: 644eb0d682c35bd604c188aa02e4a6c69b3ff209
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7474979"
---
# <a name="inventory-visibility-add-in-overview"></a>Visão geral do Suplemento Visibilidade de Estoque

[!include [banner](../includes/banner.md)]

O Suplemento Visibilidade de Estoque (também conhecido como *Visibilidade de Estoque*) é um microsserviço independente e altamente escalonável que permite o acompanhamento de estoque disponível em tempo real. Portanto, ele fornece uma visão global do estoque.

Os sistemas externos acessam o serviço por meio de APIs RESTful. Assim, podem consultar informações disponíveis sobre determinados conjuntos de dimensões ou fazer alterações em seu estoque em diferentes fontes de dados personalizadas.

Como um microsserviço fundamentado no Microsoft Dataverse, o Visibilidade de Estoque fornece extensibilidade. Você pode usar o Power Apps para criar aplicativos. Você também pode aplicar o Power BI para fornecer funcionalidade personalizada que atenda a seus requisitos de negócios.

Você pode integrar o Visibilidade de Estoque com vários sistemas de terceiros, definindo opções de configuração para dimensões de estoque padronizadas e configurando tipos de transação. O Visibilidade de Estoque também dá suporte à extensibilidade personalizada por meio de quantidades calculadas configuráveis.

## <a name="inventory-visibility-integration-with-dynamics-365-supply-chain-management"></a>Integração do Visibilidade de Estoque com o Dynamics 365 Supply Chain Management

A solução integrada extrai dados de estoque do Dynamics 365 Supply Chain Management e acompanha continuamente as alterações de estoque. Para obter mais informações, consulte [Instalar e configurar Visibilidade do Estoque](inventory-visibility-setup.md) e [Configurar Visibilidade do Estoque](inventory-visibility-configuration.md).

## <a name="get-a-global-view-of-inventory"></a>Obter uma exibição global do estoque

A solução integrada permite definir suas próprias fontes de dados e centralizar os dados de estoque. Para obter mais informações, consulte [Configurar Visibilidade de Estoque](inventory-visibility-configuration.md).

Existem duas abordagens para exibir seu estoque:

- Enviar uma consulta por meio da API de alto desempenho. Essa API pode retornar dados de estoque quase em tempo real diretamente de uma instância em cache. Você pode encontrar contratos e exemplos em [APIs públicas de Visibilidade de Estoque](inventory-visibility-api.md).
- Exibir a lista bruta disponível. Essa lista é sincronizada periodicamente de uma instância em cache e é visível no Dataverse. Para obter mais informações, consulte [Aplicativo Visibilidade de Estoque](inventory-visibility-power-platform.md).

## <a name="soft-reservations"></a>Reservas flexíveis

[!INCLUDE [preview-banner-section](../../includes/preview-banner-section.md)]

A reserva flexível é aplicada quando uma empresa deve reservar uma quantidade específica de produtos para dar suporte, por exemplo, ao atendimento de ordens de venda de modo a evitar vendas excessivas. Quando uma ordem de venda é criada e confirmada no Supply Chain Management ou em outros sistemas de gerenciamento de ordens, uma solicitação para reservar a quantidade é enviada ao Visibilidade de Estoque. O Visibilidade de Estoque permite que você reserve produtos com detalhes de dimensão e tipos de transação de estoque específicos. (Para obter mais informações, consulte [Aplicativo Visibilidade de Estoque](inventory-visibility-power-platform.md).) Depois que a quantidade for reservada com êxito, uma ID de reserva será retornada. Você pode usar essa ID de reserva para vincular de volta ao solicitação original no Supply Chain Management ou outros sistemas de gerenciamento de ordens.

A funcionalidade é projetada para que uma reserva no Visibilidade de Estoque não altere a quantidade total. Em vez disso, ele sinaliza apenas a quantidade reservada. (Por esse motivo, é chamado de *reserva flexível*.) A quantidade reserva flexível pode ser compensada quando os produtos são consumidos no Supply Chain Management ou em um sistema de terceiros, chamando a API novamente para fazer uma dedução de quantidade e atualizar a quantidade total no Visibilidade de Estoque. Para obter mais informações, consulte [Reservas de Visibilidade de Estoque](inventory-visibility-reservations.md).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
