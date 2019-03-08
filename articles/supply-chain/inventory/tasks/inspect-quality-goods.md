---
title: Verificar a qualidade de mercadorias
description: Este procedimento mostra como processar a ordem de qualidade.
author: perlynne
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventQualityOrderTable, InventQualityOrderLineResults, HcmWorkerLookUp
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f9e9d750f116db62519ac7148f19bf62050430e9
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "315420"
---
# <a name="inspect-the-quality-of-goods"></a><span data-ttu-id="a50a1-103">Verificar a qualidade de mercadorias</span><span class="sxs-lookup"><span data-stu-id="a50a1-103">Inspect the quality of goods</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="a50a1-104">Este procedimento mostra como processar a ordem de qualidade.</span><span class="sxs-lookup"><span data-stu-id="a50a1-104">This procedure shows you how to process a quality order.</span></span> <span data-ttu-id="a50a1-105">Você pode executar este guia na empresa USMF de dados de demonstração.</span><span class="sxs-lookup"><span data-stu-id="a50a1-105">You can run this guide in demo data company USMF.</span></span> <span data-ttu-id="a50a1-106">Antes de iniciar este procedimento de exemplo, você precisa confirmar a ordem de compra '000016'e lançar um recebimento de produtos.</span><span class="sxs-lookup"><span data-stu-id="a50a1-106">Before you start this example procedure, you need to confirm purchase order “000016” and post a product receipt.</span></span> <span data-ttu-id="a50a1-107">Isso criará automaticamente uma ordem de qualidade.</span><span class="sxs-lookup"><span data-stu-id="a50a1-107">This will automatically create a quality order.</span></span> <span data-ttu-id="a50a1-108">As inspeções de qualidade são realizadas tipicamente por um vendedor de qualidade.</span><span class="sxs-lookup"><span data-stu-id="a50a1-108">Quality inspections are typically carried out by a quality clerk.</span></span>


## <a name="select-a-quality-order"></a><span data-ttu-id="a50a1-109">Selecione uma ordem de qualidade</span><span class="sxs-lookup"><span data-stu-id="a50a1-109">Select a quality order</span></span>
1. <span data-ttu-id="a50a1-110">Vá para Gerenciamento de estoque > Tarefas periódicas > Gerenciamento de qualidade > Ordens de qualidade.</span><span class="sxs-lookup"><span data-stu-id="a50a1-110">Go to Inventory management > Periodic tasks > Quality management > Quality orders.</span></span>
2. <span data-ttu-id="a50a1-111">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="a50a1-111">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="a50a1-112">Selecione a ordem de qualidade que foi criada antes do início deste procedimento.</span><span class="sxs-lookup"><span data-stu-id="a50a1-112">Select the quality order that was created before you started this procedure.</span></span>  

## <a name="record-test-results"></a><span data-ttu-id="a50a1-113">Registrar resultados do teste</span><span class="sxs-lookup"><span data-stu-id="a50a1-113">Record test results</span></span>
1. <span data-ttu-id="a50a1-114">Clique em Resultados.</span><span class="sxs-lookup"><span data-stu-id="a50a1-114">Click Results.</span></span>
2. <span data-ttu-id="a50a1-115">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="a50a1-115">Click Edit.</span></span>
3. <span data-ttu-id="a50a1-116">No campo Quantidade de resultado, insira um número.</span><span class="sxs-lookup"><span data-stu-id="a50a1-116">In the Result quantity field, enter a number.</span></span>
4. <span data-ttu-id="a50a1-117">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="a50a1-117">In the list, mark the selected row.</span></span>
5. <span data-ttu-id="a50a1-118">No campo Resultado, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="a50a1-118">In the Outcome field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="a50a1-119">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="a50a1-119">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="a50a1-120">Neste exemplo o resultado é baseado em um resultado predefinido.</span><span class="sxs-lookup"><span data-stu-id="a50a1-120">In this example the result is based on a pre-defined outcome.</span></span> <span data-ttu-id="a50a1-121">Normalmente você registraria um resultado de teste mais específico por exemplo, um tamanho ou outra dimensão.</span><span class="sxs-lookup"><span data-stu-id="a50a1-121">Normally you would record a more specific test result, for example a size or other dimension.</span></span>  
7. <span data-ttu-id="a50a1-122">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="a50a1-122">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="a50a1-123">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="a50a1-123">Click Save.</span></span>
9. <span data-ttu-id="a50a1-124">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="a50a1-124">Close the page.</span></span>

## <a name="validate-the-quality-order"></a><span data-ttu-id="a50a1-125">Validar a ordem de qualidade</span><span class="sxs-lookup"><span data-stu-id="a50a1-125">Validate the quality order</span></span>
1. <span data-ttu-id="a50a1-126">Clique em Validar.</span><span class="sxs-lookup"><span data-stu-id="a50a1-126">Click Validate.</span></span>
2. <span data-ttu-id="a50a1-127">No campo Validado por, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="a50a1-127">In the Validated by field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="a50a1-128">Selecione o usuário realizando a inspeção.</span><span class="sxs-lookup"><span data-stu-id="a50a1-128">Select the user performing the inspection.</span></span>  
3. <span data-ttu-id="a50a1-129">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="a50a1-129">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="a50a1-130">Clique em Selecionar.</span><span class="sxs-lookup"><span data-stu-id="a50a1-130">Click Select.</span></span>
5. <span data-ttu-id="a50a1-131">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="a50a1-131">Click OK.</span></span>
6. <span data-ttu-id="a50a1-132">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="a50a1-132">Close the page.</span></span>

