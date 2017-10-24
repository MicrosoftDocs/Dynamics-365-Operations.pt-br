---
title: "Movimento de estoque com trabalho associado no Gerenciamento de depósito"
description: "Este tópico descreve como configurar e aplicar a confirmação de separação de peças de um dispositivo móvel."
author: Mirzaab
manager: AnnBe
ms.date: 05/26/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 463e438418c4bc1b38fd1bde8251d1383cb44a13
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---

# <a name="movement-of-inventory-with-associated-work-in-warehouse-management"></a><span data-ttu-id="25327-103">Movimento de estoque com trabalho associado no Gerenciamento de depósito</span><span class="sxs-lookup"><span data-stu-id="25327-103">Movement of inventory with associated work in Warehouse management</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="25327-104">Ao usar o movimento de estoque, você pode decidir quais funcionários do depósito têm permissão para mover o estoque reservado.</span><span class="sxs-lookup"><span data-stu-id="25327-104">Using movement of inventory, you can decide which warehouse workers are allowed to move reserved inventory.</span></span> <span data-ttu-id="25327-105">Isso fornece flexibilidade em depósitos regulamentados em que você pode decidir não permitir que um trabalhador escolha um novo local de separação para o trabalho de separação já criado.</span><span class="sxs-lookup"><span data-stu-id="25327-105">This provides a flexibility in regulated warehouses where you can decide to not allow a worker to choose a new pick location for pick work that is already created.</span></span> <span data-ttu-id="25327-106">Também permite que o gerente de depósito controle quais recursos alguns trabalhadores menos experientes devem ter.</span><span class="sxs-lookup"><span data-stu-id="25327-106">It also allows a warehouse manager to control which capabilities some less experienced workers should have.</span></span>

<span data-ttu-id="25327-107">A flexibilidade para gerenciar operações diárias de trabalhadores de depósito pode ser útil em cenários como estes:</span><span class="sxs-lookup"><span data-stu-id="25327-107">The flexibility to manage the daily operations of warehouse workers can be useful in scenarios such as these:</span></span>

## <a name="scenario-1"></a><span data-ttu-id="25327-108">Cenário 1</span><span class="sxs-lookup"><span data-stu-id="25327-108">Scenario 1</span></span>
<span data-ttu-id="25327-109">Uma empresa possui uma área de recebimento relativamente pequena, e está congestionada devido a paletes e caixas que aguardam alocação.</span><span class="sxs-lookup"><span data-stu-id="25327-109">A company has a relatively small receiving area, and it’s congested with pallets and boxes awaiting put away.</span></span> <span data-ttu-id="25327-110">Uma grande remessa é esperada no dia atual, o auxiliar de recebimento decide liberar a área de remessa movendo alguns paletes para uma área de preparo de entrada secundária.</span><span class="sxs-lookup"><span data-stu-id="25327-110">A large shipment is expected on the current day, so the receiving clerk decides to clear up the receiving area by moving some of the pallets to a secondary inbound staging area.</span></span>

## <a name="scenario-2"></a><span data-ttu-id="25327-111">Cenário 2</span><span class="sxs-lookup"><span data-stu-id="25327-111">Scenario 2</span></span>
<span data-ttu-id="25327-112">Um trabalhador de depósito experiente percebe uma oportunidade de consolidar os itens em local único em vez de ser dividido por 3 locais próximos com pouca quantidade em cada um.</span><span class="sxs-lookup"><span data-stu-id="25327-112">An experienced warehouse worker notices an opportunity in a warehouse to consolidate items in one location instead of having them divided across 3 nearby locations with little quantity on each.</span></span> <span data-ttu-id="25327-113">O trabalhador deseja consolidar a quantidade movendo itens de cada um desses locais para o mesmo local e com a mesma placa de licença.</span><span class="sxs-lookup"><span data-stu-id="25327-113">The worker wants to consolidate the quantity by moving items from each of these locations into the same location and onto the same license plate.</span></span>

## <a name="scenario-3"></a><span data-ttu-id="25327-114">Cenário 3</span><span class="sxs-lookup"><span data-stu-id="25327-114">Scenario 3</span></span>
<span data-ttu-id="25327-115">Um palete está aguardando remessa em um local de preparo, como STAGE01, que é próximo de BAYDOOR01.</span><span class="sxs-lookup"><span data-stu-id="25327-115">A pallet is awaiting shipment in a staging location, such as STAGE01, which is near BAYDOOR01.</span></span> <span data-ttu-id="25327-116">Entretanto, devido a uma mudança de planos, o caminhão está programada para chegar em BAYDOOR04.</span><span class="sxs-lookup"><span data-stu-id="25327-116">However, due to a change of plans the truck is scheduled to arrive at BAYDOOR04.</span></span> <span data-ttu-id="25327-117">O funcionário de remessa está ciente disso e precisa garantir que o caminhão não tenha que aguardar para ser carregado a partir do STAGE01.</span><span class="sxs-lookup"><span data-stu-id="25327-117">The shipping clerk is aware of this and needs to ensure that the truck does not have to wait to be loaded from STAGE01.</span></span> <span data-ttu-id="25327-118">O funcionário de remessa decide mover os itens dessa remessa de STAGE01 para STAGE04, que é mais próximo do novo destino.</span><span class="sxs-lookup"><span data-stu-id="25327-118">The shipping clerk decides to move the items in that shipment from STAGE01 to STAGE04, which is closer to the new destination.</span></span>

### <a name="current-limitations"></a><span data-ttu-id="25327-119">Limitações atuais</span><span class="sxs-lookup"><span data-stu-id="25327-119">Current limitations</span></span>

<span data-ttu-id="25327-120">As reservas de trabalho que você pode mover são limitadas à Ordem de venda, à Emissão de ordem de transferência, ao Recebimento da ordem de transferência, à Ordem de compra e ao Trabalho de reabastecimento.</span><span class="sxs-lookup"><span data-stu-id="25327-120">The work reservations that you can move are limited to Sales order, Transfer order issue, Transfer order receipt, Purchase order, and Replenishment work.</span></span>

<span data-ttu-id="25327-121">Mover itens se restringe a evitar a divisão de linhas de trabalho.</span><span class="sxs-lookup"><span data-stu-id="25327-121">Moving items is restricted to prevent splitting of work lines.</span></span> <span data-ttu-id="25327-122">Isso significa que se você tem uma linha de trabalho de 100 peças de item A, localização Loc1, não será possível mover somente 30 peças de item A para outro local.</span><span class="sxs-lookup"><span data-stu-id="25327-122">This means that if you have a work line for 100 pcs of item A from location Loc1, you won’t be able to move only 30 pcs of item A from there to another location.</span></span> <span data-ttu-id="25327-123">Isso levaria a uma divisão da linha de trabalho existente em 30 e 70, pois agora as localizações são diferentes.</span><span class="sxs-lookup"><span data-stu-id="25327-123">This would lead to a split of the existing work line to 30 and 70, because the locations are now different.</span></span>

<span data-ttu-id="25327-124">Para cenários de preparo em que você move a placa de licença da mercadoria ou em que você move a placa de licença para a mercadoria são definidas como LP de destino para uma ordem de trabalho, somente é permitido o movimento do LP inteiro, de forma a não dividir o LP de destino.</span><span class="sxs-lookup"><span data-stu-id="25327-124">For staging scenarios, where the license plate you move the goods from or the license plate you move the goods to, are set as a Target LP for a work order, only movement of the entire LP is allowed, so as not to break up the Target LP.</span></span>
<span data-ttu-id="25327-125">Somente o movimento ad hoc tem suporte atualmente.</span><span class="sxs-lookup"><span data-stu-id="25327-125">Only the ad hoc movement is currently supported.</span></span> <span data-ttu-id="25327-126">Isso significa que não será possível mover estoque reservado por modelo de itens de menu do dispositivo móvel.</span><span class="sxs-lookup"><span data-stu-id="25327-126">That means that you will not be able to move reserved inventory through the movement by template mobile device menu items.</span></span>

### <a name="set-up-permission-to-move-reserved-inventory-for-individual-workers"></a><span data-ttu-id="25327-127">Configurar permissão para mover o estoque reservado para trabalhadores individuais</span><span class="sxs-lookup"><span data-stu-id="25327-127">Set up permission to move reserved inventory for individual workers</span></span>

<span data-ttu-id="25327-128">Para o trabalhador que terá permissão para mover o estoque reservado, marque a caixa de seleção **Permitir movimento de estoque com trabalho associado** em **Gerenciamento de depósito** > **Configuração** > **Trabalhador**.</span><span class="sxs-lookup"><span data-stu-id="25327-128">For the worker who should be allowed to move reserved inventory, select the **Allow movement of inventory with work associated** check box under **Warehouse management** > **Setup** > **Worker**.</span></span>  

### <a name="backported"></a><span data-ttu-id="25327-129">Atualização retroativa</span><span class="sxs-lookup"><span data-stu-id="25327-129">Backported</span></span>

<span data-ttu-id="25327-130">Este recurso também foi atualizado de forma retroativa para Microsoft Dynamics AX 2012 R3 e estará disponível como parte do CU12.</span><span class="sxs-lookup"><span data-stu-id="25327-130">This feature has also been back-ported to Microsoft Dynamics AX 2012 R3 and will be available as part of CU12.</span></span>
<span data-ttu-id="25327-131">Ele também pode ser baixado individualmente com o número de KB 3192548.</span><span class="sxs-lookup"><span data-stu-id="25327-131">It can also be downloaded individually through KB number 3192548.</span></span> 


