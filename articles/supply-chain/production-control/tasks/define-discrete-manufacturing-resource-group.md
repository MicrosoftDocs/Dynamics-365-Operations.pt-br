---
title: Definir grupo de recursos de fabricação discreta
description: Um grupo de recursos é um conjunto de recursos de operações que geralmente correspondem à organização física das células de trabalho, definido pelas linhas amarelas no chão da fábrica de produção.
author: sorenva
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WrkCtrResourceGroup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: sorenand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 50733e34bbf14ae2cade6822105da4d8c2120d7d
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "353232"
---
# <a name="define-discrete-manufacturing-resource-group"></a><span data-ttu-id="9d4bb-103">Definir grupo de recursos de fabricação discreta</span><span class="sxs-lookup"><span data-stu-id="9d4bb-103">Define discrete manufacturing resource group</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="9d4bb-104">Um grupo de recursos é um conjunto de recursos de operações que geralmente correspondem à organização física das células de trabalho, definido pelas linhas amarelas no chão da fábrica de produção.</span><span class="sxs-lookup"><span data-stu-id="9d4bb-104">A resource group is a set of operations resources that typically correspond to the physical organization of work cells, defined by yellow lines on the production shop floor.</span></span> <span data-ttu-id="9d4bb-105">Este procedimento mostra como definir um grupo de recursos para uso na produção discreta.</span><span class="sxs-lookup"><span data-stu-id="9d4bb-105">This procedure shows you how to define a ressource group for use in discrete production.</span></span> <span data-ttu-id="9d4bb-106">Você pode ver todo esse procedimento na empresa USMF de dados demo, ou usando seus próprios dados.</span><span class="sxs-lookup"><span data-stu-id="9d4bb-106">You can walk through this procedure in demo data company USMF, or use your own data.</span></span>

1. <span data-ttu-id="9d4bb-107">Ir para grupos de Recurso.</span><span class="sxs-lookup"><span data-stu-id="9d4bb-107">Go to Resource groups.</span></span>
2. <span data-ttu-id="9d4bb-108">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="9d4bb-108">Click New.</span></span>
3. <span data-ttu-id="9d4bb-109">No campo grupo de Recurso, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="9d4bb-109">In the Resource group field, type a value.</span></span>
4. <span data-ttu-id="9d4bb-110">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="9d4bb-110">In the Description field, type a value.</span></span>
5. <span data-ttu-id="9d4bb-111">No campo Local, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="9d4bb-111">In the Site field, enter or select a value.</span></span>
6. <span data-ttu-id="9d4bb-112">No campo unidade de Produção, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="9d4bb-112">In the Production unit field, enter or select a value.</span></span>

## <a name="define-default-operational-parameters"></a><span data-ttu-id="9d4bb-113">Definir parâmetros operacionais padrão</span><span class="sxs-lookup"><span data-stu-id="9d4bb-113">Define default operational parameters</span></span>
1. <span data-ttu-id="9d4bb-114">Expandir a seção Operação.</span><span class="sxs-lookup"><span data-stu-id="9d4bb-114">Expand the Operation section.</span></span>
2. <span data-ttu-id="9d4bb-115">No campo de porcentagem de Sucata, insira um número.</span><span class="sxs-lookup"><span data-stu-id="9d4bb-115">In the Scrap percentage field, enter a number.</span></span>
3. <span data-ttu-id="9d4bb-116">No campo categoria de Configuração, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="9d4bb-116">In the Setup category field, enter or select a value.</span></span>
4. <span data-ttu-id="9d4bb-117">No campo categoria de Tempo de execução, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="9d4bb-117">In the Run time category field, enter or select a value.</span></span>
5. <span data-ttu-id="9d4bb-118">No campo percentual do plano de Operações, insira um número.</span><span class="sxs-lookup"><span data-stu-id="9d4bb-118">In the Operations scheduling percentage field, enter a number.</span></span>

## <a name="define-operating-hours"></a><span data-ttu-id="9d4bb-119">Definir horas de operação</span><span class="sxs-lookup"><span data-stu-id="9d4bb-119">Define operating hours</span></span>
1. <span data-ttu-id="9d4bb-120">Expandir a seção Calendários.</span><span class="sxs-lookup"><span data-stu-id="9d4bb-120">Expand the Calendars section.</span></span>
2. <span data-ttu-id="9d4bb-121">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="9d4bb-121">Click Add.</span></span>
3. <span data-ttu-id="9d4bb-122">No campo Calendário, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="9d4bb-122">In the Calendar field, enter or select a value.</span></span>

## <a name="add-operations-resources"></a><span data-ttu-id="9d4bb-123">Adicionar recursos de operação</span><span class="sxs-lookup"><span data-stu-id="9d4bb-123">Add operations resources</span></span>
1. <span data-ttu-id="9d4bb-124">Expandir a seção Recursos.</span><span class="sxs-lookup"><span data-stu-id="9d4bb-124">Expand the Resources section.</span></span>
2. <span data-ttu-id="9d4bb-125">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="9d4bb-125">Click Add.</span></span>
3. <span data-ttu-id="9d4bb-126">No campo Recurso, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="9d4bb-126">In the Resource field, enter or select a value.</span></span>
4. <span data-ttu-id="9d4bb-127">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="9d4bb-127">Click Add.</span></span>
5. <span data-ttu-id="9d4bb-128">No campo Recurso, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="9d4bb-128">In the Resource field, enter or select a value.</span></span>
6. <span data-ttu-id="9d4bb-129">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="9d4bb-129">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="9d4bb-130">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="9d4bb-130">In the list, click the link in the selected row.</span></span>

