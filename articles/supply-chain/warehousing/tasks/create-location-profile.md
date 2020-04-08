---
title: Criar um perfil de localização
description: Este tópico explica como criar um perfil de localização no Dynamics 365 Supply Chain Management.
author: ShylaThompson
manager: AnnBe
ms.date: 07/29/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLocationProfile
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 764d1dc1d7fb54e0fa14a681d6d3cdb1d829aa57
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3146114"
---
# <a name="create-a-location-profile"></a><span data-ttu-id="b62df-103">Criar um perfil de localização</span><span class="sxs-lookup"><span data-stu-id="b62df-103">Create a location profile</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="b62df-104">Este tópico explica como criar um perfil de localização no Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="b62df-104">This topic explains how to create a location profile in Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="b62df-105">Cada local no depósito precisa ter um perfil de local associado a ele, que descreve as propriedades do local, por exemplo, se o local permite itens mistos.</span><span class="sxs-lookup"><span data-stu-id="b62df-105">Every location in the warehouse needs to have a location profile associated with it that describes the properties of the location, for example, whether the location allows mixed items.</span></span> <span data-ttu-id="b62df-106">Neste procedimento é criaremos um perfil para um local que não exija o controle de matrícula.</span><span class="sxs-lookup"><span data-stu-id="b62df-106">In this procedure we'll create a profile for a location that doesn't require license plate control.</span></span> <span data-ttu-id="b62df-107">Nós habilitaremos misturados itens, e o status de estoque e permitimos misturados, a contagem cíclica.</span><span class="sxs-lookup"><span data-stu-id="b62df-107">We'll enable mixed items, and mixed inventory statuses, and allow cycle counting.</span></span> <span data-ttu-id="b62df-108">Você pode usar este procedimento na empresa USMF de dados de demonstração.</span><span class="sxs-lookup"><span data-stu-id="b62df-108">You can use this procedure in the USMF demo data company.</span></span>


1. <span data-ttu-id="b62df-109">No Painel de Navegação, vá para **Módulos > Gerenciamento de depósito > Configuração > Depósito > Perfis de localização**.</span><span class="sxs-lookup"><span data-stu-id="b62df-109">In the navigation pane, go to **Modules > Warehouse management > Setup > Warehouse > Location profiles**.</span></span>
2. <span data-ttu-id="b62df-110">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="b62df-110">Select **New**.</span></span>
3. <span data-ttu-id="b62df-111">No campo **ID do perfil de localização**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="b62df-111">In the **Location profile ID** field, type a value.</span></span>
4. <span data-ttu-id="b62df-112">No campo **Nome**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="b62df-112">In the **Name** field, type a value.</span></span>
5. <span data-ttu-id="b62df-113">No campo **Formato de local**, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="b62df-113">In the **Location format** field, enter or select a value.</span></span>
6. <span data-ttu-id="b62df-114">No campo **Tipo de local**, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="b62df-114">In the **Location type** field, enter or select a value.</span></span>
7. <span data-ttu-id="b62df-115">No campo **ID do perfil do gerenciamento de doca**, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="b62df-115">In the **Dock management profile ID** field, enter or select a value.</span></span>
8. <span data-ttu-id="b62df-116">Selecione **Sim** no campo **Permitir itens misturados**.</span><span class="sxs-lookup"><span data-stu-id="b62df-116">Select **Yes** in the **Allow mixed items** field.</span></span>
9. <span data-ttu-id="b62df-117">Selecione **Sim** no campo **Permitir status de estoque misturados**.</span><span class="sxs-lookup"><span data-stu-id="b62df-117">Select **Yes** in the **Allow mixed inventory statuses** field.</span></span>
10. <span data-ttu-id="b62df-118">Selecione **Sim** no campo **Permitir contagem cíclica**.</span><span class="sxs-lookup"><span data-stu-id="b62df-118">Select **Yes** in the **Allow cycle counting** field.</span></span>
11. <span data-ttu-id="b62df-119">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="b62df-119">Select **Save**.</span></span>

