---
title: Configurar cenários de pagamentos de fatura
description: Este artigo descreve como configurar o Dynamics 365 Commerce para oferecer suporte a vários cenários referentes a pagamentos de fatura.
author: josaw1
ms.date: 11/14/2018
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
ms.search.validFrom: 2018-11-15
ms.dyn365.ops.version: ''
ms.openlocfilehash: 78af54fec771e5012aca095d07fd772988a56029
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8885364"
---
# <a name="set-up-pay-invoice-scenarios"></a>Configurar cenários de pagamentos de fatura

[!include [banner](includes/banner.md)]

A funcionalidade Pagar fatura no Dynamics 365 Commerce foi expandida para oferecer suporte a:

- Pagamento de várias faturas de ordens de venda em uma única transação de PDV.
- Pagamento de vários tipos de fatura de cliente, incluindo faturas de texto livre, faturas baseadas em projetos e notas de crédito.

Para habilitar esses cenários, o perfil de funcionalidade para lojas deve ser configurado conforme definido abaixo.

1. Vá para **Retail e Commerce \> Configuração de canal \> Configuração do PDV \> Perfis de PDV \> Perfis de funcionalidade** e selecione um perfil vinculado às lojas nas quais deseja fazer as alterações.
2. Na guia **Funções**, configure os parâmetros a seguir conforme necessário.

    - **Fatura de ordem de venda** – Selecione **Sim** para permitir que os usuários paguem uma ou mais faturas baseadas em ordem de venda em uma única transação de PDV.
    - **Fatura de texto livre** – Selecione **Sim** para permitir que os usuários paguem uma ou mais faturas de texto livre em uma única transação de PDV.
    - **Fatura de projeto** – Selecione **Sim** para permitir que os usuários paguem uma ou mais faturas baseadas em projeto em uma única transação de PDV.
    - **Nota de crédito de ordem de venda** – Selecione **Sim** para permitir que os usuários liquidem várias notas de crédito baseadas em ordem de venda de faturas em aberto ou processem um reembolso a um cliente de uma nota de crédito em aberto.

> [!NOTE]
> Ainda não existe suporte para o pagamento nem para a liquidação de valores parciais.


[!INCLUDE[footer-include](../includes/footer-banner.md)]