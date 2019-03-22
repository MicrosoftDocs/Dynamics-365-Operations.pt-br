---
title: Devolver itens em várias ordens e faturas de clientes
description: Este tópico descreve a funcionalidade que habilita as devoluções em várias ordens e faturas de clientes no Microsoft Dynamics 365 for Retail.
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
ms.openlocfilehash: c201311028b11121d626e93859a2b98497c047d1
ms.sourcegitcommit: bacec397ee48ac583596be156c87ead474ee07df
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/05/2019
ms.locfileid: "777217"
---
# <a name="return-items-across-multiple-customer-orders-and-invoices"></a>Devolver itens em várias ordens e faturas de clientes

[!include [banner](includes/banner.md)]


No Dynamics 365 for Finance and Operations versão 10.0, as devoluções podem ser feitas em várias ordens e faturas, enquanto nas versões anteriores, elas só podiam ser processadas por uma única fatura por vez. 

## <a name="configure-retail-to-support-returns-across-multiple-customer-order-and-invoices"></a>Configurar o Retail para oferecer suporte a devoluções em várias ordens e faturas de clientes

1. Acesse **Parâmetros do Retail \> Ordens de cliente**.
1. Ative o parâmetro **Habilitar devoluções para várias ordens**. 

## <a name="process-returns"></a>Processar devoluções

Depois que o parâmetro for ativado e as alterações forem sincronizadas com as lojas, o operador de caixa da loja poderá selecionar várias ordens de venda de um cliente para sua devolução.

Quando as ordens estiverem selecionadas, uma lista de todos os produtos retornáveis em todas as faturas das ordens será exibida. O operador de caixa poderá então selecionar os produtos para devolução. Uma única ordem de devolução será criada para todos os produtos selecionados.
