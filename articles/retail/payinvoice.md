---
title: "Configurar cenários de fatura de pagamento"
description: "Este tópico descreve como configurar o Dynamics 365 for Retail para dar suporte a vários cenários relativos a pagamentos de fatura."
author: josaw1
manager: AnnBe
ms.date: 11/14/2018
ms.topic: index-page
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2018-11-15
ms.dyn365.ops.version: 
ms.translationtype: HT
ms.sourcegitcommit: 190d0b59ad2e232b33b3c0d1700cbaf95c45aeca
ms.openlocfilehash: b7132dc9b3c78fa04fcfc38ea72b5678ad08deb2
ms.contentlocale: pt-br
ms.lasthandoff: 01/04/2019

---
# <a name="set-up-pay-invoice-scenarios"></a>Configurar cenários de fatura de pagamento

[!include [banner](includes/banner.md)]

A funcionalidade Pagar fatura no Dynamics 365 for Retail foi expandida para dar suporte a:

- Pagamento de várias faturas de ordens de venda em uma única transação de PDV.
- Pagamento de vários tipos de fatura de cliente, incluindo faturas de texto livre, faturas baseadas em projetos e notas de crédito.

Para habilitar esses cenários, o perfil de funcionalidade para lojas deve ser configurado conforme definido abaixo.

1. Vá para **Varejo \> Configuração de canal \> Configuração do PDV \> Perfis de PDV \> Perfis de funcionalidade** e selecione um perfil vinculado às lojas nas quais deseja fazer as alterações.
2. Na guia **Funções**, configure os parâmetros a seguir conforme necessário.

    - **Fatura de ordem de venda** – Selecione **Sim** para permitir que os usuários paguem uma ou mais faturas baseadas em ordem de venda em uma única transação de PDV.
    - **Fatura de texto livre** – Selecione **Sim** para permitir que os usuários paguem uma ou mais faturas de texto livre em uma única transação de PDV.
    - **Fatura de projeto** – Selecione **Sim** para permitir que os usuários paguem uma ou mais faturas baseadas em projeto em uma única transação de PDV.
    - **Nota de crédito de ordem de venda** – Selecione **Sim** para permitir que os usuários liquidem várias notas de crédito baseadas em ordem de venda de faturas em aberto ou processem um reembolso a um cliente de uma nota de crédito em aberto.

> [!NOTE]
> Ainda não existe suporte para o pagamento nem para a liquidação de valores parciais.

