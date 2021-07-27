---
title: Devolver itens em várias ordens e faturas de clientes
description: Este tópico descreve a funcionalidade que habilita as devoluções em várias ordens e faturas de clientes no Dynamics 365 Commerce.
author: josaw1
ms.date: 08/27/2020
ms.topic: index-page
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-01-15
ms.dyn365.ops.version: 10
ms.openlocfilehash: c36fe4c8376ad0364516c0268965c798e20436c6
ms.sourcegitcommit: 3a9599e9b9458434c0e44d295eabd2304c5650be
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2021
ms.locfileid: "6334416"
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
