---
title: Status de gerenciamento de transporte
description: Este tópico explica como criar um status de transporte e mapear esse status para um status de transportadora.
author: Henrikan
manager: tfehr
ms.date: 10/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2020-09-08
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 3f7d471771ec2b4703d878fbf395cd90902b6669
ms.sourcegitcommit: fe7ac653efcb1ac6318083f482394b96ed82b4c7
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/29/2020
ms.locfileid: "4422646"
---
# <a name="transportation-management-statuses"></a><span data-ttu-id="fb8ec-103">Status de gerenciamento de transporte</span><span class="sxs-lookup"><span data-stu-id="fb8ec-103">Transportation management statuses</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="fb8ec-104">Configure códigos mestre para status de transporte para interpretar códigos fornecidos por suas transportadoras.</span><span class="sxs-lookup"><span data-stu-id="fb8ec-104">Set up master codes for transportation statuses to interpret codes that are provided by your shipping carriers.</span></span> <span data-ttu-id="fb8ec-105">Isso permite a integração com transportadoras para fornecer um status.</span><span class="sxs-lookup"><span data-stu-id="fb8ec-105">This lets you integrate with shipping carriers to provide a status.</span></span> <span data-ttu-id="fb8ec-106">O status de transporte que você fornece para um código de status mestre de transporte pode ajudar você a rastrear o status de uma carga, remessa ou contêiner.</span><span class="sxs-lookup"><span data-stu-id="fb8ec-106">The transportation status that you provide for a transportation master status code can help you track the status of a load, shipment, or container.</span></span> <span data-ttu-id="fb8ec-107">O status de transporte específico para uma carga, remessa ou contêiner só pode ser atualizado por meio da integração de dados e não manualmente por meio da interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="fb8ec-107">The specific transportation status for a load, shipment, or container can only be updated through data integration and not manually through the user interface.</span></span>

## <a name="create-a-transportation-status"></a><span data-ttu-id="fb8ec-108">Criar o status do transporte</span><span class="sxs-lookup"><span data-stu-id="fb8ec-108">Create a transportation status</span></span>

<span data-ttu-id="fb8ec-109">Para criar um status de transporte, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="fb8ec-109">To create a transportation status, follow these steps:</span></span>

1. <span data-ttu-id="fb8ec-110">Vá para **Gerenciamento de transporte \> Configurar \> Mestres do status do transporte**.</span><span class="sxs-lookup"><span data-stu-id="fb8ec-110">Go to **Transportation management \> Setup \> Transportation status masters**.</span></span>
1. <span data-ttu-id="fb8ec-111">Selecione **Novo** para criar um mestre de status do transporte.</span><span class="sxs-lookup"><span data-stu-id="fb8ec-111">Select **New** to create a transportation status master.</span></span>
1. <span data-ttu-id="fb8ec-112">No campo **Mestre do status do transporte**, insira um código exclusivo para o status de transporte.</span><span class="sxs-lookup"><span data-stu-id="fb8ec-112">In the **Transportation status master** field, enter a unique code for the transportation status.</span></span>
1. <span data-ttu-id="fb8ec-113">No campo **Tipo de transporte**, selecione *Transportadora* ou *Hub* como o tipo de transporte.</span><span class="sxs-lookup"><span data-stu-id="fb8ec-113">In the **Transportation type** field, select either *Shipping carrier* or *Hub* as the type of transportation.</span></span>
1. <span data-ttu-id="fb8ec-114">Insira um nome e status de transporte.</span><span class="sxs-lookup"><span data-stu-id="fb8ec-114">Enter a name and transportation status.</span></span>
1. <span data-ttu-id="fb8ec-115">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="fb8ec-115">Close the page.</span></span>

## <a name="map-a-transportation-status-to-a-carrier-status"></a><span data-ttu-id="fb8ec-116">Mapear um status de transporte para um status de transportadora</span><span class="sxs-lookup"><span data-stu-id="fb8ec-116">Map a transportation status to a carrier status</span></span>

<span data-ttu-id="fb8ec-117">Para mapear um status de transporte para um status de transportadora, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="fb8ec-117">To map a transportation status to a carrier status, follow these steps:</span></span>

1. <span data-ttu-id="fb8ec-118">Vá para **Gerenciamento de transporte \> Configurar \> Transportadoras \> Status do transporte da transportadora**.</span><span class="sxs-lookup"><span data-stu-id="fb8ec-118">Go to **Transportation management \> Setup \> Carriers \> Carrier transportation status**.</span></span>
1. <span data-ttu-id="fb8ec-119">Selecione **Novo** para mapear um código de uma transportadora para um código mestre de status da transportadora.</span><span class="sxs-lookup"><span data-stu-id="fb8ec-119">Select **New** to map a code from a shipping carrier to a transportation status master code.</span></span>
1. <span data-ttu-id="fb8ec-120">Selecione a ID exclusiva da transportadora e o serviço da transportadora.</span><span class="sxs-lookup"><span data-stu-id="fb8ec-120">Select the unique ID for the shipping carrier and the carrier service.</span></span>
1. <span data-ttu-id="fb8ec-121">Selecione o código de status do transporte a ser mapeado para o código da transportadora selecionada.</span><span class="sxs-lookup"><span data-stu-id="fb8ec-121">Select the transportation status code that you want to map to the selected shipping carrier's code.</span></span>
1. <span data-ttu-id="fb8ec-122">Insira o código externo que é usado pela transportadora.</span><span class="sxs-lookup"><span data-stu-id="fb8ec-122">Enter the external code that is used by the shipping carrier.</span></span>
1. <span data-ttu-id="fb8ec-123">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="fb8ec-123">Close the page.</span></span>
