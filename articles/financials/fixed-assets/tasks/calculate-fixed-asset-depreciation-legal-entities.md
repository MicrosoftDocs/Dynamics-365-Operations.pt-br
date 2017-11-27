--- 
title: "Calcular depreciação de ativo fixo entre entidades legais"
description: "Este procedimento mostra como configurar e executar o processo para várias entidades legais."
author: saraschi2
manager: AnnBe
ms.date: 11/02/2017
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
ms.sourcegitcommit: d804480167414cd038f8229db312dc9c52d131f8
ms.openlocfilehash: 4c45da124136b7fecb916d2ff9098c8ffeff6cb1
ms.contentlocale: pt-br
ms.lasthandoff: 11/02/2017

---
# <a name="calculate-fixed-asset-depreciation-across-legal-entities"></a><span data-ttu-id="2ff2a-103">Calcular depreciação de ativo fixo entre entidades legais</span><span class="sxs-lookup"><span data-stu-id="2ff2a-103">Calculate fixed asset depreciation across legal entities</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="2ff2a-104">A depreciação de ativo fixo pode ser executada nas entidades legais em uma única etapa.</span><span class="sxs-lookup"><span data-stu-id="2ff2a-104">Fixed asset depreciation can be run across legal entities in a single step.</span></span> <span data-ttu-id="2ff2a-105">Este procedimento mostra como configurar e executar o processo para várias entidades legais.</span><span class="sxs-lookup"><span data-stu-id="2ff2a-105">This procedure shows you to how set up and run the process for multiple legal entities.</span></span> <span data-ttu-id="2ff2a-106">Ele usa a função de contador.</span><span class="sxs-lookup"><span data-stu-id="2ff2a-106">It uses the accountant role.</span></span>  

<span data-ttu-id="2ff2a-107">Este registro usa a empresa de dados de demonstração USMF.</span><span class="sxs-lookup"><span data-stu-id="2ff2a-107">This recording uses the USMF demo company.</span></span>


<span data-ttu-id="2ff2a-108">Subtarefa de etapas (16): Configurar diários de execução de depreciação interempresarial.</span><span class="sxs-lookup"><span data-stu-id="2ff2a-108">Steps (16) Sub-task: Set up cross company depreciation run journals.</span></span> 

1. <span data-ttu-id="2ff2a-109">Primeiro, você deve configurar os diários a serem usados na depreciação interempresarial executada em cada entidade legal.</span><span class="sxs-lookup"><span data-stu-id="2ff2a-109">First, you must set up the journals to be used in the cross company depreciation run in each legal entity.</span></span> <span data-ttu-id="2ff2a-110">Vá para Ativos fixos > Configuração > Parâmetros de ativos fixos.</span><span class="sxs-lookup"><span data-stu-id="2ff2a-110">Go to Fixed assets > Setup > Fixed assets parameters.</span></span> 
2. <span data-ttu-id="2ff2a-111">Expanda a seção Propostas de ativos fixos.</span><span class="sxs-lookup"><span data-stu-id="2ff2a-111">Expand the Fixed asset proposals section.</span></span> 
3. <span data-ttu-id="2ff2a-112">Crie um registro com o nome do diário a ser usado para cada nível de lançamento na entidade legal.</span><span class="sxs-lookup"><span data-stu-id="2ff2a-112">Create a record with the journal name to be used for each posting layer in the legal entity.</span></span> <span data-ttu-id="2ff2a-113">Se os registros não forem lançados na contabilidade, a opção Nenhum nível de lançamento deve ser selecionada com o diário associado.</span><span class="sxs-lookup"><span data-stu-id="2ff2a-113">If books do not post to the general ledger, then the None posting layer should be selected with the associated journal.</span></span> <span data-ttu-id="2ff2a-114">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="2ff2a-114">Click Add.</span></span> 
4. <span data-ttu-id="2ff2a-115">No campo Nível de lançamento, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="2ff2a-115">In the Posting layer field, enter or select a value.</span></span> 
5. <span data-ttu-id="2ff2a-116">No campo Diário, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="2ff2a-116">In the Journal name field, enter or select a value.</span></span> 
6. <span data-ttu-id="2ff2a-117">Repita a configuração do diário na página dos parâmetros de Ativos fixos em cada entidade legal.</span><span class="sxs-lookup"><span data-stu-id="2ff2a-117">Repeat the journal setup on the Fixed asset parameters page in each legal entity.</span></span> 

<span data-ttu-id="2ff2a-118">Subtarefa: Calcular depreciação</span><span class="sxs-lookup"><span data-stu-id="2ff2a-118">Sub-task: Calculate depreciation</span></span>

1. <span data-ttu-id="2ff2a-119">Use a página Criar proposta de depreciação para iniciar a execução da depreciação nas entidades legais.</span><span class="sxs-lookup"><span data-stu-id="2ff2a-119">Use the Create depreciation proposal page to start your depreciation run across legal entities.</span></span> <span data-ttu-id="2ff2a-120">Ir para Ativos fixos > Entradas de diário > Criar proposta de depreciação.</span><span class="sxs-lookup"><span data-stu-id="2ff2a-120">Go to Fixed assets > Journal entries > Create depreciation proposal.</span></span> 
2. <span data-ttu-id="2ff2a-121">No campo Nível de lançamento, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="2ff2a-121">In the Posting layer field, enter or select a value.</span></span> 
3. <span data-ttu-id="2ff2a-122">O nome de diário usará como padrão os parâmetros de Ativo fixo.</span><span class="sxs-lookup"><span data-stu-id="2ff2a-122">The journal name will default from the Fixed asset parameters.</span></span> <span data-ttu-id="2ff2a-123">É possível alterá-lo aqui para a entidade legal atual.</span><span class="sxs-lookup"><span data-stu-id="2ff2a-123">It can be changed here for the current legal entity.</span></span> 
4. <span data-ttu-id="2ff2a-124">No campo Para data, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="2ff2a-124">In the To date field, enter a date.</span></span> 
5. <span data-ttu-id="2ff2a-125">Selecione as entidades legais a serem incluídas na execução da depreciação.</span><span class="sxs-lookup"><span data-stu-id="2ff2a-125">Select the legal entities to be included in the depreciation run.</span></span> <span data-ttu-id="2ff2a-126">Somente as entidades legais com diários configurados para Propostas de ativos fixos na página Parâmetros do ativo fixo serão mostradas na lista.</span><span class="sxs-lookup"><span data-stu-id="2ff2a-126">Only legal entities with journals set up for Fixed asset proposals on the Fixed asset parameters page will be shown in the list.</span></span> 
6. <span data-ttu-id="2ff2a-127">Quando habilitada, a opção Lançar diários lançará automaticamente os diários de depreciação quando eles forem criados.</span><span class="sxs-lookup"><span data-stu-id="2ff2a-127">When enabled, the Post journals option will automatically post the depreciation journals when they are created.</span></span> <span data-ttu-id="2ff2a-128">Quando não selecionada, os diários serão criados, mas não lançados, portanto, você poderá revisar os detalhes antes de lançá-los.</span><span class="sxs-lookup"><span data-stu-id="2ff2a-128">When not selected, the journals will be created, but not posted, so you can review the details before posting.</span></span> <span data-ttu-id="2ff2a-129">Selecione Sim no campo Lançar diários.</span><span class="sxs-lookup"><span data-stu-id="2ff2a-129">Select Yes in the Post journals field.</span></span> 
7. <span data-ttu-id="2ff2a-130">Os campos de filtragem incluem todos os ativos fixos, grupos e registros das entidades legais selecionadas para esta execução.</span><span class="sxs-lookup"><span data-stu-id="2ff2a-130">Filtering fields include all fixed assets, groups, and books for the legal entities selected for this depreciation run.</span></span> 
8. <span data-ttu-id="2ff2a-131">A opção Processamento em lotes está habilitada por padrão.</span><span class="sxs-lookup"><span data-stu-id="2ff2a-131">The Batch processing option is enabled by default.</span></span> <span data-ttu-id="2ff2a-132">Quando essa opção é habilitada, a criação e a postagem de diário de depreciação é executada em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="2ff2a-132">When this option is enabled, the depreciation journal creation and posting will run in the background.</span></span> 
9. <span data-ttu-id="2ff2a-133">Clique em Criar diário.</span><span class="sxs-lookup"><span data-stu-id="2ff2a-133">Click Create journal.</span></span> 
10. <span data-ttu-id="2ff2a-134">Você deve exibir os diários de depreciação criados nas respectivas entidades legais.</span><span class="sxs-lookup"><span data-stu-id="2ff2a-134">You must view the depreciation journals created in the respective legal entities.</span></span> <span data-ttu-id="2ff2a-135">Ir para Ativos fixos > Entradas de diário > Diário de ativos fixos.</span><span class="sxs-lookup"><span data-stu-id="2ff2a-135">Go to Fixed assets > Journal entries > Fixed assets journal.</span></span>

