---
title: A página de entrada de cartão de crédito mostra um erro na finalização da compra
description: Este tópico fornece orientações de solução de problemas que podem ajudar quando a seção do método de pagamento não está carregada e mostra uma mensagem de erro.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.service: dynamics-365-retail
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
ms.openlocfilehash: d2c5f01d17df79c9b23fd513aaeb5c0605d657e9
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5801762"
---
# <a name="credit-card-entry-page-shows-an-error-at-checkout"></a><span data-ttu-id="3bac9-103">A página de entrada de cartão de crédito mostra um erro na finalização da compra</span><span class="sxs-lookup"><span data-stu-id="3bac9-103">Credit card entry page shows an error at checkout</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="3bac9-104">Este tópico fornece orientações de solução de problemas que podem ajudar quando a seção **Método de pagamento** não está carregada e mostra uma mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="3bac9-104">This topic provides troubleshooting guidance that can help when the **Payment method** section isn't loaded and shows an error message.</span></span>

## <a name="description"></a><span data-ttu-id="3bac9-105">descrição</span><span class="sxs-lookup"><span data-stu-id="3bac9-105">Description</span></span>

<span data-ttu-id="3bac9-106">Quando você abre a página de finalização da compra de uma loja online, a seção **Método de pagamento** não é carregada e a seguinte mensagem de erro é exibida: "Algo deu errado.</span><span class="sxs-lookup"><span data-stu-id="3bac9-106">When you open the checkout page of an online store, the **Payment method** section isn't loaded, and the following error message is shown: "Something went wrong.</span></span> <span data-ttu-id="3bac9-107">Tente novamente mais tarde."</span><span class="sxs-lookup"><span data-stu-id="3bac9-107">Please try again later."</span></span>

![Erro do módulo de pagamento](media/payment-module-error.jpg)

## <a name="resolution"></a><span data-ttu-id="3bac9-109">Resolução</span><span class="sxs-lookup"><span data-stu-id="3bac9-109">Resolution</span></span>

### <a name="wait-for-the-commerce-scale-unit-cache-to-expire"></a><span data-ttu-id="3bac9-110">Aguarde o cache do Commerce Scale Unit expirar</span><span class="sxs-lookup"><span data-stu-id="3bac9-110">Wait for the Commerce Scale Unit cache to expire</span></span>

<span data-ttu-id="3bac9-111">As configurações de serviço de pagamento na página de finalização da compra da loja online são armazenadas em cache na Commerce Scale Unit e podem levar até 15 minutos para serem exibidas no site de comércio eletrônico.</span><span class="sxs-lookup"><span data-stu-id="3bac9-111">The payment service settings on the online store's checkout page are cached on the Commerce Scale Unit and can take up to 15 minutes to appear on the e-commerce site.</span></span> <span data-ttu-id="3bac9-112">Essas configurações de serviço de pagamento incluem alterações na ID da conta de comerciante, chave de API de nuvem e várias definições de configuração relacionadas ao método de pagamento.</span><span class="sxs-lookup"><span data-stu-id="3bac9-112">These payment service settings include changes to the merchant account ID, cloud API key, and various configuration settings that are related to the payment method.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="3bac9-113">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="3bac9-113">Additional resources</span></span>

[<span data-ttu-id="3bac9-114">Configurar um canal online</span><span class="sxs-lookup"><span data-stu-id="3bac9-114">Set up an online channel</span></span>](../channel-setup-online.md)