---
title: Configurar cenários de pagamentos de fatura
description: Este tópico descreve como configurar o Dynamics 365 for Retail para oferecer suporte a vários cenários referentes a pagamentos de fatura.
author: josaw1
manager: AnnBe
ms.date: 11/14/2018
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
ms.search.validFrom: 2018-11-15
ms.dyn365.ops.version: ''
ms.openlocfilehash: b7132dc9b3c78fa04fcfc38ea72b5678ad08deb2
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "301911"
---
# <a name="set-up-pay-invoice-scenarios"></a><span data-ttu-id="33347-103">Configurar cenários de pagamentos de fatura</span><span class="sxs-lookup"><span data-stu-id="33347-103">Set up pay invoice scenarios</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="33347-104">A funcionalidade Pagar fatura no Dynamics 365 for Retail foi expandida para oferecer suporte a:</span><span class="sxs-lookup"><span data-stu-id="33347-104">The Pay invoice functionality in Dynamics 365 for Retail has been expanded to support:</span></span>

- <span data-ttu-id="33347-105">Pagamento de várias faturas de ordens de venda em uma única transação de PDV.</span><span class="sxs-lookup"><span data-stu-id="33347-105">Payoff of multiple sales order invoices in a single POS transaction.</span></span>
- <span data-ttu-id="33347-106">Pagamento de vários tipos de fatura de cliente, incluindo faturas de texto livre, faturas baseadas em projetos e notas de crédito.</span><span class="sxs-lookup"><span data-stu-id="33347-106">Payment of various customer invoice types including free text invoices, project-based invoices, and credit notes.</span></span>

<span data-ttu-id="33347-107">Para habilitar esses cenários, o perfil de funcionalidade para lojas deve ser configurado conforme definido abaixo.</span><span class="sxs-lookup"><span data-stu-id="33347-107">To enable these scenarios, the functionality profile for stores must be configured as outlined in below.</span></span>

1. <span data-ttu-id="33347-108">Vá para **Varejo \> Configuração de canal \> Configuração do PDV \> Perfis de PDV \> Perfis de funcionalidade** e selecione um perfil vinculado às lojas nas quais deseja fazer as alterações.</span><span class="sxs-lookup"><span data-stu-id="33347-108">Go to **Retail \> Channel setup \> POS setup \> POS profiles \> Functionality profiles** and select a profile that's linked to the stores that you want to make the changes for.</span></span>
2. <span data-ttu-id="33347-109">Na guia **Funções**, configure os parâmetros a seguir conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="33347-109">On the **Functions** tab, configure the following parameters as needed.</span></span>

    - <span data-ttu-id="33347-110">**Fatura de ordem de venda** – Selecione **Sim** para permitir que os usuários paguem uma ou mais faturas baseadas em ordem de venda em uma única transação de PDV.</span><span class="sxs-lookup"><span data-stu-id="33347-110">**Sales order invoice** – Select **Yes** to allow users to pay one or more sales order-based invoices in a single POS transaction.</span></span>
    - <span data-ttu-id="33347-111">**Fatura de texto livre** – Selecione **Sim** para permitir que os usuários paguem uma ou mais faturas de texto livre em uma única transação de PDV.</span><span class="sxs-lookup"><span data-stu-id="33347-111">**Free text invoice** – Select **Yes** to allow users to pay one or more free text-based invoices in a single POS transaction.</span></span>
    - <span data-ttu-id="33347-112">**Fatura de projeto** – Selecione **Sim** para permitir que os usuários paguem uma ou mais faturas baseadas em projeto em uma única transação de PDV.</span><span class="sxs-lookup"><span data-stu-id="33347-112">**Project invoice** – Select **Yes** to allow users to pay one or more project-based invoices in a single POS transaction.</span></span>
    - <span data-ttu-id="33347-113">**Nota de crédito de ordem de venda** – Selecione **Sim** para permitir que os usuários liquidem várias notas de crédito baseadas em ordem de venda de faturas em aberto ou processem um reembolso a um cliente de uma nota de crédito em aberto.</span><span class="sxs-lookup"><span data-stu-id="33347-113">**Sales order credit note** – Select **Yes** to allow users to settle multiple sales order-based credit notes against open invoices or process a refund to the customer for an open credit note.</span></span>

> [!NOTE]
> <span data-ttu-id="33347-114">Ainda não existe suporte para o pagamento nem para a liquidação de valores parciais.</span><span class="sxs-lookup"><span data-stu-id="33347-114">Payment or settlement of partial amounts is not yet supported.</span></span>
