---
title: "Confirmação de lote e placa de licença"
description: "Este tópico descreve como configurar e aplicar a confirmação de lote e placa de licença de um dispositivo móvel."
author: Mirzaab
manager: AnnBe
ms.date: 05/26/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WHSRFAutoConfirm
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
ms.openlocfilehash: 90a45347cb5ed94259587024027eb8d1c4643fc6
ms.contentlocale: pt-br
ms.lasthandoff: 04/13/2018

---

# <a name="batch-and-license-plate-confirmation"></a><span data-ttu-id="006ae-103">Confirmação de lote e placa de licença</span><span class="sxs-lookup"><span data-stu-id="006ae-103">Batch and license plate confirmation</span></span>

[!INCLUDE [banner](../includes/banner.md)]

<span data-ttu-id="006ae-104">A confirmação do lote permite que você confirme se o lote correto está sendo separado do dispositivo móvel.</span><span class="sxs-lookup"><span data-stu-id="006ae-104">Batch confirmation allows you to confirm that the correct batch is being picked from the mobile device.</span></span> <span data-ttu-id="006ae-105">Na separação inicial do trabalho somente para itens acima do lote, no qual o lote acima indica que o lote é maior que a localização na hierarquia de pesquisa, você deve verificar se o lote escolhido corresponde ao lote da linha de trabalho.</span><span class="sxs-lookup"><span data-stu-id="006ae-105">On the initial pick of work for batch above-items only, where batch above indicates that batch ranges higher than location in the search hierarchy, you must verify that the batch that is picked matches the batch on the work line.</span></span> 

<span data-ttu-id="006ae-106">A confirmação da placa de licença permite que você confirme se a placa de licença correta está sendo selecionada do dispositivo móvel.</span><span class="sxs-lookup"><span data-stu-id="006ae-106">License plate confirmation allows you to confirm that the correct license plate is being picked from the mobile device.</span></span> <span data-ttu-id="006ae-107">Ao escolher o trabalho de uma localização de fase, você deve verificar se a placa de licença que foi selecionada corresponde à placa de licença associada ao trabalho.</span><span class="sxs-lookup"><span data-stu-id="006ae-107">When picking work from a stage location, you must verify that the license plate that is picked matches the license plate that is associated with the work.</span></span> <span data-ttu-id="006ae-108">Se o trabalho for iniciado pela verificação de uma placa de licença, a etapa de confirmação será ignorada.</span><span class="sxs-lookup"><span data-stu-id="006ae-108">If the work is started by scanning a license plate, this confirmation step will be skipped.</span></span>

## <a name="where-it-applies"></a><span data-ttu-id="006ae-109">Aplica-se a</span><span class="sxs-lookup"><span data-stu-id="006ae-109">Where it applies</span></span>
<span data-ttu-id="006ae-110">A confirmação aplica-se nos seguintes cenários:</span><span class="sxs-lookup"><span data-stu-id="006ae-110">Confirmation applies in the following scenarios:</span></span>

- <span data-ttu-id="006ae-111">A confirmação de lote aplica-se às seleções iniciais de trabalho dos itens acima do lote.</span><span class="sxs-lookup"><span data-stu-id="006ae-111">Batch confirmation applies to the initial picks of work for batch above-items.</span></span>
- <span data-ttu-id="006ae-112">A confirmação de placa de licença se aplica a separações de locais de fase.</span><span class="sxs-lookup"><span data-stu-id="006ae-112">License plate confirmation applies to picks from stage locations.</span></span>

## <a name="set-up-batch-and-license-plate-confirmation"></a><span data-ttu-id="006ae-113">Configurar confirmação de lote e placa de licença</span><span class="sxs-lookup"><span data-stu-id="006ae-113">Set up batch and license plate confirmation</span></span>
<span data-ttu-id="006ae-114">Você pode configurar a confirmação de lote e de placa de licença dos itens de menu de dispositivo móvel.</span><span class="sxs-lookup"><span data-stu-id="006ae-114">You can configure batch and license plate confirmation from the mobile device menu items.</span></span>  
1.  <span data-ttu-id="006ae-115">Dos itens de menu de dispositivo móvel, insira a configuração de confirmação de trabalho.</span><span class="sxs-lookup"><span data-stu-id="006ae-115">From the mobile device menu items, enter the work confirmation setup.</span></span>  
2.  <span data-ttu-id="006ae-116">Selecione a opção para o lote ou a confirmação da placa de licença.</span><span class="sxs-lookup"><span data-stu-id="006ae-116">Select the option for either batch or license plate confirmation.</span></span> <span data-ttu-id="006ae-117">As duas opções disponíveis para as separações por tipo de trabalho que não têm uma confirmação automática ativada.</span><span class="sxs-lookup"><span data-stu-id="006ae-117">Both options are available for work type picks that do not have automatic confirmation enabled.</span></span>  

