---
title: Perguntas frequentes do modo de criação de cliente assíncrono
description: Este artigo fornece respostas a perguntas frequentes sobre o modo de criação de cliente assíncrono no Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 08/04/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-12-17
ms.openlocfilehash: 35c999695ed33c4fc9731a5b8dd4d679cf55fa44
ms.sourcegitcommit: e0905a3af85d8cdc24a22e0c041cb3a391c036cb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/06/2022
ms.locfileid: "9229865"
---
# <a name="asynchronous-customer-creation-mode-faq"></a>Perguntas frequentes do modo de criação de cliente assíncrono

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

Este artigo fornece respostas a perguntas frequentes sobre o modo de criação de cliente assíncrono no Microsoft Dynamics 365 Commerce.

### <a name="why-cant-i-enable-the-enable-editing-customers-in-asynchronous-mode-feature"></a>Por que não consigo ativar o recurso "Habilitar a edição de clientes no modo assíncrono"?

Para ativar o recurso **Habilitar edição de clientes no modo assíncrono**, você deve habilitar os seguintes recursos:

- Melhorias de desempenho para ordens e transações de clientes
- Habilitar criação avançada de cliente assíncrono
- Habilitar criação assíncrona para endereços de cliente

### <a name="why-do-i-still-see-real-time-service-calls-made-to-commerce-headquarters-after-the-enable-editing-customers-in-asynchronous-mode-feature-is-enabled"></a>Por que ainda vejo chamadas de serviço em tempo real feitas ao Commerce headquarters após a ativação do recurso "Habilitar edição de clientes no modo assíncrono"?

Esse problema ocorre quando os trabalhos do Commerce Data Exchange (CDX) não foram executados para garantir que o estado do recurso e outros metadados do canal sejam sincronizados com o canal. Antes de repetir o cenário, verifique se os seguintes trabalhos CDX estão sendo executados no Commerce headquarters:

- 1110 (Configuração global)
- 1010 (Clientes)
- 1070 (Configuração do canal)

Os dados armazenados em cache na Commerce Scale Unit (CSU) podem não ser logo refletidos no Commerce headquarters após a execução dos trabalhos CDX.

### <a name="why-doesnt-commerce-headquarters-show-customer-creation-or-updates-from-the-point-of-sale-pos-or-e-commerce-channel"></a>Por que o Commerce headquarters não mostra a criação ou as atualizações do cliente a partir de PDV (ponto de venda) ou canal de comércio eletrônico?

Verifique se as seguintes ações foram executadas na ordem em que estão listadas aqui.

1. Execute o job CDX P no Commerce headquarters para garantir que dados de clientes assíncronos armazenados nas tabelas **RETAILASYNCCUSTOMERV2**, **RETAILASYNCADDRESSV2**, **RETAILASYNCCUSTOMERCONTACT**, **RETAILASYNCCUSTOMERAFFILIATION** e **RETAILASYNCCUSTOMERATTRIBUTEV2** estejam disponíveis no Commerce headquarters.
1. Execute o trabalho em lotes **Sincronizar clientes e solicitações de canal** no Commerce headquarters. Após a execução com êxito do trabalho em lotes, todos os registros processados com êxito das tabelas citadas anteriormente terão o campo **OnlineOperationCompleted** definido como **1**.
