---
title: Ativos de entrada e saída
description: Este tópico explica como registrar ativos de entrada e saída em Gerenciamento de Ativos.
author: josaw1
manager: tfehr
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetOutboundObjectsListPage, EntAssetOutboundObjectsDeliver, EntAssetInboundObjectsListPage, EntAssetInboundObjectsRecieve
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: e6dfadf6824c6a3df7be9b3b6f3d9f5dd2749e34
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/16/2021
ms.locfileid: "5018062"
---
# <a name="inbound-and-outbound-assets"></a><span data-ttu-id="4fa90-103">Ativos de entrada e saída</span><span class="sxs-lookup"><span data-stu-id="4fa90-103">Inbound and outbound assets</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="4fa90-104">Se a empresa faz trabalhos de reparo ou trabalhos de manutenção em ativos que são recebidos de outros locais ou clientes, o Gerenciamento de Ativos pode rastrear ativos de entrada que estão sendo enviados à sua empresa e ativos saída que estão sendo devolvidos.</span><span class="sxs-lookup"><span data-stu-id="4fa90-104">If your company does repair jobs or maintenance jobs on assets that are received from other locations or customers, Asset Management can track both inbound assets that are on their way to your company and outbound assets that are being returned.</span></span>

> [!NOTE]
> <span data-ttu-id="4fa90-105">Se quiser usar os estados do ciclo de vida de entrada e saída para gerenciar ativos recebidos e devolvidos, configure os estados do ciclo de vida de solicitação de manutenção e os modelos de ciclo de vida para dar suporte a essas ações.</span><span class="sxs-lookup"><span data-stu-id="4fa90-105">If you want to use inbound and outbound lifecycle states to manage assets that are coming in and being returned, you must set up maintenance request lifecycle states and lifecycle models to support these actions.</span></span> <span data-ttu-id="4fa90-106">Para obter mais informações, consulte [Solicitações de manutenção](../setup-for-maintenance-requests/requests.md).</span><span class="sxs-lookup"><span data-stu-id="4fa90-106">For more information, see [Maintenance requests](../setup-for-maintenance-requests/requests.md).</span></span>

<span data-ttu-id="4fa90-107">A configuração do Gerenciamento de Ativos determina se você pode trabalhar com ativos de entrada e saída.</span><span class="sxs-lookup"><span data-stu-id="4fa90-107">The setup of Asset Management determines whether you can work with inbound and outbound assets.</span></span>

## <a name="register-assets-as-inbound"></a><span data-ttu-id="4fa90-108">Registre ativos como entrada</span><span class="sxs-lookup"><span data-stu-id="4fa90-108">Register assets as inbound</span></span>

1. <span data-ttu-id="4fa90-109">Selecione **Gerenciamento de ativos** \> **Comum** \> **Solicitações de manutenção** \> **Solicitações manutenção de ativos**.</span><span class="sxs-lookup"><span data-stu-id="4fa90-109">Select **Asset management** \> **Common** \> **Maintenance requests** \> **Active maintenance requests**.</span></span>
2. <span data-ttu-id="4fa90-110">Selecione a solicitação de manutenção.</span><span class="sxs-lookup"><span data-stu-id="4fa90-110">Select the maintenance request.</span></span>
3. <span data-ttu-id="4fa90-111">Selecione **Atualizar estado de solicitação de manutenção**.</span><span class="sxs-lookup"><span data-stu-id="4fa90-111">Select **Update maintenance request state**.</span></span>
4. <span data-ttu-id="4fa90-112">Selecione **Entrada** (ou outro estado do ciclo de vida que você criou para ativos de entrada) e **OK**.</span><span class="sxs-lookup"><span data-stu-id="4fa90-112">Select **Inbound** (or another lifecycle state that you've created for inbound assets), and then select **OK**.</span></span>

![Registre ativos como entrada](media/07-manage-maintenance-requests.png)

## <a name="register-inbound-assets-as-received"></a><span data-ttu-id="4fa90-114">Registre ativos de entrada como recebido</span><span class="sxs-lookup"><span data-stu-id="4fa90-114">Register inbound assets as received</span></span>

1. <span data-ttu-id="4fa90-115">Selecione **Gerenciamento de ativos** \> **Comum** \> **Entrada/saída** \> **Ativos de entrada**.</span><span class="sxs-lookup"><span data-stu-id="4fa90-115">Select **Asset management** \> **Common** \> **Inbound/outbound** \> **Inbound assets**.</span></span>
2. <span data-ttu-id="4fa90-116">Selecione o ativo ou a solicitação de manutenção.</span><span class="sxs-lookup"><span data-stu-id="4fa90-116">Select the asset or maintenance request.</span></span>
3. <span data-ttu-id="4fa90-117">Selecione **Receber ativos**.</span><span class="sxs-lookup"><span data-stu-id="4fa90-117">Select **Receive assets**.</span></span>
4. <span data-ttu-id="4fa90-118">No campo **Recebido**, insira a data e a hora.</span><span class="sxs-lookup"><span data-stu-id="4fa90-118">In the **Received** field, enter the date and time.</span></span> <span data-ttu-id="4fa90-119">Em seguida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="4fa90-119">Then select **OK**.</span></span> <span data-ttu-id="4fa90-120">O registro é removido da página de lista **Ativos de entrada**.</span><span class="sxs-lookup"><span data-stu-id="4fa90-120">The record is removed from the **Inbound assets** list page.</span></span>

![Registre ativos de entrada como recebido](media/08-manage-maintenance-requests.png)

## <a name="register-assets-as-outbound"></a><span data-ttu-id="4fa90-122">Registre ativos como saída</span><span class="sxs-lookup"><span data-stu-id="4fa90-122">Register assets as outbound</span></span>

<span data-ttu-id="4fa90-123">Quando terminar o trabalho de manutenção ou de reparo, você pode registrar o ativo como devolvido.</span><span class="sxs-lookup"><span data-stu-id="4fa90-123">When you've completed the maintenance or repair job, you can register the asset as returned.</span></span>

1. <span data-ttu-id="4fa90-124">Selecione **Gerenciamento de ativos** \> **Comum** \> **Solicitações de manutenção** \> **Solicitações manutenção de ativos**.</span><span class="sxs-lookup"><span data-stu-id="4fa90-124">Select **Asset management** \> **Common** \> **Maintenance requests** \> **Active maintenance requests**.</span></span>
2. <span data-ttu-id="4fa90-125">Selecione a solicitação de manutenção.</span><span class="sxs-lookup"><span data-stu-id="4fa90-125">Select the maintenance request.</span></span>
3. <span data-ttu-id="4fa90-126">Selecione **Atualizar estado de solicitação de manutenção**.</span><span class="sxs-lookup"><span data-stu-id="4fa90-126">Select **Update maintenance request state**.</span></span>
4. <span data-ttu-id="4fa90-127">Selecione **Saída** (ou outro estado do ciclo de vida que você criou para ativos de saída) e **OK**.</span><span class="sxs-lookup"><span data-stu-id="4fa90-127">Select **Outbound** (or another lifecycle state that you've created for outbound assets), and then select **OK**.</span></span>

## <a name="register-outbound-assets-as-delivered"></a><span data-ttu-id="4fa90-128">Registre ativos de saída como entregue</span><span class="sxs-lookup"><span data-stu-id="4fa90-128">Register outbound assets as delivered</span></span>

1. <span data-ttu-id="4fa90-129">Selecione **Gerenciamento de ativos** \> **Comum** \> **Entrada/saída** \> **Ativos de saída**.</span><span class="sxs-lookup"><span data-stu-id="4fa90-129">Select **Asset management** \> **Common** \> **Inbound/outbound** \> **Outbound assets**.</span></span>
2. <span data-ttu-id="4fa90-130">Selecione o ativo ou a solicitação de manutenção.</span><span class="sxs-lookup"><span data-stu-id="4fa90-130">Select the asset or maintenance request.</span></span>
3. <span data-ttu-id="4fa90-131">Selecione **Entregar ativos**.</span><span class="sxs-lookup"><span data-stu-id="4fa90-131">Select **Deliver assets**.</span></span>
4. <span data-ttu-id="4fa90-132">No campo **Entregue**, insira a data e a hora.</span><span class="sxs-lookup"><span data-stu-id="4fa90-132">In the **Delivered** field, enter the date and time.</span></span> <span data-ttu-id="4fa90-133">Em seguida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="4fa90-133">Then select **OK**.</span></span> <span data-ttu-id="4fa90-134">O registro é removido da página de lista **Ativos de saída**.</span><span class="sxs-lookup"><span data-stu-id="4fa90-134">The record is removed from the **Outbound assets** list page.</span></span>
