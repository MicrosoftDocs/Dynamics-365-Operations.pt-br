---
title: Confirmação de separação de peças
description: Este tópico descreve como configurar e aplicar a confirmação de separação de peças de um dispositivo móvel.
author: Mirzaab
manager: tfehr
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSRFAutoConfirm, WHSRFMenuItem
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ed63245066799d7d8f14362ab6c9193c0cda7c4a
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3215576"
---
# <a name="piece-picking-confirmation"></a><span data-ttu-id="28e46-103">Confirmação de separação de peças</span><span class="sxs-lookup"><span data-stu-id="28e46-103">Piece picking confirmation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="28e46-104">A separação de peças permite que você confirme cada peça de estoque por meio do trabalho de separação ou de contagem em um dispositivo móvel.</span><span class="sxs-lookup"><span data-stu-id="28e46-104">Piece picking allows you to confirm each piece of inventory through picking or counting work on a mobile device.</span></span> <span data-ttu-id="28e46-105">Referente às separações, é possível confirmar desde a quantidade de trabalho a ser processado até a quantidade especificada no trabalho a ser separado.</span><span class="sxs-lookup"><span data-stu-id="28e46-105">For picks, you can confirm the quantity of work to be processed up to the quantity that is specified on work to be picked.</span></span> <span data-ttu-id="28e46-106">Referente ao trabalho de contagem, é possível verificar o estoque que você está contando e rastrear o valor total.</span><span class="sxs-lookup"><span data-stu-id="28e46-106">For counting work, you can scan the inventory that you are counting and track the total amount.</span></span>

<span data-ttu-id="28e46-107">Ao habilitar a separação de peças, a confirmação do produto é automaticamente selecionada.</span><span class="sxs-lookup"><span data-stu-id="28e46-107">When you enable piece picking, product confirmation is automatically selected.</span></span> <span data-ttu-id="28e46-108">Referente às separações por tipo de trabalho, o número máximo de peças é habilitado.</span><span class="sxs-lookup"><span data-stu-id="28e46-108">For work-type picks, a maximum number of pieces is enabled.</span></span> <span data-ttu-id="28e46-109">Isso permite definir um número máximo de peças a ser confirmado durante o processo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="28e46-109">This allows you to set a maximum to the number of pieces that must be confirmed during the work process.</span></span> <span data-ttu-id="28e46-110">A quantidade máxima é baseada na unidade de trabalho atual que está sendo processada.</span><span class="sxs-lookup"><span data-stu-id="28e46-110">The maximum quantity is based on the current work unit that is being processed.</span></span> <span data-ttu-id="28e46-111">O tipo de trabalho de contagem não permite uma quantidade máxima.</span><span class="sxs-lookup"><span data-stu-id="28e46-111">The counting work type does not allow a maximum.</span></span>

<span data-ttu-id="28e46-112">Você também pode usar a quantidade e a unidade de medida (UOM) associadas a um código de barras verificado.</span><span class="sxs-lookup"><span data-stu-id="28e46-112">You can also use the quantity and unit of measure (UOM) that is associated with a scanned bar code.</span></span> <span data-ttu-id="28e46-113">Isso colaborará para o recebimento em fluxos de entrada, incluindo o recebimento de placa de licença mista, item da ordem de compra, item da ordem de transferência e o item de carga.</span><span class="sxs-lookup"><span data-stu-id="28e46-113">This will work for receiving on inbound flows including mixed license plate receiving, purchase order item, transfer order item, and load item.</span></span> <span data-ttu-id="28e46-114">Também colaborará para a separação de peças em que verificar o código de barras adicionará a quantidade ao número total de peças confirmadas na conversão entre a UOM no código de barras e a unidade de trabalho.</span><span class="sxs-lookup"><span data-stu-id="28e46-114">It also works for piece picking where scanning the bar code will add the quantity to the total number of confirmed pieces converting between the UOM on the bar code and the work unit.</span></span> <span data-ttu-id="28e46-115">Se, ao contar a UOM no código de barras, for confirmado que a quantidade é permitida para contagem no grupo de foco de sequência, a quantidade será adicionada à contagem total.</span><span class="sxs-lookup"><span data-stu-id="28e46-115">If, when counting the UOM on the bar code, it is confirmed that the quantity is allowed for counting on the sequence group, the quantity will be added to the total count.</span></span>

## <a name="where-it-applies"></a><span data-ttu-id="28e46-116">Aplica-se a</span><span class="sxs-lookup"><span data-stu-id="28e46-116">Where it applies</span></span>

<span data-ttu-id="28e46-117">Trabalhos de separação de peças para todos os trabalhos de contagem e para a separação inicial relativa a qualquer tipo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="28e46-117">Piece picking works for all counting work and for the initial pick for any type of work.</span></span> <span data-ttu-id="28e46-118">A separação de peças não se aplica se o item for controlado por números de série ou for uma produção ou uma separação kanban de um local de LP (placa de licença) e o item estiver definido para preparo.</span><span class="sxs-lookup"><span data-stu-id="28e46-118">Piece picking does not apply if the item is controlled by serial numbers or if it is a production or kanban pick from a license plate (LP) location and the item is set to staging.</span></span>

## <a name="set-up-piece-picking"></a><span data-ttu-id="28e46-119">Configurar separação de peças</span><span class="sxs-lookup"><span data-stu-id="28e46-119">Set up piece picking</span></span>

1.  <span data-ttu-id="28e46-120">No item de menu do dispositivo móvel, abra o formulário de configuração para a confirmação de trabalho: Gerenciamento de depósito > **Gerenciamento de depósito** > **Configuração** > **Dispositivo móvel** > **Itens de menu do dispositivo móvel**.</span><span class="sxs-lookup"><span data-stu-id="28e46-120">On a mobile device menu item, open the setup form for work confirmation: Warehouse management > **Warehouse management** > **Setup** > **Mobile device** > **Mobile device menu items**.</span></span> 
2. <span data-ttu-id="28e46-121">Do item de menu de dispositivo móvel, abra a configuração de Confirmação de trabalho.</span><span class="sxs-lookup"><span data-stu-id="28e46-121">From the mobile device menu item, open Work confirmation setup.</span></span>

<span data-ttu-id="28e46-122">As seguintes opções tornam-se disponíveis para seleção quando o tipo de trabalho é separação e contagem.</span><span class="sxs-lookup"><span data-stu-id="28e46-122">The following options become available for selection when the work type is pick or counting.</span></span>


|           <span data-ttu-id="28e46-123">Opção</span><span class="sxs-lookup"><span data-stu-id="28e46-123">Option</span></span>           |                                                                            <span data-ttu-id="28e46-124">descrição</span><span class="sxs-lookup"><span data-stu-id="28e46-124">Description</span></span>                                                                            |
|----------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="28e46-125">Confirmação de separação de peças</span><span class="sxs-lookup"><span data-stu-id="28e46-125">Piece picking confirmation</span></span> | <span data-ttu-id="28e46-126">Disponível para tipos de trabalho de separação e contagem.</span><span class="sxs-lookup"><span data-stu-id="28e46-126">Available for pick and counting work types.</span></span> <span data-ttu-id="28e46-127">A confirmação de produto é selecionada automaticamente.</span><span class="sxs-lookup"><span data-stu-id="28e46-127">Product confirmation is automatically selected.</span></span> <span data-ttu-id="28e46-128">Permite a você confirmar cada peça de estoque do dispositivo móvel.</span><span class="sxs-lookup"><span data-stu-id="28e46-128">Allows you to confirm each piece of inventory from the mobile device.</span></span> |
|  <span data-ttu-id="28e46-129">Número máximo de peças</span><span class="sxs-lookup"><span data-stu-id="28e46-129">Maximum number of pieces</span></span>  |                   <span data-ttu-id="28e46-130">Disponível para trabalho de separação se a confirmação de separação de peças estiver habilitada.</span><span class="sxs-lookup"><span data-stu-id="28e46-130">Available for pick work if piece picking confirmation is enabled.</span></span> <span data-ttu-id="28e46-131">Define um limite para o número de peças que você deve confirmar.</span><span class="sxs-lookup"><span data-stu-id="28e46-131">Sets a limit to the number of pieces that you must confirm.</span></span>                   |

