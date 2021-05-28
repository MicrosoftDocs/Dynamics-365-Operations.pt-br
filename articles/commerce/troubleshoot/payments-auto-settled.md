---
title: Os pagamentos são automaticamente liquidados antes que as ordens sejam faturadas ou remetidas
description: Este tópico fornece orientação de solução de problemas que pode ser útil quando um pagamento é liquidado no portal Adyen imediatamente após uma ordem ser feita, mesmo que a ordem de venda não tenha sido faturada nem remetida.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: b4fd37a3c45f2559c9659f072ca0b6f02e712f53
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6018251"
---
# <a name="payments-are-automatically-settled-before-orders-are-invoiced-or-shipped"></a><span data-ttu-id="61e0a-103">Os pagamentos são automaticamente liquidados antes que as ordens sejam faturadas ou remetidas</span><span class="sxs-lookup"><span data-stu-id="61e0a-103">Payments are automatically settled before orders are invoiced or shipped</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="61e0a-104">Este tópico fornece orientação de solução de problemas que pode ser útil quando um pagamento é liquidado no portal Adyen imediatamente após uma ordem ser feita, mesmo que a ordem de venda não tenha sido faturada nem remetida.</span><span class="sxs-lookup"><span data-stu-id="61e0a-104">This topic provides troubleshooting guidance that can help when a payment is settled in the Adyen portal immediately after an order is placed, even though the sales order hasn't been invoiced or shipped.</span></span>

## <a name="description"></a><span data-ttu-id="61e0a-105">descrição</span><span class="sxs-lookup"><span data-stu-id="61e0a-105">Description</span></span>

<span data-ttu-id="61e0a-106">Depois que uma ordem é colocada, o pagamento é imediatamente liquidado no portal Adyen, mesmo que a ordem de venda não tenha sido faturada nem remetida.</span><span class="sxs-lookup"><span data-stu-id="61e0a-106">After an order is placed, the payment is immediately settled in the Adyen portal, even though the sales order hasn't been invoiced or shipped.</span></span>

## <a name="resolution"></a><span data-ttu-id="61e0a-107">Resolução</span><span class="sxs-lookup"><span data-stu-id="61e0a-107">Resolution</span></span>

### <a name="configure-manual-capture-for-e-commerce-payments-in-the-adyen-portal"></a><span data-ttu-id="61e0a-108">Configurar a captura manual de pagamentos de comércio eletrônico no portal de Adyen</span><span class="sxs-lookup"><span data-stu-id="61e0a-108">Configure manual capture for e-commerce payments in the Adyen portal</span></span>

<span data-ttu-id="61e0a-109">Para configurar a captura manual de pagamentos de comércio eletrônico no portal de Adyen, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="61e0a-109">To configure manual capture for e-commerce payments in the Adyen portal, follow these steps.</span></span>

1. <span data-ttu-id="61e0a-110">Entre no portal de Adyen.</span><span class="sxs-lookup"><span data-stu-id="61e0a-110">Sign in to the Adyen portal.</span></span>
1. <span data-ttu-id="61e0a-111">No canto superior direito, selecione sua conta de comerciante para o canal de comércio eletrônico.</span><span class="sxs-lookup"><span data-stu-id="61e0a-111">In the upper-right corner, select your merchant account for the e-commerce channel.</span></span>
1. <span data-ttu-id="61e0a-112">Na barra de navegação superior, selecione **Conta** e depois **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="61e0a-112">On the top navigation, select **Account**, and then select **Settings**.</span></span>
1. <span data-ttu-id="61e0a-113">No campo **Atraso da Captura**, selecione **manual**.</span><span class="sxs-lookup"><span data-stu-id="61e0a-113">In the **Capture Delay** field, select **manual**.</span></span>

    ![Configuração do Atraso de Captura no portal de Adyen](media/adyen-capture-delay.jpg)

## <a name="additional-resources"></a><span data-ttu-id="61e0a-115">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="61e0a-115">Additional resources</span></span>

[<span data-ttu-id="61e0a-116">Captura de pagamento de Adyen</span><span class="sxs-lookup"><span data-stu-id="61e0a-116">Adyen payment capture</span></span>](https://docs.adyen.com/point-of-sale/capturing-payments)

[<span data-ttu-id="61e0a-117">Conector de Pagamento do Dynamics 365 para Adyen</span><span class="sxs-lookup"><span data-stu-id="61e0a-117">Dynamics 365 Payment Connector for Adyen</span></span>](../dev-itpro/adyen-connector.md)

[<span data-ttu-id="61e0a-118">Configurar o conector de pagamento da Adyen para Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="61e0a-118">Set up the Adyen payment connector for Dynamics 365</span></span>](https://docs.adyen.com/plugins/microsoft-dynamics)
