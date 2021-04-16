---
title: Movimento de estoque com trabalho associado no Gerenciamento de depósitos
description: Ao usar o movimento de estoque, você pode decidir quais funcionários do depósito têm permissão para mover o estoque reservado.
author: Mirzaab
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSWorker
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d6477a91b3c65e8be5ab527eaff12c92ae7918b7
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5808741"
---
# <a name="movement-of-inventory-with-associated-work-in-warehouse-management"></a><span data-ttu-id="3622f-103">Movimento de estoque com trabalho associado no Gerenciamento de depósitos</span><span class="sxs-lookup"><span data-stu-id="3622f-103">Movement of inventory with associated work in Warehouse management</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="3622f-104">Ao usar o movimento de estoque, você pode decidir quais funcionários do depósito têm permissão para mover o estoque reservado.</span><span class="sxs-lookup"><span data-stu-id="3622f-104">Using movement of inventory, you can decide which warehouse workers are allowed to move reserved inventory.</span></span> <span data-ttu-id="3622f-105">Isso fornece flexibilidade em depósitos regulamentados em que você pode decidir não permitir que um trabalhador escolha um novo local de separação para o trabalho de separação já criado.</span><span class="sxs-lookup"><span data-stu-id="3622f-105">This provides a flexibility in regulated warehouses where you can decide to not allow a worker to choose a new pick location for pick work that is already created.</span></span> <span data-ttu-id="3622f-106">Também permite que o gerente de depósito controle quais recursos alguns trabalhadores menos experientes devem ter.</span><span class="sxs-lookup"><span data-stu-id="3622f-106">It also allows a warehouse manager to control which capabilities some less experienced workers should have.</span></span>

<span data-ttu-id="3622f-107">A flexibilidade para gerenciar operações diárias de trabalhadores de depósito pode ser útil em cenários como estes:</span><span class="sxs-lookup"><span data-stu-id="3622f-107">The flexibility to manage the daily operations of warehouse workers can be useful in scenarios such as these:</span></span>

## <a name="scenario-1"></a><span data-ttu-id="3622f-108">Cenário 1</span><span class="sxs-lookup"><span data-stu-id="3622f-108">Scenario 1</span></span>

<span data-ttu-id="3622f-109">Uma empresa possui uma área de recebimento relativamente pequena, e está congestionada devido a paletes e caixas que aguardam alocação.</span><span class="sxs-lookup"><span data-stu-id="3622f-109">A company has a relatively small receiving area, and it’s congested with pallets and boxes awaiting put away.</span></span> <span data-ttu-id="3622f-110">Uma grande remessa é esperada no dia atual, o auxiliar de recebimento decide liberar a área de remessa movendo alguns paletes para uma área de preparo de entrada secundária.</span><span class="sxs-lookup"><span data-stu-id="3622f-110">A large shipment is expected on the current day, so the receiving clerk decides to clear up the receiving area by moving some of the pallets to a secondary inbound staging area.</span></span>

## <a name="scenario-2"></a><span data-ttu-id="3622f-111">Cenário 2</span><span class="sxs-lookup"><span data-stu-id="3622f-111">Scenario 2</span></span>

<span data-ttu-id="3622f-112">Um trabalhador de depósito experiente percebe uma oportunidade de consolidar os itens em local único em vez de ser dividido por três locais próximos com pouca quantidade em cada um.</span><span class="sxs-lookup"><span data-stu-id="3622f-112">An experienced warehouse worker notices an opportunity in a warehouse to consolidate items in one location instead of having them divided across three nearby locations with little quantity on each.</span></span> <span data-ttu-id="3622f-113">O trabalhador deseja consolidar a quantidade movendo itens de cada um desses locais para o mesmo local e com a mesma placa de licença.</span><span class="sxs-lookup"><span data-stu-id="3622f-113">The worker wants to consolidate the quantity by moving items from each of these locations into the same location and onto the same license plate.</span></span>

## <a name="scenario-3"></a><span data-ttu-id="3622f-114">Cenário 3</span><span class="sxs-lookup"><span data-stu-id="3622f-114">Scenario 3</span></span>

<span data-ttu-id="3622f-115">Um palete está aguardando remessa em um local de preparo, como STAGE01, que é próximo de BAYDOOR01.</span><span class="sxs-lookup"><span data-stu-id="3622f-115">A pallet is awaiting shipment in a staging location, such as STAGE01, which is near BAYDOOR01.</span></span> <span data-ttu-id="3622f-116">Entretanto, devido a uma mudança de planos, o caminhão está programada para chegar em BAYDOOR04.</span><span class="sxs-lookup"><span data-stu-id="3622f-116">However, due to a change of plans the truck is scheduled to arrive at BAYDOOR04.</span></span> <span data-ttu-id="3622f-117">O funcionário de remessa está ciente disso e precisa garantir que o caminhão não tenha que aguardar para ser carregado a partir do STAGE01.</span><span class="sxs-lookup"><span data-stu-id="3622f-117">The shipping clerk is aware of this and needs to ensure that the truck does not have to wait to be loaded from STAGE01.</span></span> <span data-ttu-id="3622f-118">O funcionário de remessa decide mover os itens dessa remessa de STAGE01 para STAGE04, que é mais próximo do novo destino.</span><span class="sxs-lookup"><span data-stu-id="3622f-118">The shipping clerk decides to move the items in that shipment from STAGE01 to STAGE04, which is closer to the new destination.</span></span>

### <a name="current-limitations"></a><span data-ttu-id="3622f-119">Limitações atuais</span><span class="sxs-lookup"><span data-stu-id="3622f-119">Current limitations</span></span>

<span data-ttu-id="3622f-120">As reservas de trabalho que você pode mover são limitadas à Ordem de venda, à Emissão de ordem de transferência, ao Recebimento da ordem de transferência, à Ordem de compra e ao Trabalho de reabastecimento.</span><span class="sxs-lookup"><span data-stu-id="3622f-120">The work reservations that you can move are limited to Sales order, Transfer order issue, Transfer order receipt, Purchase order, and Replenishment work.</span></span>

<span data-ttu-id="3622f-121">Mover itens se restringe a evitar a divisão de linhas de trabalho.</span><span class="sxs-lookup"><span data-stu-id="3622f-121">Moving items is restricted to prevent splitting of work lines.</span></span> <span data-ttu-id="3622f-122">Isso significa que se você tem uma linha de trabalho de 100 peças de item A, localização Loc1, não será possível mover somente 30 peças de item A para outro local.</span><span class="sxs-lookup"><span data-stu-id="3622f-122">This means that if you have a work line for 100 pcs of item A from location Loc1, you won’t be able to move only 30 pcs of item A from there to another location.</span></span> <span data-ttu-id="3622f-123">Isso levaria a uma divisão da linha de trabalho existente em 30 e 70, pois agora as localizações são diferentes.</span><span class="sxs-lookup"><span data-stu-id="3622f-123">This would lead to a split of the existing work line to 30 and 70, because the locations are now different.</span></span>

<span data-ttu-id="3622f-124">Para cenários de preparo em que você move a placa de licença da mercadoria ou em que você move a placa de licença para a mercadoria são definidas como LP de destino para uma ordem de trabalho, somente é permitido o movimento do LP inteiro, de forma a não dividir o LP de destino.</span><span class="sxs-lookup"><span data-stu-id="3622f-124">For staging scenarios, where the license plate you move the goods from or the license plate you move the goods to, are set as a Target LP for a work order, only movement of the entire LP is allowed, so as not to break up the Target LP.</span></span>

<span data-ttu-id="3622f-125">Somente o movimento ad hoc tem suporte atualmente.</span><span class="sxs-lookup"><span data-stu-id="3622f-125">Only the ad hoc movement is currently supported.</span></span> <span data-ttu-id="3622f-126">Isso significa que não será possível mover estoque reservado por modelo de itens de menu do dispositivo móvel.</span><span class="sxs-lookup"><span data-stu-id="3622f-126">That means that you will not be able to move reserved inventory through the movement by template mobile device menu items.</span></span>

### <a name="set-up-permission-to-move-reserved-inventory-for-individual-workers"></a><span data-ttu-id="3622f-127">Configurar permissão para mover o estoque reservado para trabalhadores individuais</span><span class="sxs-lookup"><span data-stu-id="3622f-127">Set up permission to move reserved inventory for individual workers</span></span>

<span data-ttu-id="3622f-128">Para o trabalhador que tem permissão para mover o estoque reservado, marque a caixa de seleção **Permitir movimento de estoque com trabalho associado** em **Gerenciamento de depósito \> Configuração \> Trabalhador**.</span><span class="sxs-lookup"><span data-stu-id="3622f-128">For the worker who is allowed to move reserved inventory, select the **Allow movement of inventory with work associated** check box under **Warehouse management \> Setup \> Worker**.</span></span>  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
