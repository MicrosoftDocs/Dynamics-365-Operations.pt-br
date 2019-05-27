---
title: Configurar realocação de item de pouca seleção
description: Este procedimento mostra como permitir que os trabalhadores do depósito encontrem rapidamente localizações alternativas se não houver estoque suficiente na localização para a qual eles foram direcionados.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWorkException, WHSWorker
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: bf56a0811c4793ee2e3eaf78c8696c3c29e984c3
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1560828"
---
# <a name="set-up-short-picking-item-reallocation"></a><span data-ttu-id="808be-103">Configurar realocação de item de pouca seleção</span><span class="sxs-lookup"><span data-stu-id="808be-103">Set up short picking item reallocation</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="808be-104">Este procedimento mostra como permitir que os trabalhadores do depósito encontrem rapidamente localizações alternativas se não houver estoque suficiente na localização para a qual eles foram direcionados.</span><span class="sxs-lookup"><span data-stu-id="808be-104">This procedure shows you how to enable warehouse workers to quickly find alternative locations if there isn’t sufficient inventory at the location they’ve been directed to.</span></span> <span data-ttu-id="808be-105">É possível usar um processo de realocação automática, que usa as diretivas de localização para recuperar as mercadorias se elas estiverem disponíveis em outras localizações.</span><span class="sxs-lookup"><span data-stu-id="808be-105">It’s possible to use an automatic re-allocation process, which uses location directives to retrieve the goods if they’re available at another location.</span></span> <span data-ttu-id="808be-106">Como alternativa, quando a realocação manual for usada, uma lista das localizações com a quantidade disponível é mostrada no dispositivo móvel, permitindo que o trabalhador do depósito escolha em qual localização usar o estoque.</span><span class="sxs-lookup"><span data-stu-id="808be-106">Alternatively, when manual re-allocation is used, a list of the locations with the available quantity is shown on the mobile device, allowing the warehouse worker to choose which location to use inventory from.</span></span> <span data-ttu-id="808be-107">Você pode usar este procedimento na empresa USMF de dados de demonstração.</span><span class="sxs-lookup"><span data-stu-id="808be-107">You can use this procedure in demo data company USMF.</span></span> <span data-ttu-id="808be-108">Este procedimento é para um recurso que foi adicionado na versão 1611 do Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="808be-108">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="set-up-work-exceptions"></a><span data-ttu-id="808be-109">Configurar exceções de trabalho</span><span class="sxs-lookup"><span data-stu-id="808be-109">Set up work exceptions</span></span>
1. <span data-ttu-id="808be-110">Vá para Gerenciamento de depósito > Configuração > Trabalho > Exceções de trabalho.</span><span class="sxs-lookup"><span data-stu-id="808be-110">Go to Warehouse management > Setup > Work > Work exceptions.</span></span>
2. <span data-ttu-id="808be-111">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="808be-111">Click New.</span></span>
    * <span data-ttu-id="808be-112">É possível definir várias exceções de trabalho com diferentes políticas de realocação de itens para permitir que os trabalhadores do depósito escolham uma com base nas necessidades da remessa que eles estão processando.</span><span class="sxs-lookup"><span data-stu-id="808be-112">It’s possible to define several work exceptions with different item reallocation policies to enable the warehouse worker to choose one based on the needs of the shipment that they are processing.</span></span>  
3. <span data-ttu-id="808be-113">No campo Código de exceção do trabalho, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="808be-113">In the Work exception code field, type a value.</span></span>
    * <span data-ttu-id="808be-114">Dê à exceção de trabalho um título para indicar para que ela é usada.</span><span class="sxs-lookup"><span data-stu-id="808be-114">Give the work exception a title to indicate what it’s used for.</span></span> <span data-ttu-id="808be-115">Por exemplo, manual de separação insuficiente.</span><span class="sxs-lookup"><span data-stu-id="808be-115">For example, Short picking manual.</span></span>  
4. <span data-ttu-id="808be-116">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="808be-116">In the Description field, type a value.</span></span>
5. <span data-ttu-id="808be-117">No campo Tipo de exceção, selecione "Separação insuficiente".</span><span class="sxs-lookup"><span data-stu-id="808be-117">In the Exception type field, select 'Short pick'.</span></span>
6. <span data-ttu-id="808be-118">Marque a caixa de seleção Ajustar estoque.</span><span class="sxs-lookup"><span data-stu-id="808be-118">Select the Adjust inventory check box.</span></span>
    * <span data-ttu-id="808be-119">Essa opção significa que o estoque será automaticamente ajustado para 0 na localização separada insuficiente.</span><span class="sxs-lookup"><span data-stu-id="808be-119">This option means that inventory will automatically be adjusted to 0 at the short picked location.</span></span>  
7. <span data-ttu-id="808be-120">No campo Código de tipo de ajuste padrão, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="808be-120">In the Default adjustment type code field, enter or select a value.</span></span>
    * <span data-ttu-id="808be-121">Por exemplo, na USMF, você pode selecionar "Remover Res Adj Out".</span><span class="sxs-lookup"><span data-stu-id="808be-121">For example, in USMF you can select 'Remove Res Adj Out'.</span></span>  
8. <span data-ttu-id="808be-122">No campo Realocação de item, selecione "Manual".</span><span class="sxs-lookup"><span data-stu-id="808be-122">In the Item reallocation field, select 'Manual'.</span></span>
    * <span data-ttu-id="808be-123">Se você selecionar Manual, ou Automática e Manual, o trabalhador do depósito precisará estar habilitado para usar a realocação manual.</span><span class="sxs-lookup"><span data-stu-id="808be-123">If you select Manual, or Automatic and Manual, the warehouse worker needs to be enabled to use manual reallocation.</span></span>  

## <a name="set-up-a-worker-to-use-manual-item-reallocation"></a><span data-ttu-id="808be-124">Configurar um trabalhador para usar a realocação de item manual</span><span class="sxs-lookup"><span data-stu-id="808be-124">Set up a worker to use manual item reallocation</span></span>
1. <span data-ttu-id="808be-125">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="808be-125">Close the page.</span></span>
2. <span data-ttu-id="808be-126">Vá para Gerenciamento de depósito > Configuração > Trabalhador.</span><span class="sxs-lookup"><span data-stu-id="808be-126">Go to Warehouse management > Setup > Worker.</span></span>
3. <span data-ttu-id="808be-127">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="808be-127">Click Edit.</span></span>
4. <span data-ttu-id="808be-128">Na lista, selecione o trabalhador 24.</span><span class="sxs-lookup"><span data-stu-id="808be-128">In the list, select worker 24.</span></span>
5. <span data-ttu-id="808be-129">Expanda a seção Trabalho.</span><span class="sxs-lookup"><span data-stu-id="808be-129">Expand the Work section.</span></span>
6. <span data-ttu-id="808be-130">Selecione Sim no campo Permitir realocação manual de itens.</span><span class="sxs-lookup"><span data-stu-id="808be-130">Select Yes in the Allow manual item reallocation field.</span></span>

