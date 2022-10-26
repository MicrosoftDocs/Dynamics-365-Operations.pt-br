---
title: Parâmetros de chat proativo do módulo de chat do Commerce
description: Este artigo descreve os parâmetros de chat proativo dos módulos de chat do Commerce no Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 10/18/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2022-07-20
ms.openlocfilehash: f3cff89a25ff84414e7fdd32cbb26404c2080187
ms.sourcegitcommit: 40c80a617b903c2b26e44b41147e0021c5cb680d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2022
ms.locfileid: "9691043"
---
# <a name="commerce-chat-module-proactive-chat-parameters"></a>Parâmetros de chat proativo do módulo de chat do Commerce

[!include [banner](includes/banner.md)]

Este artigo descreve os parâmetros de chat proativo dos módulos do Chat do Commerce com Omnicanal para Customer Service e do Chat do Commerce com chat do Power Virtual Agents no Microsoft Dynamics 365 Commerce.

## <a name="proactive-chat-properties"></a>Propriedades do chat proativo

As propriedades do chat proativo estão localizadas no painel de propriedades dos módulos do Chat do Commerce com Omnicanal para Customer Service e Chat do Commerce com Power Virtual Agents no construtor de sites do Commerce.

> [!NOTE]
> Por padrão, todas as propriedades de chat proativo listadas aqui estão em branco. Recomendamos que você saiba mais sobre essas propriedades e as defina somente quando elas forem necessárias. Essa abordagem ajudará a reduzir o disparo de chats proativos errados.

### <a name="proactive-chat"></a>Chat Proativo

| Nome amigável | Descrição | Valor padrão |
|---------------|-------------|---------------|
| Habilitados | Envolver proativamente os clientes com base em diferentes gatilhos. | Desabilitado |
| Mensagem de chat | A mensagem de saudação que é usada quando um chat proativo foi disparado. | Em Branco |

### <a name="wait-time-proactive-chat"></a>Tempo de Espera (Chat Proativo)

| Nome amigável | Descrição |
|---------------|-------------|
| Tempo de espera (segundos) | O tempo (em segundos) que os usuários do site gastam em uma página de site antes que um chat proativo seja disparado. |
| Mensagem de chat | A mensagem de saudação que é usada quando um chat proativo foi disparado. |

### <a name="number-of-page-visits-proactive-chat"></a>Número de Visitas à Página (Chat Proativo)

| Nome amigável | Descrição |
|---------------|-------------|
| Número de visitas à página | O número de visitas à página antes do chat proativo ser disparado. Os usuários do site devem primeiro aceitar o aviso na faixa de consentimento por cookie. |
| Mensagem de chat | A mensagem de saudação que é usada quando um chat proativo foi disparado. |

### <a name="specific-pages-proactive-chat"></a>Páginas Específicas (Chat Proativo)

| Nome amigável | Descrição |
|---------------|-------------|
| Página(s) | Uma lista das páginas que irão disparar um chat proativo quando forem visitadas. |
| Mensagem de chat | A mensagem de saudação que é usada quando um chat proativo foi disparado. |

### <a name="from-specific-pages-proactive-chat"></a>De Páginas Específicas (Chat Proativo)

| Nome amigável | Descrição |
|---------------|-------------|
| Página(s) | Uma lista das páginas que irão disparar um chat proativo quando os usuários saírem delas. |
| Mensagem de chat | A mensagem de saudação que é usada quando um chat proativo foi disparado. |

### <a name="specific-countryregion-proactive-chat"></a>País/Região Específicos (Chat Proativo)

| Nome amigável | Descrição |
|---------------|-------------|
| Código do país/região | Os usuários que visitarem de países ou regiões especificados irão disparar um chat proativo. Os códigos de país/região devem ter duas letras maiúsculas (por exemplo, **BR**). |
| Mensagem de chat | A mensagem de saudação que é usada quando um chat proativo foi disparado. |

### <a name="date-range-proactive-chat"></a>Intervalo de Datas (Chat Proativo)

| Nome amigável | Descrição |
|---------------|-------------|
| Data Inicial (dd/mm/aaaa) | A data em ou após a qual um chat proativo será disparado. |
| Data Final (dd/mm/aaaa) | A data em ou anterior a qual um chat proativo será disparado. |
| Mensagem de chat | A mensagem de saudação que é usada quando um chat proativo foi disparado. |

### <a name="total-amount-in-cart-proactive-chat"></a>Valor Total no Carrinho (Chat Proativo)

| Nome amigável | Descrição |
|---------------|-------------|
| Mínimo | O valor monetário mínimo (inclusivo) no carrinho de compras que irá disparar um chat proativo quando os usuários visitarem a página do carrinho. |
| Máximo | O valor monetário máximo (inclusivo) no carrinho de compras que irá disparar um chat proativo quando os usuários visitarem a página do carrinho. |
|Mensagem de chat | A mensagem de saudação que é usada quando um chat proativo foi disparado. |

### <a name="total-number-of-items-in-cart-proactive-chat"></a>Número Total de Itens no Carrinho (Chat Proativo)

| Nome amigável | Descrição |
|---------------|-------------|
| Mínimo | O número mínimo de itens (inclusivo) no carrinho de compras que irá disparar um chat proativo quando os usuários visitarem a página do carrinho. |
| Máximo | O número máximo de itens (inclusivo) no carrinho de compras que irá disparar um chat proativo quando os usuários visitarem a página do carrinho. |
| Mensagem de chat | A mensagem de saudação que é usada quando um chat proativo foi disparado. |

### <a name="specific-products-in-cart-proactive-chat"></a>Produtos Específicos no Carrinho (Chat Proativo)

| Nome amigável | Descrição |
|---------------|-------------|
| ID/SKU dos Produtos | Uma lista de números de IDs de produtos/SKU (unidade de manutenção de estoque) que disparam um chat proativo quando os usuários visitarem a página do carrinho. |
| Mensagem de chat | A mensagem de saudação que é usada quando um chat proativo foi disparado. |

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral dos recursos do chat comercial](commerce-chat-overview.md)

[Módulo Chat do Commerce com Omnicanal para Customer Service](commerce-chat-module.md)

[Chat do Commerce com o módulo do Power Virtual Agents](chat-module-pva.md)
