---
title: Devolver itens em várias ordens e faturas de clientes
description: Este tópico descreve a funcionalidade que habilita as devoluções em várias ordens e faturas de clientes no Dynamics 365 Commerce.
author: josaw1
manager: AnnBe
ms.date: 03/05/2019
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-01-15
ms.dyn365.ops.version: 10
ms.openlocfilehash: c5f17424f0837344030f9ce2d2d037cde08c4e49
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/01/2020
ms.locfileid: "3004449"
---
# <a name="return-items-across-multiple-customer-orders-and-invoices"></a>Devolver itens em várias ordens e faturas de clientes

[!include [banner](includes/banner.md)]


É possível fazer devoluções em várias ordens e faturas de clientes. 

## <a name="configure-commerce-to-support-returns-across-multiple-customer-order-and-invoices"></a>Configurar o Commerce para oferecer suporte a devoluções em várias ordens e faturas de clientes

1. Acesse **Parâmetros de comércio \> Ordens de cliente**.
1. Ative o parâmetro **Habilitar devoluções para várias ordens**. 

## <a name="process-returns"></a>Processar devoluções

Depois que o parâmetro for ativado e as alterações forem sincronizadas com as lojas, o operador de caixa da loja poderá selecionar várias ordens de venda de um cliente para sua devolução.

Quando as ordens estiverem selecionadas, uma lista de todos os produtos retornáveis em todas as faturas das ordens será exibida. O operador de caixa poderá então selecionar os produtos para devolução. Uma única ordem de devolução será criada para todos os produtos selecionados.
