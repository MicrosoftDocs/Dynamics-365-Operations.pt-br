---
title: Configurar atribuições suplementares
description: Este procedimento mostra como iniciar uma atribuição suplementar.
author: ShylaThompson
manager: tfehr
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TMSAccessorialAssignment
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8d7f48da374a0434130f2cf95bf77a126635cd63
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "4422555"
---
# <a name="set-up-accessorial-assignments"></a><span data-ttu-id="46b8f-103">Configurar atribuições suplementares</span><span class="sxs-lookup"><span data-stu-id="46b8f-103">Set up accessorial assignments</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="46b8f-104">Este procedimento mostra como iniciar uma atribuição suplementar.</span><span class="sxs-lookup"><span data-stu-id="46b8f-104">This procedure shows how to set up an accessorial assignment.</span></span> <span data-ttu-id="46b8f-105">Normalmente isso é feito por um coordenador de transporte.</span><span class="sxs-lookup"><span data-stu-id="46b8f-105">This is typically done by a transportation coordinator.</span></span> <span data-ttu-id="46b8f-106">Antes de você usar este guia você precisa executar o guia "Instalar hub de encargos e mestres suplementares".</span><span class="sxs-lookup"><span data-stu-id="46b8f-106">Before you use this guide you need to run the "Set up hub accessorial charges and accessorial masters" guide.</span></span>


## <a name="set-up-accessorial-assignment"></a><span data-ttu-id="46b8f-107">Configurar Atribuição suplementar</span><span class="sxs-lookup"><span data-stu-id="46b8f-107">Set up Accessorial assignment</span></span>
1. <span data-ttu-id="46b8f-108">Vá para Gerenciamento de transporte > Configurar > Classificação > Atribuições suplementares.</span><span class="sxs-lookup"><span data-stu-id="46b8f-108">Go to Transportation management > Setup > Rating > Accessorial assignments.</span></span>
2. <span data-ttu-id="46b8f-109">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="46b8f-109">Click New.</span></span>
3. <span data-ttu-id="46b8f-110">No campo Nome, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="46b8f-110">In the Name field, type a value.</span></span>
4. <span data-ttu-id="46b8f-111">Ative a expansão da seção Detalhes.</span><span class="sxs-lookup"><span data-stu-id="46b8f-111">Toggle the expansion of the Details section.</span></span>
5. <span data-ttu-id="46b8f-112">No campo Hub, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="46b8f-112">In the Hub field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="46b8f-113">Na lista, selecione o Hub para o qual você criou um mestre suplementar quando executou o guia "Instalar hub de encargos e mestres suplementares".</span><span class="sxs-lookup"><span data-stu-id="46b8f-113">In the list, select the Hub that you created an accessorial master for when you ran the "Set up hub accessorial charges and accessorial masters" guide.</span></span> 
7. <span data-ttu-id="46b8f-114">No campo ID suplementar do Hub, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="46b8f-114">In the Hub accessorial ID field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="46b8f-115">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="46b8f-115">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="46b8f-116">Ative a expansão da seção Critérios.</span><span class="sxs-lookup"><span data-stu-id="46b8f-116">Toggle the expansion of the Criteria section.</span></span>
    * <span data-ttu-id="46b8f-117">Na seção Critérios, você pode escolher os critérios exatos para quando o encargo deve ser aplicado, com base nos diferentes valores oferecidos aqui.</span><span class="sxs-lookup"><span data-stu-id="46b8f-117">In the Criteria section you can choose the exact criteria for when the charge should apply, based on the different values offered here.</span></span>  
10. <span data-ttu-id="46b8f-118">Definir a opção Sempre aplicar para Sim.</span><span class="sxs-lookup"><span data-stu-id="46b8f-118">Set the Always apply option to Yes.</span></span>
11. <span data-ttu-id="46b8f-119">No campo Nível de atribuição suplementar, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="46b8f-119">In the Accessorial assignment level field, select an option.</span></span>
12. <span data-ttu-id="46b8f-120">Ative a expansão da seção Cálculos.</span><span class="sxs-lookup"><span data-stu-id="46b8f-120">Toggle the expansion of the Calculation section.</span></span>
13. <span data-ttu-id="46b8f-121">No campo Tipo de taxa suplementar, selecione 'Fixa'.</span><span class="sxs-lookup"><span data-stu-id="46b8f-121">In the Accessorial fee type field, select 'Flat'.</span></span>
    * <span data-ttu-id="46b8f-122">O Tipo de taxa suplementar determina como calcular o encargo real.</span><span class="sxs-lookup"><span data-stu-id="46b8f-122">The Accessorial fee type determines how to calculate the actual charge.</span></span> <span data-ttu-id="46b8f-123">Neste exemplo é um encargo fixo.</span><span class="sxs-lookup"><span data-stu-id="46b8f-123">In this example it's a flat charge.</span></span>  
14. <span data-ttu-id="46b8f-124">No campo Taxa suplementar, insira um número.</span><span class="sxs-lookup"><span data-stu-id="46b8f-124">In the Accessorial fee field, enter a number.</span></span>
15. <span data-ttu-id="46b8f-125">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="46b8f-125">Click Save.</span></span>

