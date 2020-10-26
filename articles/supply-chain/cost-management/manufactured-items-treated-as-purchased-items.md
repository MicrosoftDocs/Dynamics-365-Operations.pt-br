---
title: Configurar produtos que podem ser produzidos ou obtidos
description: Os produtos podem ser fornecidos de várias maneiras - podem ser produzidos (manufaturados) ou comprados (adquiridos). Este artigo descreve alguns pontos típicos a serem considerados quando você configura produtos para oferecer suporte de várias fontes.
author: cvocph
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqGroup, ReqItemTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 21841
ms.assetid: acc608b7-2cad-4fba-afee-9b7cc93761ec
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d9b5ba58703e636308d83a94ecc2e27e44812c49
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/10/2020
ms.locfileid: "3981526"
---
# <a name="set-up-products-that-can-be-produced-or-procured"></a><span data-ttu-id="286b9-104">Configurar produtos que podem ser produzidos ou obtidos</span><span class="sxs-lookup"><span data-stu-id="286b9-104">Set up products that can be produced or procured</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="286b9-105">Os produtos podem ser fornecidos de várias maneiras - podem ser produzidos (manufaturados) ou comprados (adquiridos).</span><span class="sxs-lookup"><span data-stu-id="286b9-105">Products can be sourced in various ways -  they can be produced (manufactured) or procured (purchased).</span></span> <span data-ttu-id="286b9-106">Este artigo descreve alguns pontos típicos a serem considerados quando você configura produtos para oferecer suporte de várias fontes.</span><span class="sxs-lookup"><span data-stu-id="286b9-106">This article describes some typical points to consider when you configure products to support multi-sourcing.</span></span> 

<span data-ttu-id="286b9-107">Várias fontes geralmente são usadas para um item comprado que é fabricado ocasionalmente, ou quando um item que era um item fabricado é alterado, de forma que agora seja um item comprado.</span><span class="sxs-lookup"><span data-stu-id="286b9-107">Multi-sourcing is typically used for a purchased item that is occasionally manufactured, or when an item that was primarily a manufactured item is changed so that it's now primarily a purchased item.</span></span> <span data-ttu-id="286b9-108">O item primeiro é designado como item fabricado para definir se as informações sobre a lista de materiais (BOM) e sobre o roteiro podem ser definidas, e para dar suporte a ordens de produção do item.</span><span class="sxs-lookup"><span data-stu-id="286b9-108">The item is first designated as a manufactured item, so that bill of materials (BOM) and route information can be defined, and to support production orders for the item.</span></span> <span data-ttu-id="286b9-109">O tipo de produção deve ser definido como **BOM** (ou, para processo de fabricação, **Fórmula** ou **Coproduto**).</span><span class="sxs-lookup"><span data-stu-id="286b9-109">The production type should be set to **BOM** (or, for process manufacturing, **Formula** or **Co-Product**).</span></span>

<span data-ttu-id="286b9-110">Quando você usa custo padrão, o registro de custo do item pode ser calculado para o item fabricado.</span><span class="sxs-lookup"><span data-stu-id="286b9-110">When you use standard cost, the item cost record can be calculated for the manufactured item.</span></span> <span data-ttu-id="286b9-111">No entanto, o registro de custo do item pode não corresponder ao custo padrão que você deseja para fins de compra.</span><span class="sxs-lookup"><span data-stu-id="286b9-111">However, the item cost record might not match the standard cost that you want for purchasing purposes.</span></span> <span data-ttu-id="286b9-112">Neste caso, o custo padrão deve ser inserido manualmente e ativado para o registro de custo do item.</span><span class="sxs-lookup"><span data-stu-id="286b9-112">In this case, the standard cost must be manually entered and activated for the item cost record.</span></span> <span data-ttu-id="286b9-113">Para o cálculo do custo, use uma BOM e roteiro especiais que representem a combinação da fonte de produtos ao longo de um período fiscal, para minimizar as variações ao longo do tempo.</span><span class="sxs-lookup"><span data-stu-id="286b9-113">For the cost calculation, consider using a special BOM and route that represent the supply mix of the product over the course of a fiscal period, to minimize the variances over time.</span></span> <span data-ttu-id="286b9-114">Além disso, um item fabricado em um site pode ser transferido para outro site.</span><span class="sxs-lookup"><span data-stu-id="286b9-114">Additionally, a manufactured item at one site can be transferred to another site.</span></span> <span data-ttu-id="286b9-115">Portanto, o custo do item deve ser inserido e ativado manualmente no site para o qual o item será transferido.</span><span class="sxs-lookup"><span data-stu-id="286b9-115">Therefore, the item's cost must be manually entered and activated for the site that the item is transferred to.</span></span> <span data-ttu-id="286b9-116">Quando você usa um item fabricado como um componente em produtos de alto nível, os custos do componente devem ser tratados como um item comprado.</span><span class="sxs-lookup"><span data-stu-id="286b9-116">When you use the manufactured item as a component in higher-level products, the component's costs should be treated as a purchased item.</span></span> <span data-ttu-id="286b9-117">Esta diretriz é aplicada, independentemente de os custos do componente serem calculados ou inseridos manualmente.</span><span class="sxs-lookup"><span data-stu-id="286b9-117">This guideline applies, regardless of whether the component’s costs were calculated or manually entered.</span></span> <span data-ttu-id="286b9-118">Em outras palavras, um cálculo de BOM deve tratar os custos do item como um componente comprado, em vez de usar informações de roteiro e de BOM do item para calcular custos.</span><span class="sxs-lookup"><span data-stu-id="286b9-118">In other words, a BOM calculation should treat the item's costs as a purchased component instead of using the item's BOM and route information to calculate costs.</span></span> 

<span data-ttu-id="286b9-119">Para impedir o cálculo, selecione o sinalizador **Parar detalhamento** que é incorporado no grupo de cálculo de BOM atribuído ao item.</span><span class="sxs-lookup"><span data-stu-id="286b9-119">To prevent the calculation from occurring, select the **Stop explosion** flag that is embedded in the BOM calculation group that is assigned to the item.</span></span> <span data-ttu-id="286b9-120">Para impedir que os cálculos de planejamento mestre detalhem os requisitos no item, defina o limite de detalhamento para 0 (zero) dias na cobertura do item ou no grupo de cobertura.</span><span class="sxs-lookup"><span data-stu-id="286b9-120">To prevent master scheduling calculations from exploding requirements through the item, set the explosion fence to 0 (zero) days in item coverage or in the coverage group.</span></span> <span data-ttu-id="286b9-121">O cálculo do agendamento mestre tratará o item como comprado e não executará mais cálculos para as informações de roteiro e de BOM do item.</span><span class="sxs-lookup"><span data-stu-id="286b9-121">The master scheduling calculation will then treat the item as a purchased item and won't perform more calculations for the item's BOM and route information.</span></span>





