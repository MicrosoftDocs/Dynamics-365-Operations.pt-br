---
title: Sequência numérica de gerenciamento de transporte
description: Este tópico descreve como configurar sequências numéricas para gerenciamento de transporte.
author: Henrikan
manager: tfehr
ms.date: 10/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2020-10-16
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: cc19110f481c11ab28532d69a4689c1db048f6c3
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5233358"
---
# <a name="transportation-management-number-sequence"></a><span data-ttu-id="c92b9-103">Sequência numérica de gerenciamento de transporte</span><span class="sxs-lookup"><span data-stu-id="c92b9-103">Transportation management number sequence</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c92b9-104">Use a página **Sequências numéricas** no módulo de gerenciamento de transporte para configurar vários números profissionais.</span><span class="sxs-lookup"><span data-stu-id="c92b9-104">Use the **Number sequences** page in the transportation management module to set up various pro numbers.</span></span> <span data-ttu-id="c92b9-105">Os números profissionais são usados pelas transportadoras para organizar e rastrear o andamento de cada remessa.</span><span class="sxs-lookup"><span data-stu-id="c92b9-105">Pro numbers are used by carriers to organize and track the progress of each shipment.</span></span>

## <a name="create-a-number-sequence-for-a-pro-number"></a><span data-ttu-id="c92b9-106">Criar uma sequência numérica para um número progressivo</span><span class="sxs-lookup"><span data-stu-id="c92b9-106">Create a number sequence for a pro number</span></span>

<span data-ttu-id="c92b9-107">Para criar uma sequência numérica para um número progressivo, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c92b9-107">To create a number sequence for a pro number, do the following:</span></span>

1. <span data-ttu-id="c92b9-108">Vá para **Gerenciamento de transporte \> Configurar \> Transportadoras \> Sequências numéricas**.</span><span class="sxs-lookup"><span data-stu-id="c92b9-108">Go to **Transportation management \> Setup \> Carriers \> Number sequences**.</span></span>
1. <span data-ttu-id="c92b9-109">Selecione **Novo** para criar uma sequência numérica.</span><span class="sxs-lookup"><span data-stu-id="c92b9-109">Select **New** to create a new number sequence.</span></span>
1. <span data-ttu-id="c92b9-110">Digite uma ID exclusiva e um nome descritivo para a sequência numérica.</span><span class="sxs-lookup"><span data-stu-id="c92b9-110">Enter a unique ID and descriptive name for the number sequence.</span></span>
1. <span data-ttu-id="c92b9-111">No campo **Tipo de sequência numérica**, *Número progressivo* é a única opção.</span><span class="sxs-lookup"><span data-stu-id="c92b9-111">In the **Number sequence type** field, *Pro number* is the only option.</span></span>
1. <span data-ttu-id="c92b9-112">No campo **Dígito de verificação**, *Dígito de verificação* é a única opção e é configurado como um mecanismo genérico.</span><span class="sxs-lookup"><span data-stu-id="c92b9-112">In the **Check digit** field, *Check digit* is the only option and is set up as a generic engine.</span></span>
1. <span data-ttu-id="c92b9-113">Na FastTab **Sequência**, fornaça informações sobre a sequência.</span><span class="sxs-lookup"><span data-stu-id="c92b9-113">On the **Sequence** FastTab, provide information about the sequence.</span></span>
1. <span data-ttu-id="c92b9-114">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="c92b9-114">Close the page.</span></span>

## <a name="link-a-number-sequence-to-a-shipping-carrier"></a><span data-ttu-id="c92b9-115">Vincular uma sequência numérica a uma transportadora</span><span class="sxs-lookup"><span data-stu-id="c92b9-115">Link a number sequence to a shipping carrier</span></span>

<span data-ttu-id="c92b9-116">Para vincular uma sequência numérica a uma transportadora, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c92b9-116">To link a number sequence to a carrier, do the following:</span></span>

1. <span data-ttu-id="c92b9-117">Vá para **Gerenciamento de transporte \> Configurar \> Transportadoras \> Transportadoras**.</span><span class="sxs-lookup"><span data-stu-id="c92b9-117">Go to **Transportation management \> Setup \> Carriers \> Shipping carriers**.</span></span>
1. <span data-ttu-id="c92b9-118">Selecione uma transportadora.</span><span class="sxs-lookup"><span data-stu-id="c92b9-118">Select a shipping carrier.</span></span>
1. <span data-ttu-id="c92b9-119">Selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="c92b9-119">Select **Edit**.</span></span>
1. <span data-ttu-id="c92b9-120">Na FastTab **Visão geral**, selecione uma opção no campo **Sequência numérica progressiva**.</span><span class="sxs-lookup"><span data-stu-id="c92b9-120">On the **Overview** FastTab, select an option in the **Pro number sequence** field.</span></span>
1. <span data-ttu-id="c92b9-121">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="c92b9-121">Close the page.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]