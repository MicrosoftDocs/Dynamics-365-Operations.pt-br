---
title: Visão geral de canais
description: Este tópico apresenta uma visão geral dos canais no Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 8ac188832bdaeba430eed7f08e91a9c2214a0e15
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5219092"
---
# <a name="channels-overview"></a><span data-ttu-id="f23cf-103">Visão geral de canais</span><span class="sxs-lookup"><span data-stu-id="f23cf-103">Channels overview</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="f23cf-104">Este tópico apresenta uma visão geral dos canais no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="f23cf-104">This topic presents an overview of channels in Microsoft Dynamics 365 Commerce.</span></span> <span data-ttu-id="f23cf-105">Inclui informações sobre as tarefas que devem ser concluídas antes e depois de você configurar cada canal.</span><span class="sxs-lookup"><span data-stu-id="f23cf-105">It includes information about the tasks that you must complete both before and after you set up each channel.</span></span>

## <a name="types-of-channels"></a><span data-ttu-id="f23cf-106">Tipos de canais</span><span class="sxs-lookup"><span data-stu-id="f23cf-106">Types of Channels</span></span>

<span data-ttu-id="f23cf-107">O Dynamics 365 Commerce oferece suporte a três diferentes tipos de canal: varejo, call center e online.</span><span class="sxs-lookup"><span data-stu-id="f23cf-107">Dynamics 365 Commerce supports three different channel types: retail, call center, and online channels.</span></span>

### <a name="retail-channels"></a><span data-ttu-id="f23cf-108">Canais de varejo</span><span class="sxs-lookup"><span data-stu-id="f23cf-108">Retail channels</span></span>

<span data-ttu-id="f23cf-109">Os canais de varejo representam as lojas físicas padrão.</span><span class="sxs-lookup"><span data-stu-id="f23cf-109">Retail channels represent standard brick-and-mortar stores.</span></span> <span data-ttu-id="f23cf-110">Cada loja pode ter seus próprios terminais de ponto de venda (PDV), contas de receita e despesa e equipe.</span><span class="sxs-lookup"><span data-stu-id="f23cf-110">Each store can have its own point of sale (POS) registers, income and expense accounts, and staff.</span></span> 

### <a name="call-center-channels"></a><span data-ttu-id="f23cf-111">Canais de call center</span><span class="sxs-lookup"><span data-stu-id="f23cf-111">Call center channels</span></span>

<span data-ttu-id="f23cf-112">Os canais de call center representam o gerenciamento de clientes e de ordens do call center.</span><span class="sxs-lookup"><span data-stu-id="f23cf-112">Call center channels represent call center order and customer management.</span></span>

### <a name="online-channels"></a><span data-ttu-id="f23cf-113">Canais online</span><span class="sxs-lookup"><span data-stu-id="f23cf-113">Online channels</span></span>

<span data-ttu-id="f23cf-114">Os canais online representam as lojas de comércio eletrônico online.</span><span class="sxs-lookup"><span data-stu-id="f23cf-114">Online channels represent online e-Commerce storefronts.</span></span> <span data-ttu-id="f23cf-115">Depois que um canal online é criado, um site deve ser criado usando a ferramenta Construtor de Sites do Microsoft Dynamics 365 Commerce ou outra solução de comércio eletrônico de terceiros.</span><span class="sxs-lookup"><span data-stu-id="f23cf-115">Once an online channel is created, a site must be created using the Microsoft Dynamics 365 Commerce Site Builder tool or other third-party e-Commerce solution.</span></span>

## <a name="channel-setup-basics"></a><span data-ttu-id="f23cf-116">Noções básicas da configuração de canal</span><span class="sxs-lookup"><span data-stu-id="f23cf-116">Channel setup basics</span></span>

<span data-ttu-id="f23cf-117">A configuração de canal é realizada na ferramenta Commerce.</span><span class="sxs-lookup"><span data-stu-id="f23cf-117">Channel set up is performed in the Commerce tool.</span></span> <span data-ttu-id="f23cf-118">Cada canal pode ter seus próprios métodos de pagamento, grupos de preços, hierarquias de produtos, classificações e conjuntos de produtos.</span><span class="sxs-lookup"><span data-stu-id="f23cf-118">Each channel can have its own payment methods, price groups, product hierarchies, assortments, and set of products.</span></span> <span data-ttu-id="f23cf-119">Depois de criar um canal, você atribui os produtos que deseja que a loja contenha e venda.</span><span class="sxs-lookup"><span data-stu-id="f23cf-119">After you create a channel, you assign the products that you want it to carry and sell.</span></span> <span data-ttu-id="f23cf-120">Cada tipo de canal tem um conjunto exclusivo de recursos que podem precisar ser configurados.</span><span class="sxs-lookup"><span data-stu-id="f23cf-120">Each channel type has a unique set of features that may need to be configured.</span></span> <span data-ttu-id="f23cf-121">Por exemplo, um canal de varejo precisa de funcionários, terminais e clientes atribuídos.</span><span class="sxs-lookup"><span data-stu-id="f23cf-121">For example, a retail channel needs assigned employees, registers, and customers.</span></span> <span data-ttu-id="f23cf-122">Depois que um novo canal é criado, ele precisa ser atribuído a uma hierarquia da organização.</span><span class="sxs-lookup"><span data-stu-id="f23cf-122">Once a new channel is created, it needs to be assigned to an organization hierarchy.</span></span>

## <a name="channel-setup-prerequisites"></a><span data-ttu-id="f23cf-123">Pré-requisitos de configuração de canal</span><span class="sxs-lookup"><span data-stu-id="f23cf-123">Channel setup prerequisites</span></span>

<span data-ttu-id="f23cf-124">Para configurar um canal, você deve concluir algumas tarefas de pré-requisito com base no tipo de canal.</span><span class="sxs-lookup"><span data-stu-id="f23cf-124">Before you can set up a channel, you must complete some prerequisite tasks based on the channel type.</span></span> <span data-ttu-id="f23cf-125">Para obter mais informações, consulte [Pré-requisitos de configuração de canal](channels-prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="f23cf-125">For more information, see [Channel setup prerequisites](channels-prerequisites.md).</span></span>

## <a name="set-up-a-channel"></a><span data-ttu-id="f23cf-126">Configurar um canal</span><span class="sxs-lookup"><span data-stu-id="f23cf-126">Set up a channel</span></span>

<span data-ttu-id="f23cf-127">Depois de concluir as tarefas de pré-requisito, para obter mais instruções de configuração, use os links a seguir.</span><span class="sxs-lookup"><span data-stu-id="f23cf-127">After you complete the prerequisite tasks, for further setup instructions, use the following links.</span></span>

- [<span data-ttu-id="f23cf-128">Configurar um canal de varejo</span><span class="sxs-lookup"><span data-stu-id="f23cf-128">Set up a retail channel</span></span>](channel-setup-retail.md)
- [<span data-ttu-id="f23cf-129">Configurar um canal de call center</span><span class="sxs-lookup"><span data-stu-id="f23cf-129">Set up a call center channel</span></span>](channel-setup-callcenter.md)
- [<span data-ttu-id="f23cf-130">Configurar um canal online</span><span class="sxs-lookup"><span data-stu-id="f23cf-130">Set up an online channel</span></span>](channel-setup-online.md)

<!--
## Post-channel configuration

After you create a channel, you may need to complete some of the below tasks:

- [Add channel to an organizational hierarchy](add-channel-org-hierarchy.md)
- Set up fulfillment groups. (LINK TBD)
- Configure the POS registers for the store. (LINK TBD)
- Assign product assortments to the store. (LINK TBD)
- Process assortments to generate the list of products that are included in the assortment and to make the products available in the retail store. (LINK TBD)
- Send data such as number sequences, hardware profiles, and POS screen layouts to the Retail POS registers.(LINK TBD)
- Publish the retail store to send store data to Retail POS. (LINK TBD)
- Run the jobs to send the store data to Retail POS. (LINK TBD)
-->

## <a name="additional-resources"></a><span data-ttu-id="f23cf-131">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="f23cf-131">Additional resources</span></span>

[<span data-ttu-id="f23cf-132">Pré-requisitos de configuração de canal</span><span class="sxs-lookup"><span data-stu-id="f23cf-132">Channel setup prerequisites</span></span>](channels-prerequisites.md)

[<span data-ttu-id="f23cf-133">Configurar um canal de varejo</span><span class="sxs-lookup"><span data-stu-id="f23cf-133">Set up a retail channel</span></span>](channel-setup-retail.md)
    
[<span data-ttu-id="f23cf-134">Configurar um canal online</span><span class="sxs-lookup"><span data-stu-id="f23cf-134">Set up an online channel</span></span>](channel-setup-online.md)

[<span data-ttu-id="f23cf-135">Configurar um canal de call center</span><span class="sxs-lookup"><span data-stu-id="f23cf-135">Set up a call center channel</span></span>](channel-setup-callcenter.md)

[<span data-ttu-id="f23cf-136">Configurar hierarquias da organização</span><span class="sxs-lookup"><span data-stu-id="f23cf-136">Set up organization hierarchies</span></span>](channels-org-hierarchies.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]