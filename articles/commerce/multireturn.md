---
title: Devolver itens em várias ordens e faturas de clientes
description: Este tópico descreve a funcionalidade que habilita as devoluções em várias ordens e faturas de clientes no Dynamics 365 Commerce.
author: josaw1
manager: AnnBe
ms.date: 08/27/2020
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
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
ms.openlocfilehash: ee4c863e617b9351e55e1fc652ea8905f17c8346
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5114694"
---
# <a name="return-items-across-multiple-customer-orders-and-invoices"></a>Devolver itens em várias ordens e faturas de clientes

[!include [banner](includes/banner.md)]


Este artigo descreve dois recursos que otimizam a devolução de ordens de clientes em várias faturas. 

## <a name="enable-refunds-over-multiple-captures"></a>Habilitar reembolsos em várias capturas

Este recurso permite vários reembolsos vinculados em relação à mesma ordem do cliente. 

1. Acesse o espaço de trabalho **Gerenciamento de recursos** e procure **Habilitar reembolsos em várias capturas**.
2. Selecione **Habilitar reembolsos em várias ordens** e clique em **Habilitar**. 

## <a name="enable-proper-tax-calculation-for-returns-with-partial-quantity"></a>Habilitar o cálculo de imposto apropriado para devoluções com quantidade parcial

Esse recurso garante que, quando uma ordem é devolvida com várias faturas, os impostos serão basicamente iguais ao valor do imposto cobrado originalmente. 

1. Acesse o espaço de trabalho **Gerenciamento de recursos** e procure **Habilitar o cálculo de imposto apropriado para devoluções com quantidade parcial**.
2. Selecione **Habilitar o cálculo de imposto apropriado para devoluções com quantidade parcial** e clique em **Habilitar**. 


## <a name="process-returns"></a>Processar devoluções

Depois que recursos forem ativados e as alterações forem sincronizadas com as lojas, o operador de caixa da loja poderá selecionar várias ordens de venda de um cliente para a devolução.

Quando as ordens estiverem selecionadas, uma lista de todos os produtos retornáveis em todas as faturas das ordens será exibida. O operador de caixa poderá então selecionar os produtos para devolução. Uma única ordem de devolução será criada para todos os produtos selecionados.

Se a ordem for totalmente devolvida, o valor dos impostos devolvidos ao cliente será igual ao valor do imposto cobrado originalmente.



[!INCLUDE[footer-include](../includes/footer-banner.md)]