--- 
title: Configurar encargos suplementares do hub e mestres suplementares
description: Este procedimento mostra como criar um mestre suplementar para um hub e usar esse mestre para criar um encargo suplementar do hub.
author: BibiSp
manager: AnnBe
ms.date: 11/11/2016
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
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 6d09e32c9e2c41c49e376320d507593849f68cb0
ms.contentlocale: pt-br
ms.lasthandoff: 04/13/2018

---
# <a name="set-up-hub-accessorial-charges-and-accessorial-masters"></a><span data-ttu-id="99dca-103">Configurar encargos suplementares do hub e mestres suplementares</span><span class="sxs-lookup"><span data-stu-id="99dca-103">Set up hub accessorial charges and accessorial masters</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="99dca-104">Este procedimento mostra como criar um mestre suplementar para um hub e usar esse mestre para criar um encargo suplementar do hub.</span><span class="sxs-lookup"><span data-stu-id="99dca-104">This procedure shows how to create an accessorial master for a hub and use that master to create a hub accessorial charge.</span></span> <span data-ttu-id="99dca-105">O procedimento usa o conjunto de dados USMF.</span><span class="sxs-lookup"><span data-stu-id="99dca-105">The procedure uses the USMF dataset.</span></span> <span data-ttu-id="99dca-106">Essa configuração será feita tipicamente por um coordenador de transporte.</span><span class="sxs-lookup"><span data-stu-id="99dca-106">This set up will typically be done by a transportation coordinator.</span></span>


## <a name="set-up-a-hub-master"></a><span data-ttu-id="99dca-107">Configurar um mestre de hub</span><span class="sxs-lookup"><span data-stu-id="99dca-107">Set up a hub master</span></span>
1. <span data-ttu-id="99dca-108">Vá para Gerenciamento de transporte > Configurar > Classificação > Mestres suplementares.</span><span class="sxs-lookup"><span data-stu-id="99dca-108">Go to Transportation management > Setup > Rating > Accessorial masters.</span></span>
2. <span data-ttu-id="99dca-109">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="99dca-109">Click New.</span></span>
3. <span data-ttu-id="99dca-110">No campo Mestre suplementar, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="99dca-110">In the Accessorial master field, type a value.</span></span>
4. <span data-ttu-id="99dca-111">No campo Nome, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="99dca-111">In the Name field, type a value.</span></span>
5. <span data-ttu-id="99dca-112">No campo Tipo de acessório, selecione 'Hub'.</span><span class="sxs-lookup"><span data-stu-id="99dca-112">In the Accessorial type field, select 'Hub'.</span></span>
6. <span data-ttu-id="99dca-113">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="99dca-113">Click Save.</span></span>
7. <span data-ttu-id="99dca-114">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="99dca-114">Close the page.</span></span>

## <a name="set-up-a-hub-accessorial-charge"></a><span data-ttu-id="99dca-115">Configurar um encargo suplementar do hub</span><span class="sxs-lookup"><span data-stu-id="99dca-115">Set up a hub accessorial charge</span></span>
1. <span data-ttu-id="99dca-116">Vá para Gerenciamento de transporte > Configurar > Classificação > Encargos suplementares do hub.</span><span class="sxs-lookup"><span data-stu-id="99dca-116">Go to Transportation management > Setup > Rating > Hub accessorial charges.</span></span>
2. <span data-ttu-id="99dca-117">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="99dca-117">Click New.</span></span>
3. <span data-ttu-id="99dca-118">No campo ID suplementar do hub, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="99dca-118">In the Hub accessorial ID field, type a value.</span></span>
4. <span data-ttu-id="99dca-119">No campo Hub, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="99dca-119">In the Hub field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="99dca-120">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="99dca-120">In the list, find and select the desired record.</span></span>
6. <span data-ttu-id="99dca-121">No campo Posição do hub, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="99dca-121">In the Hub position field, select an option.</span></span>
    * <span data-ttu-id="99dca-122">Você pode criar o encargo como uma retirada ou uma entrega.</span><span class="sxs-lookup"><span data-stu-id="99dca-122">You can either create the charge as a pickup or drop-off.</span></span> <span data-ttu-id="99dca-123">Dependendo da sua escolha, o encargo será aplicado ao segmento de transporte correspondente na sua rota.</span><span class="sxs-lookup"><span data-stu-id="99dca-123">Depending on your selection the charge will be applied to the corresponding transportation segment on your route.</span></span>  
7. <span data-ttu-id="99dca-124">No campo Mestre suplementar, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="99dca-124">In the Accessorial master field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="99dca-125">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="99dca-125">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="99dca-126">Selecione o mestre que você acabou de criar.</span><span class="sxs-lookup"><span data-stu-id="99dca-126">Select the master you just created.</span></span>  
9. <span data-ttu-id="99dca-127">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="99dca-127">Click Save.</span></span>
10. <span data-ttu-id="99dca-128">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="99dca-128">Close the page.</span></span>


