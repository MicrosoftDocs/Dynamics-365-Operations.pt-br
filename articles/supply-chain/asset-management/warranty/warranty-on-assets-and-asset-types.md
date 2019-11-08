---
title: Garantias em ativos e tipos de ativo
description: Este tópico explica como configurar garantias em ativos e tipos de ativos no Gerenciamento de Ativos.
author: josaw1
manager: AnnBe
ms.date: 08/30/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 6e69b471af0853159ba807af5f39db64dbbb04f8
ms.sourcegitcommit: d37fb09101c30858bcb975931b3d8f947d72017b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/10/2019
ms.locfileid: "2569699"
---
# <a name="warranties-on-assets-and-asset-types"></a><span data-ttu-id="708e2-103">Garantias em ativos e tipos de ativo</span><span class="sxs-lookup"><span data-stu-id="708e2-103">Warranties on assets and asset types</span></span>

[!include [banner](../../includes/banner.md)]

 


<span data-ttu-id="708e2-104">Este tópico explica como configurar garantias em ativos e tipos de ativos no Gerenciamento de Ativos.</span><span class="sxs-lookup"><span data-stu-id="708e2-104">This topic explains how to set up warranties on assets and asset types in Asset Management.</span></span>

## <a name="set-up-a-warranty-on-an-asset-type"></a><span data-ttu-id="708e2-105">Configurar uma garantia em um tipo de ativo</span><span class="sxs-lookup"><span data-stu-id="708e2-105">Set up a warranty on an asset type</span></span>

1. <span data-ttu-id="708e2-106">Selecione **Gerenciamento de ativos** \> **Configuração** \> **Tipos de ativo** \> **Tipos de ativo**.</span><span class="sxs-lookup"><span data-stu-id="708e2-106">Select **Asset management** \> **Setup** \> **Asset types** \> **Asset types**.</span></span>
2. <span data-ttu-id="708e2-107">No painel à esquerda, selecione o tipo de ativo ao qual deseja anexar o contrato de garantia do fornecedor, e depois selecione **Padrões de tipo de ativo**.</span><span class="sxs-lookup"><span data-stu-id="708e2-107">In the left pane, select the asset type to attach a vendor warranty agreement to, and then select **Asset type defaults**.</span></span>
3. <span data-ttu-id="708e2-108">Na Guia Rápida **Geral**, no campo **Garantia do fornecedor**, selecione o contrato.</span><span class="sxs-lookup"><span data-stu-id="708e2-108">On the **General** FastTab, in the **Vendor warranty** field, select the agreement.</span></span>

## <a name="set-up-a-warranty-on-an-asset"></a><span data-ttu-id="708e2-109">Configurar uma garantia em um ativo</span><span class="sxs-lookup"><span data-stu-id="708e2-109">Set up a warranty on an asset</span></span>

1. <span data-ttu-id="708e2-110">Selecione **Gerenciamento de ativos** \> **Comum** \> **Ativos** \> **Todos os ativos**.</span><span class="sxs-lookup"><span data-stu-id="708e2-110">Select **Asset management** \> **Common** \> **Assets** \> **All assets**.</span></span>
2. <span data-ttu-id="708e2-111">Selecione o ativo, e depois **Editar**.</span><span class="sxs-lookup"><span data-stu-id="708e2-111">Select the asset, and then select **Edit**.</span></span>
3. <span data-ttu-id="708e2-112">Na Guia Rápida **Fornecedor**, na seção **Garantia de fornecedor**, no campo **Garantia**, selecione o contrato de garantia.</span><span class="sxs-lookup"><span data-stu-id="708e2-112">On the **Vendor** FastTab, in the **Vendor warranty** section, in the **Warranty** field, select the warranty agreement.</span></span>
4. <span data-ttu-id="708e2-113">Nos campos **Data de início de garantia** e **Data de término de garantia**, selecione as datas de início e de término.</span><span class="sxs-lookup"><span data-stu-id="708e2-113">In the **Warranty start** and **Warranty end** fields, select the start and end dates.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="708e2-114">Se uma data for selecionada no campo **Início da garantia** em uma ordem de serviço, a garantia se torna válida para a ordem de serviço nessa data.</span><span class="sxs-lookup"><span data-stu-id="708e2-114">If a date is selected in the **Warranty start** field on a work order, the warranty becomes valid for the work order on that date.</span></span> <span data-ttu-id="708e2-115">Quando você cria uma ordem de serviço, o campo **Início da garantia** está automaticamente definido para o dia da criação.</span><span class="sxs-lookup"><span data-stu-id="708e2-115">When you create a work order, the **Warranty start** field is automatically set to the date of creation.</span></span> <span data-ttu-id="708e2-116">Entretanto, você pode alterar a data para que ela corresponda a, por exemplo, a data de início de um contrato de garantia.</span><span class="sxs-lookup"><span data-stu-id="708e2-116">However, you can change the date so that it corresponds to, for example, the start date of a warranty agreement.</span></span>
    >
    > ![Página de ordens de serviço](media/02-warranty.png)

> [!NOTE]
> <span data-ttu-id="708e2-118">Quando você cria uma ordem de serviço para um ativo que está incluído na garantia de um fornecedor, se a ordem de serviço tiver uma data de início esperada durante o período de garantia, você receberá uma notificação sobre o acordo da garantia.</span><span class="sxs-lookup"><span data-stu-id="708e2-118">When you create a work order for an asset that is covered by a vendor warranty, if the work order has an expected start date during the warranty period, you receive a notification about the warranty agreement.</span></span> <span data-ttu-id="708e2-119">Então, você pode cancelar a ordem de serviço, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="708e2-119">You can then cancel the work order, as you require.</span></span>
