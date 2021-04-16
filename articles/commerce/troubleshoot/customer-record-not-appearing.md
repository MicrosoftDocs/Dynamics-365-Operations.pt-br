---
title: Os registros de clientes não aparecem no Commerce Headquarters
description: Este tópico fornece orientações de solução de problemas que podem ajudar quando os registros de clientes não aparecem imediatamente no Commerce Headquarters.
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
ms.openlocfilehash: 5499e3c059c9e735df87ef8b462d446e0710d90c
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5801786"
---
# <a name="customer-records-dont-appear-in-commerce-headquarters"></a><span data-ttu-id="b6f07-103">Os registros de clientes não aparecem no Commerce Headquarters</span><span class="sxs-lookup"><span data-stu-id="b6f07-103">Customer records don't appear in Commerce headquarters</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="b6f07-104">Este tópico fornece orientações de solução de problemas que podem ajudar quando os registros de clientes não aparecem imediatamente no Commerce Headquarters.</span><span class="sxs-lookup"><span data-stu-id="b6f07-104">This topic provides troubleshooting guidance that can help when customer records don't immediately appear in Commerce headquarters.</span></span>

## <a name="description"></a><span data-ttu-id="b6f07-105">descrição</span><span class="sxs-lookup"><span data-stu-id="b6f07-105">Description</span></span>

<span data-ttu-id="b6f07-106">Quando você cria um novo registro de cliente usando o fluxo de inscrição na vitrine de comércio eletrônico, o registro do cliente correspondente não aparece imediatamente no Commerce Headquarters.</span><span class="sxs-lookup"><span data-stu-id="b6f07-106">When you create a new customer record by using the sign-up flow in the e-commerce storefront, the corresponding customer record doesn't immediately appear in Commerce headquarters.</span></span>

## <a name="resolution"></a><span data-ttu-id="b6f07-107">Resolução</span><span class="sxs-lookup"><span data-stu-id="b6f07-107">Resolution</span></span>

### <a name="disable-customer-creation-in-async-mode"></a><span data-ttu-id="b6f07-108">Desabilitar a criação de clientes no modo assíncrono</span><span class="sxs-lookup"><span data-stu-id="b6f07-108">Disable customer creation in async mode</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b6f07-109">Se você desabilitar a criação assíncrona de clientes, o desempenho do sistema poderá ser afetado, pois a criação de cada registro produzirá uma solicitação em tempo real para o Commerce Headquarters.</span><span class="sxs-lookup"><span data-stu-id="b6f07-109">If you disable asynchronous customer creation, system performance could be affected, because creation of each record will produce a real-time request to Commerce headquarters.</span></span> <span data-ttu-id="b6f07-110">Além disso, se o Commerce Headquarters estiver inoperante (por exemplo, durante os fluxos de serviço), todos os novos fluxos de criação de clientes produzirão erros.</span><span class="sxs-lookup"><span data-stu-id="b6f07-110">In addition, if Commerce headquarters is down (for example, during servicing flows), any new customer creation flows will produce errors.</span></span>

<span data-ttu-id="b6f07-111">Para desabilitar a criação de clientes no modo assíncrono no Commerce Headquarters, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="b6f07-111">To disable customer creation in async mode in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="b6f07-112">Vá para **Varejo e Comércio \> Configuração de canal \> Configuração da loja online \> Perfis de funcionalidade**.</span><span class="sxs-lookup"><span data-stu-id="b6f07-112">Go to **Retail and Commerce \> Channel setup \> Online store setup \> Functionality profiles**.</span></span>
1. <span data-ttu-id="b6f07-113">Se ainda não estiver usando um perfil de funcionalidade para seu canal online, crie um.</span><span class="sxs-lookup"><span data-stu-id="b6f07-113">If you aren't already using a functionality profile for your online channel, create one.</span></span>
1. <span data-ttu-id="b6f07-114">Verifique se a opção **Criar cliente no modo assíncrono** foi definida como **Não**.</span><span class="sxs-lookup"><span data-stu-id="b6f07-114">Make sure that the **Create customer in async mode** option is set to **No**.</span></span>
1. <span data-ttu-id="b6f07-115">Acesse **Varejo e Comércio \> Canais \> Lojas online**.</span><span class="sxs-lookup"><span data-stu-id="b6f07-115">Go to **Retail and Commerce \> Channels \> Online stores**.</span></span>
1. <span data-ttu-id="b6f07-116">Selecione a loja online para desabilitar a criação assíncrona de clientes.</span><span class="sxs-lookup"><span data-stu-id="b6f07-116">Select the online store to disable asynchronous customer creation for.</span></span>
1. <span data-ttu-id="b6f07-117">Na guia **Geral**, verifique se o campo **Perfil de funcionalidade** foi definido como o perfil de funcionalidade que você está usando para seu canal online.</span><span class="sxs-lookup"><span data-stu-id="b6f07-117">On the **General** tab, make sure that the **Functionality profile** field is set to the functionality profile that you're using for your online channel.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b6f07-118">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="b6f07-118">Additional resources</span></span>

[<span data-ttu-id="b6f07-119">Configurar um locatário de B2C no Commerce</span><span class="sxs-lookup"><span data-stu-id="b6f07-119">Setup a B2C tenant in Commerce</span></span>](../set-up-b2c-tenant.md)
