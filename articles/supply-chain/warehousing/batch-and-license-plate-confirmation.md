---
title: Confirmação de lote e placa de licença
description: Este tópico descreve como configurar e aplicar a confirmação de lote e placa de licença em um dispositivo móvel.
author: Mirzaab
ms.date: 11/11/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSRFAutoConfirm
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c588e6ed11d275b75133e2824f3d385048050426
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5837528"
---
# <a name="batch-and-license-plate-confirmation"></a><span data-ttu-id="3ace4-103">Confirmação de lote e placa de licença</span><span class="sxs-lookup"><span data-stu-id="3ace4-103">Batch and license plate confirmation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="3ace4-104">A confirmação do lote permite que você confirme se o lote correto está sendo separado do dispositivo móvel.</span><span class="sxs-lookup"><span data-stu-id="3ace4-104">Batch confirmation allows you to confirm that the correct batch is being picked from the mobile device.</span></span> <span data-ttu-id="3ace4-105">Na seleção inicial do trabalho somente para itens *Lote acima\[local\]*, no qual o lote acima indica que o lote é colocado acima da localização na hierarquia de pesquisa, você deve verificar se o lote escolhido corresponde ao lote da linha de trabalho.</span><span class="sxs-lookup"><span data-stu-id="3ace4-105">On the initial pick of work for *Batch-above\[location\]* items only, where batch-above indicates that batch is placed higher than location in the search hierarchy, you must verify that the batch that is picked matches the batch on the work line.</span></span>

<span data-ttu-id="3ace4-106">A confirmação da placa de licença permite que você confirme se a placa de licença correta está sendo selecionada no dispositivo móvel.</span><span class="sxs-lookup"><span data-stu-id="3ace4-106">License plate confirmation allows you to confirm that the correct license plate is being picked from the mobile device.</span></span> <span data-ttu-id="3ace4-107">Ao escolher o trabalho de um local de espera, você deve verificar se a placa de licença selecionada corresponde à placa de licença associada ao trabalho.</span><span class="sxs-lookup"><span data-stu-id="3ace4-107">When picking work from a stage location, you must verify that the license plate that is picked matches the license plate that is associated with the work.</span></span> <span data-ttu-id="3ace4-108">Se o trabalho for iniciado pela verificação de uma placa de licença, a etapa de confirmação será ignorada.</span><span class="sxs-lookup"><span data-stu-id="3ace4-108">If the work is started by scanning a license plate, this confirmation step will be skipped.</span></span>

## <a name="where-it-applies"></a><span data-ttu-id="3ace4-109">Aplica-se a</span><span class="sxs-lookup"><span data-stu-id="3ace4-109">Where it applies</span></span>

<span data-ttu-id="3ace4-110">A confirmação aplica-se nos seguintes cenários:</span><span class="sxs-lookup"><span data-stu-id="3ace4-110">Confirmation applies in the following scenarios:</span></span>

- <span data-ttu-id="3ace4-111">A confirmação de lote aplica-se às seleções iniciais de trabalho dos itens acima do lote.</span><span class="sxs-lookup"><span data-stu-id="3ace4-111">Batch confirmation applies to the initial picks of work for batch above-items.</span></span>
- <span data-ttu-id="3ace4-112">A confirmação de placa de licença se aplica a separações nos locais de espera.</span><span class="sxs-lookup"><span data-stu-id="3ace4-112">License plate confirmation applies to picks from stage locations.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3ace4-113">O reabastecimento não tem suporte para a confirmação da placa de licença.</span><span class="sxs-lookup"><span data-stu-id="3ace4-113">Replenishment is not supported for license plate confirmation.</span></span> <span data-ttu-id="3ace4-114">Ao executar o trabalho de reabastecimento, nenhuma etapa de confirmação da placa de licença é criada.</span><span class="sxs-lookup"><span data-stu-id="3ace4-114">When executing replenishment work, no license plate confirmation step is created.</span></span>

## <a name="set-up-batch-and-license-plate-confirmation"></a><span data-ttu-id="3ace4-115">Configurar confirmação de lote e placa de licença</span><span class="sxs-lookup"><span data-stu-id="3ace4-115">Set up batch and license plate confirmation</span></span>

<span data-ttu-id="3ace4-116">Você pode configurar a confirmação de lote e de placa de licença dos itens de menu de dispositivo móvel.</span><span class="sxs-lookup"><span data-stu-id="3ace4-116">You can configure batch and license plate confirmation from the mobile device menu items.</span></span>

1. <span data-ttu-id="3ace4-117">Dos itens de menu de dispositivo móvel, insira a configuração de confirmação de trabalho.</span><span class="sxs-lookup"><span data-stu-id="3ace4-117">From the mobile device menu items, enter the work confirmation setup.</span></span>  
1. <span data-ttu-id="3ace4-118">Selecione a opção para o lote ou a confirmação da placa de licença.</span><span class="sxs-lookup"><span data-stu-id="3ace4-118">Select the option for either batch or license plate confirmation.</span></span> <span data-ttu-id="3ace4-119">As duas opções disponíveis para as separações por tipo de trabalho que não têm uma confirmação automática ativada.</span><span class="sxs-lookup"><span data-stu-id="3ace4-119">Both options are available for work type picks that do not have automatic confirmation enabled.</span></span>  


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
