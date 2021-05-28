---
title: Erro de sincronização da ordem relacionado ao serviço de pagamento padrão
description: Este tópico fornece orientações de solução de problemas que podem ajudar a corrigir um erro que pode ocorrer quando uma ordem online é sincronizada.
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
ms.openlocfilehash: fa174bbb257379f6ce906dd21180bbcb19f8bc3f
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6021118"
---
# <a name="order-synchronization-error-related-to-the-default-payment-service"></a><span data-ttu-id="4a482-103">Erro de sincronização da ordem relacionado ao serviço de pagamento padrão</span><span class="sxs-lookup"><span data-stu-id="4a482-103">Order synchronization error related to the default payment service</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="4a482-104">Este tópico fornece orientações de solução de problemas que podem ajudar a corrigir um erro que pode ocorrer quando uma ordem online é sincronizada.</span><span class="sxs-lookup"><span data-stu-id="4a482-104">This topic provides troubleshooting guidance that can help fix an error that might occur when an online order is synced.</span></span>

## <a name="description"></a><span data-ttu-id="4a482-105">descrição</span><span class="sxs-lookup"><span data-stu-id="4a482-105">Description</span></span>

<span data-ttu-id="4a482-106">Ao sincronizar uma ordem online, você recebe a seguinte mensagem de erro: "deve haver um serviço de pagamento padrão para processar transações de cartão de crédito".</span><span class="sxs-lookup"><span data-stu-id="4a482-106">When you sync an online order, you receive the following error message: "There must be a default payment service to process credit card transactions."</span></span>

![Erro de serviço de pagamento padrão ausente](media/default-payment-method-error.jpg)

## <a name="resolution"></a><span data-ttu-id="4a482-108">Resolução</span><span class="sxs-lookup"><span data-stu-id="4a482-108">Resolution</span></span>

### <a name="confirm-or-set-the-default-payment-service-in-commerce-headquarters"></a><span data-ttu-id="4a482-109">Confirmar ou definir o serviço de pagamento padrão na matriz do Commerce</span><span class="sxs-lookup"><span data-stu-id="4a482-109">Confirm or set the default payment service in Commerce headquarters</span></span>

<span data-ttu-id="4a482-110">Para confirmar ou definir o serviço de pagamento padrão na matriz do Commerce, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="4a482-110">To confirm or set the default payment service in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="4a482-111">Vá para **Contas a receber \> Configuração de pagamento \> Serviços de pagamento**.</span><span class="sxs-lookup"><span data-stu-id="4a482-111">Go to **Accounts receivable \> Payment setup \> Payment services**.</span></span>
1. <span data-ttu-id="4a482-112">Verifique se a opção **Processador padrão para novos cartões de crédito** está definida como **Sim** para um serviço de pagamento.</span><span class="sxs-lookup"><span data-stu-id="4a482-112">Make sure that the **Default processor for new credit cards** option is set to **Yes** for one payment service.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="4a482-113">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="4a482-113">Additional resources</span></span>

[<span data-ttu-id="4a482-114">Configuração, autorização e captura de cartão de crédito</span><span class="sxs-lookup"><span data-stu-id="4a482-114">Credit card setup, authorization, and capture</span></span>](../../finance/accounts-receivable/credit-card-authorizations.md)