--- 
title: "Digitar um acréscimo a um ativo fixo"
description: "Este procedimento mostra como adicionar um acréscimo a um ativo fixo existente."
author: saraschi2
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 3579148033023f648e1a78a3dd009018f153fdad
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---
# <a name="enter-an-addition-to-a-fixed-asset"></a><span data-ttu-id="0b628-103">Digitar um acréscimo a um ativo fixo</span><span class="sxs-lookup"><span data-stu-id="0b628-103">Enter an addition to a fixed asset</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="0b628-104">Este procedimento mostra como adicionar um acréscimo a um ativo fixo existente.</span><span class="sxs-lookup"><span data-stu-id="0b628-104">This procedure shows how to add an addition to an existing fixed asset.</span></span> <span data-ttu-id="0b628-105">A finalidade das adições de ativo fixo são rastrear adições, manutenção, ou melhorias de um ativo fixo, além de serem informacionais.</span><span class="sxs-lookup"><span data-stu-id="0b628-105">The purpose of Fixed asset additions is to track item additions, maintenance, or improvements for an asset, and is informational only.</span></span> <span data-ttu-id="0b628-106">Algumas alterações para métodos de depreciação de ativos ou a vida útil devem ser feitas separadamente.</span><span class="sxs-lookup"><span data-stu-id="0b628-106">Any changes to the fixed asset value or service life must be made separately.</span></span>   



<span data-ttu-id="0b628-107">O procedimento usa a função de contador e os dados de demonstração da entidade legal de USMF.</span><span class="sxs-lookup"><span data-stu-id="0b628-107">The procedure uses the Accountant role and demo data for the USMF legal entity.</span></span>

1. <span data-ttu-id="0b628-108">Vá para Ativos fixos > Ativos fixos > Ativos fixos.</span><span class="sxs-lookup"><span data-stu-id="0b628-108">Go to Fixed assets > Fixed assets > Fixed assets.</span></span>
2. <span data-ttu-id="0b628-109">Na lista, localize e selecione o ativo fixo que você deseja adicionar.</span><span class="sxs-lookup"><span data-stu-id="0b628-109">In the list, find and select the fixed asset for the addition.</span></span>
3. <span data-ttu-id="0b628-110">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="0b628-110">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="0b628-111">No Painel de Ação, clique em Ativo fixo.</span><span class="sxs-lookup"><span data-stu-id="0b628-111">On the Action Pane, click Fixed asset.</span></span>
5. <span data-ttu-id="0b628-112">Clique em Acréscimos de ativo fixo.</span><span class="sxs-lookup"><span data-stu-id="0b628-112">Click Fixed asset additions.</span></span>
6. <span data-ttu-id="0b628-113">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="0b628-113">Click New.</span></span>
7. <span data-ttu-id="0b628-114">No campo Nome, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="0b628-114">In the Name field, type a value.</span></span>
8. <span data-ttu-id="0b628-115">Defina a data de compra ou de serviço de adição.</span><span class="sxs-lookup"><span data-stu-id="0b628-115">Set the date of the addition purchase or service.</span></span>
9. <span data-ttu-id="0b628-116">Insira o custo do item, manutenção ou outro aperfeiçoamento para o ativo.</span><span class="sxs-lookup"><span data-stu-id="0b628-116">Enter the cost of the item, maintenance, or other improvement for the asset.</span></span>
10. <span data-ttu-id="0b628-117">No campo Quantidade, insira um número.</span><span class="sxs-lookup"><span data-stu-id="0b628-117">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="0b628-118">Os custos totais não terão nenhum efeito no valor do ativo fixo e são para fins de rastreamento e informação.</span><span class="sxs-lookup"><span data-stu-id="0b628-118">The total cost will have no impact on the value of the fixed asset and is for tracking and informational purposes only.</span></span> <span data-ttu-id="0b628-119">Se os custos serão capitalizados, então um texto de transação de ajuste deve ser postado separadamente.</span><span class="sxs-lookup"><span data-stu-id="0b628-119">If the cost will be capitalized, then a write-up adjustment transaction must be posted separately.</span></span>  
11. <span data-ttu-id="0b628-120">Clique na guia Geral.</span><span class="sxs-lookup"><span data-stu-id="0b628-120">Click the General tab.</span></span>
    * <span data-ttu-id="0b628-121">Defina Aumento da vida útil se a adição aumentar a vida útil do ativo.</span><span class="sxs-lookup"><span data-stu-id="0b628-121">Set Increases service life if the addition increases the service life of the asset.</span></span>  
    * <span data-ttu-id="0b628-122">Este campo serve somente para informar.</span><span class="sxs-lookup"><span data-stu-id="0b628-122">This field is informational only.</span></span> <span data-ttu-id="0b628-123">Para aumentar a vida útil, modifique a vida útil nos métodos de depreciação e/ou registros de depreciações para o ativo.</span><span class="sxs-lookup"><span data-stu-id="0b628-123">To increase the service life, modify the Service life on the Value models and/or Depreciation books for the asset.</span></span>  

