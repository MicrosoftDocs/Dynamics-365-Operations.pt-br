---
title: "Configurar para exibir lotes mais antigos no depósito em um dispositivo móvel"
description: "Este tópico descreve como configurar um dispositivo móvel para exibir uma lista de locais com lotes mais antigos do que o local atual de uma linha de trabalho."
author: Mirzaab
manager: AnnBe
ms.date: 05/26/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WHSRFMenuItem
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 4f2dc9221b72600c928db9fd306038725c7af305
ms.contentlocale: pt-br
ms.lasthandoff: 04/13/2018

---

# <a name="configure-display-older-batches-within-warehouse-on-a-mobile-device"></a><span data-ttu-id="73170-103">Configurar para exibir lotes mais antigos no depósito em um dispositivo móvel</span><span class="sxs-lookup"><span data-stu-id="73170-103">Configure Display older batches within warehouse on a mobile device</span></span>

[!INCLUDE [banner](../includes/banner.md)]

<span data-ttu-id="73170-104">A configuração **Exibir lotes mais antigos no depósito** permite exibir uma lista de locais com lotes mais antigos do que o local atual da linha de trabalho.</span><span class="sxs-lookup"><span data-stu-id="73170-104">The **Display older batches within warehouse** configuration lets you display a list of locations with batches older than the current location of the work line.</span></span> <span data-ttu-id="73170-105">A lista de locais exibidos inclui informações sobre os lotes mais antigos no local com a data de vencimento e o estoque físico de cada lote.</span><span class="sxs-lookup"><span data-stu-id="73170-105">The list of locations that are displayed includes information about the older batches in the location with the expiration date and the physical inventory of each batch.</span></span> <span data-ttu-id="73170-106">Você pode optar por separar de um novo local ou por continuar separando do local atual.</span><span class="sxs-lookup"><span data-stu-id="73170-106">You can choose to pick from a new location or to continue picking from the current location.</span></span> 
- <span data-ttu-id="73170-107">Separação de um novo local- se você selecionar um novo local de separação, a linha de trabalho atual será atualizada para usar o novo local e o trabalho continuará como de costume com o novo local.</span><span class="sxs-lookup"><span data-stu-id="73170-107">Pick from a new location - If you select a new location to pick from, the  current work line will be updated to use the new location and work will continue as usual with the new location.</span></span> <span data-ttu-id="73170-108">Para que o novo local seja válido, ele deverá ter a quantidade disponível suficiente para a linha de trabalho inteira.</span><span class="sxs-lookup"><span data-stu-id="73170-108">For the new location to be valid, it must have enough available quantity for the whole work line.</span></span> <span data-ttu-id="73170-109">Se a quantidade necessária não estiver disponível, a linha de trabalho não será atualizada, e a lista será exibida.</span><span class="sxs-lookup"><span data-stu-id="73170-109">If the required quantity is not available, the work line will not be updated, and the list will display.</span></span> 
- <span data-ttu-id="73170-110">Continuar separando do local atual - se você continuar com o local da linha de trabalho atual, as quantidades da linha de trabalho continuarão a ser separadas do local original.</span><span class="sxs-lookup"><span data-stu-id="73170-110">Continue picking from the current location - If you continue with the current work line location, the quantities for the work line will continue to be picked from the original location.</span></span>

## <a name="where-it-applies"></a><span data-ttu-id="73170-111">Aplica-se a</span><span class="sxs-lookup"><span data-stu-id="73170-111">Where it applies</span></span>
<span data-ttu-id="73170-112">Exibir lotes mais antigos no depósito é configurado em itens de menu de dispositivo móvel e afeta a seleção dos itens abaixo do lote.</span><span class="sxs-lookup"><span data-stu-id="73170-112">Display older batches within warehouse is configured on mobile device menu items and affects the pick for batch below items.</span></span>

## <a name="set-up-display-older-batches-within-warehouse"></a><span data-ttu-id="73170-113">Configurar Exibir lotes mais antigos no depósito</span><span class="sxs-lookup"><span data-stu-id="73170-113">Set up Display older batches within warehouse</span></span>
<span data-ttu-id="73170-114">A configuração **Exibir lotes mais antigos no depósito** estará disponível em itens de menu de dispositivo móvel quando a opção **Separar lote mais antigo** estiver definida como **Avisar**.</span><span class="sxs-lookup"><span data-stu-id="73170-114">The **Display older batches within warehouse** configuration is available on mobile device menu items when the **Pick oldest batch** option is set to **Warn**.</span></span>

- <span data-ttu-id="73170-115">Em **Gerenciamento de depósito** > **Configuração** > **Dispositivo móvel** > **Itens de menu de dispositivo móvel**, defina **Usar rede existente** como **Sim** para o item de menu e selecione **Avisar** no campo **Escolher lote mais antigo**.</span><span class="sxs-lookup"><span data-stu-id="73170-115">Under **Warehouse management** > **Setup** > **Mobile device** > **Mobile device menu items**, set **Use existing work** to **Yes** for the menu item, and select **Warn** in the **Pick oldest batch** field.</span></span> 


