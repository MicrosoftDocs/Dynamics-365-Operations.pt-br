---
title: Configurar realocação de item de pouca seleção
description: Este procedimento mostra como permitir que os trabalhadores do depósito encontrem rapidamente localizações alternativas se não houver estoque suficiente na localização para a qual eles foram direcionados.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWorkException, WHSWorker
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e860a54c2306f8140947b77cdcb538160a84e06f
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3216795"
---
# <a name="set-up-short-picking-item-reallocation"></a><span data-ttu-id="0eee6-103">Configurar realocação de item de pouca seleção</span><span class="sxs-lookup"><span data-stu-id="0eee6-103">Set up short picking item reallocation</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="0eee6-104">Este procedimento mostra como permitir que os trabalhadores do depósito encontrem rapidamente localizações alternativas se não houver estoque suficiente na localização para a qual eles foram direcionados.</span><span class="sxs-lookup"><span data-stu-id="0eee6-104">This procedure shows you how to enable warehouse workers to quickly find alternative locations if there isn't sufficient inventory at the location they've been directed to.</span></span> <span data-ttu-id="0eee6-105">É possível usar um processo de realocação automática, que usa as diretivas de localização para recuperar as mercadorias se elas estiverem disponíveis em outras localizações.</span><span class="sxs-lookup"><span data-stu-id="0eee6-105">It's possible to use an automatic re-allocation process, which uses location directives to retrieve the goods if they're available at another location.</span></span> <span data-ttu-id="0eee6-106">Como alternativa, quando a realocação manual for usada, uma lista das localizações com a quantidade disponível é mostrada no dispositivo móvel, permitindo que o trabalhador do depósito escolha em qual localização usar o estoque.</span><span class="sxs-lookup"><span data-stu-id="0eee6-106">Alternatively, when manual re-allocation is used, a list of the locations with the available quantity is shown on the mobile device, allowing the warehouse worker to choose which location to use inventory from.</span></span> <span data-ttu-id="0eee6-107">Você pode usar este procedimento na empresa USMF de dados de demonstração.</span><span class="sxs-lookup"><span data-stu-id="0eee6-107">You can use this procedure in demo data company USMF.</span></span> <span data-ttu-id="0eee6-108">Este procedimento é para um recurso que foi adicionado na versão 1611 do Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="0eee6-108">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="set-up-work-exceptions"></a><span data-ttu-id="0eee6-109">Configurar exceções de trabalho</span><span class="sxs-lookup"><span data-stu-id="0eee6-109">Set up work exceptions</span></span>
1. <span data-ttu-id="0eee6-110">No **Painel de navegação**, acesse **Gerenciamento de depósito > Configuração > Trabalho > Exceções de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="0eee6-110">In the **Navigation pane**, go to **Warehouse management > Setup > Work > Work exceptions**.</span></span>
2. <span data-ttu-id="0eee6-111">Clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="0eee6-111">Click **New**.</span></span> <span data-ttu-id="0eee6-112">É possível definir várias exceções de trabalho com diferentes políticas de realocação de itens para permitir que os trabalhadores do depósito escolham uma com base nas necessidades da remessa que eles estão processando.</span><span class="sxs-lookup"><span data-stu-id="0eee6-112">It's possible to define several work exceptions with different item reallocation policies to enable the warehouse worker to choose one based on the needs of the shipment that they are processing.</span></span>  
3. <span data-ttu-id="0eee6-113">No campo **Código de exceção do trabalho**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="0eee6-113">In the **Work exception code** field, type a value.</span></span> <span data-ttu-id="0eee6-114">Dê à exceção de trabalho um título para indicar para que ela é usada.</span><span class="sxs-lookup"><span data-stu-id="0eee6-114">Give the work exception a title to indicate what it's used for.</span></span> <span data-ttu-id="0eee6-115">Por exemplo, manual de separação insuficiente.</span><span class="sxs-lookup"><span data-stu-id="0eee6-115">For example, Short picking manual.</span></span>  
4. <span data-ttu-id="0eee6-116">No campo **Descrição**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="0eee6-116">In the **Description** field, type a value.</span></span>
5. <span data-ttu-id="0eee6-117">No campo **Tipo de exceção**, selecione "Separação insuficiente".</span><span class="sxs-lookup"><span data-stu-id="0eee6-117">In the **Exception** type field, select 'Short pick'.</span></span>
6. <span data-ttu-id="0eee6-118">Marque a caixa de seleção **Ajustar estoque**.</span><span class="sxs-lookup"><span data-stu-id="0eee6-118">Select the **Adjust inventory** check box.</span></span> <span data-ttu-id="0eee6-119">Essa opção significa que o estoque será automaticamente ajustado para 0 na localização separada insuficiente.</span><span class="sxs-lookup"><span data-stu-id="0eee6-119">This option means that inventory will automatically be adjusted to 0 at the short picked location.</span></span>  
7. <span data-ttu-id="0eee6-120">No campo **Código de tipo de ajuste padrão**, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="0eee6-120">In the **Default adjustment type code** field, enter or select a value.</span></span> <span data-ttu-id="0eee6-121">Por exemplo, na USMF, você pode selecionar "Remover Res Adj Out".</span><span class="sxs-lookup"><span data-stu-id="0eee6-121">For example, in USMF you can select 'Remove Res Adj Out'.</span></span>  
8. <span data-ttu-id="0eee6-122">No campo **Realocação de item**, selecione "Manual".</span><span class="sxs-lookup"><span data-stu-id="0eee6-122">In the **Item reallocation** field, select 'Manual'.</span></span> <span data-ttu-id="0eee6-123">Se você selecionar Manual, ou Automática e Manual, o trabalhador do depósito precisará estar habilitado para usar a realocação manual.</span><span class="sxs-lookup"><span data-stu-id="0eee6-123">If you select Manual, or Automatic and Manual, the warehouse worker needs to be enabled to use manual reallocation.</span></span>  

## <a name="set-up-a-worker-to-use-manual-item-reallocation"></a><span data-ttu-id="0eee6-124">Configurar um trabalhador para usar a realocação de item manual</span><span class="sxs-lookup"><span data-stu-id="0eee6-124">Set up a worker to use manual item reallocation</span></span>
1. <span data-ttu-id="0eee6-125">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="0eee6-125">Close the page.</span></span>
2. <span data-ttu-id="0eee6-126">No **Painel de navegação**, acesse **Gerenciamento de depósito > Configuração > Trabalhador**.</span><span class="sxs-lookup"><span data-stu-id="0eee6-126">In the **Navigation pane**, go to **Warehouse management > Setup > Worker**.</span></span>
3. <span data-ttu-id="0eee6-127">Clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="0eee6-127">Click **Edit**.</span></span>
4. <span data-ttu-id="0eee6-128">Na lista, selecione o trabalhador 24.</span><span class="sxs-lookup"><span data-stu-id="0eee6-128">In the list, select worker 24.</span></span>
5. <span data-ttu-id="0eee6-129">Expanda a Guia Rápida **Trabalho**.</span><span class="sxs-lookup"><span data-stu-id="0eee6-129">Expand the **Work** fastTab.</span></span>
6. <span data-ttu-id="0eee6-130">Selecione 'Sim' no campo **Permitir realocação manual de itens**.</span><span class="sxs-lookup"><span data-stu-id="0eee6-130">Select 'Yes' in the **Allow manual item reallocation** field.</span></span>

