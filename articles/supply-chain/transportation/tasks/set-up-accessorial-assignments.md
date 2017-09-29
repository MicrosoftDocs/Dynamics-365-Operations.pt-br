--- 
title: "Configurar atribuições suplementares"
description: "Este procedimento mostra como iniciar uma atribuição suplementar."
author: BibiSp
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 31787aa180639b934b837b98dc170070d33fd56f
ms.contentlocale: pt-br
ms.lasthandoff: 08/29/2017

---
# <a name="set-up-accessorial-assignments"></a><span data-ttu-id="7451d-103">Configurar atribuições suplementares</span><span class="sxs-lookup"><span data-stu-id="7451d-103">Set up accessorial assignments</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="7451d-104">Este procedimento mostra como iniciar uma atribuição suplementar.</span><span class="sxs-lookup"><span data-stu-id="7451d-104">This procedure shows how to set up an accessorial assignment.</span></span> <span data-ttu-id="7451d-105">Normalmente isso é feito por um coordenador de transporte.</span><span class="sxs-lookup"><span data-stu-id="7451d-105">This is typically done by a transportation coordinator.</span></span> <span data-ttu-id="7451d-106">Antes de você usar este guia você precisa executar o guia "Instalar hub de encargos e mestres suplementares".</span><span class="sxs-lookup"><span data-stu-id="7451d-106">Before you use this guide you need to run the "Set up hub accessorial charges and accessorial masters" guide.</span></span>


## <a name="set-up-accessorial-assignment"></a><span data-ttu-id="7451d-107">Configurar Atribuição suplementar</span><span class="sxs-lookup"><span data-stu-id="7451d-107">Set up Accessorial assignment</span></span>
1. <span data-ttu-id="7451d-108">Vá para Gerenciamento de transporte > Configurar > Classificação > Atribuições suplementares.</span><span class="sxs-lookup"><span data-stu-id="7451d-108">Go to Transportation management > Setup > Rating > Accessorial assignments.</span></span>
2. <span data-ttu-id="7451d-109">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="7451d-109">Click New.</span></span>
3. <span data-ttu-id="7451d-110">No campo Nome, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="7451d-110">In the Name field, type a value.</span></span>
4. <span data-ttu-id="7451d-111">Ative a expansão da seção Detalhes.</span><span class="sxs-lookup"><span data-stu-id="7451d-111">Toggle the expansion of the Details section.</span></span>
5. <span data-ttu-id="7451d-112">No campo Hub, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="7451d-112">In the Hub field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="7451d-113">Na lista, selecione o Hub para o qual você criou um mestre suplementar quando executou o guia "Instalar hub de encargos e mestres suplementares".</span><span class="sxs-lookup"><span data-stu-id="7451d-113">In the list, select the Hub that you created an accessorial master for when you ran the "Set up hub accessorial charges and accessorial masters" guide.</span></span> 
7. <span data-ttu-id="7451d-114">No campo ID suplementar do Hub, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="7451d-114">In the Hub accessorial ID field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="7451d-115">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="7451d-115">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="7451d-116">Ative a expansão da seção Critérios.</span><span class="sxs-lookup"><span data-stu-id="7451d-116">Toggle the expansion of the Criteria section.</span></span>
    * <span data-ttu-id="7451d-117">Na seção Critérios, você pode escolher os critérios exatos para quando o encargo deve ser aplicado, com base nos diferentes valores oferecidos aqui.</span><span class="sxs-lookup"><span data-stu-id="7451d-117">In the Criteria section you can choose the exact criteria for when the charge should apply, based on the different values offered here.</span></span>  
10. <span data-ttu-id="7451d-118">Definir a opção Sempre aplicar para Sim.</span><span class="sxs-lookup"><span data-stu-id="7451d-118">Set the Always apply option to Yes.</span></span>
11. <span data-ttu-id="7451d-119">No campo Nível de atribuição suplementar, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="7451d-119">In the Accessorial assignment level field, select an option.</span></span>
12. <span data-ttu-id="7451d-120">Ative a expansão da seção Cálculos.</span><span class="sxs-lookup"><span data-stu-id="7451d-120">Toggle the expansion of the Calculation section.</span></span>
13. <span data-ttu-id="7451d-121">No campo Tipo de taxa suplementar, selecione 'Fixa'.</span><span class="sxs-lookup"><span data-stu-id="7451d-121">In the Accessorial fee type field, select 'Flat'.</span></span>
    * <span data-ttu-id="7451d-122">O Tipo de taxa suplementar determina como calcular o encargo real.</span><span class="sxs-lookup"><span data-stu-id="7451d-122">The Accessorial fee type determines how to calculate the actual charge.</span></span> <span data-ttu-id="7451d-123">Neste exemplo é um encargo fixo.</span><span class="sxs-lookup"><span data-stu-id="7451d-123">In this example it's a flat charge.</span></span>  
14. <span data-ttu-id="7451d-124">No campo Taxa suplementar, insira um número.</span><span class="sxs-lookup"><span data-stu-id="7451d-124">In the Accessorial fee field, enter a number.</span></span>
15. <span data-ttu-id="7451d-125">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="7451d-125">Click Save.</span></span>


