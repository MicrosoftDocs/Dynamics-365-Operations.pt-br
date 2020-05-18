---
title: Enviar pedidos de outra loja usando o recurso Envio de encargos
description: Este tópico descreve o recurso de Envio de encargo.
author: ashishmsft
manager: AnnBe
ms.date: 10/10/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2017-10-10
ms.dyn365.ops.version: Retail July 2017 update
ms.openlocfilehash: 0bbebcc7b2ab89bf2f5db7294acfca1d8a5ad96e
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/01/2020
ms.locfileid: "3021573"
---
# <a name="ship-orders-from-another-store-by-using-the-charge-send-feature"></a><span data-ttu-id="8732e-103">Enviar pedidos de outra loja usando o recurso Envio de encargos</span><span class="sxs-lookup"><span data-stu-id="8732e-103">Ship orders from another store by using the Charge send feature</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="8732e-104">Com o recurso de envio de encargos do Commerce, as ordens de clientes podem ser feitas em uma loja e enviadas de outra.</span><span class="sxs-lookup"><span data-stu-id="8732e-104">With the Charge send feature in Commerce, customer orders can be placed in one store and shipped from another store.</span></span>

<span data-ttu-id="8732e-105">As ordens de clientes no cliente de PDV (ponto de venda) oferecem suporte a várias opções de atendimento.</span><span class="sxs-lookup"><span data-stu-id="8732e-105">Customer orders in the point of sale (POS) client support multiple fulfillment options.</span></span> <span data-ttu-id="8732e-106">Alguns exemplos de opções de atendimento incluem:</span><span class="sxs-lookup"><span data-stu-id="8732e-106">Some examples of fulfillment options include:</span></span>

- <span data-ttu-id="8732e-107">Separar na mesma loja em uma data diferente.</span><span class="sxs-lookup"><span data-stu-id="8732e-107">Pick up from the same store on a different date.</span></span>
- <span data-ttu-id="8732e-108">Separar em uma loja diferente na mesma data ou em uma data diferente.</span><span class="sxs-lookup"><span data-stu-id="8732e-108">Pick up from a different store on the same date or a different date.</span></span>
- <span data-ttu-id="8732e-109">Enviar do depósito de remessa padrão que está atribuído à loja e entregar em uma data específica.</span><span class="sxs-lookup"><span data-stu-id="8732e-109">Ship from the default shipping warehouse that is assigned to the store, and deliver on a specific date.</span></span>

<span data-ttu-id="8732e-110">O recurso Envio de encargos usa as seguintes operações de PDV: Remeter todos os produtos e Remeter produtos selecionados.</span><span class="sxs-lookup"><span data-stu-id="8732e-110">The Charge send feature uses the following POS operations: Ship all products and Ship selected products.</span></span> <span data-ttu-id="8732e-111">Isso permite que o funcionário da loja selecione o local "remeter de" de onde a ordem ou a linha da ordem possa ser atendida.</span><span class="sxs-lookup"><span data-stu-id="8732e-111">This allows the store clerk to select the "ship from" location that the order or order line can be fulfilled from.</span></span> <span data-ttu-id="8732e-112">Por padrão, a localização "remeter de" é o depósito de remessa que está associado à loja.</span><span class="sxs-lookup"><span data-stu-id="8732e-112">By default, the "ship from" location is the shipping warehouse that is associated with the store.</span></span> <span data-ttu-id="8732e-113">No entanto, o funcionário da loja pode alterar essa localização e selecionar qualquer loja que esteja definida no grupo localizador de loja atribuído à loja.</span><span class="sxs-lookup"><span data-stu-id="8732e-113">However, the store clerk can change this location and select any store that is defined in the store locator group that is assigned to the store.</span></span>

<span data-ttu-id="8732e-114">A capacidade de selecionar endereços "remeter para" permanece inalterada.</span><span class="sxs-lookup"><span data-stu-id="8732e-114">The ability to select "ship to" addresses remains unchanged.</span></span>

<span data-ttu-id="8732e-115">Os métodos de remessa que podem ser usados para atender à linha da ordem se baseiam na configuração de modos válidos de entrega para produtos e endereços.</span><span class="sxs-lookup"><span data-stu-id="8732e-115">The shipping methods that can be used to fulfill the order line are based on the configuration of valid modes of delivery for products and addresses.</span></span> <span data-ttu-id="8732e-116">Como as regras sobre modos de entrega válidos são mantidas somente no Headquarters (HQ), o cliente de PDV faz uma chamada em tempo real para buscar os modos de entrega válidos para uma linha de remessa.</span><span class="sxs-lookup"><span data-stu-id="8732e-116">Because the rules about valid of modes of delivery are maintained only in the Headquarters (HQ), the POS client makes a real-time call to fetch the valid modes of delivery for a ship line.</span></span>