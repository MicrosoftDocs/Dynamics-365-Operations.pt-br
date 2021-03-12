---
title: Calcular depreciação de ativo fixo entre entidades legais
description: A depreciação de ativo fixo pode ser executada nas entidades legais em uma única etapa.
author: saraschi2
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetParameters, AssetProposalDepreciation, DefaultDashboard, LedgerJournalTable
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8b09bbe4d0143aa521ca0a4cf67e86b7165b0f4f
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4968945"
---
# <a name="calculate-fixed-asset-depreciation-across-legal-entities"></a><span data-ttu-id="0177d-103">Calcular depreciação de ativo fixo entre entidades legais</span><span class="sxs-lookup"><span data-stu-id="0177d-103">Calculate fixed asset depreciation across legal entities</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="0177d-104">A depreciação de ativo fixo pode ser executada nas entidades legais em uma única etapa.</span><span class="sxs-lookup"><span data-stu-id="0177d-104">Fixed asset depreciation can be run across legal entities in a single step.</span></span> <span data-ttu-id="0177d-105">Este procedimento mostra como configurar e executar o processo para várias entidades legais.</span><span class="sxs-lookup"><span data-stu-id="0177d-105">This procedure shows you to how set up and run the process for multiple legal entities.</span></span> <span data-ttu-id="0177d-106">Ela usa a função de contador e os dados de demonstração da entidade legal de USMF.</span><span class="sxs-lookup"><span data-stu-id="0177d-106">It uses the accountant role and demo data for the USMF legal entity.</span></span>


## <a name="set-up-cross-company-depreciation-run-journals"></a><span data-ttu-id="0177d-107">Configurar diários de execução de depreciação interempresariais</span><span class="sxs-lookup"><span data-stu-id="0177d-107">Set up cross company depreciation run journals</span></span>
1. <span data-ttu-id="0177d-108">Vá para Ativos fixos > Configuração > Parâmetros de ativos fixos.</span><span class="sxs-lookup"><span data-stu-id="0177d-108">Go to Fixed assets > Setup > Fixed assets parameters.</span></span>
2. <span data-ttu-id="0177d-109">Expanda a seção Propostas de ativos fixos.</span><span class="sxs-lookup"><span data-stu-id="0177d-109">Expand the Fixed asset proposals section.</span></span>
3. <span data-ttu-id="0177d-110">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="0177d-110">Click Add.</span></span>
4. <span data-ttu-id="0177d-111">No campo Nível de lançamento, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="0177d-111">In the Posting layer field, enter or select a value.</span></span>
5. <span data-ttu-id="0177d-112">No campo Diário, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="0177d-112">In the Journal name field, enter or select a value.</span></span>
    * <span data-ttu-id="0177d-113">Repita a configuração do diário na página dos parâmetros de Ativos fixos em cada entidade legal.</span><span class="sxs-lookup"><span data-stu-id="0177d-113">Repeat the journal setup on the Fixed asset parameters page in each legal entity.</span></span>  

## <a name="depreciation-run"></a><span data-ttu-id="0177d-114">Execução de depreciação</span><span class="sxs-lookup"><span data-stu-id="0177d-114">Depreciation run</span></span>
1. <span data-ttu-id="0177d-115">Ir para Ativos fixos > Entradas de diário > Criar proposta de depreciação.</span><span class="sxs-lookup"><span data-stu-id="0177d-115">Go to Fixed assets > Journal entries > Create depreciation proposal.</span></span>
2. <span data-ttu-id="0177d-116">No campo Nível de lançamento, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="0177d-116">In the Posting layer field, enter or select a value.</span></span>
    * <span data-ttu-id="0177d-117">O nome de diário usará como padrão os parâmetros de Ativo fixo.</span><span class="sxs-lookup"><span data-stu-id="0177d-117">The journal name will default from the Fixed asset parameters.</span></span> <span data-ttu-id="0177d-118">É possível alterá-lo aqui para a entidade legal atual.</span><span class="sxs-lookup"><span data-stu-id="0177d-118">It can be changed here for the current legal entity.</span></span>  
3. <span data-ttu-id="0177d-119">No campo Para data, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="0177d-119">In the To date field, enter a date.</span></span>
    * <span data-ttu-id="0177d-120">Selecione as entidades legais a serem incluídas na execução da depreciação.</span><span class="sxs-lookup"><span data-stu-id="0177d-120">Select the legal entities to be included in the depreciation run.</span></span>  
    * <span data-ttu-id="0177d-121">Somente as entidades legais com diários configurados para Propostas de ativos fixos na página Parâmetros do ativo fixo serão mostradas na lista.</span><span class="sxs-lookup"><span data-stu-id="0177d-121">Only legal entities with journals set up for Fixed asset proposals on the Fixed asset parameters page will be shown in the list.</span></span>  
4. <span data-ttu-id="0177d-122">Selecione Sim no campo Lançar diários.</span><span class="sxs-lookup"><span data-stu-id="0177d-122">Select Yes in the Post journals field.</span></span>
    * <span data-ttu-id="0177d-123">Os campos de filtragem incluem todos os ativos fixos, grupos e registros das entidades legais selecionadas para esta execução.</span><span class="sxs-lookup"><span data-stu-id="0177d-123">Filtering fields include all fixed assets, groups, and books for the legal entities selected for this depreciation run.</span></span>  
    * <span data-ttu-id="0177d-124">A opção Processamento em lotes está habilitada por padrão.</span><span class="sxs-lookup"><span data-stu-id="0177d-124">The Batch processing option is enabled by default.</span></span> <span data-ttu-id="0177d-125">Quando essa opção é habilitada, a criação e a postagem de diário de depreciação é executada em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="0177d-125">When this option is enabled, the depreciation journal creation and posting will run in the background.</span></span>  
5. <span data-ttu-id="0177d-126">Clique em Criar diário.</span><span class="sxs-lookup"><span data-stu-id="0177d-126">Click Create journal.</span></span>
6. <span data-ttu-id="0177d-127">Ir para Ativos fixos > Entradas de diário > Diário de ativos fixos.</span><span class="sxs-lookup"><span data-stu-id="0177d-127">Go to Fixed assets > Journal entries > Fixed assets journal.</span></span>

